---
weight: 400
entry: Tags
layout: page
title: Tags
---

{% for tag in site.tags %}
  <h3 id="{{ tag[0] | slugify }}">{{ tag | first }}</h3>
  <ul>
    {% for post in tag[1] %}
    <li>
      <i>{{ post.date | date: "%Y/%m/%d" }}</i>
      <a href="{{ post.url }}">{{ post.title }}</a>
    </li>
    {% endfor %}
  </ul>
{% endfor %}
