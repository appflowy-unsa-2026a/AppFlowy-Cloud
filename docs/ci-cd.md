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
> Durante el Hito 3 (Sprints 3 y 4) el pipeline evolucionó de CI a CD: se añadió un segundo workflow que construye y publica la imagen Docker del backend en GitHub Container Registry y la deja disponible para despliegue. Se documenta a continuación.

## Métricas DORA aplicadas

El equipo realiza seguimiento informal de las cuatro métricas DORA en el contexto académico:

| Métrica | Objetivo del Hito 3 | Observación al cierre del Hito 2 |
|:---|:---|:---|
| Frecuencia de despliegue | ≥ 1 por Sprint | Pipeline configurado, despliegue automatizado pendiente |
| Tiempo de entrega de cambios | < 24 horas | 26 segundos desde push hasta éxito |
| Tasa de fallo de cambio | < 15 % | 1 falla en 5 runs por falso positivo (corregida) |
| Tiempo medio de recuperación | < 2 horas | Corrección desplegada en 3 minutos |

## Pipeline de Entrega Continua (CD) — Hito 3

Durante el Sprint 3 el equipo implementó un segundo workflow, [`cd-equipo-ips.yml`](https://github.com/appflowy-unsa-2026a/AppFlowy-Cloud/blob/main/.github/workflows/cd-equipo-ips.yml), que lleva el proceso DevOps de la Integración Continua a la **Entrega Continua**. Se ejecuta en cada push a `main`, en cada tag `v*`, en pull requests (solo build, sin publicar) y de forma manual (`workflow_dispatch`).

### Etapas del pipeline CD

#### 1. Puerta de calidad de código Rust

Ejecuta `cargo fmt --all -- --check` sobre todo el workspace. Es una verificación rápida que no requiere compilar el proyecto y garantiza que el código respeta el formato definido en `rustfmt.toml` antes de invertir tiempo en la construcción de la imagen.

#### 2. Construcción y publicación de la imagen Docker

Reutiliza el `Dockerfile` del proyecto —basado en `cargo-chef` para cachear la compilación de Rust— y publica la imagen resultante en **GitHub Container Registry**:

```
ghcr.io/appflowy-unsa-2026a/appflowy-cloud:latest
ghcr.io/appflowy-unsa-2026a/appflowy-cloud:sha-<commit>
```

Aspectos clave de esta etapa:

- **Caché de capas** (`cache-from`/`cache-to: type=gha`): el primer build en modo *release* es costoso, pero los sucesivos reutilizan las capas compiladas y se completan en minutos.
- **Etiquetado automático** con [`docker/metadata-action`](https://github.com/docker/metadata-action): `latest` para la rama principal, la versión semántica para los tags y el hash corto del commit para trazabilidad.
- **Liberación de disco** del runner antes del build para acomodar los artefactos de compilación de Rust.
- En pull requests la imagen se **construye pero no se publica**, validando que el `Dockerfile` sigue compilando sin exponer paquetes desde ramas no fusionadas.

#### 3. Despliegue a staging

Como el proyecto es académico y no dispone de un servidor propio, el **entorno de staging es la propia imagen publicada en GHCR**. La etapa emite las instrucciones de despliegue reproducibles:

```bash
docker pull ghcr.io/appflowy-unsa-2026a/appflowy-cloud:latest
docker run -d -p 8000:8000 --env-file deploy.env \
  ghcr.io/appflowy-unsa-2026a/appflowy-cloud:latest
```

Cualquier integrante del equipo o el docente puede desplegar el backend a partir de la imagen versionada, cerrando el ciclo CI/CD de extremo a extremo.

### Mejora al producto: healthcheck de la imagen

Como mejora concreta del Sprint 3, se incorporó una instrucción `HEALTHCHECK` en el `Dockerfile`. La imagen publicada se autodiagnostica consultando periódicamente el endpoint `/api/health` del backend, de modo que Docker la reporta como *healthy* o *unhealthy* en cualquier entorno —incluido un despliegue con `docker run` aislado— sin depender de la configuración externa de `docker-compose`. Es una mejora de observabilidad del artefacto desplegable, alineada con las prácticas DevOps del curso.

### Métricas DORA al cierre del Hito 3

| Métrica | Objetivo | Resultado al cierre del Hito 3 |
|:---|:---|:---|
| Frecuencia de despliegue | ≥ 1 por Sprint | Imagen publicada automáticamente en cada push a `main` |
| Tiempo de entrega de cambios | < 24 horas | De push a imagen publicada en minutos (con caché tibia) |
| Tasa de fallo de cambio | < 15 % | Puerta de formato + build en PR previenen fallos en `main` |
| Tiempo medio de recuperación | < 2 horas | *Rollback* inmediato reetiquetando una imagen `sha-<commit>` previa |
