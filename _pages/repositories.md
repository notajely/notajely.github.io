---
layout: page
permalink: /repositories/
title: repositories
description: My selected GitHub repositories.
nav: true
nav_order: 4
---
{% if site.data.repositories.github_users %}

## GitHub users

<div class="repositories d-flex flex-wrap flex-md-row flex-column justify-content-between align-items-center">
  {% for user in site.data.repositories.github_users %}
    {% include repository/repo_user.liquid username=user %}
  {% endfor %}
</div>

---

{% if site.repo_trophies.enabled %}
{% for user in site.data.repositories.github_users %}
{% if site.data.repositories.github_users.size > 1 %}

<h4>{{ user }}</h4>
  {% endif %}
  <div class="repositories d-flex flex-wrap flex-md-row flex-column justify-content-between align-items-center">
  {% include repository/repo_trophies.liquid username=user %}
  </div>

---

{% endfor %}
{% endif %}
{% endif %}

## GitHub Repositories

<div class="row">
  {% for repo in site.data.repositories.repositories %}
    <div class="col-md-6 mb-3">
      <div class="repo p-3 text-center border rounded h-100">
        <a href="{{ repo.url }}" target="_blank" class="text-decoration-none">
          <h5 class="repo-name">{{ repo.name }}</h5>
          <p class="repo-description text-muted">{{ repo.description }}</p>
        </a>
      </div>
    </div>
  {% endfor %}
</div>
