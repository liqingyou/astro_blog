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

As you probably guessed, indented 4 spaces. By the way, instead of
indenting the block, you can use delimited blocks, if you like:

```
define foobar() {
    print "Welcome to flavor country!";
}
```

(which makes copying & pasting easier). You can optionally mark the
delimited block for Pandoc to syntax highlight it:

```python
import time
# Quick, count to ten!
for i in range(10):
    # (but not *too* quick)
    time.sleep(0.5)
    print i
```

### An h3 header

Now a nested list:

1. First, get these ingredients:

    - carrots
    - celery
    - lentils

2. Boil some water.

3. Dump everything in the pot and follow
    this algorithm:

        find wooden spoon
        uncover pot
        stir
        cover pot
        balance wooden spoon precariously on pot handle
        wait 10 minutes
        goto first step (or shut off burner when done)

    Do not bump wooden spoon or it will fall.

Notice again how text always lines up on 4-space indents (including
that last line which continues item 3 above).

Here's a link to [a website](http://foo.bar), to a [local
doc](local-doc.html), and to a [section heading in the current
doc](#an-h2-header). Here's a footnote [^1].

[^1]: Footnote text goes here.

Tables can look like this:

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
