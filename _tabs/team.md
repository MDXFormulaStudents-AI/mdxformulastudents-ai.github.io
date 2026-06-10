---
title: Team Members
icon: fas fa-users
order: 3
---

{% for group in site.data.team %}
  {% if site.data.team.size > 1 %}
  <h2 class="fsai-year">{{ group.year }} Team</h2>
  {% endif %}
  <div class="fsai-grid">
    {% for member in group.members %}
    {% if member.linkedin %}
    <a class="fsai-card" href="{{ member.linkedin }}" target="_blank" rel="noopener">
    {% else %}
    <div class="fsai-card">
    {% endif %}
      {% if member.photo %}
      <img class="fsai-photo" src="{{ member.photo | relative_url }}" alt="{{ member.name }}">
      {% else %}
      <div class="fsai-avatar">{{ member.name | slice: 0 }}</div>
      {% endif %}
      <h3>{{ member.name }}</h3>
      <p class="role">{{ member.role }}</p>
      {% if member.subteam %}<p class="subteam">{{ member.subteam }}</p>{% endif %}
    {% if member.linkedin %}</a>{% else %}</div>{% endif %}
    {% endfor %}
  </div>
{% endfor %}

<style>
  .fsai-year { margin: 2rem 0 1rem; padding-bottom: .3rem; border-bottom: 2px solid #E4002B; }
  .fsai-grid {
    display: grid; gap: 1.25rem;
    grid-template-columns: repeat(auto-fill, minmax(160px, 1fr));
  }
  .fsai-card { text-align: center; display: block; text-decoration: none; color: inherit; }
  .fsai-photo, .fsai-avatar {
    width: 120px; height: 120px; border-radius: 50%;
    border: 3px solid #E4002B; margin: 0 auto; transition: transform .15s ease;
  }
  .fsai-photo { object-fit: cover; }
  .fsai-avatar {
    display: flex; align-items: center; justify-content: center;
    font-size: 2.5rem; font-weight: 700; color: #fff; background: #1A1A1A;
  }
  a.fsai-card:hover .fsai-photo, a.fsai-card:hover .fsai-avatar { transform: scale(1.05); }
  a.fsai-card:hover h3 { color: #E4002B; }
  .fsai-card h3 { margin: .6rem 0 .1rem; font-size: 1.05rem; }
  .fsai-card .role { margin: 0; font-weight: 600; }
  .fsai-card .subteam { margin: .1rem 0 0; opacity: .65; font-size: .85rem; }
</style>
