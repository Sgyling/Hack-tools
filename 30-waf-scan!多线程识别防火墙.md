---
title: waf-scan-多线程批量识别WAF!
date: 2024-2-27 15:10:00
tags:
- 渗透工具推荐
categories:
- 工具推荐
---



# 01. waf-scan



> 前言：基于wafw00f的插件内容，实现多线程批量识别版本。
>
> 批量识别waf防火墙.
>
> ​	如何运行的?
>
> - 发送*正常的*HTTP请求并分析响应；这确定了许多 WAF 解决方案。
> - 如果不成功，它会发送许多（可能是恶意的）HTTP 请求，并使用简单的逻辑来推断它是哪个 WAF。
> - 如果也不成功，它会分析之前返回的响应，并使用另一种简单的算法来猜测 WAF 或安全解决方案是否正在积极响应我们的攻击。

## 1.1. Usage



```
# 对单个目标进行扫描 #
python waf-scan.py -t https://example.com

# 对多个目标进行扫描 #
python waf-scan.py -f targets.txt

# 结果输出 #
`/report/`目录下会生成对应目标的json结果文件。
```



[![img.png](https://github.com/jammny/waf-scan/raw/master/img.png)](https://github.com/jammny/waf-scan/blob/master/img.png)

## 1.2. 程序兼容性



python版本 >= 3.8.0

## 1.3. Update



| 更新时间（版本）  | 更新内容 | 备注         |
| ----------------- | -------- | ------------ |
| 2023.8.15(v0.0.1) | 内测版本 | 有问题联系我 |

## 1.4 Github链接

https://github.com/jammny/waf-scan



## 1.5 下载命令

git clone https://github.com/jammny/waf-scan.git