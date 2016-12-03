---
title: Create A Named tmux Session
layout: post
date: 2016-06-12 09:21:29
category: Tmux
tags: [Tmux]
---

When creating a new tmux session

```bash
$ tmux new
```

a default name of `0` will be given to the session.

If you'd like to give your session a name with a bit more meaning, use the
`-s` flag

```bash
$ tmux new -s burrito
```

[source](https://robots.thoughtbot.com/a-tmux-crash-course)
