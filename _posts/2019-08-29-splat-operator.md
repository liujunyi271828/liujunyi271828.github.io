---
layout: post
title: "Splat Operator 介绍"
description: "为干出产值而格物致知."
date: 2019-08-29
tags: [提高姿势水平]
comments: true
share: true
---

> 为干出产值而格物致知.

加个目录吧. 不然再过几天自己看也头疼, 毕竟这种东西写了还是方便看一点儿比较好, 要不就白写了🤦‍♂️🤦‍♀️🙈

* TOC
{:toc}


我是头一次知道 `...` 这个东西还有名字😂 `...` 这个东西*据说*是叫 Splat Operator. splat 这个词我以前确实是不认识, 当然如果我不认识的话我周围人也不可能认识...查查这个词先:

> **splat**<br/>
> N-SING; SOUND<br/>
> 1️⃣**Splat** is used to describe the sound of something wet hitting a surface with a lot of force. (湿物落在平面上发出的)啪嗒声，溅泼声<br/>
> * The egg landed on my cheek with a <strong style="color:orange;">splat</strong>. <br/>
>   鸡蛋啪嚓一声打在我脸颊上。


在 PHP 7 里出了 `<=>` 这个东西, 不管是英文官方手册还是中文都是叫 Spaceship Operator/太空船运算符. 所以既然中文网上(我是以某度一下的结果为准)也没有 Splat Operator 这个东西的翻译的话, 那我们就叫它 **啪啪啪运算符** 好了😂容易知道, 它是一个单目运算符, 也就是说它只对一个 operand 进行变换.

我记得 Swift 里是有这个东西的, 刚刚找了一下, 可以看一下 [Control Flow](https://docs.swift.org/swift-book/LanguageGuide/ControlFlow.html)、[Range Operators](https://docs.swift.org/swift-book/LanguageGuide/BasicOperators.html#ID73). 三四年没摸 Swift 了, 我记得之前摸 Swift 那会儿 Swift 好像出到 2 还不 3 的, 而现在 Swift 都出到了 5.1, Swift 语言开发组已经创造出起码 4 种语言了, 充分证明了 Swift 比有两个不互相兼容的版本的 Python (2) 和 Python 3 的 Python 更牛逼, 也就比 Java 稍微矬一点儿了, 真是可喜可贺😂



## 问题提出


之前是碰到了这么一个问题, 比如说给了一个元素为字符串的数组, 想获取数组每个元素包含的公共字符. 

前面这么一下显然是没有问题:

```php
<?php

$array = ["cool","lock","cook"];

$byteValueInfos = array_map($callback = function ($element) {
    return count_chars($element, 1);
}, $array);
var_dump($byteValueInfos);

$byteValues = array_map("array_keys", $byteValueInfos);
var_dump($byteValues);
```


效果如下:

![前半段.png](https://i.loli.net/2019/08/29/Sh5egWmksABXPIN.png)

后面当然是想取交集, 然后就是去 `array_intersect()`. 不过如果直接写 `$commonByteValues = array_intersect($byteValues);` 的话, 会提示你:

> Warning: array_intersect(): at least 2 parameters are required, 1 given in ...

可见 `array_intersect()` 这个方法是需要我们传入两个或以上的参数才能正常使用的. 

那么有没有什么比较优雅的写法呢, 某度了一下真没有查到, 全是一堆驴唇不对马嘴的结果; 去某歌了一下, 总算查到了. 先放一下解决方案:

```php
<?php

$array = ["cool","lock","cook"];

$byteValueInfos = array_map($callback = function ($element) {
    return count_chars($element, 1);
}, $array);
var_dump($byteValueInfos);

$byteValues = array_map("array_keys", $byteValueInfos);
var_dump($byteValues);

$commonByteValues = array_intersect(...$byteValues);
var_dump($commonByteValues);

```

效果:

![完整版效果.png](https://i.loli.net/2019/08/29/ZDV5IhUW1nJopQ9.png)


## 解决方案

解决方案是在这个问题 [Php - How to find common elements from multidimensional array?](https://stackoverflow.com/questions/39489449/php-how-to-find-common-elements-from-multidimensional-array) 看到的, 题主的问题和我的问题类似, 参考的解答是: [For PHP 5.6 and above, you can directly use `array_intersect()` with the `...` token (also called splat operator in other languages)](https://stackoverflow.com/a/39489788/11457285), 是用了一个 `...` 也就是这个 Splat Operator 的东西. 说是性能比用 `call_user_func_array()`, 也就是比用 `call_user_func_array (callable $callback , array $param_arr)` 这种要好, 那就不放这个了. 在 [You can simply use `call_user_func_array` on `array_intersect`, if you want to find numbers that are contained in all sub-arrays](https://stackoverflow.com/a/4704211/11457285) 这个解答里讲了用 `call_user_func_array()` 的做法. `call_user_func_array()` 的好处是它适用于从 PHP 4.0.4 开始的情形. 一般创造产值的时候 PHP 5 就是最早的了吧😂我一般没啥用 legacy 的习惯😂

至于适不适用于多维的情形、从什么角度去适用的问题等以后再说, 因为我之前在 Stack Overflow 回答还不问题啥的提供的示例材料上插了几个嵌套的数组测了一下, 结果并不是按我自己的设想来的. 此外你嵌套的时候, 可能会出现 [array to string conversion 的 notice](https://www.php.net/manual/en/function.array-intersect.php#118407). 也是没查着有什么消掉的办法(调 ERROR 等级的办法就不算在内), 所以也是先放到一边儿.

至少我确认直接调用 `array_intersect()` 这个解决方案在二维的时候好用就可以了, 它确实能保证实现我的基本需求, 我就没必要再钻牛角尖了.


## 参考阅读


### 官方文档

回 PHP 手册看一下这个点:

[Variable-length argument lists](https://www.php.net/manual/en/functions.arguments.php#functions.variable-arg-list).

这一节开头就说了:

> PHP has support for variable-length argument lists in user-defined functions. This is implemented using the `...` token in PHP 5.6 and later, and using the [`func_num_args()`](https://www.php.net/manual/en/function.func-num-args.php), [`func_get_arg()`](https://www.php.net/manual/en/function.func-get-arg.php), and [`func_get_args()`](https://www.php.net/manual/en/function.func-get-args.php) functions in PHP 5.5 and earlier.

配的几个例子也都可以看看:

* Example #14 Using `...` to access variable arguments
* Example #15 Using `...` to provide arguments
* Example #16 Type hinted variable arguments

以及在以前应该怎么办:

* Example #17 Accessing variable arguments in PHP 5.5 and earlier


此外在 PHP 5.5 迁移到 PHP 5.6 的说明有两处也说到 `...` 的事儿:

* [Variadic functions via `...`](https://www.php.net/manual/en/migration56.new-features.php#migration56.new-features.variadics)
* [Argument unpacking via `...`](https://www.php.net/manual/en/migration56.new-features.php#migration56.new-features.splat)

常量表达式和 `**` 运算符也是在 PHP 5.6 这个时期登上上市的历史舞台的😂

至于这个 variadic function 该怎么理解, 可以看 [wiki: Variadic function](https://en.wikipedia.org/wiki/Variadic_function):

> In mathematics and in computer programming, a **variadic function** is a function which accepts a variable number of arguments. 

### 博客

还有一篇讲 [PHP 5.6 and the Splat Operator - LORNAJANE Blog](http://lornajane.net/posts/2014/php-5-6-and-the-splat-operator) 的博文, 发表在 2014-03-17, 摘录一下:

> **Variadic Functions**
> 
> This feature allows you to capture a variable number of arguments to a function, combined with "normal" arguments passed in if you like. It's easiest to see with an example:

```php
function concatenate($transform, ...$strings) {
    $string = '';
    foreach($strings as $piece) {
        $string .= $piece;
    }
    return($transform($string));
}

echo concatenate("strtoupper", "I'd ", "like ",
    4 + 2, " apples");
```

> The parameters list in the function declaration has the `...` operator in it, and it basically means "... and everything else should go into `$strings`". You can pass 2 or more arguments into this function and the second and subsequent ones will be added to the `$strings` array, ready to be used.

以及:

> **Argument Unpacking**
> 
> This has a less sexy name than variadic functions, and it uses the same operator, but this is the one that made me describe PHP code as "wild" - not something that happens often! I like it because it gives a different way of using functions that already exist so it becomes relevant as soon as you upgrade to 5.6.
> 
> Variadic functions allow you to declare an array of incoming parameters, and argument unpacking allows you to pass an array in to a function expecting separate parameters in the traditional way; they are absolutely complementary to one another. To use this feature, just warn PHP that it needs to unpack the array into variables using the `...` operator. A simple example could look like this:


```php
$email[] = "Hi there";
$email[] = "Thanks for registering, hope you like it";

mail("someone@example.com", ...$email);
```

> You can pass all of your arguments in as an array (pro tip: associative arrays won't work here), or just the last however many you like, and PHP will take your array and pass each element in as the next parameter in turn. I think this is pretty neat :)



这个博主大姐和我差不多的技能树应该是, 写的东西不少我也比较感兴趣, 她的博客是 [LORNAJANE Blog](http://lornajane.net/blog), 而且还写过书, 虽说我都没读过😂关键还有菜谱: [CATEGORY ARCHIVES: RECIPES](http://lornajane.net/posts/category/4-recipes), 而且还发了不止一篇, 这个就碉堡了...




