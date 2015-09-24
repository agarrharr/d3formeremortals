---
title: Know Your Tools
author: Adam Harris
---

I seem to write an awful lot about svg on a site that is supposed to be all about D3.js. And there's a reason for that. I don't want to confuse anyone about which technology is doing which thing.

When I first starting learning D3.js, I was a little unclear when I was programming, if what I was doing was an SVG thing, a JavaScript thing, a D3 thing, or a D3.chart thing (we used [D3.chart](http://misoproject.com/d3-chart/) for building reusable charts).

And when you don't know which technology is doing what, it's hard to understand what you're doing, it's hard to know that what you did really works, and it's hard to apply that to solving new problems.

Often with D3, you'll be writing stuff like this:

{% highlight javascript %}
var data = [1, 2, 3, 5, 8];
var colors = d3.scale.category10();
var svg = d3.select('#example1')
  .append('svg');

svg.selectAll('.bar')
  .data(data)
  .enter()
  .append('rect')
  .classed('bar', true);

d3.selectAll('.bar')
  .attr({
    'x': function(d) {
      return d * 30;
    },
    'y': 0,
    'height': 20,
    'width': 20
  })
  .style({
    'fill': colors
  });
{% endhighlight %}

<div id="example1"></div>
<script>
var data = [1, 2, 3, 5, 8];
var colors = d3.scale.category10();
var svg = d3.select('#example1')
  .append('svg');

svg.selectAll('.bar')
  .data(data)
  .enter()
  .append('rect')
  .classed('bar', true);

d3.selectAll('.bar')
  .attr({
    'x': function(d) {
      return d * 30;
    },
    'y': 0,
    'height': 20,
    'width': 20
  })
  .style({
    'fill': colors
  });
</script>

when you're really just trying to get this end result in the svg:

{% highlight html %}
<svg>
  <rect class="bar" x="30" y="0" height="20" width="20" style="fill: rgb(31, 119, 180);"></rect>
  <rect class="bar" x="60" y="0" height="20" width="20" style="fill: rgb(255, 127, 14);"></rect>
  <rect class="bar" x="90" y="0" height="20" width="20" style="fill: rgb(44, 160, 44);"></rect>
  <rect class="bar" x="150" y="0" height="20" width="20" style="fill: rgb(214, 39, 40);"></rect>
  <rect class="bar" x="240" y="0" height="20" width="20" style="fill: rgb(148, 103, 189);"></rect>
</svg>
{% endhighlight %}

<svg>
  <rect class="bar" x="30" y="0" height="20" width="20" style="fill: rgb(31, 119, 180);"></rect>
  <rect class="bar" x="60" y="0" height="20" width="20" style="fill: rgb(255, 127, 14);"></rect>
  <rect class="bar" x="90" y="0" height="20" width="20" style="fill: rgb(44, 160, 44);"></rect>
  <rect class="bar" x="150" y="0" height="20" width="20" style="fill: rgb(214, 39, 40);"></rect>
  <rect class="bar" x="240" y="0" height="20" width="20" style="fill: rgb(148, 103, 189);"></rect>
</svg>

It's really helpful if you can just step back and understand the end result you're trying to create (the SVG in this case) and why it works instead of the concatenation and the math and if statements of the JavaScript and D3.
