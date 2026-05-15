---
layout: home
title: Inicio
description: Scrum y DevOps aplicado a AppFlowy-Cloud. Proyecto académico del curso IPS 2026-A en la Universidad Nacional de San Agustín de Arequipa.
permalink: /
---

<section class="hero">
  <div class="hero__inner">
    <img
      class="hero__logo"
      src="{{ '/assets/img/logo-unsa.png' | relative_url }}"
      alt="Universidad Nacional de San Agustín de Arequipa"
      width="320"
      height="107"
      loading="eager">
    <p class="eyebrow">
      <span class="eyebrow__pill">IPS 2026-A</span>
      <span>Curso de Ingeniería y Procesos de Software · Sección B</span>
    </p>
    <h1>Scrum y DevOps aplicado a <span class="gradient">AppFlowy-Cloud</span></h1>
    <p class="lead">
      Implementamos un proceso de desarrollo ágil integrado con prácticas DevOps automatizadas
      sobre un producto open source real de mediana complejidad, escrito en Rust.
    </p>
    <div class="hero__actions">
      <a class="btn btn--primary btn--lg" href="{{ '/plan-proyecto/' | relative_url }}">Ver plan de proyecto →</a>
      <a class="btn btn--ghost btn--lg" href="{{ site.project_url }}" target="_blank" rel="noopener">Tablero Scrum</a>
    </div>
  </div>
</section>

<section class="section">
  <div class="container">
    <div class="stats">
      <div class="stat">
        <div class="stat__value">4</div>
        <div class="stat__label">Integrantes del equipo</div>
      </div>
      <div class="stat">
        <div class="stat__value">5</div>
        <div class="stat__label">Sprints planificados</div>
      </div>
      <div class="stat">
        <div class="stat__value">3</div>
        <div class="stat__label">Hitos de evaluación</div>
      </div>
      <div class="stat">
        <div class="stat__value">> 10K</div>
        <div class="stat__label">LOC del producto base</div>
      </div>
    </div>
  </div>
</section>

<section class="section section--soft">
  <div class="container">
    <div class="section__head">
      <span class="section__eyebrow">Producto seleccionado</span>
      <h2 class="section__title">AppFlowy-Cloud, alternativa open source a Notion</h2>
      <p class="section__subtitle">
        Backend self-hosted del workspace colaborativo AppFlowy. Stack moderno basado en Rust,
        TypeScript y Docker Compose, con actividad reciente sostenida.
      </p>
    </div>
    <div class="grid grid--3">
      <article class="card">
        <div class="card__icon">⚡</div>
        <h3 class="card__title">Stack moderno</h3>
        <p class="card__body">Rust (86.7%), TypeScript y Flutter/Dart. Tecnologías vigentes en la industria actual.</p>
      </article>
      <article class="card">
        <div class="card__icon">🧩</div>
        <h3 class="card__title">Cinco módulos</h3>
        <p class="card__body">Kanban, Databases, Documents, AI y Templates. Complejidad acorde al curso.</p>
      </article>
      <article class="card">
        <div class="card__icon">🐳</div>
        <h3 class="card__title">Docker Compose</h3>
        <p class="card__body">Cuatro <code>docker-compose</code> listos: prod, dev, ci y extras. Pipeline DevOps natural.</p>
      </article>
      <article class="card">
        <div class="card__icon">🔄</div>
        <h3 class="card__title">Actividad reciente</h3>
        <p class="card__body">Último release v0.11.9 publicado el 12 de mayo de 2026. Más de 7,200 commits.</p>
      </article>
      <article class="card">
        <div class="card__icon">📜</div>
        <h3 class="card__title">Licencia AGPL-3.0</h3>
        <p class="card__body">Excepción aprobada por el docente. Permite el fork, modificación y entrega académica.</p>
      </article>
      <article class="card">
        <div class="card__icon">✅</div>
        <h3 class="card__title">Entorno validado</h3>
        <p class="card__body">El integrante Gabriel Quispe ya levantó AppFlowy-Cloud localmente con Docker Compose.</p>
      </article>
    </div>
  </div>
</section>

<section class="section">
  <div class="container">
    <div class="section__head">
      <span class="section__eyebrow">Proceso de trabajo</span>
      <h2 class="section__title">Scrum + DevOps integrados de extremo a extremo</h2>
      <p class="section__subtitle">
        El proyecto combina la disciplina del marco Scrum con la automatización de DevOps,
        usando las herramientas oficiales del ecosistema GitHub.
      </p>
    </div>
    <div class="grid grid--2">
      <article class="card">
        <div class="card__icon">📋</div>
        <h3 class="card__title">Scrum</h3>
        <p class="card__body">
          Sprints de 15 días, Product Backlog en GitHub Issues, tablero Kanban en GitHub Projects,
          ceremonias de planning, daily, review y retrospective. Liderazgo rotativo entre los integrantes.
        </p>
      </article>
      <article class="card">
        <div class="card__icon">⚙️</div>
        <h3 class="card__title">DevOps</h3>
        <p class="card__body">
          Pipelines de Integración Continua y Entrega Continua con GitHub Actions: build,
          tests, generación de imagen Docker y despliegue automatizado a staging.
        </p>
      </article>
    </div>
  </div>
</section>

<section class="section section--cta">
  <div class="container text-center">
    <h2 class="section__title" style="color:white">Explora la documentación pública del proyecto</h2>
    <p class="section__subtitle" style="color:rgba(255,255,255,0.85)">
      Todo el avance del equipo se documenta de forma abierta en este sitio y en el repositorio GitHub.
    </p>
    <div class="hero__actions mt-8">
      <a class="btn btn--ghost btn--lg" href="{{ '/cronograma/' | relative_url }}">Cronograma</a>
      <a class="btn btn--ghost btn--lg" href="{{ '/equipo/' | relative_url }}">Conoce al equipo</a>
      <a class="btn btn--ghost btn--lg" href="{{ site.fork_url }}" target="_blank" rel="noopener">Ver repositorio ↗</a>
    </div>
  </div>
</section>
