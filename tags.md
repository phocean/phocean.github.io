---
weight: 400
entry: Tags
layout: page
title: Tags
---

<h2>Tags</h2>

<ul>
{% assign tags_list = site.tags %}
    {% for tag in tags_list %}
      <li><a href="#{{ tag[0] | slugify }}">{{ tag[0] }} ({{ tag[1].size }})</a></li>
    {% endfor %}
{% assign tags_list = nil %}
</ul>

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
