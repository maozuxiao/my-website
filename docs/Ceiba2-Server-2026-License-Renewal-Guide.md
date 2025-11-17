---
title: Ceiba2 Server 2026 License Renewal Guide
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

###### ✒️Ceiba2 Server 2026 License Renewal Guide<br />*Version 1.0`🐾`04th November2025*<br />*一般`👀`部门可见*<br />**** <br />[✉️](mailto:sean@streamax.com)<br />**Sean°Mao**<br>*赫尔新根默斯肯的肥皂泡*

# Ceiba2 Server 2026 License Renewal Guide

[TOC]

## Work Flow Diagram

```mermaid
flowchart LR

    classDef startEnd fill:#2E7D32,stroke:#1B5E20,color:#fff,stroke-width:2px,rx:8px
    classDef process  fill:#4CAF50,stroke:#388E3C,color:#fff,stroke-width:2px,rx:8px
    classDef decision fill:#66BB6A,stroke:#2E7D32,color:#fff,stroke-width:2px,rx:8px
    linkStyle default stroke:#2E7D32,stroke-width:2px

    subgraph bg [ ]
        direction LR
        A([Start]) --> B{Check 
        Ceiba2 Server 
        Version}
        B -->|2.6.6.x.xx and below| C[Use LIC_DVRGTSERVICE.dat]
        B -->|2.6.7.x.xx| D[Use 20261203267.pem]
        B -->|2.6.8.x.xx| E[Use 20261203268.pem]
        C --> F([End])
        D --> F
        E --> F
    end

    class A,F startEnd
    class C,D,E process
    class B decision

    style bg fill:#F9FBE7,stroke:#AED581,stroke-width:0px
```

------

## ~~Download the License File~~

> [!IMPORTANT]
>
> 1. License File download link:  **[<kbd>Click to download</kbd>](https://wj.streamax.com:9443/outpublish.html?code=Bb666ad4fb81f4ba5aafe1e7588196a56&lang=zh-cn#view)**
> 2. Contact your **Technical Support** to get the password


------
## Check the Ceiba2 Server Version

_^Tab^_

> **Method 1**
> 1. Open the `Control Pannel` of Windows Server
> 2. Check the Version in version column
>
> ![Check version-Method1](https://cdn.jsdelivr.net/gh/maozuxiao/Image-shack/image-20251104134851497.png)

> **Method 2**
> 1. Access the Ceiba2 web management platform, reference url: **[<kbd>http://localhost:12056/basic/home/default.html</kbd>](http://localhost:12056/basic/home/default.html)**
> 2. Click *ⓘ`Version`* to check the version
>
> ![Check version-Method2](https://cdn.jsdelivr.net/gh/maozuxiao/Image-shack/image-20251104135043261.png)
------
## Renewal Steps

_^Tab^_

> **Ceiba 2 version 2.6.3.x.xx and below**
>
> 1. Navigate to the `\CMS Server\TransmitServer` folder on the Windows server, reference path: <kbd>C:\Program Files (x86)\CMS Server\TransmitServer</kbd>
> 2. Replace the `LIC_DVRGTSERVICE.dat` license file
> 3. Restart all services via <kbd>DVRServerCtrl</kbd> to make the license file take effect (if the server has an auto-restart policy, you can also let the server restart automatically to activate the license file)

> **Ceiba 2 version 2.6.7.x.xx**
>
> 1. Access the Ceiba2 web management platform, reference url: **[<kbd>http://localhost:12056/basic/home/default.html</kbd>](http://localhost:12056/basic/home/default.html)**
> 2. Log in with the admin username and password
> 3. Navigate to ⚙️>>Authorization
> 4. Click <kbd>Upload authorization</kbd>
> 5. Select the license file `20261203267.pem`, click <kbd>Open</kbd>

> **Ceiba 2 version 2.6.8.x.xx**
>
> 1. Access the Ceiba2 web management platform, reference url: **[<kbd>http://localhost:12056/basic/home/default.html</kbd>](http://localhost:12056/basic/home/default.html)**
> 2. Log in with the admin username and password
> 3. Navigate to ⚙️>>Authorization
> 4. Click <kbd>Upload authorization</kbd>
> 5. Select the license file `20261203268.pem`, click <kbd>Open</kbd>

------
#  Thanks for watching!