## **安装**

在kali中 可以直接使用命令进行安装 `sudo apt install gobuster`

对于其他系统则可以直接从Github仓库中直接获取源代码（需要go环境）

Github源码地址:https://github.com/OJ/gobuster

## **简介**

Gobuster 是一款使用 Go 语言编写的开源渗透测试工具，主要用于在 Web 应用程序或网络环境中进行各种暴力破解和枚举任务，后台目录、网站域名、Fuzzing测试、云桶找寻，一应俱全

- **多种扫描模式**：具备目录枚举、子域名枚举、虚拟主机枚举、AWS S3 存储桶枚举、谷歌云存储桶枚举以及 TFTP 服务器枚举等多种模式，能满足不同的安全测试需求。例如，在进行网站安全评估时，可通过目录枚举模式查找网站中可能存在的隐藏目录和文件4.
- **快速高效**：采用多线程技术，能够同时处理多个请求，大大提高了扫描速度和效率，可快速地在大量的目录或子域名中查找目标，节省时间和资源246.
- **灵活的字典支持**：支持使用自定义字典文件，用户可根据目标的特点和已知信息选择或创建合适的字典，以提高扫描的准确性和效果。比如，针对特定类型的网站或应用程序，使用与之相关的专业字典进行扫描46.
- **可定制请求头**：允许用户指定自定义的 HTTP 头部信息，从而更好地模拟不同的请求场景，绕过一些简单的访问限制或检测机制，使扫描更加隐蔽和有效4.
- **递归扫描功能**：可以对目标网站进行递归扫描，深入探索其目录结构，有助于发现更深层次的隐藏内容和潜在漏洞4.
- **多种输出方式**：扫描结果既可以输出到终端，方便实时查看，也可以保存到文件中，并且支持多种输出格式，便于后续的分析和报告生成4.
- **代理支持**：可配置代理服务器，通过代理进行扫描，隐藏自身真实 IP 地址，增加扫描的隐蔽性和安全性，同时也可用于突破一些网络访问限制4.

## **用例**

### **一、使用gobuster对网站后台目录进行爆破（dir模式）**

#### **语法：`gobuster dir [flags]`**

#### **flag：**

- **-u, --url**：指定目标 URL。这是最基本的参数，例如`gobuster dir -u http://example.com`，它告诉 gobuster 要对哪个网站进行扫描。
- **-w, --wordlist**：指定用于暴力破解的字典文件。字典文件包含了可能的目录或文件名，如`-w /usr/share/wordlists/dirb/big.txt`。
- **-t, --threads**：设置并发线程数。增加线程数可以加快扫描速度，但可能会对目标服务器造成较大压力，同时也可能导致不准确的结果或被目标服务器封禁。例如`-t 10`表示使用 10 个线程进行扫描。
- **-x, --extensions**：用于指定要查找的文件扩展名。如果要查找.php 和.html 文件，可以使用`-x php,html`。
- **-c, --cookies**：当目标网站需要身份验证（通过 cookies）才能访问某些目录或文件时，可以使用此参数提供 cookies。例如`-c "sessionid=12345"`。
- **-s, --status -codes**：可以指定要包含或排除的 HTTP 状态码。例如，只显示状态码为 200 和 301 的结果，可以使用`-s 200,301`。
- **-e, --expanded**：显示完整的 URL 路径，而不仅仅是相对路径。这对于获取准确的目录和文件位置很有用。
- **-k, --insecure**：跳过 SSL 证书验证。在扫描使用自签名证书或 SSL 配置有问题的目标时，可以使用此参数，但会带来安全风险。

#### **使用实例**

```
gobuster dir -u http://exmple.com --wordlist=/usr/share/dirbuster/wordlists/directory-list-2.3-medium.txt
```

1. dir 爆破模式（目录爆破）
2. -u 指定url
3. /usr/share/dirbuster/wordlists/directory-list-2.3-medium.txt  是kali系统中自带的专门爆破网站目录的字典

![img](https://mmbiz.qpic.cn/mmbiz_png/5IZsDqfQ73RfhLIQLoU1zgrSM4YuydqQfUWO23dyUy2WstlXv0SAfUAxrb8jo7EzbJXM61WtBQzQsWOVFOYbSg/640?wx_fmt=png&from=appmsg)

### **二、使用gobuster对网站域名进行爆破（dns模式）**

#### **语法：`gobuster dns [flag]`**

#### **flags：**

- **-u, --domain**：指定目标域名，如`gobuster dns -u example.com`。
- **-w, --wordlist**：和目录扫描模式类似，用于指定包含子域名猜测列表的字典文件。
- **-t, --threads**：设置并发线程数来加快扫描速度。
- **-i, --include -ip**：在结果中显示子域名对应的 IP 地址，这有助于进一步分析目标的网络架构。
- **-r, --resolver**：指定自定义的 DNS 服务器来进行解析。在怀疑目标的 DNS 记录被篡改或者需要使用特定的 DNS 服务器进行解析时可以使用此参数。

#### **使用实例**

```
gobuster dns -d google.com -t 50 -w /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt
```

1. dns 域名爆破模式
2. -d google.com 指定目标域名
3. -t 50 用于设置并发线程数（提高爆破速率）
4. -w /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt 选择爆破字典

`/usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt` 是kali系统中自带的域名爆破字典

![img](https://mmbiz.qpic.cn/mmbiz_png/5IZsDqfQ73RfhLIQLoU1zgrSM4YuydqQo4licPvuqmiajLRD9qibhHpUAr9puLVboNJd79sS57icjuKnLBRJ7xjJGg/640?wx_fmt=png&from=appmsg)

- 添加 -i 选项可以选择是否显示 ip信息

![img](https://mmbiz.qpic.cn/mmbiz_png/5IZsDqfQ73RfhLIQLoU1zgrSM4YuydqQBiaNS77wUSJQLnI2zvzmXL4VZsUKKYWgNXPCuWiaZg863ic004E91CRZg/640?wx_fmt=png&from=appmsg)

### **虚拟主机爆破 （vhost 模式）**

#### **语法：`gobuster vhost [flag]`**

#### **flags：**

- **-u, --url**：指定目标 URL，例如`gobuster vhost -u http://example.com`。
- **-w, --wordlist**：指定包含虚拟主机猜测列表的字典文件。
- **-t, --threads**：设置并发线程数。
- **-c, --cookies**：用于提供身份验证所需的 cookies，和目录扫描模式中的 - c 参数功能相同。
- **-s, --status -codes**：指定要包含或排除的 HTTP 状态码，以过滤虚拟主机扫描的结果。

#### **实例：**

```
gobuster vhost -u http://example.com -w /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt -t 10
```

### **fuzz 模式**

可以利用指定字典对指定测试点进行Fuzzing模糊测试

#### **flags:**

- **-u, --url**：指定要进行模糊测试的目标 URL，明确测试的具体位置，例如 `gobuster fuzz -u http://example.com/api`，这里将对 `example.com` 网站下的 `api` 接口相关部分进行模糊测试。
- **-w, --wordlist**：指定用于模糊测试的字典文件，字典里包含了各种将要替换关键测试点（比如文档中提到替换 `FUZZ` 关键字的内容）的字符串，像 `-w /path/to/your/fuzzing_wordlist.txt`。
- **-t, --threads**：设置并发线程数，合理设置线程数量能在一定程度上加快模糊测试的速度，但也要考虑目标服务器的负载承受能力以及准确性等问题，例如 `-t 10` 表示启用 10 个线程同时进行模糊测试操作。
- **-p, --parameters**（可能存在，用于特定场景）：如果模糊测试针对的是 URL 中的参数部分，可通过此参数指定具体要模糊测试的参数名称等相关设置，比如 `-p param1,param2` 表示针对 `param1` 和 `param2` 这两个参数进行模糊测试替换操作。

### **gcs 模式**

运用 GCS（Google Cloud Storage，谷歌云存储）桶枚举模式，也就是去查找谷歌云存储服务中相关的存储桶信息

#### **flags：**

- **-b, --bucket**（可能存在，用于指定桶相关）：可以用于指定具体的谷歌云存储桶名称或者桶名称的一部分（结合模糊匹配等功能）来缩小枚举范围，例如 `-b my-gcs-bucket-prefix` 去查找名字带有 `my-gcs-bucket-prefix` 开头的存储桶信息。
- **-a, --auth-file**（推测可能需要，用于认证相关）：由于访问谷歌云存储服务通常需要认证信息，可能通过此参数指定包含认证凭据（比如服务账号密钥文件等）的文件路径，像 `-a /path/to/your/gcs_auth_file.json`，以此来合法获取存储桶信息。
- **-o, --output**（通用输出相关）：指定将枚举结果输出到的文件路径，方便后续查看和分析，例如 `-o gcs_bucket_enum_results.txt`，这样扫描得到的谷歌云存储桶相关信息会保存到指定的文本文件中。

### **s3 模式**

使用 AWS（Amazon Web Services，亚马逊网络服务）桶枚举模式，类似于 `gcs` 命令对于谷歌云存储桶的操作，不过这里针对的是亚马逊云服务中的 S3 存储桶，去发现 S3 桶的相关信息

flags：

- **-r, --region**（与 AWS 区域相关）：指定要查找 S3 存储桶所在的 AWS 区域，因为 AWS 服务分布在不同区域，明确区域能更精准地进行枚举，例如 `-r us-west-1` 表示在美国西部 1 区查找 S3 桶情况。
- **-k, --access-key** 和 **-s, --secret-key**（认证相关，可能存在）：AWS S3 访问通常需要访问密钥和秘密密钥进行身份验证，可分别通过这两个参数来传入相应的密钥信息，比如 `-k YOUR_ACCESS_KEY -s YOUR_SECRET_KEY`，以此授权工具进行存储桶枚举操作。
- **-m, --match**（可能用于筛选等）：可以用来根据一些特定的规则（如桶名称匹配特定模式、桶标签等条件）对找到的 S3 存储桶进行筛选，例如 `-m "tag:env=prod"` 表示只显示带有 `env=prod` 这个标签的 S3 桶信息。

### **tftp 模式**

运用 TFTP（Trivial File Transfer Protocol，简单文件传输协议）枚举模式，可能会去扫描网络中基于 TFTP 协议进行文件传输的相关服务情况、可访问的资源等

#### **flags：**

- **-i, --ip**（指定目标 IP）：由于 TFTP 是基于网络中具体设备间的服务，需要明确要扫描的目标 IP 地址，如 `-i 192.168.1.10`，表示对 IP 为 `192.168.1.10` 的设备上的 TFTP 相关服务和资源进行枚举。
- **-l, --local-ip**（可选，本地 IP 相关）：在一些复杂网络环境中，可能需要指定本地的 IP 地址用于 TFTP 连接等情况，比如 `-l 192.168.1.20`，告诉工具从本地 `192.168.1.20` 这个 IP 去发起对目标 TFTP 服务的枚举操作。
- **-f, --file-filter**（可能存在，用于文件筛选）：若只想查找特定类型的文件（基于 TFTP 传输的文件），可以通过此参数设置文件扩展名等过滤条件，例如 `-f ".txt,.pdf"` 表示只关注扩展名为 `.txt` 和 `.pdf` 的可通过 TFTP 访问的文件情况。

## **总结**

Gobuster是一个很好用的爆破工具，功能也很多，文章只对常用的域名爆破和后台目录爆破做了详细的描述和实例，其余可根据需要自行了解