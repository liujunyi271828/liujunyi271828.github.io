---
layout: post
title: "PHP 版将字符串分割成由相同字母重复而成的子串"
description: "为公司而学习正则表达式."
date: 2019-08-20
tags: [提高姿势水平]
comments: true
share: true
---

> 为公司而学习正则表达式.

这个回答由 Stack Overflow 的答主 [user3942918](https://stackoverflow.com/users/3942918/user3942918) 提供: [How to split a string by repeated characters in PHP?](https://stackoverflow.com/a/33197074/11457285).


在 LC 撸题的第 443 题用到了.

核心代码:

```php
// PHP 5.6.13 之后好用
$array_out = preg_split('/(.)(?!\1|$)\K/', $string_in);
```

以及

```php
// 给 PHP 5.6.13 之前用的. 因为之前处理不了 `\K`.
$array_out = preg_split('/(?<=(.))(?!\1|$)/', $string_in);
```

示例:

```php
<?php

$string1 = "";
var_dump(preg_split('/(.)(?!\1|$)\K/', $string1));

$string2 = "zzzzzzuuuuullllliiiiinnnnnnggggggg";
var_dump(preg_split('/(.)(?!\1|$)\K/', $string2));

$string3 = "wwwweeeeeiiiillllleeeegggooooonnnnngggggsssssiiiii";
var_dump(preg_split('/(.)(?!\1|$)\K/', $string3));

$string4 = "SSSSSSBBBBBBBBB222222555555550000000";
var_dump(preg_split('/(.)(?!\1|$)\K/', $string4));

```


效果:

![singleByte.png](https://i.loli.net/2019/08/20/qlI3u4516zCb7kj.png)

单字节的确实能出来.


再来个多字节的:

```php
<?php

$mbstring = "为为为领领导导服服服务务";
var_dump(preg_split('/(.)(?!\1|$)\K/', $mbstring));

```

效果:

![multiByte.png](https://i.loli.net/2019/08/20/JWjixN4rgLUCpzl.png)


所以这玩意儿就不要在汉字之类的多字节场合用就行了.