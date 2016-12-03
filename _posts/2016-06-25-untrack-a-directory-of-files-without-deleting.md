---
title: Untrack A Directory Of Files Without Deleting
layout: post
date: 2016-09-12 13:21:29
category: Git
tags: [Git]
---

In [Untrack A File Without Deleting It](untrack-a-file-without-deleting-it.md),
I explained how a specific file can be removed from tracking without
actually deleting the file from the local file system. The same can be done
for a directory of files that you don't want tracked. Just use the `-r`
flag:

```bash
$ git rm --cached -r <directory>
```
