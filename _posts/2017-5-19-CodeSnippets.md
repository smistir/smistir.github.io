---
title: Code Snippets
layout: post
date: 2017-5-19 14:00:00
---



{% highlight csharp linenos %}

   public string MyCodeSnippet(string content)
   {
      return new CodeSnippet.WithHighlights(content);
   }

{% endhighlight %}

Jekyll uses Rouge and Pygments for code snippet highlighting within page content.  A small bonus was when I rendered my first code snippet that I discovered it also handles creating a styled div to separate the code snippet from the rest of the post.  Now, this might be handled by the theme (another thing for my TODO list) and it might be handled purely by the engine.

And just before I hit the submit button on this latest post, I flashed over to the documentation and found that including "linenos" to 
the markup (markdown?) would include line numbers with the code snippet.

### Quick Note:
If you try to lead off with a Code Snippet, it seems Jekyll might not give you a successful build.  Try saying something, anything, before you begin the code snippet if you ever run into trouble.
