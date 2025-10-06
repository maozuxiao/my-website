# Turkey School Bus Solution

[toc]

## Revison

| Date      | Version | Description     |
| --------- | ------- | --------------- |
| 2025-10-1 | V1.0    | Create document |

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
> ![Check Button(CCM) & IO Cable](https://cdn.jsdelivr.net/gh/maozuxiao/Image-shack/image-20251002232248095.png#800W)

> **Motion Sensor**
>
> ![Motion Sensor Cable connection](https://cdn.jsdelivr.net/gh/maozuxiao/Image-shack/image-20251002025559514.png#800w)

## Key Accessories



### Check button (CCM)



### CCM Inspection Process
1. After ACC OFF, the device immediately starts the inspection voice broadcast until the inspection time ends.
2. If the CCM button is not pressed during the inspection time after ACC OFF, an “inspection missed” alarm is sent to the customer platform.
3. If the CCM button is pressed during the inspection time after ACC OFF, no inspection alarm is generated and nothing is reported to the customer platform.
4. When the anti-forget IO has “sensor out” checked and the horn is bound, after an inspection-missed alarm is triggered, the device’s GUI shutdown countdown is canceled; the external horn beeps for 3 s and pauses for 3 s in a continuous loop.

#### CCM Alarm Configuration Field Reference

| Field                      | Range / Value     | Parametes       |
| -------------------------- | ----------------- | --------------- |
| **Trigger**                | Low(0) / High(1)  | High            |
| **CCM Duration**           | 0 – 225 minutes   | 3               |
| **Must Check Time**        | 0 – 1 200 seconds | 30              |
| **Button Check Time**      | 10 – 600 seconds  | 20              |
| **Ignition Delay**         | Read-only, grayed | 300             |
| **Pending Time**           | 0 – 600 seconds   | 123             |
| **CCM Sensor Out Linkage** | `1` or `2`        | Channels 1 & 2, |

### Motion Sensor 



### C34+ CA34



