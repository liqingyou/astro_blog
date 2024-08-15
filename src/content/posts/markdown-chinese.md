---
title: Markdown 示例
published: 2024-08-13
description: 一个简单的示例, 使用markdown构建
tags: [Markdown, Blogging, Demo]
category: Examples
draft: false
---

# An h1 header

段落之间以空行分隔。

第二个段落. _斜体_, **粗体**, and `等宽字体`. 逐项列表
看起来像:

- 这个
- 那个
- 其他

请注意 --- 不考虑星号 --- 实际的文本
内容从 4 列开始。

> 区块引用
> 写法如下.
>
> 它们可以跨越多个段落,
> 如果你喜欢.

使用 3 个破折号作为破折号. 使用 2 个破折号表示范围 (ex., "it's all
in chapters 12--14"). 三个点 ... 将转换为省略号.
支持 Unicode。☺

## An h2 header

以下是编号列表:

1. 第一个 item
2. 第二个 item
3. 第三个 item

请再次注意实际文本如何从 4 列开始 (从左侧开始 4 个字符). Here's a code sample:

    # Let me re-iterate ...
    for i in 1 .. 10 { do-something(i) }

你可能已经猜到了，缩进 4 个空格。顺便说一下，
缩进块，如果你愿意，可以使用分隔块

```
define foobar() {
    print "Welcome to flavor country!";
}
```

(这使得复制和粘贴更加容易). 您可以选择标记
分隔块，以便 Pandoc 语法高亮显示它:

```python
import time
# Quick, count to ten!
for i in range(10):
    # (but not *too* quick)
    time.sleep(0.5)
    print i
```

### An h3 header

现在是一个嵌套列表:

1. 首先，准备好这些材料:

    - 胡萝卜
    - 芹菜
    - 扁豆

2. 烧开一些水.

3. 将所有东西倒入锅中，然后按照以下算法操作：

        找到木勺
        揭开锅盖
        搅拌
        盖上锅盖
        将木勺平稳地放在锅柄上
        等待 10 分钟
        转到第一步（完成后关闭炉子）

    不要碰到木勺，否则它会掉下来。

再次注意文本如何始终在 4 个空格的缩进上对齐（包括
上面第 3 项的最后一行）。

这里有一个链接 [一个网站](http://foo.bar), 跳转 [本地文章](local-doc.html),
 and to a [这篇文章的header](#an-h2-header). 以下是脚注 [^1].

[^1]: 此处为脚注文字

表格可以像这样:

size material color

---

9 leather brown
10 hemp canvas natural
11 glass transparent

Table: Shoes, their sizes, and what they're made of

(The above is the caption for the table.) Pandoc also supports
multi-line tables:

---

keyword text

---

red Sunsets, apples, and
other red or reddish
things.

green Leaves, grass, frogs
and other things it's
not easy being.

---

A horizontal rule follows.

---

Here's a definition list:

apples
: Good for making applesauce.
oranges
: Citrus!
tomatoes
: There's no "e" in tomatoe.

Again, text is indented 4 spaces. (Put a blank line between each
term/definition pair to spread things out more.)

Here's a "line block":

| Line one
| Line too
| Line tree

and images can be specified like so:

[//]: # (![example image]&#40;./demo-banner.png "An exemplary image"&#41;)

Inline math equations go in like so: $\omega = d\phi / dt$. Display
math should get its own line and be put in in double-dollarsigns:

$$I = \int \rho R^{2} dV$$

And note that you can backslash-escape any punctuation characters
which you wish to be displayed literally, ex.: \`foo\`, \*bar\*, etc.
