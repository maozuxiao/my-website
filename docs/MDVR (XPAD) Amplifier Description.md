---
title: MDVR (XPAD) Amplifier Description
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

###### ✒️MDVR (XPAD) Amplifier Description<br />*Version 1.0`🐾`09th December*<br />*一般`👀`部门可见*<br />**** <br />[✉️](mailto:sean@streamax.com)<br />**Sean°Mao**<br>*赫尔新根默斯肯的肥皂泡*

> [!IMPORTANT]
>
> 1. MDVR(XPAD)的功放功率是20W/4欧姆，则恒定的正弦电压 \( U²=P·R=20×4=80 \)
> 2. XPAD 的 4 Ω 是`标称最佳负载`，为了长期可靠，请把每路负载保持在 ≥ 4 Ω



[TOC]

## XPAD Specification

[<kbd>Click here to download XPAD Specification</kbd>](https://wj.streamax.com:9443/outpublish.html?code=Aac1d93ee36c646c4a0db9f6edfbe6eb8&lang=zh-cn#view)

## Power matching principle
1. MDVR(XPAD)功放输出功率可以小于喇叭的功率
2. MDVR(XPAD)功放输出功率可以等于喇叭的功率，音量最大
3. MDVR(XPAD)功放输出功率不能大于喇叭的功率，否则会导致设备损坏

## 功率匹配计算示例
_^Tab^_
> **示例1**
>
> ---
>
> - 说明
>
>   - 喇叭配置：4个*25W`8 Ω`*的喇叭（连接后总阻抗为8Ω）
>   - 总阻抗：8欧姆
>   - MDVR(XPAD)输出功放功率：\( P=U²/R=80/8=10W \)
>   - 匹配结果：喇叭最大功率25W，满足原则1，但声音会偏小
>
> - Example Diagram-1
>
>   <iframe frameborder="no" border="0" marginwidth="0" marginheight="0" width=556 height=366 src="https://edrawcloudpublicus.s3.amazonaws.com/viewer/self/2539370/share/2025-12-9/1765251494/page-5.svg"></iframe>

> **示例2<a id="示例2"></a>**
>
> ---
>
> - 说明
>
>   - 喇叭配置：8个*25W`8 Ω`*的喇叭（分组连接后总阻抗为4Ω）
>   - 总阻抗：4欧姆
>   - MDVR(XPAD)输出功放功率：\( P=U²/R=80/4=20W \)
>   - 匹配结果：喇叭最大功率25W，满足原则2
>
>   > [!CAUTION]
>   >
>   > 功放的瞬态功率可以到25W
>
> - Example Diagram-2
>
>   <iframe frameborder="no" border="0" marginwidth="0" marginheight="0" width=677 height=638 src="https://edrawcloudpublicus.s3.amazonaws.com/viewer/self/2539370/share/2025-12-9/1765251494/page-6.svg"></iframe>
## 方案说明

### 客户需求 & 疑问

**需求**

> 1. We plan to use 10 pieces of *10W`8 Ω`* speakers in the project.
> 2. We will use these only for internal speakers. We will not use external speakers. Therefore, we will need to connect all 10 speakers to the internal speaker output.

**建议**

_^Tab^_

> **Connect two series and five parallel connections at 3.2 ohms**
>
> #### Diagram-1
>
> <iframe frameborder="no" border="0" marginwidth="0" marginheight="0" width=661 height=661 src="https://edrawcloudpublicus.s3.amazonaws.com/viewer/self/2539370/share/2025-12-9/1765251494/page-2.svg"></iframe>
>
> #### Calculation process-1
>
> 1. **General formula for the equivalent resistance of a parallel circuit** →  \(\frac{1}{R_{\text{total}}} = \frac{1}{R_1} + \frac{1}{R_2} + \dots + \frac{1}{R_n}\)
> 2. **Substitution calculation for this problem (5 resistors of 16Ω in parallel)** → \(\frac{1}{R_{\text{total}}} = \frac{1}{16} + \frac{1}{16} + \frac{1}{16} + \frac{1}{16} + \frac{1}{16} = \frac{5}{16}\)
> 3. **Calculation of total equivalent resistance** → \(R_{\text{total}} = \frac{16}{5} = 3.2\,\Omega\)
>
> #### Refer to [<kbd>Power matching principle</kbd>](#Power matching principle)
>
> MDVR(XPAD)输出功放功率：\( P=U²/R=80/3.2=25W \)
>
> MDVR(XPAD)输出功放功率 25W ＞ 喇叭的功放功率 10W，存在烧坏喇叭或者损坏MDVR(XPAD)的风险，请勿使用该方案
>
> 
>
> 

> **Connect two series and three series, then connect them in parallel and use 4.8 ohms**
>
> #### Diagram-2
>
> <iframe frameborder="no" border="0" marginwidth="0" marginheight="0" width=745 height=677 src="https://edrawcloudpublicus.s3.amazonaws.com/viewer/self/2539370/share/2025-12-9/1765251494/page-3.svg"></iframe>
>
> #### Calculation process-2
>
> 1. **Make a 9.6Ω sub-unit (5×8Ω speakers per sub-unit)**：
>
>    - Sub-unit internal structure:
>
>      - String 1: 2×8Ω speakers in series → \(R_1 = 8+8 = 16\,\Omega\)
>      - String 2: 3×8Ω speakers in series → \(R_2 = 8+8+8 = 24\,\Omega\)
>
>    - Parallel String 1 and String 2 to get sub-unit resistance:
>
>      * \(R_{\text{sub1}} = \frac{R_1 \times R_2}{R_1 + R_2} = \frac{16 \times 24}{16 + 24} = 9.6\,\Omega\)
>
>      * \(R_{\text{sub2}} = \frac{R_3 \times R_4}{R_3 + R_4} = \frac{16 \times 24}{16 + 24} = 9.6\,\Omega\)
>
> 2. **Final circuit connection**：
>
>    Make two identical 9.6Ω sub-units, then connect them **in parallel** → Total resistance:
>
>    \(R_{\text{final}} = \frac{9.6 \times 9.6}{9.6 + 9.6} = 4.8\,\Omega\)
>
> #### Refer to [<kbd>Power matching principle</kbd>](#Power matching principle)
>
> MDVR(XPAD)输出功放功率：\( P=U²/R=80/4.8≈16.67W \)
>
> MDVR(XPAD)输出功放功率 16.67W ＞ 喇叭的功放功率 10W，存在烧坏喇叭或者损坏MDVR(XPAD)的风险，请勿使用该方案

## Streamax建议

1. 喇叭功率≥20W时，且阻抗=4Ω为最佳状态
2. 使用10W功率的喇叭，可能导致喇叭和MDVR(XPAD)的风险，不建议使用
3. 可以参考[示例2](#示例2)中的案例进行配置

#  Thanks for watching!