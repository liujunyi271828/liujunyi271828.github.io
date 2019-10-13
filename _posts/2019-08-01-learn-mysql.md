---
layout: post
title: "MySQL笔记"
description: "为公司上市霸业而学习MySQL."
date: 2019-08-01
tags: [提高姿势水平]
comments: true
share: true
---


[![996.icu](https://img.shields.io/badge/link-996.icu-red.svg)](https://996.icu) [![LICENSE](https://img.shields.io/badge/license-Anti%20996-blue.svg)](https://github.com/996icu/996.ICU/blob/master/LICENSE) ![fuck-Scdiler](https://img.shields.io/badge/fuck-Scdiler-brightgreen.svg) ![sponsors-FUCengers](https://img.shields.io/badge/sponsors-FUCengers-brightgreen.svg) 

* TOC
{:toc}


## 前言


照例寒暄几句, 以免上来就干太过硬核.

以前摸过SQLite、MicroSoft SQL Server, MySQL算是我接触的第二个数据库(和MicroSoft SQL Server差不多同时期). 不过只会建库建表和CRUD... 所以好好看看.


看的是 Learning MySQL and MariaDB by Russell J.T. Dyer (O’Reilly). Copyright 2015 Russell J.T. Dyer, 978-1-449-36290-4.

## Part 1: 软件

> 关键程序之一: 服务器 `mysqld`(d 代表 daemon, 即守护进程, 通常服务器都是守护进程). MySQL 和 MariaDB 的守护进程都叫 `mysqld`. 该守护进程必须一直运行着, 这样人们才能访问并修改数据. 如果你是管理员, 你就有能力进行配置, 使 `mysqld` 符合你建立 数据库系统的需求. 

*原来 d 是 daemon 的意思!!! 隔了两三年终于知道了...*

> 关键程序之二: 关键程序, 就是基本的 MySQL 客户端, 简称 `mysql`, 本书中经常用到它. 有了它, 你就可以与 `mysqld`, 即数据库, 进行交互. 


### 第 1 章: 入门


没啥可说的.

### 第 2 章: 安装 MySQL 和 MariaDB


#### 2.3 获取软件

检查 MySQL 是否安装(在 Linux 或 macOS 上):


```shell
ps aux | grep mysql
```

或


```bash
mysqladmin -p version status
```

#### 2.5 各种_AMP

就是一条龙软件.



*  最新 Linux 版, 请看 Apache XAMPP 网站(多出的 P 是指 Perl):http://www.apachefriends. org/en/xampp-linux.html. 尽管该网站将这个包称为 XAMPP 而非 LAMPP, 但其实是一 回事. 
*  最新 Mac 版, 请看 SourceForge MAMP 网站:http://sourceforge.net/projects/mamp/. 
* 最新 Windows 版, 请看 EasyPHP WAMP 网站:http://www.easyphp.org/download.php. 


##### 2.5.2 Mac OS X发行版


MariaDB 的安装: 写书的时候 macOS 上还没有 MariaDB 的官方安装工具, 不过可以用 `homebrew` 来安装: 

```bash
brew install mariadb
```


#### 2.6 安装后


##### 2.6.2 给root设置初始密码


MySQL 的 root 跟操作系统的 root 是完全不同的两个概念(虽然名字一样). 它只在 MySQL 和 MariaDB 中有意义. 



##### 2.6.4


我们最好不要用 root 来做数据库的日常管理. 要建立另一个用户, 用这条命令:

```bash
mysql -u root -p -e "GRANT USAGE ON *.*
TO '用户名字符串blahblah'@'主机名字符串blahblah'
IDENTIFIED BY '密码字符串blahblah';"
```

这样如果提示

> -bash: !': event not found 

之类的东西的话, 我个人是先 `mysql -u root -p` 进去之后再 `GRANT USAGE ON *.* TO '用户名字符串blahblah'@'主机名字符串blahblah' IDENTIFIED BY '密码字符串blahblah';` . 注意要加半角单引号 `'`.

---

上面这个用户只能从 localhost(举例来说) 登录 MySQL. 其中 *.* 表示所有 数据库和所有表. 更详细的解释会在后面讲到. 同时这里将其密码设置为 `xxx...` . 但他现在还没有任何权限: 不能查看数据库, 更不用说写入数据. 

给这个人只读的话是用 

```sql
GRANT SELECT ON *.* TO '用户名字符串blahblah'@'主机名字符串blahblah'
``` 

这种的. 现在这个人无法增加、修改或删除数据. 如果你想给他查询以外的权限, 可用逗号分隔来指定.


给这个人赋予所有权限是:

```sql
GRANT ALL ON *.* TO '用户名字符串blahblah'@'主机名字符串blahblah';
```


都弄好以后, 如果不小心 `exit` 了就再 `mysql -u root -p` 登录, 进到 MySQL 模式以后刷新权限:

```sql
flush privileges;
```

查看某用户的权限(先 `mysql -u root -p` 进去):


```sql
SHOW GRANTS FOR '用户名字符串blahblah'@'主机名字符串blahblah'\G 
```

### 第 3 章: 基础知识与 MySQL 客户端

#### 3.2 连接到服务器

比如说我们有个叫 learn.mysql 的用户, 那我们可以在终端输入

```bash
mysql -u learn.mysql -p
```

来连接 MySQL. 自己用的时候把我上面例子的用户名换成自己的用户名. 这个也是比较基础的了...

`-p` 后面可以带参数, 这个参数不需要用半角单引号引起来. 不过带参数的话别人很容易看到, 而且这个参数将在网络上以明文方式传输, 同时, 只要有人监控着服务器的进程列表, 那么他也能看到. 所以你想想该不该带吧...

如果你要用的 MySQL 用户名与操作系统的相同，那么你不需要加上 `-u` 选项，直接 `-p` 就行。即是这样:

```bash
mysql -p
```

登录进去后: 

```
Welcome to the MySQL monitor.  Commands end with ; or \g. # 这行说的是命令要以分号(`;`) 或斜线 +g(`\g`)结尾. 
Your MySQL connection id is 22 # 本次连接的标识号
Type 'help;' or '\h' for help. Type '\c' to clear the current input statement. # 获得帮助。如果你想取消输入到一半的 SQL 语句，可接着输入 \c，然后无需加分号，直接按 Enter 键。这样就能清空 mysql 缓存着的那写到一半的命令，甚至分行输入的也能清空，使你回到 mysql> 提示符。
```

不过这个 `\c` 看起来你用 control + c 也行.


关于帮助: 

* `help`: 此命令会介绍如何使用 `mysql`。
* `help contents`: 此命令将 MySQL 或 MariaDB 的各种帮助分门别类地以列表展示出来。在列表中你会看到有个 Data Manipulation，里面就包含了有关增删改的 SQL 语句。
* `help Data Manipulation`: 此命令会将所有可用的数据操作语句显示出来，比如 SHOW DATABASES。
* `help SHOW DATABASES`: 此命令用于找到 SQL 语句相关的帮助。如你所见，`mysql` 提供了大量有用的信息。如果你忘了某个 SQL 语法，可以在这里快速地找到答案。



#### 3.3 开始探索数据库

表: 表是用于存储数据的，反映用户查看数据的方式。


查看表的话在 m`ysql>` 提示符处输入:

```sql
SHOW DATABASES;
```



MySQL 不区分关键字(如 SHOW)的大小写，所以你可以用 `show` 甚至 `sHoW`。然而，数据库、表和列的名字却可能是区分大小写的，尤其是在那些大小写敏感的操作系统上，如 macOS 或 Linux。大多数书籍和文档都会将关键字大写，但同时告诉你其实可以随意大小写。对于数据库、表和列的名字，我们全用小写，因为这样看着舒服，敲字也简单.

查看表结构:

```sql
DESCRIBE 表名blahblah;
```

回车会出来(比方说像下面这样):

```
+---------+---------+------+-----+---------+-------+
| Field   | Type    | Null | Key | Default | Extra |
+---------+---------+------+-----+---------+-------+
| book_id | int(11) | YES  |     | NULL    |       |
| title   | text    | YES  |     | NULL    |       |
| status  | int(11) | YES  |     | NULL    |       |
+---------+---------+------+-----+---------+-------+
```

下面来几个例子, 主要是这个 `\G` 我没见过:


![select.png](https://i.loli.net/2019/08/01/5d42b1a988fbc34646.png)


## Part 2: 数据库结构


### 第 4 章: 创建数据库和表

建表要考虑的一些基本问题:


创建时需要考虑的一些基本问题。
* 数据库中要建多少个表，以及需要多少个表名。 
* 每个表中要建多少列，以及需要多少个列名。
* 每一列存储的数据类型。