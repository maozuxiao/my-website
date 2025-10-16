---
title: Ceiba 2 Windows Server Configuration Recommendations
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
###### ✒️Ceiba 2 Windows Server Configuration Recommendations<br />*Version 1.0`🐾`16th October 2025*<br />*一般`👀`部门可见*<br />**** <br />[✉️](mailto:sean@streamax.com)<br />**Sean°Mao**<br>*Streamax*

# Ceiba 2 Windows Server Configuration Recommendations

[TOC]

## Recommended Configuration for CB2 Server

| Number of Hosts | CPU | Memory |
| --- | --- | --- |
| 0-1000 | 2.2GHz Frequency, 6 Cores 12 Threads <br />(12 Processors Recommended for Virtual Machines) | 16GB |
| 1000-3000 | 2.2GHz Frequency, 8 Cores 16 Threads<br /> (16 Processors Recommended for Virtual Machines) | 32GB |
| 3000-5000 | 2.4GHz Frequency, 10 Cores 20 Threads <br />(20 Processors Recommended for Virtual Machines) | 32GB |
| 5000-10000 | 2.4GHz Frequency, 2 Units of 8 Cores 16 Threads <br />(32 Processors Recommended for Virtual Machines) | 64GB |
| Operating System | Recommended: Windows Server 2016 Standard, 2019 Standard | == |
| Operating Environment | Microsoft .NET Framework v3.5 SP1 Must Be Installed | == |
| Hard Disk | 500GB or More. <br />Calculate based on actual vehicle quantity. Estimated disk space for GPS + alarm data: approximately 50MB per vehicle per day. Automatic video download + evidence center, and other data account for a small proportion, which can be ignored. | == |
| Network Card | 1000M Network Port Recommended | == |
| Note | Bandwidth Estimation: CIF bitrate is 100kbps, D1 is about 1Mbps, 720P and above are about 2-4Mbps. <br />Calculate according to actual usage. | == |


## Reference for Configuration Calculation Method
### Reference Scenario
There are 5,000 vehicles, with an average of 3,000 online daily and an average online time of 12 hours. The GPS reporting frequency is 1 entry every 10 seconds. 

A maximum of 500 pieces of evidence are uploaded simultaneously (average 10MB per piece, required to be uploaded within 60 seconds). 

There are 10,000 pieces of evidence and 100,000 alarms generated daily. 400 channels of CIF resolution direct video are viewed simultaneously, and black box data and videos are stored for 30 days.

| Avg. Daily Online/Total Vehicles | Avg. Daily Online Duration | Max Concurrent Evidence | Max Concurrent Direct Video | Daily Evidence | GPS Reporting Frequency |
| --- | --- | --- | --- | --- | --- |
| 3000/5000 | 10 Hours | 500 Pieces | 400 Channels | 10,000 Pieces | 1 Entry/10s |


### Hard Disk Write Performance Requirements
Assuming each piece of evidence is 10MB and needs to be uploaded within 60 seconds, the write requirement per evidence entry is approximately 10/60 ≈ 0.17 MB/s.

The concurrent requirement for 500 pieces of evidence is 0.17 * 500 ≈ 85 MB/s.

Transcoding is required after evidence upload, and the size of the MP4 file is close to that of the original file. The total hard disk write requirement is 85 * 2 = 170 MB/s. 

In addition to GPS, alarms, and other system tasks, it is recommended that the hard disk can reach a write speed of `200 MB/s`.


### Hard Disk Capacity Requirements
- Daily number of GPS entries: (10 * 3600) / 10 * 3000 = 10,800,000. Hard disk space occupied: 10,800,000 * 380 B ≈ 3.6 GB.
- Daily hard disk space required for alarms: 100,000 * 600 B ≈ 60 MB.
- Estimated evidence video size: 10,000 * 10 MB ≈ 100 GB.
- 30-day hard disk requirement: (3.6 GB + 60 MB + 100 GB) * 30 ≈ 3.1 TB. A 4TB capacity hard disk is recommended.


### Bandwidth Requirements
- Direct bandwidth requirement: Device side: 512 kbps * 400 = 200 Mbps; Client side: 512 kbps * 400 = 200 Mbps. Total: 400 Mbps.
- Evidence bandwidth requirement: 85 MB/s * 8 = 680 Mbps.
- Total bandwidth: 400 + 680 = 1.08 Gbps. In addition to evidence playback, GPS, alarms, and other protocol interactions, 1100 Mbps is recommended.

### Reference Configuration for Scenario

| CPU | Memory | Hard Disk | Bandwidth |
| --- | --- | --- | --- |
| 2.4GHz Frequency, 10 Cores 20 Threads (20 Processors Recommended for Virtual Machines) | 64GB | 4TB Capacity, 200MB/s Write Speed | 1100Mbps |



# Thanks for Choosing Streamax!!!