---
layout: post
title: "&lt;style&gt;blahblahblah...&lt;/style&gt;和&lt;script&gt;blahblah......&lt;/script&gt;该放到HTML文档中的什么位置呢..."
description: "为公司而研究技术"
date: 2019-07-19
tags: [提高姿势水平]
comments: true
share: true
---

看 jQuery 视频的时候想到的这个问题...确认一下.

我司以前的前端小姐姐跑路回家生孩子去了...本来想问别人, 不过一想还是自己查吧...主要我现在认识的操作代码的人全是后端四血红皮, 一直不认识前端三血绿皮三血蓝皮, 三血银皮美工倒是认识好几个...而且关键问人得到的结果也不一定有自己找合理渠道查的准...

另外现在是2019年, 可能网上有些解答的理念已经过时了.

目录:

* toc
{:toc}


## &lt;style&gt;blahblahblah...&lt;/style&gt; 篇

抄[MDN](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/style)吧:

> The `<style>` element can be included inside the <a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/head"><code><head></code></a> or <a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/body"><code><body></code></a> of the document, and the styles will still be applied, however it is recommended that you include your styles in the `<head>` for organizational purposes — it is a lot better to separate your content from your presentation as much as possible. Even better, put your styles in external stylesheets and apply them using <a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/link"><code><link></code></a> elements.

If you include multiple `<style>` and `<link>` elements in your document, they will be applied to the DOM in the order they are included in the document — make sure you include them in the correct order, to avoid unexpected cascade issues.

In the same manner as `<link>` elements, `<style>` elements can include media attributes that contain [media queries](https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries), allowing you to selectively apply internal stylesheets to your document depending on media features such as viewport width.


## &lt;script&gt;blahblah......&lt;/script&gt; 篇

[MDN上的文档](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/script)没写`<script>code block;</script>`具体该放哪. 不过看看`async`和`defer`这两个属性也是好的. 关于这两个属性可以看下[Efficiently load JavaScript with defer and async](https://flaviocopes.com/javascript-async-defer/).

关于`<script>code block;</script>`究竟该放在哪儿的问题, 说到底, 是一个需要随机应变的问题, 请综合(也算是把我比较关心的几个方面都给覆盖到了):

### 1. [网站为什么 JS 调用尽量放到网页底部？ - 于江水的回答 编辑于 2015-09-13](https://www.zhihu.com/question/34147508/answer/63469443)

> 浏览器加载页面是按从上到下顺序加载的。加载 JavaScript 并执行的时候，会阻塞其他资源的加载。这是因为 JavaScript 可能会有 DOM 、样式等等操作，所以浏览器要先加载这段 JavaScript 并执行，再加载放在它后面的 HTML、CSS。
> 
> 因此，加入一段巨大的 JS 放在最上面，浏览器首先要下载并执行，这段时间里面，页面是空白的。相比于加载了部分 HTML 和 样式 但是没有 JavaScript 交互功能，显然是后者对于浏览者体验要好。
> 
>** 然而，是否所有 JavaScript 都要放在最下面呢？并不是。**
> 
> 举实际的例子：
> 
> <a href="https://github.com/aFarkas/html5shiv"><strong>html5shiv</strong></a>是一段 JS 脚本，用来是早期 IE 兼容 HTML5 新增标签的支持。
> 
> 这个 JS 脚本，必须要放在上面 head 部分，为什么呢？因为在老 IE 浏览器下面，不支持 `<section>` 这样的标签，所以用 JS 来兼容。如果放在底部，等 IE 浏览器先报错了，才会执行这块 JS 没多大用。
> 
> jQuery 这类的库，也是建议放在最上面的。首先最大的疑问可能是 jQuery 这么大，放在上面岂不是阻塞的很厉害？
> 
> 不过 jQuery 通常引用的是 CDN 地址，而且经过 gzip 压缩之后并不是很大，而且引用公共 CDN 上面的 jQuery 话，很大几率早已被用户缓存下来了。所以可以不需要考虑阻塞产生的性能问题。
> 
> 而我们都知道，JS 是按顺序执行下来的。也就是你没运行 jQuery 之前，先运行了调用 jQuery 函数的代码，就会报错。你可以控制你自己写的 JS 放在页面最下面，放在 jQuery 下面，但是你无法保证页面上其他地方会不会有人图省事直接在 HTML 代码里面输出 JS。如果有，那么就会报错。
> 
> 所以我建议: **类库放在上面加载, 其余代码尽可能放在最底下加载.**

> ---

> 然而，前端性能优化只是薄薄一层.<br/>
> 可能前端优化半天，还不如上个 CDN 或者加个宽带或者优化一个后端算法来的效果好.

### 2. [网站为什么 JS 调用尽量放到网页底部？ - 玉兔的回答 编辑于 2015-08-12](https://www.zhihu.com/question/34147508/answer/58855939)


因为浏览器渲染HTML文件是从上往下渲染的.<br/>
即先执行 `<head></head>` 标签里的内容, 再执行`<body></body>` 标签里的, 一行行渲染下去.

无论当前 JavaScript 代码是内嵌还是在外链文件中, 页面的下载和渲染都必须停下来等待脚本执行完成. JavaScript 执行过程耗时越久, 浏览器等待响应用户输入的时间就越长. 

所以 JavaScript 尽量放底部可以有一定的性能优化效果.

题外话——关于 JavaScript 性能优化:<br/>
除了上面这个方法, 还可以通过设置 `<script></script>` 标签的 `defer` 或 `async` 属性、合并脚本等等方法来优化. 

推荐一篇干货: [JavaScript 的性能优化：加载和执行](https://www.ibm.com/developerworks/cn/web/1308_caiys_jsload/)

### 3. [2019前端最全面试题](https://zhuanlan.zhihu.com/p/63962882)


> #### 把<code>&lt;script&gt;</code>标签恰好放在<code>&lt;/body&gt;</code>之前.
> 
> (说实话, 这里我不知道为什么我需要把小于号 `<` 和大于号 `>` 转义, 但是不转义还真输出不出来...)
> 
> 脚本在下载和执行期间会阻止 HTML 解析。把 `<script>` 标签放在底部，保证 HTML 首先完成解析，将页面尽早呈现给用户。
> 
> 例外情况是当你的脚本里包含 `document.write()` 时。但是现在, `document.write()` 不推荐使用。同时，将`<script>`标签放在底部，意味着浏览器不能开始下载脚本，直到整个文档 (document) 被解析. 也许, 对此比较好的做法是, `<script>` 使用defer属性, 放在 `<head>` 中.
> 
> (下面几个记得不是很清楚, 也顺便看一下.)
> 
> #### <code>&lt;img/&gt;</code>中的<code>alt</code>和元素的<code>title</code>属性作用
> 
> * `<img/>`的`alt`属性: 如果无法显示图像，浏览器将显示`alt`指定的内容
> * 元素`title`属性: 在鼠标移到元素上时显示`title`的内容
>
> #### <code>href</code>和<code>src</code>区别
> 
> * `href`:<br/>
>   `href`标识超文本引用，用在`<link/>`和`<a>`等元素上，`href`是引用和页面关联，是在当前元素和引用资源之间建立联系.<br/>
>   若在文档中添加`href`, 浏览器会识别该文档为 CSS 文件，就会并行下载资源并且不会停止对当前文档的处理。这也是为什么建议使用 `<link/>` 方式加载 CSS，而不是使用 `@import` 方式。
> * `src`:<br/>
>   `src`表示引用资源，替换当前元素，用在`<img/>`, `<script>`, `<iframe>`上，`src`是页面内容不可缺少的一部分.<br/>
>   当浏览器解析到`src`, 会暂停其他资源的下载和处理（图片不会暂停其他资源下载），直到将该资源加载、编译、执行完毕，类似于将所指向资源应用到当前内容。这也是为什么建议把 JavaScript 脚本放在底部而不是头部的原因.
> 
> #### 行内元素和块级元素有哪些
> 
> ##### 行内元素
> 
> 一个行内元素只占据它对应标签的边框所包含的空间.<br/>
> 一般情况下，行内元素只能包含数据和其他行内元素
> 
> ```
> b, big, i, small, tt
> abbr, acronym, cite, code, dfn, em, kbd, strong, samp, var
> a, bdo, br, img, map, object, q, script, span, sub, sup
> button, input, label, select, textarea
> ```

> ##### 块级元素
> 
> 占据一整行，高度、行高、内边距和外边距都可以改变，可以容纳块级标签和其他行内标签.
> 
> ```
> header,form,ul,ol,table,article,div,hr,aside,figure,canvas,video,audio,footer
> ```
> 
> #### 行内元素、块级元素区别
> 
> 行内元素: 和其他元素都在一行上，高度、行高及外边距和内边距都不可改变，文字图片的宽度不可改变，只能容纳文本或者其他行内元素；其中`<img/>`是行元素.
> 
> 块级元素: 总是在新行上开始，高度、行高及外边距和内边距都可控制，可以容纳内敛元素和其他元素；行元素转换为块级元素方式: `display：block;`.
> 
> #### <code>display: none;</code>、<code>visibile: hidden;</code>、<code>opacity: 0</code>的区别
> 
> |  | 是否隐藏 | 是否在文档中占用空间 | 是否会触发事件 | 
> |----|----|----|----| 
> |display: none;|是|否|否|
> |visibile: hidden;|是|是|否|
> |opacity: 0;|是|是|是|