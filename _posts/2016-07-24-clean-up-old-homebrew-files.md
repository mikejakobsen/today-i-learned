---
title: Clean up Homebrew
layout: post
date: 2016-05-12 09:21:29
category: Zsh
tags: [Zsh]
---

If you've been using [Homebrew](https://github.com/Homebrew/homebrew) for a
while, you may have built up some cruft in the form old and outdated files.
These will not be cleaned up automatically. You have do tell Homebrew to do
so. This can be done with the following command.

```bash
$ brew cleanup
```

This command will report what files it cleans up as well as how much disk
space it was able to clear.

See `man brew` for more details.
