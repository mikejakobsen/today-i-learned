---
title: Working with Google Fonts
layout: post
date: 2016-12-05 17:21:29
category: HTML, OSX, Fonts
tags: [HTML, OSX, Fonts]
---

If you're doing any work creating UI mockups, chances are you've downloaded a few [Google fonts] to your computer. Doing this manually is tedious, and you wouldn't be up to date when the fonts get updated.

A while ago i made a simple script to install all [Google fonts] on your local machine. But since Google Fonts
include approximately 1660 fonts. That might not be a good idear.

{% highlight ruby %}
curl https://raw.githubusercontent.com/mikejakobsen/dotfiles/master/fonts/install.sh | sh
{% endhighlight %}

Here a Gist containing the install script.

{% gist mikejakobsen/e300ae5a67634608db4c2a57102cc73f %}

If you wanna limit yourself to the 40 best fonts. Just run this instead. 

{% highlight ruby %}
curl https://raw.githubusercontent.com/mikejakobsen/dotfiles/master/fonts/top40.sh | sh
{% endhighlight %}


## Skyfonts

Another option is [SkyFonts] it's a free font syncing service that puts webfonts into your computer. It works with paid services like [LinoType], [MonoType] and [fonts.com], but also offers unlimited support for Google Fonts.

![SkyFonts](http://i.imgur.com/Jrj7NaK.png)

This by far is the most convenient way to get Google Fonts onto your computer. Adding new fonts is mostly a one-click affair, fonts updates are automatically pushed to your computer, and you can even conveniently install the top 50 Google Fonts.

Monotype Skyfonts is available via [Caskroom] as `monotype-skyfonts`.

	brew cask install skyfonts

## Homebrew Fonts

Another great approach to handle your fonts, is [Caskroom-fonts]. It's simply an extension to Homebrew cask, which
contains 1000+ fonts.

First you need to `tap` the Fonts cask.

	brew tap caskroom/fonts 

And then you simply install font, like you would normally do with [Caskroom].

	brew cask install font-source-code-pro

[![asciicast](https://asciinema.org/a/99flrwzbyqqbrofyfvyyzwb79.png)](https://asciinema.org/a/99flrwzbyqqbrofyfvyyzwb79)

Here a small list of Caskroom fonts i can't live without

{% gist mikejakobsen/13912253026863336ae61e9b31f15024 %}

[Caskroom]: http://caskroom.io/
[Caskroom-fonts]: https://github.com/caskroom/homebrew-fonts
[Google fonts]: http://www.google.com/fonts
[SkyFonts]: https://skyfonts.com/
[MonoType]: https://monotype.com/
[LinoType]: https://linotype.com/
[fonts.com]: http://www.fonts.com/
