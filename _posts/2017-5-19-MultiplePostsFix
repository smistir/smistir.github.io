---
title: Fix for Multiple Posts
layout: post
date: 2017-5-19 14:30
---

Last post, for now.  But, while I was writing the last post I found out how to solve the 'Multiple Posts in a Single Day' issue.  By 
default, Jekyll reads the date from the file name under the '_posts' directory.  It was mentioned that it still knows when the files 
were created and posted in chronological order but that wasn't my experience.

I found some people discussing the issue and tested out a solution that looks really good - but there is a manual step that you'll have 
to track.

Up until now, we have been recording title and layout in our Front Matter.  Typically, the title will be read from the file name after
the date.  But, I hate really long file names and special characters in my file names.  So, I keep my file names as simple as I can and
override the title for the post within the Front Matter.  We also record the layout there using our 'post' override (you can find that in
the '_layouts' directory.

Turns out, we can also add a date item to the Front Matter.  Here we can refine the date to include Time and Jekyll will process this and
know what to do.  Now, you might be able to include time in your file name and have Jekyll recognize and process the data.  But, I like
clean file names so I likely won't go that route.

{% highlight markdown %}

  ---
  title: Post_Title
  layout: You_Layout
  date: 1900-1-1 01:02:03
  ---
 
{% endhighlight %}

Above you will find a code-snippet with a simple Front Matter including Date.  It is also possible to include TimeZone (+/- value) after 
the value for time.
