---
layout: post
title: "TP3页面提示“SQLSTATE[HY000] [2002] No such file or directory”错误"
description: "TP3框架使用的问题"
date: 2019-07-08
tags: [提高姿势水平]
comments: true
share: true
---

这个和[TP3页面提示“SQLSTATE[HY000] [1045] Access denied for user 'root'@'localhost'(using password: YES)”错误](https://liujunyi271828.github.io/2019-06-04/tp-framework-1045-error/)比较类似. 可以传送过去看看.

故事背景: 在macOS系统上部署了TP3框架之后动手写PHP应用, 来干出产值.

用的是MAMP一条龙 + MySQL + PHP. 建完库还能拿账号登到库里面也成功跑完了建表脚本. 拿MAMP在HOSTS里做完目录映射以后, 在某某模块下面的一个Controller里写了个操作, 用来`new`一个控制器相应的Model, 结果他妈打开`localhost:8888/tp3项目根目录/index.php/模块/控制器/操作`的时候提示“SQLSTATE[HY000] [2002] No such file or directory”. 让敝人烦躁得一中午没吃饭(今天确实没吃中午饭😂).

应用的tp3应用级配置如下:

![tp3应用配置.png](https://i.loli.net/2019/07/08/5d22c90a2135426530.png)

也是得益于敝人强烈的上市性, 发现了问题的解决办法:

在`tp3项目根目录/Application/Common/Conf/config.php`下, 原来的服务器地址配置的是: `'DB_HOST' => 'localhost'`, 改成`'DB_HOST' => '127.0.0.1'`即可干出产值.

顺便吐个槽, BD之后, 居然有答案是让改mac的`php.ini`文件中的**dll**文件路径的, 不知道你用的是Hackintosh还是Macintosh虚拟机...