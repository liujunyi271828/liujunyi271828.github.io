---
layout: post
title: "hosts 文件和 macOS 环境变量配置文件位置与编辑方式"
description: "认识你的系统，认识你的设备，认识你自己。"
date: 2019-09-29
tags: [提高姿势水平]
comments: true
share: true
---

> 认识你的系统，认识你的设备，认识你自己。

* TOC
{:toc}


鉴于我的记忆只有七秒，所以看一下 macOS 下的 hosts 文件和环境变量配置文件的位置和相关属性、编辑方式并记录一下，省着到处查了。

## macOS 下的 hosts 文件

这个一般是在 MAMP 配置虚拟主机信息的时候用，基本不用你去手动维护.

* 作用：The computer file hosts is an operating system file that maps hostnames to IP addresses.
* 可见性：默认可见
* 默认位置：`/etc/hosts`
* 默认编辑方式：需要开启权限狗模式，即 `sudo vi /etc/hosts`


## macOS 下的环境变量配置文件

这个一般是 macOS 下安完什么东西之后配置环境变量的时候用的，macOS 下一般是 `.bash_profile` 用得多。环境变量的话 macOS 可以用的有 MySQL、Ruby、Python 2/3、Laravel、Perl 等。

* 作用：环境变量 PATH，相当于 Windows 的右键计算机→高级→环境变量什么的（记不清了，反正我知道是啥。）
* 可见性：默认隐藏，需要用 `ls -a` 来保证看到
* 默认位置：`~/.bash_profile`、`~/.bashrc`、`~/.profile`、`~/.zshrc`，我不是很清楚具体哪个哪个是和 macOS 下的环境变量相关的，不过家目录下的 `.bash_profile` 肯定是。
* 默认编辑方式：正常 `vi` 编辑就行。