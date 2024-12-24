---
title: APK自动反编译工具-androidkiller
date: 2024-3-15 16:18:46
tags:
- 渗透工具推荐
categories:
- 工具推荐
---



```shell
#带插件的androidkiller的github链接:
https://github.com/liaojack8/AndroidKiller #androidkiller
#Apktool|ShakaApktool 简体中文汉化版|APK反编译工具
#ShakaApktool源码：#https://github.com/rover12421/ShakaApktool 作者：rover12421
#apktool源码：https://github.com/iBotPeaches/Apktool  作者：iBotPeaches
#smali/baksmali源码：https://github.com/JesusFreke/smali 作者：JesusFreke
```



# 1-简介

## 	功能简介-工具

```
#文本-编码相互转换
#支持UTF-8,Unicode,ANSI
```

### 	MD5查看器-支持文件和字符串

```
#MD5查看器
MD5-16: 
743267D4B546565A

MD5-32: 
B268D6A7743267D4B546565ABA342DC1

CRC-16: 
3A3C

CRC-32: 
63F5515A

SHA-1: 
D80FC5C3B3E486AD3B0845CE72D35723C44172FD

SHA-224: 
F2FAFE6313E18882CCA2A430A2AC693EB96A0D809B5090B069084194

SHA-256: 
632288A3470DCDE8424B2D029A8B899804346E5912C2BE482085F7F9BDCDFBFC

SHA-384: 
C8540FD141D450EAABDA0F3AABA1EE8BB7DB43ED29943B19C387F69B6368A5F9CCCB8DB2DDEC8445DB9E2C11177D9519

SHA-512: 
23DD1C8EDD75AE38D9390F1495BDEDE95CEEBFB4CF9F03C8FFCA5F66034E7B22B8CA8A23E585B6B160C8FA0E12A1262BB0751F67C678458BD5B67A57520D5A74
```

### 	文件搜索

```
#搜索指定文件
```

### 	自定义功能

```
#支持一些其他工具显示出来
```

### 	APK签名

```
#将APK拖入进去,选择签名,然后执行
#傻瓜式的一键签名
```

### 	APK查壳

```
#直接将APK拖入,然后会自动查询使用的是什么壳
```

### 	伪加密解密

```
#只支持android4.2以前的版本
```

## 	功能简介-android

### 	编译

```
#打开工程后,编译成APK文件
```

### 	批量编译

```
#好几个一起编译
```

### 	插入代码管理器

```
#可以让你直接的修改部分代码
```

### 	apktool管理器

```shell
#就是该工具的支持,可以直接下载最新版
https://github.com/iBotPeaches/Apktool  #apktool.jar包 github链接
```

# 2-使用

```
#直接将apk文件拖进来,会自动反编译
#等待反编译完成
#工程信息-简单信息
#工程管理是源代码
#携带smali的文件夹里面是反编译后的源码
#其他文件夹当中是其他的一些文件.
#apktool.yml当中是一些配置文件,以及导入的一些so文件
#AndroidManifest.xml是一些用到的权限
#lib文件夹中是一些so文件.
```

## 	工程搜索

```
#可以扫描所有的一些字符串,或者说ip地址等等
#可以搜索字符,替换字符
#搜索范围,可以搜索整个项目,或者指定的文件或者文件夹
#支持搜索文件类型,可以选择后缀,或者自己输入后缀
#支持三种字符搜索.
```

