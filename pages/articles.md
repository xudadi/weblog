---
title: 归档
layout: post
permalink: /articles/
dskey: /articles.html
favicon: /assets/img/fav/articles.png
show_ad: true
---

{% for category in site.categories %}
<div class="category-item">
    <div class="category-title"><b>#{{ category | first | capitalize }}丨{{ category | last | size }}</b></div>
</div>
{% for post in category.last %}
<div class="article-item">
    <div class="article-title">
        <a href="{{ post.url }}" target="_blank">{{ post.title }}</a>
        <span class="article-date">{{post.date | date:"%Y %m-%d"}}</span>
    </div>
</div>
{% endfor %}
{% endfor %}