---
layout: default
title: Posts
---

# Posts

Browse all posts by month and year.

{% assign postsByYearMonth = site.posts | group_by_exp: "post", "post.date | date: '%B %Y'" %}
{% for yearMonth in postsByYearMonth %}
  <h2>{{ yearMonth.name }}</h2>
  <ul>
    {% for post in yearMonth.items %}
      <li><a href="{{ post.url }}" style="color: white;">{{ post.title }}</a></li>
    {% endfor %}
  </ul>
{% endfor %}
