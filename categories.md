---
weight: 300
entry: Categories
layout: page
title: Categories
---

<ul>
{% assign categories_list = site.categories %}
  {% if categories_list.first[0] == null %}
    {% for category in categories_list %}
      <li><a href="#{{ category | slugify }}">{{ category | upcase }} ({{ site.tags[category].size }})</a></li>
    {% endfor %}
  {% else %}
    {% for category in categories_list %}
      <li><a href="#{{ category[0] | slugify }}">{{ category[0] | upcase }} ({{ category[1].size }})</a></li>
    {% endfor %}
  {% endif %}
{% assign categories_list = nil %}
</ul>

{% for category in site.categories %}
  <h3 id="{{ category[0] | slugify }}">{{ category[0] | upcase }}</h3>
  <ul>
    {% assign pages_list = category[1] %}
    {% for post in pages_list %}
      {% if post.title != null %}
      {% if group == null or group == post.group %}
  <li><a href="{{ site.url }}{{ post.url }}">{{ post.title }}</a>&nbsp;&nbsp;<i><time datetime="{{ post.date | date_to_xmlschema }}" itemprop="datePublished">{{ post.date | date: "%B %d, %Y" }}</time></i></li>
      {% endif %}
      {% endif %}
    {% endfor %}
    {% assign pages_list = nil %}
    {% assign group = nil %}
  </ul>
{% endfor %}
