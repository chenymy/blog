## 访问github方法

1. ### 方法一

   修改hosts文件

   - 查询DNS和IP

     通过网站https://tool.chinaz.com/dns

     查询 github.com 和 github.global.ssl.fastly.net 所对应ip

   - 修改hosts文件

     以管理员身份运行txt，再打开 C:\Windows\System32\drivers\etc\hosts文件，回车输入

     ```
     20.205.243.166       github.com
     199.16.156.11		 github.global.ssl.fastly.net
     ```

   - 重启系统或刷新DNS(获取不需要)

     打开cmd，输入 ipconfig /flushdns

