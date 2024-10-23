## 使用VMware虚拟机安装RHEL7（RedHat Enterprise Linux7.6）步骤

#### 准备工具

1. VMware Workstation 17 
2. RedHat Enterprise Linux 7.6 镜像文件

#### 在虚拟机内设置操作系统的硬件标准

1. 单机 “创建新的虚拟机” 选项

   ![image-20240303215039646](https://gitee.com/chenymy/picbed/raw/master/img/image-20240303215039646-1709473976297-1.png)

2. 在弹出的 “新建虚拟机向导” 界面中选择 “典型” 单选按钮，然后单击 “下一步” 按钮

   ![image-20240303221544225](https://gitee.com/chenymy/picbed/raw/master/img/image-20240303221544225.png)

3. 选中 “稍后安装操作系统” 单选按钮，然后点击 “下一步” 按钮

   ![image-20240303221653698](https://gitee.com/chenymy/picbed/raw/master/img/image-20240303221653698.png)

4. 将客户机操作系统的类型选择为 “Linux” ，版本为 “Red Hat Enterprise Linux 7 64 位” ，然后单击 “下一步” 按钮

   ![image-20240303221855101](https://gitee.com/chenymy/picbed/raw/master/img/image-20240303221855101.png)

5. 填写 “虚拟机名称” 字段，并在选择安装位置之后单击 “下一步” 按钮

   ![image-20240303222029680](https://gitee.com/chenymy/picbed/raw/master/img/image-20240303222029680.png)

6. 将虚拟机系统的 “最大磁盘大小” 设置为 20.0GB（默认即可） ，选中 “将虚拟磁盘拆分成多个文件” 单选按钮，然后点击 “下一步” 按钮

   ![image-20240303222345001](https://gitee.com/chenymy/picbed/raw/master/img/image-20240303222345001.png)

7. 单击 “自定义硬件” 按钮

   ![image-20240303222454680](https://gitee.com/chenymy/picbed/raw/master/img/image-20240303222454680.png)

8. 根据你的物理机性能设置虚拟机系统内容，建议设置为2GB，最低不低于1GB（如果你的物理机内存充沛，现在可以多分配一点，系统安装完成后再降低，这样可以加快安装速度）

   ![image-20240303222711165](https://gitee.com/chenymy/picbed/raw/master/img/image-20240303222711165.png)

9. 根据你的物理机性能设置虚拟机系统CPU处理的数量以及每个处理器的核心数量

   ![image-20240303222835277](https://gitee.com/chenymy/picbed/raw/master/img/image-20240303222835277.png)

10. “新 CD/DVD (SATA)” 应在 “使用ISO镜像文件” 中选择下载的RHEL系统镜像文件

    ![image-20240303223216659](https://gitee.com/chenymy/picbed/raw/master/img/image-20240303223216659.png)

11. 其余选项默认即可（USB控制器、声卡等不需要的设备可以移除），然后单击 “关闭” 按钮

    ![image-20240303223514714](https://gitee.com/chenymy/picbed/raw/master/img/image-20240303223514714.png)

12. 返回到虚拟机配置向导界面后单击 “完成” 按钮，虚拟机的配置顺利完成

    ![image-20240303223616325](https://gitee.com/chenymy/picbed/raw/master/img/image-20240303223616325.png)

#### 安装您的Linux系统

1. 在虚拟机管理界面中单击 “开启此虚拟机” 按钮，然后可以看到RHEL7.6系统安装界面

   ![image-20240303223808104](https://gitee.com/chenymy/picbed/raw/master/img/image-20240303223808104.png)

2. 此时通过键盘方向键选择 “Install Rad Hat Enterprise Linux 7.6” 选项来直接安装Linux系统（鼠标先点击安装界面从而将键盘切换到Linux系统中）

   ![image-20240303224035580](https://gitee.com/chenymy/picbed/raw/master/img/image-20240303224035580.png)

3. 按下回车键后开始加载安装镜像，请耐心等待

   ![image-20240303224254894](https://gitee.com/chenymy/picbed/raw/master/img/image-20240303224254894.png)

4. 选择系统的安装语言后点击 “Continue” 按钮

   ![image-20240303224416928](https://gitee.com/chenymy/picbed/raw/master/img/image-20240303224416928.png)

5. 在安装主界面中单击 “DATE & TIME” 选项

   ![image-20240303224832533](https://gitee.com/chenymy/picbed/raw/master/img/image-20240303224832533.png)

6. 在 “DATE & TIME” 界面中选择和确认时区和时间，然后单击左上角的 “Done” 按钮返回安装界面![image-20240303224720836](https://gitee.com/chenymy/picbed/raw/master/img/image-20240303224720836.png)

7. 在安装主界面中单击 “SOFTWARE SELECTION” 选项 

   ![image-20240303225052736](https://gitee.com/chenymy/picbed/raw/master/img/image-20240303225052736.png)

8. 在 “SOFTWARE SELECTION” 界面中单击选中 “Server with GUI” 单选按钮，可以实际情况选择安装环境工具，然后单击左上角的 “Done” 按钮返回安装主界面

   ![image-20240303225212164](https://gitee.com/chenymy/picbed/raw/master/img/image-20240303225212164.png)

9. 在安装主界面中单击 “NSTALLATION DESTINATION” 选项

   ![image-20240303225716697](https://gitee.com/chenymy/picbed/raw/master/img/image-20240303225716697.png)

10. 在 “NSTALLATION DESTINATION” 选择安装媒介并设置分区（默认即可），然后单击左上角的 “Done” 按钮返回安装主界面

    ![image-20240303230330064](https://gitee.com/chenymy/picbed/raw/master/img/image-20240303230330064.png)

11. 在安装主界面单击 “NETWORK & HOSTNAME” 选项

    ![image-20240303230413129](https://gitee.com/chenymy/picbed/raw/master/img/image-20240303230413129.png)

12. 在 "" 界面设置 “Host name”，打开 “Ethernet”，然后单击左上角的 “Done” 按钮返回安装主界面

    ![image-20240303230050680](https://gitee.com/chenymy/picbed/raw/master/img/image-20240303230050680.png)

13. 在安装主界面中单击 “Begin Installation” 按钮

    ![image-20240303230810267](https://gitee.com/chenymy/picbed/raw/master/img/image-20240303230810267.png)

14. 在 “CONFIGURATION” 界面可以看到安装进度，在此处选择 "ROOT PASSWORD" 选项

    ![image-20240303230915509](https://gitee.com/chenymy/picbed/raw/master/img/image-20240303230915509.png)

15. 在 “ROOT PASSWORD” 页面设置 root 管理员的密码。若坚持用弱口令的密码则需要单击2次坐上角的 “Done” 按钮才可以确认

    ![image-20240303230949814](https://gitee.com/chenymy/picbed/raw/master/img/image-20240303230949814.png)

16. 在 “CONFIGURATION” 界面可以看到安装进度，在此处选择 "USER CREATION" 选项

    ![image-20240303231032381](https://gitee.com/chenymy/picbed/raw/master/img/image-20240303231032381.png)

17. 在 “CREATE USER” 页面填写用户和密码，创建一个普通用户， 然后单击左上角的 “Done” 按钮返回安装主界面

    ![image-20240303231115145](https://gitee.com/chenymy/picbed/raw/master/img/image-20240303231115145.png)

18. Linux系统安装需要一点时间，期间耐心等待即可，安装完成后单击 “Reboot” 按钮

    ![image-20240303231858961](https://gitee.com/chenymy/picbed/raw/master/img/image-20240303231858961.png)

19. 重启系统后将看到系统的初始化界面，单击 “LICENSE INFORMATION” 选项

    ![image-20240303232020023](https://gitee.com/chenymy/picbed/raw/master/img/image-20240303232020023.png)

20. 在 “LICENSE INFORMATION” 界面中选中 “I accept the license agreement” 复选框，然后单击左上角的 “Done” 按钮返回初始化界面

    ![image-20240303232234411](https://gitee.com/chenymy/picbed/raw/master/img/image-20240303232234411.png)

21. 返回初始化界面后单击 “FINISH CONFIGURATION” 按钮，系统将会重启

    ![image-20240303232340578](https://gitee.com/chenymy/picbed/raw/master/img/image-20240303232340578.png)

22. 系统重启后输入用户和密码即可登录

    ![image-20240303232630813](https://gitee.com/chenymy/picbed/raw/master/img/image-20240303232630813.png)

23. 登录成功后终于看到RHEL系统的 “WelCome” 界面，在界面中选择默认语言 "English (United States)" ,然后单击 "Next" 按钮

    ![image-20240303232955152](https://gitee.com/chenymy/picbed/raw/master/img/image-20240303232955152.png)

24. 将系统的输入来源类型选择" English (US)"，然后单击 "Next" 按钮

    ![image-20240303233043632](https://gitee.com/chenymy/picbed/raw/master/img/image-20240303233043632.png)

25. 将系统的隐私权限关闭，然后单击 "Next" 按钮

    ![image-20240303233256512](https://gitee.com/chenymy/picbed/raw/master/img/image-20240303233256512.png)

26. 跳过连接其他网络账号

    ![image-20240303233326685](https://gitee.com/chenymy/picbed/raw/master/img/image-20240303233326685.png)

27. 在界面中单击 ”“ 按钮，至此，RHEL 7 系统完成了全部安装工作

    ![image-20240303233459516](https://gitee.com/chenymy/picbed/raw/master/img/image-20240303233459516.png)

28. 快速开始界面，关掉即可

    ![image-20240303233556290](https://gitee.com/chenymy/picbed/raw/master/img/image-20240303233556290.png)

29. 人生苦短，我用python！
