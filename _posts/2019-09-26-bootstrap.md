---
layout: post
title: "Bootstrap 4"
description: "Bootstrap 4 学习"
date: 2019-09-26
tags: [提高姿势水平]
comments: true
share: true
---


Bootstrap 大概是在 2010 年左右被推特的人开发粗来. 总之 Bootstrap 是个比较火的响应式 CSS 框架. 现在要看的是 4.3.1 版本.

正在写的过程中, 如果打开网页看 404 了, 请把 URL 中的 4.3 自行换成 3.4, 因为我这最开始是基于 3.4 写的.


## 第一章 从CSS开始


### 1.1 基础


一个HTML文件有三种方式使用CSS语句:

1. 在HTML元素里的`style`属性里写.
2. 在`<style></style>`元素里写.
3. 用`<link />`元素指向包含了样式定义的CSS文件.


比较建议用第三种也就是引用 CSS 文件这个, 这个可以在浏览器缓存的时候引用完, 然后内容可以用适当的工具来展示. 这样可以减少带宽使用.

第二种的那个局部的 `<style>` 元素应当只被使用在例外情形, 比如说对复杂文件的临时改动之类的. 这种局部样式指令具有相对导入样式要更高的优先级; 第一种的 `style` 属性每次只调整单个元素, 在和局部样式、导入样式发生冲突时, 它具有最高的优先级.


指向CSS文件发生在HTML文档的头部 (`<head></head>` 元素内):


```css
`<link rel="stylesheet" type="text/css" href="path/relative/to/html/style.css" />`
```

注意, 指向的 CSS 文件路径是相对于当前 HTML 文件的路径.


### 1.2 语法

CSS 的语法比较简单, 主要结构包含了两个构建块(building block):


> 1. 选择器(selector)
> 
> 2. 规则集(ruleset)


选择器指定了规则所应用的元素:


```css
selector {
    ruleset
}
```



当样式在`style`属性里的时候, 它们只在该标签中生效, 因此选择器被省略掉.

标准的规则集由规则构成. 它们具有如下形式:

```css
style: parameter;
```

规则后面的分号得加上.



### 1.3 选择器


选择器是页面上元素可以被选择性获取的手段. 选择器本身是个比较复杂的课题, 这里我们看几个最常用的.


#### 1.3.1 元素(标签) (Element (Tag))


用CSS可以处理各种独立的物件(individual items). 元素选择器的语法如下:

```css
tag-name {
    ruleset
}
```


举例来说, 想获取所有的`<p>`元素, 可以这么写:

```css
p {

}
```



#### 1.3.2 ID


通常每个标签都会被格式化. 这个标签必须得是可分辨的, 也就是说它得有个可访问的ID. HTML的ID属性(attribute)包含一个字符串, 其在CSS属性(property)中可以被获取. 一个ID在一个文件中最多只能被应用到一个元素上, 因而也只最多只能出现一次. ID选择器的语法如下:

```css
#id {

}
```


举个栗子:

```html
<style> 
#send {
    color: red;
}
</style>
<button id="send">发送</button>
```



#### 1.3.3 类(Class)


有那么几个元素会被经常处理. 这些元素被写到HTML中的`class`属性里, 也就是类. 可以通过合并规则集的方式来向多个空格分开的类添加属性.


这样做省下了外延定义(extensive definition). Bootstrap广泛利用了这种可能, 并用几个规则集和很多的调整选项来获取之(Bootstrap utilizes this possibility comprehensively and achieves this with a few rulesets and a large number of modification options. 德国友人的英语真好, 我他妈认识每一个单词, 然而还是没严格看懂这句话). 和ID不同, 可以定义许多元素的类, 从而类可以在一个文件中多次出现.

类选择器的语法如下:

```css
.class {

}
```


举个例子:

```html
<style> 
.btn {
    color: red;
}
</style>
<button class="btn">发送</button>
```


#### 1.3.4 属性(Attribute)


使用HTML元素的属性选择器语法, 可以指向属性:

```css
[name] {

}
```


```css
[name="value"] {

}
```

举个例子:


```html
<style> 
[data-item] {
    color: blue;
}
</style>
<a href="link.html" data-item="22">下一个</a>
```

如果属性的值(赋值号`=`右边的部分)没有指定, 那么只有存在该属性的对象会应用规则(only the
existence of the attribute is considered sufficient to apply to the rules).


#### 1.3.5 逻辑选择(Logical Selection)


这种情况通常发生在规则集被应用到多个选择器上的情形. 出于这个目的, 需要`OR`的逻辑, 这个在CSS里被标记成一个逗号`,`:

```css
a, b {

}
```

在`a`和`b`之间没有链接, 这个规则是分别独立作用于这两者的. 当然了, `a`和`b`这两个占位符在实际干出产值的时候可以换成其他更复杂的选择器(毫无疑问, 你也可以多个选择器这么用, 比如初始化CSS的时候...).


#### 1.3.6 其他的选择器


创造产值的时候, 上面列出来的那些选择器可能不够. 下面表格里给出了一个选择器的概览(当然和官网上的比也明显不够...):


翻译可能有问题, 但那基本也不是我的问题, 毕竟原文作者是德国人...


碰到翻译感觉有问题的时候, 请上官网看[简单选择器](https://developer.mozilla.org/zh-CN/docs/Web/CSS/CSS_Selectors#Simple_selectors).

<table>
<caption>表1-1. 简单的CSS选择器</caption>
<thead>
    <tr>
        <th>符号</th>
        <th>描述</th>
    </tr>
</thead>
<tbody>
    <tr>
        <td>*</td>
        <td>全局(universal)/全部(all)</td>
    </tr>
    <tr>
        <td>tag</td>
        <td>元素名</td>
    </tr>
    <tr>
        <td>.class</td>
        <td>类(类属性)</td>
    </tr>
    <tr>
        <td>#id</td>
        <td>ID(id属性)</td>
    </tr>
    <tr>
        <td>[a]</td>
        <td>存在属性(attribute presence)</td>
    </tr>
    <tr>
        <td>[a=v]</td>
        <td>值为什么什么的属性</td>
    </tr>
    <tr>
        <td>[a~=v]</td>
        <td>包含某个作为单个字的值(a value as a standalone word)的属性</td>
    </tr>
    <tr>
        <td>[a|=v]</td>
        <td>不包含什么什么值的属性</td>
    </tr>
    <tr>
        <td>[a^=v]</td>
        <td>以什么什么值开始(starts with value)的属性</td>
    </tr>
    <tr>
        <td>[a$=v]</td>
        <td>以什么什么值结束(ends with value)的属性</td>
    </tr>
    <tr>
        <td>[a*=v]</td>
        <td>包含某个值(contains a value)的属性</td>
    </tr>
</tbody>
</table>


处理层次关系也素狠重要滴...因为HTML文档就是分层的, 也被叫做(文档)树(写得真是无语, 明白意思就行). 文档树中的元素关系如下所示(这个图里有错别词, 所以不是我做的...):

![WX20190605-143630@2x.png](https://i.loli.net/2019/06/05/5cf76333e655661837.png)


当感觉翻译有问题的时候, 请上官网看[组合选择器](https://developer.mozilla.org/zh-CN/docs/Web/CSS/CSS_Selectors#Combinators).


<table>
<caption>表1-2. 层次关系CSS选择器</caption>
<thead>
    <tr>
        <th>符号</th>
        <th>描述</th>
    </tr>
</thead>
<tbody>
    <tr>
        <td>e > f</td>
        <td>如果f是e的孩子(父母-孩子关系中的那个孩子)就选中</td>
    </tr>
    <tr>
        <td>e f</td>
        <td>如果f是e的后辈(祖灵-后辈关系中的那个后辈)就选中</td>
    </tr>
    <tr>
        <td>e + f</td>
        <td>如果f是e的后继(sibling中的successor情况)就选中</td>
    </tr>
    <tr>
        <td>e ~ f</td>
        <td>当e是f的兄弟就选中</td>
    </tr>
</tbody>
</table>


和上面相比, 关系的可能性没有选择祖灵的选择器、选择前驱(predecessor)的选择器和选择父母的选择器. 为了实现这个需求只需要把两个元素交换一下顺序就可以了.


伪选择器(Pseudoselector)是那些在HTML中没有相近表示, 但可从元素位置或使用中导出的结果(result from the position of elements or use). 有三种伪类选择器:


* 静态位置(见表1-3)
* 区域选择(见表1-4)
* 动态行为(见表1-5)


感觉翻译有问题的时候请上官网看[伪元素](https://developer.mozilla.org/zh-CN/docs/Web/CSS/Pseudo-elements).

<table>
<caption>表1-3. 静态CSS选择器</caption>
<thead>
    <tr>
        <th>符号</th>
        <th>描述</th>
    </tr>
</thead>
<tbody>
    <tr>
        <td>::first-line</td>
        <td>首行</td>
    </tr>
    <tr>
        <td>::first-letter</td>
        <td>首字母</td>
    </tr>
    <tr>
        <td>::before</td>
        <td>该元素前面(Before the element)</td>
    </tr>
    <tr>
        <td>::after</td>
        <td>该元素后面(After the element)</td>
    </tr>
    <tr>
        <td>::selection</td>
        <td>高亮(被选中)区域</td>
    </tr>
</tbody>
</table>


后面两个表, 感觉翻得有问题的时候请上官网看[伪类](https://developer.mozilla.org/zh-CN/docs/Web/CSS/Pseudo-classes).


<table>
<caption>表1-4. 区域CSS选择器</caption>
<thead>
    <tr>
        <th>符号</th>
        <th>描述</th>
    </tr>
</thead>
<tbody>
    <tr>
        <td>:root</td>
        <td>基元素(Basic element)</td>
    </tr>
    <tr>
        <td>:empty</td>
        <td>仅当物件为空应用(Applies only if the item is empty)</td>
    </tr>
    <tr>
        <td>:first-child</td>
        <td>列表(list)中的第一个子元素</td>
    </tr>
    <tr>
        <td>:last-child</td>
        <td>列表中的最后一个子元素</td>
    </tr>
    <tr>
        <td>:nth-child(&nbsp;)</td>
        <td>列表中的正数特定子元素(这话很有内涵, 建议跟下一个上官网看看)</td>
    </tr>
    <tr>
        <td>:nth-last-child(&nbsp;)</td>
        <td>列表中的倒数特定子元素</td>
    </tr>
    <tr>
        <td>:only-child</td>
        <td>列表中仅有一个子元素时生效</td>
    </tr>
    <tr>
        <td>:first-of-type</td>
        <td>First child element of a type(无力吐槽, 这作者说的是人话吗, 上官网看吧)</td>
    </tr>
    <tr>
        <td>:last-of-type</td>
        <td>Last child element of a type(上官网看吧...)</td>
    </tr>
    <tr>
        <td>:nth-of-type(&nbsp;)</td>
        <td>Child element of a type in a list(上官网看吧...)</td>
    </tr>
    <tr>
        <td>:nth-last-of-type(&nbsp;)</td>
        <td>Child element of a type by the end of a list(上官网看吧...)</td>
    </tr>
    <tr>
        <td>:only-of-type</td>
        <td>Only this type from a list
  (上官网看吧...)</td>
    </tr>
</tbody>
</table>





<table>
<caption>表1-5. 动态CSS选择器</caption>
<thead>
    <tr>
        <th>符号</th>
        <th>描述</th>
    </tr>
</thead>
<tbody>
    <tr>
        <td>:link</td>
        <td>超链接</td>
    </tr>
    <tr>
        <td>:visited</td>
        <td>访问过的超链接</td>
    </tr>
    <tr>
        <td>:hover</td>
        <td>鼠标指针悬浮在其上的超链接</td>
    </tr>
    <tr>
        <td>:active</td>
        <td>活动状态(正被点击的)超链接</td>
    </tr>
    <tr>
        <td>:focus</td>
        <td>一个具有焦点(也就是闪烁光标)的物件(item)</td>
    </tr>
    <tr>
        <td>:target</td>
        <td>一个具有target属性的物件(item)</td>
    </tr>
     <tr>
        <td>:disabled</td>
        <td>一个被禁用的(被禁用属性disabled attribute)物件(item)</td>
    </tr>
    <tr>
        <td>:enabled</td>
        <td>一个非被禁用的(非被禁用属性not disabled attribute)物件(item)</td>
    </tr>
    <tr>
        <td>:checked</td>
        <td>一个被勾选的物件(item, 仅限复选框)</td>
    </tr>
    <tr>
        <td>:valid</td>
        <td>一个生效的(valid)物件(item)</td>
    </tr>
    <tr>
        <td>:invalid</td>
        <td>一个无效的(invalid)物件(item)</td>
    </tr>
    <tr>
        <td>:lang(&nbsp;)</td>
        <td>一个具有合适lang=""属性为..的物件(item)(作者说的是人话吗)</td>
    </tr>
    <tr>
        <td>:not(&nbsp;)</td>
        <td>取反如下选择(这个是个运算符)</td>
    </tr>
</tbody>
</table>



(伪类)选择器的浏览器支持情况得上官网去看.


### 1.4 盒模型


待续, 总不能一天都在看这个东西吧.


## 第二章 Bootstrap 4 基本

建议先把框架名写对, 以免简历上写了个错误的名称遭人耻笑.

Bootstrap 4 下载地址: [Bootstrap 4 系列最新版本 4.3.1: Download · Bootstrap](https://getbootstrap.com/docs/4.3/getting-started/download/). 当然了, 不是直接下, 你看看 [Contents](https://getbootstrap.com/docs/4.3/getting-started/contents/) 以及自己实际情况再随机应变决定怎么下.

或是用 CDN.

在 Bootstrap 4 中, 浏览器的水平向宽度是 12 个单位.

Bootstrap 的 class 中有个 container 属性, 可以将这个 class 加到属性里, 从而可在块元素两边加上空白.

也可以设置区域的宽度, 参考:

```html
<div class="container">
    <div class="row">
        <!-- 可以通过调整`col-md-`后面的这个数值来修改宽度. -->
        <div class="col-md-2">申帝我操你妈!</div>
        <div class="col-md-2">串相我操你妈血逼!</div>
        <div class="col-md-3">孙鸿昌你还不上钱的话和它们几个一个样.</div>
        <div class="col-md-4">刘燕你贪的东西太多了, 早点儿死吧.</div>
    </div>
</div>
```


## 第三章 Bootstrap 4 时代的响应式

可以通过这个链接 [Responsive breakpoints](https://getbootstrap.com/docs/4.3/layout/overview/#responsive-breakpoints) 看一下设备的种类.

主要是有这么五种设备 —— `xs`、`sm`、`md`、`lg`、`xl`, 对应的 CSS 写法如下:

```css
// Extra small devices (portrait phones, less than 576px)
// No media query for `xs` since this is the default in Bootstrap

// Small devices (landscape phones, 576px and up)
@media (min-width: 576px) { ... }

// Medium devices (tablets, 768px and up)
@media (min-width: 768px) { ... }

// Large devices (desktops, 992px and up)
@media (min-width: 992px) { ... }

// Extra large devices (large desktops, 1200px and up)
@media (min-width: 1200px) { ... }
```

响应式布局在以控制组件的显示和隐藏为代表等的场景下应用:

* 显示/隐藏: [Display property](https://getbootstrap.com/docs/4.3/utilities/display/)
* 流式布局: [Flex](https://getbootstrap.com/docs/4.3/utilities/flex/)
* 浮动方式: [Float](https://getbootstrap.com/docs/4.3/utilities/float/)
* ...

  
## 第四章 Bootstrap 表格

参考: [Bootstrap 表格](https://getbootstrap.com/docs/4.3/css/tables).


表格常用的有这么几种样式:

* `table(Bootstrap基本表格)`
* `table-striped(隔行高亮)`
* `table-bordered(边框线)`
* `table-hover(悬浮动态显示背景色)`
* `table-condensed(紧凑形式)`



对于高亮显示, 则有:

* `active`
* `success`
* `warning`
* `danger`
* `info`


高亮显示可以应用于行(`tr`元素)或是单元格(`td`/`th`元素)


## 第五章 Bootstrap 表单


参考: [Bootstrap 表单](https://getbootstrap.com/docs/4.3/css/forms).

`<label>` 标签的 `for` 属性以前用得很少, 照文档补一补.


Bootstrap 的表单常用属性:

* form-group
* 控件类型(email、password、file、checkbox、button)
* 控件着色(has-warning、has-error、has-success)
* 帮助提示(help-block)
* form-inline(横向表单)
* form-horizontal(纵向两列表单)
* sr-only(屏幕阅读器, 增加字段的可访问性, 比如放在页面顶部供登录的时候用)
* 纵向两列表单的宽度设置(col-设备类型-xx, col-设备类型-offset-xx)
* 表单支持的控件【HTML 5】: text、password、datetime、datetime-local、date、month、time、week、number、email、url、search、tel、color



## 第六章 Bootstrap 内置图标和按钮


图标(这个算是组件了, Glyphicons): [Glyphicons 图标-组件](https://getbootstrap.com/docs/4.3/components/#glyphicons).

按钮样式(这个倒还是 CSS): [Bootstrap 按钮 - CSS](https://getbootstrap.com/docs/4.3/css/#buttons).

按钮组(这个也是组件): [Bootstrap 按钮组 - 组件](https://getbootstrap.com/docs/4.3/components/#btn-groups).

Glyphicon 图标: 相当于对 `<span>` 标签进行修饰. 注意每一个 Glyphicon 需要单独放置. `<span>` 的属性用什么查什么.

常见按钮样式: btn-default、btn-primary、btn-success、btn-info、btn-warning、btn-danger、btn-link


按钮组: 比如下拉菜单这种出来一堆链接的按钮.

**注意**: CDN 引用方式导入的 jQuery 库应该先于导入 bootstrap(.min).js 之前, 否则下拉按钮之类的样式不会生效.



## 第七章 Bootstrap 分页相关

这几个都是组件里的.

常用组件:

* breadcrumb (面包屑导航, 比如像“首页 - 关于畐国 - 企业自勉”这种的)[Bootstrap 组件-面包屑](https://getbootstrap.com/docs/4.3/components/#breadcrumbs)
* pagination (这个就是分页了, 比如 TP5.1 手册中杂项里的)[Bootstrap组件-分页](https://getbootstrap.com/docs/4.3/components/#pagination)
  * pager (快速导航, 无页号, 就是简单的那种前后翻, 少量页的时候还不错)[Bootstrap组件-pager](https://getbootstrap.com/docs/4.3/components/#pagination-pager)
* label (这个好像不算那种分页...也是可以设那种 warning、success 之类的风格的.)[Bootstrap组件-label](https://getbootstrap.com/docs/4.3/components/#labels) 



## 第八章 Bootstrap 导航条

https://getbootstrap.com/docs/4.3/components/navs/
导航: [Bootstrap 组件-导航](https://getbootstrap.com/docs/4.3/components/navs/)

导航条: [Bootstrap 组件-导航条](https://getbootstrap.com/docs/4.3/components/navbar/)


导航条的常用属性:

* navbar
* navbar-header
* navbar-brand
* navbar-form
* navbar-right



## 第九章 Bootstrap的其他基本组件

* input groups (文本输入旁边的辅助显示标签)
* badge (也是 `<span>` 标签使用 `badge` 属性, `<span>` 标签对里单独放 badge 的内容)
* alert(alert-success、alert-info、alert-warning、alert-danger等)
* panel(分 panel 头、panel 体、panel 脚)[Bootstrap 组件 - panel](https://getbootstrap.com/docs/4.3/components/#panels)


## 第十章 Bootstrap 的进度条

[Bootstrap 组件 - 进度条](https://getbootstrap.com/docs/4.3/components/#progress)

进度条的常用属性:

* progress
* progress-bar (样式、百分比、颜色、条纹等)
* progress-bar-striped (进度条纹理: 纹理斜线+深浅交错)
* progress-bar-success、progress-bar-warning、progress-bar-danger 等总共六个


用的时候注意给 `<div>` 设置 `role` 属性.

也可以就是在同一个进度条中拿多个子进度条拼起来.

## 第十一章 Bootstrap 的模态窗体

关于模态视图, 听过三四年了, 但是一直不很了解.

这里放两个解释参考:

[zhihu: 模态对话框(modal dialogue box)中模态一词的意思是什么？](https://www.zhihu.com/question/21883669)

[zhihu: 弹窗、模态、提示、浮层，这几位是什么关系？](https://www.zhihu.com/question/41953649)

感觉模态就是成为第一响应者的那个东西, 同时模态内容要求必须处理, 比如 Clash Royale 里你打出一个箱子以后, 你直接在CR的界面里就按手机右侧的键把手机黑屏了, 再进 (唤醒屏幕 + Home) 的时候手机还会回到你那个 CR 的界面, 但是会弹出来一个 alert 提示你掉线了让你重新连进去, 这个应该就是模态视图.

感觉这个移动端用得还可以, 网页端用得好像真不多...

文档见[Bootstrap 的 JavaScript - 模态](https://getbootstrap.com/docs/4.3/javascript/#modals)

模态视图常用属性:

* modal
* modal-dialog
* modal-content
  * modal-header
  * modal-body
  * modal-footer 
* 窗体布局
  * 一般布局(流布局)
  * 网格布局
  
  
  
## 第十二章 Bootstrap 的 tab 标签页


感觉还是移动端用的多...电脑端基本没看过几次有这么干的.

一般似乎是 tab 和 nav 配合使用, 然后 `<ul>` 标签的 `role` 属性为 tablist, 而 **`<li>` 标签内部**的 `<a>` 之类的标签的 `role` 属性值为 tab, 内部的 `<a>` 之类的标签的 `data-toggle` 属性也很重要, 写 tab.


3.几版本的 Bootstrap 官方明确说了不支持 Tab 的嵌套.


[Bootstrap-JavaScript的tab](https://getbootstrap.com/docs/4.3/javascript/#tabs)  


常用属性:

* nav-tabs
* tab-content
* tab-pane(当标签页切换时, 切换显示的内容)
* fade in
* tabs event(jQuery使用) [Bootstrap的Tab Events](https://getbootstrap.com/docs/4.3/javascript/#tabs-events)


如果写了`fade`的话, 一定要在一个`fade`的后面追加`in active`, 即`fade in active`, 否则不会显示tab初始内容.

tab-content块中的tab-panel块的`id`要和相应`<a>`锚链接的`href`属性值相对应.


## 第十三章 Bootstrap的工具条和弹出框


* tooltip([Bootstrap的JavaScript-工具条](https://getbootstrap.com/docs/4.3/javascript/#tooltips))
* popover([Bootstrap的JavaScript-弹出框](https://getbootstrap.com/docs/4.3/javascript/#popovers))


工具条(或者更像是提示条)在鼠标放上去的时候显示, 拿走的时候就消失了.

弹出框在点一次按钮的时候可以保持存在, 再点一次相同按钮的时候才会消失.


## 第十四章 Bootstrap 的轮播


查了一下, 虽然汉语理解的是叫轮播, 不过 carousel 在英语里的实际意思是旋转木🐴, 也就是旋木.


适合新闻图片之类的展示. 这个用得确实是比较多的.


[Bootstrap的JavaScript-Carousel](https://getbootstrap.com/docs/4.3/javascript/#carousel)


常用属性:

* carousel slide(用于设置轮播的行为)
* carousel-indicators(就是轮播下面的那个点, 作为指示当前轮播的位置的token)
* carousel-inner(设置轮播滚动的内容, 页面中所有的滚动内容都要在这里设置)
* carousel-control(就是轮播左右边侧各自的那个左箭头右箭头, 实际上是锚`<a>`的class属性的值)
  * left
  * right 


这个差不多就是以前在前我司门户网站上用的LayerSlider了...不过好像没法像LayerSlider那样做子附件的滑入滑出效果.

  
  
## 第十五章 Bootstrap的折叠

[Bootstrap的JavaScript-Collapse](https://getbootstrap.com/docs/4.3/javascript/#collapse)  


* collapse(折叠)
* accordion(风琴, 就是那种 `UITableView` 的那种折叠展开的那种下拉菜单显示隐藏效果)[风琴例子](https://getbootstrap.com/docs/4.3/javascript/#collapse-example-accordion)


心里不要有恐惧, 有的时候代码显得多的那部分只是框架的代码, 不是纯粹的内部内容.