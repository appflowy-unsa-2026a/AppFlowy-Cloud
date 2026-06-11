---
title: Sprints
eyebrow: Documentación · Scrum
description: Retrospectiva de cada Sprint del proyecto. Trabajo realizado, lecciones aprendidas y entregables verificados.
permalink: /sprints/
---

Esta página recoge el estado de cada Sprint del proyecto a medida que avanza, con foco en las entregas verificables y las lecciones aprendidas por el equipo.

## Sprint 0 — Planificación
{: .d-inline-block }

✓ Cerrado
{: .badge .badge--green }

**Período:** hasta 16.MAY.2026
**Líder:** Huaynacho Mango, Jerry Anderson

### Trabajo realizado

- Selección y justificación de AppFlowy-Cloud como producto de trabajo.
- Creación de la Organization `appflowy-unsa-2026a` en GitHub e invitación a los cuatro integrantes.
- Fork del repositorio oficial AppFlowy-IO/AppFlowy-Cloud.
- Configuración del tablero Scrum en GitHub Projects.
- Activación de GitHub Pages y publicación de la documentación inicial.
- Definición del Product Backlog con seis Issues iniciales.
- Spike técnico: validación del entorno local por Quispe Mamani, José Gabriel.

### Lecciones aprendidas

- La planificación temprana del Product Backlog redujo los bloqueadores en el inicio del Sprint 1.
- La validación previa del entorno con Docker Compose evitó sorpresas técnicas posteriores.

---

## Sprint 1 — Análisis y configuración DevOps inicial
{: .d-inline-block }

✓ Cerrado
{: .badge .badge--green }

**Período:** 17.MAY – 27.MAY.2026
**Líder:** Mendoza Contreras, Giovani Angel

### Trabajo realizado

- Análisis arquitectónico completo de AppFlowy-Cloud (Issue [#2](https://github.com/appflowy-unsa-2026a/AppFlowy-Cloud/issues/2)).
- Identificación de los cinco módulos funcionales: Documentos, Databases, Kanban, AI y Templates.
- Mapeo de los servicios del backend: API en Rust, PostgreSQL con pgvector, Redis, GoTrue, MinIO y nginx.
- Levantamiento del entorno local con Docker Compose (Issue [#3](https://github.com/appflowy-unsa-2026a/AppFlowy-Cloud/issues/3)).
- Once servicios orquestados correctamente, diez de ellos en estado *healthy*.

### Indicadores Scrum

| Métrica | Valor |
|:---|:---|
| Issues cerrados | 2 de 4 planificados |
| Story points completados | 9 de 20 |
| Velocity del Sprint | 9 puntos |

### Lecciones aprendidas

- Comprender la arquitectura antes de tocar código aceleró la implementación posterior del pipeline CI.
- El tamaño del Sprint 1 fue ligeramente sobreestimado; se reasignó carga al Sprint 2.

---

## Sprint 2 — CI/CD funcionando · Hito 2
{: .d-inline-block }

✓ Cerrado
{: .badge .badge--green }

**Período:** 28.MAY – 10.JUN.2026
**Líder:** Ticona Saure, José María

### Trabajo realizado

- Configuración del pipeline CI propio del equipo en GitHub Actions (Issue [#4](https://github.com/appflowy-unsa-2026a/AppFlowy-Cloud/issues/4)).
- Workflow `ci-equipo-ips.yml` con cinco jobs: docs, docker-compose, YAML, seguridad y resumen.
- Primer run exitoso del pipeline ([ver run](https://github.com/appflowy-unsa-2026a/AppFlowy-Cloud/actions/runs/27365922005)).
- Validación del flujo de registro de usuarios sobre la API GoTrue (Issue [#5](https://github.com/appflowy-unsa-2026a/AppFlowy-Cloud/issues/5)).
- Documentación del proceso CI/CD en la sección [CI/CD]({{ '/ci-cd/' | relative_url }}) del sitio.

### Indicadores Scrum

| Métrica | Valor |
|:---|:---|
| Issues cerrados | 3 de 3 planificados |
| Story points completados | 18 de 15 (incluye carga del Sprint 1) |
| Velocity del Sprint | 18 puntos |

### Burndown de Sprints 1 y 2

[Ver gráfico burndown en el informe Hito 2]

### Lecciones aprendidas

- Importar la idea de "spike" desde el inicio del proyecto facilitó superar los pequeños retrasos del Sprint 1.
- El pipeline CI propio permitió descubrir falsos positivos en validaciones de seguridad y corregirlos en tiempo real.

---

## Sprint 3 — Mejoras y refactorización
{: .d-inline-block }

Pendiente
{: .badge .badge--gray }

**Período previsto:** 11.JUN – 26.JUN.2026
**Líder:** Quispe Mamani, José Gabriel

---

## Sprint 4 — Cierre y artículo IEEE
{: .d-inline-block }

Pendiente
{: .badge .badge--gray }

**Período previsto:** 27.JUN – 13.JUL.2026
**Líder:** Huaynacho Mango, Jerry Anderson
