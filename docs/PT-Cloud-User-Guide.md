---
title: PT Cloud User Guide
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

###### ✒️PT Cloud User Guide<br />*Version 1.0`🐾`15th September 2025*<br />*一般`👀`部门可见*<br />**** <br />*Sean`🍍` Mao*<br />[✉️](mailto:sean@streamax.com)

# **✒️**PT Cloud User Guide

[TOC]

## OverView

_^tab^_

> **What's PT Cloud?**
>
> PT Cloud is a Modular, Intelligent, All-in-one Public Transit Platform Focused on Safety and Operations.

> **Video Introduction**
> 
> <iframe width="1236" height="695" src="https://www.youtube.com/embed/T-xQuW6ARNo" title="PT cloud Overview" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>



## How to use the PT Cloud?



### Basic Data Management



#### 1. Login
- URL → login page  
- Enter **username**, **password**, pick **language**  
- 5 failed attempts = account locked (contact admin)  
- Security verification on 1st login or after fail

---

#### 2. Home Page Layout
| Area             | Function                                     |
| ---------------- | -------------------------------------------- |
| **Banner**       | configurable ad picture                      |
| **User**         | logout                                       |
| **System Entry** | subsystem icons (role-based) open in new tab |
| **Shortcut**     | max 8 user-defined quick links (edit ✏️)      |

---

#### 3. Global Toolbar
Icons left → right  
1. **Language** switch  
2. **Help** (built-in Open-API docs only)  
3. **Download Center** (drawer)  
4. **Notifications** (drawer)

---

#### 4. Basic Data – Add Order
**Priority 1 (must)**  
1. Create **Organization** (fleet/company)  
2. Create **Role**  
3. Create **User** (link to org + role)

**Priority 2**  
4. Add **Vehicle** + on-board **Device**  
5. Add **Practitioner** (driver, conductor …)

**Priority 3**  
6. Add **Station**, **Depot**, **Line**, **Sub-line**  
7. Bind stations/depots to sub-line

---

#### 5. Organization Mgmt
- **Add**: name + parent (top = Center) + optional city/code/map-center  
- **Disable/Enable** toggle (blocked if resources inside)  
- **Delete** only when unused  
- **Search** by keyword (fuzzy)

---

#### 6. User Mgmt
- Fields: username (≥6), email, strong pwd, name, phone, org  
- **Status**: enable/disable (instant)  
- **Auth**: multiple roles per user; data scope by org/line/depot  
- **Bulk suspend** & **delete** available

---

#### 7. Role & Auth Center
- **Role** = collection of **Services** (function bundles)  
- Copy / enable / disable roles  
- **Role Authorization**: link users ↔ roles  
- **Data Authorization**: link users ↔ org, line, depot trees  
- **Service Mgmt**: create custom service bundles

---

#### 8. Practitioner (Driver) Mgmt
**Single Add**  
- Required: name, employee-ID (unique), IC chip ID, org, post type  
- Optional: ID, licence, certificate, contact …  

**Bulk Import**  
- Download template → fill → zip → upload → task queued  
- **Ignore** = skip duplicates; **Overwrite** = update  
- Import photos: zip named “EmployeeID.jpg”  

**Transfer Group**: move staff between orgs (face photo auto-sent)

---

#### 9. Vehicle Mgmt
**Core fields**  
- License plate & color, internal ID, org, operation status  
- Device info: signalling/video protocol, SPC, model, camera count  
- Optional: VIN, capacity, mileage, insurance, maintenance  

**Bulk import / custom template / transfer group** same as practitioners

---

#### 10. Station & Depot & Line
**Station**  
- Add: name, ID (unique), alias, coords, description  
- Import GTFS-like template supported  

**Depot**  
- fenced area on map; link to org & city  

**Line**  
- Add: name, number, type, org, city, color trace  
- **Sub-line** (run-mode): different stop sequence/shape under same line  
  – set stations → mileage → schedule duration → save  
- **Field Info**: non-revenue stops (yard, charging …)  
- **Route File**: generate & push to device (voice, map, speed, fence …)

---

#### 11. Route File Workflow
1. **Audio Mgmt**  
   - Import multi-lang files (keyword “(en)” …)  
   - Build **Audio Template** (inbound, outbound, terminal …)  
   - Bind station ↔ audio  

2. **Parameter Template**  
   - Default speed limit, stop radius, service terms, alerts, business requests  

3. **Create File**  
   - pick sub-line + template → audition → generate  

4. **Remote Update**  
   - task: select vehicles + file + effective time + diff/full upgrade  
   - monitor progress, cancel or re-push

---

#### 12. SMS & Phonebook
**SMS Template**  
- general / schedule / safety types  
- max 500 chars, sort order  

**Appointment SMS**  
- auto-send to driver screen + TTS in set date & interval  

**Phonebook** (device/SIM)  
- white-list to block spam; set in/out call rules per contact

---

#### 13. Channel Configuration
- rename video channels (platform-only)  
- global default vs per-vehicle custom  
- enable/disable decides live-view availability

---

#### 14. Auto Import (GTFS)
- ftp/ftps/http(s) fetch on schedule  
- sync stations, lines, trips into PT Cloud  
- test connection, logs & error details provided

---

&gt; **Tip**: always create org first; every other object needs it.  
&gt; **Tip**: use templates (audio, parameter, import) to speed up bulk work.


------

# Thanks for watching!