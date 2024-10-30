## Windows下右键新建md文件

原本创建.md文件需要首先打开markdown文本编辑器，如Typora，或者新建.txt文件然后修改后缀名，本文介绍了如何在Windows操作系统中添加右键创建.md文件的方法。

### 步骤

1. 在磁盘任意位置新建一个文件，后缀为`.reg`

2. 打开编辑刚刚创建好的注册表文件，写入以下内容并保存：

   ```
   Windows Registry Editor Version 5.00
   [HKEY_CLASSES_ROOT\.md]
   @="Typora.exe"
   [HKEY_CLASSES_ROOT\.md\ShellNew]
   "NullFile"=""
   [HKEY_CLASSES_ROOT\Typora.exe]
   @="Markdown"
   ```

   `@="Typora.exe"` 代表的是指定.md文件的运行程序

   `@="Markdown"` 代表的是右键时默认的文件名字，这样写新建为`新建Markdown.md`文件，而且右键菜单中显示`MarkDown`

   文件名可以随便设置，但是后缀必须是`.reg`文件，保存类型一定要是`文本文档(*.txt)`，编码选择`Unicode`，非常重要！！！

   保存文件后，双击运行，修改注册表即可，现在右键即可达到预期效果，如果不行，请重启一下。