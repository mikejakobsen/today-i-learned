---
title: Chromecast
layout: post
date: 2016-12-06 13:21:29
category: Chromecast, OSX
tags: [OSX, Chromecast]
---

Do you love your Chromecast just as much as i do - And do you miss Popcorn Time just as much as i do? 

There's a simple NPM tool [Castnow], to help you achieve something similar.

```
	npm install castnow -g
```

Simply start playback using the commandline.

`castnow ./back-to-the-future.mp4`

And to simply que an entire folder, just append the folder, to the castnow command.

`castnow ./folder/`

A function Chromecast really lacks is the ability to to simply play random videos, you find online.
The only way to stream such videos, is to stream it straight within the browser, and simply clone the browser window
to your device.

`castnow http://commondatastorage.googleapis.com/gtv-videos-bucket/ED_1280.mp4`

### PopcornTime

Simply visit your favorite torrent site, here's [mine]. And copy the link to the torrent/magnet files

`castnow <url-to-torrent-file OR magnet>`


## YouTube support

We had to drop direct YouTube support for now since google changed the chromecast YouTube API.
However, there is a nice workaround in combination with the tool [youtube-dl](https://github.com/rg3/youtube-dl):

`youtube-dl -o - https://youtu.be/vid | castnow --quiet -`

| Key     | Description                 |
| ---     | ---                         |
| `␣`     | Play/pause					|
| `m`     | Toggle mute                 |
| `↑`     | Volume up                   |
| `↓`     | Volume down                 |
| `←`     | Backward					|
| `→`     | Forware						|
| `n`     | Next                        |
| `s`     | Stop playback               |
| `q`     | Quit                        |
{:.shortcuts}


[mine]: https://extratorrent.unblockall.xyz/
[Castnow]: https://www.npmjs.com/package/castnow
