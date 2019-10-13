---
layout: post
title: "PHP 正则表达式学习"
description: "为公司而学习正则表达式."
date: 2019-08-12
tags: [提高姿势水平]
comments: true
share: true
---

目录:

* TOC
{:toc}


## 正则表达式小抄

正则表达式是个比较有用的东西, 不过目前还是先达到想干什么就能干什么的水平再说, 以后再慢慢花时间撸.

![regex-cheat-sheet.png](https://i.loli.net/2019/08/12/e3GZFdnABz9QaoP.png)


## 参考资源


1. [Online regex tester, debugger with highlighting for PHP, PCRE, Python, Golang and JavaScript.](https://regex101.com)
2. [Regulex：JavaScript Regular Expression Visualizer](https://jex.im/regulex/)


第一个应该是 2017 年的, 而第二个是 2014 年的.

两个国内都可以访问. 我之前用第二个比较多.


## PHP 与正则表达式


还行吧, 会用倒是会用, 要不然有的题目在刷的时候要是不会的话就过不了了...不过看看也好. 毕竟正则表达式除了刷题之外还有别的用途, 比如文本处理之类的. 


### 复习: if 结构与转换为布尔值

由于我们会用到 [*if*](https://www.php.net/manual/zh/control-structures.if.php#control-structures.if) 结构, 在此先回顾一下:

> *if* 结构是很多语言包括 PHP 在内最重要的特性之一，它允许按照条件执行代码片段。PHP 的 *if* 结构和 C 语言相似：

```php
<?php
if (expr)
  statement
?>
```

> 如同在[表达式](https://www.php.net/manual/zh/language.expressions.php)一章中定义的，expr 按照布尔求值。如果 expr 的值为 **TRUE**，PHP 将执行 statement，如果值为 **FALSE** ——将忽略 statement。有关哪些值被视为 **FALSE** 的更多信息参见[转换为布尔值](https://www.php.net/manual/zh/language.types.boolean.php#language.types.boolean.casting)一节。

下面我们再来看下[转换为布尔值](https://www.php.net/manual/zh/language.types.boolean.php#language.types.boolean.casting).

> 要明确地将一个值转换成 [boolean](https://www.php.net/manual/zh/language.types.boolean.php)，用 *(bool)* 或者 *(boolean)* 来强制转换。但是很多情况下不需要用强制转换，因为当运算符，函数或者流程控制结构需要一个 [boolean](https://www.php.net/manual/zh/language.types.boolean.php) 参数时，该值会被自动转换。
> 
> 参见[类型转换的判别](https://www.php.net/manual/zh/language.types.type-juggling.php)。
> 
> 当转换为 [boolean](https://www.php.net/manual/zh/language.types.boolean.php) 时，以下值被认为是 **FALSE**：
>
> * [布尔](https://www.php.net/manual/zh/language.types.boolean.php)值 **FALSE** 本身
> * [整型](https://www.php.net/manual/zh/language.types.integer.php)值 0（零）
> * [浮点型](https://www.php.net/manual/zh/language.types.float.php)值 0.0（零）
> * 空[字符串](https://www.php.net/manual/zh/language.types.string.php)，以及[字符串](https://www.php.net/manual/zh/language.types.string.php) "0"
> * 不包括任何元素的[数组](https://www.php.net/manual/zh/language.types.array.php)
> * 特殊类型 [NULL](https://www.php.net/manual/zh/language.types.null.php)（包括尚未赋值的变量）
> * 从空标记生成的 [SimpleXML](https://www.php.net/manual/zh/ref.simplexml.phphttps://www.php.net/manual/zh/ref.simplexml.php) 对象
>
> 所有其它值都被认为是 **TRUE**（包括任何[资源](https://www.php.net/manual/zh/language.types.resource.php) 和 **NAN**）。
>
> <p style="background-color:MistyRose"><strong>Warning</strong> <em>-1</em> 和其它非零值（不论正负）一样，被认为是 <strong>TRUE</strong>！</p>


### TODO: PHP 与正则表达式