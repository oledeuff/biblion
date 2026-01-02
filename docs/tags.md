---
layout: page
title: Tags
permalink: /tags/
---

## Index des tags

{% assign tags_sorted = site.tags | sort %}
<ul>
{% for tag in tags_sorted %}
  {% assign tag_name = tag[0] %}
  {% assign tag_posts = tag[1] %}
  <li>
    <a href="#{{ tag_name | slugify }}">{{ tag_name }}</a>
    ({{ tag_posts | size }})
  </li>
{% endfor %}
</ul>

---

## Entrées par tag

{% for tag in tags_sorted %}
  {% assign tag_name = tag[0] %}
  {% assign tag_posts = tag[1] %}

  <h3 id="{{ tag_name | slugify }}">{{ tag_name }}</h3>
  <ul>
  {% for post in tag_posts %}
    <li>
      <span>{{ post.date | date: "%Y-%m-%d" }}</span>
      —
      <a href="{{ site.baseurl }}{{ post.url }}">{{ post.title }}</a>
    </li>
  {% endfor %}
  </ul>

{% endfor %}
