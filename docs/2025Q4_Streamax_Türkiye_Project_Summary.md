---
title: 土耳其国标项目：软硬件定制化开发与低成本未来方案
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
vlook-header-dup: 项目意义;项目团队构成;投入资源;
---

###### ✒️土耳其国标项目：软硬件定制化开发与低成本未来方案<br />*Version 1.0`🐾`20th December*<br />*一般`👀`部门可见*<br />**** <br />[✉️](mailto:sean@streamax.com)<br />**Sean°Mao**<br>*<img alt="今日诗词" src="https://v2.jinrishici.com/one.svg?font-size=23&amp;spacing=2&amp;color=White" style="max-width:100%; display: block; margin: 0;">*

# 土耳其国标项目：软硬件定制化开发与低成本未来方案

[TOC]



---

---

---

- Beijing, 中国

  <iframe src="https://www.zeitverschiebung.net/clock-widget-iframe-v2?language=cn&amp;size=medium&amp;timezone=Asia%2FShanghai" width="100%" frameborder="0" seamless=""></iframe>

- Istanbul, 土耳其

  <iframe src="https://www.zeitverschiebung.net/clock-widget-iframe-v2?language=cn&amp;size=medium&amp;timezone=Europe%2FIstanbul" width="100%" frameborder="0" seamless=""></iframe>

- London, 英国

  <iframe src="https://www.zeitverschiebung.net/clock-widget-iframe-v2?language=cn&amp;size=medium&amp;timezone=Europe%2FLondon" width="100%" frameborder="0" seamless=""></iframe>

- Netherlands, 荷兰

  <iframe src="https://www.zeitverschiebung.net/clock-widget-iframe-v2?language=cn&size=medium&timezone=Europe%2FAmsterdam" width="100%" frameborder="0" seamless></iframe> 

------

## 分享目的



> **定制化与规模化的平衡艺术**_~GdPkAq~_：系统梳理为国标定制的全套流程，并探讨未来通过技术手段实现降本增效的可行路径。

------

## 项目背景

土耳其政府发布规定，要求所有M1[^M1]、M2[^M2]和M3[^M3]类商用车辆必须配备与112紧急呼叫中心连接的移动安全系统。**根据土耳其政府要求，2025年7月1日确定为土耳其国标开始实施的日期，所有变更将于2028年底前完成。**_~Rd~_政府针对各个技术指标给出了权重，并要求强制考核。后续所有进入土耳其的产品都需要符合新国标。即所有DVR和摄像机均需要满足这套国标，才能在土耳其市场上售卖。这套国标的要求主要包含

> *==项目需求==*
>
> 1. **通过安装紧急按钮、摄像头和录像设备，实现了对车载硬件的集中控制**
> 2. **MDVR数据传输接口需要为<kbd>Type-C</kbd>**
> 3. **室内摄像头支持*IP65防护`2M Pixel`Global Shutter***
> 4. **支持DVR直连土耳其报警<kbd>112平台</kbd>，软件通过指定机构`TSE`的<kbd>渗透性测试</kbd>**
>
> ![112 Workflow](https://cdn.jsdelivr.net/gh/maozuxiao/Misaki/%E5%9B%BE%E7%89%871.png)
>

---

---

> **项目意义**
>
> ![项目意义](https://cdn.jsdelivr.net/gh/maozuxiao/Image-shack/%E9%A1%B9%E7%9B%AE%E6%84%8F%E4%B9%89.svg)

> **项目团队构成**
>
> ![项目团队构成](https://cdn.jsdelivr.net/gh/maozuxiao/Image-shack/%E9%A1%B9%E7%9B%AE%E5%9B%A2%E9%98%9F%E6%9E%84%E6%88%90.svg)

> **投入资源**
> 
> ![投入资源](https://cdn.jsdelivr.net/gh/maozuxiao/Image-shack/%E6%8A%95%E5%85%A5%E8%B5%84%E6%BA%90.png)

------


## 核心挑战

_^tab^_

> **核心挑战一：产品认证缺失**
>
> 应新国标要求，需要厂商提供多种类型的产品认证，包含`IP65 (EN 60529)` `ISO 16750-3 (需有ILC)` `IK08 (60068-2-75)` `TS EN 62471 (需有ILC)` `UN/ECE R10(E-Mark)` `UN/ECE R118` 目前土耳其在售的部分产品**缺少这些认证，可能影响后续产品的销售。**_~Rd~_
>
> *==Turkish National Standard Certification Form-CN==*
>
> |    Category    |   Product Name    | Certification/Standard                       | ==                                                           | ==                                                           | ==                        | ==                     | ==              |
> | :------------: | :---------------: | -------------------------------------------- | ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------- | ---------------------- | --------------- |
> |       :        |         :         | ==IP65 (EN 60529)==                          | ==ISO 16750-3 (需有ILC)==                                    | ==IK08 (60068-2-75)==                                        | ==TS EN 62471 (需有ILC)== | ==UN/ECE R10(E-Mark)== | ==UN/ECE R118== |
> |  MDVR _~Gn!~_  |  C6D5.0(Type-C)   | N/A                                          | ✅                                                            | ❌(In Roadmap)<br />已经提交[认证申请](http://oa.streamax.com:8080/km/review/km_review_main/kmReviewMain.do?method=view&fdId=19ae23d144f47636ef8c9a64aa5bd473&s_css=default) | N/A                       |                        | N/A             |
> |       :        | X1N-N0400(Type-C) | N/A                                          | ✅                                                            | N/A                                                          | N/A                       | ✅                      | N/A             |
> |       :        |     X1N-H0401     | N/A                                          | ➖<br />有机械冲击, 暂时挂起                                  | N/A                                                          | N/A                       | ✅                      | N/A             |
> |       :        | X3N-H0208(Type-C) | N/A                                          | ✅                                                            | N/A                                                          | N/A                       | ✅                      | N/A             |
> |       :        |  X7NPRO(Type-C)   | N/A                                          | ❌(In Roadmap)<br />样机已就绪，先安排Emark认证，有草稿后寄回样机做ISO 16750-3（预计202512月底），已经提交[认证申请](http://oa.streamax.com:8080/km/review/km_review_main/kmReviewMain.do?method=view&fdId=19ad866e5a1ab9b3e24433c44579ac62) | N/A                                                          | N/A                       | ❌                      | N/A             |
> |       :        |   A8PRO(Type-C)   | N/A                                          | ❌(In Roadmap)<br />第一轮测试失败，预计202512初开始第二轮测，已经提交[认证申请](http://oa.streamax.com:8080/km/review/km_review_main/kmReviewMain.do?method=view&fdId=19a299d9640373531fe47414f4e8c32f) | N/A                                                          | N/A                       | ✅                      | N/A             |
> |       :        |  A16Max(Type-C)   | N/A                                          | ❌(In Roadmap)<br />样机整改中，先安排Emark认证，有草稿后寄回样机做ISO 16750-3（预计202601月中），已经提交[认证申请](http://oa.streamax.com:8080/km/review/km_review_main/kmReviewMain.do?method=view&fdId=19a299d9640373531fe47414f4e8c32f) | N/A                                                          | N/A                       | ❌                      | N/A             |
> | Camera _~Ro!~_ |       C39B        | ✅(IP66)                                      | ❌<br />已经提交[认证申请](http://58.250.161.100:8080/km/review/km_review_main/kmReviewMain.do?method=view&fdId=19726d7a703a1843d00752e48c7bd563) @蒋旭辉 | ✅                                                            | ✅                         | ❌                      | ❌               |
> |       :        |        C39        | ❌                                            | ❌<br />已经提交[认证申请](http://58.250.161.100:8080/km/review/km_review_main/kmReviewMain.do?method=view&fdId=19726ca8fca8fecd165450b415997ff9) @蒋旭辉 | ❌                                                            | ❌                         | ❌(In Roadmap)          | ❌               |
> |       :        |       CA39        | ✅(IP69K)                                     | ❌<br />需要提供认证证书@蒋旭辉                               | ✅                                                            | ❌                         | ✅                      | ❌               |
> |       :        |       CA39B       | ❌<br />已经提交认证申请@陈峰(Felix 陈峰)     | ❌<br />已经提交认证申请 @蒋旭辉                              | ✅                                                            | ❌                         | ❌                      | ❌               |
> |       :        |        C25        | ✅(IP67)                                      | ✅                                                            | ✅(IK10)                                                      | ❌                         | ✅                      | ❌               |
> |       :        |        C24        | ✅(IP69K)                                     | ❌                                                            | ❌                                                            | ❌                         | ✅                      | ✅               |
> |       :        |       C24M        | ✅(IP67)                                      | ✅                                                            | ✅(IK10)                                                      | ❌                         | ✅                      | ❌               |
> |       :        |        C11        | ✅(IP66)                                      | ❌                                                            | ✅                                                            | ❌                         | ✅                      | ❌               |
> |       :        |  CA11(MINI DOME)  | ❌                                            | ❌                                                            | ❌                                                            | ❌                         | ✅                      | ❌               |
> |       :        |        C26        | ❌<br />murat安排样品交期@许嘉达(Murat許嘉達) | ❌                                                            | ✅                                                            | ❌                         | ✅                      | ❌               |
> |       :        |        C20        | ❌                                            | ✅(In Roadmap)<br />但證書已過期, 須更新<br />已经提交[认证申请](http://oa.streamax.com:8080/km/review/km_review_main/kmReviewMain.do?method=view&fdId=19b027c889849b1dad1b59b45f4b1077&s_css=default) @蒋旭辉 | N/A                                                          | ❌                         | ❌                      | ❌               |

> **核心挑战二：C25G Global shuttle过检受阻**
>
> 
>
> TSE验收方法不透明，通过代理商被告知测试结果：Streamax提供的的C25G样品不支持*全局快门`Global shuttle`*以及其特性*LED防频闪`Auti-LED flicker`*

> **核心挑战三：解决方案成本较高**
>
> *==厂商优劣势对比==*
>
> |        维度        | **Streamax**                                                 | **主要竞争对手**                                             |
> | :----------------: | ------------------------------------------------------------ | ------------------------------------------------------------ |
> | 资金与渠道 _~Aq!~_ | 经销商资金强，公司可额外授信；统一渠道投标，易保护项目       | JMK、DigiMaksi 资金断链，急寻财务伙伴；Dahua 多头代理，内部杀价混乱 |
> |   产品线_~Aq!~_    | 覆盖 M1[^M1]/M2[^M2]/M3[^M3] 全系，已有合规套件              | DTSis  M3[^M3]车辆仅支持8路录像；JMK/Openeye M2[^M2]车辆仅支持4路录像；缺全系方案 |
> |    产能_~Aq!~_     | 年产能力碾压级；对手 Beylerbeyi 仅 3 000 台/年，主攻校车     | 总体产能有限，交付风险高                                     |
> |  认证进度_~Aq!~_   | 预计新年前率先拿到 M2[^M2] 永久准入；对手 JMK/Paress/SFA 或被官方淘汰（非正式消息） | 需更多时间测试，淘汰风险大                                   |
> | 总拥有成本_~Aq!~_  | 多法规一体集成，售后少、单供应商省心                         | 多系统拼凑，额外成本 + 时间损耗                              |
> |    价格 _~Ro!~_    | 进口含税，售价最高；利润已到底线，==需开发经济版==           | 本土厂商免税 25%，仍有降价空间；正推更低价新品               |
> |    政策 _~Ro!~_    | “土耳其制造” 倾向本土，外资被严审；对手可凭声明即过关，Streamax 需逐项测试认证 | 本土厂商吃享政策红利，易把外资挡在门外                       |
>
> 
>
> ------
>
> ### 当前市场进展与竞品情况总结
>
> 截至目前，除 Streamax 外，另有 `8` 家公司已获得临时授权，其产品已完成硬件测试及 112 报警中心连接测试，目前均与 Streamax 一样，正在等待网络安全测试的完成。
>
> ------
>
> - 已入围企业及其品牌
>   - **JMK Güvenlik**：品牌 JMK，中国 OEM  
>   - **Digimaksi Güvenlik**：品牌 ICAR，中国 OEM  
>   - **Mobilbil：品牌 Streamax，中国 OEM**_~GdPkAq~_
>   - **Openeye Mobility**：品牌 Openeye，OEM 来源未知  
>   - **Paress Teknoloji**：品牌 Paress，OEM 来源未知  
>   - **SFA Korkmazlar**：品牌未知  
>   - **Dijital Tanıma Sistemleri (DTSis)**：土耳其本土品牌  
>   - **Seyir Mobil**：品牌 Dahua，中国 OEM  
>   - **Beylerbeyi**：品牌 Beylerbeyi，中土混合 OEM 
> - 竞品套件价格
>   （含MDVR+3路摄像头+2TB SSD）
>   - **JMK**：550 美元（注：此报价基于存储危机前的 2TB SSD 成本，实际价格可能随 SSD 市场波动而变化）  
>   - **Digimaksi / ICAR**：650–700 美元（依客户和采购量浮动）  
>   - **Openeye**：725–770 美元（依客户和采购量浮动）  
>   - **Dahua**：650–700 美元（依客户和采购量浮动）  
>   - **Streamax：820 美元**_~Rd~_
>
> > [!caution]
> >
> > 1. Streamax 并不以 550 美元价位段产品为直接竞争目标，而是将主要竞争对手定位在 650–700 美元区间内的成熟品牌，如 Dahua 和 ICAR
> > 2. 受全球存储行业价格变动影响，如上提到的价格会根据实时行情波动
>


------

## 解决方案

_^tab^_

> **解决方案一：补齐产品认证**
>
> ### 认证流程
>
> ```mermaid
> flowchart LR
> A[提交认证申请] --> B[样机申请]
> B --> E{修改硬件？}
> E -.->|是| F[提供样机给<br/>硬件结构工程师修改]
> F --> G[提供样机给<br/>认证对接人]
> E -.->|否| G
> G --> C[获取<br/>认证报告和证书]
> C --> D[同步<br/>代理商和客户]
> C --> H[同步<br/>硬件工程师并创建Bom和延伸机型料号]
> 
> style A fill:#FEEBD5,stroke:#7AC5CD,stroke-width:2px,color:#00868B
> style B fill:#E6E6FA,stroke:#9370DB,stroke-width:2px,color:#4B0082
> style C fill:#F0F8FF,stroke:#7AC5CD,stroke-width:2px,color:#00868B
> style D fill:#FFD700,stroke:#7AC5CD,stroke-width:2px,color:#00868B
> style E fill:#FFFACD,stroke:#FF8C00,stroke-width:2px,color:#B22222
> style F fill:#E6E6FA,stroke:#9370DB,stroke-width:2px,color:#4B0082
> style G fill:#E6E6FA,stroke:#9370DB,stroke-width:2px,color:#4B0082
> style H fill:#E0FFFF,stroke:#20B2AA,stroke-width:2px,color:#008B8B
> linkStyle default stroke:#9370DB,stroke-width:2px
> ```
> ### 流程详情
>
> ---
>
> ---
>
>
> - 一、提交认证申请
>
>   1. **确认认证类型**：明确是外发认证还是实验室认证，不同的认证类型对应不同的OA流程。
>
>      > * <u>外发认证OA路径</u>：11 产品发展中心类 > > 产品认证申请流程_~Rd~_
>      >
>      > * <u>实验室认证OA路径</u>：10 整机研发中心类 > > 1003 测试类 >> 检测申请业务流程_~Gn~_
>
>   2. **明确费用以及归属**
>
>      > * <u>外发认证</u>：和认证负责人（陈峰/夏文浩）沟通了解认证所需费用，再与销售 & 大区经理确认费用归属_~Rd~_
>      >
>      > * <u>实验室认证</u>: 直接和销售 & 大区经理确认费用归属，实验室负责人（蒋旭辉）_~Gn~_
>
>   3. **确认样机料号以及准备样机规格书**
>
>   4. **填写认证的目的以及流程所需的信息后提交认证申请**
>
> - 二、样机申请并提供给认证对接人
>
>   **费用由`客户`承担**：
>
>   * <u>有在行订单</u>：与商务以及客户沟通，从订单中抽取一台进行认证
>   * <u>无在行订单</u>：商务走下单流程
>
>   **费用由`战区`承担**：内部进行邮件申请，跟单同事进行OA流程申请
>
>   > [!NOTE] 
>   >
>   > 部分认证涉及硬件修改，请提前与硬件结构工程师沟通，安排样机的硬件整改
>
> - 三、获取认证报告和证书
>
>   获取认证报告和证书后需要归档，以便后续项目使用
>
>   > [!NOTE]
>   >
>   > 部分认证需要核对草稿再发放报告和证书，注意核对好产品名称之类的细节
>
> - 四、同步给代理商和客户
>
>   准备外发文档，同步客户，[<kbd>点击访问 >> </kbd>](https://maozuxiao.github.io/my-website/Summary_of_Turkish_National_Standard_Certification_Information.html)
>
> - 五、同步硬件工程师创建Bom和延伸机型料号
>
>   考虑后续存在市场售卖行为，提前相关机型新建料号，方便后续有订单后直接使用
>
>   | OA标题                                                       |  申请单编号   |
>   | :----------------------------------------------------------- | :-----------: |
>   | A8Pro-H1204的TYPE-C的接口                                    | P202511080010 |
>   | A8PRO-H1204 整机料号申请                                     | P202511050073 |
>   | C25G(Global Shuttle) PON 航空6 PIN 新料号申请                | P202511040078 |
>   | 土耳其A8Pro 2.0改TYPE-C接口的BOM申请                         | P202511030136 |
>   | 土耳其X3N-H0208的TYPE-C接口BOM的RJ45和6PIN航空头申请要求申请 | P202511030132 |
>
> 
>
> 

> **解决方案二：提供C25G Global shuttle的证明材料和视频**
>
> ---
>
> - 证明材料
>
>   ### C25G料号
>
>   | 料号          | 描述                                                         |
>   | ------------- | ------------------------------------------------------------ |
>   | 5152200100003 | IP973C25G/V1.0/I1A1S0M3.0P2T1C0/E0001/AX620Q+**SC233HGS**_~Rd~_/1080P/有红外/带音频/无SD卡/3mm/PON供电/另一端RS765-6航空母头/0.5M/白色壳/无/锐明英文LOGO/带独立包装/通用 |
>
>   ### 传感器Spec
>
>   ![SC233HGS Spec](https://cdn.jsdelivr.net/gh/maozuxiao/Misaki/image-20251205114429121.png "SC233HGS Spec")
>
> - 证明视频
>
>   ![C25G Global shuttle Video](https://cdn.jsdelivr.net/gh/maozuxiao/Misaki/Global%20shuttle%20test-Compressed.mp4)
>   
>   [<kbd>C25G anti-led flicker</kbd>](https://app.filmora.io/#/object/d51q8lo7ut3k3vpfq62g)
>   
>   <iframe src="https://app.filmora.io/#/object/d51q8lo7ut3k3vpfq62g" width="100%" height="600" frameborder="0" allowfullscreen loading="lazy" title="Filmora App"></iframe>
>
> 

> **解决方案三：开发低成本方案**
>
> > ------
> > ------
> > ------
> >
> > > **M1 类出租车（60,000辆）**
> > >
> > > - **基础设备**：C6D v5.0 + C25G + C20
> > > - **集成方案**：
> > >   - 符合土耳其112紧急呼叫、税务局、警方乘客人脸识别等法规
> > >   - 内置TP2、Push&Talk、POS、计价器
> > >   - 配套出租车车队管理软件 + 移动叫车App
> > > - **优势**：全功能一体化，无需第三方集成
> > >
> > > _~Rd!~_
> >
> > > **M2 类校车（150,000+辆）**
> > >
> > > - **基础设备**：X1N（即将替换为F6N）+ 2×C25G（未来支持C39B-G）+ C20
> > > - **集成方案**：
> > >   - 满足112法规及教育部校车安全标准
> > >   - 标配BSD盲区监测、座位传感器、移动报警套件
> > >   - 可选SBS云平台 + 家长端追踪App
> > > - **优势**：安全功能预集成，家长可实时监护
> > >
> > > _~Rd!~_
> >
> > > **M2 类公共小巴（350,000辆）**
> > >
> > > - **基础设备**：X1N + 2×C25G + C20
> > > - **方案特点**：
> > >   - 仅提供基础MDVR与摄像系统
> > >   - 无额外集成功能（因客户追求最低成本）
> > > - **定位**：经济型基础监控方案
> > >
> > > _~Gn!~_
> >
> > > **M3 类公共交通大巴（100,000辆）**
> > >
> > > - **基础设备**：X1N / X3N / A8 / A16（依车长配置）+ 多路C25G + C20
> > > - **集成方案**：
> > >   - IBCU智能套件：客流统计、BSD、AVM环视、智能报站、多屏管理
> > >   - 支持PT Cloud平台
> > > - **优势**：面向智慧公交的高阶集成平台
> > >
> > > _~Rd!~_
>
> > [!CAUTION]
> >
> > **核心竞争力**：红色标注的集成功能均为Streamax独家提供的一体化套件，竞品仅能提供MDVR+摄像头，其余竞争对手系统需依赖第三方，增加部署复杂度与成本。
------

------

## 成果与复盘

### 新增多个产品的认证报告

------

- UN/ECE R10(E-Mark)
  - [x] C6D V5.0^Type-c^
  - [x] X1N-N0400^Type-c^
  - [x] X3N-H0208^Type-c^
  - [x]  A8PRO(A8PRO-H0412/A8PRO-H0808/A8PRO-H1204)^Type-c^
  - [ ] X7NPRO (X7NPRO-H0416/X7NPRO-H1608)^Type-c^ <kbd>已审核草稿，待发证</kbd>
  - [ ] A16Max^Type-c^ <kbd>申请中</kbd>
- ISO 16750-3
  - [x] C6D V5.0^Type-c^
  - [x] X1N-N0400^Type-c^
  - [x] X3N-H0208^Type-c^
  - [ ] A8PRO-H0412^Type-c^<kbd>申请中</kbd>
  - [ ] X7NPRO-H0416^Type-c^<kbd>申请中</kbd>
  - [ ] A16Max^Type-c^<kbd>申请中</kbd>
  - [ ] C20 <kbd>申请中</kbd>
- IK08
  - [ ] C6D V5.0^Type-c^<kbd>申请中</kbd>

------
### C25G Global shuttle过检

> C25G Global shuttle过检有序推进中，等待代理商的同步更新。

------
### 开发低成本方案

> 1. 在前线同事Emrys以及Murat的推动下，已经采购并寄回竞品MDVR * 1 pcs 以及 IPC * 3 pcs，并提供给相关的产品工程师进行逆向分析
>    1. IPC已完成方案拆解
>
>    2. MDVR因使用方案不同未进行逆向分析
>
> 2. **在各方领导同事的推动下已经通过立项，预计这周**_~GdPkAq~_*2025-12-22`~`2025-12-26* **完成需求澄清，再协调资源准备kick-off会议**_~GdPkAq~_


------

## Q & A

![Q&A](https://cdn.jsdelivr.net/gh/maozuxiao/Image-shack/q-and-a.gif)

> [^M1]: M1指出租车
> [^M2]: M2指校车和公共小巴
> [^M3]: M3指公共汽车和长途客车

#  Thanks for watching!