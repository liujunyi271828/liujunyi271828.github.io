---
layout: post
title: "小程序基本操作"
description: "为公司上市而学习小程序."
date: 2019-09-21
tags: [提高姿势水平]
comments: true
share: true
---

> 为公司上市而学习小程序.

[![996.icu](https://img.shields.io/badge/link-996.icu-red.svg)](https://996.icu) [![LICENSE](https://img.shields.io/badge/license-Anti%20996-blue.svg)](https://github.com/996icu/996.ICU/blob/master/LICENSE) ![fuck-Scdiler](https://img.shields.io/badge/fuck-Scdiler-brightgreen.svg) ![sponsors-FUCengers](https://img.shields.io/badge/sponsors-FUCengers-brightgreen.svg)

* TOC
{:toc}

## 前言

看了三天小程序. 当然, 这里的三天只是三天历史. 又不是什么时候都在看...

不过经验还是有的. 比如你可以从 ThinkPHP 框架中类比出模板的相关操作, 至少你看个 Mushache (是这么拼吧? 我只知道后面四个字母和 cache 特别像😂 PS: 还是拼错了, 是 Mustache)语法还是不会特别特别奇怪吧; 再就 [框架接口 → 页面 → Page](https://developers.weixin.qq.com/miniprogram/dev/reference/api/Page.html) 里的那堆方法

![page](https://upload.cc/i1/2019/09/21/TsdyrC.png)

![page-demo](https://upload.cc/i1/2019/09/21/Ic3glt.png)

是不是和 iOS 里的视图生命周期那堆方法特别像:

![view.png](https://i.loli.net/2019/09/21/B3p6euHWk5ad2NV.png)

各自的生命周期图如下:

[微信小程序版](https://developers.weixin.qq.com/miniprogram/dev/framework/app-service/page-life-cycle.html): 

![lifecycle.png](https://i.loli.net/2019/09/23/D7UIBmbnOtcyeZf.png)

[iOS 版(截止到 2019 年在官网看到的版本)](https://developer.apple.com/documentation/uikit/uiviewcontroller?language=objc):

![apple-life-cycle.png](https://i.loli.net/2019/09/23/4fMA3LFadC1nJKy.png)

括号里我加的那句的意思是: 有的老版本的 iOS 版的图(以各种中文版的图为主)就不要看了. 都 deprecated 了还看啥...

做 iOS 的话除上面官网链接外这个也可以看一下: [Looking to understand the iOS UIViewController lifecycle](https://stackoverflow.com/questions/5562938/looking-to-understand-the-ios-uiviewcontroller-lifecycle).

---

这么多年过去了, Objective-C 还是那个优雅的 Objective-C, 感动. Objective-C 算是 Smalltalk 的精神继承吧, 当然原版的 Smalltalk 我不了解, 我见过的是 Pharo 方言版的 Smalltalk.

前戏先到这里. 主要是上来就说 code 没什么代入感, 从情感方面的角度看给人感觉也不是很好. 下面 show world the code. 

## JSON

JSON(JavaScript Object Notation) 作为数据载体还是比较重要的. 比如你从接口地址 request 数据得拿 JSON 传吧. 

可以看看 [JSON](http://www.json.org) 的介绍. 不过我写差不多的时候才发现有 [中文版](http://www.json.org/json-zh.html) 的😂这里摘抄部分, 毕竟看看基础也不错:

JSON 由两类结构构建:

* A collection of name/value pairs. In various languages, this is realized as an *object*, record, struct, dictionary, hash table, keyed list, or associative array.
* An ordered list of values. In most languages, this is realized as an *array*, vector, list, or sequence.

下面介绍一下 JSON 中的各种元素. 这里我把顺序调整了一下. 毕竟你前面的图用到后面的东西算什么回事儿, 这就和美国队长 3 里出现黑豹、复仇者联盟 3 结尾菜单里 @ 了惊奇队长性质类似😂

另外 object 和 array 看起来像是官方划的重点.

### 1. JSON - Whitespace

*Whitespace* can be inserted between any pair of tokens. Excepting a few encoding details, that completely describes the language.

英语比较简单, 没什么生词, 不翻译了.

![1-whitespace.png](https://i.loli.net/2019/09/21/W8R2hUHZmwBkcuJ.png)

### 2. JSON - Number

A *number* is very much like a C or Java number, except that the octal and hexadecimal formats are not used.

![2-number.png](https://i.loli.net/2019/09/21/t6PeFcskUvhDrdQ.png)


### 3. JSON - String

A *string* is a sequence of zero or more Unicode characters, wrapped in double quotes, using backslash escapes. A character is represented as a single character string. A string is very much like a C or Java string.

![3-string.png](https://i.loli.net/2019/09/21/o1jlbCYgGqQ6S5m.png)

### 4. JSON - Object

`<tt>` 这个标签现在凉凉了, 具体的替代方法, 可以看 [&lt;tt&gt;: The Teletype Text element (obsolete)](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/tt) (这块儿 `[]()` 里的那个锚文本的大于号和小于号需要用 HTML 实体转义, 要不我在编辑器里看后面全特么给渲染成 Teletype Text 元素了), 翻到底下有个 CSS 样式替代的代码:

**CSS**:

```css
tt {
  font-family: "Lucida Console", "Menlo", "Monaco", "Courier",
               monospace;
}
```

**HTML**:

```html
<p>Enter the following at the telnet command prompt: <code>set localecho</code><br />

The telnet client should display: <tt>Local Echo is on</tt></p>
```

前面一些的地方还说过:

This element is obsolete, however. You should use the more semantically helpful [`<code>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/code), [`<kbd>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/kbd), [`<samp>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/samp), or [`<var>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/var) elements for inline text that needs to be presented in monospace type, or the [`<pre>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/pre) tag for content that should be presented as a separate block.

> If none of the semantic elements are appropriate for your use case (for example, if you simply need to show some content in a non-proportional font), you should consider using the [`<span>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/span) element, styling it as desired using CSS. The [`font-family`](https://developer.mozilla.org/en-US/docs/Web/CSS/font-family) property is a good place to start.

好了, 下面继续看 Object.

---

An <i>object</i> is an unordered set of name/value pairs. An object begins with <span style='font-family:"Lucida Console", "Menlo","Monaco","Courier",monospace;'>{</span><small>left brace</small> and ends with <span style='font-family:"Lucida Console", "Menlo","Monaco","Courier",monospace;'>}</span><small>right brace</small>. Each name is followed by <span style='font-family:"Lucida Console", "Menlo","Monaco","Courier",monospace;'>:</span><small>colon</small> and the name/value pairs are separated by <span style='font-family:"Lucida Console", "Menlo","Monaco","Courier",monospace;'>,</span><small>comma</small>.

![4-object.png](https://i.loli.net/2019/09/21/yXrNz7BUlDHK18C.png)

(尴尬, 前面的话当我没说)

### 5. JSON - Array

An <i>array</i> is an ordered collection of values. An array begins with <span style='font-family:"Lucida Console", "Menlo","Monaco","Courier",monospace;'>[</span><small>left bracket</small> and ends with <span style='font-family:"Lucida Console", "Menlo","Monaco","Courier",monospace;'>]</span><small>right bracket</small>. Values are separated by <span style='font-family:"Lucida Console", "Menlo","Monaco","Courier",monospace;'>,</span><small>comma</small>.

![5-array.png](https://i.loli.net/2019/09/21/2o5ONQZd8ks9y7S.png)

(再尴尬一次...)

### 6. JSON - Value

A *value* can be a *string* in double quotes, or a *number*, or `true` or `false` or `null`, or an *object* or an *array*. These structures can be nested.

![6-value.png](https://i.loli.net/2019/09/21/NGVbSKJY7npfxaM.png)

### 坑点

出自 [起步 - 小程序代码构成 - JSON 配置](https://developers.weixin.qq.com/miniprogram/dev/framework/quickstart/code.html#JSON-配置).

1. 在实践中，编写 JSON 的时候，忘了给 key 值加双引号或者是把双引号写成单引号是常见错误。
2. JSON 文件中无法使用注释，试图添加注释将会引发报错。

结合一下 JSON 的官方文档. 就会发现说得确实是比较有道理的...


## 小程序配置

主要是承接 JSON 的配置. sitemap 的就不说了.

这个内容是在 [框架 - 小程序配置 - 全局配置](https://developers.weixin.qq.com/miniprogram/dev/reference/configuration/app.html) 这里.

### 全局配置

就是 [框架 - 小程序配置 - 全局配置](https://developers.weixin.qq.com/miniprogram/dev/reference/configuration/app.html), 微信官方的这个链接编排我没看明白...

这个参考全局配置的各个配置项看下. 里面有一些比较著名的选项, 比如 `pages`、`window`、`tabBar`、`networkTimeout` 等. 具体如何需要点开各项的链接来看.

全局配置是在 app.json 里写的.

### 页面配置

位置是在 [框架 - 小程序配置 - 页面配置](https://developers.weixin.qq.com/miniprogram/dev/reference/configuration/page.html).

注意: 

> 页面配置中只能设置 app.json 中 `window` 对应的配置项，以决定本页面的窗口表现，所以无需写 `window` 这个属性。

页面中配置项在当前页面会覆盖 app.json 的 `window` 中相同的配置项. 感觉这就和在页面 head 写 style 与导入 CSS 样式表的关系差不多...


## WXML 语法参考

> WXML（WeiXin Markup Language）是框架设计的一套标签语言，结合基础组件、事件系统，可以构建出页面的结构。

要完整了解 WXML 语法，请参考 [WXML 语法参考](https://developers.weixin.qq.com/miniprogram/dev/reference/wxml/), 以及快来开发微信小程序实践一下吧!

微信头像镇楼, 举抱了:

![辣个女人.jpeg](https://i.loli.net/2019/09/21/irh4CfYwnlUaE17.jpg)

以下内容都是在 pages/index 目录下完成的. 除了在 app.json 里注册了一下 pages/index 对应的页面文件路径 pages/index/index.

![目录.png](https://i.loli.net/2019/09/21/yCWqlhEASm8Y2JZ.png)

### [数据绑定](https://developers.weixin.qq.com/miniprogram/dev/reference/wxml/data.html)

下面演示一下数据绑定. 这个是比较重要的.

平时写代码的话注意数据也不要给写死. 留给将来套模板或是循环输出等等一定的发挥空间.

#### 简单绑定

简单绑定的话就使用 Mustache 语法把变量括起来. 谷歌的 google-analytics.html 之类的东西也有这种代码, 不过是不是真能起到作用就不知道了...因为我的 google-analytics 一直没出来数😂

##### 内容

直接上代码:

```html
<!-- index.wxml -->
<!-- 简单绑定 - 内容. -->
<text class="demo">简单绑定 - 内容 demo:</text>
<view>
    <text>{{content}}</text>
</view>
```

```css
/* index.wxss */
.demo {
    color: gray;
    font-size: 24rpx;
    margin-top: 40rpx;
}
```

```javascript
//index.js
Page({
    data: {
        content: '申帝我透你妈!',
    }
})    
```

效果:

![简单绑定](https://upload.cc/i1/2019/09/23/A86mfe.png)


##### 组件属性


代码:

```html
<!-- index.wxml -->
<!-- 简单绑定 - 组件属性. -->
<text class="demo">简单绑定 - 组件属性 demo:</text>
<view>
    <rich-text><h2>东哥语录畐国个性化版</h2></rich-text>
    <!-- WXML 的 view 标签自带换行, 感觉类似 HTML 里的 div 标签. -->
    <view class="brother-motto-{{no1}}">申帝永远不会开除任何一个兄弟!</view>
    <view class="brother-motto-{{no2}}">混日子的人不是申帝的兄弟.</view>
</view>
```

```css
/* index.wxss */
.demo {
    color: gray;
    font-size: 24rpx;
    margin-top: 40rpx;
}

rich-text {
    text-align: center;
}

.brother-motto-1 {
    color: green;
}

.brother-motto-2 {
    color: red;
}
```


```javascript
//index.js(核心部分)
Page({
    data: {
        no1: 1,
        no2: 2,
    }
})
```


效果: 

![申帝的兄弟](https://upload.cc/i1/2019/09/23/pUIbQh.png)


## WeUI 组件库

前置阅读: [指南 - 自定义组件](https://developers.weixin.qq.com/miniprogram/dev/framework/custom-component/).

安装方法有两种, 一种是 npm 安装, 但是我只在 mac 终端中用过 npm, 所以这个渠道以后再论.

另一种方法是在 [扩展能力 - WeUI 组件库 - 下载组件](https://developers.weixin.qq.com/miniprogram/dev/extended/weui/download.html) 中按需下载. 注意阅读 [快速上手](https://developers.weixin.qq.com/miniprogram/dev/extended/weui/quickstart.html).

## WXSS 备忘

下面看一下 WXSS 的相关基本内容.

### 长度单位 rpx

rpx 是由 WXSS 引入到小程序宇宙中的一个长度单位. 概念上有些类似于 rem.

rpx（responsive pixel）: 可以根据屏幕宽度进行自适应。规定屏幕宽为750rpx。如在 iPhone6 上，屏幕宽度为375px，共有750个物理像素，则750rpx = 375px = 750物理像素，1rpx = 0.5px = 1物理像素。

| 设备 |  rpx换算px (屏幕宽度/750) | px换算rpx (750/屏幕宽度)  |
|---|---|---|
| iPhone5 | 1rpx = 0.42px  | 1px = 2.34rpx |
| iPhone6 | 1rpx = 0.5px |  1px = 2rpx |
| iPhone6 Plus | 1rpx = 0.552px | 1px = 1.81rpx |

**建议**： 开发微信小程序时设计师可以用 iPhone6 作为视觉稿的标准。

所以一般来说我们的 1rpx = 0.5px 是没跑了, 当然更常用的关系应该是 1px = 2rpx.

## WXS 语法参考

这个要是时间够的话就写一写.

## WXS 编程

这里写一下看到的比较有用的想法.

### 封装

将一些常用的操作封装到一起, 比如将网络请求这种的封装为一个自制的函数. 爱怎么调怎么掉, 就算官方的 API 改了对你本身的影响也比较小.

比方说网络请求的话可以使用 [Promise](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) 技术. 关于 Promises 的基础可以看 [Using Promises](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Using_promises).

再就这个微信开发者工具好像是对重构方面儿的功能支持不太好.

## 微信开发者工具使用

下面记一下微信开发者工具的几个常用操作.

### 检查 WXML 元素

开发者默认工具的调试器部分好像是没给咱提供检查元素功能, 需要自己在调试器处打开:

![查看元素.png](https://i.loli.net/2019/09/24/sm1xTcdaKJw4b53.png)

选中 Wxml 之后, 再在**调试器中的** Wxml 界面中选择指定的 WXML 元素, 就可以看到对应结果:

![检查元素结果.png](https://i.loli.net/2019/09/24/EZsnPu7riXt8WBS.png)

## PhotoShop 使用

看一下你为了写一个页面而获取相关数据时的相关 PS 操作.

### 像素单位区域尺寸测量

看区域的尺寸的话, 可以:

![测量.png](https://i.loli.net/2019/09/23/rKw5udkztCYOWID.png)

1. 使用图上从上到下数的第二个图标里的 Rectangualar Marquee Tool: ![rect.png](https://i.loli.net/2019/09/23/7SAifqERL8dcV6G.png) 用的时候注意右键点一下标尺, 选到合适的尺寸单位上: ![scale.png](https://i.loli.net/2019/09/23/HLdxwozK6qltDiQ.png) 比如 Pixels 之类的, 不然如果做前端部分的话你用 Centimeters 卵用没有, 耽误产值不说还影响心情和士气.
2. 使用图上从上到下数的第六个图标里的 Ruler Tool: ![rulertool.png](https://i.loli.net/2019/09/23/5RjuEqkyvb1JrLd.png) 你可以在选择起点和终点这期间按下 shift 键, 这样你的线就会保持水平或铅直, 不然你量个斜线也没啥用是吧, 又不是给你家 29 寸彩电弄前端.

### 像素单位字号测量

字号测量的话是使用 Horizontal Type Tool 这个东西: ![horizon-type-tool.png](https://i.loli.net/2019/09/23/WmOG1K5HM76SdBi.png) 顾名思义, 这个是水平方向的; 垂直方向我感觉应该是 Vertical Type Tool, 不过我没用过, 就不浪费时间试了.

此外有的人可能会遇见默认测量的字体单位为 pt 的情形, 很显然这个单位上市性也不强, 我们要是用 px 这个上市性强的单位的话, 应该上偏好设置这种地方去设置: ![字号单位.png](https://i.loli.net/2019/09/23/Oz4sSx8kM1AXdiD.png) 把 Type 项的单位设成 px, 这样量完之后上面就会按照 px 给你显示.



### 十六进制颜色取色

第一步: 右键图里左侧的从上到下数第六个图标, 选择其中的 Color Sampler Tool. 然后在下面那个黑白图里点上边儿那个小的, 也就是那个直角箭头往左指的那个小的黑白图标, 把前景色弄成黑色、背景色弄成白色:

![color-picker.png](https://i.loli.net/2019/09/23/BLRGZbTvNEMrXK6.png)

第二步: 点直角箭头向下指的那个大的黑白图标中的黑色部分, 会出现一个胶头滴管状的东西和 Color Picker (Foreground Color) 界面:

![hex-color.png](https://i.loli.net/2019/09/23/FHvomxD8XgIuOkE.png) 

第三步: 你拿这个胶头滴管状的东西去点目标区域, 就能在上面的 Color Picker (Foreground Color) 界面中显示出你心心念念的十六进制值.(第把把该放在第二步的图放到第三步了, 导致图截得有点儿问题, 不改了, 能看懂文字叙述就行.)

像你在 CSS 里写的颜色拿腰子原生的数码测色计再在 `rgb(R, G, B[, A])` 或 `rgba(R, G, B, A)` 函数里填各个分量的值对付一下也就算了, 不过后来我发现也有十六进制显示的:

![数码测色计.png](https://i.loli.net/2019/09/23/sjmAdv4173IopPy.png)

当然拿函数记法对付对付在没法用这种函数记法颜色表示的场合还是比较好用的. 想办法把产值干出来.

如果要获取 PhotoShop 工作区域外的区域的颜色的话, 需要长按鼠标左键,直到取到目标点位的颜色值.

难倒不是很难. 但是很麻烦, 时不时就得查个这种和技术没有什么关系的东西, 很影响士气. 归档的话费时间, 不归档吧万一忘了还烦躁. 

### 矩形圆角半径测量

这个暂时没学会, 等以后能实装测出来了再写.

















