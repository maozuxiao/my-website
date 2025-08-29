---
title: 112 platform test
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
###### 112 platform test<br /><br />*Version 1.0`🐾`09th August 2025*<br />*一般`👀`所有人可见*<br />**** <br />*Sean`🍍` Mao*<br />

# 112 platform test

[TOC]

## Log in to 112 Test Panel

1. Access http://test-panel.mobilbil.com/login
   * `UserName`: streamax
   * `Password`: streamax!232!

## Log in to the device web UI

### Device Info

| Product Name     | Serial Number | Vehicle Plate | Public IP      | Firmware Version            | MCU Version                   |
| ---------------- | ------------- | ------------- | -------------- | --------------------------- | ----------------------------- |
| X3N3.0-H0208     | 00E80005CF    | 44M3647       | 5.11.182.231   | B359\_1029\_B242\_D25080802 | X3N30-M01-STM32-MCU-T25022501 |
| A8PRO2.0-PTH0412 | 00B8006EC0    | 51M3647       | 178.242.166.60 | B359\_1029\_B242\_D25080804 | A8-M01-STM32-MCU-T25072401    |

> [!IMPORTANT]
>
> Access the Public IP to view the device web UI
>
> * `UserName`: admin
> * `Password`: admin

## Add Kit in 112 Test Panel

### Kit Information

| Kit Information | Description                                                  | Example                                              |
| --------------- | ------------------------------------------------------------ | ---------------------------------------------------- |
| Email           | No restrictions                                              | admin@example.com                                    |
| Phone           | No restrictions                                              | (532) 277 30 74                                      |
| License Plate   | Consistent with the `Vehicle Plate` in the MDVR `Register Info` | X3N: 44M3647<br />A8Pro: 51M3647                     |
| VIN             | Consistent with the `VIN Number` in `112 Register Info` under the MDVR `Register Info` | X3N: W1K6X8GB3PA123711<br />A8Pro: W1K6X8GB3PA123748 |
| IMEI            | Consistent with the `IMEI` in the `Device module` under MDVR `Maintenance` | X3N: 865828069174967<br />A8Pro: 865828063050569     |
| Model           | Consistent with the `Product Name` in the `Version Info` under MDVR `Maintenance` | X3N3.0-H0208<br />A8PRO2.0-PTH0412                   |
| Serial No       | Consistent with the `Serial Number` in the MDVR `Register Info` | X3N: 00E80005CF<br />A8Pro: 00B8006EC0               |
| IP              | Consistent with the `IPV4 Address` in the `Device Module` under MDVR `Maintenance` | X3N: 5.11.182.231<br />A8Pro: 178.242.166.60         |
| MAC             | Consistent with the`Mac Address` in the `Device module` under MDVR `Maintenance` | 00:1B:44:11:3A:B7<br />00:00:00:00:00:00             |
| Port            | Consistent with the `WEB Port` in the `Network>>Ports` Under MDVR `Config` | 80                                                   |

### Device Information

| Device Information | Description     | Example        |
| ------------------ | --------------- | -------------- |
| Device Name        | No restrictions | X3N<br />A8PRO |

### Cameras

| Cameras  | Description                                                  | Example                                          |
| -------- | ------------------------------------------------------------ | ------------------------------------------------ |
| Label    | Refer to `Example`                                           | Sürücü ve Yol Görüş Kamerası<br />Yolcu Kamerası |
| Protocol | HLS(Default)                                                 | HLS(Default)<br />FLV                            |
| Port     | Consistent with the `WEB Port` in the `Network>>Ports` Under MDVR `Config` | 80                                               |
| Username | Need to set the username in `User Setup` under MDVR `Config` | MOBILBIL                                         |
| Password | Need to set the password in `User Setup` under MDVR `Config` | Xx7*Lp1!                                         |
| Endpoint | cam_000X                                                     | cam_0001<br />cam_0002                           |

### Button

| Buttons   | Description     | Example             |
| --------- | --------------- | ------------------- |
| Pin No    | /               | 1                   |
| Serial No | No restrictions | 4163066343085875200 |
| Type      | /               | 1                   |

> [!IMPORTANT]
>
> After completing the configuration, click Add kit

## Set Device Configuration

1. Access to [112 test panel](http://test-panel.mobilbil.com/kit-list)
2. Navigate to `Kit List`
3. Search by plate or serial number (**recommended to set a new plate for the new test**)
4. Find the kit and click `Set Device Configuration`
5. Click `Send to Device`
6. Check the Kit ID if the server sync succussed
   * Access MDVR web UI
   * Navigate to Config>>Basic Setup>>Register  Info>>112 Register  Info>>Kit ID

## Config the MDVR

### 112 Regist Info

| Label             | data-param                                                   |
| ----------------- | ------------------------------------------------------------ |
| Kit ID            | {Issued by 112 platform}                                     |
| Brand ID          | 0                                                            |
| VIN Number        | {Issued by 112 platform}                                     |
| Model             | Consistent with the `Product Name` in the `Version Info` under MDVR `Maintenance` |
| Port              | 80                                                           |
| 112 User Name     | MOBILBIL                                                     |
| 112 User Password | Xx7*Lp1!                                                     |
| 112 API Address   | https://test-panel-backend.mobilbil.com/producer/aracaacildurum/test |

### Alarm--Signal Alarm

|     Name     | Enable | Alarm Type | Trigger | Linkage |
| :----------: | :----: | :--------: | :-----: | :-----: |
| Urgent Alarm |   ☑    |   Alarm    |  Setup  |  Setup  |

#### Trigger Setup

1. **Effective Time**: Set to 1 second (range is 0 to 10 seconds).
2. **Duration**: Set to 1 second (range is 0 to 255 seconds).
3. **Signal Name**: Named "Sensor1".
4. **Abbreviation**: Abbreviated as "S1".
5. **IO Enable**: Enabled (checked box).
6. **Trigger Source**: Set to "Source Voltage".
7. **Trigger**: Configured with "Sensor number" set to 1 and "Trigger" set to "High".

> [!CAUTION]
>
> 1. You can simulate pressing the panic button by adjusting the high level to a low level.
> 2. The panic button should be pressed for ≥ 1 second.

#### Linkage Setup

Alarm Snap: ☑

### Alarm--Urgent Alarm

| Name  | Enable | Alarm Type | Trigger | Linkage |
| :---: | :----: | :--------: | :-----: | :-----: |
| Panic |   ☑    |   Alarm    |  Setup  |  Setup  |

#### Trigger Setup

**Any Key**: Set to 1 second (range is 1 to 255seconds).

#### Linkage Setup

Alarm Snap: ☑

### Collection

1. Navigate to `Snap Setting`>>`Trigger Snap`>>`Alarm Snap`>>`Snap Link`>>`Setup`

2. Enable the snap channel

   | Channel | Snap Enable | Resolution | Quality | Upload Type | Snap Numbers (1~3)Pcs | Interval (1~3600)Second |
   | :-----: | :---------: | :--------: | :-----: | :---------: | :-------------------: | :---------------------: |
   |    1    |      ☑      |   1080P    | 1(Best) |    Setup    |           1           |          3600           |
   |    2    |      ☑      |   1080P    | 1(Best) |    Setup    |           1           |          3600           |
   |    3    |      ☑      |   1080P    | 1(Best) |    Setup    |           1           |          3600           |

> [!NOTE]
>
> In this case, the customer does not want to upload multiple snaps at the same time, so the value of Interval (1~3600) Second can be set to 3600

## Test steps

1. Search the Kit ID by hotkey <kbd>CTRL</kbd>+<kbd>F</kbd> Example: `225a37f8-bf72-4194-a4bd-f13befaf5552`

2. Click the highlighted kit card

3. Click `Go To Test Screen` and click <kbd>F12</kbd> to open the browser's developer tools (The server is getting Incident)
   ![Getting Incident](https://cdn.jsdelivr.net/gh/maozuxiao/Image-shack/image-20250809192623046.png)

4. Click the panic button≥1s (The server obtains the incident information, and the test passes.)
   ![incident information](https://cdn.jsdelivr.net/gh/maozuxiao/Image-shack/image-20250809192822962.png)

5. Duplicate the webpage and check if the server gets a new incident ID

6. Click the `Start Test` button on the right side of the Device Data/Incident Images/Location Data/Device Health Check cards to test
   ![Test overview](https://cdn.jsdelivr.net/gh/maozuxiao/Image-shack/image-20250809193553598.png)

   > [!NOTE]
   >
   > Camera Data requires verification.
   > 1. The video plays normally.
   > 2. The connection URL is correct.
   >    * Format: http://{username}:{password}@{public IP}:{port}/api/{Endpoint}.m3u8
   >    * Example: http://MOBILBIL:Xx7*Lp1!@5.11.182.231:80/api/cam_0003.m3u8
   
## 验收配置

_^tab^_

> **X1N_AI-N0400**
>
> ### Product Info
>
> Product Name: X1N_AI-N0400
>
> Firmware Version: B3.5.10_DC25071099
>
> ### Config
>
> 1. Disabled the MDVR server
> 1. Enabled Video audio
>
> ### Other
>
> 1. 当前112测试过检，仅要求1路APN连接112平台，不需要2路APNs(1路连接112,1路连接其他平台，比如FT Cloud)
> 2. X1N软件不支持1个模块1张SIM卡多个APN的场景，需要软件开发。建议从SIM测进行管控，配置成允许访问多个服务端（112，FT Cloud等）


# Thanks for Watching!!!