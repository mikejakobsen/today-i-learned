---
title: Run ESLint with webpack
layout: post
date: 2016-11-29 23:21:29
category: Webpack, JavaScript
tags: [Webpack, JavaScript]
---
You may already be running [ESLint](http://eslint.org/) manually or as a
script command via `npm`.  You can also include it as part of the Webpack
build process. By adding it as a *preloader*, Webpack will lint your
JavaScript files before running other loaders. 

The results of linting will be reported in the terminal. Assuming you've already installed
`eslint` and set up your `.eslintrc` file, all you need to do is `npm
install --save-dev eslint-loader` and then add something like the following
to your `webpack.config.js` file:

{% highlight javascript %}
module: {
  preLoaders: [
    {
      test: /\.js$/,
      loaders: ['eslint'],
      exclude: /node_modules/,
    }
  ],
  ...
}
{% endhighlight %}

Running something like `webpack -w` will now lint your JavaScript before
running other loaders.

Depending on your project, you may also want to include `babel-eslint` and
`eslint-plugin-react` with your setup.
