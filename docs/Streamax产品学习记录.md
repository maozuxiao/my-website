---
title: Streamax 产品学习记录
author: Sean Mao
keywords:
- 问题处理步骤
- 说明
- Business,Enterprise,FAE,Technical Support
- 海外营销中心-欧洲战区-土耳其区
- 仅内部使用
vlook-welcome: Streamax
vlook-header-autonum: h1{{Chapter ###. }},h2{{Chapter ###. }},h3{{Chapter ###. }},h4{{Chapter ###. }},h5{{Chapter ###. }}
layout: default
vlook-query: coating=bu&ws=3&toc=3
vlook-header-dup: A/V IN;WAN口;LAN口;操作手册;MDVR设置;基本信息;视频演示;模拟测试接线;
---

###### ✒️Streamax 产品学习记录<br />*Version 1.0`🐾`20th June 2025*<br />*一般`👀`部门可见*<br />**** <br />*Sean`🍍` Mao*<br />[✉️](mailto:sean@streamax.com)

# **✒️**Streamax 产品学习记录

[TOC]

## 课程表

| 时间    | 课件  | 总结 |
| --------------- | ----------------------------------------------------- | ---- |
| 2025-6-20 14:15 | Comprehensive MDVR series from Streamax 20230911.pptx | MDVR系列产品命名规范，产品硬件接口、产品参数，一些专业术语介绍 |
| 2025-6-26 14:12 | MDVR GUI介绍 | 主要围绕主机操作界面的功能讲解、设置方法以及相关问题的讨论展开，重点在于掌握设备的操作逻辑和常见问题处理。 |

## 待办事项

- [x] 借用测试样机X3N-H0404
  1. 2025-6-20：覃海传-Beacher：下周会准备一台提供给我
  1. 2025-6-23：找Cedric_张炯荣借用1台X3N-GMH0404，Mac `0018F55933F5` ； 1根电源线
  1. 2025-6-23：找Frank孟祥奇借用1个适配器；1台CP4
- [x] 了解样机X3N-H0404的硬件结构并成功点亮测试样机X3N-H0404
  ![点亮样机X3N-H0404](https://cdn.jsdelivr.net/gh/maozuxiao/Image-shack/image-20250623171956703.png#40%)
- [x] 验证问题：如果AHD支持X路，只使用X-1路，视频输出质量是否会提升，比如1080P@12fps(AHD)>>1080P@25fps(AHD)？

## 学习路径

- [ ] 硬件学习
- [ ] 软件操作系统学习
- [ ] 云平台学习
- [ ] 行业解决方案讲解

## 汇报方式

_^tab^_

> **发送相关方**
>
> 日报发送emrys@streamax.com，抄送maxwell@streamax.com; pascal@streamax.com

> **邮件发送小工具**
>
> <textarea id="emailBody" placeholder="请输入邮件正文..." rows="6" style="width: 300px;">尊敬的各位领导，您好：
> 以下是我的学习情况：
>   1. 
>   2. 整理学习过程中所需的知识
>     a. 
> 学习记录详见链接：https://maozuxiao.github.io/my-website/Streamax%E4%BA%A7%E5%93%81%E5%AD%A6%E4%B9%A0%E8%AE%B0%E5%BD%95.html</textarea><a class="btn" onclick="var emailBody = encodeURIComponent(document.getElementById('emailBody').value); window.location.href = 'mailto:emrys@streamax.com?cc=maxwell@streamax.com,pascal@streamax.com&subject=Sean的学习日报&body=' + emailBody;"><br><kbd>点击发送邮件⌯⌲</kbd></a>

## 产品信息查询

1. 登录<kbd>[鸿翼文件服务器](https://wj.streamax.com:9443/)</kbd>
1. 搜索关键词`xx可售清单`，找到表格文件后**下载**打开
1. 找到对应物料的`参考料号`，并复制到剪切板
1. 登录<kbd>[OA系统](http://oa.streamax.com:8080/login.jsp)</kbd>>>常用新建/发起>>MC查询>>规格文件查询，相关`参考料号`
1. 如有文件名，点击下载PDF文档

## 待验证问题

> ###### 如果AHD支持X路，只使用X-1路，视频输出质量是否会提升，比如1080P@12fps(AHD)>>1080P@25fps(AHD)？
>
> > [!NOTE]
> > MDVR-X3N-H0404支持参数：
> >
> > **PAL**
> > `4*720P@25fps(AHD)+4*1080P@30fps(IPC)`Or `4*1080P@12fps(AHD)+4*1080P@30fps(IPC)`
> >
> > **NTS** 
> > `4*720P@30fps(AHD)+4*1080P@30fps(IPC)` Or `4*1080P@12fps(AHD)+4*1080P@30fps(IPC)`
> >
> > 
> >
> > -----
> >
> > **验证步骤**：
> >
> > 1. 在View MDVR WebUI中配置4个信道的AHD摄像头主码流`4*1080P@12fps(AHD)`，主码流资源百分比**==90==**
> >      ![4*1080P@12fps(AHD)](https://cdn.jsdelivr.net/gh/maozuxiao/Image-shack/image-20250624164230485.png#40%)
> > 2. 取消第四路AHD摄像头的勾选，配置`2*1080P@12fps(AHD)+1*1080P@25fps(AHD)`，主码流资源百分比**==91.9==**
> >      ![2*1080P@12fps(AHD)+1*1080P@25fps(AHD)](https://cdn.jsdelivr.net/gh/maozuxiao/Image-shack/image-20250624164658884.png#40%)
> > 3. 在大胆尝试把子码流全部信道取消勾选并保存，就可以进一步提高AHD摄像头的帧率，`1*1080P@12fps(AHD)+*1080P@16fps(AHD)+1*1080P@25fps(AHD)`，主码流资源百分比**==99.4==**
> >      ![1*1080P@12fps(AHD)+*1080P@16fps(AHD)+1*1080P@25fps(AHD)](https://cdn.jsdelivr.net/gh/maozuxiao/Image-shack/image-20250624165412496.png#40%)
> > 4. 进一步提高画质，将会有警告弹出：`当前选择的通道过多，导致： 双码流录像设置超过系统总资源 请重新选择双码流录像通道! 选择的录像码率: 12570Kb. 录像码率最大值: 12288Kb`
> >      ![录像设置警告](https://cdn.jsdelivr.net/gh/maozuxiao/Image-shack/image-20250624165531377.png#40%)
> >
> > **验证结果**：减少AHD路数，可以提升剩下摄像头的视频输出质量，但是视频输出质量受到硬件能力限制，录像码率不能超过额定值。

> ###### 导出视频时Proprietary data和 AVI data有什么区别？
> ![Proprietary data & AVI data](https://cdn.jsdelivr.net/gh/maozuxiao/Image-shack/image-20250626141959846.png#left#40%)
>
> **Proprietary data（专有数据）**：指由特定公司、组织或个人拥有知识产权的私有数据，通常受专利、版权或商业秘密保护，不对外公开其技术规范或格式标准。
>
> **AVI data（AVI 格式数据）**：AVI（Audio Video Interleave）是由微软开发的一种**开放式视频容器格式**，于 1992 年推出，属于通用标准格式。
>
> > [!NOTE]
> >
> > 在X3N上导出的格式为H264/H265 Data & MP4 Data，如需播放H264/H265 Data文件需要下载解码器，比如[K-Lite Codec Pack](https://www.codecguide.com/download_kl.htm)才能播放，并且不能调节时间
> > ![H264/H265 Data & MP4 Data](https://cdn.jsdelivr.net/gh/maozuxiao/Image-shack/image-20250626174846893.png#40%)

> ###### 不同层级的账号（admin/user）有什么区别？
>
> User没有config菜单，无法对MDVR进行配置



## 产品通用类知识



### 产品命名规范

> **示例**：**X**_~Rd~_<sup>①</sup>**3**_~Gn~_<sup>②</sup>**N**_~Ye~_<sup>③</sup>-**GM**_~Aq~_<sup>④</sup>-**H**_~Pu~_<sup>⑤</sup>**04**_~Ol~_<sup>⑥</sup>**04**_~Og~_<sup>⑦</sup>
>
> ![X3N-GM-H0404](https://cdn.jsdelivr.net/gh/maozuxiao/Image-shack/20250626094225648.png)
>
> | 序号 | 编码部分 | 类型 | 含义 |
> |:--------:|:----:|:----:|------|
> | ①       | X        | 存储介质 | `X`：机械硬盘（需区分3.5和2.5尺寸）或SATA SSD<br />`M`：Micro SD /M.2 SSD<br />`A`：==待补充== |
> | ②       | 3        | 产品等级 | 产品等级，数字越大性能越高，性能排序`X5N-E0804`>`X3N-H0404`>`M1N-H0401` |
> | ③       | N        | 芯片信息 | `N`：NovaTek（联咏芯片）<br />如果该字段为空代表hisilicon(海思芯片) |
> | ④ | GM | 行业代表 | `GM`：“Gengeral Mobile DVR” 通用车载视频<br />`TK`：“Trucking” 货运产品线<br />`PT`：“Public Transit” 公交产品线 |
> | ⑤      | H        | 工作模式 | `H`：Hybrid，混合模式<br />`E`：Extension，扩展模式比如`X5N-E0804`拥有`LAN`连接 External Switch拓展IP camera & `AV IN总线`拓展AHD camera |
> | ⑥     | 04       | AHD camera支持路数 | 支持4路模拟摄像头（AHD camera） |
> | ⑦    | 04       | IP camera支持路数 | 支持4路IP摄像头（IP camera） |
>



### MDVR 产品矩阵



> <iframe frameborder="no" border="0" marginwidth="0" marginheight="0" width=1046 height=626 src="https://edrawcloudpublicus.s3.amazonaws.com/viewer/self/2539370/share/2025-6-26/1750906868/main.svg"></iframe>

### 产品规格书 & 说明书

_^tab^_

> **MDVR**
>
> | 产品名称       | 规格书                                                       | 说明书                                                       | 其他                                                         |
> | -------------- | ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ |
> | M1N-H0401      | [M1N-H0401规格书（V1.0）.docx](https://wj.streamax.com:9443/preview.html?fileid=0125934b-5fa5-4e98-a284-e94ed007c91a)<br />[M1N-H0401 Specification Q3.docx](https://wj.streamax.com:9443/preview.html?fileid=f810386b-c7f7-4f40-a4a4-f9f17609d199) | [M1N产品使用说明书V2.0.docx](https://wj.streamax.com:9443/preview.html?fileid=064e99f2-3515-45e6-a41d-dd32703467e6)<br />[M1N User ManualV2.0.docx](https://wj.streamax.com:9443/preview.html?fileid=a5f523f9-ba84-44a7-8595-dd01110140f4) |                                                              |
> | X3N-H0404      | [X3N-H0404规格书（V1.0）.doc](https://wj.streamax.com:9443/preview.html?fileid=544b0b8e-31fe-484a-8232-f15945ea4bfd)<br />[X3N-H0404 Specification-20220421-EN.docx](https://wj.streamax.com:9443/preview.html?fileid=7354e8a1-c410-4874-89c3-c4af95f030c0) | [X3N系列产品使用说明书-V2.0.doc](https://wj.streamax.com:9443/preview.html?fileid=28300d23-1b1c-4bb5-8010-36065a818659)<br />[X3N Series Product User Manual-V2.0.docx](https://wj.streamax.com:9443/preview.html?fileid=c939d7a5-1a6c-46ab-97b8-e62b518849fb) |                                                              |
> | X3NPro-PTH0404 | [X3NPro-PTH0404中文规格书.docx](https://wj.streamax.com:9443/preview.html?fileid=54d7dd2f-8b73-45ff-a2b6-8673fdb2aaf2)<br />[X3NPro-PTH0404 Specification.doc.docx](https://wj.streamax.com:9443/preview.html?fileid=036af7da-e11e-48dd-b007-72f548237c90) | [X3N Pro使用说明书.docx](https://wj.streamax.com:9443/preview.html?fileid=0615eb0e-55e1-45fb-99c2-be7a15b3d220)<br />[X3N Pro使用说明书（英文版）.docx](https://wj.streamax.com:9443/preview.html?fileid=00054bfc-3121-4586-a409-ae110ec71e95) | [X3NPro-PTH0404配置清单.xlsx](https://wj.streamax.com:9443/preview.html?fileid=1051676a-3c3f-43c4-b26d-b8cf2bae5b78) |
> | X3N-H0208      | [X3N-H0208产品规格书V1.0.doc](https://wj.streamax.com:9443/preview.html?fileid=be609bc2-4ab1-4fe0-8a14-86abeac5ec53)<br />[X3N-H0208 Specification.pdf](https://wj.streamax.com:9443/preview.html?fileid=f8cc96d3-02a9-47e0-b715-7a976f126001) | [X3N-H0208客车安装方案（V1.0）.docx](https://wj.streamax.com:9443/preview.html?fileid=82077bee-988f-46cf-8cfa-821028a1dc3e)<br />[X3N-H0208 Installation Guide.pdf](https://wj.streamax.com:9443/preview.html?fileid=a2f39053-7e48-4c63-b46f-4a7c455b01ee) | [X3N-H0404-H0208配置表0909.xlsx](https://wj.streamax.com:9443/preview.html?fileid=e76df95a-7a4d-445d-8575-764a2b3c8a63) |
> | AD plus 2.0    | [AD Plus 2.0 产品规格书.pdf](https://wj.streamax.com:9443/preview.html?fileid=04ed189d-5eac-4a25-a047-e5d6f7534edf)<br />[AD Plus 2.0 Specification.pdf](https://wj.streamax.com:9443/preview.html?fileid=9dcc63b9-ea91-48fe-856b-31452b99e82e) | [04-Quick User Manual & Installation Guidance of AD Plus.pdf](https://wj.streamax.com:9443/preview.html?fileid=24b0d8f9-3f14-4645-bbd1-dd37dddc953d) | [AD Plus 2.0 System diagram (Standard).pdf](https://wj.streamax.com:9443/preview.html?fileid=5d0e1ec2-2af5-4656-9d18-8a6cfb5b3521) |

> **Control Panel **
>
> | 产品名称 | 规格书                                                       | 说明书                                                       |
> | -------- | ------------------------------------------------------------ | ------------------------------------------------------------ |
> | CP4      | [CP4产品规格书.pdf](https://wj.streamax.com:9443/preview.html?fileid=74bc4ab3-f0b4-4065-8e43-b526105f5519)<br /> [Spe-CP4 20230629.docx](https://wj.streamax.com:9443/preview.html?fileid=6695f7e1-6419-4596-8ebf-8fff9c8be876) | [锐明 CP4 产品说明书.doc](https://wj.streamax.com:9443/preview.html?fileid=10a894af-dd24-47fa-a6f5-7cdc986f1497)<br />[CP4 Manual-2014_Q4.doc](https://wj.streamax.com:9443/preview.html?fileid=a0bd0c52-b17d-4fa0-ae01-606dd50eeabe) |



### 面板接口说明

_^tab^_

> **前置面板(Front panel)**
>
> | 名称          | 定义                                                         | M1N-H0401             | X3N-H0404                                 |
> | ------------- | ------------------------------------------------------------ | --------------------- | ----------------------------------------- |
> | PWR(指示灯)   | 电源指示灯<br />蓝色；设备上电时常亮；关机、待机或休眠时熄灭 | ✅                     | ✅                                         |
> | USB(指示灯)   | USB指示灯<br />绿色；设备识别到U盘时常亮；设备对U盘进行读写操作时闪烁，闪烁频率1HZ | ✅                     | ✅                                         |
> | ALM(指示灯)   | 报警指示灯<br />红色；触发任意报警时常亮；正常情况下熄灭     | ✅                     | ✅                                         |
> | REC(指示灯)   | 录制指示灯<br />红色；绿色；录像时常亮；非录像时熄灭         | ✅                     | ✅                                         |
> | ERR(指示灯)   | 故障指示灯<br />红色；硬盘加密芯片未获取到时常亮；其他状态熄灭 | ✅                     | ✅                                         |
> | NET(指示灯)   | 网络指示灯<br />绿色；通讯模块正常，无数通讯时常亮；通讯模块正常，有数据通讯时闪烁，闪烁频率1HZ；无通讯模块时熄灭 | ✅                     | ✅                                         |
> | VLOSS(指示灯) | 视频丢失或无信号指示灯                                       | ❌                     | ❌                                         |
> | SD(接口)      | SD卡接口<br />支持SDXC 32GB/64GB/128GB/256GB，可热插拔<br />**读写速率最低要求Class10<sup>10MB / 秒</sup>**_~Rd~_ | ✅2个                  | ✅1个                                      |
> | SIM(接口)     | SIM卡接口<br />**要求使用工业级SIM卡（MP2），禁用普通级SIM卡（MP1）**_~Rd~_ | ✅1个；Mini Sim卡      | ✅1个；Mini Sim卡                          |
> | USB(接口)     | 升级固件/运维宝（Easy check）                                | ✅运维宝（Easy check） | ✅运维宝（Easy check                       |
> | A/V OUT(接口) | 外接显示器/控制面板                                          | ❌                     | ❌                                         |
> | 硬盘盒        | 插入2.5寸/3.5寸 HDD/SSD，M.2 SSD                             | ❌                     | ✅上置硬盘盒；1 x2.5"SATA HDD或SSD(最大2T) |
>
> 

> **后置面板(Rear panel)**
>
> | 名称                                                         | 定义                                             | M1N-H0401                   | X3N-H0404                   |
> | ------------------------------------------------------------ | ------------------------------------------------ | --------------------------- | --------------------------- |
> | WIFI Antenna<br />![WIFI天线图标](https://cdn.jsdelivr.net/gh/maozuxiao/Image-shack/image-20250623112524303.png)<br />![WIFI天线接口](https://cdn.jsdelivr.net/gh/maozuxiao/Image-shack/image-20250623115334151.png#20%) | WIFI天线接口                                     | ✅1*SMA                      | ✅1*SMA                      |
> | External GPS<br />![GPS/BD北斗图标](https://cdn.jsdelivr.net/gh/maozuxiao/Image-shack/image-20250623112539202.png)<br />![GPS&北斗外接接口](https://cdn.jsdelivr.net/gh/maozuxiao/Image-shack/image-20250623113425889.png#20%) | 外接GPS/北斗定位模块接口                         | ✅1个；4Pin；支持GPS/BD 北斗 | ✅1个；4Pin；支持GPS/BD 北斗 |
> | 3G or 4G Antenna<br />![3G or 4G Antenna](https://cdn.jsdelivr.net/gh/maozuxiao/Image-shack/image-20250623112622148.png)<br />![3G or 4G Antenna接口](https://cdn.jsdelivr.net/gh/maozuxiao/Image-shack/image-20250623112743027.png#20%) | 3G/4G天线接口                                    | ✅1*SMA                      | ✅1*SMA                      |
> | A/V IN<br />![A/V IN](https://cdn.jsdelivr.net/gh/maozuxiao/Image-shack/image-20250623113616780.png#20%) | 模拟音视频输入                                   | ✅4个；4Pin同轴电缆          | ✅4个；4Pin同轴电缆          |
> | AV-IN Type2<br />![AV-IN Type2](https://cdn.jsdelivr.net/gh/maozuxiao/Image-shack/image-20250626140644985.png#20%) | 模拟音视频输入                                   | ❌                           | ❌                           |
> | IPC<br />![IP摄像头](https://cdn.jsdelivr.net/gh/maozuxiao/Image-shack/image-20250623114134142.png#20%) | PON供电IPC接口                                   | ✅1个；6Pin同轴电缆          | ✅4个；6Pin同轴电缆_~Rd~_    |
> | POE-IPC<br />![POE-IPC](https://cdn.jsdelivr.net/gh/maozuxiao/Image-shack/image-20250626140425150.png#20%) | IPC音视频输入1-4（POE/PON)<br />POE 即以太网供电 | ❌                           | ❌                           |
> | Power<br />![电源接口](https://cdn.jsdelivr.net/gh/maozuxiao/Image-shack/image-20250623114054994.png#20%) | DC8-36V电源输入                                  | ✅1个；9Pin电源线            | ✅1个；9Pin电源线            |
> | R-WATCH & AV out<br />![R-WATCH & AV out](https://cdn.jsdelivr.net/gh/maozuxiao/Image-shack/image-20250623114201780.png#20%) | R-WATCH&A/V OUT接口                              | ✅1个；8Pin                  | ❌                           |
> | Sensor & Serial<br />![Sensor & Serial](https://cdn.jsdelivr.net/gh/maozuxiao/Image-shack/image-20250623114344644.png#20%) | 串口和开关量接口                                 | ✅1个；22Pin                 | ✅1个；22Pin                 |
> | USB通用串行总线接口<br />![USB](https://cdn.jsdelivr.net/gh/maozuxiao/Image-shack/image-20250626164913699.png#20%) | USB通用串行总线接口                              | ❌                           | ❌                           |
> | USB Type B<br />![USB Type B](https://cdn.jsdelivr.net/gh/maozuxiao/Image-shack/image-20250623164433187.png#20%) | USB Type B(可连防火盒)                           | ❌                           | ✅1个；2.0版本               |
> | WAN<br />![WAN口](https://cdn.jsdelivr.net/gh/maozuxiao/Image-shack/image-20250623164459316.png#20%) | WAN 口，连接电脑配置MDVR                         | ❌                           | ✅1个；100M                  |
> | LAN<br />![LAN口](https://cdn.jsdelivr.net/gh/maozuxiao/Image-shack/image-20250624110338651.png#20%) | LAN口，连接Extension Switch                      | ❌                           | ❌                           |
> | Serial<br />![Serial](https://cdn.jsdelivr.net/gh/maozuxiao/Image-shack/image-20250623164519364.png#20%) | 串口接口                                         | ❌                           | ✅1个；12Pin                 |
> | VGA<br />![VGA](https://cdn.jsdelivr.net/gh/maozuxiao/Image-shack/image-20250623164535733.png#20%) | VGA视频接口                                      | ❌                           | ✅1个；8Pin                  |
> | Panel<br />![Panel](https://cdn.jsdelivr.net/gh/maozuxiao/Image-shack/image-20250623164555190.png#20%) | 控制面板（CP4）接口                              | ❌                           | ✅1个；10Pin                 |

### IP camera Vs AHD camera

| 特点           | IP camera                                                    | AHD camera                                                   |
| -------------- | ------------------------------------------------------------ | ------------------------------------------------------------ |
| 传输方式       | 网线传输图像，可支持多种接入方式                             | 模拟传输，通过同轴电缆传输高清视频信号                       |
| 信号处理       | ==将视频信号转换为数字信号，`经编码压缩处理，转化为网络数据信号传输`== | ==采用 Y/C 信号分离和模拟滤波技术，传输的是`未经压缩的模拟信号`== |
| 图像质量       | 受编码压缩算法和网络带宽等因素影响较大，最高可达 4K 甚至更高 | 在同分辨率下，图像的色彩还原度和细节表现好，最高清晰度等同于网络高清 1080P |
| 系统架构与成本 | 可直接接入网络交换及路由设备，布线成本低，但网络摄像机本身价格相对较高 | 需与同轴电缆和 AHD 录像机配合使用，若升级原有模拟监控系统可降低成本，新建系统布线成本高 |
| 远程监控与管理 | 可方便地通过网络进行远程访问和管理，支持多用户同时访问和分级管理 | 一般需在本地设置参数，通过连接到录像机或监控主机管理，远程监控便捷性和灵活性稍逊一筹 |
| 扩展性与兼容性 | 具有很强的扩展性，可方便地添加设备或与其他网络设备集成，不同品牌和型号设备只要符合相关网络协议和标准就能互联互通，但实际应用中可能存在兼容性问题 | 兼容性较好，可与传统模拟设备和 AHD 设备混合使用，但扩展性相对较弱 |



### 航空公头 & 航空母头

> <b>示例</b>: IP camera的连接方式
>
> | 特点         | 航空公头                 | 航空母头                 |
> | :----------- | :----------------------- | :----------------------- |
> | **结构外观** | 凸起的针或柱状体         | 内有空腔的插孔           |
> | **连接方式** | 插入母头                 | 接收公头                 |
> | **电气性能** | 针脚导电性好、耐腐蚀     | 插孔接触性能好、绝缘性强 |
> | **应用场景** | 信号输出端、主动连接设备 | 信号接收端、固定安装设备 |

### GPS模块外置设计

> Streamax MDVR部分产品采用外接GPS模块，GPS模块从内置改为外置，以减少干扰，通过串口传输定位信息。有信号接收性能强，定位精度高，灵活性和可扩展性强等优点

### RS232 & RS485

_^tab^_

> **RS232 定义**
> - RS - 232 - C（推荐标准 232 - C）是美国电子工业协会（EIA）制定的一种串行物理接口标准。它是在 1969 年公布的，用于连接数据终端设备（DTE，Data Terminal Equipment）和数据通信设备（DCE，Data Communication Equipment）。
>
> - RS - 232 - C 接口的信号线定义包括多种信号类型。例如，数据线路（如 TxD - 发送数据，RxD - 接收数据），用于在设备之间传输数据；控制线路（如 RTS - 请求发送，CTS - 允许发送，DSR - 数据设备就绪，DTR - 数据终端就绪等），用于对数据的传输过程和链路状态进行控制。其`最大传输距离约为 15 米（在波特率为 19200 的情况下），最大传输速率为 20kbps 左右`。通常使用 9 针或 25 针的 DB - 9 或 DB - 25 接口。这个接口曾经广泛应用于计算机与调制解调器、计算机与其他串行设备之间的连接，如早期的计算机与打印机、终端设备等之间的通信。
>   [<kbd>📖百度百科：RS-232 ❯❯</kbd>](https://baike.baidu.com/lemma/api/entry?word=RS-232&fromModule=lemma_search-b)
>   ![4分钟听懂！什么是 RS-232？](https://cdn.jsdelivr.net/gh/maozuxiao/Image-shack/mda-mi8b0n3irhcdj0h6.mp4)

> **RS485 定义**
>
> - RS - 485 是一种常用的总线标准，由美国电子工业协会（EIA）于 1983 年正式颁布。它是一种平衡串行通信接口，主要用于连接多个设备，构成分布式控制系统或进行长距离的数据传输。
> - RS - 485 接口采用了差分信号传输方式，具有良好的抗干扰能力。它采用两线制（半双工）或四线制（全双工）的通信方式。在两线制中，A 线和 B 线（也称为 “+” 和 “ - ”）用于数据传输，通过比较两线之间的电位差来判断信号的逻辑状态。RS - 485 的`最大传输距离可达 1200 米左右（在波特率为 90kbps 时），最大传输速率可达 10Mbps（在 12 米范围内）`。它**可以连接多个节点**，一般最多可以连接 **32 个节点**（通过中继器等设备可以扩展连接数量），在工业自动化、楼宇自动化等领域得到了广泛应用，如连接 PLC（可编程逻辑控制器）与传感器、执行器等设备，实现数据采集和控制指令的传输。
> [<kbd>📖百度百科：RS-485 ❯❯</kbd>](https://baike.baidu.com/lemma/api/entry?word=RS-232&fromModule=lemma_search-b)
> ![【工程师必备技能】什么是RS485？如何在工业控制系统中使用它？](https://cdn.jsdelivr.net/gh/maozuxiao/Image-shack/mda-mcqfjn3f1k7fjdd5.mp4)

> **RS232 VS RS485**
> |                            对比项                            | RS232                                    | RS485                                        |
> | :----------------------------------------------------------: | :--------------------------------------- | -------------------------------------------- |
> |                           通信方式                           | 单端通信，易受干扰                       | 差分通信，抗干扰能力强                       |
> |                           传输距离                           | 最大传输距离约 15 米（19200bps）         | 最大传输距离约 1200 米（90kbps）             |
> |                         最大传输速率                         | 最大传输速率为 20kbps（15 米）           | 最大传输速率为 10Mbps（12 米）               |
> |                         网络拓扑结构                         | 通常为点 - 点通信                        | 支持多点链路，最多可连接 32 个节点（可扩展） |
> |                          抗干扰能力                          | 抗干扰能力弱，易受地电位差和电磁干扰影响 | 抗干扰能力强，能有效抑制共模干扰             |
> |                           电源供给                           | 通常需要单独电源                         | 可通过信号线供电                             |
> 
> 
> ![RS232、RS485、TTL到底能传输多远距离？](https://cdn.jsdelivr.net/gh/maozuxiao/Image-shack/mda-pg97k2dwfd1twyiq.mp4)

### PAL & NTSC 

_^tab^_

> **PAL 定义**
>
> PAL（Phase-Alternating Line）是一种电视视频制式，主要在欧洲、亚洲、非洲等许多国家和地区使用。它的帧频率为 50Hz，分辨率为 720×576（实际有效分辨率为 704×576），采用逐行扫描，色差信号采用逐行倒相的方式对副载波进行调制，以减少副载波对图像载波的干扰。

> **NTSC 定义**
> 
> NTSC（National Television System Committee）是美国国家电视标准委员会制定的一种电视视频制式，主要在美国、加拿大、日本等国家使用。其帧频率为 60Hz（实际上是 59.94Hz），分辨率为 720×480（实际有效分辨率为 704×480），采用隔行扫描，色度信号采用平衡调幅的方式对副载波进行调制 。

> **PAL VS NTSC**
>
>
> |        特点        | PAL 制式                                                     | NTSC 制式                                                    |
> | :----------------: | ------------------------------------------------------------ | ------------------------------------------------------------ |
> |       帧频率       | 25 帧 / 秒（50Hz/s）                                         | 29.97 帧 / 秒≈30 帧 / 秒(59.94Hz/s（接近 60Hz）)             |
> | 分辨率（实际有效） | 704×576                                                      | 704×480                                                      |
> |      扫描方式      | 逐行扫描 & 隔行扫描                                          | 逐行扫描 & 隔行扫描                                          |
> |    色差编码方式    | 采用逐行倒相（Phase Alternating Line）的方式对副载波进行调制 | 色信号度采用正交调幅（Quadrature Amplitude Modulation）的方式对副载波进行调制 |
> |     画面流畅度     | 画面较为流畅，但相比 NTSC 在快速运动画面时稍显逊色           | 画面流畅度高，快速运动画面表现较好                           |
> |      适用范围      | 主要应用于欧洲、亚洲、非洲等地区                             | 主要应用于美国、加拿大、日本等国家                           |
> 
> <iframe src='https://player.bilibili.com/player.html?bvid=BV12a411Y7tJ&cid=586526065&p=1&share_source=copy_web&autoplay=0' scrolling='no' border='0' frameborder='no' framespacing='0' allowfullscreen='true'></iframe>

> [!note]
>
> 如上分辨率为标准制定时的分辨率，后续是可以支1080P的，比如`1080P@12fps`,`1080P@30fps`



### A/V IN & A/V OUT

_^tab^_

> **A/V IN**
>
> ‌A/V IN接口‌：主要用于连接外部音频和视频源，如摄像头、DVD播放器等。通过A/V IN接口，行车记录仪可以接收来自这些外部设备的信号，实现视频和音频的输入‌，比如倒车后视频摄像头的视频信号可以通过A/V IN接口输入到行车记录仪中‌

> **A/V OUT**
>
> ‌A/V OUT接口‌：用于将信号从行车记录仪输出到外部设备，如电视或显示器。通过A/V OUT接口，可以将行车记录仪拍摄的影像和声音传输到更大的屏幕上显示，提供更好的视觉体验‌



### USB Type-B 接口

_^tab^_

> **USB Type-B 接口用途**
>
> USB Type-B接口主要用于连接大型设备和计算机或其他设备进行数据传输和供电，常见于打印机、扫描仪、外部硬盘等设备。**在X3N-H0404(N2.1) 的Rear Panel中有该接口，用于连接防火箱（Fireproof box--类似于飞机的黑匣子，以存储重要数据）**_~RdGnBuRo~_
>
> 
>
> USB Type-B接口的主要用途：
>
> - **连接打印机和扫描仪:**
>
>   大多数打印机和扫描仪都使用Type-B接口与计算机连接，实现文档的打印和扫描。
>
> - **连接外部硬盘:**
>
>   外部硬盘通常配备Type-B接口，方便用户连接到计算机进行数据传输和存储。
>
> - **连接其他大型设备:**
>
>   一些专业音频设备、医疗设备等也可能使用Type-B接口。
>
> - **数据传输和供电:**
>
>   Type-B接口支持全双工传输，可以同时进行数据传输和供电。﻿

> **应用示例**
>
> ![USB_TypeB-FireProof box](https://cdn.jsdelivr.net/gh/maozuxiao/Image-shack/20250623100633279.png)



------
### MDVR上WAN & LAN 口的应用场景

_^tab^_

> **WAN口**
>
> 1. 用于固件升级、参数配置、录像回放等。可通过RJ45网线连接电脑以访问WebUI：<kbd>View MDVR</kbd>，比如<kbd>**X3N-H0404**</kbd>
>
>    > <b>网络配置</b>:
>    >
>    > *IPv4 address`10.100.100.101`*
>    > *IPv4 default gateway`10.100.100.1`*
>    > *Subnet Mask`255.0.0.0`*
>    
>   > [!NOTE]
>    >
>    > 1. IPV4地址可以设置成：*10.100.100.2`𓍯𓂃𓏧♡`10.100.100.255`*
>    > 2. **如MDVR无WAN/LAN口，还可以通过IPC 6Pin母口转接RJ45母口的方法，连接电脑以访问WebUI：<kbd>View MDVR</kbd>**_~GdPkAq~_
>    
>2. 连接有线网络，为MDVD提供网络服务

> **LAN口**
>
> 1. 可以连接 External Switch拓展IPC，比如<kbd>**X5N-E0804**</kbd>
> 1. 用于固件升级、参数配置、录像回放等。可通过RJ45网线连接电脑以访问WebUI：<kbd>View MDVR</kbd>，比如<kbd>**X5N-E0804**</kbd>



### Easy Check运维宝

_^tab^_

> **产品介绍 & Diagram**
>
> **产品概述**
> Easy Check 是一款基于 Android 平板运行的设备管理软件，通过 WIFI 模块与 MDVR 设备连接，实现设备管理与维护，提高工作效率。
>
> **主要功能**
>
> 1. **WIFI 模块**：采用 USB 扩展设计，支持插拔即用、自动连接 WIFI、外部 SD 卡备份等功能。
> 2. **软件功能**：支持快速搜索 MDVR 设备、查看设备状态、多通道高清视频预览、视频回放分析、视频备份、解锁锁定视频、导出报警日志、用户操作日志及参数文件等。
>
> **软件模块**
>
> 1. **通用模块**：显示设备基本信息、通信模块详情、存储设备状态、版本信息等。
> 2. **预览模块**：支持 1 通道或 4 通道分屏显示，可切换音量开关。
> 3. **回放模块**：支持报警、锁定、视频日历，可进行播放、快进、倒退等操作。
> 4. **偏好设置模块**：可设置设备信息、时间、启动模式、用户信息、网络配置、实时预览、录像参数等。
> 5. **帮助模块**：提供帮助文件及 Easy Check 版本信息。
>
> **使用步骤**
>
> 1. 安装软件(参考<kbd>[这里 >>](#Veyes(锐明运维宝)使用说明)</kbd>)后，点击刷新搜索本地网络中的 WIFI 设备，选择设备并登录。
> 2. 根据需求进入不同模块进行操作，如预览、回放、设置等。
>
> **Diagram**
>
> ![Streamax Easycheck](https://cdn.jsdelivr.net/gh/maozuxiao/Image-shack/Streamax%20Easycheck.gif)

> **操作手册**
>
> [<kbd>📖Easy Check Manual.doc</kbd>](https://wj.streamax.com:9443/preview.html?fileid=9a787a1b-967f-4272-b4f3-bc055d61cfee)



### Veyes(锐明运维宝)使用说明

_^tab^_

> **软件安装**
>
> * Android手机用户请在谷歌商店搜索“Veyes” 下载后安装
> * IOS手机用户请在APP商店内搜索“Veyes”下载后安装
>
> > [!CAUTION]
> >
> > Mobile Apps对系统版本有限制，要求Android 5.0或者IOS 11及以上系统版

> **WIFI连接**
>
> 1. 开启设备WIFI为AP模式：设备启动3分钟内WIFI为AP模式，或者设备启动后双击前面板按钮启动AP模式。
> 2.	打开手机WIFI，打开Veyes点击【搜索】按钮，进入WIFI热点搜索界面选择对应热点。初次登录时，WIFI热点名称以设备SeriaNum号命名（设备标签可查找SeriaNum），若车牌号不为空，则热点名称为车牌号。
> 3.	在登陆界面，输入对应的用户名、密码后点击登录进入操作界面。默认用户名/密码为：admin/admin。
>
> > [!CAUTION]
> >
> > 效果等同于通过浏览器访问WIFI网关IP

> **操作手册**
>
> [<kbd>📖运维宝产品使用说明书(V1.0.0(2014-11-13)).doc</kbd>](https://wj.streamax.com:9443/preview.html?fileid=4f7398e2-0505-4f99-b535-b35908e32a22)

### ALM报警配置

_^tab^_

> **基础**
>
> ---
>
> ---
>
> ---
>
> - 开关量报警
>
>   ![开关量报警](D:\Typora pictures\Streamax产品学习记录\image-20250624093632460.png)
>
> - 速度报警
>
>   ![速度报警](D:\Typora pictures\Streamax产品学习记录\image-20250624093725470.png)
>
> - 面板报警
>
>   ![面板报警](D:\Typora pictures\Streamax产品学习记录\image-20250624094053036.png)
>
> - GPS报警
>
>   ![GPS报警](D:\Typora pictures\Streamax产品学习记录\image-20250624094201088.png)

> **视频**
>
> ---
>
> ---
>
> ---
>
> - 视频丢失
>
>   ![视频丢失](D:\Typora pictures\Streamax产品学习记录\image-20250624094306931.png)
>
> - 移动侦测
>
>   ![移动侦测](D:\Typora pictures\Streamax产品学习记录\image-20250624094428793.png)
>
> - 视频遮挡
>
>   ![视频遮挡](D:\Typora pictures\Streamax产品学习记录\image-20250624094423161.png)
>
> - 隐私模式
>
>   ![隐私模式](D:\Typora pictures\Streamax产品学习记录\image-20250624094414320.png)

> **高级**
>
> ---
>
> - 冲撞报警
>
>   ![冲撞报警](D:\Typora pictures\Streamax产品学习记录\image-20250624094645745.png)
>
> - 电子围栏
>
>   ![电子围栏](D:\Typora pictures\Streamax产品学习记录\image-20250624094628801.png)

> **智能应用**
>
> ---
>
> ---
>
> - ADAS
>
>   ![ADAS](D:\Typora pictures\Streamax产品学习记录\image-20250624094731441.png)
>
> - DMS
>
>   ![DMS](D:\Typora pictures\Streamax产品学习记录\image-20250624094855855.png)
>
> - BSD
>
>   ![BSD](D:\Typora pictures\Streamax产品学习记录\image-20250624094910851.png)
>
> - 算法参数
>
>   ![算法参数](D:\Typora pictures\Streamax产品学习记录\image-20250624094931091.png)
>
> - 报警提醒
>
>   ![报警提醒](D:\Typora pictures\Streamax产品学习记录\image-20250624095055123.png)
>
> - 算法标定
>
>   ![算法标定](D:\Typora pictures\Streamax产品学习记录\image-20250624095148173.png)

### G-Sensor在MDVR中的应用

> **触发录像功能**
> G-Sensor可以检测车辆的加速度变化，当车辆发生碰撞、急刹车、急加速或其他异常运动时，G-Sensor会触发MDVR自动开始录像。这种触发机制确保在关键时刻能够自动记录视频，为事故分析和责任判定提供有力证据。例如，敏视的MDVR系统支持G-Sensor触发录像，并且具备15秒预录功能，可以记录事件发生前的视频画面。
> **防抖功能**
> 在一些MDVR系统中，G-Sensor用于摄像头的防抖功能。它可以测量摄像头的抖动加速度，并将数据发送给处理器，通过图像处理单元对模糊的图像进行清晰化处理。这有助于提高视频的清晰度和稳定性，尤其是在车辆行驶过程中。
> **安全监控与报警**
> G-Sensor可以与其他安全系统（如ADAS、DMS、BSD等）集成，用于检测车辆的异常运动。例如，当车辆发生碰撞时，G-Sensor触发报警，同时将报警信息和录像上传到远程服务器。这种集成方式不仅提升了车辆行驶的安全性，还方便了车队管理和调度。
> **数据记录与分析**
> G-Sensor记录的加速度数据可以用于分析车辆的行驶状态，例如急刹车的频率、急加速的次数等。这些数据可以作为驾驶行为分析的依据，帮助车队管理者优化驾驶员的驾驶习惯，提高行车安全。
> **与其他功能联动**
> G-Sensor可以与MDVR的其他功能（如超速触发录像、自定义告警输入触发录像等）联动。例如，当车辆超速时，G-Sensor可以触发录像，并将超速信息记录下来，方便后续的管理和分析。
> **远程监控与管理**
> G-Sensor触发的录像和报警信息可以通过3G/4G、WIFI等无线通信技术上传到远程服务器。用户可以通过手机或电脑实时查看车辆状态、历史轨迹、录像文件等



### RTSP介绍

_^tab^_

> **什么是RTSP**
>
> RTSP（Real Time Streaming Protocol）是一种网络协议，主要用于控制流媒体服务器上的媒体流。在视频监控领域，RTSP被广泛应用于监控摄像头与监控中心之间的通信。监控中心可以通过RTSP协议向摄像头发送控制指令，获取摄像头的实时视频流，并对视频流进行实时监控、录制、回放等操作。

> **Potplayer实时预览和回放MDVR录像**
>
> 1. <kbd>[下载potplayer](https://potplayer.tv/?lang=zh_CN)</kbd>
> 2. 右键播放器空处，点击打开链接
>    ![Potplayer _Open URL](https://s3-eu-central-1.amazonaws.com/euc-cdn.freshdesk.com/data/helpdesk/attachments/production/80169828999/original/H62tNU180Wb6zTY_ebvsfyMyRLvDa34Dcg.jpg?1671390516)
> 3. 输入流的RTSP地址，然后点击“ OK”。
>
> > [!NOTE]
> >
> > **RTSP拉码流格式**
> >
> > * Main streaming video : rtsp://user:pwd@IP:554/mainstreamX 
> >
> > * Sub streaming video: rtsp:// user:pwd@IP:554/substreamX 
> >
> >   > X is Channel number，**Start from zero**_~Rd~_
> >
> > **举例（MDVR密码为空时）**
> >
> > ```rtsp
> > rtsp://admin:@10.100.100.1:554/mainstream0
> > rtsp://admin:@10.100.100.1:554/mainstream1
> > rtsp://admin:@10.100.100.1:554/mainstream2
> > rtsp://admin:@10.100.100.1:554/mainstream3
> > rtsp://admin:@10.100.100.1:554/mainstream4
> > ```

### 视频分辨率说明

_^tab^_

> **MDVR视频分辨率**
>
> **参考**：[N9M码率表.xls](https://wj.streamax.com:9443/preview.html?fileid=b6e99bde-26d9-4a92-a6bf-03c9187ed450)  
>
> | 名称         | 分辨率参数                     |
> | ------------ | ------------------------------ |
> | CIF          | PAL:352×288 NTSC:352×240       |
> | WCIF_~Rd~_   | PAL:480×288 NTSC:480×240_~Rd~_ |
> | HD1_~Rd~_    | PAL:704×288 NTSC:704×240_~Rd~_ |
> | WD1          | PAL:960×576 NTSC:960×480       |
> | WHD1_~Rd~_   | PAL:960×288 NTSC:960×240_~Rd~_ |
> | D1/VGA_~Rd~_ | PAL:704×576 NTSC:704×480_~Rd~_ |
> | QCIF/QVGA    | PAL:176×144 NTSC:176×120       |
> | 720P         | 1280×720                       |
> | 1080P        | 1920×1080                      |

> **行业视频分配率**
>
> | **分辨率**  | **释义**                  | **分辨率参数（PAL/NTSC）**            | **宽高比** | **典型应用**                 |
> | ----------- | ------------------------- | ------------------------------------- | ---------- | ---------------------------- |
> | CIF         | 标清中间格式              | 352×288 / 352×240                     | 4:3        | 早期监控、视频会议           |
> | WCIF_~Rd~_  | 宽屏 CIF_~Rd~_            | 352×240（统一）_~Rd~_                 | 16:9_~Rd~_ | 宽屏标清视频_~Rd~_           |
> | HD1_~Rd~_   | 标清 / 高清模糊定义_~Rd~_ | 720×576/720×480 ~~或 1280×720~~_~Rd~_ | -_~Rd~_    | 老款监控、早期高清实验_~Rd~_ |
> | WD1（960H） | 宽屏 D1（监控专用）       | 960×576 / 960×480                     | 接近 16:9  | 高清模拟监控                 |
> | WHD1_~Rd~_  | 宽屏 HD1（即 720P）_~Rd~_ | 1280×720（统一）_~Rd~_                | 16:9_~Rd~_ | 高清监控、网络视频_~Rd~_     |
> | D1_~Rd~_    | 标准标清数字视频_~Rd~_    | 720×576 / 720×480_~Rd~_               | 4:3_~Rd~_  | DVD、老式电视_~Rd~_          |
> | 720P        | 高清基础标准              | 1280×720（统一）                      | 16:9       | 网络视频、HDTV               |
> | 960P        | 非标准准高清              | 1280×960（统一）                      | 4:3        | 4:3 屏幕监控、老式投影仪     |
> | 1080P       | 全高清标准                | 1920×1080（统一）                     | 16:9       | 蓝光、主流显示器、高清录像   |

> **MDVR导出视频验证结果**
>
> <b>PAL</b>
>
> | 文件名                       | 设置分辨率 | 分辨率（宽 × 高） | Quality | 格式   | 文件大小（字节） | 时长（秒） | 总比特率（bps） | 视频格式 | 视频比特率（bps） | 帧率（fps） | 音频格式 | 音频比特率（bps） | 声道数 | 采样率（Hz） |
> | ---------------------------- | ---------- | ----------------- | ------- | ------ | ---------------- | ---------- | --------------- | -------- | ----------------- | ----------- | -------- | ----------------- | ------ | ------------ |
> | CH1-250627-084600-084700.mp4 | WHD1       | 960×288           | 1       | MPEG-4 | 4813147          | 61.056     | 630653          | AVC      | 585816            | 25.000      | AAC      | 43294             | 1      | 8000         |
> | CH2-250627-084600-084700.mp4 | WCIF       | 480×288           | 6       | MPEG-4 | 1439745          | 61.056     | 188646          | AVC      | 144651            | 25.000      | AAC      | 42120             | 1      | 8000         |
> | CH3-250627-084600-084700.mp4 | HD1        | 704×288           | 8       | MPEG-4 | 1640402          | 60.961     | 215272          | AVC      | 173591            | 25.000      | AAC      | 39332             | 1      | 8000         |
> | CH4-250627-084600-084700.mp4 | D1         | 704×576           | 8       | MPEG-4 | 5342181          | 61.056     | 699971          | AVC      | 658770            | 25.000      | AAC      | 39888             | 1      | 8000         |
>
> <b>NTSC</b>
>
> 测试设备仅支持PAL，暂未验证
>
> 
>
> *==视频文件属性使用[MediaInfo](https://mediaarea.net/en/MediaInfo)进行导出==*



### 视频录制中的主码流和子码流

> 在多码流编码中，一个视频源可以同时生成多个视频流，每个流具有不同的分辨率、帧率或比特率，以适应不同的使用需求。
>
> 例如，一个监控摄像头可能同时生成一个高分辨率的主码流用于存储，以及一个低分辨率的子码流用于实时监控。这样可以在保证视频质量的同时，优化存储空间和网络带宽的使用。
>
> | 特性         | 主码流                                                       | 子码流                                                    |
> | ------------ | ------------------------------------------------------------ | --------------------------------------------------------- |
> | **定义**     | 主码流是视频录制中的主要视频流，通常用于高质量的视频存储或传输。 | 子码流是辅助视频流，通常用于低带宽或低存储需求的场景。    |
> | **分辨率**   | 较高分辨率（如1080p、4K等），适合高质量视频录制和播放。      | 较低分辨率（如480p、720p等），适合低带宽传输或存储。      |
> | **码率**     | 码率较高，通常在数Mbps到数十Mbps之间，保证视频质量。         | 码率较低，通常在几百kbps到1Mbps之间，节省带宽和存储空间。 |
> | **用途**     | 用于本地高清存储、高清视频会议、高质量视频监控等。           | 用于移动设备预览、远程监控、低带宽网络传输等。            |
> | **存储空间** | 占用存储空间较大，适合对视频质量要求较高的场景。             | 占用存储空间较小，适合存储空间有限的场景。                |
> | **传输带宽** | 需要较高的网络带宽支持，适合网络条件较好的环境。             | 对网络带宽要求较低，适合网络条件较差的环境。              |
> | **应用场景** | 高清视频录制、专业视频制作、高清视频监控等。                 | 移动设备预览、远程监控、视频会议的预览流等。              |
>
> > [!CAUTION]
> >
> > 关闭子码流使能后，录像预览会显示为<kbd>未编码</kbd>
> >
> > ![关闭子码流使能](https://cdn.jsdelivr.net/gh/maozuxiao/Image-shack/image-20250625091350269.png)



### 音视频编码参数



_^tab^_



> **编码标准**
>
> - **H264**：应用广泛的视频编码标准，在**压缩效率与兼容性间实现较好平衡**_~Gn~_，可在相对低码率下提供不错的视频质量，适配众多设备与平台，如网络视频播放、常规视频监控等场景 。
> - **H265（HEVC）**：新一代视频编码标准，**压缩效率优于 H264，相同画质下能降低约 50% 码率**_~Gn~_，**不过对设备解码性能要求更高**_~Rd~_，适合超高清视频（如 4K/8K 内容）、高画质视频监控等场景 。
>
> <b>视频编码标准用于规定视频数据的压缩、编码与解码方式，影响视频画质、体积及设备兼容性</b>
>
> | 编码标准            | 优势                                                         | 劣势                                                         | 应用场景                                                     |
> | ------------------- | ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ |
> | *H264`MDVR 默认值`* | 兼容性极强，多数设备、平台广泛支持；压缩效率适中，平衡画质与存储 / 传输成本 | 相比 H265，相同画质下码率更高、体积更大                      | 网络视频播放（如早期短视频平台）、常规视频监控、视频会议（通用场景） |
> | H265（HEVC）        | 压缩效率高，相同画质码率可降约 50%，节省存储与带宽；适配超高清内容 | 解码对设备性能要求高，老旧设备可能不支持；编码计算复杂度高，耗时久 | 超高清视频监控（4K/8K 场景）、高端视频会议、4K/8K 影视内容分发 |

> **编码模式**
>
> - **CBR（Constant Bit Rate，恒定码率）**：**编码时维持码率稳定，便于网络带宽规划**_~Gn~_，让视频流输出速率均匀。但复杂场景可能因维持码率损失画质，简单场景易造成带宽浪费，常用于对带宽稳定性要求高的直播、传统广播等场景 。
> - **VBR（Variable Bit Rate，可变码率）**：**依据视频内容复杂度动态调整码率**_~Gn~_，复杂场景（如激烈运动画面）用高码率保障画质，简单场景（如静态画面）用低码率节省带宽，更智能适配内容，多用于视频点播、影视制作素材采集等场景，不过码率波动可能给传输存储带来挑战 。
>
> <b>编码模式决定视频码率分配策略，影响画质稳定性、带宽适配性，是编码流程的关键调控逻辑</b>
>
> | 编码模式                       | 优势                                                         | 劣势                                                         | 应用场景                                                     |
> | ------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ |
> | CBR（恒定码率）                | 码率稳定，便于网络带宽规划（如直播推流）；输出流均匀，适配对速率敏感的传输场景 | 复杂场景易因强行控码率损失画质；简单场景会浪费带宽，造成存储 / 传输冗余 | 直播（如赛事、活动直播）、传统广播系统（固定带宽分发）、对速率稳定性要求高的监控（专网小范围传输） |
> | *VBR（可变码率）`MDVR 默认值`* | 智能适配内容复杂度，复杂场景高码率保画质，简单场景低码率省资源；整体更高效利用带宽 / 存储 | 码率波动大，可能干扰网络传输（如弱网环境卡顿）；对设备缓存   |                                                              |

> **音频编码格式**
>
> - **G711A**：语音通信常用的 PCM 变体，编码简单，语音场景音质可接受，码率相对固定（单声道常为 64kbps ），数据量大，适用于传统电话系统、简单语音对讲（如老式门禁对讲）等场景 。
> - **G711U**：与 G711A 类似，同为语音通信编码，仅量化方式等有差异，用于保障语音通话质量，在传统语音交互场景（如部分电话系统）应用，码率通常也为 64kbps 单声道左右 。
> - **ADPCM（Adaptive Differential Pulse Code Modulation）**：通过预测算法减少音频数据量，自适应调整量化步长，能在较低码率下尽量保留音频质量，适合对音频质量有一定要求且需节省带宽 / 存储的场景，如嵌入式设备音频交互、低端音频存储等 。
>
> <b>音频编码格式定义音频数据的压缩规则，影响音质、数据量及场景适配性，服务于语音 / 音频的高效传输与存储</b>
>
> | 音频编码格式         | 优势                                                         | 劣势                                                         | 应用场景                                                     |
> | -------------------- | ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ |
> | *G711A`MDVR 默认值`* | 语音还原度高，通话场景音质清晰；编码解码简单，设备适配成本低 | 码率高（单声道 64kbps ），占用带宽 / 存储大；仅适配语音，不适合音乐等复杂音频 | 传统电话系统（PSTN 网络）、简单语音对讲（门禁、调度通话）、基础语音质检场景 |
> | G711U                | 与 G711A 功能类似，语音场景音质可靠；算法差异适配部分设备偏好 | 同 G711A，码率高、适用场景窄；仅聚焦语音，扩展性差           | 与 G711A 重叠，如部分地区 / 设备定制化语音系统、特定语音终端（因算法兼容选用） |
> | ADPCM                | 低码率下保留音频基本质量；自适应调整量化步长，适配简单音频场景 | 音质上限低，复杂音频（如音乐）会失真；编码依赖预测算法，极端场景可能出错 | 嵌入式设备音频交互（如智能硬件语音反馈）、低端音频存储（如老旧录音设备）、简单音频监控（如环境声音采集） |



### N9M & ONVIF 协议


> | **对比维度**   | **N9M 协议**                                                 | **ONVIF 协议**                                               |
> | -------------- | ------------------------------------------------------------ | ------------------------------------------------------------ |
> | **协议性质**   | Streamax 私有协议                                            | 开放性行业标准                                               |
> | **兼容性**     | 仅限Streamax 设备                                            | 支持多品牌设备互操作                                         |
> | **技术公开性** | [客流仪N9M网络对接协议_20230906.pdf](https://wj.streamax.com:9443/preview.html?fileid=67fcb820-e3fb-497a-aaf6-fb9c2dc1c8cb) | 规范公开，可免费获取[<kbd>📝点击获取</kbd>](https://www.onvif.org/ch/profiles/specifications/) |
> | **应用范围**   | 中小型单一品牌系统                                           | 大型跨品牌集成系统                                           |
> | **标准化组织** | 无                                                           | ONVIF 论坛（非盈利组织）                                     |
> | **开发支持**   | 依赖厂商提供的 SDK                                           | 提供公开的 API 和开发文档                                    |



### P frame和 I frame的区别

>| **对比维度**         | **I 帧（Intra - coded Frame）帧内编码帧**                    | **P 帧（Predicted Frame）前向预测编码帧**                    |
>| -------------------- | ------------------------------------------------------------ | ------------------------------------------------------------ |
>| **编码方式**         | 帧内编码，完全自包含，采用 JPEG 压缩编码全帧图像信息。       | 帧间编码，通过参考前一帧数据预测当前帧，仅编码与前一帧的差异。 |
>| **数据完整性**       | 包含完整图像信息（背景和运动主体详情），是全帧压缩编码帧。   | 不包含完整图像信息，仅记录与前面 I 帧或 P 帧的差值及运动矢量。 |
>| **解码依赖性**       | 可独立解码，无需参考其他帧，常作为视频流起始点或恢复点。     | 解码时必须参考前面最近的 I 帧或 P 帧，需结合参考帧重构图像。 |
>| **压缩效率**         | 压缩效率较低，文件体积较大，但画面质量较稳定。               | 压缩效率高于 I 帧（低于 B 帧），文件体积更小，仅编码帧间差异。 |
>| **在视频流中的作用** | 是 P 帧和 B 帧的参考帧，决定同组后续帧质量；作为 GOP 基础帧，支持随机访问和错误恢复。 | 可作为后续 P 帧或 B 帧的参考帧，但解码错误可能扩散影响后续帧。 |



### 如何确认MDVR保险丝状态



> 要确认MDVR（移动硬盘录像机）的保险丝是否断裂，可以从外观和电阻值两个方面进行检查。首先，观察保险丝的金属丝是否完整，有无断裂或烧焦痕迹。其次，可以使用万用表测量保险丝的电阻值，正常保险丝电阻值接近零，而断裂的保险丝电阻值会是无穷大。
>
> 
>
> 具体步骤如下:
>
> 
>
> 1. **断电:**在进行任何检查之前，务必断开MDVR的电源，以确保安全。
>
> 2. **外观检查:**
>
>    - **正常保险丝:**保险丝的金属丝应该是完整的，表面光滑，没有断裂、烧焦或变形的迹象。
>      ![image-20250630093333345](https://cdn.jsdelivr.net/gh/maozuxiao/Image-shack/image-20250630093333345.png#20%)
>    - **断裂的保险丝:**金属丝中间断开，或者保险丝表面有烧焦痕迹（黑色或棕色）。
>
> 3. **万用表测量:**
>
>    - 将万用表调到电阻档。
>
>    - 将万用表的表笔分别接触保险丝的两端。
>
>      > **正常保险丝:**电阻值接近零欧姆。
>      >
>      > **断裂的保险丝:**电阻值会显示为无穷大（通常是“OL”或“1”）。



###  P3 V3.0 车载客流统计仪与 P3-AHD 摄像机的特性及搭配使用

> ---
>
> - [P3 V3.0](https://wj.streamax.com:9443/preview.html?fileid=3867f511-3656-42bc-b9af-b4e398ba28c5)
>
>   P3 V3.0是一款专业车载客流统计仪，内含人工智能算法，是P3客流仪的升级版本（V3.0）。其核心特性如下：
>
>   - **功能定位**：使用AI算法准确判断乘客进出方向，统计上下车客流量。支持通过网络接口将客流数据同步到车载主机，并上传至平台进行分析
>   - 核心优势：
>     - **AI客流统计**：基于深度学习，支持客流方向判断、大人小孩识别、轮椅/单车/婴儿车识别（选配）。
>     - **智能图像处理**：支持自动曝光、自动白平衡、自动降噪，以及基于AI的车辆开关门识别。
>     - 高分辨率支持：1920×1080@30fps。
>     - 宽动态范围：2F WDR动态范围≥80db。
>     - 全天候工作：适应车载环境。
>     - 网络功能：内置Web Server，支持IE浏览器访问，10M/100M自适应以太网接口。
>   - 关键规格参数：
>     - **Sensor类型**：1/2.8'' 2M pixel CMOS（与P3-AHD类似，但焦距更新为2.7mm）。
>     - **电子快门**：1/60秒至1/5000秒（比P3-AHD范围更窄）。
>     - **视频编码**：支持H.264和H.265，压缩码率512Kbps-10Mbps。
>     - **接口**：支持RS485、USB、Sensor输入（4路）。
>     - **尺寸**：类似P3-AHD（嵌入式188.05mm×67.04mm×33mm）。
>     - **工作环境**：与P3-AHD一致（温度-30℃至+70℃，湿度0%-90%）。
>
>   ==P3 V3.0是处理核心，依赖外部视频输入进行客流分析。==
>
> - [P3-AHD](http://oa.streamax.com:8080/sys/attachment/sys_att_main/sysAttMain.do?method=view&fdId=17264fd8d2d9fb0df7e7ff4460684630)
>
>   P3-AHD是一款专业车载摄像机，主要用于客流统计场景。其核心特性如下：
>
>   - **功能定位**：**搭配P3客流仪使用**_~Rd~_，提供视频图像输入。通过P3客流仪的AI算法，判断乘客进出方向，精准统计上下车客流量
>   - 核心优势：
>     - 支持高分辨率视频：1920×1080@30fps。
>     - 宽动态范围：适应多种车辆运行环境（如光线变化）。
>     - 全天候工作：能在不同光照和温度条件下稳定运行。
>     - 抗震设计：符合车辆抗震要求，适应车载环境。
>     - 多种安装方式：支持嵌入式、吊顶和侧向安装，适应不同车型。
>   - 关键规格参数：
>     - **Sensor类型**：1/2.8'' 2M pixel CMOS。
>     - **最低照度**：彩色模式下0.05Lux/F1.2；黑白模式下0Lux（红外开启）。
>     - **焦距和视角**：M12型2.6mm镜头，水平视角120°，垂直视角62.5°。
>     - **功耗**：<3W，输入电源DC12V。
>     - **工作环境**：工作温度-30℃至+70℃，存储温度-40℃至+85℃，湿度0%-90%。
>     - **尺寸**：根据安装方式不同（如嵌入式：188.05mm×67.04mm×33mm）。
>
>   ==P3-AHD本身不具备AI处理能力，仅作为视频采集设备。==
>
> **搭配方式**：
>
> - P3-AHD摄像机作为视频采集设备，安装在车辆入口/出口处（如车门上方），捕捉乘客视频流。
> - P3 V3.0客流统计仪作为处理单元，接收P3-AHD的视频输入。
> - P3 V3.0通过内置AI算法分析视频，识别乘客进出方向、统计客流量，并处理高级功能如大人小孩识别或轮椅检测。
> - 客流数据通过网络接口（如以太网）同步到车载主机或上传至云平台，用于车队管理和数据分析。
>
> **优势**：
>
> - **互补性**：P3-AHD提供高质量视频输入（高分辨率、宽动态），P3 V3.0提供AI处理能力，形成完整的客流统计系统。
> - **安装灵活性**：两款产品均支持多种安装方式（嵌入式、吊顶、侧向），适应不同车型，确保系统稳定。
> - **效率提升**：在公交或客运场景中，这种搭配能实现自动化客流统计，减少人工干预，提高数据准确性。
>
> > [!NOTE]
> >
> > **P3 V3.0** 支持以下两种电源规格
> >
> > | **电源类型** | **电压范围**    | **功耗** | **接口方式**                                                 | **优势**                 | **接口线缆定义**                                             |
> > | ------------ | --------------- | -------- | ------------------------------------------------------------ | ------------------------ | ------------------------------------------------------------ |
> > | **PON**      | 9V–16V (DC12V)  | <3W      | ==RS765-6 航空母头3号pin口提供12V电压（红线）==              | 兼容传统车辆电源系统     | ![PON接口线缆定义](https://cdn.jsdelivr.net/gh/maozuxiao/Image-shack/image-20250703092011140.png) |
> > | **POE**      | 37V–57V (DC48V) | <3.8W    | ==网线供电（M12/航空头），遵循 IEEE 802.3af/at 标准，通过以太网线将电源和数据信号同时传输给连接设备。M12 航空头作为连接接口，内部的供电引脚与网线中的相应线对相连，实现供电功能== | 一线多用，减少布线复杂度 | ![POE接口线缆定义](https://cdn.jsdelivr.net/gh/maozuxiao/Image-shack/image-20250703092201995.png) |
> >
> > **注**：
> >
> > - 接入从机设备时，功耗会升至 **<5W（PON）** 或 **<5.8W（POE）**。
> > - 两种模式均支持宽压输入，适应车辆复杂电气环境。

## 第一阶段考核



### 如何设置并触发报警录像

_^tab^_

>   **MDVR设置**
>
>   1. Log in WebUI
>   2. Access Config>>Surveillance>>Record>>Main Stream
>      1. *Record mode`Alam`* 
>
>   3. Access Config>>Alarm, Config the Alarm settings
>     4. Base
>        1. lO Alarm
>        2. Speed Alarm
>        3. Panel Alarm
>        4. GPS Alarm
>     5. Video
>        1. Video Loss
>        2. Motion
>        3. Cover
>        4. Privacy Mode
>     6. Advanced
>        1. Driver Behavior Alarm
>        2. Geo-Fence
>     7. AI App
>        1. ADAS
>        2. DMS
>        3. BSD
>        4. Calibration Parameter
>        5. Alarm Notifications
>        6. Algorithm Calibration

>   **视频演示**
>
>   ![How_to_set_alarm_recording](https://cdn.jsdelivr.net/gh/maozuxiao/Image-shack/How2set_alarm_recording.mp4)



### 平时主机不需要录像，当IO1报警产生时，需要预录和后录1分钟，如何实现

_^tab^_

>   **MDVR设置**
>
>   1. Log in WebUI
>   2. Access Config>>Surveillance>>Record>>General
>      1. *Pre-recording`1 Min`*
>
>   3. Access Config>>Surveillance>>Record>>Main Stream
>      1. *Record mode`Alam`* 
>
>   4. Access Config>>Alarm>>Base>>IO Alarm
>     5. Click “Enable” checkbox of “Sensor1”
>     6. Setup `Trigger`
>        1. *Trigger Source`Source Voltage`*
>        2. *Trigger`High`*
>        3. *Effective Time`5 Seconds`*
>     7. Setup `LinkPage`
>        1. *Channel`1`*
>        2. *Post Recording`1 Min`*
>        3. *Lock`☑`*

>   **连线图示**
>
>   1. MDVR连接Sensor & Serial线
>   2. SENSOR IN1与+5V导线相连，模拟高电平状态
>
> <iframe frameborder="no" border="0" marginwidth="0" marginheight="0" width=833 height=401 src="https://edrawcloudpublicus.s3.amazonaws.com/viewer/self/2539370/share/2025-7-1/1751340446/main.svg"></iframe>

>   **视频演示**
>
>   ![S1_alarm_recording](https://cdn.jsdelivr.net/gh/maozuxiao/Image-shack/S1_alarm_recording.mp4)

### 需要报警抓拍上传到指定FTP，并同时在设备导出至PC查看

_^tab^_

>  **MDVR设置**
>
> 1. Log in WebUI
> 2. Access Config>>Basic Setup>>Application>>FTP Server
>    1. *FTP Enable`☑`*
>    2. *Server`Server IP`*
>    3. *Port`FTP Port`*
>    4. *User Name`FTP UserName`*
>    5. *Password`FTP Password`*
> 3. Access Config>>Collection>>Snap Setting>>Trigger Snap>>Alarm Snap>>Snap Link>>Setup>>Channel
>    1. *Snap Enable`☑`*
>    2. *Upload Type`FTP`*
>    3. *Snap Numbers (1~3)Pcs`3`*
>    4. *Interval (5~3600)Seconds`30`*
> 4. Access Config>>Alarm>>Base>>IO Alarm
>    1. Click “Enable” checkbox of “Sensor1”
>    2. Setup `Trigger`
>       1. *Trigger Source`Source Voltage`*
>       2. *Trigger`High`*
>       3. *Effective Time`5 Seconds`*
>    3. Setup `LinkPage`
>       1. *Channel`1`*
>       2. *Post Recording`1 Min`*
>       3. *Lock`☑`*
>       4. *Alarm snap`☑`*

> **设置视频**
>
> ![Alarm_Snap](https://cdn.jsdelivr.net/gh/maozuxiao/Image-shack/Alarm_Snap.mp4)

> **导出抓拍图片**
>
> 1. Login CP4 GUI
> 2. Click Setup>>Maintenance>>FileData>>Data Export
>    1. ◉Export Time
>    2. Start Time
>    3. End Time
>    4. *File Type`Captured Picture`*
> 3. Click <kbd>Export</kbd>

> **导出视频**
>
> ![export_alarm_snapshot](https://cdn.jsdelivr.net/gh/maozuxiao/Image-shack/export_alarm_snapshot.mp4)
>
> 


### 设备没能正常录像，如何处理

> 1. **检查电源连接**：确保 MDVR 已正确连接到电源插座，且电源线无损坏、保险丝正确安装，确保MDVR 的电源稳定，无电压过低或波动情况。可尝试更换其他电源插座进行测试，若问题依旧，可能是电源适配器故障，需更换电源适配器。
> 2. **查看设备连接**：确认 MDVR 与摄像头等其他设备的连接正常，连接端口有无损坏。若连接线松动或损坏，应更换新的连接线。
> 3. **检查摄像头** ：查看摄像头是否正常安装，有无遮挡、故障或电源问题。可尝试更换摄像头或将其连接到其他正常设备上测试。若摄像头本身有问题，需维修或更换。
> 4. **排查存储设备**：检查硬盘或存储卡是否正确安装，必要时刻需考虑先格式化存储设备。若存储设备存在故障，需对其进行修复或更换。
> 5. **核对设置参数**：
>    1. 进入 MDVR 设置界面，检查日期、时间设置是否正确，是否有定时录像
>    2. 进入 MDVR 设置界面，查看视频编码格式、分辨率、帧率、`PAL & NTSC`系统设置等参数是否设置正确。如果参数设置不正确，按实际情况进行调整
>    3. 进入 MDVR 设置界面，检查是否有太多的加锁录像，导致存储剩余空间不足；检查是否未打开录像覆盖功能，导致存储空间不足
>    4. 进入 MDVR 设置界面，检查录像通道使能开关是否打开；检查是否设置报警录像但关闭报警使能开关
> 6. **处理软件问题**：尝试重新启动 MDVR，看是否能恢复正常录像。若设备有可用的软件更新，可更新到最新版本，以修复可能存在的软件漏洞。若问题仍未解决，可尝试将设备恢复出厂设置，但需注意此操作会清除原有设置，需重新进行配置。


### 设备上报服务器的操作步骤

>  1. Navigate to http://10.100.100.1/
>  2. Click `Config`>>`Network`
>  3. Config the servers parameters under `Server Setup`，以下为示例，其中`Register Server IP`可以是服务器IP或者URL，但是不能包含/字符
>     1. *ON`☑`*
>     2. *Protocol Type`N9M`*
>     3. *TLS Enable`☐`*
>     4. *Enable Network`示例：WIFI，也可选择Local或者Module`*
>     5. *Register Server IP`uat-saas.streamamax.com`*
>     6. *Register Server port`TCP 21803`*
>     7. ~~*Register Server TLS`5556`*~~
>     8. *Media Server IP`58.250.161.103`*
>     9. *Media Server port`TCP 21803`*
>     10. ~~*Media Server TLS`5556`*~~
>  4. Click `Maintenance` >>`Server Status` to check the **Server Connect Status**_~Cy~_
>
>  > [!NOTE]
>  >
>  > 由于缺少测试账号，设备上报服务器后的步骤暂时没办法测试
>  >
>  > [<kbd>用户手册参考 > ></kbd>](https://uat-saas.streamax.com/ftm/docs/help-center?appId=10001&tab=product-doc)


### 如何查线序

> <kbd>[内部知识库搜索设备规格书>>](#如何查设备规格书)</kbd>>>搜索关键词`Cable Connector Pinouts`
>
> > [!NOTE]
> >
> > 线序信息除了在规格书中存在，还在安装手册中可以找到，关键词 `Installation `，比如X3N Installation 


### 如何查设备规格书

> * **鸿翼服务器**：企业内容库>STREAMAX 锐明技术>Overseas department>Europe>Product list；也可使用模糊查找功能，比如搜索关键词`X3N specification`
> * **OA**：使用模糊查找功能，比如搜索关键词`X3N specification`


### 实现U盘自动升级

> 1. 准备一个 U 盘，并将其连接到电脑。
>
> 2. 在 U 盘根目录下，新建名为 `autoupgrade`的文件夹
>
>    > 比如："E:\autoupgrade\X3N_AI_V3.5.6.8_T240508.02_M0010"
>
> 3. 把需要用于升级的文件复制并粘贴到 “autoupgrade” 文件夹内。
>
> 4. 确保所有升级文件已正确放置后，安全弹出 U 盘。
>
> 5. 将该 U 盘插入目标MDVR设备，设备会自动识别并开始升级流程。
>
> > [!WARNING]
> >
> > 1. 各个版本之前存在差异，相同型号的软件不同分支可能存在隔离导致无法升级。升级前需要内部确认当前版本能否升级到待升级版本
> > 2.  `autoupgrade`目录下只放1个待升级文件


### 如何实现设备熄火后15分钟关机

_^tab^_

> **点火关机延迟**
>
> 1) 只有在**点火开机(Ignition)状态**下才起效；关闭车钥匙进入点火关机延时处理，并在直通界面提示倒计时关机时间，延时时间可设置（0~86399秒）
> 2) 如果操作界面停留在设置界面，则不进入倒计时，但退出到直通界面则进入倒计时

> **操作步骤**
>
> Setup>>Basic Setup>>Startup>>ON/OFF>>Ignition Delay>><kbd>900（15分钟）</kbd> *0`~`86399*Seconds
>
> ![设备熄火后15分钟关机](https://cdn.jsdelivr.net/gh/maozuxiao/Image-shack/%E7%86%84%E7%81%AB%E5%90%8E15%E5%88%86%E9%92%9F%E5%85%B3%E6%9C%BA.mp4)

> **模拟测试接线**
>
> <iframe frameborder="no" border="0" marginwidth="0" marginheight="0" width=967 height=533 src="https://edrawcloudpublicus.s3.amazonaws.com/viewer/self/2539370/share/2025-6-30/1751265660/page-1.svg"></iframe>

> [!IMPORTANT]
> 
> **模拟车辆熄火**：*ACC` &` DC IN+* 与适配器的DC母口的正极连接在一起，<kbd>DC IN-</kbd>与适配器的DC母口的负极连接在一起，断开ACC的连接
> 
> **模拟车辆点火**：**模拟车辆熄火后**_~Rd~_，<kbd>DC IN+</kbd>与适配器的DC母口的正极连接在一起，<kbd>DC IN-</kbd>与适配器的DC母口的负极连接在一起，连接*ACC` &` DC IN+* 

### 如何实现设备IO唤醒/G-sensor唤醒

_^tab^_

> **MDVR设置**
>
> 1. Log in WebUI
>
> 2. Access Config>>Startup>>Sleep
>
>    1. *Sleep Mode`Low power standby`*
>
> 3. Access Config>>Startup>>Wake
>
>    1. *IO Wake`√`*
>
>    2. *G-sensor Wake`√`*(降低阈值以方便测试)
>1. *X Threshold`0.1`*
>       
>2. *Y Threshold`0.1`*
>       
>3. *Z Threshold`0.1`*

> **模拟测试接线**
>
> 1. ACC连接DC IN+点火启动MDVR
> 2. ACC断开DC IN+模拟MDVR休眠
> 3. 外接一个DC IN+给SENSOR IN1模拟IO唤醒；或者摇晃MDVR触发G-sensor唤醒
>
>  <iframe frameborder="no" border="0" marginwidth="0" marginheight="0" width=1946 height=1301 src="https://edrawcloudpublicus.s3.amazonaws.com/viewer/self/2539370/share/2025-6-30/1751265660/page-2.svg"></iframe>


### 如何使用电脑浏览器导出设备视频

> 1. **登录**：登录WebUI，访问“PlayBack”
> 2. **选择日期**：在日历区域，点击要查询视频的日期（如 2025 - 07 - 01 ）
> 3. **设置时间范围**： “Start Time” 栏输入起始时间（如 09:25:00  ），“End Time” 栏输入结束时间（如 23:59:59  ） 。  
> 4. **选择通道**：在 “Channel” 区域，勾选要查询的通道（可全选或按需选，如示例中 1 - 8 通道  ） 
> 5. **搜索视频**：点击 “Search” 按钮，检索对应日期、时间、通道的视频  
> 6. **查看列表**：点击“Record List”按钮。列出符合筛选规则的视频条目
> 7. **下载视频**：列表在右侧显示，若需下载，点击视频条目旁 “Download” 按钮 
>
> ![DL_Video_WebUI](https://cdn.jsdelivr.net/gh/maozuxiao/Image-shack/DL_Video_WebUI.mp4)


### 如何配置SD卡子码流录像和硬盘双码流录像

> Open WebUI>>Login Account>>Config>>Surveillance>>Record>>General
>
> * **SDRecord Mode**_~Rd~_ set as `Sub-Record`
> * Enable **HDD Double Recording**_~Rd~_ 
>
> 
>
> ![SD_SuBRecord_HDD_Double_Recording](https://cdn.jsdelivr.net/gh/maozuxiao/Image-shack/SD_SuBRecord_HDD_Double_Recording.mp4)


### 导出设备视频有多少种方式，分别是什么

> 导出视频有4种方式，分别是
>
> 1. 通过浏览器登录WebUI导出
> 2. U盘导出
> 3. 通过专用软件[<kbd>CEIBA2 Client</kbd>](http://jfwiki.streamax.com:7503/web/#/172/4819)导出
>    1. 登录账号：*Type`Local`* *User`admin`* *Password`空`*
>    2. 连接硬盘/SD卡,点击侧边栏的目录刷新按钮即可识别目录
>    3. 通过日历组件选择需要导出的录像日期
>    4. 点击时间轴上放的clip✂️按钮
>    5. 通过拖动时间轴上的虚线来选取开始和结束时间，点击`OK`
>    6. 配置`Clip Settings`>>选择导出的格式
>       1. Standard: 包含log和Raw H.264以及265格式的文件（如需播放H264/H265 Data文件需要下载解码器，比如[K-Lite Codec Pack](https://www.codecguide.com/download_kl.htm)才能播放，并且不能调节时间）
>       2. Export: EXE格式文件，通过Ceiba2打开
>       3. MP4: MP4格式的视频文件
>    7. 配置`Clip Settings`>>选择路径 & 主码流/子码流
> 4. FT Cloud导出


### 升级设备的有多少种方式，分别是什么

> 升级设备有3种方式，分别是
>
> 1. WebUI升级
> 2. U盘升级(运维宝)
> 3. FT Cloud升级


### 📍批量对设备进行参数配置的步骤是什么？哪一类参数能/不能进行批量配置？

> 


### 如何查询某运营商的APN参数并对设备进行设置

_^tab^_

>  **获取APN参数**
>
>  1. Google检索该运营商的IoT APN参数
>  2. 通过<kbd>[Global IoT APN List](https://maozuxiao.github.io/my-website/Apn_list.html)</kbd>进行检索
>  3. 把SIM卡插入其他通信设备上进行查看

>  **配置APN参数**
>
>  ---
>
>  - GUI
>
>    路径：Setup>>Basic Setup>>Network>Communication Module
>     ![GUI Set Apn](https://cdn.jsdelivr.net/gh/maozuxiao/Image-shack/Gui_set_apn.mp4)
>
>  - WebUi
>
>    路径：Config>>Network>>Communication Module ![WebUI Set Apn](https://cdn.jsdelivr.net/gh/maozuxiao/Image-shack/Webui_set_apn.mp4)

------

### 保险丝的电流大小应该如何选择？

_^tab^_

>  **保险丝选择方法**
>  
>  保险丝的选择需要根据**车电系统的电压**，电压为`12V`时选择**7.5A Fuse**_~Rd~_，电压为`24V`时选择**15A Fuse**_~Bu~_
>
>  | Model               | Picture                                                      | Part No.      | Application Scenario                         | Part No.  Description                                        |
>  | ------------------- | ------------------------------------------------------------ | ------------- | -------------------------------------------- | ------------------------------------------------------------ |
>  | **7.5A Fuse**_~Rd~_ | ![7.5A Fuse](https://cdn.jsdelivr.net/gh/maozuxiao/Image-shack/image-20250627112227582.png) | 1060970000006 | Voltage of vehicle electrical system = `12V` | Female  Connector Mounted Fuse \| Plug-in Common Type \| 32V \| 7.5A \| 028707.5 |
>  | **15A Fuse**_~Bu~_  | ![15A  Fuse](https://cdn.jsdelivr.net/gh/maozuxiao/Image-shack/image-20250627112331262.png) | 1060970000005 | Voltage of vehicle electrical system = `24V` | Female  Connector Mounted Fuse \| Plug-in Common Type, Blue Shell \| 32V \| 15A \|  0287015 |

>  **保险丝工作原理**
>
>  保险丝利用**电流热效应**工作，核心原理基于焦耳定律 $$ Q = 0.24I^2RT $$（*Q* 为发热量，*I* 是电流，*R* 是电阻，*T* 是时间 ），具体过程：
>
>  1. **正常工作**：电流小于额定值，保险丝电阻 *R* 稳定，产热（*Q* ）速度 ≤ 散热速度，温度稳定，不熔断。
>  2. **过载 / 短路时**：电流异常升高，*I* 增大使 *Q* 急剧增加，产热速度＞散热速度，热量累积致温度上升，达到保险丝熔体（由低熔点合金等制成）熔点时，熔体熔断，切断电路，保护设备。
>



### 如何区分是SMR还是CMR的硬盘

_^tab^_

>  **什么是CMR和SMR?**
>
> * 垂直盘（即CMR，在某些场合也称为垂直磁记录PMR）曾经的主流技术，采用独立平行的磁道布局，相邻磁道间保留物理间隙。磁头可直接读写目标磁道，无需干扰相邻数据区域，实现高效操作。
> * 叠瓦盘（SMR）相对的新技术，采用类似屋顶瓦片的重叠磁道设计，取消磁道间隙以提升存储密度（相同盘片容量可提升约25%）。其写入新数据时需先读取并修改重叠区域的相邻磁道数据，再进行整体重写，操作更复杂。

> **可以通过如下方式来区分硬盘类型**_~Rd~_
>
> ---
>
> - 公司提供
>   1. <kbd>[OA搜索关键词：存储推荐> >](http://oa.streamax.com:8080/kms/multidoc/index.jsp?j_module=true#cri.q=docSubject%3A%E5%AD%98%E5%82%A8%E6%8E%A8%E8%8D%90)</kbd>，找到最近的存储推荐表
>   2. 查阅表格：搜索型号如MQ01ABD100V，即可在表中找到对应信息
> - 客户自购
>   1. **品牌官网查阅官方文档**：通过查看硬盘品牌官方文档，获取该型号硬盘的相关信息来确定硬盘类型
>   2. **缓存大小**：叠瓦式（SMR）硬盘通常还有一个典型特征，即便是在低容量下也配备更大的缓存。比如2TB叠瓦盘配备256MB缓存
>   3. **工具检测**：CrystalDiskInfo（Windows）/  HDDScan（Windows）/ GNOME Disks（Linux）
>   4. **性能测试**：
>      CMR（传统磁记录）硬盘在大文件持续写入或随机读写时速度稳定
>      SMR（叠瓦式磁记录）硬盘在写入数据量超过缓存后速度会大幅下降且恢复缓慢，随机写入时明显下降
>   5. **使用场景判断**
>      * **冷数据存储（如影视备份、历史档案），数据一次写入后极少修改**_~Gn~_
>        * 移动硬盘等便携设备（2.5英寸机械盘90%为SMR）
>        * 超大规模冷存储库，优先考虑容量与能耗成本
>      * **频繁读写、`监控领域`：优先采用CMR硬盘方案**_~Gn~_
>        * 需频繁读写的系统盘、数据库、游戏存储
>        * NAS网络存储、RAID阵列及企业级服务器（群晖/威联通等NAS厂商明确禁用SMR盘）
>        * 7×24小时运行的监控与企业级应用（氦气封装硬盘均为CMR）


### 📍如何抓设备的打印，有几种方式？

> 

### 如何区分新旧文件系统/硬盘？使用起来有什么注意事项

_^tab^_

>  **区分新旧文件系统/硬盘**
>
>  连接电脑查看存储设备属性中的文件系统格式
>
>  | 文件系统 | 推出时间            | 典型特性（与 MDVR 适配性）                                   | 新旧定位         |
>  | -------- | ------------------- | ------------------------------------------------------------ | ---------------- |
>  | FAT32    | 1996 年             | 兼容性强，支持多数设备；单文件最大 4GB，不支持超过 2TB 的分区 | 较旧             |
>  | NTFS     | 1993 年（迭代更新） | 支持大文件（无 4GB 限制）、权限管理、日志功能；MDVR 兼容性中等（部分老设备不支持） | 中等（持续更新） |
>  | exFAT    | 2006 年             | 专为移动设备设计，支持大文件和大分区，兼容 Windows 和 Mac；MDVR 新机型普遍支持 | 较新             |
>  | EXT4     | 2008 年             | Linux 系统专用，稳定性强、碎片少，支持大分区；高端 MDVR（基于 Linux 系统）常用 | 较新             |
>
>  **接口**类型：IDE接口为旧硬盘，SATA/NVMe接口为新硬盘
>
>  **物理外观**
>
>  * 包装和标签上的生产日期
>  * 接口与触点是否有插拔痕迹和氧化痕迹

> **使用注意事项**
>
> **FAT32文件系统格式**: 避免存储单文件＞4GB，否则会提示 “文件过大”；分区大小不能超过2TB
>
> 


### 客户提出需求：两路录像，录像需要保存至少两周，你应该怎么推荐硬盘的大小，你还要问什么问题

_^tab^_

> **更多信息**
>
> 1. 视频分辨率 [<kbd>参考这里>></kbd>](#视频分辨率说明) 
> 2. 画质等级 1~8 （默认画质等级：Normal:3；Alarm:2）
> 3. 每天录像时长
> 4. 录像帧率（可选）
> 5. 编码标准（可选）*H264`H265`* 、编码模式（可选） *VBR`CBR`*、音频编码格式（可选）*G711A`G711U`ADPCM*  [<kbd>参考这里>></kbd>](#音视频编码参数)

> **硬盘推荐**
>
> 参考[N9M码率表.xls](https://wj.streamax.com:9443/preview.html?fileid=b6e99bde-26d9-4a92-a6bf-03c9187ed450)，找到客户所需分辨率和画质等级的数据×每天录像时长×14天×2路
>
> > 比如客户选择*分辨率`WD1`*  *画质等级`1`* *每天录像时长`8 H`*，查找表格发现测试数据：*单通道录像文件大小（MB）/小时`1170 MB`*, 则可以给客户推荐 1170×8×14×2=262080 MB=255.9375 GB，考虑冗余情况，建议512 GB以上的硬盘大小。<kbd>[OA搜索关键词：存储推荐> >](http://oa.streamax.com:8080/kms/multidoc/index.jsp?j_module=true#cri.q=docSubject%3A%E5%AD%98%E5%82%A8%E6%8E%A8%E8%8D%90)</kbd>找到最近的存储推荐表提供具体型号给客户

### 📍客户要求联调外设：外置GPS，波特率59600，完成接线与设置，定位失败或者无信号如何处理

> 


### 锐明主机接第三方摄像头测试可行性，主机要设置什么参数，如果无视频画面或录像，如何处理

_^tab^_

> **MDVR设置参数(IP摄像头)**
>
> *Remote Device`Default`*
>
> **Protocol Type`ONVIF`* | N9M是私有协议，IPC的通用协议是ONVIF，<kbd>[请参考N9M & ONVIF 协议 > >](#N9M & ONVIF 协议)</kbd>
>
> *IP Address`示例：10.100.100.101`*
>
> *Port`示例：9006`*
>
> *User Name`示例：admin`*
>
> *Password`示例：[empty]`*
>
> > [!CAUTION]
> >
> > 对接第三方摄像头可能存在第三方AHD摄像头和第三方IP摄像头，但AHD摄像头主要考虑信号制式能否匹配系统设置，没有其他额外的参数设置。
> >
> > 因此该问题的答案是基于第三方摄像头为IPC回复



> **排查无视频画面或无法录像**
>
> 1. **硬件排查**
>    1. 重新插拔接口，或更换其他IPC接口，确认接口无松动、针脚无弯曲 / 氧化
>    2. 测试确认IPC供电端电压电流满足IPC的额定电压/电流需求
> 2. **确认网络连接**：用电脑直连摄像头（需要IPC公对公线缆），通过摄像头*IP`如 192.168.1.100`*登录管理界面，检查是否能正常显示画面，排除摄像头自身故障。
> 3. **协议匹配**：MDVR 需在 “IPC Setup” 中开启 ONVIF 协议，并手动输入摄像头 IP、用户名 / 密码（默认如 admin/admin）
> 4. **录像设置**
>    1. 进入 MDVR 设置界面，检查日期、时间设置是否正确，是否有定时录像
>    2. 进入 MDVR 设置界面，查看视频编码格式、分辨率、帧率、系统设置等参数是否设置正确。如果参数设置不正确，按IPC支持的参数进行调整
>    3. 进入 MDVR 设置界面，检查是否有太多的加锁录像，导致存储剩余空间不足；检查是否未打开录像覆盖功能，导致存储空间不足
>    4. 进入 MDVR 设置界面，检查录像通道使能开关是否打开；检查是否设置报警录像但关闭报警使能开关
> 5. **排查存储设备**：检查硬盘或存储卡是否正确安装，必要时刻需考虑先格式化存储设备。若存储设备存在故障，需对其进行修复或更换。
> 6. **处理软件问题**：尝试重新启动 MDVR，看是否能恢复正常录像。若设备有可用的软件更新，可更新到最新版本，以修复可能存在的软件漏洞。若问题仍未解决，可尝试将设备恢复出厂设置，但需注意此操作会清除原有设置，需重新进行配置。


### 司机投诉CP4常亮，而且声音太大，如何处理

> **声音设置**：Setup>>Basic Setup>>Other Setup>>Voice Setup>>CP4 Voice
>
> **亮度设置**：Setup>>Surveillance>>Live View>>Preview>>Image Setup>>Bright
>
> **息屏设置**（重新生效）：Setup>>Basic Setup>>Startup>>ON/OFF>>Light Off Time>>Custom>>*1`~`3600*Second
>
> ![CP4_Settings_Vol_Bri_LightOff](https://cdn.jsdelivr.net/gh/maozuxiao/Image-shack/CP4_Settings_Vol_Bri.mp4)

### 由于料号搞错，导致客户收到的是侧装的AHD摄像头，但是客户需要是正装摄像头，如何处理？

_^tab^_

> **前置工作**
>
> 1. 查询内部是否有发货错误的解决措施相关的SOP。如有遵循SOP处理，如果没有参考后续步骤
> 2. 确认该AHD摄像头的规格书，确认安装方式是否同时支持正装和侧装
> 3. 尝试修改`Camera Setup`中的`Install Angle` & `Mirror/Flip`设置，测试评估整体的画面效果是否影响摄像头的正常功能
> 4. 与内部确认补发正确料号货物到客户手上所需的时间，成本

> **外部：对接客户**
>
> 1. 主动联系，诚恳道歉
> 2. 倾听客户反馈，记录核心诉求
> 3. 根据客户核心述求，告诉客户`可落地的解决方案`
>    1. 临时解决方案：侧装摄像头通过摄像头设置进行修改，可以达到正装的效果，不影响车辆的正常使用
>    2. 最终解决方案：补寄正确的产品，告知客户预计到货的时间（可在与内部确认的时间上预留点buffer）
> 4. 安排内部发货，提供对应的`订单号`。根据订单号跟进货物的到货状态，在正确料号的摄像头到货后，主动跟进客户的安装使用情况
> 5. 客户完成正确料号摄像头的部署后，感谢客户的耐心和理解，告诉客户我们会优化流程，杜绝错误的再次发生
> 6. 回收错误料号的摄像头

> **内部：优化流程**
>
> 1. 追溯错误原因，排查内部流程
>    1. 订单录入是否错选料号？
>    2. 仓库发货是否未核对料号标签？
>    3. 系统料号与产品型号是否匹配（如侧装 / 正装的料号是否易混淆）？
> 2. 内部整改
>    1. 若为人工失误：加强岗位培训（如发货前 “双人核对料号 + 产品外观”）
>    2. 若为系统漏洞：优化料号命名规则（如在料号中明确标注 “正装 - Z”“侧装 - C”），或增加系统校验（如订单备注 “正装” 时，自动匹配对应料号）
> 3. 优化/输出SOP以应对该类典型问题，SOP的背景部分可以添加补发货物所需的时间和成本


### 📍客户投诉设备缺失WIFI/GPS/4G模块，如何排查并证明设备没有问题？

> 


### 客户要求某报警产生后，需要联动一个蜂鸣器，如何设置（用万用表去验证）

_^tab^_

> **MDVR设置**
>
> 1. Log in WebUI
> 2. Access Config>>Alarm>>Base>>IO Alarm
>   3. Click “Enable” checkbox of “Sensor1”
>   4. Setup `Trigger`
>      1. *Trigger Source`Source Voltage`*
>      2. *Trigger`High`*
>      3. *Effective Time`5 Seconds`*
>   5. Setup `LinkPage`
>      1. *Linkage IO Output`☑1`*
>      2. *Output Delay Time`0`*
>
> **连线图示**
>
> 1. MDVR连接Sensor & Serial线
> 2. SENSOR IN1与+5V导线相连，模拟高电平状态
> 3. 万用表红表笔接 sensor out 的输出线（信号线），黑表笔接设备的**公共地（GND）**
>
> <iframe frameborder="no" border="0" marginwidth="0" marginheight="0" width=833 height=401 src="https://edrawcloudpublicus.s3.amazonaws.com/viewer/self/2539370/share/2025-7-1/1751340446/page-2.svg"></iframe>
> 

> **万用表验证步骤**
>
> #### **步骤 1：静态状态检测（未触发报警时）**
>
> - **目的**：检测 sensor out 在未触发时的基准电压（判断初始状态是否正常）。
>
> - 操作：
>
>   1. 确保 MDVR 或传感器处于**未报警状态**（无触发信号）。
>   2. 万用表红表笔接 sensor out 的输出线（信号线），黑表笔接设备的**公共地（GND）**（如 MDVR 的外壳、电源负极）。
>   3. 观察万用表读数：
>      - 若设置为 “低电平有效”：未触发时应为高电平（接近供电电压）。
>      - 若设置为 “高电平有效”：未触发时应为低电平（接近 0V或显示电阻值）。
>
> #### **步骤 2：触发状态检测（模拟报警时）**
>
> - **目的**：检测 sensor out 在触发时能否正常切换电平（判断输出功能是否有效）。
>
> - 操作：
>
>   1. 手动触发报警（保持表笔连接（红笔接 sensor out 线，黑笔接 GND），观察电压变化：
>      - 若为 “低电平有效”：触发时应从高电平跳变为低电平（0V 左右）。
>      - 若为 “高电平有效”：触发时应从低电平（0V）跳变为高电平（接近供电电压，测试值为11.5V左右）。

### 客户需要进行画面联动，当车辆开门和倒车时，分别显示不同摄像头的画面。

> 1. Log in WebUI
> 2. Access Config>>Alarm>>Base>>IO Alarm
>
> ---
>
> - 车辆开门
>
>   ### 基本信息
>
>   - **名称（Name）**：Sensor1
>   - **OSD 标识**：S1
>   - **启用（Enable）**：已勾选，即启用该传感器
>   - **报警类型（Alarm Type）**：Event（事件型报警 ）
>   - **关联传感器用途（Sensor Uses）**：`Door 1`（关联门 1 ，用于监测门相关状态 ）
>
>   ### 触发设置（Sensor1 Trigger ）
>
>   - **触发源（Trigger Source）**：Source Voltage（电源电压，监测电压变化作为触发条件 ）
>   - **触发条件（Trigger）**：High（电压高电平触发 ）
>   - **有效时间（Effective Time）**：5 秒（电压高电平持续 5 秒才会触发后续动作，范围 0 - 10 秒 ）
>
>   ### 报警联动设置（Sensor1 Linkage ）
>
>   - **通道（Channel）**：未勾选 1 - 8 通道，即不联动这些通道录像等
>
>   - **后录像时长（Post Recording）**：~~1 Min（触发报警后，持续录像 1 分钟 ）~~
>
>   - **锁定（Lock）**：未勾选，不执行锁定动作
>
>   - **联动 IO 输出（Linkage IO Output）**：未勾选 1、2 输出，不联动外部 IO 设备
>
>   - **输出延迟时间（Output Delay Time）**：0 秒（若启用 IO 输出，无延迟立即执行 ，范围 0 - 255 秒 ）
>
>   - 联动画面（Linkage Screen）：Single（单画面显示 ）
>
>     - **布局通道（Layout）**：Channel 2（联动显示通道 2 的画面 ）
>   - **显示时长（Duration）**：10 秒（联动画面显示 10 秒，范围 1 - 300 秒 ）
>
>   - **报警抓拍（Alarm Snap）**：未勾选，不执行报警抓拍
>
> - 倒车
>
>   ### 基本信息
>
>   - **名称（Name）**：Sensor2
>   - **OSD 标识**：S2
>   - **启用（Enable）**：已勾选，启用该传感器
>   - **报警类型（Alarm Type）**：Event（事件型报警 ）
>   - **关联用途（Sensor Uses）**：`Aster` 
>
>   ### 触发设置（Sensor2 Trigger ）
>
>   - **触发源（Trigger Source）**：Source Voltage（电源电压，监测电压变化触发 ）
>   - **触发条件（Trigger）**：High（电压高电平触发 ）
>   - **有效时间（Effective Time）**：5 秒（电压高电平持续 5 秒触发后续动作，范围 0 - 10 秒 ）
>
>   ### 报警联动设置（Sensor2 Linkage ）
>
>   - **通道（Channel）**：未勾选 1 - 8 通道，不联动这些通道录像等
>   - **后录像时长（Post Recording）**：~~1 Min（触发报警后，持续录像 1 分钟 ）~~
>   - **锁定（Lock）**：未勾选，不执行锁定动作
>   - **联动 IO 输出（Linkage IO Output）**：未勾选 1、2 输出，不联动外部 IO 设备
>   - **输出延迟时间（Output Delay Time）**：0 秒（若启用 IO 输出，无延迟立即执行 ，范围 0 - 255 秒 ）
>   - 联动画面（Linkage Screen）：Single（单画面显示 ）；AsterMirror 功能：Support（支持 ）
>     - **布局通道（Layout）**：Channel 5（联动显示通道 5 的画面 ）
>     - **显示时长（Duration）**：10 秒（联动画面显示 10 秒，范围 1 - 300 秒 ）
>   - **报警抓拍（Alarm Snap）**：未勾选，不执行报警抓拍


### 但客户发现倒车过程中开门，画面变成门的画面，客户希望我们解决此问题。

> 检查**关联用途（Sensor Uses）**是否设置为`Aster`，如果为为`Aster`设置，则进行修改即可。
>
> > [!NOTE]
> >
> > 测试发现，
> >
> > 1. 当 S1：Sensor Uses=Door 1；S2：Sensor Uses=Aster时
> >    1. 先触发S1并保持S1的触发状态，再触发S2，会变成Sensor2 Linkage的配置
> >    2. 先触发S2并保持S2的触发状态，再触发S1，仍然是Sensor2 Linkage的配置
> > 2. 当 S1：Sensor Uses=Door 1；S2：Sensor Uses=Door 2或其他非Aster设置时
> >    1. 先触发S1并保持S1的触发状态，再触发S2，会变成Sensor2 Linkage的配置
> >    2. 先触发S2并保持S2的触发状态，再触发S1，会变成Sensor1 Linkage的配置
> >
> > **综上，传感器 的 “Sensor Uses” 是否为 “Aster” 是决定联动配置是否受触发顺序影响的关键因素：非 “Aster” 设置下，触发顺序决定最终联动对象；Aster 设置下，触发顺序不影响，始终联动Aster传感器的配置。**_~OgCyGn~_


### 📍客户解决方案模拟

> 客户要求下周安装一台设备，要求支持：
> 1. 5路录像（1*IPC@4@AHD）,
> 2. panic button
> 3. UPS
> 4. Monitor（触控）
> 5. 摄像头选型线材
>
> 需要你提供完整的料号，除此信息，你还需要问什么问题（提示：安装方式和环境，分辨率，系统资源消耗等）。

_^tab^_

> **信息获取**
>
> 1. 

> **方案选型**
>
> 1. 

## 解决方案接线图

_^tab^_

> **方案1**
>
> A8PRO-H0412
>
> C24M x 3
>
> IPC P3 x 2
>
> AHD P3 x 1
>
> C25 x 2
>
> C20 x 1
>
> CP4
>
> <iframe frameborder="no" border="0" marginwidth="0" marginheight="0" width=2757 height=1259 src="https://edrawcloudpublicus.s3.amazonaws.com/viewer/self/2539370/share/2025-7-2/1751451782/main.svg"></iframe>
> 

> **方案2**
>
> A8PRO-H0412
>
> C20 x 1
>
> C25 x 2
>
> IPC P3 x 2
>
> AHD P3 x 2
>
> C24M x 3
>
> CP4
>
> <iframe frameborder="no" border="0" marginwidth="0" marginheight="0" width=2757 height=1222 src="https://edrawcloudpublicus.s3.amazonaws.com/viewer/self/2539370/share/2025-7-2/1751451847/main.svg"></iframe>
> 

## 测试问题汇总



> | 问题                               | 解决方案                 |
> | ---------------------------------- | ------------------------ |
> | 电源线连接正常，但是``无法上电``   | 电源线内没装``保险丝``   |
> | 浏览器实时`预览录屏`显示为全黑     | 清除`浏览器缓存`         |
> | 浏览器实时`预览录屏`显示为`未编码` | 未打开`子码流`           |
> | AHD P3连接AV IN                    | AHD P3作为从机连接IPC P3 |
>
> 

------

# <center>*感谢观看！**Thanks for watching!***_~Bn~_</center><br><center>*科技构筑美好交通未来**Building a Brighter Future of Transportation with Technology***_~Bn~_</center><br><center>*Streamax**锐明技术股份有限公司***_~Bn~_</center>