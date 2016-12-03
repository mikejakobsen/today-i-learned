---
title: What Is The Current Branch?
layout: post
date: 2016-09-12 13:21:29
category: Git
tags: [Git]
---

This question can be answered with one of git's plumbing commands,
`rev-parse`.

```
$ git rev-parse --abbrev-ref HEAD
```

The `--abbrev-ref` flag tells `git-rev-parse` to give us the short name for
`HEAD` instead of the SHA.
