# IDENTIDAD DE MARCA — Memoria de Agente

> Memoria persistente para trabajo de extracción y estructuración del sistema de marcas Grupo Ortiz. Lee esto antes de actuar sobre la carpeta.

---

## Propósito de la carpeta

`IDENTIDAD DE MARCA/` es la fuente única de verdad visual de Grupo Ortiz y sus sub-marcas. Se adjunta como contexto a proyectos de diseño (PDFs, reportes, presentaciones, web, packaging, email).

Archivos clave:
- `context_design.md` → sistema GO maestro (paleta, tipografía, tokens CSS, reglas globales). 584 líneas.
- `guias y manuales/` → manuales originales en PDF + carpeta `markdowns/` con extracciones estructuradas.
- `01_LOGO/` `02_TIPOGRAFIA/` `03_PALETA DE COLORES/` `04_ELEMENTOS GRAFICOS/` `05_GUIAS DE MARCA/` → assets físicos.

---

## Inventario de marcas (6 PDFs)

| Slug archivo MD | Marca real | PDF fuente | Páginas | Tamaño | Texto extraíble |
|---|---|---|---|---|---|
| `go.md` | Grupo Ortiz (madre) | `MANUAL DE MARCA_GO_V3 2.pdf` | 14 | 326 MB | Mixto — pdftotext OK en pgs 3-9, OCR necesario en covers/titulares |
| `pm.md` | Plaza Madero | `BRANDBOOK PM.pdf` | 13 | 109 MB | Bajo — texto convertido a paths, OCR obligatorio |
| `hpg.md` | HPG | `Manual de marca HPG.pdf` | 11 | 110 MB | Bajo — OCR obligatorio (paleta + tipo extrae OK) |
| `loly.md` | Loly Gummies | `MANUAL DE MARCA_LOLY.pdf` | 10 | 5.5 MB | Alto — pdftotext extrae bien |
| `ichigo.md` | Ichigo (Agencia Creativa) | `Ichigo - Manual de identidad.pdf` | 6 | 1.6 MB | Medio — pdftotext + OCR complementario |
| `todo-pal-negocio.md` | Todo Pal Negocio® | `Manual de identidad.pdf` | 11 | 15.7 MB | Bajo — texto en paths, OCR obligatorio |

Total = **65 páginas**.

---

## Decisiones del proyecto (confirmadas con usuario 2026-04-25)

1. Idioma de salida: **español**.
2. Slugs: **minúscula**, formato `kebab-case` cuando aplica multipalabra.
3. PDFs digitales — si encuentro escaneo, salto y reporto.
4. Maestro orquestador: **`brand_system.md`** (NO `INDEX.md`).
5. Marca #5 confirmada vía OCR: **Todo Pal Negocio**.

---

## Capacidades del sandbox (Fase 0 verificada 2026-04-25)

- `pdftotext` (poppler 22.02) ✅
- `pdfinfo` ✅
- `pdfimages` ✅
- `pdftoppm` ✅ — render rápido (~0.15s/pg @120dpi, ~0.6s/pg @200dpi)
- `tesseract` 4.1.1 ✅ — **solo idioma `eng`**; no hay permisos de `apt`/`sudo` para instalar `spa`. La descarga de `spa.traineddata` desde GitHub falló (curl 56 / red restringida). El modelo `eng` rinde aceptable con español de titulares; pierde precisión en acentos y `ñ`.
- `pymupdf` (fitz) ✅ — útil para texto-por-página + conteo imágenes.
- `convert` (ImageMagick) ✅.
- Sin acceso root. Sin `apt install`. Sin descarga libre desde `raw.githubusercontent.com`.

Pipeline elegido para extracción:
1. `pdftotext -layout` por PDF (texto real cuando existe).
2. Para páginas con `<100 chars` extraídos: `pdftoppm -r 200` + `tesseract eng` (rellena titulares y texto vectorizado).
3. Combinar + estructurar manualmente al esqueleto MD.

---

## Estructura objetivo

```
guias y manuales/
├── *.pdf                          (fuentes originales — no tocar)
└── markdowns/
    ├── brand_system.md            ← maestro orquestador (Fase 3)
    ├── go.md                      ← Grupo Ortiz
    ├── pm.md                      ← Plaza Madero
    ├── hpg.md                     ← HPG
    ├── loly.md                    ← Loly Gummies
    ├── ichigo.md                  ← Ichigo (Agencia Creativa)
    ├── todo-pal-negocio.md        ← Todo Pal Negocio
    └── _raw/                      ← (opcional) extracciones crudas para auditoría
        └── {slug}.txt
```

Esqueleto fijo de cada `{marca}.md`:

```
# {Marca} — Manual de Marca
## 1. Esencia & Posicionamiento
## 2. Logo (versiones, usos, mínimos, áreas seguridad)
## 3. Paleta de colores (hex + RGB + CMYK + Pantone + uso)
## 4. Tipografía (familia + jerarquía + fallback)
## 5. Elementos gráficos / patrones
## 6. Tono & Voz
## 7. Aplicaciones (papelería, redes, packaging, web)
## 8. Restricciones / NO hacer
## 9. Tokens CSS sugeridos
## 10. Checklist de uso (para IA/agente)
```

Front-matter YAML por archivo:
```yaml
---
marca: "<nombre>"
slug: "<slug>"
fuente_pdf: "<archivo.pdf>"
paginas_fuente: <int>
version: "1.0"
fecha_extraccion: "YYYY-MM-DD"
aplica_a: ["pdf","reporte","presentacion","web","email","packaging"]
---
```

---

## Fases del plan

| Fase | Estado | Descripción |
|---|---|---|
| 0 | ✅ COMPLETA (2026-04-25) | Probe tools + inventario + confirmar marcas |
| 1 | ⏸️ Esperando go | Extracción texto + OCR de los 6 PDFs → `markdowns/_raw/` |
| 2 | ⏸️ | Generar 6 archivos `{slug}.md` con esqueleto unificado |
| 3 | ⏸️ | Generar `brand_system.md` maestro |
| 4 | ⏸️ | Validar links cruzados + front-matter |
| 5 | ⏸️ | Hookear `brand_system.md` desde `context_design.md` |

---

## Reglas para el agente cuando trabaje sobre esta carpeta

1. **No tocar** los PDFs originales. Sólo lectura.
2. **No duplicar** info que ya viva en `context_design.md` — referenciarlo.
3. **Tokens CSS**: cada marca debe exponer su propio set de variables (`--{marca}-primary`, etc.) que conviven con `--go-*` del sistema madre.
4. **Orden de precedencia** cuando un proyecto necesite saber qué marca aplicar:
   1. Si el proyecto pertenece a una sub-marca específica → su `{slug}.md` manda.
   2. Reglas globales (typo escala, modo oscuro, márgenes PDF) → vienen de `context_design.md`.
   3. Conflictos de paleta → la sub-marca gana **dentro de su producto**; GO gana en cabeceras corporativas y firmas.
5. **OCR limitations**: si encuentras texto sospechoso (acentos faltantes, `ñ`→`n`, palabras cortadas), márcalo `<!-- OCR: revisar -->` en el MD para que el humano valide.
6. **Imágenes**: extraer assets clave (logos, paletas) sólo si el usuario lo pide explícitamente. Por defecto sólo texto+estructura.

---

## 🔁 Handoff al próximo agente (LEE PRIMERO)

**Estado actual: Fase 0 ✅ completa. Esperando arrancar Fase 1.**

Si el usuario te pide "continuar", "seguir con identidad de marca", "fase 1" o equivalente — esto es lo que sigue:

### Fase 1 — Extracción texto + OCR (ejecutable directo)

```bash
# 1. Crear carpetas de trabajo
mkdir -p "/sessions/<sesion>/mnt/IDENTIDAD DE MARCA/guias y manuales/markdowns/_raw"

# 2. Loop por los 6 PDFs — extracción texto real
cd "/sessions/<sesion>/mnt/IDENTIDAD DE MARCA/guias y manuales/"
declare -A MAP=(
  ["MANUAL DE MARCA_GO_V3 2.pdf"]="go"
  ["BRANDBOOK PM.pdf"]="pm"
  ["Manual de marca HPG.pdf"]="hpg"
  ["MANUAL DE MARCA_LOLY.pdf"]="loly"
  ["Ichigo - Manual de identidad.pdf"]="ichigo"
  ["Manual de identidad.pdf"]="todo-pal-negocio"
)
for pdf in "${!MAP[@]}"; do
  slug="${MAP[$pdf]}"
  pdftotext -layout "$pdf" "markdowns/_raw/${slug}.txt"
done

# 3. Para páginas con texto < 100 chars, render + OCR
#    (script Python con pymupdf detecta páginas pobres y OCR sólo esas)
```

### Comandos de probe ya validados (Fase 0)

- `pdftoppm -r 200 -f N -l N "$pdf" /tmp/probe/p -png` (render página N)
- `tesseract /tmp/probe/p-1.png - 2>/dev/null` (OCR — solo `eng` disponible)
- `pdftotext -layout "$pdf" -` (texto plano respetando layout)
- Python `fitz` (`pymupdf`) — `page.get_text()` y `page.get_images(full=True)`

### Output esperado de Fase 1

```
markdowns/_raw/
├── go.txt
├── pm.txt
├── hpg.txt
├── loly.txt
├── ichigo.txt
└── todo-pal-negocio.txt
```

Cada `.txt` debe contener:
- bloque `=== PAGE N (pdftotext) ===` con texto real
- bloque `=== PAGE N (OCR fallback) ===` cuando se haya OCRizado

### Validación antes de pasar a Fase 2
- Verificar que cada `.txt` contenga al menos: nombre de marca, ≥1 código hex, ≥1 nombre de tipografía.
- Si algún PDF da `< 200 chars` totales tras OCR → reportar como "extracción insuficiente, requiere revisión humana".

### NO hacer en Fase 1
- No estructurar todavía al esqueleto MD (eso es Fase 2).
- No tocar `brand_system.md` (Fase 3).
- No modificar `context_design.md`.

---

## Última actualización
2026-04-25 — Fase 0 completada + handoff listo para Fase 1.
