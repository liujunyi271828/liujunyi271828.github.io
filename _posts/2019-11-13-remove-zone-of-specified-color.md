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

需求如题, 把下面这个原图的橙色部分去掉. 以前看公司的美工做过类似的这种操作, 不过人家是手绘板 + PS, 比我这个专业. 不过我对此也确实是没什么兴趣. 美工乃末道, 还是技术重要.

![logo 01.JPG](https://i.loli.net/2019/11/12/wdCylmA7scM2I3g.jpg)

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