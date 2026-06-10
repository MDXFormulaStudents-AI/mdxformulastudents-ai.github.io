---
title: Team Members
icon: fas fa-users
order: 3
---

<div class="fsai-grid">
  {% for member in site.data.team %}
  <div class="fsai-card">
    {% if member.photo %}
    <img src="{{ member.photo | relative_url }}" alt="{{ member.name }}">
    {% else %}
    <div class="fsai-avatar">{{ member.name | slice: 0 }}</div>
    {% endif %}
    <h3>{{ member.name }}</h3>
    <p class="role">{{ member.role }}</p>
    {% if member.subteam %}<p class="subteam">{{ member.subteam }}</p>{% endif %}
  </div>
  {% endfor %}
</div>

<style>
  .fsai-grid {
    display: grid; gap: 1.25rem;
    grid-template-columns: repeat(auto-fill, minmax(160px, 1fr));
  }
  .fsai-card { text-align: center; }
  .fsai-card img, .fsai-avatar {
    width: 120px; height: 120px; border-radius: 50%;
    border: 3px solid #E4002B; margin: 0 auto;
  }
  .fsai-card img { object-fit: cover; }
  .fsai-avatar {
    display: flex; align-items: center; justify-content: center;
    font-size: 2.5rem; font-weight: 700; color: #fff; background: #1A1A1A;
  }
  .fsai-card h3 { margin: .6rem 0 .1rem; font-size: 1.05rem; }
  .fsai-card .role { margin: 0; font-weight: 600; }
  .fsai-card .subteam { margin: .1rem 0 0; opacity: .65; font-size: .85rem; }
</style>
