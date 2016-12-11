---
title: The rename files function on steroids.
layout: post
date: 2016-12-14 13:21:29
category: OSX, Vim
tags: [OSX, Vim]
---

One of the major flaws in Vim, is the weird way to rename files. 


Vim uses [buffers]. In fact whenever you edit a file, you interact with the buffer, and then when you are done, you save
it to a file. That approach is different, then any other editor i ever worked with.

So if you save the current buffer to a new name, you woudn't rename the file, you'll save a new one.

Normaly i resolve, to a small function i made.

```
  :rename {newname}
```

{% gist mikejakobsen/715dc9f5d8e7de3b0d8ce2905fc34630 %}

## Batch renaming

Mostly i resolve to OSX native, rename function. Most people dosen't know how good the renaming functionality in OSX
really is. There's no need to resolve to applications like [A better finder renamer].

With OS X Yosemite, Apple introduced an integrated basic batch renaming capabilities directly into Finder. To use it,
simply highlight or select multiple files in a Finder window, right-click (Control-click) on the selected items, and
choose Rename. 

![Rename](https://i.imgur.com/jYV7gDe.png)

The `batch renaminging` function introduces three diffrent functionalities.

**Add text**. As the name suggest. `Add text` gives you the ability to add text to the filename.
It's a great way to prefx filename. If you work a lot with [AngularJS components] like i do, this function is a great way to rename
the components part `about.component{.html, .scss, .spec.ts, .ts}`

**Formatting** must be the must used function, when people think `batch renaming`. It allows you to add dates, a prefix,
or to change the names entirely.

**Replace text** is a way to search/replace with in the file names.

## Batch renaming with Vim

Vim might be the best tool to handle large codebases. With the great Regex based [Search/Replace] function, or the
[Macro] function. Why not use it to batch rename files then?

[Vidir] let's you do that, it allows editing of the contents of a directory within Vim, or any other editor. And if no directory is specified, the current directory is edited.

Let's say i wanna postpone, all my upcoming blockposts to januar 2017. `Vidir` would be a great tool for that.

[![asciicast](https://asciinema.org/a/4t72571g00s55e9yh413e8d68.png)](https://asciinema.org/a/4t72571g00s55e9yh413e8d68)

Then Vim let's you update the date within the header of the markdown files, to postponed the post date.

{% highlight bash %}
:argdo %s/2016-12/2017-01/g | update
{% endhighlight %}

And if i want to rename this post from `function on drugs.` to `function on steorids`.

[![asciicast](https://asciinema.org/a/c7kecw63lzr4rl5x7c278l1mi.png)](https://asciinema.org/a/c7kecw63lzr4rl5x7c278l1mi)


[buffers]: http://todayilearned.dk/vim/2016/06/02/close-the-current-buffer/
[A better finder renamer]: https://github.com/caskroom/homebrew-cask/blob/master/Casks/a-better-finder-rename.rb
[AngularJS components]: http://learnangular2.com/components/
[Vidir]: https://github.com/trapd00r/vidir
[Search/Replace]: http://vim.wikia.com/wiki/Search_and_replace
[Macro]: http://vim.wikia.com/wiki/Macros
