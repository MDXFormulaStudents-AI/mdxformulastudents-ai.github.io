---
title: What We've Been Up To
icon: fas fa-bullhorn
order: 2
---

{% if site.posts.size > 0 %}
<div class="fsai-feed">
  {% for post in site.posts %}
  <a class="fsai-feed-item" href="{{ post.url | relative_url }}">
    {% if post.image %}
    <img src="{{ post.image.path | default: post.image | relative_url }}" alt="">
    {% endif %}
    <div class="fsai-feed-body">
      <h3>{{ post.title }}</h3>
      <p>{{ post.description | default: post.excerpt | strip_html | truncate: 140 }}</p>
      <small>{{ post.date | date: '%b %d, %Y' }}</small>
    </div>
  </a>
  {% endfor %}
</div>
{% else %}
<p>No updates yet. Posts added to <code>_posts/</code> will appear here.</p>
{% endif %}

<style>
  .fsai-feed { display: flex; flex-direction: column; gap: 1rem; }
  .fsai-feed-item {
    display: flex; gap: 1rem; padding: 1rem; border-radius: .5rem;
    text-decoration: none; color: inherit;
    background: rgba(127,127,127,.06); transition: background .15s ease;
  }
  .fsai-feed-item:hover { background: rgba(228,0,43,.10); }
  .fsai-feed-item img {
    width: 120px; height: 80px; object-fit: cover; border-radius: .4rem; flex: none;
  }
  .fsai-feed-body h3 { margin: 0 0 .25rem; }
  .fsai-feed-body small { opacity: .65; }
  @media (max-width: 560px) {
    .fsai-feed-item { flex-direction: column; }
    .fsai-feed-item img { width: 100%; height: 160px; }
  }
</style>
