# RISKS.md — IDENTIDAD DE MARCA

> Owner: Jose Aguilar — Fecha: 12/05/26

| # | Riesgo | Probabilidad | Impacto | Mitigacion |
|---|---|---|---|---|
| R1 | Tesseract eng pierde precision en acentos y n-tilde | Alta | Medio | Marcar con comentario OCR: revisar para revision humana |
| R2 | PDFs grandes (326MB, 110MB) lentos en OCR | Media | Bajo | Procesar por pagina, solo las que fallan pdftotext |
| R3 | Contenido de PDF vectorizado sin texto extraible | Media | Alto | pdftoppm + tesseract como fallback, reportar si < 200 chars totales |
| R4 | PDFs originales modificados o reemplazados | Baja | Alto | No tocar PDFs originales. Solo lectura. |
| R5 | Informacion de marca desactualizada en los PDFs | Media | Medio | Versionar con fecha_extraccion en front-matter YAML |
| R6 | Duplicar info ya en context_design.md | Media | Bajo | Regla: referenciar context_design.md, no duplicar tokens globales |
| R7 | Proyecto paralizado sin go-ahead de Fase 1 | Alta (actual) | Medio | Esperando arranque. Fase 0 completa. Sin accion hasta confirmacion. |
