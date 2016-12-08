---
title: Markdown tables made easy
layout: post
date: 2016-12-07 13:21:29
category: Vim, Markdown
tags: [Vim, Markdown]
---

If your anything like me, you spend a lot of time making boring markdown tables.

Toole like [Markdown Tables Generator] might be a help, but i find that they make the task even more unbareble.

I made a simple plugin to make the task less tedious.

Simply type the data as a comma seperated list, select it and run

```
:Table
```

If the top field is within the data, `:Table!` does the trick.

It actually works pretty well with `comma seperated` csv files as well.

[![asciicast](https://asciinema.org/a/a79szwikq5royax9e5gnyagj4.png)](https://asciinema.org/a/a79szwikq5royax9e5gnyagj4)

Save the code below as a `.vim` file in your Plugin directory.

{% gist mikejakobsen/b28b65b4f6dd2abf1679fd53ce10f700 %}


[Markdown Tables Generator]: http://www.tablesgenerator.com/markdown_tables
