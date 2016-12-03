---
title: Grab A Single File From A Stash
layout: post
date: 2016-09-12 13:21:29
category: Git
tags: [Git]
---

In git, you can reference a commit SHA or branch to checkout differing
versions of files.

```bash
$ git checkout d3d2e38 -- README.md
```

In the same way, you can snag the version of a file as it existed in a
stash. Just reference the relevant stash.

```bash
$ git checkout stash@{1} -- README.md
```
