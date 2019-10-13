---
layout: post
title: "property 和 attribute 的区别"
description: "为公司上市而研究技术."
date: 2019-07-25
tags: [提高姿势水平]
comments: true
share: true
---

照理17号就想写这个东西, 但是实在是很累很烦躁. 加上我的姥爷在22号走了, 父母亲回姥爷那边儿去料理后事, 虽说我还是在该干啥干啥, 不过也是感慨万千.

我的姥爷是哈工大(就是大家所知的那个哈工大)的一名教授, 可想而知, 他算是一名知识分子. 不管放在什么时代, 就姿势水平而言, 他也都是比我牛逼的. 然而在外人看来或者说在我看来, 过得并不幸福, 生活质量很差, 对**身边**子女的教育方式也不行, 总之是一言难尽. 为他感到深深的惋惜, 如果以后有对象有孩子的话, 得努力避免这种前车之鉴, 成为好对象好父母.


总之, 如果还有来生的话, 希望我姥爷不要再像这辈子这样窝囊.

正文开始.


## [Property](https://developer.mozilla.org/en-US/docs/Glossary/Property)


**property**这个词根据上下文可能有两种意思, 请参考:

### [Property (CSS)](https://developer.mozilla.org/en-US/docs/Glossary/property/CSS)

A **CSS property** is a characteristic (like color) whose associated value defines one aspect of how the browser should display the element.


看一下官网的这个例子:

```css
/* "div" is a selector indicating that all the div elements */
/* in the document will be styled by that rule */
div {
  /* The property "color" with the value "black" indicates */
  /* that the text will have the color black */
  color: black;

  /* The property "background-color" with the value "white" indicates */
  /* that the background color of the elements will be white */ 
  background-color: white;
}
```

### [Property (JavaScript)](https://developer.mozilla.org/en-US/docs/Glossary/property/JavaScript)

A **JavaScript property** is a characteristic of an object, often describing attributes associated with a data structure.

There are two kinds of properties: 

* *Instance properties* hold data that are specific to a given object instance. 
* *Static properties* hold data that are shared among all object instances.

这个应该就可以理解为 Objective-C 里你写一个类的时候用到的那种 `@property`. 说白了也就是在 PHP、Java 等语言中 OO 时的成员属性. 事实上, 上面 CSS 的选择器和 PHP、Java 等语言中的 class、C 中的结构体很神似.


总的说来, property 可以理解为一个什么什么东西的 characteristic, 而characteristic这个词作名词解的时候意思描述如下:

> 特色;特点;特征<br/>
> The characteristics of a person or thing are the qualities or features that belong to them and make them recognizable.


---

## [Attribute](https://developer.mozilla.org/en-US/docs/Glossary/Attribute)


**attribute** 是对标签的扩展, 改变标签的行为或是提供元数据. 一个 **attribute** 总是具有 `name=value` 的形式(**attribute** 的标识符然后跟一个与其相关联的值.)


---

看了文档以后觉着比较简单, 现在一下就明白了. 算是穿成一个宇宙了.


