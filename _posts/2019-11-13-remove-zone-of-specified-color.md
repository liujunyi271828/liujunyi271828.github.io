---
layout: post
title: "使用 Photoshop 移除图片中的特定颜色区域"
description: "大道三千."
date: 2019-11-13
tags: [提高姿势水平]
comments: true
share: true
---

> 大道三千.

* TOC
{:toc}

先提一嘴: 往朋友圈发照片的话考虑避免发带透明部分的 PNG 的, 听后文提到的李画师说可能会出现黑块. 亲测也确实如此.

需求如题, 把下面这个原图的橙色部分去掉. 以前看公司的美工做过类似的这种操作, 不过人家是手绘板 + PS, 比我这个专业. 不过我对此也确实是没什么兴趣. 美工乃末道, 还是技术重要.

![logo 01.JPG](https://i.loli.net/2019/11/12/wdCylmA7scM2I3g.jpg)

## 01 PS: 选择 → 色彩范围

我参考的是这个做法: [怎么用PS将图层上的特定颜色删除？如图。](https://zhidao.baidu.com/question/129884113.html)

<span style="color:red;">注意: 做之前, 先保存一个图片的副本.</span>

使用 Photoshop 打开图片, 然后在顶栏的 `选择` 中选择 `色彩范围`: ![选择-色彩范围.png](https://i.loli.net/2019/11/13/FGTs1QwLYmVZedO.png)

再点进去. 颜色容差默认给的是 80, 你要选的话 80 可能不一定能全选上, 所以可以来个 200. 然后在大图中取色(如果觉着没法取到具体位置的颜色可以放大取), 选好之后按确定选中指定颜色部分, command + delete 删除.

![取样-颜色容差.png](https://i.loli.net/2019/11/13/XrQlhYqNPMJzBgH.png)

你删一次的话, 可能有些边边角角顾及不到:

![第一次删除.png](https://i.loli.net/2019/11/13/qGM1huFBD4VHLvx.png)

这时候可以在触摸板上放大, 删第二次或是再多删除几次.

最后的效果是这样:

![第二次修完的logo01.JPG](https://i.loli.net/2019/11/13/U2Y8WNyOSKJtTxF.jpg)

只适用于我这种需求比较简单的情形. 要是周围还有非白颜色的话, 这个暂时不在本文讨论范围内.

## 02 PS: 魔棒 → 魔术擦子

14 号新加的, 实际上昨天已经会差不多了, 这个是看李经理操作会的. 

我决定用这个修完的结果. 原图如下, 这个原图可以明确作者, 就是**在下芭蕉桑**大姐♂姐:

![原材备份.jpg](https://i.loli.net/2019/11/14/txa7yXKVE18mzYr.jpg)

可以看到: 里面有多个封闭区域.

先使用魔棒点白色区域, 选中操作区域:

![魔棒.png](https://i.loli.net/2019/11/14/fF5EcXNrmdyZSTu.png)

然后再使用魔术擦子:

![魔术擦子.jpg](https://i.loli.net/2019/11/14/tK2jEMUwLFqAoJe.jpg)

单击, 删除选中区域:

![删除.png](https://i.loli.net/2019/11/14/QX4ncb9TB7fFwOh.png)

删除所有的封闭区域, 最终结果如下:

![最终.png](https://i.loli.net/2019/11/14/RF8dqItikC6N1V5.png)

就这个图而言, 更小的区域比如眼睛、6 的那个空心、e、a 中间的空心也需要抠掉. 当然这个是就事论事了.

## 03 抠图神器: remove.bg

拿陈工双十一囤积钢丝球的图换来了芭蕉桑大姐姐路由的安利福利, 链接如下:

> [删除图像中的背景 – remove.bg](https://www.remove.bg/zh)

这个东西一想有很多的应用价值. 比如抠个孽畜健身完自拍的图出来.

此外这个除了在线外, 也有本地客户端, 可以参考 [Remove.bg for Windows/Mac/Linux – remove.bg](https://www.remove.bg/zh/windows-mac-linux) 来使用. 至于下载地址则是 [Starting download... – remove.bg](https://www.remove.bg/windows-mac-linux/download), 安装指南仔细看看就有, 我觉着这英语对一个做技术的应该没有多难.

本地用客户端的话需要注册一个 API Key, 但是好像零氪玩家有限制, 只不过这个限制的 total credits 我确实是没看懂. 可以看 [remove.bg：最高效的一键扣图软件「有免费版本」 - Mac玩儿法](https://www.waerfa.com/remove-bg-review) 这篇文章后面写的收费策略大概理解一下.