
---
title: Create a Github Repository from the command-line
layout: post
date: 2016-02-14 23:21:29
category: Git, ZSH
tags: [Git, ZSH]
---

{% highlight bash %}
create-repo()
{
    USERNAME=<username>
    ACCESS_TOKEN=`cat ~/.config/github-access-token`

    curl -u $USERNAME:$ACCESS_TOKEN https://api.github.com/user/repos -d '{"name": "'$1'"}' -o /dev/null -s
    echo "git remote add origin git@github.com:$USERNAME/$1.git"
}
{% endhighlight %}
