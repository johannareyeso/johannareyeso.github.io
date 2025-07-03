---
layout: archive
title: "Revolutionary Oral History Project"
permalink: /oral-history/
author_profile: true
---

This project documents the lived experiences of revolutionary actors through a series of oral history interviews. It features portraits and testimonies of women and men who participated in post-World War II revolutions. By preserving their voices and personal narratives, the project aims to recover grassroots perspectives on political struggle, gender roles, and the long-term legacies of revolutionary change.

{% for person in site.data.revolutionaries %}
  <div style="margin-bottom: 3em;">
    <img src="{{ person.photo | relative_url }}" alt="{{ person.name }}" style="width: 100%; height: auto; margin-bottom: 0.5em;">
    
    {% if person.credit_text and person.credit_url %}
      <p style="font-size: 0.8em; color: #777; margin: 0;">
        <a href="{{ person.credit_url }}" target="_blank" style="color: #777; text-decoration: none;">{{ person.credit_text }}</a>
      </p>
    {% endif %}
    
    <h3 style="margin-top: 0.5em;">{{ person.name }}</h3>
    <p>{{ person.description }}</p>
  </div>
{% endfor %}
