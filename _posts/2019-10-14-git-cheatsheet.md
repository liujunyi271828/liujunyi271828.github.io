---
layout: post
title: "Git 命令小抄"
description: "学习常见 Git 命令, 为公司上市做贡献."
date: 2019-10-14
tags: [提高姿势水平,工具]
comments: true
share: true
---

> 学习常见 Git 命令, 为公司上市做贡献.

本文内容出自: [GitSheet](https://gitsheet.wtf).

一个值得学习的点是 Git 命令, 再一个值得学习的点是那个 copy 的效果.

正文开始.

<table>
  <tr>
    <th colspan="3"><strong>BRANCHES.</strong></th>
  </tr>
  <tr>
    <td><code style="color:#FF00FF">git branch</code></td>
    <td>List all local branches.</td>
    <td><input name="git branch" class="copyEl" type="button" value="Copy" readonly/></td>
  </tr>
  <tr>
    <td><code style="color:#FF00FF">git branch -a</code></td>
    <td>List remote and local branches.</td>
    <td><input name="git branch -a" class="copyEl" type="button" value="Copy" readonly/></td>
  </tr>
  <tr>
    <td><code style="color:#FF00FF">git checkout -b branch_name</code></td>
    <td>Create a local branch and switch to it.</td>
    <td><input name="git checkout -b branch_name" class="copyEl" type="button" value="Copy" readonly/></td>
  </tr>
  <tr>
    <td><code style="color:#FF00FF">git checkout branch_name</code></td>
    <td>Switch to an existing branch.</td>
    <td><input name="git checkout branch_name" class="copyEl" type="button" value="Copy" readonly/></td>
  </tr>
  <tr>
    <td><code style="color:#FF00FF">git push origin branch_name</code></td>
    <td>Push branch to remote.</td>
    <td><input name="git push origin branch_name" class="copyEl" type="button" value="Copy" readonly/></td>
  </tr>
  <tr>
    <td><code style="color:#FF00FF">git branch -m new_name</code></td>
    <td>Rename current branch.</td>
    <td><input name="git branch -m new_name" class="copyEl" type="button" value="Copy" readonly/></td>
  </tr>
  <tr>
    <td><code style="color:#FF00FF">git branch -d branch_name</code></td>
    <td>Delete a local branch.</td>
    <td><input name="git branch -d branch_name" class="copyEl" type="button" value="Copy" readonly/></td>
  </tr>
  <tr>
    <td><code style="color:#FF00FF">git push origin :branch_name</code></td>
    <td>Delete a remote branch.</td>
    <td><input name="git push origin :branch_name" class="copyEl" type="button" value="Copy" readonly/></td>
  </tr>
  <tr>
    <th colspan="3"><strong>LOGS.</strong></th>
  </tr>
  <tr>
    <td><code style="color:#FF00FF">git log --oneline</code></td>
    <td>Show commit history in single lines.</td>
    <td><input name="git log --oneline" class="copyEl" type="button" value="Copy" readonly/></td>
  </tr>
  <tr>
    <td><code style="color:#FF00FF">git log -2</code></td>
    <td>Show commit history for last N commits.</td>
    <td><input name="git log -2" class="copyEl" type="button" value="Copy" readonly/></td>
  </tr>
  <tr>
    <td><code style="color:#FF00FF">git log -p -2</code></td>
    <td>Show commit history for last N commits with diff.</td>
    <td><input name="git log -p -2" class="copyEl" type="button" value="Copy" readonly/></td>
  </tr>
  <tr>
    <td><code style="color:#FF00FF">git diff</code></td>
    <td>Show all local file changes in the working tree.</td>
    <td><input name="git diff" class="copyEl" type="button" value="Copy" readonly/></td>
  </tr>
  <tr>
    <td><code style="color:#FF00FF">git diff myfile</code></td>
    <td>Show changes made to a file.</td>
    <td><input name="git diff myfile" class="copyEl" type="button" value="Copy" readonly/></td>
  </tr>
  <tr>
    <td><code style="color:#FF00FF">git blame myfile</code></td>
    <td>Show who changed what & when in a file.</td>
    <td><input name="git blame myfile" class="copyEl" type="button" value="Copy" readonly/></td>
  </tr>
  <tr>
    <td><code style="color:#FF00FF">git remote show origin</code></td>
    <td>Show remote branches and their mapping to local.</td>
    <td><input name="git remote show origin" class="copyEl" type="button" value="Copy" readonly/></td>
  </tr>
  <tr>
    <th colspan="3"><strong>CLEANUP.</strong></th>
  </tr>
  <tr>
    <td><code style="color:#FF00FF">git clean -f</code></td>
    <td>Delete all untracked files.</td>
    <td><input name="git clean -f" class="copyEl" type="button" value="Copy" readonly/></td>
  </tr>
  <tr>
    <td><code style="color:#FF00FF">git clean -df</code></td>
    <td>Delete all untracked files and directories.</td>
    <td><input name="git clean -df" class="copyEl" type="button" value="Copy" readonly/></td>
  </tr>
  <tr>
    <td><code style="color:#FF00FF">git checkout -- .</code></td>
    <td>Undo local modifications to all files.</td>
    <td><input name="git checkout -- ." class="copyEl" type="button" value="Copy" readonly/></td>
  </tr>
  <tr>
    <td><code style="color:#FF00FF">git reset HEAD myfile</code></td>
    <td>Unstage a file.</td>
    <td><input name="git reset HEAD myfile" class="copyEl" type="button" value="Copy" readonly/></td>
  </tr>
  <tr>
    <th colspan="3"><strong>TAGS.</strong></th>
  </tr>
  <tr>
    <td><code style="color:#FF00FF">git tag</code></td>
    <td>List all tags.</td>
    <td><input name="git tag" class="copyEl" type="button" value="Copy" readonly/></td>
  </tr>
  <tr>
    <td><code style="color:#FF00FF">git tag -a tag_name -m "tag message"</code></td>
    <td>Create a new tag.</td>
    <td><input name="git tag -a tag_name -m 'tag message'" class="copyEl" type="button" value="Copy" readonly/></td>
  </tr>
  <tr>
    <td><code style="color:#FF00FF">git push --tags</code></td>
    <td>Push all tags to remote repo.</td>
    <td><input name="git push --tags" class="copyEl" type="button" value="Copy" readonly/></td>
  </tr>
  <tr>
    <th colspan="3"><strong>STASHES.</strong></th>
  </tr>
  <tr>
    <td><code style="color:#FF00FF">git stash save "stash name" && git stash</code></td>
    <td>Save changes to a stash.</td>
    <td><input name="git stash save 'stash_name' && git stash" class="copyEl" type="button" value="Copy" readonly/></td>
  </tr>
  <tr>
    <td><code style="color:#FF00FF">git stash list</code></td>
    <td>List all stashes.</td>
    <td><input name="git stash list" class="copyEl" type="button" value="Copy" readonly/></td>
  </tr>
  <tr>
    <td><code style="color:#FF00FF">git stash pop</code></td>
    <td>Apply a stash.</td>
    <td><input name="git stash pop" class="copyEl" type="button" value="Copy" readonly/></td>
  </tr>
</table>

PS: 起拷贝功能的那个 JavaScript 代码出自 [2015 年的 Stack Overflow 问题回答](https://stackoverflow.com/a/33928558):

```javascript
<script>
// Credit for copyToCliboard(text) function: https://stackoverflow.com/a/33928558

// Copies a string to the clipboard. Must be called from within an
// event handler such as click. May return false if it failed, but
// this is not always possible. Browser support for Chrome 43+,
// Firefox 42+, Safari 10+, Edge and IE 10+.
// IE: The clipboard feature may be disabled by an administrator. By
// default a prompt is shown the first time the clipboard is
// used (per session).
function copyToClipboard(text) {
    if (window.clipboardData && window.clipboardData.setData) {
        // IE specific code path to prevent textarea being shown while dialog is visible.
        return clipboardData.setData("Text", text);

    } else if (document.queryCommandSupported && document.queryCommandSupported("copy")) {
        var textarea = document.createElement("textarea");
        textarea.textContent = text;
        textarea.style.position = "fixed";  // Prevent scrolling to bottom of page in MS Edge.
        document.body.appendChild(textarea);
        textarea.select();
        try {
            return document.execCommand("copy");  // Security exception may be thrown by some browsers.
        } catch (ex) {
            console.warn("Copy to clipboard failed.", ex);
            return false;
        } finally {
            document.body.removeChild(textarea);
        }
    }
}

var myDivs = document.getElementsByClassName('copyEl');

for (var i = 0; i < myDivs.length; i++) {
    myDivs[i].addEventListener('click', function (event) {
        copyToClipboard(this.getAttribute("name"));

        // Indicate last copied item
        for (var i = 0; i < myDivs.length; i++) {
            myDivs[i].value = "Copy";
        }
        this.value = "Copied!";
    });
}
```

<!-- copy.js: https://gitsheet.wtf/js/copy.js -->
<script>
// Credit for copyToCliboard(text) function: https://stackoverflow.com/a/33928558

// Copies a string to the clipboard. Must be called from within an
// event handler such as click. May return false if it failed, but
// this is not always possible. Browser support for Chrome 43+,
// Firefox 42+, Safari 10+, Edge and IE 10+.
// IE: The clipboard feature may be disabled by an administrator. By
// default a prompt is shown the first time the clipboard is
// used (per session).
function copyToClipboard(text) {
    if (window.clipboardData && window.clipboardData.setData) {
        // IE specific code path to prevent textarea being shown while dialog is visible.
        return clipboardData.setData("Text", text);

    } else if (document.queryCommandSupported && document.queryCommandSupported("copy")) {
        var textarea = document.createElement("textarea");
        textarea.textContent = text;
        textarea.style.position = "fixed";  // Prevent scrolling to bottom of page in MS Edge.
        document.body.appendChild(textarea);
        textarea.select();
        try {
            return document.execCommand("copy");  // Security exception may be thrown by some browsers.
        } catch (ex) {
            console.warn("Copy to clipboard failed.", ex);
            return false;
        } finally {
            document.body.removeChild(textarea);
        }
    }
}

var myDivs = document.getElementsByClassName('copyEl');

for (var i = 0; i < myDivs.length; i++) {
    myDivs[i].addEventListener('click', function (event) {
        copyToClipboard(this.getAttribute("name"));

        // Indicate last copied item
        for (var i = 0; i < myDivs.length; i++) {
            myDivs[i].value = "Copy";
        }
        this.value = "Copied!";
    });
}
</script>
