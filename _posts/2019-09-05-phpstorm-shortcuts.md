---
layout: post
title: "PhpStorm 快捷键等使用"
description: "人类与动物的区别正在于人类会使用工具."
date: 2019-09-05
tags: [提高姿势水平]
comments: true
share: true
---

> 人类与动物的区别正在于人类会使用工具.

目录:

* TOC
{:toc}

IntelliJ IDEA CE😅、WebStorm、PhpStorm 我都用过, 但很显然属于那种运行完一跑的层次, 这把好好看下它们还能干什么😂

这里以 macOS 版的 JetBrains 家软件为准, 别的平台暂不考虑.

## Mac 修饰键

先回顾一下 Mac 的修饰键, 请参考苹果官网的文章 [Mac 上的菜单中显示的那些符号表示什么？](https://support.apple.com/zh-cn/guide/mac-help/cpmh0011/mac) 以及 [Mac 键盘快捷键](https://support.apple.com/zh-cn/HT201236).

不多说, 直接上图:

<!--![mac snapshots.png](https://i.loli.net/2019/09/05/IgXOxYeBsuiwy7J.png)-->

<table data-type="Multicolumn" aria-label="修饰键符号">
<thead>
<tr>
<th scope="col"><p class="TableHead">修饰键</p></th>
<th scope="col"><p class="TableHead">符号</p></th>
</tr>
</thead>
<tbody>
<tr><td><p>Command</p></td><td><figure><img src="https://help.apple.com/assets/5BFDD3F8094622802EEE504F/5BFDD3F9094622802EEE5056/zh_CN/9808e0a4c5ca7d8f3661af19ca54058e.png" alt="Command 符号" height="23" width="23" originalImageName="SharedGlobalArt/L0060_modcm.png"></figure></td></tr>
<tr><td><p>Shift</p></td><td><figure><img src="https://help.apple.com/assets/5BFDD3F8094622802EEE504F/5BFDD3F9094622802EEE5056/zh_CN/da6e9b7f91e7eb13915e29d5288d8d3f.png" alt="Shift 符号" height="23" width="23" originalImageName="SharedGlobalArt/L0073_modsh.png"></figure></td></tr>
<tr><td><p>Option</p></td><td><figure><img src="https://help.apple.com/assets/5BFDD3F8094622802EEE504F/5BFDD3F9094622802EEE5056/zh_CN/4fa4885c9111e0de6faeb637be746e2a.png" alt="Option 符号" height="23" width="23" originalImageName="SharedGlobalArt/L0068_modop.png"></figure></td></tr><tr><td><p>Control</p></td><td><figure><img src="https://help.apple.com/assets/5BFDD3F8094622802EEE504F/5BFDD3F9094622802EEE5056/zh_CN/d4a120294e44333f6ec6c00ef4648ee1.png" alt="Control 符号" height="23" width="23" originalImageName="SharedGlobalArt/L0061_modcn.png"></figure></td></tr><tr><td><p>Return</p></td><td><figure><img src="https://help.apple.com/assets/5BFDD3F8094622802EEE504F/5BFDD3F9094622802EEE5056/zh_CN/078689fe0beeb14141babebacd04c2b6.png" alt="Return 符号" height="23" width="23" originalImageName="SharedGlobalArt/L0072_modrtn.png"></figure></td></tr><tr><td><p>Delete</p></td><td><figure><img src="https://help.apple.com/assets/5BFDD3F8094622802EEE504F/5BFDD3F9094622802EEE5056/zh_CN/218d37fa854c02bcf94075c546a8c409.png" alt="Delete 符号" height="23" width="23" originalImageName="SharedGlobalArt/L0062_moddl.png"></figure></td></tr><tr><td><p>向前删除键</p></td><td><figure><img src="https://help.apple.com/assets/5BFDD3F8094622802EEE504F/5BFDD3F9094622802EEE5056/zh_CN/ada1e91f6f600e9bedfd0cfa6350016e.png" alt="向前删除符号" height="23" width="23" originalImageName="SharedGlobalArt/L0065_modfdl.png"></figure></td></tr><tr><td><p>上箭头键</p></td><td><figure><img src="https://help.apple.com/assets/5BFDD3F8094622802EEE504F/5BFDD3F9094622802EEE5056/zh_CN/f0580e8a608126a12c53e7e9cb781f6a.png" alt="上箭头符号" height="23" width="23" originalImageName="SharedGlobalArt/L0076_modup.png"></figure></td></tr><tr><td><p>下箭头键</p></td><td><figure><img src="https://help.apple.com/assets/5BFDD3F8094622802EEE504F/5BFDD3F9094622802EEE5056/zh_CN/c3eaebe7bf4f546981782483deb66c3d.png" alt="下箭头符号" height="23" width="23" originalImageName="SharedGlobalArt/L0063_moddn.png"></figure></td></tr><tr><td><p>左箭头键</p></td><td><figure><img src="https://help.apple.com/assets/5BFDD3F8094622802EEE504F/5BFDD3F9094622802EEE5056/zh_CN/48aad3ebcec5008affc2c4d1909e8181.png" alt="左箭头符号" height="23" width="23" originalImageName="SharedGlobalArt/L0067_modlt.png"></figure></td></tr><tr><td><p>右箭头键</p></td><td><figure><img src="https://help.apple.com/assets/5BFDD3F8094622802EEE504F/5BFDD3F9094622802EEE5056/zh_CN/910af33ff9bce5ce72f76173bbee6db8.png" alt="右箭头符号" height="23" width="23" originalImageName="SharedGlobalArt/L0071_modrt.png"></figure></td></tr><tr><td><p>Page Up</p></td><td><figure><img src="https://help.apple.com/assets/5BFDD3F8094622802EEE504F/5BFDD3F9094622802EEE5056/zh_CN/3ebb2923e18011444f96c5250e45aba5.png" alt="Page Up 符号" height="23" width="23" originalImageName="SharedGlobalArt/L0070_modpup.png"></figure></td></tr><tr><td><p>Page Down</p></td><td><figure><img src="https://help.apple.com/assets/5BFDD3F8094622802EEE504F/5BFDD3F9094622802EEE5056/zh_CN/293ba6a98cc6b5d2ef0c991aa127b16b.png" alt="Page Down 符号" height="23" width="23" originalImageName="SharedGlobalArt/L0069_modpdn.png"></figure></td></tr><tr><td><p>Top (Home)</p></td><td><figure><img src="https://help.apple.com/assets/5BFDD3F8094622802EEE504F/5BFDD3F9094622802EEE5056/zh_CN/f2459d16a2dc99487ffedccd96ba2371.png" alt="Top 符号" height="23" width="23" originalImageName="SharedGlobalArt/L0066_modhm.png"></figure></td></tr><tr><td><p>End</p></td><td><figure><img src="https://help.apple.com/assets/5BFDD3F8094622802EEE504F/5BFDD3F9094622802EEE5056/zh_CN/070b28862a467ea7a5adc92d58159d4c.png" alt="End 符号" height="23" width="23" originalImageName="SharedGlobalArt/L0064_modend.png"></figure></td></tr><tr><td><p>右制表符</p></td><td><figure><img src="https://help.apple.com/assets/5BFDD3F8094622802EEE504F/5BFDD3F9094622802EEE5056/zh_CN/cd484d20455f2ae2026ed324d873c1d7.png" alt="右制表符符号" height="23" width="23" originalImageName="SharedGlobalArt/L0075_modtabr.png"></figure></td></tr><tr><td><p>左制表符</p></td><td><figure><img src="https://help.apple.com/assets/5BFDD3F8094622802EEE504F/5BFDD3F9094622802EEE5056/zh_CN/980be5db7a048e35a2227a5ecf9f1118.png" alt="左制表符符号" height="23" width="23" originalImageName="SharedGlobalArt/L0074_modtabl.png"></figure></td></tr><tr><td><p>Escape (Esc)</p></td><td><figure><img src="https://help.apple.com/assets/5BFDD3F8094622802EEE504F/5BFDD3F9094622802EEE5056/zh_CN/aa1397cc08985a6824afe45c4f62ac87.png" alt="Escape 符号" height="23" width="23" originalImageName="SharedGlobalArt/L0077_modesc.png"></figure></td></tr>
</tbody>
</table>

苹果家官网的修饰键图标使用了 `<figure>` 标签. 关于这个标签的介绍, 可见: [`<figure>`: The Figure with Optional Caption element](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/figure). 以前有一次想用, 但用完感觉效果不对, 这把学习一下人家的使用场景和效果.


上网找到一个文字版的: [Making Sense of Mac Keyboard Symbols](http://osxdaily.com/2012/03/27/making-sense-of-mac-keyboard-symbols/):

⌘ is the Command () key.
⌃ is the Control key.
⌥ is the Option (alt) key.
⇧ is the Shift key.
⇪ is the Caps Lock key.
fn is the Function key. Now you know, but if the symbols confuse you, don't feel too bad about it.

⌘ is command 
⌥ is option 
⌃ is control 
⇧ is shift 
⇪ is caps lock 
← is left arrow 
→ is right arrow 
↑ is up arrow 
↓ is down arrow 
⇥ is tab 
⇤ is backtab 
↩ is return 
⌤ is enter 
⌫ is delete 
⌦ is forward delete 
⇞ is page up 
⇟ is page down 
↖ is home 
↘ is end 
⌧ is clear 
␣ is space 
⎋ is escape 
⏏ is eject

## PhpStorm 快捷键

⌘ is the Command () key.
⌃ is the Control key.
⌥ is the Option (alt) key.
⇧ is the Shift key.
⇪ is the Caps Lock key.
fn is the Function key. Now you know, but if the symbols confuse you, don't feel too bad about it.

* command + shift + A (⌘⇧A): 这个就是 “Help > Find Action...”, 你可以通过这组快捷键搜索到 PhpStorm 任何一个可配置的选项.




