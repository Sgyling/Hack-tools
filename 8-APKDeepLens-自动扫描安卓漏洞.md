---
title: APKDeepLens-APK自动渗透
date: 2024-3-14 15:07:46
tags:
- 渗透工具推荐
categories:
- 工具推荐
---



# APKDeepLens

APKDeepLens 是一个基于 Python 的工具，旨在扫描 Android 应用程序（APK 文件）是否存在安全漏洞。它专门针对 OWASP Top 10 移动漏洞，为开发人员、渗透测试人员和安全研究人员提供一种简单有效的方法来评估 Android 应用程序的安全状况。

[![图像](https://private-user-images.githubusercontent.com/27950739/299625348-c9236e3d-60d5-4832-85dc-f09a449bade3.png?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3MTA0MDAyOTksIm5iZiI6MTcxMDM5OTk5OSwicGF0aCI6Ii8yNzk1MDczOS8yOTk2MjUzNDgtYzkyMzZlM2QtNjBkNS00ODMyLTg1ZGMtZjA5YTQ0OWJhZGUzLnBuZz9YLUFtei1BbGdvcml0aG09QVdTNC1ITUFDLVNIQTI1NiZYLUFtei1DcmVkZW50aWFsPUFLSUFWQ09EWUxTQTUzUFFLNFpBJTJGMjAyNDAzMTQlMkZ1cy1lYXN0LTElMkZzMyUyRmF3czRfcmVxdWVzdCZYLUFtei1EYXRlPTIwMjQwMzE0VDA3MDYzOVomWC1BbXotRXhwaXJlcz0zMDAmWC1BbXotU2lnbmF0dXJlPTYyOWZjNzRkYWUwNDlkMzUxMTI3ZDhkMjU0NjMwYTE1NTdlMzg3ZTVkYTFlZjJhNWNkNTcxM2ZiMDNhYTE3ZjUmWC1BbXotU2lnbmVkSGVhZGVycz1ob3N0JmFjdG9yX2lkPTAma2V5X2lkPTAmcmVwb19pZD0wIn0.gDYBdiQYyoOiNWTv-gbi43Wac2hmrEOiNiw9D3FK5dc)](https://private-user-images.githubusercontent.com/27950739/299625348-c9236e3d-60d5-4832-85dc-f09a449bade3.png?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3MTA0MDAyOTksIm5iZiI6MTcxMDM5OTk5OSwicGF0aCI6Ii8yNzk1MDczOS8yOTk2MjUzNDgtYzkyMzZlM2QtNjBkNS00ODMyLTg1ZGMtZjA5YTQ0OWJhZGUzLnBuZz9YLUFtei1BbGdvcml0aG09QVdTNC1ITUFDLVNIQTI1NiZYLUFtei1DcmVkZW50aWFsPUFLSUFWQ09EWUxTQTUzUFFLNFpBJTJGMjAyNDAzMTQlMkZ1cy1lYXN0LTElMkZzMyUyRmF3czRfcmVxdWVzdCZYLUFtei1EYXRlPTIwMjQwMzE0VDA3MDYzOVomWC1BbXotRXhwaXJlcz0zMDAmWC1BbXotU2lnbmF0dXJlPTYyOWZjNzRkYWUwNDlkMzUxMTI3ZDhkMjU0NjMwYTE1NTdlMzg3ZTVkYTFlZjJhNWNkNTcxM2ZiMDNhYTE3ZjUmWC1BbXotU2lnbmVkSGVhZGVycz1ob3N0JmFjdG9yX2lkPTAma2V5X2lkPTAmcmVwb19pZD0wIn0.gDYBdiQYyoOiNWTv-gbi43Wac2hmrEOiNiw9D3FK5dc)

## 特征



APKDeepLens 是一个基于 Python 的工具，可对 APK 文件执行各种操作。其主要特点包括：

- **APK 分析**-> 扫描 Android 应用程序包 (APK) 文件是否存在安全漏洞。
- **OWASP 覆盖范围**-> 涵盖 OWASP Top 10 漏洞，以确保全面的安全评估。
- **高级检测**-> 利用自定义 python 代码进行 APK 文件分析和漏洞检测。
- **敏感信息提取**-> 通过从APK文件中提取敏感信息来识别潜在的安全风险，例如不安全的身份验证/授权密钥和不安全的请求协议。
- **深入分析**-> 检测不安全的数据存储实践，包括与 SD 卡相关的数据，并突出显示代码中不安全请求协议的使用。
- **意图过滤器漏洞**-> 通过分析从 AndroidManifest.xml 中提取的意图过滤器来查明漏洞。
- **本地文件漏洞检测**-> 通过识别与本地文件操作相关的潜在错误处理来保护您的应用程序
- **报告生成**-> 为每个扫描的 APK 生成详细且易于理解的报告，为开发人员提供可操作的见解。
- **CI/CD 集成**-> 旨在轻松集成到 CI/CD 管道中，从而在开发工作流程中实现自动化安全测试。
- **用户友好的界面**-> 颜色编码的终端输出可以轻松区分不同类型的结果。

## 安装



要使用 APKDeepLens，您需要在系统上安装 Python 3.8 或更高版本。然后，您可以使用以下命令安装 APKDeepLens：

### 对于Linux



```
git clone https://github.com/d78ui98/APKDeepLens/tree/main
cd /APKDeepLens
python3 -m venv venv
source venv/bin/activate
pip install -r requirements.txt
python APKDeepLens.py --help
```



### 对于 Windows



```
git clone https://github.com/d78ui98/APKDeepLens/tree/main
cd \APKDeepLens
python3 -m venv venv
.\venv\Scripts\activate
pip install -r .\requirements.txt
python APKDeepLens.py --help
```

### #使用手动下载方式

```shell
https://github.com/d78ui98/APKDeepLens #打开链接
#选择code
#选择Download zip
#解压
#打开终端
cd 解压目录
python -m pip install -r requirements.txt #安装环境
python -m venv venv #进入虚拟环境
.\venv\Scripts\activate #进入虚拟环境
python -m pip install -r .\requirements.txt #安装库
python APKDeepLens.py --help #查看帮助
```





## 用法



要简单地扫描 APK，请使用以下命令。使用参数提及 apk 文件`-apk`。扫描完成后，详细报告将显示在控制台中。

```
python3 APKDeepLens.py -apk file.apk
```



如果您已经提取了源代码并希望提供其路径以进行更快的扫描，您可以使用以下命令。使用参数提及 android 应用程序的源代码`-source`。

```
python3 APKDeepLens.py -apk file.apk -source <source-code-path>
```



要在扫描后生成详细的 PDF 和 HTML 报告，您可以传递`-report`如下所述的参数。

```
python3 APKDeepLens.py -apk file.apk -report
```