---
title: 全自动提权工具-Windows-Linux-Macos
date: 2024-3-16 16:14:46
tags:
- 渗透工具推荐
categories:
- 工具推荐
---



# PEASS-ng-全自动提权工具

## 	1-简介

![img](https://pic.imgdb.cn/item/65f565eb9f345e8d03b55cf4.png)

一款支持Linux-Windows-MacOS的自动提权工具.直接运行即可.

```
按下Win+R，运行netplwiz，查看您的账户
```



## 	2-github链接

```
https://github.com/carlospolop/PEASS-ng
```



## 	3-github下载链接

```
https://github.com/carlospolop/PEASS-ng/releases/tag/20240310-532aceca
```

## 	4-使用方式

```
#Windows下
最好使用pwershell运行即可
#Linux下
直接运行
#MacOS下,自行测试
```

## 	5-扫描哪些信息

#### 能检查哪些信息:

- 系统信息
  - 基本系统信息
  - 使用 Watson 搜索漏洞
  - 枚举 Microsoft 更新信息
  - PS、审计、WEF 和 LAPS 设置
  - LSA 保护
  - 凭据保护
  - WDigest
  - 缓存的信用数量
  - 环境变量
  - 互联网设置
  - 当前驱动器信息
  - 杀毒软件
  - Windows Defender
  - UAC 配置
  - NTLM 设置
  - 本地组策略
  - Applocker 配置和绕过建议
  - 打印机
  - 命名管道
  - AMSI 供应商
  - 系统监视器
  - .NET 版本
- 用户信息
  - 用户信息
  - 当前令牌特权
  - 剪贴板文本
  - 当前登录的用户
  - RDP 会话
  - 曾经登录过的用户
  - 自动登录凭据
  - 主文件夹
  - 密码策略
  - 本地用户详细信息
  - 登录会话
- 进程信息
  - 有趣的进程（非微软）
- 服务信息
  - 有趣的服务（非 Microsoft）信息
  - 可修改的服务
  - 可写服务注册表binpath
  - PATH DLL劫持
- 应用信息
  - 当前活动窗口
  - 安装的软件
  - 自动运行
  - 计划任务
  - 设备驱动程序
- 网络信息
  - 当前net share
  - 映射驱动器 (WMI)
  - 主机文件
  - 网络接口
  - 监听端口
  - 防火墙规则
  - DNS 缓存（限制 70）
  - 互联网设置
- Windows 凭据
  - Windows 保险库
  - 凭证管理器
  - 保存的 RDP 设置
  - 最近运行的命令
  - 默认 PS 成绩单文件
  - DPAPI 万能密钥
  - DPAPI 凭据文件
  - 远程桌面连接管理器凭据
  - Kerberos 门票
  - 无线上网
  - AppCmd.exe
  - SSClient.exe
  - SCCM
  - 安全包凭证
  - AlwaysInstallElevated
  - WSUS
- 浏览器信息
  - Firefox 数据库
  - Firefox 历史上的凭据
  - Chrome 数据库
  - chrome 历史上的凭据
  - 当前的 IE 选项卡
  - IE历史上的凭据
  - IE 收藏夹
  - **提取已保存的密码：Firefox、Chrome、Opera、Brave**
- 有趣的文件和注册表
  -  Putty会话
  - Putty SSH 主机密钥
  - SuperPutty信息
  - OneDrive 同步的 Office365 端点
  - 注册表中的 SSH 密钥
  - 云凭证
  - 检查无人参与的文件
  - 检查 SAM 和 SYSTEM 备份
  - 检查缓存的 GPP 密码
  - 从 McAffe SiteList.xml 文件中检查并提取凭据
  - 可能的具有凭据的注册表
  - 用户家中可能的凭据文件
  - **回收站中可能存在的密码文件**
  - 可能包含凭据的文件（这需要几分钟）
  - 用户文件（限制 100 个）
  - Oracle SQL Developer 配置文件检查
  - Slack文件搜索
  - Outlook 下载
  - 机器和用户证书文件
  - Office最近的文件
  - 隐藏的文件和文件夹
  - 具有写入权限的非默认文件夹中的可执行文件
  - WSL 检查
- 活动信息
  - 登录 + 显式登录事件
  - 流程创建事件
  - PowerShell 事件
  - 电源开/关事件
- 附加（较慢）检查
  - LOLBAS 搜索
  - 在默认 WSL 分发中运行**[linpeas.sh](https://raw.githubusercontent.com/carlospolop/privilege-escalation-awesome-scripts-suite/master/linPEAS/linpeas.sh)**