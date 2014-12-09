---
layout: page
title: archive
permalink: /archive/
---

{% for post in site.posts %}
  * [ {{ post.title }} ]({{ post.url }})
{% endfor %}
