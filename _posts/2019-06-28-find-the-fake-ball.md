---
layout: post
title: "找假球"
description: "有12个球，外形一模一样，其中有11个是真球，重量相等; 有1个假球，与真球重量不同，但不知道假球比真球重还是轻. 问能否用没有砝码的天平称三次，将假球找出来，并判断出假球比真球重还是轻."
date: 2019-06-28
tags: [数学]
comments: true
share: true
---

> 有 12 个球，外形一模一样，其中有 11 个是真球，重量相等；有 1 个假球，与真球重量不同，但不知道假球比真球重还是轻。问能否用没有砝码的天平称三次，将假球找出来，并判断出假球比真球重还是轻。

题目如上述。

解答:

用 B<sub>1</sub>，B<sub>2</sub>，B<sub>3</sub>，B<sub>4</sub>，B<sub>5</sub>，B<sub>6</sub>，B<sub>7</sub>，B<sub>8</sub>，B<sub>9</sub>，B<sub>10</sub>，B<sub>11</sub>，B<sub>12</sub>分别表示这12个球. 用{B<sub>x</sub>，B<sub>xx</sub>，B<sub>xxx</sub>，...}表示某几个球构成的集合(也就是组). 将这12个球分为每组4个的三组<strong>G<sub>1</sub></strong>、<strong>G<sub>2</sub></strong>和<strong>G<sub>3</sub></strong>: 

* G<sub>1</sub>组 := {B<sub>1</sub>，B<sub>2</sub>，B<sub>3</sub>，B<sub>4</sub>};
* G<sub>2</sub>组 := {B<sub>5</sub>，B<sub>6</sub>，B<sub>7</sub>，B<sub>8</sub>};
* G<sub>3</sub>组 := {B<sub>9</sub>，B<sub>10</sub>，B<sub>11</sub>，B<sub>12</sub>}. 

用 w({B<sub>x</sub>，B<sub>xx</sub>，B<sub>xxx</sub>，...})表示将某几个球放在天平上称重。用`>`表示天平上左边的球的重量比右边的球的重量大，用`<`表示天平上左边的球的重量比右边的球的重量小，用`=`表示天平上两边球的重量相等即天平平衡。用`~`表示天平两边球的重量大小关系待定。


1. 先比较第一组和第二组。如果平衡，则说明假球在第三组，然后称两次可以判断假球，过程如下：
比较 w({B<sub>1</sub>，B<sub>2</sub>，B<sub>3</sub>}) 和 w({B<sub>9</sub>，B<sub>10</sub>，B<sub>11</sub>})，如果平衡，则说明 B<sub>12</sub>是假球，然后任取一真球和B<sub>12</sub>比较，就可以完满解决；如果不平衡，则说明假球在{{B<sub>9</sub>，B<sub>10</sub>，B<sub>11</sub>}}中，并且可以判断假球比真球重还是轻，然后比较B<sub>9</sub>和B<sub>10</sub>即可判断出哪个是假球。
2. 如果不平衡，不妨假设 w({B<sub>1</sub>, B<sub>2</sub>, B<sub>3</sub>, B<sub>4</sub>}) > w({B<sub>5</sub>, B<sub>6</sub>, B<sub>7</sub>, B<sub>8</sub>})，那么假球在前两组中，B<sub>9</sub>, B<sub>10</sub>, B<sub>11</sub>, B<sub>12</sub>为真球。
   
   下面比较 w({B<sub>1</sub>, B<sub>2</sub>, B<sub>3</sub>, B<sub>5</sub>}) 与 w({B<sub>4</sub>, B<sub>9</sub>, B<sub>10</sub>, B<sub>11</sub>})，有三种情况：
    
   * 如果平衡，则说明 B<sub>1</sub>, B<sub>2</sub>, B<sub>3</sub>, B<sub>4</sub>, B<sub>5</sub> 全为真球，那么假球在 {B<sub>6</sub>, B<sub>7</sub>, B<sub>8</sub>} 中，且由 w({B<sub>1</sub>, B<sub>2</sub>, B<sub>3</sub>, B<sub>4</sub>}) > w({B<sub>5</sub>, B<sub>6</sub>, B<sub>7</sub>, B<sub>8</sub>}) 知假球比真球轻。进一步比较w({B<sub>6</sub>})和w({B<sub>7</sub>})，若平衡则B<sub>8</sub>为假球，若不平衡则 B<sub>6</sub> 和 B<sub>7</sub> 中的轻者为假球;
   * 如果 w({B<sub>1</sub>, B<sub>2</sub>, B<sub>3</sub>, B<sub>5</sub>}) > w({B<sub>4</sub>, B<sub>9</sub>, B<sub>10</sub>, B<sub>11</sub>})，则 {B<sub>4</sub>, B<sub>5</sub>} 中不可能包含假球，否则将 B<sub>4</sub> 和 B<sub>5</sub> 左右交换位置，不等号会改变方向，因此假球在 {B<sub>1</sub>, B<sub>2</sub>, B<sub>3</sub>} 中，且比真球重。进一步比较 w({B<sub>1</sub>}) 和 w({B<sub>2</sub>})，若平衡则 B<sub>3</sub> 为假球，若不平衡则重者为假球；
   * 如果 w({B<sub>1</sub>, B<sub>2</sub>, B<sub>3</sub>, B<sub>5</sub>}) < w({B<sub>4</sub>, B<sub>9</sub>, B<sub>10</sub>, B<sub>11</sub>})，则 B<sub>4</sub>，B<sub>5</sub> 不能全为真球，否则假球必在 {B<sub>1</sub>，B<sub>2</sub>，B<sub>3</sub>} 中且比真球轻，这与 w({B<sub>1</sub>，B<sub>2</sub>，B<sub>3</sub>，B<sub>4</sub>}) > w({B<sub>5</sub>，B<sub>6</sub>，B<sub>7</sub>，B<sub>8</sub>}) 矛盾，因此假球为 B<sub>4</sub> 和 B<sub>5</sub> 之一，这时，显然 B<sub>4</sub> 比 B<sub>5</sub> 重。任取真球 B<sub>1</sub> 与 B<sub>4</sub> 比较，若平衡则 B<sub>5</sub> 为假球且比真球轻；若 w({B<sub>1</sub>}) < w({B<sub>4</sub>})，则 B<sub>4</sub> 为假球且比真球重；w({B<sub>1</sub>}) > w({B<sub>4</sub>}) 的情况不可能发生(因为球的重量只有两种)。
3. 如果 w({B<sub>5</sub>，B<sub>6</sub>，B<sub>7</sub>，B<sub>8</sub>}) > w({B<sub>1</sub>，B<sub>2</sub>，B<sub>3</sub>，B<sub>4</sub>})，比较过程与 2. 完全类似，这里从略。


<!--
<style type="text/css">
.tg  {border-collapse:collapse;border-spacing:0;}
.tg td{font-family:Arial，sans-serif;font-size:14px;padding:10px 5px;border-style:solid;border-width:1px;overflow:hidden;word-break:normal;border-color:black;}
.tg th{font-family:Arial，sans-serif;font-size:14px;font-weight:normal;padding:10px 5px;border-style:solid;border-width:1px;overflow:hidden;word-break:normal;border-color:black;}
.tg .tg-0pky{border-color:inherit;text-align:left;vertical-align:top}
.tg .tg-0lax{text-align:left;vertical-align:top}
</style>
-->

<table class="tg">
  <tr>
    <th class="tg-0pky">第一次比较</th>
    <th class="tg-0lax">第二次比较</th>
    <th class="tg-0lax">第三次比较</th>
  </tr>
  <tr>
    <td class="tg-0lax" rowspan="3">G<sub>1</sub> = G<sub>2</sub></td>
    <td class="tg-0lax">w({B<sub>1</sub>，B<sub>2</sub>，B<sub>3</sub>}) = w({B<sub>9</sub>，B<sub>10</sub>，B<sub>11</sub>})</td>
    <td class="tg-0lax">w({B<sub>1</sub>}) ~ w({B<sub>12</sub>})</td>
  </tr>
  <tr>
    <td class="tg-0lax">w({B<sub>1</sub>，B<sub>2</sub>，B<sub>3</sub>}) > w({B<sub>9</sub>，B<sub>10</sub>，B<sub>11</sub>})</td>
    <td class="tg-0lax">w({B<sub>9</sub>}) ~ w({B<sub>10</sub>})</td>
  </tr>
  <tr>
    <td class="tg-0lax">w({B<sub>1</sub>，B<sub>2</sub>，B<sub>3</sub>}) < w({B<sub>9</sub>，B<sub>10</sub>，B<sub>11</sub>})</td>
    <td class="tg-0lax">w({B<sub>9</sub>}) ~ w({B<sub>10</sub>})</td>
  </tr>
  <tr>
    <td class="tg-0lax" rowspan="3">G<sub>1</sub> > G<sub>2</sub></td>
    <td class="tg-0lax">w({B<sub>1</sub>，B<sub>2</sub>，B<sub>3</sub>，B<sub>5</sub>}) = w({B<sub>4</sub>，B<sub>9</sub>，B<sub>10</sub>，B<sub>11</sub>})</td>
    <td class="tg-0lax">w({B<sub>6</sub>}) ~ w({B<sub>7</sub>})</td>
  </tr>
  <tr>
    <td class="tg-0lax">w({B<sub>1</sub>，B<sub>2</sub>，B<sub>3</sub>，B<sub>5</sub>}) > w({B<sub>4</sub>，B<sub>9</sub>，B<sub>10</sub>，B<sub>11</sub>})</td>
    <td class="tg-0lax">w({B<sub>1</sub>}) ~ w({B<sub>2</sub>})</td>
  </tr>
  <tr>
    <td class="tg-0lax">w({B<sub>1</sub>，B<sub>2</sub>，B<sub>3</sub>，B<sub>5</sub>}) < w({B<sub>4</sub>，B<sub>9</sub>，B<sub>10</sub>，B<sub>11</sub>})</td>
    <td class="tg-0lax">w({B<sub>1</sub>}) ~ w({B<sub>4</sub>})</td>
  </tr>
  <tr>
    <td class="tg-0lax" rowspan="3">G<sub>1</sub> < G<sub>2</sub></td>
    <td class="tg-0lax">w({B<sub>1</sub>，B<sub>2</sub>，B<sub>3</sub>，B<sub>5</sub>}) = w({B<sub>4</sub>，B<sub>9</sub>，B<sub>10</sub>，B<sub>11</sub>})</td>
    <td class="tg-0lax">w({B<sub>6</sub>}) ~ w({B<sub>7</sub>})</td>
  </tr>
  <tr>
    <td class="tg-0lax">w({B<sub>1</sub>，B<sub>2</sub>，B<sub>3</sub>，B<sub>5</sub>}) < w({B<sub>4</sub>，B<sub>9</sub>，B<sub>10</sub>，B<sub>11</sub>})</td>
    <td class="tg-0lax">w({B<sub>1</sub>}) ~ w({B<sub>2</sub>})</td>
  </tr>
  <tr>
    <td class="tg-0lax">w({B<sub>1</sub>，B<sub>2</sub>，B<sub>3</sub>，B<sub>5</sub>}) > w({B<sub>4</sub>，B<sub>9</sub>，B<sub>10</sub>，B<sub>11</sub>})</td>
    <td class="tg-0lax">w({B<sub>1</sub>}) ~ w({B<sub>4</sub>})</td>
  </tr>
</table>