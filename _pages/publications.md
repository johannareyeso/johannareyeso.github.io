---
layout: archive
title: "Research"
permalink: /research/
author_profile: true
---

{% assign grouped = site.publications | sort: 'status' | group_by: 'status' %}
{% assign order = "Dissertation Project,Under Review,Working Papers" | split: "," %}

{% for heading in order %}
  {% assign group = grouped | where: "name", heading | first %}
  {% if group %}
### {{ heading }}
  {% for post in group.items %}
  - [{{ post.title }}]({{ post.url | relative_url }})
  {% endfor %}
  {% endif %}
{% endfor %}



