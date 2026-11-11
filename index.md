---
title: Inicio
---

<div class="hero">
  <span class="eyebrow">CENTRO DE AYUDA</span>
  <h1>Todo lo que necesitas para usar nuestros productos.</h1>
  <p>Guías claras, instrucciones prácticas y novedades para aprovechar mejor las herramientas de tu equipo.</p>
</div>

<h2 id="projects">Explora la documentación</h2>

<div class="project-list">
{% assign project_pages = site.pages | sort: "url" %}
{% for project_page in project_pages %}
{% assign url_parts = project_page.url | split: "/" %}
{% if project_page.name == "index.md" and url_parts[1] == "projects" and url_parts.size == 3 %}
{% assign project_description = project_page.description | default: "Consulta las guías disponibles para este proyecto." %}
<a class="project-card" href="{{ project_page.url | relative_url }}">
  <span class="card-icon" aria-hidden="true">{{ project_page.title | slice: 0 | upcase | escape }}</span>
  <span class="card-copy">
    <strong>{{ project_page.title | escape }}</strong>
    <span>{{ project_description | escape }}</span>
  </span>
  <span class="card-arrow" aria-hidden="true">→</span>
</a>
{% endif %}
{% endfor %}
</div>

<a class="project-card" href="{{ '/projects/app-autorizaciones/' | relative_url }}">
  <span class="card-icon" aria-hidden="true">A</span>
  <span class="card-copy">
    <strong>App Autorizaciones</strong>
    <span>Guía para consultar órdenes de compra, facturas y pagos.</span>
  </span>
  <span class="card-arrow" aria-hidden="true">→</span>
</a>

<p class="home-note">Selecciona un producto para consultar sus guías de usuario.</p>
