---
layout: page
weight: 200
entry: Blog
---

<ul>
  {% for post in site.posts %}
    <li>
      <a href="{{ post.url }}">[{{ post.categorie }}]{{ post.title }}</a>
      ({{ post.date | date: "%d/%m/%y" }})
    </li>
  {% endfor %}
</ul>
