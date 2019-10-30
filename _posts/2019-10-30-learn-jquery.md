---
layout: post
title: "新《我们的公司》三部曲之二: jQuery 学习"
description: "为公司上市而学习 jQuery."
date: 2019-10-30
tags: [提高姿势水平,我们的公司]
comments: true
share: true
---

> 为公司上市而学习 jQuery.

> ...As capitalist, shEnD is only capital personified. His soul is the soul of capital. But capital has one single life impulse, the tendency to create value and surplus-value, to make its constant factor, the means of production, absorb the greatest possible amount of surplus labour.
> 
> Scdiler is dead labour, that, vampire-like, only lives by sucking living labour, and lives the more, the more labour it sucks. ...

![fuck-Scdiler](https://img.shields.io/badge/fuck-Scdiler-FD9827)

![sponsors-FUCengers](https://img.shields.io/badge/sponsors-FUCengers-brightgreen.svg)


如果这个算文章的话, 那可能有点儿长...总之谨以此文献祭给资本的化身——申帝. 


---


* TOC
{:toc}


友情提示: 本文可能有部分内容会引起不适, 请谨慎阅读.


> “那么人呐就都不知道，自己就不可以预料。你一个人的命运啊，当然要靠自我奋斗，但是也要考虑到历史的行程。”


勉勉强强能看懂 jQuery, 这番稍微仔细看看. 看的 [jQuery 开发教程](https://edu.aliyun.com/course/25), B 站上也有[尚学堂_李思莹_ jQuery 视频教程](https://www.bilibili.com/video/av44907596), 主要是里面叫李思莹的这只小姐姐的声音比较好听...另外这个 PPT 的大小写还可以, 至少不会把 jQuery 写成 Jquery 等奇怪的东西; 不过这只小姐姐还是会把 Ajax 念成啊假克思, 勉强能接受吧, 我现在认识的人中, 真的确实只有贝老经理能把 Ajax 的发音读对...当然, 他代码的风格也确实是非常好. 虽说上点儿岁数不愿学新东西了, 但是底子真的是没得挑剔. 也是第一个工作环境中见到的英语水平能比肩我的人. 应当多向这种人学习.

视频中 PPT 的翻译我都过了一遍, 和官网文档有出入的我就自己翻译了一下...

说到官网, jQuery 官网在[这里](https://jquery.com), 官方 API 在[这里](https://api.jquery.com), 官方教程在[这里](https://learn.jquery.com). 上[这里](https://jquery.com/download/)下载最新版jQuery. 去[这儿](https://code.jquery.com)找 jQuery Core、jQuery UI、jQuery Mobile 等的各个主版本的稳定发行版. 当然我们平时用[jQuery Core](https://code.jquery.com/jquery/)比较多. JavaScript 官方教程在[这里](https://developer.mozilla.org/en-US/docs/Learn/Getting_started_with_the_web/JavaScript_basics)...只是说一下我有找到资料和能看懂的能力, 以免我被认为是智障...


## jQuery 基础

这个不是视频本身的内容, 只是我个人的一点建议. 我觉着建议在看 jQuery 之前稍微复习一下 CSS 选择器:

[CSS selectors](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Selectors).

后面还有 Next steps 环节, 也可以顺下去看看.

### jQuery 简介

#### jQuery 是啥

jQuery is a fast, small, and feature-rich JavaScript library. It makes things like HTML document traversal and manipulation, event handling, animation, and Ajax much simpler with an easy-to-use API that works across a multitude of browsers. With a combination of versatility and extensibility, jQuery has changed the way that millions of people write JavaScript.

所以, 像有的公司就可以出个考察基本概念的题: jQuery是框架还是库? 答错了面试官就认为你基本功堪忧.

#### jQuery的兼容性

兼容CSS3, 以及各种浏览器.

#### jQuery的版本

jQuery 1.0.0 发布于 2006-10-27.<br/>
jQuery 2.0.0 发布于 2013-04-18.<br/>
jQuery 3.0.0 发布于 2016-06-09.

真是时光荏苒啊.

1.x: 兼容低端浏览器.<br/>
2.x: 兼容从 IE9 开始的以及其他的高端浏览器.<br/>
3.x: 视频就没讲 3.x, 官网也没查到有什么特色, 以后再说.

据说 jQuery *基本*是向下兼容的, 一般推荐使用新版的 jQuery. 

#### jQuery的优点

jQuery 使用户能更方便处理 HTML、events, 实现动画效果, 并能方便地为网站提供 *Ajax* (*Asynchronous JavaScript and XML*) 交互.

jQuery 的文档说明很全, 应用说得很详细, 同时还有许多成熟插件可供选择.

开源免费, 可以将节省下来的钱用于促进公司上市.

#### jQuery的核心理念

网页上 `<meta>` 的 `description` 的 content: "jQuery: The Write Less, Do More, JavaScript Library" 中的 write less, do more.

### jQuery引入

这个没什么好说的吧...

视频用的 jQuery 2.2.1, 但是官网上就连 2.2.4 都没源码了, 所以我们用 jQuery 3.4.1 的未压缩版. 链接上面有, 没有 3.4.1 的话找个更新的也行...

压缩的也可以用, 不过可读性不如原版好. 所以创造产值的时候再用压缩的.

下完之后注意把 standard 什么的插件给关了, 要不然卡编辑器.

我们在一条龙软件里建个目录作为工程目录, 把 jquery-3.4.1.js 拷到那里. 我这里由于是 macOS 玩家所以用的是 MAMP Pro. 像 Windows 玩家可以用 phpStudy. 像 Linux 玩家可以 `yum install httpd`, 然后 `service httpd start` 和 `chkconfig httpd on` 然后在 `/var/www/html` 下面 `vi` 玩. 大道三千, 上市的路不止一条, 能干出产值的员工才是好员工.


这里再看下 Win 下的一条龙软件, 因为我平时都用 macOS. 到 2019-09-03 它们都还是可用的:

* [phpStudy - 让天下没有难配的服务器环境！](https://www.xp.cn)
* [XAMPP Installers and Downloads for Apache Friends](https://www.apachefriends.org/index.html)
* [WampServer, la plate-forme de développement Web sous Windows - Apache, MySQL, PHP](http://www.wampserver.com/en/#)

还要注意, 在文档中引用 jQuery 库本体的时候, 一定要发生在引入使用 jQuery 库的文件/代码之前.

### jQuery基本语法

`$(selector).action()`

解释:<br/>
1. 美刀符号 `$` 是 `jQuery` 的别名, 这个官网上我记得明确写了.
2. 选择符 `(selector)` 用于查询查找HTML元素.
3. jQuery的 `action()` 执行对元素的操作.


当然了, 这个是比较基本的, 鉴于我们在生活中并不总是十全十美一帆风顺, “一年三百六十五天, 黑夜占据了一半, 阴雨天占据了一些, 晴天终究是少数, 包括我的内心也有阴暗的部分. 光明无法击败所有的黑暗, 就像阳光无法照亮每一个角落, 善良无法冲去所有的恶意, 真诚也无法解释所有的误解. 旅途里不要被坏天气牵绊了, 前行吧朋友, 你总会遇上心上人.”所以 jQuery 有时候也会有一些非常规操作. 这些等我们碰到了再说. 

顺便说一嘴, 上面那个引号里段子原来是 HH 写的, 我以为是 LHP 写的, 那看来这个好像是 HH 在光明与磊落里写的...我知道以前李大梅是两个人都喜欢, 而富逼和老流氓是坚定的 HH 黑, 不知道他们对 LHP 的态度怎样...当然这种人畜无害的段子随便用就行了...

下面来一个简单的例子:

项目根目录/index.html:

```html
<!DOCTYPE html>
<!-- 项目根目录/01-index.html -->
<html lang="en" dir="ltr">
    <head>
        <meta charset="utf-8">
        <script type="text/javascript" src="jquery-3.4.1.js"></script>
        <script src="demo.js"></script>
        <style media="screen">
            p {
                background-color: lightgreen;
            }
        </style>
        <title>申帝我操你妈.</title>
    </head>
    <body>
        <p>申帝我QNMLGB!</p>
        <p>串相我草拟吗!</p>
        <p>申帝我透你妈!</p>
        <p>串相我去年买了个表!</p>
    </body>
</html>
```

项目根目录/demo.js:

```js
// 项目根目录/demo.js
$(document).ready(function () {
  alert('文档加载完毕')
  $("p").click(function () {
    $(this).hide()
  })
})

```

## jQuery 的选择器

### 基础选择器

#### 1. [All Selector ("*")](https://api.jquery.com/all-selector/)

描述: 选择所有元素

语法: `$("*")`

注意: 由于 `*` 选择器获取的是全部元素, 因此, 在有些浏览器中会比较缓慢, 这个选择器慎用.

[jQuery( callback )](https://api.jquery.com/jQuery/#jQuery-callback)说明:

`jQuery( callback )` <strong>behaves just like</strong> `$( document ).ready()`, in that it should be used to wrap other `$()` operations on your page that depend on the DOM being ready. While this function is, technically, chainable, there really isn't much use for chaining against it.

#### 2. [Class Selector (".class")](https://api.jquery.com/class-selector/)


描述: 选择给定样式类名的所有元素.

语法: `$(".class")`

注:

此处开始我们约定:

> class 名用连字符(solution-title)连接各个构成单词;
> 
> id 命名: 驼峰式命名法(CamelCase).


当然, 由于我看的时间比较长, 时间长了我可能会忘了自己在前面说过什么😂但是我从来不会忘记初心.

#### 3. [Element Selector ("element")](https://api.jquery.com/element-selector/)

描述: 根据给定HTML标记名称选择所有的元素.

语法: `$("element")`


#### 4. [ID Selector ("#id")](https://api.jquery.com/id-selector/)

描述: 选择一个具有给定 `id` 属性的单个元素.

语法: `$("#id")`

#### 5. [Multiple Selector ("selector1, selector2, selectorN")](https://api.jquery.com/multiple-selector/)

描述: 将每一个选择器匹配到的元素合并后一起返回.

语法: `$("selector1, selector2, ..., selectorN")`


代码如下:

```html
<!DOCTYPE html>
<html lang="en" dir="ltr">
    <head>
        <meta charset="utf-8">
        <script src="jquery-3.4.1.js" charset="utf-8"></script>
        <title></title>
    </head>
    <body>
        <!-- emmet: div>(span+p+label) -->
        <div>
            <span class="span-class"></span>
            <p></p>
            <label></label>
            <p></p>
            <a id="anchorId"></a><br/>
            <b>四年的时间, 从来没有连续睡眠两个小时以上的!</b><br/>
            <i>那个时候兄弟们也很拼.</i><br/>
            <em>但是以我的体质, 做到8116+8完全没有问题!</em><br/>
            <strong>我很幸运，我没有后悔12x12，我从没有改变过自己这一点.</strong>
        </div>
        <script type="text/javascript">
            // https://api.jquery.com/jQuery/#jQuery-callback
            // jQuery( callback ) behaves just like $( document ).ready()
            $(function(){
                $("div *").html("混日子的人不是我的兄弟.")
                $(".span-class").html("能做996是一种巨大的福气.")
                $("label").html("几年后回看，这次绝对是好事.")
                $("#anchorId").html("工作上我们强调996的精神, 生活上我们要669.")
                $("b, i").html("那个时候兄弟们也很拼.")
            })
        </script>
    </body>
</html>
```

效果(in Google Chrome 75.0.3770.100(正式版本)(64 位)):

![基础选择器](https://i.loli.net/2019/07/12/5d282ecbe5e9b55544.png)


### 属性选择器

#### 1. [Attribute Contains Prefix Selector [name|=”value”]](https://api.jquery.com/attribute-contains-prefix-selector/)

描述: 选择指定属性值等于给定字符串, 或以该字符串为前缀(**该字符串后跟一个连字符**`"-"`)的元素

语法: `$("[attribute|='value']")`

注意: 引号是可选的, 比如可以是一个不带引号的单词, 或是带一个引号的字符串.

#### 2. [Attribute Contains Selector [name*="value"]](https://api.jquery.com/attribute-contains-selector/)

描述: 选择指定属性具有包含一个给定的子字符串的元素. (选择给定的属性包含某些值的元素.)

语法: `$( "[attribute*='value']" )`


#### 3. [Attribute Contains Word Selector [name~=”value”]](https://api.jquery.com/attribute-contains-word-selector/)

描述: 选择指定属性用空格分隔的值中包含一个给定值的元素.

语法: `$( "[attribute~='value']" )`


#### 4. [Attribute Equals Selector [name=value"]](https://api.jquery.com/attribute-equals-selector/)

PS: 这块儿视频里的小姐姐的PPT弄错了, 子标题弄成了Attribute Ends With Selector [name$="value"].

描述: 选择指定属性是给定值的元素.

语法: `$( "[attribute='value']" )`



#### 5. [Attribute Not Equal Selector [name!="value"]](https://api.jquery.com/attribute-not-equal-selector/)

描述: 选择不存在指定属性, 或者指定的属性值不等于给定值的元素.

语法: `$( "[attribute!='value']" )`


#### 6. [Attribute Ends With Selector [name$="value"]](https://api.jquery.com/attribute-ends-with-selector/)

描述: 选择指定属性是以给定值结尾的元素. 这个比较是区分大小写的.

语法: `$( "[attribute$='value']" )`


#### 7. [Attribute Starts With Selector [name\^="value"]](https://api.jquery.com/attribute-starts-with-selector/)

描述: 选择指定属性是以给定字符串开始的元素. 

(英文描述是“Selects elements that have the specified attribute with a value beginning exactly with a given string.” 从这个exactly来看似乎也是区分大小写的...)

语法: `$( "[attribute^='value']" )`


#### 8. [Has Attribute Selector [name]](https://api.jquery.com/has-attribute-selector/)

描述: 选择所有具有指定属性的元素, 该属性可以是任何值.

语法: `$( "[attribute]" )`


#### 9. [Multiple Attribute Selector [name="value"][name2="value2"]](https://api.jquery.com/multiple-attribute-selector/)

描述: 选择匹配所有指定的属性筛选器的元素.

语法: `$( "[attributeFilter1][attributeFilter2][...][attributeFilterN]" )`



代码如下:

```html
<!DOCTYPE html>
<html lang="en" dir="ltr">
    <head>
        <meta charset="utf-8">
        <title>早点儿来, 晚点儿走.</title>
        <script src="jquery-3.4.1.js" charset="utf-8"></script>
    </head>
    <body>
        <!-- 虽然没见过hreflang, 但是我见过href和lang... -->
        <!-- jQuery 2.2.1 那会儿的主流浏览器都不支持hreflang属性. -->
        <!-- 查了一下HTML文档, 现在2019年这会儿都支持了. -->
        <a href="#" hreflang="en">制度的唯一好处是你可以跟领导说no.</a><br/>
        <a href="#" hreflang="zh">早点上班吧，有点想这些人了.</a><br/>
        <input name="shen news" /><br/>
        <input name="shen-news" id="shenNews"/><br/>
        <input name="shitshen"/><br/>
        <input name="new-fuckshen" id="fuckshen"/><br/>
        <input name="shensmomexplodes"/><br/>
        <script charset="utf-8">
            $(function () {
                $("[hreflang|=en]").css("color", "red")
            })
            $(function () {
                $("input[name~='shen']").val('Dear Mr.申')
            })
            // 现在要查找具有id属性, 且name值是以shen结尾的.
            // 然后将name值设为'Mr.申 is here.'
            $(function () {
                $("input[id][name$='shen']").val("Mr.申 is here.")
            })
        </script>
    </body>
</html>
```

效果: 

![03-选择器](https://i.loli.net/2019/07/12/5d283e969160424466.png)


### 基础过滤选择器

过滤性的选择器前面都是有`:`的形式.


#### 1. [:animated Selector](https://api.jquery.com/animated-selector/)

描述: 选择所有正在执行动画效果的元素.

语法: `$( ":animated" )`


#### 2. [:eq() Selector](https://api.jquery.com/eq-selector/)

描述: 在匹配的集合中, 选择索引值为 `n` 的元素.

语法: 

1. `$( ":eq(index)" )`: `index`: 要匹配元素的索引值(从0开始计数).
2. `$( ":eq(-index)" )`: `-index`: 要匹配元素的索引值(从0开始计数), 从最后一个元素开始倒计数.


#### 3. [:even Selector](https://api.jquery.com/even-selector/)

描述: 选择索引值为偶数的元素, 从0开始计数. 可另见 [:odd Selector](https://api.jquery.com/odd-selector/).

语法: `$( ":even" )`

注意: 索引值是基于 0 的, 所以 `:even` 选择器是选择排在第一个的元素、排在第三个的元素...以此类推再匹配.

#### 3.5 [:odd Selector](https://api.jquery.com/odd-selector/)

描述: 选择索引值为奇数的元素, 索引值从 0 开始. 可另见[:even Selector](https://api.jquery.com/even-selector/)

语法: `$( ":odd" )`

注意: 索引值是从0开始的, 所以`:odd`选择器是选择排在第二个的元素、排在第四个的元素...以此类推再匹配.

#### 4. [:first Selector](https://api.jquery.com/first-selector/)

描述: 选择第一个匹配的DOM元素.【视频里没说是DOM, 不过官方文档里说了】

语法: `$( ":first" )`


#### 5. [:focus Selector](https://api.jquery.com/focus-selector/)

描述: 选择当前获取焦点的元素.

语法: `$( ":focus" )`

举例:

```html
<!DOCTYPE html>
<html lang="en" dir="ltr">
    <head>
        <meta charset="utf-8">
        <title>衷心祝愿畐国早日倒闭</title>
        <style>
            .is-focused {
                background-color: #abcdef;
            }
        </style>
        <meta content="为当前获取焦点的元素增加背景色效果." name="description"/>
        <script src="jquery-3.4.1.js" charset="utf-8"></script>
    </head>
    <body>
        <div id="content">
            <input tabindex="1"/><br/>
            <input tabindex="2"/><br/>
            <select tabindex="3">
                <option>申帝我操你妈</option>
                <option>串相我操你妈</option>
                <option>Fuck Scdiler 3000</option>
            </select>
            <div tabindex="4">
                <p>这是一个div.</p>
            </div>
        </div>
        <script type="text/javascript">
            $(function () {
                // .delegate(): https://api.jquery.com/delegate/
                // Description: Attach a handler to one or more events for all elements that match the selector, now or in the future, based on a specific set of root elements.
                // 从jQuery 3.0开始就弃用.delegate()了, 不过还没移除. 总之现在是不鼓励用

                // .on(): https://api.jquery.com/on/
                // 看官网说明这意思, 现在推荐使用.on()方法来代替.delegate(). 注意: .on()方法和.delegate()方法的参数传递顺序不一样!!!

                // HTMLElement.focus(): https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/focus
                // 方法说明: The HTMLElement.focus() method sets focus on the specified element, if it can be focused. The focused element is the element which will receive keyboard and similar events by default.

                // HTMLElement.blur(): https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/blur
                // 方法说明: The HTMLElement.blur() method removes keyboard focus from the current element.

                $("#content").delegate("*", "focus blur", function () {
                // jQuery 3.0之后用.on()的写法是这么写:
                // $("#content").on("focus blur", "*", function () {
                    var e = $(this);
                    // WindowOrWorkerGlobalScope.setTimeout(): https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/setTimeout
                    // 方法说明: The setTimeout() method of the WindowOrWorkerGlobalScope mixin (and successor to Window.setTimeout()) sets a timer which executes a function or specified piece of code once the timer expires.
                    // 注意setTimeout的方法名不要写错!!! o是小写的o!!! 第把调这个调了老半天...
                    setTimeout(function () {
                        // .is(): https://api.jquery.com/is/
                        // 方法说明: Check the current matched set of elements against a selector, element, or jQuery object and return true if at least one of these elements matches the given arguments.
                        e.toggleClass("is-focused", e.is(":focus"))
                    }, 0)
                })
            })
        </script>
    </body>
</html>

```

效果:

![:focus](https://i.loli.net/2019/07/15/5d2be251b540652289.png)


#### 6. [:header Selector](https://api.jquery.com/header-selector/)

描述： 选择所有标题元素, 像`h1`、`h2`、`h3`等.

语法: `$( ":header" )`


#### 7. [:last Selector](https://api.jquery.com/last-selector/)


描述: 选择最后一个匹配的元素.

语法: `$( ":last" )`


#### 8. [:gt() Selector](https://api.jquery.com/gt-selector/)

描述: 选择匹配集合中所有**大于**给定`index`(索引值)的元素.

语法: `$( ":gt(index)" )`【下标从0开始】 或 `$( ":gt(-index)" )`【下标从0开始, 从最后一个元素往回数】



#### 9. [:lt() Selector](https://api.jquery.com/lt-selector/)

描述: 选择匹配集合中所有索引值**小于**给定`index`参数的元素.

语法: `$( ":lt(index)" )` 或 `$( ":lt(-index)" )`

举例:

```html
<!DOCTYPE html>
<html lang="en" dir="ltr">
    <head>
        <meta charset="utf-8">
        <title>高新技术</title>
        <script src="jquery-3.4.1.js" charset="utf-8"></script>
    </head>
    <body>
        <table border="1">
            <caption><strong>注意: 我在结尾加这个编号只是为了方便看, 实际上不需要这个数值.</strong></caption>
            <tr>
                <td>申帝 #0</td>
                <td>串相 #1</td>
                <td>右妃 #2</td>
            </tr>
            <tr>
                <td>艹帅 #3</td>
                <td>㐅大将 #4</td>
                <td>赤国师 #5</td>
            </tr>
            <tr>
                <td>木贵人 #6</td>
                <td>宛史官 #8</td>
                <td>丶贵人 #7</td>
            </tr>
            <tr>
                <td>厶将军 #9</td>
                <td>羽将军 #10</td>
                <td>长皇后 #11</td>
            </tr>
        </table>
        <script type="text/javascript">
            $(function () {
                $("td:lt(4)").css("backgroundColor", "green")
                $("td:gt(-4)").css("color", "red")
            })
        </script>
    </body>
</html>
```

效果:

![大于小于](https://i.loli.net/2019/07/15/5d2bf512139c768041.png)


#### 10. [:not() Selector](https://api.jquery.com/not-selector/)

说明: 选择所有元素中那些不匹配给定的选择器的元素.

用法: `$( ":not(selector)" )`


### 子元素选择器

#### 1. [:first-child Selector](https://api.jquery.com/first-child-selector/)


描述: 选择所有父级元素下的第一个子元素.

语法: `$( ":first-child" )`

`:first-child`等价于`:nth-child(1)`.


#### 2. [:last-child Selector](https://api.jquery.com/last-child-selector/)


描述: 选择所有父级元素下的最后一个子元素.

语法: `$( ":last-child" )`


#### 3. [:first-of-type Selector](https://api.jquery.com/first-of-type-selector/)

描述: 选择所有相同的元素名称的第一个兄弟元素.

> Description: Selects all elements that are the first among siblings of the same element name.

留着当英语阅读题, 或者英语二笔题.


语法: `$( ":first-of-type" )`

#### 4. [:last-of-type Selector](https://api.jquery.com/last-of-type-selector/)

描述: 选择所有元素之中具有相同元素名称的最后一个兄弟元素.

> Description: Selects all elements that are the last among siblings of the same element name.

语法: `$( ":last-of-type" )`



#### 5. [:nth-child() Selector](:nth-child() Selector)

描述: 选择它们的所有父元素的第`n`个子元素.

> Description: Selects all elements that are the nth-child of their parent.

语法: `$( ":nth-child(index/even/odd/equation)" )`


举例:

```html
<!DOCTYPE html>
<html lang="en" dir="ltr">
    <head>
        <meta charset="utf-8">
        <script src="jquery-3.4.1.js" charset="utf-8"></script>
        <style>
            /*
             * CSS 具名颜色清单:
             * https://kapeli.com/cheat_sheets/CSS_Named_Colors.docset/Contents/Resources/Documents/index
             */
            .sodagreen {
                background-color: LimeGreen;
            }
            .hatgreen {
                background-color: ForestGreen;
            }
        </style>
        <title></title>
    </head>
    <body>
        <!-- 需求: 给每一个div中的第一个span标签添加一些样式. -->
        <div>
            <span>申帝</span>
            <span>畐太祖</span>
            <span>串相</span>
        </div>
        <div>
            <span>右妃</span>
            <span>木贵人</span>
            <span>丶贵人</span>
        </div>
        <div>
            <span>艹帅</span>
            <span>㐅大将</span>
            <span>厶将军</span>
        </div>
        <script type="text/javascript">
            $(function () {
                $("div span:first-child").css("text-decoration", "underline").hover(function () {
                    $(this).addClass("hatgreen")
                }, function () {
                    $(this).removeClass("hatgreen")
                })
                $("div span:last-child").css("text-decoration", "overline").hover(function () {
                    $(this).addClass("sodagreen")
                }, function () {
                    $(this).removeClass("sodagreen")
                })
            })
        </script>
    </body>
</html>
```

效果(我把两个图合一起了...):

![Unti<x>tled.png](https://i.loli.net/2019/07/16/5d2d360659ce791056.png)

### 内容选择器

#### 1. [:contains() Selector](https://api.jquery.com/contains-selector/)

描述: 选择所有包含指定文本的元素.

语法: `$( ":contains(text)" )`

注意: `text`: 用来查找的一个文本字符串. 它是区分大小写的. 匹配的文本可以直接出现在所选的元素中, 或在该元素的任何后代中, 或两者兼有.


举例:

```html
<!DOCTYPE html>
<html lang="en" dir="ltr">
    <head>
        <meta charset="utf-8">
        <script src="jquery-3.4.1.js" charset="utf-8"></script>
        <title></title>
    </head>
    <body>
        <!-- 选择所有包含 fucheng 的div, 并下划线之. -->
        <div>www.e-fucheng.com</div>
        <div>www.scdiler.com</div>
        <div>js.e-fucheng.com</div>
        <div>yun.e-fucheng.com</div>
        <script type="text/javascript">
            $(function () {
                $("div:contains('fucheng')").css("text-decoration", "underline")
            })
        </script>
    </body>
</html>
```

效果:


![WX20190716-112606@2x.png](https://i.loli.net/2019/07/16/5d2d43fa0834951796.png)

#### 2. [:empty Selector](https://api.jquery.com/empty-selector/)


描述: 选择所有没有子元素的元素(包括文本节点).

> Description: Select all elements that have no children (including text nodes).

语法: `$( ":empty" )`

注意: `:empty`是`:parent`的逆.


举例:


```html
<!DOCTYPE html>
<html lang="en" dir="ltr">
    <head>
        <meta charset="utf-8">
        <script src="jquery-3.4.1.js" charset="utf-8"></script>
        <title></title>
    </head>
    <body>
        <!-- 查找所有的td内容为空的元素, 并为之添加一个背景颜色. -->
        <!-- table元素的border attribute已经deprecated了. -->
        <!-- 现在应该是用 border、border-color、border-width 和 border-style 这些个CSS properties来修饰table元素的这方面. -->
        <table border="1">
            <tr>
                <td>申帝</td>
                <td>串相</td>
            </tr>
            <tr>
                <td></td>
                <td>长皇后</td>
            </tr>
            <tr>
                <td>艹帅</td>
                <td>㐅大将</td>
            </tr>
            <tr>
                <td></td>
                <td></td>
            </tr>
            <tr>
                <td>木贵人</td>
                <td>右妃</td>
            </tr>
            <tr>
                <td>厶将军</td>
                <td></td>
            </tr>

        </table>
        <script type="text/javascript">
            $("td:empty").text("单元格内容为空").css("background-color", "green")
        </script>
    </body>
</html>

```

效果:

![WX20190716-132633@2x.png](https://i.loli.net/2019/07/16/5d2d6013b67a287807.png)

#### 3. [:has() Selector](https://api.jquery.com/has-selector/)


描述: 选择元素, 在其中至少包含指定选择器匹配的一种元素.

用法: `$( ":has(selector)" )`

举例:

```html
<!DOCTYPE html>
<html lang="en" dir="ltr">
    <head>
        <meta charset="utf-8">
        <script src="jquery-3.4.1.js" charset="utf-8"></script>
        <title></title>
        <style>
            .hatgreen {
                border: 1px solid green;
            }
        </style>
    </head>
    <!-- 给所有含有p标签的div元素添加一个hatgreen类. -->
    <body>
        <div>
            <p>申帝你妈炸了.</p>
        </div>
        <div>
            串相我透你妈.【串相木有小丁丁】
        </div>
        <script type="text/javascript">
            $(function () {
                $("div:has(p)").addClass("hatgreen")
            })
        </script>
    </body>
</html>

```

效果:

![WX20190716-133633@2x.png](https://i.loli.net/2019/07/16/5d2d62807067280891.png)


#### 4. [:parent Selector](https://api.jquery.com/parent-selector/)

描述: 选择所有含有子元素或者文本的父级元素.

> Description: Select all elements that have at least one child node (either an element or text).


语法: `$( ":parent" )`

注意: `:parent`是`:empty`的逆.

### 表单选择器


#### 1. [:button Selector](https://api.jquery.com/button-selector/)

描述: 选择所有按钮元素和类型(type)为按钮的元素.

语法: `$( ":button" )`

#### 2. [:checkbox Selector](https://api.jquery.com/checkbox-selector/)

描述: 选择所有类型为复选框的元素.

语法: `$( ":checkbox" )`


#### 3. [:checked Selector](https://api.jquery.com/checked-selector/)

描述: 匹配所有勾选(checked or selected)的元素.

语法: `$( ":checked" )`

#### 4. [:disabled Selector](https://api.jquery.com/disabled-selector/)


描述: 选择所有被禁用的元素.

语法: `$( ":disabled" )`


#### 5. [:enabled Selector](https://api.jquery.com/enabled-selector/)

描述: 选择所有可用的元素.

语法: `$( ":enabled" )`


#### 6. [:file Selector](https://api.jquery.com/file-selector/)

描述: 选择所有类型(type)为文件(file)的元素.

语法: `$( ":file" )`

`:file` 与 `[type="file"]` 等价. 

> Additional Notes:
> 
> * Because `:file` is a jQuery extension and not part of the CSS specification, queries using `:file` cannot take advantage of the performance boost provided by the native DOM `querySelectorAll()` method. For better performance in modern browsers, use `[type="file"]` instead.

#### 7. [:focus Selector](https://api.jquery.com/focus-selector/)


描述: 选择当前获取焦点的元素.

语法: `$( ":focus" )`


#### 8. [:image Selector](https://api.jquery.com/image-selector/)

描述: 选择所有图像类型的元素.

语法: `$( ":image" )`


`:image` 与 `[type="image"]` 等价.

> Additional Notes:
> 
> * Because `:image` is a jQuery extension and not part of the CSS specification, queries using `:image` cannot take advantage of the performance boost provided by the native DOM `querySelectorAll()` method. For better performance in modern browsers, use `[type="image"]` instead.

性质和上面的 :file Selector 差不多.

#### 9. [:input Selector](https://api.jquery.com/input-selector/)

描述: 选择所有 input, textarea, select 和 button 元素.

语法: `$( ":input" )`


#### 10. [:password Selector](https://api.jquery.com/password-selector/)

描述: 选择所有类型(type)为密码(password)的元素.

语法: `$( ":password" )`


`$( ":password" )` 和 `$( "[type=password]" )` 等价.

> Additional Notes:
> 
> * Because `:password` is a jQuery extension and not part of the CSS specification, queries using `:password` cannot take advantage of the performance boost provided by the native DOM `querySelectorAll()` method. For better performance in modern browsers, use `[type="password"]` instead.

#### 11. [:radio Selector](https://api.jquery.com/radio-selector/)

描述: 选择所有类型为单选框的元素.

语法: `$( ":radio" )`


`$( ":radio" )` 和 `$( "[type=radio]" )` 等价.

> Additional Notes:
> 
> Because `:radio` is a jQuery extension and not part of the CSS specification, queries using `:radio` cannot take advantage of the performance boost provided by the native DOM `querySelectorAll()` method. For better performance in modern browsers, use `[type="radio"]` instead.



#### 12. [:submit Selector](https://api.jquery.com/submit-selector/)

描述: 选择所有类型(type)为提交的元素.

语法: `$( ":submit" )`

> The `:submit` selector typically applies to button or input elements. Note that some browsers treat `<button>` element as `type="submit"` implicitly while others (such as Internet Explorer) do not. To ensure that markup works consistently across all browsers and guarantee that it is possible to consistently select buttons that will submit a form, always specify a `type` property.
> 
> Additional Notes:
> 
> * Because `:submit` is a jQuery extension and not part of the CSS specification, queries using `:submit` cannot take advantage of the performance boost provided by the native DOM `querySelectorAll()` method. For better performance in modern browsers, use `input[type="submit"]`, `button[type="submit"]` instead.


例子1:

```html
<!DOCTYPE html>
<html lang="en" dir="ltr">
    <head>
        <meta charset="utf-8">
        <script src="jquery-3.4.1.js" charset="utf-8"></script>
        <title></title>
        <style>
            textarea {
                height: 35px;
            }
            div {
                color: red;
            }
            fieldset {
                margin: 0;
                padding: 0;
                border-width: 0;
            }
            .button-marked {
                background-color: limegreen;
                border: 3px solid red;
            }
            .image-input-marked {
                background-color: yellow;
                border: 2px solid red;
            }
        </style>
    </head>
    <body>
        <!-- 查找出所有的button, 并给它们添加一个 button-marked 类. -->
        <!-- 查找出所有image的input, 并给它们添加一个 image-input-marked 类. -->
        <form action="">
            <fieldset>
                type属性值为"button"的input标签: <input type="button" value="定点爆破SCD大楼的核爆按钮" /><br/>
                复选框: <input type="checkbox" /><br/>
                文件: <input type="file" /><br/>
                隐藏: <input type="hidden" /><br/>
                图片: <input type="image" /><br/>
                密码输入: <input type="password" /><br/>
                单选: <input type="radio" /><br/>
                重置: <input type="reset" /><br/>
                提交: <input type="submit" /><br/>
                文本: <input type="text" /><br/>
                下拉选项:
                <select>
                    <option>申畜能拱地.</option>
                    <option>串犬能咬人.</option>
                </select>
                <br/>
                文本域: <textarea></textarea>
                <br/>
                标签button: <button>定点爆破尚品天城10#2-40-1违建的核爆按钮</button>
            </fieldset>
        </form>
        <div></div>
        <script type="text/javascript">
            $(function () {
                var button = $(":button").addClass("button-marked")
                var imageInput = $("input:image").addClass("image-input-marked")
            })
        </script>
    </body>
</html>
```

效果:

![例子1.png](https://i.loli.net/2019/07/17/5d2e769e0ff8127538.png)


----

例子2:


```html
<!DOCTYPE html>
<html lang="en" dir="ltr">
    <head>
        <meta charset="utf-8">
        <script src="jquery-3.4.1.js" charset="utf-8"></script>
        <title></title>
        <style>
            textarea {
                height: 35px;
            }
            div {
                color: red;
            }
            fieldset {
                margin: 0;
                padding: 0;
                border-width: 0;
            }
            .marked {
                background-color: cyan;
                border: 1px solid orange;
            }
        </style>
    </head>
    <body>
        <!-- 查找出所有input, 并给它们添加一个marked类. -->
        <form action="">
            <fieldset>
                type属性值为"button"的input标签: <input type="button" value="定点爆破SCD大楼的核爆按钮" /><br/>
                复选框: <input type="checkbox" /><br/>
                文件: <input type="file" /><br/>
                隐藏: <input type="hidden" /><br/>
                图片: <input type="image" /><br/>
                密码输入: <input type="password" /><br/>
                单选: <input type="radio" /><br/>
                重置: <input type="reset" /><br/>
                提交: <input type="submit" /><br/>
                文本: <input type="text" /><br/>
                下拉选项:
                <select>
                    <option>申畜能拱地.</option>
                    <option>串犬能咬人.</option>
                </select>
                <br/>
                文本域: <textarea></textarea>
                <br/>
                标签button: <button>定点爆破尚品天城10#2-40-1违建的核爆按钮</button>
            </fieldset>
        </form>
        <div></div>
        <script type="text/javascript">
            $(function () {
                var input = $(":input").addClass("marked")
            })
        </script>
    </body>
</html>
```

效果: 

![例子2.png](https://i.loli.net/2019/07/17/5d2e769df11b428236.png)


---

例子3:


```html
<!DOCTYPE html>
<html lang="en" dir="ltr">
    <head>
        <meta charset="utf-8">
        <script src="jquery-3.4.1.js" charset="utf-8"></script>
        <title></title>
        <style>
        </style>
    </head>
    <body>
        <!-- 给禁用的元素添加一个值. -->
        <form>
            <input name="email" disabled="disabled">
            <input name="id" placeholder="Dear Mr.申">
        </form>
        <script type="text/javascript">
            $(function () {
                $("input:disabled").val("申帝, 我操你妈!")
            })
        </script>
    </body>
</html>
```

效果: 

![例子3.png](https://i.loli.net/2019/07/17/5d2e769dd539525756.png)


### 层级选择器

我可能会把视频里的名称翻译给搬过来, 因为我个人的翻译有时候不太信达雅, 比如我真的有可能会把Child Selector翻译成孩子选择器...

顺便表示 hierarchy 这个词我不会拼当然也不会读, 虽然看过很多次知道意思. 今天就先正视一下这个词...

hierarchy [ˈhaɪərɑ:ki]


1. N-VAR 等级制度
   A hierarchy is a system of organizing people into different ranks or levels of importance, for example in society or in a company.
   * Like most other American companies with a rigid <strong style="color:orange">hierarchy</strong>, workers and managers had strictly defined duties... 
     和其他多数拥有严格等级制度的美国公司一样，这里的工人和管理人员都有界定严格的职责。
   * She rose up the Tory <strong style="color:orange">hierarchy</strong> by the local government route... 
     她通过地方政府的渠道在保守党的等级制度中一步步地晋升。
2. N-COUNT-COLL(组织中的)掌权集团, 统治集团
   The hierarchy of an organization such as the Church is the group of people who manage and control it.
3. N-COUNT (思想、信仰的)等级体系, 分级结构
   A hierarchy of ideas and beliefs involves organizing them into a system or structure.
   * ...the notion of 'cultural imperialism' implies a <strong style="color:orange">hierarchy</strong> of cultures, some of which are stronger than others. 
     “文化扩张主义”意味着一种文化等级体系的存在, 其中有些文化要比其他文化更强大.

此外, 还有个词叫heir, 和ear发一个音, 感觉heir和hierarchy应该是同源的...

#### 1. [Child Selector ("parent > child")](https://api.jquery.com/child-selector/) 子元素选择器


描述: 选择所有指定 "parent" 元素中指定的 "child" 的直接子元素.

语法: `$( "parent > child" )`


注: 

* parent: 任何有效的选择器.
* child: 用来筛选子元素的选择器.


举例:

```html
<!DOCTYPE html>
<html lang="en" dir="ltr">
    <head>
        <meta charset="utf-8">
        <script src="jquery-3.4.1.js" charset="utf-8"></script>
        <title></title>
    </head>
    <body>
        <!-- 需求: 为class名为topnav的ul标签的所有直接的子元素添加一个边框. -->
        <ul class="topnav">
            <li>首页</li>
            <li>
                产品中心
                <ul>
                    <li>畐国云服务</li>
                    <li>RFID远距离自动识别管理系统</li>
                    <li>畐国综合运维管理平台</li>
                    <li>畐国视频智能分析管理系统</li>
                    <li>畐国远距离POE大功率供电交换机</li>
                    <li>Easy Life</li>
                </ul>
            </li>
            <li>核心服务</li>
            <li>经典案例</li>
            <li>关于畐国</li>
            <li>畐国动态</li>
            <li>项目合作</li>
            <li>联系我们</li>
        </ul>
        <script type="text/javascript">
            $(function () {
                $(".topnav>li").css("border", "1px solid red")
            })
        </script>
    </body>
</html>
```

效果:

![子元素选择器效果.png](https://i.loli.net/2019/07/17/5d2ed61c7219919494.png)

#### 2. [Descendant Selector ("ancestor descendant")](https://api.jquery.com/descendant-selector/) 后代选择器


描述: 选择给定的祖先元素的**所有**后代元素.

语法: `$( "ancestor descendant" )`

注:

* ancestor: 任何有效的选择器.
* descendant: 一个用来筛选后代元素的选择器.


举例:

```html
<!DOCTYPE html>
<html lang="en" dir="ltr">
    <head>
        <meta charset="utf-8">
        <script src="jquery-3.4.1.js" charset="utf-8"></script>
        <title></title>
    </head>
    <body>
        <!-- 需求: 为class名为topnav的ul标签的所有后代元素添加一个边框. -->
        <ul class="topnav">
            <li>首页</li>
            <li>产品中心</li>
            <li>核心服务</li>
            <li>经典案例</li>
            <li>
                关于畐国
                <ul>
                    <li>公司概况</li>
                    <li>荣誉资质</li>
                    <li>企业文化</li>
                    <li>企业自勉</li>
                    <li>科研成果</li>
                    <li>招贤纳士</li>
                </ul>
            </li>
            <li>畐国动态</li>
            <li>项目合作</li>
            <li>联系我们</li>
        </ul>
        <script type="text/javascript">
            $(function () {
                $(".topnav li").css("border", "1px solid cyan")
            })
        </script>
    </body>
</html>
```

效果:

![后代元素选择器效果.png](https://i.loli.net/2019/07/17/5d2ee0a8c770f60397.png)


#### 3. [Next Adjacent Selector ("prev + next")](https://api.jquery.com/next-adjacent-selector/) 相邻选择器

描述: 选择所有紧接在 "prev" 元素后的 "next" 元素.

语法: `$( "prev + next" )`

注: 

* prev: 任何有效的选择器
* next: 用于筛选紧跟在 "prev" 后面的元素的选择器.

举例:

```html
<!DOCTYPE html>
<html lang="en" dir="ltr">
    <head>
        <meta charset="utf-8">
        <script src="jquery-3.4.1.js" charset="utf-8"></script>
        <title></title>
    </head>
    <body>
        <!-- 需求: 为所有紧跟在 li 标签后的 li 标签添加一个边框. -->
        <ul class="topnav">
            <li>首页</li>
            <li>产品中心</li>
            <li>
                核心服务
                <ul>
                    <li>信息系统集成服务</li>
                    <li>智能化系统工程服务</li>
                    <li>智能化系统咨询设计服务</li>
                    <li>IT运维服务</li>
                    <li>IT规划咨询服务</li>
                    <li>数据机房建设服务</li>
                </ul>
            </li>
            <li>经典案例</li>
            <li>关于畐国</li>
            <li>畐国动态</li>
            <li>项目合作</li>
            <li>联系我们</li>
        </ul>
        <script type="text/javascript">
            $(function () {
                $("li+li").css("border", "1px solid blue")
            })
        </script>
    </body>
</html>

```


效果:

![相邻选择器效果.png](https://i.loli.net/2019/07/17/5d2eda6a68eaa58532.png)

确实就是首页和信息系统集成服务这两个没有被加上边框.

#### 4. [Next Siblings Selector ("prev ~ siblings")](https://api.jquery.com/next-siblings-selector/)

这个sibling是发 /i/ 的音.

描述: 匹配 "prev" 元素之后所有的兄弟元素. 它们具有相同的父元素, 并且匹配过滤 "siblings"选择器.

语法: `$( "prev ~ siblings" )`

注: 

* prev: 任何有效的选择器.
* siblings: 一个用来过滤第一选择器以后的兄弟元素的选择器.


举例:

```html
<!DOCTYPE html>
<html lang="en" dir="ltr">
    <head>
        <meta charset="utf-8">
        <script src="jquery-3.4.1.js" charset="utf-8"></script>
        <title></title>
    </head>
    <body>
        <!-- 查找id为prev后面的所有兄弟关系的li标签. -->
        <ul>
            <li id="prev">首页</li>
            <li>产品中心</li>
            <li>核心服务</li>
            <li>
                经典案例
                <ul>
                    <li>行政办公</li>
                    <li>城市综合馆</li>
                    <li>工业厂房</li>
                    <li>高端住宅</li>
                    <li>商业广场</li>
                    <li>豪华酒店</li>
                    <li>医养项目</li>
                    <li>金融项目</li>
                    <li>汽车精品4S店</li>
                </ul>
            </li>
            <li>关于畐国</li>
            <li>畐国动态</li>
            <li>项目合作</li>
            <li>联系我们</li>
        </ul>
        <script type="text/javascript">
            $(function () {
                $("#prev ~ li").css("border", "1px solid green")
            })
        </script>
    </body>
</html>

```

效果:

![兄弟选择器效果.png](https://i.loli.net/2019/07/17/5d2ee1612d9b355323.png)

应当指出, 混日子的 `<li>` 不是 `#prev` 的兄弟.


接下来真正要注意的是: 

`(prev + next)` 和 `(prev ~ siblings)` 之间最显著的不同点是它们各自的可及范围. `(prev + next)` 只达到紧随的同级元素, 而 `(prev ~ siblings)` 达到了跟随其的所有同级元素.

### jQuery扩展选择器

由于jQuery扩展选择器是对CSS 3中的选择器的扩展, 并非CSS内置的选择器中的一部分, 故使用jQuery扩展选择器查询时无法使性能得到提升. 所以使用jQuery扩展选择器的时候, 建议先使用一些CSS选择器选择部分元素, 再使用jQuery扩展选择器.

而且里面不少前面也确实都写过. 当个笑话看看吧.


#### 1. [:animated Selector](https://api.jquery.com/animated-selector/)

描述: 选择所有正在执行动画效果的元素.

#### 2. [Attribute Not Equal Selector [name!="value"]](https://api.jquery.com/attribute-not-equal-selector/)

描述: 选择不存在指定属性, 或指定的属性值不等于给定值的元素.


#### 3. [:button Selector](https://api.jquery.com/button-selector/)

描述: 选择所有按钮元素和类型为按钮的元素.


#### 4. [:checkbox Selector](https://api.jquery.com/checkbox-selector/)

描述: 选择所有类型为复选框的元素.


#### 5. [:eq() Selector](https://api.jquery.com/eq-selector/)

描述: 在匹配的集合中选择索引值为index的元素.



#### 6. [:even Selector](https://api.jquery.com/even-selector/)


描述: 选择索引值为偶数的元素, 从0开始计数. 也可以查看[:odd Selector](https://api.jquery.com/odd-selector/).


#### 7. [:file Selector](https://api.jquery.com/file-selector/)


描述: 选择所有类型为文件(file)的元素.


#### 8. [:first Selector](https://api.jquery.com/first-selector/)

描述: 选择第一个匹配的元素.


#### 9. [:gt() Selector](https://api.jquery.com/gt-selector/)

描述: 选择匹配集合中所有大于给定index(索引值)的元素.


#### 10. [:has() Selector](https://api.jquery.com/has-selector/)

描述: 选择包含匹配指定选择器的至少一个元素的元素.

> **Description:** Selects elements which contain at least one element that matches the specified selector.

#### 11. [:header Selector](https://api.jquery.com/header-selector/)

描述: 选择所有标题元素, 像 h1, h2, h3 等.

#### 12. [:hidden Selector](https://api.jquery.com/hidden-selector/)

描述: 选择所有隐藏的元素.


#### 13. [:image Selector](https://api.jquery.com/image-selector/)


描述: 选择所有图像类型的元素.



#### 14. [:input Selector](https://api.jquery.com/input-selector/)


描述: 选择所有 input, textarea, select 和 button 元素.


#### 15. [:last Selector](https://api.jquery.com/last-selector/)

描述: 选择最后一个匹配的元素.


#### 16. [:lt() Selector](https://api.jquery.com/lt-selector/)


描述: 选择匹配集合中, 所有索引值小于给定 index 参数的元素.


#### 17. [:odd Selector](https://api.jquery.com/odd-selector/)


描述: 选择索引值为奇数的元素, 从0开始计数. 也可以查看[:even Selector](https://api.jquery.com/even-selector/).


#### 18. [:parent Selector](https://api.jquery.com/parent-selector/)

描述: 选择所有含有子元素或者文本的父级元素.

#### 19. [:password Selector](https://api.jquery.com/password-selector/)

描述: 选择所有类型为密码的元素.


#### 20. [:radio Selector](https://api.jquery.com/radio-selector/)


描述: 选择所有类型为单选框的元素.

#### 21. [:reset Selector](https://api.jquery.com/reset-selector/)

描述: 选择所有类型为重置的元素.


#### 22. [:selected Selector](https://api.jquery.com/selected-selector/)

描述: 选择所有被选中的元素.


#### 23. [:submit Selector](https://api.jquery.com/submit-selector/)

描述: 选择所有类型为提交的元素.


#### 24. [:text Selector](https://api.jquery.com/text-selector/)

描述: 选择所有类型为文本的元素.


#### 25. [:visible Selector](https://api.jquery.com/visible-selector/)

描述: 选择所有可见的元素. 


举例:

```html
<!DOCTYPE html>
<html lang="en" dir="ltr">
    <head>
        <meta charset="utf-8">
        <script src="jquery-3.4.1.js" charset="utf-8"></script>
        <title></title>
    </head>
    <body>
        <!-- 给所有索引值为偶数的 tr 添加一个背景颜色, 索引值为奇数的 tr 添加一个文字颜色. -->
        <table border="1">
            <tr>
                <td>申帝</td>
            </tr>
            <tr>
                <td>串相</td>
            </tr>
            <tr>
                <td>右妃</td>
            </tr>
            <tr>
                <td>艹帅</td>
            </tr>
            <tr>
                <td>㐅大将</td>
            </tr>
            <tr>
                <td>木贵人</td>
            </tr>
            <tr>
                <td>厶将军</td>
            </tr>
            <tr>
                <td>丶贵人</td>
            </tr>

        </table>
        <script type="text/javascript">
            $(function () {
                $("table tr:even").css("background-color", "green")
                $("table tr:odd").css("color", "red")
            })
        </script>
    </body>
</html>
```

效果:

![贞良死节之臣.png](https://i.loli.net/2019/07/18/5d2ffe402cc1773682.png)



### 可见性过滤选择器

注意视频里用的是 jQuery 2.2.1, 而现在已村通电, 用的 jQuery 3.4.1. 涉及到 jQuery 3 的地方注意一下.

#### 1. [:hidden Selector](https://api.jquery.com/hidden-selector/)

描述: 选择所有隐藏的元素.

语法: `$( ":hidden" )`

注: 元素可以被认为是隐藏的的几个情况:

1. 它们的 CSS 的 `display` 的值是 `none`.
2. 它们是 `type="hidden"` 的表单元素.
3. 它们的宽度和高度都被显式 (explicitly) 设置为 0.
4. (该元素的)一个祖先元素是隐藏的, 因此该元素不会在页面上被显示.


看看官网原文.

> Elements with `visibility: hidden` or `opacity: 0` are considered to be visible, since they still consume space in the layout. During animations that hide an element, the element is considered to be visible until the end of the animation.
> 
> Elements that are not in a document are not considered to be visible; jQuery does not have a way to know if they will be visible when appended to a document since it depends on the applicable styles.
> 
> This selector is the opposite of the [:visible](https://api.jquery.com/visible-selector/) selector. So, every element selected by `:hidden` isn't selected by `:visible` and vice versa.
> 
> During animations to show an element, the element is considered to be visible at the start of the animation.
> 
> How `:hidden` is determined was changed in jQuery 1.3.2. An element is assumed to be hidden if it or any of its parents consumes no space in the document. CSS visibility isn't taken into account (therefore `$( elem ).css( "visibility", "hidden" ).is( ":hidden" ) == false`). The [release notes](https://blog.jquery.com/2009/02/20/jquery-1-3-2-released/) outline the changes in more detail.
> 
> jQuery 3 slightly modifies the meaning of `:hidden` (and therefore of [:visible](https://api.jquery.com/visible-selector/)). Starting with this version, elements will be considered `:hidden` if they don't have any layout boxes. For example, `br` elements and inline elements with no content will not be selected by the `:hidden` selector.
> 
> **Additional Notes:**
> 
> * Because `:hidden` is a jQuery extension and not part of the CSS specification, queries using `:hidden` cannot take advantage of the performance boost provided by the native DOM `querySelectorAll()` method. To achieve the best performance when using `:hidden` to select elements, first select the elements using a pure CSS selector, then use [.filter(":hidden")](https://api.jquery.com/filter/).
> * Using this selector heavily can have performance implications, as it may force the browser to re-render the page before it can determine visibility. Tracking the visibility of elements via other methods, using a class for example, can provide better performance.


#### 2. [:visible Selector](https://api.jquery.com/visible-selector/)

描述: 选择所有可见的元素.

语法: `$( ":visible" )`

注: 

如果元素占据文档中一定的空间, 元素就被认为是可见的. 可见元素具有大于 0 的宽度或高度. 所以, `visibility: hidden` 或 `opacity: 0` 元素被认为是可见的, 因为它们仍然在布局中占用空间.

不在文档中的元素被认为是隐藏的. jQuery无法知道当它们被附加到文档中的时候是否会是可见的, 因为这依赖于适用的样式.

做隐藏某个元素的动画期间, 直到动画结束之前该元素都被认为是可见的. 做显示某个元素的动画期间, 在动画的开始处该元素即被认为是可见的.


> Elements are considered visible if they consume space in the document. Visible elements have a width or height that is greater than zero.
> 
> Elements with `visibility: hidden` or `opacity: 0` are considered visible, since they still consume space in the layout.
> 
> Elements that are not in a document are considered hidden; jQuery does not have a way to know if they will be visible when appended to a document since it depends on the applicable styles.
> 
> This selector is the opposite of the [:hidden](https://api.jquery.com/hidden-selector/) selector. So, every element selected by `:visible` isn't selected by `:hidden` and vice versa.
> 
> All `option` elements are considered hidden, regardless of their `selected` state.
> 
> During animations that hide an element, the element is considered visible until the end of the animation. During animations to show an element, the element is considered visible at the start at the animation.
> 
> How `:visible` is calculated was changed in jQuery 1.3.2. The [release notes](https://blog.jquery.com/2009/02/20/jquery-1-3-2-released/) outline the changes in more detail.
> 
> jQuery 3 slightly modifies the meaning of `:visible` (and therefore of [:hidden](https://api.jquery.com/hidden-selector/)). Starting with this version, elements will be considered `:visible` if they have any layout boxes, including those of zero width and/or height. For example, `br` elements and inline elements with no content will be selected by the `:visible` selector.
> 
> Additional Notes:
> 
> * Because `:visible` is a jQuery extension and not part of the CSS specification, queries using `:visible` cannot take advantage of the performance boost provided by the native DOM `querySelectorAll()` method. To achieve the best performance when using `:visible` to select elements, first select the elements using a pure CSS selector, then use [.filter(":visible")](https://api.jquery.com/filter/).
> * Using this selector heavily can have performance implications, as it may force the browser to re-render the page before it can determine visibility. Tracking the visibility of elements via other methods, using a class for example, can provide better performance.

举例:

```html
<!DOCTYPE html>
<html lang="en" dir="ltr">
    <head>
        <meta charset="utf-8">
        <script src="jquery-3.4.1.js" charset="utf-8"></script>
        <title></title>
        <style>
            .outer {
                width: 250px;
                height: 250px;
                background-color: green;

            }
            .inner {
                background: 100px;
                height: 100px;
                background-color: #abcdef;
                display: none;
            }
        </style>
    </head>
    <body>
        <!-- 实现对 class 名为 inner 的元素的可见性的控制. -->
        <div class="outer">
            申畜一直苟活着和串犬狼狈为奸呢.
            <div class="inner">申畜的🐴被灭霸打响指化灰了呢.</div>
        </div>
        <button class="button1">响指键1</button>
        <button class="button2">响指键2</button>
        <script type="text/javascript">
            $(function () {
                $(".button1").click(function () {
                    $(".outer .inner:hidden").css("display", "block")
                })
                $(".button2").click(function () {
                    $(".outer .inner:visible").css("display", "none")
                })
            })
        </script>
    </body>
</html>

```


效果:

![Unti<x>tled.png](https://i.loli.net/2019/07/18/5d3015a38c66b63850.png)



## jQuery 事件

### [鼠标事件](https://api.jquery.com/category/events/mouse-events/)

不少都是联动 JavaScript 的相应事件的. 这个是[JavaScript的一个事件清单链接列表](https://developer.mozilla.org/en-US/docs/Web/Events), 注意参照阅读.


jQuery 鼠标事件联动 JavaScript 事件对应关系姿势网络:


| jQuery 鼠标事件 | 对应的 JavaScript 事件 |
|---|---|
| [Events > Mouse Events > .click()](https://api.jquery.com/click/) | [Element: click event](https://developer.mozilla.org/en-US/docs/Web/API/Element/click_event) |
| [Events > Mouse Events > .dblclick()](https://api.jquery.com/dblclick/) | [Element: dblclick event](https://developer.mozilla.org/en-US/docs/Web/API/Element/dblclick_event) |
| [Events > Mouse Events > .hover()](https://api.jquery.com/hover/): The `.hover()` method binds handlers for both `mouseenter` and `mouseleave` events. | 无, 不过可以参考jQuery把 `.hover()` 理解为 `.mouseenter()` + `.mouseleave()` |
| [Events > Mouse Events > .mousedown()](https://api.jquery.com/mousedown/) | [Element: mousedown event](https://developer.mozilla.org/en-US/docs/Web/API/Element/mousedown_event) |
| [Events > Mouse Events > .mouseenter()](https://api.jquery.com/mouseenter/) | [Element: mouseenter event](https://developer.mozilla.org/en-US/docs/Web/API/Element/mouseenter_event) |
| [Events > Mouse Events > .mouseleave()](https://api.jquery.com/mouseleave/) | [Element: mouseleave event](https://developer.mozilla.org/en-US/docs/Web/API/Element/mouseleave_event) |
| [Events > Mouse Events > .mousemove()](https://api.jquery.com/mousemove/) | [Element: mousemove event](https://developer.mozilla.org/en-US/docs/Web/API/Element/mousemove_event) |
| [Events > Mouse Events > .mouseout()](https://api.jquery.com/mouseout/) | [Element: mouseout event](https://developer.mozilla.org/en-US/docs/Web/API/Element/mouseout_event) |
| [Events > Mouse Events > .mouseover()](https://api.jquery.com/mouseover/) | [Element: mouseover event](https://developer.mozilla.org/en-US/docs/Web/API/Element/mouseover_event) |
| [Events > Mouse Events > .mouseup()](https://api.jquery.com/mouseup/) | [Element: mouseup event](https://developer.mozilla.org/en-US/docs/Web/API/Element/mouseup_event) |

1. `.click()`: 点击事件.
2. `.dblclick()`: 双击事件. 注意前缀是“dbl”而不是“db”...不仔细看的话确实能给少看个l...
3. `.hover()`: 鼠标悬停和离开.
4. `.mousedown()`: 鼠标按下.
5. `.mouseenter()`: 鼠标进入元素.
6. `.mouseleave()`: 鼠标离开元素.
7. `.mousemove()`: 鼠标在元素内移动.
8. `.mouseout()`: 鼠标离开元素(支持事件冒泡).
9. `.mouseover()`: 鼠标进入元素内(支持事件冒泡).
10. `.mouseup()`: 鼠标按键被释放.




关于事件冒泡, 以前真没听过, 视频里关于冒泡事件是这么说的:

> 事件按照从规定从特定的事件目标到最不特定的事件目标的顺序触发. 就是说, 从事件目标开始往上冒泡, 直到页面的最上一级标签. 这就是事件冒泡.

是不是感觉没看懂? 可以参考:

* [Event bubbling and capture](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Building_blocks/Events#Event_bubbling_and_capture)
* [Event Bubbling and Event Capturing in JavaScript](https://medium.com/@vsvaibhav2016/event-bubbling-and-event-capturing-in-javascript-6ff38bec30e)
* [Bubbling and capturing](https://javascript.info/bubbling-and-capturing)
* <a href="https://en.wikipedia.org/wiki/Event_bubbling">Event bubbling <small>From Wikipedia, the free encyclopedia</small></a>
* [What is event bubbling and capturing?](https://stackoverflow.com/questions/4616694/what-is-event-bubbling-and-capturing)


至少拿谷歌找还行, 一会儿就找着看着靠谱的了...


`.contextmenu()` 和 `.toggle()`(事件版的 `.toggle()` 在 jQuery 1.8弃用, 现移除)没说.



`.click()`举例: 

```html
<!DOCTYPE html>
<html lang="en" dir="ltr">
    <head>
        <meta charset="utf-8">
        <script src="jquery-3.4.1.js" charset="utf-8"></script>
        <title></title>
    </head>
    <body>
        <!-- 实现单击 p 标签内容, 能够将相应内容 alert 出来. -->
        <p>申帝我艹拟吗!</p>
        <p>串相我透你妈!</p>
        <p>申帝我QNMLGB!</p>
        <p>串相我去年买了个包!</p>
        <script type="text/javascript">
            // 原生JavaScript写法.
            // var p = document.getElementsByTagName("p")
            // for (var i = 0; i < p.length; i++) {
            //     p[i].onclick = function () {
            //         alert(this.innerHTML)
            //     }
            // }

            // jQuery写法.
            $(function () {
                $("p").click(function () {
                    alert($(this).html())
                })
            })
        </script>
    </body>
</html>
```


效果:

![.click](https://upload.cc/i1/2019/07/19/Sz1nra.png)


发现暴躁老哥形态的图是传不上去的😂...

jQuery 写法是比原生的 JavaScript 写法简单一些. 不过都会也确实很重要, 又不是写得有多高难. 什么都略懂一点, 生活更多彩一些. 

上面例子的原生 JavaScript 里把`onclick`改成`ondblclick`、jQuery里把`click`改成`dblclick`就是相应的双击出alert弹窗的版本.


> The `.hover()` method binds handlers for both `mouseenter` and `mouseleave` events. You can use it to simply apply behavior to an element during the time the mouse is within the element.

`.hover()` 举例:

```html
<!DOCTYPE html>
<html lang="en" dir="ltr">
    <head>
        <meta charset="utf-8">
        <script src="jquery-3.4.1.js" charset="utf-8"></script>
        <title></title>
        <style>
            .span1 {
                color: red;
                font-size: 20px;
            }
            .span2 {
                color: orange;
                font-size: 20px;
            }
            .span3 {
                color: yellow;
                font-size: 20px;
            }
            .span4 {
                color: green;
                font-size: 20px;
            }
            .span5 {
                color: cyan;
                font-size: 20px;
            }
            .span6 {
                color: blue;
                font-size: 20px;
            }
            .span7 {
                color: purple;
                font-size: 20px;
            }
        </style>
    </head>
    <body>
        <!-- 实现: 当鼠标悬浮到字符上面的时候, 相应字符能够变大;
            当鼠标移出的时候, 相应字符缩小. -->
        <span class="span1">S</span>
        <span class="span2">C</span>
        <span class="span3">D</span>
        <span class="span4">I</span>
        <span class="span5">L</span>
        <span class="span6">E</span>
        <span class="span7">R</span>
        <script type="text/javascript">
            // 注意第二个function的位置, 不要写在中间那层jQ代码平行的地方.
            $(function () {
                $("span").hover(function () {
                    $(this).css("font-size", "40px")
                }, function () {
                    $(this).css("font-size", "20px")
                })
            })
        </script>
    </body>
</html>

```

效果:

![跑马灯、.png](https://i.loli.net/2019/07/19/5d3153e33e0ef58190.png)


由于找不到模板项目的实际跑马灯图片, 颜色就先那么弄了.

注意`.hover()`有两种用法:

* 悬浮上和退出悬浮用的两个不同事件的`.hover( handlerIn, handlerOut )`;
* 悬浮上和退出悬浮都用的一个事件的`.hover( handlerInOut )`.


再来个`.mousedown()`和`.mouseup()`的例子:

```html
<!DOCTYPE html>
<html lang="en" dir="ltr">
    <head>
        <meta charset="utf-8">
        <script src="jquery-3.4.1.js" charset="utf-8"></script>
        <title></title>
    </head>
    <body>
        <!-- 实现鼠标在 p 标签上移动, 能够放大字体; 离开 p 标签, 字体恢复原大. -->
        <!-- 之前通过检查元素知道原先字体大小是 16px. -->
        <!-- 也可以用jQuery的`.css( propertyName )`方法直接从页面中读取属性值. 但是会出现意料外的情形. 比如弄一弄字体就不恢复原样了. -->
        <p>大家的努力领导都看在眼里, 年底一定会有说法的.</p>
        <p>早点儿来, 晚点儿走.</p>
        <p>拍拍胸脯问问你自己, 干出今天的产值没有.</p>
        <p>肯定行, 没问题, 放一万个心.</p>
        <script type="text/javascript">
            $(function () {
                $("p").mousemove(function () {
                    $(this).css("fontSize", "40px")
                })
                $("p").mouseout(function () {
                    $(this).css("fontSize", "16px")
                })
            })
        </script>
    </body>
</html>

```

效果:

![mousedown和up.png](https://i.loli.net/2019/07/19/5d3180b62274622411.png)


再举个 `.mouseenter()` 和 `.mouseleave()` 的例子:


```html
<!DOCTYPE html>
<html lang="en" dir="ltr">
    <head>
        <meta charset="utf-8">
        <script src="jquery-3.4.1.js" charset="utf-8"></script>
        <title></title>
        <style>
            div {
                width: 200px;
                height: 50px;
            }
        </style>
    </head>
    <body>
        <!-- 实现鼠标进入div区域, 颜色就发生改变; 鼠标离开div区域, 颜色再改变. -->
        <div>
            <p>申帝我QNMLGB!</p>
        </div>
        <div>
            <p>串相我去年买了个包!</p>
        </div>
        <div>
            <p>申帝我艹拟吗!</p>
        </div>
        <div>
            <p>串相我透你妈!</p>
        </div>
        <script type="text/javascript">
            $(function () {
                $("div").mouseenter(function () {
                    $(this).css("color", "green")
                })
                $("div").mouseleave(function () {
                    $(this).css("color", "black")
                })
            })
        </script>
    </body>
</html>

```


效果:

![mouseenter和leave.png](https://i.loli.net/2019/07/19/5d315e9ea3c1b30228.png)

再来个 `.mouseover()` 和 `.mouseout()` 的例子:

```html
<!DOCTYPE html>
<html lang="en" dir="ltr">
    <head>
        <meta charset="utf-8">
        <script src="jquery-3.4.1.js" charset="utf-8"></script>
        <title></title>
    </head>
    <body>
        <!-- 实现鼠标放到 p 标签上的时候, 能够放大字体; 不在 p 标签, 字体恢复原大. -->
        <p>大家的努力领导都看在眼里, 年底一定会有说法的.</p>
        <p>早点儿来, 晚点儿走.</p>
        <p>拍拍胸脯问问你自己, 干出今天的产值没有.</p>
        <p>肯定行, 没问题, 放一万个心.</p>
        <script type="text/javascript">
            // 之前通过检查元素知道原先字体大小是 16px. 直接赋值的写法.
            // $(function () {
            //     $("p").mouseover(function () {
            //         $(this).css("fontSize", "40px")
            //     })
            //     $("p").mouseout(function () {
            //         $(this).css("fontSize", "16px")
            //     })
            // })

            // 也可以用jQuery的 `.css( propertyName )` 方法直接从页面中读取属性值.
            // 不过不知道对不对, 为此试了一段时间, 看样子没什么问题.
            // 但是你 `.mousemove()` 换 `.mouseover()` 是一定会有问题的.
            $(function () {
                let originFontSize = 0
                $("p").mouseover(function () {
                    originFontSize = $(this).css("fontSize")
                    $(this).css("fontSize", "40px")
                })
                $("p").mouseout(function () {
                    $(this).css("fontSize", originFontSize)
                })
            })
        </script>
    </body>
</html>

```

效果:

![mouseover和out.png](https://i.loli.net/2019/07/19/5d3163010b98f23859.png)

一般 `.mouseover()` 和 `.mouseout()` 一起使用, `.mouseenter()` 和 `.mouseleave()` 一起使用.



再看一下 `.mousemove()`的例子:


```html
<!DOCTYPE html>
<html lang="en" dir="ltr">
    <head>
        <meta charset="utf-8">
        <script src="jquery-3.4.1.js" charset="utf-8"></script>
        <title></title>
        <style>
            div {
                width: 400px;
                height: 50px;
            }
        </style>
    </head>
    <body>
        <div>
            <p>大家的努力领导都看在眼里, 年底一定会有说法的.</p>
        </div>
        <div>
            <p>早点儿来, 晚点儿走.</p>
        </div>
        <div>
            <p>拍拍胸脯问问你自己, 干出今天的产值没有.</p>
        </div>
        <div>
            <p>肯定行, 没问题, 放一万个心.</p>
        </div>
        <script type="text/javascript">
            let i = 0
            $(function () {
                $("p").mousemove(function () {
                    console.log('艹申帝的🐴' + (i++) + '次.')
                })
            })
        </script>
    </body>
</html>

```



效果:

![mousemove.png](https://i.loli.net/2019/07/23/5d3699745637085759.png)


### [键盘事件](https://api.jquery.com/category/events/keyboard-events/)


jQuery 的键盘事件有三个:

1. `.keydown()`: 在键盘按下时被触发.
2. `.keypress()`: 在敲击键盘时被触发, 我们可以理解为按下并抬起同一个键.
3. `.keyup()`: 在按键释放时被触发.


有相应的 JavaScript 事件. 上[JS Event Reference](https://developer.mozilla.org/en-US/docs/Web/Events)里去翻对应的 keyboard 的.

#### 常用Windows键盘按键对应代码


可以看看[谁知道电脑键盘按键代码表](https://zhidao.baidu.com/question/103727178.html), 看起来比较准. 

这个是Windows版的, 注意一下. 


| Windows键盘按键 | 对应代码 |
|---|---|
| Backspace | 8 |
| Tab | 9 |
| Clear | 12 |
| Enter | 13 |
| Shift | 16 |
| Control | 17 |
| Alt | 18 |
| Caps Lock | 20 |
| Esc | 27 |
| 空格键 | 32 |


先看个`.keydown()`的例子:

```html
<!DOCTYPE html>
<html lang="en" dir="ltr">
    <head>
        <meta charset="utf-8">
        <script src="jquery-3.4.1.js" charset="utf-8"></script>
        <title></title>
    </head>
    <body>
        <!-- 获取 mac 键盘上按键对应的代码. -->
        <script type="text/javascript">
            $(document).keydown(function (event) {
                alert('按键名: ' + event.key + ';\n按键代码: ' + event.keyCode + '.')
            })
        </script>
    </body>
</html>

```

效果:

![keydown.png](https://i.loli.net/2019/07/23/5d36ab5a25fb281059.png)

基本是对的. 主要是对于这种BD和西S地N上找的东西, 我向来不完全信任结果.

键盘事件的触发顺序: 当 `.keydown()`、`.keypress()`、`.keyup()` 这三个事件都被注册的时候, 它是先触发 `.keydown()`, 再触发 `.keypress()`. 只有在 `.keydown()` 和 `.keypress()` 没有注册的情况下, 才会触发 `.keyup()`, 否则就不会触发 `.keyup()`.

具体来说, 举例如下:


```html
<!DOCTYPE html>
<html lang="en" dir="ltr">
    <head>
        <meta charset="utf-8">
        <script src="jquery-3.4.1.js" charset="utf-8"></script>
        <title></title>
    </head>
    <body>
        <!-- 观察`.keydown()`、`.keypress()`、`.keyup()`的触发情况. -->
        <!-- 这么写的话只会触发 `.keydown()`、`.keypress()`, 但不会触发 `.keyup()`. -->
        <script type="text/javascript">
            $(document).keydown(function (event) {
                alert('keydown了.')
            })
            $(document).keypress(function (event) {
                alert('keypress了.')
            })
            $(document).keyup(function (event) {
                alert('keyup了.')
            })
        </script>
    </body>
</html>

```

效果:

![先down后press.png](https://i.loli.net/2019/07/23/5d36b8accae7629350.png)


还有这个关于 `.keyup()` 的例子:

```html
<!DOCTYPE html>
<html lang="en" dir="ltr">
    <head>
        <meta charset="utf-8">
        <script src="jquery-3.4.1.js" charset="utf-8"></script>
        <title></title>
    </head>
    <body>
        <!-- 观察`.keydown()`、`.keypress()`、`.keyup()`的触发情况. -->
        <!-- `.keydown()`、`.keypress()` 都没有注册的时候, 才会触发 `.keyup()`. -->
        <script type="text/javascript">
            $(document).keyup(function (event) {
                alert('keyup了.')
            })
        </script>
    </body>
</html>

```


效果:

![都没注册才keyup.png](https://i.loli.net/2019/07/23/5d36b9d5c545a61521.png)

### [浏览器事件](https://api.jquery.com/category/events/browser-events/)


浏览器事件有如下几个:

* `.error()`: 出现错误的处理事件. 这个不看也罢, 在 jQuery 1.8中被弃用, 在 jQuery 3.0 中被移除. 至于从 jQuery 3.0 开始怎么找东西替代, 可以参见[.error() function alternative on jquery 3.x](https://stackoverflow.com/questions/45282498/error-function-alternative-on-jquery-3-x)
* `.resize()`: 页面重置事件. 当页面大小改变的时候它会被触发. 它是给`window`来绑定的.
* `.scroll()`: 滚动事件. 



先来一个 `.error()` 替代方法的例子:

```html
<!DOCTYPE html>
<html lang="en" dir="ltr">
    <head>
        <meta charset="utf-8">
        <script src="jquery-3.4.1.js" charset="utf-8"></script>
        <title></title>
    </head>
    <body>
        <!-- jQ 3 之前浏览器事件的 `.error()` 方法. -->
        <!-- 我们用的 jQ 3.4.1, 用不了这个, 我们用替代方法. -->

        <!-- 给一个不存在的静态图片资源路径, 来产生错误. -->
        <img src="deepest-place-in-the-vaginal-orifice-of-shendi-mom" />
        <script type="text/javascript">
            $(function () {
                $("img").on('error', function () {
                    alert('申帝, 你家右妃跟人跑了.')
                })
            })
        </script>
    </body>
</html>

```

效果:

![.error()替代操作.png](https://i.loli.net/2019/07/23/5d36cd9c2cba017203.png)

来个 `.scroll()` 事件针对整个窗口的例子:


```html
<!DOCTYPE html>
<html lang="en" dir="ltr">
   <head>
      <meta charset="utf-8">
      <script src="jquery-3.4.1.js" charset="utf-8"></script>
      <title></title>
      <style>
         p {
            color: red;
         }
         span {
            color: blue;
         }
         pre {
            color: orange;
         }
      </style>
   </head>
   <body>
      <!-- 我们看一下浏览器的 `.scroll()` 事件 -->
      <span>“苟利单位生死以, 岂因祸福避趋之.”</span><br/>
      <span>“寄意寒星荃不察, 我以我血荐单位.”</span><br/>
      <span>“干而不思则罔, 思而不干则殆.”</span><br/>
      <span>“一个真正具有公司发展正史深刻意义的时刻－－一个公司员工的群星闪耀时刻出现以前, 必然会有漫长的岁月没有意义地流逝而去, 那些平时慢慢悠悠顺序发生和并列发生的事, 都压缩在这样一个决定一切的短暂时刻表现出来. 这一时刻对世世代代作出不可改变的决定, 它决定着一个公司的上市、一个单位的存续甚至整个行业的命运.”</span><br/>
      <span>“孤单, 是一个人的开会; 开会, 是一群人的孤单.”</span><br/>
      <span>“上市本身就是好的。有一天我们都会死去, 追求上市的道路还会有公司在走着. 死掉以后的事我看不到, 但在我活着的时候, 想到这件事, 心里就很高兴.”</span><br/>
      <span>“个人再大的事儿也是小事儿, 公司再小的事儿也是大事儿.”</span><br/>
      <span>“公司自成立以来, 就有埋头苦干的人, 有拼命硬干的人, 有殒身不恤的人, 有鞠躬尽瘁的人……虽是等于在我司上市历史进程中写入的所谓‘正史’, 也往往掩不住他们的光耀, 这就是公司的脊梁.”</span><br/>
      <span>“博学之, 审问之, 慎思之, 明辨之, 笃行之.”</span><br/>
      <span>“纵观公司上市历史长河, 危机时刻有幸担当维持公司产值大任的人们并非多数. 我不愿逃避责任——我乐于承担. 我不相信谁能避开现实. 我们为公司上市事业所尽的力量、忠诚和奉献将照亮这个公司和所有为之服务的人们——其光芒也将照亮整个行业. 所以, 我亲爱的同事, 不要问你的公司能为你做什么, 问你能为你的公司做什么; 我亲爱的同行和甲方, 不要问我司能为你做什么, 问我们大家能为我司的雄起做什么.”</span><br/>
      <span>“凡事预则立, 不预则废.”</span><br/>
      <span>“生, 亦我所欲也; 上市, 亦我所欲也. 二者不可得兼, 舍生而取上市者也.”</span><br/>
      <span>人最宝贵的东西是生命, 生命属于人只有一次. 一个人的一生应该是这样度过的: 当他回首往事的时候, 他不会因为虚度年华而悔恨, 也不会因为碌碌无为而羞耻; 这样, 在临死的时候, 他就能够说:“我的整个生命和全部精力, 都已经献给世界上最壮丽的事业——为公司的上市而奋斗.”</span><br/>
      <span>企业号发日志是平台内容的多样展示, 是工作内容的全面复盘, 是集体纪律的高度体现, 是公司上市的必要保证.一定要想方设法把日志发粗来.</span><br/>
      <span>“大江歌罢掉头东, 邃密群科济世穷。面壁十年图破壁, 未能上市亦英雄.”</span><br/>
      <span>“凡是领导作出的决策, 我们都坚决拥护; 凡是领导的指示, 我们都始终不渝地遵循.”</span><br/>
      <span>“希望你有个美好的夜晚. 从公司的窗户望出去, 可以欣赏到日出的愉悦景象, 还有就寝前天空宁静的繁星.”</span><br/>
      <span>中国古人说: “口言之, 身必行之.”实现公司上市, 需要每个员工脚踏实地拿出行动.</span><br/>
      <span>公司广大员工要不忘初心、牢记使命, 以“上市不必在我”的精神境界和“上市必定有我”的历史担当, 保持历史耐心, 发扬具有公司特色的上市精神, 一条上市路走到底, 一任接着一任干.</span><br/>
      <span>辛弃疾在一首词中写道:“乘风好去, 长空万里, 直下看山河.”上市梦是历史的、现实的, 也是未来的; 是我们这一代的, 更是下一代的.</span><br/>
      <span>吾心信上市可行, 则移山填海之难, 终有成功之日; 吾心信上市不可行, 则反掌折枝之易, 亦无收效之期也.</span><br/>
      <span>公司已经到了最危急的时候了, 现在这个行业大家日子都不好过. 每天拍良心想一想, 拍拍胸脯问问你自己, 你干出今天的产值了吗? 你干出的产值够不够每天在公司吃中午饭的饭钱? 你还好意思走那么早吗?</span><br/>
      <span>“功以才成, 业由才广. 世上一切事物中公司是最可宝贵的, 一切上市成果都是公司实现的.”</span><br/>
      <span>“孔子登东山而小鲁, 登泰山而小天下.” 面对行业大发展大变革大调整的新形势, 为更好推进公司上市进步事业, 我们必须登高望远, 正确认识和把握上市大势和行业潮流.</span><br/>
      <span>“从实践到认识、从认识到实践, 实践、认识、再实践、再认识, 认识运动不断反复和无限发展, 这是公司上市认识运动的辩证发展过程, 也是公司上市认识运动的基本规律.”</span><br/>
      <span>“潮平两岸阔, 风正一帆悬.” 新时代公司上市的航线已经明确, 公司全面崛起的巨轮正在乘风破浪前行.</span><br/>
      <span>“行业里并不全是阳光和彩虹, 这是个十分卑鄙肮脏的地方. 我不管你有多狠, 但只要你允许, 公司的竞争对手会永久性地把你打得跪在地上起不来. 你、我、没有人, 能打得比竞争对手还重. 但重要的并不是你能打多重, 而是你能挨多重, 并且坚持促进公司上市. 你能承受多少并且推动公司上市, 这样才叫胜利!”</span><br/>
      <span>工作时希望一生年少, 上市时希望瞬间变老.</span><br/>
      <span>“广大员工要坚定理想信念, 志存高远, 脚踏实地, 勇做时代的弄潮儿, 在实现上市梦的生动实践中放飞个人梦想, 在为公司利益的不懈奋斗中书写人生华章!”</span><br/>
      <span>上市从来都是九死一生, 但我们必须有“亦余心之所善兮, 虽九死其犹未悔”的豪情.</span><br/>
      <span>孜孜不倦, 必能求索; 风尘仆仆, 终有归途.</span><br/>
      <span>“九层之台, 起于累土. 要把公司上市这个蓝图变为现实, 必须不驰于空想、不鹜于虚声, 一步一个脚印, 踏踏实实干好工作.”</span><br/>
      <span>“广大公司员工坚持爱岗奉献, 无怨无悔, 让我感到千千万万普通人最伟大, 同时让我感到上市都是奋斗出来的.”</span><br/>
      <span>“每晚八点召开的晚间公司代表大会, 是工作日志的另类补充, 是工作方式的多维体现, 是工作时间的广博延展, 是工作内容的全面复盘, 是公司蓝图的高度前瞻, 是公司意志的深刻凝聚, 是公司纪律的丰富具象, 是公司上市的必要保障. 一定要身体力行、想方设法、不惜一切将公司代表大会制度贯彻到底、落地到位、推广到点.”</span><br/>
      <span>“我们要以庆祝公司成立20周年为契机, 逢山开路, 遇水架桥, 将上市进行到底.”</span><br/>
      <span>“积土而为山, 积水而为海.”幸福和美好的上市未来不会自己出现, 成功属于勇毅而笃行的人.</span><br/>
      <span>“像蜜蜂一样勤劳工作才能享受蜜甜生活.”</span><br/>
      <span>“对公司上市事业有功的人才配进入公司的凌烟阁; 公司上市路上的绊脚石们则当防备火狱, 那是用人和石做燃料的, 已为他们预备好了. 所有站在公司利益对立面的人都注定要被钉在公司门口的耻辱柱上, 这下场真恶劣!”</span><br/>
      <span>“公司有什么精神？公司有特别能吃苦、特别能战斗、特别能攻关、特别能奉献的促进上市精神.”</span><br/>
      <span>古今之成大公司、大事业者, 罔不经过三种之境界:“昨夜西风凋碧树, 独上单位, 望尽上市路.” 此第一境界也; “衣带渐宽终不悔, 上市消得人憔悴.” 此第二境界也; “众里寻它千百度, 蓦然回首, 上市正在灯火阑珊处.” 此第三境界也.</span><br/>
      <span>“上市无王者之道.” —— 欧几里得</span><br/>
      <span>“世间最真挚的爱莫过于对公司的爱.”——萧伯纳</span><br/>
      <span>“一次次规范的公司项目, 使员工的个人觉悟、集体意识、纪律观念得到锤炼; 一次次高质量的代表大会, 使员工学习理论、交流业务、坚定上市的过程得到升华; 一次次制度化的流程建设, 使员工经常感受到领导的存在、公司的力量、部门的帮助.”</span><br/>
      <span>“上市的盛宴已经摆在我们的面前, 现在唯一的问题是我们的胃口怎么样.”—— 林语堂</span><br/>
      <span>“发领导愿, 结甲方缘, 享工作福; 择项目立, 寻公司住, 向上市行.”</span><br/>
      <span>“新形势下, 公司的上市工作只能加强, 不能削弱; 只能改进提高, 不能停滞不前.”</span><br/>
      <span>会而必议, 议而必行, 行而必决, 决而必果.</span><br/>
      <span>“Three passions, simple but overwhelmingly strong, have governed my life: the longing for listing, the search of rise, and unbearable pity for the suffering of competitor.” —— 伯特兰·罗素</span><br/>
      <pre>
“Be near me when I fade away,
   To point the term of company listing,
   And on the low dark verge of life,
   The twilight of eternal day.” —— 阿尔弗雷德·丁尼生
      </pre>
      <span>"Years may wrinkle the skin, but to give up listing wrinkles the soul."</span><br/>
      <pre>
“Made weak by time and competitor, but strong in will of listing.
    To strive, to seek, to find, and not to yield.” —— 阿尔弗雷德·丁尼生
      </pre>
      <pre>
“丢了一个钉子, 坏了一只蹄铁;
 坏了一只蹄铁, 折了一匹战马;
 折了一匹战马, 伤了一位骑士;
 伤了一位骑士, 输了一场战斗;
 输了一场战斗, 亡了一个帝国.”
     ——《钉子与王国》
     天气炎热, 今天不报中午饭. 各位旁友在外注意饮食安全, 切勿饮用过凉饮品刺激肠胃, 避免吃坏肚子, 降低效率, 影响产值, 耽误上市.
      </pre>
      <span>“大厨在炖芸豆里放了这么多猪皮, 虽然从形式上看不清真, 却也是让大家美容养颜, 提升公司形象, 拿下更多业务, 增加公司产值, 推动公司上市. 大家都在自己的岗位上默默耕耘, 为公司的上市事业添砖加瓦. 这就是到单位最需要的地方去、会什么干什么的公司服务器精神. 安拉胡阿克巴!”</span><br/>
      <span>“现在, 我们提出觉悟上靠得住、工作上有本事、作风上过得硬、公司领导信得过等具体要求, 突出了好员工标准的时代内涵.”</span><br/>
      <span>“上市是段光谱. 白里透黑。暗里有光. 少年才问黑白, 成年人只看几十度灰.”</span><br/>
      <span>“一个人做好上市每一个阶段中应该做好的事情, 把领导让你做的事情尽可能地做到极致甚至像绿教徒那样对待自己喜欢的职业并愿意为此努力一生, 你就是一个具有使命感的人. 所谓工匠精神, 本质上与这种对领导的敬畏和使命感的理解与坚守密不可分. 工匠精神与功利主义无缘.”——《公司命运与个人命运》</span><br/>
      <span>“今天的公司面对着前所未有的经济全球化的大环境、面对着如何成为创新性高新技术企业的重任, 只有我们每一个人、单位的每一位员工成为真正的人, 即成为具有学习能力、独立思考能力、自主选择能力、奉献能力、战胜困难能力和有使命感的人, 你自己的一生才会幸福, 我们这个公司才能不断进步, 公司上市才真的有希望.”——《公司命运与个人命运》</span><br/>
      <span>“认真学习贯彻新时代公司特色上市主义思想, 自觉用科学上市理论武装头脑、指导实践、推动工作, 坚定公司特色上市主义道路自信、理论自信、制度自信、文化自信。”</span><br/>
      <span>“公司领导高度重视公司代表大会筹备工作, 多次听取公司代表汇报, 对做好大会筹备工作作出明确指导, 为大会的召开和员工的工作指明了方向.”</span><br/>
      <span>“以领导为本, 心系领导、心向领导, 了解领导所需所急所盼, 真心诚意服务领导。”</span><br/>
      <span>“新时代呼唤新作为. 公司代表大会擘画的宏伟蓝图, 为员工工作发展带来了难得的机遇, 也对员工工作提出了更高的要求.”</span><br/>
      <span>公司还有什么精神? 公司还有“春蚕到死丝方尽, 蜡炬成灰泪始干”“鞠躬尽瘁, 死而后已”“横眉冷对甲方指,俯首甘为公司牛”的奉献精神、“身先士卒先拔头筹一马当先”的测试电动车精神、“到公司最需要的地方去, 到项目最需要的地方去, 到上市最需要的地方去”的服务器精神、“战至最后一口气, 流尽最后一滴血, 打光最后一颗子弹”的笔记本精神。</span><br/>
      <span>上市工作, 抓住的是当下, 传承的是根脉, 面向的是未来, 攸关公司前途命运。我们要有千钧重任在肩的神圣感使命感, 倾心倾情倾力为公司做好上市工作。</span><br/>
      <span>“现在就能出来逛街的, 都是有钱人家里啥事儿都不用干的阔太太. 我们能做的, 就是多创造产值, 让公司早日上市, 使得公司里的每一个成员, 都能在工作日想逛就逛.”</span><br/>
      <span>“从运行机理看, 为领导服务的内在动力来自价值实现的需要, 即员工是大写的人而不是低级动物, 不为领导服务就没有人的真正价值. 而员工的最大价值在于全心全意为领导服务, 把一切奉献给领导.”</span><br/>
      <span>“活下去。无论洪水、瘟疫、饥荒、灾难, 还是连绵不绝、永不停息的战火, 都无法战胜生的顽强, 生命对死亡的优势.”——加西亚·马尔克斯</span><br/>
      <span>“一段旅程结束, 下一段又会开始. 有的人会再度相逢, 也有的人将不复再见. 还有人会在不知不觉间悄然离去, 或只是擦肩而过. 在同他们寒暄的时间里, 我觉得自己的心越来越澄澈. 凝望着奔流不息的河水, 我告诉自己：要活下去.”</span><br/>
      <span>“范堂主文正, 尝因业务繁忙, 无暇外出用餐, 乃备稀粥冻于冰箱, 待用膳之时, 取焉冰箱, 以刀画为六块, 每餐取其二就咸菜而食, 如此可终日于公司工作也; 杜香主少陵, 尝以单位停电之故, 电脑弗能开机, 无论画图, 乃使器具钻墙引线, 自楼道灯处取电, 方能通宵作图, 以保项目进度. ”——《凌烟阁序》</span><br/>
      <span>“一个不成熟的人的标志是他愿意为了上市而轰轰烈烈地死去, 而一个成熟的人的标志是他愿意为了上市而谦恭的活下去.”——J.D.赛林格</span><br/>
      <span>“上市工作是快乐时, 人生便是幸福; 上市工作是义务时, 人生便是苦役.”</span><br/>
      <span>“If I were dead and buried and I heard Leader's voice, beneath the sod my heart of dust would still rejoice.”——《Roman Holiday》</span><br/>
      <span>“积极工作, 勤于奉献, 随时准备为领导和公司的利益牺牲一切, 正是广大员工的铮铮誓言, 也是广大员工最高价值体现, 也是一种幸福。”</span><br/>
      <span>“上市以幽暗, 明之始也; 上市以牺牲, 善之始也; 上市以光明, 人之始也.”</span><br/>
      <span>“全公司上下紧紧围绕公司总领导人重要要求, 不断提升责任感紧迫感, 坚持眼睛向下、重心下移, 坚持把公司代表大会制度作为上市工作的基本方式, 坚持把管日志、管考勤的体制机制改革作为加强公司组织建设的突破口, 不断提升公司建设上市化水平.”</span><br/>
      <pre>
“如果把整个SCD大楼鱼缸的水倒出, 也浇不熄我对公司爱的火焰.
   整个鱼缸的水全部倒得出吗? 可以.
   所以, 是的. 我爱公司.”
      </pre>
      <span>“One of the penalties for refusing to participate in Listing is that you end up being governed by your inferiors.”——柏拉图</span><br/>
      <span>“要沉下心来干工作, 心无旁骛钻业务, 干一行、爱一行、精一行. 要信念如磐、意志如铁、勇往直前, 遇到挫折撑得住, 关键时刻顶得住, 抬得了龙雕, 换得了桌面, 浇得了花草.”</span><br/>
      <span>“回望初心, 展望新时代, 坚持以领导为中心、为领导谋幸福, 是员工舍我其谁的使命担当. 为领导服务是员工的天然责任、必然任务、唯一使命. 将为领导服务进行到底是员工存在的最高意义和永恒追求. 员工就是为领导服务而生的, 员工与为领导服务同在同行. 为领导服务永远在路上.”</span><br/>
      <span>“我们既要有钉钉子精神, 像老黄牛一样吃苦耐劳, 滴水穿石, 更要有滚石上山的耐力和韧劲, 持续发力, 久久为功, 还要有经历曲折磨难的充分准备, “岂畏其难其痛”, 愈挫愈勇, 百折不挠, 决不能因为困难而退缩.”</span><br/>
      <span>“新时代, 公司将不断增强规范性、模块性、平台性, 努力将每一个部门都建成一面旗帜, 将二十多位员工、六个多部门拧成一股绳, 心往一处想、力往一处使, 团结带领公司员工奋勇投身实现上市梦的伟大实践.”</span><br/>
      <span>“主动服务是积极主动、满怀热情的, 是即知即行、马上就办, 是挂在心头、夙兴夜寐、旰食宵衣的, 是不计得失的, 而不是消极被动、散漫拖拉、高高挂起, 更不是看价钱多少、看利益得失、看权力‘收益’、看亲疏远近的服务.”</span><br/>
      <span>“一是要做业务的明白人, 二是要做上市的开路人, 三是要做领导的贴心人, 四是要做部门的带头人.”</span><br/>
      <span>“愚公移山, 改变历史, 创造伟业。上市只会眷顾坚定者、奋进者、搏击者, 而不会等待犹豫者、懈怠者、畏难者。”</span><br/>
      <span>“制度, 就是一张写着员工权利的纸.”—— 列宁</span><br/>
      <pre>
“唯此世间, 善少恶多. 饮苦食毒, 未尝宁息.”——《佛说大乘无量寿庄严清净平等觉经》
 准备断食了?
      </pre>
      <span>“合抱之木, 生于毫末; 九层之台, 起于累土; 上市之行, 始于足下.”</span><br/>
      <span>“只有与同事同甘共苦、风雨同舟, 让不懈奋斗成为公司的最强音, 才能共建共享, 谱写公司上市的新篇章, 实现奋斗目标.”</span><br/>
      <span>“为项目立心, 为公司立命, 为上市继绝学, 为领导开太平.”</span><br/>
      <span>世上所有的路, 最终都是上市的路.</span><br/>
      <span>我司员工之间的所有相遇, 都是同上市的久别重逢.</span><br/>
      <pre>
“广大员工要这样做——
把爱岗奉献的热情转化为创造产值的不竭动力,
把科研成果应用在建设共产主义高新技术企业的伟大事业中,
把人生理想融入到实现公司全面崛起上市梦的不懈奋斗中.”
      </pre>
      <span>“强化公司的上市性建设, 必须大力抓严员工队伍建设。员工是公司的细胞.”</span><br/>
      <span>“我们一定要在全公司大力弘扬劳模精神、劳动精神, 大力宣传劳动模范和其他典型的先进事迹, 引导广大员工树立辛勤劳动、诚实劳动、创造性劳动的理念, 让劳动光荣、创造伟大成为铿锵的时代强音, 让劳动最光荣、劳动最崇高、劳动最伟大、劳动最美丽蔚然成风.”</span><br/>
      <span>“要广泛宣传表彰热爱公司回报公司、为公司上市事业作出突出贡献的优秀人才, 在广大员工中大力弘扬爱岗奉献精神.”</span><br/>
      <span>“我司广大员工要以时不我待的紧迫感、舍我其谁的责任感, 主动担当, 积极作为, 刻苦钻研, 勤奋工作, 为全面建成共产主义公司、建设上市事业作出更大贡献.”</span><br/>
      <span>“一个山头一个山头地攻, 一个难关一个难关地破.”</span><br/>
      <span>“员工不舒服一点、不自在一点, 领导的舒适度就好一点、满意度就高一点, 对员工的感觉就好一点.”</span><br/>
      <span>“当员工得整天装着问题、带着矛盾, 绷紧脑子里的那根弦, 轻飘飘、无所用心是当不好员工的, 心中无数、脑中无事是难以为员工的.”</span><br/>
      <span>“生命好在无意义, 才容得下各自赋予意义. 假如生命是有意义的, 这个意义却不合我的志趣, 那才尴尬狼狈.” —— 木心</span><br/>
      <span>“We celebrate today, because we go to work tomorrow; and we need to work hard, for there is work to be done.”</span><br/>
      <span>“勤奋就是勤勤恳恳, 不怕吃苦, 踏实工作。勤奋是通往上市的必由之路, 是成长成才的必备特质. 在我司走向强起来的新征程上, 公司员工必须始终保持人一之我十之、人十之我百之的工作干劲, 担起历史责任、共享伟大荣光.”</span><br/>
      <span>“坚韧就是在遭遇身体和精神压力时, 有坚持而不放弃的忍受力, 面对危险与灾难时有坚强的耐受力. 古之成大事者, 不惟有超世之才, 亦必有坚韧不拔之志。前进的道路上, 难免遭遇艰难坎坷, 一有困难就叫、一压担子就倒, 抓工作不能一抓到底, 长此以往, 事业没干成, 员工也成长不了.”</span><br/>
      <span>今天是用全时云会议APP召开公司代表大会的第一天, 这标志着公司代表大会从F2F(Face to Face)模式转变到V2V(Voice to Voice)模式, 从传统的在室内召开跃迁到托管到云上召开, 是开会领域的重大革命之一.</span><br/>
      <span>“奉献就是恭敬地交付、献出, 是不计报酬的给予. 在人生价值的天平上, 奉献是永远不变的砝码.‘春蚕到死丝方尽, 蜡炬成灰泪始干’, 就是奉献的最好诠释. 爱因斯坦说, ‘一个人的价值应当看他奉献了什么, 而不是取得了什么.’没有奉献精神的员工不是好员工.”</span><br/>
      <span>“责任是一种职责和任务, 是分内应该做的事. 通俗来讲, 就是承担应当承担的任务, 完成应当完成的使命, 做好应当做好的工作. 公司员工能力越大责任就越大, 职位越高责任就越重, 必须树立责任意识, 自觉知责担责履责, 做到工作有责、工作尽责、工作负责.”</span><br/>
      <span>“上市的意义不在于那个结果, 而在于享受那个过程.”</span><br/>
      <span>“上市不是看到了希望才去坚持, 而是坚持了才会看到希望.”</span><br/>
      <span>实现上市梦必须坚持走上市道路、弘扬上市精神、凝聚上市力量.</span><br/>
      <span>上市的磨难, 对于弱者是绊脚石; 对于强者, 则是攀登顶峰的垫脚石.</span><br/>
      <span>一切为了公司, 为了公司一切, 为了一切公司!</span><br/>
      <span>“有一些宝贵的东西作为目标时, 生活才有价值.” —— 黑格尔</span><br/>
      <span>公司上市越到紧要关头, 越要坚定必胜的信心, 越要有一鼓作气的决心, 尽锐出战、迎难而上.</span><br/>
      <span>公司的上市过程, 是一步一个脚印、一棒接着一棒往前走. 既要看到我们取得的辉煌成就, 更要看到前面的路还很长, 我们要继续努力地走下去!</span><br/>
      <span>求其上, 产值其中; 求其中, 产值其下; 求其下, 干不出产值.</span><br/>
      <span>“留在我身边的都是能吃苦的, 吃不了苦的我也不能让他留下.”</span><br/>
      <span>男女之情花前月下种种只是私情小爱, 是低俗的无聊的狭隘的; 为公司无私奉献奋勇拼搏才是人间大爱, 是崇高的永恒的广博的. 人与人可能始乱终弃生离死别, 但是上市的荣耀却坚如磐石万古常青.</span><br/>
      <span>设备是死的, 人是活的, 不要被动等着设备能配合你走向你, 而是要主动去适应设备.</span><br/>
      <span>“哪里有天才, 我是把公司蛀虫玩手机的工夫都用在干出产值上的.” —— 鲁迅</span><br/>
      <span>“居庙堂之高则忧公司, 处江湖之远则忧同事, 是进亦忧, 退亦忧. 然则何时而乐耶? 其必曰‘先领导之忧而忧, 后领导之乐而乐’乎. 噫! 微斯人, 吾谁与归?” —— 范仲淹</span><br/>
      <span>“There is no royal road to listing, and only those who do not dread the fatiguing climb of the steep paths have a chance of gaining its luminous summits.” —— 马克思</span><br/>
      <span>“这么大一个公司, 责任非常重、工作非常艰巨. 我将无我, 不负领导. 我愿意做到一个‘无我’的状态, 为公司的发展奉献自己.”</span><br/>
      <span>“无我”是一种大境界, 是不计得失、不谋私利, 是鞠躬尽瘁、无私奉献. 从“领导对公司上市的向往就是我们的奋斗目标”的拳拳之心, 到“为领导服务, 担当起该担当的责任”的铮铮之誓, 再到“我是领导的勤务员”的初心之诺, 无不蕴含着以身许领导许公司、报领导报公司的宏大境界.</span><br/>
      <script type="text/javascript">
         let i = 0
         $(window).scroll(function () {
            console.log('申帝, 我操你妈' + (i++) + '次!')
         })
      </script>
   </body>
</html>
```


效果:

![上市的希望.png](https://i.loli.net/2019/07/25/5d39061ac4ef939614.png)



`.scroll()`事件针对内容元素的例子:

```html
<!DOCTYPE html>
<html lang="en" dir="ltr">
   <head>
      <meta charset="utf-8">
      <script src="jquery-3.4.1.js" charset="utf-8"></script>
      <title></title>
      <style>
         div {
            /**
             * overflow: 内容超出容器宽度的时候如何如何...
             */
            overflow: auto;
            width: 150px;
            padding: 8px;
            height: 400px;
            /**
             * `float` 用于设置元素的浮动方式, 取值集合: {left, right, none}
             */
            float: left;
            display: block;
         }
         #div1 {
            color: red;
         }
         #div2 {
            color: blue;
         }
         #div3 {
            color: orange;
         }
         #div4 {
            color: magenta;
         }
         #div5 {
             color: cyan;
         }
      </style>
   </head>
   <body>
      <!-- div区域滚动的时候能出效果. -->
      <div id="div1">
         “苟利单位生死以, 岂因祸福避趋之.”
         “寄意寒星荃不察, 我以我血荐单位.”
         “干而不思则罔, 思而不干则殆.”
         “一个真正具有公司发展正史深刻意义的时刻－－一个公司员工的群星闪耀时刻出现以前, 必然会有漫长的岁月没有意义地流逝而去, 那些平时慢慢悠悠顺序发生和并列发生的事, 都压缩在这样一个决定一切的短暂时刻表现出来. 这一时刻对世世代代作出不可改变的决定, 它决定着一个公司的上市、一个单位的存续甚至整个行业的命运.”
         “孤单, 是一个人的开会; 开会, 是一群人的孤单.”
         “上市本身就是好的。有一天我们都会死去, 追求上市的道路还会有公司在走着. 死掉以后的事我看不到, 但在我活着的时候, 想到这件事, 心里就很高兴.”
         “个人再大的事儿也是小事儿, 公司再小的事儿也是大事儿.”
         “公司自成立以来, 就有埋头苦干的人, 有拼命硬干的人, 有殒身不恤的人, 有鞠躬尽瘁的人……虽是等于在我司上市历史进程中写入的所谓‘正史’, 也往往掩不住他们的光耀, 这就是公司的脊梁.”
         “博学之, 审问之, 慎思之, 明辨之, 笃行之.”
         “纵观公司上市历史长河, 危机时刻有幸担当维持公司产值大任的人们并非多数. 我不愿逃避责任——我乐于承担. 我不相信谁能避开现实. 我们为公司上市事业所尽的力量、忠诚和奉献将照亮这个公司和所有为之服务的人们——其光芒也将照亮整个行业. 所以, 我亲爱的同事, 不要问你的公司能为你做什么, 问你能为你的公司做什么; 我亲爱的同行和甲方, 不要问我司能为你做什么, 问我们大家能为我司的雄起做什么.”
         “凡事预则立, 不预则废.”
         “生, 亦我所欲也; 上市, 亦我所欲也. 二者不可得兼, 舍生而取上市者也.”
         人最宝贵的东西是生命, 生命属于人只有一次. 一个人的一生应该是这样度过的: 当他回首往事的时候, 他不会因为虚度年华而悔恨, 也不会因为碌碌无为而羞耻; 这样, 在临死的时候, 他就能够说:“我的整个生命和全部精力, 都已经献给世界上最壮丽的事业——为公司的上市而奋斗.”
         企业号发日志是平台内容的多样展示, 是工作内容的全面复盘, 是集体纪律的高度体现, 是公司上市的必要保证.一定要想方设法把日志发粗来.
         “大江歌罢掉头东, 邃密群科济世穷。面壁十年图破壁, 未能上市亦英雄.”
         “凡是领导作出的决策, 我们都坚决拥护; 凡是领导的指示, 我们都始终不渝地遵循.”
         “希望你有个美好的夜晚. 从公司的窗户望出去, 可以欣赏到日出的愉悦景象, 还有就寝前天空宁静的繁星.”
         中国古人说: “口言之, 身必行之.”实现公司上市, 需要每个员工脚踏实地拿出行动.
         公司广大员工要不忘初心、牢记使命, 以“上市不必在我”的精神境界和“上市必定有我”的历史担当, 保持历史耐心, 发扬具有公司特色的上市精神, 一条上市路走到底, 一任接着一任干.
         辛弃疾在一首词中写道:“乘风好去, 长空万里, 直下看山河.”上市梦是历史的、现实的, 也是未来的; 是我们这一代的, 更是下一代的.
         吾心信上市可行, 则移山填海之难, 终有成功之日; 吾心信上市不可行, 则反掌折枝之易, 亦无收效之期也.
         公司已经到了最危急的时候了, 现在这个行业大家日子都不好过. 每天拍良心想一想, 拍拍胸脯问问你自己, 你干出今天的产值了吗? 你干出的产值够不够每天在公司吃中午饭的饭钱? 你还好意思走那么早吗?
          “功以才成, 业由才广. 世上一切事物中公司是最可宝贵的, 一切上市成果都是公司实现的.”
          “孔子登东山而小鲁, 登泰山而小天下.” 面对行业大发展大变革大调整的新形势, 为更好推进公司上市进步事业, 我们必须登高望远, 正确认识和把握上市大势和行业潮流.
          “从实践到认识、从认识到实践, 实践、认识、再实践、再认识, 认识运动不断反复和无限发展, 这是公司上市认识运动的辩证发展过程, 也是公司上市认识运动的基本规律.”
          “潮平两岸阔, 风正一帆悬.” 新时代公司上市的航线已经明确, 公司全面崛起的巨轮正在乘风破浪前行.
          “行业里并不全是阳光和彩虹, 这是个十分卑鄙肮脏的地方. 我不管你有多狠, 但只要你允许, 公司的竞争对手会永久性地把你打得跪在地上起不来. 你、我、没有人, 能打得比竞争对手还重. 但重要的并不是你能打多重, 而是你能挨多重, 并且坚持促进公司上市. 你能承受多少并且推动公司上市, 这样才叫胜利!”
          工作时希望一生年少, 上市时希望瞬间变老.
          “广大员工要坚定理想信念, 志存高远, 脚踏实地, 勇做时代的弄潮儿, 在实现上市梦的生动实践中放飞个人梦想, 在为公司利益的不懈奋斗中书写人生华章!”
          上市从来都是九死一生, 但我们必须有“亦余心之所善兮, 虽九死其犹未悔”的豪情.
      </div>
      <div id="div2">
          孜孜不倦, 必能求索; 风尘仆仆, 终有归途.
          “九层之台, 起于累土. 要把公司上市这个蓝图变为现实, 必须不驰于空想、不鹜于虚声, 一步一个脚印, 踏踏实实干好工作.”
          “广大公司员工坚持爱岗奉献, 无怨无悔, 让我感到千千万万普通人最伟大, 同时让我感到上市都是奋斗出来的.”
          “每晚八点召开的晚间公司代表大会, 是工作日志的另类补充, 是工作方式的多维体现, 是工作时间的广博延展, 是工作内容的全面复盘, 是公司蓝图的高度前瞻, 是公司意志的深刻凝聚, 是公司纪律的丰富具象, 是公司上市的必要保障. 一定要身体力行、想方设法、不惜一切将公司代表大会制度贯彻到底、落地到位、推广到点.”
          “我们要以庆祝公司成立20周年为契机, 逢山开路, 遇水架桥, 将上市进行到底.”
          “积土而为山, 积水而为海.”幸福和美好的上市未来不会自己出现, 成功属于勇毅而笃行的人.
          “像蜜蜂一样勤劳工作才能享受蜜甜生活.”
          “对公司上市事业有功的人才配进入公司的凌烟阁; 公司上市路上的绊脚石们则当防备火狱, 那是用人和石做燃料的, 已为他们预备好了. 所有站在公司利益对立面的人都注定要被钉在公司门口的耻辱柱上, 这下场真恶劣!”
          “公司有什么精神？公司有特别能吃苦、特别能战斗、特别能攻关、特别能奉献的促进上市精神.”
          古今之成大公司、大事业者, 罔不经过三种之境界:“昨夜西风凋碧树, 独上单位, 望尽上市路.” 此第一境界也; “衣带渐宽终不悔, 上市消得人憔悴.” 此第二境界也; “众里寻它千百度, 蓦然回首, 上市正在灯火阑珊处.” 此第三境界也.
          “上市无王者之道.” —— 欧几里得
          “世间最真挚的爱莫过于对公司的爱.”——萧伯纳
          “一次次规范的公司项目, 使员工的个人觉悟、集体意识、纪律观念得到锤炼; 一次次高质量的代表大会, 使员工学习理论、交流业务、坚定上市的过程得到升华; 一次次制度化的流程建设, 使员工经常感受到领导的存在、公司的力量、部门的帮助.”
          “上市的盛宴已经摆在我们的面前, 现在唯一的问题是我们的胃口怎么样.”—— 林语堂
          “发领导愿, 结甲方缘, 享工作福; 择项目立, 寻公司住, 向上市行.”
      </div>
      <div id="div5">
          “新形势下, 公司的上市工作只能加强, 不能削弱; 只能改进提高, 不能停滞不前.”
          会而必议, 议而必行, 行而必决, 决而必果.
          “Three passions, simple but overwhelmingly strong, have governed my life: the longing for listing, the search of rise, and unbearable pity for the suffering of competitor.” —— 伯特兰·罗素

    “Be near me when I fade away,
       To point the term of company listing,
       And on the low dark verge of life,
       The twilight of eternal day.” —— 阿尔弗雷德·丁尼生

          "Years may wrinkle the skin, but to give up listing wrinkles the soul."

    “Made weak by time and competitor, but strong in will of listing.
        To strive, to seek, to find, and not to yield.” —— 阿尔弗雷德·丁尼生


    “丢了一个钉子, 坏了一只蹄铁;
     坏了一只蹄铁, 折了一匹战马;
     折了一匹战马, 伤了一位骑士;
     伤了一位骑士, 输了一场战斗;
     输了一场战斗, 亡了一个帝国.”
         ——《钉子与王国》
         天气炎热, 今天不报中午饭. 各位旁友在外注意饮食安全, 切勿饮用过凉饮品刺激肠胃, 避免吃坏肚子, 降低效率, 影响产值, 耽误上市.

          “大厨在炖芸豆里放了这么多猪皮, 虽然从形式上看不清真, 却也是让大家美容养颜, 提升公司形象, 拿下更多业务, 增加公司产值, 推动公司上市. 大家都在自己的岗位上默默耕耘, 为公司的上市事业添砖加瓦. 这就是到单位最需要的地方去、会什么干什么的公司服务器精神. 安拉胡阿克巴!”
          “现在, 我们提出觉悟上靠得住、工作上有本事、作风上过得硬、公司领导信得过等具体要求, 突出了好员工标准的时代内涵.”
          “上市是段光谱. 白里透黑。暗里有光. 少年才问黑白, 成年人只看几十度灰.”
      </div>
      <div id="div3">
          “一个人做好上市每一个阶段中应该做好的事情, 把领导让你做的事情尽可能地做到极致甚至像绿教徒那样对待自己喜欢的职业并愿意为此努力一生, 你就是一个具有使命感的人. 所谓工匠精神, 本质上与这种对领导的敬畏和使命感的理解与坚守密不可分. 工匠精神与功利主义无缘.”——《公司命运与个人命运》
          “今天的公司面对着前所未有的经济全球化的大环境、面对着如何成为创新性高新技术企业的重任, 只有我们每一个人、单位的每一位员工成为真正的人, 即成为具有学习能力、独立思考能力、自主选择能力、奉献能力、战胜困难能力和有使命感的人, 你自己的一生才会幸福, 我们这个公司才能不断进步, 公司上市才真的有希望.”——《公司命运与个人命运》
          “认真学习贯彻新时代公司特色上市主义思想, 自觉用科学上市理论武装头脑、指导实践、推动工作, 坚定公司特色上市主义道路自信、理论自信、制度自信、文化自信。”
          “公司领导高度重视公司代表大会筹备工作, 多次听取公司代表汇报, 对做好大会筹备工作作出明确指导, 为大会的召开和员工的工作指明了方向.”
          “以领导为本, 心系领导、心向领导, 了解领导所需所急所盼, 真心诚意服务领导。”
          “新时代呼唤新作为. 公司代表大会擘画的宏伟蓝图, 为员工工作发展带来了难得的机遇, 也对员工工作提出了更高的要求.”
          公司还有什么精神? 公司还有“春蚕到死丝方尽, 蜡炬成灰泪始干”“鞠躬尽瘁, 死而后已”“横眉冷对甲方指,俯首甘为公司牛”的奉献精神、“身先士卒先拔头筹一马当先”的测试电动车精神、“到公司最需要的地方去, 到项目最需要的地方去, 到上市最需要的地方去”的服务器精神、“战至最后一口气, 流尽最后一滴血, 打光最后一颗子弹”的笔记本精神。
          上市工作, 抓住的是当下, 传承的是根脉, 面向的是未来, 攸关公司前途命运。我们要有千钧重任在肩的神圣感使命感, 倾心倾情倾力为公司做好上市工作。
          “现在就能出来逛街的, 都是有钱人家里啥事儿都不用干的阔太太. 我们能做的, 就是多创造产值, 让公司早日上市, 使得公司里的每一个成员, 都能在工作日想逛就逛.”
          “从运行机理看, 为领导服务的内在动力来自价值实现的需要, 即员工是大写的人而不是低级动物, 不为领导服务就没有人的真正价值. 而员工的最大价值在于全心全意为领导服务, 把一切奉献给领导.”
          “活下去。无论洪水、瘟疫、饥荒、灾难, 还是连绵不绝、永不停息的战火, 都无法战胜生的顽强, 生命对死亡的优势.”——加西亚·马尔克斯
          “一段旅程结束, 下一段又会开始. 有的人会再度相逢, 也有的人将不复再见. 还有人会在不知不觉间悄然离去, 或只是擦肩而过. 在同他们寒暄的时间里, 我觉得自己的心越来越澄澈. 凝望着奔流不息的河水, 我告诉自己：要活下去.”
          “范堂主文正, 尝因业务繁忙, 无暇外出用餐, 乃备稀粥冻于冰箱, 待用膳之时, 取焉冰箱, 以刀画为六块, 每餐取其二就咸菜而食, 如此可终日于公司工作也; 杜香主少陵, 尝以单位停电之故, 电脑弗能开机, 无论画图, 乃使器具钻墙引线, 自楼道灯处取电, 方能通宵作图, 以保项目进度. ”——《凌烟阁序》
          “一个不成熟的人的标志是他愿意为了上市而轰轰烈烈地死去, 而一个成熟的人的标志是他愿意为了上市而谦恭的活下去.”——J.D.赛林格
          “上市工作是快乐时, 人生便是幸福; 上市工作是义务时, 人生便是苦役.”
          “If I were dead and buried and I heard Leader's voice, beneath the sod my heart of dust would still rejoice.”——《Roman Holiday》
          “积极工作, 勤于奉献, 随时准备为领导和公司的利益牺牲一切, 正是广大员工的铮铮誓言, 也是广大员工最高价值体现, 也是一种幸福。”
          “上市以幽暗, 明之始也; 上市以牺牲, 善之始也; 上市以光明, 人之始也.”
          “全公司上下紧紧围绕公司总领导人重要要求, 不断提升责任感紧迫感, 坚持眼睛向下、重心下移, 坚持把公司代表大会制度作为上市工作的基本方式, 坚持把管日志、管考勤的体制机制改革作为加强公司组织建设的突破口, 不断提升公司建设上市化水平.”

    “如果把整个SCD大楼鱼缸的水倒出, 也浇不熄我对公司爱的火焰.
       整个鱼缸的水全部倒得出吗? 可以.
       所以, 是的. 我爱公司.”

          “One of the penalties for refusing to participate in Listing is that you end up being governed by your inferiors.”——柏拉图
          “要沉下心来干工作, 心无旁骛钻业务, 干一行、爱一行、精一行. 要信念如磐、意志如铁、勇往直前, 遇到挫折撑得住, 关键时刻顶得住, 抬得了龙雕, 换得了桌面, 浇得了花草.”
          “回望初心, 展望新时代, 坚持以领导为中心、为领导谋幸福, 是员工舍我其谁的使命担当. 为领导服务是员工的天然责任、必然任务、唯一使命. 将为领导服务进行到底是员工存在的最高意义和永恒追求. 员工就是为领导服务而生的, 员工与为领导服务同在同行. 为领导服务永远在路上.”
          “我们既要有钉钉子精神, 像老黄牛一样吃苦耐劳, 滴水穿石, 更要有滚石上山的耐力和韧劲, 持续发力, 久久为功, 还要有经历曲折磨难的充分准备, “岂畏其难其痛”, 愈挫愈勇, 百折不挠, 决不能因为困难而退缩.”
          “新时代, 公司将不断增强规范性、模块性、平台性, 努力将每一个部门都建成一面旗帜, 将二十多位员工、六个多部门拧成一股绳, 心往一处想、力往一处使, 团结带领公司员工奋勇投身实现上市梦的伟大实践.”
          “主动服务是积极主动、满怀热情的, 是即知即行、马上就办, 是挂在心头、夙兴夜寐、旰食宵衣的, 是不计得失的, 而不是消极被动、散漫拖拉、高高挂起, 更不是看价钱多少、看利益得失、看权力‘收益’、看亲疏远近的服务.”
          “一是要做业务的明白人, 二是要做上市的开路人, 三是要做领导的贴心人, 四是要做部门的带头人.”
          “愚公移山, 改变历史, 创造伟业。上市只会眷顾坚定者、奋进者、搏击者, 而不会等待犹豫者、懈怠者、畏难者。”
          “制度, 就是一张写着员工权利的纸.”—— 列宁

    “唯此世间, 善少恶多. 饮苦食毒, 未尝宁息.”——《佛说大乘无量寿庄严清净平等觉经》
     准备断食了?

          “合抱之木, 生于毫末; 九层之台, 起于累土; 上市之行, 始于足下.”
          “只有与同事同甘共苦、风雨同舟, 让不懈奋斗成为公司的最强音, 才能共建共享, 谱写公司上市的新篇章, 实现奋斗目标.”
          “为项目立心, 为公司立命, 为上市继绝学, 为领导开太平.”
          世上所有的路, 最终都是上市的路.
          我司员工之间的所有相遇, 都是同上市的久别重逢.

    “广大员工要这样做——
    把爱岗奉献的热情转化为创造产值的不竭动力,
    把科研成果应用在建设共产主义高新技术企业的伟大事业中,
    把人生理想融入到实现公司全面崛起上市梦的不懈奋斗中.”

      </div>
      <div id="div4">
          “强化公司的上市性建设, 必须大力抓严员工队伍建设。员工是公司的细胞.”
          “我们一定要在全公司大力弘扬劳模精神、劳动精神, 大力宣传劳动模范和其他典型的先进事迹, 引导广大员工树立辛勤劳动、诚实劳动、创造性劳动的理念, 让劳动光荣、创造伟大成为铿锵的时代强音, 让劳动最光荣、劳动最崇高、劳动最伟大、劳动最美丽蔚然成风.”
          “要广泛宣传表彰热爱公司回报公司、为公司上市事业作出突出贡献的优秀人才, 在广大员工中大力弘扬爱岗奉献精神.”
          “我司广大员工要以时不我待的紧迫感、舍我其谁的责任感, 主动担当, 积极作为, 刻苦钻研, 勤奋工作, 为全面建成共产主义公司、建设上市事业作出更大贡献.”
          “一个山头一个山头地攻, 一个难关一个难关地破.”
          “员工不舒服一点、不自在一点, 领导的舒适度就好一点、满意度就高一点, 对员工的感觉就好一点.”
          “当员工得整天装着问题、带着矛盾, 绷紧脑子里的那根弦, 轻飘飘、无所用心是当不好员工的, 心中无数、脑中无事是难以为员工的.”
          “生命好在无意义, 才容得下各自赋予意义. 假如生命是有意义的, 这个意义却不合我的志趣, 那才尴尬狼狈.” —— 木心
          “We celebrate today, because we go to work tomorrow; and we need to work hard, for there is work to be done.”
          “勤奋就是勤勤恳恳, 不怕吃苦, 踏实工作。勤奋是通往上市的必由之路, 是成长成才的必备特质. 在我司走向强起来的新征程上, 公司员工必须始终保持人一之我十之、人十之我百之的工作干劲, 担起历史责任、共享伟大荣光.”
          “坚韧就是在遭遇身体和精神压力时, 有坚持而不放弃的忍受力, 面对危险与灾难时有坚强的耐受力. 古之成大事者, 不惟有超世之才, 亦必有坚韧不拔之志。前进的道路上, 难免遭遇艰难坎坷, 一有困难就叫、一压担子就倒, 抓工作不能一抓到底, 长此以往, 事业没干成, 员工也成长不了.”
          今天是用全时云会议APP召开公司代表大会的第一天, 这标志着公司代表大会从F2F(Face to Face)模式转变到V2V(Voice to Voice)模式, 从传统的在室内召开跃迁到托管到云上召开, 是开会领域的重大革命之一.
          “奉献就是恭敬地交付、献出, 是不计报酬的给予. 在人生价值的天平上, 奉献是永远不变的砝码.‘春蚕到死丝方尽, 蜡炬成灰泪始干’, 就是奉献的最好诠释. 爱因斯坦说, ‘一个人的价值应当看他奉献了什么, 而不是取得了什么.’没有奉献精神的员工不是好员工.”
          “责任是一种职责和任务, 是分内应该做的事. 通俗来讲, 就是承担应当承担的任务, 完成应当完成的使命, 做好应当做好的工作. 公司员工能力越大责任就越大, 职位越高责任就越重, 必须树立责任意识, 自觉知责担责履责, 做到工作有责、工作尽责、工作负责.”
          “上市的意义不在于那个结果, 而在于享受那个过程.”
          “上市不是看到了希望才去坚持, 而是坚持了才会看到希望.”
          实现上市梦必须坚持走上市道路、弘扬上市精神、凝聚上市力量.
          上市的磨难, 对于弱者是绊脚石; 对于强者, 则是攀登顶峰的垫脚石.
          一切为了公司, 为了公司一切, 为了一切公司!
          “有一些宝贵的东西作为目标时, 生活才有价值.” —— 黑格尔
          公司上市越到紧要关头, 越要坚定必胜的信心, 越要有一鼓作气的决心, 尽锐出战、迎难而上.
          公司的上市过程, 是一步一个脚印、一棒接着一棒往前走. 既要看到我们取得的辉煌成就, 更要看到前面的路还很长, 我们要继续努力地走下去!
          求其上, 产值其中; 求其中, 产值其下; 求其下, 干不出产值.
          “留在我身边的都是能吃苦的, 吃不了苦的我也不能让他留下.”
          男女之情花前月下种种只是私情小爱, 是低俗的无聊的狭隘的; 为公司无私奉献奋勇拼搏才是人间大爱, 是崇高的永恒的广博的. 人与人可能始乱终弃生离死别, 但是上市的荣耀却坚如磐石万古常青.
          设备是死的, 人是活的, 不要被动等着设备能配合你走向你, 而是要主动去适应设备.
          “哪里有天才, 我是把公司蛀虫玩手机的工夫都用在干出产值上的.” —— 鲁迅
          “居庙堂之高则忧公司, 处江湖之远则忧同事, 是进亦忧, 退亦忧. 然则何时而乐耶? 其必曰‘先领导之忧而忧, 后领导之乐而乐’乎. 噫! 微斯人, 吾谁与归?” —— 范仲淹
          “There is no royal road to listing, and only those who do not dread the fatiguing climb of the steep paths have a chance of gaining its luminous summits.” —— 马克思
          “这么大一个公司, 责任非常重、工作非常艰巨. 我将无我, 不负领导. 我愿意做到一个‘无我’的状态, 为公司的发展奉献自己.”
          “无我”是一种大境界, 是不计得失、不谋私利, 是鞠躬尽瘁、无私奉献. 从“领导对公司上市的向往就是我们的奋斗目标”的拳拳之心, 到“为领导服务, 担当起该担当的责任”的铮铮之誓, 再到“我是领导的勤务员”的初心之诺, 无不蕴含着以身许领导许公司、报领导报公司的宏大境界.
      </div>

      <script type="text/javascript">

         $(function () {
            let i = 1, j = 1, m = 1, n = 1
            $("#div1").scroll(function () {
               console.log('申畜, 我艹你妈' + (i++) + '次!')
            })
            $("#div2").scroll(function () {
               console.log('串犬, 我艹你妈' + (j++) + '次!')
            })
            $("#div3").scroll(function () {
               console.log('申畜, 我透你妈' + (m++) + '次!')
            })
            $("#div4").scroll(function () {
               console.log('串犬, 我透你妈' + (n++) + '次!')
            })
            $("#div5").scroll(function () {
               console.log('祝畐国早日倒闭.')
            })
         })

      </script>
   </body>
</html>
```

效果:

![scroll的另外例子.png](https://i.loli.net/2019/07/25/5d39180f7463e35996.png)

第二个例子主要是要弄出滚动条, 不然你直接在整个窗口滚也是触发不出来的. 


`.resize()`的例子:

```html
<!DOCTYPE html>
<html lang="en" dir="ltr">
    <head>
        <meta charset="utf-8">
        <script src="jquery-3.4.1.js" charset="utf-8"></script>
        <title>凌烟阁序</title>
    </head>
    <body>
        <pre>
会公司成立二十周年, 领导属意兴凌烟阁以志之, 亦可为领导行宫以利其料理公事, 乃有此序.
——题记

凌烟阁者, 兴建于六月, 告竣于七月, 工期凡一月有余. 其神且速, 堪为史上第八大奇迹. 是阁也, 雄踞滨都西南, 傲视东北; 凌立百合之巅, 睥睨天下. 与公司总坛、海景分舵互为掎角之势. 若得扩张, 日后定能包举宇内, 扬名四海. 远观之, 是阁常隐于云雾之中, 若仙居之所, 难见世间. 阁正门处有对联, 上联曰:“后乐先忧, 范文正庶几知道.” 下联曰:“昔闻今上, 杜少陵始可开工.” 分别出自综合部范文正“先领导之忧而忧, 后领导之乐而乐”与工程部杜少陵“昔闻凌水河, 今上凌烟阁”之典. 至于范文正与杜少陵之事迹, 后续将分解. 阁外百草园内有占星台, 可于此观星象, 上承天意, 下施号令, 以推上市.

入阁内, 则别有洞天: 鱼跃此时, 花开彼岸; 龙翔穹顶, 凤舞壁上; 木雕神器, 随处可见; 珍宝古玩, 不计其数. 逢领导召见蛮夷使节于龙榻之上, 满堂生辉, 王道气势充盈乾坤; 会领导大宴公司功臣于亭榭之下, 觥筹交错, 欢愉言笑绕梁三日. 阁中另有画框, 凡四六之数也, 盖为公司上市之时元老功臣绘像所备. 缘何至今无人像入框耶? 公司现有人数尚不足二十四数为其一; 君不闻“革命尚未成功, 同志仍需努力”乎? 当以劝勉加身, 而非居功自傲, 此乃其二也.

敝人昔时尝有公司要务系于身, 乃得入凌烟阁, 此乃我辈三生之幸也. 不然以吾之鄙薄操行, 微末贡献, 安能入圣地! 待尘埃落定, 万事停当之时, 当止有功臣准入也. 其时诸英贤可分列龙榻两侧, 禀告业务要事; 领导可阅奏章于榻上, 调兵遣将, 谋图霸业. 或于百草园烹羊宰牛, 歃血为盟, 斩妨碍上市之蛀虫两三献祭祖灵, 可求上天之佑. 上下齐心, 则上市可图也. 至于上市之绊脚石, 当钉于公司总坛旁耻辱柱上, 并永居火狱, 不得出耳. 若夫无利益公司之心, 无侍奉领导之意, 宜速卷铺盖而走, 以免自取其辱.

我司栋梁众多, 有自长兴海上来者, 有自内蒙草原来者, 有自白山黑水来者, 有自锦州山间来者. 来地众多, 不一一例举. 虽各人族姓相异, 然为谋求上市霸业, 而共聚一堂, 齐举大事. 范堂主文正, 尝因业务繁忙, 无暇外出用餐, 乃备稀粥冻于冰箱, 待用膳之时, 取焉冰箱, 以刀画为六块，每餐取其二就咸菜而食, 如此可终日于公司工作也; 杜香主少陵, 尝以单位停电之故, 电脑弗能开机, 无论画图, 乃使器具钻墙引线, 自楼道灯处取电, 方能通宵作图, 以保项目进度. 筚路蓝缕, 栉风沐雨, 概莫如此. 前贤为公司百年大计, 呕心沥血, 前仆后继, 鞠躬尽瘁, 殒身不恤, 不求回报. 此乃吾人之表率也, 后来者亦当师法先人. 先贤虽湮没于公司正史之烟海, 然诸人之气魄风骨, 弗能折损半分丝毫也: “寄意寒星荃不察, 我以我血荐公司”“横眉冷对甲方指, 俯首甘为公司牛”“苟利领导生死以, 岂因祸福避趋之”“想领导之所想, 急领导之所急”“面壁十年图破壁，未能上市亦英雄”“上市不必在我, 上市必定有我” 时至今日, 读来亦使人感佩莫名, 崇敬颇多. 吾人当以诸贤为万世师也.

噫! 天色已晚, 行当搁笔. 公司总坛正门口有沉香木匾者一, 上书之文今录于此, 以之作结, 并与后人共勉:

发领导愿
结甲方缘
享工作福
择项目立
寻公司住
向上市行
        </pre>
        <script type="text/javascript">
            $(window).resize(function () {
                alert("坐等申帝痛斥东北经济环境恶劣怒骂人心不古忘恩负义.")
            })
        </script>
    </body>
</html>
```


效果:

![resize.png](https://i.loli.net/2019/07/25/5d391b2c96be875974.png)


### [文档加载事件](https://api.jquery.com/category/events/document-loading/)

视频中说的 `ready` 和 `load` 事件:

* `ready`: `ready` 事件在 DOM 结构绘制完成之后就会执行, 这样能确保就算有大量的媒体文件没加载出来, JavaScript 代码一样可以执行.
* `load`: `load` 事件必须等到网页中所有内容全部加载完毕之后才被执行. 如果一个网页中有大量的图片的话, 就会出现这种情况: 网页文档已经呈现出来, 但由于网页数据还没有完全加载完毕, 导致 `load` 事件不能够即时触发. 就是说, 要等到网页文档以及图片等数据全部加载完毕之后 `load` 事件才会被触发.

jQuery 中到 jQuery 3 的时候还活着的文档加载事件还有三个. 

* `$.holdReady()`
* `$.ready`
* ~~`.load()`~~: 在 jQuery 1.8中被弃用, 在 jQuery 3.0 中被移除.
* `.ready()`
* ~~`.unload()`~~: 在 jQuery 1.8中被弃用, 在 jQuery 3.0 中被移除.


关于`.ready()`的用法举例:


```html
<!DOCTYPE html>
<html lang="en" dir="ltr">
    <head>
        <meta charset="utf-8">
        <script src="jquery-3.4.1.js" charset="utf-8"></script>
        <title>验证码</title>
    </head>
    <body>
        <img src="https://upload.cc/i1/2019/07/25/Acdwf8.png" />
        <img src="https://upload.cc/i1/2019/07/25/sV3HKU.png" alt="">
        <img src="https://upload.cc/i1/2019/07/25/v0guko.png" alt="">
        <img src="https://upload.cc/i1/2019/07/25/I5Okeh.png" alt="">
        <img src="https://upload.cc/i1/2019/07/25/9lcaIW.png" alt="">
        <img src="https://upload.cc/i1/2019/07/25/GJnBCF.png" alt="">
        <script type="text/javascript">
            // 写法1.
            $().ready(function () {
                alert('申帝我艹你妈个大血逼三千次.')
            })

            // 写法2, 可读性比较好.
            $(document).ready(function () {
                alert('孽畜不得好死.')
            })

            // 写法3, 创造产值的时候比较常用.
            $(function () {
                alert('串犬早日爆炸.')
            })
        </script>
    </body>
</html>

```

其中验证码图片由TP3框架生成.


效果:

![](https://upload.cc/i1/2019/07/25/jh42rC.png)


关于 `.load()`和 `.unload()` 在 jQ 3 中被移除了怎么办的问题, 可以看 [jQuery : replacement for deprecated “.load()”?](https://stackoverflow.com/questions/37817448/jquery-replacement-for-deprecated-load)、[load() method deprecated?](https://stackoverflow.com/questions/12643160/load-method-deprecated) 还有 [What is a foolproof alternative to $(window).unload()?](https://stackoverflow.com/questions/46443032/what-is-a-foolproof-alternative-to-window-unload)

在 jQ 官博中, 3.0更新调整详情 [jQuery 3.0 Final Released!](https://blog.jquery.com/2016/06/09/jquery-3-0-final-released/) 里说了:

> Removed deprecated event aliases
> 
> `.load`, `.unload`, and `.error`, deprecated since jQuery 1.8, are no more. Use `.on()` to register listeners.
> 
> [https://github.com/jquery/jquery/issues/2286](https://github.com/jquery/jquery/issues/2286)

也就是参考上面的浏览器事件中的 `.error()` 那么改.

#### 文档加载过程


1. 解析HTML结构.
2. 加载外部脚本和样式表文件.
3. 解析并执行脚本代码.
4. 构造HTML DOM模型. // ready
5. 加载图片等外部文件.
6. 页面加载完毕. // load


### [事件处理器绑定](https://api.jquery.com/category/events/event-handler-attachment/)


从官网上的分类来看, 这个东西也给归到事件里了. 叫 Event Handler Attachment.


官网文档上有以下方法, 也是有一堆被钉在耻辱柱上的和被踢出上市队伍的:

* `.bind()`: 在 jQuery 3.0 中被弃用.
* `.delegate()`: 在 jQuery 3.0 中被弃用.
* `.die()`: 在 jQuery 1.7 中被弃用, 在 jQuery 1.9 中被移除. 这个撤得倒是挺果断, 估计是这个方法名不吉利.
* `$.proxy()`
* `.live()`: 在 jQuery 1.7 中被弃用, 在 jQuery 1.9 中被移除.
* `.off()`
* `.on()`
* `.one()`
* `.trigger()`
* `.triggerHandler()`
* `.unbind()`: 在 jQuery 3.0 中被弃用.
* `.undelegate()`: 在 jQuery 3.0 中被弃用.


主要是 `delegate` 这种理念我现在理解起来有些费事儿, 坦承是自己功夫没下到也没什么丢人的, 总比说天赋不行强. 


这里我们在视频里会看:

1. `.bind()`: 在 jQuery 3.0 中被弃用. 官方推荐用`.on()`来摆平.
2. `.delegate()`: 在 jQuery 3.0 中被弃用.
3. `.off()`:
4. `.on()`
5. `.one()`
6. `.unbind()`: 在 jQuery 3.0 中被弃用.
7. `.undelegate()`: 在 jQuery 3.0 中被弃用.


#### [.bind()](https://api.jquery.com/bind/)

来看一下jQuery 2.2.1时候的`.bind()`的例子:


```html
<!DOCTYPE html>
<html lang="en" dir="ltr">
    <head>
        <meta charset="utf-8">
        <title>.bind()方法</title>
        <script src="jquery-3.4.1.js" charset="utf-8"></script>
    </head>
    <body>
        <button id="btn1">
            申畜我操你妈!
        </button>
        <br/>
        <button id="btn2">
            串犬我操你妈!
        </button>
        <script type="text/javascript">
            // 有第三个参数是防止冒泡的方法签名, 参考: https://api.jquery.com/bind/#bind-eventType-eventData-preventBubble. 默认是true.
            $(function () {
                $("#btn1").bind("click", function () {
                    alert('申畜你妈炸了.')
                })
                // `.bind()`不是在jQuery 3.0中被弃用了嘛, 这个是替代方法.
                $("#btn2").on("click", function () {
                    alert('串犬你妈炸了.')
                })
            })
        </script>
    </body>
</html>
```

效果:

![bind.png](https://i.loli.net/2019/07/26/5d3a6aa3b1ea687499.png)


`.bind()`是可以同时绑定两个事件的, 这里我们用 `.on()` 来写一个例子:

```html
<!DOCTYPE html>
<html lang="en" dir="ltr">
    <head>
        <meta charset="utf-8">
        <title>.bind()两个事件</title>
        <script src="jquery-3.4.1.js" charset="utf-8"></script>
        <style>
            div {
                width: 200px;
                height: 120px;
                border: solid;
            }
        </style>
    </head>
    <body>
        <div>
            <p>右妃的X.</p>
        </div>
        <script type="text/javascript">
            // .bind也可以一下绑定两个事件.
            $(function () {
                $("div").on({
                    mousemove: function () {
                        $(this).css("color", "red")
                        console.log('申帝在SCD大楼306默默耕耘着右妃的花径.')
                    },
                    mouseleave: function () {
                        alert('申帝心满意足地把龙根从右妃的下体缓缓抽出.')
                    }
                })
            })
        </script>
    </body>
</html>

```


效果:

![bind两个事件.png](https://i.loli.net/2019/07/26/5d3a723285d1f52889.png)


下面再打开某度的首页, 鼠标指针在某度一下晃一晃它会变色, 我们来模仿一下这个效果:

```html
<!DOCTYPE html>
<html lang="en" dir="ltr">
    <head>
        <meta charset="utf-8">
        <title>模仿某度首页的按钮效果</title>
        <script src="jquery-3.4.1.js" charset="utf-8"></script>
        <style>
            p {
                width: 150px;
                height: 50px;
                background-color: DodgerBlue; /* 这个是相对深一点的那个蓝色. */ 
                border-radius: 5px;
                text-align: center;
                line-height: 50px;
                margin: 0 auto;
                color: #ffffff;
                font-size: 16px;
            }
            .p-btn {
                background-color: DeepSkyBlue; /* 这个是相对浅一点的那个蓝色. */
            }
        </style>
    </head>
    <body>
        <p>模仿某度首页按钮</p>
        <script type="text/javascript">
            $(function () {
                $("p").on({
                    mouseover: function () {
                        $(this).addClass("p-btn")
                    },
                    mouseout: function () {
                        $(this).removeClass("p-btn")
                    }
                })
            })
        </script>
    </body>
</html>

```


效果:

![某度button效果.png](https://i.loli.net/2019/07/26/5d3a87286ad9546179.png)


用`.toggleClass()`代替刚才的 `.addClass()` + `.removeClass()`:


```html
<!DOCTYPE html>
<html lang="en" dir="ltr">
    <head>
        <meta charset="utf-8">
        <title>.toggleClass()方法实现效果</title>
        <script src="jquery-3.4.1.js" charset="utf-8"></script>
        <style>
            p {
                width: 150px;
                height: 50px;
                background-color: DodgerBlue; /* 这个是相对深一点的那个蓝色. */
                border-radius: 5px;
                text-align: center;
                line-height: 50px;
                margin: 0 auto;
                color: #ffffff;
                font-size: 16px;
            }
            .p-btn {
                background-color: DeepSkyBlue; /* 这个是相对浅一点的那个蓝色. */
            }
        </style>
    </head>
    <body>
        <!-- 实现鼠标指针移到上面和移出颜色发生改变. -->
        <p>某度一下</p>
        <script type="text/javascript">
            $("p").on("mouseover mouseout", function () {
                // `.toggleClass()`: 在匹配的元素集合中的每个元素上, 添加或删除一个或多个样式类, 取决于这个样式类是否存在或(视频原话: 值切换属性)(翻译: 状态参数的值).

                // 听这只小姐姐说得好费事儿, 我看英文吧:  Add or remove one or more classes from each element in the set of matched elements, depending on either the class's presence or the value of the state argument.

                $(this).toggleClass("p-btn")
                // 说白了就是检测到<p>标签, 如果有这个类名, 就把它删掉, 如果没有就把它添加上.
            })
        </script>
    </body>
</html>
```

效果:

![toggleclass.png](https://i.loli.net/2019/07/26/5d3a962dc579738972.png)


#### [.delegate()](https://api.jquery.com/delegate/)


说白了 `.delegate()` 就是一个事件委托. 但是我对 delegate 这种东西也不是特别理解.

不知道啥情况就先看官网, 官网上的描述是这样: Attach a handler to one or more events for all elements that match the selector, now or in the future, based on a specific set of root elements.


再就 `.delegate()` 在 jQuery 3.0 中已经被踢出上市队伍了. 不知道啥时候会凉凉. 推荐的是用 `.on()` 来代替.


就 `.delegate()` 本身而言, 可以用在 `<ul>` + `<li>` 这种地方. 


举例:

```html
<!DOCTYPE html>
<html lang="en" dir="ltr">
    <head>
        <meta charset="utf-8">
        <title>.delegate()</title>
        <script src="jquery-3.4.1.js" charset="utf-8"></script>
        <style>
            ul li {
                border: solid;
                width: 80px;
                margin: 5px;
                border-color: green;
            }
            ol li {
                border: dotted;
                width: 80px;
                margin: 5px;
                border-color: blue;
            }
        </style>
    </head>
    <body>
        <ul>
            <li>申帝</li>
            <li>串相</li>
            <li>右妃</li>
            <li>木贵人</li>
        </ul>
        <ol>
            <li>丶贵人</li>
            <li>艹帅</li>
            <li>㐅大将</li>
            <li>厶将军</li>
        </ol>
        <script type="text/javascript">
            $(function () {
                $("ul").delegate("li", "click", function () {
                    alert($(this).html())
                })
                $("ol").on("mouseover", "li", function () {
                    alert($(this).html())
                })
            })
        </script>
    </body>
</html>
```

效果:

![delegate().png](https://i.loli.net/2019/07/26/5d3aa183c7f8096996.png)



#### [.on()](https://api.jquery.com/on/)


`.on()`: 视频教程里说的是“在选定的元素上绑定一个或多个处理函数.” 而官网上说的是:

> Attach an event handler function for one or more events to the selected elements.


差得还是不小的...

举个 `.on()` 的例子, 虽然可能之前弄过了:


```html
<!DOCTYPE html>
<html lang="en" dir="ltr">
    <head>
        <meta charset="utf-8">
        <title></title>
        <script src="jquery-3.4.1.js" charset="utf-8"></script>
    </head>
    <body>
        <button id="btn">广大社会友人对申帝美好的祝愿</button>
        <script type="text/javascript">
            $(function () {
                $("#btn").on("click", function () {
                    alert('申帝我操你妈!')
                })
            })
        </script>
    </body>
</html>

```

效果:

![on.png](https://i.loli.net/2019/07/26/5d3aa5a89c65f53472.png)

之前几个被钉到耻辱柱乃至退出上市历史舞台的方法我都拿 `.on()` 重写了, 可以参考一下.


#### [.off()](https://api.jquery.com/off/#off-events-selector)

描述: Remove an event handler. 

这个方法的解读还是值得看看的.


The `.off()` method removes event handlers that were attached with <a href="https://api.jquery.com/on/"><code>.on()</code></a>. See the discussion of delegated and directly bound events on that page for more information. Calling `.off()` with no arguments removes all handlers attached to the elements. Specific event handlers can be removed on elements by providing combinations of event names, namespaces, selectors, or handler function names. **When multiple filtering arguments are given, all of the arguments provided must match for the event handler to be removed.**


看个 `.off()` 移除的例子.

```html
<!DOCTYPE html>
<html lang="en" dir="ltr">
    <head>
        <meta charset="utf-8">
        <title>.off()方法</title>
        <script src="jquery-3.4.1.js" charset="utf-8"></script>
        <style>
            li {
                width: 80px;
                border: blue dotted;
                border-radius: 5px;
                margin: 8px;
            }
        </style>
    </head>
    <body>
        <ul>
            <li>申帝</li>
            <li>串相</li>
        </ul>
        <script type="text/javascript">
            $(function () {
                // 之前没研究过JavaScript的闭包传参, 都是照PHP的闭包脑补的. 我真是太他妈天才了!
                callback = function (foo) {
                    foo = $(this).html() // 注意上一行的foo的位置应该类似一个形参, 你不传 foo 而是直接传 $(this).html() 会炸.
                    alert(foo + ', 我操你妈!')
                }
                $("ul").on("mouseover click", "li", callback)

                // `.off()` 方法不传参的话, 会移除相应的 `.on()` 上去的所有事件处理器.
                $("ul").off("mouseover", "li", callback)

            })
        </script>
    </body>
</html>

```

效果: 

![offdemo.png](https://i.loli.net/2019/07/26/5d3abcc130dc231007.png)


#### [.one()](https://api.jquery.com/one/)


描述: 为元素的事件添加处理函数, 处理函数在每个事件上每种事件类型最多执行一次. 


Attach a handler to an event for the elements. The handler is executed at most once per element per event type.

`.one()` 方法一般常在引导页应用.


```html
<!DOCTYPE html>
<html lang="en" dir="ltr">
    <head>
        <meta charset="utf-8">
        <title>.delegate()</title>
        <script src="jquery-3.4.1.js" charset="utf-8"></script>
        <style>
            p {
                border: solid;
                width: 80px;
                margin: 5px;
                border-color: green;
            }
        </style>
    </head>
    <body>
        <!-- 实现: 每一个 <p> 标签点击第一次的时候会有弹窗. 关闭弹窗之后再点就不再有弹窗了. -->
        <p>申畜</p>
        <p>串犬</p>
        <script type="text/javascript">
            $(function () {
                $("p").one("click", function () {
                    alert($(this).html() + ', 我操你妈!')
                })
            })
        </script>
    </body>
</html>
```


#### [.unbind()](https://api.jquery.com/unbind/) 和 [.undelegate()](https://api.jquery.com/undelegate/)

也是两个在 jQ 3 中被钉在耻辱柱上的方法. 参考[`.bind()`](https://api.jquery.com/unbind/) 和 [`.delegate()`](https://api.jquery.com/undelegate/). 放在现在这个时代, 应当使用 [`.off()`](https://api.jquery.com/off/) 来代替 `.bind()` 和 `.delegate()` 的使用.


### [事件对象](https://api.jquery.com/category/events/event-object/)


视频里主要讲了以下几个内容:

1. [event.currentTarget](https://api.jquery.com/event.currentTarget/)
2. [event.target](https://api.jquery.com/event.target/)
3. [event.delegateTarget](https://api.jquery.com/event.delegateTarget/)
4. [event.pageX](https://api.jquery.com/event.pageX/)
5. [event.pageY](https://api.jquery.com/event.pageY/)
6. [event.type](https://api.jquery.com/event.type/)
7. [event.preventDefault()](https://api.jquery.com/event.preventDefault/)
8. [event.stopPropagation()](https://api.jquery.com/event.stopPropagation/)


看一下 propagate 这个词是什么意思:

propagate [ˈprɒpəgeɪt]

1. v. 宣传; 传播; 使普及
   If people propagate an idea or piece of information, they spread it and try to make people believe it or support it.
   * They propagated political doctrines which promised to tear apart the fabric of British society. 
     他们鼓吹能颠覆英国社会结构的政治学说。
2. v. 繁殖，培植（植物）
   If you propagate plants, you grow more of them from the original ones.
   * The easiest way to propagate a vine is to take hardwood cuttings... 
     栽培葡萄最简便的方法就是硬条扦插。
   * The pasque flower can be propagated from seed. 
     欧白头翁可以通过种子进行繁殖。


关于事件代理可以看看: [Understanding Event Delegation](https://learn.jquery.com/events/event-delegation/). 这个一直是我个人的弱项, 需要认真理解一下.



#### [event.currentTarget](https://api.jquery.com/event.currentTarget/)

描述: The current DOM element within the event bubbling phase.

`event.currentTarget` 指向的永远都是事件的监听者.


#### [event.target](https://api.jquery.com/event.target/)

描述: The DOM element that initiated the event.


先看一下 `event.currentTarget` 和 `event.target` 的例子:


```html
<!DOCTYPE html>
<html lang="en" dir="ltr">
    <head>
        <meta charset="utf-8">
        <title></title>
        <script src="jquery-3.4.1.js" charset="utf-8"></script>
    </head>
    <body>
        <div>
            <p>请点击这段文本并在控制台中观察现象: 申帝我操你妈!</p>
        </div>
        <script>
            $(function () {
                $("div").on("click", function (event) {
                    console.log($(event.currentTarget)) // 结果: div, 事件的监听者
                    console.log($(event.target)) // 结果: p, 事件的目标
                    console.log($(this)) // 结果: div
                })
            })
        </script>
    </body>
</html>
```



效果:


![currentTarget-vs-target-vs-this.png](https://i.loli.net/2019/07/29/5d3e853d5706b27292.png)

可以看到, 第 15 行: `console.log($(event.currentTarget))` 打印的是 `<div>`; 第 16 行 `console.log($(event.target))` 打印的是 `<p>` 标签; 第 17 行 `console.log($(event.target))` 打印的是 `<div>`.


#### [event.delegateTarget](https://api.jquery.com/event.delegateTarget/)

描述: The element where the currently-called jQuery event handler was attached. 

绑定了当前正在处理 jQuery 事件处理器的元素. 就是说 `event.delegateTarget` 表示的是当前事件的委托者.

举个 `event.delegateTarget` 的例子:


```html
<!DOCTYPE html>
<html lang="en" dir="ltr">
    <head>
        <meta charset="utf-8">
        <title></title>
        <script src="jquery-3.4.1.js" charset="utf-8"></script>
    </head>
    <body>
        <div>
            <p>请点击这段文本并在控制台中观察现象: 串相我操你妈!</p>
        </div>
        <script>
            $(function () {
                $("div").on("click", "p", function (event) {
                    console.log($(this).html())
                    console.log($(event.delegateTarget))
                    $(event.delegateTarget).css({
                        'border': '1px solid red',
                        'border-width': '2px',
                        'width': '400px'
                    })
                })
            })
        </script>
    </body>
</html>
```


以前确实不怎么用 JavaScript 和 CSS, 都是写了看到问题了才能想到可能要怎么怎么改, 这里提几个我需要注意的点:

* 像 `.css()` 方法这样传多组值的时候用 JSON 传.
* `border-width` 是边框的线的宽度.
* `width` 才是边框本体的宽度.


效果:

![delegateTarget.png](https://i.loli.net/2019/07/29/5d3e8bf37568a54223.png)





#### [event.pageX](https://api.jquery.com/event.pageX/)

描述: The mouse position relative to the left edge of the document.

鼠标相对于文档的左边沿的位置.


#### [event.pageY](https://api.jquery.com/event.pageY/)

描述: The mouse position relative to the top edge of the document.

鼠标相对于文档的上边沿的位置.


举个 `event.pageX` 和 `event.pageY` 的例子:


```html
<!DOCTYPE html>
<html lang="en" dir="ltr">
    <head>
        <meta charset="utf-8">
        <title></title>
        <script src="jquery-3.4.1.js" charset="utf-8"></script>
        <style>
            div {
                width: 240px;
                height: 90px;
                background-color: green;
            }
        </style>
    </head>
    <body>
        <!-- 实现鼠标在区域内移动时, 在后台能够打印出鼠标的相对于上边沿和左边沿的位置. -->
        <div>
            <p>申畜我透你妈!</p>
            <p>串犬我透你妈!</p>
        </div>
        <script>
            $(function () {
                $("div").on("mousemove", function (event) {
                    console.log("pageX: " + event.pageX + ", pageY: " + event.pageY)
                })
            })
        </script>
    </body>
</html>

```


效果:

![pageXpageY.png](https://i.loli.net/2019/07/29/5d3e94864d5fd56831.png)


#### [event.type](https://api.jquery.com/event.type/)

描述: Describes the nature of the event. 

获取当前的事件类型.


举个 `event.type` 的例子:

```html
<!DOCTYPE html>
<html lang="en" dir="ltr">
    <head>
        <meta charset="utf-8">
        <title></title>
        <script src="jquery-3.4.1.js" charset="utf-8"></script>
        <style>
            p {
                width: 120px;
                height: 40px;
                border: 1px solid red;
                margin: 20px;
            }
            div {
                width: 150px;
                border: 1px solid green;
                margin-left: 30px;
            }
        </style>
    </head>
    <body>
        <p>申畜我操你妈!</p>
        <div>
            <span>串犬我操你妈!</span>
        </div>
        <script>
            $(function () {
                $("p").on("click", function (event) {
                    alert(event.type)
                })
                $("div").on("mouseover", function (event) {
                    alert(event.type)
                })
            })
        </script>
    </body>
</html>

```



效果:

![event.type.png](https://i.loli.net/2019/07/29/5d3e95b84089a46293.png)

注意: 就算改成 `$("span").on("mouseover", function (event) {...}` 也会触发 `mouseover` 事件.

#### [event.preventDefault()](https://api.jquery.com/event.preventDefault/)


描述: If this method is called, the default action of the event will not be triggered.


阻止默认事件.


看一下 `event.preventDefault()` 的一个例子:

```html
<!DOCTYPE html>
<html lang="en" dir="ltr">
    <head>
        <meta charset="utf-8">
        <title></title>
        <script src="jquery-3.4.1.js" charset="utf-8"></script>
        <style>
            /* 默认会显示 :visited 的样式. 我也不知道是咋回事儿. */
            a:visited {
                color: blue;
            }
        </style>
    </head>
    <body>
        <!-- 阻止<a>标签点击时跳转到指定链接. -->
        <a href="https://www.google.com/">谷歌一下, 你就知道得太多了.</a>
        <script>
            $(function () {
                $("a").click(function (event) {
                    event.preventDefault()
                    alert('您好, 您要访问的页面已被河蟹.')
                })
            })
        </script>
    </body>
</html>

```

效果:

![preventDefault.png](https://i.loli.net/2019/07/29/5d3e996e5a53364165.png)



#### [event.stopPropagation()](https://api.jquery.com/event.stopPropagation/)


描述: Prevents the event from bubbling up the DOM tree, preventing any parent handlers from being notified of the event.

阻止冒泡事件.

举个 `event.stopPropagation()` 的例子:


```html
<!DOCTYPE html>
<html lang="en" dir="ltr">
    <head>
        <meta charset="utf-8">
        <title>日常</title>
        <script src="jquery-3.4.1.js" charset="utf-8"></script>
        <style>
            .outer-div {
                background-color: green;
                width: 240px;
                height: 160px;
            }
            .inner-div {
                background-color: Cyan;
                position: absolute;
                width: 180px;
                height: 80px;
                padding: 10px;
                margin-top: 30px;
                margin-left: 20px;
            }
            p {
                background-color: orange;
                border-radius: 4px;
            }
            span {
                background-color: GreenYellow;
                border-radius: 4px;
            }
            a:visited {
                color: blue;
            }
        </style>
    </head>
    <body>
        <div class="outer-div">
            <div class="inner-div">
                <p>串相我操你妈!</p>
                <span>申帝我透你妈!</span>
            </div>
        </div>
        <script type="text/javascript">
            $("p").click(function (event) {
                event.stopPropagation()
                alert($(this).html())
            })
            $("span").click(function () {
                alert($(this).html())
            })
            $(".inner-div").click(function () {
                alert('串犬我透你妈!')
            })
            $(".outer-div").click(function () {
                alert('申畜我操你妈!')
            })
        </script>
    </body>
</html>
```

这个比较微妙, 点击不同区域这种效果不太好弄, 不太好放例子, 就不放了. 要看的话自己跑一下便是.


主要是看元素的定位. 你要是想设个相对父级元素的位置的话, 你得给 `position` 这个 property 的值设个 `absolute` 或是 `fixed`. 定位的缺省值是 `static`.



### [表单事件](https://api.jquery.com/category/events/form-events/)


在官网上发布了这些方法:


* `.blur()`
* `.change()`
* `.focus()`
* `.focusin()`
* `.focusout()`
* `.select()`
* `.submit()`


不过我们在视频里只看这些:



1. [.focus()](https://api.jquery.com/focus/)
2. [.blur()](https://api.jquery.com/blur/)
3. [.change()](https://api.jquery.com/change/)
4. [.select()](https://api.jquery.com/select/)
5. [.submit()](https://api.jquery.com/submit/)



#### [.focus()](https://api.jquery.com/focus/) 与 [.blur()](https://api.jquery.com/blur/)


[.focus()](https://api.jquery.com/focus/) 描述: Bind an event handler to the "focus" JavaScript event, or trigger that event on an element.



[.blur()](https://api.jquery.com/blur/) 描述: Bind an event handler to the "blur" JavaScript event, or trigger that event on an element.


这俩方法分别说的是获得焦点和失去焦点.

来个 `.blur()` 和 `.focus()` 的例子:

```html
<!DOCTYPE html>
<html lang="en" dir="ltr">
    <head>
        <meta charset="utf-8">
        <title></title>
        <script src="jquery-3.4.1.js" charset="utf-8"></script>
    </head>
    <body>
        <form action="">
            <input id="target" type="text" value="申帝我草拟吗!"><br/>
            <input type="text" value="串相我操你妈!"><br/>
            <input class="test" type="text" value="申帝你妈炸了."><br/>
        </form>
        <script type="text/javascript">
            $(function () {
                // `.blur()` 失去焦点和 `.focus()` 获得焦点适用于所有的元素, 不单单是表单元素.
                $("#target").blur(function () {
                    alert("右妃在申帝身下娇喘得失去了焦点.")
                })
            })
            $(function () {
                $(".test").focus(function () {
                    console.log("右妖女获得了申暴君的临幸, 便也获得了焦点.")
                })
            })
        </script>
    </body>
</html>

```


效果:


![focus-and-blur.png](https://i.loli.net/2019/07/30/5d3f9d3dbd0fc95545.png)


#### [.change()](https://api.jquery.com/change/)

描述: Bind an event handler to the "change" JavaScript event, or trigger that event on an element.

注意: This event is limited to `<input>` elements, `<textarea>` boxes and `<select>` elements. For select boxes, checkboxes, and radio buttons, the event is fired immediately when the user makes a selection with the mouse, but for the other element types the event is deferred until the element loses focus.


`.change()` 这个事件仅限于 `<input>`、`<textarea>` 和 `<select>` 元素.



举个 `change()` 应用于 `<select>` 的例子:

```html
<!DOCTYPE html>
<html lang="zh-CN" dir="ltr">
    <head>
        <meta charset="utf-8">
        <title></title>
        <script src="jquery-3.4.1.js" charset="utf-8"></script>
    </head>
    <body>
        <small>请选择畐国的一名英雄:</small>
        <form>
            <select>
                <option value="1">申帝</option>
                <option value="2">串相</option>
                <option value="3">㐅大将</option>
                <option value="4">艹帅</option>
                <option value="5">木贵人 </option>
                <option value="6">丶贵人</option>
                <option value="7">右妃</option>
                <option value="8">宛史官</option>
            </select>
        </form>
        <script type="text/javascript">
            $("select").change(function () {
                $("select option:selected").each(function () {
                    alert($(this).html())
                });
            })
        </script>
    </body>
</html>
``` 


效果:

![畐国先锋大将.png](https://i.loli.net/2019/07/30/5d3fb6c85175b32655.png)


看了下关于 `<small>` 的介绍:

The **HTML** `<small>` **element** makes the text *font size* one size smaller (for example, from large to medium, or from small to x-small) down to the browser's minimum font size.  In HTML5, this element is repurposed to represent side-comments and small print, including copyright and legal text, independent of its styled presentation.

所以好像确实没检查出来字号.


再次写一下: `.change()` 只适用于 `<input>`、`<textarea>` 以及 `<select>`, 仅限于这三个元素. 而得到焦点、失去焦点则适用于所有元素.


#### [.select()](https://api.jquery.com/select/)


描述: Bind an event handler to the "select" JavaScript event, or trigger that event on an element.

注意: The `select` event is sent to an element when the user makes a text selection inside it. This event is limited to `<input type="text">` fields and `<textarea>` boxes.


举个 `.select()` 的例子:


```html
<!DOCTYPE html>
<html lang="en" dir="ltr">
    <head>
        <meta charset="utf-8">
        <title></title>
        <script src="jquery-3.4.1.js" charset="utf-8"></script>
    </head>
    <body>
        <form action="">
            <input id="target" type="text" value="申畜我草拟吗!"><br/>
            <input class="test" type="text" value="串犬你妈炸了."><br/>
            <div></div>
            <p></p>
        </form>
        <script type="text/javascript">
            $("#target").select(function () {
                $("div").text("随着一声响指申畜的🐴化成了灰." ).show().fadeOut( 4000);
            })
            $(".test").select(function () {
                $("p").text("随着一声响指串犬的🐴化成了灰." ).show().fadeOut( 2000);
            })
        </script>
    </body>
</html>

```




效果:


![响指.png](https://i.loli.net/2019/07/30/5d3fbb061ec1b83581.png)





#### [.submit()](https://api.jquery.com/submit/)


描述: Bind an event handler to the "submit" JavaScript event, or trigger that event on an element.

注意: The `submit` event is sent to an element when the user is attempting to submit a form. It can only be attached to `<form>` elements. Forms can be submitted either by clicking an explicit `<input type="submit">`, `<input type="image">`, or `<button type="submit">`, or by pressing Enter when certain form elements have focus.


孔子曰:“学而时习之, 不亦说乎.”现在我们对表单事件的作用对象做一个总结:

| 表单事件 | 绑定后能生效的对象 |
|---|---|
| `.select()` | `<input type="text">` 和 `<textarea>` |
| `.change()` | `<input>`, `<textarea>` 和 `<select>` |
| `.submit()` | `<form>` 元素 |
| `.focus()` | 所有元素 |
| `.blur()` | 所有元素 |


现在我们来看一下 `.submit()` 的例子:


```html
<!DOCTYPE html>
<html lang="en" dir="ltr">
    <head>
        <meta charset="utf-8">
        <title></title>
        <script src="jquery-3.4.1.js" charset="utf-8"></script>
    </head>
    <body>
        <form>
            <input id="target" type="text" value="申帝我草拟吗!"><br/>
            <input type="text" value="串相我操你妈!"><br/>
            <input type="submit" name="" value="小手一抖, 畜🐴带走">
        </form>
        <script type="text/javascript">
            $("form").submit(function () {
                alert("确定要将两位畜牲的🐴献祭吗?")
            })
        </script>
    </body>
</html>

```



效果:

![submit.png](https://i.loli.net/2019/07/30/5d3fcb1157f2757354.png)


## DOM 属性(官网上的[Attributes](https://api.jquery.com/category/attributes/))


视频里会讲以下十个方法:

1. [.addClass()](https://api.jquery.com/addClass/)
2. [.attr()](https://api.jquery.com/attr/)
3. [.hasClass()](https://api.jquery.com/hasClass/)
4. [.html()](https://api.jquery.com/html/)
5. [.prop()](https://api.jquery.com/prop/)
6. [.removeAttr()](https://api.jquery.com/removeAttr/)
7. [.removeClass()](https://api.jquery.com/removeClass/)
8. [.removeProp()](https://api.jquery.com/removeProp/)
9. [.toggleClass()](https://api.jquery.com/toggleClass/)
10. [.val()](https://api.jquery.com/val/)


#### 1. [.addClass()](https://api.jquery.com/addClass/)

描述: Adds the specified class(es) to each element in the set of matched elements. 为每个匹配的元素添加指定的样式类名.

官网上关于 `.addClass()` 这个方法有这么一点得注意一下:

> It's important to note that this method does not replace a class. It simply adds the class, appending it to any which may already be assigned to the elements.


现在举个 `.addClass()` 的例子:

```html
<!DOCTYPE html>
<html lang="en" dir="ltr">
    <head>
        <meta charset="utf-8">
        <title></title>
        <script src="jquery-3.4.1.js" charset="utf-8"></script>
        <style>
            .bold {
                font-weight: bold;
            }
            .italic {
                font-style: italic;
            }
            .red-colored {
                color: red;
            }
            .blue-colored {
                color: blue;
            }
        </style>
    </head>
    <body>
        <p>申畜我操你妈!</p>
        <div><span>串犬我透你妈!</span></div>
        <p>申畜你妈炸了.</p>
        <div><span>串犬你妈凉了.</span></div>
        <script type="text/javascript">
            // 原生JavaScript写法.
            let paras = document.getElementsByTagName('p')
            for (let i = 0; i < paras.length; i++) {
                paras[i].className = 'bold red-colored'
            }

            // jQuery写法.
            $(function () {
                $("span").addClass('italic blue-colored')
            })
        </script>
    </body>
</html>

```

效果:

![addClass.png](https://i.loli.net/2019/07/31/5d412cd0dfd4a90034.png)


提这么几点注意事项:

原生JavaScript写法中元素有多个的时候不能直接给选完的结果添加类, 而应当给数组中每一个元素添加类, 否则不会生效. 

再就是这里用 `for` 循环可以实现, 但是用 `for-in` 循环就实现不了, 不知为何.

还有就是在 [Element.className](https://developer.mozilla.org/en-US/docs/Web/API/Element/className) 的描述中, 提到了:

> The `className` property of the [`Element`](https://developer.mozilla.org/en-US/docs/Web/API/Element) interface gets and sets the value of the [`class attribute`](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/class) of the specified element.


这个 JS 里的 `className` 属性就相当于一个 getter 或 setter 的作用, 直接读, 但也直接洗. 你再 `className` 是不会在原有的基础上添加新的类名, 而是直接把类名洗成新的.


#### 2. [.attr()](https://api.jquery.com/attr/)

描述: Get the value of an attribute for the first element in the set of matched elements or set one or more attributes for every matched element. 获取匹配的元素集合中的第一个元素的属性的值， 或是设置每一个匹配元素的一个或多个属性.

这个是个典型的 getter/setter 方法.

在 jQuery 官方文档 [.attr()](https://api.jquery.com/attr/) 的下面, 有提到 **Attributes vs. Properties** 这么个话题, 可以看看. 另外我本人也写了一篇介绍两者区别的文章: [property 和 attribute 的区别](https://liujunyi271828.github.io/2019-07-25/property-vs-attribute/)


举个 `.attr()` 的例子:


```html
<!DOCTYPE html>
<html lang="en" dir="ltr">
    <head>
        <meta charset="utf-8">
        <title></title>
        <script src="jquery-3.4.1.js" charset="utf-8"></script>
        <style>
            .red-colored {
                color: red;
            }
        </style>
    </head>
    <body>
        <p>申畜我操你妈!</p>
        <a>串犬我透你妈!</a>
        <br/>
        <img width="300px" src="https://i.loli.net/2019/05/15/5cdb8768e904626027.jpeg" title="自由领导人民" alt="Eugène Delacroix's 1830 painting “Liberty Leading the People”" style="display:block; margin-left:auto; margin-right:auto"/>
        <!-- 将图片相关信息输出到下面的 div 中 -->
        <div></div>
        <script type="text/javascript">
            $("p").addClass('red-colored')
            // `.attr()` 方法传双参数进去作为 setter.
            $("a").attr({
                'href': 'www.chuan-quan-yun-zhi-sang-wei-yuan-hui.com',
                'title': 'www.chuan-quan-yun-zhi-sang-wei-yuan-hui.com'
            })
            // `.attr()` 方法传  attribute 名进去作为 getter 获取 attribute 值.
            title = $("img").attr("title")
            description = $("img").attr("alt")
            $("div").text('图片标题: ' + title + '; 图片描述: ' + description)
        </script>
    </body>
</html>
```

效果:

![attr.png](https://i.loli.net/2019/07/31/5d414c8638f1276162.png)


我要说的就是传多个键值对的时候就上 JSON(真心好用啊...).

还有就是如果你想实现鼠标放在上面有说明那种的效果, 就添加一个 `title` 的 attribute. 不管是 `<a>` 还是 `<img>` 都是这样. `<img>` 的 `title` 属性的例子可以看 [日志考勤论](https://liujunyi271828.github.io/2019-05-15/ri-zhi-kao-qin-lun/) 中的第一个图.

再个就是你 `<a>` 标签在不添加 `href` 属性的时候是不会出下划线的.


#### 3. [.hasClass()](https://api.jquery.com/hasClass/)

描述: Determine whether any of the matched elements are assigned the given class. 确定任何一个匹配元素是否有被分配给定的(样式)类.


举个 `.hasClass()` 的例子:


```html
<!DOCTYPE html>
<html lang="en" dir="ltr">
    <head>
        <meta charset="utf-8">
        <title></title>
        <script src="jquery-3.4.1.js" charset="utf-8"></script>
        <style>
            .is-leader {
                color: green;
            }
        </style>
    </head>
    <body>
        <h2>畐国皇室电影宇宙</h2>
        <h3 class="is-leader">申帝: 畐国皇室第一人</h3>
        <p>讲述商二代专科生申帝最终取得高级工程师证并从985211高校MBA专硕毕业的故事.</p>
        <h3>串相</h3>
        <p>讲述串相父竭力尽智揣测申帝心意, 铲除异己的故事.</p>
        <h3>艹帅</h3>
        <p>讲述畐国天下兵马大元帅艹帅不辞辛劳南征北战, 为畐国而陪甲方吃饭K歌洗澡的故事.</p>
        <h3>㐅大将</h3>
        <p>讲述申帝心腹㐅大将为畐国开疆扩土, 任劳任怨为畐国打出一片大好河山的故事.</p>
        <h3>串相2: 串相与木贵人</h3>
        <p>木贵人来到畐国不久, 串相就与木贵人情同兄妹, 这份感情甚至超越了亲情...</p>
        <h3>SCD队长</h3>
        <p>畐国的新一代领军人物SCD队长, 深明大义向申帝献祭出庸俗的皮囊, 从而走向不凡.</p>
        <script type="text/javascript">
            if ($('h3:first').hasClass("is-leader")) {
                alert('Long live the 申!')
            }
        </script>
    </body>
</html>

```

效果:

![畐国皇室电影宇宙.png](https://i.loli.net/2019/07/31/5d4155a863a8b83879.png)


#### 4. [.html()](https://api.jquery.com/html/)


描述: Get the HTML contents of the first element in the set of matched elements or set the HTML contents of every matched element. 获取集合中第一个匹配元素的 HTML 内容, 或设置每一个匹配元素的 HTML 内容.


也是一个又可以当 getter 又可以当 setter 的方法.


举个 `.html()` 的例子:

```html
<!DOCTYPE html>
<html lang="en" dir="ltr">
    <head>
        <meta charset="utf-8">
        <title></title>
        <script src="jquery-3.4.1.js" charset="utf-8"></script>
        <style>
            span  {
                color: red;
            }
        </style>
    </head>
    <body>
        <!-- 获取指定元素内容并 alert. -->
        <h2>申帝我操你妈.</h2>
        <p>畐二世申帝长期将下属当佣人，有揣测心意为申作伥的、有无偿提供特殊服务的、有免费帮其打通和项目经理关系的、有自愿加班帮助申帝完成任务的、更有甚者还有代其供佛做法事的……许多下属长期被申帝奴役，敢怒不敢言。</p>
        <p>为了求得内心宁静，申帝曾去过西藏的星隐寺、四川的碧莲寺以及山西、福建等著名宗教景点敬香。2018年10月，某活佛到昆明活动，申帝赶到活佛驻地拜见，皈依到大师名下，取名为“窝槽尼玛”。</p>
        <p>除此之外，申帝还带风水先生到办公室看风水、设佛龛、挂字画，用公款非法购买字画乃至基金，连鱼缸里鱼的颜色及条数都按大师的“点拨”布局。有时申帝抽不开身，又不愿错过“良辰吉时”，就安排亲信妖女右皇妃轮班到议事殿的佛堂代替自己跪拜、做法事。</p>
        <!-- 新建一个空 span, 向里面写入 HTML 文本. -->
        <span></span>
        <script type="text/javascript">
            alert($("h2").html())
            $("span").html("衷心祝愿申帝早日驾崩。")
        </script>
    </body>
</html>

```


效果:

![html方法.png](https://i.loli.net/2019/07/31/5d415b4dab58d57593.png)



#### 5. [.prop()](https://api.jquery.com/prop/)


描述: Get the value of a property for the first element in the set of matched elements or set one or more properties for every matched element. 获取匹配的元素集中第一个元素的属性 (property) 值, 或者为匹配的元素设置一个或多个属性 (property).

是个又可以当 getter 又可以当 setter 的方法.

 
注意 `.prop()` 方法只能获取原生 property 值, 自己编的是获取不到的. 此外还有: The `.prop()` method gets the property value for only the *first* element in the matched set. It returns `undefined` for the value of a property that has not been set, or if the matched set has no elements. To get the value for each element individually, use a looping construct such as jQuery's `.each()` or `.map()` method.

官方文档这一页也是有个关于 **Attributes vs. Properties** 的说明.


举个 `.prop()` 的例子:


```html
<!DOCTYPE html>
<html lang="en" dir="ltr">
    <head>
        <meta charset="utf-8">
        <title></title>
        <script src="jquery-3.4.1.js" charset="utf-8"></script>
    </head>
    <body>
        <form action="">
            <!-- 将原类型为 text 的 input 元素的 value 设为指定值. -->
            <!-- 并遍历输出每一个 option 的 value 值. -->
            <input type="text" name="" value="申帝我操你🐴."><br/>
            <select class="" name="">
                <option value="shendi-mom-boom">申帝你妈炸了.</option>
                <option value="chuanxiang-mom-boom">串相你妈炸了.</option>
                <option value="fuck-shenchu-mom">申畜我透你妈.</option>
                <option value="fuck-chuanquan-mom">串犬我透你妈.</option>
            </select>
        </form>
        <script type="text/javascript">
            // To get the value for each element individually, use a looping construct such as jQuery's `.each()` or `.map()` method.
            $(function () {
                $("option").each(function () {
                    console.log($(this).prop("value"))
                })
                $("input").prop("value", "操申帝和串相的🐴三千次.")
            })
        </script>
    </body>
</html>
```


效果:

![prop.png](https://i.loli.net/2019/08/01/5d42521f64cea46779.png)




#### 6. [.removeAttr()](https://api.jquery.com/removeAttr/)

描述: Remove an attribute from each element in the set of matched elements. 为匹配的元素集合中的每个元素移除一个属性 (attribute).


举个 `.removeAttr()` 的例子:

```html
<!DOCTYPE html>
<html lang="en" dir="ltr">
    <head>
        <meta charset="utf-8">
        <title></title>
        <script src="jquery-3.4.1.js" charset="utf-8"></script>
    </head>
    <body>
        <!-- 移除第二个 <a> 标签的 href 属性. -->
        <!-- 移除第一个 <p> 标签的双击不选中文本效果. -->
        <a href="www.shendi-cloud-zhisang-committee.com">申帝云治丧委员会</a>
        <br/>
        <a href="www.chuanxiang-cloud-zhisang-committee.com">串相云治丧委员会</a>
        <p onselectstart="return false">有的申和串活着, 它们已经死了; 有的申和串活着, 别人就不能活.</p>
        <p onselectstart="return false">艹申和串的🐴三千次.</p>
        <script type="text/javascript">
            $("a:last").removeAttr("href")
            $("p:first").removeAttr("onselectstart")
        </script>
    </body>
</html>

```


效果:

![removeAttr.png](https://i.loli.net/2019/08/01/5d425ed29060c60554.png)


#### 7. [.removeClass()](https://api.jquery.com/removeClass/)


描述: Remove a single class, multiple classes, or all classes from each element in the set of matched elements. 移除集合中每个匹配元素上一个、多个或全部样式.

举个 `.removeClass()` 的例子:

```html
<!DOCTYPE html>
<html lang="en" dir="ltr">
    <head>
        <meta charset="utf-8">
        <title></title>
        <script src="jquery-3.4.1.js" charset="utf-8"></script>
        <style>
            .bold {
                font-weight: bold;
            }
            .italic {
                font-style: italic;
            }
            .red-colored {
                color: red;
            }
            .blue-colored {
                color: blue;
            }
        </style>
    </head>
    <body>
        <p class="bold">申畜我操你妈!</p>
        <div><span class="italic">串犬我透你妈!</span></div>
        <p class="red-colored">申畜你妈炸了.</p>
        <div><span class="blue-colored">串犬你妈凉了.</span></div>
        <script type="text/javascript">
            $(function () {
                $("p").removeClass("bold")
                $("span").removeClass("blue-colored")
            })
        </script>
    </body>
</html>

```



效果:


![removeClass.png](https://i.loli.net/2019/08/01/5d4266acf20c793476.png)



#### 8. [.removeProp()](https://api.jquery.com/removeProp/)

描述: Remove a property for the set of matched elements. 为集合中匹配的元素删除一个属性. 

注意: 

> Do not use this method to remove native properties such as checked, disabled, or selected. This will remove the property completely and, once removed, cannot be added again to element. Use [.prop()](https://api.jquery.com/prop/) to set these properties to `false` instead.


这个视频里没给例子, 所以我也不给例子了, 想看例子上官网看吧.

#### 9. [.toggleClass()](https://api.jquery.com/toggleClass/)


描述: Add or remove one or more classes from each element in the set of matched elements, depending on either the class's presence or the value of the state argument. 在匹配的元素集合中的每个元素上添加或删除一个或多个样式类, 取决于这个样式类是否存在或值切换属性. 即: 如果存在的话就删除这个类, 如果不存在的话就添加这个类.


下面我们来写一个车场闸机的SCD跑马灯 `.toggleClass()` 的例子~~(没想到居然写出来了233)~~:

```html
<!DOCTYPE html>
<html lang="en" dir="ltr">
    <head>
        <meta charset="utf-8">
        <title></title>
        <script src="jquery-3.4.1.js" charset="utf-8"></script>
        <style>
            .red-colored {
                color: red;
            }
            .orange-colored {
                color: orange;
            }
            .yellow-colored {
                color: yellow;
            }
            .green-colored {
                color: green;
            }
            .cyan-colored {
                color: cyan;
            }
            .blue-colored {
                color: blue;
            }
            .purple-colored {
                color: purple;
            }
            span {
                font-size: 30px;
            }
        </style>
    </head>
    <body>
        <button>申帝我操你妈.</button>
        <div class="">
            <span>S</span>
            <span>C</span>
            <span>D</span>
            <span>I</span>
            <span>L</span>
            <span>E</span>
            <span>R</span>
        </div>

        <script type="text/javascript">
            var count = 0
            $("button").click(function () {
                switch (count % 14) {
                    case 0:
                    case 1: {
                        $("span").toggleClass("red-colored")
                        break;
                    }
                    case 2:
                    case 3: {
                        $("span").toggleClass("orange-colored")
                        break;
                    }
                    case 4:
                    case 5: {
                        $("span").toggleClass("yellow-colored")
                        break;
                    }
                    case 6:
                    case 7: {
                        $("span").toggleClass("green-colored")
                        break;
                    }
                    case 8:
                    case 9: {
                        $("span").toggleClass("cyan-colored")
                        break;
                    }
                    case 10:
                    case 11: {
                        $("span").toggleClass("blue-colored")
                        break;
                    }
                    case 12:
                    case 13: {
                        $("span").toggleClass("purple-colored")
                        break;
                    }
                }
                count++
                console.log(count)
            })
        </script>
    </body>
</html>
```

效果:


![跑马灯.png](https://i.loli.net/2019/08/01/5d4273f2a2a0645793.png)

就是大概演示个意思. 至少我认为逻辑看起来是对的.

有这么几个要注意的地方:

* 注意加 `break`.(很久没用过 `switch` 语句了, 都是凭感觉写的)
* 注意点击计数 `count` 自增的时机.




#### 10. [.val()](https://api.jquery.com/val/)


Get the current value of the first element in the set of matched elements or set the value of every matched element.

获取匹配的元素集合中第一个元素的当前值, 或是设置匹配的元素集合中每个元素的值.


也是个既可以当 getter 又可以当 setter 的方法.

可以用来获取表单元素的值.


举个 `.val()` 的例子:

```html
<!DOCTYPE html>
<html lang="en" dir="ltr">
    <head>
        <meta charset="utf-8">
        <title></title>
        <script src="jquery-3.4.1.js" charset="utf-8"></script>
    </head>
    <body>
        <!-- 实现选中 radio 的时候下面能够动态显示 选中的 radio 值. -->
        <form id="form">
            <!-- 如果要实现在几个单选里几选一的效果的话, 注意同一组 input 选项保持相同的 name 值. -->
            <label><input name="Membership" type="radio" checked="true" value="Forbidden">Forbidden</label>&nbsp;&nbsp;&nbsp;
            <label><input name="Membership" type="radio" value="Excluded">Excluded</label>&nbsp;&nbsp;&nbsp;
            <label><input name="Membership" type="radio" value="Tagged">Tagged</label>&nbsp;&nbsp;&nbsp;
            <label><input name="Membership" type="radio" value="Untagged">Untagged</label>&nbsp;&nbsp;&nbsp;
        </form>
        <p></p>
        <script type="text/javascript">
            $('#form input').on('change', function() {
                // 你用 input[name="Membership"]:checked 也可以
                // 要是拿 radio 选的话就用下面代码里键值对的方式选. 直接 `:radio` 的话官网说了 `:radio` 这么做的话不能达到最好性能: https://api.jquery.com/radio-selector/
                $("p").text('您选择了: ' + $('input[type="radio"]:checked', '#form').val());
            });
        </script>
    </body>
</html>
```

效果: 

![val.png](https://i.loli.net/2019/08/01/5d42864a69e4915358.png)


找这个东西的实现的时候, 我某度了一堆方法, 结果在看到的一堆博文中试了一圈, 没一个能实现 jQuery 版点击 radio 能让下面的值也改变的. 我就笑了, 这帮人是怎么找到开发类工作的? 自己写东西的时候不先看看能不能用就瞎几把乱抄么??? 就和考试打小抄结果抄了个 50 分的答案一样.

正解请参考: [How can I know which radio button is selected via jQuery?](https://stackoverflow.com/questions/596351/how-can-i-know-which-radio-button-is-selected-via-jquery)


要注意的点是(虽然在注释里写过了):

* 你用 `input[name="Membership"]:checked` 也可以, 要是通过 `radio` 选的话就用例子代码里键值对的方式选. 如果直接 `:radio` 的话官网说了 `:radio` 这么做的话不能达到最好性能. 出处: [https://api.jquery.com/radio-selector/](https://api.jquery.com/radio-selector/)
* 如果要实现在几个单选里几选一的效果的话, 注意同一组 `input` 选项保持相同的 `name` 值.


## DOM 操作


看一下官网关于“操作”这个类别的描述:

> All of the methods in this section manipulate the DOM in some manner. A few of them simply change one of the attributes of an element (also listed in the [Attributes category](https://api.jquery.com/category/attributes/)), while others set an element's style properties (also listed in the [CSS category](https://api.jquery.com/category/css/)). Still others modify entire elements (or groups of elements) themselves—inserting, copying, removing, and so on. All of these methods are referred to as "setters," as they change the values of properties.
> 
> A few of these methods—such as `.attr()`, `.html()`, and `.val()`—also act as "getters," retrieving information from DOM elements for later use.



官网的左边栏(假如后人看的时候还没改版的话)中的 Manipulation 有以下内容:

* [Manipulation](https://api.jquery.com/category/manipulation/)
  * [Class Attribute](https://api.jquery.com/category/manipulation/class-attribute/)
  * [Copying](https://api.jquery.com/category/manipulation/copying/)
  * [DOM Insertion, Around](https://api.jquery.com/category/manipulation/dom-insertion-around/)
  * [DOM Insertion, Inside](https://api.jquery.com/category/manipulation/dom-insertion-inside/)
  * [DOM Insertion, Outside](https://api.jquery.com/category/manipulation/dom-insertion-outside/)
  * [DOM Removal](https://api.jquery.com/category/manipulation/dom-removal/)
  * [DOM Replacement](https://api.jquery.com/category/manipulation/dom-replacement/)
  * [General Attributes](https://api.jquery.com/category/manipulation/general-attributes/)
  * [Style Properties](https://api.jquery.com/category/manipulation/style-properties/)


视频里给的分类如下:

1. class 属性: `.addClass()`、`.hasClass()`、`.removeClass()`、`.toggleClass()`.
2. DOM 插入并包裹现有内容.
3. DOM 插入到现有元素内.
4. DOM 插入到现有元素外.
5. DOM 移除.
6. DOM 替换.
7. 通用属性操作: `.attr()`、`.prop()`、`.removeAttr()`、`.removeProp()`、`.val()`.
8. CSS(也就是上面英文版目录的那个Style) 属性.
9. 复制元素.


在继续学习之前, 让我们先学习一个姿势点: **CDN**.


### CDN

CDN 的全称是 Content Delivery Network, 即内容分发网络. 其基本思路是尽可能避开互联网上有可能影响数据传输速度和稳定性的瓶颈和环节, 使内容传输的更快、更稳定. 通过在网络各处放置节点服务器所构成的在现有的互联网基础之上的一层智能虚拟网络, CDN 系统能够实时地根据网络流量和各节点的连接、负载状况以及到用户的距离和响应时间等综合信息将用户的请求重新导向离用户最近的服务节点上. 其目的是使用户可就近取得所需内容, 解决 Internet 网络拥挤的状况, 提高用户访问网站的响应速度.


视频用的某度的CDN, 不过我感觉某度要凉. 

我自己找了一下, 有这么几个看起来还凑合的:

* [CDNJS.NET: 前端公共库CDN，开源项目CDN公共库，静态资源库。永久免费，保护隐私，500+节点毫秒级响应。实时同步cdnjs.com，全面支持https，安全稳定快速！](https://cdnjs.net)
* [cdnjs.com - The best FOSS CDN for web related libraries to speed up your websites!](https://cdnjs.com) 顺便说下这个有对应的 GitHub 项目仓库首页: [cdnjs/cdnjs](https://github.com/cdnjs/cdnjs)
* [jsDelivr: A free, fast, and reliable Open Source CDN for npm and GitHub with the largest network and best performance among all CDNs. Serving more than 40 billion requests per month.](https://www.jsdelivr.com)
* [BootCDN: Bootstrap 中文网开源项目免费 CDN 加速服务 - 我们致力于为 Bootstrap、jQuery、Angular、Vue.js 一样优秀的开源项目提供稳定、快速、免费的 CDN 加速服务。BootCDN 是运营时间最长、用户量最大、最早同时支持 HTTPS（SSL）和 HTTP/2.0 协议的中立免费 CDN 。](https://www.bootcdn.cn)


作为补充, 可以看一下这篇文章: [漫话：如何给女朋友解释什么是CDN？](https://juejin.im/post/5d478c48e51d453c135c5a5c)

摘录一下某乎上关于 CDN 的评论:

> [ggggff的某乎回答](https://www.zhihu.com/question/20227463/answer/128583602): 对于 JS 的 CDN 这种服务比对一般的图片cdn服务要求更严格，出一次问题你会骂娘，出两次问题你就考虑备选方案或者换一家了。连阿里云可能都无法保证一年之内少于两次事故，所以还是不要为了那点流量增加出风险概率。当然那些开源免费的cdn除了在个人项目玩玩，就不要放到公司项目里面来了。
对于js的cdn这种服务比对一般的图片cdn服务要求更严格，出一次问题你会骂娘，出两次问题你就考虑备选方案或者换一家了。连阿里云可能都无法保证一年之内少于两次事故，所以还是不要为了那点流量增加出风险概率。当然那些开源免费的cdn除了在个人项目玩玩，就不要放到公司项目里面来了。



可以看看[RequireJS: a JavaScript module loader](https://requirejs.org). 这个据说是有遇到取不到cdn上的资源的时候可以选择访问自己服务器上的资源的解决方案.


下面我们举个例子:

![cdnjs1.png](https://i.loli.net/2019/08/02/5d43abfd3a56191405.png)


![cdnjs2.png](https://i.loli.net/2019/08/02/5d43abfe161e331721.png)

随便抄个 URL 粘到 `src` 里, 就可以用了. 但是一定要慎重.


举个引用 CDN 资源的例子:


```html
<!DOCTYPE html>
<html lang="en" dir="ltr">
    <head>
        <meta charset="utf-8">
        <title></title>
        <!-- 引入 CDN 版 jQuery 3.4.1 资源. -->
        <script src="https://cdn.jsdelivr.net/npm/jquery@3.4.1/dist/jquery.min.js"></script>
    </head>
    <body>
        <!-- 看看能不能打印出这个 jQ 对象. -->
        <script type="text/javascript">
            console.log($)
        </script>
    </body>
</html>

```



效果:

![consolejq.png](https://i.loli.net/2019/08/02/5d43afa6e86fe58880.png)


那么使用 CDN 有什么好处呢? 可以看看各种云关于 CDN 的广告词, 而视频里说:

CDN 可以方便我们的统一管理, 譬如说版本的更改等等; 同时呢 CDN 可以节省空间, 在手机项目中这个优点还是比较突出的, 因为它毕竟还是占用了一定的存储空间. 所以说使用这种外部引用的方式就可以避免了我们将这个文件拷贝到我们的工程当中, 而且 CDN 的引入方式还是比较方便的.


### DOM 插入并包裹现有内容(官网上叫[Category: DOM Insertion, Around](https://api.jquery.com/category/manipulation/dom-insertion-around/))


1. [`.wrap()`](https://api.jquery.com/wrap/)
2. [`.unwrap()`](https://api.jquery.com/unwrap/)
3. [`.wrapAll()`](https://api.jquery.com/wrapAll/)
4. [`.wrapInner()`](https://api.jquery.com/wrapInner/)

#### 1. [.wrap()](https://api.jquery.com/wrap/)

描述: Wrap an HTML structure around each element in the set of matched elements. 在每个匹配的元素外层包上一个 HTML 元素.

举例:


```html
<!DOCTYPE html>
<html lang="en" dir="ltr">
    <head>
        <meta charset="utf-8">
        <title></title>
        <!-- jQuery 3.4.1 的塑形压缩版. -->
        <script src="https://libs.cdnjs.net/jquery/3.4.1/jquery.slim.min.js"></script>
        <style>
            .shen-pig-p {
                color: green;
            }
            .chuan-dog-p {
                color: Lime;
            }
            .shen-pig-div {
                /* 注意别手滑把 border 写成 color 了, 当时改了好长时间. */
                border: 2px solid black;
                width: 200px;
                margin: 20px;
                padding: 2px;
            }
            .chuan-dog-div {
                border: 1px solid silver;
                width: 320px;
                padding: 2px;
                margin: 20px;
            }
        </style>
    </head>
    <body>
        <p class="shen-pig-p">坐在鳖头战车🚘里的申畜</p>
        <p class="chuan-dog-p">在吹逼卫星🛰上绕它🐴坟环游八十天的串犬</p>
        <script>
            $(document).ready(function () {
                // 都在同一个参数里的话注意单引号双引号穿插着用.
                $(".shen-pig-p").wrap("<div class='shen-pig-div'></div>")
                $(".chuan-dog-p").wrap("<div class='chuan-dog-div'></div>")
            })
        </script>
    </body>
</html>
```


效果:

![wrap.png](https://i.loli.net/2019/08/02/5d43d48a4817291591.png)

#### 2. [.unwrap()](https://api.jquery.com/unwrap/)

描述: Remove the parents of the set of matched elements from the DOM, leaving the matched elements in their place. 将匹配元素集合的父级元素删除, 保留自身(和兄弟元素, 如果存在)在原来的位置.


举例:


```html
<!DOCTYPE html>
<html lang="en" dir="ltr">
    <head>
        <meta charset="utf-8">
        <title></title>
        <!-- jQuery 3.4.1 的塑形压缩版. -->
        <script src="https://libs.cdnjs.net/jquery/3.4.1/jquery.slim.min.js"></script>
        <style>
            fieldset {
                width: 400px;
                border: 5px solid black;
            }
        </style>
    </head>
    <body>
        <fieldset>
            <legend>&nbsp;&nbsp;&nbsp;&nbsp;申帝的Charlie战袍&nbsp;&nbsp;&nbsp;&nbsp;</legend>
            <p>得地的用法教学: <br/><cite>申帝按捺不住要狂艹右妃的心, 直接猴急地脱得赤条条的.</cite></p>
        </fieldset>

        <script>
            $(document).ready(function () {
                // `.prev()` 和 `.prevAll()` 是 Tree Traversal 里的方法, 还没讲.
                $("p").prevAll().html("")
                $("p").unwrap()
            })
        </script>
    </body>
</html>

```


效果:


![unwrap.png](https://i.loli.net/2019/08/02/5d43dbbe5b10446189.png)


注意这个 `unwrap()` 方法不删除套着它的祖先元素, 只删除套着它的父级元素(就是**紧**挨着它的那个外层的元素). 这个一定要注意.



#### 3. [.wrapAll()](https://api.jquery.com/wrapAll/)


描述: Wrap an HTML structure around all elements in the set of matched elements. 在所有匹配元素外面包一层 HTML 结构.

举例:


```html
<!DOCTYPE html>
<html lang="en" dir="ltr">
    <head>
        <meta charset="utf-8">
        <title></title>
        <!-- Bootcdn 家的 jQuery 3.4.1 的塑形压缩版. -->
        <script src="https://cdn.bootcss.com/jquery/3.4.1/jquery.slim.min.js"></script>
        <style>
            div {
                width: 300px;
                background-color: #000;
                color: #fff;
                padding: 3px 6px;
            }
        </style>
    </head>
    <body>
        <h2>SCD 家族</h2>
        <p>雄德尔 AI 安防解决方案</p>
        <p>TG 德尔数通解决方案</p>
        <p>浩博德尔车场管理解决方案</p>
        <p>微德尔门禁解决方案</p>
        <p>申帝健身私教与宝剑解决方案</p>
        <script>
            $(document).ready(function () {
                $("p").wrapAll("<div></div>")
            })
        </script>
    </body>
</html>
```


效果:

![wrapAll.png](https://i.loli.net/2019/08/02/5d43e621aa06a99894.png)


注意是把选择器匹配出来的块整个给插到 `.wrapAll()` 中参数匹配到的第一个最内层里, 而不是插到参数中最深的地方. 比如说 `fieldset>(legend+(div>div))` 这种的, 它会给你匹配到 `<legend></legend>` 里而不是 `<div><div></div></div>` 里.


#### 4. [.wrapInner()](https://api.jquery.com/wrapInner/)


描述: Wrap an HTML structure around the content of each element in the set of matched elements. 在匹配元素里的**内容外**包一层 HTML 结构. 

仔细体会 “内容” 的含义, 这就是 `.wrapInner()` 和 `.wrap()` 的差异之处.

注意: The `.wrapInner()` function can take any string or object that could be passed to the `$()` factory function to specify a DOM structure. This structure may be nested several levels deep, but should contain only one inmost element. The structure will be wrapped around the content of each of the elements in the set of matched elements. 

划重点: 可以多层嵌套, 但是应该只包含一个最内层的元素.


举例:


```html
<!DOCTYPE html>
<html lang="en" dir="ltr">
    <head>
        <meta charset="utf-8">
        <title></title>
        <!-- cdnjs 家的 jQuery 3.4.1 的塑形压缩版. -->
        <script src="https://cdnjs.cloudflare.com/ajax/libs/jquery/3.4.1/jquery.slim.min.js"></script>
        <style>
            .outer {
                border: 2px solid black;
                width: 240px;
                height: 60px;
            }
            .inner {
                position: absolute;
                width: 200px;
                margin-top: 5px;
                margin-left: 20px;
                border: 1px solid red;
            }
        </style>
    </head>
    <body>
        <div>
            <p>雄从未忘记姨</p>
            <p>雄姨手拉手啊 想说的太多</p>
            <p>空气开始冒烟</p>
        </div>
        <script>
            $("p").wrapInner("<div class='outer'>在那座阴雨的小城里<div class='inner'></div></div>")
        </script>
    </body>
</html>

```



效果:


![wrapInner.png](https://i.loli.net/2019/08/02/5d43f9faa7c2821255.png)


这个是给你每个选择器里选出来的 **东西内容** 套一个你往 `.wrapInner()` 里传的参数对应的那个 HTML 结构.


### DOM 插入到现有元素内(官网上叫[DOM Insertion, Inside](https://api.jquery.com/category/manipulation/dom-insertion-inside/))


六个方法.

1. [`.append()`](https://api.jquery.com/append/)
2. [`.appendTo()`](https://api.jquery.com/appendTo/)
3. [`.html()`](https://api.jquery.com/html/)
4. [`.prepend()`](https://api.jquery.com/prepend/)
5. [`.prependTo()`](https://api.jquery.com/prependTo/)
6. [`.text()`](https://api.jquery.com/text/)


下面分别来看一下.


#### 1. [`.append()`](https://api.jquery.com/append/)


相当于 JavaScript 中的 [Node.appendChild()](https://developer.mozilla.org/en-US/docs/Web/API/Node/appendChild).


描述: Insert content, specified by the parameter, to the end of each element in the set of matched elements. 在每个匹配元素里面的末尾处插入参数内容.


举个 `.append()` 的例子:


```html
<!DOCTYPE html>
<html lang="en" dir="ltr">
    <head>
        <meta charset="utf-8">
        <title></title>
        <script src="jquery-3.4.1.js" charset="utf-8"></script>
    </head>
    <body>
        <!-- 在每一个 `<span>` 标签后面追加一个 `<small>` 标签. -->
        <span>早上艹一遍申畜的🐴, 心情好!</span><span>晚上透一遍串犬的🐎, 睡得香!</span>
        <script type="text/javascript">
            $(document).ready(function () {
                $("span").append("<small>操申畜和串犬的妈三千次.</small>")
            })
        </script>
    </body>
</html>

```

效果:

![append.png](https://i.loli.net/2019/08/05/KX4fb2zF5WwhBng.png)


在上面的例子中, 是这么一个结构: `(span>small)*2`, 而不是 `(span+small)*2`.


`.append()` 也可以在页面上选择页面上已有的存在的元素, 然后插在另一个元素里面. 它呢就相当于一个元素的移动.


举例如下:


```html
<!DOCTYPE html>
<html lang="en" dir="ltr">
    <head>
        <meta charset="utf-8">
        <title></title>
        <script src="jquery-3.4.1.js" charset="utf-8"></script>
    </head>
    <body>
        <!-- 把 `<span>` 标签移动到最后一个 `<p>` 标签的里面. -->
        <span id="prostitute">“妓女不能等有了性欲才接客，作家不能等有了灵感才写作，所以，平日也就不能等有了状态才学习。应该做的事，即使勉强，也要坚持......”</span>
        <fieldset>
            <legend>&nbsp;&nbsp;&nbsp;畐国皇室语录&nbsp;&nbsp;&nbsp;</legend>
            <p>“无商不奸~~~~”</p>
            <p>“喜欢是浅浅的爱 爱是深深地喜欢 因为喜欢的我的心才痛的厉害 以为喜欢割舍的时候才难过 我喜欢时你不是我的错 你说对不起时也不是你的错”</p>
            <p>“现在人全搞暧昧 找什么对象?”</p>
            <p>“别给自己锻炼偷懒找借口，一切地方都可以健身。”</p>
            <p>“瓜子吃完了，会也开完了”</p>
            <p>“制度是标准，不是哪一个领导是标准。”</p>
            <p id="empty"></p>
        </fieldset>
        <script type="text/javascript">
            $(document).ready(function () {
                $("#empty").append($("#prostitute"))
            })
        </script>
    </body>
</html>
```


效果:

![append2.png](https://i.loli.net/2019/08/05/rjYqJ7w2EPk61OZ.png)


这个例子里如果被 append 的地方能选出来多个, 那么也会每一个都追加.




#### 2. [`.appendTo()`](https://api.jquery.com/appendTo/)


描述: Insert every element in the set of matched elements to the end of the target. 将匹配的元素插入到目标元素的最后面.(在目标元素的内部插入.)


`.appendTo()` 和 `.append()` 的插入方式是一样的. 只是书写的方式是颠倒的. 这么一说看方法名就可以反应过来了.


举个 `.appendTo()` 的例子:

```html
<!DOCTYPE html>
<html lang="en" dir="ltr">
    <head>
        <meta charset="utf-8">
        <title></title>
        <script src="jquery-3.4.1.js" charset="utf-8"></script>
    </head>
    <body>
        <!-- 把 `<span>` 标签插入到 `<p>` 标签的里面. -->
        <span>我操你妈!</span>
        <p>申帝</p>
        <p>串相</p>
        <script type="text/javascript">
            $(document).ready(function () {
                $("span").appendTo($("p"))
            })
        </script>
    </body>
</html>

```

效果:

![appendTo.png](https://i.loli.net/2019/08/05/saKYABDCNkJ3478.png)


弄好之后就是个 `(p>span)*2` 的结构.



#### 3. [`.html()`](https://api.jquery.com/html/)

描述: Get the HTML contents of the first element in the set of matched elements or set the HTML contents of every matched element. 获取集合中第一个匹配元素的 HTML 内容, 或设置每一个匹配元素的 HTML 内容.


貌似是相当于 JavaScript 中的 [Element​.inner​HTML](https://developer.mozilla.org/en-US/docs/Web/API/Element/innerHTML) .

`.text()` 与 `.html()` 的作用是相同的、差不太多的. 但是呢 `.text()` 与 `.html()` 还有区别. `.html()` 对于获取(也就是 getter 方面)它只能获取到第一个匹配的元素, 而 `.text()` 呢它可以获取到所有匹配的元素; 对于设置元素内容(也就是 setter 方面)它们都能设置到所有的匹配元素里面的内容. 只有获取它俩是不同的.


举例, 实际上这个用过好多遍了, 可以 get 也可以 set...:

```html
<!DOCTYPE html>
<html lang="en" dir="ltr">
    <head>
        <meta http-equiv="Content-Type" content="text/html; charset=utf-8" />
        <title></title>
        <script src="jquery-3.4.1.js" charset="utf-8"></script>
    </head>
    <body>
        <!-- 在控制台中输粗 `<strong>` 标签中的内容. -->
        <div>
            <strong>让规范化、模块化、平台化成为公司常态.</strong>
            <div>
                企业管理规范化的体现：
                <ul>
                    <li>层次清晰</li>
                    <li>责权明确</li>
                    <li>流程高效</li>
                    <li>信息畅达</li>
                </ul>
            </div>
            <div>
                科学规范的制度体系包括如下内容：
                <ul>
                    <li>法人治理 + 战略规划 + 组织结构</li>
                    <li>目标管理 + 岗位绩效 + 权限分配</li>
                    <li>流程管理 + 内控管理 + 信息化</li>
                </ul>
            </div>
        </div>
        <script>
            $(document).ready(function () {
                console.log($("strong").html())
            })
        </script>
    </body>
</html>

```

效果:

![html.png](https://i.loli.net/2019/08/05/w3GuzOnt4LD2Pic.png)


不过适当的有效练习还是有好处的.

再举个 `.html()` 当 setter 用的例子:


```html
<!DOCTYPE html>
<html lang="en" dir="ltr">
    <head>
        <meta http-equiv="Content-Type" content="text/html; charset=utf-8" />
        <title></title>
        <script src="jquery-3.4.1.js" charset="utf-8"></script>
    </head>
    <body>
        <!-- 修改两组 `<li>` 标签中的内容. -->
        <div>
            <strong>让规范化、模块化、平台化成为公司常态.</strong>
            <div>
                企业管理规范化的体现：
                <ul>
                    <li>层次清晰</li>
                    <li>责权明确</li>
                    <li>流程高效</li>
                    <li>信息畅达</li>
                </ul>
            </div>
            <div>
                科学规范的制度体系包括如下内容：
                <ul>
                    <li>法人治理 + 战略规划 + 组织结构</li>
                    <li>目标管理 + 岗位绩效 + 权限分配</li>
                    <li>流程管理 + 内控管理 + 信息化</li>
                </ul>
            </div>
        </div>
        <script>
            $(document).ready(function () {
                $("ul:first > li").html("连续三天erp软件接洽实施会，每天开会超过8小时，厉害word畐国")
                $("ul:last > li").html("制度是标准，不是哪一个领导是标准。制度的唯一好处是你可以跟领导说no")
            })
        </script>
    </body>
</html>
```

效果:

![html2.png](https://i.loli.net/2019/08/05/iWAuTUyDkf8dX5a.png)


申帝是畐国的皇帝、畐国共主、畐国的天. 所以碰到这种申帝允许你做主质疑的事儿, 一定要拍拍脑袋想想、拍拍胸脯问问你自己, 是畐国的制度大还是天大.


同样, 对于右妃这种在畐国一人之下万人之上的核心皇室成员, 一定要保持充分的尊敬.



#### 4. [`.prepend()`](https://api.jquery.com/prepend/)


描述: Insert content, specified by the parameter, to the beginning of each element in the set of matched elements. 将参数内容插入到每个匹配元素的前面.(在目标元素的内部插入.)


举个 `.prepend()` 的例子:

```html
<!DOCTYPE html>
<html lang="en" dir="ltr">
    <head>
        <meta charset="utf-8">
        <title></title>
        <script src="jquery-3.4.1.js" charset="utf-8"></script>
        <style>
            /**
             * 注意这个 `display: inline-block` 的用法, 可以动态调整 `<span>` 标签的宽度.
             * 用 `display: block` 是达不到想要的效果的.
             * 百度一下 “html span自动调整宽度” 你就知道.
             */
            span {
                display: inline-block;
                border: 1px solid red;
            }
        </style>
    </head>
    <body>
        <!-- 在 `<p>` 标签前追加一个公共前缀. -->
        <p>凉了.</p>
        <hr/>
        <p>炸了.</p>
        <script type="text/javascript">
            $(document).ready(function () {
                $("p").prepend("<span>申帝和串相的🐴</span>")
            })
        </script>
    </body>
</html>
```


效果:

![prepend.png](https://i.loli.net/2019/08/05/cfSi4w5VkN6C92z.png)


我这里面用了 `display: inline-block` 的 CSS 手法, 可以参考一下 [What are best practices for using “display: inline-block”](https://stackoverflow.com/questions/11812046/what-are-best-practices-for-using-display-inline-block) . 不过是七年前的文章了, 看官方文档写的这个是 display-legacy 说实话心里也不是很有底. 以后公司来了什么牛逼的前端再问问吧...



#### 5. [`.prependTo()`](https://api.jquery.com/prependTo/)


描述: Insert every element in the set of matched elements to the beginning of the target. 将所有元素插入到目标前面(元素内).(在目标元素的内部插入.)


举个 `.prependTo()` 的例子:


```html
<!DOCTYPE html>
<html lang="en" dir="ltr">
    <head>
        <meta charset="utf-8">
        <title></title>
        <script src="jquery-3.4.1.js" charset="utf-8"></script>
        <style>
            .prefix {
                color: red;
                font-weight: bold;
            }
        </style>
    </head>
    <body>
        <!-- 将公共前缀添加到每个 `<li>` 标签前. -->
        <ul>
            <li>从来都是九死一生, 但我们必须有“亦余心之所善兮, 虽九死其犹未悔”的豪情.</li>
            <li>的盛宴已经摆在我们的面前, 现在唯一的问题是我们的胃口怎么样.</li>
            <li>的磨难, 对于弱者是绊脚石; 对于强者, 则是攀登顶峰的垫脚石.</li>
            <li>是段光谱. 白里透黑。暗里有光. 少年才问黑白, 成年人只看几十度灰.</li>
            <li>的意义不在于那个结果, 而在于享受那个过程.</li>
            <li>不是看到了希望才去坚持, 而是坚持了才会看到希望.</li>
        </ul>
        <script type="text/javascript">
            $(document).ready(function () {
                // 这种情况注意单双引号套着用, 别一双到底.
                $("<span class='prefix'>上市</span>").prependTo($("li"))
            })
        </script>
    </body>
</html>

```

效果:


![prependTo.png](https://i.loli.net/2019/08/05/koRxt9KpTBX2gOH.png)

在上面这个例子中就是 `ul>((li>span)*6)` 这么个结构, 而不是 `ul>(span+li)*6` 的结构.


#### 6. [`.text()`](https://api.jquery.com/text/)

描述: Get the combined text contents of each element in the set of matched elements, including their descendants, or set the text contents of the matched elements. 得到匹配元素集合中每个元素的合并文本, 包括他们的后代, 或是设置匹配元素集合中每个元素的文本内容为指定的文本内容. 


这个 PPT 老不把 or 翻译出来是怎么回事儿...


貌似是相当于 JavaScript 中的 [HTMLElement​.inner​Text](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/innerText) .


视频说在 `.html()` 那会儿讲过了, 所以就不讲了. 也确实不用讲.



### 复制元素(官网上的[Copying](https://api.jquery.com/category/manipulation/copying/))

就一个方法: `.clone()`.


#### [`.clone()`](https://api.jquery.com/clone/)

描述: Create a ***deep copy*** of the set of matched elements. 创建一个匹配的元素集合的***深度拷贝***副本.

关于什么是深拷贝什么是浅拷贝, 我在这边儿写了一个介绍: [深拷贝与浅拷贝](https://liujunyi271828.github.io/2019-08-05/deep-copy-and-shallow-copy/). 就不在这里再搬一次了.


`.clone()` 举例:

```html
<!DOCTYPE html>
<html lang="en" dir="ltr">
    <head>
        <meta charset="utf-8">
        <title></title>
        <script src="jquery-3.4.1.js" charset="utf-8"></script>
    </head>
    <body>
        <!-- 克隆 `<span>` 标签追加到 `<p>` 标签里. 并清空原 `<span>` 标签中的内容  -->
        <p style="color:red;">申畜</p>
        <p style="color:orange;">串犬</p>
        <p style="color:yellow;">申帝</p>
        <p style="color:green;">串相</p>
        <p style="color:cyan;">申国父</p>
        <p style="color:blue;">串亚父</p>
        <span class="copy" style="color:purple;">我透你妈!</span>
        <script type="text/javascript">
            $(function () {
                $(".copy").clone().appendTo("p");
                // `.html()` 方法当 getter 使用时是匹配匹配到的第一个, `.text()`方法 当 setter 使用时是匹配匹配到的所有元素.
                // 注意最好不要拷贝有 id 属性的.
                $(".copy:last").text("")
            })
        </script>
    </body>
</html>
```

效果: 

![clone.png](https://i.loli.net/2019/08/05/fYrzZkd82DgjSqT.png)

最终呈现的视觉效果部分是一个 `(p>span)*6` 的结构. 

官网上提出有这么两点要注意的:

> 1. When using the `.clone()` method, you can modify the cloned elements or their contents before (re-)inserting them into the document.
> 2. Using `.clone()` has the side-effect of producing elements with duplicate `id` attributes, which are supposed to be unique. Where possible, it is recommended to avoid cloning elements with this attribute or using `class` attributes as identifiers instead.
> 3. For performance reasons, the dynamic state of certain form elements (e.g., user data typed into `textarea` and user selections made to a `select`) is not copied to the cloned elements. When cloning `input` elements, the dynamic state of the element (e.g., user data typed into text inputs and user selections made to a checkbox) is retained in the cloned elements.


前两点比较实用, 第三点就是和性能有关了, 我觉着一般人不会拷贝表单这种重要东西的... 当然, 第一点在例子中不会体现, 因为我注意了一下调用的顺序; 第二点的坑在写例子的过程中我倒是踩了, 踩完看页面发现不对就秒懂了...


### DOM 插入到现有元素外(官网上叫[DOM Insertion, Outside](https://api.jquery.com/category/manipulation/dom-insertion-outside/))


四个方法.

1. [`.after()`](https://api.jquery.com/after/)
2. [`.before()`](https://api.jquery.com/before/)
3. [`.insertAfter()`](https://api.jquery.com/insertAfter/)
4. [`.insertBefore()`](https://api.jquery.com/insertBefore/)


下面分别来看一下.


#### 1. [`.after()`](https://api.jquery.com/after/)

描述: Insert content, specified by the parameter, after each element in the set of matched elements. 在匹配元素集合中的每个元素后面插入参数所指定的内容, 作为其兄弟节点.


也没什么可注意的, 除了:

* The [`.append()`](https://api.jquery.com/append/) and [`.appendTo()`](https://api.jquery.com/appendTo/) methods perform the same task. The major difference is in the syntax-specifically, in the placement of the content and target.
* The [`.prepend()`](https://api.jquery.com/prepend/) and [`.prependTo()`](https://api.jquery.com/prependTo/) methods perform the same task. The major difference is in the syntax—specifically, in the placement of the content and target.
* The [`.after()`](https://api.jquery.com/after/) and [`.insertAfter()`](https://api.jquery.com/insertAfter/) methods perform the same task. The major difference is in the syntax—specifically, in the placement of the content and target.
* The [`.before()`](https://api.jquery.com/before/) and [`.insertBefore()`](https://api.jquery.com/insertBefore/) methods perform the same task. The major difference is in the syntax—specifically, in the placement of the content and target.


举个 `.after()` 的例子:


```html
<!DOCTYPE html>
<html lang="en" dir="ltr">
    <head>
        <meta charset="utf-8">
        <title></title>
        <script src="jquery-3.4.1.js" charset="utf-8"></script>
        <style>
            div {
                width: 120px;
                background-color: LightBlue;
            }
        </style>
    </head>
    <body>
        <div>
            <strong style="color:red;">申帝</strong>
            <strong style="color:orange;">串相</strong>
            <strong style="color:yellow;">申畜</strong>
            <strong style="color:green">串犬</strong>
        </div>
        <script type="text/javascript">
            $("strong").after("<em style='color:purple'>我操你妈!</em><br/>")
        </script>
    </body>
</html>

```


效果:


![after.png](https://i.loli.net/2019/08/06/75rudwhiWseF6z4.png)



这个结构是一个 `div>((strong+em+br)*4)` 的结构. 顺便日常关怀一下吃人血馒头的高新技术企业的领导. 既然开始玩了就要遵守游戏规则; 一旦犯了错就要承担后果, 不要成天想着撤销记录(2019-08-05: 去安监局, 沟通撤销记录的事)撤销黑名单(2019-07-29: 去安监局, 解决撤销黑名单事宜). 难道你还想再砸死个人?



#### 2. [`.before()`](https://api.jquery.com/before/)


描述: Insert content, specified by the parameter, before each element in the set of matched elements. 根据参数设定, 在匹配元素的前面插入内容.(在目标元素的外部插入.)

<!-- TODO: .before() 的例子有一处代码需要改, 就是统一插入那块儿的内容. 晚上回家登录一下看看. -->


举个 `.before()` 的例子:


```html
<!DOCTYPE html>
<html lang="en" dir="ltr">
    <head>
        <meta charset="utf-8">
        <title></title>
        <script src="jquery-3.4.1.js" charset="utf-8"></script>
        <style>
            strong {
                color: green;
            }
        </style>
    </head>
    <body>
        <span>才华横溢的高级工程师.</span><br/>
        <span>成功青年企业家, 霸业的继承者.</span><br/>
        <span>在畐国学历最高的MBA专硕申硕士.</span><br/>
        <span>真·斜杠青年.</span><br/>
        <script type="text/javascript">
            $("span").before("<strong>Dear 申: </strong>")
        </script>
    </body>
</html>

```


效果:


![before.png](https://i.loli.net/2019/08/08/VXTRqnW43PchpZb.png)


#### 3. [`.insertAfter()`](https://api.jquery.com/insertAfter/)

描述: Insert every element in the set of matched elements after the target. 在目标元素后面插入集合中每个匹配的元素(插入的元素作为目标元素的兄弟元素.)

举个 `.insertAfter()` 的例子:


```html
<!DOCTYPE html>
<html lang="en" dir="ltr">
    <head>
        <meta charset="utf-8">
        <title></title>
        <script src="jquery-3.4.1.js" charset="utf-8"></script>
        <style>
            div {
                width: 120px;
                background-color: LightBlue;
            }
        </style>
    </head>
    <body>
        <div>
            <strong style="color:red;">申帝</strong>
            <strong style="color:orange;">串相</strong>
            <strong style="color:yellow;">申畜</strong>
            <strong style="color:green">串犬</strong>
        </div>
        <script type="text/javascript">
            $("<em style='color:purple'>不得好死.</em><br/>").insertAfter("strong")
        </script>
    </body>
</html>
```


效果:

![insertAfter.png](https://upload.cc/i1/2019/08/08/wIgxLK.png)




#### 4. [`.insertBefore()`](https://api.jquery.com/insertBefore/)


描述: Insert every element in the set of matched elements before the target. 在目标元素前面插入集合中每个匹配的元素(插入的元素作为目标元素的兄弟元素.)

举个 `.insertBefore()` 的例子:


```html
<!DOCTYPE html>
<html lang="en" dir="ltr">
    <head>
        <meta charset="utf-8">
        <title></title>
        <script src="jquery-3.4.1.js" charset="utf-8"></script>
    </head>
    <body>
        <p>广大员工要这样做——</p>
        <ul>
            <li><span>爱岗奉献的热情转化为创造产值的不竭动力,</span></li>
            <li><span>科研成果应用在建设GCZY高新技术企业的伟大事业中,</span></li>
            <li><span>人生理想融入到实现公司全面崛起上市梦的不懈奋斗中.</span></li>
        </ul>
        <script type="text/javascript">
            $(function () {
                $("<b style='color:red;'>把</b>").insertBefore($("span"))
            })
        </script>
    </body>
</html>

```


效果:

![insertBefore.png](https://i.loli.net/2019/08/07/o2nqf5COAMITsxR.png)


也确实是 `p+(ul>(li>(b+span))*3)` 的结构.


### 什么是 DOM


在看下一章 **DOM 移除**之前, 我们先看一下什么是 DOM.

不多说, 上官网看一下: 

1. [Document Object Model (DOM)](https://developer.mozilla.org/en-US/docs/Web/API/Document_Object_Model) 
2. [Introduction to the DOM](https://developer.mozilla.org/en-US/docs/Web/API/Document_Object_Model/Introduction)
3. [Examples of web and XML development using the DOM](https://developer.mozilla.org/en-US/docs/Web/API/Document_Object_Model/Examples)


这几篇文章, 对 DOM 有一个初步的认识. 


划重点:

* The **Document Object Model** (**DOM**) is the data representation of the objects that comprise the structure and content of a document on the web.
* The **Document Object Model** (**DOM**) is a programming interface for HTML and XML documents. 


所以才能:

> The **Document Object Model** (**DOM**) connects web pages to scripts or programming languages by representing the structure of a document—such as the HTML representing a web page—in memory.
> 
> The DOM represents a document with a logical tree.

如果有哪个面试官问 DOM 是什么然后还对这个回答不满意的, 让它滚回去看文档, 问问是它们公司牛逼还是 MDN 牛逼.

想起我很久一起拿面一个叫华宇信息的地方的 Java 也是, 面试的那个人问我面向对象有几大特性, 然后我把封装继承多态挨个给它解释了一遍, 结果问我还有吗还有吗, 我不知道是它耳朵进水了导致少听了一两个点呢, 还是它的脑子被办公室的门给夹了.


### DOM 移除(官网上叫[DOM Removal](https://api.jquery.com/category/manipulation/dom-removal/))


DOM 移除有这四个方法:



1. `.detach()`
2. `.empty()`
3. `.remove()`
4. `.unwrap()`


#### 1. [`.detach()`](https://api.jquery.com/detach/)


描述: Remove the set of matched elements from the DOM. 从 DOM 中去掉所有匹配的元素.

注意: The `.detach()` method is the same as [`.remove()`](https://api.jquery.com/remove/), except that `.detach()` keeps all jQuery data associated with the removed elements. This method is useful when removed elements are to be reinserted into the DOM at a later time.



举个 `.detach()` 的例子:

```html
<!DOCTYPE html>
<html lang="en" dir="ltr">
    <head>
        <meta charset="utf-8">
        <title></title>
        <script src="jquery-3.4.1.js" charset="utf-8"></script>
    </head>
    <body>
        <!-- 移除 class 为 "target" 的元素. -->
        <!-- 移除所有的 span 元素. -->
        <p class="target">世界上最好的老板，没有之一。祝开心、健康永远永远…</p>
        <span>申帝我操你妈!</span>
        <div>我爱畐国, 愿你越来越好, 你我一起共同进步成长🎉🎉🎉</div>
        <div>兄弟姐妹们公司虽然不年轻，但是咱们人年轻有干劲，我虽然不可能像马云当年带领十八罗汉创造现在的淘宝，但是我相信一点只要给我的机遇我一定会像马元当年那样抓住我不敢说能创造未来，但是我一定能让大家感觉因为在畐国上班而自豪，我不希望大家是畐国的看客和过客，而是一个可以依靠终身的伴侣，这是一个大家庭，一个有活力的大家庭，有未来发展的大家庭，公司不是一个人的，是全体的。</div>
        <strong>艹申畜和串犬的🐴三千次.</strong>
        <em>申畜和串犬不得好死.</em>
        <script type="text/javascript">
            $(function () {
                $("div").detach()
                $("p").detach(".target")
            })
        </script>
    </body>
</html>

```


效果:


![detach](https://upload.cc/i1/2019/08/08/aqBt7s.png)


移除完以后, 就是 `span+strong+em` 的结构.


如果在 `.detach()` 中传参的话, 它会进一步用参数的这个选择器来过滤调用方法的对象元素.



#### 2. [`.empty()`](https://api.jquery.com/empty/)


描述: Remove all child nodes of the set of matched elements from the DOM. 从 DOM 中移除集合中匹配元素的所有子节点. 

`.empty()` method removes not only child (and other descendant) elements, but also any text within the set of matched elements. This is because, according to the DOM specification, any string of text within an element is considered a child node of that element.

举个 `.empty()` 的例子:

```html
<!DOCTYPE html>
<html lang="en" dir="ltr">
    <head>
        <meta charset="utf-8">
        <title></title>
        <script src="jquery-3.4.1.js" charset="utf-8"></script>
    </head>
    <body>
        <!-- 删除 menu3 这个 class 下的所有元素. -->
        <div class="wrapper" id="wrapperWrappingNav">
            <div class="sidenav menu1">
                <ul>
                    <div class="left"></div>
                    <li><a href="product/biguocloud_service.html" >畐国云服务</a></li>
                    <li><a href="product/rfid_automatic_remote_identity_management_system.html" >RFID远距离自动识别管理系统</a></li>
                    <li><a href="product/biguo_integration_operations_management_platform.html" >畐国综合运维管理平台</a></li>
                    <li><a href="product/intelligent_video_analytics_management_system.html" >畐国视频智能分析管理系统</a></li>
                    <li><a href="product/remote_poe_switch.html" >畐国远距离POE大功率供电交换机</a></li>
                    <li><a href="product/easy_life.html" >Easy Life</a></li>
                    <div class="right"></div>
                </ul>
            </div>
            <div class="sidenav menu2">
                <ul>
                    <div class="left"></div>
                    <li><a href="service/infomation_system_integration.html" >信息系统集成服务</a></li>
                    <li><a href="service/intelligent_systems_engineering.html" >智能化系统工程服务</a></li>
                    <li><a href="service/intelligent_systems_consultation_and_design.html" >智能化系统咨询设计服务</a></li>
                    <li><a href="service/it_operation_and_maintenance.html" >IT运维服务</a></li>
                    <li><a href="service/it_planning_consultation.html" >IT规划咨询服务</a></li>
                    <li><a href="service/data_room_construction.html" >数据机房建设服务</a></li>

                    <div class="right"></div>
                </ul>
            </div>
            <div class="sidenav menu3">
                <ul>
                    <div class="left"></div>
                    <li><a href="case/administrative_office.html" >行政办公</a></li>
                    <li><a href="case/city_comprehensive_architecture.html" >城市综合馆</a></li>
                    <li><a href="case/industry_building.html" >工业厂房</a></li>
                    <li><a href="case/apartment_building.html" >高端住宅</a></li>
                    <li><a href="case/shopping_mall.html" >商业广场</a></li>
                    <li><a href="case/hotel.html" >豪华酒店</a></li>
                    <li><a href="case/medical_nourishment_project.html" >医养项目</a></li>
                    <li><a href="case/financial_project.html" >金融项目</a></li>
                    <li><a href="case/4S_car_shop.html" >汽车精品4S店</a></li>
                    <div class="right"></div>
                </ul>

            </div>
            <div class="sidenav menu4">
                <ul>
                    <div class="left"></div>
                    <li><a href="aboutbg/our_introduction.html">公司概况</a></li>
                    <li><a href="aboutbg/honor_and_qualification.html">荣誉资质</a></li>
                    <li><a href="aboutbg/our_culture.html">企业文化</a></li>
                    <li><a href="aboutbg/our_vision.html">企业自勉</a></li>
                    <li><a href="aboutbg/research_achievement.html">科研成果</a></li>
                    <li><a href="aboutbg/jobs.html" >招贤纳士</a></li>
                    <div class="right"></div>
                </ul>
            </div>
        </div>
        <script type="text/javascript">
            $(".menu3").empty()
        </script>
    </body>
</html>

```


效果:


![empty](https://upload.cc/i1/2019/08/08/jFNCke.png)


使用 `.empty()` 的话不用传参数.

关于畐国我知道得不多, 唯一能建议的是能不找他们做项目就不找他们做项目, 除非你关系就是硬就是能找着他们人给你修时常罢工的各种解决方案.





#### 3. [`.remove()`](https://api.jquery.com/remove/)


描述: Remove the set of matched elements from the DOM. 将匹配元素集合从 DOM 中删除.(同时移除元素上的事件及 jQuery 数据).


这个视频里没讲. 



#### 4. [`.unwrap()`](https://api.jquery.com/unwrap/)


描述: Remove the parents of the set of matched elements from the DOM, leaving the matched elements in their place. 将匹配元素集合的父级元素删除, 保留自身(如果存在兄弟元素的话也保留兄弟元素)在原来的位置.


这个在前面讲过了: 在 DOM 插入并包裹现有内容 - `.unwrap()` 那块儿.


### DOM 替换(官网上叫[DOM Replacement](https://api.jquery.com/category/manipulation/dom-replacement/))

DOM 替换有这两个方法:

1. `.replaceAll()`
2. `.replaceWith()`



#### 1. [`.replaceAll()`](https://api.jquery.com/replaceAll/)

描述: Replace each target element with the set of matched elements.  用集合的匹配元素替换每个目标元素.

举个 `.replaceAll()` 的例子: 

```html
<!DOCTYPE html>
<html lang="en" dir="ltr">
    <head>
        <meta charset="utf-8">
        <title></title>
        <script src="jquery-3.4.1.js" charset="utf-8"></script>
        <style>
            .origin {
                color: red;
            }
            .fake {
                color: green;
                font-weight: bolder;
            }
        </style>
    </head>
    <body>
        <!-- 将 div 中的 class 为 origin 的元素都换成 fake 的 class. -->
        <div>
            <p><span class="origin">XM</span> AI艺术摄像机解决方案</p>
            <p><span class="origin">WG</span> 门禁解决方案</p>
            <p><span class="origin">HBX</span> 云停车场解决方案</p>
            <p><span class="origin">WWBT</span> 网络交换解决方案</p>
            <p><span class="origin">XM</span> 视频平台及存储解决方案</p>
            <p><span class="origin">匿名过期网线</span>综合布线解决方案</p>
        </div>
        <script type="text/javascript">
            $(function () {
                // 要用于更换的内容作为调用方法的对象.
                $("<span class='fake'>SCD </span>").replaceAll($(".origin"))
            })
        </script>
    </body>
</html>

```


效果:

![replaceAll](https://upload.cc/i1/2019/08/08/CQsoB4.png)


还是给换成 `div>((p>span)*7)` 的结构.




#### 2. [`.replaceWith()`](https://api.jquery.com/replaceWith/)

描述: Replace each element in the set of matched elements with the provided new content and return the set of elements that was removed. 用提供的内容替换集合中所有匹配的元素并且返回被删除元素的集合.


视频里说这个用得比较少. 那就自己去看官网文档吧.


### 通用属性操作(官网上叫[General Attributes](https://api.jquery.com/category/manipulation/general-attributes/))


五个方法:

1. `.attr()`
2. `.prop()`
3. `.removeAttr()`
4. `.removeProp()`
5. `.val()`



都在 [DOM 属性](https://api.jquery.com/category/attributes/) 里有, 前面也写过了. 有疑问往回翻.


### CSS 属性(官网上叫 [Style Properties](https://api.jquery.com/category/manipulation/style-properties/))


有以下这些方法:


1. [`.css()`](https://api.jquery.com/css/)
2. [`.height()`](https://api.jquery.com/height/)
3. [`.width()`](https://api.jquery.com/width/)
4. [`.innerHeight()`](https://api.jquery.com/innerHeight/)
5. [`.innerWidth()`](https://api.jquery.com/innerWidth/)
6. [`.offset()`](https://api.jquery.com/offset/)
7. [`.outerHeight()`](https://api.jquery.com/outerHeight/)
8. [`.outerWidth()`](https://api.jquery.com/outerWidth/)
9. [`.position()`](https://api.jquery.com/position/)
10. [`.scrollLeft()`](https://api.jquery.com/scrollLeft/)
11. [`.scrollTop()`](https://api.jquery.com/scrollTop/)
12. [`jQuery.cssNumber`](https://api.jquery.com/jQuery.cssNumber/)


最后那个 [`jQuery.cssNumber`](https://api.jquery.com/jQuery.cssNumber/) 视频里没讲, 官网上也没示例, 所以这个自己看看文档再查查资料差不多就完事儿了.


现在我们来看打算讲的那些.


#### 1. [`.css()`](https://api.jquery.com/css/)


描述: Get the value of a computed style property for the first element in the set of matched elements or set one or more CSS properties for every matched element. 获取匹配元素集合中的第一个元素的 computed 样式属性的值, 或设置每个匹配元素的一个或多个 CSS 属性.


对于 computed 这个词视频里没提到. 不过官网上说:

> Note that the *computed style* of an element may not be the same as the value specified for that element in a style sheet. For example, computed styles of dimensions are almost always pixels, but they can be specified as em, ex, px or % in a style sheet. Different browsers may return CSS color values that are logically but not textually equal, e.g., #FFF, #ffffff, and rgb(255,255,255).


不过我记得似乎好像不建议拿 jQuery 直接操作属性, 而是对 HTML 元素进行添加或删除 class 的操作.


举个 `.css()` 的例子:


```html
<!DOCTYPE html>
<html lang="en" dir="ltr">
    <head>
        <meta charset="utf-8">
        <title></title>
        <script src="jquery-3.4.1.js" charset="utf-8"></script>
        <style media="screen">
            span {
                color: yellow;
                /* #D8BFD8: Thistle */
                background-color: Thistle;
            }
        </style>
    </head>
    <body>
        <p>串犬不得好死.</p>
        <span >像申畜这样的东西活着, 别人就不能活.</span>
        <script type="text/javascript">
            $(function () {
                $("p").css({
                    'color': 'red',
                    'font-weight': 'bold'
                })
                console.log($("span").css('background-color'))
            })
        </script>
    </body>
</html>
```


效果:


![css](https://upload.cc/i1/2019/08/16/z4vDxl.png)


对于 `color`、`background-color` 这种的, 会返回一个 rgb 的那种 24 位真彩色向量, 每一个分量的值都是以十进制值给出. 如果你前面在 CSS 里写一个十六进制的颜色值, 那么最后在 console 里也仍然会输出十进制表示.

可以同时在 `.css()` 方法中同时传多组值, 那样的话就是传一个 JSON 串或是值为 JSON 串的 JS 对象过去. JSON 虽然平时写得比较少, 但是可以看看 Sublime Text 下的 Preferences > Settings 里人家是怎么写的.



#### 2. [`.height()`](https://api.jquery.com/height/)


描述: Get the current computed height for the first element in the set of matched elements or set the height of every matched element. 获取匹配元素集合中的第一个元素的当前计算高度值, 或设置每一个匹配元素的高度值.


也是集 getter 和 setter 于一体.





#### 3. [`.width()`](https://api.jquery.com/width/)

描述: Get the current computed width for the first element in the set of matched elements or set the width of every matched element. 获取匹配元素集合中的第一个元素的当前计算高度值, 或是设置每一个匹配元素的高度值.

下面举个 `.height()` 和 `.width()` 的例子:

```html
<!DOCTYPE html>
<html lang="en" dir="ltr">
    <head>
        <meta charset="utf-8">
        <title></title>
        <script src="jquery-3.4.1.js" charset="utf-8"></script>
        <style media="screen">
            div {
                background-color: black;
                color: white;
                width: 450px;
                height: 200px;
                padding: 30px;
                margin: 10px;
                border: 2px solid green;
            }
        </style>
    </head>
    <body>
        <div>沉痛悼念畐国人民的老朋友: 丶贵人.<br/>
            丶贵人永远是申帝最忠诚的走狗.<br/>
            丶贵人永远和申帝穿一条裤子.<br/>
        </div>
        <script type="text/javascript">
            // 获取 div 元素的宽度和高度.
            $(function () {
                var divObj = $("div")
                divObj.height(150)
                divObj.width(300)
                console.log('div元素的宽度为: ' + divObj.width())
                console.log('div元素的高度为: ' + divObj.height())
            })
        </script>
    </body>
</html>

```


效果:

![为畜作伥](https://upload.cc/i1/2019/08/16/UyHZVD.png)

`.width()` 和 `.height()` 这两个方法都是读取或修改内容的宽度/高度. 至于为啥要说这两点, 后面会提到.


#### 4. [`.innerHeight()`](https://api.jquery.com/innerHeight/)

描述: Get the current computed inner height (including padding but not border) for the first element in the set of matched elements or set the inner height of every matched element. 为匹配的元素集合中获取第一个元素的当前计算内部高度值, 包括 padding, 但是不包括 border. 

视频里少写了: ...或是设置每个匹配元素的 inner height. 

上面的描述中文版原先是写的当前计算高度值, 没交代内部. 要是我的话, 我要么就不翻 inner height 要么就翻成内部高度, 光翻成高度明显是有问题的.

可以当 getter 也可以当 setter.


#### 5. [`.innerWidth()`](https://api.jquery.com/innerWidth/)


描述: Get the current computed inner width (including padding but not border) for the first element in the set of matched elements or set the inner width of every matched element. 为匹配的元素集合中获取第一个元素的当前计算内部宽度值, 包括 padding, 但是不包括 border.

原来的翻译也是没有翻译或翻出后半句以及 inner width. 

也应该在后面加上: ...或是设置每个匹配元素的 inner width. 

同上, 也是既可以当 getter 又可以当 setter.


举个 `.innerHeight()` 和 `.innerWidth()` 的例子:

```html
<!DOCTYPE html>
<html lang="en" dir="ltr">
    <head>
        <meta charset="utf-8">
        <title></title>
        <script src="jquery-3.4.1.js" charset="utf-8"></script>
        <style media="screen">
            div {
                background-color: black;
                color: white;
                width: 300px;
                height: 150px;
                padding: 30px;
                margin: 10px;
                border: 2px solid green;
            }
        </style>
    </head>
    <body>
        <div>申畜死个🐴.<br/>
            串犬死个🐴.<br/>
            艹申畜和串犬的🐴三千次.<br/>
        </div>
        <script type="text/javascript">
            // 获取 div 元素的宽度和高度.
            $(function () {
                var divObj = $("div")
                divObj.height(100)
                divObj.width(200)
                console.log('div元素的内部宽度为: ' + divObj.innerWidth())
                console.log('div元素的内部高度为: ' + divObj.innerHeight())
            })
        </script>
    </body>
</html>

```


效果:

![.innerHeight() and .innerWidth()](https://upload.cc/i1/2019/08/16/6v1cad.png)


#### 6. [`.offset()`](https://api.jquery.com/offset/)

描述: Get the current coordinates of the first element, or set the coordinates of every element, in the set of matched elements, relative to the document. 在匹配的元素集合中, 获取的第一个元素的当前坐标, 这个坐标是相对于文档的; 或是设置匹配的元素集合中每一个元素的坐标, 坐标也是相对于文档.

也是又可以当 setter 又可以当 getter.


下面举个 `.offset()` 方法的例子:

```html
<!DOCTYPE html>
<html lang="en" dir="ltr">
    <head>
        <meta charset="utf-8">
        <title></title>
        <script src="jquery-3.4.1.js" charset="utf-8"></script>
        <link rel="stylesheet" href="css-reset.css">
        <style>
            div {
                width: 300px;
                float: left;
                height: 200px;
                padding: 50px;
                margin-left: 20px;
                margin-top: 50px;
                border: 2px solid green;
            }
        </style>
    </head>
    <body>
        <a href="https://mp.weixin.qq.com/s/P7G15dSFhl4kwUriduPmmQ">
            <img src="https://i.loli.net/2019/08/22/OLlmX9oH2pgBR4W.png" alt="2025十大趋势" style="height: 400px; margin-left: 50px;"/>
        </a>
        <div>花厂发布了 2025 年十大趋势, 但是在另一条时间线上, 2023 年长皇后因为与申帝感情破裂而将其刺杀, 顿时畐国陷入群龙无首的状态, 江山陷入一片风雨飘摇中. 少年天子兀太子临危受命登基准备挽救败局未果, 最终于 2025 年决定将畐国栋梁、辽警秘密搜查官の女右阿姨的意识传送至 2015 年我们当前的时间线去结识申帝. 由 2019 年时候的年轻版右阿姨、亦即畐国圣女/女子亲卫队队长/SCD 队长右皇妃去入驻畐国诱惑申帝, 实现右皇妃的成功上位, 保护申帝免于被刺杀的黑暗命运. </div>
        <script type="text/javascript">
            $(function() {
                var div = $("div")
                console.log(div.offset())
            })
        </script>
    </body>
</html>

```


其中用到的这个 css-reset.css 如下, 以后不再赘述:

```css
/* CSS reset */
body {
	font: 14px Microsoft YaHei, arial, verdana, sans-serif;
}

body, div, p, form, ul, ol, li, dl, dt, dd, h1, h2, h3, h4, h5, h6 {
	margin: 0;
	padding: 0;
}

img {
	border:0;
}

ul, ol {
	list-style: none;
}

table {
	border-collapse: collapse;
	border-spacing: 0;
}

a:hover {
	color: #BB1E13;
}

a:link, a:visited {
	color: #333;
	text-decoration: none;
	outline: none;
}

```


效果:

![offset.png](https://i.loli.net/2019/08/22/ldHvXk3cOFWuD7N.png)

再举个 `.offset()` 作为 setter 的例子:

```html
<!DOCTYPE html>
<html lang="en" dir="ltr">
    <head>
        <meta charset="utf-8">
        <title></title>
        <script src="jquery-3.4.1.js" charset="utf-8"></script>
        <!-- 洗掉以前的 CSS, 具体代码在 18-manipulation-32 里给过. -->
        <link rel="stylesheet" href="css-reset.css">
        <style>
            div {
                width: 300px;
                float: left;
                height: 200px;
                padding: 50px;
                margin-left: 20px;
                margin-top: 50px;
                border: 2px solid green;
            }
        </style>
    </head>
    <body>
        <div>在我们当前时间线2023年11月16日的时候, 畐国已经倒闭了. 在片片初雪中, 申帝来到畐国的废墟, 独坐在残破的台阶上, 回忆着往事. 想起当他爱右妃的时候, 会觉得右妃就是一个天使, 特别可爱, 成天上班玩手机逛淘宝看小说从来不收拾垃圾堆一样的工位桌面这些都不是事儿; 但当他恨右妃的时候, 她就比魔鬼还可怕, 右妃从前那些喂鱼、为申帝满上议事偏殿桌上的瓜子、充当申帝的健身私教、向畐国共主申帝献祭出肉身的种种好都记不得了. 总之, 不管他是如何想的, 现在一切都灰飞烟灭了. 一想到这里, 申帝眼眶中的热泪就情不自禁簌簌落下来.</div>
        <script type="text/javascript">
            var div = $("div")
            var coordinates = {
                top: 100,
                left: 80
            }
            div.offset(coordinates)
            console.log(div.offset())
        </script>
    </body>
</html>

```

效果:

![offset-set.png](https://i.loli.net/2019/08/22/4c6GZVYNJnUoukS.png)

#### 7. [`.outerHeight()`](https://api.jquery.com/outerHeight/)

描述: Get the current computed outer height (including padding, border, and optionally margin) for the first element in the set of matched elements or set the outer height of every matched element. 获取元素集合中第一个元素的当前计算外部高度值, 包括 padding, border 和选择性的 margin, 返回一个整数(不包含 "px")表示的值, 就是返回一个 number 类型, 或者呢如果在一个空集合上调用该方法, 则会返回为 `undefined`(视频里说的返回为 `null`, 这是因为视频里用的是 jQuery 2.x.x, 而官方文档上说: “If called on an empty set of elements, returns `undefined` (`null` before jQuery 3.0)”); 或是设置每个匹配元素的 outer width. 

视频里这翻译真捉鸡, 以我上面写的为准.


传进来的参数中不指定是否包含 margin 时, 缺省值是不包含 margin 的.

既可以当 setter 又可以当 getter 的方法.



#### 8. [`.outerWidth()`](https://api.jquery.com/outerWidth/)


描述: Get the current computed outer width (including padding, border, and optionally margin) for the first element in the set of matched elements or set the outer width of every matched element. 获取元素集合中第一个元素的当前计算外部宽度值, 包括 padding, border 和选择性的 margin, 返回一个整数(不包含 "px")表示的值, 就是返回一个 number 类型, 或者呢如果在一个空集合上调用该方法, 则会返回为 `undefined`(官方文档上说: “If called on an empty set of elements, returns `undefined` (`null` before jQuery 3.0)”); 或是设置每个匹配元素的 outer width. 


传进来的参数中不指定是否包含 margin 时, 默认是不包含 margin 的.


也是既可以当 setter 又可以当 getter 的方法.

举个 `.outerHeight()` 和 `.outerWidth()` 的例子:


```html
<!DOCTYPE html>
<html lang="en" dir="ltr">
    <head>
        <meta charset="utf-8">
        <title></title>
        <link rel="stylesheet" href="css-reset.css">
        <!-- 洗掉以前的 CSS, 具体代码在 18-manipulation-32 里给过. -->
        <style>
            div {
                width: 300px;
                float: left;
                height: 100px;
                padding: 50px;
                margin-left: 100px;
                margin-top: 40px;
                border: 2px solid green;
            }
        </style>
        <script src="jquery-3.4.1.js" charset="utf-8"></script>
    </head>
    <body>
        <div>
            <cite>
                AI 这两个字现在变得和网红一样廉价, 罪魁祸首就是狗贼这种侮辱技术的乐色.
            </cite>
        </div>
        <script type="text/javascript">
            $(function() {
                var div = $("div")
                console.log(`div 的外部高度(不算 margin)为: ` + div.outerHeight())
                console.log(`div 的外部宽度(不算 margin)为: ` + div.outerWidth())
                console.log(`div 的外部高度(算上 margin)为: ` + div.outerHeight(true))
                console.log(`div 的外部宽度(算上 margin)为: ` + div.outerWidth(true))
            })
        </script>
    </body>
</html>

```

效果:

![outer-width-and-outer-height.png](https://i.loli.net/2019/08/22/dr9yb5JpAV4xa7M.png)


#### 9. [`.position()`](https://api.jquery.com/position/)


描述: Get the current coordinates of the first element in the set of matched elements, relative to the offset parent. 获取匹配元素中第一个元素的当前坐标, 相对于 offset parent 的坐标.(offset parent 指离该元素最近的而且被定位过的祖先元素)


和 `.offset()` 方法的对比:

> The `.position()` method allows us to retrieve the current position of an element (specifically its margin box) <span style="color:grey;font-style:italic">relative to the offset parent</span> (specifically its padding box, which excludes margins and borders). Contrast this with [`.offset()`](https://api.jquery.com/offset/), which retrieves the current position <span style="color:grey;font-style:italic">relative to the document</span>. When positioning a new element near another one and within the same containing DOM element, `.position()` is the more useful.
> 
> Returns an object containing the properties `top` and `left`.


使用场合、坑点说明:

> **Note:** jQuery does not support getting the position coordinates of hidden elements or accounting for margins set on the `<html>` document element.
> 
> ---
> 
> The number returned by dimensions-related APIs, including `.position()`, may be fractional in some cases. Code should not assume it is an integer. Also, dimensions may be incorrect when the page is zoomed by the user; browsers do not expose an API to detect this condition.


举个 `.position()` 的例子:


```html
<!DOCTYPE html>
<html lang="en" dir="ltr">
    <head>
        <meta charset="utf-8">
        <title></title>
        <link rel="stylesheet" href="css-reset.css"/>
        <script src="jquery-3.4.1.js" charset="utf-8"></script>
        <style>
            div {
                padding: 20px;
                background-color: antiquewhite;
            }
            p {
                margin-left: 10px;
                background-color: aquamarine;
            }
        </style>
    </head>
    <body>
        <div>
            <p>
                那话咋说来着，上帝给你关了个啥，然后就会给你开了个啥，就是老天想让你挣钱，怎么都会挣，就是的安排点小插曲😜 ，活在当下，别想那么多，该吃吃，该喝喝，别老天天难为自己，天天当思想家，不如当头不思考的🐷
            </p>
            <script type="text/javascript">
                // 获取 p 标签相对于 div 标签的坐标.
                console.log($("p").position())
            </script>
        </div>
    </body>
</html>

```



效果:

![position.png](https://i.loli.net/2019/08/22/JYCB8TNzufUIhHa.png)


以及和 `.offset()` 方法的对比:


```html
<!DOCTYPE html>
<html lang="en" dir="ltr">
    <head>
        <meta charset="utf-8">
        <title></title>
        <link rel="stylesheet" href="css-reset.css"/>
        <script src="jquery-3.4.1.js" charset="utf-8"></script>
        <style>
            div {
                padding: 20px;
                background-color: antiquewhite;
            }
            .delta {
                /**
                 * 要控制元素在页面上的位置, 得先选择定位方案. 定位方案有 4 种: 静态(static)、相对(relative)、绝对(absolute)和固定(fixed). 要指定元素使用的定位方案, 可使用 CSS 属性 `position`.
                 */
                position: absolute;
                left: 100px;
                top: 60px;
            }
            p {
                margin-left: 10px;
                background-color: aquamarine;
            }
        </style>
    </head>
    <body>
        <div>
            <p>
                那话咋说来着，上帝给你关了个啥，然后就会给你开了个啥，就是老天想让你挣钱，怎么都会挣，就是的安排点小插曲😜 ，活在当下，别想那么多，该吃吃，该喝喝，别老天天难为自己，天天当思想家，不如当头不思考的🐷
            </p>
            <script type="text/javascript">
                // 获取 p 标签相对于 div 标签的坐标.
                console.log(`向 div 添加位置改变量之前 p 元素的 position 为: ` + `top: ` + $("p").position().top + `, left: ` + $("p").position().left)
                console.log(`向 div 添加位置改变量之前 p 元素的 offset 为: ` + `top: ` + $("p").offset().top + `, left: ` + $("p").offset().left)

                // 向 p 元素的祖灵元素 div 添加一个 class 用于改变 div 的位置.
                $("div").toggleClass("delta")

                console.log(`向 div 添加位置改变量以后 p 元素的 position 为: ` + `top: ` + $("p").position().top + `, left: ` + $("p").position().left)
                console.log(`向 div 添加位置改变量以后 p 元素的 offset 为: ` + `top: ` + $("p").offset().top + `, left: ` + $("p").offset().left)
            </script>
        </div>
    </body>
</html>

```

效果:

![position-demo.png](https://i.loli.net/2019/08/22/2pPfiYKswgV7CE6.png)


#### 10. [`.scrollLeft()`](https://api.jquery.com/scrollLeft/)

描述: Get the current horizontal position of the scroll bar for the first element in the set of matched elements or set the horizontal position of the scroll bar for every matched element. 获取匹配的元素集合中第一个元素的当前水平滚动条的位置; 或是设置每个匹配元素的水平滚动条位置.

既可以当 getter 用也可以当 setter 用.


#### 11. [`.scrollTop()`](https://api.jquery.com/scrollTop/)

描述: Get the current vertical position of the scroll bar for the first element in the set of matched elements or set the vertical position of the scroll bar for every matched element. 获取匹配的元素集合中第一个元素的当前垂直滚动条的位置; 或是设置每个匹配元素的垂直滚动条位置.

既可以当 getter 又可以当 setter.


作为这一章的结束, 下面我们举个 `.scrollLeft()` 和 `.scrollTop()` 的例子, 并赏析一下畐国共主申帝的文学作品作为彩蛋:


```html
<!DOCTYPE html>
<html lang="en" dir="ltr">
    <head>
        <meta charset="utf-8">
        <title></title>
        <script src="jquery-3.4.1.js" charset="utf-8"></script>
        <style>
            h2 {
                font-style: italic;
            }
            .test {
                width: 300px;
                height: 420px;
                overflow: auto;
                margin-top: 5px;
                margin-left: 60px;
                padding: 5px;
                position: relative;
                border: 3px solid #666666;
                background-color: #cccccc;
            }
            .p1 {
                width: 400px;
                height: 300px;
                margin: 10px;
                padding: 5px;
                border: 2px solid red;
            }
            .p2 {
                width: 450px;
                height: 350px;
                margin: 10px;
                padding: 30px;
                border: 2px solid yellow;
            }
            .p3 {
                width: 350px;
                height: 550px;
                margin: 10px;
                padding: 20px;
                border: 2px solid green;
            }
        </style>
    </head>
    <body>
        <div class="test">
            <h2>申帝散文选</h2>
            <p class="p1">
                曾几何时，气势恢宏的厂房大楼，富丽堂皇的办公室，风华正茂的年薪副总，各类叱咤职场月薪过万的总监，如今他们已不在江湖，我还在江湖打听他们的传说。也在思考一些问题，团队固然重要，但团队也跟资本走，有资本有项目组建团队很容易，没资本团队随时也可以鸟兽散。即使有团队，创业的核心灵魂人物还是创业者本人，创业者自己必须要有主心骨，知道自己要干什么，因为最终替全局负责和买单的还是创业者本人，团队的职业经理人，用好了是这个赢利机器中的良性链条，用不好只是过客，而且走时不该少的你什么也少不了他的。兵不在多而在乎精，企业不在大小在乎赢利能力。如果不能避开恶性竞争实现创新完成产业升级，就算再会玩市场最终也会累死在市场上，当企业已经没有了健康的现金流，离死也就不远了。
            </p>
            <p class="p2">
                从没想过有一天，自己想吃一碗碳水牛肉面，也需要给自己找一个理由。人的第一个青春是老天和父母给的，第二个青春是要靠自己努力，现在我经常提醒自己要注意自己的身体，虽然心里已经很变态，但身体一定要健康。上有老，下有小，还有一些志同道合的兄弟需要养家。选择了就不能放弃，负担起责任需要好的身体。今天一天真的很忙碌，刚才跟哥们打电话开玩笑说我上午开标，下午开庭，就差晚上来个人开房了。没个强大的内心和健壮的体魄，早就被这些妖魔鬼怪打倒了，恋爱期的多巴胺能分泌四个月，跑步期的多巴胺能分泌一辈子，来，再努力一下子，想想前段时间大姐的那句话永远相信美好的事情即将发生，只要能一直走下去，哪有那么多一切安好，童话终究是童话，选对了方向，就得靠自己努力。这一年就这么过去了，感谢老天给了那么多的历练，不忘初心，方得始终，我会更好的走下去。
            </p>
            <p class="p3">
                时间都去哪了，转眼又过了一年，除了年龄的增长，所谓的人生阅历也在逐渐丰富。做项目就是一场在人间的修行，一个项目认识了一些人，又疏远了一些人，总是在和不同的人打交道，男的女的，老的少的，有些一样，又有些不一样，没有绝对的好人，也没有绝对的坏人，一个圈子，就是一个小小的缤纷世界。曾几何时，从天真浪漫，到再也不相信别人只言片语，不知何时有了从语态就知道别人说谎的能力，我本善良，真的希望我的判断是错觉，但多的还是失望。一个圈子，就像一池子的水，当水清氧气充足的时候，鱼儿活的自由自在都会把自己最美丽最优雅的一面展现给别人欣赏，当水干缺氧的时候，就不会顾及自己的优雅，拼命翻腾，争取一口喘息。人生如戏，戏如人生，自己永远不是自己这出戏的编剧，拼命工作的人都过上了拼命工作的生活，老天不会承诺你的任何努力都会有等值的回报，我们只是人生的过客，珍惜当下，不和别人对比，开心过好每一天，是对自己最好的负责。格局的大小取决于所处的圈子和圈子的人，当这个圈子谎话连篇，乌烟瘴气，有谁还敢说自己有什么样的格局，知止可以不殆，考虑换个健康的生态圈，该给自己提上日程了，2019，我的37岁阳光生活。
            </p>
        </div>
        <script type="text/javascript">
            var test = $(".test")
            test.scrollTop(240)
            console.log(`垂直滚动条滚动的距离为: ` + test.scrollTop())
            test.scrollLeft(168)
            console.log(`水平滚动条滚动的距离为: ` + test.scrollLeft())
        </script>
    </body>
</html>

```

效果:

![scroll.png](https://i.loli.net/2019/08/22/bxuWvUBJCO5d3zc.png)


除了通过这个例子学习技术外, 申帝深厚的文学底蕴亦由此可见一斑. 至于文中提到的妖魔鬼怪是谁, 我想申帝早已有了答案: 咬住嘴里肉不松口的无耻甲方。。。狼心狗肺忘恩负义的乱臣贼子。。。烂泥糊不上墙的公司蛆虫。。。岁月催人老的结发之妻。。。

好了, Style roperties 要讲的方法就都讲完了... Manipulation 这一章也讲完了, 写了三十六个 HTML 文件, 吐血...


## jQuery 遍历


不少都感觉似曾相识...

仔细看了下快捷键表, 原来 macOS 上在 MWeb 里插入链接是 shift + control + L, 了解了...


### [过滤 Filtering](https://api.jquery.com/category/traversing/filtering/)


过滤总共有九个方法.


#### 1. [`.eq()`](https://api.jquery.com/eq/)

描述: Reduce the set of matched elements to the one at the specified index. 减少匹配元素的集合为指定的索引的哪一个元素.


注意这个是按照索引值等于多少多少来, 而不是按照属性值或内容值之类的.


可以正着数, 也可以传一个负值参数进去从末尾往回数:

> Providing a negative number indicates a position starting from the end of the set, rather than the beginning.


举个 `.eq()` 的例子:


```html
<!DOCTYPE html>
<html lang="en" dir="ltr">
    <head>
        <meta charset="utf-8">
        <title></title>
        <script src="jquery-3.4.1.js" charset="utf-8"></script>
        <style>
        </style>
    </head>
    <body>
        <!-- 由 ul>(li{list item $$}*6) 生成. -->
        <!-- 我们为 list item 03、list item 05 添加背景色等样式. -->
        <ul>
            <li>list item 01</li>
            <li>list item 02</li>
            <li>list item 03</li>
            <li>list item 04</li>
            <li>list item 05</li>
            <li>list item 06</li>
        </ul>
        <script type="text/javascript">
            $(function () {
                $("ul li").eq(2).css({
                    'background-color': 'green',
                    'width': '200px'
                })
                // 负值就是从最后一个往回数.
                // 倒数第一个对应 -1 索引值, 倒数第二个对应 -2 索引值, 以此类推.
                $("li").eq(-2).css({
                    'width': '240px',
                    'background-color': 'yellow'
                })
            })
        </script>
    </body>
</html>

```

效果:

![eq.png](https://i.loli.net/2019/08/23/Xd8ZMTbaAkh1Bl3.png)

再就注意下这玩意儿和 [`:eq()` 选择器](https://api.jquery.com/eq-selector/)是不一样的... `:` 加上 xxx, 不就是类似伪类那种东西么; 而这个 `.eq()` 则是 `obj.方法名()`, 也就是由对象调用方法...

#### 2. [`.filter()`](https://api.jquery.com/filter/)

描述: Reduce the set of matched elements to those that match the selector or pass the function's test. 筛选元素集合中匹配表达式或通过传递函数测试的那些元素集合.


就是说 `.filter()` 这个方法呢它是可以定位多个元素的, 而 `.eq()` 这个方法呢它只是能定位到一个元素.

过滤方式如下:

![`.filter()`传参类型.png](https://i.loli.net/2019/08/23/hW978zYoBRCfig1.png)

至于传函数进去, 就类似于往 PHP 的 `array_filter()` 这个函数里传 callable 类型的 `$callback` 进去, 这个 `$callback` 就是一个用于过滤的函数, 返回 boolean 类型的值. 返回 true 的才会留下, 返回 false 的申帝也不会让它留下. 

举个 `.filter()` 的例子:


```html
<!DOCTYPE html>
<html lang="en" dir="ltr">
    <head>
        <meta charset="utf-8">
        <title>操申帝和串相的🐴三千次</title>
        <script src="jquery-3.4.1.js" charset="utf-8"></script>
        <style>
            p {
                width: 150px;
                background-color: aquamarine;
                float: left;
                margin-left: 10px;
            }
        </style>
    </head>
    <body>
        <!-- 分别改变索引值为奇数和索引值为4的倍数(索引值都是从 0 开始)的 li 标签内容值. -->
        <ul>
            <li>list item 01</li>
            <li>list item 02</li>
            <li>list item 03</li>
            <li>list item 04</li>
            <li>list item 05</li>
            <li>list item 06</li>
        </ul>
        <p>串相陪同申大帝亲临紫御现场，下基层与一线工人肩并肩，慰问一线职工，并带去慰问品：隆力奇花露水。广大员工围坐在花露水钱内牛满面，这体现了领导对一线员工的关怀。</p>
        <p class="middle">有的申和串活着, 它们已经死了; 有的申和串活着, 别人就不能活.</p>
        <p class="middle">窖藏假酒夜光杯，欲饮琵琶马上催</p>
        <p class="middle">跨海大桥明月夜, 队长何处教吹箫</p>
        <p>是挺难受的, 地产就那几家, ZF 性质的还干不了, 地产那几家得罪的也都差不多了, 串犬该骂的骂过该吵的吵过.</p>
        <script type="text/javascript">
            $("li").filter(":odd").html("申畜我操你妈!")
            $("li").filter(function (index) {
                return (index % 4 === 0)
            }).html("串犬我操你妈!")
            $("p").filter(".middle").css("border", "2px solid red")
        </script>
    </body>
</html>
```

不加 jQuery 代码渲染的原版:


![原版](https://upload.cc/i1/2019/08/23/eU38nZ.png)


应用 jQuery 代码的效果:


![filter](https://upload.cc/i1/2019/08/23/qUJfhc.png)


#### 3. [`.first()`](https://api.jquery.com/first/)

描述: Reduce the set of matched elements to the first in the set. 获取匹配元素集合中的第一个元素.



#### 4. [`.last()`](https://api.jquery.com/last/)

描述: Reduce the set of matched elements to the final one in the set. 获取匹配元素集合中的最后一个元素.

`.first()` 方法和 `.last()` 方法在使用时都不接收参数.


下面举个 `.first()` 方法和 `.last()` 方法的例子:

```html
<!DOCTYPE html>
<html lang="en" dir="ltr">
    <head>
        <meta charset="utf-8">
        <title></title>
        <script src="jquery-3.4.1.js" charset="utf-8"></script>
        <style media="screen">
            li {
                width: 350px;
            }
            .backgroundColor {
                background-color: red;
            }
            .font {
                font-style: italic;
                font-weight: bolder;
                color: red;
            }
        </style>
    </head>
    <body>
        <!-- 给第一个 li 标签和最后一个 li 标签分别添加样式. -->
        <ul>
            <li>2018年5月29日，凯丹置地（大连）有限公司向你单位发出《中标通知书》，将大连东港区C12地块项目（凯丹广场）三期弱电工程发包给你单位施工，你单位将该弱电工程施工劳务分包给没有施工劳务资质的大连东丽智能网络科技有限公司，且未与大连东丽智能网络科技有限公司签订安全生产管理协议。</li>
            <li>2018年7月28日10时30分左右，东港区C12地块项目, C2#10层弱电井内桥架安装作业过程中，发生物体打击事故,造成1人死亡，直接经济损失126万元，死者张志新系大连东丽智能网络科技有限公司员工，事发时未戴安全帽。</li>
            <li>此次事故为一起一般生产安全责任事故，且你单位对事故发生负有责任。</li>
            <li>给予处人民币210,000.00元（贰拾壹万元）罚款的行政处罚</li>
        </ul>
        <script type="text/javascript">
            $("li").first().toggleClass("backgroundColor")
            $("li").last().toggleClass("font")
        </script>
    </body>
</html>

```

效果:

![first-and-last.png](https://i.loli.net/2019/08/23/FEelQvS12irnyBC.png)



#### 5. [`.has()`](https://api.jquery.com/has/)


描述: Reduce the set of matched elements to those that have a descendant that matches the selector or DOM element. 筛选匹配元素集合中的那些有相匹配的选择器或 DOM 元素的后代元素.

这个翻译的啥几把玩意儿. 注意这个是过滤到具有 xx 后代元素的那些父元素乃至祖灵元素. 不是定位到 xx 元素下的后代元素. 要是由我来翻译的话, 我会这么翻译:

<cite style="color:grey;">将匹配的元素集合缩小到那些仅具有匹配某选择器或匹配 DOM 元素的后代的元素构成的集合.</cite>

可能写得不太通顺, 但是问题是人家官方文档的这两个定语从句写得也是尾大不掉啊...总之信达雅的信我肯定是达到了.


下面看个 `.has()` 方法的例子:


```html
<!DOCTYPE html>
<html lang="en" dir="ltr">
    <head>
        <meta charset="utf-8">
        <title></title>
        <script src="jquery-3.4.1.js" charset="utf-8"></script>
        <style>
            span {
                background-color: yellow;
            }
        </style>
    </head>
    <body>
        <div>
            <p class="target-1">每件作品只仅一幅，世界上独一无二的作品。</p>
            <p>无论是装裱于家中和办公室，还是作为增值收藏品，或是馈赠亲朋好友、客户、领导的礼品，都是最佳的选择。</p>
            <div class="target-1">
                <span>一千多元的画可以送出几万元的档次，画的作者如果去世，更是增值数十倍，这就是为何北京、广州、上海拥有无数收集朝鲜画工作者的重要原因之一。</span>
            </div>
            <p class="target-2">本店长年从朝鲜采购一手画家名画，更常请朝鲜画家来中国现场作画，如有需求，请关注我们店铺的直播。</p>
            <div class="target-2">
                <cite>狗逼是不是天天盼着人家往生极乐</cite>
            </div>
        </div>
        <script>
            $(".target-1").has("span").css({
                "padding": "6px",
                "background-color": "orange",
                "border": "4px solid green"
            })
            $(".target-2").has("cite").css("border", "4px solid grey")
        </script>
    </body>
</html>

```

效果:

![has](https://upload.cc/i1/2019/08/23/nQt5kY.png)


#### 6. [`.is()`](https://api.jquery.com/is/)


描述: Check the current matched set of elements against a selector, element, or jQuery object and return `true` if at least one of these elements matches the given arguments. 判断当前匹配的元素集合中的元素是否为一个选择器/DOM 元素/jQuery 对象, 如果这些元素至少一个匹配给定的参数, 那么返回 `true`.

注意这个 `.is()` 的用法:

![is用法.png](https://i.loli.net/2019/08/23/xb4p3fS6D1EL9iA.png)

传个 function 类型进去, 也行吧. 反正 function 是 JS 里的一等公民, 就类似串相右妃木贵人之类的核心皇室成员在畐国的地位. 官网说什么我就信什么, 反正要错也不是我的错.


不管是文档里写到的这个方法的签名格式还是下面这句话

> Unlike other filtering methods, `.is()` does not create a new jQuery object. Instead, it allows you to test the contents of a jQuery object without modification. This is often useful inside callbacks, such as event handlers.


都很明确告诉你了, 这个东西返回 Boolean 对象...所以很明显就不应该指望靠它返回一个 jQuery 对象.



我们来举一个 `.is()` 的例子:

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

![is.png](https://i.loli.net/2019/08/23/5qgZjMQtDoImXHC.png)


申帝考的 MBA 这种专硕虽然含金量低了一些而且从结果来看确实没体现出申帝学会了什么管理技巧, 但是从本质上 MBA 这玩意儿确实算是硕士. 虽说孽畜不受待见, 但咱也不能信口开河歪曲事实, 所以文中的这位申校长确有硕士之名.


#### 7. [`.not()`](https://api.jquery.com/not/)


描述: Remove elements from the set of matched elements. 从匹配的元素集合中移除指定的元素.


三种用法:

![not用法.png](https://i.loli.net/2019/08/23/5X8M6Ox1Dymnrow.png)


不过我习惯的好像还是用选择器😂


下面我们举一个 `.not()` 的例子:

```html
<!DOCTYPE html>
<html lang="en" dir="ltr">
    <head>
        <meta charset="utf-8">
        <title>孽畜不得好死.</title>
        <script src="jquery-3.4.1.js" charset="utf-8"></script>
    </head>
    <body>
        <img style="width:800px;" src="https://i.loli.net/2019/08/23/WNuGeiy8rZRd2Ah.png" alt="5265行脚本"/>
        <!-- 除了下标为奇数的 li 标签外, 剩下的 li 标签都加上个样式. -->
        <ul>
            <li>还记得之前弄平台的时候, 第二天要开会, 搞得我前一天晚上通宵在大道整理数据, 好不容易整理完了. 结果领导见我, 说: 别以为我不知道你在大道干什么.</li>
            <li>卧槽, 哈哈.</li>
            <li>领导真是机智!</li>
            <li>对</li>
            <li>然后在会上对我进行了语重心长的教育. 羞愧, 让领导为我担心了.</li>
            <li>我怎么记得好像还问过你在大道干什么, 怎么总在那, 是不是在玩, 在吃饭在逛街.</li>
            <li>完全可以这么理解啊! 对啊! 没人看着我. 怎么能确保我不是在逛街呢!</li>
        </ul>
        <script type="text/javascript">
            $("li").not(":odd").css("background-color", "aquamarine")
        </script>
    </body>
</html>

```


效果:

![not](https://upload.cc/i1/2019/08/23/y1LaiD.png)


每次看到那个 `<img>` 标签的内容我都会非常激动. 不说一辈子都忘不了, 起码也是好几年都难忘.


#### 8. [`.map()`](https://api.jquery.com/map/)


描述: Pass each element in the current matched set through a function, producing a new jQuery object containing the return values. 通过一个函数来匹配当前集合中的每个元素, 并且产生一个包含返回值的 jQuery 对象.

是不是和 PHP 数组的 `array_map()` 方法比较像哪.

下面我们举一个 `.map()` 方法的例子:


```html
<!DOCTYPE html>
<html lang="en" dir="ltr">
    <head>
        <meta charset="utf-8">
        <title>申帝的管理智慧</title>
        <link rel="stylesheet" href="css-reset.css">
        <script src="jquery-3.4.1.js" charset="utf-8"></script>
        <style media="screen">
            p {
                width: 600px;
            }
        </style>
    </head>
    <body>
        <!-- 遍历打出每一个 p 标签的 HTML 文本内容. -->
        <p id="p01">200块钱这种巨款，不但能搞定甲方关系，还能再填三百搞定300多万项目的关系，意义重大怎么能随便挥霍，这可是上市资金。</p>
        <p id="p02">这种搞定甲方关系的设备虽然不稳定，但是也正是因为此可以让我司人员勤与甲方走动，拉近两方关系，具有重大的战略意义。</p>
        <p id="p03">上次一听 teambition 给畐国这个规模的公司用都要收费, 然后用这个 teambition 的想法就无疾而终了。再就晚上召开公司代表大会, 当时五六个人开，用的“全时云会议”这个 APP，免费试用一个月，好像是这样，然后一年4000左右收费，也是胎死腹中了。</p>
        <p id="p04">我认为申帝这次必定一定肯定乃至于甚至是必须会做出遵循内心的选择。两百块钱，都够给甲方领导家买一个 NVR 了</p>
        <script>
            $("p").map(function () {
                console.log($(this).html())
            })
        </script>
    </body>
</html>

```


效果:

![map.png](https://i.loli.net/2019/08/23/pomPiaIkRd8s7rH.png)


再举个原生 JavaScript 里的 `.map()` 方法的例子:


```html
<!DOCTYPE html>
<html lang="en" dir="ltr">
    <head>
        <meta charset="utf-8">
        <title></title>
    </head>
    <body>
        <script type="text/javascript">
            var array1 = [1, 2, 3, 5, 8]
            result1 = array1.map(callback = function (element) {
                return element ** 3
            })
            console.log(result1)
            var array2 = [1, 3, 4, 7, 11, 18, 29]
            result2 = array2.map(callback = function (element) {
                return Math.pow(element, 2)
            })
            console.log(result2)
        </script>
    </body>
</html>

```

效果:

![原生map](https://i.loli.net/2019/08/23/CHox1lyevIiruQP.png)

不要像视频里那样说这个原生方法是 jQuery 里的就行. 因为我根本就没看着 jQuery 文档里说原生 JS 里的东西(我就先用这个词吧, 不会犯错)能够调用这个方法😂文档诚不我欺也.


#### 9. [`.slice()`](https://api.jquery.com/slice/)


描述: Reduce the set of matched elements to a subset specified by a range of indices. 根据指定的下标范围, 过滤匹配的元素集合, 并生成一个新的 jQuery 对象.

这里原来的方法没提到会新生成. 但是在后面有说:

> Given a jQuery object that represents a set of DOM elements, the `.slice()` method constructs a new jQuery object containing a subset of the elements specified by the `start` and, optionally, `end` argument. The supplied `start` index identifies the position of one of the elements in the set; if `end` is omitted, all elements after this one will be included in the result.



举个 `.slice()` 的例子:


```html
<!DOCTYPE html>
<html lang="en" dir="ltr">
    <head>
        <meta charset="utf-8">
        <title></title>
        <link rel="stylesheet" href="css-reset.css">
        <script src="jquery-3.4.1.js" charset="utf-8"></script>
    </head>
    <body>
        <!-- 为 p 元素集合指定下标范围的部分添加样式. -->
        <p>菊厂发布了 2025 年十大趋势, 但是在另一条时间线上, 2023 年长皇后因为与申帝感情破裂而将其刺杀, 顿时畐国群龙无首, 江山陷入一片风雨飘摇中. 兀太子由串相㐅大将艹帅等一干旧臣扶持临危受命登基挽救败局未果, 最终于 2025 年决定拼尽畐国最后的国力将畐国栋梁、辽警秘密搜查官の女右阿姨的意识传送至 2015 年我们当前的时间线, 让那时的右阿姨在久光百货结识了申帝. 由年轻版右阿姨、亦即畐国圣女/女子亲卫队队长/Scdiler 队长右皇妃在 2019 年入主畐国诱惑申帝促使申帝尽快抛弃结发之妻, 实现右皇妃的成功上位, 同时刻苦练拳并充当申帝的健身私教, 与厶将军羽将军等死士一同保护申帝免于刺杀, 避免畐国走向不可知的结局.</p>
        <p>2023年11月16日的时候, 畐国已经倒闭了. 在片片初雪中, 申帝来到畐国的废墟, 独坐在残破的台阶上, 回忆着往事. 想起当他爱右妃的时候, 会觉得右妃就是一个天使, 特别可爱, 成天上班玩手机逛淘宝看小说从来不收拾垃圾堆一样的工位桌面这些都不是事儿; 但当他恨右妃的时候, 她就比魔鬼还可怕, 右妃从前那些喂鱼、为申帝满上议事偏殿桌上的瓜子、充当申帝的健身私教、向公司共主献祭出肉身的种种好都记不得了. 总之, 不管自己是如何想的, 现在一切都灰飞烟灭了. 一想到这里, 申帝眼眶中的热泪就情不自禁簌簌落下来.</p>
        <p>
            申帝陪右妃去久光百货逛街, 右妃看中一条裙子可没带钱, 申帝借钱给她. 右妃问他: 有女朋友吗? 申帝说没有. 右妃踮起脚尖, 提起裙摆转了一圈, 问申帝: 好看吗? 申帝: 好看. 右妃说: 男朋友买的. 申帝一巴掌抽过去: 明明是我给的钱, 你是不是不想还了?&#x21A9;<br/>
            然后右妃委屈地看着申帝, 申帝突然意识到了什么, 问道: 难道, 你想让我做你男朋友? 右妃羞哒哒地点了点头, 申帝反手又是一巴掌: 你TM果然不想还了.&#x21A9;<br/>
            右妃心灰意冷, 拿钱砸到申帝的脸上, 一脸决然地走了. 看着右妃的背影, 申帝觉得心好痛. 他捡起钱, 追上右妃又是一巴掌: 妈的, 原来你有钱, 还一直磨磨蹭蹭不想给.
        </p>
        <p>
            畐二世申帝长期将下属当佣人，有无偿提供特殊服务的、有自愿帮其打通和项目经理关系的、有免费加班帮助申帝完成任务的、更有甚者还有天天中午从现场跑来为其送饭的……许多下属长期被申帝奴役，敢怒不敢言。&#x21A9;<br/>
            为了求得内心宁静，申帝曾去过西藏的星隐寺、四川的碧莲寺以及山西、福建等著名宗教景点敬香。2018年10月，某活佛到昆明活动，申帝赶到活佛驻地拜见，皈依到大师名下，取名为“窝槽尼玛”。&#x21A9;<br/>
            除此之外，申帝还带风水先生到办公室看风水、设佛龛、挂字画，用公款非法购买字画乃至资金，连鱼缸里鱼的颜色及条数都按大师的“点拨”布局。有时申帝抽不开身，又不愿错过“良辰吉时”，就安排亲信妖女右皇妃轮班到议事殿的佛堂代替自己跪拜、做法事。
        </p>
        <p>右妃修剪畐国名贵花朵的这种否定之否定的过程, 从内容上看, 是自己动态调整自己、自己长期完善自己的过程; 从形式上看, 是螺旋式上升或波浪式前进, 方向是前进上升的, 道路是迂回曲折的, 是前进性与曲折性的统一.</p>
        <script type="text/javascript">
            $("p").slice(2, 4).css("background-color", "pink")
        </script>
    </body>
</html>

```

效果:

![slice](https://upload.cc/i1/2019/08/23/vr4WOq.png)

注意坑点:

> Given a jQuery object that represents a set of DOM elements, the `.slice()` method constructs a new jQuery object containing a subset of the elements specified by the `start` and, optionally, `end` argument. The supplied `start` index identifies the position of one of the elements in the set; if `end` is omitted, all elements after this one will be included in the result.
> 
> The jQuery `.slice()` method is patterned after the JavaScript .slice() method for arrays. One of the features that it mimics is the ability for negative numbers to be passed as either the `start` or `end` parameter. If a negative number is provided, this indicates a position starting from the end of the set, rather than the beginning.

注意如果是传双参数进去的话就是左闭右开这么选. 再一个就是可以传负值参数进去, 这个和本节开头提到的 `.eq()` 方法类似. 你传两个负值参数的话也是左闭右开那么选.

你如果只传一个负值的话, 那就是从倒数第(负值的相反数)个开始(包括端点)往后面数.

你也可以传前负后正的两参数, 而且确实能用, 但我觉着还是活着最重要, 方法能用就行, 这么瞎比写不是给自己找麻烦么...

再一个就是怎么在 HTML 页面打出 emoji 的问题, 我是参考了 [How To Insert Emojis In HTML 😀😁😜](https://linuxwebdevelopment.com/how-to-insert-emojis-in-html/), 此外有需要的时候这个也比较有用: [Full Emoji List, v12.0](https://unicode.org/emoji/charts/full-emoji-list.html).


这个方法和 JS 的 `.slice()` 比较像, 和 PHP 的 `substr()` 以及 `array_slice()` 还是有差别的...

一个 emoji 表情怎么转成一个 HTML entity 呢, 除了直接粘以外, 比较简单的操作就是: 

1. 先找到你要打的 emoji 的 Unicode code point value 还不 Unified 值, 总之它要么以 `U+` 开头, 要么就是一个十六进制数, 智商没问题的话肯定能认出这玩意儿.
2. 下面我们以 `1F474` 或 `U+1F474` 为例, 我们主要是要的是后者的 `U+` 后面的部分(不包括那个 `U+`), 也就是说我们主要是要的前者. Anyway, 最终我们要的是  `1F474`. 
3. 然后我们在 `1F474` 前面加上 `&#x`, 在 `1F474` 后面加上一个 `;`, 也就是说整出个我们常见的 HTML entity 的那种格式. 总之, 一顿操作以后, 应该是会得出: `&#x1F474;`.
4. 当然了, 你把 `&#x1F474;` 粘到 HTML 代码里就完事儿了, 也就是说它是这么个玩意儿: &#x1F474;

上面提到的那个 Full Emoji List, v12.0 除了看码以外还有个功能是看 emoji 在各平台的支持情况. 当然不同浏览器对于这个东西的显示情况可能是不同的, 再就可能有的不一定会给你按照你设想的那么显示. 主要是如果碰到这个相关的事儿的话该怎么敲这个😂


### [其他遍历(这他喵的不就是遍历杂项么, 专业点儿) Miscellaneous Traversing](https://api.jquery.com/category/traversing/miscellaneous-traversal/)


官网上遍历杂项共有六个:


1. [`.add()`](https://api.jquery.com/add/)
2. [`.addBack()`](https://api.jquery.com/addBack/)
3. [`.andSelf()`](https://api.jquery.com/andSelf/): 这个方法在 jQ 1.8 中就不建议用了, 在 jQ 3.0 中被逐出上市队伍. 看样子意思好像是作为 `.addBack()` 方法的别名.
4. [`.contents()`](https://api.jquery.com/contents/)
5. [`.end()`](https://api.jquery.com/end/)
6. [`.not()`](https://api.jquery.com/not/)


这里视频讲三个比较常用的:


#### [`.add()`](https://api.jquery.com/add/)


描述: Create a new jQuery object with elements added to the set of matched elements. 添加元素到匹配的元素集合.

`.add()` 的用法还是比较多的:


![add用法.png](https://i.loli.net/2019/08/26/SHAaOZY1vK2kxWU.png)


可以加入五种参数.


下面举一个 `.add()` 方法的例子:

```html
<!DOCTYPE html>
<html lang="en" dir="ltr">
    <head>
        <meta charset="utf-8">
        <title></title>
        <script src="jquery-3.4.1.js" charset="utf-8"></script>
        <style>
            div {
                height: 300px;
                color: blue;
            }
            p {
                height: 50px;
            }
            .border {
                border: 3px solid green;
                margin: 10px;
            }
            .common {
                width: 100px;
                float: left;
                background-color: orange;
            }
        </style>
    </head>
    <body>
        <!-- 为 div 和 p 添加一个统一样式. -->
        <div>我对刻录的印象一直停留在把申帝和右妃啪啪啪小视频刻到阳光一照发出炫彩的光的光盘里的那个时代.</div>
        <div>申帝戴上无限手套，一个响指，右妃的衣服就少了一半.</div>
        <div>跑累了申帝就在背后的垫子上艹一会儿右，然后提上裤子心满意足地发出一条四点半召开公司代表大会的微信消息.</div>
        <div>想要雕刻曲面需要加物理支架额外加3万，申帝一听我操他妈的一个机器5万一个曲轴平台加3万这他妈的让人坑了，于是开始虐待咱们了，疯狂而毫无意义的实验开始了.</div>
        <div>右妃施展法力，拿出爱疯一挥，划出了一道能容纳申帝的空间裂缝.</div>
        <p>申帝故事集</p>
        <script type="text/javascript">
            $("div").toggleClass("border").add("p").toggleClass("common")
        </script>
    </body>
</html>

```

效果:

![.add()](https://upload.cc/i1/2019/08/26/ibocW7.png)

右妃拿出肾 X 那段很有生化奇兵无限里伊丽莎白打开 tear 的既视感😂



#### [`.contents()`](https://api.jquery.com/contents/)


描述: Get the children of each element in the set of matched elements, including text and comment nodes. 获得匹配元素集合中每个元素的子元素, 包括文字和注释节点.

 `.contents()` 方法和树遍历里的 `.children()` 方法类似. 只不过 `.contents()` 包括文字和注释节点而 `.children()` 不包括:

>  The `.contents()` and `.children()` methods are similar, except that the former includes text nodes and comment nodes as well as HTML elements in the resulting jQuery object. Please note that most jQuery operations don't support text nodes and comment nodes. The few that do will have an explicit note on their API documentation page.


举个 `.contents()` 的例子:

```html
<!DOCTYPE html>
<html lang="en" dir="ltr">
    <head>
        <meta charset="utf-8">
        <title></title>
        <script src="jquery-3.4.1.js" charset="utf-8"></script>
    </head>
    <body>
        <test>
            <div>这是一个 ELEMENT_NODE.</div>
            而这是一个 TEXT_NODE. 申帝你妈炸了.
            <p>这又是个 ELEMENT_NODE.</p>
            这又是一个 TEXT_NODE. 串相你妈凉了.
            <!-- 这是一个 COMMENT_NODE. -->
            <!-- 申帝我操你妈! -->
            <!-- 串相我操你妈! -->
            <!-- 申畜不得好死! -->
            <!-- 串犬不得好死! -->
        </test>
        <!-- 为元素节点、文本节点添加样式效果. 打印注释节点内容. -->
        <script type="text/javascript">
            $(function () {
                var elements = $("test").contents().filter(function () {
                    return this.nodeType === 1
                })
                elements.css({
                    "color": "red",
                    "border": "2px solid green"
                })
                var texts = $("test").contents().filter(function () {
                    return this.nodeType === 3
                })
                texts.wrap("<em><strong>")
                var comments = $("test").contents().filter(function () {
                    return this.nodeType === 8
                })
                console.log(`注释条数: ` + comments.length)
                for (var item of comments) {
                    console.log(item)
                }
            })
        </script>
    </body>
</html>

```

效果如下:


![contents代码结构+效果.png](https://i.loli.net/2019/08/26/9eFfJwvoqnKuHVa.png)


JavaScript 循环目前写得还比较少, 基本不会坑的也就是会写 `for` 了😂

虽说写得少, 不过看看文档也就完事儿了:

* [Web technology for developers > JavaScript > JavaScript reference > Statements and declarations > for](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/for)
* [Web technology for developers > JavaScript > JavaScript reference > Statements and declarations > for...in](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/for...in)
* [Web technology for developers > JavaScript > JavaScript reference > Statements and declarations > for...of](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/for...of)
* [Web technology for developers > JavaScript > JavaScript reference > Statements and declarations > while](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/while)
* [Web technology for developers > JavaScript > JavaScript reference > Statements and declarations > do...while](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/do...while)

再就还有个异步版的 for-of 循环, for-await-of:

* [Web technology for developers > JavaScript > JavaScript reference > Statements and declarations > for await...of](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/for-await...of)

现在一般都懒得看 xDxN 之类的地方上的东西了, 一方面这些东西也都是互相抄, 再一方面儿还有些比较那啥的人说看这个缺少自学能力, 所以我就直接撸文档了😂

说白了, JS 的这个 for-in 循环相当于(拿伪代码演示一下):

```javascript
for (key in collection) {
    // do your product 干出你的产值
}
```

注意 JavaScript 里的这个 for-in 循环遍历的是集合中的键, 如果要相应值的话得需要你拿集合配合键去获取. 这种骚操作以前不管是在腰子 C、Java 还是 PHP 都没见过...之前就是想当然就直接拿 for-in 写了, 然后就得到了不想要的结果. 

而 JS 的这个 for-of 循环则相当于(也是拿伪代码演示一下):

```javascript
for (value of collection) {
    // do your product 干出你的产值
}
```

JavaScript 里的这个 for-of 循环遍历的才是集合中的值, 也就是我们在腰子 C 里看到的 for-in 循环(`for (obj in collection)`)(腰子 C 这个好像只能遍历高级类型, 好久不写了😂)、PHP 里的 foreach-as 循环(`foreach (collection as key[ => value])`)、Java 里的 foreach 循环(`for (value : collection)`). 


while 类的循环用得比较少, 不过说实话, do-while 循环很少有符合思维习惯的时候😂


#### [`.end()`](https://api.jquery.com/end/)


描述: End the most recent filtering operation in the current chain and return the set of matched elements to its previous state. 终止在当前链的最新过滤操作, 并返回匹配的元素的以前状态.


举一个 `.end()` 方法的例子:

```html
<!DOCTYPE html>
<html lang="en" dir="ltr">
    <head>
        <meta charset="utf-8">
        <title></title>
        <script src="jquery-3.4.1.js" charset="utf-8"></script>
        <style media="screen">
            p {
                width: 450px;
            }
            .love-right-delilah {
                font-weight: bold;
                color: green;
            }
            .love-company {
                font-style: italic;
                color: red;
            }
        </style>
    </head>
    <body>
        <div>
            <!-- 给 .love-xxx 的 p 标签添加一个样式.-->
            <p class="delilah love-right-delilah">申帝和右妃从相遇到后来这一系列的事儿, 也算是始于才华, 陷于颜值, 忠于人品.</p>
            <p class="delilah love-right-delilah">右妃让申帝回想起了曾经的那个邻家小妹.</p>
            <p>赵师傅说过申帝对婚姻曾经动摇过。如果不是因为生了儿都要离婚.</p>
            <p>申帝被爱的火焰蒙蔽了双眼.</p>
            <p class="company love-company">如果把整个 SCD 大楼鱼缸的水倒出, 也浇不熄我对公司爱的火焰. 整个鱼缸的水全部倒得出吗? 可以. 所以, 是的. 我爱公司.</p>
            <p class="company love-company">世间最真挚的爱莫过于对公司的爱. —— 萧伯纳</p>
            <p class="company love-company">要广泛宣传表彰热爱公司回报公司、为公司上市事业作出突出贡献的优秀人才, 在广大员工中大力弘扬爱岗奉献精神.</p>
        </div>

        <script type="text/javascript">
            // 注意 .find() 方法是在调用方法的对象的 descendants 里找, 而不是找具有要 find 的什么什么性质的那部分调用对象.
            $("div").find(".delilah").addClass("love-right-delilah").end().find("company").addClass("love-company")
        </script>
    </body>
</html>

```

效果如下:

![end.png](https://i.loli.net/2019/08/26/Bm1eYvOTxcZVhj7.png)

自 2015 年开始, 右妃便存在申帝深深的脑海里. 一想到这些年来, 平时那么张扬热衷表现好大喜功的申帝居然能几年如一日默默地守护这份见不得光的奸情, 我不禁感动得落下泪来.


就是在一次性调用所需要的所有方法有些用, 但是还是应该注意可读性.


### [树遍历 Tree Traversal](https://api.jquery.com/category/traversing/tree-traversal/)

jQuery 3.4.1 时代的官网上总共有这么 14 个方法, 视频里我们也会讲这些:


1. [`.children()`](https://api.jquery.com/children/)
2. [`.closest()`](https://api.jquery.com/closest/)
3. [`.find()`](https://api.jquery.com/find/)
4. [`.next()`](https://api.jquery.com/next/)
5. [`.nextAll()`](https://api.jquery.com/nextAll/)
6. [`.nextUntil()`](https://api.jquery.com/nextUntil/)
7. [`.offsetParent()`](https://api.jquery.com/offsetParent/)
8. [`.parent()`](https://api.jquery.com/parent/)
9. [`.parents()`](https://api.jquery.com/parents/)
10. [`.parentsUntil()`](https://api.jquery.com/parentsUntil/)
11. [`.prev()`](https://api.jquery.com/prev/)
12. [`.prevAll()`](https://api.jquery.com/prevAll/)
13. [`.prevUntil()`](https://api.jquery.com/prevUntil/)
14. [`.siblings()`](https://api.jquery.com/siblings/)


树是一种数据结构, 说白了, 你一棵普通的树不也是得有一个根, 然后从根开始分枝出叶么. 然后树多了, 自然就叫森林, 不过我好像没见过什么森林相关的算法😂当然了, 创造产值的时候并不需要我们实现个红黑树什么的, 但是基本的还是得知道, 随便找本儿严蔚敏吴伟民殷人昆之类的象征性看下即可, 一般进公司不会有人问你这个, 看设计模式啥的都比这强...


顺便插一嘴, 我用的 MWeb 原来是用 control + 1/2/3/4/5/6 来插入一/二/三/四/五/六级标题... 我是实在受不了打十四个 `####` 所以才去找快捷键了...


#### 1. [`.children()`](https://api.jquery.com/children/)

描述: Get the children of each element in the set of matched elements, optionally filtered by a selector. 获得匹配元素集合中每个元素的直接子元素, 选择器选择性筛选.

要注意的地方:

> The `.children()` method differs from [`.find()`](https://api.jquery.com/find/) in that `.children()` only travels a single level down the DOM tree while `.find()` can traverse down multiple levels to select descendant elements (grandchildren, etc.) as well. Note also that like most jQuery methods, `.children()` does not return text nodes; to get all children including text and comment nodes, use [`.contents()`](https://api.jquery.com/contents/).


后半段在前面讲 `.contents()` 方法的时候提到过, 现在看前半段. 举个例子, 比如说畐国有这么串关系: `公司祖灵 > 畐太祖 > ((申帝 > 兀太子), 右妃, 木贵人, 艹帅, 㐅大将, 厶将军, 羽将军, 串相, 宛史官, 长皇后)`(照理实战中用的时候不应该有空格, 就是那么展示一下, 提高可读性), 那么从公司祖灵出发用 `.children()` 只能选到畐太祖、从申帝出发用 `.children()` 只能选到兀太子这样的; 但是你要是从畐太祖出发用 `.find()` 选有可能选到兀太子、从公司祖灵出发用 `.find()` 选有可能选到申帝、右妃、木贵人、宛史官等乃至兀太子.


举个 `.children()` 方法的例子:

```html
<!DOCTYPE html>
<html lang="en" dir="ltr">
    <head>
        <meta charset="utf-8">
        <title></title>
        <!-- <link rel="stylesheet" href="css-reset.css"> -->
        <script src="jquery-3.4.1.js" charset="utf-8"></script>
        <style>
        </style>
    </head>
    <body>
        <ul class="level-2">
            <li>
                <a href="#creational-design-patterns">Creational Design Patterns 创建型设计模式</a>
                <ul class="level-3">
                    <li><a href="#-simple-factory">🏠 Simple Factory 简单工厂模式</a></li>
                    <li><a href="#-factory-method">🏭 Factory Method 工厂方法模式</a></li>
                    <li><a href="#-abstract-factory">🔨 Abstract Factory 抽象工厂模式</a></li>
                    <li><a href="#-builder">👷 Builder 构建器模式</a></li>
                    <li><a href="#-prototype">🐑 Prototype 原型模式</a></li>
                    <li><a href="#-singleton">💍 Singleton 单例模式</a></li>
                </ul>
            </li>
            <li>
                <a href="#structural-design-patterns">Structural Design Patterns 结构型设计模式</a>
                <ul class="level-3">
                    <li><a href="#-adapter">🔌 Adapter 适配器模式</a></li>
                    <li><a href="#-bridge">🚡 Bridge 桥梁模式</a></li>
                    <li><a href="#-composite">🌿 Composite 组合模式</a></li>
                    <li><a href="#-decorator">☕️ Decorator 装饰器模式</a></li>
                    <li><a href="#-facade">📦 Facade 门面模式</a></li>
                    <li><a href="#-flyweight">🍃 Flyweight 享元模式</a></li>
                    <li><a href="#-proxy">🎱 Proxy 代理模式</a></li>
                </ul>
            </li>
            <li>
                <a href="#behavioral-design-patterns">Behavioral Design Patterns 行为型设计模式</a>
                <ul class="level-3">
                    <li><a href="#-chain-of-responsibility">🔗 Chain of Responsibility 责任链模式</a></li>
                    <li><a href="#-command">👮 Command 命令模式</a></li>
                    <li><a href="#-iterator">➿ Iterator 迭代器模式</a></li>
                    <li><a href="#-mediator">👽 Mediator 中介者模式</a></li>
                    <li><a href="#-memento">📔 Memento 备忘录模式</a></li>
                    <li><a href="#-observer">😎 Observer 观察者模式</a></li>
                    <li><a href="#-visitor">🏃 Visitor 访问者模式</a></li>
                    <li><a href="#-strategy">💡 Strategy 策略模式</a></li>
                    <li><a href="#-state">💢 State 状态模式</a></li>
                    <li><a href="#-template-method">📄 Template Method 模板方法模式</a></li>
                </ul>
            </li>
        </ul>
        <script type="text/javascript">
            // 为 level-2、level-3 下的 children 添加样式.
            $("ul.level-2").children().css({
                "border": "2px solid #333"
            })
            // 调用 .children() 方法时可以传个选择器作为参数.
            $("ul.level-3").children("li:odd").css({
                "font-weight": "bold",
                "background-color": "GoldenRod"
            })
            $("ul.level-3").children("li:even").css({
                "font-style": "italic",
                "background-color": "aquamarine"
            })
        </script>
    </body>
</html>

```


效果:

![children.png](https://i.loli.net/2019/08/27/xwBpRFEVMUhmi1O.png)


#### 2. [`.closest()`](https://api.jquery.com/closest/)


描述: For each element in the set, get the first element that matches the selector by testing the element itself and traversing up through its ancestors in the DOM tree. 从元素本身开始, 在 DOM 树上逐级向上级元素匹配, 并返回最先匹配的祖先元素.

举个 `.closest()` 方法的例子:

```html
<!DOCTYPE html>
<html lang="en" dir="ltr">
    <head>
        <meta charset="utf-8">
        <title></title>
        <script src="jQuery-3.4.1.js" charset="utf-8"></script>
    </head>
    <body>
        <p style="text-align:center">畐国通讯工程有限公司</p>
        <cite>
            “以后就再没有什么技术部、技装部, 统一合成一个大的工程部. 项目不再设项目经理, 而是改为不同时期设不同的项目负责人. 一个项目可以有多个负责人.” —— 串相父
        </cite>
        <ul class="level-1">
            <li>
                总经理
                <ul class="level-2">
                    <li>综合部</li>
                    <li class="project-department">
                        工程部
                        <ul class="level-3">
                            <li class="tech-department">
                                技术部
                                <!-- <ul>
                                    <li>实验室</li>
                                    <li>售后部</li>
                                    <li>配装室</li>
                                </ul> -->
                            </li>
                            <li>技装部</li>
                        </ul>
                    </li>
                    <li>业务部</li>
                    <li>设计部</li>
                    <li>财务部</li>
                </ul>
            </li>
        </ul>
        <script type="text/javascript">
            // 打印出 .project-department 最近上级的 ul 和 .tech-department 最近上级的 li.
            $(function () {
                // 第一个返回的是 .tech-department 本身这个 li, 因为它是从本身开始比符不符合选择器.
                console.log($(".tech-department").closest("li"))
                console.log($(".project-department").closest("ul"))
            })
        </script>
    </body>
</html>
```

效果:

![closest.png](https://i.loli.net/2019/08/27/bZt8lP7ryYaAEIn.png)

当然, 在 2018 年年后回来的畐国誓师大会上, 串相父代为发布了申国父的重要指示: 取消周六下午和周日的假期, 周六周日全天上班. 相传串相父干着干着自己就休息了. 串相父休没休息我不知道, 至少前半段我可以保证是真实存在的, 因为我当时就坐在议事殿佛堂的斜对面听串相父慷慨陈词...

艹申畜血🐴, 也艹串犬血🐴.


#### 3. [`.find()`](https://api.jquery.com/find/)

描述: Get the descendants of each element in the current set of matched elements, filtered by a selector, jQuery object, or element. 通过一个选择器/jQuery 对象/元素过滤, 得到当前匹配的元素集合中每个元素的后代.


还是讲一下关于后代的理解. 举个例子, 有这么一串关系: `公司祖灵 > 畐太祖 > ((申帝 > 兀太子), 右妃, 木贵人, 艹帅, 㐅大将, 厶将军, 羽将军, 串相, 宛史官, 长皇后)`, 通过 `.find()` 方法是可以从畐太祖找到兀太子的, 而通过 `.children()` 方法从畐太祖开始只能找到申帝右妃木贵人这一层.

举一个 `.find()` 方法的例子:

```html
<!DOCTYPE html>
<html lang="en" dir="ltr">
    <head>
        <meta charset="utf-8">
        <title></title>
        <script src="jquery-3.4.1.js" charset="utf-8"></script>
    </head>
    <body>
        <p style="font-weight: bold">东尼大木老师 MV 作品集</p>
        <ul class="collection">
            <li>
                范特西
                <ul class="list">
                    <li>爱在西元前</li>
                    <li class="song">忍者</li>
                    <li>开不了口</li>
                </ul>
            </li>
            <li class="album">
                八度空间
                <ul>
                    <li>暗号</li>
                    <li>半兽人</li>
                    <li class="song">龙拳</li>
                </ul>
            </li>
            <li>
                叶惠美
                <ul>
                    <li>三年二班</li>
                    <li>梯田</li>
                    <li>以父之名</li>
                </ul>
            </li>
            <li class="album">
                七里香
                <ul class="list">
                    <li>我的地盘</li>
                    <li class="song">七里香</li>
                    <li class="song">搁浅</li>
                </ul>
            </li>
            <li>
                十一月的萧邦
                <ul>
                    <li>夜曲</li>
                    <li>浪漫手机</li>
                    <li>珊瑚海</li>
                </ul>
            </li>
            <li>依然范特西</li>
            <li>我很忙</li>
            <li>
                跨时代
                <ul class="list">
                    <li class="song">说了再见</li>
                    <li>烟花易冷</li>
                </ul>
            </li>
        </ul>
        <script type="text/javascript">
            $(".collection").find(".album").css("border", "1px solid blue")
            $(".list").find(".song").css({
                "font-style": "italic",
                "color": "red"
            })
        </script>
    </body>
</html>

```

效果: 


![find.png](https://i.loli.net/2019/08/31/mlxGBhbKV3M4Ye8.png)





#### 4. [`.next()`](https://api.jquery.com/next/)

描述: Get the immediately following sibling of each element in the set of matched elements. If a selector is provided, it retrieves the next sibling only if it matches that selector. 取得匹配的元素集合中每一个元素紧邻的后面兄弟元素的元素集合. 如果提供一个选择器, 那么只有紧跟着的兄弟元素满足选择器时, 才会返回此元素.


`.next()` 这个方法的参数是可选的, 如果传参的话就是传个选择器进去.

下面举一个 `.next()` 方法的例子:


```html
<!DOCTYPE html>
<html lang="en" dir="ltr">
    <head>
        <meta charset="utf-8">
        <title>东尼大木·暗号</title>
        <script src="jquery-3.4.1.js" charset="utf-8"></script>
        <style media="screen">
            .highlight-style-1 {
                background-color: yellow;
            }
            .highlight-style-2 {
                background-color: orange;
            }
            .epilogue {
                float: right;
            }
        </style>
    </head>
    <body>
        <p class="first">我想要的想做的/你比谁都了/你想说的想给的/我全都知道/<strong>未接来电没留言/一定是你孤单的想念/任何人都猜不到/这是我们的暗号/</strong></p>
        <p class="second">他们猜随便猜不重要/连上彼此的讯号/才有个依靠/<em>有太多人太多事/夹在我们之间咆哮/杂讯太多讯号弱/就连风吹都要干扰/</em></p>
        <p class="third">可是你不想/一直走在黑暗地下道/想吹风想自由/想要一起手牵手/去看海绕世界流浪/</p>
        <em>我害怕你心碎/没人帮你擦眼泪/别管那是非/只要我们感觉对/</em><span>我害怕你心碎/没人帮你擦眼泪/别离开身边/拥有你我的世界才能完美/</span>
        <br/>
        <cite class="epilogue">感恩咪咕音乐, 感恩贫穷, 让我们相遇.🎆🎇🎉</cite>
        <script type="text/javascript">
            $(function () {
                // next() 不传参的话就是选东哥的兄弟; 传参的话就是从东哥兄弟中选匹配选择器的最 next 的那个.
                $(".first").next().addClass("highlight-style-1")
                $("p").next("em").addClass("highlight-style-2")
            })
        </script>
    </body>
</html>

```

效果:

![.next()](https://upload.cc/i1/2019/09/02/KyTcXU.png)

抛开 script 部分的话, 这个文档是 `(p.first>strong)+(p.second>em)+p.third+em+span+br+cite` 结构.


#### 5. [`.nextAll()`](https://api.jquery.com/nextAll/)

描述: Get all following siblings of each element in the set of matched elements, optionally filtered by a selector. 获得每个匹配元素集合中所有下面的同辈元素, 可以选择性地根据选择器筛选. 

视频中原先后半部分的翻译是“选择性筛选的选择器”. 翻得还是比较不忍直视的...

下面举一个 `.nextAll()` 方法的例子:

```html
<!DOCTYPE html>
<html lang="en" dir="ltr">
    <head>
        <meta charset="utf-8">
        <title>畐国电影节作品选</title>
        <script src="jquery-3.4.1.js" charset="utf-8"></script>
    </head>
    <body>
        <div class="shen-pig">绿盔侠</div>
        <div class="chuan-dog">上市幻想7: 串犬的挽歌</div>
        <div class="right-concubine">申的女人: 秘密服务</div>
        <div class="right-concubine">Scdiler 队长</div>
        <div class="small-potatoes">高中生: 返校季</div>
        <div class="small-potatoes">高中生: 废物远征</div>
        <div class="small-potatoes">富仇者: 黑暗命运</div>
        <script type="text/javascript">
            $(function () {
                $(".shen-pig").nextAll().css("background-color", "pink")
                $(".shen-pig").nextAll(".right-concubine").css("color", "grey")
            })
        </script>
    </body>
</html>

```

效果:

![.nextAll()](https://upload.cc/i1/2019/09/02/8QqD1H.png)

 `.nextAll()` 方法和 `.next()` 方法的区别就是 `.nextAll()` 方法可以选调用者后面的**一堆**兄弟元素(如果不加选择器的话).


#### 6. [`.nextUntil()`](https://api.jquery.com/nextUntil/)

描述: Get all following siblings of each element up to but not including the element matched by the selector, DOM node, or jQuery object passed. 


这个我就不放视频上的翻译了, 视频上和 [jquery123上](https://www.jquery123.com/nextUntil/) 翻得和屎一样. 

我目前想到会这么翻: 获取每个元素的所有后续兄弟元素, 这些兄弟元素是直到但不包括由传递的选择器，DOM节点或 jQuery 对象匹配的元素.


虽然不太雅, 达可能也差一点儿, 但是好歹信是做到了.


`.nextUntil()` 方法参数有如下两大类情况:

![.nextUntil()方法参数](https://upload.cc/i1/2019/09/02/g3pMPL.png)

下面举一个 `.nextUntil()` 方法的例子:

```html
<!DOCTYPE html>
<html lang="en" dir="ltr">
    <head>
        <meta charset="utf-8">
        <title></title>
        <script src="jquery-3.4.1.js" charset="utf-8"></script>
    </head>
    <body>
        <strong>畐国皇室成员简介</strong>
        <dl>
            <dt id="shen-pig">申帝:</dt>
            <dd>畐国共主, 绿盔侠, 申高工, 申硕士.</dd>
            <!-- 这个 right 真是一语双关. -->
            <dt id="right-concubine">右妃:</dt>
            <dd>施德尔队长/畐国女子亲卫队队长, 申帝特聘的外援, 用于在 2019 年逆转无限, 挽救畐国于树倒猢狲散的黑暗命运.</dd>
            <dt>艹帅:</dt>
            <dd>申帝的心腹, 天下兵马大元帅.</dd>
            <dt>㐅大将:</dt>
            <dd>申帝心腹, 申帝的御前侍卫, 华博队长.</dd>
            <dt>木贵人:</dt>
            <dd>申帝心腹, 掌管内政事务.</dd>
            <dt id="chuan-dog">串相:</dt>
            <dd>畐国的二把手, 申帝的走狗.</dd>
            <dt>羽将军:</dt>
            <dd>畐国两朝元老, 畐国死士.</dd>
            <dt>厶将军:</dt>
            <dd>也是畐国死士.</dd>
            <dt>宛史官:</dt>
            <dd>畐国史官, 负责掌管畐国典籍.</dd>
            <dt>丶贵人:</dt>
            <dd>前申帝心腹, 虽饱受申帝折磨仍能不忘初心, 敢于为维护申帝利益而颠倒黑白混淆是非, 依然属于社会各界友畐人士.</dd>
            <dt id="queen-chang">长皇后</dt>
            <dd>申帝的发妻, 即将被废黜.</dd>
        </dl>
        <script type="text/javascript">
            // 查找 id 为 `shen-pig` 的那个 dt 元素的所有兄弟元素, 直到遇见下一个 dt 为止. 并将找到的兄弟元素的背景颜色设为绿色.
            $(function () {
                $("#shen-pig").nextUntil("dt").css("background-color", "green")
            })

            // 查找 id 为 `right-concubine` 的那个 dt 元素之后 dd 的所有兄弟元素, 直到遇到 id 为 `queen-chang` 为止, 将这些兄弟设为蓝色.
            $(function () {
                var start = $("#right-concubine")
                var end = $("#queen-chang")
                start.nextUntil(end, "dd").css("color", "blue")
            })
        </script>
    </body>
</html>

```

效果:

![nextuntil.png](https://i.loli.net/2019/09/09/3KuRvaC9EPkbAQX.png)


注意 `.nextUntil()` 的结果是不包含起始和结束的两端点的. 


#### 7. [`.parent()`](https://api.jquery.com/parent/)

描述: Get the parent of each element in the current set of matched elements, optionally filtered by a selector. 取得匹配元素集合中每个元素的父元素, 可以提供一个可选的选择器来过滤.

举个 `.parent()` 方法的例子:


```html
<!DOCTYPE html>
<html lang="en" dir="ltr">
    <head>
        <meta charset="utf-8">
        <script src="jquery-3.4.1.js" charset="utf-8"></script>
        <title></title>
    </head>
    <body>
        <div style="border: 3px dotted green; padding: 10px">
            <div>申:
                <p>我们恨申畜, 是申畜压迫我们的结果. 世上决没有无缘无故的爱, 也没有无缘无故的恨.</p>
            </div>
            <div>串:
                <p>有的串犬活着, 它已经死了.</p>
            </div>
            <div>
                <ul>畐国高层语录:
                    <li>
                        <ul>孽畜篇:
                            <!-- 孽畜想看平台成果了, 要开会, 我一看没办法就通宵写完了五千多行的脚本还有更新服务器配置啥的. 然后孽畜看我第一面来了这句. -->
                            <li>你这活怎么才干这么点儿, 找个高中生都能干.</li>
                            <li>你们负责干活, 我负责后方.</li>
                            <!-- 当时模板项目的财务那儿电脑上就一个账号能选, 而且还不是项目能用的那个账户, 因为就是没有现象. 非得让我选一个, 我操他妈. -->
                            <li>那就加把劲儿吧, 赶紧选了账号儿, 该问问该问谁问谁要干嘛, 弄完这东西.</li>
                            <li>你说你还能干点什么, 废物.</li>
                        </ul>
                    </li>
                    <li>
                        <ul>狗腿子篇:
                            <li>年轻人多坚持坚持.</li>
                            <li>你们的努力公司领导都看着呐, 不会亏待大家伙, 年底会有说法的.</li>
                            <li>你早干什么了?</li>
                            <li>公司现在已经到了最危险的时候了, 现在这个行业大家的日子都不好过. 每天拍良心想一想, 拍拍胸脯问问你自己, 你干出今天的产值了吗? 你干出的产值够不够每天在公司吃中午饭的饭钱? 你还好意思走那么早吗?</li>
                        </ul>
                    </li>
                </ul>
            </div>
        </div>
        <script type="text/javascript">
            // 为每一个 p 元素的父元素加一个红色边框.
            $(function () {
                $("p").parent().css({
                    "border": "2px solid red",
                    "margin": "10px"
                })
            })

            // 向 .parent() 方法传入参数
            $(function () {
                $("li").parent("ul").css({
                    "border": "3px solid black",
                    "margin": "5px"
                })
            })
        </script>
    </body>
</html>

```

效果:

![.parent()](https://upload.cc/i1/2019/09/09/G9KNO7.png)


#### 8. [`.parents()`](https://api.jquery.com/parents/)

描述: Get the ancestors of each element in the current set of matched elements, optionally filtered by a selector. 获得集合中每个匹配元素的祖灵元素(包括父级元素那个层次), 可以提供一个可选的选择器用来过滤.


举个 `.parents()` 方法的例子:

```html
<!DOCTYPE html>
<html lang="en" dir="ltr">
    <head>
        <meta charset="utf-8">
        <title></title>
        <script src="jquery-3.4.1.js" charset="utf-8"></script>
    </head>
    <body>
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
        <script>
            // 打印出 id 为 `grand-hall` 的所有祖灵元素.
            console.log($("#grand-hall").parents());

	        // 打印出 id 为 `306` 的所有祖灵 ul 元素.
            console.log($("#room-306").parents("ul"))
        </script>
    </body>
</html>

```


效果:

![parents.png](https://i.loli.net/2019/09/09/xTXkirWPCSZyQn3.png)


#### 9. [`.offsetParent()`](https://api.jquery.com/offsetParent/)

描述: Get the closest ancestor element that is positioned. 取得离指定元素最近的含有定位信息的祖灵元素. 含有定位信息的元素指的是: CSS 的 position 属性是 relative、absolute 或 fixed 的元素.

看一下要注意的点: 

> Given a jQuery object that represents a set of DOM elements, the `.offsetParent()` method allows us to search through the ancestors of these elements in the DOM tree and construct a new jQuery object wrapped around the closest positioned ancestor. An element is said to be positioned if it has a CSS position attribute of `relative`, `absolute`, or `fixed`. This information is useful for calculating offsets for performing animations and placing objects on the page.

这个方法不接受任何参数. 这里的祖灵元素也包括畐太祖之于申帝这种的父级元素.

举个 `.offsetParents()` 方法的例子:

```html
<!DOCTYPE html>
<html lang="en">
	<head>
		<meta charset="UTF-8">
		<title>Title</title>
		<script src="jquery-3.4.1.js"></script>
		<style>
			#shen-pig li span {
				display: inline-block;
			}
			cite {
				border: 2px solid darkred;
			}
			#shen-pig li span {
				border: 2px solid springgreen;
			}
		</style>
		</head>
	<body>
		<!-- 打 emoji: `&#x` + 表情码 + `;` -->
		<span>上联: 广大员工 996</span><br/>
		<span>下联: 申串早日 ICU</span><br/>
		<span>横批: 年底会有说法&#x1F604;&#x1F604;&#x1F604;</span>
		<ul class="level-1-ul" style="position: relative;">畐国高层身先士卒奋勇拼搏事迹
			<li class="level-1-li" style="position: fixed;">
				<ul class="level-2-ul" style="position: static;">串犬篇
					<li style="position: inherit;" class="level-2-li">
						<cite>“现场着急安装调试, 中秋节相关人员不能放假, 需领导安排.”</cite>
					</li>
				</ul>
			</li>
		</ul>
		<script>
			console.log($("cite").offsetParent())
		</script>
	</body>
</html>
```

效果:

![offsetparent](https://upload.cc/i1/2019/09/10/MF7w2m.png)

方法描述里明确说不能选不了 static 的了, 再就 inherit 这个词认识吧.


#### 10. [`.parentsUntil()`](https://api.jquery.com/parentsUntil/)

描述: Get the ancestors of each element in the current set of matched elements, up to but not including the element matched by the selector, DOM node, or jQuery object. 查找当前元素的所有的祖灵元素, 直到遇到选择器、DOM 节点或 jQuery 对象匹配的元素为止, 但不包括这些元素.

举个 `.parentsUntil()` 方法的例子:

```html
<!DOCTYPE html>
<html lang="en">
    <head>
    	<meta charset="UTF-8">
    	<title>Title</title>
    	<script src="jquery-3.4.1.js"></script>
    </head>
    <body>
    	<div class="wrapper">
    		<strong>畐国皇室诗选</strong>
    		<ol class="ol">
    			<li class="level-1-li">
    				<ul class="ul">
    					<li class="level-2-li-1">串的名字对木有什么意义?</li>
    					<li>它会死去,</li>
    					<li>像大海拍击海堤, 发出的忧郁的汩汩涛声</li>
    					<li>像密林中幽幽的夜声,</li>
    					<li class="level-2-li-2">没有意义.</li>
    				</ul>
    			</li>
    			<li>
    				<ul>
    					<li>但是在右孤独、悲伤的日子,</li>
    					<li>请右悄悄地念一念申的名字,</li>
    					<li>并且说: 有畜在思念我,</li>
    					<li>在世间我活在一个畜的心里.</li>
    				</ul>
    			</li>
    		</ol>
    	</div>
    	<script>
    		// 打印 class 为 level-2-li 的直到 level-1-li 的所有祖灵元素.
    		console.log($(".level-2-li-1").parentsUntil(".level-1-li"));
    
    		// 打印 class 为 level-2-li 的直到 wrapper 的所有祖灵元素中为 ol 和 ul 的那些.
    		console.log($(".level-2-li-2").parentsUntil(".wrapper", "ul, ol"))
    	</script>
    </body>
</html>
```

效果:

![parentsUntil.png](https://i.loli.net/2019/09/10/RFCYVhtIijMWzNE.png)


注意这个方法可以双参数单参数或是无参数.

> Given a selector expression that represents a set of DOM elements, the `.parentsUntil()` method traverses through the ancestors of these elements until it reaches an element matched by the selector passed in the method's argument. The resulting jQuery object contains all of the ancestors up to but not including the one matched by the `.parentsUntil()` selector.
> 
> If the selector is not matched or is not supplied, all ancestors will be selected; in these cases it selects the same elements as the `.parents()` method does when no selector is provided.


#### 11. [`.prev()`](https://api.jquery.com/prev/)


描述: Get the immediately preceding sibling of each element in the set of matched elements. If a selector is provided, it retrieves the previous sibling only if it matches that selector. 取得一个包含匹配的元素集合中每一个元素**紧邻的前一个**兄弟元素的元素集合. 如果传一个选择器进去的话, 仅当前面的兄弟匹配选择器的时候这个方法才提取这个兄弟.

视频上后半部分翻译的什么东西...当阅读理解么...


举个 `.prev()` 方法的例子:

```html
<!DOCTYPE html>
<html lang="en">
	<head>
		<meta charset="UTF-8">
		<title>SCD 跑马灯</title>
		<script src="https://cdnjs.cloudflare.com/ajax/libs/jquery/3.4.1/jquery.slim.min.js"></script>
		<style>
			div {
				width: 90px;
				height: 90px;
				margin-left: 10px;
				float: left;
				color: white;
				border: 2px solid black;
			}
			button {
				margin-left: 10px;
			}
		</style>
	</head>
	<body>
		<div></div>
		<div></div>
		<div></div>
		<div></div>
		<div></div>
		<div></div>
		<div></div>
		<div id="start"></div>
		<button>往前一个</button>
		<script>
			$(function () {
			    let collection = ["申帝我艹你妈!", "串相我艹你妈!", "申畜我透你妈!",
					"串犬我透你妈!", "孽畜我日你妈!", "走狗我日你妈!", "SCD 跑马灯"];
			    let start = $("#start");
			    let i = 6;
                $("button").click(function () {
                    start = start.prev();
                    start.html(collection[i]);
                    start.css("background-color", "#" + Math.random().toString(16).slice(2, 8));
					i--
                })
            })
		</script>
	</body>
</html>
```

效果:

![prev](https://upload.cc/i1/2019/09/10/u4MaBO.png)

这个取随机颜色我是参考的这个 [Random Hex Color Code Generator in JavaScript](https://www.paulirish.com/2009/random-hex-color-code-snippets/) 下的评论: [A solution by @kriskowal: "#" + Math.random().toString(16).slice(2, 8)](http://disq.us/p/d0itcq). 这种去谷歌一下 “javascript random hex color” 就出来了...

用其他做法也可以, 总之要注意这个值要在 0x000000 和 0xFFFFFF (= 16777215) 之间. 有的做法是不行的.


#### 12. [`.prevAll()`](https://api.jquery.com/prevAll/)

描述: Get all preceding siblings of each element in the set of matched elements, optionally filtered by a selector. 获得集合中每个匹配元素的所有前面的兄弟元素, 可以提供一个可选的选择器用来过滤.

这个方法可以接受一个参数, 这个参数内容是选择器.

举个 `.prevAll()` 的例子:

```html
<!DOCTYPE html>
<html lang="en">
    <head>
        <meta charset="UTF-8">
        <title>Title</title>
        <script src="jquery-3.4.1.js"></script>
    </head>
    <body>
        <div>
            <p>如果畐国要招一个写 Bug 的, 那右妃上就可以了。</p>
            <em>右妃年底应该还是能把IDE装完环境搭好的.</em>
            <strong>到畐国倒闭的时候应该能学会写 Hello Scdiler.</strong>
            <p class="selected">申帝说它会写HTML.</p>
            <ul>
                <li>申帝前端, 右妃后台.</li>
                <li>画师负责美工.</li>
                <li>剩下的人运维，为皇室成员保驾护航.</li>
            </ul>
        </div>
        <script>
            $(function () {
                for (let obj of $(".selected").prevAll()) {
                	console.log(obj)
                }
                console.log($("ul").prevAll("em"))
            })
        </script>
    </body>
</html>
```


效果:


![prevall.png](https://i.loli.net/2019/09/11/uf3EgJk9SDjCmiW.png)


#### 13. [`.prevUntil()`](https://api.jquery.com/prevUntil/)


描述: Get all preceding siblings of each element up to but not including the element matched by the selector, DOM node, or jQuery object. 获取每个元素前面的所有兄弟, 但不包括选择器、DOM 节点、或者 jQuery 对象匹配的那些元素. 

可以接收两个参数.


举个 `.prevUntil()` 方法的例子:


```html
<!DOCTYPE html>
<html lang="en">
    <head>
        <meta charset="UTF-8">
        <title></title>
        <script src="jquery-3.4.1.js"></script>
        <style>
            .culture {
                float:left;
            }
            .members {
                float: right;
            }
            .group-1, .group-2, .group-3 {
                float: left;
            }
        </style>
    </head>
    <body>
        <fieldset>
            <legend>申帝寄语</legend>
            <cite>
                家里的兄弟姐妹我感谢你们选择这个家，这个家需要发展，我想给大家带来好的物质生活和精神上荣誉，让大家感到在这个公司工作为荣，把家里不好的坏习惯彻底改掉，也许会失去一些人，但是我坚定我的想法，我要让努力工作的人得到更多，让偷懒找借口和互相推诿在公司消失，希望大家支持我的工作，谢谢。
            </cite>
        </fieldset>
        <div class="culture">
            <strong>企业文化</strong>
            <p>让规范化、模块化、平台化成为公司常态.</p>
            <span>企业管理规范化的体现：</span>
            <ul>
                <li>层次清晰</li>
                <li>责权明确</li>
                <li>流程高效</li>
                <li>信息畅达</li>
            </ul>
            <span>科学规范的制度体系包括如下内容：</span>
            <ul>
                <li>法人治理 + 战略规划 + 组织结构</li>
                <li>目标管理 + 岗位绩效 + 权限分配</li>
                <li>流程管理 + 内控管理 + 信息化</li>
            </ul>
        </div>
        <div class="members">
            <strong>部分人员列表</strong>
            <ul>
                <li class="group-1">
                    死士
                    <ul>
                        <li>羽将军</li>
                        <li>厶将军</li>
                    </ul>
                </li>
                <li class="group-2">
                    蛆虫
                    <ul>
                        <li>逆贼</li>
                        <li>废物</li>
                        <li>高中生</li>
                    </ul>
                </li>
                <li class="group-3">
                    其他皇室成员
                    <ul>
                        <li id="right-concubine">右妃</li>
                        <li>艹帅</li>
                        <li>㐅大将</li>
                        <li>木贵人</li>
                        <li>宛史官</li>
                        <li id="chuan-dog">串相</li>
                        <li>韦画师</li>
                        <li>丶贵人</li>
                        <li>长皇后</li>
                    </ul>
                </li>
            </ul>
        </div>
        <script>
            // 选取从串犬开始往回直到右妖女结束的兄弟, 不包括端点. 设置这些兄弟的字体颜色为绿色.
            $(function () {
                $("#chuan-dog").prevUntil("#right-concubine").css("color", "green")
            })

            // 选取 ul 开始往回直到 strong 的 span 兄弟, 不包括端点, 给这些兄弟加个边框.
            $(function () {
                $("ul").prevUntil("strong", "span").css("border", "2px solid red")
            })
        </script>
    </body>
</html>
```


效果:

![prevuntil.png](https://i.loli.net/2019/09/11/6xcuU2rT4F1NPGv.png)



#### 14. [`.siblings()`](https://api.jquery.com/siblings/)

描述: Get the siblings of each element in the set of matched elements, optionally filtered by a selector. 获得匹配元素集合中每个元素的兄弟, 可以提供一个可选的选择器用来过滤.

举个 `.siblings()` 的例子:

```html
<!DOCTYPE html>
<html lang="en">
    <head>
        <meta charset="UTF-8">
        <title>混日子的人不是我的兄弟</title>
        <script src="jquery-3.4.1.js"></script>
    </head>
    <body>
        <strong>申帝: 混日子的人不是我的兄弟.</strong>
        <ul>
            <li><strong style="color:red;">申帝</strong></li>
            <li class="is-brother">右妃</li>
            <li class="is-brother">艹帅</li>
            <li class="is-brother">羽将军</li>
            <li class="is-brother">厶将军</li>
            <li>高中生: 高中生都能干，要你个 985 的大学生有什么用</li>
            <li>废物: 我一天花150雇你，你就干这些，手脖子还扭了你能干点什么你个废物</li>
            <li>逆贼: 因为前东家不给加班费、还欠两万证书挂靠费这么点儿鸡毛蒜皮的小事儿就把前东家给告了</li>
            <li class="is-brother">串相</li>
            <li class="is-brother">木贵人</li>
            <li class="is-brother">宛史官</li>
        </ul>
        <script>
            // 给申帝的兄弟们添加一个样式.
            $(function () {
                $("li").has("strong").siblings(".is-brother").css("color", "green")
            })
        </script>
    </body>
</html>
```

效果:

![siblings.png](https://i.loli.net/2019/09/11/dE4iAJX5CzZTYme.png)

到这儿 jQuery 遍历终于完事儿了😂


## [jQuery 特效](https://api.jquery.com/category/effects/)


### [基本(说白了就是隐藏与显示)](https://api.jquery.com/category/effects/basics/)


#### 1. [`.hide()`](https://api.jquery.com/hide/)

描述: Hide the matched elements.

传入参数的情形和选项比较多, 具体情况如下:

![hide用法.png](https://i.loli.net/2019/09/11/l27Me8PJqaiYOvj.png)

duration 的单位是以毫秒计算的. 1 s = 1000 ms.


#### 2. [`.show()`](https://api.jquery.com/show/)

描述: Display the matched elements.

和 `.hide()` 方法一样, 也是参数配置情况比较多:

![show用法.png](https://i.loli.net/2019/09/11/BE47w6pK1g2sltO.png)




#### 3. [`.toggle()`](https://api.jquery.com/toggle/)

描述: Display or hide the matched elements.

也是用法比较多:

![toggle用法.png](https://i.loli.net/2019/09/11/V65uRplBEr94oyZ.png)


下面我们将这一节的三个方法放在一起举一个例子:

```html
<!DOCTYPE html>
<html lang="en">
    <head>
        <meta charset="UTF-8">
        <title>Title</title>
        <script src="jquery-3.4.1.js"></script>
    </head>
    <body>
        <p class="mother">申帝的&#x1F434;</p>
        <p hidden class="message">申帝, 你妈炸了!</p>
        <p class="clothes">右妃的&#x1F459;</p>
        <button id="hide-button">消失键</button>
        <button id="show-button">显示键</button>
        <button id="snap-button">响指键</button>
        <script>
            // 申畜的 &#x1F434; 消失了.
            $(function () {
                $("#hide-button").click(function () {
                    $(".mother").hide(2500)
                })
            })

            $(function () {
                $("#show-button").click(function () {
                    $(".message").show(2000)
                })
            })

            $(function () {
                $("#snap-button").click(function () {
                    $(".clothes").toggle(1500)
                })
            })
        </script>
    </body>
</html>
```


效果: 


![basics.png](https://i.loli.net/2019/09/11/73dWkSAHenXTt2M.png)


再举一个例子:

```html
<!DOCTYPE html>
<html lang="en">
    <head>
        <meta charset="UTF-8">
        <title>Title</title>
        <script src="jquery-3.4.1.js"></script>
        <style>
            div {
                width: 80px;
                height: 80px;
                float: left;
                background-color: #abcdef;
                border: 3px solid black;
                margin: 20px;
            }
        </style>
    </head>
    <body>
        <div>畐国本埠</div>
        <div>SCD 大楼</div>
        <div>凌烟阁</div>
        <div>畐国驻魔都办事处</div>
        <div>SCD 驻深圳办事处</div>
        <div>SCD 海景分舵</div>
        <p hidden>一声响指响起, 申帝霸业化灰&#x1F604;&#x1F604;&#x1F604;</p>
        <button>响指键</button>
        <script>
            $(function () {
                $("button").click(function () {
                    $("div").hide(3000, function() {
                        $("div").remove()
                    })
                    $("p").show(5000)
                })
            })
        </script>
    </body>
</html>
```

效果:


![hideshow2.png](https://i.loli.net/2019/09/12/SrJatGL6oQlvfFu.png)



### [淡入淡出](https://api.jquery.com/category/effects/fading/)

These methods adjust the opacity of elements.

Fading.

#### 1. [`.fadeIn()`](https://api.jquery.com/fadeIn/)

描述: Display the matched elements by fading them to opaque.

查一下 **opaque** 这个词是啥意思. 以前看过好几次, 不过有些忘了.

1. ADJ-GRADED 不透明的; 不透光的
   If an object or substance is **opaque**, you cannot see through it.
   * You can always use <strong style="color:orange;">opaque</strong> glass if you need to block a street view. 
     如果不想从室内看到街景，可以使用不透明玻璃。
2. ADJ-GRADED 费解的; 难懂的; 晦涩的
   If you say that something is **opaque**, you mean that it is difficult to understand.
   * ...the <strong style="color:orange;">opaque</strong> language of the inspector's reports. 
     巡视员报告中晦涩难懂的语言

#### 2. [`.fadeOut()`](https://api.jquery.com/fadeOut/)

描述: Hide the matched elements by fading them to transparent.

#### 3. [`.fadeTo()`](https://api.jquery.com/fadeTo/)

描述: Adjust the opacity of the matched elements.

![fadeto参数.png](https://i.loli.net/2019/09/15/MgZc96X34a2Cl5N.png)

看样子, 这个 `.fadeTo()` 主要是把对象的**不**透明度 (opacity) 用多长多长时间来给调到某个值.

下面举一个 `.fadeTo()` 方法的例子: 

```html
<!DOCTYPE html>
<html lang="en">
    <head>
        <meta charset="UTF-8">
        <title>辽警秘密捜査官の女右妃</title>
        <script src="jquery-3.4.1.js"></script>
        <style>
            img {
                width: 300px;
            }
        </style>
    </head>
    <body>
        <img src="https://i.loli.net/2019/09/15/dNaq6Y34BE8lhMA.jpg"
             title="SCD-500 辽警秘密捜査官の女右妃3 ファイナル 復讐の女豹、闘いの挽歌"
             alt="SCD-500 辽警秘密捜査官の女右妃3 ファイナル 復讐の女豹、闘いの挽歌">
        <img src="https://i.loli.net/2019/09/15/AlCyG3c4zTwFqeJ.jpg"
             title="SCD-750 辽警秘密捜査官の女右妃2 裏切りと凌辱のテロル"
             alt="SCD-750 辽警秘密捜査官の女右妃2 裏切りと凌辱のテロル">
        <br/><button>Fade to</button>
        <script>
            $(function () {
                $("button").on("click", function () {
                    $("img").fadeTo(3000, 0.4)
                })
            })
        </script>
    </body>
</html>
```

效果:

![fade-to](https://upload.cc/i1/2019/09/15/Dq5dBf.png)

辽警, 专科子弟的摇篮.


#### 4. [`.fadeToggle()`](https://api.jquery.com/fadeToggle/)

描述: Display or hide the matched elements by animating their opacity.

下面举一个 `.fadeIn()`、`.fadeOut()`、`.fadeToggle()` 方法的例子:

```html
<!DOCTYPE html>
<html lang="en">
    <head>
        <meta charset="UTF-8">
        <title>Title</title>
        <script src="jquery-3.4.1.js"></script>
    </head>
    <body>
        <p hidden>Fading.</p>
        <div id="div1" style="width:80px;height:80px;background-color: aquamarine;">畐国本埠</div>
        <div id="div2" style="width:80px;height:80px;background-color: palegreen;">施德尔大楼</div>
        <div id="div3" style="width:80px;height:80px;background-color: palevioletred;">海景分舵</div>
        <span hidden>申帝无中生&#x1F434;/申帝亲&#x1F434;爆炸</span><br/>
        <button id="fade-in">Fade in</button>
        <button id="fade-out">一声响指, 霸业化灰</button>
        <button id="fade-toggle">响指键</button>
        <script>
            $(function () {
                $("#fade-in").on("click", function () {
                    $("p").fadeIn(4000);
                })
                $("#fade-out").click(function () {
                    $("div").fadeOut(2000);
                })
                $("#fade-toggle").on("click", function () {
                    $("span").fadeToggle(3000);
                })
            })
        </script>
    </body>
</html>
```

效果:

![fade](https://upload.cc/i1/2019/09/15/dksYHx.png)

### [滑动](https://api.jquery.com/category/effects/sliding/)

#### 1. [`.slideDown()`](https://api.jquery.com/slideDown/)

描述: Display the matched elements with a sliding motion.

#### 2. [`.slideUp()`](https://api.jquery.com/slideUp/)

描述: Hide the matched elements with a sliding motion.

下面举一个 `.slideDown()` 和 `.slideUp()` 方法的例子:

```html
<!DOCTYPE html>
<html lang="en">
    <head>
        <meta charset="UTF-8">
        <title>为了公司!</title>
        <script src="jquery-3.4.1.js"></script>
        <style>
            #content-1, #content-2 {
                padding: 30px;
                background-color: aquamarine;
            }
            #button-1, #button-2 {
                padding: 5px;
                background-color: palegoldenrod;
            }
            #button-1, #content-1, #button-2, #content-2 {
                width: 350px;
                margin: 20px;
                text-align: center;
                border: 4px solid green;
                border-radius: 10px;
            }

        </style>
    </head>
    <body>
        <div id="button-1">公司精锐事迹</div>
        <div id="content-1" hidden>
            <cite>
                > (中秋假期的第三天问的) 昨晚你们干通宵啊？？<br/>
                > 12点多，到家1点，大前天11:30到家
            </cite>
        </div>
        <div id="button-2">申畜你可省省吧.</div>
        <div id="content-2">
            <cite>
                > 我一年给员工发工资就得发 300 多万
            </cite>
        </div>
        <script>
            $(function () {
                $("#button-1").click(function () {
                    $("#content-1").slideDown(3000)
                })
                $("#button-2").click(function () {
                    $("#content-2").slideUp(2000)
                })
            })
        </script>
    </body>
</html>
```

效果:

![](https://upload.cc/i1/2019/09/15/yzxKV7.png)

注意: 调用 `.slideDown()` 方法的对象是从上向下展开粗现; 而调用 `.slideUp()` 方法的对象是从下向上收起消失.

参数好像没有关于调整方向方面儿的. 兴许开发组成员以后可以琢磨琢磨这方面, 这样我有码之年也许还能看到. 当然这个码不是马赛克的 mǎ.

#### 3. [`.slideToggle()`](https://api.jquery.com/slideToggle/)

描述: Display or hide the matched elements with a sliding motion.

下面我们举一个 `.slideToggle()` 的例子:

```html
<!DOCTYPE html>
<html lang="en">
    <head>
        <meta charset="UTF-8">
        <title>薛定谔的右妃</title>
        <script src="jquery-3.4.1.js"></script>
        <style>
            .outer {
                text-align: center;
                padding: 30px;
                width: 160px;
                background-color: palevioletred;
                border: 4px solid black;
                border-radius: 8px;
                margin: 20px;
            }
            .inner {
                padding: 10px;
                width: 80px;
                background-color: aquamarine;
                border: 4px solid green;
                border-radius: 8px;
                margin: 20px;
            }
        </style>
    </head>
    <body>
        <div class="outer">公司
            <div class="inner">右妃</div>
        </div>
        <button>变右键</button>
        <p>
            > 右妃看来就没来上班.<br/>
            > 薛定谔的右. 明明不在却又处处不在.
        </p>
        <script>
            $(function () {
                $("button").click(function () {
                    $(".inner").slideToggle(3000)
                })
            })
        </script>
    </body>
</html>
```

效果:

![slideToggle()](https://upload.cc/i1/2019/09/15/vT21Wl.png)

### 回调(临时加戏, 不是官网上那个 Callbacks Object)

这个就是讲在特效函数里插入 closure 还不 lambda 还不 block 还不 callable 之类的东西. 下面我们举一个例子:

```html
<!DOCTYPE html>
<html lang="en">
    <head>
        <meta charset="UTF-8">
        <title>Title</title>
        <script src="jquery-3.4.1.js"></script>
    </head>
    <body>
        <span>历史上王朝的毁灭都是从大兴土木开始的.</span>
        <p>申帝的&#x1F434;</p>
        <button>响指键</button>
        <script>
            // 申帝的🐴没了以后, 加一个其他的函数效果.
            $(function () {
                $("button").click(function () {
                    $("p").hide(2000, function () {
                        alert("申帝, 你🐴炸了!")
                    })
                })
                $("span").slideUp(4000).css("color", "red").slideDown(3000)
            })
        </script>
    </body>
</html>
```


效果: 

![callable](https://upload.cc/i1/2019/09/16/87Qs3d.png)


### [自定义](https://api.jquery.com/category/effects/custom-effects/)

列了七个, 不过官网上不止七个. 没列出来的有一个在 jQuery 3.0 时代已经没有意义了.

#### 1. [`.animate()`](https://api.jquery.com/animate/)

描述: Perform a custom animation of a set of CSS properties. 根据一组 CSS 属性来执行一个自定义动画.

用法比较多, 截图如下:

![animate().png](https://i.loli.net/2019/09/16/VyL8tvjNTHwbYiO.png)

看下这一段:

The `.animate()` method allows us to create animation effects on any numeric CSS property. The only required parameter is a plain object of CSS properties. This object is similar to the one that can be sent to the `.css()` method, except that the range of properties is more restrictive.

看到那个 numeric 了吧? 很好. 也就是说呢, 所有用于 `.animate()` 方法的属性值必须是数字的. 比如说你 `background-color` 这个 property 通常来说就没法用 `.animate()` 来改值, 除非是装插件.

注意: 

> Unlike shorthand animation methods such as `.slideDown()` and `.fadeIn()`, the `.animate()` method does *not* make hidden elements visible as part of the effect. For example, given `$( "someElement" ).hide().animate({height: "20px"}, 500)`, the animation will run, but *the element will remain hidden*.

`easing` 的值看起来有两个选项, 一个是 `linear`, 一个是 `swing`, 缺省值是 `swing`. 非要说出处的话是在 jQuery JavaScript Library v3.4.1 (普通完整版) 的第 7004 行到第 7012 行左右. 至于那些奇形怪状的值应该是 jQueryUI 里的. 但说实话, 恕我愚钝, 我还是没看出来这个 `linear` 和 `swing` 有什么区别...

上例子:

```html
<!DOCTYPE html>
<html lang="en">
    <head>
        <meta charset="UTF-8">
        <title>帽子绿</title>
        <script src="jquery-3.4.1.js"></script>
        <style>
            div {
                width: 200px;
                height: 200px;
                background-color: green;
                position: absolute;
            }
        </style>
    </head>
    <body>
        <div></div>
        <script type="text/javascript">
            $(function () {
                $("div").click(function () {
                    $(this).animate({
                        opacity: 0.2,
                        width: 400,
                        left: 100,
                    }, 1957, "linear", function () {
                        alert("申帝你家右妃跟人跑了.")
                    })
                })
            })
        </script>
    </body>
</html>

```

效果如下:

![animate](https://upload.cc/i1/2019/10/30/eQEL0y.png)

我们也可以对某个 CSS property 通过赋数组值的形式来进行单独指定, 比如我们把上面代码中的 `width: 400` 改为 `width: [400, "swing"]` 这种.

我们也可以用 `.animate()` 方法来添加多个动画:

```html
<!DOCTYPE html>
<html lang="en">
    <head>
        <meta charset="UTF-8">
        <title>帽子绿</title>
        <script src="jquery-3.4.1.js"></script>
        <style>
            div {
                width: 200px;
                height: 200px;
                background-color: green;
                position: absolute;
            }
        </style>
    </head>
    <body>
        <div></div>
        <script type="text/javascript">
            $(function () {
                $("div").click(function () {
                    // 第一个动画
                    $(this).animate({
                        opacity: 0.2,
                        width: 400,
                        left: 100,
                    }, 1957, "linear")
                    // 第二个动画
                    $(this).animate({
                        opacity: 0.6,
                        width: [300, "linear"],
                        top: 150,
                    }, 1957, "linear", function () {
                        alert("申帝你公司倒闭了.")
                    })
                })
            })
        </script>
    </body>
</html>

```

添加多个动画的时候, 多个动画会依次执行.

#### 2. [`.clearQueue()`](https://api.jquery.com/clearQueue/)

描述: Remove from the queue all items that have not yet been run. 从队列中移除所有未被执行的项.

注意是移除掉所有*未被执行的*项.

可以传一个参数: `queueName`, 也就是字符串类型, 默认是 `fx`.

举例如下:

```html
<!DOCTYPE html>
<html lang="en" dir="ltr">
    <head>
        <meta charset="utf-8">
        <title>Clear Queue</title>
        <script src="jquery-3.4.1.js" charset="utf-8"></script>
        <style>
            div {
                width: 200px;
                height: 200px;
                background-color: GreenYellow;
                position: absolute;
            }
            button {
                position: absolute;
            }
        </style>
    </head>
    <body>
        <div>申帝的绿盔</div>
        <button>清除</button>
        <script type="text/javascript">
            $(function () {
                var div = $("div")
                div.click(function () {
                    $(this).animate({
                        width: 500,
                        opacity: 0.2,
                        left: 200
                    }, 1957, "linear")
                    $(this).animate({
                        width: 200,
                        opacity: 0.8,
                        left: 100,
                    }, 4000, "swing", function () {
                        alert("绿盔侠与畐国女子亲卫队队长的故事, 下略 30 万字.")
                    })
                })
                $("button").click(function () {
                    div.clearQueue()
                })
            })
        </script>
    </body>
</html>

```

效果如下:

![clearQueue](https://upload.cc/i1/2019/10/30/NH3YMe.png)

分别对应的动画开始前、两个动画均结束以后、在第一个动画运行时点按钮停止. 上面那个效果图我是按照“停止”写的, 回头想想写“清除”更好一点儿, 就不回头改了.

清队列的话, 不会立即停止, 而是把当前动画对应的 `.animate()` 的内容跑完之后再停止, 不往下跑之后的 `.animate()` 内容了.

#### 3. [`.delay()`](https://api.jquery.com/delay/)

描述: Set a timer to delay execution of subsequent items in the queue. 设置一个定时器来延迟执行队列中后续的项.

参数可以传两个. 其中第一个参数 `duration` 必传, 第二个参数 `queueName` 可选.

举例如下:

```html
<!DOCTYPE html>
<html lang="en" dir="ltr">
    <head>
        <meta charset="utf-8">
        <title>Delay</title>
        <script src="jquery-3.4.1.js" charset="utf-8"></script>
        <style>
            div {
                width: 200px;
                height: 200px;
                background-color: GreenYellow;
                position: absolute;
            }
        </style>
    </head>
    <body>
        <div>申帝的绿盔</div><br>
        <script type="text/javascript">
            $(function () {
                var div = $("div")
                div.click(function () {
                    $(this).animate({
                        width: 500,
                        opacity: 0.2,
                        left: 200
                    }, 1957, "linear").delay(1957)
                    $(this).animate({
                        width: 200,
                        opacity: 0.8,
                        left: 100,
                    }, 4000, "swing", function () {
                        alert("长皇后的意义就是没有意义.")
                    })
                })
            })
        </script>
    </body>
</html>

```

这样, 在第一个动画跑完以后, 会停 1957 ms, 然后接着跑第二个动画.

#### 4. [`.finish()`](https://api.jquery.com/finish/)

描述: Stop the currently-running animation, remove all queued animations, and complete all animations for the matched elements. 停止当前正在运行的动画, 移除所有加入队列中的动画, 并完成匹配元素的所有动画.

可以接收一个可选参数 —— 队列名. 

举例如下:

```html
<!DOCTYPE html>
<html lang="en" dir="ltr">
    <head>
        <meta charset="utf-8">
        <title>Finish</title>
        <script src="jquery-3.4.1.js" charset="utf-8"></script>
        <style>
            div {
                width: 200px;
                height: 200px;
                background-color: GreenYellow;
                position: absolute;
            }
            button {
                position: absolute;
            }
        </style>
    </head>
    <body>
        <div>申帝的绿盔</div><br>
        <button>完成</button>
        <script type="text/javascript">
            $(function () {
                var div = $("div")
                div.click(function () {
                    $(this).animate({
                        width: 500,
                        opacity: 0.2,
                        left: 200
                    }, 1957, "linear")
                    $(this).animate({
                        width: 200,
                        opacity: 0.8,
                        left: 100,
                    }, 4000, "swing", function () {
                        alert("SCD 队长的第二春.")
                    })
                })
                $("button").click(function () {
                    div.finish()
                })
            })
        </script>
    </body>
</html>

```

点击“完成”按钮以后, 会直接跳转到 `alert(blahblahblah...)` 那块儿, 关掉弹窗之后 `div` 直接跳转到最后理论上动画结束的状态. 就不截图了.

#### 5. [`.stop()`](https://api.jquery.com/stop/)

描述: Stop the currently-running animation on the matched elements. 停止匹配元素当前正在运行的动画.

停止会停止当前 `.animate()` 方法的内容, 保留当前状态, 继续执行下一项 `.animate()` 方法的动画内容(如果有的话).

举例如下:

```html
<!DOCTYPE html>
<html lang="en" dir="ltr">
    <head>
        <meta charset="utf-8">
        <title>Stop</title>
        <script src="jquery-3.4.1.js" charset="utf-8"></script>
        <style>
            div {
                width: 200px;
                height: 200px;
                background-color: GreenYellow;
                position: absolute;
            }
            button {
                position: absolute;
            }
        </style>
    </head>
    <body>
        <div>申帝的绿盔</div><br>
        <button>停止</button>
        <script type="text/javascript">
            $(function () {
                var div = $("div")
                div.click(function () {
                    $(this).animate({
                        width: 500,
                        opacity: 0.2,
                        left: 200
                    }, 1957, "linear")
                    $(this).animate({
                        width: 200,
                        opacity: 0.8,
                        left: 100
                    }, 1998, "swing")
                    $(this).animate({
                        opacity: 0.5,
                        top: 150
                    }, 4000, "linear", function () {
                        alert("申帝赐了长皇后一杯有机白干.")
                    })
                })
                $("button").click(function () {
                    div.stop()
                })
            })
        </script>
    </body>
</html>

```

#### 6. [`.queue()`](https://api.jquery.com/queue/)

描述: Show the queue of functions to be executed on the matched elements.

这个视频里没讲. 自己下去看官网文档.

感觉官方那个例子还可以.

#### 7. [`.dequeue()`](https://api.jquery.com/dequeue/)

描述: Execute the next function on the queue for the matched elements.

这个视频里没讲. 也是自己下去看官网文档.
