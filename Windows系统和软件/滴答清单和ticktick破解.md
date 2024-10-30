## 滴答清单/ticktick 破解

1. #### 下载软件和工具

   软件是滴答官网下载，滴答国内，ticktick国外，我用的6.1.1

   https://www.dida365.com/

   https://www.ticktick.com/

   工具是反编译工具doSpy，下载最新版就行，我用的6.1.9

   https://github.com/kkwpsv/dnSpy/tags

2. #### 步骤

   - 安装滴答清单，使用dnSpy到安装目录下打开ticktick.exe，打开ticktick_WPF.Models.UserModel

   - 找到public DateTime 的 get 方法，右键编辑方法

     修改如下所示

     ```c#
     // ticktick_WPF.Models.UserModel
     // Token: 0x170015CA RID: 5578
     // (get) Token: 0x0600A23F RID: 41535 RVA: 0x000597B3 File Offset: 0x000579B3
     // (set) Token: 0x0600A240 RID: 41536 RVA: 0x000597C8 File Offset: 0x000579C8
     public DateTime? proEndDate
     {
     	[CompilerGenerated]
     	get
     	{
     		return new DateTime?(new DateTime(2030, 12, 25));
     	}
     	[CompilerGenerated]
     	set
     	{
     		this.<proEndDate>k__BackingField = value;
     	}
     }
     ```

   - 找到public bool pro 的 get 方法，右键编辑方法

     修改如下所示

     ```c#
     // ticktick_WPF.Models.UserModel
     // Token: 0x0600A249 RID: 41545 RVA: 0x0001367C File Offset: 0x0001187C
     [CompilerGenerated]
     public bool get_pro()
     {
     	return true;
     }
     ```

     的撒

3. #### 保存模块并退出，就能正常使用会员功能了