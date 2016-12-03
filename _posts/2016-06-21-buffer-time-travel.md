---
title: Buffer time travel
layout: post
date: 2016-06-21 14:21:29
category: Vim
tags: [Vim]
---


Vim allows you to go to an *earlier* text state for a buffer with
`:earlier`. For instance, if you want to see the state of the buffer from 10
minutes ago:

```
:earlier 10m
```

Similarly, you can move back toward the present text state of the buffer
with `:later`. If 10 minutes earlier was too far, you can come back 5
minutes like so:

```
:later 5m
```

I encountered these in [Nick Nisi's 'Vim +
Tmux'](https://www.youtube.com/watch?v=5r6yzFEXajQ) talk.
