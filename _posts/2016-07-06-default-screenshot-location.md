---
title: Default Screenshot Location
layout: post
date: 2016-07-06 09:21:29
category: Zsh
tags: [Zsh]
---

By default, Mac saves all screenshots to the desktop. If you'd like
screenshots to be dumped somewhere else, you have to configure it manually
from the command line. For instance, if you'd like your screenshots to be
saved in the `~/screenshots` directory, then enter the following commands:

```bash
$ mkdir ~/Screenshots
$ defaults write com.apple.screencapture location ~/Screenshots
$ killall SystemUIServer
```
