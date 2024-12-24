---
title: 帮你识别目标防火墙的工具
date: 2024-4-1 13:10:00
tags:
- 渗透工具推荐
categories:
- 工具推荐
---



## 它是如何工作的？

github:https://github.com/EnableSecurity/wafw00f

为了发挥其魔力，WAFW00F 执行以下操作：

- 发送*正常的*HTTP请求并分析响应；这确定了许多 WAF 解决方案。
- 如果不成功，它会发送许多（可能是恶意的）HTTP 请求，并使用简单的逻辑来推断它是哪个 WAF。
- 如果也不成功，它会分析之前返回的响应，并使用另一种简单的算法来猜测 WAF 或安全解决方案是否正在积极响应我们的攻击。

[有关更多详细信息，请查看我们的主存储库](https://github.com/EnableSecurity/wafw00f)上的源代码。

## 它检测到什么？



WAFW00F可以检测多种防火墙，列表如下：

```
$ wafw00f -l

                   ______
                  /      \
                 (  Woof! )
                  \  ____/                      )
                  ,,                           ) (_
             .-. -    _______                 ( |__|
            ()``; |==|_______)                .)|__|
            / ('        /|\                  (  |__|
        (  /  )        / | \                  . |__|
         \(_)_))      /  |  \                   |__|

                    ~ WAFW00F : v2.2.0 ~
    The Web Application Firewall Fingerprinting Toolkit

[+] Can test for these WAFs:

  WAF Name                        Manufacturer
  --------                        ------------

  ACE XML Gateway                  Cisco
  aeSecure                         aeSecure
  AireeCDN                         Airee
  Airlock                          Phion/Ergon
  Alert Logic                      Alert Logic
  AliYunDun                        Alibaba Cloud Computing
  Anquanbao                        Anquanbao
  AnYu                             AnYu Technologies
  Approach                         Approach
  AppWall                          Radware
  Armor Defense                    Armor
  ArvanCloud                       ArvanCloud
  ASP.NET Generic                  Microsoft
  ASPA Firewall                    ASPA Engineering Co.
  Astra                            Czar Securities
  AWS Elastic Load Balancer        Amazon
  AzionCDN                         AzionCDN
  Azure Front Door                 Microsoft
  Barikode                         Ethic Ninja
  Barracuda                        Barracuda Networks
  Bekchy                           Faydata Technologies Inc.
  Beluga CDN                       Beluga
  BIG-IP Local Traffic Manager     F5 Networks
  BinarySec                        BinarySec
  BitNinja                         BitNinja
  BlockDoS                         BlockDoS
  Bluedon                          Bluedon IST
  BulletProof Security Pro         AITpro Security
  CacheWall                        Varnish
  CacheFly CDN                     CacheFly
  Comodo cWatch                    Comodo CyberSecurity
  CdnNS Application Gateway        CdnNs/WdidcNet
  ChinaCache Load Balancer         ChinaCache
  Chuang Yu Shield                 Yunaq
  Cloudbric                        Penta Security
  Cloudflare                       Cloudflare Inc.
  Cloudfloor                       Cloudfloor DNS
  Cloudfront                       Amazon
  CrawlProtect                     Jean-Denis Brun
  DataPower                        IBM
  DenyALL                          Rohde & Schwarz CyberSecurity
  Distil                           Distil Networks
  DOSarrest                        DOSarrest Internet Security
  DotDefender                      Applicure Technologies
  DynamicWeb Injection Check       DynamicWeb
  Edgecast                         Verizon Digital Media
  Eisoo Cloud Firewall             Eisoo
  Expression Engine                EllisLab
  BIG-IP AppSec Manager            F5 Networks
  BIG-IP AP Manager                F5 Networks
  Fastly                           Fastly CDN
  FirePass                         F5 Networks
  FortiWeb                         Fortinet
  GoDaddy Website Protection       GoDaddy
  Greywizard                       Grey Wizard
  Huawei Cloud Firewall            Huawei
  HyperGuard                       Art of Defense
  Imunify360                       CloudLinux
  Incapsula                        Imperva Inc.
  IndusGuard                       Indusface
  Instart DX                       Instart Logic
  ISA Server                       Microsoft
  Janusec Application Gateway      Janusec
  Jiasule                          Jiasule
  Kona SiteDefender                Akamai
  KS-WAF                           KnownSec
  KeyCDN                           KeyCDN
  LimeLight CDN                    LimeLight
  LiteSpeed                        LiteSpeed Technologies
  Open-Resty Lua Nginx             FLOSS
  Oracle Cloud                     Oracle
  Malcare                          Inactiv
  MaxCDN                           MaxCDN
  Mission Control Shield           Mission Control
  ModSecurity                      SpiderLabs
  NAXSI                            NBS Systems
  Nemesida                         PentestIt
  NevisProxy                       AdNovum
  NetContinuum                     Barracuda Networks
  NetScaler AppFirewall            Citrix Systems
  Newdefend                        NewDefend
  NexusGuard Firewall              NexusGuard
  NinjaFirewall                    NinTechNet
  NullDDoS Protection              NullDDoS
  NSFocus                          NSFocus Global Inc.
  OnMessage Shield                 BlackBaud
  Palo Alto Next Gen Firewall      Palo Alto Networks
  PerimeterX                       PerimeterX
  PentaWAF                         Global Network Services
  pkSecurity IDS                   pkSec
  PT Application Firewall          Positive Technologies
  PowerCDN                         PowerCDN
  Profense                         ArmorLogic
  Puhui                            Puhui
  Qcloud                           Tencent Cloud
  Qiniu                            Qiniu CDN
  Qrator                           Qrator
  Reblaze                          Reblaze
  RSFirewall                       RSJoomla!
  RequestValidationMode            Microsoft
  Sabre Firewall                   Sabre
  Safe3 Web Firewall               Safe3
  Safedog                          SafeDog
  Safeline                         Chaitin Tech.
  SecKing                          SecKing
  eEye SecureIIS                   BeyondTrust
  SecuPress WP Security            SecuPress
  SecureSphere                     Imperva Inc.
  Secure Entry                     United Security Providers
  SEnginx                          Neusoft
  ServerDefender VP                Port80 Software
  Shield Security                  One Dollar Plugin
  Shadow Daemon                    Zecure
  SiteGround                       SiteGround
  SiteGuard                        Sakura Inc.
  Sitelock                         TrueShield
  SonicWall                        Dell
  UTM Web Protection               Sophos
  Squarespace                      Squarespace
  SquidProxy IDS                   SquidProxy
  StackPath                        StackPath
  Sucuri CloudProxy                Sucuri Inc.
  Tencent Cloud Firewall           Tencent Technologies
  Teros                            Citrix Systems
  Trafficshield                    F5 Networks
  TransIP Web Firewall             TransIP
  URLMaster SecurityCheck          iFinity/DotNetNuke
  URLScan                          Microsoft
  UEWaf                            UCloud
  Varnish                          OWASP
  Viettel                          Cloudrity
  VirusDie                         VirusDie LLC
  Wallarm                          Wallarm Inc.
  WatchGuard                       WatchGuard Technologies
  WebARX                           WebARX Security Solutions
  WebKnight                        AQTRONIX
  WebLand                          WebLand
  RayWAF                           WebRay Solutions
  WebSEAL                          IBM
  WebTotem                         WebTotem
  West263 CDN                      West263CDN
  Wordfence                        Defiant
  WP Cerber Security               Cerber Tech
  WTS-WAF                          WTS
  360WangZhanBao                   360 Technologies
  XLabs Security WAF               XLabs
  Xuanwudun                        Xuanwudun
  Yundun                           Yundun
  Yunsuo                           Yunsuo
  Yunjiasu                         Baidu Cloud Computing
  YXLink                           YxLink Technologies
  Zenedge                          Zenedge
  ZScaler                          Accenture
```



## 我该如何使用它？



[首先，按照此处](https://github.com/EnableSecurity/wafw00f#how-do-i-install-it)所述安装工具。

如需帮助，您可以使用该`--help`选项。基本用法是将 URL 作为参数传递。例子：

```
$   wafw00f https://example.org

                   ______
                  /      \
                 (  Woof! )
                  \  ____/                      )
                  ,,                           ) (_
             .-. -    _______                 ( |__|
            ()``; |==|_______)                .)|__|
            / ('        /|\                  (  |__|
        (  /  )        / | \                  . |__|
         \(_)_))      /  |  \                   |__|

                    ~ WAFW00F : v2.2.0 ~
    The Web Application Firewall Fingerprinting Toolkit

[*] Checking https://example.org
[+] The site https://example.org is behind Edgecast (Verizon Digital Media) WAF.
[~] Number of requests: 2
```



## 我该如何安装它？



以下应该可以解决问题：

```
python setup.py install
```



也可以在 Docker 容器中运行它。首先克隆此存储库并使用`docker build . -t wafw00f`.现在你可以运行`docker run --rm -it wafw00f https://example.com`

## 下载和安装使用

```shell
#下载
git clone https://github.com/EnableSecurity/wafw00f.git
#安装
python setup.py install
#使用:
wafw00f -l #显示所有防火墙
wafw00f <域名(需要携带http://或者https://)> #运行
#下载2
https://github.com/EnableSecurity/wafw00f/releases/tag/v2.2.0
```

