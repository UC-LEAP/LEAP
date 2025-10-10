---
layout: page
title: People
permalink: /people/
---

Below is our team & collaborators list.

<style>
.people-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(220px, 1fr));
  gap: 18px;
}
.person-card {
  display: grid;
  gap: 8px;
  padding: 10px;
  border-radius: 12px;
  border: 1px solid #ddd;
}
.person-card img {
  width: 160px; height: 160px; object-fit: cover; border-radius: 50%;
  justify-self: center;
}
.person-card h3 { margin: 6px 0 2px; font-size: 1.05rem; }
.person-card p  { margin: 0; }
</style>

<div class="people-grid">
{% assign folks = site.data.people %}
{% for p in folks %}
  <div class="person-card">
    {% if p.photo_url %}
      {% if p.photo_url contains '://' %}
        {% assign img_url = p.photo_url %}
      {% else %}
        {% assign img_url = p.photo_url | relative_url %}
      {% endif %}
      <img src="{{ img_url }}" alt="{{ p.name }}">
    {% endif %}
    <h3>{{ p.name }}</h3>
    {% if p.affiliation %}<p>{{ p.affiliation }}</p>{% endif %}
    {% if p.homepage %}<p><a href="{{ p.homepage }}">Homepage</a></p>{% endif %}
  </div>
{% endfor %}
</div>

