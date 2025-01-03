# wig - WebApp 信息收集器

github:https://github.com/jekyc/wig

wig 是一个 Web 应用程序信息收集工具，它可以识别大量内容管理系统和其他管理应用程序。

应用程序指纹识别基于不同版本 CMS 的已知文件的校验和和字符串匹配。这将为每个检测到的 CMS 及其版本计算一个分数。每个检测到的 CMS 都会与其最可能的版本一起显示。分数计算基于权重和给定校验和的“命中”量。

wig 还会尝试根据“server”和“x-powered-by”标头猜测服务器上的操作系统。wig 中包含一个包含不同操作系统已知标头值的数据库，这允许 wig 猜测 Microsoft Windows 版本以及 Linux 发行版和版本。

## 要求



wig 是用**Python 3**构建的，因此与 Python 2 不兼容。

## 安装



wig 可以从命令行运行或者使用 distuils 安装。

### 命令行



```
$ python3 wig.py example.com
```



### 脚本中的用法



安装

```
$ python3 setup.py install
```



然后可以从任何位置导入假发，如下所示：

```
>>>> from wig.wig import wig
>>>> w = wig(url='example.com')
>>>> w.run()
>>>> results = w.get_results()
```



## 工作原理



wig 的默认行为是识别 CMS，并在检测到 CMS 的版本后退出。这样做是为了限制发送到目标服务器的流量。可以通过设置“-a”标志来覆盖此行为，在这种情况下，wig 将测试所有已知指纹。由于某些应用程序配置不使用文件和资源的默认位置，因此可以让 wig 获取其在扫描期间遇到的所有静态资源。这是通过“-c”选项完成的。“-m”选项会针对所有获取的 URL 测试所有指纹，如果默认位置已更改，这将很有帮助。

## 帮助屏幕



```
usage: wig.py [-h] [-l INPUT_FILE] [-q] [-n STOP_AFTER] [-a] [-m] [-u] [-d]
              [-t THREADS] [--no_cache_load] [--no_cache_save] [-N]
              [--verbosity] [--proxy PROXY] [-w OUTPUT_FILE]
              [url]

WebApp Information Gatherer

positional arguments:
  url              The url to scan e.g. http://example.com

optional arguments:
  -h, --help       show this help message and exit
  -l INPUT_FILE    File with urls, one per line.
  -q               Set wig to not prompt for user input during run
  -n STOP_AFTER    Stop after this amount of CMSs have been detected. Default:
                   1
  -a               Do not stop after the first CMS is detected
  -m               Try harder to find a match without making more requests
  -u               User-agent to use in the requests
  -d               Disable the search for subdomains
  -t THREADS       Number of threads to use
  --no_cache_load  Do not load cached responses
  --no_cache_save  Do not save the cache for later use
  -N               Shortcut for --no_cache_load and --no_cache_save
  --verbosity, -v  Increase verbosity. Use multiple times for more info
  --proxy PROXY    Tunnel through a proxy (format: localhost:8080)
  -w OUTPUT_FILE   File to dump results into (JSON)
```



## 运行示例：



```
$ python3 wig.py example.com

wig - WebApp Information Gatherer


Redirected to http://www.example.com
Continue? [Y|n]:
Scanning http://www.example.com...
_____________________________________________________ SITE INFO _____________________________________________________
IP                        Title                                                                                      
256.256.256.256           PAGE_TITLE                                 
                                                                                                                     
______________________________________________________ VERSION ______________________________________________________
Name                      Versions                                               Type                                
Drupal                    7.38                                                   CMS                                 
nginx                                                                            Platform                            
amazons3                                                                         Platform                            
Varnish                                                                          Platform                            
IIS                       7.5                                                    Platform                            
ASP.NET                   4.0.30319                                              Platform                            
jQuery                    1.4.4                                                  JavaScript                          
Microsoft Windows Server  2008 R2                                                OS                                  
                                                                                                                     
_____________________________________________________ SUBDOMAINS ____________________________________________________
Name                      Page Title                                             IP                                  
http://m.example.com:80   Mobile Page                                            256.256.256.257                     
https://m.example.com:443 Secure Mobil Page                                      256.256.256.258                     
                                                                                                                     
____________________________________________________ INTERESTING ____________________________________________________
URL                       Note                                                   Type                                
/test/                    Test directory                                         Interesting                         
/login/                   Login Page                                             Interesting                         
                                                                                                                     
_______________________________________________ PLATFORM OBSERVATIONS _______________________________________________
Platform                  URL                                                    Type                                
ASP.NET 2.0.50727         /old.aspx                                              Observation                         
ASP.NET 4.0.30319         /login/                                                Observation                         
IIS 6.0                   http://www.example.com/templates/file.css              Observation                         
IIS 7.0                   https://www.example.com/login/                         Observation                         
IIS 7.5                   http://www.example.com                                 Observation                         
                                                                                                                     
_______________________________________________________ TOOLS _______________________________________________________
Name                      Link                                                   Software                            
droopescan                https://github.com/droope/droopescan                   Drupal                              
CMSmap                    https://github.com/Dionach/CMSmap                      Drupal                              
                                                                                                                     
__________________________________________________ VULNERABILITIES __________________________________________________
Affected                  #Vulns                                                 Link                                
Drupal 7.38               5                                                      http://cvedetails.com/version/185744
                                                                                                                     
_____________________________________________________________________________________________________________________
Time: 11.3 sec            Urls: 310                                              Fingerprints: 37580       
```