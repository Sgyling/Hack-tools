---
title: FindUpload-寻找上传点-登陆点
date: 2024-3-17 13:10:46
tags:
- 渗透工具推荐
categories:
- 工具推荐
---



# 🚀 FindUpload 💥



帮助你快速发现文件上传点,遇强则强,知攻善防

## ⚙️ 功能



- 通过批量的 URL 进行目标搜索
- 支持使用代理进行扫描
- 可以配置线程数以提高效率

## 📝 使用方法



1. 在 `urls.txt` 文件中添加目标 URL。每行一个 URL，可以按需添加需要扫描的目标。(完整的url,需包含http/https)
2. 在 `config.ini` 文件中配置代理和线程数。根据需要设置代理和适当的线程数以达到最佳效果。
3. 在命令行中执行以下命令来启动工具：

```
python f.py -u # 扫描上传点
python f.py -l # 扫描登录点
```



1. 工具将自动进行扫描，当发现文件上传点时，将会输出结果到upload.txt文件中
2. 当发现登录点时，将会输出结果到login.txt文件中

## ⚠️ 注意事项



- ⚠️ 请确保你具有合法授权来测试和使用此工具。
- ⚠️ 在使用该工具期间，请遵守当地相关法律法规。
- ⚠️ 开发者对工具使用所产生的任何不当行为概不负责。

## github链接:

https://github.com/dahezhiquan/FindUpload/

## 下载和使用

```
#下载该工具
git clone https://github.com/dahezhiquan/FindUpload.git
#使用命令
python f.py -u # 扫描上传点
python f.py -l # 扫描登录点
```

