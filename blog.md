---
layout: page
weight: 200
entry: Posts
---

<ul>
  {% for post in site.posts %}
    <li>
      {{ post.categories | capitalize }}
      <i>{{ post.date | date: "%Y/%m/%d" }}</i>
      <a href="{{ post.url }}">{{ post.title }}</a>
    </li>
  {% endfor %}
</ul>
