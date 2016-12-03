---
title: PID Of The Current Shell
layout: post
date: 2016-05-12 09:21:29
category: Zsh
tags: [Zsh]
---

`$` expands to the process ID of the shell. So, you can see the PID of the
current shell with `echo $$`.

```bash
> echo $$
36609

> zsh

> echo $$
45431

> exit

> echo $$
36609
```

See the `Special Paramaters` section of `man bash` for more details.
