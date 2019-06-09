---
layout: page
weight: 200
entry: Blog
---

<ul>
  {% for post in site.posts %}
    <li>
      <a href="{{ post.url }}">{{ post.title }}</a>
      {{ post.excerpt | strip_html }}
    </li>
  {% endfor %}
</ul>