# BACKLOG — IDENTIDAD DE MARCA

## Pendientes activos

### Fase 1 — Extraccion de texto + OCR
1. Ejecutar pdftotext -layout en los 6 PDFs -> markdowns/_raw/
2. OCR con tesseract eng en paginas con <100 chars extraidos
3. Generar: go.txt, pm.txt, hpg.txt, loly.txt, ichigo.txt, todo-pal-negocio.txt

### Fase 2 — Generar archivos MD por marca
4. go.md — Grupo Ortiz (14 pags, 326MB, pdftotext + OCR parcial)
5. pm.md — Plaza Madero (13 pags, 109MB, OCR obligatorio)
6. hpg.md — HPG (11 pags, 110MB, OCR obligatorio)
7. loly.md — Loly Gummies (10 pags, 5.5MB, pdftotext OK)
8. ichigo.md — Ichigo Agencia Creativa (6 pags, 1.6MB, pdftotext + OCR)
9. todo-pal-negocio.md — Todo Pal Negocio (11 pags, 15.7MB, OCR obligatorio)

### Fase 3 — Maestro orquestador
10. Generar brand_system.md con links cruzados a los 6 archivos MD

### Fase 4 — Validacion
11. Verificar links cruzados y front-matter YAML en cada MD
12. Confirmar tokens CSS por marca (--{marca}-primary, etc.)

### Fase 5 — Hookear con context_design.md
13. Agregar referencias a brand_system.md desde context_design.md

## Completado

- Fase 0 (2026-04-25): Inventario 6 PDFs + confirmacion marcas + validacion tools (pdftotext, tesseract, pymupdf, pdftoppm)
