---
title: FT Cloud training for Mobilbil
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

###### ✒️FT Cloud training for Mobilbil<br />*Version 1.0`🐾`10th December*<br />*一般`👀`部门可见*<br />**** <br />[✉️](mailto:sean@streamax.com)<br />**Sean°Mao**<br>*赫尔新根默斯肯的肥皂泡*
# FT Cloud training for Mobilbil

[TOC]

## INFOs

| Training Instructor |      Trainer       |
| :-----------------: | :----------------: |
|    Doris & Sean     | Mobilbil Engineers |

------

**Training Date**

*2025-12-11`XX:XX`GMT+8*

------

**TimeZone**

------

- *Beijing`中国` UTC+8*

  <iframe src="https://www.zeitverschiebung.net/clock-widget-iframe-v2?language=cn&amp;size=medium&amp;timezone=Asia%2FShanghai" width="100%" height="115" frameborder="0" seamless=""></iframe>

- *Istanbul`土耳其`UTC+3*

  <iframe src="https://www.zeitverschiebung.net/clock-widget-iframe-v2?language=cn&amp;size=medium&amp;timezone=Europe%2FIstanbul" width="100%" height="115" frameborder="0" seamless=""></iframe>

------

## Training Agenda

### Overview of  FT Cloud

> Streamax gave Mobilbil an overview of FT Cloud, explaining its background, value, and the roles of its various functional modules.
> 

------

### Quick Demo base on Mobilbil questions

> Streamax gave a quick demo for Mobilbil.
>
> | No.  | 问题总结 (Issue Summary)                 | 问题描述 (Issue Description)                                 | 操作路径 (Steps to Reproduce)                                |
> | ---- | ---------------------------------------- | ------------------------------------------------------------ | ------------------------------------------------------------ |
> | 1    | How are Driver Faces Defined?            | 客户希望只允许已定义的驾驶员驾驶车辆，如果未定义的驾驶员正在驾驶或发生警报，则只发出未定义驾驶员的警报。这是否可行？如果可行，我们希望知道在哪里可以进行设置。<br />The customer wants to have only defined drivers and if an undefined driver is driving or an alarm occurs, they want an undefined driver alarm. Is this possible? If possible, we would like to be shown where the settings are made |                                                              |
> | 2    | Automatic Email with Alarm Video Link    | 客户希望报警信息能自动通过邮件发送，并且邮件中包含链接，点击链接后能查看相关报警视频（类似 Ceiba 系统），这是如何实现的？<br>The customer wants the incoming alarms to be sent automatically as an e-mail, and when a link is created in this e-mail and clicked on it, they want to see the related alarm video (just like Ceiba), how does this happen? | Need to configure Alarm upload rule if you want to view the evidence while the Device is offline, but it will occupy a lot of cloud storage<br />FT Manager >> Alarm Management >> Alarm Notification >> Add<br />无法设置模板 |
> | 3    | Evidence Video Auto-play Issue           | 某些证据视频在鼠标悬停时自动播放，而另一些则完全无法播放，原因是什么？<br>Some of the evidence videos are automatically watched when you hover over them and some are not watched at all, what is the reason for this? | Some are pictures， some are evidence that was not uploaded  |
> | 4    | Alarm Reporting Location                 | 所有报警的报告从哪里获取？如何查看哪位司机触发了哪些报警？在哪里可以打印周报和月报？<br>Where is the reporting of all alarms taken from? Which driver generated which alarms and where can I print weekly and monthly reports? | FT Vision >> Report Center >> Safety Analysis Risk Ranking >> Driver |
> | 5    | Alarm Time Settings for Evidence         | 证据视频的报警时间设置在哪里？如“报警前3秒”、“报警后5秒”等选项在哪里配置？<br>Where do we set the alarm times of the evidence generated, where are the options such as 3 seconds before alarm, 5 seconds after alarm? | FT Manager >> Alarm Management >> Alarm Upload >> Add >> Recordingf`enabled` >> Before Alarm (s) & After Alarm (s) |
> | 6    | Purpose of Range and Traffic on Homepage | 车辆监控菜单首页上显示的范围和流量信息有何用途？<br>What is the range and traffic that appears on the homepage in the Vehicle Monitoring menu for? | Ranging : Length measurement<br />Traffic: Transportation status |
> | 7    | Evidence Tracking When Device is Offline | 当设备离线时无法追踪证据，只有在线时才能追踪。客户无法接受这种情况，是否可以通过软件修复？<br>The evidence is not tracked when the device is offline, it can only be tracked when it is online, will this always be the case because no customer will accept this, can it be fixed with software? | FT Manager >> Alarm Management >> Alarm Upload               |

------

### Q & A

> If Mobilbil has any further questions, they can be asked at the meeting.

------

### Summary

> 1. Provide the path to the user manual for reference if you are unsure how to use subsequent functions.
>
> 2. Ask Mobilbil for their opinions and suggestions on FT Cloud.

------

# Thanks for Watching!!!