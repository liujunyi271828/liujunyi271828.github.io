---
layout: post
title: "Git 相关"
description: "继续祈祷陈工保佑我们能完成每天的产值."
date: 2019-10-22
tags: [提高姿势水平,工具]
comments: true
share: true
---

> 继续祈祷陈工保佑我们能完成每天的产值.

昨天晚上太累了, 只写了个开头就躺下了. 今天把这个写完.

之前我司有个稍微会一点儿 Git 的小哥, 但是已经跑路了. 后悔没好好珍惜; 剩下的人都没必要用 Git, 甚至都没听过 Git😂之前贝老经理也不用 Git, 倒是知道从 GitHub 上下代码; 至于我自己是单打独斗猛如虎, 和人开团零输出😂

坐车没事儿的时候打算看看: [Pro Git（中文版）](https://gitee.com/progit/). 感觉基础实在是比较抱歉. 应当补一补. 主要是我平时上下班必定会经过一个软件园, 看这个有点儿像装 X😂

昨天往一位儿子菊苣的仓库提交 PR. 本来可以很好, 后面出了个岔子, 导致我自己也不知道自己在干什么, 感觉把他坑了😂下面我尽可能把碰到的坑写一下, 以后不再犯. 毕竟我认为和用 Git 的人做同事的概率更高一些.

需求是这样. 把一个本地 repo 向两个远端 repo (比如 GitHub 和 Gitee) push. 向 GitHub 的提交好说, 这位菊苣给我过了; 但是 Gitee 的一直提交不上去. 我当然知道理论上应该是可以一个本地往两个远端地方 push, 但是实践起来有困难. 实在没办法只能把人在 Gitee 上的给 fork 过来在本地改然后再提交了. 虽然确实结果上是一样的, 但是操作手法有问题. 然后就试了一下一个本地往两个远端提交. 下面记一下.

你要向一个远端仓库提交的时候, 首先应当将这个远端仓库加入豪华 remote 套餐. 命令是:

(前提你要 `cd` 到你本地的仓库的根目录下, 否则在一个非仓库目录的 pwd 下 `add` 会报:
> fatal: not a git repository (or any of the parent directories): .git

)

```bash
git remote add 远端仓库名称 git@主机名称:仓库所有者/仓库名.git
```

先大概这么写着, 写个能看懂会用的版本. 等把 Pro Git 看差不多之后回头改.

查看远端仓库有哪些, 就是:

```bash
git remote -v
```

这个 `-v` 就相当于 `--verbose`, 话痨模式, cocoapods 的什么命令里好像有这个参数.

如果要我说的话, `git remote -v` 这个命令应该放在前面用, 看看你用了哪些远端仓库名称, 以免重名. 不知道是我智商低还是网上写得本来就不清楚的问题, 网上远端仓库基本一水儿写的 origin. 那你要提交两个岂不是必然会重.

你提交远端的时候(先玩的 GitHub, 后来用的 Gitee, 以此为例), 注意应当配置 SSH key. 否则你向远端提交的时候:

```bash
git push -u 远端仓库名称 远端仓库目标分支名称
```

会报类似这样的错误:

```
git@gitee.com: Permission denied (publickey).
fatal: Could not read from remote repository.

Please make sure you have the correct access rights
and the repository exists.
```

(以 Gitee 为例)我们是在这里添加:

![设置.png](https://i.loli.net/2019/10/23/fGPdMRiN1zQhILA.png)

点进去, 在下面的 *公钥* 的那个 `<input>` 中粘你的公钥, Gitee 会为你自动生成标题:

![公钥.png](https://i.loli.net/2019/10/23/GvXxOi7ABJfEja6.png)

你自己的公钥应该是这么看:

```bash
less(cat 也行, 随便, 主要是看文件位置) ~/.ssh/id_rsa.pub
```

然后把里面的东西复制粘贴保存, 公钥就配置好了.

下面说一下提交格式. 我是看的阮一峰老师的这篇 [Commit message 和 Change log 编写指南](http://www.ruanyifeng.com/blog/2016/01/commit_message_change_log.html), 以后如果看到更好或是更权威的再改. 那位儿子菊苣客观角度上提交格式如何我不知道, 在我目前看来确实很有法度, 也值得学习.

参考阅读:

* [常用 Git 命令清单](http://www.ruanyifeng.com/blog/2015/12/git-cheat-sheet.html)
* [Commit message 和 Change log 编写指南](http://www.ruanyifeng.com/blog/2016/01/commit_message_change_log.html)

再就我第把安了一个 commitizen:

![commitizen.png](https://i.loli.net/2019/10/23/ydjz8mwAY9VSPkX.png)

以后看看怎么用: [commitizen/cz-cli](https://github.com/commitizen/cz-cli).