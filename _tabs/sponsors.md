---
title: Sponsors
icon: fas fa-handshake
order: 4
---

<p class="fsai-sponsor-intro">
  TODO: A line thanking your sponsors, and an invitation for new sponsors to get in touch.
</p>

{% if site.data.sponsors and site.data.sponsors.size > 0 %}
<div class="fsai-sponsors">
  {% for s in site.data.sponsors %}
  {% if s.url %}
  <a class="fsai-sponsor" href="{{ s.url }}" target="_blank" rel="noopener" title="{{ s.name }}">
  {% else %}
  <div class="fsai-sponsor" title="{{ s.name }}">
  {% endif %}
    {% if s.logo %}
    <img src="{{ s.logo | relative_url }}" alt="{{ s.name }}">
    {% else %}
    <span class="fsai-sponsor-name">{{ s.name }}</span>
    {% endif %}
  {% if s.url %}</a>{% else %}</div>{% endif %}
  {% endfor %}
</div>
{% else %}
<p>We're currently looking for sponsors. Get in touch via the Contact page.</p>
{% endif %}

<style>
  .fsai-sponsor-intro { margin-bottom: 1.5rem; }
  .fsai-sponsors {
    display: grid; gap: 1.5rem;
    grid-template-columns: repeat(auto-fill, minmax(160px, 1fr));
  }
  .fsai-sponsor {
    display: flex; align-items: center; justify-content: center;
    min-height: 100px; padding: 1rem; border-radius: .5rem;
    text-decoration: none; color: inherit;
    background: rgba(127,127,127,.06); border: 1px solid transparent;
    transition: all .15s ease;
  }
  a.fsai-sponsor:hover { border-color: #E4002B; background: rgba(228,0,43,.08); }
  .fsai-sponsor img {
    max-width: 100%; max-height: 80px; object-fit: contain;
    filter: grayscale(1); opacity: .85; transition: all .15s ease;
  }
  a.fsai-sponsor:hover img { filter: none; opacity: 1; }
  .fsai-sponsor-name { font-weight: 600; text-align: center; }
</style>
