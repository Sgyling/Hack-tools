---
title: 54-敏感信息收集-burp插件
date: 2024-05-05 19:30:50
tags:
- 渗透工具推荐
categories:
- 工具推荐
- burp插件
---

# BurpAPI查找器

下载链接:https://github.com/shuanx/BurpAPIFinder/releases/download/v1.7/BurpAPIFinder.jar

[![img](https://camo.githubusercontent.com/aec62dc0b68de45205213e0a66854fd631127f8745f8a42d6340d3028a2cd8f7/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f417574686f722d536861756e2d626c7565)](https://camo.githubusercontent.com/aec62dc0b68de45205213e0a66854fd631127f8745f8a42d6340d3028a2cd8f7/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f417574686f722d536861756e2d626c7565) [![img](https://camo.githubusercontent.com/a0f773456863099bcf616a51290c7ea9df5f80dad5116aa42793f3f8cffd5ef7/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f4a444b2d392b2d79656c6c6f77)](https://camo.githubusercontent.com/a0f773456863099bcf616a51290c7ea9df5f80dad5116aa42793f3f8cffd5ef7/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f4a444b2d392b2d79656c6c6f77) [![img](https://camo.githubusercontent.com/58e5f7dfab13434e66cf8dc2eb3c2c17e8ef39e24748293fad85aba83a4be899/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f2545362538442541312545362542432538462545362539382541462545392539372541382545382538392542412545362539432541462d2545352542452538302545352542452538302545362539432538392545362538342538462545362538332542332545342542382538442545352538382542302545372539412538342545362538382539302545362539452539432d726564)](https://camo.githubusercontent.com/58e5f7dfab13434e66cf8dc2eb3c2c17e8ef39e24748293fad85aba83a4be899/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f2545362538442541312545362542432538462545362539382541462545392539372541382545382538392542412545362539432541462d2545352542452538302545352542452538302545362539432538392545362538342538462545362538332542332545342542382538442545352538382542302545372539412538342545362538382539302545362539452539432d726564)

> 在攻防演练过程中，我们通常会使用浏览器访问一些资产，但很多未授权/敏感信息/越权隐匿在访问接口过html、JS文件等，通过该Burp插件我们可以：
> 1、通过某些接口可以发现进行未授权/越权获取到所有的账号密码、私钥、凭证
> 2、发现通过某接口可以枚举用户信息、修改密码、用户创建接口
> 3、发现登陆后台网址
> 4、发现在html、JS中漏洞账号密码或者云主机的Access Key和SecretKey
> ...

[![图片.png](https://github.com/shuanx/BurpAPIFinder/raw/main/images/main.png)](https://github.com/shuanx/BurpAPIFinder/blob/main/images/main.png)

## 功能如下



> 如果有更好的建议或者期待使用的，点个免费的星星

- 网站提取的URL链接并解析JS文件中的URL链接
- 前段界面可自行定义铭感关键词、敏感url匹配
- 界面可配置的开启主动探测探测、铭感信息获取
- 集成主题攻防场景敏感信息的指纹库
  [![图片.png](https://github.com/shuanx/BurpAPIFinder/raw/main/images/config.png)](https://github.com/shuanx/BurpAPIFinder/blob/main/images/config.png)
- 集成HaE的敏感信息识别指纹
  [![图片.png](https://github.com/shuanx/BurpAPIFinder/raw/main/images/HaE.png)](https://github.com/shuanx/BurpAPIFinder/blob/main/images/HaE.png)
- 集成APIKit的敏感信息识别指纹
  [![图片.png](https://github.com/shuanx/BurpAPIFinder/raw/main/images/APIKit.png)](https://github.com/shuanx/BurpAPIFinder/blob/main/images/APIKit.png)
- 集成红薯的敏感信息识别指纹
  [![图片.png](https://github.com/shuanx/BurpAPIFinder/raw/main/images/sweetPotato.png)](https://github.com/shuanx/BurpAPIFinder/blob/main/images/sweetPotato.png)
