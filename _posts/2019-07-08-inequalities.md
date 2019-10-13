---
layout: post
title: "不等式"
description: "随手写两个题健健身."
date: 2019-07-08
tags: [数学]
comments: true
share: true
---

* toc
{:toc}


## 1.􏱋􏱌 2019 年普通高等学校招生全国统一􏰢􏰁􏰣考试 理科数学I


已知 *a*, *b*, *c* 为正􏵆数, 且满足􏰵􏱓􏱑􏱒 *abc* = 1. 􏳘􏴰􏲈证明:<br/>
(1) (1 / *a*) + (1 / *b*) + (1 / *c*) ≤ *a*<sup>2</sup> + *b*<sup>2</sup> + *c*<sup>2</sup>;<br/>
(2) (*a* + *b*)<sup>3</sup> + (*b* + *c*)<sup>3</sup> + (*c* + *a*)<sup>3</sup> ≥ 24.<br/>

证明:

(1) 由于 *abc* = 1, 故只需证 *ab* + *bc* + *ca* ≤ *a*<sup>2</sup> + *b*<sup>2</sup> + *c*<sup>2</sup> 成立. 而 *a*<sup>2</sup> + *b*<sup>2</sup> + *c*<sup>2</sup> - *ab* - *bc* - *ca* = (1 / 2) * [(*a* - *b*)<sup>2</sup> + (*b* - *c*)<sup>2</sup> + (*c* - *a*)<sup>2</sup>] ≥ 0, 从而 *ab* + *bc* + *ca* ≤ *a*<sup>2</sup> + *b*<sup>2</sup> + *c*<sup>2</sup> 成立, 进而有 (1 / *a*) + (1 / *b*) + (1 / *c*) ≤ *a*<sup>2</sup> + *b*<sup>2</sup> + *c*<sup>2</sup>.

(2) 由于 *abc* = 1, 故只需证 (*a* + *b*)<sup>3</sup> + (*b* + *c*)<sup>3</sup> + (*c* + *a*)<sup>3</sup> ≥ 24*abc*.<br/>结合 *a* > 0, *b* > 0, *c* > 0 有:<br/> (*a* + *b*)<sup>3</sup> + (*b* + *c*)<sup>3</sup> + (*c* + *a*)<sup>3</sup> - 24*abc* <br/>= (*a*<sup>3</sup> + 3*a*<sup>2</sup>*b* + 3*ab*<sup>2</sup> + *b*<sup>3</sup>) + (*b*<sup>3</sup> + 3*b*<sup>2</sup>*c* + 3*bc*<sup>2</sup> + *c*<sup>3</sup>) + (*c*<sup>3</sup> + 3*c*<sup>2</sup>*a* + 3*ca*<sup>2</sup> + *a*<sup>3</sup>) - 24*abc* <br/>= 2(*a*<sup>3</sup> + *b*<sup>3</sup> + *c*<sup>3</sup> - 3*abc*) + 3(*a*<sup>2</sup>*b* + *ab*<sup>2</sup> + *b*<sup>2</sup>*c* + *bc*<sup>2</sup> + *c*<sup>2</sup>*a* + *ca*<sup>2</sup> - 6*abc*)<br/>= 2(*a*<sup>3</sup> + *b*<sup>3</sup> + *c*<sup>3</sup> - 3*abc*) + 3[*a*(*b*<sup>2</sup> + *c*<sup>2</sup> - 2*bc*) + *b*(*c*<sup>2</sup> + *a*<sup>2</sup> - 2*ca*) + *c*(*a*<sup>2</sup> + *b*<sup>2</sup> - 2ab)]<br/>= 2(*a* + *b* + *c*)(*a*<sup>2</sup> + *b*<sup>2</sup> + *c*<sup>2</sup> - *ab* - *bc* - *ca*) + 3[*a*(*b* - *c*)<sup>2</sup> + *b*(*c* - *a*)<sup>2</sup> + *c*(*a* - *b*)<sup>2</sup>] <br/>≥ 0. 从而 (*a* + *b*)<sup>3</sup> + (*b* + *c*)<sup>3</sup> + (*c* + *a*)<sup>3</sup> ≥ 24*abc* 成立. 进而有 (*a* + *b*)<sup>3</sup> + (*b* + *c*)<sup>3</sup> + (*c* + *a*)<sup>3</sup> ≥ 24.


还是比较简单的...不过结果很纯粹, 比较artisanal and elegant.


## 2. 北一女中數學挑戰甄答題(第七期)第1题

设 *a* > *b* > *c*, 证明 *a*<sup>2<i>a</i></sup>*b*<sup>2<i>b</i></sup>*c*<sup>2<i>c</i></sup> > *a*<sup><i>b</i> + <i>c</i></sup>*b*<sup><i>c</i> + <i>a</i></sup>*c*<sup><i>a</i> + <i>b</i></sup>.


证明I: 由题设可知 *a* > *b* > *c* > 0. 则为证原命题成立, 只需证2*a*ln*a* + 2*b*ln*b* + 2*c*ln*c* > (*b* + *c*)ln*a* + (*c* + *a*)ln*b* + (*a* + *b*)ln*c*成立. 由函数f(*x*) = ln*x*在定义域上的严格单调性, 有 ln*a* > ln*b* > ln*c*. 由排序不等式同序和 ≥ 乱序和知: *a*ln*a* + *b*ln*b* + *c*ln*c* > *b*ln*a* + *c*ln*b* + *a*ln*c*, 以及 *a*ln*a* + *b*ln*b* + *c*ln*c* > *c*ln*a* + *a*ln*b* + *b*ln*c*. 两式相加即有 2*a*ln*a* + 2*b*ln*b* + 2*c*ln*c* > (*b* + *c*)ln*a* + (*c* + *a*)ln*b* + (*a* + *b*)ln*c*. 从而原不等式成立.

证明II: 由题设可知 *a* > *b* > *c* > 0, 即有(*a* / *b*) > 1, (*b* / *c*) > 1, (*c* / *a*) > 1. 且 *a* - *b* > 0, *b* - *c* > 0, *a* - *c* > 0. 从而 (*a*<sup>2<i>a</i></sup>*b*<sup>2<i>b</i></sup>*c*<sup>2<i>c</i></sup>) / (*a*<sup><i>b</i> + <i>c</i></sup>*b*<sup><i>c</i> + <i>a</i></sup>*c*<sup><i>a</i> + <i>b</i></sup>) = *a*<sup>2<i>a</i> - (<i>b</i> + <i>c</i>)</sup>*b*<sup>2<i>b</i> - (<i>c</i> + <i>a</i>)</sup>*c*<sup>2<i>c</i> - (<i>a</i> + <i>b</i>)</sup> = *a*<sup>(<i>a</i> - <i>b</i>) + (<i>a</i> - <i>c</i>)</sup>*b*<sup>(<i>b</i> - <i>c</i>) + (<i>b</i> - <i>a</i>)</sup>*c*<sup>(<i>c</i> - <i>a</i>) + (<i>c</i> - <i>b</i>)</sup> = (<i>a</i> / <i>b</i>)<sup><i>a</i> - <i>b</i></sup>(<i>a</i> / <i>c</i>)<sup><i>a</i> - <i>c</i></sup>(<i>b</i> / <i>c</i>)<sup><i>b</i> - <i>c</i></sup> > 1<sup>0</sup> × 1<sup>0</sup> × 1<sup>0</sup> = 1. 因此 *a*<sup>2<i>a</i></sup>*b*<sup>2<i>b</i></sup>*c*<sup>2<i>c</i></sup> > *a*<sup><i>b</i> + <i>c</i></sup>*b*<sup><i>c</i> + <i>a</i></sup>*c*<sup><i>a</i> + <i>b</i></sup>.