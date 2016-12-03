---
title: Grep For Multiple Patterns
layout: post
date: 2016-05-12 09:21:29
category: Unix
tags: [Unix]
---

You can use the `-e` flag with the `grep` command to search for a pattern.
Additionally, you can use multiple `-e` flags to search for multiple
patterns. For instance, if you want to search for occurrences of `ruby` and
`clojure` in a `README.md` file, use the following command:

```
$ grep -e ruby -e clojure README.md
```

See `man grep` for more details.
