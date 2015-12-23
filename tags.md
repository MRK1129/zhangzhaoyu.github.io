---
layout: default
title: Tags
permalink: /tags/
---
<div class="page-content wc-container">
  {% for tag in site.tags %}
    <a name="{{ tag[0] }}"></a><h3>{{ tag[0] }}({{ tag[1].size }})</h3>
    <ul class="posts">
     {% for post in tag[1] %}
       <li><span>{{ post.date | date_to_string }}</span> &raquo; <a href="{{ post.url }}">{{ post.title }}</a></li>
     {% endfor %}
    </ul>
  {% endfor %}
</div>
