---
title: 62-XSS自动扫描工具 - X-Recon
date: 2024-06-13 20:24:59
tags:
- 渗透工具推荐
- XSS扫描工具
categories:
- 工具推荐
---

 [![X-侦察](https://github.com/joshkar/X-Recon/raw/main/.imgs/banner.jpg)](https://github.com/joshkar/X-Recon)



#### 用于识别网页输入并进行 XSS 扫描的实用程序。

目前测试PHP开发的网站比较好用,其他自行测试!



[![img](https://camo.githubusercontent.com/2b67215b1f14c2b78b7fbbb0f2de3d1fea1276cc68a9f0fab475ce5a329c8214/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f707974686f6e2d76332d626c7565) ](http://python.org/)[![img](https://camo.githubusercontent.com/1ffbafdfd9ce5312d5640c000f8c4e0b559e538f22773c122e358ccd031bee8f/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f506c6174666f726d2d4c696e75782d726564)](https://en.wikipedia.org/wiki/Linux)

### 特征：

- **子域名发现：**
  - 检索目标网站的相关子域名并将其整合到白名单中。这些子域名可在抓取过程中使用。
- **全站链接发现：**
  - 根据提供的白名单和指定的 收集整个网站的所有链接`max_depth`。
- **表单和输入提取：**
  - 识别提取的链接中找到的所有表单和输入，生成 JSON 输出。此 JSON 输出是利用该工具的 XSS 扫描功能的基础。
- **XSS 扫描：**
  - 一旦开始侦察选项返回包含提取条目的自定义 JSON，X-Recon 工具就可以启动 XSS 漏洞测试过程并为您提供所需的结果！


[![X-侦察](https://github.com/joshkar/X-Recon/raw/main/.imgs/demo1.jpg)](https://github.com/joshkar/X-Recon)



**笔记：**

> 目前，扫描功能在 SPA（单页应用程序）Web 应用程序上不可用，我们仅在使用 PHP 开发的网站上进行了测试，取得了显著的效果。未来，我们计划将这些功能整合到该工具中。





[![X-Recon XSS 扫描](https://github.com/joshkar/X-Recon/raw/main/.imgs/demo2.jpg)](https://github.com/joshkar/X-Recon)



**笔记：**

> 此工具会维护一个最新的文件扩展名列表，这些文件扩展名会在探索过程中跳过。默认列表包括图像、样式表和脚本 ( `".css",".js",".mp4",".zip","png",".svg",".jpeg",".webp",".jpg",".gif"`) 等常见文件类型。您可以通过编辑 setting.json 文件自定义此列表，以更好地满足您的需求。

### 安装

```
$ git clone https://github.com/joshkar/X-Recon
$ cd X-Recon
$ python3 -m pip install -r requirements.txt
$ python3 xr.py
```

## 测试目标：

> 您可以在“获取 URL”部分中使用此地址

```
  http://testphp.vulnweb.com
  #不可以携带http
```
