---
layout: plain
permalink: /writing/
---

# Engineering in the 2020s

<ul>
  {% for post in site.posts %}
  <li><a href="{{ post.url }}">{{ post.title }}</a></li>
  {% endfor %}
</ul>