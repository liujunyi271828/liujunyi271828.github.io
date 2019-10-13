---
layout: post
title: "PHP 中 for 循环的一个优化点"
description: "为公司上市而学习语言."
date: 2019-09-04
tags: [提高姿势水平]
comments: true
share: true
---

> 为公司上市而学习语言.

有这么一个项目: [firegore2/clash-royale-php](https://github.com/firegore2/clash-royale-php), 在这个项目的 [clash-royale-php/src/Console/ConsoleMarkdown.php](https://github.com/firegore2/clash-royale-php/blob/master/src/Console/ConsoleMarkdown.php) 文件中, 有一块儿是写的:


```php
protected function consumeParagraph($lines, $current)
{
    // consume until newline
    $content = [];
    for ($i = $current, $count = count($lines); $i < $count; $i++) {
        $line = $lines[$i];
        if ($line === ''
            || ltrim($line) === ''
            || !ctype_alpha($line[0]) && (
                $this->identifyQuote($line, $lines, $i)
                || $this->identifyUl($line, $lines, $i)
                || $this->identifyOl($line, $lines, $i)
            )
        ) {
            break;
        } elseif ($this->identifyCode($line, $lines, $i)) {
            if (preg_match('~<\w+([^>]+)$~s', implode("\n", $content))) {
                $content[] = $line;
            } else {
                break;
            }
        } else {
            $content[] = $line;
        }
    }
    $block = [
        'paragraph',
        'content' => $this->parseInline(implode("\n", $content)),
    ];
    return [$block, --$i];
}
```

这里人家小哥的 `for ($i = $current, $count = count($lines); $i < $count; $i++) {...}` 是这么样写的, 那句 `$count = count($lines)` 不用拿到外面去优化.


应该去优化的是这种情形: `for ($i = $current; $i < $count = count($lines); $i++) {...}`.

出处见 [PHP Manual - Language Reference - Control Structures - for](https://www.php.net/manual/en/control-structures.for.php) 中的最后两个 demo. 说白了写这个文章主要是分清优化的情形. 这种比较简单的优化也不费啥事儿, 碰到的时候随手就可以给做了.

