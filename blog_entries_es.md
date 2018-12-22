---
layout: page
title: Blog
lang: es
permalink: /es/blog/
---

{% assign sorted_cats = site.blog_entries_es | group_by: "region" %}
{% for category in sorted_cats reversed %}
  
  <div id="#{{ category.name }}"></div>
  <p></p>
  
  <h3 class="category-head">{{ category.name | replace: "_", " " }}</h3>
  <a name="{{ category.name | slugize }}"></a>
  {% assign sorted_days = category.items | reverse %}
  {% for item in sorted_days %}
  <h4><a href="{{ site.baseurl }}{{ item.url }}">{{item.title}}. {{item.location}}</a></h4>
  {% endfor %}
{% endfor %}
