---
title: Why i love CSS
layout: post
date: 2016-12-30 23:21:29
category: CSS, Workflow
tags: [CSS, Workflow]
---

If you're anything like me, you learned CSS by setting a `wrapper` as 980px.

And back then most people was seeing your page at `1024x768`. Soo.. It looked great.

You're design dosen't break at a specific device width, you're design breaks when your design breaks, not the *fucking*
device.


*“Is the medium breakpoint up to 768px, or including 768? I see… and that’s iPad landscape, or is that ‘large’? Oh, large
is 768px and up. I see. And small is 320px? What is this range from 0 to 319px? A breakpoint for ants?”*

I think we mix up “boundaries” and “ranges” in our discussions and implementations of breakpoints.

Tell me, if you do breakpoints in Sass, do you have a variable called $large that is, say, 768px?

Is that the lower boundary of the range you refer to as large, or the upper boundary? If it’s the lower, then you must have no $small because that should be 0, right?
And if it’s the upper boundary then how would you define a breakpoint $large-and-up? That must be a media query with a min-width of $medium, right?

Where is 768px? That's the only device width i remember, and suddenly it's gone?

I always hated the mobile-first approach. We'll basically because, my brain doesn't work mobile-first. When was the last
time, you visited a site on your 4-5 inch mobile, and thought to your self. *Wow, that looks great*.. 

And the last time, you started picturing a design in your mind, did you see the mobile version? *Oh', you didn't.*

![Gif](http://gif.co/EkRQ.gif)

{% gist mikejakobsen/2cd1e7b4e974e0a1c715b2d22fa2944f %}

{% gist mikejakobsen/b27cbb62de71d4348ab4ce81d36d73f4 %}

This is how i solved, the BEM mindset thingy..

{% highlight scss %}
nav {
  @include has(item) {
    color: blue;
  }
  @include variant(login) {
    color: green;
  }
}
{% endhighlight %}

{% highlight css %}
nav .nav--item {
    color: blue;
  }
nav .nav--login {
    color: green;
  }
{% endhighlight %}


That's why i love mixins so much.

CSS is a bloated markup thing. And i would love sticking with the *stylus* syntax. Just typing `+font-size(13px);`, when
you wanna use the 13px typography from your PSD file, most be the most intuitive thing ever.

[Selecto]: https://github.com/LukyVj/family.scss
