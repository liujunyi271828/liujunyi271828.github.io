---
layout: post
title: "关掉肾接入腰子 Book (Pro) 的自动同步"
description: "电脑应该多放有用的东西."
date: 2019-11-04
tags: [提高姿势水平,工具]
comments: true
share: true
---

> 电脑应该多放有用的东西.

现在我的腰 BP 是 macOS 10.15.1 的操作系统. iTunes 是 1.0.1.37 的版本.

最开始是为了解决肾接入腰子 Book (Pro) 的自动同步问题, 因为我在公司的时候经常拿数据线通过腰 BP 给肾充电. 然后你接到腰 BP 上就会默认同步, 很占腰 BP 的硬盘空间(将近 20 个 G 总是有的), 很烦人.

直接上一下结论, 在这个环境下, 肾的备份位于: `/Users/liujunyi/Library/Application Support/MobileSync/Backup` 目录下. 你删的话, 需要通过访达的“前往 > 前往文件夹”来到这个目录, 找到里面的东西去删. 如果通过命令行的话, 你 `cd` 到 `/Users/liujunyi/Library/Application Support/MobileSync/Backup` 目录以后再 `ls`, 是看不到里面是什么的, 哪怕是 `sudo ls` 也会提示你: 

> ls: .: Operation not permitted

所以还得通过访达的“前往 > 前往文件夹”这个渠道来删. 

删掉同步内容说完了. 下面讲一下怎么关掉备份. 


先打开腰 BP 上的 iTunes 应用, 在里面找到你的肾, 当然了, 现在 iTunes 叫音乐了:

![设备.png](https://i.loli.net/2019/11/04/8Dqm2ylvO6GKd7u.png)

点开同步设置, 把“选项”里的那个“连接此 iPhone 时自动同步”给勾掉就行. 然后点“应用”. 当然了, 我为了让“应用”可选, 我把第二个选项勾上了, 原先默认是没有的:

![应用.png](https://i.loli.net/2019/11/04/IC4or2tDF687zHc.png)

当然了, 如果“应用”还是灰的那种禁用状态, 我当时的解决方法似乎是删了一个音频. 然后“应用”就可用了.
