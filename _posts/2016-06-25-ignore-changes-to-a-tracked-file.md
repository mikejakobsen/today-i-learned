---
title: Ignore Changes To A Tracked File
layout: post
date: 2016-09-12 13:21:29
category: Git
tags: [Git]
---

Files that should never be tracked are listed in your `.gitignore` file. But
what about if you want to ignore some local changes to a tracked file?

You can tell git to assume the file is unchanged

```bash
$ git update-index --assume-unchanged <some-file>
```

Reversing the process can be done with the `--no-assume-unchanged` flag.
