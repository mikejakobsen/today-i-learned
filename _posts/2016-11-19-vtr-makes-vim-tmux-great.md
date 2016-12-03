---
title: VTR makes Vim and Tmux great
layout: post
date: 2016-11-19 23:21:29
category: Vim, Tmux
tags: [Vim, Tmux]
---
So 90% of my working day is spend, tabbing around on the command-line. And the only thing keeping my sanity
straight, while i do that, is Tmux.

![VTR-tmux](https://media.giphy.com/media/3oriNYyu4t1G3DdPr2/giphy.gif)

[VTR](https://github.com/christoomey/vim-tmux-runner) provides a collection of commands and functions that allow Vim to interact with tmux. The primary command is `VtrSendCommandToRunner`. `(Leader+sc)` . This allows for any command string to be passed to tmux for execution. 
The command `VtrSendLinesToRunner` allow for either the current visually selected region or the current line to be sent to the tmux runner pane for execution.

So simply tapping `<leader>or` and `<leader>kr` has slowly become one of my favorite tools.

|Mapping      |   Command                    |
|--------------------------------------------|
|<leader>rr   |   VtrResizeRunner<cr>        |
|<leader>ror  |   VtrReorientRunner<cr>      |
|<leader>sc   |   VtrSendCommandToRunner<cr> |
|<leader>sl   |   VtrSendLinesToRunner<cr>   |
|<leader>or   |   VtrOpenRunner<cr>          |
|<leader>kr   |   VtrKillRunner<cr>          |
|<leader>fr   |   VtrFocusRunner<cr>         |
|<leader>dr   |   VtrDetachRunner<cr>        |
|<leader>ar   |   VtrReattachRunner<cr>      |
|<leader>cr   |   VtrClearRunner<cr>         |
|<leader>fc   |   VtrFlushCommand<cr>        |
