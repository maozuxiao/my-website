# Ceiba2新服务器部署流程

## 前置条件

### 确认服务器配置满足要求

> 参考文章：https://maozuxiao.github.io/my-website/Ceiba_2_Windows_Server_Configuration_Recommendations.html

###  关闭杀毒软件
> 如果有杀毒软件，请先退出或者关闭！
> 
### 安装.NET3.5

1. 打开控制面板—程序与功能—启用或关闭Windows功能。
2. 点击到功能—将.NET3.5勾选上，点击安装，等待安装完成即可。
3. 如果安装有异常，可参考文档http://jf.streamax.com:8081/f/db78d7d76a284f3eb3ce/?dl=1
> [!CAUTION]
>
> **如果在线安装.NET3.5失败**
>
> > 方法一：采用离线安装包方式安装，点击以下链接进入微软官网去下载.NET3.5的完整安装包并安装：https://www.microsoft.com/zh-cn/download/details.aspx?id=25150
>
> **如果提示安装.NET3.5找不到源文件**
>
> > 方法二：
> >
> > 针对2016版本的源文件下载链接：
> > http://jf.streamax.com:8081/f/4395c400f8154c17859a/?dl=1
> >
> > 针对2019版本的源文件下载链接：
> > http://jf.streamax.com:8081/f/6daf042642e74d8b8e07/?dl=1
> >
> > 源文件下载后，请将该源文件放到C:\Windows\路径下，且目录不要包含中文名
> >
> > 然后再次点击打开控制面板—程序与功能—启用或关闭Windows功能
> >
> > 点击到功能—将.NET3.5勾选上，点击下一步
> >
> > 点击指定备用源路径，将上一步下载的文件夹的路径的sys文件夹全路径填写到这里，比如
> > E:\Wechat\WeChat Files\WeChat Files\wxid_5f373hh96unk21\FileStorage\File\2021-11\sources\sources\sxs（根据自己的实际路径来）然后点击安装即可
>
> **你也可以选择命令行安装**
>
> > 方法三：点击以下链接下载需要的文件：
> > http://jf.streamax.com:8081/f/e42de3c28f8249a7b172/?dl=1
> >
> > 将该源文件放到C:\Windows\路径下：
> >
> > 点击“开始”找到“Windows PowerShell”右击“以管理员身份运行”，输入如下命令：
> >
> > ```powershell
> > dism.exe /online /add-package /packagepath:C:\WINDOWS\netfx3.caB
> > ```
### 检查服务器版本

> 如果服务器版本为2008 R2，需要下载SP1补丁进行安装。
> 可点击计算机—属性，若如以下截图中有”Service Pack 1“，即表明安装了SP1补丁。



> 若未安装，请点击以下链接下载SP1补丁进行安装：
> http://download.windowsupdate.com/msdownload/update/software/svpk/2011/02/windows6.1-kb976932-x64_74865ef2562006e51d7f9333b4a8d45b7a749dab.exe

## CMS Server部署

### 下载服务端软件

访问以下链接：http://jfwiki.streamax.com:7503/web/#/172/4819
> 名称示例：[Ceiba2Srv_2.6.8.0.24_en.exe](https://streamax-file02-1304261646.cos.ap-guangzhou.myqcloud.com/STREAMAX/平台软件安装包/CB2/Ceiba2_2.6.8.0.24/Ceiba2Srv_2.6.8.0.24_en.exe)

### 安装

1. 双击exe格式的文件，点击第一步下载完成的安装包进行安装，选择 “定制安装”。
   ![定制安装](https://cdn.jsdelivr.net/gh/maozuxiao/Steamax_IMG/index.php)

2. 选择安装路径后点击确定，点击下一步，等待安装完成即可。

   ![选择安装路径](https://cdn.jsdelivr.net/gh/maozuxiao/Steamax_IMG/image-20251224112741906.png)
   
3. 安装完成后，在弹出的网络配置工具中，将流媒体IP修改为外网ip，注意服务器外网IP就是0.0.0.0，最后点击修改配置等待服务重启完成即可。

   ![设置流媒体IP为外网IP](https://cdn.jsdelivr.net/gh/maozuxiao/Steamax_IMG/image-20251224112846210.png)

   

## 补丁

> [!CAUTION]
>
> 2025年12月出现安全漏洞，如果版本等于或小于[Ceiba2Srv_2.6.8.0.24_en.exe](https://streamax-file02-1304261646.cos.ap-guangzhou.myqcloud.com/STREAMAX/平台软件安装包/CB2/Ceiba2_2.6.8.0.24/Ceiba2Srv_2.6.8.0.24_en.exe)需要打补丁处理
>
> 
>
> 1. Copy the script file to the WCMS5 service directory of Ceiba2; For example: C:\Program Files (x86)\CMS Server\WCMS5
>
> 2. Launch Windows PowerShell as an administrator in the Start menu;
>
> 3. Access the WCMS5 service directory of Ceiba2 via PowerShell;
>
>    ```powershell
>    cd "C:\Program Files (x86)\CMS Server\WCMS5"
>    ```
>
> 4. Run the script.
>
>    ```powershell
>    .\monitor-device-protocol.ps1
>    ```
>
> 5. The system will verify whether the user password security reinforcement has been completed during output.
>
> > **Security status**: 
> >
> > "Green" indicates the system is either a security-hardened version or has been deployed with hardened patches.
> >
> > Red indicates unsecured, requiring the Expert Department to apply user password reinforcement patches.
> >
> > total call count: The number indicating whether any API/v1/basic/device/protocol interfaces have been invoked.
> >
> > File modified successfully: Interface shielding completed.
>
> 6. Upon script execution completion, the WCMS5 service will restart automatically to enable interface blocking.
>
> >  If CB2 patch script failed. You can follow the steps below to run it:
> >
> >  1. Open PowerShell.
> >
> >  2. Enter the following command:
> >
> >     ```powershell
> >     Set-ExecutionPolicy -ExecutionPolicy UNRESTRICTED -Scope CurrentUser
> >     ```
> >
> >  3. Then type `Y` and press Enter.
> >
> >  4. Enter the following command:
> >     ```powershell
> >     .\monitor-device-protocol.ps1
> >     ```
> > 5. Then type `R` and press Enter.
> >
> >  ![command-overview](https://cdn.jsdelivr.net/gh/maozuxiao/Steamax_IMG/iwElAqNwbmcDBgTRA9cF0QJxBrAxkJkkaF4YbAkjGgRHAy4AB9IEB8MmCAAJsmRpbmdSaWNoVGV4dEVkaXRvcgoAC9IABCBW.png_720x720q90.jpg)
>
> 

> Dear Customer,
>
> We would like to inform you of a recently identified **critical security vulnerability** in CEIBA2 Server. This vulnerability could potentially be exploited by malicious actors to send unauthorized configuration modification commands to devices, including altering reporting server addresses. Such an attack could result in mass device disconnections and significantly disrupt the normal operation of customer platforms.
>
> To mitigate these risks, we kindly request that you run the **remediation script** provided in the following link. Remote support can be arranged upon request if needed.
>
> https://wj.streamax.com:9443/outpublish.html?code=Bcd823993d9774301853e238a4f565b63&lang=en#view
>
> The remediation script will:
>
> 1. Scan the CEIBA2 Server for any known unpatched critical vulnerabilities.
> 2. Check whether the CEIBA2 Server has been previously compromised via known exploit attempts.
> 3. Immediately patch vulnerable interfaces that are susceptible to attacks.
>
> After execution, the script will automatically restart the **WCMS5 service**, resulting in a brief web service interruption of no more than one minute.
>
> We kindly ask you to acknowledge this situation and grant authorization for the remediation procedure. Please follow the instructions in the readme to install and run the script.
>
> Thank you for your prompt attention and cooperation in ensuring the continued security and stability of your CEIBA2 platform.
>
> ![Full process](https://cdn.jsdelivr.net/gh/maozuxiao/Steamax_IMG/image-20251224161441117.png)



