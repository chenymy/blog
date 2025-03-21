# 操作ppt

## ppt转pdf

### 依赖office应用的略

### 方法一

```python
pip install Spire.Presentation
```

生成的pdf有水印，去水印参考其他文档

```python
import time

from spire.presentation import *
from spire.presentation.common import *

aa = time.time()
# Create an object of Presentation class
presentation = Presentation()

# Load a presentation file
presentation.LoadFromFile("测试.pptx")

# Convert the presentation file to PDF and save it
presentation.SaveToFile("测试.pdf", FileFormat.PDF)
presentation.Dispose()
print(time.time() - aa)	# 1.6696088314056396
```

