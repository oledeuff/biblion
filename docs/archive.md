---
layout: page
title: Archive
permalink: /archive/
---

{% assign posts_by_year = site.posts | group_by_exp: "post", "post.date | date: '%Y'" %}

{% for year in posts_by_year %}
  <h2>{{ year.name }}</h2>
  <ul>
    {% for post in year.items %}
      <li>
        <span>{{ post.date | date: "%Y-%m-%d" }}</span>
        —
        <a href="{{ site.baseurl }}{{ post.url }}">{{ post.title }}</a>
      </li>
    {% endfor %}
  </ul>
{% endfor %}
