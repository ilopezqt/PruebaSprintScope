# Roadmap — Product Recommender System

## F1 — Research & Definición

- [x] REC-01 | Kick-off y definición de alcance | est:4h | area:producto | type:meeting | assigned:todos | depends:[]
- [x] REC-02 | Análisis exploratorio del dataset | est:8h | area:research | type:research | assigned:Persona2 | depends:[REC-01]
- [x] REC-03 | Spec técnica del sistema de recomendación | est:6h | area:producto | type:product | assigned:Persona1 | depends:[REC-02]
- [x] REC-04 | Diseño de la arquitectura del modelo | est:4h | area:code | type:code | assigned:Persona1 | depends:[REC-03]
- [x] REC-05 | Investigación de algoritmos de recomendación | est:6h | area:research | type:research | assigned:Persona2 | depends:[REC-02]

## F2 — Desarrollo & Diseño

- [ ] REC-06 | Pipeline de limpieza y preprocesado de datos | est:8h | area:code | type:code | assigned:Persona4 | depends:[REC-05]
  - [ ] REC-06a | Limpieza de datos nulos y outliers | est:3h | area:code | type:code | assigned:Persona4 | depends:[]
  - [ ] REC-06b | Feature engineering | est:3h | area:code | type:code | assigned:Persona4 | depends:[REC-06a]
  - [ ] REC-06c | Validación del pipeline con tests | est:2h | area:code | type:code | assigned:Persona1 | depends:[REC-06b]
- [ ] REC-07 | Entrenamiento del modelo colaborativo | est:10h | area:code | type:code | assigned:Persona1 | depends:[REC-06]
  - [ ] REC-07a | Implementar matrix factorization | est:4h | area:code | type:code | assigned:Persona1 | depends:[]
  - [ ] REC-07b | Implementar content-based filtering | est:4h | area:code | type:code | assigned:Persona4 | depends:[]
  - [ ] REC-07c | Evaluación y comparación de modelos | est:2h | area:research | type:research | assigned:Persona2 | depends:[REC-07a,REC-07b]
- [ ] REC-08 | API REST de predicciones | est:6h | area:code | type:code | assigned:Persona1 | depends:[REC-07]
- [ ] REC-09 | Diseño del dashboard de métricas | est:8h | area:diseño | type:design | assigned:Persona3 | depends:[REC-03]
  - [ ] REC-09a | Wireframes y flujo de usuario | est:3h | area:diseño | type:design | assigned:Persona3 | depends:[]
  - [ ] REC-09b | Diseño visual y componentes | est:3h | area:diseño | type:design | assigned:Persona3 | depends:[REC-09a]
  - [ ] REC-09c | Prototipo interactivo en Figma | est:2h | area:diseño | type:design | assigned:Persona3 | depends:[REC-09b]
- [ ] REC-10 | Implementación del dashboard | est:8h | area:code | type:code | assigned:Persona4 | depends:[REC-08,REC-09]
- [ ] REC-11 | Revisión de diseño con el cliente | est:2h | area:producto | type:meeting | assigned:todos | depends:[REC-09]

## F3 — Validación & Entrega

- [ ] REC-12 | Evaluación del modelo con datos reales | est:6h | area:research | type:research | assigned:Persona2 | depends:[REC-07]
  - [ ] REC-12a | Métricas de precisión y recall | est:2h | area:research | type:research | assigned:Persona2 | depends:[]
  - [ ] REC-12b | Test A/B con usuarios piloto | est:4h | area:research | type:research | assigned:Persona2 | depends:[REC-12a]
- [ ] REC-13 | Documentación técnica | est:4h | area:docs | type:docs | assigned:Persona3 | depends:[REC-08]
- [ ] REC-14 | Manual de usuario del dashboard | est:3h | area:docs | type:docs | assigned:Persona3 | depends:[REC-10]
- [ ] REC-15 | Reunión de validación final con el cliente | est:2h | area:producto | type:meeting | assigned:todos | depends:[REC-12,REC-10]
- [ ] REC-16 | Despliegue en producción | est:4h | area:code | type:code | assigned:Persona1 | depends:[REC-12,REC-13]
