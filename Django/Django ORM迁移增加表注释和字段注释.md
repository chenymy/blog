# Django ORM迁移增加表注释和字段注释

## 环境说明

```bash
django == 2.2.0
```

## 表注释

利用`model._meta.verbose_name`增加针对mysql表注释的处理

修改`django/db/backends/base/schema.py` 文件，`create_model`函数，如下：

```python
# 利用[model._meta.verbose_name]增加针对mysql表注释的处理
if self.connection.client.executable_name == 'mysql' and model._meta.verbose_name:
	sql += " COMMENT '%s'" % model._meta.verbose_name
```

![image-20240511231403198](https://s2.loli.net/2024/05/11/tzBgM8mo3qD6f7V.png)

## 字段注释

利用`field.verbose_name`增加针对mysql字段注释的处理

修改`django/db/backends/base/schema.py` 文件，`column_sql`函数，如下：

```python
# 利用[field.verbose_name]增加针对mysql字段注释的处理
if self.connection.client.executable_name == 'mysql' and field.verbose_name:
	sql += " COMMENT '%s'" % field.verbose_name
```

![image-20240511231307038](https://s2.loli.net/2024/05/11/mOrcLNQwa56EKuC.png)