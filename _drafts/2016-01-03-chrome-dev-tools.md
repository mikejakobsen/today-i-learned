---
title: Chrome Dev tools - stuff i should have known all along
layout: post
date: 2016-01-03 19:21:29
category: Chrome
tags: [Chrome]
---

*This post assumes you know a bit about browser caches.*

Sometimes I want to empty Chrome's cache and do a hard reload. Maybe I'm getting some stale resources that I'm pretty sure have changed and I want to make sure I'm getting fresh files.

To empty Chrome's cache and do a hard refresh:

1. [Open the Chrome DevTools.](https://developer.chrome.com/devtools#access) You can't do a hard reload if you don't have the DevTools open.
2. Right-click on the Reload button.
3. Click "Empty Cache and Hard Reload".

Here's what that looks like:

![Screenshot of "Empty Cache and Hard Reload" in Chrome](https://i.imgur.com/PiCZsq7.png)

I haven't seen this concisely documented anywhere, so I thought I'd write this post!

*Edit:* A reader sent [Clear Cache](https://chrome.google.com/webstore/detail/clear-cache/cppjkneekbjaeellbfkmgnhonkkjfpdn?hl=en), a simple Chrome extension that can do this too.