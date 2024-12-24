---
title: 52-zmap-45分钟即可全网ipv4端口
date: 2024-04-30 19:40:38
tags:
- 渗透工具推荐
categories:
- 工具推荐
---

# ZMap：互联网扫描仪



[![构建状态](https://github.com/zmap/zmap/actions/workflows/cmake.yml/badge.svg)](https://github.com/zmap/zmap/actions/workflows/cmake.yml/badge.svg)

ZMap 是一款快速单数据包网络扫描仪，专为互联网范围内的网络调查而设计。在具有千兆位以太网连接的典型台式计算机上，ZMap 能够在 45 分钟内扫描单个端口上的整个公共 IPv4 地址空间。通过 10gigE 连接和[netmap](http://info.iet.unipi.it/~luigi/netmap/)或[PF_RING](http://www.ntop.org/products/packet-capture/pf_ring/)，ZMap 可以在 5 分钟内扫描 IPv4 地址空间。

ZMap 可在 GNU/Linux、Mac OS 和 BSD 上运行。 ZMap目前已经完全实现了TCP SYN扫描、ICMP、DNS查询、UPnP、BACNET的探测模块，并且可以发送大量的[UDP探测](https://github.com/zmap/zmap/blob/master/examples/udp-probes/README)。如果您希望进行更多复杂的扫描（例如，横幅抓取或 TLS 握手），请查看[ZGrab 2](https://github.com/zmap/zgrab2)，它是 ZMap 的姊妹项目，它执行有状态的应用程序层握手。

## 使用 ZMap



如果您以前没有使用过 ZMap，我们有一份分步入门[指南](https://github.com/zmap/zmap/wiki/Getting-Started-Guide)，详细介绍了如何执行基本扫描。有关 ZMap 所有选项和更高级功能的文档可以在我们的[GitHub Wiki](https://github.com/zmap/zmap/wiki)中找到。

如果您有疑问，请先查看我们的[常见问题解答](https://github.com/zmap/zmap/wiki/FAQ)。还有疑问吗？在[Github 讨论](https://github.com/zmap/zmap/discussions/categories/q-a)中询问社区。请不要针对使用或支持问题创建问题。

## 安装



ZMap 的最新稳定版本是版本[3.0.0](https://github.com/zmap/zmap/releases/tag/v3.0.0)，支持 Linux、macOS 和 BSD。 ZMap [4.1.0-RC2](https://github.com/zmap/zmap/releases/tag/v4.1.0-RC2)添加了对扫描多个端口的支持。

**从源代码构建 ZMap 的说明**可以在[INSTALL](https://github.com/zmap/zmap/blob/main/INSTALL.md)中找到。

blackarch中使用命令:

```shell
sudo pacman -Syu yay && sudo yay -S zmap
```

kali/parrot/debian系列安装命令:

```shell
sudo apt update && sudo apt install zmap
```

centos/redhat系列安装命令

```shell
sudo yum install -y zmap
```



## 建筑学



有关 ZMap 架构的更多信息以及与其他工具的比较可以在这两篇研究论文中找到：

- [ZMap：快速互联网范围扫描及其安全应用](https://zmap.io/paper.pdf)
- [Zippier ZMap：10 Gbps 的互联网范围扫描](https://jhalderm.com/pub/papers/zmap10gig-woot14.pdf)

如果您使用 ZMap 进行已发表的研究，请引用原始研究论文：

```
@inproceedings{durumeric2013zmap,
  title={{ZMap}: Fast Internet-wide scanning and its security applications},
  author={Durumeric, Zakir and Wustrow, Eric and Halderman, J Alex},
  booktitle={22nd USENIX Security Symposium},
  year={2013}
}
```



引用 ZMap 论文有助于我们跟踪研究社区内的 ZMap 使用情况，并为持续开发寻求资金。

## 许可和版权



ZMap 版权所有 2023 密歇根大学董事会

根据 Apache 许可证 2.0 版（“许可证”）获得许可；除非遵守许可证，否则您不得使用此文件。您可以在http://www.apache.org/licenses/LICENSE-2.0获取许可证副本

除非适用法律要求或书面同意，否则根据许可证分发的软件均按“原样”分发，不带任何明示或暗示的保证或条件。请参阅许可证，了解许可证下管理权限和限制的特定语言。

# 入门指南

[编辑](https://github.com/zmap/zmap/wiki/Getting-Started-Guide/_edit) [新一页](https://github.com/zmap/zmap/wiki/_new)

菲利普·斯蒂芬斯编辑了此页面3周前 · [19次修订](https://github.com/zmap/zmap/wiki/Getting-Started-Guide/_history)

边做边学最好？想要一些指导示例来演示使用 ZMap 进行基本扫描以入门吗？这是开始的地方！ ZMap 团队创建本指南是为了帮助新手习惯扫描，但如果仍有不清楚的地方，请随时在我们的[Github 讨论](https://github.com/zmap/zmap/discussions)中提问。

我们将介绍：

- 安装 ZMap
- 运行第一次扫描
- 定向输出
- 表现
- 其他扫描类型
- 默认阻止的子网
- 更多资源

## 安装



ZMap 可通过许多常见的包管理器获得，或者您也可以从源代码进行编译。完整说明可[在此处](https://github.com/zmap/zmap/blob/main/INSTALL.md)获取。要检查您是否已正确安装所有内容，请运行`zmap --version`.目前我们建议使用版本 4.1.0-RC2。

## ⚠️扫描速率警告



默认情况下，ZMap 将以您的网卡允许的速度进行扫描。由于 ZMap 直接组成以太网帧，因此它没有任何拥塞控制的概念（就像 TCP 默认情况下那样）。这有两个潜在的陷阱：

- *目标网络 DoS：*如果您以非常高的速率扫描小型子网（例如，单个组织），您很容易意外地对目标网络进行 DOS。我们建议*不要*以 1Gbps 或更快的速度运行扫描，除非您要扫描整个互联网。如果您扫描单个网络，则以接近 10Mbps 的速率运行会更成功。
- *源网络过载：*无论您扫描多少台主机，您都可能面临*源*网络（即用于扫描 Internet 的网络）过载的风险。许多仅通告*吞吐量*数字（例如 1Gbps）的网络设备无法使用最小大小的数据包来处理全速（因为这需要处理设备的理论每秒最大数据包速率。）

为了减少对目标网络的影响，ZMap 以随机顺序扫描范围内的 IP 地址。这意味着给定时间段内目标子网上的负载取决于 ZMap 的扫描速率和目标范围的大小。

![目标子网负载](https://private-user-images.githubusercontent.com/23459798/288224881-8642008a-df16-40ac-a7ec-d9389964e7b3.gif?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3MTQ0NjQ0OTEsIm5iZiI6MTcxNDQ2NDE5MSwicGF0aCI6Ii8yMzQ1OTc5OC8yODgyMjQ4ODEtODY0MjAwOGEtZGYxNi00MGFjLWE3ZWMtZDkzODk5NjRlN2IzLmdpZj9YLUFtei1BbGdvcml0aG09QVdTNC1ITUFDLVNIQTI1NiZYLUFtei1DcmVkZW50aWFsPUFLSUFWQ09EWUxTQTUzUFFLNFpBJTJGMjAyNDA0MzAlMkZ1cy1lYXN0LTElMkZzMyUyRmF3czRfcmVxdWVzdCZYLUFtei1EYXRlPTIwMjQwNDMwVDA4MDMxMVomWC1BbXotRXhwaXJlcz0zMDAmWC1BbXotU2lnbmF0dXJlPWMyM2U1MWQ0MDU4MWI0YmY1ZmM5ODk0YWIzNjA4ZTc5NmU1NTgzZDYxNDUzOTgyNDg2YmNjOGNiNTVlOTNlMTAmWC1BbXotU2lnbmVkSGVhZGVycz1ob3N0JmFjdG9yX2lkPTAma2V5X2lkPTAmcmVwb19pZD0wIn0.iQ0ZNY5fL4LEUqZ5yCrWVzKPK4naw-G0HqqzIqn4McU)

在上图中，正在扫描的不同子网由彩色线表示。因此，如果扫描的目标较大，“良好”的扫描速率可能会更快，因为负载更加分散。

这不仅关系到成为无私的互联网公民，目标网络超载可能会导致：

1. 网络管理员封锁你的IP
2. 路由器丢弃您的扫描数据包
3. 剥夺其他 LAN 用户的互联网带宽

\#1 和 #2 都会导致扫描结果不准确，因为无法区分扫描无响应是由于不存在主机、防火墙阻止您的 IP 还是由于途中丢失数据包。更多详细信息，请参阅“提高扫描精度”部分。

我们在给定示例中根据扫描目标的大小列出了我们认为合理的带宽/探头节流参数，但一个好的经验法则是以特定应用程序所需的最慢速率进行扫描。

## ⚠️线程警告



ZMap CLI 提供了使用 来设置发送线程数量的功能`-T number_of_threads`。还会创建用于接收数据包和监视扫描进度的线程，因此 ZMap 所需的线程数就是`2 + T`其中 T 是您设置的线程数（默认为 4，除非主机的核心数 < 4）。

作为一般规则，我们建议坚持 <= 8 个发送线程，因为我们发现在此之后性能趋于稳定。此外，使用非常大的线程数 (> 32) 不会*提高*扫描性能，并且可能会导致您遇到数据包发送问题或遇到数据包丢失，从而导致扫描结果不准确。

需要明确的是，创建比机器上的内核数量更多的线程的好处为零。发送线程都尽可能快地发送，并且增加线程超过核心数量将导致核心争用。

提示

与扫描速率一样，我们建议从较低的速率开始，然后根据需要增加，以确保扫描准确并最大限度地减少主机和网络压力。

## 运行您的第一次扫描



让我们开始第一次扫描。我们将通过端口 80 向`TCP SYN`子网中的所有 IP 发送一个数据包`171.67.70.0/23`，数据包发送速率为每秒 128 个数据包。如果该 IP/端口对上有任何运行，我们应该会收到一个`SYN ACK`数据包作为回复。

运行以下命令：

```
sudo zmap -p 80 -r 128 171.67.70.0/23
```

您应该得到一些类似于以下内容的输出：

```
171.67.71.204
171.67.71.128
171.67.70.245
171.67.71.191
171.67.71.186
171.67.71.202
171.67.70.240
171.67.70.242
171.67.71.192
 0:05 42% (7s left); send: 512 done (127 p/s avg); recv: 91 17 p/s (17 p/s avg); drops: 0 p/s (0 p/s avg); hitrate: 17.77%
 0:06 50% (6s left); send: 512 done (127 p/s avg); recv: 91 0 p/s (15 p/s avg); drops: 0 p/s (0 p/s avg); hitrate: 17.77%
 0:07 59% (5s left); send: 512 done (127 p/s avg); recv: 91 0 p/s (12 p/s avg); drops: 0 p/s (0 p/s avg); hitrate: 17.77%
 0:08 67% (4s left); send: 512 done (127 p/s avg); recv: 91 0 p/s (11 p/s avg); drops: 0 p/s (0 p/s avg); hitrate: 17.77%
 0:09 75% (3s left); send: 512 done (127 p/s avg); recv: 91 0 p/s (10 p/s avg); drops: 0 p/s (0 p/s avg); hitrate: 17.77%
 0:10 84% (2s left); send: 512 done (127 p/s avg); recv: 91 0 p/s (9 p/s avg); drops: 0 p/s (0 p/s avg); hitrate: 17.77%
 0:11 92% (1s left); send: 512 done (127 p/s avg); recv: 91 0 p/s (8 p/s avg); drops: 0 p/s (0 p/s avg); hitrate: 17.77%
Dec 05 22:29:12.352 [INFO] zmap: completed
```



> **故障排除**
>
> ZMap 非常擅长告诉您它遇到的任何问题。一些常见的包括：
>
> 1. 您的用户可能无权捕获默认接口上的流量，除非您使用`sudo`.
> 2. 如果有多个网络适配器可供选择，您可能需要指定您的 MAC 地址。如果您看到类似的情况，请`--source-mac=XX:XX:XX:XX:XX:XX`在您运行的任何 ZMap 命令中使用该标志。
> 3. 第一次运行 ZMap 时，ZMap 可能会提到`zmap: could not detect GW MAC address...`.按照其指示运行命令`curl zmap.io`，这应该初始化 GW MAC 地址，以便 ZMap 可以正确路由流量。
>
> 如果您按照说明操作，使用的是受支持的操作系统，但*仍然遇到问题，请通过*[Github 讨论](https://github.com/zmap/zmap/discussions)与我们联系！

我们可以在这里看到两种类型的输出：

1. 响应我们的`SYN`数据包的 IP
2. 每秒打印详细的扫描状态（完成百分比、剩余秒数、发送/接收速率……）

我们确实说过“输出类似于”，这提出了一个关键点，您的结果可能会略有不同。可访问 Internet 的主机可以在扫描之间打开/离线，并且您的硬件可能比我们正在运行的硬件更快/更慢。

将所有输出显示在一个屏幕中固然很好，但您可能希望将 IP/端口命中和状态信息分开。

### 输出



`-o`or标志`--output-file`允许我们指定 IP/端口对命中的位置。尝试`-o`像这样使用该标志：

```
sudo zmap -p 80 -o "output.csv" -r 128 171.67.70.0/23
```



您应该得到类似于以下内容的输出：

```
Dec 05 21:52:43.347 [INFO] zmap: By default, ZMap will output the unique IP addresses of hosts that respond successfully (e.g., SYN-ACK packet). This is equivalent to running ZMap with the following flags: --output-module=csv --output-fields=saddr --output-filter='success=1 && repeat=0' --no-header-row. If you want all responses, explicitly set an output module or set --output-filter="".
Dec 05 21:52:43.348 [INFO] dedup: Response deduplication method is full
Dec 05 21:52:43.406 [INFO] recv: duplicate responses will be excluded from output
Dec 05 21:52:43.406 [INFO] recv: unsuccessful responses will be excluded from output
 0:00 0%; send: 1 1 p/s (22 p/s avg); recv: 0 0 p/s (0 p/s avg); drops: 0 p/s (0 p/s avg); hitrate: 0.00%
 0:00 0%; send: 1 0 p/s (22 p/s avg); recv: 0 0 p/s (0 p/s avg); drops: 0 p/s (0 p/s avg); hitrate: 0.00%
 0:01 9%; send: 134 133 p/s (128 p/s avg); recv: 22 22 p/s (21 p/s avg); drops: 0 p/s (0 p/s avg); hitrate: 16.42%
 0:02 17%; send: 263 129 p/s (128 p/s avg); recv: 22 0 p/s (10 p/s avg); drops: 0 p/s (0 p/s avg); hitrate: 8.37%
 0:03 25%; send: 391 128 p/s (128 p/s avg); recv: 51 29 p/s (16 p/s avg); drops: 0 p/s (0 p/s avg); hitrate: 13.04%
 0:04 34%; send: 512 done (128 p/s avg); recv: 74 23 p/s (18 p/s avg); drops: 0 p/s (0 p/s avg); hitrate: 14.45%
 0:05 42% (7s left); send: 512 done (128 p/s avg); recv: 90 16 p/s (17 p/s avg); drops: 0 p/s (0 p/s avg); hitrate: 17.58%
 0:06 50% (6s left); send: 512 done (128 p/s avg); recv: 90 0 p/s (14 p/s avg); drops: 0 p/s (0 p/s avg); hitrate: 17.58%
 0:07 59% (5s left); send: 512 done (128 p/s avg); recv: 90 0 p/s (12 p/s avg); drops: 0 p/s (0 p/s avg); hitrate: 17.58%
 0:08 67% (4s left); send: 512 done (128 p/s avg); recv: 90 0 p/s (11 p/s avg); drops: 0 p/s (0 p/s avg); hitrate: 17.58%
 0:09 75% (3s left); send: 512 done (128 p/s avg); recv: 90 0 p/s (9 p/s avg); drops: 0 p/s (0 p/s avg); hitrate: 17.58%
 0:10 84% (2s left); send: 512 done (128 p/s avg); recv: 90 0 p/s (8 p/s avg); drops: 0 p/s (0 p/s avg); hitrate: 17.58%
 0:11 92% (1s left); send: 512 done (128 p/s avg); recv: 90 0 p/s (8 p/s avg); drops: 0 p/s (0 p/s avg); hitrate: 17.58%
Dec 05 21:52:55.412 [INFO] zmap: completed
```



新`output.csv`文件（位于运行扫描的文件夹中）现在应该包含在端口 80 上响应的所有 IP，并且我们`stdout`只会向我们显示扫描的状态，很好！

## 表现



ZMap 的一大卖点是它调查大型子网的速度。在千兆位以太网连接上，可以在 40 分钟内勘察单个端口上的整个 IPv4 空间！让我们讨论一下影响性能的各种因素。为此，我们需要更多地了解 ZMap 的运作方式。

### 发送/接收解耦



为了获得如此高性能，ZMap 在设计上是无状态的。这意味着一个/多个发送线程发送数据包，一个/多个接收线程记录任何回复，但没有线程间通信。正是由于缺乏通信/锁定，ZMap 才具有如此高的性能。它还有助于解释我们上面看到的输出。子网 ( `/23`) 有 512 个 IP，加上每秒 128 个数据包的扫描速率 ( `p/s`)，探测数据包（`SYN`默认为 TCP 数据包）的发送在 4 秒内结束。

```
 0:04 34%; send: 512 done (128 p/s avg); recv: 74 23 p/s (18 p/s avg); drops: 0 p/s (0 p/s avg); hitrate: 14.45%
```



默认情况下，接收线程在发送线程完成发送后等待 8 秒以等待任何`SYN ACK`数据包。我们发现 8 秒在等待`SYN ACK`来自远程主机的潜在慢速和等待时间不长以致回报递减之间取得了良好的平衡。根据您的需要，您可能希望使用 修改此值`--cooldown-time=10`。这将迫使接收线程等待 10 秒以接收任何落后的数据包。

请注意，在我们上面捕获的输出中，命中率在 后没有增加（至少在百分之一的粒度上）`0:05`，因此请记住收益递减。

### 提高发送性能



我们在上面的部分中介绍了接收线程将等待的恒定时间`SYN ACK`，`--cooldown-time`但这并没有解决发送的速率`SYN`。在较大的扫描中，这是将主导扫描运行时间的组件。

有了足够大的目标范围，就不用担心目标子网过载。为了进一步提高性能，我们需要添加更多线程。使用该`--sender-threads=N`标志来执行此操作：

#### **1 线程发送速率**

```
sudo zmap -p 80 -o "output.csv" -B 1G --sender-threads=1 171.67.70.0/2
```

```
 0:00 0%; send: 211 1 p/s (3.69 Kp/s avg); recv: 0 0 p/s (0 p/s avg); drops: 0 p/s (0 p/s avg); hitrate: 0.00%
 0:00 0%; send: 400 274 Kp/s (6.92 Kp/s avg); recv: 0 0 p/s (0 p/s avg); drops: 0 p/s (0 p/s avg); hitrate: 0.00%
 0:01 0%; send: 505473 505 Kp/s (478 Kp/s avg); recv: 5176 5.17 Kp/s (4.89 Kp/s avg); drops: 0 p/s (0 p/s avg); hitrate: 1.02%
 0:02 0%; send: 1113056 607 Kp/s (541 Kp/s avg); recv: 12962 7.78 Kp/s (6.30 Kp/s avg); drops: 0 p/s (0 p/s avg); hitrate: 1.16%
 0:03 0%; send: 1726996 614 Kp/s (565 Kp/s avg); recv: 20562 7.60 Kp/s (6.72 Kp/s avg); drops: 0 p/s (0 p/s avg); hitrate: 1.19%
 0:04 0%; send: 2335833 609 Kp/s (575 Kp/s avg); recv: 28571 8.01 Kp/s (7.04 Kp/s avg); drops: 0 p/s (0 p/s avg); hitrate: 1.22%
 0:05 0% (30m left); send: 2943829 608 Kp/s (582 Kp/s avg); recv: 36420 7.85 Kp/s (7.20 Kp/s avg); drops: 0 p/s (0 p/s avg); hitrate: 1.24%
 0:06 0% (30m left); send: 3550851 607 Kp/s (586 Kp/s avg); recv: 44122 7.70 Kp/s (7.28 Kp/s avg); drops: 0 p/s (0 p/s avg); hitrate: 1.24%
 0:07 0% (30m left); send: 4156961 606 Kp/s (589 Kp/s avg); recv: 52047 7.92 Kp/s (7.37 Kp/s avg); drops: 0 p/s (0 p/s avg); hitrate: 1.25%
 0:08 0% (30m left); send: 4756743 600 Kp/s (590 Kp/s avg); recv: 59834 7.79 Kp/s (7.42 Kp/s avg); drops: 0 p/s (0 p/s avg); hitrate: 1.26%
 ...
```



#### **4线程发送速率**



```
sudo zmap -p 80 -o "output.csv" -B 1G --sender-threads=4 171.67.70.0/2
```



```
 0:00 0%; send: 360 1 p/s (5.31 Kp/s avg); recv: 0 0 p/s (0 p/s avg); drops: 0 p/s (0 p/s avg); hitrate: 0.00%
 0:00 0%; send: 586 388 Kp/s (8.58 Kp/s avg); recv: 0 0 p/s (0 p/s avg); drops: 0 p/s (0 p/s avg); hitrate: 0.00%
 0:01 0%; send: 1125395 1.12 Mp/s (1.05 Mp/s avg); recv: 11804 11.8 Kp/s (11.0 Kp/s avg); drops: 0 p/s (0 p/s avg); hitrate: 1.05%
 0:02 0%; send: 2401617 1.28 Mp/s (1.16 Mp/s avg); recv: 28248 16.4 Kp/s (13.7 Kp/s avg); drops: 0 p/s (0 p/s avg); hitrate: 1.18%
 0:03 0%; send: 3667077 1.27 Mp/s (1.19 Mp/s avg); recv: 44305 16.1 Kp/s (14.4 Kp/s avg); drops: 0 p/s (0 p/s avg); hitrate: 1.21%
 0:04 0%; send: 4932812 1.27 Mp/s (1.21 Mp/s avg); recv: 60886 16.6 Kp/s (15.0 Kp/s avg); drops: 0 p/s (0 p/s avg); hitrate: 1.23%
 0:05 1% (14m left); send: 6193698 1.26 Mp/s (1.22 Mp/s avg); recv: 77131 16.2 Kp/s (15.2 Kp/s avg); drops: 0 p/s (0 p/s avg); hitrate: 1.25%
 0:06 1% (14m left); send: 7452466 1.26 Mp/s (1.23 Mp/s avg); recv: 93092 16.0 Kp/s (15.3 Kp/s avg); drops: 0 p/s (0 p/s avg); hitrate: 1.25%
 0:07 1% (14m left); send: 8713445 1.26 Mp/s (1.23 Mp/s avg); recv: 109494 16.4 Kp/s (15.5 Kp/s avg); drops: 0 p/s (0 p/s avg); hitrate: 1.26%
 0:08 1% (14m left); send: 9970806 1.26 Mp/s (1.24 Mp/s avg); recv: 125807 16.3 Kp/s (15.6 Kp/s avg); drops: 0 p/s (0 p/s avg); hitrate: 1.26%
 ...
```



我们可以看到，增加发送线程的数量提高了数据包发送速率，因此减少了运行时间（预期运行时间为 30 分钟，而预期运行时间为 14 分钟）。对于大多数用途，单个线程可能就足够了，但如果您需要提高性能、拥有高带宽上行链路，并且要扫描大部分 IPv4 空间，则可以使用该线程。

## 提高扫描精度



ZMap 将以 的速率发送数据包`min(max rate your Network Interface Card (NIC) can sustain, the rate you specify with CLI flags)`。该速率*可能*高于您的 LAN 或目标子网的处理能力，从而导致数据包丢失和扫描结果不精确。

删除的`SYN`或`SYN ACK`将在 ZMap 中显示为相同，就好像根本不存在主机一样。由于 ZMap 直接组成以太网帧，因此无法保证交付。考虑到这一点，您可能希望降低`--rate=pps`或`--bandwidth=bps`确定您的命中率是否保持一致（表明您没有看到大量丢包/漏报）。另一种选择是增加`--probes=N (default = 1)`. “探测”是 ZMap 术语，指的是 ZMap 发送到潜在主机的数据包，您可以对每个 IP/端口对使用多个探测来尝试解决数据包丢失的情况。

### 探测和重复数据删除



如上一节所述，您可能希望增加计数`--probes=N`以减少扫描中出现假阴性的可能性。然而，由于 ZMap 是无状态的，它如何防止给定 IP if`--probes=N`和 的多个日志`N > 1`？

例如：

```
sudo zmap -p 80 --probes=5 -B 100M --dedup-method=none 171.67.70.0/10
```



```
 0:00 0%; send: 42 1 p/s (821 p/s avg); recv: 0 0 p/s (0 p/s avg); drops: 0 p/s (0 p/s avg); hitrate: 0.00%
171.67.224.74
171.67.224.74
171.67.224.74
171.67.224.74
171.67.224.74
171.67.35.131
171.67.35.131
171.67.35.131
171.67.35.131
171.67.35.131
171.67.7.61
171.67.7.61
171.67.7.61
171.67.7.61
171.67.7.61
...
```



每次响应探测时，都会记录下来。默认情况下，`--dedup-method=window`窗口大小为1M。这意味着 ZMap 将跟踪内存中最后 1M 探测响应，以避免多次记录命中。您可以使用`--dedup-method=full`，但要了解内存需求将随着扫描空间的大小而增加。

> 注意：我们已经说过 ZMap 是无状态的，但在这里我们似乎与该声明相矛盾，提到存储最后 1M 探测响应😄。 ZMap 在发送线程和接收线程之间是无状态的，但 ZMap 的接收线程可以保存状态以免记录重复项。

### 预期最大发送速率



在我们的实验室环境中，具有 1 Gbit 有线以太网的现成 Ubuntu 虚拟机每秒可处理多达 1.3-145 万个数据包。使用无线连接、低端硬件或 LAN 带宽争用都可能对您的性能产生负面影响。

## 其他扫描



### 获取 N 个可达主机



在前面的示例 ( `sudo zmap -p 80 -o "output.csv" -B 1G --sender-threads=4 171.67.70.0/2`) 中，我们使用了给定的子网。然而，也许您只想在 IPv4 空间中获得 10 个可访问的主机。您可以使用`--max-results=10`或`-N 10`

```
sudo zmap -p 80 -B 100M -N 10
```



```
 0:00 0%; send: 0 0 p/s (0 p/s avg); recv: 0 0 p/s (0 p/s avg); drops: 0 p/s (0 p/s avg); hitrate: 0.00%
 0:00 0%; send: 0 0 p/s (0 p/s avg); recv: 0 0 p/s (0 p/s avg); drops: 0 p/s (0 p/s avg); hitrate: 0.00%
104.252.154.129
207.241.227.232
34.102.143.17
185.227.252.87
88.218.93.178
206.54.174.210
50.3.14.225
34.43.9.190
184.84.170.239
154.37.15.2
Dec 05 22:19:22.112 [INFO] zmap: completed
```



### 再现性和随机搜索



再次运行上面的命令...

```
sudo zmap -p 80 -B 100M -N 10
```



```
 0:00 0%; send: 0 0 p/s (0 p/s avg); recv: 0 0 p/s (0 p/s avg); drops: 0 p/s (0 p/s avg); hitrate: 0.00%
 0:00 0%; send: 17 62.7 Kp/s (305 p/s avg); recv: 0 0 p/s (0 p/s avg); drops: 0 p/s (0 p/s avg); hitrate: 0.00%
206.2.159.123
47.251.50.46
144.49.230.210
34.220.245.127
34.160.175.57
216.180.232.245
20.94.252.204
172.65.73.3
38.173.125.213
172.67.201.97
Dec 05 22:33:37.695 [INFO] zmap: completed
```



这很有趣，我们得到了一组完全不同的 IP！当您定义给定的搜索空间时，ZMap 会随机而不是线性地扫描它。当我们想要像之前的扫描一样搜索整个搜索空间时，这并不是什么大问题，因为我们最终仍然会得到相同的（无序的）结果集。然而，在这种情况下，ZMap 在给定搜索空间中找到前 10 个命中时返回。 ZMap 的随机搜索模式导致输出出现这种差异。

为什么要随机搜索？发送端和接收端都可能发生资源争用。我们希望尽可能分散放置在接收子网上的负载，因此通过随机搜索搜索空间，我们可以分散在给定时间放置在给定网络上的负载。

您可能希望扫描顺序具有可重复性，因此您可以使用 来`--seed=n`确保后续运行使用相同的顺序。

### 多个端口



> ZMap v.4.0.0 中添加

您可以扫描多个端口。在这种情况下，ZMap 将向`SYN`每个 IP/端口对发送 TCP数据包。

```
sudo zmap -p 22,80 -B 100M -N 10 171.67.70.0/10
```



```
 0:00 0%; send: 824 1 p/s (10.7 Kp/s avg); recv: 0 0 p/s (0 p/s avg); drops: 0 p/s (0 p/s avg); hitrate: 0.00%
 0:00 0%; send: 1163 623 Kp/s (15.0 Kp/s avg); recv: 0 0 p/s (0 p/s avg); drops: 0 p/s (0 p/s avg); hitrate: 0.00%
125.6.184.89,80
125.6.189.199,80
125.62.85.202,22
125.62.86.43,22
125.103.118.1,22
125.135.32.198,80
125.136.125.185,80
125.140.210.154,80
125.143.130.34,80
125.137.239.225,80
Nov 28 23:15:06.878 [INFO] zmap: completed
```



### 多个子网



您也可以使用同一扫描来扫描多个子网。

```
sudo zmap -p 80 10.0.0.0/8 192.168.0.0/16 (scan both subnets on TCP/80)
```



## ZMap 的配置文件



默认情况下，ZMap 不会扫描*整个*IPv4 空间。有两个文件包含默认情况下不扫描的子网。您可以更改这些文件以显式扫描这些范围，但是在每种情况下，默认情况下不扫描它们都是有原因的。

### `blocklist.conf`



`blocklist.conf`包括 RFC 定义的子网（例如多播、保留/未分配的[RFC 1918 ，默认情况下不扫描这些子网。如果您不希望扫描某些 IP/子网，可以添加到此文件。](https://tools.ietf.org/html/rfc1918)

### `zmap.conf`



如果您发现自己指定了某些设置，例如每次运行 ZMap 时的最大带宽或黑名单文件，您可以在其中指定这些设置`/etc/zmap/zmap.conf`或使用自定义配置文件。

### 在您的安装中查找配置文件



*您通常*可以在安装中找到这些文件，位置为`/etc/zmap/...conf`。

如果您使用包管理器安装 ZMap，它可能已将配置文件安装在其自己的位置。

例如，`homebrew`将配置文件安装在`/opt/homebrew/etc/zmap/`.如果您无法找到这些文件，请尝试`sudo find . -name "blocklist.conf" -maxdepth 5`在安装 ZMap 后从根目录运行。
