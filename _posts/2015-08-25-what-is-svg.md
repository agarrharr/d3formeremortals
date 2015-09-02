---
title: What is SVG?
author: Adam Harris
---

There are 2 ways of describing what SVG is. One is that SVG is a vector image format. And another is to say that it's a markup language to create graphics. It's written out with markup very similar to HTML or XML. It stands for Scalable Vector Graphics which means that instead of representing the image with pixels, it's stored as vectors, which can scale as large as you want without losing any quality. You may have seen SVG as an option when saving files from Adobe Illustrator. That's because Illustrator saves imges in vector format and SVG is a vector format.

It's been around for a while (1999) and it's supported in pretty much every web browser along with other image formats like jpg, gif, and png.

Since it's a markup language, that means it's stored in plain text files that you can open with a normal editor like Notepad on Windows or TextEdit on a Mac. And of course, you can also open it in other programs like Illustrator. It's saved with the file extension `.svg`.

It can also be embedded directly into an html document instead of being saved as a separate file. To do this, all you have to do is include an `svg` tag in your html and then put some SVG code inside of those tags like this:

{% highlight html %}
<svg height="52" width="52">
   <circle r="25" cy="26" cx="26" style="stroke: black; stroke-width: 1px; fill: blue;" />
</svg>
{% endhighlight %}

<svg height="52" width="52">
   <circle r="25" cy="26" cx="26" style="stroke: black; stroke-width: 1px; fill: blue;" />
</svg>

This draws a blue circle with a black outline and a radius of 25px on the page.

So as you can see, SVG markup is readable to humans unlike other image formats. If you opened up a jpg file with a text editor you would just see a bunch of gibberish.

Here are some shapes that SVG has available. You can build almost any image with these basic shapes.

* `circle`
* `rect`
* `ellipse`
* `line`
* `polygon`
* `path`

So SVG is a great option for using with D3 to create visualizations. But you don't have to use SVG in order to use D3. You can also use html, canvas, or maybe something else, but in general, most of the examples you're going to see will be using SVG.
