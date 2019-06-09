---
weight: 300
entry: Tags
layout: page
title: Tags
---


{% assign all_tags = '' | split: ',' %}

 {% for post in site.posts %}
    {% for tags in post.tags %}
        {% for tag in tags %}
            {% assign all_tags = all_tags | push: tag %}
        {% endfor %}
    {% endfor %}
{% endfor %}

{% assign all_tags = all_tags | sort %}
{% assign all_tags = all_tags | uniq %}

{% for tag in site.tags %}
  <h3 id="{{ tag[0] | slugify }}">{{ tag | first }}</h3>
  <ul class="tags-expo-posts">
    {% for post in tag[1] %}
    <a href="{{ post.url }}">
    <li>
      {{ post.title }}
    </li>
    </a>
    ({{ post.date | date: "%Y/%m/%d" }})
    {% endfor %}
  </ul>
{% endfor %}
