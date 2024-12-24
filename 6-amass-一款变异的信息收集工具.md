---
title: amass-一款变异又有维护的信息收集工具!
date: 2024-3-4 18:44:46
tags:
- 渗透工具推荐
categories:
- 工具推荐
---



OWASP Amass 项目使用开源信息收集和主动侦察技术来执行攻击面的网络映射和外部资产发现。

### github链接:

https://github.com/owasp-amass/amass?tab=readme-ov-file

### 下载链接:

https://github.com/owasp-amass/amass/releases/tag/v4.2.0



**使用的信息收集技术：**

| 技术     | 数据源                                                       |
| -------- | ------------------------------------------------------------ |
| 蜜蜂     | 360PassiveDNS、Ahrefs、AnubisDB、BeVigil、BinaryEdge、BufferOver、BuiltWith、C99、Chaos、CIRCL、DNSDB、DNSRepo、Deepinfo、Detectify、FOFA、FullHunt、GitHub、GitLab、GrepApp、Greynoise、HackerTarget、Hunter、IntelX、LeakIX、Maltiverse、 Mnemonic、Netlas、Pastebin、PassiveTotal、PentestTools、Pulsedive、Quake、SOCRadar、Searchcode、Shodan、Spamhaus、Sublist3rAPI、SubdomainCenter、ThreatBook、ThreatMiner、URLScan、VirusTotal、Yandex、ZETAlytics、ZoomEye |
| 证书     | 主动拉取（可选）、Censys、CertCentral、CertSpotter、Crtsh、Digitorus、FacebookCT |
| 域名系统 | 暴力破解、反向 DNS 扫描、NSEC 区域行走、区域传输、FQDN 更改/排列、FQDN 基于相似性的猜测 |
| 路由     | ASNLookup、BGPTools、BGPView、BigDataCloud、IPdata、IPinfo、RADb、Robtex、ShadowServer、TeamCymru |
| 刮痧     | 滥用IPDB、Ask、百度、Bing、CSP 标头、DNSDumpster、DNSHistory、DNSSpy、DuckDuckGo、Gists、Google、HackerOne、HyperStat、PKey、RapidDNS、Riddler、Searx、SiteDossier、雅虎 |
| 网络档案 | Arquivo、CommonCrawl、HAW、PublicWWW、UKWebArchive、Wayback  |
| 谁是     | AlienVault、AskDNS、DNSlytics、ONYPHE、SecurityTrails、SpyOnWeb、WhoisXMLAPI |

------

## 安装

## [![去版本](https://camo.githubusercontent.com/4004c7b3350134d3d4f559db3c9820b398cbf16f069fad8a55a2f088e111e0fb/68747470733a2f2f696d672e736869656c64732e696f2f6769746875622f676f2d6d6f642f676f2d76657273696f6e2f6f776173702d616d6173732f616d617373)](https://golang.org/dl/) [![Docker 镜像](https://camo.githubusercontent.com/15ae103c2a653f12d2862dd74b5b9f78df79baa14dc16a3bbc04460d61705db8/68747470733a2f2f696d672e736869656c64732e696f2f646f636b65722f70756c6c732f6361666669782f616d6173732e737667)](https://hub.docker.com/r/caffix/amass) [![GitHub 下载](https://camo.githubusercontent.com/6c4e2b61a93f20d608d6e54b59081cbc8bdb5471b4aa050c4b70459c030be6c6/68747470733a2f2f696d672e736869656c64732e696f2f6769746875622f646f776e6c6f6164732f6f776173702d616d6173732f616d6173732f6c61746573742f746f74616c2e737667)](https://github.com/owasp-amass/amass/releases/latest)



> [您可以在安装指南](https://github.com/owasp-amass/amass/blob/master/doc/install.md)中找到一些其他安装变体。

### 预建包



1. 只需解压[包即可](https://github.com/owasp-amass/amass/releases/latest)
2. 将预编译的二进制文件放入您的路径中
3. 开始使用 OWASP Amass！

#### 自制



```
brew tap owasp-amass/amass
brew install amass
```



### Docker容器



1. 安装[Docker](https://www.docker.com/)
2. 通过运行拉取 Docker 镜像`docker pull caffix/amass`
3. 跑步`docker run -v OUTPUT_DIR_PATH:/.config/amass/ caffix/amass enum -d example.com`

卷参数允许 Amass 图形数据库在执行和输出文件之间保留以在主机系统上访问。Volume 选项的第一个字段（冒号左侧）是 Docker 外部的 amass 输出目录，而第二个字段是 Docker 内部的路径，amass 将在其中写入输出文件。

### 从源头



1. 安装[Go](https://golang.org/doc/install)并设置您的 Go 工作区
2. 通过运行下载 OWASP Amass`go install -v github.com/owasp-amass/amass/v4/...@master`
3. 此时，二进制文件应该位于`$GOPATH/bin`

## 文档

## [![戈多克](https://camo.githubusercontent.com/343f881605faf63ad5d6889130b47fa935cc77d5b7841927dbb763466a1bff03/68747470733a2f2f706b672e676f2e6465762f62616467652f6769746875622e636f6d2f6f776173702d616d6173732f616d6173732f76343f75746d5f736f757263653d676f646f63)](https://pkg.go.dev/github.com/owasp-amass/amass/v4)



使用[安装指南](https://github.com/owasp-amass/amass/blob/master/doc/install.md)开始。

请参阅[用户指南](https://github.com/owasp-amass/amass/blob/master/doc/user_guide.md)以获取更多信息。

有关示例用法，请参阅[教程。](https://github.com/owasp-amass/amass/blob/master/doc/tutorial.md)

请参阅[Amass 脚本引擎手册，](https://github.com/owasp-amass/amass/blob/master/doc/scripting.md)以更好地控制枚举过程。

## 介绍



无论您是渗透测试员、审计员、安全研究人员还是 CISO/IT 经理，您都可能有几个合理的理由来绘制组织的外部攻击面。此过程也称为侦察或信息收集。

[OWASP Amass 项目](https://owasp.org/www-project-amass/) (Amass) 可以在很大程度上根据您的要求提供帮助。在这篇博文中，我们的目标是演示如何使用 Amass 来发现组织的大部分外部暴露资产。

重点将是执行连续的子域发现练习。我们已将这篇博文分为不同的部分，以便您更轻松地掌握 Amass 的各种功能。应该注意的是，可能存在未映射到域的资产，您需要采用其他技术来发现它们，例如在组织拥有的 IP 范围上运行网络扫描。虽然我们不会完全演示如何使用 Amass 提供的所有功能，但我们希望这篇博客能够涵盖足够的内容，让您能够快速掌握该收集工具。

## 为什么选择 OWASP Amass？



有大量开源工具和软件可用于枚举子域、自治系统编号 (ASN) 以及组织拥有的其他资产。尽管这些工具中的大多数在利用特定方法方面都非常出色，但它们并不总是得到积极维护和更新以跟上最新的技术和方法。说实话，大多数可用的工具都不完整，仅仅依赖这些工具可能会产生错误的安全感或导致丢失易受攻击的资产。现实情况是，子域名现在可以在任何地方公开，例如社交媒体、Pastebin、源代码存储库、HTTP 标头等。

Amass 得到 OWASP 的支持，这应该会为结果带来威望和信心。它得到积极维护，并且可能会得到长期支持，这意味着未来的任何错误都将得到解决。此外，Amass 的采用率很高，这可能意味着更好的数据一致性以及与其他工具的集成。因此，它可以构成一个更好、更值得信赖的工具，用于证明概念和参与。这可以更轻松地说服您的客户或经理使用它来定期绘制组织的攻击面。

还有许多更多的技术原因，我们将在下面解释并稍后更详细地演示：

- 带有 3 个子命令，换句话说就是函数：
  - amass intel -- 发现枚举的目标命名空间
  - amass enum -- 执行枚举和网络映射
  - amass db -- 操作 Amass 图形数据库
- 在某些情况下，Amass 的子命令可以结合使用，这可以让您创建执行多个 Amass 操作的脚本。
- 在撰写本文时，作为其子域发现和信息收集技术的一部分，支持超过 80 个来源，例如 API 和网站。可以使用以下命令列出这些：
  - 大量枚举列表
  - `AlienVault,ArchiveIt,Arquivo,Ask,Baidu,BinaryEdge,Bing,BufferOver,Censys,CertSpotter,CIRCL,CommonCrawl,Crtsh,[...],VirusTotal,Wayback,WhoisXML,Yahoo`（完整列表[在这里](https://github.com/owasp-amass/amass)）
- 它采用各种信息收集技术进行 DNS 枚举
  - 使用域名单词列表和更改单词列表对子域进行暴力破解
  - 通过读取 SSL/TLS 证书、执行 DNS 区域传输或检查证书透明度日志来识别子域
  - 已识别域的递归子域发现
  - 用于暴力破解子域的 Hashcat 式掩码（如果您有有关命名约定等的内部信息，这可能非常有用）
- 它可以使用配置文件进行配置，这使得维护、使用或与脚本集成变得容易

最后，我们不会在这篇博文中详细介绍安装 Amass，但如果您有兴趣，可以通过多种方式进行安装。如果您有正确配置的 Golang 环境 (Go >= 1.20)，则可以从源代码进行编译，使用 Docker 运行它，或者如果您的发行版有可用的包，则可以将其安装为包。详细的安装说明可[在此处](https://github.com/owasp-amass/amass/blob/master/doc/install.md)获取。

## 积聚英特尔



Amass intel 子命令或模块（如果您需要）可以帮助收集有关组织的开源情报，并允许您找到与该组织相关的更多根域名。要查看此子命令的可用选项，只需在终端中键入：

```
$ amass intel
[...]
Usage: amass intel [options] [-whois -d DOMAIN] [-addr ADDR -asn ASN -cidr CIDR]
  -active
        Attempt certificate name grabs
  -addr value
        IPs and ranges (192.168.1.1-254) separated by commas
  -asn value
        ASNs separated by commas (can be used multiple times)
[...]
```



此时可能值得注意的是，Amass 的另一个巨大好处是所有子命令都试图保持参数的一致性。

默认情况下，该子命令将使用许多信息收集技术和数据源（例如 WHOIS），以便获取组织拥有的情报和父域，除非在 Amass 的配置文件中明确禁用这些技术和数据源。[GitHub 配置存储库上](https://github.com/owasp-amass/config/blob/master/examples/config.yaml)提供了示例 Amass 配置文件。

```
$ amass intel -d owasp.org -whois
appseceu.com
owasp.com
appsecasiapac.com
appsecnorthamerica.com
appsecus.com
[...]
owasp.org
appsecapac.com
appsecla.org
[...]
```



您还可以通过手动浏览数据源来确认上面的一些结果。在下面的屏幕截图中，我们对“OWASP Foundation”执行了反向 WHOIS 搜索，并发现了类似的域：

https://viewdns.info/reversewhois/?q=OWASP+Foundation [![OWASP Amass 信息收集技术](https://github.com/owasp-amass/amass/raw/master/images/tutorial/viewdnsinfo_example.png?raw=true)](https://github.com/owasp-amass/amass/blob/master/images/tutorial/viewdnsinfo_example.png?raw=true)

当使用 amass intel 执行搜索时，您始终可以使用更多配置选项来运行它，例如“-active”参数，它将尝试区域传输并主动扫描以获取 SSL/TLS 证书以提取信息。与任何参与一样，确保您有权对目标执行主动搜索。

此时值得注意的是，某些配置标志将无法与其他配置标志一起使用，在这种情况下，Amass 将简单地忽略它们。

Amass 的调查结果并不总是准确的，这可能有多种原因，例如，Amass 使用的数据源可能不一致或不是最新的。Amass 尝试使用 DNS 查询进一步验证信息，未来将实施更多验证技术。尽管 Amass 做得很好，但用户仍然应该对看似与目标无关的结果进行进一步的验证检查。这可以使用多种方法来执行，例如：

- 使用实用程序来解析域（例如 dig、nslookup）
- 执行 WHOIS 查询以确认组织详细信息
- 在搜索引擎上的搜索结果，例如父域

您还可以使用 Amass 查找组织名称，它可以返回分配给目标的 ASN ID，示例如下所示(已经测试中文)：

```
$ amass intel -org 'Example Ltd'
111111, MAIN_PRODUCT -- Example Ltd
222222, SECONDARY_PRODUCT - Example Ltd
[...]

Please note that the above data is fictitious for demonstration purposes. Retrieved ASNs could then be fed back into Amass. The below command attempts to retrieve registered domains found within the specified ASN and return them along with the IP address they resolve to (127.0.0.1 in this case for demonstration purposes):

$ amass intel -active -asn 222222 -ip
some-example-ltd-domain.com 127.0.0.1
[...]
```



## 大量枚举



让我们转向 Amass 枚举，这是 Amass 大部分强大功能所在的地方。Amass 枚举允许您执行 DNS 枚举和目标映射，以确定组织暴露的攻击面。枚举结果存储在图形数据库中，该数据库将位于 Amass 的默认输出文件夹或带有“-dir”标志的指定输出目录中。其他 Amass 子命令也是如此。

### 在被动或主动配置下运行 Amass



Amass enum 可以在被动或主动配置模式的上下文中执行。被动模式要快得多，但 Amass 不会验证 DNS 信息，例如通过解析子域。您可以使用“-passive”标志被动运行它，并且您将无法启用许多技术或配置，例如 DNS 暴力破解和名称更改。选择被动模式而不是主动模式有多种原因，例如：

- 您需要了解所有可能已使用过且将来可能会重复使用的子域，这可能是因为您需要不断监控目标攻击面的变化，或者因为您正在进行网络钓鱼活动并寻找子域。
- 您的周边安全测试流程会在稍后阶段验证 DNS 信息，并需要快速收集结果。
- 由于安全参与的限制或要求，您只能执行被动信息收集。

在下面的示例中，我们在 owasp.org 上被动搜索子域(以测试)：

```
$ amass enum -passive -d owasp.org
[...]
update-wiki.owasp.org
[...]
my.owasp.org
www.lists.owasp.org
www.ocms.owasp.org
[...]
```



值得一提的是，尽管 Amass intel 将帮助收集组织拥有的 IP 范围、ASN 和注册域，但 Amass enum 将识别所有子域。在我的测试机器上，这个子域枚举在 2 分钟内完成。这是一个稍微修改过的屏幕截图，显示了此枚举的结果：

[![用于子域发现的 OWASP Amass 枚举教程](https://github.com/owasp-amass/amass/raw/master/images/tutorial/amass_passive_run_example.png?raw=true)](https://github.com/owasp-amass/amass/blob/master/images/tutorial/amass_passive_run_example.png?raw=true)

在主动配置模式下使用 Amass 意味着您将获得更准确的结果，并且可以发现更多资产，因为所有 DNS 枚举技术都将启用。应该注意的是，“主动配置模式”并不是严格指“-active”标志，该标志启用 SSL/TLS 服务的区域传输和端口扫描，并抓取其证书以从证书字段中提取任何子域（例如 Common姓名）。

下面的命令（稍后详细解释）可以被认为是总体活跃的，因为它以多种方式（单词列表、掩码等）执行子域暴力破解，并且启用了“-active”标志。所有结果都将由 Amass 使用默认或指定的解析器进行验证：

```
$ amass enum -active -d owasp.org -brute -w /root/dns_lists/deepmagic.com-top50kprefixes.txt -ip -dir amass4owasp -config /root/amass/config.yaml -o amass_results_owasp.txt
```



[![使用 OWASP Amass 执行子域发现练习](https://github.com/owasp-amass/amass/raw/master/images/tutorial/amass_active_run_example.png?raw=true)](https://github.com/owasp-amass/amass/blob/master/images/tutorial/amass_active_run_example.png?raw=true)

我们上面使用的命令指定 Amass 图形数据库以及日志文件将存储在“./amass4owasp”。我们还要求 Amass 使用“-ip”标志显示其解析名称的 IP 地址。我们使用“-w”参数为 Amass 提供了 [deepmagic](https://github.com/danielmiessler/SecLists/tree/master/Discovery/DNS) DNS 单词列表，并使用“-config”指定了 config.yaml 文件的位置，并使用“-o”指定了输出。

虽然上面的命令希望很简单，但我们想提供一些进一步的说明：

- 在这种情况下，Amass 将在 config.yaml 文件中检查 DNS 解析器，或使用 Amass 代码中嵌入的默认解析器。您还可以使用“-r”和“-rf”标志或在 config.yaml 文件中指定自己的 DNS 解析器。使用“-r”标志，您可以在命令行指定 DNS 解析器的 IP 地址，而使用“-rf”，您可以在每行指定包含这些地址的文件。
- 我们可以在 config.yaml 文件中指定所有这些配置，并使用“-config”将其提供给 Amass。此时值得说明的是，命令行参数将优先于 config.yaml 文件中指定的内容。因此，如果您在 config.yaml 文件中禁用暴力破解，但在命令行上提供“-brute”参数，则将使用暴力破解技术。
- 除非使用“-norecursive”明确禁用，否则上述命令将对默认识别的子域执行递归 DNS 枚举。

此时，您还应该记住，如果您在短时间内从同一 IP 执行多个 Amass 操作，则该 IP 可能会被永久阻止 Amass 抓取的某些来源，例如 Google/Yahoo 搜索引擎。

为了以更有趣的方式结束本节，我们假设由于某种原因 OWASP 组织倾向于创建带有“zzz”前缀的子域，例如 zzz-dev.owasp.org。您可以利用 Amass 的 hashcat 式单词列表掩码功能，使用以下命令来暴力破解“zzz-[az][az][az].owasp.org”的所有组合：

```
$ amass enum -d owasp.org -norecursive -wm "zzz-?l?l?l" -dir amass4owasp
```



请注意，在上面的配置中，我们已明确禁用递归 DNS 枚举，因为我们希望仅使用掩码获得更快的结果。

最后，您可以随时检查输出目录中的 Amass 日志文件，以确保您的配置按预期工作：

[![OWASP Amass 使用 hashcat 掩码进行高级子域发现](https://github.com/owasp-amass/amass/raw/master/images/tutorial/amass_logs_example2.png?raw=true)](https://github.com/owasp-amass/amass/blob/master/images/tutorial/amass_logs_example2.png?raw=true)

## 海量数据库



您可以使用此子命令与 Amass 图形数据库（默认数据库或使用“-dir”标志指定的数据库）进行交互。

例如，以下命令将列出您在 owasp.org 上执行的枚举过程中发现并存储在“amass4owasp”图形数据库中的所有名称：

```
$ amass db -dir amass4owasp -names -d owasp.org
```



接下来，使用类似的命令，您可以检索 owasp.org 的完整输出并将其存储在“amass4owasp”图形数据库中：

```
$ amass db -dir amass4owasp -d owasp.org -show -ip
```



您可能希望出于统计或历史目的维护相同的 Amass 输出目录，通过该目录执行所有子域枚举练习，因为 Amass 跟踪只能针对相同的图形数据库和输出目录使用。

## 结论



最后，OWASP Amass 是一个越来越受欢迎的项目。如果您有信息收集和子域发现需求，我们强烈建议您将 Amass 纳入您的工作流程/流程中，并且随着每个版本都会添加越来越多的功能和改进，请继续关注。最后，您可以随时参考 Amass 的官方[用户指南](https://github.com/owasp-amass/amass/blob/master/doc/user_guide.md)。