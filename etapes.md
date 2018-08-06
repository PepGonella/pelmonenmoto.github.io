---
layout: page
title: Blog
permalink: /etapes/
---

## Blog

<div class="clear">&nbsp;</div>

{% assign sorted_cats = site.categories | sort %}
{% for category in sorted_cats reversed %}
  <div id="#{{ category[0] }}"></div>
  <p></p>
  
  <h3 class="category-head">{{ category[0] | replace: "_", " " }}</h3>
  <a name="{{ category[0] | slugize }}"></a>
  {% assign sorted_posts = category[1] %}
  {% for post in sorted_posts %}
  <h4><a href="{{ site.baseurl }}{{ post.url }}">{{post.title}}. {{post.location}}</a></h4>
  {% endfor %}
{% endfor %}

<div style="text-align:center; padding: 0 0 30px 0;color: rgb(219, 115, 43)">{{ page.location }} - {{ page.date | date: "%B %Y"}}</div>
