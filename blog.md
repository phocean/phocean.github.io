---
layout: page
weight: 200
entry: Posts
---

<ul>
  {% for post in site.posts %}
    <li>
      [{{ post.categories }}]
      <a href="{{ post.url }}">{{ post.title }}</a>
      ({{ post.date | date: "%Y/%m/%d" }})
    </li>
  {% endfor %}
</ul>
