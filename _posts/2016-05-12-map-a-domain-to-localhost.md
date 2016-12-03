---
title: Map a domain to Localhost
layout: post
date: 2016-05-12 09:21:29
category: Unix, Wordpress
tags: [Unix, Wordpress]
---

Do you want your computer to treat a domain as `localhost`? You can map it
as such in your `/etc/hosts` file. For example, if I have an web app that
refers to itself with the `dev.app.com` domain, I can add the following line
to my `/etc/hosts` file to make sure the domain resolves to `localhost`:

```
127.0.0.1 dev.app.com
```

Now, if I pop open my browser and visit `dev.app.com:3000`, I will see
whatever is being served to `localhost:3000`.


[Laravel Valet](www.laravel.com/valet) also does a great job doing the same.
