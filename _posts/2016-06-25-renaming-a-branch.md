---
title: Renaming A Git Branch
layout: post
date: 2016-11-29 19:21:29
category: Git
tags: [Git]
---

{% highlight bash %}
$ git branch -m oldBranchName newBranchName
{% endhighlight %}

The `-m` flag can be used with `git branch` to move/rename an existing
branch. If you are already on the branch that you want to rename, all you
need to do is provide the new branch name.

{% highlight bash %}
$ git branch -m <new-branch-name>
{% endhighlight %}

If you want to rename a branch other than the one you are currently on, you
must specify both the existing (old) branch name and the new branch name.

{% highlight bash %}
$ git branch -m <old-branch-name> <new-branch-name>
{% endhighlight %}
