---
layout: page
title: blog 
permalink: /posts/
---

<ul class="posts">
  {% for post in site.posts %}
    <li>
      <a class="post-link" href="{{ post.url | prepend: site.baseurl }}">{{ post.title }}</a>
              <span class="post-date">{{ post.date | date: "%b %-d, %Y" }}</span>
       <span>{{ post.excerpt }}</span>
      <span><a href="{{ post.url | prepend: site.baseurl}}">read more</a>...</span>
    </li>
  {% endfor %}
</ul>
