---
layout: post
title: "命令行登录 MySQL 在 macOS Catalina 中提示 zsh: command not found: mysql 的解决办法"
date: 2019-12-25
tags: [提高姿势水平,工具]
comments: true
share: true
---

升级了腰子 OS Catalina，然后就逼事儿一堆。

比如这个：

```bash
mysql -uroot -p
```

然后会提示你：

> zsh: command not found: mysql

注意 Catalina 的环境用的是 Zsh 而非 Bash，所以你配环境变量的时候，应该上 `~/.zshrc` 里去写环境变量：

```bash
export PATH=/usr/local/mysql/bin:$PATH
```

这样你 `mysql -uroot -p` 才能有反应。

在此也致敬 `~/.bash_profile`，感谢这个配置文件陪我走过一段又一段难忘的旅行，many thanks.

