---
layout: archive
title: "Revolutionary Oral History Project"
permalink: /oral-history/
author_profile: true
---

<style>
  /* Two-column grid that collapses to one on small screens */
  .rev-grid {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    gap: 2rem 1.5rem; /* row gap / column gap */
  }
  @media (max-width: 720px) {
    .rev-grid { grid-template-columns: 1fr; }
  }

  /* Keep original image shape */
  .rev-card img {
    width: 100%;
    height: auto;    /* preserves original aspect ratio */
    display: block;
    margin-bottom: 0.5em;
    border-radius: 6px;
  }
  .rev-credit {
    font-size: 0.85em;
    color: #777;
    margin: 0 0 0.25em 0;
  }
  .rev-credit a { color: inherit; text-decoration: none; }
  .rev-card h3 { margin: 0.4em 0 0.25em; }
  .rev-card p { margin: 0; }
</style>

<p>
This project documents the lived experiences of revolutionary actors through a series of oral history interviews. It features portraits and testimonies of women and men who participated in post-World War II revolutions. By preserving their voices and personal narratives, the project aims to recover grassroots perspectives on political struggle, gender roles, and the long-term legacies of revolutionary change.
</p>

<div class="rev-grid">
{% for person in site.data.revolutionaries %}
  <div class="rev-card">
    <img src="{{ person.photo | relative_url }}" alt="{{ person.name }}" loading="lazy">

    {% if person.credit_text and person.credit_url %}
      <p class="rev-credit">
        <a href="{{ person.credit_url }}" target="_blank" rel="noopener">{{ person.credit_text }}</a>
      </p>
    {% endif %}

    <h3>{{ person.name }}</h3>
    {% if person.description %}<p>{{ person.description }}</p>{% endif %}
  </div>
{% endfor %}
</div>
