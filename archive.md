---
layout: page
title: archive
permalink: /archive/
---

{% for post in site.posts %}
  * <h4 class="tight post-title">[ {{ post.title }} ]({{ post.url }})</h4>
{% endfor %}
