---
layout: post
title: "Emmet 学习"
description: "学习一下 Emmet."
date: 2019-09-26
tags: [提高姿势水平,工具]
comments: true
share: true
---

> 学习一下 Emmet.

今天让我们来学习一下 Emmet.

## 写在前面

这个文章最开始是在 7 月 16 号写的, 当时的期望是能把这整套都给翻译完. 现在都已经用了两个月了, 不过这篇 Emmet 教程翻译的进度倒是一直都半死不活😂

最近发现了这个站点, 分享一下:

[Emmet-HTML/CSS代码自动补全语法](https://code.z01.com/Emmet/)

这样我就直接放这个站点了. 省事儿.

作者还不网站阿婆主的还弄了个 Bootstrap 的中文站点: [Bootstrap4中文站 &middot; 全球最流行的 HTML、CSS 和 JS 工具库。](https://code.z01.com/v4/). 也是创造了不少产值.

## 认识你自己

首先认识一下你的设备. 在苹果官网上, 有如下描述(根据实际情况加以改动):

> Mac 菜单和键盘通常对某些按键使用符号，其中包括以下修饰键：
> 
> * command（或 cmd）⌘
> * shift ⇧
> * option（或 alt）⌥
> * control（或 ctrl）⌃
> * caps lock ⇪
> * fn
>
> *在 Windows PC 专用键盘上，请用 alt 键代替 option 键，用 windows 徽标键代替 command 键。*


写这些主要是我记不住快捷键, 重新记一下.

最近家里事儿有些多, 要崩溃了. 不过年轻人多坚持坚持.



## 文档首页 Demo

在这个 Demo 中, 主要是为我们讲述了以下基本用法:


* Run “Expand Abbreviation” action to expand it into HTML: “**Expand Abbreviation**” (Tab key)【也就是键盘的tab键】  
* Traverse between important code points with “Next/Previous Edit Point” action: “**Next Edit Point**” (⌃⌥→) 【也就是键盘的control键 + option键 + →键】
* Traverse between important code points with “Next/Previous Edit Point” action: “**Previous Edit Point**” (⌃⌥←)【也就是键盘的control键 + option键 + ←键】
* Select tags with “Balance” action: “**Balance**” (⌘D)【也就是键盘的command键 + D键】
*  Select important parts with “Select Next/Previous Item” action: “**Select Next Item**” (⇧⌘.) 【也就是键盘的shift键 + command键 + .键】
*  Select important parts with “Select Next/Previous Item” action: “**Select Previous Item**” (⇧⌘,)【也就是键盘的shift键 + command键 + ,键】
* Quickly comment full tag with “Toggle Comment” action: “**Toggle Comment**” (⌘/)【也就是键盘的command键 + /键】


详解:

* 用tab键可将`ul#nav>li.item$*4>a{Item $}`这类有意义的缩写代码解释为完整的脚本:

```html
    <ul id="nav">
    	<li class="item1"><a href="">Item 1</a></li>
    	<li class="item2"><a href="">Item 2</a></li>
    	<li class="item3"><a href="">Item 3</a></li>
    	<li class="item4"><a href="">Item 4</a></li>
    </ul>
```


* 光标在某个位置, 按键盘的control键 + option键 + →键/键盘的control键 + option键 + ←键可以将光标向右/向左移动到可以编辑**一个`<>`紧挨另一个`<>`中间部分的标签内容/空属性值**这类可编辑的位置(注意: 无法用此操作移动到已经有值的属性, 也无法用此操作移动到某标签来新加属性).

举例来说, 我们的光标在`<li class=""><a href="">Item 1</a></li>`中`c`和`l`的中间, 那我们control键 + option键 + →键可以将光标移动到`<li class="">`中两个双引号的中间, 再control键 + option键 + →键可以将光标移动到`<li class="">`和`<a href="">`的中间. 

同理, 倘若光标在`</a>`中`/`和`a`的中间的话, 按control键 + option键 + ←键会移动到`<a href="">`中两个双引号的中间, 并不是移动到Item 1那块儿的什么位置.


* 将光标移到标签内部, 用command键 + /键可将该标签注释掉.


举例来说, 如果光标在`<a href="">Item 2</a>`中的`/`和`a`之间, 就可以用command键 + /键注释为: `<!-- <a href="">Item 2</a> -->`; 又比如说, 光标放在`<li class="item2"><a href="">Item 2</a></li>`中小写`i`和小写`t`之间, 可以用command键 + /键注释为: `<!-- <li class="item2"><a href="">Item 2</a></li> -->`. 这就避免了找到头找到尾一个个注释耽误干出产值的恶劣影响.


举例:

```html
<html lang="en" dir="ltr">
    <head>
        <!-- blahblahblah... -->
    </head>
    <body>
        table>(tr>(td*2))*3
    </body>
</html>
```

我们如果在数字`3`的紧后面`tab`一下, 内容就会变成:

```html
<!DOCTYPE html>
<html lang="en" dir="ltr">
    <head>
        <!-- blahblahblah... -->
    </head>
    <body>
        <table>
            <tr>
                <td></td>
                <td></td>
            </tr>
            <tr>
                <td></td>
                <td></td>
            </tr>
            <tr>
                <td></td>
                <td></td>
            </tr>
        </table>
    </body>
</html>
```

括号多点儿无所谓, 本来就是保证语义明确, 出于这点随便加.

注意像 `<a>`、`<img>` 这种的, 扩展以后可以自带主要的 attribute.

比如:

* `a*3` + tab → `<a href=""></a><a href=""></a><a href=""></a>`(我把换行删了)
* `img*2` + tab → `<img src="" alt=""><img src="" alt="">`


## 缩写

### 缩写语法

Emmet 用的是一个类似 CSS 选择器的语法来描述生成树内部元素的位置, 以及元素的 attribute.


#### 元素

可以根据元素的名称来生成 HTML 标签, 当然了, 如果不是标准 HTML 标签的话, 它会转换成 `<标签名></标签名>` 的形式.

比如:

* `php` + tab → `<php></php>`
* `literal` + tab → `<literal></literal>`


#### 嵌套运算符

##### 子元素: >

举例: 

`div>ul>li` + tab →

```html
<div>
    <ul>
        <li></li>
    </ul>
</div>
```

##### 兄弟元素: +

举例:

`div+p+bq` + tab →

```html
<div></div>
<p></p>
<blockquote></blockquote>
```

注意: 混日子的元素不配成为 `+` 号连接的运算数(也就是 operand 啦...).

##### clime up: ^

`^` 可以让 `^` 后面的元素往上一个层级(是文档树的角度的那个层级, 不是兄弟元素谁第一谁第二的那个层级)

比如: `div>p>span>strong^em` + tab →

```html
<div>
    <p>
        <span>
            <strong></strong>
        </span>
        <em></em>
    </p>
</div>
```


`em` 可以连续使用多次, 每一次使用都会将后面的元素提高一个层级:

`div>p>span>strong^^em` + tab →

```html
<div>
    <p>
        <span>
            <strong></strong>
        </span>
    </p>
    <em></em>
</div>
```

又比如:

`div>p>span>strong^^^em` + tab →

```html
<div>
    <p>
        <span>
            <strong></strong>
        </span>
    </p>
</div>
<em></em>
```

##### 乘法: *

举例:

`ul>li*4` + tab:

```html
<ul>
    <li></li>
    <li></li>
    <li></li>
    <li></li>
</ul>
```

##### 分组: ()

个人认为这个主要是增加可读性的, 比如上面的 `ul>li*5` 我感觉就应该在 `li*5` 的两边加一对括弧.

示例:

`div>(header>ul>li*2>a)+footer>p` + tab → 


```html
<div>
    <header>
        <ul>
            <li><a href=""></a></li>
            <li><a href=""></a></li>
        </ul>
    </header>
    <footer>
        <p></p>
    </footer>
</div>
```

嵌套分组:


`(div>dl>(dt+dd)*3)+footer>p` + tab →

```html
<div>
    <dl>
        <dt></dt>
        <dd></dd>
        <dt></dt>
        <dd></dd>
        <dt></dt>
        <dd></dd>
    </dl>
</div>
<footer>
    <p></p>
</footer>
```


#### 属性 (attribute) 运算符


为了避免和 property 发生混淆, 我就不翻译属性这个词了, 直接拿 attribute 上去干.


##### id 与 class

在 CSS 中, 我们都是使用 `elem#id` 以及 `elem.class` 记法来获取具有指定 `id` 和 `class` 的 attribute. 

举例:

`div.wrapper>((div.nav>((img#nav-logo)+(ul>(li*2))))+(div.sidenav.menu1)+(div.sidenav.menu2)+(div.sidenav.menu3)+(div.sidenav.menu4))` + tab →

```html
<div class="wrapper">
    <div class="nav">
        <img src="" alt="" id="nav-logo">
        <ul>
            <li></li>
            <li></li>
        </ul>
    </div>
    <div class="sidenav menu1"></div>
    <div class="sidenav menu2"></div>
    <div class="sidenav menu3"></div>
    <div class="sidenav menu4"></div>
</div>
```

当然了, `img` 那个 `alt` 和 `src` 这俩 attribute 是 Emmet 内置的, 就让它带着吧. 而且一般你都得用 `alt` 和 `src`, 最起码 `src` 你得用吧.


##### 自定义 attribute

这个要用到 `[attr]` 的记法. 

举例:

`p[style]` + tab → 

```html
<p style=""></p>
```

别的就不举了. 如果不是引用 CSS 文件或是在页面头部扔个 `<style>` 块的话, 你一般都还是 `tag[style="attr1:value1;attr2:value2;..."]` 这么弄吧, 直接 `tag[attr=value;]` 这种太 low 了.

也可以传值进去:

`td[title="Hello world!" colspan=3]` + tab → 

```html
<td title="Hello world!" colspan="3"></td>
```

##### 对象编号: $

我把原来文档的 item 给翻成“对象”了. 这个 item 实在是不好翻, 自己意会吧.

`$`起一个给迭代元素编号的作用.

示例:

`ul>li.item$*11` + tab →

```html
<ul>
    <li class="item1"></li>
    <li class="item2"></li>
    <li class="item3"></li>
    <li class="item4"></li>
    <li class="item5"></li>
    <li class="item6"></li>
    <li class="item7"></li>
    <li class="item8"></li>
    <li class="item9"></li>
    <li class="item10"></li>
    <li class="item11"></li>
</ul>
```

你也可以连着用多个 `$` 来实现用 0 占位的效果:

`ul>li.item$$$*11` + tab →

```html
<ul>
    <li class="item001"></li>
    <li class="item002"></li>
    <li class="item003"></li>
    <li class="item004"></li>
    <li class="item005"></li>
    <li class="item006"></li>
    <li class="item007"></li>
    <li class="item008"></li>
    <li class="item009"></li>
    <li class="item010"></li>
    <li class="item011"></li>
</ul>
```


##### 调整计数的起始基准和计数的方向.

原文文档里的 base 我给翻成基准了, 不是我们通常所说的进制. 所谓基准就是你是从 1 开始数啊, 还是从 2 开始数啊, 还是从 3 开始数这样的; 而方向就是你是从小到大数呢, 还是从大到小往回数呢这样的.


比如说你只想改方向的话, 那就是在最后一个 `$` 后面加上 `@-` :

`ul>li.item$$@-*12` + tab →

```html
<ul>
    <li class="item12"></li>
    <li class="item11"></li>
    <li class="item10"></li>
    <li class="item09"></li>
    <li class="item08"></li>
    <li class="item07"></li>
    <li class="item06"></li>
    <li class="item05"></li>
    <li class="item04"></li>
    <li class="item03"></li>
    <li class="item02"></li>
    <li class="item01"></li>
</ul>
```

如果你是想改基准呢, 那么你就是在第一个 `$` 前面加上 `@基准数值` :

`ul>li.item$$@8*6` + tab →

```html
<ul>
    <li class="item08"></li>
    <li class="item09"></li>
    <li class="item10"></li>
    <li class="item11"></li>
    <li class="item12"></li>
    <li class="item13"></li>
</ul>
```

上面也就是说, 以 8 为基准, 从 8 开始连着数 6 个, 也就是 8、9、10、J、Q、K.


当然了, 基数基准和计数方向也可以结合起来:

`ul>li.item$$$@-6*6` + tab →

```html
<ul>
    <li class="item011"></li>
    <li class="item010"></li>
    <li class="item009"></li>
    <li class="item008"></li>
    <li class="item007"></li>
    <li class="item006"></li>
</ul>
```

此时要注意的是, 如果是从大到小数的话, 你这个基准是你最终要达到的值.


#### 文本: {}

使用花括号向 HTML 元素添加文本: 

`a[href="www.chuan-dog-cloud-zhisang-commitee.com"]{串犬云治丧委员会}` + tab →

```html
a[href="www.chuan-dog-cloud-zhisang-commitee.com"]{串犬云治丧委员会}
```


也可以往 HTML 文本里编号计数:

`(p{申畜我艹你妈$遍})*5` + tab →


```html
<p>申畜我艹你妈1遍</p>
<p>申畜我艹你妈2遍</p>
<p>申畜我艹你妈3遍</p>
<p>申畜我艹你妈4遍</p>
<p>申畜我艹你妈5遍</p>
```

官网这块儿的子元素示例就不写了, 完全可以用 `()` 来避免语义上的歧义. 主要是认识到你的每一组 `element{content}` 都是一个整体, 就可以了.

### 缩写格式注意事项

注意**不要**在元素和运算符之间加上空格, 也就是说**不要**像下面这样:

```
(header > ul.nav > li*5) + footer
```

这样 tab 是 tab 不出来你想要的东西的, 因为空格是停止的符号, Emmet 会在空格的位置停止解析.

再摘录一下原文:

> * Abbreviations are not a template language, they don’t have to be “readable”, they have to be “quickly expandable and removable”.
> * You don’t really need to write complex abbreviations. Stop thinking that “typing” is the slowest process in web-development. You’ll quickly find out that constructing a single complex abbreviation is much slower and error-prone than constructing and typing a few short ones.


问题我他妈也没想让它完全可读啊, 关键是得保证它对, 你加括号分组啥的不就是为了让它一定能对么...