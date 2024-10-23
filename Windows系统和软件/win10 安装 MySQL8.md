### win10 安装 MySQL8

1. 下载mysql8（仅供参考https://www.onlinedown.net/soft/3573.htm）

2. 解压

3. 在mysql8根目录下创建 my.ini 文件，配置以下信息，参考，此步在新版mysql中可省略

    ```shell
    [client]
    # 设置mysql客户端默认字符集
    default-character-set=utf8
    [mysqld]
    # 设置3306端口
    port = 3306
    # 设置mysql的安装目录
    basedir=D:\mysql-8.0.22-winx64
    # 允许最大连接数
    max_connections=20
    # 服务端使用的字符集默认为8比特编码的latin1字符集
    character-set-server=utf8mb4
    # 创建新表时将使用的默认存储引擎
    default-storage-engine=INNODB
    ```

4. 以管理员身份打开 Windows PowerShell，切换目录

    ```shell
    cd D:\mysql-8.0.22-winx64\bin
    ```

5. 初始化数据库

    ```shell
    .\mysqld.exe --initialize --console
    ```

    执行完成后，会输出 root 用户的初始默认密码，如： SD2fG6rFs*w_就是初始密码，后续登录需要用到，你也可以在登陆后修改密码。

6. 安装

    ```shell
    .\mysqld.exe install
    ```

7. 启动服务

    ```shell
    net start mysql
    ```

8. 进入mysql

    ```shell
    .\mysql.exe -u root -p
    ```

9. 进入myslq，修改密码

    ```shell
    ALTER USER 'root'@'localhost' IDENTIFIED BY '新密码';
    ```

10. 退出

    ```shell
    exit
    或
    quit
    ```

- utf8和utf8mb4的区别

​	MySQL在5.5.3之后增加了这个utf8mb4的编码，mb4就是most bytes 4的意思，专门用来兼容四 字节的unicode。好在utf8mb4是utf8的超集，除了将编码改为utf8mb4外不需要做其他转换。当 然，为了节省空间，一般情况下使用utf8也就够了。 

​	那上面说了既然utf8能够存下大部分中文汉字,那为什么还要使用utf8mb4呢? 原来mysql支持的 utf8 编码最大字符长度为 3 字节，如果遇到 4 字节的宽字符就会插入异常了。三个字节的 UTF-8 最大能编码的 Unicode 字符是 0xffff，也就是 Unicode 中的基本多文种平面(BMP)。也就是说，任 何不在基本多文本平面的 Unicode字符，都无法使用 Mysql 的 utf8 字符集存储。包括 Emoji 表情 (Emoji 是一种特殊的 Unicode 编码，常见于 ios 和 android 手机上)，和很多不常用的汉字，以及 任何新增的 Unicode 字符等等(utf8的缺点)。

- 配置环境变量（目的是为了避免在CMD窗口下操作时反复切换路径）

​	在Path下添加 D:\mysql-8.0.22-winx64\bin 

​	环境变量设置好之后，以后重新打开CMD或者Windows Powershell，就可直接输入mysql登陆 了，而不用再切换到mysql的bin目录再执行指令了。