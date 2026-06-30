---
project: "TaskFlow"
version: "1.0"
target_date: "2026-09-30"
description: "App colaborativa de gestión de tareas: tableros, tiempo real y asistente IA."
---

# Roadmap — TaskFlow

## F1 — Fundaciones

- [x] TF-01 | Kick-off y definición de alcance | est:4h | area:docs | type:meeting | assigned:todos | depends:[]
  Reunión inicial para acordar visión de producto, alcance del MVP y reparto de áreas
  entre el equipo. Salida: documento de alcance y backlog inicial priorizado.
- [x] TF-02 | Diseño del esquema de datos | est:8h | area:backend | type:product | assigned:ilopezqt | depends:[TF-01]
  Modelar usuarios, tableros, listas y tarjetas. Decidir relaciones y estrategia de
  migraciones. Hay que dejar el esquema preparado para colaboración en tiempo real.
- [x] TF-03 | Sistema de autenticación | est:10h | area:backend | type:code | assigned:ilopezqt | depends:[TF-02]
  Login con OAuth, sesiones y middleware de protección de rutas. Base sobre la que se
  apoyan todos los permisos del producto.
  - [x] TF-03a | Proveedor OAuth y callback | est:4h | area:backend | type:code | assigned:ilopezqt | depends:[]
  - [x] TF-03b | Middleware de sesión | est:3h | area:backend | type:code | assigned:ilopezqt | depends:[TF-03a]
  - [ ] TF-03c | Roles y permisos por tablero | est:3h | area:backend | type:code | assigned:bgomezqt | depends:[TF-03b]
- [x] TF-04 | Sistema de diseño y componentes base | est:8h | area:frontend | type:design | assigned:tmunozqt | depends:[TF-01]
  Tokens de color, tipografía y componentes reutilizables (botón, input, modal, tarjeta).
  Define el lenguaje visual de toda la app.
- [ ] TF-05 | Infraestructura y despliegue | est:6h | area:infra | type:code | assigned:bgomezqt | depends:[TF-02]
  Pipeline de CI, entorno de staging y producción, base de datos gestionada y variables
  de entorno. Que un push a main despliegue solo.

## F2 — Producto

- [ ] TF-06 | Tableros y listas | est:10h | area:frontend | type:code | assigned:tmunozqt | depends:[TF-03,TF-04]
  La pantalla principal: crear tableros, columnas (listas) y moverse entre ellos.
  - [ ] TF-06a | CRUD de tableros | est:3h | area:frontend | type:code | assigned:tmunozqt | depends:[]
  - [ ] TF-06b | CRUD de listas dentro del tablero | est:3h | area:frontend | type:code | assigned:tmunozqt | depends:[TF-06a]
  - [ ] TF-06c | Reordenar listas | est:4h | area:frontend | type:code | assigned:ilopezqt | depends:[TF-06b]
- [ ] TF-07 | Tarjetas de tarea | est:12h | area:frontend | type:code | assigned:ilopezqt | depends:[TF-06]
  El corazón de la app: tarjetas con título, descripción, asignado y fecha.
  - [ ] TF-07a | Crear y editar tarjeta | est:4h | area:frontend | type:code | assigned:ilopezqt | depends:[]
  - [ ] TF-07b | Arrastrar tarjetas entre listas | est:5h | area:frontend | type:code | assigned:ilopezqt | depends:[TF-07a]
    El drag & drop entre columnas debe ser fluido y persistir el orden al instante.
  - [ ] TF-07c | Detalle de tarjeta en panel | est:3h | area:frontend | type:design | assigned:tmunozqt | depends:[TF-07a]
- [ ] TF-08 | Colaboración en tiempo real | est:14h | area:backend | type:code | assigned:bgomezqt | depends:[TF-05,TF-07]
  Que varios usuarios vean los cambios de los demás al instante mediante websockets.
  - [ ] TF-08a | Servidor de websockets | est:5h | area:backend | type:code | assigned:bgomezqt | depends:[]
  - [ ] TF-08b | Sincronización de tarjetas en vivo | est:5h | area:backend | type:code | assigned:bgomezqt | depends:[TF-08a]
  - [ ] TF-08c | Indicadores de presencia | est:4h | area:frontend | type:code | assigned:tmunozqt | depends:[TF-08b]
- [ ] TF-09 | Comentarios y menciones | est:8h | area:backend | type:code | assigned:ilopezqt | depends:[TF-07]
  Conversación por tarjeta con @menciones que notifican al mencionado.
- [ ] TF-10 | Investigación del asistente IA | est:6h | area:llm | type:research | assigned:bgomezqt | depends:[TF-07]
  Explorar cómo un asistente puede sugerir subtareas y resumir tableros. Comparar
  enfoques y coste. Salida: recomendación técnica.

## F3 — Inteligencia y entrega

- [ ] TF-11 | Asistente IA de tareas | est:12h | area:llm | type:code | assigned:bgomezqt | depends:[TF-09,TF-10]
  Generar subtareas a partir de una descripción y resumir la actividad de un tablero.
  - [ ] TF-11a | Generación de subtareas | est:5h | area:llm | type:code | assigned:bgomezqt | depends:[]
  - [ ] TF-11b | Resumen de tablero | est:4h | area:llm | type:code | assigned:bgomezqt | depends:[TF-11a]
  - [ ] TF-11c | Revisión y ajuste por el usuario | est:3h | area:frontend | type:design | assigned:tmunozqt | depends:[TF-11a]
- [ ] TF-12 | Métricas y dashboard | est:8h | area:data | type:code | assigned:ilopezqt | depends:[TF-08]
  Panel con tareas completadas por semana, carga por persona y tiempo de ciclo.
- [ ] TF-13 | Pruebas end-to-end | est:6h | area:testing | type:code | assigned:tmunozqt | depends:[TF-08,TF-09]
  Cubrir el recorrido crítico: login, crear tablero, mover tarjeta, comentar.
- [ ] TF-14 | Documentación de producto | est:4h | area:docs | type:docs | assigned:tmunozqt | depends:[TF-11]
  Guía de usuario y manual del asistente IA.
- [ ] TF-15 | Lanzamiento y validación con cliente | est:3h | area:docs | type:meeting | assigned:todos | depends:[TF-12,TF-13,TF-14]
  Demo final, recogida de feedback y plan de despliegue a producción.
