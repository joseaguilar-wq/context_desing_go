# CHANGELOG — IDENTIDAD DE MARCA

> Registro de cambios por sesion.

## 2026-08-28 — El favicon pierde el fondo (regla nueva del departamento)

Directiva de Jose: **el favicon son las hojas naranjas y nada mas.** Se deroga la
regla del 27/08, que componia el isotipo al 66% sobre el negro de marca `#262626`
en un squircle. Aplica a TODOS los favicons del departamento.

Cambios en `scripts/generate_favicon_go.py`:

- Fuera la placa y el radio. El lienzo queda transparente.
- La marca pasa del 66% al **100% del ancho**. Sin placa no hay borde del que
  alejarse, y ese 34% se pagaba en legibilidad: a 16 px el icono pasa de 59 a 100
  pixeles con tinta, y la hoja de contorno solo se lee con los segundos.
- Se ajusta por el lado que limita (ancho o alto), no siempre por el ancho, para que
  un isotipo vertical no se desborde si un dia cambia el asset.

Dos defectos de imagen encontrados al verificar, no al escribir:

- **RGB negro en pixeles visibles.** `Image.resize` sobre RGBA premultiplica —bien,
  no deja halo— pero luego no puede des-premultiplicar donde el alfa quedo bajo y
  escribe negro ahi. Medido en el favicon de 32 px: **201 de 469 pixeles con alfa>0**
  salian negruzcos (alfa 1..7). Como la marca es de un solo color, la forma vive
  entera en el alfa: se toma el alfa reescalado y se pinta la tinta plana encima.
- **El `.ico` no se arreglaba solo.** `IcoImagePlugin._save` reescala por dentro
  (`frame.thumbnail`) cada tamano que no reciba ya hecho. Los cuadros de 16 y 32
  salian con desvio 152 aunque el de 48 estuviera limpio — y no se veia midiendo el
  archivo, porque `Image.open(.ico)` devuelve solo el cuadro mayor. Ahora se le
  entregan los tres por `append_images`.

Verificado: en los 11 archivos y en los 3 cuadros del `.ico`, esquinas con alfa 0 y
desvio de color **0** contra `#FB670B` en todo pixel visible.

Nota de plataforma: iOS no respeta la transparencia en `apple-touch-icon`, la compone
sobre negro. El resultado es la marca sobre negro, que es la marca. Se emite sin
fondo igual.

## 2026-08-27 — Favicon corporativo GO

Directiva de Jose: el favicon GO (isotipo naranja `#FB670B` sobre negro de marca
`#262626`, cuadrado redondeado) pasa a ser el default del 100% de los proyectos de
IA. Excepcion: unidades de negocio con marca propia (TPN, TPC, sub-marcas).

### Agregado
- `01_LOGO/favicon_go/` — set completo generado desde `ISOTIPO_GO_NARANJA.png`:
  `favicon.ico` (16/32/48), PNG 16→512, `apple-touch-icon.png`, `icon-192/512`.
- Seccion 4 "Favicon corporativo — REGLA DURA" en `context_design.md`, con el
  snippet HTML y el porque de NO usar SVG.

### Corregido
- La regla "Fondo del icono en UI" decia `#F97316`, que **no es** el naranja de la
  marca (el oficial, en la seccion 2 del mismo archivo, es `#FB670B`). Era una
  contradiccion dentro de la propia fuente de verdad visual.

---

## 2026-05-22

- UPDATED: `guias y manuales/markdowns/ui_shell_component.md` v1.0 → v1.1
  - Sidebar promovido a componente plug-and-play reciclable 100%
  - Agregada documentacion completa del boton plegar/expandir (`.sidebar-collapse-btn`)
  - SVG icon catalog ampliado (11 iconos base: grid, box, clipboard, truck, shield, target, star, chart, play, chat, gear)
  - JS API publico expuesto via `window.GoShell` (renderSidebar, applyState, bindToggles, bindNav, toggleSidebar)
  - Bloques CSS y JS copy-paste-ready (secciones 4 y 5)
  - Tests de aceptacion (10 items) + checklist accesibilidad WCAG AA
  - Tabla customizacion permitida vs prohibida (mantener consistencia cross-proyecto)
  - Procedimiento adopcion (9 pasos)
  - Verificado en `ventas_rafias_go` v1.1 (con boton plegar funcional + zero "Fase 7 Pilot" footer)
- REF: el shell ya no es solo "semilla", es estandar Grupo Ortiz aplicable a cualquier app web

---

## 2026-05-12

- CREATED: BACKLOG.md (fases 1-5 pendientes)
- CREATED: RISKS.md (7 riesgos del proyecto)
- CREATED: avances_diarios.md (template con sesion 2026-04-25)
- CREATED: MVP_BREAKDOWN.md (11 entregables, 9% MVP)
- CREATED: CHANGELOG.md

## 2026-04-25

- Fase 0 completada
- Tools validadas en sandbox: pdftotext, tesseract, pymupdf, pdftoppm, convert
- 6 PDFs inventariados y mapeados a slugs
- Decisiones de proyecto confirmadas con usuario
- Handoff listo para Fase 1
