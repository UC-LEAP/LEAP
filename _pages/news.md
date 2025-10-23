---
layout: page
title: News
permalink: /news/
---

<style>
.news-cards {
  display: flex;
  flex-wrap: wrap;
  gap: 1.5rem;
  justify-content: flex-start;
}
.news-card {
  border: 1px solid #ddd;
  border-radius: 8px;
  width: 300px;
  overflow: hidden;
  box-shadow: 0 2px 5px rgba(0,0,0,0.1);
  display: flex;
  flex-direction: column;
}
.news-card img {
  width: 100%;
  height: auto;
}
.news-card-content {
  padding: 1rem;
}
.news-card-content h3 {
  margin-top: 0;
  font-size: 1.2rem;
}
.news-card-content p {
  font-size: 0.9rem;
  color: #555;
}
.news-card-date {
  font-size: 0.8rem;
  color: #999;
  margin-bottom: 0.5rem;
}
</style>

<div class="news-cards">
{% assign posts = site.posts | sort: "date" | reverse %}
{% for post in posts %}
  <div class="news-card">
    {% if post.image %}
      <img src="{{ post.image | relative_url }}" alt="{{ post.title }}">
    {% endif %}
    <div class="news-card-content">
      <h3><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h3>
      <div class="news-card-date">{{ post.date | date: "%b %d, %Y" }}</div>
      {% if post.excerpt %}
        <p>{{ post.excerpt }}</p>
      {% else %}
        <p>{{ post.content | strip_html | truncatewords: 25 }}</p>
      {% endif %}
    </div>
  </div>
{% endfor %}
</div>
