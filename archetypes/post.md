---
title: {{ replace .Name "-" " " | title }}
date: {{ dateFormat "2006-01-02" .Date }}
author: John Doe    # author should exist in the author folder
image: images/blog/generic.jpg
# image_webp: images/blog/generic.webp
description : "Short description of the post"
categories:
  - Games
hasMath: true # define this to be able to use math typesetting between $ $ or $$ $$
draft: true
---

# Post Title

Write post with pictures, math, etc.
Use [markdown](https://www.markdownguide.org/extended-syntax) that is GitHub-flavored,
detailed in the [Goldmark docs](https://github.com/yuin/goldmark#goldmark).
Also supports [Hugo shortcodes](https://gohugo.io/content-management/shortcodes/#use-hugos-built-in-shortcodes).
And supports math typesetting using [$\KaTeX$](https://www.katex.org), if you set the property `hasMath: true`
in the post's front matter.
It uses $\LaTeX$ [compatible syntax](https://math.meta.stackexchange.com/questions/5020/mathjax-basic-tutorial-and-quick-reference).
For example, entering
```
$$e^{\infty}_{x}$$
```
in your markdown file would produce $$e^{\infty}_{x}$$