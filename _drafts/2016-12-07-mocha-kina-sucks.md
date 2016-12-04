---
title: JavaScript testing dosen't suck anymore
layout: post
date: 2016-12-07 18:21:29
category: JavaScript
tags: [JavaScript]
---


When did setting up tests suddently stop being the worst part of JavaScript?
Testing Node.js packages is easy. Here's a small walkthrough.


### Start with a package
Make a `package.json` file if you don't have one yet, then install your weapons of choice.

{% highlight sh %}
npm init
{% endhighlight %}

Which greates the package.json file.

{% highlight sh %}
npm install --save-dev mocha chai
{% endhighlight %}

### Write tests

Make your first test file `test/my_test.js`:

{% highlight javascript %}
/* test/my_test.js */
var expect = require('chai').expect;

describe('my test suite', function () {
  it('fails majestically', function () {
    expect(3).to.eql(2);
  });
});
{% endhighlight %}


### Update scripts

Update your `package.json` to use mocha.

{% highlight json %}
  "scripts": {
   "test": "mocha"
  },
{% endhighlight %}

### Run tests

Type `npm test` to run your tests. It should fail. Now go write tests that will pass!


Here's a quick Mocha cheatsheet. Also see [mochajs.org](http://mochajs.org).


{% gist mikejakobsen/2fa2a792fd7627fedcc2a80975f6d187 %}


### Expectations with Chai

Here's a quick Chai cheatsheet. See [chaijs.com](http://chaijs.com/api/bdd/) for other `expect()` actions.

{% highlight javascript %}
expect(3).to.eql(2);

expect(obj).to.be.a('string');
expect(obj).to.be.null;
expect(obj).to.be.true;
expect(obj).to.be.false;
expect(obj).to.be.undefined;

expect(list).to.include("item");
expect(list).to.have.length(3);
expect(list).to.have.length.gt(0);
{% endhighlight %}


### Where go to from here?

Use Sinon ([sinonjs.org][Sinon]) for mocks.

[Mocha]: http://mochajs.org/
[Sinon]: http://sinonjs.org/
