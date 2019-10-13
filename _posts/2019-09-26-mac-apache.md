---
layout: post
title: "macOS 上 Apache 服务器的使用"
description: "希望能正式用上 80 端口 Apache 服务的 MAMP."
date: 2019-09-26
tags: [提高姿势水平]
comments: true
share: true
---

> 希望能正式用上 80 端口 Apache 服务的 MAMP.

先看一下 mac 上操作 Apache 状态的命令:

```bash
sudo apachectl start    # 启动 Apache, 这个我没试过.
sudo apachectl restart  # 重启 Apache, 这个我也没试过.
sudo apachectl stop     # 停止 Apache, 这个确实是好用的.
sudo apachectl reload   # 我猜也许有这么个命令, 没试过.
sudo apachectl status   # 查看 Apache 状态, 看起来是有用的.
```

mac 上的 Apache 好像默认是给开了. 像是 `chkconfig httpd on` 的那种效果. 不过开机关 Apache 的话好像比较麻烦, 不是很像 Linux 风格. 就先不研究了, 我每次都手动关一下还不行么...

关于 MAMP Pro 的设置端口问题, 可以看下  [MAMP PRO (Mac) Documentation &gt; Settings &gt; Hosts &gt; General](https://documentation.mamp.info/en/MAMP-PRO-Mac/Settings/Hosts/General/).

