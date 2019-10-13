---
layout: post
title: "WebStorm 选中所有相同单词"
description: "为创造更多产值而学习 WebStorm 使用."
date: 2019-09-27
tags: [提高姿势水平]
comments: true
share: true
---

> 为创造更多产值而学习 WebStorm 使用.

用的是 2016.3.3 的 WebStorm, 最开始是写了一堆绝对路径名放到模板里来复用, 后来项目名改了(pseudo → fake), 但是选中这个项目目录中的一个目录环节对应的单词想 refactor 没成功. 后来仔细看了一下, 知道该怎么干了.

举个例子, 比如你要把一堆 `pseudo-project` 给改成 `fake-project`, 那么你就先选中某个 `pseudo-project` 然后 command + F 查找到所有的 `pseudo-project`, 然后点那个 Select All Occurrences, 这样就选中到所有的 `pseudo-project`:

![selectAll.png](https://i.loli.net/2019/09/27/KCMAhSyJoLWj2On.png)

然后是逐字符移动光标, 把所有的 `pseudo` 都给改成 `fake` 就完事儿了. 虽说目前不知道怎么批量选中, 不过现在也能用.

再就上网查了一下, command shift F 或是 command shift R 似乎能完全起到我期望的作用:


<img src="https://i.ibb.co/Ny62RVK/commandshiftf.png" alt="commandshiftf" border="0">

<img src="https://i.ibb.co/Rg1D49k/commandshiftr.png" alt="commandshiftr" border="0">


没在 PhpStorm、IntelliJ IDEA CE 上试过, 不过我觉着应该也能这么操作.


