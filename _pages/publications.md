---
layout: archive
title: "Research"
permalink: /research/
author_profile: true
---

<style>
.paper-abstract {
  display: none;
  margin-top: 0.4em;
  margin-left: 1em;
  color: #555;
  font-size: 0.95em;
  line-height: 1.5;
}
.toggle-abstract {
  background: none;
  border: none;
  color: #888;
  font-size: 0.8em;
  cursor: pointer;
  padding: 0 0.3em;
  margin-left: 0.4em;
}
.toggle-abstract:hover {
  color: #333;
}
</style>

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
- {{ post.title }}
  {% if post.abstract %}
  <button class="toggle-abstract" onclick="toggleAbstract(this)">▸ abstract</button>
  <div class="paper-abstract">{{ post.abstract }}</div>
  {% endif %}
    {% endfor %}
  {% endif %}
{% endfor %}

<script>
function toggleAbstract(btn) {
  const div = btn.nextElementSibling;
  const open = div.style.display === 'block';
  div.style.display = open ? 'none' : 'block';
  btn.textContent = open ? '▸ abstract' : '▾ abstract';
}
</script>
