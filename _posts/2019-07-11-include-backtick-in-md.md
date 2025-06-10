---
layout: post
title: "如何在 Markdown 中打出反单引号 (backtick)"
description: "为干出产值而研究技术."
date: 2019-07-11
tags: [提高姿势水平]
comments: true
share: true
---

> 为干出产值而研究技术.

举个例子, 比如说我们想打出下面这个东西, 该如何是好呀:

> 你`->count('*')`、 ``->count(`*`)``、`->count()`都会报这个错.


应该这么打, 也就是行内代码块的最外层两边分别套两个反单引号:

```markdown
你`->count('*')`、 ``->count(`*`)``、`->count()`都会报这个错.
```

出处: [Markdown: Syntax](https://daringfireball.net/projects/markdown/syntax#code):

> To include a literal backtick character within a code span, you can use multiple backticks as the opening and closing delimiters.


注意: 你在一对单个的反单引号外面套`<code></code>`是不行的...你在一对单个的反单引号前面加反斜杠`\`试图转义也是不行的...

顺便一提, 这个人叫[John Grubber](https://en.wikipedia.org/wiki/John_Gruber), 好像挺牛逼的, 貌似就是[md](https://daringfireball.net/projects/markdown/)的作者本尊...果然还是作者对自己写的东西的理解比较高妙...

