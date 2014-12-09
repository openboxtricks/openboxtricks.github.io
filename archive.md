---
layout: page
title: archive
permalink: /archive/
---

{% for post in site.posts %}
    <div class="post ml2">
      <a href="{{ post.url | prepend: site.baseurl }}" class="post-link">
        <h4 class="tight post-title">{{ post.title }}</h4>
        <p class="small post-summary">{{ post.summary }}</p>
      </a>
    </div>
{% endfor %}
