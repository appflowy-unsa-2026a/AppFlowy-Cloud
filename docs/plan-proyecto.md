---
title: Plan de proyecto
eyebrow: Documentación · Hito 1
description: Objetivos, alcance, herramientas, modelo de proceso y entregables del trabajo final.
permalink: /plan-proyecto/
---

## 1. Información general

<dl class="dl">
  <dt>Título</dt><dd>Scrum y DevOps aplicado a AppFlowy-Cloud</dd>
  <dt>Curso</dt><dd>Ingeniería y Procesos de Software (IPS) — 2026-A</dd>
  <dt>Sección</dt><dd>B</dd>
  <dt>Universidad</dt><dd>Universidad Nacional de San Agustín de Arequipa</dd>
  <dt>Equipo</dt><dd>4 integrantes — ver <a href="{{ '/equipo/' | relative_url }}">página del equipo</a></dd>
</dl>

## 2. Objetivo general

Implementar un proceso de desarrollo de software que integre la metodología ágil **Scrum** con prácticas **DevOps** automatizadas, aplicado sobre el proyecto open source **AppFlowy-Cloud**, con el propósito de comprender, analizar y ejecutar las fases del ciclo de vida del software en un producto real.

## 3. Producto de software seleccionado

AppFlowy-Cloud es el backend self-hosted de **AppFlowy**, una alternativa open source a Notion enfocada en workspaces colaborativos para equipos y empresas. Permite a las organizaciones tener pleno control sobre sus datos al alojar la solución en infraestructura propia.

| Aspecto | Detalle |
|:---|:---|
| Repositorio original | [AppFlowy-IO/AppFlowy-Cloud](https://github.com/AppFlowy-IO/AppFlowy-Cloud) |
| Fork del equipo | [appflowy-unsa-2026a/AppFlowy-Cloud](https://github.com/appflowy-unsa-2026a/AppFlowy-Cloud) |
| Último release | v0.11.9 — 12 de mayo de 2026 |
| Commits totales | más de 7,200 |

### Justificación frente a los criterios de la ficha

| Criterio | Requisito | AppFlowy-Cloud cumple |
|:---|:---|:---|
| Licencia | MIT preferentemente | AGPL-3.0 *(aprobada como excepción por el docente)* |
| Dominio empresarial | Sistemas para PyMEs | Workspace colaborativo para equipos y empresas |
| Stack moderno | Frontend + backend vigentes | Rust (86.7%), TypeScript, Flutter/Dart |
| Complejidad | 3 a 5 módulos y > 10 KLOC | Kanban, Databases, Documents, AI, Templates — > 10 KLOC |
| Docker Compose | Preferentemente incluido | `docker-compose.yml`, `-dev`, `-ci`, `-extras` |
| Actividad reciente | Obligatoria | Release v0.11.9 del 12.MAY.2026 |

<div class="callout callout--note">
  <span class="callout__icon">✦</span>
  <div class="callout__body">
    <p><strong>Validación del entorno.</strong> El integrante Gabriel Quispe Mamani levantó AppFlowy-Cloud localmente con Docker Compose, confirmando que el proyecto compila y arranca correctamente. Esto garantiza que el equipo puede iniciar el Sprint 1 sin bloqueadores técnicos.</p>
  </div>
</div>

## 4. Alcance del proyecto

Durante el semestre 2026-A el equipo:

1. **Analizará** el estado actual de AppFlowy-Cloud, identificando módulos y arquitectura.
2. **Aplicará el marco Scrum** mediante GitHub Projects, organizando el trabajo en Sprints de aproximadamente 15 días.
3. **Implementará prácticas DevOps** usando GitHub Actions para automatizar pruebas, construcción y despliegue continuo.
4. **Propondrá mejoras o refactorizaciones** sobre módulos seleccionados del proyecto.
5. **Publicará** la documentación técnica del proceso en GitHub Pages.
6. **Redactará** un artículo en formato IEEE describiendo el modelo de desarrollo aplicado.

## 5. Herramientas

| Herramienta | Uso en el proyecto |
|:---|:---|
| **GitHub Projects** | Tablero Scrum / Kanban del equipo |
| **GitHub Issues** | Product Backlog e historias de usuario |
| **GitHub Actions** | Pipelines de CI/CD automatizados |
| **GitHub Pages** | Publicación de la documentación |
| **Docker Compose** | Infraestructura local del backend |

## 6. Modelo de proceso

El proyecto sigue un modelo **Scrum + DevOps**:

- **Scrum** estructura el trabajo en Sprints, Product Backlog, Sprint Backlog y revisiones.
- **DevOps** automatiza las fases de integración y entrega continua mediante pipelines en GitHub Actions, asegurando calidad y rapidez de retroalimentación.

## 7. Entregables por hito

| Hito | Fecha | Entregables |
|:---|:---|:---|
| **Hito 1** | 13.MAY.2026 | Plan de proyecto, cronograma, presentación del producto, GitHub Project, GitHub Pages |
| **Hito 2** | 10.JUN.2026 | Producto funcionando con CI/CD, Scrum implementado (Sprints 1–2) |
| **Hito 3** | 13.JUL.2026 | Mejoras al producto con despliegue automatizado, documentación técnica completa, artículo IEEE |

Ver detalle en la página de [Cronograma]({{ '/cronograma/' | relative_url }}).
