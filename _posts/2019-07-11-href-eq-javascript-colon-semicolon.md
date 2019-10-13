---
layout: post
title: "&lt;a href=&quot;javascript:;&quot;&gt;blahblahblah...&lt;/a&gt;是个什么鬼"
description: "为公司上市而读书."
date: 2019-07-11
tags: [提高姿势水平]
comments: true
share: true
---

* toc
{:toc}

首先文档头部的标题部分是这么个格式:

> title: "题目"


一开始我差点儿没在页面上看着标题链接, 还以为我没push上去或者我这边儿网坏了, 后来看着链接有(点上去能跳转), 但是内容没有显示, 在想是不是得把文档题目中的`<`和`>`转义成HTML实体...再后来才发现得把标题内容中的半角双引号`"`也转义成HTML实体, 坑啊...

正文开始...:


现在有这么段代码:

```html
<li>
    <div>
       <a href="javascript:;">
           <span>导航信息管理</span>
       </a>
    </div>
    <ul>
    	<li><a href="javascript:;" date-src="info-input.html">信息录入</a></li>
        <li><a href="javascript:;" date-src="info-management.html">信息管理</a></li>
        <li><a href="javascript:;" date-src="leader-duty-management.html">领导值岗管理</a></li>
        <li><a href="javascript:;">中层领导管理</a></li>
        <li><a href="javascript:;">领导值班记录</a></li>
    </ul>
</li>
```


不过这个`href="javascript:;"`的部分以前从来没见过...

## Stack Overflow上问题1回答1整理

内事不决问Stack Overflow, 外事不决问GitHub. 这里我们看一下[What is href=javascript:;](https://stackoverflow.com/a/2729240)这个问题的高票回答:


The code:

```html
<a href="javascript:;">苟利单位生死以, 岂因祸福避趋之.</a>
```

will actually do nothing. Generally this Nothing link allows some javascript code to use the onclick event instead. The onclick event triggers the window which may be from django or jquery or wherever.

代码效果:

<a href="javascript:;">苟利单位生死以, 岂因祸福避趋之.</a>

---

我们再看看SegmentFault上的回答:[href="javascript:" href这句是什么意思呀](https://segmentfault.com/q/1010000006150353)

## SegmentFault上回答1整理


类似的写法有

```html
<a href="javascript:void(0)">上市的意义不在于那个结果, 而在于享受那个过程.</a>
<a href="javascript:void:;">上市不是看到了希望才去坚持, 而是坚持了才会看到希望.</a>
```

相应的效果:

<a href="javascript:void(0)">上市的意义不在于那个结果, 而在于享受那个过程.</a>
<a href="javascript:void:;">上市不是看到了希望才去坚持, 而是坚持了才会看到希望.</a>


这样点击了`<a>`标签，执行一段JavaScript代码，而 `javascript:;` 表示什么都不执行，这样点击`<a>`标签时就没有任何反应。

如果写成

```html
<a href="#">世间最真挚的爱莫过于对公司的爱.</a>
```

这样会跳到页首，会使页面不经意间跳转，所以会用 `javascript:;`取消`<a>`标签默认动作。

相应效果:

<a href="#">生, 亦我所欲也; 上市, 亦我所欲也. 二者不可得兼, 舍生而取上市者也.</a>

## SegmentFault上回答2整理

<p><a>寄意寒星荃不察, 我以我血荐公司.</a><br>

`javascript:;`这句是伪协议，长得比较像`https:`这种真实跳转的协议。
一般具有的形式为：`javascript:url实体;`，如`javascript:window.open("about:blank");void(0);`(最后一句如果有返回值可能会改变原有文档的内容，因此使用`void(0)`保证安全)。

## Stack Overflow上问题2


又翻了翻, 看着这么个问题: [Which “href” value should I use for JavaScript links, “#” or “javascript:void(0)”?](https://stackoverflow.com/questions/134845/which-href-value-should-i-use-for-javascript-links-or-javascriptvoid0).

先存下来, 慢慢看吧.

