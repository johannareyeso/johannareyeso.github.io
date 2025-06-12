---
layout: archive
title: "Research"
permalink: /research/
author_profile: true
---

{% assign grouped = site.publications | group_by: 'status' %}
{% assign order = "Dissertation Project,Under Review,Working Papers" | split: "," %}

{% for heading in order %}
  {% assign group = grouped | where: "name", heading | first %}
  {% if group %}
### {{ heading }}

    {% assign posts = group.items %}
    {% if heading == "Working Papers" %}
      {% assign posts = posts | sort: 'path' | reverse %}
    {% endif %}

    {% for post in posts %}
  - [{{ post.title }}]({{ post.url | relative_url }})
    {% endfor %}
  {% endif %}
{% endfor %}




