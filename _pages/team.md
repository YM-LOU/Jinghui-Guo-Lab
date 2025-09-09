---
permalink: /team/
title: "Team"
layout: single
---

{% for member in site.data.team %}
  <div class="feature__item">
    <div class="archive__item">
      <div class="archive__item-teaser">
        <img src="{{ member.image | default: '/assets/images/team/placeholder.jpg' }}" 
             alt="{{ member.name }}"
             onerror="this.src='/assets/images/team/placeholder.jpg'">
      </div>
      <div class="archive__item-body">
        <h3 class="archive__item-title">{{ member.name }}</h3>
        <div class="archive__item-excerpt">
          <p><em>{{ member.position }}</em></p>
          <p>{{ member.bio }}</p>
          {% if member.email or member.website %}
          <div class="page__meta">
            {% if member.email %}
            <a href="mailto:{{ member.email }}"><i class="fas fa-fw fa-envelope" aria-hidden="true"></i> Email</a>
            {% endif %}
            {% if member.website %}
            <a href="{{ member.website }}" target="_blank"><i class="fas fa-fw fa-link" aria-hidden="true"></i> Website</a>
            {% endif %}
          </div>
          {% endif %}
        </div>
      </div>
    </div>
  </div>
{% endfor %}

<style>
.feature__item {
  margin-bottom: 2em;
}

@media screen and (min-width: 768px) {
  .feature__wrapper {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    gap: 2rem;
  }
}

@media screen and (min-width: 1200px) {
  .feature__wrapper {
    grid-template-columns: repeat(3, 1fr);
  }
}
</style>
