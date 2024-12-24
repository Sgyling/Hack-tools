---
title: DDOS工具推荐(需要肉鸡)
date: 2024-2-24 16:14:46
tags:
- 渗透工具推荐
categories:
- 工具推荐
---



分布式拒绝服务(DDoS:Distributed Denial of Service)攻击指借助于客户/服务器技术，将多个计算机联合起来作为攻击平台，对一个或多个目标发动DDoS攻击，从而成倍地提高拒绝服务攻击的威力。通常，攻击者使用一个偷窃帐号将DDoS主控程序安装在一个计算机上，在一个设定的时间主控程序将与大量代理程序通讯，代理程序已经被安装在网络上的许多计算机上。代理程序收到指令时就发动攻击。利用客户/服务器技术，主控程序能在几秒钟内激活成百上千次代理程序的运行。

### DDOs-Attack

#### 安装

```
git clone https://github.com/Ha3MrX/DDOs-Attack  
cd DDOs-Attack  
chmod +x ddos-attack.py  
python ddos-attack.py  
```

输入目标网址和端口便可完成 ddos![null](https://mmbiz.qpic.cn/mmbiz_jpg/Xb3L3wnAiatjLSiaoEp46uGFJOx7sKDArVGT7ghmEs2RoZAksbzvH5Mic0ic0VMLjmciapnB6HgfS8gM6yNicL6XwkmA/640?wx_fmt=jpeg)

### Slowloris

`Slowloris` 是 Github 上提供的免费开源工具。我们可以使用此工具执行拒绝服务攻击。这是一个用`python`编写的框架。此工具允许单台机器关闭另一台机器的 `Web` 服务器，它使用完全合法的 `HTTP`流量。它建立一个完整的 `TCP` 连接，然后在长期和定期的时间间隔只需要几百个请求。因此，该工具不需要花费大量流量来耗尽服务器上的可用连接。

### Slowloris 的用途：

`Slowloris` 向目标发送多个请求，因此会产生大量流量的僵尸网络。`Slowloris` 可用于对任何网络服务器执行 ddos 攻击。它是一个开源工具，因此您可以从 github 免费下载它。它使用完全合法的 HTTP 流量。可以在 Slowloris 的帮助下通过产生大量僵尸网络流量来执行拒绝服务攻击。

### 安装食用

```
git clone https://github.com/gkbrk/slowloris.git  
python3 slowloris .py（你的IP地址）-s 500
```

![null](https://mmbiz.qpic.cn/mmbiz_jpg/Xb3L3wnAiatjLSiaoEp46uGFJOx7sKDArVNyBnSbCqhkaQ7JIvPCWRIEWnaR8HMslC0S1wtjkrUmYzU9TMHdicfVg/640?wx_fmt=jpeg)

### Goldeneye

`Goldeneye`是GitHub 上提供的免费开源工具。我们可以使用此工具执行拒绝服务攻击。它是一个用 `.NET Core` 编写的框架。该工具提供了许多用于日常工作的基类和扩展。此工具允许单台机器关闭另一台机器的 Web 服务器，它使用完全合法的 HTTP 流量。它建立一个完整的 TCP 连接，然后在长期和定期的时间间隔只需要几百个请求。因此，该工具不需要使用大量流量来耗尽服务器上的可用连接。

### 特征

- Goldeneye 使用完全合法的 HTTP 流量。拒绝服务攻击可以在 Goldeneye 的帮助下通过产生大量僵尸网络流量来执行。
- Goldeneye 向目标发送多个请求，结果会产生大量流量的僵尸网络。
- Goldeneye 是一个开源工具，因此您可以从 GitHub 免费下载它。
- Goldeneye 可用于对任何网络服务器执行 ddos攻击。

### 安装食用

```
git clone https://github.com/jseidl/GoldenEye.git  
#示例 1使用 GoldenEye 工具对任意域进行 DDoS 攻击。  
./goldeneye.py https://www.google.com -s 1000  
#以“随机”模式发送流量  
./goldeneye.py http://192.168.0.233:80/ -s 10 -m 6  
```