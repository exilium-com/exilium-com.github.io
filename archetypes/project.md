---
title: {{ replace .Name "-" " " | title }}
date: {{ dateFormat "2006-01-02" .Date }}
image : images/portfolio/generic.jpg
# image_webp : images/portfolio/generic.webp
draft: true
# hasMath: true # define this to be able to use math typesetting between $ $ or $$ $$
categories:
  - Games
---

# Project Name

Describe project, with pictures, math, etc.
Use markdown that is GitHub-flavored, detailed in the [Goldmark docs](https://github.com/yuin/goldmark#goldmark).
Also supports [Hugo shortcodes](https://gohugo.io/content-management/shortcodes/#use-hugos-built-in-shortcodes).
And supports math typesetting using [$\KaTeX$](https://www.katex.org).
It uses $\LaTeX$ [compatible syntax](https://math.meta.stackexchange.com/questions/5020/mathjax-basic-tutorial-and-quick-reference).