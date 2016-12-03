---
title: List of sessions to a machine
layout: post
date: 2016-07-19 23:21:29
category: Unix
tags: [Unix]
---

The `last` command is a handy way to find out who has been connecting to a
machine and when.

> Last will list the sessions of specified users, ttys, and hosts, in
> reverse time order.  Each line of output contains the user name, the tty
> from which the session was conducted, any hostname, the start and stop
> times for the session, and the duration of the session.  If the session is
> still continuing or was cut short by a crash or shutdown, last will so
> indicate.

In particular, this can be useful for finding an IP address that you want to
connect to.

See `man last` for more details.
