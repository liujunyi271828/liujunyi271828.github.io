---
layout: post
title: "TP3页面提示“SQLSTATE[HY000] [1045] Access denied for user 'root'@'localhost'(using password: YES)”错误"
description: "TP框架使用的问题"
date: 2019-06-04
tags: [提高姿势水平]
comments: true
share: true
---


故事背景: 往macOS系统上部署使用了TP3框架的PHP应用, 想方设法让它跑起来, 要不干不出产值, 往后一切都是扯谈.


用的是MAMP一条龙 + MySQL + PHP. 建完库还能拿账号登到库里面也成功跑完了建表脚本. 拿MAMP在HOSTS里做完www.地址.com到项目根目录的映射以后, 他妈打开`www.地址.com:8888`的时候提示“SQLSTATE[HY000] [1045] Access denied for user 'root'@'localhost' (using password: YES)”. 反之, 在WAMP的PhpStudy一条龙上就能跑起来. 总之没按照剧本来. 这可如何是好啊!

也是得益于敝人强烈的上市性, 发现了问题的解决办法:

在`tp3项目根目录/Application/Common/Conf/config.php`下, 原来的服务器地址配置的是: `'DB_HOST' => 'localhost'`, 改成`'DB_HOST' => '127.0.0.1'`即可干出产值.



