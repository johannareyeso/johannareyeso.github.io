---
layout: archive
title: "Research"
permalink: /research/
author_profile: true
---

<style>
  ul {
  list-style: none;
  padding-left: 0;
}
.paper-abstract {
  display: none;
  margin-top: 0.5em;
  margin-left: 0.5em;
  color: #555;
  font-size: 0.95em;
  line-height: 1.6;
  padding-left: 0.5em;
  border-left: 2px solid #ddd;
}
.paper-title {
  cursor: pointer;
  color: #52adc8;
}
.paper-title:hover {
  text-decoration: underline;
}
</style>

{% assign grouped = site.publications | group_by: 'status' %}
{% assign order = "Dissertation Project,Under Review,Working Papers" | split: "," %}

{% for heading in order %}
  {% assign group = grouped | where: "name", heading | first %}
  {% if group %}
    {% assign posts = group.items %}
    {% if heading == "Working Papers" %}
      {% assign posts = posts | sort: 'path' | reverse %}
    {% endif %}

<h3>{{ heading }}</h3>
<ul>
  {% for post in posts %}
  <li>
    <span class="paper-title" onclick="toggleAbstract(this)">▸ {{ post.title }}</span>
    {% if post.abstract %}
    <div class="paper-abstract">{{ post.abstract }}</div>
    {% endif %}
  </li>
  {% endfor %}
</ul>

  {% endif %}
{% endfor %}

<script>
function toggleAbstract(span) {
  const div = span.nextElementSibling;
  if (!div) return;
  const open = div.style.display === 'block';
  div.style.display = open ? 'none' : 'block';
  span.textContent = (open ? '▸ ' : '▾ ') + span.textContent.slice(2);
}
</script>
