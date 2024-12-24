---
title: CloakQuest3r-寻找服务器真实IP地址.
date: 2024-2-25 20:14:46
tags:
- 渗透工具推荐
categories:
- 工具推荐
---



## CloakQuest3r -绕过防护-获取真实IP地址.而且还是爆破子域名最快的工具?

CloakQuest3r 是一款功能强大的 Python 工具，经过精心设计，可揭示由 Cloudflare 和其他替代方案（一项广泛采用的 Web 安全和性能增强服务）保护的网站的真实 IP 地址。其核心任务是准确识别隐藏在 Cloudflare 防护罩后面的 Web 服务器的实际 IP 地址。子域扫描被用作实现这一目标的关键技术。对于寻求执行全面安全评估并识别可能被 Cloudflare 安全措施掩盖的漏洞的渗透测试人员、安全专业人员和 Web 管理员来说，该工具是宝贵的资源。

**主要特征：**

- **真实 IP 检测：** CloakQuest3r 擅长发现使用 Cloudflare 服务的 Web 服务器的真实 IP 地址。这一关键信息对于进行全面的渗透测试和确保网络资产的安全至关重要。
- **子域扫描：**子域扫描是查找真实 IP 地址过程中的基本组成部分。它有助于识别负责托管网站及其相关子域的实际服务器。
- **IP 地址历史记录：**检索给定域的历史 IP 地址信息。它使用 ViewDNS 服务来获取和显示 IP 地址、位置、所有者和上次查看日期等详细信息。
- **SSL 证书分析：**提取并分析与目标域关联的 SSL 证书。这可以提供有关托管基础设施的附加信息，并有可能泄露真实的 IP 地址。
- **SecurityTrails API（可选）：** 如果您将免费的 SecurityTrails API 密钥添加到 config.ini 文件中，则可以从 SecurityTrails 检索历史 IP 信息。
- **线程扫描：**为了提高效率并加快真实 IP 检测过程，CloakQuest3r 使用线程。此功能可以扫描大量子域列表，而无需显着延长执行时间。
- **详细报告：**该工具提供全面的输出，包括扫描的子域总数、找到的子域总数以及扫描所需的时间。在此过程中公开的任何真实 IP 地址也会被显示，以便于深入分析和渗透测试。

借助 CloakQuest3r，您可以自信地评估网站安全性、发现隐藏的漏洞，并通过公开隐藏在 Cloudflare 保护层后面的真实 IP 地址来保护您的 Web 资产。

#### 特色：

```
CloakQuest3r``Top 20 Most Popular Hacking Tools`是2023 年的其中之一`KitPloit
```

- [2023 年 20 种最受欢迎的黑客工具](https://www.kitploit.com/2023/12/top-20-most-popular-hacking-tools-in.html)

#### 局限性

```
- Sometimes it can't detect the real Ip.

- CloakQuest3r combines multiple indicators to uncover real IP addresses behind Cloudflare. While subdomain scanning is a part of the process, we do not assume that all subdomains' A records point to the target host. The tool is designed to provide valuable insights but may not work in every scenario. We welcome any specific suggestions for improvement.

- We created a proof of concept, but it's not well-written. We welcome pull requests to improve it.

1. False Negatives: CloakReveal3r may not always accurately identify the real IP address behind Cloudflare, particularly for websites with complex network configurations or strict security measures.

2. Dynamic Environments: Websites' infrastructure and configurations can change over time. The tool may not capture these changes, potentially leading to outdated information.

3. Subdomain Variation: While the tool scans subdomains, it doesn't guarantee that all subdomains' A records will point to the primary host. Some subdomains may also be protected by Cloudflare.
```



#### 该工具是概念验证，仅用于教育目的。

------

#### 操作系统兼容性：  [![img](https://camo.githubusercontent.com/0825e0d13a2e355ab5aa1ccc2773878bb7089111646767276f0b621bae2eb403/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f57696e646f77732d3035313232413f7374796c653d666f722d7468652d6261646765266c6f676f3d77696e646f7773)](https://camo.githubusercontent.com/0825e0d13a2e355ab5aa1ccc2773878bb7089111646767276f0b621bae2eb403/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f57696e646f77732d3035313232413f7374796c653d666f722d7468652d6261646765266c6f676f3d77696e646f7773) [![img](https://camo.githubusercontent.com/9c344f779907c0d4267caa574f27fe72819712469967f411e6db7cc5a07c5a68/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f4c696e75782d3035313232413f7374796c653d666f722d7468652d6261646765266c6f676f3d6c696e7578)](https://camo.githubusercontent.com/9c344f779907c0d4267caa574f27fe72819712469967f411e6db7cc5a07c5a68/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f4c696e75782d3035313232413f7374796c653d666f722d7468652d6261646765266c6f676f3d6c696e7578) [![img](https://camo.githubusercontent.com/c5e66de293ad5e36c75502d4e9b6bc21e7e10c6c80a5081fa041adc334c5a367/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f416e64726f69642d3035313232413f7374796c653d666f722d7468652d6261646765266c6f676f3d616e64726f6964)](https://camo.githubusercontent.com/c5e66de293ad5e36c75502d4e9b6bc21e7e10c6c80a5081fa041adc334c5a367/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f416e64726f69642d3035313232413f7374796c653d666f722d7468652d6261646765266c6f676f3d616e64726f6964) [![img](https://camo.githubusercontent.com/4d89a67864d198e1a612a51a1b2c2e7d938628c6e5152fd1a8d4c3c97f41808e/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f6d61634f532d3035313232413f7374796c653d666f722d7468652d6261646765266c6f676f3d6d61636f73)](https://camo.githubusercontent.com/4d89a67864d198e1a612a51a1b2c2e7d938628c6e5152fd1a8d4c3c97f41808e/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f6d61634f532d3035313232413f7374796c653d666f722d7468652d6261646765266c6f676f3d6d61636f73)

#### 要求：  [![img](https://camo.githubusercontent.com/72cc453bfaa3fb96883c90c6421df75856d4248fc7373d7e564c989143f8bf7f/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f507974686f6e2d3035313232413f7374796c653d666f722d7468652d6261646765266c6f676f3d707974686f6e)](https://camo.githubusercontent.com/72cc453bfaa3fb96883c90c6421df75856d4248fc7373d7e564c989143f8bf7f/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f507974686f6e2d3035313232413f7374796c653d666f722d7468652d6261646765266c6f676f3d707974686f6e) [![img](https://camo.githubusercontent.com/e2359785a0e6de4231c6bfa16b8bcddb08127c9268928869c432cc0fd2fe1086/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f4769742d3035313232413f7374796c653d666f722d7468652d6261646765266c6f676f3d676974)](https://camo.githubusercontent.com/e2359785a0e6de4231c6bfa16b8bcddb08127c9268928869c432cc0fd2fe1086/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f4769742d3035313232413f7374796c653d666f722d7468652d6261646765266c6f676f3d676974)

**如何使用：**

1. 使用单个命令行参数运行 CloudScan：您要分析的目标域。

   ```
    git clone https://github.com/spyboy-productions/CloakQuest3r.git
   ```

   

   ```
   cd CloakQuest3r
   ```

   

   ```
   pip3 install -r requirements.txt
   ```

   如果是电脑上有两个python环境,2和3.则命令更换为
   python3 -m pip install -r requirements.txt

   

   `For Termux(android) User``cryptography`如果使用requirements.txt安装时遇到问题，请使用下面给出的命令

   `pkg install python-cryptography`

   ```
   python cloakquest3r.py example.com
   ```

   

2. 该工具将检查网站是否使用 Cloudflare。如果没有，它会通知您并询问您是否仍要继续。

3. 如果检测到 Cloudflare，它会首先打印历史 IP 记录，然后扫描子域并识别其真实 IP 地址。

4. 您将收到详细的输出，包括扫描的子域数量、找到的子域总数以及扫描所需的时间。

5. 任何找到的真实IP地址都会显示出来，以便您进行进一步的分析和渗透测试。

它通过提供清晰、有组织且内容丰富的报告，简化了评估网站安全的过程。使用它来增强您的安全评估、识别潜在漏洞并保护您的网络资产。

------

**可选**：[SecurityTrails API](https://securitytrails.com/)

从 SecurityTrails 检索历史 IP 信息。如果您有 API 密钥，请将其添加到配置文件 (config.ini) 中。

初次执行脚本时，它会生成一个包含以下内容的 config.ini 文件：

```
[DEFAULT]
securitytrails_api_key = your_api_key
```



随后，该脚本尝试从 SecurityTrails API 检索数据。如果由于配额限制或站点不可用等原因导致检索失败，则会优雅地跳过相应的功能。

------

#### 在 replit.com 上在线运行

这只是一个演示，并非所有功能都可用。请安装该工具以充分发挥其潜力。

[![在 Repl.it 上运行](https://camo.githubusercontent.com/373b6e697b06b2d984b47d282c2f9d62cbb41c9270b734844ec2aba160de06b5/68747470733a2f2f7265706c2e69742f62616467652f6769746875622f737079626f792d70726f64756374696f6e732f436c6f616b51756573743372)](https://replit.com/@spyb0y/CloakQuest3r)

------

#### 贡献：

欢迎贡献和功能请求！如果您遇到任何问题或有改进的想法，请随时提出问题或提交拉取请求。

#### 😴🥱😪💤待办事项：

- 在子域扫描之前要求用户提供自定义子域单词列表，如果用户没有，则使用默认的子域单词列表。
- 通过网站 API 调用 (POC) 发现 IP
- 将所有信息保存在 Txt/CSV 文件中。