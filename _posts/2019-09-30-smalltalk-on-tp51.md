---
layout: post
title: "关于 ThinkPHP 5.1 的记忆"
description: "关于 ThinkPHP 5.1 我知道得不多, 为了公司曾经看过这个."
date: 2019-09-30
tags: [提高姿势水平]
comments: true
share: true
---

> 关于 ThinkPHP 5.1 我知道得不多, 为了公司曾经看过这个.

在这儿写一写 ThinkPHP 5.1 的日常操作.

## ThinkPHP 5.1 的安装

安装的话当然是使用 Composer 安装. 可以参考一下 [ThinkPHP 框架 5.1 版本 composer 安装与 `ls` 结果高亮](https://liujunyi271828.github.io/2019-09-02/install-tp51-framework/) 这篇文章. 总之结果如下:

```bash
cd /path/to/your/project # 这个一般是你 Web 服务器的根目录.
composer create-project topthink/think=5.1.* tp51test # tp51test 是你要安装 ThinkPHP 5.1 的目录. 根据实际调整.
```

装完以后, 看好不好用的话, 需要你打开一个一条龙软件, 比如 MAMP, 再开一个 Apache 服务, 然后在浏览器中输入 `http://localhost:8888/tp51test/public/` (承接上面的 `tp51test`.) 回车, 即可看到初始界面 (MAMP 默认的 Apache HTTPD 服务端口号是 8888):

![Apache8888](https://upload.cc/i1/2019/09/16/louHcA.png)

但是你如果在终端中 `cd` 到 Web 服务器根目录, 然后 `php -S 127.0.0.1:9527` 或是 `php -S localhost:9527` 的话, 会发生: 

![PHPBuiltInServer9527](https://upload.cc/i1/2019/09/16/k0KyQa.png)

暂时不很清楚原因.

你访问 `http://localhost:8888/tp51test/public/index.php/index/index/index` 也是可以看到初始界面的:

![四个index](https://upload.cc/i1/2019/09/16/YTC6dA.png)

这是因为在[架构总览](https://www.kancloud.cn/manual/thinkphp5_1/353953)中说了:

> 5.1 的 URL 访问受路由决定，如果在没有定义或匹配路由的情况下（并且没有开启强制路由模式的话），则是基于：
> 
> > http://serverName/index.php(或者其它入口文件)/模块/控制器/操作/参数/值…

不过在 macOS 上, 你还是把操作系统自身的 Apache httpd 关了, 拿一条龙把这个 8888 端口改成 80 顺便弄个虚拟主机好一点.

## ThinkPHP 5.1 添加模块 + 控制器

出处是 [练习1：Hello,ThinkPHP - 实现二：控制器实现](https://www.kancloud.cn/thinkphp/thinkphp-the-hard-way/548599), 举例如下. 

先 `cd` 到 TP5.1 项目根目录, 然后在终端输入: `php think make:controller 小写字母开头的模块名/大写字母开头的控制器名`. 如: `php think make:controller home/Index`. 

成功的话, 它会提示你一行绿色的字：“Controller created successfully.” 这时候, 在你的 `TP5.1 项目根目录/application/` 目录下会出现一串目录 + 文件, 按照我上面的例子的话就是会多出

1. `TP5.1 项目根目录/application/home/` 模块目录;
2. `TP5.1 项目根目录/application/home/controller` 控制器目录;
3. `TP5.1 项目根目录/application/home/controller/Index.php` 控制器文件

这三个东西.

失败的话, 一般都是 “Could not open input file: think”, 说明你的 pwd 不对, 没能成功发起 think 程序, 应该先 `cd` 到 TP5.1 项目的根目录再一顿操作.

下面我们让它好用.

```php
// TP5.1 项目根目录/application/home/controller/Index.php
namespace app\home\controller;

use think\Controller;
use think\Request;

class Index extends Controller
{
    public function index()
    {
        // 测试方法, 将来在这儿写前台首页.
        return '申帝, 我透你🐴!';
    }
    // 框架给你创建的一堆别的方法.
}    
```

## ThinkPHP 5.1 请求 - 伪静态

地址: [伪静态](https://www.kancloud.cn/manual/thinkphp5_1/353990).

主要是为了 SEO 的. 不过可能甲方爸爸对这个不感兴趣. 关键我配了一下没能像想象地那么好用.

框架中这个属性是在 `ThinkPHP5.1项目根目录/thinkphp/library/think/Request.php` 中**定义**的. 至于你为项目而配置的话, 还是乖乖去 `tp51hardway/config/app.php` 目录下配置好一些.

我试了一下, 不管我怎么弄, 在最新版本的 TP5.1 上只有 `'html'` 后缀是好用的, 真不知道是怎么回事儿, 这个功能应该有问题.

