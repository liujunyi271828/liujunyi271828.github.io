---
layout: post
title: "位运算符与源码反码补码"
description: "为公司上市而学习计算机组成原理姿势."
date: 2019-09-25
tags: [提高姿势水平]
comments: true
share: true
---

> 为公司上市而学习计算机组成原理姿势.

24 号也就是当时的昨天晚上长长问我一个按位取反的问题, 但我俩都不很明白😂抽空看一下这方面的东西. 

* TOC
{:toc}

## 位运算符

> 我能和申帝学习同一门课程 (45 讲入门人工智能与 Python)，真是太荣幸了，<br/>
> 领导在七点半结束公司代表大会以后，还要参加将课程托管在云上的云学习。相反很多员工九点回到家提交工作日志以后都无暇学习，应当感到羞愧汗颜。<br/>
> 领导早在两天前就已经下决心学习这门课程了，当真具有远见卓识真知灼见。

后来申帝在 2019 年 8 月 17 日发布 AI BA 系统上线消息:

> [前端AI摄像机做人数统计，配合环境和历史数据+AI动态调节控制风阀，水阀开合角度大小，和灯光明亮度的AI BA系统即将上线。](https://liujunyi271828.github.io/2019-09-23/shen-di-yu-lu/#申帝美文)

引用某人的一句话: AI 这两个字现在变得和网红一样廉价, 罪魁祸首就是申畜这种侮辱技术的乐色.

可以参考一下以下资料:

* [BitwiseOperators - Python Wiki](https://wiki.python.org/moin/BitwiseOperators)
* [PHP: Bitwise Operators - Manual](https://www.php.net/manual/en/language.operators.bitwise.php)
* [Advanced Operators &mdash; The Swift Programming Language (Swift 5.1)](https://docs.swift.org/swift-book/LanguageGuide/AdvancedOperators.html)
* [Bitwise operators - JavaScript &#x2758; MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Bitwise_Operators)(没想到这个 `|` 还能给当表格分列那个分隔符来给渲染了, 真 TM 智能. `|` 拿 HTML 实体解释不了, 要用 Unicode 那个十六进制码来写, 这个十六进制码是 `&#x2758;`)
* [keon/awesome-bits: A curated list of awesome bitwise operations and tricks](https://github.com/keon/awesome-bits)

虽说 Python 排在第一位, 但这并不是我最喜欢的语言. 

至于应用会看着讲一点儿. 但正如上面所说应该不会用 Python, 因为孽畜的存在还有刷题网站上强行一行的答案让我对这个语言的印象分大打折扣.

位运算的比较常见的应用就是在 PHP 里调各种报错信息的档位: [错误处理 - 预定义常量](https://www.php.net/manual/zh/errorfunc.constants.php). 当然了, 这个操作在位运算的那个文档手册里也确实说了.

下面看下各种位运算和各自的求法:

<table>
  <thead>
    <tr>
      <th style="width:34%;min-width:34%;">运算符</th>
      <th style="width:16%;min-width:16%;">用法</th>
      <th style="width:50%;min-width:50%;">描述</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>按位与 (AND)</td>
      <td><code>a &amp; b</code></td>
      <td>对于每一个比特位，只有两个操作数相应的比特位都是 1 时，结果才为 1，否则为 0。</td>
    </tr>
    <tr>
      <td>按位或 (OR)</td>
      <td><code>a | b</code></td>
      <td>对于每一个比特位，当两个操作数相应的比特位至少有一个 1 时，结果为 1，否则为 0。</td>
    </tr>
    <tr>
      <td>按位异或 (XOR)</td>
      <td><code>a ^ b</code></td>
      <td>对于每一个比特位，当两个操作数相应的比特位有且只有一个 1 时，结果为 1，否则为 0。</td>
    </tr>
    <tr>
      <td>按位非 (NOT)</td>
      <td><code>~ a</code></td>
      <td>反转操作数的比特位，即 0 变成 1，1 变成 0。</td>
    </tr>
    <tr>
      <td>左移 (Left shift)</td>
      <td><code>a &lt;&lt; b</code></td>
      <td>将 <code>a</code> 的二进制形式向左移 <code>b</code> (&lt; 32) 比特位，右边用 0 填充。</td>
    </tr>
    <tr>
      <td>有符号右移 (Sign-propagating right shift)</td>
      <td><code>a &gt;&gt; b</code></td>
      <td>将 <code>a</code> 的二进制表示向右移 <code>b</code> (&lt; 32) 位，丢弃被移出的位。</td>
    </tr>
    <tr>
      <td>无符号右移 (Zero-fill right shift)</td>
      <td><code>a &gt;&gt;&gt; b</code></td>
      <td>将 <code>a</code> 的二进制表示向右移 <code class="highlighter-rouge">b</code> (&lt; 32) 位，丢弃被移出的位，并使用 0 在左侧填充。</td>
    </tr>
  </tbody>
</table>

## 源码、反码与补码

一会儿得创造产值了, 今晚继续看.