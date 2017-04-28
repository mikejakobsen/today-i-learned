---
title: Kill Frozen SSH session
layout: post
date: 2016-10-19 19:21:29
category: Unix, Tmux
tags: [Unix, Tmux]
---

Whenever an SSH session freezes, I usually mash the keyboard in desperation
and then kill the terminal session. This can be avoided though. SSH will
listen for the following kill command:

```
~.<cr>
```

This will kill the frozen SSH session and leave you in the terminal where
you were before you SSH'd.

### Inside Tmux

If the session is running inside a Tmux instance.

```
prefix+x
```

Will do the trick.
