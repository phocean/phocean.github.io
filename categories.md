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
            {{ category[0] }}
        </a>
    </li>
    {% endfor %}
    <ul>
        {% for post in category[1] %}
        <li>{{post.title}}</li>
        {% endfor %}
    </ul>
</ul>
