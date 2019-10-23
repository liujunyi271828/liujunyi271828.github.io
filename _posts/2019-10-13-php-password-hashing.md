---
layout: post
title: "PHP 密码哈希"
description: "看一下 PHP 哈希密码的这个操作."
date: 2019-10-13
tags: [提高姿势水平,工具]
comments: true
share: true
---

> 看一下 PHP 哈希密码的这个操作.

作为辣个女人的生日贺文了😂

<img src="https://upload.cc/i1/2019/10/13/JtiG4d.jpg" style="display:block;margin-left:auto;width:400px;margin-right:auto" />

<small style="display:block; text-align:center;">By 動咸心</small>

注意你图片水平居中的话是用 `margin-left:auto;margin-right:auto;`. `text-align:center;` 在这个场合并没有什么卵用😂

* TOC
{:toc}

从 WordPress 的密码加密机制右转过来的. [*相传*](https://stackoverflow.com/questions/51299530/how-to-create-wordpress-password-hash-generator-using-php) WordPress 之前用的是 [phpass: A portable public domain password hashing framework for use in PHP applications.](https://www.openwall.com/phpass/). 不过 phpass 他们自己说在 PHP 5.5 以上的环境还是建议用 `password_hash()` 或是 `password_verify()`:

![phpass](https://i.ibb.co/FxdxYHz/phpass.png)

所以我们当然是用比较清真的原生手法来写. 再说不管是 ThinkPHP 5.1 还是 Laravel 5.8 都不支持 PHP 5.5 吧😂

哈希的安全性, 可以通过阮一峰老师的这篇文章大概来了解一下: [哈希碰撞与生日攻击](http://www.ruanyifeng.com/blog/2018/09/hash-collision-and-birthday-attack.html)

## 1 [`password_hash()`](https://www.php.net/manual/en/function.password-hash.php)

`password_hash()` 创建了一个密码的哈希值.

### 1.1 `password_hash()` 函数描述

```php
password_hash(string $password, int $algo[, array $options]) : string
```

`password_hash()` 函数使用强单向哈希算法来创建一个新的密码哈希值.

目前支持如下算法 (PHP 7.3.8 时代):

1. `PASSWORD_DEFAULT` - Use the bcrypt algorithm (default as of PHP 5.5.0). Note that this constant is designed to change over time as new and stronger algorithms are added to PHP. For that reason, the length of the result from using this identifier can change over time. Therefore, it is recommended to store the result in a database column that can expand beyond 60 characters (255 characters would be a good choice).
2. `PASSWORD_BCRYPT` - Use the `CRYPT_BLOWFISH` algorithm to create the hash. This will produce a standard `crypt()` compatible hash using the "`$2y$`" identifier. The result will always be a 60 character string, or `FALSE` on failure.
3. `PASSWORD_ARGON2I` - Use the Argon2i hashing algorithm to create the hash. This algorithm is only available if PHP has been compiled with Argon2 support.
4. PASSWORD_ARGON2ID - Use the Argon2id hashing algorithm to create the hash. This algorithm is only available if PHP has been compiled with Argon2 support.

第 3、4 个基本可以不用考虑了, 我们用 1、2 或者准确说是用 2 就行.

对 2: `PASSWORD_BCRYPT` 的支持选项:

* salt(string) - 当哈希密码的时候人工提供盐用的. 在 PHP 7.0.0 时代被 deprecated 了. 可以无视. 现在倾向用默认生成的随机盐. 如果你用了这个参数会把自动生成的盐给覆盖掉. 注意你传盐的时候对盐的长度有要求, 22 个字符起步. 所以还是别用了...
* cost(integer) - 决定了算法的花销. 具体可以上 [`crypt()`](https://www.php.net/manual/en/function.crypt.php) 函数的介绍页去看看. 省略花销值的时候, 会使用一个值为 10 的缺省花销. 觉着你机子硬件牛逼的话可以使用比较大的花销, 不过买设备的钱还是应该甲方出.

3、4 的支持选项我就不说了, 反正我也不打算用.

### 1.2 `password_hash()` 参数解释

* `password`: 用户密码.
* `algo`: 表示哈希密码时使用的算法.
* `options`: 包含选项的**关联数组**. 你不往后翻文档你当然是不知道这个数组得是字典那种的了😂

### 1.3 `password_hash()` 返回值

成功的话就返回哈希过的密码; 否则就返回一个 `false`.

## 2 [`password_verify()`](https://www.php.net/manual/en/function.password-verify.php)

`password_verify()` 函数用来验证一个密码是否匹配哈希值.

### 2.1 `password_verify` 函数描述

```
password_verify(string $password, string $hash) : bool
```

实在是没什么好描述的, 是个人都能看懂, 除非你英语连四级都没过...

注意这个函数能扛住 [timing attack (定时攻击)](https://en.wikipedia.org/wiki/Timing_attack).

### 2.2 `password_verify` 参数解释

* `password` - 用户密码.
* `hash` - 通过 `password_hash()` 函数生成的哈希值.

### 2.3 `password_verify` 返回值

当密码和哈希匹配的时候, 返回 `true`; 否则返回 `false`.

## 举例

就是大概举个例子. 实际操作的话得考虑到和数据库联动的环节.

代码如下:

```php
<?php

// 哈希环节
$password = "67373";
$hash = password_hash($password, PASSWORD_BCRYPT);
var_dump($hash);

// 验证环节
$isVerified = password_verify($password, $hash);
var_dump($isVerified);
```

效果:

![效果1](https://upload.cc/i1/2019/10/13/ToQRWy.png)

如上面所说, 由你不指定盐的话, PHP 会给你一个随机盐. 所以每次的哈希值都是不同的:

![效果2](https://upload.cc/i1/2019/10/13/BuvLS4.png)

![效果3](https://upload.cc/i1/2019/10/13/tkU5A4.png)

但是呢, 你确实是可以用之前生成的哈希值作为一个字面量, 来当做后续比对的父本:

```php
<?php

// 哈希环节
$password = "67373";
$hash = '$2y$10$.2pUc8r7noqfv9/H/nbOmur9poJ3QaX3LshyludwbR7u8CcgN1zP.'; // 之前拿同一个 $password 通过 `password_hash()` 函数生成的. 
var_dump($hash);

// 验证环节
$isVerified = password_verify($password, $hash);
var_dump($isVerified);
```

结果:

![结果](https://upload.cc/i1/2019/10/13/9vrdaq.png)

当然了, 考虑到这个哈希字面量里可能会包含比如 `$` 之类的不明飞行物, 我建议还是用 `'single-quoted string'` 这种单引号字符串的方式括起来. 不过我这就是个演示, 你实战里肯定是把值放在变量里传了😂