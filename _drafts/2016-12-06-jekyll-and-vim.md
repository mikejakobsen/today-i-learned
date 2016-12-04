---
title: Jekyll and Vim
layout: post
date: 2016-12-06 10:21:29
category: Jekyll, Vim
tags: [Jekyll, Vim]
---

Vim is kinda awful with Markdown straight out of the box.

**Example:**
- If today is 18 March 2016, `:til blog 2 new-post-title` will try to
  create or open `2016-03-20-new-post-title.md`.
- If current year is 2016, `:til blog 5/12 new-post-title` will try to
  create or open `2016-05-12-new-post-title.md`.
