---
layout: page
title: "Revolutionary Oral History Project"
permalink: /oral-history/
---

## Revolutionary Oral History Project

This project documents the lived experiences of revolutionary actors through a series of oral history interviews. It features portraits and testimonies of women and men who participated in post-World War II revolutions. By preserving their voices and personal narratives, the project aims to recover grassroots perspectives on political struggle, gender roles, and the long-term legacies of revolutionary change.

{% for person in site.data.revolutionaries %}
<div style="display: flex; margin-bottom: 2em;">
  <img src="{{ person.photo | relative_url }}" alt="{{ person.name }}" style="width: 150px; height: auto; margin-right: 20px;">
  <div>
    <h3>{{ person.name }}</h3>
    <p>{{ person.description }}</p>
  </div>
</div>
{% endfor %}
