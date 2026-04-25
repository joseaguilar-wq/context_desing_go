---
tipo: "maestro-orquestador"
version: "1.0"
fecha: "2026-04-25"
mantenido_por: "Nexus GO"
cubre: ["go","pm","hpg","loly","ichigo","todo-pal-negocio"]
---

# Brand System — Grupo Ortiz & Sub-marcas

> **Este archivo es el punto de entrada para cualquier agente o diseñador.**  
> No duplica el sistema de diseño global — para tokens CSS, componentes UI, tablas, modos y assets, ver [`context_design.md`](../../context_design.md).  
> Este documento define quién es cada marca, cuándo se usa y cómo conviven.

---

## 1. Mapa del Portafolio

```
GRUPO ORTIZ® (marca madre)
│
├── go              → Grupo Ortiz (corporativo)
├── pm              → Plaza Madero (centro tecnológico)
├── hpg             → Hotel Punta Galería (hospitalidad)
├── loly            → Loly Gummies (consumo / salud)
├── ichigo          → Ichigo Agencia Creativa (servicios)
└── todo-pal-negocio → Todo Pal Negocio® (comercio / ofertas)
```

| Slug | Marca | Sector | Paleta dominante | Archivo |
|---|---|---|---|---|
| `go` | Grupo Ortiz | Corporativo | Naranja `#FB670B` + Gris `#262626` | [go.md](go.md) |
| `pm` | Plaza Madero | Retail tech | Dorado `#D6B78D` + Azul `#7C90E5` + Lima `#CCFF50` | [pm.md](pm.md) |
| `hpg` | Hotel Punta Galería | Hospitalidad | Verde oliva `#838c2f` + Arena `#e5e0d8` | [hpg.md](hpg.md) |
| `loly` | Loly Gummies | CPG / salud | Morado `#B02686` + Rosa `#EA9BD6` + Azul `#2E4EE0` | [loly.md](loly.md) |
| `ichigo` | Ichigo Agencia Creativa | Servicios creativos | Amarillo `#FFD72E` + Negro `#282828` | [ichigo.md](ichigo.md) |
| `todo-pal-negocio` | Todo Pal Negocio® | Comercio / ofertas | Rojo `#E2032C` + Amarillo `#FBBE27` | [todo-pal-negocio.md](todo-pal-negocio.md) |

---

## 2. Árbol de Decisión — ¿Qué marca aplicar?

Usa este árbol antes de comenzar cualquier pieza visual o comunicado.

```
¿Qué tipo de pieza es?
│
├── CORPORATIVA (inversiones, legal, corporativo, firmas, reportes internos)
│   └── → USA: go.md  +  context_design.md como base
│
├── PLAZA MADERO (centro comercial de tecnología, evento, señalética del lugar)
│   └── → USA: pm.md  (GO en pie de página como marca madre)
│
├── HOTEL PUNTA GALERÍA (hospedaje, amenidades, restaurante, spa)
│   └── → USA: hpg.md  (GO en pie de página como marca madre)
│
├── LOLY GUMMIES (producto, empaque, e-commerce, redes de producto)
│   ├── Marca general LOLY → USA: loly.md sección colores principales
│   ├── División BIUR / KIDS → paleta roja (#F23325)
│   ├── División ACTI-B → paleta naranja (#F67A1D)
│   └── División CITRUS → paleta amarilla (#F4B000)
│
├── ICHIGO (propuesta creativa, portafolio de agencia, contenido de marca)
│   └── → USA: ichigo.md  (GO en pie de página como marca madre)
│
├── TODO PAL NEGOCIO (ofertas, carteles, flyers, redes comerciales)
│   └── → USA: todo-pal-negocio.md  (GO en pie de página como marca madre)
│
└── PIEZA MIXTA (múltiples marcas GO en un mismo documento)
    └── → Cabecera/firma: go.md manda
        → Cuerpo del producto: slug de la sub-marca correspondiente
        → Reglas de conflicto: ver Sección 4
```

---

## 3. Reglas de Precedencia

### Regla 1 — Sub-marca manda dentro de su producto
Cuando el contenido pertenece exclusivamente a una sub-marca (empaque de Loly, cartel de Todo Pal Negocio, tarjeta del hotel), la paleta, tipografía y tono de esa sub-marca tienen prioridad total.

### Regla 2 — GO manda en cabeceras corporativas y firmas
En cualquier documento que lleve la firma institucional de Grupo Ortiz — reportes, contratos, comunicados internos, presentaciones directivas — el encabezado y pie usan siempre `go.md` + `context_design.md`.

### Regla 3 — Conflicto de paleta: sub-marca gana en su producto
Si un color de sub-marca entra en conflicto con el naranja GO `#FB670B` dentro de una pieza de producto, la sub-marca tiene precedencia en esa pieza. El naranja GO solo aparece en el indicador de marca madre (pie de página, sello, cabecera corporativa).

### Regla 4 — Tipografía global (escala y modo oscuro)
La escala tipográfica y el modo oscuro vienen siempre de `context_design.md`, independientemente de la sub-marca. Cada sub-marca añade sus propias fuentes de display/cuerpo **sin reemplazar** la escala del sistema.

### Regla 5 — Tono & voz por sub-marca
El tono es propiedad de cada sub-marca. Ichigo es audaz, HPG es sereno, Todo Pal Negocio es coloquial — no intercambiar voces entre marcas aunque convivan en un mismo documento.

---

## 4. Tabla de Conflictos de Color

Cuando dos marcas deban convivir en una misma pieza, usa esta tabla para resolver conflictos:

| Sub-marca A | Sub-marca B | Color en conflicto | Resolución |
|---|---|---|---|
| GO naranja `#FB670B` | PM lima `#CCFF50` | Ambos como acento | GO solo en cabecera/firma; PM lima como acento interno |
| GO naranja `#FB670B` | Loly morado `#B02686` | Primarios distintos | Separar secciones; GO en marco, Loly en contenido |
| GO naranja `#FB670B` | TPN rojo `#E2032C` | Colores cálidos | No mezclar en misma zona; GO en header, TPN en body |
| Ichigo negro `#282828` | GO negro `#262626` | Casi idénticos | Unificar en `#262626` (GO) — diferencia imperceptible |
| HPG arena `#e5e0d8` | GO crema `#ECEBE0` | Tonos cálidos similares | Preferir `#ECEBE0` (GO) en piezas mixtas |

---

## 5. Fichas Rápidas de cada Marca

### go — Grupo Ortiz (corporativo)
- **Paleta:** Naranja `#FB670B` · Gris Oscuro `#262626` · Gris `#535353` · Gris Claro `#C5C5C5`
- **Tipo display:** Morganite Extra Bold (MAYÚSCULAS)
- **Tipo cuerpo:** Helony / fallback Blauer Nue (ver `context_design.md`)
- **Voz:** Formal, aspiracional, familiar de 65 años
- **Restricción clave:** Logo nunca distorsionado, rotado ni recoloreado
- → [go.md](go.md)

### pm — Plaza Madero
- **Paleta:** Dorado `#D6B78D` · Azul lavanda `#7C90E5` · Negro `#222524` · Lima `#CCFF50`
- **Tipo:** Menseal Regular (logo) · Articular SF Regular (cuerpo)
- **Voz:** Tecnológico, accesible, moderno
- **Restricción clave:** Lima solo como acento — nunca como fondo dominante
- → [pm.md](pm.md)

### hpg — Hotel Punta Galería
- **Paleta:** Verde oliva `#838c2f` · Arena `#e5e0d8` · Azul pizarra `#323f48`
- **Tipo:** Brisbane Semibold (kerning -20) · Salford Sans VF
- **Voz:** Sereno, evocador, hospitalidad de alta gama
- **Restricción clave:** Sin colores llamativos ajenos al espectro verde-arena
- **⚠️ OCR:** Nombre exacto del logo y variantes pendientes de validación visual
- → [hpg.md](hpg.md)

### loly — Loly Gummies
- **Paleta:** Morado `#B02686` · Rosa `#EA9BD6` · Azul `#2E4EE0` + paletas por división
- **Tipo:** Rooney Sans · SF Pro Rounded
- **Voz:** Alegre, familiar, saludable
- **Restricción clave:** No mezclar paletas de divisiones distintas en una misma pieza
- → [loly.md](loly.md)

### ichigo — Ichigo Agencia Creativa
- **Paleta:** Amarillo `#FFD72E` · Verde `#236D2D` · Negro `#282828`
- **Tipo:** ITC Avant Garde Book (títulos) · ITC Avant Garde Bold (cuerpo)
- **Voz:** Creativo, directo, audaz
- **Restricción clave:** Seis prohibiciones del logo (opacidad, rotación, deformación, sombra, omisión, cambio de color)
- → [ichigo.md](ichigo.md)

### todo-pal-negocio — Todo Pal Negocio®
- **Paleta:** Rojo `#E2032C` · Amarillo `#FBBE27` · Azul oscuro `#394652`
- **Tipo:** Eigerdals Black (títulos) · Como Family kerning -28 (cuerpo)
- **Voz:** Directo, coloquial, energético, comercial
- **Restricción clave:** Siempre incluir ® · Paleta alta energía — sin pasteles
- **⚠️ OCR:** Paleta obtenida de paths vectoriales — validar contra PDF original
- → [todo-pal-negocio.md](todo-pal-negocio.md)

---

## 6. Tokens CSS del Sistema Completo

> Los tokens de Grupo Ortiz (--go-*) están definidos en [`context_design.md §2`](../../context_design.md).  
> Aquí se muestra cómo se relacionan todos los namespaces.

```css
/* ================================================
   BRAND SYSTEM — Grupo Ortiz & Sub-marcas
   Cargar context_design.md primero (--go-* base)
   ================================================ */

/* ── Plaza Madero ─────────────────────── */
--pm-dorado:      #D6B78D;
--pm-azul:        #7C90E5;
--pm-negro:       #222524;
--pm-blanco-humo: #F5F7F0;
--pm-lima:        #CCFF50;
--pm-cafe:        #9B8B78;

/* ── Hotel Punta Galería ──────────────── */
--hpg-verde-oliva:  #838c2f;
--hpg-verde-oscuro: #626c1f;
--hpg-verde-bosque: #236d00;
--hpg-azul-pizarra: #323f48;
--hpg-arena-claro:  #e5e0d8;
--hpg-arena-medio:  #c7b7a4;

/* ── Loly Gummies ─────────────────────── */
--loly-morado:    #B02686;
--loly-rosa:      #EA9BD6;
--loly-azul:      #2E4EE0;
/* divisiones */
--loly-biur:      #F23325;
--loly-actib:     #F67A1D;
--loly-citrus:    #F4B000;

/* ── Ichigo Agencia Creativa ──────────── */
--ichigo-amarillo: #FFD72E;
--ichigo-verde:    #236D2D;
--ichigo-negro:    #282828;

/* ── Todo Pal Negocio ─────────────────── */
--tpn-rojo:        #E2032C;   /* ⚠️ validar vs PDF */
--tpn-amarillo:    #FBBE27;   /* ⚠️ validar vs PDF */
--tpn-azul-oscuro: #394652;   /* ⚠️ validar vs PDF */
```

---

## 7. Guía de Tipografía por Marca

| Slug | Display / Títulos | Cuerpo / Párrafos | Fallback display | Fallback cuerpo |
|---|---|---|---|---|
| go | Morganite Extra Bold | Helony | Impact, Arial Narrow | Helvetica Neue |
| pm | Menseal Regular | Articular SF Regular | Futura, Century Gothic | SF Pro, Helvetica Neue |
| hpg | Brisbane Semibold | Salford Sans VF | Cormorant Garamond, Georgia | Lato, Helvetica Neue |
| loly | Rooney Sans | SF Pro Rounded | Nunito, Varela Round | Nunito, Poppins |
| ichigo | ITC Avant Garde Book | ITC Avant Garde Bold | Futura, Century Gothic | Gill Sans, Arial |
| todo-pal-negocio | Eigerdals Black | Como Family | Impact, Arial Black | Trebuchet MS, Arial |

> Para la escala (tamaños, pesos, line-height) y el sistema de fallbacks web, ver [`context_design.md §3`](../../context_design.md).

---

## 8. Inventario de Assets Físicos

```
IDENTIDAD DE MARCA/
├── context_design.md               ← Sistema GO maestro (tokens, UI, modo oscuro)
├── guias y manuales/
│   ├── *.pdf                       ← PDFs originales (solo lectura)
│   └── markdowns/
│       ├── brand_system.md         ← ESTE ARCHIVO
│       ├── go.md
│       ├── pm.md
│       ├── hpg.md
│       ├── loly.md
│       ├── ichigo.md
│       ├── todo-pal-negocio.md
│       └── _raw/                   ← Extracciones crudas (auditoría)
│           ├── go.txt  pm.txt  hpg.txt
│           ├── loly.txt  ichigo.txt
│           └── todo-pal-negocio.txt
├── 01_LOGO/                        ← Variantes PNG de logo GO
├── 02_TIPOGRAFIA/                  ← Fuentes ZIP (Blauer Nue, Morganite, Conthic)
├── 03_PALETA DE COLORES/           ← Swatches PNG de colores GO
├── 04_ELEMENTOS GRAFICOS/          ← Íconos de divisiones GO
└── 05_GUIAS DE MARCA/              ← Guías visuales adicionales
```

---

## 9. Alertas de Validación Pendiente

Los siguientes puntos requieren revisión humana contra los PDFs originales antes de usar en producción:

| Marca | Elemento | Motivo | PDF a revisar |
|---|---|---|---|
| HPG | Nombre exacto del logo / isotipo | OCR leyó "Klinta Galería" — posible error | `Manual de marca HPG.pdf` pg 1 |
| HPG | Variantes de logo (positivo/negativo) | Páginas 3–6 sin texto extraíble | `Manual de marca HPG.pdf` pgs 3–6 |
| PM | Variantes de logo y aplicaciones | Páginas 1–8 y 11–13 con OCR débil | `BRANDBOOK PM.pdf` pgs 1–8, 11–13 |
| TPN | Paleta corporativa completa | Colores extraídos de paths vectoriales, no de texto | `Manual de identidad.pdf` pg 6 |
| TPN | Variantes de logo | Páginas 1–6 sin texto legible | `Manual de identidad.pdf` pgs 1–5 |

---

## 10. Checklist de Integración (para IA/Agente)

Antes de generar cualquier pieza visual o comunicado del ecosistema GO:

- [ ] ¿Identifiqué a qué slug/marca pertenece esta pieza? (ver Sección 2)
- [ ] ¿Cargué el archivo `{slug}.md` correspondiente?
- [ ] ¿Para tipografía global, escala y modo oscuro, consulté `context_design.md`?
- [ ] ¿Apliqué las reglas de precedencia de Sección 3?
- [ ] ¿Revisé la tabla de conflictos si la pieza involucra más de una marca? (Sección 4)
- [ ] ¿Los tokens CSS que uso pertenecen al namespace correcto (`--{slug}-*`)?
- [ ] ¿Hay alertas de validación pendiente para esta marca? (Sección 9)
- [ ] ¿En cabeceras y firmas corporativas, el logo GO es el protagonista?
- [ ] ¿El tono de voz corresponde a la sub-marca, no a GO corporativo?
- [ ] ¿Los PDFs originales NO fueron modificados?
