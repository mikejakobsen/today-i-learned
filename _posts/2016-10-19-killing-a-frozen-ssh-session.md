---
title: Frozen SSH session
layout: post
date: 2016-10-19 19:21:29
category: Unix
tags: [Unix]
---

Whenever an SSH session freezes, I usually mash the keyboard in desperation
and then kill the terminal session. This can be avoided though. SSH will
listen for the following kill command:

```
~.<cr>
```

This will kill the frozen SSH session and leave you in the terminal where
you were before you SSH'd.

source: [Jack C.](http://hashrocket.com/team/jack-christensen)
