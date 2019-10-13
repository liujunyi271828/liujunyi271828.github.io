---
layout: post
title: "WebStorm 自动缩进设置"
description: "为更快创造产值而研究使用工具."
date: 2019-09-10
tags: [提高姿势水平]
comments: true
share: true
---

> 为更快创造产值而研究使用工具.

* TOC
{:toc}

**这个有问题...并不能完全解决我的问题, 先不用参考了.**

虽说是为了解决 WebStorm 方面的问题, 但也许也适合 JetBrains 家的其他应用,  比如 PhpStorm、IntelliJ IDEA 等.

## 背景

WebStorm 2016.3.3, macOS 系统. 

虽然有点儿老, 但是目前看起来能用. 比如我写 JS 想用 `for-of` 循环的时候这个 IDE 还是提供 ECMAScript 6 标准的. Old, but not obsolete.

## 具体问题

碰到的问题是想换行的时候, 回车总是回到下一行定格的位置, 或是在标签行回车的时候光标会来到下一行的与上一行标签的开始部分的头对齐的位置.

## 解决方案

上编码风格里改行分隔符的位置. 原先可能默认设的是 System-Dependent, 此外还有 Unix and OS X(`\n`)、Windows(`\r\n`)、Class Mac(`\r`) 这几个选项, 选 Unix and OS X 是可以达到设想效果的.

再就我之前的自动缩进设的是 4 空格 (= 1 tab)(这个自动缩进是在编码风格那儿取个主题, 然后上你用的那几个前端编程语言/标记语言里设, 就不细说了), 说实话目前我不太能理解为啥有的人非要两空格缩进, 你看着不头疼么, 你写着写着就得打两个空格不蛋疼么...

然后就可以继续写代码而不用专门去调行首位置了...

![webstorm.png](https://i.loli.net/2019/09/10/pKQhweylu68DHbr.png)


## 模板

找到一个设置模板的地方, 很显然, 只要想调模板的话, 你就搜 template 相关的就行了, 肯定能找到. 原先的模板它不缩进 `html>(head+body)` 中的 `head+body` 部分, 所以我就直接把这段儿 tab 了...这方面儿 WebStorm 比配了包的 Atom 稍微差了一点点儿, 不过勉强可以忽略.

![template.png](https://i.loli.net/2019/09/10/BiR2A9rge3FlakK.png)



