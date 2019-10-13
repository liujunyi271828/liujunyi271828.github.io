---
layout: post
title: "小程序 from scratch"
description: "为公司上市而学习小程序."
date: 2019-09-20
tags: [提高姿势水平]
comments: true
share: true
---

> 为公司上市而学习小程序.

## 小程序预备姿势

### 1、小程序开发主要分成三部分

* 页面布局: WXML (WeiXin Markup Language, 类似 HTML)
* 页面样式: WXSS (WeiXin Style Sheets, WXSS 具有 CSS 大部分特性。同时为了更适合开发微信小程序，WXSS 对 CSS 进行了扩充以及修改.)
* 页面脚本: JavaScript + WXS


### 2、版本管理

发布的时候才用, 以后再说.


### 3、IDE/编辑器

首选官方的[小程序开发工具](https://developers.weixin.qq.com/miniprogram/dev/devtools/download.html). 然后就是 Sublime Text、Atom 那些第二梯队. WebStorm 除了重构牛逼一点儿以外其他也就 so-so.

关于官方的小程序开发工具, 使用说明见[工具](https://developers.weixin.qq.com/miniprogram/dev/devtools/devtools.html).

## JSON 配置注意事项

JSON文件都是被包裹在一个大括号中 {}，通过key-value的方式来表达数据。JSON的Key必须包裹在一个双引号中，在实践中，编写 JSON 的时候，忘了给 Key 值加双引号或者是把双引号写成单引号是常见错误。

JSON的值只能是以下几种数据格式，其他任何格式都会触发报错，例如 JavaScript 中的 undefined。

* 数字，包含浮点数和整数
* 字符串，需要包裹在双引号中
* Bool 值，`true` 或者 `false`
* 数组，需要包裹在方括号中 `[]`
* 对象，需要包裹在大括号中 `{}`
* `Null`

还需要注意的是 **JSON 文件中无法使用注释**，试图添加注释将会引发报错。

下面看一下在 .json 文件里有哪些可以配置的.


### 全局配置

见[全局配置](https://developers.weixin.qq.com/miniprogram/dev/reference/configuration/app.html).

### 页面(局部)配置

见[页面配置](https://developers.weixin.qq.com/miniprogram/dev/reference/configuration/page.html).

## WXML 简介

[WXML 简介](https://developers.weixin.qq.com/miniprogram/dev/framework/view/wxml/)

​一个完整的 WXML 语句由一段开始标签和一段结束标签组成，在标签中可以是内容，也可以是其他的 WXML 语句，这一点上同 HTML 是一致的。有所不同的是，WXML 要求标签必须是严格闭合的，没有闭合将会导致编译错误。

`<text></text>` 标签: 大概类似于 HTML 中的 `<span></span>`


WXML 中的动态数据均来自**对应 Page**(对应的 .js 文件) 的 data。

[WXML 语法参考](https://developers.weixin.qq.com/miniprogram/dev/reference/wxml/) 下面的内容要好好看下.

### 数据绑定

### 列表渲染


### 条件渲染


### 模板


### 引用




### WeUI 组件库

[WeUI组件库简介](https://developers.weixin.qq.com/miniprogram/dev/extended/weui/)

### 功能组件库

需要 npm: 微信开发者工具 → 工具 → 构建 npm

* [recycle-view](https://developers.weixin.qq.com/miniprogram/dev/extended/functional/recycle-view.html): 长列表组件
* [threejs-miniprogram](https://developers.weixin.qq.com/miniprogram/dev/extended/functional/threejs.html)：Three.js 小程序 WebGL 的适配版本。至于 Three.js 是什么：three.js – JavaScript 3D library
* [lottie-miniprogram](https://developers.weixin.qq.com/miniprogram/dev/extended/functional/lottie.html)：lottie 动画库适配小程序的版本。
* [mobx-miniprogram](https://developers.weixin.qq.com/miniprogram/dev/extended/functional/mobx.html)：可用于小程序的 MobX 构建版本。基于 MobX 4 （因为 iOS 9 不支持 MobX 5 ）。

## WXSS 简介

好像没有专门介绍 WXSS 属性的, 所以就先看了一下这个: [WXSS](https://developers.weixin.qq.com/miniprogram/dev/framework/view/wxss.html).


与 CSS 相比，WXSS 扩展的特性有：

* 尺寸单位
* 样式导入

#### 尺寸单位

* rpx（responsive pixel）: 可以根据屏幕宽度进行自适应。规定屏幕宽为750rpx。如在 iPhone6 上，屏幕宽度为375px，共有750个物理像素，则750rpx = 375px = 750物理像素，1rpx = 0.5px = 1物理像素。

| 设备 |  rpx换算px (屏幕宽度/750) | px换算rpx (750/屏幕宽度)  |
|---|---|---|
| iPhone5 | 1rpx = 0.42px  | 1px = 2.34rpx |
| iPhone6 | 1rpx = 0.5px |  1px = 2rpx |
| iPhone6 Plus | 1rpx = 0.552px | 1px = 1.81rpx |

**建议**： 开发微信小程序时设计师可以用 iPhone6 作为视觉稿的标准。

**注意**： 在较小的屏幕上不可避免的会有一些毛刺，请在开发时尽量避免这种情况。


#### 样式导入

使用 `@import` 语句可以导入外联样式表，`@import` 后跟需要导入的外联样式表的相对路径，用 `;` 表示语句结束。

如:

```css
@import "foo.wxss";
```

#### 内联样式

框架组件上支持使用 style、class 属性来控制组件的样式。

* style：静态的样式统一写到 class 中。style 接收动态的样式，在运行时会进行解析，请尽量避免将静态的样式写进 style 中，以免影响渲染速度。

示例:

```html
<view style="color:{{color-variable}};" />
```


* class：用于指定样式规则，其属性值是样式规则中类选择器名(样式类名)的集合，样式类名不需要带上.，样式类名之间用空格分隔。


示例: 

```html
<view class="bar-class" />
```

#### 选择器

WXSS 目前支持这些选择器, 当然可能实际会更多：

|  选择器 | 样例  | 样例描述  |
|---|---|---|
| `.class`  | `.classname`  | 选择所有拥有 `class="classname"` 的组件  |
| `#id`  | `#idtitle`  | 选择拥有 `id="idtitle"` 的组件  |
| `element`  | `elementname` | 选择所有为 `elementname` 的组件, 比如你 `elementname` 是 `view` 那就是选了所有的 `view` |
| `element1, element2`	 | elementname1, elementname2  | 选择所有为 `elementname1` 和 `elementname2` 的组件|
| `::after` | `element::after` | 在 element 组件后边插入内容 |
| `::before` | `element::before` | 在 `element` 组件前边插入内容 |


#### 全局样式与局部样式

定义在 app.wxss 中的样式为全局样式，作用于每一个页面。在 page 的 wxss 文件中定义的样式为局部样式，只作用在对应的页面，并会覆盖 app.wxss 中相同的选择器。

## WXS 简介

WXS 与 JavaScript 是不同的语言，有自己的语法，并不和 JavaScript 一致。

[WXS 语法参考](https://developers.weixin.qq.com/miniprogram/dev/reference/wxs/)

## 小程序框架

[小程序框架](https://developers.weixin.qq.com/miniprogram/dev/framework/MINA.html) 

这个可能还是得看看的. 

### 框架接口导论

可以在 [小程序框架参考文档](https://developers.weixin.qq.com/miniprogram/dev/reference/) 看到.

这里看几个我目前看到的.

#### 小程序 App: App

[App](https://developers.weixin.qq.com/miniprogram/dev/reference/api/App.html). 在 app.js 中可以看到.


#### 页面: Page

[Page](https://developers.weixin.qq.com/miniprogram/dev/reference/api/Page.html). 在 index.js 中可以看到.

##### 页面的生命周期

[页面生命周期](https://developers.weixin.qq.com/miniprogram/dev/framework/app-service/page-life-cycle.html). 这里就直接放图吧:

![lifecycle.png](https://i.loli.net/2019/09/20/BVZ5S1dnqAhrDEJ.png)

#### 自定义组件: Component

[自定义组件: Component](https://developers.weixin.qq.com/miniprogram/dev/reference/api/Component.html). 你新建一页的时候可以在该页对应的 `.js` 文件中看到.

## 第一个小程序

一个小程序 App 包含多个 Page, 而每个 Page 又包含了很多组件. 这里的组件我理解的是相当于以 HTML 标签为基本单位的对象.

小程序文件结构:

![小程序文件结构.png](https://i.loli.net/2019/09/20/BEPDIqCn1oLt3pF.png)

如果想秒生成一组 `.js` + `.json` + `.wxss` + `.wxml`, 选中 `pages` 目录, 选 `+` 号下面的 `目录` 来建立目标目录用来存放文件, 然后再选到这个目标目录点 `+` 号下的 component 来创建:

![component.png](https://i.loli.net/2019/09/20/AZ8ygibRfloaYvG.png)

新建了什么页以后, 注意上 `app.json` 下的 `pages` 对应的值数组中将该页路径写进去(不用带扩展, 何况你也带不了)来注册该页.


## 杂项

### 1. 微信小程序在 Sublime Text 开发代码高亮显示

[微信小程序在 Sublime Text 开发代码高亮显示](https://blog.csdn.net/kuaixiangzi/article/details/78339522)

### 2. 待查找解决方案: Emmet 等插件正常使用