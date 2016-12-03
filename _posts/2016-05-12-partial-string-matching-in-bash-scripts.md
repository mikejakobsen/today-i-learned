---
title: Partial String Matching In Bash Scripts
layout: post
date: 2016-05-12 09:21:29
category: Zsh
tags: [Zsh]
---

To compare two strings in a bash script, you will have a snippet of code
similar to the following:

```bash
if [[ $(pwd) == "/path/to/current/directory" ]]
then
  echo "You are in that directory";
fi
```

You may only want to do a partial string match. For this, you can use the
`*` wildcard symbol.

```bash
if [[ $(pwd) == *"directory"* ]]
then
  echo "You are in that directory";
fi
```
