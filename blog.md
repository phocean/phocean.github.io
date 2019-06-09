---
layout: page
weight: 200
entry: Posts
---

<ul>
  {% for post in site.posts %}
    <li>
      <i>{{ post.date | date: "%Y/%m/%d" }}</i>
      {{ post.categories[0] | capitalize }}
      <a href="{{ post.url }}">{{ post.title }}</a>
    </li>
  {% endfor %}
</ul>
