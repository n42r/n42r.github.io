---
layout: plain
permalink: /writing/
---

# Engineering in the 2020s

<ul>
  {% for post in site.posts %}
  <li><a href="{{ post.url }}">{{ post.title }}</a> <span class="listing-meta">{% include read_time.html content=post.content %}</span></li>
  {% endfor %}
</ul>