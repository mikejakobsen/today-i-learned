---
title: Your hostfile might be the best AdBlocker there is.
layout: post
date: 2016-12-14 19:21:29
category: OSX
tags: [OSX]
---

You may not know it, but your host file is the backbone of your Internet ussage.

A host file serves the function of translating human-friendly hostnames into numeric protocol addresses. Like
dialing a phone number, and connecting that number to the right user. For instance connecting to `www.google.com`
will actualy connect you to the [IP address] `213.58.210.196`.

That's why the host file also can acts as the best and most thorough AddBlocker there is.

Edit the hosts file as root, for example with `sudo vim /etc/hosts`. If your not, that familiar with the command-line the Host file can also be managed with the app [2ndalpha/gasmask](https://github.com/2ndalpha/gasmask).

```
brew cask install gas-mask
```

To block a domain, append `0 facebook.com` or `0.0.0.0 facebook.com` or `127.0.0.1 facebook.com` to `/etc/hosts`

Another way to use the Host file, is to make a redirect. Here i made a redirect from [Ekstra Bladet] to a real news
source. [Berlingske]

```
91.214.22.68 berlingske.dk
```

There are many lists of domains available online which you can paste in, just make sure each line starts with `0`, `0.0.0.0`, `127.0.0.1`, and the line `127.0.0.1 localhost` is included.

For Spam hosts lists, see [someonewhocares.org](http://someonewhocares.org/hosts/zero/hosts), [l1k/osxparanoia/blob/master/hosts](https://github.com/l1k/osxparanoia/blob/master/hosts), [StevenBlack/hosts](https://github.com/StevenBlack/hosts) and [gorhill/uMatrix/hosts-files.json](https://github.com/gorhill/uMatrix/blob/master/assets/umatrix/hosts-files.json).


If you wanna append a list to your own host file. A simple `curl` command will do the trick.

{% highlight bash %}
	curl "https://raw.githubusercontent.com/StevenBlack/hosts/master/hosts" | sudo tee -a /etc/hosts
{% endhighlight %}

To check if the host file is updated. The following command should return similar to 31.998.

{% highlight bash %}
	wc -l /etc/hosts
{% endhighlight %}

Below is a Gist containing my Host file. If you want to add it to your own host file. Just run.

{% highlight bash %}
	curl "https://gist.github.com/mikejakobsen/f4aed82e6dd846eb7a49d795d10c8fe7" | sudo tee -a /etc/hosts
{% endhighlight %}

Which contains nearly 81.000 lines.

[![asciicast](https://asciinema.org/a/3vwo5v1i3y40k9ss9mbz8o4zq.png)](https://asciinema.org/a/3vwo5v1i3y40k9ss9mbz8o4zq)

{% gist mikejakobsen/f4aed82e6dd846eb7a49d795d10c8fe7 %}

See `man hosts` and [FreeBSD Configuration Files](https://www.freebsd.org/doc/handbook/configtuning-configfiles.html) for more information.

[Ip address]: https://en.wikipedia.org/wiki/IP_address
[Ekstra Bladet]: www.eb.dk
[Berlingske]: www.b.dk
