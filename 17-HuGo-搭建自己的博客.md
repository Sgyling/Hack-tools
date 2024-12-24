---
title: 使用Hugo框架,从0搭建自己的博客
date: 2024-3-27 16:14:46
tags:
- 渗透工具推荐
categories:
- 搭建博客
---



# Hugo-安装博客

## 1x下载

​	简单说明:Windows下需要使用pwershell,不要使用CMD

​	Windows:

```
winget install Hugo.Hugo.Extended #下载Hugo-扩展版
```

​	安装教程连接:

```shell
https://gohugo.io/categories/installation/
#git 命令自行下载
```

## 2x使用

### 	新建项目命令:

```shell
hugo new site quickstart #开启一个名称为quickstart的项目
cd quickstart #进入quickstart
git init #构建
git submodule add https://github.com/theNewDynamic/gohugo-theme-ananke.git themes/ananke #添加Ananke主题
echo "theme = 'ananke'" >> hugo.toml #更换配置
hugo server #启动
```

### 	添加网站内容

```shell
hugo new content posts/my-first-post.md #创建一个新的md文件,未来界面
```

```
#默认内容
+++
title = 'My First Post'
date = 2024-01-14T07:07:07+01:00
draft = true
+++
```

### 	启动服务-站点

```shell
hugo server --buildDrafts #携带草稿启动
hugo server -D #携带草稿启动命令2
```

### 	生成静态文件

```
hugo
```

## 3x安装主题

```shell
#链接
https://github.com/xioyito/NewBee
#在项目文件中,拉下主题
git clone https://github.com/xioyito/NewBee.git themes/NewBee
#复制hugo.toml到根目录
cp NewBee/config-example/hugo.toml hugo.toml
```

#### 	最后演示:

![img](https://pic.imgdb.cn/item/6603e1549f345e8d0369a06e.png)

![](https://pic.imgdb.cn/item/6603e1929f345e8d036b4c31.png)