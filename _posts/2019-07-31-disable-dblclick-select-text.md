---
layout: post
title: "禁用双击选中HTML页面中的文本效果."
description: "为公司崛起而提高自身前端姿势水平."
date: 2019-07-31
tags: [提高姿势水平]
comments: true
share: true
---

> 为公司崛起而提高自身前端姿势水平.

主要是有的时候双击点什么文本的时候, 把文字还能给选上, 比较烦. 看下处理方法.

```html
<!DOCTYPE html>
<html lang="en" dir="ltr">
    <head>
        <meta charset="utf-8">
        <title>网页中防止双击选中HTML中文字</title>
        <style>
            .test-span {
                -moz-user-select:none; /* 火狐 */
                -webkit-user-select:none; /* webkit浏览器 */
                -ms-user-select:none; /* IE10 */
                user-select:none;
            }
        </style>
    </head>
    <body>
        <p onselectstart="return false">申帝我透你妈!<span style="color:red">【双击不会选中文本内容】</span></p>
        <p>串相我透你妈!</p>
        <span class="test-span">申畜你妈炸了.<span style="color:red">【双击不会选中文本内容】</span></span>
        <div>
            <span>串犬你妈炸了.</span>
        </div>
    </body>
</html>

```


效果:


![双击选择文本.png](https://i.loli.net/2019/07/31/5d40fad89c44558654.png)