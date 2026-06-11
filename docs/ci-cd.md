---
title: CI/CD Pipeline
eyebrow: Documentación · DevOps
description: Pipeline de Integración Continua del equipo IPS 2026-A, implementado con GitHub Actions sobre el fork de AppFlowy-Cloud.
permalink: /ci-cd/
---

Esta página describe el pipeline de Integración Continua propio del equipo, diseñado para validar la integridad del repositorio en cada cambio. Forma parte del entregable del **Hito 2** del curso y materializa las prácticas DevOps acordadas en el marco teórico del proyecto.

## Arquitectura del pipeline

El workflow [`ci-equipo-ips.yml`](https://github.com/appflowy-unsa-2026a/AppFlowy-Cloud/blob/main/.github/workflows/ci-equipo-ips.yml) se ejecuta en tres situaciones:

1. **En cada push a la rama principal** (`main`).
2. **En cada pull request abierto contra `main`**.
3. **Manualmente** mediante el botón "Run workflow" de GitHub Actions (`workflow_dispatch`).

El pipeline está compuesto por cinco trabajos independientes que se ejecutan en paralelo y un trabajo final de resumen que depende de los anteriores.

## Trabajos (jobs) del pipeline

### 1. Validar documentación Markdown

Comprueba la presencia de los archivos clave de la documentación pública en la carpeta `docs/`:

- `docs/index.md`
- `docs/plan-proyecto.md`
- `docs/cronograma.md`
- `docs/equipo.md`

Falla si falta cualquiera de estos documentos, garantizando que la documentación pública siempre esté disponible para el docente y para los revisores del proyecto.

### 2. Validar docker-compose.yml

Copia el archivo `deploy.env` a `.env` y ejecuta:

```bash
docker compose config --quiet
```

Este comando interpreta el archivo `docker-compose.yml` y reporta errores de sintaxis, de variables faltantes o de servicios mal definidos. Si pasa, se listan los servicios para que cualquier integrante pueda verificar el alcance del despliegue.

### 3. Validar workflows YAML

Instala `yamllint` y revisa la sintaxis del propio workflow, previniendo errores de formato que romperían silenciosamente el pipeline.

### 4. Inspección de seguridad

Realiza dos verificaciones:

- **Búsqueda de secretos accidentalmente versionados:** patrones de claves RSA, claves de OpenAI y claves de AWS.
- **Confirmación de que el archivo `.env` real no está versionado** (debe estar listado en `.gitignore`).

Una falla en este trabajo bloquea la integración para proteger los datos sensibles del proyecto.

### 5. Resumen del pipeline

Se ejecuta siempre (incluso si los anteriores fallan) y produce un reporte consolidado con el resultado de cada trabajo. Sirve como evidencia ejecutiva para las revisiones de Sprint Review.

## Resultados verificables

El pipeline ha ejecutado exitosamente desde su configuración. La última ejecución pública verificable es:

| Aspecto | Valor |
|:---|:---|
| Estado | Success |
| Duración total | 26 segundos |
| Jobs ejecutados | 5 de 5 |
| Triggered by | push del commit `cd4fe09` |
| Run completo | [Ver en GitHub Actions](https://github.com/appflowy-unsa-2026a/AppFlowy-Cloud/actions/runs/27365922005) |

{: .callout .callout--note }
> El pipeline está pensado para evolucionar en los Sprints 3 y 4 incorporando *build* y *tests* del backend en Rust, generación y publicación de la imagen Docker en GitHub Container Registry, y despliegue automatizado al entorno de staging.

## Métricas DORA aplicadas

El equipo realiza seguimiento informal de las cuatro métricas DORA en el contexto académico:

| Métrica | Objetivo del Hito 3 | Observación al cierre del Hito 2 |
|:---|:---|:---|
| Frecuencia de despliegue | ≥ 1 por Sprint | Pipeline configurado, despliegue automatizado pendiente |
| Tiempo de entrega de cambios | < 24 horas | 26 segundos desde push hasta éxito |
| Tasa de fallo de cambio | < 15 % | 1 falla en 5 runs por falso positivo (corregida) |
| Tiempo medio de recuperación | < 2 horas | Corrección desplegada en 3 minutos |

## Próximos pasos del pipeline

Durante el Sprint 3 se ampliará el pipeline para incorporar:

1. Compilación incremental del backend en Rust (`cargo build`).
2. Ejecución de la suite de pruebas (`cargo test`).
3. Análisis estático con `clippy` y formato con `rustfmt`.
4. Construcción y publicación de la imagen Docker en GitHub Container Registry.
5. Despliegue automatizado al entorno de staging mediante GitHub Pages o servicios equivalentes.
