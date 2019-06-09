---
weight: 300
entry: Categories
layout: page
title: Categories
---

{% for category in site.categories %}
    <a href="/category/{{ category[0] | slugify }}">
        <h3>{{ category[0] | capitalize }}</h3>
    </a>
    <ul>
        {% for post in category[1] %}
        <li>
            <i>{{ post.date | date: "%Y/%m/%d" }}</i>
            <a href="{{ post.url }}">{{ post.title }}</a>
        </li>
        {% endfor %}
    </ul>
{% endfor %}