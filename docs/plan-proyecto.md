---
title: Plan de proyecto
nav_order: 2
description: "Objetivos, alcance, herramientas y modelo de proceso del trabajo final de IPS 2026-A."
---

# Plan de proyecto
{: .no_toc }

<details open markdown="block">
  <summary>Contenido</summary>
  {: .text-delta }
- TOC
{:toc}
</details>

---

## 1. Información general

| Campo | Valor |
|:---|:---|
| Título del proyecto | Scrum y DevOps aplicado a AppFlowy-Cloud |
| Curso | Ingeniería y Procesos de Software (IPS) — 2026-A |
| Sección | B |
| Universidad | Universidad Nacional de San Agustín de Arequipa |
| Equipo | 4 integrantes (ver [Equipo](equipo.html)) |

## 2. Objetivo general

Implementar un proceso de desarrollo de software que integre la metodología ágil **Scrum** con prácticas **DevOps** automatizadas, aplicado sobre el proyecto open source **AppFlowy-Cloud**, con el propósito de comprender, analizar y ejecutar las fases del ciclo de vida del software.

## 3. Producto de software seleccionado

### AppFlowy-Cloud

AppFlowy-Cloud es el backend _self-hosted_ de **AppFlowy**, una alternativa open source a Notion enfocada en workspaces colaborativos para equipos y empresas. Permite a las organizaciones tener pleno control sobre sus datos al alojar la solución en infraestructura propia.

- **Repositorio original:** <https://github.com/AppFlowy-IO/AppFlowy-Cloud>
- **Fork del equipo:** <https://github.com/appflowy-unsa-2026a/AppFlowy-Cloud>
- **Último release:** v0.11.9 (12 de mayo de 2026)
- **Commits totales:** más de 7,200

### Justificación frente a los criterios de la ficha

| Criterio | Requisito | AppFlowy-Cloud cumple |
|:---|:---|:---|
| Licencia | MIT preferentemente | AGPL-3.0 _(aprobada como excepción por el docente)_ |
| Dominio empresarial | Sistemas para PyMEs (ERP, CRM, SCM, etc.) | Workspace colaborativo para equipos y empresas |
| Stack moderno | Frontend y backend open source vigentes | Rust (86.7%), TypeScript, Flutter/Dart |
| Complejidad | 3 a 5 módulos y > 10 KLOC | Kanban, Databases, Documents, AI, Templates — > 10 KLOC |
| Docker Compose | Preferentemente incluido | `docker-compose.yml`, `-dev`, `-ci`, `-extras` |
| Documentación técnica | Obligatoria | Documentación pública en el README y wiki |
| Actividad reciente | Obligatoria | Release v0.11.9 del 12.MAY.2026 |

{: .important }
> El integrante Gabriel Quispe Mamani realizó la validación del entorno local de AppFlowy-Cloud, confirmando que el proyecto compila y se levanta correctamente con Docker Compose en su equipo. Esto garantiza que el equipo puede iniciar el Sprint 1 sin bloqueadores técnicos.

## 4. Alcance del proyecto

Durante el semestre 2026-A, el equipo:

1. **Analizará** el estado actual de AppFlowy-Cloud, identificando sus módulos principales y arquitectura.
2. **Aplicará el marco Scrum** mediante GitHub Projects, organizando el trabajo en Sprints de aproximadamente 15 días.
3. **Implementará prácticas DevOps** usando GitHub Actions para automatizar pruebas, construcción y despliegue continuo (CI/CD).
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

El proyecto seguirá un modelo **Scrum + DevOps**:

- **Scrum** estructura el trabajo en Sprints, Product Backlog, Sprint Backlog y revisiones.
- **DevOps** automatiza las fases de integración y entrega continua a través de pipelines en GitHub Actions, asegurando calidad y rapidez de retroalimentación.

## 7. Entregables por hito

| Hito | Fecha | Entregables |
|:---|:---|:---|
| Hito 1 | 13.MAY.2026 | Plan de proyecto, cronograma, presentación del producto seleccionado, GitHub Project, GitHub Pages |
| Hito 2 | 10.JUN.2026 | Producto funcionando con CI/CD, Scrum implementado (Sprints 1–2) |
| Hito 3 | 13.JUL.2026 | Mejoras al producto con despliegue automatizado, documentación técnica completa, artículo IEEE |

Ver detalle en [Cronograma](cronograma.html).
