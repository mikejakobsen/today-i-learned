---
title: Grep For Files Without A Match
layout: post
date: 2016-07-19 22:21:29
category: Zsh
tags: [Zsh]
---

The `grep` command is generally used to find files whose contents match a
pattern. With the `-L` (`--files-without-match`) flag, `grep` can be used to
find files that don't match the given pattern.

For instance, to find files in the current directory that don't have
`foobar` anywhere in their content, run:

```bash
$ grep -L "foobar" ./*
```
