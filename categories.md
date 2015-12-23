---
layout: default
title: "Categories"
permalink: /categories/
---
<div class="page-content wc-container">
    <ul class="posts">
    {% for cat in site.categories %}
        {% if cat[0] != 'blog' %}
          <a name="{{ cat[0] }}"></a>
           <h3>{{ cat[0] }}({{ cat[1].size }})</h3>
           {% for post in cat[1] %}
              <li><h5><span>{{ post.date | date_to_string }}</span> &raquo; <a href="{{ post.url }}">{{ post.title }}</a></h5></li>
           {% endfor %}
         {% endif %}
    {% endfor %}
    </ul>
</div>
