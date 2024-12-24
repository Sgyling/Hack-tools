---
title: Jenkins-综合漏洞利用工具
date: 2024-2-24 16:14:46
tags:
- 渗透工具推荐
categories:
- 工具推荐
---



# jenkins综合漏洞利用工具

## 使用

### jdk版本

在windows或linux使用jdk8的哪一个版本都应该可以，在macOS里需要jdk8u以上的版本，比如jdk8u321

安装jdk8

```
sudo apt install openjdk-8-jdk
```

kali切换jdk版本.

```
update-alternatives --config java
```



### 外置有效负载

从release下载windows_tools,linux_tools或macOS_tools并放在与JenkinsExploit-GUI-*-SNAPSHOT.jar相同的目录,可以或者自行压缩tools_source中的python源码文件



如果是linux或macOS的话需要对外置payload进行chmod +x 赋予权限 [![图片.png](https://github.com/TheBeastofwar/JenkinsExploit-GUI/raw/master/img/img.png)](https://github.com/TheBeastofwar/JenkinsExploit-GUI/blob/master/img/img.png) [![img_1.png](https://github.com/TheBeastofwar/JenkinsExploit-GUI/raw/master/img/img_1.png)](https://github.com/TheBeastofwar/JenkinsExploit-GUI/blob/master/img/img_1.png)

### dnslog配置

进行dnslog设置，目前仅支持dnslog.pw和ceye.io

[![img_3.png](https://github.com/TheBeastofwar/JenkinsExploit-GUI/raw/master/img/img_3.png)](https://github.com/TheBeastofwar/JenkinsExploit-GUI/blob/master/img/img_3.png) [![img_4.png](https://github.com/TheBeastofwar/JenkinsExploit-GUI/raw/master/img/img_4.png)](https://github.com/TheBeastofwar/JenkinsExploit-GUI/blob/master/img/img_4.png)

### 进行检测

[![img_2.png](https://github.com/TheBeastofwar/JenkinsExploit-GUI/raw/master/img/img_2.png)](https://github.com/TheBeastofwar/JenkinsExploit-GUI/blob/master/img/img_2.png)

- 在验证无回显命令执行的时候为了避免转义问题，推荐使用如下方式进行反弹shell和dnslog外带信息

```
bash -c {echo,Y....}|{base64,-d}|{bash,-i}
```



## 支持检测：

- CVE-2015-8103/CVE-2016-0788 Jenkins 反序列化远程代码执行https://github.com/Medicean/VulApps/tree/master/j/jenkins/1
- CVE-2016-0792 Jenkins XStream反序列化远程代码执行https://github.com/jpiechowka/jenkins-cve-2016-0792
- CVE-2017-1000353 Jenkins-CI 远程代码执行漏洞https://github.com/vulhub/CVE-2017-1000353
- CVE-2018-1000600 Jenkins GitHub SSRF+信息泄露
- CVE-2018-1000861 Jenkins 绕过Groovy沙盒未授权命令执行漏洞https://github.com/orangetw/awesome-jenkins-rce-2019
- CVE-2018-1999002 Jenkins 任意文件读取https://mp.weixin.qq.com/s/MOKeN1qEBonS8bOLw6LH_w
- CVE-2019-1003000 Jenkins 远程代码执行https://github.com/adamyordan/cve-2019-1003000-jenkins-rce-poc
- CVE-2019-1003005/CVE-2019-1003029 远程代码执行（脚本安全插件沙箱绕过）https://github.com/orangetw/awesome-jenkins-rce-2019
- CVE-2024-23897 Jenkins CLI接口任意文件读取漏洞https://github.com/vulhub/vulhub/blob/master/jenkins/CVE-2024-23897

## 未完待续:

- CVE-2016-9299 Jenkins ldap 反序列化远程代码执行，添加 poc

- CVE-2017-1000353 无法检测的错误

- 继续尝试将外部设置的有效负载接入到java代码中

- 新增批量检测功能

  

- # 下载链接

  https://github.com/TheBeastofwar/JenkinsExploit-GUI

​		https://github.com/TheBeastofwar/JenkinsExploit-GUI/releases/tag/v1.3