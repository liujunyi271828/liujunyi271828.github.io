---
layout: post
title: "macOS上配置环境变量"
description: "记录下来, 省着一遍遍查..."
date: 2019-06-20
tags: [提高姿势水平]
comments: true
share: true
---

> 记录下来, 省着一遍遍查...

Windows的由于目前不怎么用, 就不写了, 等用到的时候再说.

目前关于Windows配置环境变量有印象的是右键计算机, 有个高级 → 环境变量之类的东西.

macOS的话, `echo $PATH`是查看当前应用的全部环境变量值; `sudo vi ~/.bash_profile`是编辑, 至于后面怎么改就是每个人自个儿的事儿了. 完事儿之后esc + `:wq`存一下即可.

最后再`source ~/.bash_profile`让命令生效. 否则也是木有什么卵用的...

当然了, 除`~/.bash_profile`外, 据说环境变量配置文件还有`~/.zshrc`、`~/.bashrc`. 这个到时候就顺着上面的随机应变了.