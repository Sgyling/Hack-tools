```
软件名称：FuzzDomain
源码地址：https://github.com/Chora10/FuzzDomain
下载地址：https://pan.baidu.com/s/1o8bMaca  密码：is5f
官方博客：http://www.ms509.com/
作者：	Chora
----------------------------------------------------------------------------------------------------------
免责声明：
本工具仅限于安全研究与教学使用，用户使用本工具所造成的所有后果，由用户承担全部法律及连带责任！作者不承担任何法律及连带责任。
----------------------------------------------------------------------------------------------------------
FuzzDomain是CDomain的域名爆破模块
----------------------------------------------------------------------------------------------------------
爆破原理：
爆破的原理其实是通过枚举域名的A记录的方式来实现的

泛解析如果爆破：
首先的访问一个随机并不存在的域名chorashishuaige.xx.com，记录其泛解析到的IP地址。
然后通过字典或者自定义规则的方式枚举域名的A记录，并与最开始的chorashishuaige.xx.com的A记录做对比，不同的则是存在的域名，也就是在用的域名。

如何防御：
并没有真正意义上的防御方案，只能说增大域名爆破的难度。可以使用泛解析配合DNS轮询的方式，即访问一个随机不存在的域名chorashishuaige.xx.com会得到一组IP，访问另一个不存在的域名又会得到另外一组IP，
这样就会给域名爆破工具带来误报，当然域名爆破工具完全可以先多次枚举随机域名，将得到的IP组保存在集合里，然后再进行对比，如果枚举到的域名A记录不在该集合里，则是存在的域名，也就是在用的域名。

特色:
一、有的厂商喜欢使用mxxx.xx.com有的厂商喜欢使用xxx-o2o.xx.com，这个时候想要提高爆破效率，就可以使用{fuzz}代替xxx，即{fuzz}xxx.xx.com或者{fuzz}-o2o.xx.com的方式来在指定位置进行爆破
二、比如有一个6级域名test.m.esf.db.house.xx.com，如果不支持循环遍历，则需要先爆破xx.com，爆破出house.xx.com再爆破db.house.xx.com依此类推爆破到test.m.esf.db.house.xx.com，每一步都需要手动来爆破，效率太低了
这个时候如果支持循环爆破，只需要填入xx.com，就会自动遍历到指定层次，或者遍历到没有域名为止。
三、大量的DNS请求会造成网络卡顿，特别是挂机循环爆破几天的情况下可能会影响到同事的网络，这个时候可以先暂停等后续再进行爆破。

使用方法：
可以导入自己的字典进行爆破，也可以自己定义规则进行爆破。
层次选项即为要遍历多少层的意思，比如从xx.com开始遍历，遍历到test.m.esf.db.house.xx.com为5层，当然不需要人进行计算，那样就太麻烦了
直接可以写大于5层的数，比如10层，如果在遍历到第五层没有新的域名出现，则会自动停止。
爆破二级域名使用的是字典或者规则，爆破三级及以下使用的是字典2或者规则2。
开始功能即为使用字典或者规则进行二级域名的爆破，然后使用字典2或者规则2一直遍历到没有发现新的域名或者指定的层次为止。
遍历功能首先要导入或者添加要遍历的域名(支持带{fuzz}的域名)，使用字典2或者规则2一直遍历到没有发现新的域名或者指定的层次为止。
```

***\*0x01 工具介绍\****

子域名爆破神器，需要java环境。

***\*0x02 安装与使用\****
```
  #下载完成后,是一个文件夹
  #从终端打开
  java -jar FuzzDomain.jar
```

一、输入域名

![img](https://mmbiz.qpic.cn/sz_mmbiz_png/8H1dCzib3UibticFw0wQxBZIxQjDdlibVPfTjMvdhq63W3VicA0t2b3wgVic3hVRn6vEcTzJibDpj3e1m0zic8HxwoWcvQ/640?wx_fmt=png&from=appmsg)

二、选择字典，点击浏览，导入字典，然后点击开始

![img](https://mmbiz.qpic.cn/sz_mmbiz_png/8H1dCzib3UibticFw0wQxBZIxQjDdlibVPfTOW3nGYEIATmzanRmxgNq7CBWwSdlR0xVoKESxicxtzh72ZcJmQh1rPw/640?wx_fmt=png&from=appmsg)

三、右击，导出当前域名

![img](https://mmbiz.qpic.cn/sz_mmbiz_png/8H1dCzib3UibticFw0wQxBZIxQjDdlibVPfTr3ickRJFmibSHwl6wXGVQg34xuKwKyNSJQJ2xUAuyOlibriaUbGbBjDPCw/640?wx_fmt=png&from=appmsg)

