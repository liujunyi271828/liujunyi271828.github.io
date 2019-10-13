---
layout: post
title: "php.ini 位置和重安 Xdebug 还有消除 Cannot load Xdebug - it was already loaded 信息的方法"
description: "记录一下, 省着费老大劲儿才找着."
date: 2019-10-11
tags: [提高姿势水平]
comments: true
share: true
---

> 记录一下, 省着费老大劲儿才找着.

* TOC
{:toc}

更新了一下一条龙软件, 其实这个还好. 主要是手滑把 xdebug.so 给删了😂

操作系统: macOS

## 手滑删掉 xdebug.so 的解决办法

这个会报 “Failed loading Zend extension 'xdebug.so'” 的 *warning*:

![xdebug.so](https://i.ibb.co/WtYzNT1/xdebug-so.png)

能想到的办法就是重装:

通过 `pecl help` 的结果可以知道:

* search 是 Search remote package database
* list 是 List Installed Packages In The Default Channel
* upgrade 是 Upgrade Package
* uninstall 是 Un-install Package
* install 是 Install Package

(和 Homebrew 的 `brew 操作 参数` 的性质差不多)

在之前安装了 Xdebug 但是只是把 xdebug.so `rm` 了的情况下, 直接 `pecl install xdebug` 会提示:

> pecl/xdebug is already installed and is the same as the released version 2.7.2<br/>
> install failed

总之不会覆盖. 所以应该先 `pecl uninstall xdebug`, 再 `pecl install xdebug`. 这样才能重新安装上 Xdebug.

## Homebrew 安装的 PHP 7.3.9 的 php.ini 位置

对于我这个机子, php.ini 的绝对路径是 `/usr/local/etc/php/7.3/php.ini`. 而且我 Homebrew 什么的配置都是很默认的了.

这个事儿是从 PhpStorm 里看的:

![php.ini](https://i.ibb.co/0szjdzS/php-ini.png)

再一个就是 `php -i | grep php.ini` 来找:

![php -i-grep php.ini](https://i.ibb.co/jzKhKXc/php-i-grep.png)

## MAMP PRO 的 php.ini 位置

我的 MAMP PRO 也是默认安的. 一般默认都是给安在 `应用` 目录下.

php.ini 的绝对路径是 `/Applications/MAMP/bin/php/php7.3.8/conf/php.ini`. 

事实上, 只要你在 MAMP PRO 下安装了多个版本的 PHP 语言包:

![mamp-php](https://i.ibb.co/N9HyL9T/php-mamp.png)

那么在每个对应版本 PHP 下面都会有相应的 php.ini (实际情况随自己的 pwd 而作调整):

![tree -CL 3-grep -E "php.ini-php7-php5"](https://i.ibb.co/FqR83xR/tree-grep.png)

再就是可以加个 `-v` 进一步过滤:

![grep-v](https://i.ibb.co/P5RkRVY/grep-v.png)

对 `grep` 用法有疑问的话, 如果安了太长不看 *tldr* 工具的话, 可以 `tldr grep` 看一下. 结果如下:

![tldr-grep](https://i.ibb.co/MZ7wHqH/tldr-grep.png)


## 报 “Cannot load Xdebug - it was already loaded” 的解决办法

这是最近一直都有的问题:

![Cannot load Xdebug - it was already loaded](https://i.ibb.co/Jj7bP3Y/cannot-load-xdebug.png)

需要你找到你相应的 PHP 然后去 php.ini 改. 比如我这个命令行中的环境 PHP 是通过 Homebrew 装的, 那么就是上这个 PHP 对应的 php.ini 里改:

![zend-extension](https://i.ibb.co/T4BK0XW/zend-extension.png) 

我这是为了演示多写了一遍, 那么退出的时候就应该 esc + `:q!` 避免给存上了. 