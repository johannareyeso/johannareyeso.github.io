---
layout: archive
title: "Research"
permalink: /research/
author_profile: true
---


{% include base_path %}

{% for post in site.publications reversed %}
  [{{ post.title }}]({{ post.url | relative_url }})
{% endfor %}


