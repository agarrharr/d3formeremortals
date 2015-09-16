---
title: SVG Viewbox
author: Adam Harris
---

The viewbox is an attribute of an svg element that can be pretty confusing if you don't know what it is, or if you don't know that it's there.

Suppose that you had the following svg, which draws a blue square with a height of 25px:

{% highlight html %}
<svg width="500px" height="100px" viewbox="0 0 500 100">
  <rect width="50" height="50" style="fill: blue;" />
</svg>
{% endhighlight %}

<svg width="500px" height="100px" viewbox="0 0 500 100">
  <rect width="50" height="50" style="fill: blue;" />
</svg>

And then you changed the width of the svg from 500px to 250px:

{% highlight html %}
<svg width="250px" height="100px" viewbox="0 0 500 100">
  <rect width="50" height="50" style="fill: blue;" />
</svg>
{% endhighlight %}

<svg width="250px" height="100px" viewbox="0 0 500 100">
  <rect width="50" height="50" style="fill: blue;" />
</svg>

What!? Now all of a sudden the rectangle appears to be 25px instead of 50px!

This is because of the viewbox. The height and width of the svg is the size of the svg image and the viewbox is the coordinates to show on that svg. So in the first example, the height and the width of the viewbox match and we see exactly what we expect, but for the second one, the width of the svg has changed and the viewbox hasn't.

#### What do the viewbox numbers mean?

The viewbox has 4 numbers separated by spaces:

* The first number is the min-x coordinate

* The second is the min-y coordinate

* Then the width

* Then the height

So, in our second example, even though the svg is only 250px wide, it's coordinate system goes from 0-500, so everything will appear at half the size.
