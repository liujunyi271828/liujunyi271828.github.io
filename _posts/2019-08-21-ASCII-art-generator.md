---
layout: post
title: "ASCII 艺术生成器资源"
description: "不用再编源码了."
date: 2019-08-21
tags: [提高姿势水平,工具]
comments: true
share: true
---

> 不用再编源码了.

```
    __  __________    __    ____     _       ______  ____  __    ____ 
   / / / / ____/ /   / /   / __ \   | |     / / __ \/ __ \/ /   / __ \
  / /_/ / __/ / /   / /   / / / /   | | /| / / / / / /_/ / /   / / / /
 / __  / /___/ /___/ /___/ /_/ /    | |/ |/ / /_/ / _, _/ /___/ /_/ / 
/_/ /_/_____/_____/_____/\____/     |__/|__/\____/_/ |_/_____/_____/  
```


```
 ______   ______     ______        ______     ______     __    __     ______   ______     __   __     __  __    
/\  ___\ /\  __ \   /\  == \      /\  ___\   /\  __ \   /\ "-./  \   /\  == \ /\  __ \   /\ "-.\ \   /\ \_\ \   
\ \  __\ \ \ \/\ \  \ \  __<      \ \ \____  \ \ \/\ \  \ \ \-./\ \  \ \  _-/ \ \  __ \  \ \ \-.  \  \ \____ \  
 \ \_\    \ \_____\  \ \_\ \_\     \ \_____\  \ \_____\  \ \_\ \ \_\  \ \_\    \ \_\ \_\  \ \_\\"\_\  \/\_____\ 
  \/_/     \/_____/   \/_/ /_/      \/_____/   \/_____/   \/_/  \/_/   \/_/     \/_/\/_/   \/_/ \/_/   \/_____/ 
                                                                                                                
```

这个东西如果在 Markdown 里显示的话, 拿两组 <code>```</code> 在代码块儿头部和尾部包或是拿 <code>&lt;pre&gt;</code> 和 <code>&lt;/pre&gt;</code> 在头尾部一包都可以. 这块儿我的转义和 HTML 与 Markdown 混排用得比较精髓.


这个东西我见过的一般是扔到 README 或是扔到个人介绍里的. 毕竟你把这玩意儿扔代码文件头部里没卵用不说, 给人看好像也不太好, 显得你不庄重...


为什么突然想起这个, 是因为刷题的网站前端字体改了(就是那种普通的 `<code>` 形式给改成 regular 啥的), 导致 ASCII 码显示得全乱了. 于是当时就把乱了的 ASCII 码部分删掉了, 只保留了文字部分. 但是。。。我忘了留源码!!! 后来这个字体又给改了个好用的, 所以我这不就在找省事儿的 ASCII 图案生成器么...


打几个词一搜便知. 我看这个不错[Text to ASCII Art Generator (TAAG)](http://patorjk.com/software/taag/), 最底下那个 [Free online tool to create colored or monochrome Ascii Art. Also including a text to Ascii Banner option.](https://www.ascii-art-generator.org) 没仔细看, 好像是给你生成图片.


![generating-ascii-art.png](https://i.loli.net/2019/08/21/OW4JMtSRvj21sk6.png)

这个是我 LC 刷题网站上个人介绍的成品, 写好内容选好形式然后点击那个 ASCII 码版的下面的 “Select & Copy” 再 Ctrl + V 就完事儿了:

![fuck-scd.png](https://i.loli.net/2019/08/21/dPEjC8HlI26f7b3.png)


这个是他们家的相关 GitHub 目录: [patorjk/figlet.js](https://github.com/patorjk/figlet.js).

