---
layout: page
weight: 200
entry: Posts
---

<ul>
  {% for post in site.posts %}
    <li>
      <i>{{ post.date | date: "%Y/%m/%d" }}
      {{ post.categories[0] | upcase }}</i>
      <a href="{{ post.url }}">{{ post.title }}</a>
    </li>
  {% endfor %}
</ul>
