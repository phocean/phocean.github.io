---
weight: 300
entry: Categories
layout: page
title: Categories
---

{% for category in site.categories %}
<ul>
    <li>
        <a href="/category/{{ category[0] | slugify }}">
            <h2>{{ category[0] }}</h2>
        </a>
    </li>
    {% for post in site.categories[page.tag] %}
    <ul>
        <li>{{post.title}}</li>
        ({{ post.date | date: "%Y/%m/%d" }})
    </ul>
    {% endfor %}
</ul>
{% endfor %}
