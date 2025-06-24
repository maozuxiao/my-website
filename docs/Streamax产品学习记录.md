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
vlook-header-dup: A/V IN;
---

###### ✒️Streamax 产品学习记录<br />*Version 1.0`🐾`20th June 2025*<br />*一般`👀`部门可见*<br />**** <br />*Sean`🍍` Mao*<br />[✉️](mailto:sean@streamax.com)

# **✒️**Streamax 产品学习记录

[TOC]

## 课程表

| 时间    | 课件  | 总结 |
| --------------- | ----------------------------------------------------- | ---- |
| 2025-6-20 14:15 | Comprehensive MDVR series from Streamax 20230911.pptx | MDVR系列产品命名规范，产品硬件接口、产品参数，一些专业术语介绍 |

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
> 1. 
> 2. 
> 学习记录详见链接：https://maozuxiao.github.io/my-website/Streamax%E4%BA%A7%E5%93%81%E5%AD%A6%E4%B9%A0%E8%AE%B0%E5%BD%95.html</textarea><a class="btn" onclick="var emailBody = encodeURIComponent(document.getElementById('emailBody').value); window.location.href = 'mailto:emrys@streamax.com?cc=maxwell@streamax.com,pascal@streamax.com&subject=Sean的学习日报&body=' + emailBody;"><br><kbd>点击发送邮件</kbd></a>

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





## 产品通用类知识

### 产品命名

> **示例**：M1N-H0401
>
> ![M1N-H0401](https://cdn.jsdelivr.net/gh/maozuxiao/Image-shack/20250620160900347.png)
>
> | 序号 | 编码部分 | 类型 | 含义 |
> |:--------:|:----:|:----:|------|
> | ①       | M        | 存储介质 | `M`代表Memory，存储介质为SD卡；若为`X`则代表机械硬盘（需区分3.5和2.5尺寸）或SATA SSD |
> | ②       | 1        | 产品等级 | 产品等级，数字越大性能越高，性能排序`X5N-E0804`>`X3N-H0404`>`M1N-H0401` |
> | ③       | N        | 芯片信息 | `N`代表NovaTek（联咏芯片）；`H`代表hisilicon(海思芯片) |
> | ④       | H        | 工作模式 | 代表Hybrid 混合模式； `E`代表Extension为扩展模式，比如`X5N-E0804`拥有`LAN`连接 External Switch拓展IP camera & `AV IN总线`拓展AHD camera |
> | ⑤      | 04       | AHD camera支持路数 | 支持4路模拟摄像头（AHD camera） |
> | ⑥      | 01       | IP camera支持路数 | 支持1路IP摄像头（IP camera） |
>
> > [!NOTE]
> >
> > 1. 如果产品名称为M1N-**GM**_~Rd~_H0401，GM代表：`GENERAL MACHINE`

### 产品规格书 & 说明书

_^tab^_

> **MDVR**
>
> | 产品名称       | 规格书                                                       | 说明书                                                       |
> | -------------- | ------------------------------------------------------------ | ------------------------------------------------------------ |
> | M1N-H0401      | [M1N-H0401规格书（V1.0）.docx](https://wj.streamax.com:9443/preview.html?fileid=0125934b-5fa5-4e98-a284-e94ed007c91a)<br />[M1N-H0401 Specification Q3.docx](https://wj.streamax.com:9443/preview.html?fileid=f810386b-c7f7-4f40-a4a4-f9f17609d199) | [M1N产品使用说明书V2.0.docx](https://wj.streamax.com:9443/preview.html?fileid=064e99f2-3515-45e6-a41d-dd32703467e6)<br />[M1N User ManualV2.0.docx](https://wj.streamax.com:9443/preview.html?fileid=a5f523f9-ba84-44a7-8595-dd01110140f4) |
> | X3N-H0404      | [X3N-H0404规格书（V1.0）.doc](https://wj.streamax.com:9443/preview.html?fileid=544b0b8e-31fe-484a-8232-f15945ea4bfd)<br />[X3N-H0404 Specification-20220421-EN.docx](https://wj.streamax.com:9443/preview.html?fileid=7354e8a1-c410-4874-89c3-c4af95f030c0) | [X3N系列产品使用说明书-V2.0.doc](https://wj.streamax.com:9443/preview.html?fileid=28300d23-1b1c-4bb5-8010-36065a818659)<br />[X3N Series Product User Manual-V2.0.docx](https://wj.streamax.com:9443/preview.html?fileid=c939d7a5-1a6c-46ab-97b8-e62b518849fb) |
> | X3NPro-PTH0404 | [X3NPro-PTH0404中文规格书.docx](https://wj.streamax.com:9443/preview.html?fileid=54d7dd2f-8b73-45ff-a2b6-8673fdb2aaf2)<br />[X3NPro-PTH0404 Specification.doc.docx](https://wj.streamax.com:9443/preview.html?fileid=036af7da-e11e-48dd-b007-72f548237c90) | [X3N Pro使用说明书.docx](https://wj.streamax.com:9443/preview.html?fileid=0615eb0e-55e1-45fb-99c2-be7a15b3d220)<br />[X3N Pro使用说明书（英文版）.docx](https://wj.streamax.com:9443/preview.html?fileid=00054bfc-3121-4586-a409-ae110ec71e95) |

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
> | 名称                                                         | 定义                        | M1N-H0401                   | X3N-H0404                   |
> | ------------------------------------------------------------ | --------------------------- | --------------------------- | --------------------------- |
> | WIFI Antenna<br />![WIFI天线图标](https://cdn.jsdelivr.net/gh/maozuxiao/Image-shack/image-20250623112524303.png)<br />![WIFI天线接口](https://cdn.jsdelivr.net/gh/maozuxiao/Image-shack/image-20250623115334151.png#20%) | WIFI天线接口                | ✅1*SMA                      | ✅1*SMA                      |
> | External GPS<br />![GPS/BD北斗图标](https://cdn.jsdelivr.net/gh/maozuxiao/Image-shack/image-20250623112539202.png)<br />![GPS&北斗外接接口](https://cdn.jsdelivr.net/gh/maozuxiao/Image-shack/image-20250623113425889.png#20%) | 外接GPS/北斗定位模块接口    | ✅1个；4Pin；支持GPS/BD 北斗 | ✅1个；4Pin；支持GPS/BD 北斗 |
> | 3G or 4G Antenna<br />![3G or 4G Antenna](https://cdn.jsdelivr.net/gh/maozuxiao/Image-shack/image-20250623112622148.png)<br />![3G or 4G Antenna接口](https://cdn.jsdelivr.net/gh/maozuxiao/Image-shack/image-20250623112743027.png#20%) | 3G/4G天线接口               | ✅1*SMA                      | ✅1*SMA                      |
> | A/V IN<br />![A/V IN](https://cdn.jsdelivr.net/gh/maozuxiao/Image-shack/image-20250623113616780.png#20%) | 模拟音视频输入              | ✅4个；4Pin同轴电缆          | ✅4个；4Pin同轴电缆          |
> | IPC<br />![IP摄像头](https://cdn.jsdelivr.net/gh/maozuxiao/Image-shack/image-20250623114134142.png#20%) | PON供电IPC接口              | ✅1个；6Pin同轴电缆          | ✅4个；6Pin同轴电缆_~Rd~_    |
> | Power<br />![电源接口](https://cdn.jsdelivr.net/gh/maozuxiao/Image-shack/image-20250623114054994.png#20%) | DC8-36V电源输入             | ✅1个；9Pin电源线            | ✅1个；9Pin电源线            |
> | R-WATCH & AV out<br />![R-WATCH & AV out](https://cdn.jsdelivr.net/gh/maozuxiao/Image-shack/image-20250623114201780.png#20%) | R-WATCH&A/V OUT接口         | ✅1个；8Pin                  | ❌                           |
> | Sensor & Serial<br />![Sensor & Serial](https://cdn.jsdelivr.net/gh/maozuxiao/Image-shack/image-20250623114344644.png#20%) | 串口和开关量接口            | ✅1个；22Pin                 | ✅1个；22Pin                 |
> | USB Type B<br />![USB Type B](https://cdn.jsdelivr.net/gh/maozuxiao/Image-shack/image-20250623164433187.png#20%) | USB Type B(可连防火盒)      | ❌                           | ✅1个；2.0版本               |
> | WAN<br />![WAN口](https://cdn.jsdelivr.net/gh/maozuxiao/Image-shack/image-20250623164459316.png#20%) | WAN 口，连接电脑配置MDVR    | ❌                           | ✅1个；100M                  |
> | LAN<br />![LAN口](https://cdn.jsdelivr.net/gh/maozuxiao/Image-shack/image-20250624110338651.png#20%) | LAN口，连接Extension Switch | ❌                           | ❌                           |
> | Serial<br />![Serial](https://cdn.jsdelivr.net/gh/maozuxiao/Image-shack/image-20250623164519364.png#20%) | 串口接口                    | ❌                           | ✅1个；12Pin                 |
> | VGA<br />![VGA](https://cdn.jsdelivr.net/gh/maozuxiao/Image-shack/image-20250623164535733.png#20%) | VGA视频接口                 | ❌                           | ✅1个；8Pin                  |
> | Panel<br />![Panel](https://cdn.jsdelivr.net/gh/maozuxiao/Image-shack/image-20250623164555190.png#20%) | 控制面板（CP4）接口         | ❌                           | ✅1个；10Pin                 |

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



### Veyes(锐明运维宝)使用说明

_^tab^_

> **安装**
>
> * Android手机用户请在谷歌商店搜索“Veyes” 下载后安装
> * IOS手机用户请在APP商店内搜索“Veyes”下载后安装
>
> > [!CAUTION]
> >
> > Mobile Apps对系统版本有限制，要求Android 5.0或者IOS 11及以上系统版

> **连接**
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
> > rtsp://admin:@10.100.100.1:554/mainstream0
> > rtsp://admin:@10.100.100.1:554/mainstream1
> > rtsp://admin:@10.100.100.1:554/mainstream2
> > rtsp://admin:@10.100.100.1:554/mainstream4

### 视频分辨率说明

> | 分辨率                                     | 描述                     | 像素尺寸（宽x高）              |
> | ------------------------------------------ | ------------------------ | ------------------------------ |
> | **CIF (Common Intermediate Format)**       | 标准视频分辨率           | 352x288                        |
> | **WCIF (Wide Common Intermediate Format)** | CIF的宽屏版本            | 704x288                        |
> | HD1                                        | 高清视频分辨率           | 1280x720                       |
> | WHD1                                       | HD1的宽屏版本            | 1920x720                       |
> | **D1 (Digital Video)**                     | 数字视频标准清晰度分辨率 | 720x480 (NTSC) / 720x576 (PAL) |
> | WD1(960H)                                  | 宽屏标准清晰度视频分辨率 | 1280x960                       |
> | 720P                                       | 高清视频分辨率           | 1280x720                       |
> | 960P                                       | 高分辨率视频             | 1280x960                       |
> | 1080P                                      | 全高清视频分辨率         | 1920x1080                      |



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


# <center>*感谢观看！**Thanks for watching!***_~Bn~_</center><br><center>*科技构筑美好交通未来**Building a Brighter Future of Transportation with Technology***_~Bn~_</center><br><center>*Streamax**锐明技术股份有限公司***_~Bn~_</center>