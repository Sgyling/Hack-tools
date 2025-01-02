[![图像-20240811182803001](https://github.com/P001water/P1finger/raw/master/img/image-20240811182803001.png)](https://github.com/P001water/P1finger/blob/master/img/image-20240811182803001.png)

### P1finger红队行动下重点资产指纹识别工具

github:https://github.com/P001water/P1finger

------

1. 单个目标研究

```
P1finger -u [target]
```



[![图像-20240925112824861](https://github.com/P001water/P1finger/raw/master/img/image-20240925112824861.png)](https://github.com/P001water/P1finger/blob/master/img/image-20240925112824861.png)

1. 多目标探索

```
P1finger -uf [target file] //-uf 指定url文件
```



[![图像-20240925112939825](https://github.com/P001water/P1finger/raw/master/img/image-20240925112939825.png)](https://github.com/P001water/P1finger/blob/master/img/image-20240925112939825.png)

1. 输出到 Excel 表格文件

```
P1finger -uf [target file] -o //-o 参数输出到文件
```



[![图像-20240925021744468](https://github.com/P001water/P1finger/raw/master/img/image-20240925021744468.png)](https://github.com/P001water/P1finger/blob/master/img/image-20240925021744468.png)

1. 推荐建筑师

默认只读取指定目录下.yaml后缀的文件

```
P1finger.exe -uf D:\tools_dev\Go\P1finger\urls.txt -fd D:/tools_dev/Go/P1finger
```



1. socks5 代理

```
P1finger.exe -uf D:\tools_dev\Go\P1finger\show.txt -socks 127.0.0.1:4781
```



1. http 代理

```
P1finger.exe -uf D:\tools_dev\Go\P1finger\show.txt -httpproxy 127.0.0.1:4781
```



# 问题规范



[一款红队重点资产指纹识别工具 - P1finger.exe (qq.com)](https://mp.weixin.qq.com/s?__biz=MzkwNjY0MzIyNw==&mid=2247483705&idx=1&sn=9205adf34b53b9f9c8f09c99e246c44e&chksm=c0e4134df7939a5b5b58399bdf6e3d591fa51968a6e350c5930f2dfee3f600b34d6ba7444c9e#rd)

由于工具仍在测试阶段，欢迎提出问题，问题标题建议如下

[指纹未识别] [未识别系统名]

> 例如。 [指纹未识别] [ phpcms ]

[指纹误报] [未识别系统名]

> [指纹报] [xxx-OA]

[软件bug] [bug类型]

> 例如[软件bug] [报错xxx]