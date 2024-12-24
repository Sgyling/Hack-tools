---
title: 55-指纹扫描-burp插件
date: 2024-05-06 14:21:30
tags:
- 渗透工具推荐
categories:
- 工具推荐
- burp插件
---

# Burp 指纹识别

下载链接:https://github.com/shuanx/BurpFingerPrint/releases/download/v1.5/BurpFingerPrint.jar

[![img](https://camo.githubusercontent.com/aec62dc0b68de45205213e0a66854fd631127f8745f8a42d6340d3028a2cd8f7/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f417574686f722d536861756e2d626c7565)](https://camo.githubusercontent.com/aec62dc0b68de45205213e0a66854fd631127f8745f8a42d6340d3028a2cd8f7/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f417574686f722d536861756e2d626c7565) [![img](https://camo.githubusercontent.com/a0f773456863099bcf616a51290c7ea9df5f80dad5116aa42793f3f8cffd5ef7/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f4a444b2d392b2d79656c6c6f77)](https://camo.githubusercontent.com/a0f773456863099bcf616a51290c7ea9df5f80dad5116aa42793f3f8cffd5ef7/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f4a444b2d392b2d79656c6c6f77) [![img](https://camo.githubusercontent.com/58e5f7dfab13434e66cf8dc2eb3c2c17e8ef39e24748293fad85aba83a4be899/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f2545362538442541312545362542432538462545362539382541462545392539372541382545382538392542412545362539432541462d2545352542452538302545352542452538302545362539432538392545362538342538462545362538332542332545342542382538442545352538382542302545372539412538342545362538382539302545362539452539432d726564)](https://camo.githubusercontent.com/58e5f7dfab13434e66cf8dc2eb3c2c17e8ef39e24748293fad85aba83a4be899/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f2545362538442541312545362542432538462545362539382541462545392539372541382545382538392542412545362539432541462d2545352542452538302545352542452538302545362539432538392545362538342538462545362538332542332545342542382538442545352538382542302545372539412538342545362538382539302545362539452539432d726564)

> 攻击过程中，我们通常会用浏览器访问一些资产，该BurpSuite插件实现被动指纹识别+网站提取链接+OA爆破，可帮助我们发现更多资产。

## 功能如下



> 下述功能会在2024年5月底完成，如果有更好的建议都可以提，然后再麻烦点个Star，创作不易，打造最强指纹识别库和弱口令探测库

-  浏览器被动指纹识别，已集成Ehole指纹识别库
-  提取网站的URL链接和解析JS文件中的URL链接后进行指纹识别
-  开界面进行指纹库修改，可导入、导出、重置
-  优化已有指纹库，区分重点指纹和常见指纹，补充部分实战热门漏洞的指纹，方便直接一键getshell [![img.png](https://github.com/shuanx/BurpFingerPrint/raw/main/images/importantFinger.png)](https://github.com/shuanx/BurpFingerPrint/blob/main/images/importantFinger.png)
-  优化算法，提升性能、减少内存开销
-  使用sqlite存储扫描结果，放置因BurpSuite意外退出而导致数据丢失
-  收集github上常见的EXP工具，提起其含有EXP漏洞的指纹，当成重要指纹，一旦页面出现该指纹，就表示有戏有戏
- 1、https://github.com/R4gd0ll/I-Wanna-Get-All
- 2、https://github.com/YinWC/2021hvv_vul
- 3、https://github.com/zhzyker/vulmap
- 4、https://github.com/SecWiki/CMS-Hunter
- 5、https://github.com/coffeehb/Some-PoC-oR-ExP
- 6、https://github.com/White-hua/Apt_t00ls
- 7、https://github.com/biggerwing/nsfocus-rsas-knowledge-base
-  优化GUI，指纹识别出来后，可以快速查看对应的利用EXP的github地址
-  OA类弱口令爆破
-  与本地Packer Fuzzer JS扫描器配合发现隐秘漏洞

## 支持检测指纹



-  通达OA
-  致远OA
-  蓝凌OA
-  泛微OA
-  万户OA
-  东华OA
-  信呼OA
-  等等

## 支持弱口令爆破组件



-  Apache Tomcat
