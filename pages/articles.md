---
title: 归档
layout: post
permalink: /articles/
dskey: /articles.html
favicon: /assets/img/fav/articles.png
show_ad: true
---

<!--{% for category in site.categories %}
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
{% endfor %}-->
{% for post in site.posts %}
    {% assign year = post.date | date: '%Y' %}
    {% assign nyear = post.next.date | date: '%Y' %}
    {% if year != nyear %}
## {{ post.date | date: '%Y' }}
{:.archive-title}
    {% endif %}
* {{ post.date | date: '%m-%d' }} &raquo; [{{ post.title }}]({{ post.url }} "{{ post.title }}"){:.archive-item-link}
{% endfor %}
