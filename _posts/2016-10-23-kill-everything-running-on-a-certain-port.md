---
title: Kill everything on a port
layout: post
date: 2016-10-23 21:25:29
category: Unix
tags: [Unix]
---

You can quickly kill everything running on a certain port with the following
command.

```bash
sudo kill `sudo lsof -t -i:3000`
```

This gets a list of pids for all the processes and then kills them.

I made a simple script, to contain the script.

```
portkill 5000
```

[![asciicast](https://asciinema.org/a/8v9cs8blx1cx47lopk3kpojlf.png)](https://asciinema.org/a/8v9cs8blx1cx47lopk3kpojlf)

Save it to your `Bin` directory.

{% gist mikejakobsen/d5c988a52e8c2b831f95e25c9265647e %}
