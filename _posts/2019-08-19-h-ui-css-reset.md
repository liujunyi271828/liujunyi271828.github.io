---
layout: post
title: "H-ui CSS reset重定义浏览器默认样式"
description: "CSS 重置解决方案."
date: 2019-08-19
tags: [提高姿势水平]
comments: true
share: true
---

> CSS 重置解决方案.

> H-ui 前端框架是在 Bootstrap 的思想基础上基于 HTML、CSS、JavaScript 开发的轻量级 web 前端框架，开源免费，简单灵活，兼容性好，满足大多数中国网站，H-ui —— 专注前端解决方案。
> 
> H-ui.admin v3.1，是一款由国人开发的轻量级扁平化网站后台模板，完全免费开源的网站后台管理系统模版，适合中小型 CMS 后台系统。

原先网站的字母大小写做得不是很好...还得帮他们改一下. 建议这方面多注意一下.

![大小写](https://upload.cc/i1/2019/08/19/ZGry3S.png)


这个是前端版的: [H-ui 前端框架](http://www.h-ui.net).

这个是后台版的: [H-ui.admin v3.1](http://www.h-ui.net/H-ui.admin.shtml) 注意这个后台版不适配 IE 8 以下. 用的时候注意看一下常见问题, 这个 H-ui.admin 会与 TP3 冲突, 需要上 TP3 里改模板引擎普通标签的左分隔符和右分隔符.

这边儿有个氪金版本的后台版: [H-ui.admin.Pro v1.0](http://www.h-ui.net/H-ui.admin.pro.shtml), 49块钱, 价格还可以, 有需要的旁友们可以氪一发.

回到正题, 我这主要是想看人家的 CSS 初始化的... 下面我们看一下 [H-ui 家的 CSS reset重定义浏览器默认样式](http://www.h-ui.net/Hui-1-cssReset.shtml):

```css
*{word-wrap:break-word}
html,body,h1,h2,h3,h4,h5,h6,hr,p,iframe,dl,dt,dd,ul,ol,li,pre,form,button,input,textarea,th,td,fieldset{margin:0;padding:0}
ul,ol,dl{list-style-type:none}
html,body{*position:static}
html{font-family: sans-serif;-webkit-text-size-adjust:100%;-ms-text-size-adjust:100%}
address,caption,cite,code,dfn,em,th,var{font-style:normal;font-weight:400}
input,button,textarea,select,optgroup,option{font-family:inherit;font-size:inherit;font-style:inherit;font-weight:inherit}
input,button{overflow: visible;vertical-align:middle;outline:none}
body,th,td,button,input,select,textarea{font-family:"Microsoft Yahei","Hiragino Sans GB","Helvetica Neue",Helvetica,tahoma,arial,Verdana,sans-serif,"WenQuanYi Micro Hei","\5B8B\4F53";font-size:12px;color: #333;-webkit-font-smoothing: antialiased;-moz-osx-font-smoothing:grayscale}
body{line-height:1.6}
h1,h2,h3,h4,h5,h6{font-size:100%}
a,area{outline:none;blr:expression(this.onFocus=this.blur())}
a{text-decoration:none;cursor: pointer}
a:hover{text-decoration:underline;outline:none}
a.ie6:hover{zoom:1}
a:focus{outline:none}
a:hover,a:active{outline:none}:focus{outline:none}
sub,sup{vertical-align:baseline}
button,input[type="button"], input[type="submit"] {line-height:normal !important}
/*img*/
img{border:0;vertical-align:middle}
a img,img{-ms-interpolation-mode:bicubic}
.img-responsive{max-width: 100%;height: auto}
 
/*IE下a:hover 背景闪烁*/
*html{overflow:-moz-scrollbars-vertical;zoom:expression(function(ele){ele.style.zoom = "1";document.execCommand("BackgroundImageCache",false,true)}(this))}
 
/*HTML5 reset*/
header,footer,section,aside,details,menu,article,section,nav,address,hgroup,figure,figcaption,legend{display:block;margin:0;padding:0}time{display:inline}
audio,canvas,video{display:inline-block;*display:inline;*zoom:1}
audio:not([controls]){display:none}
legend{width:100%;margin-bottom:20px;font-size:21px;line-height:40px;border:0;border-bottom:1px solid #e5e5e5}
legend small{font-size:15px;color:#999}
svg:not(:root) {overflow: hidden}
fieldset {border-width:0;padding: 0.35em 0.625em 0.75em;margin: 0 2px;border: 1px solid #c0c0c0}
input[type="number"]::-webkit-inner-spin-button,input[type="number"]::-webkit-outer-spin-button {height: auto}
input[type="search"] {-webkit-appearance: textfield; /* 1 */-moz-box-sizing: content-box;-webkit-box-sizing: content-box; /* 2 */box-sizing: content-box}
input[type="search"]::-webkit-search-cancel-button,input[type="search"]::-webkit-search-decoration {-webkit-appearance: none}
/*
Name:			style_clearfix
Example:		class="clearfix|cl"
Explain:		Clearfix（简写cl）避免因子元素浮动而导致的父元素高度缺失能问题
*/
.cl:after,.clearfix:after{content:".";display:block;height:0;clear:both;visibility:hidden}.cl,.clearfix{zoom:1}
```