---
title: APK自动扫描漏洞
date: 2024-4-23 16:14:46
tags:
- 渗透工具推荐
categories:
- 工具推荐
---



# AppMessenger(appmsg)



下载地址：https://github.com/sulab999/AppMessenger/releases/download/v4.6.3/appmsg4.6.3.zip

jdk17下载地址:https://www.oracle.com/java/technologies/javase/jdk17-archive-downloads.html

# 介绍



## 解析APP



一款适用于以APP病毒分析、APP漏洞挖掘、APP开发、HW行动/红队/渗透测试团队为场景的移动端(Android、iOS)辅助分析工具，可以帮助APP开发工程师、病毒分析师、漏洞/安全研究员提高工作效率，帮助渗透测试工程师、攻击队成员/红队成员快速收集到移动端中关键的资产信息并提供基本的信息输出,如：包名（packageName）、版本(versionName\versionCode)、应用签名(Signature)、文件MD5、SDK、URL、APP漏洞等信息。

## APK文件解析



[![img](https://github.com/sulab999/AppMessenger/raw/master/pic/pic1.png)](https://github.com/sulab999/AppMessenger/blob/master/pic/pic1.png)

[![img](https://github.com/sulab999/AppMessenger/raw/master/pic/pic2.png)](https://github.com/sulab999/AppMessenger/blob/master/pic/pic2.png)

[![img](https://github.com/sulab999/AppMessenger/raw/master/pic/pic3.png)](https://github.com/sulab999/AppMessenger/blob/master/pic/pic3.png)

## IPA文件解析



[![img](https://github.com/sulab999/AppMessenger/raw/master/pic/ipa1.png)](https://github.com/sulab999/AppMessenger/blob/master/pic/ipa1.png)

[![img](https://github.com/sulab999/AppMessenger/raw/master/pic/ipa2.png)](https://github.com/sulab999/AppMessenger/blob/master/pic/ipa2.png)

## 高级检测(目前只支持APK)



[![img](https://github.com/sulab999/AppMessenger/raw/master/pic/gj1.png)](https://github.com/sulab999/AppMessenger/blob/master/pic/gj1.png)

[![img](https://github.com/sulab999/AppMessenger/raw/master/pic/gj2.png)](https://github.com/sulab999/AppMessenger/blob/master/pic/gj2.png)

[![img](https://github.com/sulab999/AppMessenger/raw/master/pic/gj3.png)](https://github.com/sulab999/AppMessenger/blob/master/pic/gj3.png)

# 前言



- 本项目始于SULAB安全团队，并联合知识星球：移动安全
- 如果您觉得这个项目对您有用，请点击本项目右上角的"star"按钮。
- 如果您想持续跟进新的版本情况，请点击本项目右上角的"Watch"按钮。
- 会在知识星球发布内测或特别版
- 新的功能或者需求会持续进行开发，欢迎提BUG。
- 后期更新版本见releases

# 适用场景



- APP病毒分析
- APP漏洞挖掘
- APP信息收集
- 日常渗透测试/攻防演练中对APP中涉及的关键资产信息收集，比如URL地址、IP地址、关键字等信息的采集等。

# 功能介绍:



- [√] 支持任意文件MD5识别
- [√] 支持DEX、APK、IPA文件的信息收集
- [√] 支持Android壳识别（识别准确率99%，业界一流）
- [√] 支持基础检测：文件路径、包名、版本名、文件MD5、文件SHA1、DEX MD5、文件大小、allowbackup、debuggable、打包时间
- [√] 支持解析APP权限信息、签名信息、支持系统版本等其他信息
- [√] 支持敏感信息检测，如：url、ip等
- [√] 支持Windows系统、MacOS系统、*nux系列的系统
- [√] APP漏洞检测
- [×] 一键对APK文件重打包

# 环境说明



- App文件解析需要使用JAVA环境,JAVA版本11及以上
- 检测java版本命令:java --version
- 启动:java -jar appmsg.jar
- Pro版已集成java环境可开箱即用

# 使用方法



pro版
可直接安装使用

v4.5之前
建议使用jdk9或jdk1.8

v4.5-v4.6.3版本
1、如有java环境，可双击apkmsg.jar，即可启动，直接将APP拖入即可自动识别
2、如果无法打开或显示有乱码，可下载配套的jdk11，运行里面写好的脚本，即可一键启动
3、MAC和Linux系统需要对运行脚本和JAVA_HOME里的文件授予可执行权限，命令如下
chmod 777 运行mac/运行linux.sh
chmod -R 777 JAVA_HOME
jdk11：https://github.com/sulab999/AppMessenger/releases/download/v4.6.2/jdk11.zip
[![start](https://github.com/sulab999/AppMessenger/raw/master/pic/start.png)](https://github.com/sulab999/AppMessenger/blob/master/pic/start.png)

# 感谢“移动安全”知识星球的小伙伴，欢迎进群

![zsxq](https://github.com/sulab999/AppMessenger/raw/master/pic/kefu.jpg)