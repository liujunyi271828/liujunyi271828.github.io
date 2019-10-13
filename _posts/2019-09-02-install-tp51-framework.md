---
layout: post
title: "ThinkPHP 框架 5.1 版本 composer 安装与  &#96;ls&#96; 结果高亮"
description: "学习新版 ThinkPHP 框架的安装, 推动公司的上市."
date: 2019-09-02
tags: [提高姿势水平]
comments: true
share: true
---

> 学习新版 ThinkPHP 框架的安装, 推动公司的上市.

* TOC
{:toc}


## TP5.1 安装 

现在(2019-09-02) TP 框架还没正式发行 ThinkPHP6 的版本, 所以我们先用 ThinkPHP5.1.

这里只讲拿 Composer 安, 别的不考虑, 因为其他方法不是主流; 也不会提 Composer 怎么安, 因为没有意义, 这个是早就该弄好的东西.

以下两种方式均可安装, 前提是你要先 `cd` 到你的 WEB 文档根目录下, 比如说我的 docroot 就是 `/Application/MAMP/htdocs/`, 以下如果用到的话均以此为前提.

都不需要开梯子, 直接打开终端复制粘贴回车就可以.

* 安装方式 1:

   ```bash
   # 安装方式 1, 其中 tp51project 为你的应用根目录
   composer create-project topthink/think=5.1.* tp51project
   ```


* 安装方式 2:

   ```bash
   # 安装方式 2, 其中 tp51project 为你的应用根目录
   composer create-project topthink/think tp51project --prefer-dist
   ```

絮叨一句: 你的 WEB 文档根目录 `/Application/MAMP/htdocs/` 和你的应用根目录 `tp51project` 应该是包含与被包含的关系, 即应用根目录 `tp51project` 的完全路径为: `/Application/MAMP/htdocs/tp51project/`


## &#96;ls&#96; 结果高亮

[How can the backtick character ` be included in code?](https://meta.stackexchange.com/questions/55437/how-can-the-backtick-character-be-included-in-code) 这个其实才是我想要的结果, 不过我找到了一个解决方案所以一开始就没好好看😂

反引号 <code>&#96;</code>(十进制码: <code>&amp;#96;</code>, 注意你如果为了要表达 <code>&amp;#96;</code> 这个内容而需要使用 <code>&amp;</code> 这个符号将之展示给人看的话, 你把 <code>&amp;</code> 放在 `<code></code>` 内的时候是需要将其转义的) 放在 GitHub Pages 的标题里能被渲染出效果是要转义的. 我知道这一点然后就去查这个实体码, 但是某度三分钟没查出来, 全他妈是单引号双引号要么就是反引号在 JS 字符串里的用途; 气得没办法某歌了一下 backtick html entity, 结果一分钟就查出来 + 看完结果了, 艹他妈.

我之前也不知道 `ls` 完的结果这玩意儿怎么高亮, 也懒得上网查了. 自己动手探索一下:

不知道怎么敲命令就 `man 命令` 一下, 这个是常识:

```bash
man ls
```

然后它会给你显示出一堆讲解, 你不用全看, 何况以大多数人的水平全看也看不懂😂先按一下 `/`, 然后敲:

```bash
/color
```

为什么敲 `color` 我就不多说了, 就算是前我司的大学学韩语的档案女神, 之所以拉她过来是因为她英语够差, 但我可以肯定她知道这个词. 如果有谁连这个词都不认识的话, 说句可能伤人的, 我觉着还是赶紧找个大款嫁了或是娶个富婆来及早安排一下后半辈子. 然后回车, 接下来你中指食指上下划也行鼠标滚轮来回滚也好按 `N` 或 `B` 也可以总之慢慢儿看吧.

这里挑俩要用的:

```
···
-F      Display a slash (`/') immediately after each pathname that is a
        directory, an asterisk (`*') after each that is executable, an at
        sign (`@') after each symbolic link, an equals sign (`=') after
        each socket, a percent sign (`%') after each whiteout, and a ver-
        tical bar (`|') after each that is a FIFO.
...
-G      Enable colorized output.  This option is equivalent to defining
        CLICOLOR in the environment.  (See below.)
...
```

所以最终, 我们可以组装成一个命令: `ls -GF`, 效果如下:

![lsgf.png](https://i.loli.net/2019/09/02/fJ6joILRGSWAD2M.png)

这样又是高亮又是`/`, 省下了广大员工一个个分哪个颜色是目录哪个颜色是普通文件的时间或是避免了头昏眼花的时候少看了一个 `/` 符号, 从而可以省下时间干出更多产值. 如果有智商的话要将智商用在有意义的地方.

如果你电脑安了 tree 这个插件的话你可以: `tree -CL 1`, 其中那个数值 `1` 代表从你当前目录下探的层数.

效果如下:

![treecl.png](https://i.loli.net/2019/09/02/DSn3x9tAjo6mTlU.png)

当然你也可以 `tree -CLF 1`, 这个也算是对 `ls -GF` 的一个完美继承:

![treeclf.png](https://i.loli.net/2019/09/02/k9UOLY7yIMP4oex.png)

完事儿, 撒花.









