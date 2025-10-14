---
title: Turkey School Bus Solution
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

###### ✒️Turkey School Bus Solution<br />*Version 1.0`🐾`13th October 2025*<br />*一般`👀`部门可见*<br />**** <br />[✉️](mailto:sean@streamax.com)<br />**Sean°Mao**<br>*赫尔新根默斯肯的肥皂泡*

# Turkey School Bus Solution

[toc]

## Revison

| Date       | Version | Description                                                  |
| ---------- | ------- | ------------------------------------------------------------ |
| 2025-10-1  | V1.0    | Create document                                              |
| 2025-10-13 | V1.1    | Modify the sensor out alarm description from 3 seconds of sound and 3 seconds of pause to continuous sound |

## System Diagram

_^tab^_

> **Overview**
>
> > [!TIP]
> >
> > <kbd>[Click here]( https://wj.streamax.com:9443/outpublish.html?code=Afbb35b6f138049a09e1fc9bbf657b994#view )</kbd> to download the PDF file.
> 
> ![System Diagram](https://cdn.jsdelivr.net/gh/maozuxiao/Image-shack/X1N-N0400-%E5%9C%9F%E8%80%B3%E5%85%B6%E6%A0%A1%E8%BD%A6%E6%96%B9%E6%A1%88-%E6%A8%A1%E5%9E%8B_1.png#1080w)

> **Check Button(CCM) & IO Cable**
>
> ![Check Button(CCM) & IO Cable](https://cdn.jsdelivr.net/gh/maozuxiao/Image-shack/image-20251002232248095.png#800w)

> **Motion Sensor**
>
> ![Motion Sensor Cable connection](https://cdn.jsdelivr.net/gh/maozuxiao/Image-shack/image-20251002025559514.png#800w)



## Precondition

### Sensor 3

Sensor 3 Connect with the Student's Door

Path: EasyCheck>>Preferences>>Alarm>>Base

| Name    | OSD  | Enable | Alarm Type | Sensor Uses |
| ------- | ---- | ------ | ---------- | ----------- |
| Sensor3 | S3   | ✔      | Alarm      | Door 1      |

### Startup Settings

> Path: EasyCheck>>Preferences>>Startup 

_^tab^_

> **On/Off**
>
> ![On/Off](https://cdn.jsdelivr.net/gh/maozuxiao/Image-shack/image-20251010220359695.png#800w)

> **Sleep**
>
> ![Sleep](https://cdn.jsdelivr.net/gh/maozuxiao/Image-shack/image-20251010220422946.png#800w)

> **Wake**
>
> ![Wake](https://cdn.jsdelivr.net/gh/maozuxiao/Image-shack/image-20251010220455413.png#800w)

###  Anti Forgotten Settings

> Path: EasyCheck>>Preferences>>Alarm>>AI>>AF

| Name           | Enable | Alarm Type |
| -------------- | ------ | ---------- |
| Anti Forgotten | ✔      | Alarm      |

_^tab^_

> **Trigger**
>
> > Adjust according to the actual situation
>
> ![Anti Forgotten Trigger](https://cdn.jsdelivr.net/gh/maozuxiao/Image-shack/image-20251010214709270.png#800w)

> **Linkage**
>
> > Adjust according to the actual situation
>
> ![Anti Forgotten Linkage](https://cdn.jsdelivr.net/gh/maozuxiao/Image-shack/image-20251010214755013.png#800w)

> **Snap**
>
> > Adjust according to the actual situation
>
> ![Anti Forgotten Alarm Capture](https://cdn.jsdelivr.net/gh/maozuxiao/Image-shack/image-20251010214840226.png#800w)

## Key Accessories



### Check button (CCM)



#### Description

Before leaving, the driver must confirm whether there are any students left in the bus. Therefore, we regard the patrol check button (CCM button) as one of the core components of the school bus anti-forgotten solution

#### Scenario

1. To ensure the driver completes their inspection at the rear of the bus, a button will be installed inside the rear of the school bus to monitor the driver's inspection. One end of the inspection button is connected to the sensor in the terminal, and the other to the 5V line.
2. To prevent the driver from forgetting to perform an interior inspection, potentially leaving students behind, when ACC is turned off, the CP4 will play an MP3 voice prompt to remind the driver to inspect the bus: "`Please check the children and press the button.`"

#### CCM Inspection Process
1. After ACC OFF, the device immediately starts the inspection voice broadcast until the inspection time ends.
2. If the CCM button is not pressed during the inspection time after ACC OFF, an “inspection missed” alarm is sent to the customer platform.
3. If the CCM button is pressed during the inspection time after ACC OFF, no inspection alarm is generated and nothing is reported to the customer platform.
4. When the anti-forget IO has “sensor out” checked and the horn is bound, after an inspection-missed alarm is triggered, the device’s GUI shutdown countdown is canceled; the external horn beeps continuously.

#### CCM Related Configuration



Path: EasyCheck>>Preferences>>Alarm>>Base

| Name    | OSD  | Enable | Alarm Type | Sensor Uses    |
| ------- | ---- | ------ | ---------- | -------------- |
| Sensor1 | S1   | ✔      | Alarm      | Anti Forgotten |

_^tab^_

> **Sensor1 Trigger**
>
> > Adjust according to the actual situation
> 
> ![Sensor1 Trigger](https://cdn.jsdelivr.net/gh/maozuxiao/Image-shack/image-20251010212818399.png#800w)

> **Sensor1 Alarm Linkage**
>
> > Adjust according to the actual situation
> 
> ![Sensor1 Alarm Linkage](https://cdn.jsdelivr.net/gh/maozuxiao/Image-shack/image-20251010213151488.png#800w)

### Motion Sensor 



#### Description

After the driver leaves, the device can continue to detect whether there are any students left in the car.

#### Scenario

1. After the driver turns off ACC and shuts down the vehicle, and all occupants have exited with the student door closed, the motion sensor begins operating following the delay period to check whether any students remain inside. If no person is detected, the MS powers off when the total operating-time countdown ends and stays off until the next ACC ON.

2. If a student is left inside and triggers the motion sensor, the sensor uses its IO to wake the hibernating MDVR. Upon waking, the MDVR displays an alarm-cancel dialog and the shutdown countdown switches to 15 minutes:
    a) Tap “Cancel”: the “student left on bus” alarm is blocked; the MDVR resumes its 15-minute shutdown countdown, enters low-power hibernation, and cannot be woken again until the next ACC ON.
    b) Do nothing: the dialog times out, firing the “student left on bus” alarm. The MDVR logs the event locally, reports it to the platform, and plays calming audio. The shutdown countdown is cancelled and the unit stays powered on continuously. Simultaneously, an IO output activates the external alarm continuously.

3. The school-bus maintenance team will contact on-site personnel remotely to open the door and rescue the student. After the student is freed, the calming audio and external alarm keep sounding; to stop them, the rescuer must board the bus while the student door is open and press the patrol button—`ACC ON` can release the alarm.

#### Motion Sensor Related Configuration

##### Alarm related

Path: EasyCheck>>Preferences>>Alarm>>Base

| Name    | OSD  | Enable | Alarm Type | Sensor Uses       |
| ------- | ---- | ------ | ---------- | ----------------- |
| Sensor2 | S2   | ✔      | Alarm      | Out Device Motion |

_^tab^_

> **Sensor2 Trigger**
>
> > Adjust according to the actual situation
> 
>  ![Sensor2 Trigger](https://cdn.jsdelivr.net/gh/maozuxiao/Image-shack/image-20251010220932002.png#800w)

> **Sensor2 Alarm Linkage**
>
> > Adjust according to the actual situation
>
> ![Sensor2 Alarm Linkage](https://cdn.jsdelivr.net/gh/maozuxiao/Image-shack/image-20251010221044770.png#800w)

##### Collection Related

Path: EasyCheck>>Preferences>>Collection>>General

_^tab^_

> **Serial Port**
>
> > Adjust according to the actual situation
>
> ![Serial Port](https://cdn.jsdelivr.net/gh/maozuxiao/Image-shack/image-20251010221439139.png#800w)

> **Motion Sensor**
>
> > Adjust according to the actual situation
>
> ![Motion Sensor](https://cdn.jsdelivr.net/gh/maozuxiao/Image-shack/image-20251010221707972.png#800w)

### C34+ CA34

#### Description

The motion sensor only supports aisle detection and cannot detect whether there are students left on the seats, resulting in a detection blind spot. However, installing multiple sensors may detect movements outside the car. Therefore, the best way is to use camera algorithms for supplementary judgment.

#### Scenario

1. C34 enters the algorithm-enabled state as soon as it is powered on, but the alarm only becomes effective after ACC OFF, once the “alarm-valid after ACC OFF” time has elapsed and the student door is closed.

2. After the driver parks and shuts down the engine, completes the patrol routine and presses the CCM, then closes the student door: if the MDVR has not yet powered off and the current time is past the “alarm-valid after ACC OFF” time, any detected student left inside will make the MDVR pop up the alarm-prevention window.

3. If the MDVR was woken by the MS, C34 starts its algorithm immediately upon power-on and the alarm is effective right away.

4. When a student is detected remaining in the vehicle, the alarm-prevention dialog is triggered; if no one cancels it in time, an alarm is generated and uploaded to the platform, and the MP3 plays the voice prompt:  “Please sit down, someone will be here shortly”.

#### C34+ CA34 Related Configuration

Path: EasyCheck>>General>>AI Calibration>>Student Anti-foregetting & Sear Calibration

![C34+ CA34 Related Configuration](https://cdn.jsdelivr.net/gh/maozuxiao/Image-shack/image-20251010223522670.png#800w)

# Thanks for watching!