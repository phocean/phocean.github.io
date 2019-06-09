---
weight: 300
entry: Categories
layout: page
title: Categories
---

{% for category in site.categories %}
    {% capture category_name %}{{ category | first }}{% endcapture %}
    "#{{ category_name | slugize }}"
    <h3 class="category-head">{{ category_name  | capitalize}}</h3>
    <a name="{{ category_name | slugize }}"></a>
    {% for post in site.categories[category_name] %}
    <ul>
        <li>
        <a href="{{ post.url }}">{{post.title}}</a>
        </li>
    </ul>
    {% endfor %}
{% endfor %}