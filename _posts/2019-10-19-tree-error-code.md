---
layout: post
title: "macOS 下 `tree` 命令乱码解决方案"
description: "为加速搬砖而了解你的设备."
date: 2019-10-19
tags: [提高姿势水平,工具]
comments: true
share: true
---

> 为加速搬砖而了解你的设备.

* TOC
{:toc}

## 问题情景

现在有一个目录, 我想用 `tree -CL 2` 出一个里面的内容结构(需要对内容有着充分了解), 然后好复制粘贴做目录结构图:

![tree乱码1](https://upload.cc/i1/2019/10/19/k98zed.png)

![tree乱码2](https://upload.cc/i1/2019/10/19/Nk3DfR.png)

![tree乱码3](https://upload.cc/i1/2019/10/19/sqL4QZ.png)

如上图所示, 可以看到明显的伤感情的乱码.

## 解决过程

不外乎就是问某歌问某度或是 `--help` 或是看官方文档或是看 API.

`tree --help` 一下:

![tree--help-1](https://upload.cc/i1/2019/10/19/WPU9hQ.png)

![tree--help-2](https://upload.cc/i1/2019/10/19/qMC5EN.png)

可以看到一条:

> ```
>   ------- File options -------
>  -q            Print non-printable characters as '?'.
>  -N            Print non-printable characters as is.
> ...
> ```

所以追加一个 `N` 参数即可.

## 成果验收

`tree -NCL 2` 之后, 结果如下:

![treeNCL1](https://upload.cc/i1/2019/10/19/t2v5WL.png)

![treeNCL2](https://upload.cc/i1/2019/10/19/oTpW5Q.png)

![treeNCL3](https://upload.cc/i1/2019/10/19/4wkGHE.png)

至此, 问题解决.

当然, 为了过滤掉没有意义的内容, 比如 `.srt` 后缀的字幕文件, 你可以输入 `tree -NCL 2 | grep -v ".srt"`, 效果如下:

![tree-NCLgrep-v1](https://upload.cc/i1/2019/10/19/YxIq21.png)

![tree-NCLgrep-v2](https://upload.cc/i1/2019/10/19/a09qKU.png)

记得贝老经理这种东西玩得比较溜, 我还得多向他学习.