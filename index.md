---
title: Home
layout: default
---

<div class="posts">
  {% for post in site.posts %}
    <article class="post">

      <h1><a class="articletitle" href="{{ site.baseurl }}{{ post.url }}">{{ post.title }}</a></h1>

      <div class="entry">
        {{ post.excerpt }}
      </div>

      <a href="{{ site.baseurl }}{{ post.url }}" class="read-more">Read More</a>

    </article>
    <br />
    <br />
  {% endfor %}
</div>
