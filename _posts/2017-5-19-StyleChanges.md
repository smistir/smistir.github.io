---
title: Changes Required
layout: post
---

Some changes were required and some changes were preferred.  Is any of it a big deal, probably not.  One issue stood out as being really ugly and I discuss that here as well as some
other observations and changes.

### Mobile Display Issue

After playing around, I decided to see what all of this looked like on a mobile device.  Turns out, there was a stip of black running down the right-hand side of the page.  I pulled up
the developer tools in Chrome and discovered that it was limited to mobile devices (using the Mobile device emulator).  The issue didn't appear on a desktop system using a manually reduced
browser width.  Turns out, the default styling of this theme was setting a "min-width" of 380px that caused a sort of overflow that grew as the width of the display decreased.

As a quick fix, here is the code:

'''code

@media screen and (max-width: 480px) {
   .inner {
      min-width:0;
      max-width: 480px;
   }

'''

This will need to be placed in a styles file in your own implementation.  If you don't have one setup, create a directory structure from root as "assets / css".  Within the CSS folder, create
a "style.scss" (Sassy CSS) file.  At the top, you need to add the following:

'''code

   ---
   ---

   @import "{{site.theme}}";

'''

And don't forget the semicolon (yea, I did that).  The base theme is already wired to look at this location for a stylesheet.  What you are doing here is providing it while also telling it to
import the default theme for your site.  You'll notice at the top of the file you have added Front Matter that doesn't contain anything.  This is something we add to make sure Jekyll will process
the SASS - Jekyll parses every file and will process any file it comes across that contains Front Matter.

Some other changes that I made were to turn the sites title, in the header, into a link back to root.  Otherwise, you would be forced to use the back button to return to the previous page until
you returned to the root.  In order to achieve this, it was necessary to override the default.html for the site.  Because we didn't have one, the theme used its own default.html for displaying
content.  What we did was go to the repository for the theme and copy the contents of default.html.  You'll need to make sure you have a folder "_layouts" under your repository root and create a 
file for default.html.  Then paste the contents that you copied from the theme's repository.  More on naming conventions later.

Once you have a default.html in place, this is what you will need to do.  On line 22:

'''code

   <h1 id="project_title"><a class="sitetitle" href="https://{{ site.github.repository_name }}">{{ site.title | default: site.github.repository_name }}</a></h1>

'''

