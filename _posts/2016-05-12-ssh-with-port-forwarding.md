---
title: SSH With Port Forwarding
layout: post
date: 2016-05-12 09:21:29
category: Zsh
tags: [Zsh]
---

Use the `-L` flag with `ssh` to forward a connection to a remote server

```
$ ssh someserver -L3000:localhost:3000
```
