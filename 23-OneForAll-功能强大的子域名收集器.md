---
title: OneForAll-功能及其强大的子域名收集器
date: 2024-3-4 17:14:46
tags:
- 渗透工具推荐
categories:
- 工具推荐
---



# OneForAll-一款功能及其强大的子域名收集器

github下载命令:

```
git clone https://github.com/shmilylty/OneForAll.git
```

安装所需要库:

```shell
#如果同时存在python和python3则用下方命令.如果仅有python3则使用pyton -m pip install -r XXXXXX.txt
python3 -m pip install -r requirements.txt
```

[![Build Status](https://camo.githubusercontent.com/28d8eb019184e0c26904d9db5c78d1e12d6cb2075881a7dd9e0f51aef7e1a685/68747470733a2f2f7472617669732d63692e6f72672f73686d696c796c74792f4f6e65466f72416c6c2e7376673f6272616e63683d6d6173746572)](https://travis-ci.org/shmilylty/OneForAll) [![codecov](https://camo.githubusercontent.com/af91a11feeb69e74125ef0f25a24b551829f5d82261b631d885198be740ee00f/68747470733a2f2f636f6465636f762e696f2f67682f73686d696c796c74792f4f6e65466f72416c6c2f6272616e63682f6d61737465722f67726170682f62616467652e737667)](https://codecov.io/gh/shmilylty/OneForAll) [![Maintainability](https://camo.githubusercontent.com/30dcea766e6a01b3b5c96152a1ba9ece563166d0ba9dc79b6d2d4832db0def92/68747470733a2f2f6170692e636f6465636c696d6174652e636f6d2f76312f6261646765732f31323837363638613662346337326166363833652f6d61696e7461696e6162696c697479)](https://codeclimate.com/github/shmilylty/OneForAll/maintainability) [![License](https://camo.githubusercontent.com/6495cd59ec5ee81d9cb19e7968764ffdcc5602965fc59078514555d8f4ee740a/68747470733a2f2f696d672e736869656c64732e696f2f6769746875622f6c6963656e73652f73686d696c796c74792f4f6e65466f72416c6c)](https://github.com/shmilylty/OneForAll/tree/master/LICENSE) [![python](https://camo.githubusercontent.com/f05bb33587273c2995490cff0b4a8252973798fb0fef81ba873a990748fddbda/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f707974686f6e2d332e362b2d626c7565)](https://github.com/shmilylty/OneForAll/tree/master/) [![python](https://camo.githubusercontent.com/9a81975096841a305eebd1a14c923d87da2fe06ff76de01d2baa731231c4f711/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f72656c656173652d76302e342e352d627269676874677265656e)](https://github.com/shmilylty/OneForAll/releases)

👊**OneForAll是一款功能强大的子域收集工具** 📝[English Document](https://github.com/shmilylty/OneForAll/tree/master/docs/en-us/README.md)

[![Example](https://github.com/shmilylty/OneForAll/raw/master/docs/usage_example.svg)](https://github.com/shmilylty/OneForAll/blob/master/docs/usage_example.svg)

## 🚀上手指南



📢 请务必花一点时间阅读此文档，有助于你快速熟悉OneForAll！

<details style="box-sizing: border-box; display: block; margin-top: 0px; margin-bottom: 16px; color: rgb(31, 35, 40); font-family: -apple-system, BlinkMacSystemFont, &quot;Segoe UI&quot;, &quot;Noto Sans&quot;, Helvetica, Arial, sans-serif, &quot;Apple Color Emoji&quot;, &quot;Segoe UI Emoji&quot;; font-size: 16px; font-style: normal; font-variant-ligatures: normal; font-variant-caps: normal; font-weight: 400; letter-spacing: normal; orphans: 2; text-align: start; text-indent: 0px; text-transform: none; widows: 2; word-spacing: 0px; -webkit-text-stroke-width: 0px; white-space: normal; background-color: rgb(255, 255, 255); text-decoration-thickness: initial; text-decoration-style: initial; text-decoration-color: initial;"><summary style="box-sizing: border-box; display: list-item; cursor: pointer;"><b style="box-sizing: border-box; font-weight: var(--base-text-weight-semibold, 600);">🐍安装要求</b></summary></details>

<details style="box-sizing: border-box; display: block; margin-top: 0px; margin-bottom: 16px; color: rgb(31, 35, 40); font-family: -apple-system, BlinkMacSystemFont, &quot;Segoe UI&quot;, &quot;Noto Sans&quot;, Helvetica, Arial, sans-serif, &quot;Apple Color Emoji&quot;, &quot;Segoe UI Emoji&quot;; font-size: 16px; font-style: normal; font-variant-ligatures: normal; font-variant-caps: normal; font-weight: 400; letter-spacing: normal; orphans: 2; text-align: start; text-indent: 0px; text-transform: none; widows: 2; word-spacing: 0px; -webkit-text-stroke-width: 0px; white-space: normal; background-color: rgb(255, 255, 255); text-decoration-thickness: initial; text-decoration-style: initial; text-decoration-color: initial;"><summary style="box-sizing: border-box; display: list-item; cursor: pointer;"><b style="box-sizing: border-box; font-weight: var(--base-text-weight-semibold, 600);">✔安装步骤（git 版）</b></summary></details>

<details style="box-sizing: border-box; display: block; margin-top: 0px; margin-bottom: 16px; color: rgb(31, 35, 40); font-family: -apple-system, BlinkMacSystemFont, &quot;Segoe UI&quot;, &quot;Noto Sans&quot;, Helvetica, Arial, sans-serif, &quot;Apple Color Emoji&quot;, &quot;Segoe UI Emoji&quot;; font-size: 16px; font-style: normal; font-variant-ligatures: normal; font-variant-caps: normal; font-weight: 400; letter-spacing: normal; orphans: 2; text-align: start; text-indent: 0px; text-transform: none; widows: 2; word-spacing: 0px; -webkit-text-stroke-width: 0px; white-space: normal; background-color: rgb(255, 255, 255); text-decoration-thickness: initial; text-decoration-style: initial; text-decoration-color: initial;"><summary style="box-sizing: border-box; display: list-item; cursor: pointer;"><b style="box-sizing: border-box; font-weight: var(--base-text-weight-semibold, 600);">✔安装步骤（docker 版）</b></summary></details>

<details style="box-sizing: border-box; display: block; margin-top: 0px; margin-bottom: 16px; color: rgb(31, 35, 40); font-family: -apple-system, BlinkMacSystemFont, &quot;Segoe UI&quot;, &quot;Noto Sans&quot;, Helvetica, Arial, sans-serif, &quot;Apple Color Emoji&quot;, &quot;Segoe UI Emoji&quot;; font-size: 16px; font-style: normal; font-variant-ligatures: normal; font-variant-caps: normal; font-weight: 400; letter-spacing: normal; orphans: 2; text-align: start; text-indent: 0px; text-transform: none; widows: 2; word-spacing: 0px; -webkit-text-stroke-width: 0px; white-space: normal; background-color: rgb(255, 255, 255); text-decoration-thickness: initial; text-decoration-style: initial; text-decoration-color: initial;"><summary style="box-sizing: border-box; display: list-item; cursor: pointer;"><b style="box-sizing: border-box; font-weight: var(--base-text-weight-semibold, 600);">✨使用演示</b></summary></details>

<details style="box-sizing: border-box; display: block; margin-top: 0px; margin-bottom: 16px; color: rgb(31, 35, 40); font-family: -apple-system, BlinkMacSystemFont, &quot;Segoe UI&quot;, &quot;Noto Sans&quot;, Helvetica, Arial, sans-serif, &quot;Apple Color Emoji&quot;, &quot;Segoe UI Emoji&quot;; font-size: 16px; font-style: normal; font-variant-ligatures: normal; font-variant-caps: normal; font-weight: 400; letter-spacing: normal; orphans: 2; text-align: start; text-indent: 0px; text-transform: none; widows: 2; word-spacing: 0px; -webkit-text-stroke-width: 0px; white-space: normal; background-color: rgb(255, 255, 255); text-decoration-thickness: initial; text-decoration-style: initial; text-decoration-color: initial;"><summary style="box-sizing: border-box; display: list-item; cursor: pointer;"><b style="box-sizing: border-box; font-weight: var(--base-text-weight-semibold, 600);">🧐结果说明</b></summary></details>

<details open="" style="box-sizing: border-box; display: block; margin-top: 0px; margin-bottom: 16px; color: rgb(31, 35, 40); font-family: -apple-system, BlinkMacSystemFont, &quot;Segoe UI&quot;, &quot;Noto Sans&quot;, Helvetica, Arial, sans-serif, &quot;Apple Color Emoji&quot;, &quot;Segoe UI Emoji&quot;; font-size: 16px; font-style: normal; font-variant-ligatures: normal; font-variant-caps: normal; font-weight: 400; letter-spacing: normal; orphans: 2; text-align: start; text-indent: 0px; text-transform: none; widows: 2; word-spacing: 0px; -webkit-text-stroke-width: 0px; white-space: normal; background-color: rgb(255, 255, 255); text-decoration-thickness: initial; text-decoration-style: initial; text-decoration-color: initial;"><summary style="box-sizing: border-box; display: list-item; cursor: pointer;"><b style="box-sizing: border-box; font-weight: var(--base-text-weight-semibold, 600);">🤔使用帮助</b></summary><p dir="auto" style="box-sizing: border-box; margin-top: 0px; margin-bottom: 16px;">命令行参数只提供了一些常用参数，更多详细的参数配置请见<a href="https://github.com/shmilylty/OneForAll/tree/master/config/setting.py" style="box-sizing: border-box; background-color: transparent; color: var(--fgColor-accent, var(--color-accent-fg)); text-decoration: underline; text-underline-offset: 0.2rem;">setting.py</a>，如果你认为有些参数是命令界面经常使用到的或缺少了什么参数等问题非常欢迎反馈。由于众所周知的原因，如果要使用一些被墙的收集接口请先到<a href="https://github.com/shmilylty/OneForAll/tree/master/config/setting.py" style="box-sizing: border-box; background-color: transparent; color: var(--fgColor-accent, var(--color-accent-fg)); text-decoration: underline; text-underline-offset: 0.2rem;">setting.py</a>配置代理，有些收集模块需要提供API（大多都是可以注册账号免费获取），如果需要使用请到<a href="https://github.com/shmilylty/OneForAll/tree/master/config/api.py" style="box-sizing: border-box; background-color: transparent; color: var(--fgColor-accent, var(--color-accent-fg)); text-decoration: underline; text-underline-offset: 0.2rem;">api.py</a>配置API信息，如果不使用请忽略有关报错提示。（详细模块请阅读<a href="https://github.com/shmilylty/OneForAll/tree/master/docs/collection_modules.md" style="box-sizing: border-box; background-color: transparent; color: var(--fgColor-accent, var(--color-accent-fg)); text-decoration: underline; text-underline-offset: 0.2rem;">收集模块说明</a>）</p><p dir="auto" style="box-sizing: border-box; margin-top: 0px; margin-bottom: 16px;">OneForAll命令行界面基于<a href="https://github.com/google/python-fire/" style="box-sizing: border-box; background-color: transparent; color: var(--fgColor-accent, var(--color-accent-fg)); text-decoration: underline; text-underline-offset: 0.2rem;">Fire</a>实现，有关Fire更高级使用方法请参阅<a href="https://github.com/google/python-fire/blob/master/docs/using-cli.md" style="box-sizing: border-box; background-color: transparent; color: var(--fgColor-accent, var(--color-accent-fg)); text-decoration: underline; text-underline-offset: 0.2rem;">使用Fire CLI</a>。</p><p dir="auto" style="box-sizing: border-box; margin-top: 0px; margin-bottom: 16px;"><a href="https://github.com/shmilylty/OneForAll/tree/master/oneforall.py" style="box-sizing: border-box; background-color: transparent; color: var(--fgColor-accent, var(--color-accent-fg)); text-decoration: underline; text-underline-offset: 0.2rem;">oneforall.py</a>是主程序入口，oneforall.py可以调用<a href="https://github.com/shmilylty/OneForAll/tree/master/brute.py" style="box-sizing: border-box; background-color: transparent; color: var(--fgColor-accent, var(--color-accent-fg)); text-decoration: underline; text-underline-offset: 0.2rem;">brute.py</a>，<a href="https://github.com/shmilylty/OneForAll/tree/master/takerover.py" style="box-sizing: border-box; background-color: transparent; color: var(--fgColor-accent, var(--color-accent-fg)); text-decoration: underline; text-underline-offset: 0.2rem;">takerover.py</a>及<a href="https://github.com/shmilylty/OneForAll/tree/master/dbexport.py" style="box-sizing: border-box; background-color: transparent; color: var(--fgColor-accent, var(--color-accent-fg)); text-decoration: underline; text-underline-offset: 0.2rem;">dbexport.py</a>等模块，为了方便进行子域爆破独立出了brute.py，为了方便进行子域接管风险检查独立出了takerover.py，为了方便数据库导出独立出了dbexport.py，这些模块都可以单独运行，并且所接受参数要更丰富一点，如果要单独使用这些模块请参考<a href="https://github.com/shmilylty/OneForAll/tree/master/docs/usage_help.md" style="box-sizing: border-box; background-color: transparent; color: var(--fgColor-accent, var(--color-accent-fg)); text-decoration: underline; text-underline-offset: 0.2rem;">使用帮助</a></p><p dir="auto" style="box-sizing: border-box; margin-top: 0px; margin-bottom: 16px;">❗注意：当你在使用过程中遇到一些问题或者疑惑时，请先到<a href="https://github.com/shmilylty/OneForAll/issues" style="box-sizing: border-box; background-color: transparent; color: var(--fgColor-accent, var(--color-accent-fg)); text-decoration: underline; text-underline-offset: 0.2rem;">Issues</a>里使用搜索找找答案，还可以参阅<a href="https://github.com/shmilylty/OneForAll/tree/master/docs/troubleshooting.md" style="box-sizing: border-box; background-color: transparent; color: var(--fgColor-accent, var(--color-accent-fg)); text-decoration: underline; text-underline-offset: 0.2rem;">常见问题与回答</a>。</p><p dir="auto" style="box-sizing: border-box; margin-top: 0px; margin-bottom: 16px;"><strong style="box-sizing: border-box; font-weight: var(--base-text-weight-semibold, 600);">oneforall.py使用帮助</strong></p><p dir="auto" style="box-sizing: border-box; margin-top: 0px; margin-bottom: 16px;">以下帮助信息可能不是最新的，你可以使用<code style="box-sizing: border-box; font-family: ui-monospace, SFMono-Regular, &quot;SF Mono&quot;, Menlo, Consolas, &quot;Liberation Mono&quot;, monospace; font-size: 13.6px; padding: 0.2em 0.4em; margin: 0px; white-space: break-spaces; background-color: var(--bgColor-neutral-muted, var(--color-neutral-muted)); border-radius: 6px;">python oneforall.py --help</code>获取最新的帮助信息。</p><div class="highlight highlight-source-shell notranslate position-relative overflow-auto" dir="auto" style="box-sizing: border-box; position: relative !important; overflow: auto !important; margin-bottom: 16px; display: flex; justify-content: space-between; background-color: var(--bgColor-muted, var(--color-canvas-subtle));"><pre style="box-sizing: border-box; font-family: ui-monospace, SFMono-Regular, &quot;SF Mono&quot;, Menlo, Consolas, &quot;Liberation Mono&quot;, monospace; font-size: 13.6px; margin-top: 0px; margin-bottom: 0px; overflow-wrap: normal; padding: 16px; overflow: auto; line-height: 1.45; color: var(--fgColor-default, var(--color-fg-default)); background-color: var(--bgColor-muted, var(--color-canvas-subtle)); border-radius: 6px; word-break: normal; min-height: 52px;">python oneforall.py --help</pre><div class="zeroclipboard-container" style="box-sizing: border-box; display: block; animation: auto ease 0s 1 normal none running none;"><clipboard-copy aria-label="Copy" class="ClipboardButton btn btn-invisible js-clipboard-copy m-2 p-0 tooltipped-no-delay d-flex flex-justify-center flex-items-center" data-copy-feedback="Copied!" data-tooltip-direction="w" value="python oneforall.py --help" tabindex="0" role="button" style="box-sizing: border-box; position: relative; display: flex !important; padding: 0px !important; font-size: 14px; font-weight: var(--base-text-weight-medium, 500); line-height: 20px; white-space: nowrap; vertical-align: middle; cursor: pointer; user-select: none; border: 0px; border-radius: 6px; appearance: none; color: var(--fgColor-accent, var(--color-accent-fg)); background-color: transparent; box-shadow: none; transition: color 80ms cubic-bezier(0.33, 1, 0.68, 1) 0s, background-color, box-shadow, border-color; justify-content: center !important; align-items: center !important; margin: var(--base-size-8, 8px) !important; width: var(--control-small-size, 28px); height: var(--control-small-size, 28px);"><svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-copy js-clipboard-copy-icon"><path d="M0 6.75C0 5.784.784 5 1.75 5h1.5a.75.75 0 0 1 0 1.5h-1.5a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-1.5a.75.75 0 0 1 1.5 0v1.5A1.75 1.75 0 0 1 9.25 16h-7.5A1.75 1.75 0 0 1 0 14.25Z"></path><path d="M5 1.75C5 .784 5.784 0 6.75 0h7.5C15.216 0 16 .784 16 1.75v7.5A1.75 1.75 0 0 1 14.25 11h-7.5A1.75 1.75 0 0 1 5 9.25Zm1.75-.25a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-7.5a.25.25 0 0 0-.25-.25Z"></path></svg></clipboard-copy></div></div><div class="highlight highlight-source-shell notranslate position-relative overflow-auto" dir="auto" style="box-sizing: border-box; position: relative !important; overflow: auto !important; margin-bottom: 16px; display: flex; justify-content: space-between; background-color: var(--bgColor-muted, var(--color-canvas-subtle));"><pre style="box-sizing: border-box; font-family: ui-monospace, SFMono-Regular, &quot;SF Mono&quot;, Menlo, Consolas, &quot;Liberation Mono&quot;, monospace; font-size: 13.6px; margin-top: 0px; margin-bottom: 0px; overflow-wrap: normal; padding: 16px; overflow: auto; line-height: 1.45; color: var(--fgColor-default, var(--color-fg-default)); background-color: var(--bgColor-muted, var(--color-canvas-subtle)); border-radius: 6px; word-break: normal; min-height: 52px;">NAME
    oneforall.py - OneForAll帮助信息

SYNOPSIS
    oneforall.py COMMAND <span class="pl-k" style="box-sizing: border-box; color: var(--color-prettylights-syntax-keyword);">|</span> --target=TARGET <span class="pl-k" style="box-sizing: border-box; color: var(--color-prettylights-syntax-keyword);">&lt;</span>flags<span class="pl-k" style="box-sizing: border-box; color: var(--color-prettylights-syntax-keyword);">&gt;</span>

DESCRIPTION
    OneForAll是一款功能强大的子域收集工具

    Example:
        python3 oneforall.py version
        python3 oneforall.py --target example.com run
        python3 oneforall.py --targets ./domains.txt run
        python3 oneforall.py --target example.com --valid None run
        python3 oneforall.py --target example.com --brute True run
        python3 oneforall.py --target example.com --port small run
        python3 oneforall.py --target example.com --fmt csv run
        python3 oneforall.py --target example.com --dns False run
        python3 oneforall.py --target example.com --req False run
        python3 oneforall.py --target example.com --takeover False run
        python3 oneforall.py --target example.com --show True run
    
    Note:
        参数alive可选值True，False分别表示导出存活，全部子域结果
        参数port可选值有<span class="pl-s" style="box-sizing: border-box; color: var(--color-prettylights-syntax-string);"><span class="pl-pds" style="box-sizing: border-box; color: var(--color-prettylights-syntax-string);">'</span>default<span class="pl-pds" style="box-sizing: border-box; color: var(--color-prettylights-syntax-string);">'</span></span>, <span class="pl-s" style="box-sizing: border-box; color: var(--color-prettylights-syntax-string);"><span class="pl-pds" style="box-sizing: border-box; color: var(--color-prettylights-syntax-string);">'</span>small<span class="pl-pds" style="box-sizing: border-box; color: var(--color-prettylights-syntax-string);">'</span></span>, <span class="pl-s" style="box-sizing: border-box; color: var(--color-prettylights-syntax-string);"><span class="pl-pds" style="box-sizing: border-box; color: var(--color-prettylights-syntax-string);">'</span>large<span class="pl-pds" style="box-sizing: border-box; color: var(--color-prettylights-syntax-string);">'</span></span>, 详见config.py配置
        参数fmt可选格式有 <span class="pl-s" style="box-sizing: border-box; color: var(--color-prettylights-syntax-string);"><span class="pl-pds" style="box-sizing: border-box; color: var(--color-prettylights-syntax-string);">'</span>csv<span class="pl-pds" style="box-sizing: border-box; color: var(--color-prettylights-syntax-string);">'</span></span>,<span class="pl-s" style="box-sizing: border-box; color: var(--color-prettylights-syntax-string);"><span class="pl-pds" style="box-sizing: border-box; color: var(--color-prettylights-syntax-string);">'</span>json<span class="pl-pds" style="box-sizing: border-box; color: var(--color-prettylights-syntax-string);">'</span></span>
        参数path默认None使用OneForAll结果目录生成路径

ARGUMENTS
    TARGET
        单个域名(二选一必需参数)
    TARGETS
        每行一个域名的文件路径(二选一必需参数)

FLAGS
    --brute=BRUTE
        s
    --dns=DNS
        DNS解析子域(默认True)
    --req=REQ
        HTTP请求子域(默认True)
    --port=PORT
        请求验证子域的端口范围(默认只探测80端口)
    --valid=VALID
        只导出存活的子域结果(默认False)
    --fmt=FMT
        结果保存格式(默认csv)
    --path=PATH
        结果保存路径(默认None)
    --takeover=TAKEOVER
        检查子域接管(默认False)</pre><div class="zeroclipboard-container" style="box-sizing: border-box; display: block; animation: auto ease 0s 1 normal none running none;"><clipboard-copy aria-label="Copy" class="ClipboardButton btn btn-invisible js-clipboard-copy m-2 p-0 tooltipped-no-delay d-flex flex-justify-center flex-items-center" data-copy-feedback="Copied!" data-tooltip-direction="w" value="NAME
    oneforall.py - OneForAll帮助信息

SYNOPSIS
    oneforall.py COMMAND | --target=TARGET <flags>

DESCRIPTION
    OneForAll是一款功能强大的子域收集工具

    Example:
        python3 oneforall.py version
        python3 oneforall.py --target example.com run
        python3 oneforall.py --targets ./domains.txt run
        python3 oneforall.py --target example.com --valid None run
        python3 oneforall.py --target example.com --brute True run
        python3 oneforall.py --target example.com --port small run
        python3 oneforall.py --target example.com --fmt csv run
        python3 oneforall.py --target example.com --dns False run
        python3 oneforall.py --target example.com --req False run
        python3 oneforall.py --target example.com --takeover False run
        python3 oneforall.py --target example.com --show True run
    
    Note:
        参数alive可选值True，False分别表示导出存活，全部子域结果
        参数port可选值有'default', 'small', 'large', 详见config.py配置
        参数fmt可选格式有 'csv','json'
        参数path默认None使用OneForAll结果目录生成路径

ARGUMENTS
    TARGET
        单个域名(二选一必需参数)
    TARGETS
        每行一个域名的文件路径(二选一必需参数)

FLAGS
    --brute=BRUTE
        s
    --dns=DNS
        DNS解析子域(默认True)
    --req=REQ
        HTTP请求子域(默认True)
    --port=PORT
        请求验证子域的端口范围(默认只探测80端口)
    --valid=VALID
        只导出存活的子域结果(默认False)
    --fmt=FMT
        结果保存格式(默认csv)
    --path=PATH
        结果保存路径(默认None)
    --takeover=TAKEOVER
        检查子域接管(默认False)" tabindex="0" role="button" style="box-sizing: border-box; position: relative; display: flex !important; padding: 0px !important; font-size: 14px; font-weight: var(--base-text-weight-medium, 500); line-height: 20px; white-space: nowrap; vertical-align: middle; cursor: pointer; user-select: none; border: 0px; border-radius: 6px; appearance: none; color: var(--fgColor-accent, var(--color-accent-fg)); background-color: transparent; box-shadow: none; transition: color 80ms cubic-bezier(0.33, 1, 0.68, 1) 0s, background-color, box-shadow, border-color; justify-content: center !important; align-items: center !important; margin: var(--base-size-8, 8px) !important; width: var(--control-small-size, 28px); height: var(--control-small-size, 28px);"><svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-copy js-clipboard-copy-icon"><path d="M0 6.75C0 5.784.784 5 1.75 5h1.5a.75.75 0 0 1 0 1.5h-1.5a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-1.5a.75.75 0 0 1 1.5 0v1.5A1.75 1.75 0 0 1 9.25 16h-7.5A1.75 1.75 0 0 1 0 14.25Z"></path><path d="M5 1.75C5 .784 5.784 0 6.75 0h7.5C15.216 0 16 .784 16 1.75v7.5A1.75 1.75 0 0 1 14.25 11h-7.5A1.75 1.75 0 0 1 5 9.25Zm1.75-.25a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-7.5a.25.25 0 0 0-.25-.25Z"></path></svg></clipboard-copy></div></div></details>

## 🎉项目简介



项目地址：https://github.com/shmilylty/OneForAll

在渗透测试中信息收集的重要性不言而喻，子域收集是信息收集中必不可少且非常重要的一环，目前网上也开源了许多子域收集的工具，但是总是存在以下部分问题：

- **不够强大**，子域收集的接口不够多，不能做到对批量子域自动收集，没有自动子域解析，验证，FUZZ以及信息拓展等功能。
- **不够友好**，固然命令行模块比较方便，但是当可选的参数很多，要实现的操作复杂，用命令行模式就有点不够友好，如果有交互良好，高可操作的前端那么使用体验就会好很多。
- **缺少维护**，很多工具几年没有更新过一次，issues和PR是啥，不存在的。
- **效率问题**，没有利用多进程，多线程以及异步协程技术，速度较慢。

为了解决以上痛点，此项目应用而生，正如其名，我希望OneForAll是一款集百家之长，功能强大的全面快速子域收集终极神器🔨。

目前OneForAll还在开发中，肯定有不少问题和需要改进的地方，欢迎大佬们提交[Issues](https://github.com/shmilylty/OneForAll/issues)和[PR](https://github.com/shmilylty/OneForAll/pulls)，用着还行给个小星星✨吧，目前有一个专门用于OneForAll交流和反馈QQ群👨‍👨‍👦‍👦：:[**824414244**](https://shang.qq.com/wpa/qunwpa?idkey=125d3689b60445cdbb11e4ddff38036b7f6f2abbf4f7957df5dddba81aa90771)（加群验证：信息收集）。

## 👍功能特性



- 收集能力强大

  ，详细模块请阅读

  收集模块说明

  。

  1. 利用证书透明度收集子域（目前有6个模块：`censys_api`，`certspotter`，`crtsh`，`entrust`，`google`，`spyse_api`）
  2. 常规检查收集子域（目前有4个模块：域传送漏洞利用`axfr`，检查跨域策略文件`cdx`，检查HTTPS证书`cert`，检查内容安全策略`csp`，检查robots文件`robots`，检查sitemap文件`sitemap`，利用NSEC记录遍历DNS域`dnssec`，后续会添加NSEC3记录等模块）
  3. 利用网上爬虫档案收集子域（目前有2个模块：`archivecrawl`，`commoncrawl`，此模块还在调试，该模块还有待添加和完善）
  4. 利用DNS数据集收集子域（目前有24个模块：`bevigil_api`, `binaryedge_api`, `bufferover`, `cebaidu`, `chinaz`, `chinaz_api`, `circl_api`, `cloudflare`, `dnsdb_api`, `dnsdumpster`, `hackertarget`, `ip138`, `ipv4info_api`, `netcraft`, `passivedns_api`, `ptrarchive`, `qianxun`, `rapiddns`, `riddler`, `robtex`, `securitytrails_api`, `sitedossier`, `threatcrowd`, `wzpc`, `ximcx`）
  5. 利用DNS查询收集子域（目前有5个模块：通过枚举常见的SRV记录并做查询来收集子域`srv`，以及通过查询域名的DNS记录中的MX,NS,SOA,TXT记录来收集子域）
  6. 利用威胁情报平台数据收集子域（目前有6个模块：`alienvault`, `riskiq_api`，`threatbook_api`，`threatminer`，`virustotal`，`virustotal_api`该模块还有待添加和完善）
  7. 利用搜索引擎发现子域（目前有18个模块：`ask`, `baidu`, `bing`, `bing_api`, `duckduckgo`, `exalead`, `fofa_api`, `gitee`, `github`, `github_api`, `google`, `google_api`, `shodan_api`, `so`, `sogou`, `yahoo`, `yandex`, `zoomeye_api`），在搜索模块中除特殊搜索引擎，通用的搜索引擎都支持自动排除搜索，全量搜索，递归搜索。

- **支持子域爆破**，该模块有常规的字典爆破，也有自定义的fuzz模式，支持批量爆破和递归爆破，自动判断泛解析并处理。

- **支持子域验证**，默认开启子域验证，自动解析子域DNS，自动请求子域获取title和banner，并综合判断子域存活情况。

- **支持子域爬取**，根据已有的子域，请求子域响应体以及响应体里的JS，从中再次发现新的子域。

- **支持子域置换**，根据已有的子域，使用子域替换技术再次发现新的子域。

- **支持子域接管**，默认开启子域接管风险检查，支持子域自动接管（目前只有Github，有待完善），支持批量检查。

- **处理功能强大**，发现的子域结果支持自动去除，自动DNS解析，HTTP请求探测，自动筛选出有效子域，拓展子域的Banner信息，最终支持的导出格式有`txt`, `csv`, `json`。

- **速度极快**，[收集模块](https://github.com/shmilylty/OneForAll/tree/master/collect.py)使用多线程调用，[爆破模块](https://github.com/shmilylty/OneForAll/tree/master/brute.py)使用[massdns](https://github.com/blechschmidt/massdns)，DNS解析速度每秒可解析350000以上个域名，子域验证中DNS解析和HTTP请求使用异步多协程，多线程检查[子域接管](https://github.com/shmilylty/OneForAll/tree/master/takeover.py)风险。

- **体验良好**，各模块都有进度条，异步保存各模块结果。

如果你有其他很棒的想法请务必告诉我！😎

## 🌲目录结构



更多信息请参阅[目录结构说明](https://github.com/shmilylty/OneForAll/tree/master/docs/directory_structure.md)。

本项目[docs](https://github.com/shmilylty/OneForAll/tree/master/docs/)目录下还提供了一些帮助与说明，如[子域字典来源说明](https://github.com/shmilylty/OneForAll/tree/master/docs/dictionary_source.md)、[泛解析判断流程](https://github.com/shmilylty/OneForAll/tree/master/docs/wildcard_judgment.png)。

## 👏用到框架



- [aiohttp](https://github.com/aio-libs/aiohttp) - 异步http客户端/服务器框架
- [beautifulsoup4](https://pypi.org/project/beautifulsoup4/) - 可以轻松从HTML或XML文件中提取数据的Python库
- [fire](https://github.com/google/python-fire) - Python Fire是一个纯粹根据任何Python对象自动生成命令行界面（CLI）的库
- [loguru](https://github.com/Delgan/loguru) - 旨在带来愉快的日志记录Python库
- [massdns](https://github.com/blechschmidt/massdns) - 高性能的DNS解析器
- [records](https://github.com/kennethreitz/records) - Records是一个非常简单但功能强大的库，用于对大多数关系数据库进行最原始SQL查询。
- [requests](https://github.com/psf/requests) - Requests 唯一的一个非转基因的 Python HTTP 库，人类可以安全享用。
- [tqdm](https://github.com/tqdm/tqdm) - 适用于Python和CLI的快速，可扩展的进度条库

感谢这些伟大优秀的Python库！

## 🔖版本控制



该项目使用[SemVer](https://semver.org/)语言化版本格式进行版本管理，你可以参阅[变更记录说明](https://github.com/shmilylty/OneForAll/tree/master/docs/changes.md)了解历史变更情况。

## ⌛后续计划



-  各模块持续优化和完善
-  操作强大交互人性的前端界面实现

更多信息请参阅[后续开发计划](https://github.com/shmilylty/OneForAll/tree/master/docs/todo.md)。

## 🙏贡献



非常热烈欢迎各位大佬一起完善本项目！

## 👨‍💻贡献者



- [Jing Ling](https://github.com/shmilylty)
  - 核心开发

你可以在[贡献者文档](https://github.com/shmilylty/OneForAll/tree/master/docs/contributors.md)中查看所有贡献者以及他们所做出的贡献，感谢他们让OneForAll变得更强大好用。