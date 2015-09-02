---
title: The Painter's Algorithm
author: Adam Harris
---

One thing you need to know about [svg]({{site.baseurl}}/what-is-svg/) is how to put one shape on top of another. If you're familiar with html, you might have heard of the z-index. And so you might be asking yourself what's the equivalent of z-index in svg. The answer is, there is none.

In html you can arbitrarily tell the browser to paint one element on top of another element just by giving it a higher value for the z-index, but in svg the source order of the elements is the only thing that matters.

The best way to think about this is the painter's algorithm. Basically, whichever elements are painted first, are on the bottom, and whichever elements are painted later, are on top. It's just like with real paint. If you paint something later, you end up painting on top of the other stuff that you painted earlier.

The thing that can be confusing about this is that the things that are further down in the svg document, are the ones which are drawn later. This might seem counter-intuitive because the things at the top of the svg are on the bottom of the image when it is painted, but remember that the code is interpreted from top to bottom, so the things at the top of the svg are painted first, and are therefore drawn on the bottom of the image.

Here is a simple example:

{% highlight html %}
<svg height="50" width="100">
   <circle r="25" cx="25" cy="25" style="fill: blue;" />
   <circle r="25" cx="50" cy="25" style="fill: red;" />
</svg>
{% endhighlight %}

<svg height="50" width="100">
   <circle r="25" cx="25" cy="25" style="fill: blue;" />
   <circle r="25" cx="50" cy="25" style="fill: red;" />
</svg>

You can see that because the blue circle is drawn first and the red circle is drawn second, the red circle is on top.
