# dnsenum-一款强大的域名信息收集工具

## 简介

DNSenum是一款用于枚举目标域名系统（DNS）信息的强大工具，它能够帮助渗透测试人员、安全研究人员和系统管理员收集与目标域名相关的各种信息。以下是DNSenum的基本使用方法：

### 一、安装DNSenum

- **对于Kali Linux用户**：Kali Linux默认安装了dnsenum，因此无需额外安装。

- 对于Parrot Linux 用户:Parrot Linux默认安装了dnsenum，因此无需额外安装

- 对于:Arch Linux 用户: sudo pacman -Sy dnsenum 

- 对于:Blackarch 用户 :自带

- **对于其他Linux发行版或Windows用户**：可能需要从源代码编译或查找适用于自己系统的预编译版本进行安装。安装方法可能因系统而异，建议参考官方文档或社区提供的教程。

  

  ## 二、基本使用

  1. **打开命令行或终端**：在Kali Linux或其他支持DNSenum的操作系统上，打开命令行或终端界面。

  2. **执行DNSenum命令**：在命令行或终端中输入`dnsenum`命令，后跟目标域名，即可开始枚举过程。例如：

     ```
     dnsenum example.com
     ```

     这条命令会启动DNSenum，并尝试收集关于`example.com`域名的各种信息。

     

     ## 三、常用参数

     ### 版本及基本用法

     

     - **版本**：`VERSION:1.2.6`
     - **基本用法**：`dnsenum [Options] <domain>`，即通过指定不同选项来对给定的域名进行相关操作。

     ### 通用选项（GENERAL OPTIONS）

     

     - **`--dnsserver <server>`**：指定使用该 DNS 服务器来进行 A、NS 和 MX 查询。
     - **`--enum`**：快捷选项，等同于`--threads 5 -s 15 -w`。
     - **`-h, --help`**：打印帮助信息，显示该工具的使用说明。
     - **`--noreverse`**：跳过反向查找操作。
     - **`--nocolor`**：禁用 ANSI 色彩输出，使输出内容不带有彩色显示效果。
     - **`--private`**：在文件`domain_ips.txt`末尾展示并保存私有 IP 地址。
     - **`--subfile <file>`**：将所有有效的子域名写入到指定的文件中。
     - **`-t, --timeout <value>`**：设置 TCP 和 UDP 超时时间（单位为秒），默认值是 10 秒。
     - **`--threads <value>`**：指定执行不同查询的线程数量。
     - **`-v, --verbose`**：启用详细模式，会展示所有操作的进展情况以及错误消息。

     ### 谷歌抓取选项（GOOGLE SCRAPING OPTIONS）

     

     - **`-p, --pages <value>`**：指定处理谷歌搜索页面的数量，用于抓取域名时，默认是 5 页，不过必须同时指定`-s`开关。
     - **`-s, --scrap <value>`**：设定从谷歌抓取的最大子域名数量，默认值是 15 个。

     ### 暴力破解选项（BRUTE FORCE OPTIONS）

     

     - **`-f, --file <file>`**：从指定文件中读取子域名来进行暴力破解，该选项优先级高于默认的`dns.txt`文件。

     - `-u, --update <a|g|r|z>`

       ：使用有效的子域名来更新通过

       ```
       -f
       ```

       开关指定的文件，具体更新方式有以下几种：

       - **`a (all)`**：使用所有结果进行更新。
       - **`g`**：仅使用谷歌抓取的结果进行更新。
       - **`r`**：仅使用反向查找结果进行更新。
       - **`z`**：仅使用区域传输结果进行更新。

     - **`-r, --recursion`**：对子域名进行递归操作，对所有发现的有 NS 记录的子域名进行暴力破解。

     ### WHOIS 网络范围选项（WHOIS NETRANGE OPTIONS）

     

     - **`-d, --delay <value>`**：设定在进行 WHOIS 查询时等待的最大秒数，该值随机定义，默认是 3 秒。
     - **`-w, --whois`**：对 C 类网络范围执行 WHOIS 查询，不过需注意这可能会产生非常大的网络范围，且进行反向查找会花费大量时间。

     ### 反向查找选项（REVERSE LOOKUP OPTIONS）

     

     - **`-e, --exclude <regexp>`**：从反向查找结果中排除匹配正则表达式的 PTR 记录，在处理无效主机名时很有用。

     ### 输出选项（OUTPUT OPTIONS）

     

     - **`-o --output <file>`**：以 XML 格式输出内容，输出结果可导入到 MagicTree（网址：[www.gremwell.com](https://www.gremwell.com/)）中。

     



DNSenum提供了丰富的命令行参数，以满足不同用户的需求。以下是一些常用的参数及其说明：

- `--dnsserver <server>`：指定用于A、NS和MX查询的DNS服务器。这有助于绕过本地DNS服务器的限制或查询特定DNS服务器上的记录。
- `--enum`：这是一个快捷选项，相当于设置了一组默认的查询参数（如线程数、抓取页面数等），以快速启动枚举过程。
- `--noreverse`：跳过反向查询操作，以提高枚举效率。
- `--file <file>`：从指定文件中读取子域名列表，用于执行暴力破解或进一步查询。
- `--output <file>`：将枚举结果输出到指定文件，方便后续分析和处理。
- `--verbose`：详细输出模式，显示所有进度和错误消息。这有助于了解枚举过程中的详细情况，但可能会产生大量输出。







## 4.常用命令

```
#默认扫描 
dnsenum baidu.com
#子域名+dns扫描
dnsemu -w baidu.com

```

