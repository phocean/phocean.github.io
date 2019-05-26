---
layout: page
weigth: 200
entry: Blog
title: Phocean's Infosec Blog
description: blog, hacking, pentest, forensics, infosec
permalink: blog.html
---

{% for post in site.posts %}

<article class='post'>
  <h3 class='post-title'>
    <a href="{{ site.baseurl }}{{ post.url }}">
      {{ post.title }}
    </a>
  </h3>
  <div class="post-date">{{ post.date | date: "%b %-d, %Y" }}</div>
  {{ post.content }}
</article>

{% endfor %}
