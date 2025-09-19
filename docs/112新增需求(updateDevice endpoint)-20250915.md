---
title: 112新增需求(updateDevice endpoint)-20250915
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
vlook-query: coating=bu&ws=3&toc=2
vlook-header-dup: 
---
# 112新增需求(updateDevice endpoint)-20250915

[TOC]

## Revision

| VERSION | PREPARED BY  | CREATION / MODIFICATION DATE | EXPLANATION                                                  |
| ------- | ------------ | ---------------------------- | ------------------------------------------------------------ |
| V1.0    | Kübra UÇARSU | 30.05.2025                   | The first  publication has been created.                     |
| V1.1    | Kübra UÇARSU | 25.06.2025                   | Host  information has been updated.                          |
| V.1.2   | Kübra UÇARSU | 08.07.2025                   | Host  information has been updated. IP information has been removed. |
| V.1.3   | Kübra UÇARSU | 15.09.2025                   | **The  updateDevice endpoint has been added.**               |

## UPDATE SERVER INTEGRATION

> [!IMPORTANT]
>
> FTP 使用和更新协议规定，对于 112 紧急呼叫按钮注册系统中设备 FTP 服务器上的文件更新过程，用户只能通过 FTP 服务器下载自己的更新软件。公司无法在 FTP 环境中执行文件更新。112 紧急呼叫中心收到的、经 TÜBİTAK BİLGEM 网络安全测试批准的软件更新必须上传到相关公司的套件模型文件夹中，并由该模型的套件执行更新。
> 为了使设备能够接收更新，必须指定它们将连接到的更新服务器的地址以及必要的端口信息。在此背景下，设备将用于执行更新的地址如下：
>
> - **HOST**：`aad-ftp.ng112.gov.tr` 
> - **Port**：`21 `
> - **协议**：FTP over SSL（`FTPS`） 
> - **用户名**：`MOBILBIL`
> - **密码**：`Xx7*Lp1!`
>
> 这些数据必须在设备固件（嵌入式软件）开发阶段集成。这将使设备能够连接到预定义的服务器地址进行更新并执行授权的 FTP 操作。
> 此信息仅用于支持您设备的更新过程，不会用于任何其他目的。文件更新将通过更新服务器执行，并且此信息必须包含在固件开发过程中，以确保设备能够顺利管理此过程。

## UPDATE API ENDPOINT (updateDevice)

> [!IMPORTANT]
>
> 必须集成 updateDevice API 端点，该端点将触发设备内部的更新状态。请求将使用基本身份验证方法发送到此 API 端点。设备将检查发送请求中包含的 kitId，并查询其是否与之前写入设备的 kitId 匹配。如果匹配，则应配置设备以连接到 FTP 服务器并启动更新过程。启动更新后，设备应发送下方响应中的数据集。该数据集必须包含旧版本信息 (oldVersion)、新版本信息 (newVersion) 和预计更新时间 (estimatedTime)。预计更新时间 (estimatedTime) 的格式必须为 Unix 时间格式。

**新增 API 接口** 

设备必须实现 `updateDevice` 接口： 

- **鉴权方式**：Basic Auth 
- **方法**：POST 
- **请求体**： 
  
  ```json
  { 
      "kitId": "d8110f9d-d5ce-4451-ab12-d5881d-dfe4d6" 
  }
  ```
- **响应体**： 
  ```json
  {
   "success": true,
   "data": {
     "oldVersion":"0.0.21",
     "newVersion":"0.0.22",
     "estimatedTime":5400 //1h 30m
   },
   "message": "Güncelleme İşlemi Başlatıldı",
   "status": 200,
   "timestamp": 1748854198343
  }
  ```

* Diagram

  ```mermaid
  graph TD
      A[Start] --> B[Device connects to FTP server with username and password]
      B --> C[Company kit model provides access to its own folder]
      C --> D[Software update initiated for download by device]
      D --> E{Was the download successful?}
      E -->|Yes| G[The device updates the system version and sends it to the 112 Emergency Call Center system by updating the versionparameter in getDeviceInfo.]
      E -->|No| I[The Kit continues to work with old version]
      G --> J[Finish]
      I --> J
  ```

  

## Exceptional Adverse Event Protocol Flow Scenario

> [!IMPORTANT]
>
> 此场景涵盖了更新过程中出现的异常不利情况，包括与更新相关的连接失败以及其他不利情况。



1. **升级流程自检与回退** 
   - 下载失败 → 设备继续运行旧版本，不向平台报错。 
   - 下载中断 → 必须支持标准 FTP 断点续传。 
   - 升级后设备无响应 →  
     1. 自动向“公司负责人 + 车主”发送预警短信； 
     2. 车辆需进指定站点人工更新（USB-Type-C 线下刷包）； 
     3. 刷完后主动联系 112 中心做远程健康检查，通过后才允许上路。

2. **版本号实时同步** 
   升级成功后，设备在下一次 `getDeviceInfo` 上报中必须将 `version` 字段更新为最新版本号，供 112 平台校验。

3. **安全与权限** 
   - 厂商只能把经 TÜBİTAK BİLGEM 安全测试通过的升级包上传至自己型号目录； 
   - 设备仅可下载本公司、本型号目录下的文件，无法浏览其它厂商数据。

4. Diagram

   ```mermaid
   graph TD
       A(Start) --> B[The device must be operated in accordance with FTP Standard Protocols.]
       B --> C{Are there any issues outside the FTP Standard Protocol?}
       C -- Yes --> D[112 AÇM communicates with the device using the healthCheck function.]
       D --> E{Did the device respond?}
       E -- Yes --> F{Does the version held by 112 AÇM match the version included in the KK?}
       F -- Yes --> G[Device update successful]
       F -- No --> H[The system continues in its old version and sends a notification to the company via 112 AÇM SMS.]
       E -- No --> I[An SMS is sent to the authorized person and vehicle license holder of the company. The vehicle is expected to be updated at the station.]
       I --> J[Updates must be requested by 112 AÇM.]
       J --> K[Updates must be transferred manually to the device via USB-TYPE-C.]
       K --> L[Contact 112 AÇM to request a device test.]
       L --> M{If the test is successful, the vehicle is permitted to enter traffic.}
       M --> N[Finish]
       C -- No --> O[The update has been successfully completed.]
       O --> N
       G --> N
       H --> N
   ```