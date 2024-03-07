---
layout: page
title: Quiz Archive
---

{% assign sorted_posts = site.posts | sort: 'date' %}
{% assign grouped_posts = sorted_posts | group_by_exp: "post", "post.date | date: '%Y %B'" %}

{% for group in grouped_posts %}
  <h3>{{ group.name }}</h3>
  <ul>
    {% for post in group.items %}
      <li><a href="{{ post.url }}">{{ post.title }}</a> - {{ post.date | date: "%d %B %Y" }}</li>
    {% endfor %}
  </ul>
{% endfor %}
