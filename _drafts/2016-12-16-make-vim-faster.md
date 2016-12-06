
---
title: Tips to make Vim faster
layout: post
date: 2016-12-06 22:21:29
category: Vim
tags: [Vim]
---

It's always a good idea to install [MacVim] with Lua support. [Homebrew] does not compile with Lua support by default.

```
brew install macvim --with-cscope --with-lua --override-system-vim --with-luajit --with-python3
```

The option `--override-system-vim` will allow you to use `vim` in the command line apart from the GUI... also a great idea.

[MacVim]: https://github.com/macvim-dev/macvim
[Homebrew]: http://brew.sh/
