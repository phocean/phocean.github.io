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

<ul class="tag-list">
    {% for tag in all_tags %}
        <li><a href="{{ site.tag_dir | prepend: '/' }}/{{ tag | uri_escape }}">{{ tag }}</a></li>
    {% endfor %}

</ul>


<div class="tags-expo">
  <div class="tags-expo-list">
    {% for tag in site.tags %}
    <a href="#{{ tag[0] | slugify }}" class="post-tag">{{ tag[0] }}</a>
    {% endfor %}
  </div>
  <hr/>
  <div class="tags-expo-section">
    {% for tag in site.tags %}
    <h2 id="{{ tag[0] | slugify }}">{{ tag | first }}</h2>
    <ul class="tags-expo-posts">
      {% for post in tag[1] %}
        <a class="post-title" href="{{ site.baseurl }}{{ post.url }}">
      <li>
        {{ post.title }}
      &nbsp;<small class="post-date">({{ post.date | date: "%d/%m/%y" }})</small>
      </li>
      </a>
      {% endfor %}
    </ul>
    {% endfor %}
  </div>
</div>