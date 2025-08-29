# A8Pro IPC Setup

[TOC]



> [!NOTE]
>
> A8PRO has optimized the logic for assigning IP addresses to IPCs, so you don't need to search for the device and then bind it to the IP address. 
>
> This is an exciting improvement that saves customers time configuring their settings.

## A8PRO H0412 Physical Interface – Channel – IP Address Mapping Table

> A8PRO now supports IPC Plug-and-Play; the A8PRO automatically assigns the correct IP addresses to IPCs as soon as they are connected—no manual network setup is required.
> For your convenience, the table below lists the factory-default mapping that is instantly applied when each IPC is plugged in. You can use it as a quick reference when setting up channel names, recording schedules, or other advanced functions.

| A8PRO H0412 physical interface | Channel | IP address          |
| ------------------------------ | ------- | ------------------- |
| AV/IN 1                        | CH1     | /                   |
| AV/IN 2                        | CH2     | /                   |
| AV/IN 3                        | CH3     | /                   |
| AV/IN 4                        | CH4     | /                   |
| IPC1                           | CH5     | 10.100.100.100:9006 |
| IPC2                           | CH6     | 10.100.100.101:9006 |
| IPC3                           | CH7     | 10.100.100.102:9006 |
| IPC4                           | CH8     | 10.100.100.103:9006 |
| IPC5                           | CH9     | 10.100.100.104:9006 |
| IPC6                           | CH10    | 10.100.100.105:9006 |
| IPC7                           | CH11    | 10.100.100.106:9006 |
| IPC8                           | CH12    | 10.100.100.107:9006 |
| IPC9                           | CH13    | 10.100.100.108:9006 |
| IPC10                          | CH14    | 10.100.100.109:9006 |
| IPC11                          | CH15    | 10.100.100.110:9006 |
| IPC12                          | CH16    | 10.100.100.111:9006 |



## Set up the startup screen

> If you want to customize the display of the startup screen on your control panel, please refer to the following steps

### Precondition

Reboot the device to make sure the IPC settings default.

### Navigate to Live View Settings

WebUI PATH: Config>>Surveillance>>Live View
Control Panel PATH: Setup>>Surveillance>>Live View


### Set the Preview Parameters

- **Startup Screen**: In the "Preview" tab, find the "Startup Screen" option. Click on the dropdown menu and select "9 - split" to set the startup screen to a 9 - split display mode.
- **Channel Selection**: Under the "Channel" option, check the boxes corresponding to the channels (such as 5 - 13 in the given interface) that you want to include in the live view.

### Save the Settings

After completing all the settings, click the "Save" button at the bottom right corner of the interface to save your configuration. If you want to revert to the default settings, you can click the "Default" button.

![Set up the start screen](https://cdn.jsdelivr.net/gh/maozuxiao/Image-shack/image-20250829203834670.png)

