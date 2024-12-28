# 数据库提权工具-MDUT-Extend

github:https://github.com/DeEpinGh0st/MDUT-Extend-Release

## Ⅰ前言

经过几个月的缝缝补补,`MDUT-Extend`终于迎来了`v1.2.0`的累积更新. 此次的更新主要着重于修复师傅们提出的BUG和相关优化建议以及对`Postgresql`和`Mssql`上的功能增强.

**Here we go**

![img](https://mmbiz.qpic.cn/mmbiz_png/KGyt5Iecd5FdNbgG2ran6WdRiaUlTGl6IVrq5MyxPjRPRsts3vSRe2y6yIMkibdTq7IY2U4uXtVKkHTvia9ziaUMsg/640?wx_fmt=png&from=appmsg)

**注意: 从此版本开始全面取消了对Http隧道模式的支持,如果师傅们需要此功能那么请不要使用此版本**

## Ⅱ更新内容

### Postgresql文件管理重写

在此版本中对`postgresql`中的文件管理功能进行重写和增强 

现在`postgresql`的文件管理支持使用`PG FUNC`和`CVE`两种方式,两种方式均支持`windows`和`linux`

其中`PG FUNC`依赖postgresql内置的文件管理函数

![img](https://mmbiz.qpic.cn/mmbiz_png/KGyt5Iecd5FdNbgG2ran6WdRiaUlTGl6Iu8OxyTtgCFl8radibhbg2cqmiaYvicsRoVy0h7aGvVib0fto6tgaHR7zmA/640?wx_fmt=png&from=appmsg)

由于内置函数的限制,此方式只能获取基础的文件名,并且此方式不支持读取中文目录``

`CVE`方式则使用`CVE-2019-9193`进行读取和管理

**Windows**

![img](https://mmbiz.qpic.cn/mmbiz_png/KGyt5Iecd5FdNbgG2ran6WdRiaUlTGl6Iria7eHM6Uycwj0nIKsiaicWiaLRdJK057WZLsD9bkcxfcg1q76B2cFseRQ/640?wx_fmt=png&from=appmsg)

**Linux**

![img](https://mmbiz.qpic.cn/mmbiz_png/KGyt5Iecd5FdNbgG2ran6WdRiaUlTGl6IW0gKoGbUeG8w1KVAGlcWYicNnT5MD2QLE50SZbcJ0G4e23s9DmTzxTw/640?wx_fmt=png&from=appmsg)

相对于`PG FUNC`使用`CVE`方式能获取较为详细的目录和文件信息，同时也支持读取中文目录

![img](https://mmbiz.qpic.cn/mmbiz_png/KGyt5Iecd5FdNbgG2ran6WdRiaUlTGl6IZP3qqLWRKuyOw3wPVD2xibdqhuDbs1xDIJSSR8sm6ib7flMHekm6F0Cg/640?wx_fmt=png&from=appmsg)

### Postgresql新增CVE方式读取文件

在postgresql文件管理右键菜单中新增了`读取文件(CVE)`选项,该选项主要弥补无法读取含有中文字符和内容的文件问题

![img](https://mmbiz.qpic.cn/mmbiz_png/KGyt5Iecd5FdNbgG2ran6WdRiaUlTGl6IEOHpEoQ4iaakBicEEEw68HJib3OKsMIqXJ4v3ohT2fiaTlYhhSRo5SLyXw/640?wx_fmt=png&from=appmsg)

![img](https://mmbiz.qpic.cn/mmbiz_png/KGyt5Iecd5FdNbgG2ran6WdRiaUlTGl6IKe9No7Wez28nN5ykzvVyicA4SJFicmgmzQdIurOd7BRZ4ZtYtEUk3JjA/640?wx_fmt=png&from=appmsg)

### 优化Postgresql命令执行问题

**@badboycxcc**

在上一版本中,针对postgresql命令执行`UTF-8`报错问题只对windows情况进行了处理(#14).

此版本中对该问题进行了优化.选项由`direct`更改为`base64`

![img](https://mmbiz.qpic.cn/mmbiz_png/KGyt5Iecd5FdNbgG2ran6WdRiaUlTGl6ImhQbZic4YxPNPEwOky6B4caaq2zOdR4kEGulOR1skicC4nNxqagMtJ2w/640?wx_fmt=png&from=appmsg)

### 修复Mssql下载文件大小问题

**@Conan924**

在原版和之前版本中,使用mssql下载文件时只能保存前10kb的数据(#15).

此版本中对该BUG进行了修复

![img](https://mmbiz.qpic.cn/mmbiz_png/KGyt5Iecd5FdNbgG2ran6WdRiaUlTGl6IochGsaxTjU71Bu1utjkNoEKmsphQe5NW7uJuF96Yic5Z0icfYobjBpRA/640?wx_fmt=png&from=appmsg)

### 新增Mssql提权对Godpotato支持

此版本中对Mssql的CLR命令执行功能进行了增强,添加了`Godpotato`提权方式

![img](https://mmbiz.qpic.cn/mmbiz_png/KGyt5Iecd5FdNbgG2ran6WdRiaUlTGl6IiaItNmmJHqkzziacsEArVb2VCLk1qIYnCLphiaZ68wqFV3MZWHdvRdibqg/640?wx_fmt=png&from=appmsg)

### 修复Redis命令执行问题

此版本修复了之前redis执行命令时回显存在多余空格和中文字符乱码的问题

需配合最新版本的redis模块文件使用

![img](https://mmbiz.qpic.cn/mmbiz_png/KGyt5Iecd5FdNbgG2ran6WdRiaUlTGl6Iicmx8iaWFaXTh6LSmaRUeZjKnXSUguYhkArSw98kTHYDMGm7aXHDxg8Q/640?wx_fmt=png&from=appmsg)

### 新增Redis主从同步前数据备份

**@枇杷哥**

新增在利用redis主从同步前,对redis中的内存数据同步到磁盘.以防数据丢失

![img](https://mmbiz.qpic.cn/mmbiz_png/KGyt5Iecd5FdNbgG2ran6WdRiaUlTGl6ILh14JCKhvnPd1EtREzNYad0N9IwbTTy1dw4qInQ0z8WZEKmOiaQenibw/640?wx_fmt=png&from=appmsg)

### 其他

- 修复配置文件刷新问题
- 修复postgresql文件删除失败问题
- UI界面调整