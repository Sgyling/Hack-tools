---
title: Hexo框架-搭建博客(部署服务器)
date: 2024-3-2 16:14:46
tags:
- 教程
categories:
- 搭建博客
---



# Hexo框架-搭建博客(部署服务器)

## 官方网站:

```
https://hexo.io/  #hexo官网
https://hexo.io/zh-cn/docs/ #hexo文档
https://hexo.io/zh-cn/api/ #Hexo API 页面
https://hexo.io/plugins/ #Hexo 插件页面
https://hexo.io/themes/ #Hexo 主题页面
```



## 什么是 Hexo？

Hexo 是一个快速、简洁且高效的博客框架。Hexo 使用 [Markdown](http://daringfireball.net/projects/markdown/)（或其他标记语言）解析文章，在几秒内，即可利用靓丽的主题生成静态网页。

<iframe src="https://www.youtube.com/embed/PsXWbI2Mqu0" frameborder="0" loading="lazy" allowfullscreen="" style="box-sizing: inherit; margin: 1em 0px; padding: 0px; border: 0px; outline: 0px; font-weight: inherit; font-style: inherit; font-family: inherit; font-size: 15px; vertical-align: baseline;"></iframe>

## 安装

安装 Hexo 只需几分钟时间，若您在安装过程中遇到问题或无法找到解决方式，请 [提交问题](https://github.com/hexojs/hexo/issues)，我们会尽力解决您的问题。

### 安装前提

安装 Hexo 相当简单，只需要先安装下列应用程序即可：

- [Node.js](http://nodejs.org/) (Node.js 版本需不低于 10.13，建议使用 Node.js 12.0 及以上版本)
- [Git](http://git-scm.com/)

如果您的电脑中已经安装上述必备程序，那么恭喜您！你可以直接前往 [安装 Hexo](https://hexo.io/zh-cn/docs/#安装-Hexo) 步骤。

如果您的电脑中尚未安装所需要的程序，请根据以下安装指示完成安装。

### 安装 Git

- Windows：下载并安装 [git](https://git-scm.com/download/win)。
- Mac：使用 [Homebrew](http://mxcl.github.com/homebrew/), [MacPorts](http://www.macports.org/) 或者下载 [安装程序](http://sourceforge.net/projects/git-osx-installer/)。
- Linux (Ubuntu, Debian)：`sudo apt-get install git-core`
- Linux (Fedora, Red Hat, CentOS)：`sudo yum install git-core`

> Mac 用户
>
> 如果在编译时可能会遇到问题，请先到 App Store 安装 Xcode，Xcode 完成后，启动并进入 **Preferences -> Download -> Command Line Tools -> Install** 安装命令行工具。

> Windows 用户
>
> 对于中国大陆地区用户，可以前往 [淘宝 Git for Windows 镜像](https://npmmirror.com/mirrors/git-for-windows/) 下载 git 安装包。

### 安装 Node.js

Node.js 为大多数平台提供了官方的 [安装程序](https://nodejs.org/zh-cn/download/)。对于中国大陆地区用户，可以前往 [淘宝 Node.js 镜像](https://npmmirror.com/mirrors/node/) 下载。

### Node.js官网:

```http
https://nodejs.org/en  #官网
https://nodejs.org/en/download  #下载页面
```

其它的安装方法：

- Windows：通过 [nvs](https://github.com/jasongin/nvs/)（推荐）或者 [nvm](https://github.com/nvm-sh/nvm) 安装。
- Mac：使用 [Homebrew](https://brew.sh/) 或 [MacPorts](http://www.macports.org/) 安装。
- Linux（DEB/RPM-based）：从 [NodeSource](https://github.com/nodesource/distributions) 安装。
- 其它：使用相应的软件包管理器进行安装，可以参考由 Node.js 提供的 [指导](https://nodejs.org/en/download/package-manager/)。

对于 Mac 和 Linux 同样建议使用 nvs 或者 nvm，以避免可能会出现的权限问题。

#### Node.js-ubuntu-Debian系列安装

**Node.js v21.x**：

##### 使用Ubuntu

```
curl -fsSL https://deb.nodesource.com/setup_21.x | sudo -E bash - &&\
sudo apt-get install -y nodejs
node --version #检查node.js版本
npm --version  #检查npm版本
```

##### 以 root 身份使用 Debian

```
curl -fsSL https://deb.nodesource.com/setup_21.x | bash - &&\
apt-get install -y nodejs
```

#### Node.js-centos\radhat系列安装(不支持7)

### RPM 安装说明

Nodesource RPM 包签名密钥可在此处获取：[https ://rpm.nodesource.com/gpgkey/nodesource.gpg.key](https://rpm.nodesource.com/gpgkey/nodesource.gpg.key)

**Node.js v21.x**

##### 作为root用户

```
curl -fsSL https://rpm.nodesource.com/setup_21.x | bash -
yum install -y nodejs
```

##### 没有root权限

```
curl -fsSL https://rpm.nodesource.com/setup_21.x | sudo bash -
yum install -y nodejs
```

> Windows 用户
>
> 使用 Node.js 官方安装程序时，请确保勾选 **Add to PATH** 选项（默认已勾选）

> For Mac / Linux 用户
>
> 如果在尝试安装 Hexo 的过程中出现 `EACCES` 权限错误，请遵循 [由 npmjs 发布的指导](https://docs.npmjs.com/resolving-eacces-permissions-errors-when-installing-packages-globally) 修复该问题。强烈建议 **不要** 使用 root、sudo 等方法覆盖权限

> Linux
>
> 如果您使用 Snap 来安装 Node.js，在 [初始化](https://hexo.io/zh-cn/docs/commands#init) 博客时您可能需要手动在目标文件夹中执行 `npm install`。

### 安装 Hexo

所有必备的应用程序安装完成后，即可使用 npm 安装 Hexo。

建议使用这一条命令

```
$ npm install -g hexo-cli
hexo version #检查hexo版本
```

### 进阶安装和使用

对于熟悉 npm 的进阶用户，可以仅局部安装 `hexo` 包。

```
$ npm install hexo
```

安装以后，可以使用以下两种方式执行 Hexo：

1. `npx hexo <command>`
2. Linux 用户可以将 Hexo 所在的目录下的 `node_modules` 添加到环境变量之中即可直接使用 `hexo <command>`：

```
echo 'PATH="$PATH:./node_modules/.bin"' >> ~/.profile
```

### Node.js 版本限制

如果你坚持使用旧的 Node.js，你可以考虑安装 Hexo 的过去版本。

请注意，我们不提供对过去版本 Hexo 的错误修复。

我们强烈建议永远安装 [最新版本](https://www.npmjs.com/package/hexo?activeTab=versions) 的 Hexo，以及 [推荐的 Node.js 版本](https://hexo.io/zh-cn/docs/#安装前提)。

| Hexo 版本   | 最低版本 (Node.js 版本) | 最高版本 (Node.js 版本) |
| :---------- | :---------------------- | :---------------------- |
| 7.0+        | 14.0.0                  | latest                  |
| 6.2+        | 12.13.0                 | latest                  |
| 6.0+        | 12.13.0                 | 18.5.0                  |
| 5.0+        | 10.13.0                 | 12.0.0                  |
| 4.1 - 4.2   | 8.10                    | 10.0.0                  |
| 4.0         | 8.6                     | 8.10.0                  |
| 3.3 - 3.9   | 6.9                     | 8.0.0                   |
| 3.2 - 3.3   | 0.12                    | 未知                    |
| 3.0 - 3.1   | 0.10 或 iojs            | 未知                    |
| 0.0.1 - 2.8 | 0.10                    | 未知                    |



## hexo-建站

安装 Hexo 完成后，请执行下列命令，Hexo 将会在指定文件夹中新建所需要的文件。

```shell
hexo init <文件夹名称>
cd <文件夹名称>
npm install #安装/初始化
```

新建完成后，指定文件夹的目录如下：

```
.
├── _config.yml
├── package.json
├── scaffolds
├── source
|   ├── _drafts
|   └── _posts
└── themes
```

### _config.yml

网站的 [配置](https://hexo.io/zh-cn/docs/configuration) 信息，您可以在此配置大部分的参数。

https://hexo.io/zh-cn/docs/configuration  #配置链接

编辑配置文件信息



### 配置信息说明

| 参数          | 描述                                                         |
| :------------ | :----------------------------------------------------------- |
| `title`       | 网站标题                                                     |
| `subtitle`    | 网站副标题                                                   |
| `description` | 网站描述                                                     |
| `keywords`    | 网站的关键词。支持多个关键词。                               |
| `author`      | 您的名字                                                     |
| `language`    | 网站使用的语言。对于简体中文用户来说，使用不同的主题可能需要设置成不同的值，请参考你的主题的文档自行设置，常见的有 `zh-Hans`和 `zh-CN`。 |
| `timezone`    | 网站时区。Hexo 默认使用您电脑的时区。请参考 [时区列表](https://en.wikipedia.org/wiki/List_of_tz_database_time_zones) 进行设置，如 `America/New_York`, `Japan`, 和 `UTC` 。一般的，对于中国大陆地区可以使用 `Asia/Shanghai`。 |

### package.json

应用程序的信息。[EJS](https://ejs.co/), [Stylus](http://learnboost.github.io/stylus/) 和 [Markdown](http://daringfireball.net/projects/markdown/) 渲染引擎 已默认安装，您可以自由移除。

```
package.json{
  "name": "hexo-site",
  "version": "0.0.0",
  "private": true,
  "hexo": {
    "version": ""
  },
  "dependencies": {
    "hexo": "^7.0.0",
    "hexo-generator-archive": "^2.0.0",
    "hexo-generator-category": "^2.0.0",
    "hexo-generator-index": "^3.0.0",
    "hexo-generator-tag": "^2.0.0",
    "hexo-renderer-ejs": "^2.0.0",
    "hexo-renderer-stylus": "^3.0.0",
    "hexo-renderer-marked": "^6.0.0",
    "hexo-server": "^3.0.0",
    "hexo-theme-landscape": "^1.0.0"
  }
}
```

### 运行命令

#### #生成静态文件:

```
hexo generat  简写:hexo g
```

| 选项                  | 描述                                                         |
| :-------------------- | :----------------------------------------------------------- |
| `-d`, `--deploy`      | 文件生成后立即部署网站                                       |
| `-w`, `--watch`       | 监视文件变动                                                 |
| `-b`, `--bail`        | 生成过程中如果发生任何未处理的异常则抛出异常                 |
| `-f`, `--force`       | 强制重新生成文件 Hexo 引入了差分机制，如果 `public` 目录存在，那么 `hexo g` 只会重新生成改动的文件。 使用该参数的效果接近 `hexo clean && hexo generate` |
| `-c`, `--concurrency` | 最大同时生成文件的数量，默认无限制                           |

### 运行命令

```
hexo server #运行
```

启动服务器。默认情况下，访问网址为： `http://localhost:4000/`。

| 选项             | 描述                           |
| :--------------- | :----------------------------- |
| `-p`, `--port`   | 重设端口                       |
| `-s`, `--static` | 只使用静态文件                 |
| `-l`, `--log`    | 启动日记记录，使用覆盖记录格式 |

## deploy-部署

```
$ hexo deploy
```

部署网站。

| 参数               | 描述                     |
| :----------------- | :----------------------- |
| `-g`, `--generate` | 部署之前预先生成静态文件 |

该命令可以简写为：

```
$ hexo d
```

## clean-清理缓存

```
$ hexo clean
```

清除缓存文件 (`db.json`) 和已生成的静态文件 (`public`)。

在某些情况（尤其是更换主题后），如果发现您对站点的更改无论如何也不生效，您可能需要运行该命令。











## 更换主题:

链接:https://hexo.io/themes/

主题:https://github.com/Yue-plus/hexo-theme-arknights/blob/main/README.md

### 安装教程:

```shell
#在自己的hexo框架目录下,运行:
git clone https://github.com/Yue-plus/hexo-theme-arknights.git themes/arknights
#安装依赖:
npm install hexo-server hexo-browsersync hexo-renderer-pug --save

#记录名称:hexo-theme-arknights

#剪切 Hexo/themes/arknights/_config.yml到 Hexo 目录下，并重命名为_config.arknights.yml。
cp themes/arknights/_config.yml _config.arknights.yml

#使用vim打开_config.yml,并在文件中找到theme:XXXX   将XXXX更换为:arknights,最后保存



```



## 添加文章:

```
#md文件存放路径:source/_posts/
#默认有一个hello-world.md,记得删除

```



## 在服务器长期运行

### **1.用pm2管理进程让 hexo 博客在服务器后台跑起来**

**1,安装pm2**(建议初学者使用此命令)

```
npm install -g pm2
#高级工程师请使用下方命令
npm install pm2
```

**2,编写一个执行脚本 —— 在博客根目录下创建一个文件 run.js**

```shell
cd /usr/local/src/myblog

vim run.js

##添加如下内容:
const { exec } = require('child_process')
exec('hexo server -s -p 指定端口',(error, stdout, stderr) => {
if(error){
        console.log('exec error: ${error}')
        return
}
console.log('stdout: ${stdout}');
console.log('stderr: ${stderr}');
})
```

**3,使用pm2运行脚本 run.js**

```
cd hexo目录
指令: pm2 start run.js
运行起来后可以使用pm2 show + 进程pid查看后台hexo进行
```

##### 4.提示缺少文件

```shell
#安装文件 缺少啥安装啥
sudo apt-get install powerman linuxptp  pmw wm2 libpod-pom-perl  pms powermanagement-interface gm2 
#实例命令
sudo apt-get install 缺少的文件1 缺少的文件2 缺少的文件3
```

## 自动清理缓存并生成静态文件脚本

依然在根目录运行.

```shell
vim del_old_file.sh

#文件内容:
hexo clean
hexo g
```

# 
