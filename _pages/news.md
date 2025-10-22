---
layout: page
title: News
permalink: /news/
---

Below are our latest posts.

{% assign posts = site.posts | sort: "date" | reverse %}
{% if posts and posts.size > 0 %}
<ul>
{% for post in posts %}
  <li>
    <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
    — {{ post.date | date: "%b %d, %Y" }}
    {% comment %}
    <code>{{ post.path }}</code>   <!-- debug: shows source file -->
    {% endcomment %}
  </li>
{% endfor %}
</ul>
{% else %}
<p>No posts yet.</p>
{% endif %}

