---
title: 53-nacs-自动扫描并且利用漏洞
date: 2024-05-01 17:53:07
tags:
- 渗透工具推荐
categories:
- 工具推荐
---

# nacs 事件驱动的扫描器

github:https://github.com/u21h2/nacs

下载链接:https://github.com/u21h2/nacs/releases/tag/0.0.4

[[中文自述\]](https://github.com/u21h2/nacs/blob/main/README.md) | [[英文自述文件\]](https://github.com/u21h2/nacs/blob/main/README_EN.md)

[![发布](https://camo.githubusercontent.com/3ec3266145c2f5f5b9eeecdeee15398f69fffe59d87cb53043aa3ec2f5aba0c1/68747470733a2f2f696d672e736869656c64732e696f2f6769746875622f676f2d6d6f642f676f2d76657273696f6e2f75323168322f6e6163733f66696c656e616d653d676f2e6d6f64)](https://github.com/u21h2/nacs) [![发布](https://camo.githubusercontent.com/6847718f24bd6b0de661635fef3bb95d170dcf748f85d38def9bc280bc15f4e4/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f6e6163732d302e302e342d666636396234)](https://github.com/u21h2/nacs) [![img](https://camo.githubusercontent.com/42dde9b88cc4ed858ff81187d443213d08910c2178c924988e82749cccf30074/68747470733a2f2f696d672e736869656c64732e696f2f6769746875622f646f776e6c6f6164732f75323168322f6e6163732f746f74616c)](https://github.com/u21h2/nacs/releases) [![img](https://camo.githubusercontent.com/e7a05da50fc9b9c1fa905d506a3d7078c798cd05c2859cfdece0a8e4c9f25d0c/68747470733a2f2f696d672e736869656c64732e696f2f6769746875622f666f726b732f75323168322f6e616373)](https://github.com/u21h2/nacs)

## ✨ 功能



- 探活
- 服务扫描(常规&非常规则端口)
- poc探测(xray&nuclei格式)
- 数据库等弱口令爆破
- 内网常见漏洞利用

## ⭐️亮点



- 常见组件及常见HTTP请求头的log4j漏洞检测 [![图像](https://github.com/u21h2/nacs/raw/main/utils/3.png)](https://github.com/u21h2/nacs/blob/main/utils/3.png)
- 非常规范端口的服务扫描和使用（比如2222端口的ssh等等）
- 识别为公网IP时，从fofa搜索可用的资产作为扫描的补充（正在写）
- 自动识别简单web页面的输入框，用于弱口令爆破及log4j的检测(正在写)

# 利用过程



```
环境配置
    弱口令配置、要写入的公钥、反弹的地址、ceye的API等等
探活
    icmp ping
资产初筛
    确定哪个端口对应哪种服务，尤其是非常规端口
漏洞打点(根据指纹信息发送到相应的模块)
    可以RCE的非web服务 进行探测或者利用(redis、永恒之蓝等)
    web服务 扫poc 如log4j
    非web服务 未授权及爆破
    web服务 自动爆破登录 (未实现)
    重点服务 OA、VPN、Weblogic、蜜罐等
```



## 使用方法

### 快速使用

```
sudo ./nacs -h IP或IP段 -o result.txt
sudo ./nacs -hf IP或IP段的文件 -o result.txt
sudo ./nacs -u url(支持http、ssh、ftp、smb等) -o result.txt
sudo ./nacs -uf url文件 -o result.txt
```



### 效果



- （1）添加目标IP：对10.15.196.135机器进行扫描，手动添加密码，并关闭反连平台的测试（即不测试log4j等）

  ```
  sudo ./nacs -h 10.15.196.135 -passwordadd "xxx,xxx" -noreverse
  ```

  

  [![图像](https://github.com/u21h2/nacs/raw/main/utils/1.png)](https://github.com/u21h2/nacs/blob/main/utils/1.png) 可见发现了nacos的权限绕过漏洞，以及各服务爆破成功

- （2）直接添加目标url：对10.211.55.7的ssh端口进行爆破，添加用户名密码第一测试，爆破成功后执行ifconfig；文档某靶场url尝试log4j漏洞

  ```
  sudo ./nacs -u "ssh://10.211.55.7:22,http://123.58.224.8:13099" -usernameadd test -passwordadd test -command ifconfig
  ```

  

  [![图像](https://github.com/u21h2/nacs/raw/main/utils/2.png)](https://github.com/u21h2/nacs/blob/main/utils/2.png) 可见两个log4j的poc都检测成功了，注入点在请求头的X-Api-Version字段；ssh爆破也成功了

### 常用参数



```
-o 指定输出的日志文件
-np 不探活, 直接扫端口
-po 只使用这些端口
-pa 添加这些端口
-fscanpocpath fscan的poc路径 格式为"web/pocs/"
-nucleipocpath nuclei的poc路径 格式为"xxx/pocs/**"
-nopoc 不进行poc探测, 包括xray与nuclei
-nuclei 使用nuclei进行探测(不强烈建议加上此参数,因为nuclei的poc太多了)
-nobrute 不进行爆破
-pocdebug poc探测时打印全部信息
-brutedebug 爆破时打印全部信息
-useradd 爆破时添加用户名
-passwordadd 爆破时添加密码
-noreverse 不使用反连平台
-ceyekey 你自己的ceye token
-ceyedomain 你自己的ceye domain
```



## 表格



资料参考了以下优秀作品

- fscan https://github.com/shadow1ng/fscan专注于内网 web 和服务的 poc 服务的爆破
- kscan https://github.com/lcvvvv/kscan专注于信息收集能够探测到非常规端口开的服务，例如 2222 的 ssh
- dismap https://github.com/zhzyker/dismap资产收集
- 拉登https://github.com/k8gege/LadonGo
- xray https://github.com/chaitin/xray主动/被动扫常见web漏洞 扫poc
- 虾虎鱼https://cn.gobies.org/
- vulmap https://github.com/zhzyker/vulmap
- nali https://github.com/zu1k/nali查询IP地理信息和CDN最成功
- ehole https://github.com/EdgeSecurityTeam/EHole重点攻击系统指纹探测暂时不能用了
- Nuclei https://github.com/projectdiscovery/nuclei基于poc的快速扫描
- pocV https://github.com/WAY29/pocV能够扫描x射线和细胞核的poc
- afrog https://github.com/zan8in/afrog CVE、CNVD、默认口令、信息泄露、指纹识别、未授权访问、任意文件读取、命令执行
- 啄木鸟https://github.com/Ciyfly/woodpecker
- xray-poc-scan-engine https://github.com/h1iba1/xray-poc-scan-engine
- pocassist https://github.com/jweny/pocassist可视化编辑导入和运行
- Aopo https://github.com/ExpLangcn/Aopo
- SpringExploit https://github.com/SummerSec/SpringExploit
- fscanpoc补充https://github.com/chaosec2021/fscan-POC
