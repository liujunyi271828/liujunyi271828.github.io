---
layout: post
title: "Navicat Premium 导出数据"
description: "为公司上市霸业而学习 Navicat Premium 使用."
date: 2019-08-20
tags: [提高姿势水平,工具]
comments: true
share: true
---

> 为公司上市霸业而学习 Navicat Premium 使用.

花点儿时间写一下 Navicat 导出数据. 

第一部分是建表. 这个选到某个 table, 然后在那个最右侧的 Sign in 那块儿下面儿有个 DDL, 也就是 Data Definition Language. 把这里面的 MySQL 脚本 command + A 再 command + C 接着 command + V 最后 command + S 就完事儿了.

第二部分是导数据. 点开某个表, 在你表名下面的工具栏的最后一行有个 export, 点进去, All Data 还是 Data in This Page, 然后就到了选导出格式的地方. 

![导出格式](https://upload.cc/i1/2019/08/20/3QqJod.png)

如果你没啥特殊需要的话, 就选 *.sql 吧...至于 *.csv 啥的, 我觉得是 MicroSoft SQL Server 用的, 不过具体它是不是用的 csv 我也不清楚, 我只是会安 SQL Server😂 

扯远了, 要是你选 *.txt 的话, Navicat Premium 并不会给你生成 Data Manipulation Language 的 SQL 语句的文本版, 相反它会给你个 txt 版的表格, 拿来看看还行, 实战的话并没有什么卵用😂 

后面要不要加列名那个, 可加可不加.

