---
layout: post
title: "自增自减运算符"
description: "为干出产值而学习技术."
date: 2019-07-04
tags: [提高姿势水平]
comments: true
share: true
---


懒得记这个东西, 只会最常用的. 真到需要抠细节的时候再查呗...

上官方文档看一下[自增自减运算符](https://www.php.net/manual/zh/language.operators.increment.php).

> PHP 支持 C 风格的前／后递增与递减运算符。
> 
> > **Note:** 递增／递减运算符不影响布尔值。递减 **NULL** 值也没有效果，但是递增 **NULL** 的结果是 *1*。


我个人原则上是在循环以外的地方尽量少用这个. 这貌似也是Swift的一个编程规范.

<table>
  <caption><strong>自增／自减运算符</strong></caption>
  <tr>
    <th>例子</th>
    <th>名称</th>
    <th>效果</th>
  </tr>
  <tr>
    <td>++$a</td>
    <td>前加</td>
    <td>$a 的值加一，然后返回 $a。</td>
  </tr>
  <tr>
    <td>$a++</td>
    <td>后加</td>
    <td>返回 $a，然后将 $a 的值加一。</td>
  </tr>
  <tr>
    <td>--$a</td>
    <td>前减</td>
    <td>$a 的值减一， 然后返回 $a。</td>
  </tr>
  <tr>
    <td>$a--</td>
    <td>后减</td>
    <td>返回 $a，然后将 $a 的值减一。</td>
  </tr>
</table>


[如何解释“a+=a+=a+=(a++)+(++a) ;输出a；”在java和c中的结果不同呢？](https://www.zhihu.com/question/34590874)


```php
<?php

$a = 0;
$a += $a += $a += ($a++) + (++$a);
echo '$a' . " = {$a}";
```

结果输出:

> $a = 16


哪怕写成`$a += ($a += ($a += (($a++) + (++$a))));`, 这也是一滩翔.

此外还有这个:

![Java示例](https://i.loli.net/2019/07/16/5d2d23be0cf9230696.png)

跑了一下:

![WX20190716-091036@2x.png](https://i.loli.net/2019/07/16/5d2d2424cc9f062690.png)

我觉着如果我以前像题目这么写的话, 贝老经理一定会语重心长地和我交流一番; 假如以前我看着贝老经理这么写的话, 我一定也会毫不留情地指出贝老经理的这个问题. 然而我们并不可能会这么写...


最后, 建议在碰到平时也这么写的公司精锐时请直接辞退, 谢谢!!!