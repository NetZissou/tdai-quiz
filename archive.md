---
layout: page
title: Blog Archive
---

{% assign sorted_posts = site.posts | sort: 'date' | reverse %}
{% for post in sorted_posts %}
  {% unless post.previous %}
    {% capture current_date %}{{ post.date | date: '%B %Y' }}{% endcapture %}
    {% capture previous_date %}{{ post.previous.date | date: '%B %Y' }}{% endcapture %}
    {% if current_date != previous_date %}
      <h3>{{ current_date }}</h3>
    {% endif %}
  {% endunless %}
  <ul>
      <li>{{ post.date | date: "%B %d, %Y" }} - <a href="{{ post.url }}">{{ post.title }}</a></li>
  </ul>
{% endfor %}
