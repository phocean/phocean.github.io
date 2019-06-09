---
weight: 300
entry: Categories
layout: page
title: Categories
---

{% for category in site.categories %}
    <a href="/category/{{ category[0] | slugify }}">
        <h2>{{ category[0] }}</h2>
    </a>
    <ul>
    {% for post in site.categories[page.tag] %}
        <li>
            <i>{{ post.date | date: "%Y/%m/%d" }}</i>
            <a href="{{ post.url }}">{{ post.title }}</a>
        </li>
    {% endfor %}
    </ul>
{% endfor %}
