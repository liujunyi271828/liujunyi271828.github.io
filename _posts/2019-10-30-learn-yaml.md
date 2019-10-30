---
layout: post
title: "关于 YAML"
description: "为振兴喜瑞斯而学习 YAML."
date: 2019-10-30
tags: [提高姿势水平,工具]
comments: true
share: true
---

此前看了一会儿 Symfony, 跑 [它的第一个例子](https://symfony.com/doc/master/page_creation.html#creating-a-page-route-and-controller) 的时候就崩了, 提示你:

> An exception has been thrown during the rendering of a template ("The file "Symfony项目根目录/config/routes.yaml" does not contain valid YAML in Symfony项目根目录/config/routes.yaml (which is loaded in resource "Symfony项目根目录/config/routes.yaml").").

检查了两遍代码, 发现只是因为用了 tab 缩进. 不了解的话比较难发现这个问题, 也是福至心灵想到的.

之前找过 YAML 的资源.<br/>

* 官网: [The Official YAML Web Site](https://yaml.org);
* 教程: [YAML Ain’t Markup Language (YAML™) Version 1.2: 3rd Edition, Patched at 2009-10-01](https://yaml.org/spec/1.2/spec.html). 
* 阮一峰老师的中文版简介: [YAML 语言教程](http://www.ruanyifeng.com/blog/2016/07/yaml.html).

阮一峰老师的中文版简介我大概看了一下. 看的时候都是拿 YAML 和 JSON 进行比对. 关于使用 YAML 的要点个人总结如下, 以后有什么想到的再补充: 

* 注意用空格进行缩进, 而非使用 tab.
* YAML 的部分是可以在 GFM 的 Markdown 文件中解析为表格的, 但是在我的这个 Markdown 编辑器中是解析不了的.