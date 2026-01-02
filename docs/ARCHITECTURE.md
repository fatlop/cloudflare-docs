# ARCHITECTURE - Estado actual y pauta mínima de evolución

## Propósito del repositorio

Este repositorio contiene la documentación y artefactos relacionados con nuestro proyecto orgánico (Etheos / HoloMeta). En su estado actual predomina contenido estático (Astro + MDX) y existe una carpeta 'worker' para lógica en el borde.

## Mapa ligero de responsabilidades

- **core**: código de infraestructura crítica (cuando exista) y adaptadores a motores/renderer.
- **ui**: componentes de interfaz, MDX y presentaciones.
- **assets**: modelos 3D, texturas y recursos pesados. Recomendado: externalizar a Cloudflare R2/S3 y mantener referencias en el repo.
- **worker**: código edge / APIs (Cloudflare Workers). Mantener claramente separado de runtime del metaverso.

## Política mínima de ramas

- Nunca trabajar directo en production o main. Usar ramas: **ops/*** para tareas operativas, **feature/*** para nuevas funcionalidades.

## Política de dependencias y cambios

- Ninguna actualización automática de dependencias sin PR y revisión. Mantener auditoría de dependencias como paso obligatorio en CI.

## Actuaciones inmediatas (prioridad baja/mediana)

1. Ejecutar auditoría de dependencias (npm audit) y revisar vulnerabilidades.
2. Externalizar assets pesados fuera de git (R2/S3) si existen.
3. Añadir CI mínima que valide build/lint/test y genere reporte de auditoría.

## Comentarios sobre identidad del proyecto

Estas recomendaciones buscan ordenar el repositorio sin imponer una arquitectura rígida. Se respeta el crecimiento orgánico: las secciones y decisiones que ya existen se documentarán y clarificarán antes de mover o reubicar artefactos.
