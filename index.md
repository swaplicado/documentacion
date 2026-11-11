---
title: Inicio
---

<div class="hero">
  <span class="eyebrow">CENTRO DE AYUDA</span>
  <h1>Todo lo que necesitas para usar nuestros productos.</h1>
  <p>Guías claras, instrucciones prácticas y novedades para aprovechar mejor las herramientas de tu equipo.</p>
</div>

<h2 id="projects">Explora la documentación</h2>

{% assign project_pages = site.pages | sort: "url" %}
{% for project_page in project_pages %}
{% assign url_parts = project_page.url | split: "/" %}
{% if project_page.name == "index.md" and url_parts[1] == "projects" and url_parts.size == 4 %}
<a class="project-card" href="{{ project_page.url | relative_url }}">
  <span class="card-icon" aria-hidden="true">{{ project_page.title | slice: 0 | upcase | escape }}</span>
  <span class="card-copy">
    <strong>{{ project_page.title | escape }}</strong>
    {% if project_page.description %}<span>{{ project_page.description | escape }}</span>{% endif %}
  </span>
  <span class="card-arrow" aria-hidden="true">→</span>
</a>
{% endif %}
{% endfor %}

<p class="home-note">Selecciona un producto para consultar sus guías de usuario.</p>
