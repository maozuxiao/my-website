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
vlook-header-dup: 
---

###### ✒️Streamax 产品学习记录<br /><br />*Version 1.0`🐾`20th June 2025*<br />*一般`👀`部门可见*<br />**** <br />*Sean`🍍` Mao*<br />

# **✒️**Streamax 产品学习记录

[TOC]

## 课程表

| 时间    | 课件  | 总结 |
| --------------- | ----------------------------------------------------- | ---- |
| 2025-6-20 14:15 | Comprehensive MDVR series from Streamax 20230911.pptx | MDVR系列产品命名规范，产品硬件接口、产品参数，一些专业术语介绍 |

## 待办事项

- [ ] 借用测试样机X3N-H0404
  1. 2025-6-20：覃海传-Beacher：下周会准备一台提供给我

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

1. 如果AHD如果支持X路，只使用X-1路，视频输出质量是否会提升，比如1080P@12fps(AHD)>>1080P@25fps(AHD)？

   > [!NOTE]
   >
   > MDVR-X3N-H0404支持参数：
   >
   > **PAL**
   > `4*720P@25fps(AHD)+4*1080P@30fps(IPC)`Or `4*1080P@12fps(AHD)+4*1080P@30fps(IPC)`
   >
   > **NTS** 
   > `4*720P@30fps(AHD)+4*1080P@30fps(IPC)` Or `4*1080P@12fps(AHD)+4*1080P@30fps(IPC)`

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

### 产品规格书

| 产品名称       | 规格书                                                       | Specification                                                |
| -------------- | ------------------------------------------------------------ | ------------------------------------------------------------ |
| M1N-H0401      | [M1N-H0401规格书（V1.0）.docx](https://wj.streamax.com:9443/preview.html?fileid=0125934b-5fa5-4e98-a284-e94ed007c91a) | [M1N-H0401 Specification Q3.docx](https://wj.streamax.com:9443/preview.html?fileid=f810386b-c7f7-4f40-a4a4-f9f17609d199) |
| X3NPro-PTH0404 | [X3NPro-PTH0404中文规格书.docx](https://wj.streamax.com:9443/preview.html?fileid=54d7dd2f-8b73-45ff-a2b6-8673fdb2aaf2) | [X3NPro-PTH0404 Specification.doc.docx](https://wj.streamax.com:9443/preview.html?fileid=036af7da-e11e-48dd-b007-72f548237c90) |



### 面板接口说明

_^tab^_



> **前置面板(Front panel)**
>
> | 名称          | 定义                                                         | M1N-H0401             |
> | ------------- | ------------------------------------------------------------ | --------------------- |
> | PWR(指示灯)   | 电源指示灯<br />蓝色；设备上电时常亮；关机、待机或休眠时熄灭 | ✅                     |
> | USB(指示灯)   | USB指示灯<br />绿色；设备识别到U盘时常亮；设备对U盘进行读写操作时闪烁，闪烁频率1HZ | ✅                     |
> | ALM(指示灯)   | 报警指示灯<br />红色；触发任意报警时常亮；正常情况下熄灭     | ✅                     |
> | REC(指示灯)   | 录制指示灯<br />红色；绿色；录像时常亮；非录像时熄灭         | ✅                     |
> | ERR(指示灯)   | 故障指示灯<br />红色；硬盘加密芯片未获取到时常亮；其他状态熄灭 | ✅                     |
> | NET(指示灯)   | 网络指示灯<br />绿色；通讯模块正常，无数通讯时常亮；通讯模块正常，有数据通讯时闪烁，闪烁频率1HZ；无通讯模块时熄灭 | ✅                     |
> | VLOSS(指示灯) | 视频丢失或无信号指示灯                                       | ❌                     |
> | SD(接口)      | SD卡接口<br />支持SDXC 32GB/64GB/128GB/256GB，可热插拔       | ✅2个                  |
> | SIM(接口)     | SIM卡接口                                                    | ✅1个；Mini Sim卡      |
> | USB(接口)     | 升级固件/运维宝（Easy check）                                | ✅运维宝（Easy check） |
> | A/V OUT(接口) | 外接显示器/控制面板                                          | ❌                     |
>
> 

> **后置面板(Rear panel)**
>
> | 名称                                                         | 定义                     | M1N-H0401                   |
> | ------------------------------------------------------------ | ------------------------ | --------------------------- |
> | WIFI Antenna![WIFI天线图标](https://cdn.jsdelivr.net/gh/maozuxiao/Image-shack/image-20250623112524303.png)<br />![WIFI天线接口](https://cdn.jsdelivr.net/gh/maozuxiao/Image-shack/image-20250623115334151.png#20%) | WIFI天线接口             | ✅1*SMA                      |
> | External GPS![GPS/BD北斗图标](https://cdn.jsdelivr.net/gh/maozuxiao/Image-shack/image-20250623112539202.png)<br />![GPS&北斗外接接口](https://cdn.jsdelivr.net/gh/maozuxiao/Image-shack/image-20250623113425889.png#20%) | 外接GPS/北斗定位模块接口 | ✅1个；4Pin；支持GPS/BD 北斗 |
> | 3G or 4G Antenna![3G or 4G Antenna](https://cdn.jsdelivr.net/gh/maozuxiao/Image-shack/image-20250623112622148.png)<br />![3G or 4G Antenna接口](https://cdn.jsdelivr.net/gh/maozuxiao/Image-shack/image-20250623112743027.png#20%) | 3G/4G天线接口            | ✅1*SMA                      |
> | A/V IN<br />![A/V IN](https://cdn.jsdelivr.net/gh/maozuxiao/Image-shack/image-20250623113616780.png#20%) | 模拟音视频输入           | ✅4个；4Pin同轴电缆          |
> | IPC<br />![IP摄像头](https://cdn.jsdelivr.net/gh/maozuxiao/Image-shack/image-20250623114134142.png#20%) | PON供电IPC接口           | ✅1个；6Pin同轴电缆          |
> | Power<br />![电源接口](https://cdn.jsdelivr.net/gh/maozuxiao/Image-shack/image-20250623114054994.png#20%) | DC8-36V电源输入          | ✅1个；9Pin电源线            |
> | R-WATCH & AV out<br />![R-WATCH & AV out](https://cdn.jsdelivr.net/gh/maozuxiao/Image-shack/image-20250623114201780.png#20%) | R-WATCH&A/V OUT接口      | ✅1个；8Pin                  |
> | Sensor & Serial<br />![Sensor & Serial](https://cdn.jsdelivr.net/gh/maozuxiao/Image-shack/image-20250623114344644.png#20%) | 串口和开关量接口         | ✅1个；22Pin                 |

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
> - RS - 232 - C 接口的信号线定义包括多种信号类型。例如，数据线路（如 TxD - 发送数据，RxD - 接收数据），用于在设备之间传输数据；控制线路（如 RTS - 请求发送，CTS - 允许发送，DSR - 数据设备就绪，DTR - 数据终端就绪等），用于对数据的传输过程和链路状态进行控制。其`最大传输距离约为 15 米（在波特率为 19200 的情况下），最大传输速率为 20kbps 左右`。通常使用 9 针或 25 针的 DB - 9 或 DB - 25 接口。这个接口曾经广泛应用于计算机与调制解调器、计算机与其他串行设备之间的连接，如早期的计算机与打印机、终端设备等之间的通信。
> [<kbd>百度百科：RS-232 ❯❯</kbd>](https://baike.baidu.com/lemma/api/entry?word=RS-232&fromModule=lemma_search-b)
> ![4分钟听懂！什么是 RS-232？](https://vd3.bdstatic.com/mda-mi8b0n3irhcdj0h6/480p/h264/1631173619817638772/mda-mi8b0n3irhcdj0h6.mp4)

> **RS485 定义**
> - RS - 485 是一种常用的总线标准，由美国电子工业协会（EIA）于 1983 年正式颁布。它是一种平衡串行通信接口，主要用于连接多个设备，构成分布式控制系统或进行长距离的数据传输。
> - RS - 485 接口采用了差分信号传输方式，具有良好的抗干扰能力。它采用两线制（半双工）或四线制（全双工）的通信方式。在两线制中，A 线和 B 线（也称为 “+” 和 “ - ”）用于数据传输，通过比较两线之间的电位差来判断信号的逻辑状态。RS - 485 的`最大传输距离可达 1200 米左右（在波特率为 90kbps 时），最大传输速率可达 10Mbps（在 12 米范围内）`。它**可以连接多个节点**，一般最多可以连接 **32 个节点**（通过中继器等设备可以扩展连接数量），在工业自动化、楼宇自动化等领域得到了广泛应用，如连接 PLC（可编程逻辑控制器）与传感器、执行器等设备，实现数据采集和控制指令的传输。
> [<kbd>百度百科：RS-485 ❯❯</kbd>](https://baike.baidu.com/lemma/api/entry?word=RS-232&fromModule=lemma_search-b)
> ![【工程师必备技能】什么是RS485？如何在工业控制系统中使用它？](https://vd3.bdstatic.com/mda-mcqfjn3f1k7fjdd5/hd/cae_h264/1616671155/mda-mcqfjn3f1k7fjdd5.mp4)


> **RS232 VS RS485**
> |    对比项    | RS232                                    | RS485                                        |
> | :----------: | :--------------------------------------- | -------------------------------------------- |
> |   通信方式   | 单端通信，易受干扰                       | 差分通信，抗干扰能力强                       |
> |   传输距离   | 最大传输距离约 15 米（19200bps）         | 最大传输距离约 1200 米（90kbps）             |
> | 最大传输速率 | 最大传输速率为 20kbps（15 米）           | 最大传输速率为 10Mbps（12 米）               |
> | 网络拓扑结构 | 通常为点 - 点通信                        | 支持多点链路，最多可连接 32 个节点（可扩展） |
> |  抗干扰能力  | 抗干扰能力弱，易受地电位差和电磁干扰影响 | 抗干扰能力强，能有效抑制共模干扰             |
> |   电源供给   | 通常需要单独电源                         | 可通过信号线供电                             |
> 
> ![RS232、RS485、TTL到底能传输多远距离？](https://vd3.bdstatic.com/mda-pg97k2dwfd1twyiq/hd/cae_h264/1689225328082064355/mda-pg97k2dwfd1twyiq.mp4)

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



# <center>*感谢观看！**Thanks for watching!***_~Bn~_</center></br><center>*科技构筑美好交通未来**Building a Brighter Future of Transportation with Technology***_~Bn~_</center></br><center>*Streamax**锐明技术股份有限公司***_~Bn~_</center>
