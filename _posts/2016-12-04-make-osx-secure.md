---
title: Make OSX secure
layout: post
date: 2016-12-06 23:41:29
category: OSX
tags: [OSX]
---

90% of the times i am online, i spendt on a open network. Were everybody can connect. 

Before connecting to the Internet, it's a good idea to first configure a firewall.
There are several types of firewall available for macOS.

## Application layer firewall

Built-in, basic firewall which blocks `incoming` connections only.

Note, this firewall does not have the ability to monitor, nor block **outgoing** connections.

It can be controlled by the `Firewall` tab of `Security & Privacy` in `System Preferences`, or with the following commands.

Enable the firewall:

    $ sudo /usr/libexec/ApplicationFirewall/socketfilterfw --setglobalstate on

Enable logging:

    $ sudo /usr/libexec/ApplicationFirewall/socketfilterfw --setloggingmode on

You may also wish to enable stealth mode:

    $ sudo /usr/libexec/ApplicationFirewall/socketfilterfw --setstealthmode on

> Computer hackers scan networks so they can attempt to identify computers to attack. You can prevent your computer from responding to some of these scans by using `stealth mode`. When stealth mode is enabled, your computer does not respond to ICMP ping requests, and does not answer to connection attempts from a closed TCP or UDP port. This makes it more difficult for attackers to find your computer.

Finally, you may wish to prevent `built-in software` as well as `code-signed, downloaded software from being whitelisted automatically`:

    $ sudo /usr/libexec/ApplicationFirewall/socketfilterfw --setallowsigned off

    $ sudo /usr/libexec/ApplicationFirewall/socketfilterfw --setallowsignedapp off

Applications that are signed by a valid certificate authority are automatically added to the list of allowed apps, rather than prompting the user to authorize them. Apps included in OS X are signed by Apple and are allowed to receive incoming connections when this setting is enabled. For example, since iTunes is already signed by Apple, it is automatically allowed to receive incoming connections through the firewall.

If you run an unsigned app that is not listed in the firewall list, a dialog appears with options to Allow or Deny connections for the app. If you choose Allow, OS X signs the application and automatically adds it to the firewall list. If you choose Deny, OS X adds it to the list but denies incoming connections intended for this app.

After interacting with `socketfilterfw`, you may want to restart (or terminate) the process:

    $ sudo pkill -HUP socketfilterfw
