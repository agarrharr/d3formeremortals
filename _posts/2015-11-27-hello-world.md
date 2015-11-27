---
title: Hello World
author: Adam Harris
tags:
- d3js
published: true
---

This is a super simple program that just puts the words, "Hello World!" on the page.

It's really simple, but it's an easy way to try out d3 for the first time.

{% highlight html %}
<div id="helloWorld"></div>
<script>
d3.select('#helloWorld')
  .append('text')
  .text('Hello World!');
</script>
{% endhighlight %}

1. It uses 3 common functions in D3.

    `select` is probably the most common method used in D3. It uses css-style syntax to select elements. However, it only returns the *first* element that matches the selector. If you want all of the matches returned, you can use `selectAll` instead.

1. It illustrates D3's great chaining syntax.

    Almost every method in D3 supports chaining. So, in this example, select returns a D3 selection of the helloWorld div. And the append method that d3 selection and appends a text element. And then the text method takes that text element and puts the text inside of it.

1. It shows that you don't have to use svg.

Normally, visualizations in D3 are made with svg, but you can do normal DOM manipulation with html, which is pretty handy.

Next time, we'll do a simple example with some real data binding.
