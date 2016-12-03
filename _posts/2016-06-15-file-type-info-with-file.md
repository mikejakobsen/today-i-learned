---
title: File Type Info With File
layout: post
date: 2016-06-15 13:21:29
category: Zsh, Unix
tags: [Zsh, Unix]
---

Use the `file` utility to determine the type of a file:

```bash
$ file todo.md
todo.md: ASCII English text

$ file Hello.java
Hello.java: ASCII C++ program text

$ file Hello.class
Hello.class: compiled Java class data, version 52.0
```

The `Hello.java` file isn't exactly a C++ program, but close enough.
