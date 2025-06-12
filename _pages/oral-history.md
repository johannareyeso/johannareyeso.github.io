---
layout: page
title: "Revolutionary Oral History Project"
permalink: /oral-history/
---

## Revolutionary Oral History Project

{% for person in site.data.revolutionaries %}
<div style="display: flex; margin-bottom: 2em;">
  <img src="{{ person.photo | relative_url }}" alt="{{ person.name }}" style="width: 150px; height: auto; margin-right: 20px;">
  <div>
    <h3>{{ person.name }}</h3>
    <p>{{ person.description }}</p>
  </div>
</div>
{% endfor %}
