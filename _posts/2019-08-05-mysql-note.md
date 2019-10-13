---
layout: post
title: "MySQL 笔记"
description: "为公司崛起而成为一名优秀的(MySQL)数据库库管."
date: 2019-08-05
tags: [提高姿势水平]
comments: true
share: true
---


如果说以前工作的铺垫算是第零季的话, 那这篇只能算第一季了. 我在这里是拿视频复习一下 MySQL . 当然这仅仅是 CRUD 的水平, 接下来还打算看一些更具体的名著, 再就王珊 + 萨师煊这种理论还有数据库设计之类的东西.


再一个就是通过这个了解一下 phpMyAdmin, 因为平时确实不用这个, 而视频里的这个~~美帝~~南非小哥用的是 MAMP.

这个~~美帝~~南非小哥的 YTB 视频地址是: [Quentin Watt Tutorials](https://www.youtube.com/user/QuentinWatt/videos) . 之所以认为他是美帝的, 是因为他英语说得确实不错, 总之以我的听力水平居然能无字幕听懂... 在[他的 YTB 主页的简介](https://www.youtube.com/user/QuentinWatt/about)部分 的下面有他的 推特、脸书、INS、Patreon、Donate with PayPal 等链接, 也是希望有经济实力的大佬可以支持一波. 当然他还有 GitHub 链接: [QuentinWatt](https://github.com/QuentinWatt) . 这小哥应该和我一样也是 PHP 路线的全栈, 所以讲的基本上就是那些东西.


我们是基于小哥写的这个 SQL 脚本, 当然, 这个作为学习是可以的, 但是写项目不要按照某些细节来:

```sql
-- Add By liujunyi271828: 
-- This script is written by Quentin Watt: https://www.youtube.com/user/QuentinWatt/about

-- phpMyAdmin SQL Dump
-- version 4.4.10
-- http://www.phpmyadmin.net
--
-- Host: localhost:8889
-- Generation Time: Jun 03, 2017 at 12:01 PM
-- Server version: 5.5.42
-- PHP Version: 7.0.0

SET SQL_MODE = "NO_AUTO_VALUE_ON_ZERO";
SET time_zone = "+00:00";


/*!40101 SET @OLD_CHARACTER_SET_CLIENT=@@CHARACTER_SET_CLIENT */;
/*!40101 SET @OLD_CHARACTER_SET_RESULTS=@@CHARACTER_SET_RESULTS */;
/*!40101 SET @OLD_COLLATION_CONNECTION=@@COLLATION_CONNECTION */;
/*!40101 SET NAMES utf8mb4 */;

--
-- Database: `learning_over_here`
--
CREATE DATABASE IF NOT EXISTS `learning_over_here` DEFAULT CHARACTER SET utf8 COLLATE utf8_general_ci;
USE `learning_over_here`;

-- --------------------------------------------------------

--
-- Table structure for table `addresses`
--

DROP TABLE IF EXISTS `addresses`;
CREATE TABLE `addresses` (
  `address_id` int(11) NOT NULL,
  `users_id` int(11) NOT NULL,
  `address_line_1` varchar(250) DEFAULT NULL,
  `address_line_2` varchar(250) DEFAULT NULL,
  `address_line_3` varchar(250) DEFAULT NULL,
  `city` varchar(100) DEFAULT NULL,
  `state_province` varchar(100) DEFAULT NULL,
  `zip` varchar(10) DEFAULT NULL
) ENGINE=InnoDB AUTO_INCREMENT=10 DEFAULT CHARSET=utf8;

--
-- Dumping data for table `addresses`
--

INSERT INTO `addresses` (`address_id`, `users_id`, `address_line_1`, `address_line_2`, `address_line_3`, `city`, `state_province`, `zip`) VALUES
(1, 1, '79 Beach Rd', 'Mouille Point', '', 'Cape Town', 'Western Cape', '8005'),
(2, 15, '2 Gray St', 'Knysna Central', '', 'Knysna', 'Western Cape', '6571'),
(3, 9, 'Bentley Office Park', '70 Wessel Road', 'Rivonia', 'Johannesburg', 'Gauteng', '2191'),
(4, 14, 'Apartment 21', '2461 desert Road', 'Yellow Sands', 'Tatooine Villa', 'Tatooine', '908709'),
(5, 10, '59 Albert Embankment', '', 'Lambeth', 'London', 'UK', 'SE1 7TP'),
(6, 8, '742 Evergreen Terrace', '', '', 'Springfield', 'ORE', '97001'),
(7, 14, 'Queens Palace', 'Naboo Main Road', 'Naboo City', 'Naboo', 'NAB', '71992'),
(8, 12, '28201 E. Bonanza St.', 'South Park', '', 'South Park City', 'CAL', '28201'),
(9, 12, '635 Avenue de Los Mexicanos', 'South Park', '', 'South Park City', 'CAL', '28201');

-- --------------------------------------------------------

--
-- Table structure for table `orders`
--

DROP TABLE IF EXISTS `orders`;
CREATE TABLE `orders` (
  `order_id` int(11) NOT NULL,
  `product_id` int(11) NOT NULL,
  `user_id` int(11) NOT NULL,
  `address_id` int(11) NOT NULL
) ENGINE=InnoDB AUTO_INCREMENT=5 DEFAULT CHARSET=utf8;

--
-- Dumping data for table `orders`
--

INSERT INTO `orders` (`order_id`, `product_id`, `user_id`, `address_id`) VALUES
(1, 2, 14, 7),
(2, 6, 14, 7),
(3, 13, 9, 1),
(4, 12, 8, 6);

-- --------------------------------------------------------

--
-- Table structure for table `products`
--

DROP TABLE IF EXISTS `products`;
CREATE TABLE `products` (
  `product_id` int(11) NOT NULL,
  `product_name` varchar(100) NOT NULL,
  `product_description` varchar(500) DEFAULT NULL,
  `product_img` varchar(100) DEFAULT NULL,
  `product_stock` int(11) DEFAULT NULL,
  `product_price` decimal(18,2) DEFAULT NULL
) ENGINE=InnoDB AUTO_INCREMENT=14 DEFAULT CHARSET=utf8;

--
-- Dumping data for table `products`
--

INSERT INTO `products` (`product_id`, `product_name`, `product_description`, `product_img`, `product_stock`, `product_price`) VALUES
(1, 'Cannon 600D camera', 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Duis posuere eget erat eu placerat. Phasellus pretium leo varius est blandit consequat. Pellentesque rutrum velit dui, congue ultrices lectus feugiat ac. Nullam ac sem vestibulum, imperdiet nulla sit amet, auctor ipsum.', 'imgs/products/imgname.jpg', 10, '349.99'),
(2, 'Lightsaber - Blue', 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Duis posuere eget erat eu placerat. Phasellus pretium leo varius est blandit consequat. Pellentesque rutrum velit dui, congue ultrices lectus feugiat ac. Nullam ac sem vestibulum, imperdiet nulla sit amet, auctor ipsum.', 'imgs/products/lightsaber.jpg', 5, '39999.99'),
(3, 'Lightsaber - Red', 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Duis posuere eget erat eu placerat. Phasellus pretium leo varius est blandit consequat. Pellentesque rutrum velit dui, congue ultrices lectus feugiat ac. Nullam ac sem vestibulum, imperdiet nulla sit amet, auctor ipsum.', 'imgs/products/lightsaber-red.jpg', 1, '79999.99'),
(4, '2017 Apple Macbook Pro - 256gb', 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Duis posuere eget erat eu placerat. Phasellus pretium leo varius est blandit consequat. Pellentesque rutrum velit dui, congue ultrices lectus feugiat ac. Nullam ac sem vestibulum, imperdiet nulla sit amet, auctor ipsum.', 'imgs/products/macbookpro.jpg', 50, '1989.99'),
(5, 'Spiced Biltong - 5kg', 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Duis posuere eget erat eu placerat. Phasellus pretium leo varius est blandit consequat. Pellentesque rutrum velit dui, congue ultrices lectus feugiat ac. Nullam ac sem vestibulum, imperdiet nulla sit amet, auctor ipsum.', 'imgs/products/spiced-biltong.jpg', 500, '48.99'),
(6, 'Storm Trooper Uniform', 'A standard 2015 Storm Trooper uniform. Use it as a disguise to infiltrate the enemy, or as a cool costume for a dress up party', 'imgs/products/storm-trooper-uniform.jpg', 5, '399.90'),
(7, 'Pink Doughnuts', 'Perfectly glazed pink doughnut', 'imgs/products/pink-doughnut.jpg', 12, '3.50'),
(8, 'Nunchucks - Wooden', 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Duis posuere eget erat eu placerat. Phasellus pretium leo varius est blandit consequat. Pellentesque rutrum velit dui, congue ultrices lectus feugiat ac. Nullam ac sem vestibulum, imperdiet nulla sit amet, auctor ipsum.', 'imgs/products/wooden-chucks.jpg', 67, '29.90'),
(9, 'Gravestone - Granite', 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Duis posuere eget erat eu placerat. Phasellus pretium leo varius est blandit consequat. Pellentesque rutrum velit dui, congue ultrices lectus feugiat ac. Nullam ac sem vestibulum, imperdiet nulla sit amet, auctor ipsum.', 'imgs/products/granite-gravestone.jpg', 4, '699.00'),
(10, 'Blue Yeti Mircrophone - silver', 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Duis posuere eget erat eu placerat. Phasellus pretium leo varius est blandit consequat. Pellentesque rutrum velit dui, congue ultrices lectus feugiat ac. Nullam ac sem vestibulum, imperdiet nulla sit amet, auctor ipsum.', 'imgs/products/blue-yeti-microphone-silver.jpg', 8, '249.90'),
(11, 'Death Star Miniature Replica', 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Duis posuere eget erat eu placerat. Phasellus pretium leo varius est blandit consequat. Pellentesque rutrum velit dui, congue ultrices lectus feugiat ac. Nullam ac sem vestibulum, imperdiet nulla sit amet, auctor ipsum.', 'imgs/products/deathstarreplica.jpg', 13, '24.00'),
(12, 'Hazmat Suit', 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Duis posuere eget erat eu placerat. Phasellus pretium leo varius est blandit consequat. Pellentesque rutrum velit dui, congue ultrices lectus feugiat ac. Nullam ac sem vestibulum, imperdiet nulla sit amet, auctor ipsum.', 'imgs/products/hazmat-suit.jpg', 2, '849.99'),
(13, 'facebook idea', 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Duis posuere eget erat eu placerat. Phasellus pretium leo varius est blandit consequat. Pellentesque rutrum velit dui, congue ultrices lectus feugiat ac. Nullam ac sem vestibulum, imperdiet nulla sit amet, auctor ipsum.', '', 1, '0.99');

-- --------------------------------------------------------

--
-- Table structure for table `users`
--

DROP TABLE IF EXISTS `users`;
CREATE TABLE `users` (
  `id` int(11) NOT NULL,
  `username` varchar(150) NOT NULL,
  `password` varchar(35) NOT NULL,
  `user_email` varchar(150) NOT NULL,
  `first_name` varchar(150) DEFAULT NULL,
  `last_name` varchar(150) DEFAULT NULL
) ENGINE=InnoDB AUTO_INCREMENT=16 DEFAULT CHARSET=utf8;

--
-- Dumping data for table `users`
--

INSERT INTO `users` (`id`, `username`, `password`, `user_email`, `first_name`, `last_name`) VALUES
(1, 'quentin92', 'password123', 'business@quentinwatt.com', 'Quentin', 'Watt'),
(2, 'sean', 'pass123', 'sean@hiscompany.co.za', '', ''),
(3, 'sibu', 's!bu', 'sibu@sibuthelegend.co.za', 'Sibu', ''),
(4, 'ryan', 'ryebread', 'ryan@shweshwe.co.za', 'Ryan', 'Schwulst'),
(5, 'kristi87', 'kr!5t!', 'kristi@fakemail.com', 'Kristi', 'Dunsk'),
(6, 'SuzelleDIY', 'suzzles1989', 'suzelle@thediychannel.com', 'Suzelle', ''),
(7, 'jackie', 'therealjackiechan', 'jackie@therealjackiechan.com', 'Jackie', 'Chan'),
(8, 'homer', 'doh!', 'homer@thesimpsons.com', 'Homer', 'Simpson'),
(9, 'thezuckmeister', 'zucker!@9)BNa', 'markzuckerberg@facebook.com', 'Mark', 'Zuckerberg'),
(10, 'james', 'jamesbond007', 'james@mi6.gov.uk', 'James', 'Bond'),
(11, 'kenny', 'foreverdead', 'kenny@southpark.show', 'Kenny', ''),
(12, 'cartman', 'thecoon!', 'cartman@southpark.show', 'Cartman', ''),
(13, 'greg0812', 'sup3rstr0ngp455!', 'greg@fakemail.com', 'Greg', 'Coltman'),
(14, 'thejedimasterluke', 'thef0rc3', 'lukeskywalker@thejedicouncil.galaxy', 'Luke', 'Skywalker'),
(15, 'wreckitralph', 'imgonnawreck!t', 'ralph@wreck.it', 'Ralph', '');

--
-- Indexes for dumped tables
--

--
-- Indexes for table `addresses`
--
ALTER TABLE `addresses`
  ADD PRIMARY KEY (`address_id`);

--
-- Indexes for table `orders`
--
ALTER TABLE `orders`
  ADD PRIMARY KEY (`order_id`);

--
-- Indexes for table `products`
--
ALTER TABLE `products`
  ADD PRIMARY KEY (`product_id`);

--
-- Indexes for table `users`
--
ALTER TABLE `users`
  ADD PRIMARY KEY (`id`);

--
-- AUTO_INCREMENT for dumped tables
--

--
-- AUTO_INCREMENT for table `addresses`
--
ALTER TABLE `addresses`
  MODIFY `address_id` int(11) NOT NULL AUTO_INCREMENT,AUTO_INCREMENT=10;
--
-- AUTO_INCREMENT for table `orders`
--
ALTER TABLE `orders`
  MODIFY `order_id` int(11) NOT NULL AUTO_INCREMENT,AUTO_INCREMENT=5;
--
-- AUTO_INCREMENT for table `products`
--
ALTER TABLE `products`
  MODIFY `product_id` int(11) NOT NULL AUTO_INCREMENT,AUTO_INCREMENT=14;
--
-- AUTO_INCREMENT for table `users`
--
ALTER TABLE `users`
  MODIFY `id` int(11) NOT NULL AUTO_INCREMENT,AUTO_INCREMENT=16;
/*!40101 SET CHARACTER_SET_CLIENT=@OLD_CHARACTER_SET_CLIENT */;
/*!40101 SET CHARACTER_SET_RESULTS=@OLD_CHARACTER_SET_RESULTS */;
/*!40101 SET COLLATION_CONNECTION=@OLD_COLLATION_CONNECTION */;

```

在数据库里, 不要存储明文密码. 也不要 md5 加密, 目前看的比较好的实践貌似是 Hash 加密.



## LIMIT, OFFSET 与 ORDER BY

### 1. LIMIT 和 OFFSET 的缩写形式

``SELECT * FROM `users` LIMIT 4 OFFSET 8;`` <=> ``SELECT * FROM ``users`` LIMIT 4, 8;`` . 其中 “<=>” 符号代表等价.

如果你写 ``SELECT * FROM `users` LIMIT 4, 8;`` 的话, 得到的结果是 `users` 表中的从第 5 条数据到第 12 条数据的总共 8 条数据. 

而 ``SELECT * FROM `users` LIMIT 8, 4;`` 才是 `users` 表中的从第 9 条数据到第 12 条数据的总共 4 条数据. 

所以我个人觉着还是不要缩写的好, 缩写写好要费脑子, 写不好的话就是出错. 当然你牛逼的话你也可以用缩写.

### 2. ORDER BY 子句、ASC/DESC 子句和 LIMIT 子句的位置

像 ``SELECT * FROM `users` ORDER BY `id` LIMIT 10`` 这么写是对的. 

也就是说, `ORDER BY` 要放在 `LIMIT` 的前面.

加上排序关键字后, 像 ``SELECT * FROM `users` ORDER BY `id` DESC LIMIT 10;`` 这么写是对的.

排序方式关键字是需要放在 `ORDER BY` 和 `LIMIT` 的中间.


### 3. ORDER 的默认顺序

你什么都不加的话, ORDER 缺省是给你按 ascending 排, 也就是说是和 PHP 中的 `sort()` 函数一样, 给你按从小到大升序排.

| SQL 关键字 | 英语中对应的全称 | 排序方式 | 类比 |
|---|---|---|---|
| ASC | ascending | 升序(根据字段值从小到大排) | PHP 中的 `sort()` 函数 |
| DESC | descending | 降序(根据字段值从大到小排) | PHP 中的 `rsort()` 函数 |


## WHERE

示例:

```sql
SELECT `product_name`, `product_price` FROM `products` WHERE `product_price` >= 200;
```


### WHERE 1 的含义

并没有什么卵用. 参考在问题 [What does “WHERE 1” mean in SQL?](https://stackoverflow.com/questions/3720735/what-does-where-1-mean-in-sql) 中的高票回答: 

> It doesn't. It means **ALWAYS TRUE** so it won't have any filtering impact on your query. Query planner will probably ignore that clause.
> 
> It's usually used when you build a client side query by concatenating filtering conditions.
> 
> So, if your base query is stored in a string like this (example is in PHP, but it certainly applies to many other languages):

```php
$sql = "select * from foo where 1 ";
```

Then you can just concatenate a lot of filtering conditions with an `AND` clause regardless of it being the first condition you are using or not:


```php
// pseudo php follows...
if ($filter_by_name) {
    $sql = $sql . " and name = ? ";
}
if ($filter_by_number) {
    $sql = $sql . " and number = ? ";
}
// so on, and so forth.
```

这个在 phpMyAdmin 上体现得尤为明显. 当然 PhpStudy 之类的我也没用过, 不知道有没有. 就算有我也是用 Navicat Premium.

#### phpMyAdmin 操作

在 phpMyAdmin 的 SQL 语句编辑模式下, 双击窗口右边的某某字段名, 可以在 SQL 语句编辑模式的光标位置插入 `` `某某字段名` ``.

一般来说, 想打出反单引号的话就是在行内代码块的最外层两边分别套两个反单引号. 不过像上面这种反单引号刚好在两边的情况在两边分别加个空格就能解决:

```markdown
`` `某某字段名` ``
```


## WHERE, AND 与 OR


示例:

```sql
SELECT * FROM `addresses` WHERE `state_province` = 'CAL' OR `state_province` = 'WESTERN Cape';
```

用于增加选择条件.


## LIKE 与通配符

`%` 符号是 SQL 中的通配符. 我们配置用户的时候就曾经用到过 `%`.

示例: 

```sql
SELECT * FROM `products` WHERE `product_name` LIKE '%light%';
```

注意 `LIKE` 后面的参数是用半角单引号括起来, 而不是拿反单引号括起来.

`LIKE` 是个 comparison 抑或 comparator 之类的东西.

划重点: `LIKE` 的东西算上通配符什么的以后必须与结果的形式**完全一致**才算匹配上. 默认匹配模式中的模式字符串不区分大小写.

比如: 要匹配 `scdiler network switch` 的话, 你可以:

* `%work%`, 
* `%WORK%`, 
* `%ler%work%`, 

这三个都可以 `LIKE` 上. 但你如果 `%scdiler` 的话, 则是匹配不到的, 因为你 `%scdiler` 这个模式只匹配上了 `scdiler` 本身以及 `s` 前面没有字符的那部分, 但没有体现出在 `r` 的后面有东西.

效果:

![like.png](https://i.loli.net/2019/08/06/fdP216NMoHEZSwv.png)


## WHERE NOT


示例:

```sql
SELECT `username` FROM `users` WHERE NOT `username` = 'quentin92';
```

这样会选出 `user` 表中所有用户名中值并非 `quentin92` 的那些. 注意两边的半角单引号不算到值里. 就上面的情况而言, 我们写 ``WHERE `username` != 'quentin92'`` 或 ``WHERE `username` <> 'quentin92'`` 也是一样的.

你写 ``SELECT `username` FROM `users` WHERE NOT `username` = 'quentin92' OR `username` = 'jackie'`` 和 写 ``SELECT `username` FROM `users` WHERE NOT (`username` = 'quentin92' OR `username` = 'jackie')`` 是一样的, 不过貌似后面这种写法明确了范围, 能省心一点儿. 

上面同时非掉两个情况的例子要仔细确认是 `AND` 还是 `OR`.


## COUNT, SUM 与 AVG

`COUNT`, `SUM` 与 `AVG` 这三个都是 MySQL 中的函数. 当然了, 这只是函数名, 不算是完整的调用. 调用的话, 就是 `函数名()` 的形式, 注意 SQL 中的函数名和括号之间不能有空格, 否则报错, 这一点就不要像 JavaScript 和 PHP 中的闭包那样学了.

此外这三个函数都是要传参进去的, 这个毋庸置疑了, 不传参的话你调用以后都不起什么卵用.


### COUNT

示例:

```sql
SELECT COUNT(`username`) FROM `users`;
```

效果:

![count.png](https://i.loli.net/2019/08/06/8CeHTMvrocYwxFV.png)

从这个效果上来看, 感觉像把 ``COUNT(`username`)`` 整体看成了一个字段, 输出这个字段的值.


也可以结合过滤条件使用:

```sql
SELECT COUNT(`username`) FROM `users` WHERE `username` = 'quentin92';
```

像上面这个查询就是查在 `users` 表中 `username` 字段的值为 `quentin92` 的记录有多少条.


### AVG


`AVG` 就是英文单词 average 的缩写, 这个词是个人都认识, 意思就不说了.

示例:

```sql
SELECT AVG(`product_price`) FROM `products`;
```


效果:

![AVG.png](https://i.loli.net/2019/08/06/C4VuxENwGOsQ1Ki.png)


### SUM

示例:

```sql
SELECT SUM(`product_stock`) FROM `products`;
```


效果:

![sum.png](https://i.loli.net/2019/08/06/5EKylYBbNvVQZa8.png)


最好拿 `SUM` 加点儿有用的东西, 一个苹果加两个梨问有几个水果、一碗泡面加两听皮久blahblah这种驴唇不对马嘴的东西就不要 `SUM` 了.


## INSERT 添加新行

示例:

```sql
INSERT INTO `users` (`username`, `password`, `user_email`, `first_name`, `last_name`) VALUES ('Brad', 'pass1234', 'brad@fakemail.com', 'Brad', 'Goddard');
```



中间用到的 `VALUES` 也是一个函数, 这个函数看文档就知道, 只为 `INSERT` 而生. 文档位置在 [`VALUES(col_name)`](https://dev.mysql.com/doc/refman/5.7/en/miscellaneous-functions.html#function_values)

看文档的时候有个词不认识, 查一下.

miscellaneous [ˌmɪsəˈleɪniəs]

1. adj. A **miscellaneous** group consists of many different kinds of things or people that are difficult to put into a particular category. 混杂的; 五花八门的; 各式各样的
   * ...a hoard of **miscellaneous** junk... 收藏的一堆乱七八糟的破烂
   * They eat a lot of meats and dairy foods, along with a lot of **miscellaneous** items that don't fall into any group. 他们吃了大量的肉和奶制品，还有许多不知道该归为什么类别的杂七杂八的东西。

估计像 TP 框架中的*杂项*的英文单词应该就是这个.


## UPDATE 修改数据

示例:

```sql
UPDATE `users` SET `username` = 'quentin92', `user_email` = 'business@quentinwatt.com', `first_name` = 'Quentin' WHERE `id` = 1;
```


## DELECT 删除记录

示例:

```sql
DELETE FROM `users` WHERE `id` = 16;
```

删东西的时候长点儿心. 直接 `DELETE` 已经属于那种物理删了.


## CREATE 与 DROP - 从建 xx 到删 xx 跑路


### CREATE

示例:

```sql
CREATE TABLE `reviews` (
    review_id INT NOT NULL AUTO_INCREMENT,
    review_title VARCHAR(255) NOT NULL,
    review_description TEXT(1000) NOT NULL,
    users_id INT NOT NULL,
    product_id INT NOT NULL,
    PRIMARY KEY (review_id)
);
```


### DROP

示例:


```sql
DROP TABLE `reviews`;
```


确认完要 `DROP` 以后浏览器左边数据库下的表也会相应减少掉你 `DROP` 的那个.



## ALTER

官方文档的位置是在 [MySQL 5.7 Reference Manual - SQL Statement Syntax - Data Definition Statements - ALTER TABLE Syntax](https://dev.mysql.com/doc/refman/5.7/en/alter-table.html).

当我们拿 `ALTER` 和 `UPDATE` 来操作表的时候, `ALTER` 主要偏向于调整表的结构级别的东西, 而 `UPDATE` 则是在改表中的数据.

示例:

```sql
ALTER TABLE `users` ADD `random_column` VARCHAR(255);
ALTER TABLE `users` MODIFY `random_column` TEXT(1000);
ALTER TABLE `users` MODIFY `random_column` DATE;
ALTER TABLE `users` DROP `random_column`;
```


## JOIN 两表连接


这个东西真没在 MySQL 5.7 的文档里找着.

示例:


```sql
SELECT users.username, users.first_name, users.last_name, addresses.address_line_1, addresses.city, addresses.state_province FROM addresses JOIN users ON addresses.users_id = users.id;
```


效果:


![JOIN.png](https://i.loli.net/2019/08/07/PHgIfODyUa4cmn1.png)

上面例子的 `SELECT users.username, users.first_name, users.last_name, addresses.address_line_1, addresses.city, addresses.state_province FROM addresses JOIN users ON addresses.users_id = users.id;` <=> `SELECT users.username, users.first_name, users.last_name, addresses.address_line_1, addresses.city, addresses.state_province FROM addresses INNER JOIN users ON addresses.users_id = users.id;`


关于 `JOIN` 的具体信息, 可见 [SQL Joins](https://www.w3schools.com/sql/sql_join.asp). 顺便可以看下:

![JOIN的多种方式.png](https://i.loli.net/2019/08/07/EBIdc3PvxNRwnCO.png)

左连接查询示例:

```sql
SELECT users.username, users.first_name, users.last_name, addresses.address_line_1, addresses.city, addresses.state_province FROM addresses LEFT JOIN users ON addresses.users_id = users.id;
```


效果:

![left join.png](https://i.loli.net/2019/08/07/1YNGDe9TdkAUip7.png)


右连接查询示例:

```sql
SELECT users.username, users.first_name, users.last_name, addresses.address_line_1, addresses.city, addresses.state_province FROM addresses RIGHT JOIN users ON addresses.users_id = users.id;
```

效果:

![right join.png](https://i.loli.net/2019/08/07/VfZ7KAsNeMFYcw2.png)

在上面这个右连接查询中就算是没有 address 的 user 也会被查询到.


FULL JOIN:


![full join.png](https://i.loli.net/2019/08/07/8mN6JrvfFV3M7nW.png)

之所以炸了, 并不是因为语法有问题, 而是因为有的 user 没有 address 的这种数据问题.


## JOIN 多(>= 3)表连接

先来回顾一下简单的 `JOIN` :


![simple join.png](https://i.loli.net/2019/08/07/FwNsVtfZXIqJ6ci.png)

下面我们看一下多表连接. 

示例:


```sql
SELECT orders.order_id, products.product_name, users.first_name FROM orders JOIN products ON orders.product_id = products.product_id JOIN users ON orders.order_id = users.id;
```

效果:

![join many.png](https://i.loli.net/2019/08/07/QbJqCVj7O5cDTL8.png)

比如说你想在原先的基础上再连接表的话, 就是 `... JOIN xx表 ON xx字段.xx条件 ...`.

再举个例子:

```sql
SELECT orders.order_id, products.product_name, users.first_name, addresses.city FROM orders JOIN products ON orders.product_id = products.product_id JOIN users ON orders.order_id = users.id JOIN addresses ON orders.address_id = addresses.address_id;
```


效果:

![join many 2.png](https://i.loli.net/2019/08/07/Ny6gX9S7GFOcMZA.png)


## AS (概念上可以理解为英文的 ALIAS) 别名


作用: 改写 SQL 语句中较长的表名或字段名.

随便在 MySQL 的官方文档上查了一下 `AS`, 居然没查着. 但是在关键字列表里能看着, 这我就不知道文档是怎么编的了. 先放一下关键字和保留字列表页: [MySQL 5.7 Reference Manual - Language Structure - Keywords and Reserved Words](https://dev.mysql.com/doc/refman/5.7/en/keywords.html) . 类似的还有 `JOIN` 等等. 说实话, MySQL 的文档每次都查得我头大...怎么说呢, 就是你知道它是语言内置的东西, 但是你想在官方文档里查它是怎么用的就很费劲儿.

先来个基础的热身例子:


```sql
SELECT orders.`order_id`, products.`product_name` FROM orders JOIN products ON orders.product_id = products.product_id;
```


效果:


![intro.png](https://i.loli.net/2019/08/07/MDyspZIOAgbWKEP.png)

我们现在把热身例子用别名的方式改一下:


```sql
SELECT o.`order_id`, p.`product_name` FROM orders AS o JOIN products AS p ON o.product_id = p.product_id;
```


## FOREIGN KEY



示例1 - 添加外键:


```sql
ALTER TABLE orders ADD FOREIGN KEY (product_id) REFERENCES products(product_id);
```

示例2 - 添加外键:

```sql
ALTER TABLE orders ADD FOREIGN KEY (user_id) REFERENCES users(id);
```

如果你想删除外键的话, 像这么删会报错: `ALTER TABLE orders DROP FOREIGN KEY product_id;` MySQL 返回提示说是 #1091 - Can't DROP 'product_id'; check that column/key exists. 这个就是没找到 `product_id` 对应的具体外键名:

![foreign key name.png](https://i.loli.net/2019/08/07/bKgsYnANrXHfMUZ.png) 


这样做才是对的:

```sql
ALTER TABLE orders DROP FOREIGN KEY orders_ibfk_1;
```

这里的 ibfk 意思是 innodb foreign key. 当然了, 我不知道别的引擎是否支持外键, 这个以后有闲心看的时候再说.