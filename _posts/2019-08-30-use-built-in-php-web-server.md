---
layout: post
title: "使用内置 PHP 服务器"
description: "为节省电脑资源创造更多产值而学习内置 PHP 服务器使用."
date: 2019-08-30
tags: [提高姿势水平,工具]
comments: true
share: true
---

> 为节省电脑资源创造更多产值而学习内置 PHP 服务器使用.

我这是在 mac 上跑的. 别的平台上自行变通吧. 不过说实话我觉着应该没啥好变通的空间...

开 MAMP Pro 以后感觉内存飙升, 想想反正我也不专门拿 MAMP Pro 看数据库, 我就还是先拿 PHP 的内置服务器跑吧...

先打开终端, 输入 `php -h`, 看看都有什么:

```
Usage: php [options] [-f] <file> [--] [args...]
   php [options] -r <code> [--] [args...]
   php [options] [-B <begin_code>] -R <code> [-E <end_code>] [--] [args...]
   php [options] [-B <begin_code>] -F <file> [-E <end_code>] [--] [args...]
   php [options] -S <addr>:<port> [-t docroot] [router]
   php [options] -- [args...]
   php [options] -a

  -a               Run as interactive shell
  -c <path>|<file> Look for php.ini file in this directory
  -n               No configuration (ini) files will be used
  -d foo[=bar]     Define INI entry foo with value 'bar'
  -e               Generate extended information for debugger/profiler
  -f <file>        Parse and execute <file>.
  -h               This help
  -i               PHP information
  -l               Syntax check only (lint)
  -m               Show compiled in modules
  -r <code>        Run PHP <code> without using script tags <?..?>
  -B <begin_code>  Run PHP <begin_code> before processing input lines
  -R <code>        Run PHP <code> for every input line
  -F <file>        Parse and execute <file> for every input line
  -E <end_code>    Run PHP <end_code> after processing all input lines
  -H               Hide any passed arguments from external tools.
  -S <addr>:<port> Run with built-in web server.
  -t <docroot>     Specify document root <docroot> for built-in web server.
  -s               Output HTML syntax highlighted source.
  -v               Version number
  -w               Output source with stripped comments and whitespace.
  -z <file>        Load Zend extension <file>.

  args...          Arguments passed to script. Use -- args when first argument
                   starts with - or script is read from stdin

  --ini            Show configuration file names

  --rf <name>      Show information about function <name>.
  --rc <name>      Show information about class <name>.
  --re <name>      Show information about extension <name>.
  --rz <name>      Show information about Zend extension <name>.
  --ri <name>      Show configuration for extension <name>.

```


看到 `php [options] -S <addr>:<port> [-t docroot] [router]` 这句了吗? 就是当个 PHP 内置服务器的话, 也没什么可 options 的, 所以 `[options]` 就省了; `<addr>` 的话, 在你自己机器跑的话就是 `localhost` 或 `127.0.0.1`, 如果用的 mac 的话我觉着还是 `127.0.0.1` 好些, 能保证肯定好用不出事儿; `<port>` 就选个正常点儿的就行, 别写个什么 21/22/23 之类的知名端口(当然 mac 好像用不着 23, 但还是应该规避风险), 0~1024 照理都别用, 3306 也别用😂; `[-t docroot]` 的话还是要加的, 这个就是你的文档根目录, 也就是所谓的服务器的根目录位置; `[router]` 是路由, 好像一般情况也不用😂

所以总的来说, 一个能用的命令大概就是像这样:

```bash
php -S 127.0.0.1:8888 -t /Applications/MAMP/htdocs/
```


![内置服务器运行效果.png](https://i.loli.net/2019/08/30/CoRTivaZmX3dhWp.png)


那么问题来了, 怎么样停掉服务器服务呢, 这就不用我废话了, 用过 Linux/macOS 的旁友应该都能猜到.