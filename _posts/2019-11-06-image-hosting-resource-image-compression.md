---
layout: post
title: "图床 (image hosting) 资源整理与图片压缩介绍"
description: "为文学事业而寻找趁手的工具."
date: 2019-11-06
tags: [提高姿势水平,工具]
comments: true
share: true
---

> 为文学事业而寻找趁手的工具。

* TOC
{:toc}

整理一下常用的或者准确来说是自己用的图床服务。当前是查资料的形态，如果是普通状态的话能否访问待验证。总之全凭印象写了...

* 2019.10.21 更新：新加了个 PhotoShop 图片压缩。
* 2019.11.06 更新：新加了个 Optimizilla 图片压缩。更新 PS 压缩信息。

## 图床资源

1. [Image Upload - SM.MS - Simple Free Image Hosting](https://sm.ms)：普通状态即可使用，自带 `img[src]`、`![Alt text](/path/to/img)`、`url` 功能。内容过滤可能比较严格，且文件最大只支持 5MB（2019.10.6）。
2. [Upload.cc: 免費圖片上傳網](https://upload.cc)：只有 `url` 功能，得自己用 URL 做 Markdown 图片和 HTML 图片。内容过滤相对宽松。
3. [ImgBB — 免费图片存取/上传图片](https://imgbb.com)：貌似是普通状态即可使用，想充分发挥功能的话需要注册账号（不算复杂）。写东西的话一般是用 Direct links 和 HTML image，Markdown 图片需要自己做，但不嫌弃的话照理也可以用 HTML 图片代替。
4. [路过图床 - 免费图片上传, 专业图片外链, 免费公共图床](http://im.sb)：这个是看一位水友用的，最大单张支持 10MB。具体特性不详。
5. [你的靈感泉源。 &#x2758; Flickr](https://www.flickr.com): 需要注册账号才能使用. 看另一位宝岛水友用应该是支持 10MB 以上图片上传，能以上到多少不详。可能需要开启查资料模式才能访问。有一定社交性质。可以用作找某类图片的素材资源。
6. [Imgur: The magic of the Internet](https://imgur.com)：感觉同 Flickr。应该是需要注册账号，而相比于 Flickr 注册账号还多了个用到手机号，虽然说是支持 86 开头的国内号。如果从图床使用的角度看我还不如用 Flickr 呢，总之我个人不推荐。也是可以用作找某类图片的素材资源。
7. [照片 - Google 相册](https://photos.google.com)：上传照片的空间要从 15G 的共享空间里抛除，应该是需要开启查资料模式才能访问。
8. [Dropbox 是为减轻您的繁重工作而设计的现代化工作空间—您可以专心处理重要工作。登录并将您的创造力投入到工作中。](https://www.dropbox.com)：这个非氪金版最大只有 2G 的存储空间，优点据说是和别的博客系统联动比较好，但是具体我也没用过。一个图按 0.5MB 算的话，大概能传 4100 张。

## 图片压缩

注意在线压缩可能压着压着会卡，特别是 Optimizilla 这个，要有心理准备。

1. [TinyPNG – 压缩PNG图片的同时保留透明度](https://tinify.cn) 这个，这个神器由前面提到的那位水友推荐。<br/>感谢他的指导。<br/>TinyPNG 可以上传一个最大长度为 20 的图片队列来进行压缩处理，图片最大尺寸为 5 MB。可以分别单图下载，也可以将解压内容打包下载。
2. [在线图片优化器 - Optimizilla是一款压缩JPEG和PNG图片至尽可能小尺寸的终极的图像优化器。](https://imagecompressor.com/zh/)：前面的 TinyPNG 不氪金买 Pro 的话最多能压 5 MB 的图，再大的就压不了。亲测这个 Optimizilla 可以压 10 MB 的图。可以单图下载，也可以在队列都压完以后点“合并”多图下载。

再就像上面所说，可以使用 Photoshop 来压。先把参考材料放在这儿：[PS压缩图片文件大小,不失真！！！](https://blog.csdn.net/hetongun/article/details/78121062). 有空再整理成自己的版本。

Photoshop 可以批处理来压，操作手法见：[用Photoshop软件实现批量压缩照片](https://www.cnblogs.com/sfriend/p/10853075.html)。我觉着参考大小 200 Kb 到 500 Kb 左右就可以了。Life is short, you need Photoshop。

### 对中间操作的评论

你可能会用到一个叫 Renamer 的重命名批处理 App，你整理图片的时候可能会弄出一堆名字重复的图，但无论如何，千万不要 Replace! 千万不要 Replace! 千万不要 Replace!

再就是 Renamer 的 6 版本相对于 5 版本来说是个飞跃，5 版本忘了是你直接拖拽文件还不你点按钮从目录中加文件的时候会莫名闪退。

我个人认为应该认识到工具的一些问题，但是很不喜欢浪费时间解决这些问题。时间还是应该多花在更有用的地方上。