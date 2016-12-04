---
title: Homebrew bundle
layout: post
date: 2016-12-01 23:21:29
category: OSX, Homebrew
tags: [OSX, Homebrew]
---

Homebrew might be the best thing that happened to MacOS since the first real MacBook was released in 2006. 

Apple have always been one of the best at making compelling infrastructure for their product. For instance the iPod, might not have survived if it wasn't for the iTunes store that was opened back in 2013. It removed the hassle of connection your device to your computer, and synchronise your CD's to MP3.

Apple tried the same thing with the Apple Store. But it absolutely sucks. The fact, that Apple takes 30% of the paid
fees is kinda okay. But the GUI-thing is really bad.

[Homebrew Bundle](https://github.com/Homebrew/homebrew-bundle) enable you to list all your installed applications,
or even storing a snapshot you can revert to later on. I often install useless formulas i really don't need, so i
use that a lot.

	brew tap Homebrew/bundle
	brew tap caskroom/cask

### Usage

You can create a `Brewfile` from all the existing Homebrew packages you have installed with:

    brew bundle dump

Here's my [Brewfile](https://github.com/mikejakobsen/dotfiles/blob/master/Brewfile).

You can then easily install all of the dependencies with the following command:

    $ brew bundle

If a dependency is already installed and there is an update available it will be upgraded.

![Homebrew Bundle](https://media.giphy.com/media/3o6ZsUkLabZSwZLTQQ/giphy.gif)


You can even choos whether `brew bundle` restarts a service every time it's run, or
only when the formula is installed or upgraded in your `Brewfile`:

Always restart myservice

{% highlight ruby %}
brew 'myservice', restart_service: true
{% endhighlight %}

Only restart when installing or upgrading myservice

{% highlight ruby %}
brew 'myservice', restart_service: :changed
{% endhighlight %}

