---
title: apk2url-自动提取apk中的ip和域名
date: 2024-2-24 16:14:46
tags:
- 渗透工具推荐
categories:
- 工具推荐
---



> 在渗透测试中，攻击者可以通过对app进行逆向分析。获取app访问的url或者IP。从而对IP进行攻击，本文为大家介绍的这款工具，可以方便的为你分析app中存在的url。

注意：本文仅供学习和研究，坚决反对一切危害网络安全的行为。

# 关于

`apk2url` 可以轻松地将 URL 和 IP 端点从 APK 文件提取到 .txt 输出。这适合红队、渗透测试人员和开发人员收集信息，以快速识别与应用程序关联的端点。与 APKleaks、MobSF和 AppInfoScanner 相比，apk2url 识别出的端点数量明显增多。apk2url 进行了重写和升级，增加了 IP 支持、更强的正则表达式、自动过滤和 Jadx 反编译。

# 安装

在`kali`中安装也很简单，我们只需执行下面命令。

```
git clone https://github.com/n0mi1k/apk2url
# 安装依赖工具
apt-get install apktool
apt-get install jadx
```

![图片](https://mmbiz.qpic.cn/mmbiz_png/Xb3L3wnAiatiaFhbmibudQviacyzJHltYPUzWKG35SjmkNuszcicIggl5FXj1lVXhkT9dxAva394icKiaN7OUmmkmjibWw/640?wx_fmt=png&from=appmsg&tp=wxpic&wxfrom=5&wx_lazy=1&wx_co=1)

# 测试

安装完成后，我们执行下面命令即可。

```
apk2url
```

![图片](https://mmbiz.qpic.cn/mmbiz_png/Xb3L3wnAiatiaFhbmibudQviacyzJHltYPUzOiattCed1R8ASPjYwM61ezKWq58BNvpcHFICt63icStvib1ib7R08e4ibNQ/640?wx_fmt=png&from=appmsg&tp=wxpic&wxfrom=5&wx_lazy=1&wx_co=1)接下来，我们随便下载一个app 进行测试。

![图片](https://mmbiz.qpic.cn/mmbiz_png/Xb3L3wnAiatiaFhbmibudQviacyzJHltYPUzicJoVJ4ZaVtiaOIicvZHdLl0a7xmDQ6Eq9Wx6RFOwia0g8oebT99n6WwuA/640?wx_fmt=png&from=appmsg&tp=wxpic&wxfrom=5&wx_lazy=1&wx_co=1)为了方便，app随便重命名。这里我改为了33.apk。

```
apk2url "33.apk"
```

![图片](https://mmbiz.qpic.cn/mmbiz_png/Xb3L3wnAiatiaFhbmibudQviacyzJHltYPUzJV9jJmQuewrzWjTOex2nVPeQRVUscL4CG8hao6hMFzXlzHgP65w7Rw/640?wx_fmt=png&from=appmsg&tp=wxpic&wxfrom=5&wx_lazy=1&wx_co=1)完成之后，在endpoints目录下会有txt文件。便是app中存在的url和IP地址。

![图片](https://mmbiz.qpic.cn/mmbiz_png/Xb3L3wnAiatiaFhbmibudQviacyzJHltYPUzAl2F9t0JRqxCatRtZGs84eQHVvhNfCrUOTTtatSLEdWcUQBHWquOBg/640?wx_fmt=png&from=appmsg&tp=wxpic&wxfrom=5&wx_lazy=1&wx_co=1)

# 应用

在实际中，我们通过对app逆向分析，得到app访问的网站或者IP地址，然后对IP或者域名进行端口扫描，从而进一步获取相关信息。