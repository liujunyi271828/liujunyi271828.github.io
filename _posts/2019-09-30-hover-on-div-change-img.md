---
layout: post
title: "鼠标指针放在 &lt;div&gt; 上, 然后里面的 &lt;img&gt; 会改变, 鼠标移出时又会变回原状效果实现 1.0 版"
description: "为公司上市而学习做导航栏."
date: 2019-09-30
tags: [提高姿势水平]
comments: true
share: true
---

> 为公司上市而学习做导航栏.

整理一下, 以备后用.


这个是一个核心基于 jQuery 的实现. 底子是在 Bootstrap 4.3.1 框架里写的. 你要是正常用 Bootstrap 的话, 不可能不导入 jQuery, 不然我就从 SCD 大楼楼顶上跳下来.

## 资源介绍

主要就是 Bootstrap 那几样:

1. bootstrap-4.3.1.min.css
2. jquery-3.4.1.slim.min.js
3. popper-1.15.0.min.js
4. bootstrap-4.3.1.min.js

上面都是 Bootstrap 4.3.1 时期的那一套, 要是中间儿哪个东西更新的话就不关我事儿了.

自己写的 CSS 样式基本就是就调个字的颜色和 `<div></div>` 元素宽度还有浮动啥的, 没啥本质的东西, 基本可以无视. 后文中 `scd` 前缀的基本就是相关的 CSS. 剩下基本都是 Bootstrap 的 class.

图标的话用这个目录下面的: [nav 图标](https://github.com/liujunyi271828/resources/tree/master/img/2019-09-30-nav). 列表如下:

![导航图标素材列表](https://upload.cc/i1/2019/09/30/P8Q6Ht.png)

如果我没调整目录的话自然好用, 所以如果链接挂了的话就是我不知道什么时候调整目录了...重点其实还是怎么做这个的技巧, 图标应该都是小意思吧...


## 难点

主要是你 hover 到 div 上之后, 你的 img 和文字要同时变化. 文字还好说, 写个 `:hover` 就完事儿了; img 不好弄.

不多哔哔, 下面看代码.

## HTML 内容表现

核心部分: `nav>ul>((li>a>div>(img+p))*6)`

```html
<nav class="navbar navbar-ligh navbar-toggler rounded-0 bg-light p-0 m-0" id="scd-nav-bar w-100">
    <ul class="nav m-0 p-0">
        <li>
            <a class="m-0 p-0" href="index.html">
                <div class="scd-nav-item" id="scd-nav-item-index">
                    <img src="../static/img/nav/index.png" alt="">
                    <p>网站首页</p>
                </div>
            </a>
        </li>
        <li>
            <a class="m-0 p-0" href="">
                <div class="scd-nav-item" id="scd-nav-item-product">
                    <img src="../static/img/nav/product.png" alt="">
                    <p>产品中心</p>
                </div>
            </a>
        </li>
        <li>
            <a class="m-0 p-0" href="">
                <div class="scd-nav-item" id="scd-nav-item-support">
                    <img src="../static/img/nav/support.png" alt="">
                    <p>服务支持</p>
                </div>
            </a>
        </li>
        <li>
            <a class="my-0 py-0" href="">
                <div class="scd-nav-item" id="scd-nav-item-solution">
                    <img src="../static/img/nav/solution.png" alt="">
                    <p>解决方案</p>
                </div>
            </a>
        </li>
        <li>
            <a class="m-0 p-0" href="">
                <div class="scd-nav-item" id="scd-nav-item-aboutscd">
                    <img src="../static/img/nav/aboutscd.png" alt="">
                    <p>关于施德尔</p>
                </div>
            </a>
        </li>
        <li>
            <a class="m-0 p-0" href="">
                <div class="scd-nav-item" id="scd-nav-item-joinus">
                    <img src="../static/img/nav/joinus.png" alt="">
                    <p>加入我们</p>
                </div>
            </a>
        </li>
    </ul>
</nav>
```

## JavaScript 动画渲染效果

实装的时候可以放在 `<script></script>` 标签中.

我在想能不能就是用 JavaScript 调整图片名, 这个说实话有点儿费劲儿...关键你实现 JavaScript 增加图片名修改图片名的这个时间都够把整套效果写完了...

上面只是个思路, 以后可以试试...

```javascript
$(function () {
    /**
     * 实现鼠标放到区域和移出区域时申帝心心念念的的高大上效果.
     * 必须一定要先在页面 head 标签内引入来自大洋彼岸家乡老乡的 jQuery 库才能看到高大上的效果.
     */
    /* 网站首页. */
    $("#scd-nav-item-index").hover(
        function () {
            $(this).children("img").attr('src', '../static/img/nav/index-hover.png')
        },
        function () {
            $(this).children("img").attr('src', '../static/img/nav/index.png')
        }
    )
    /* 产品中心. */
    $("#scd-nav-item-product").hover(
        function () {
            $(this).children("img").attr('src', '../static/img/nav/product-hover.png')
        },
        function () {
            $(this).children("img").attr('src', '../static/img/nav/product.png')
        }
    )
    /* 服务支持. */
    $("#scd-nav-item-support").hover(
        function () {
            $(this).children("img").attr('src', '../static/img/nav/support-hover.png')
        },
        function () {
            $(this).children("img").attr('src', '../static/img/nav/support.png')
        }
    )
    /* 解决方案. */
    $("#scd-nav-item-solution").hover(
        function () {
            $(this).children("img").attr('src', '../static/img/nav/solution-hover.png')
        },
        function () {
            $(this).children("img").attr('src', '../static/img/nav/solution.png')
        }
    )
    /* 关于施德尔. */
    $("#scd-nav-item-aboutscd").hover(
        function () {
            $(this).children("img").attr('src', '../static/img/nav/aboutscd-hover.png')
        },
        function () {
            $(this).children("img").attr('src', '../static/img/nav/aboutscd.png')
        }
    )
    /* 加入我们. */
    $("#scd-nav-item-joinus").hover(
        function () {
            $(this).children("img").attr('src', '../static/img/nav/joinus-hover.png')
        },
        function () {
            $(this).children("img").attr('src', '../static/img/nav/joinus.png')
        }
    )
})
```

### 关于用到的 jQuery 方法 `.hover()`

在 [`.hover()`](https://api.jquery.com/hover/) 方法的描述中说:

> Calling `$(selector).hover(handlerIn, handlerOut)` is shorthand for:
> 
> ```javascript
> $(selector).mouseenter(handlerIn).mouseleave(handlerOut);
> ```

也就是说, 你用 [`.mouseenter()`](https://api.jquery.com/mouseenter/)、[`.mouseleave()`](https://api.jquery.com/mouseleave/) 的话也可以. 不过还是推荐用 `hover()` 写.

## 效果

之前: 

![before](https://upload.cc/i1/2019/09/30/qSFVyi.png)

之后: 

![after](https://upload.cc/i1/2019/09/30/G3taB6.png)