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
        <div class="stat__value">9/9</div>
        <div class="stat__label">Issues cerrados</div>
      </div>
      <div class="stat">
        <div class="stat__value">11</div>
        <div class="stat__label">Servicios Docker activos</div>
      </div>
      <div class="stat">
        <div class="stat__value">2</div>
        <div class="stat__label">Pipelines CI + CD</div>
      </div>
      <div class="stat">
        <div class="stat__value">5/5</div>
        <div class="stat__label">Sprints completados</div>
      </div>
    </div>
  </div>
</section>

<section class="section section--soft">
  <div class="container">
    <div class="section__head">
      <span class="section__eyebrow">Hito 3 · Proyecto completo</span>
      <h2 class="section__title">Ciclo CI/CD completo y cuatro Sprints cerrados</h2>
      <p class="section__subtitle">
        Al cierre del Hito 3 el equipo cuenta con el producto AppFlowy-Cloud levantado con Docker
        Compose, dos pipelines propios —CI y CD— que construyen y publican la imagen del backend en
        GitHub Container Registry, y los cuatro Sprints documentados con su artículo IEEE final.
      </p>
    </div>
    <div class="grid grid--3">
      <article class="card">
        <div class="card__icon">🐳</div>
        <h3 class="card__title">Entorno funcionando</h3>
        <p class="card__body">
          Once servicios orquestados con Docker Compose, diez de ellos saludables.
          API REST, base de datos PostgreSQL, autenticación GoTrue y panel administrativo accesibles en localhost.
        </p>
      </article>
      <article class="card">
        <div class="card__icon">⚙️</div>
        <h3 class="card__title">Pipelines CI y CD propios</h3>
        <p class="card__body">
          <code>ci-equipo-ips.yml</code> valida el repositorio en cada push;
          <code>cd-equipo-ips.yml</code> construye y publica la imagen Docker del
          backend en GitHub Container Registry.
          <a href="{{ '/ci-cd/' | relative_url }}">Detalles del pipeline →</a>
        </p>
      </article>
      <article class="card">
        <div class="card__icon">📊</div>
        <h3 class="card__title">Cuatro Sprints documentados</h3>
        <p class="card__body">
          Sprints 0 a 4 cerrados con retrospectivas, métricas de velocity
          y burndown charts. <a href="{{ '/sprints/' | relative_url }}">Ver retrospectivas →</a>
        </p>
      </article>
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
