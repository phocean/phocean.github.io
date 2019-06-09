---
weight: 300
entry: Categories
layout: page
title: Categories
---

<ul>
    {% for category in site.categories %}
    <li>
        <a href="/category/{{ category[0] | slugify }}">
            <h2>{{ category[0] }}</h2>
        </a>
    </li>
    {% endfor %}
    <ul>
        {% for post in category[1] %}
        <li>{{post.title}}</li>
        ({{ post.date | date: "%Y/%m/%d" }})
        {% endfor %}
    </ul>
</ul>
