---
title: Ammend commit with fugitive
layout: post
date: 2016-06-24 14:21:29
category: Vim
tags: [Vim]
---
If i could add one, and only one plugin to my Vim setup. It would probably be Fugitive.

Let's assume you are using [fugitive](https://github.com/tpope/vim-fugitive)
for Git integration with Vim. You've made a commit that you want to amend.
First, stage any changes that should be included in the amend with `:Gstatus` or
`:Ge:`. Then hit `ca` to open up the commit window for amending. Save and
quit when you are finished.

Want to view the aggregate changes? Open the commit window for amending in
verbose mode with `cva`.

See the [vim-fugitive
docs](https://github.com/tpope/vim-fugitive/blob/master/doc/fugitive.txt)
for more details.
