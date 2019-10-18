---
layout: post
title: "查看当前 Laravel App 使用的 Laravel 框架版本"
description: "认识你的框架."
date: 2019-10-18
tags: [提高姿势水平]
comments: true
share: true
---

> 认识你的框架.

* TOC
{:toc}

最近在看世界上最好的框架 —— Laravel. 你看框架不可能不看文档吧. 结果文档就两个: 一个是 6.x 分支的, 一个是 5.8 分支的. 现在我就想知道我给应用安的是哪个版本的分支.

## 1. 使用命令行查看

```bash
cd Laravel应用根目录
php artisan --version # 结果参考: Laravel Framework 6.3.0
```

注意不是:

```bash
cd Laravel应用根目录
laravel --version # 比如: Laravel Installer 2.1.0
```

这个查的是你 Laravel 安装器的版本.

## 2. 在应用的 composer.json 中查看

具体如下:

```bash
cd Laravel应用根目录
less composer.json
```

结果参考:

```json
{
    "name": "laravel/laravel",
    "type": "project",
    "description": "The Laravel Framework.",
    "keywords": [
        "framework",
        "laravel"
    ],
    "license": "MIT",
    "require": {
        "php": "^7.2",
        "fideloper/proxy": "^4.0",
        "laravel/framework": "^6.2",
        "laravel/tinker": "^1.0"
    },
    后面太长不看......
}    
```

其中 "laravel/framework" 这个键盘对应的值是 Laravel 框架的大版本号.

## 3. 写代码去看（个人比较不推荐）

可以是可以, 但是还是喜欢命令行交互或是简单查看配置文件. 

在 `Laravel应用根目录/routes/web.php` 里注册一个**专门**用于查看框架版本的路由, 比如:

```php
Route::get('version', function () {
    return "你应用里的 Laravel 框架的版本是: ".app()::VERSION;
});
```

然后你在浏览器中访问 `http://网站根目录/version` 就能看到.

## 4. 去框架文件里看（费事儿，个人很不推荐）

为什么个人不推荐? 你看个版本号你还得专门去查位置, 再跑那么里面, 又不是 php.ini 那种重要的东西, 再说 php.ini 也是 `phpinfo();` 就完事儿了.

具体如下:

```bash
cd Laravel应用根目录/vendor/laravel/framework/src/Illuminate/Foundation/
less Application.php
```

结果参考:

```php
class Application extends Container implements ApplicationContract, HttpKernelInterface
{
    /**
     * The Laravel framework version.
     *
     * @var string
     */
    const VERSION = '6.3.0';
    
    /**
     * 和版本无关的内容blahblah, 太长不看.
     */
}    
```