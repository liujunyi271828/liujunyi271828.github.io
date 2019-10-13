---
layout: post
title: "库 vs. 工具箱 vs. 框架 vs. 设计语言 vs. 样板 vs. 脚手架工具"
description: "了解一下这几个东西的区别和联系."
date: 2019-07-21
tags: [提高姿势水平]
comments: true
share: true
---


前两天在ZH上看到的一个回答[前端三大框架以及jQuery与bootstrap这种框架有什么（概念上、范畴上的）区别？- 陈龙](https://www.zhihu.com/question/304757674/answer/546374749), 个人感觉写得比较好. 把里面拼错的单词改正了一下.

正文开始:


我们先分清六个基本概念：Library，Toolkit，Framework，Design，Boilerplate，Scaffolding。看似这是几个基本概念，但是对于学习技术却很重要。我见过多个有十年工作经验的开发，简历里写的：熟悉jQuery框架。在很多人脑子里都只有框架这一个概念，啥都是框架。

**Library**就是库，而且分为两类。

一类是方法库，用来实现特定需求的一组API集合。最常见的就是jQuery，它是一系列操作DOM和AJAX的API组成的方法库。除了jQuery，还有早期的Prototype，Dojo，Mootools，后面这三个在当时也被称为三大前端工具库。

操作Data的有 UnderScore 和 Lodash，操作 Event 的有现在流行的 RxJS，他们都是 Library，在需要的时候，正确调用他们提供的方法就可以。

一类是 UI 组件库，满足特定业务需要的高可复用的常见UI组件集合。例如 Ant Design of React/Ant Design of Angular(NG-ZORRO)，Element UI，LayUI，EasyUI。早期的 ExtJS，jQuery UI。

Bootstrap是一个**Toolkit**(工具箱)，给你提供创建现代响应式页面所需要的工具，包含一套完整的响应式CSS类库，字体，同时还有一套很完整的UI组件。只是这些组件原生是用jQuery写的，不适用于现在主流的前端。所以产生了很多衍生UI库，例如 Angular 实现的ng-bootstrap 和 ngx-bootstrap，React 实现的react-bootstrap，Vue 实现的 bootstrap-vue。

**Framework**是框架，用来构建一个应用的主体结构。然后你在这个主体结构上添砖加瓦，实现自己的需求。Web 服务器端的框架基本实现的都是MVC设计模式，你在 Model、View、Controller 层分别去添加代码。Web前端，Angular(以及它的前身 Angularjs)实现的都是 MVP 模式，是 Model、View、Presenter 三层。老一辈的其他前端框架，例如Backbone、Ember，实现的是所谓 MVVM。

当前*所谓*的前端三大框架，只有 Angular 算作严格意义上的Framework，而且是一个 *Opinionated* Framework，其他两个不算。

Vue官网首页最大的字说：

> The Progressive 
> 
> JavaScript Framework


但是，在Guide页面说：

> Vue (pronounced /vjuː/, like view) is a progressive framework for building user interfaces. The core library is focused on the view layer only, and is easy to pick up and integrate with other libraries or existing projects.


所以，Vue (法文 View 的意思)本质上是一个解决 View 层的Library.

React 官网就没这么遮遮掩掩了，首页最大的字：

> A JavaScript library for building user interfaces


所以，Vue 和 React 都是关注于 View 这一层的 Library。也正因如此，用React或Vue搭建项目就还需要一系列其他周边库做补充支持。例如React本身没有实现路由导航，就需要react-router。等等，还有很多，俗称全家桶。

**Design** 是设计语言。当说到 xxx Design 的时候，前端应该经常听到 Material Design 和 Ant Design，分别是Google和阿里的推出的两种前端UI设计语言。

设计语言(或者说设计风格)，是指导UI设计需要遵循的一些约束。这些约束包括：色彩、布局、层次、交互反馈等等。就像我们说建筑，有哥特式的、中国古典式的、希腊式的。买衣服，我们知道韩版、英伦风格、波斯米亚风格。

Design 和具体实现是松耦合的，没有直接必然关联。规范只规定这种设计语言的风格是什么样子的，从来不指定具体实现，谁都可以实现。就是 Specification 和 Implementation 的关系。就好像中国古典建筑，古时候多用木材，现在用钢筋混凝土一样可以建造出同样的风格。就好像程序员喜欢的格子衫(一种风格)，可以用法兰绒的，也可以棉麻的。

Material Design 起初是指导 Andoid 界面的，但是也存在很多 Web UI 的实现，例如基于 Bootstrap 开源的有 Bootstrap Material。

Ant Design也是一样。只是最开始只有React的实现Ant Design of React。阿里团队后期发布了Angular的实现Ant Design of Angular(NG-ZORRO)。

**Boilerplate** 是模板、样板的意思。一般程序员很少了解这个概念，而是Library和Framework知道的多一些。上面说过了，当你用React开发的时候，React本身不能满足全部需求，就需要周边辅助的项目。如何把这些全家桶用最佳实践(Best Practice)的方式组合在一起？就需要有人给一个样板，Ant Design Pro就产生了。所以Ant Design是设计语言、Ant Design of React是遵循这门设计语言并且用React实现的UI组件库，Ant Design Pro就是模板。

**Scaffolding** 是脚手架工具。前端的脚手架工具一般都是用 cli 提供的，cli 是Command Line Interface的缩写，不是 Client 的前三个字母。例如ng-cli, create-react-app, vue cli，以及用Yeoman(YO)做出来的许多generator。


脚手架这个词看似陌生，但其实大家都见过。就是建筑工地大楼施工时候外面那一层钢管搭建的架子，还有很多绿色的网起到保护作用。*Scaffolding的作用就是辅助你快速搭建项目。但是Scaffolding不是最终成果物的一部分！*

不管你用了 jQuery 也好，用了 Vue 也好，用了 Bootstrap 也好，这些东西的代码都会成为你最终编译成果的一部分，而Scaffolding不会。所以大楼建成以后，外面的脚手架是要被拆掉的，不会和大楼一起交付给业主！