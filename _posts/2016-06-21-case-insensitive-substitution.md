---
title: Case-Insensitive Substitution
layout: post
date: 2016-06-21 14:21:29
category: Vim
tags: [Vim]
---

Use the `i` `s-flag` to perform a case-insensitive substitution (search and
replace).

For instance, `:%s/blog/article/gi` will turn

```
blog bLOg BLOG Blog
```

into

```
article article article article
```

See `:h s_flags` for more details.
