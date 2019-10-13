---
layout: post
title: "使用 PHP 去掉富文本中的尖角括号标签"
description: "为提高搬砖速度而淬炼技巧."
date: 2019-10-08
tags: [提高姿势水平]
comments: true
share: true
---

> 为提高搬砖速度而淬炼技巧.

![fuck-Scdiler](https://img.shields.io/badge/fuck-scdiler-%23fd9827) ![sponsors-FUCengers](https://img.shields.io/badge/sponsors-FUCengers-brightgreen.svg)

需求是这样的, 比如说我们从 [360doc个人图书馆](http://www.360doc.com/index.html) 这种地方找了个文章, 但是吧直接选中里面内容 ctrl + C 再 ctrl + V 是搞不下来的, 你注册个账号可能都不一定能搞到, 简直不能更坑爹, 所以你自然而然就得查看源代码去把你要的那些纯文本对应的 HTML 富文本代码给复制粘贴过来, 现在说的就是怎么从 HTML 富文本里面搞到纯文本. 那种本身就是个 PDF 或是 DOC 这种的东西不在讨论范围内.

* TOC
{:toc}

## 原生手法: 使用 `strip_tags()` 函数

`strip_tags()` 函数的签名如下:

```php
strip_tags ( string $str [, string $allowable_tags ] ) : string
```

参数描述:

* `str`: The input string.
* `allowable_tags`: You can use the optional second parameter to specify tags which should not be stripped.

备忘:

> * HTML comments and PHP tags are also stripped. This is hardcoded and can not be changed with <strong>allowable_tags</strong>.
> * In PHP 5.3.4 and later, self-closing XHTML tags are ignored and only non-self-closing tags should be used in <strong>allowable_tags</strong>. For example, to allow both <em>&lt;br&gt;</em> and <em>&lt;br/&gt;</em>, you should use:
> 
> ```
> <?php
> strip_tags($input, '<br>');
> ?>
> ```

举例:

```php
<?php

$rich_text = <<<'EOT'
<strong>畐国景区一览</strong>
<ul class="level-1-ul">
    <li class="level-1-li">
        畐国本埠
        <ul class="level-2-ul">
            <li class="level-2-li">畐国本埠3F
                <ul class="level-3-ul">
                    <li id="grand-hall" class="level-3-li" style="border: 2px solid mediumvioletred;display: inline-block;">太极殿</li>
                    <li>3F朝堂</li>
                </ul>
            </li>
            <li>畐国本埠2F
                <ul>
                    <li>修身馆</li>
                    <li>议事殿</li>
                    <li>议事偏殿</li>
                </ul>
            </li>
            <li>畐国本埠1F
                <ul>
                    <li>内务部</li>
                    <li>印书阁</li>
                    <li>1F朝堂</li>
                </ul>
            </li>
        </ul>
    </li>
    <li>
        施德尔大楼
        <ul class="level-2-ul">
            <li>施德尔大楼1F
                <ul>
                    <li>御膳房</li>
                    <li>国宾馆</li>
                </ul>
            </li>
            <li>施德尔大楼2F
                <ul>
                    <li>养心殿</li>
                </ul>
            </li>
            <li>施德尔大楼3F
                <ul class="level-3-ul">
                    <li id="room-306" style="border: 3px solid limegreen;display: inline-block;">306</li>
                </ul>
            </li>
        </ul>
    </li>
</ul>
EOT;

$plain_text = strip_tags($rich_text);

echo $plain_text;
```

效果(输出结果):

> 畐国景区一览 畐国本埠 畐国本埠3F 太极殿 3F朝堂 畐国本埠2F 修身馆 议事殿 议事偏殿 畐国本埠1F 内务部 印书阁 1F朝堂 施德尔大楼 施德尔大楼1F 御膳房 国宾馆 施德尔大楼2F 养心殿 施德尔大楼3F 306

**注意**: 

`strip_tags()` 函数要 strip 的字符串得是 [Nowdoc 结构](https://www.php.net/manual/zh/language.types.string.php#language.types.string.syntax.nowdoc), 也就是: 

```php
$str = <<<'EOD'
Example of string
spanning multiple lines
using nowdoc syntax.
EOD;
```

这种的.

你用 [单引号](https://www.php.net/manual/zh/language.types.string.php#language.types.string.syntax.single) 字符串在碰到 JavaScript 脚本(用单引号的这种情况在 JavaScript 代码规范中确实是非常常见)或是 HTML 标签中的什么 attribute 键对应的值是拿单引号括起来的时候会报类似以下的错, 因为你富文本字符串两边的单引号和富文本内部的单引号结合成对了:

> Parse error: syntax error, unexpected '60' (T_LNUMBER) in /path/to/your/phpfile.php on line xxx

所以为了省事儿起见, 一定要用 Nowdoc 结构... 你用 [双引号](https://www.php.net/manual/zh/language.types.string.php#language.types.string.syntax.double) 字符串和 [Heredoc 结构](https://www.php.net/manual/zh/language.types.string.php#language.types.string.syntax.heredoc) 这种带解析功能的就更不对了...

我知道正则表达式肯定是可以做, 但问题是目前的需求拿原生的手法就可以解决了, 要啥正则表达式😂

## 正则表达式手法

主要是好奇心驱使的, 想看看正则表达式能不能干点儿什么.

看一个推广情形. 表现层 CSS 和 行为层 JavaScript 都属于那种对我们获取结构层 HTML 内容没什么卵用的噪声. 所以我们要把 `<style></style>` 和 `<script></script>` 中的内容给砍掉; 再一方面, 就是 HTML 脚本中 `html>head` 内部的内容基本上也是我们不需要的, 也给砍掉.

我们举个例子. 假设我们的网站根目录是: `/Applications/MAMP/htdocs/`, 端口号为 80, 我们要获取 `/Applications/MAMP/htdocs/learn.jquery.aliyun/19-traversing-5.html` 这个页面的内容, 这个页面的 URL 应该是 `http://localhost/learn.jquery.aliyun/19-traversing-5.html`. 中间用到的 jQuery 库也在 `/Applications/MAMP/htdocs/learn.jquery.aliyun/` 目录下, 不过这个不是很重要. 用来抓取页面内容的 PHP 脚本位于网站根目录 `/Applications/MAMP/htdocs/` 下, 名字随便, 比如说 `test.php` 吧.

要抓取内容的 `19-traversing-5.html` 内容如下:

```html
<!DOCTYPE html>
<html lang="en" dir="ltr">
    <head>
        <meta charset="utf-8">
        <title></title>
        <style>
            span {
                color: green;
            }
            .background {
                background-color: red;
            }
        </style>
        <script src="jquery-3.4.1.js" charset="utf-8"></script>
    </head>
    <body>
        <!-- 实现点击 li 元素本身的时候才触发动画效果, 而点击 li 元素的子元素的时候不会触发动画效果. -->
        <!-- 具体来说, 你点击时间那部分不会触发效果, 你点后面的内容才会触发效果. -->
        <p>阅读下面的材料, 根据要求写作.</p>
        <pre>
1957年, 美国·施德尔智能从此站立起来了! 广大施德尔青年投身于公司建设的新征程.
2007年, “畐国的春天”生机勃勃, 莘莘学子胸怀报国之志, 汇入畐国改革开放的时代洪流.
2017年, 弱电行业的西点军校危亡之际, 校长申硕士带领广大青年掀起了一场彻底反压价甲方反恶劣东北经济环境的伟大弱电公司转型革命运动.
2027年, 青春畐国凯歌前行, 新时代青年奋勇接棒, 宣誓“我爱畐国, 愿你越来越好, 你我一起共同进步成长🎉🎉🎉”.
2057年, 施德尔实现伟大复兴, 畐国有志青年接续奋斗……
        </pre>
        <p>请从下列任务中任选一个, 以青年学生当事人的身份完成写作.</p>
        <ol>
            <li><span>1957年1月1日, </span>在施德尔元年开发者大会上的演讲稿.</li>
            <li><span>2007年9月18日, </span>参加畐国校庆游行暨完成畐国高中函授学习后写给家人的信.</li>
            <li><span>2017年2月15日, </span>参加申校长主持的学生代表座谈会后写的日记.</li>
            <li><span>2027年1月12日, </span>参加畐国学生活动“畐国学生代表大会”后的感想.</li>
            <li><span>2057年1月1日, </span>写给某位“百年SCD功勋人物”的慰问信.</li>
        </ol>
        <p>要求: 结合材料, 自选角度, 确定立意; 切合身份, 贴合背景; 符合文体特征; 不要套作, 不得抄袭; 不得泄露个人信息; 不少于800字.</p>
        <script type="text/javascript">
            $("ol").click(function (event) {
                var target = $(event.target)
                if (target.is("li")) {
                    target.toggleClass("background")
                }
            })
        </script>
    </body>
</html>
```

效果:

![弱电黄埔军校](https://upload.cc/i1/2019/10/09/fyaPLC.png)

负责抓取的 HTML 脚本(第二天早上回来检查的时候才发现太困口胡了, 不是 HTML 脚本而应该是 PHP 脚本, 以后看的人注意一下就好了...) `test.php` 内容如下:

```php
<?php

$url = "http://localhost/learn.jquery.aliyun/19-traversing-5.html";
$fileHeaders = @get_headers($url);
if ($fileHeaders[0] == "HTTP/1.1 200 OK" || $fileHeaders[0] == "HTTP/1.0 200 OK") {
    $content = strip_html_tags(file_url_contents($url));
    echo $content;
}

// Fetch the $url by using cURL
function file_url_contents($url)
{
    $curl = curl_init();
    $timeout = 30;
    curl_setopt($curl, CURLOPT_URL, $url);
    curl_setopt($curl, CURLOPT_RETURNTRANSFER, 1);
    curl_setopt($curl, CURLOPT_CONNECTTIMEOUT, $timeout);
    $return_value = curl_exec($curl);
    curl_close($curl);
    return $return_value;
}

// Remove all the hidden text not displayed on a webpage
function strip_html_tags($str)
{
    $str = preg_replace('/(<|>)\1{2}/is', '', $str);
    $str = preg_replace(
        [ // Remove invisible content
            '@<head[^>]*?>.*?</head>@siu',
            '@<style[^>]*?>.*?</style>@siu',
            '@<script[^>]*?.*?</script>@siu',
            '@<noscript[^>]*?.*?</noscript>@siu',
        ],
        "", // Replace above with nothing
        $str);
    $str = replace_white_space($str);
    $str = strip_tags($str);
    return $str;
}

// Replace all types of whitespace with a single space
function replace_white_space($rawStr)
{
    $result = $rawStr;
    foreach (
        [
            "  ", " \t",  " \r",  " \n",
            "\t\t", "\t ", "\t\r", "\t\n",
            "\r\r", "\r ", "\r\t", "\r\n",
            "\n\n", "\n ", "\n\t", "\n\r",
        ] as $replacement) {
        $result = str_replace($replacement, $replacement[0], $result);
    }
    return $rawStr !== $result ? replace_white_space($result) : $result;
}

```

那么现在我们在浏览器中访问 `http://localhost/test.php`, 结果如下:

> 阅读下面的材料, 根据要求写作. 1957年, 美国·施德尔智能从此站立起来了! 广大施德尔青年投身于公司建设的新征程. 2007年, “畐国的春天”生机勃勃, 莘莘学子胸怀报国之志, 汇入畐国改革开放的时代洪流. 2017年, 弱电行业的西点军校危亡之际, 校长申硕士带领广大青年掀起了一场彻底反压价甲方反恶劣东北经济环境的伟大弱电公司转型革命运动. 2027年, 青春畐国凯歌前行, 新时代青年奋勇接棒, 宣誓“我爱畐国, 愿你越来越好, 你我一起共同进步成长🎉🎉🎉”. 2057年, 施德尔实现伟大复兴, 畐国有志青年接续奋斗…… 请从下列任务中任选一个, 以青年学生当事人的身份完成写作. 1957年1月1日, 在施德尔元年开发者大会上的演讲稿. 2007年9月18日, 参加畐国校庆游行暨完成畐国高中函授学习后写给家人的信. 2017年2月15日, 参加申校长主持的学生代表座谈会后写的日记. 2027年1月12日, 参加畐国学生活动“畐国学生代表大会”后的感想. 2057年1月1日, 写给某位“百年SCD功勋人物”的慰问信. 要求: 结合材料, 自选角度, 确定立意; 切合身份, 贴合背景; 符合文体特征; 不要套作, 不得抄袭; 不得泄露个人信息; 不少于800字.

注意就是 URL 要带上协议名, 不然你在上面这块儿

```php
$url = "localhost/learn.jquery.aliyun/19-traversing-5.html";
$fileHeaders = get_headers($url);
var_dump($fileHeaders);
```

的话, 结果会是:

> Warning: get_headers(): This function may only be used against URLs in /Applications/MAMP/htdocs/test.php on line 4
> ...
> 
> /Applications/MAMP/htdocs/test.php:5:boolean false

因为 `get_headers()` 函数的签名和方法描述是这样:

```php
get_headers(string $url [, int $format = 0 [, resource $context ]]) : array
```

`get_headers()` returns an array with the headers sent by the server in response to a HTTP request.

`get_headers()` 函数的参数解释如下:

* url - The target URL.
* format - If the optional format parameter is set to non-zero, `get_headers()` parses the response and sets the array's keys.
* context - A valid context resource created with `stream_context_create()`.

返回值是这么个情况:

Returns an indexed or associative array with the headers, or FALSE on failure.