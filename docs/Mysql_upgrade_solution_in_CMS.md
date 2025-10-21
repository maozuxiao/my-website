---
title: Mysql upgrade solution in CMS
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
vlook-header-dup: Back up the MySql directory;Patch Mysql new version;Start the MySql service;Restore the data using the Data Tool;
---

###### ✒️Mysql upgrade solution in CMS<br />*Version 1.0`🐾`20th October 2025*<br />*一般`👀`部门可见*<br />**** <br />[✉️](mailto:sean@streamax.com)<br />**Sean°Mao**<br>*赫尔新根默斯肯的肥皂泡*

# Mysql upgrade solution in CMS

[toc]

## Revison

| Date       | Version | Description     |
| ---------- | ------- | --------------- |
| 2025-10-20 | V1.0    | Create document |

------

## Check the MySQL version

1. **Navigate to the MySQL Bin Directory**
   - Open Command Prompt.
   - Change directory to the MySQL bin folder:
     ```bash
     cd C:\Program Files (x86)\CMS Server\MySql\bin
     ```

2. **Start the MySQL Service (if not already running)**
   - If the MySQL service is not running, start it using:
     ```bash
     net start mysql
     ```
     - Note: Skip this step if the service is already running.

3. **Connect to the MySQL Server**
   - Use the following command to connect to the MySQL server:
     ```bash
     mysql -uroot -p -P3307 -hlocalhost
     ```
     - Replace `3307` with your server port if different. The default port is `3307`.

4. **Enter the Password**
   - When prompted, enter the password: ***c6l7r8ceacvi2010vs***
   
5. **Check MySQL Version**
   
   - Once connected, check the MySQL version by running:
     ```mysql
     mysql> SELECT VERSION();
     +-----------+
     | VERSION() |
     +-----------+
     | 5.7.44    |
     +-----------+
     1 row in set (0.00 sec)
     ```
------
## Upgrade steps

> [!CAUTION]
>
> 1. Patch download link:  **[<kbd>Click to download</kbd>](https://wj.streamax.com:9443/outpublish.html?code=Aeec36a9c65f848c88fe62c11f122e803&lang=zh-cn#view)**
> 2. The MySQL version in the patch is 5.7.44

------

### Backup the basic data using the Data Tool

1. Open the Backup & Restore Tool: `Data Tool`

2. Back up `Basic Data` & `ADS index files`. You can also back up every item, which may take extra time.

3. Click <kbd>Start backup</kbd>, the `Save As` dialog box pops up, Select the path you need and click <kbd>Save</kbd>![Data Tool-Backup-1](https://cdn.jsdelivr.net/gh/maozuxiao/Image-shack/image-20251021151949809.png)
   
4. After the backup is completed, the following window will pop up
   ![Data Tool-Backup-2](https://cdn.jsdelivr.net/gh/maozuxiao/Image-shack/image-20251020230324644.png)

### Stop all services

1. Open the `DVRServerCtrl`

2. Click <kbd>Stop all server</kbd>

   ![Stop all server](https://cdn.jsdelivr.net/gh/maozuxiao/Image-shack/image-20251020230909101.png)

   > [!WARNING]
   >
   > Wait until all services are stopped before proceeding to the next step

### Back up the MySql directory

To prevent accidental data loss, it is recommended to back up the MySQL folder. Reference path: `C:\Program Files (x86)\CMS Server\MySql`

![Back up the MySql directory](https://cdn.jsdelivr.net/gh/maozuxiao/Image-shack/image-20251020231302647.png)



### Patch Mysql new version 

Copy all files in the MySql directory from the patch (`MySql-3.7.44-SP251009`) to the reference path `C:\Program Files (x86)\CMS Server\MySql`

![Patch Mysql new version](https://cdn.jsdelivr.net/gh/maozuxiao/Image-shack/image-20251020232045466.png)

> [!NOTE]
>
> If the following pop-up window appears, click `Replace the files in the destination`
>
> ![Replace the files in the destination](https://cdn.jsdelivr.net/gh/maozuxiao/Image-shack/image-20251020232208090.png)

### Start the MySql service

Start the MySql service in Windows `Task Manager`
![Start the MySql service](https://cdn.jsdelivr.net/gh/maozuxiao/Image-shack/image-20251020234322339.png)

### Restore the data using the Data Tool

1. Open the Backup & Restore Tool: `Data Tool`，click <kbd>Start restore</kbd>
2. Select [<kbd>Previous backup folder ❯❯</kbd>](#Backup the basic data using the Data Tool )
3. Click <kbd>OK</kbd> and **wait for the restoration to complete**
    ![Restore the data using the Data Tool](https://cdn.jsdelivr.net/gh/maozuxiao/Image-shack/image-20251020235115708.png)
4. After the restore is completed, the following window will pop up
    ![Restore successful](https://cdn.jsdelivr.net/gh/maozuxiao/Image-shack/image-20251021150853710.png#400w)

### Start all service

1. Open the `DVRServerCtrl`

2. Check if any services are not started. If so, click <kbd>Start all server</kbd>

### Check the upgraded MySQL version

 [<kbd>Check the MySQL version ❯❯</kbd>](#Check the MySQL version )

#  Thanks for watching!