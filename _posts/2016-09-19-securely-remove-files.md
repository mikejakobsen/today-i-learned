---
title: Prermantly delete files
layout: post
date: 2016-09-19 23:21:29
category: Zsh
tags: [Zsh]
---

If you really want to make sure you have wiped a file from your hard drive,
you are going to want to use `srm` instead of `rm`. The man page for `srm`
gives the following description:

> srm  removes  each  specified file by overwriting, renaming, and truncating
> it before unlinking. This prevents other people from undeleting or
> recovering any information about the file from the command line.
