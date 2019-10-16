---
layout: post
title: "Git Pages 博客主题重要改革感言"
description: "成功完成了 GitHub 主题的重要改革, 发表一下感言."
date: 2019-10-14
tags: [提高姿势水平]
comments: true
share: true
---

> 成功完成了 GitHub 主题的重要改革, 发表一下感言.

在昨天这样一个特殊的日子里, 把自己博客主题改了, 具体可以参见: [关于 Intrastellar](https://liujunyi271828.github.io/about/). 当然了, 如果有哪位旁友看的话, 最好是祈祷我别再次发起改革, 以免链接丢失😂

我就不截图自证了, 反正确实是改了, 就是想折腾一下图个乐呵. 

下面谈一下我做的大改动或是感兴趣的东西吧.

1. 404 界面定做问题. 之前的主题的 404 页是 `404.html`, 确实是好用的; 换的这个新主题的 404 页对应的是 `404.md`. 当时新主题的这个 404 是不好用的. 然后我就把新主题的 `404.md` 和以前的主题的 `404.html` 比对了一下, 发现以前的多个 `permalink: /404.html`, 然后我想咱这个是 `.md`, 怎么着不得 `permalink: /404.md` 吧, 虽然有点儿奇怪😂 当然这个是不行的...后来 `permalink: /404/` 也试了下, 就 `网站URL/404/` 是好用的😂 后来还改了 `layout`... 实在没办法就某度了一下, 没看着写得好的; 后来就用了某歌, 我当时搜的是:“custom git page 404”, 这把可以了: ![404custom](https://upload.cc/i1/2019/10/14/KOd1QG.png) 进去之后可以看到: ![permalink](https://upload.cc/i1/2019/10/14/gcnPHs.png) 这就是我们要的答案. 注意要把 `permalink: /404.html` 这一行放到最前面, 放到 `layout` 或是别的什么东西的后面依然是不行的.
2. YAML. 也是通过那个 Help 页面了解到了原来那个就是 YAML(**Y**AML **A**in't **M**arkup **L**anguage), 看了一下 [The Official YAML Web Site](https://yaml.org), 感觉这个东西和 JSON 性质差不多. 具体的教程可以看看 [YAML Ain’t Markup Language (YAML™) Version 1.2: 3rd Edition, Patched at 2009-10-01](https://yaml.org/spec/1.2/spec.html). 不过目前还没在 Git Pages 以外的场景见过它...
3. 博客主题. 可以看 [Jekyll Themes](http://jekyllthemes.org) 这个页面选自己喜欢的主题 fork 到自己的 GitHub Repository 然后再上命令行里 `git clone path/to/yourusername.github.io.git` 就行, 当然这次我没弄, 只是记一下告诉自己有那么个东西而已. 如果启动不了的话就 `vi` 一下 `博客根目录/_config.yml` 然后 `:wq` 完 PR 给自己然后 merge, 基本上能好用. 确实有别人看起来的高大上侧边栏那种的, 但是我真就只喜欢性冷淡的殡仪馆风格😂 再就大部分主题可能手机上看可能有些问题, 所以我选了这个主题. 这个看个人喜好吧.
4. `.git` 目录问题. 如图在 ![项目摘要](https://upload.cc/i1/2019/10/14/dPYtaw.png) 红框里的位置, 你 fork 完别人的项目不改的话这些数会比较诡异, 都是原先被 fork 的项目的相应值. 所以就想清一下. 当然我这里并没有不尊重别人劳动成果的意思, 只是一多确实会显得比较乱. 我个人的做法是先把你的 Git Pages 项目做个备份, 然后 `cd` 到你本地的 Git Pages 项目根目录下, `ls -alGF` 可以看到: ![ls-alGF](https://upload.cc/i1/2019/10/14/BMOtjJ.png). 然后 `rm -rf .git` 删掉 `.git/` 目录, 再用剩下的这部分内容去重新上传到 GitHub Repository 来诱导出 `.git/` 目录, 这样就是一个比较干净的信息界面. 当然 Git 我用得不怎么好, 目前还处在上市的初级阶段, 可能效率不是那么高😂
5. 开黑. GitHub 的仓库可以添加协作者 (Collaborators), 这和刀塔开黑窝窝成立五五队的意义类似, 开黑是在这个地方: ![开黑](https://upload.cc/i1/2019/10/14/S9o7nP.png) 我设想的用法是你可以让别人和你共同来搞 private 的项目. 亲测确实是可以. ![开黑](https://upload.cc/i1/2019/10/17/TEYLht.png) 看英文简介就可以了. 这个操作需要权限狗 sudo 权限. 你加完之后需要对面确认, 算上自己似乎最多能开四人黑.
 