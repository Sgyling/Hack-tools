---
title: Webshell_Generate-支持生成Webshell并且自带免杀!
date: 2024-3-7 18:10:00
tags:
- 渗透工具推荐
categories:
- 工具推荐
---



## Github官网:

https://github.com/cseroad/Webshell_Generate

## Github下载链接:

https://github.com/cseroad/Webshell_Generate/releases/tag/v1.2.4

## 使用说明

### java版本-1.8

```text
jdk-1.8
```

运行命令:

```shell
java -jar XXXXXX.jar
```

直接下载releases版即可

[![image-20220519102709278](https://github.com/cseroad/Webshell_Generate/raw/main/images/Snipaste_2023-02-25_14-29-13.jpg)](https://github.com/cseroad/Webshell_Generate/blob/main/images/Snipaste_2023-02-25_14-29-13.jpg)

## 更新



- 兼容java.util 和 sun.misc 两个包
- jsp部分将404状态码修改为按钮，默认返回200状态码
- 新增AntSword_jspjs无jsp标签webshell
- 新增asmx_Godzilla_CSHAP_ASMX_AES_BASE64 webshel
- 优化部分免杀代码

## 2024.3.2更新



- 优化部分免杀代码
- jsp部分通过OrderClassLoaders类调用defineClass方法

## 参考资料



参考了诸多大佬的文章、工具、思路，如

https://github.com/CrackerCat/JSPHorse

https://github.com/LandGrey/webshell-detect-bypass

https://github.com/czz1233/GBByPass

https://github.com/pureqh/Troy

http://yzddmr6.com/posts/jsp-webshell-upload-bypass/

https://xz.aliyun.com/t/10937

## Star History



[![Star History Chart](https://camo.githubusercontent.com/1946b674268e5a5a34c3db04bd56faefdefe52f5219847f8bc9e274010894fdf/68747470733a2f2f6170692e737461722d686973746f72792e636f6d2f7376673f7265706f733d637365726f61642f5765627368656c6c5f47656e657261746526747970653d44617465)](https://star-history.com/#cseroad/Webshell_Generate&Date)