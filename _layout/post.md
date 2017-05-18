---
layout: default
---

<article class="post">
  <h1>{{ page.title }}</h1>

  <div class="entry">
    {{ content }}
  </div>
  
  <br />
  <br />
  <div>
    --
  </div>
  <div class="date">
    Written on {{ page.date | date: "%B %e, %Y" }}
  </div>
</article>
