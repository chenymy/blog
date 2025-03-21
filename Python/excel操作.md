# openpyxl

openpyxl is a Python library to read/write Excel 2010 xlsx/xlsm/xltx/xltm files.

PyPI地址：

https://pypi.org/project/openpyxl/

官网文档：

https://openpyxl.readthedocs.io/

## 安装

```python
pip install openpyxl
# 或从清华源安装
pip install -i https://pypi.tuna.tsinghua.edu.cn/simple openpyxl
```

## 数据验证

输入验证支持的方法有以下几种：

1. list
2. wohole
3. decimal
4. date
5. time
6. textLength
7. custom

### list模式

list就是从列表中选择输入。方法是：

1. 先奖励验证规则dv
2. 将需要添加在验证的单元格加入验证规则中

实例：

```python
from openpyxl import Workbook
from openpyxl.worksheet.datavalidation import DataValidation

wb = Workbook()
ws = wb.active

# Create a data-validation object with list validation
dv = DataValidation(type="list", formula1='"猫,狗,蝙蝠"', allow_blank=True, showErrorMessage=True, showInputMessage=True, errorStyle="warning")

# Optionally set a custom error message
dv.error ='你的输入值不在列表中'
dv.errorTitle = '非法输入'

# Optionally set a custom prompt message
dv.prompt = '请从列表中选择合理的输入值'
dv.promptTitle = '选择列表'

# Create some cells, and add them to the data-validation object
c1 = ws["A1"]
c1.value = "狗"
dv.add(c1)
# Or, apply the validation to a range of cells
dv.add("A1:A100")
dv.add('B1:B1048576')   # This is the same as for the whole of column B

# Add the data-validation object to the worksheet
ws.add_data_validation(dv)

wb.save('测试excel数据验证.xlsx')
```

