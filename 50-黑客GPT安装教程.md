---
title: 50-黑客GPT安装教程
date: 2024-04-28 23:33:32
tags:
- 教程
categories:
- 工具推荐
---

# 1x个人使用环境

parrotsec os,可以使用kali

## 2x安装

```shell
#注意:请提前开启VPN
cd Desktop #进入桌面
mkdir hackergpt #创建文件夹
cd hackergpt #进入文件夹
git clone https://github.com/Hacker-GPT/HackerGPT-2.0.git #进行克隆
ls 
cd HakerGPT-2.0 
npm --version #查看是否拥有npm
node --version #查看是否存在node环境
npm install #安装依赖


```

## #如果node版本低于18,请使用下方命令,如果高于18,请跳过

```shell
#sudo apt upgrade #更新
sudo apt remove npm #卸载npm
sudo apt remove nodejs #删除node.js
sudo apt autoremove #清理没用的安装包
cd .. #返回上一层
mkdir node #创建node文件夹
cd node #进入
wget https://nodejs.org/dist/v20.12.2/node-v20.12.2-linux-x64.tar.xz #下载
tar -xvf node-v20.12.2-linux-x64.tar.xz #解压
mv node-v20.12.2-linux-x64 nodejs #把文件夹名字换成node.js20
cd ndoejs #进入
sudo cp -r nodejs/ /usr/local/sbin/ #将文件复制到目录
#为node及npm建立软链接，以便全局使用
sudo ln -s /usr/local/sbin/nodejs/bin/node /usr/local/bin/

sudo ln -s /usr/local/sbin/nodejs/bin/npm /usr/local/bin/
```

```shell
cd ../HackerGPT-2.0/ #返回之前的目录

npm install #安装依赖
```

### #安装必备软件

```shell
sudo apt install docker.io docker docker-compose  #安装容器
#如果出现报错,请先运行:sudo apt install -f 再运行上方命令,如果还不行就安装缺乏的包,例如:sudo apt install python3-cached-property python3-docker python3-dockerpty python3-docopt python3-texttable
#如果还不行,就更新:sudo apt upgrade,更新完再运行上面的命令行
#安装完以后会重新启动,重启后打开终端cd到目录,再运行下面的命令
npm install tailwind-merge --save-dev #安装tailwind-merge模块
#npm run build #清理下缓存 
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)" #安装brew
echo 'eval "$(/home/linuxbrew/.linuxbrew/bin/brew shellenv)"' >> $HOME/.bash_profile #添加到环境变量
eval "$(/home/linuxbrew/.linuxbrew/bin/brew shellenv)" #添加到环境变量
#重启终端
cd Desktop/HackerGpt/HackerGPT-2.0/ #进入路径
brew install supabase/tap/supabase #安装supabase cli
supabase start #启动supabase
#启动后会有一些信息
```

![img](https://pic.imgdb.cn/item/662e5d170ea9cb1403f463fe.png)

## #填写秘钥



#### 1.环境变量

在本地 Chatbot UI 存储库根目录的终端中，运行：

```
cp .env.local.example .env.local
```

通过运行获取所需的值：

```
supabase status
```

注意：使用`API URL`from `supabase status`for`NEXT_PUBLIC_SUPABASE_URL`

现在转到您的`.env.local`文件并填写值。

如果设置了环境变量，它将禁用用户设置中的输入。

#### 2. SQL设置

在第一个迁移文件中，`supabase/migrations/20240108234540_setup.sql`您需要将 2 个值替换为上面获得的值：

- `project_url`（第 53 行）：（`http://supabase_kong_chatbotui:8000`默认）如果您不更改文件`project_id`中的内容，则可以保持不变`config.toml`
- `service_role_key`（第 54 行）：你通过运行获得了这个值`supabase status`

这可以防止存储文件未被正确删除的问题。

## #安装Ollama

运行命令:

```shell
curl -fsSL https://ollama.com/install.sh | sh #需要在同一个终端中运行,路径不变
```

## #本地运行

```shell
npm run chat #运行
```

## #常见错误

```
报错: ⨯ Error: Your project's URL and Key are required to create a Supabase client!

Check your Supabase project's API settings to find these values

https://supabase.com/dashboard/project/_/settings/api
    at RootLayout (./app/[locale]/layout.tsx:113:87)
    at AsyncLocalStorage.run (node:async_hooks:346:14)
    at AsyncLocalStorage.run (node:async_hooks:346:14)
    at Object.apply (./app/[locale]/layout.tsx:230:10)
    at stringify (<anonymous>)
 ⨯ Error: Your project's URL and Key are required to create a Supabase client!

Check your Supabase project's API settings to find these values

https://supabase.com/dashboard/project/_/settings/api
    at RootLayout (./app/[locale]/layout.tsx:113:87)
    at AsyncLocalStorage.run (node:async_hooks:346:14)
    at AsyncLocalStorage.run (node:async_hooks:346:14)
    at Object.apply (./app/[locale]/layout.tsx:230:10)
    at stringify (<anonymous>)
digest: "1122167698"
```

如果出现这种错误,请在.env.local中添加变量:

```shell
NEXT_PUBLIC_SUPABASE_URL=这里写API URL
NEXT_PUBLIC_SUPABASE_ANON_KEY=这里写anon key
#运行supabase status后,可以看到
```

### 运行supabase status后的信息为:

```
         API URL: http://127.0.0.1:54321
     GraphQL URL: http://127.0.0.1:54321/graphql/v1
  S3 Storage URL: http://127.0.0.1:54321/storage/v1/s3
          DB URL: postgresql://postgres:postgres@127.0.0.1:54322/postgres
      Studio URL: http://127.0.0.1:54323
    Inbucket URL: http://127.0.0.1:54324
      JWT secret: super-secret-jwt-token-with-at-least-32-characters-long
        anon key: eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJzdXBhYmFzZS1kZW1vIiwicm9sZSI6ImFub24iLCJleHAiOjE5ODM4MTI5OTZ9.CRXP1A7WOeoJeXxjNni43kdQwgnWNReilDMblYTn_I0
service_role key: eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJzdXBhYmFzZS1kZW1vIiwicm9sZSI6InNlcnZpY2Vfcm9sZSIsImV4cCI6MTk4MzgxMjk5Nn0.EGIM96RAZx35lJzdJsyH-qQwv8Hdp7fsn3W0YpN81IU
   S3 Access Key: 625729a08b95bf1b7ff351a663f3a23c
   S3 Secret Key: 850181e4652dd023b7a98c58ae0d2d34bd487ee0cc3254aed6eda37307425907
       S3 Region: local
```

