---
layout: post
title: "深拷贝与浅拷贝"
description: "为公司上市而学习技术."
date: 2019-08-05
tags: [提高姿势水平]
comments: true
share: true
---


可能有问这个的面试题, 但是我不知道你问这个在项目里能起什么用... 反正有面试题问这个的我就写出来得了.


看 jQuery 的 [`.clone()`](https://api.jquery.com/clone/) 方法的时候想到的. 在 PHP 中, 也有[对象克隆](https://secure.php.net/manual/en/language.oop5.cloning.php)的理念, 具体看文档就完了. 顺便也可以看看文档中的这篇: [对象和引用](https://www.php.net/manual/en/language.oop5.references.php).


PHP 中的 `__clone()` 和 `__construct()`、`__destruct()` 啥的一样, 也是[魔术方法](https://www.php.net/manual/zh/language.oop5.magic.php). 当然了, 这个是 OOP 的. 在文档里说了:

> When an object is cloned, PHP will perform a shallow copy of all of the object's properties.


这里我看了一下这篇文章: [What is deep copy and shallow copy? How PHP uses them?](https://kuntalchandra.wordpress.com/2014/12/06/what-is-deep-copy-and-shallow-copy-how-php-uses-them/), 摘录如下:

> **Shallow copy**: In the process of shallow copying A, B will copy all of A’s field values. If the field value is a memory address it copies the memory address, and if the field value is a primitive type it copies the value of the primitive type. In layman’s term, shallow copy duplicates as minimum as possible. But the disadvantage is if you modify the memory address that one of B’s fields point to, you are also modifying what A’s fields point to.
> 
> **Deep copy**: In this process the data is actually copied completely. The advantage is that A and B do not depend on each other but this process is relatively slower and more expensive.

虽说是 2014 年的文章所以显得有点儿老, 但是取地址符可是和 OOP 无关的.

我把文章里例子改了一下:


```php
<?php

// 浅拷贝: 地址传递.
// 常见的地址传递应用比如 `array_walk()`、各种 `sort`、魔术方法 `__clone()` 等等.
// 这些函数/方法调用的时候都是原地操作.
$source1 = array(2, 3, 5, 8, 13);
$shallow_copy_array = &$source1;
$count1 = count($shallow_copy_array);
// 文档 https://www.php.net/manual/zh/control-structures.foreach.php 里明确说了:
// 由于 foreach 依赖内部数组指针，在循环中修改其值将可能导致意外的行为。
for ($i = 0; $i < $count1; $i++) {
    $shallow_copy_array[$i]++;
}
echo "<h2>#### 浅拷贝: 地址传递 ####</h2>";
var_dump($source1);
var_dump($shallow_copy_array);

// 深拷贝: 值传递. 常见的应用比如 `array_map`、`array_diff`、`array_merge` 等等.
// 这些函数调用的时候得到的结果需要另外声明一个变量来接收才能用.
$source2 = array(2, 4, 8, 16, 32);
$deep_copy_array = $source2;
$count2 = count($deep_copy_array);
for ($j = 0; $j < $count2; $j++) {
    $deep_copy_array[$j]++;
}
echo "<h2>---- 深拷贝: 值传递 ----</h2>";
var_dump($source2);
var_dump($deep_copy_array);
```


效果:

![shallow-copy-and-deep-copy](https://upload.cc/i1/2019/08/05/RYBl2D.png)



总论:

> 浅拷贝好比红警2里盟军造的某个谭雅, 还有该谭雅的影子. 这个谭雅凉了的时候, 该谭雅的影子也凉了;
> 
> 深拷贝好比红警2里苏俄从兵营造的某个尤里, 以及兵营造完之后从复制中心出来的尤里. 哪怕兵营造的被狙击手做掉了, 复制中心出来的不出意外的话也还在.


反正我是差不多懂了, 当然对不对我不知道, 不过十有八九是对的. 就算不懂或不对的话写了这么多东西看了这么多书验证了这么多回差不多也会了.

顺便再强调一下, [foreach](https://www.php.net/manual/zh/control-structures.foreach.php) 和 [for](https://www.php.net/manual/zh/control-structures.for.php) 最本质的区别在于:

> 当 `foreach` 开始执行时，数组内部的指针会自动指向第一个单元。这意味着不需要在 `foreach` 循环之前调用 `reset()`。
> 
> 由于 `foreach` 依赖内部数组指针，在循环中修改其值将可能导致意外的行为。


也是不用多说, 写多了自然就看到差别了. 我们改值的时候都是拿 `for` 改才能改成功.