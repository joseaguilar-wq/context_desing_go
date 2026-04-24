# Grupo Ortiz — Design System Context
> Fuente de verdad para todos los proyectos internos. Aplica a: web apps, reportes HTML, PDFs, emails, tablas, presentaciones y cualquier pieza digital de Grupo Ortiz.

---

## 1. IDENTIDAD DE MARCA

**Empresa:** Grupo Ortiz  
**Abreviatura oficial:** GO  
**Símbolo:** Dos hojas estilizadas (una sólida, una en trazo) — representa crecimiento orgánico  
**Tipografía del logo:** Blauer Nue (geométrica redondeada)  
**Color primario:** Naranja GO `#FB670B`

---

## 2. PALETA DE COLORES OFICIAL

### Primario
| Nombre | Hex | Uso |
|--------|-----|-----|
| Naranja GO | `#FB670B` | Color de marca, CTAs, acentos, links activos, botones primarios |
| Naranja Web (app) | `#F97316` | Aproximación web del naranja GO — usar en CSS cuando FB670B no esté disponible |

### Neutrales
| Nombre | Hex | Uso |
|--------|-----|-----|
| Negro GO | `#262626` | Fondos oscuros, textos principales sobre claro, logo versión oscura |
| Gris Oscuro | `#535353` | Texto secundario, bordes fuertes, iconos secundarios |
| Gris Claro | `#C5C5C5` | Bordes, separadores, fondos de tabla alternos |
| Crema / Marfil | `#ECEBE0` | Fondos cálidos, fondos de reportes, áreas de contenido |
| Blanco | `#FFFFFF` | Fondo principal, logo blanco sobre oscuro |

### Paleta completa ordenada (oscuro → claro)
```
#262626  →  #535353  →  #C5C5C5  →  #ECEBE0  →  #FFFFFF
```
Con acento: `#FB670B` (naranja)

### Tokens CSS recomendados
```css
:root {
  --go-orange:      #FB670B;
  --go-orange-hot:  #FF7A22;        /* hover */
  --go-orange-deep: #D95C00;        /* pressed */
  --go-orange-tint: rgba(251,103,11,0.10); /* fondos suaves */

  --go-black:   #262626;
  --go-gray-1:  #535353;
  --go-gray-2:  #C5C5C5;
  --go-cream:   #ECEBE0;
  --go-white:   #FFFFFF;

  /* Semánticos */
  --go-bg:        var(--go-white);
  --go-bg-warm:   var(--go-cream);
  --go-text:      var(--go-black);
  --go-text-2:    var(--go-gray-1);
  --go-text-3:    var(--go-gray-2);
  --go-accent:    var(--go-orange);
  --go-border:    var(--go-gray-2);
}
```

---

## 3. TIPOGRAFÍA

### Fuentes oficiales GO
Las fuentes están en `02_TIPOGRAFIA/` del repositorio de diseño.

| Fuente | Archivo | Rol | Características |
|--------|---------|-----|-----------------|
| **Blauer Nue** | `blauer-nue-font-family.zip` | **PRINCIPAL** — logo, display, UI | Geométrica redondeada, moderna, friendly. Usada en "grupo ortiz" y "go" |
| **Morganite Pro** | `MorganitePro™.zip` | Display / titulares grandes | Condensada, alto impacto visual — para portadas, KPIs grandes |
| **Conthic** | `conthic-font.zip` | Cuerpo / apoyo | Legible en tamaños pequeños — tablas, reportes, texto corrido |

### Fallbacks seguros (cuando fuentes GO no estén instaladas)
```css
--go-font-display: 'Blauer Nue', 'Nunito', 'Poppins', 'Inter', sans-serif;
--go-font-headline: 'Morganite Pro', 'Archivo Black', 'Bebas Neue', sans-serif;
--go-font-body: 'Conthic', 'Inter', 'Segoe UI', system-ui, sans-serif;
--go-font-mono: 'JetBrains Mono', 'Fira Code', Consolas, monospace;
```

### Escala tipográfica
| Nivel | Fuente | Tamaño | Peso | Uso |
|-------|--------|--------|------|-----|
| Display XL | Morganite Pro | 72–96px | 700 | Portadas, hero sections |
| H1 | Blauer Nue | 48–64px | 700 | Títulos principales de página |
| H2 | Blauer Nue | 32–40px | 600 | Secciones, títulos de tarjeta |
| H3 | Blauer Nue | 24–28px | 600 | Subtítulos |
| H4 | Blauer Nue | 18–20px | 600 | Encabezados de tabla, labels fuertes |
| Body | Conthic | 14–16px | 400 | Texto corrido, párrafos |
| Body Small | Conthic | 12–13px | 400 | Notas, pie de página, metadatos |
| Label | Conthic | 10–11px | 600–700 | Etiquetas, eyebrows (uppercase + letter-spacing) |
| Mono | JetBrains Mono | 12–13px | 400 | Precios, cifras, código, fechas |

### Reglas tipográficas
- **Eyebrow / label:** `font-size: 11px; font-weight: 700; text-transform: uppercase; letter-spacing: 0.14em; color: var(--go-orange)`
- **Precio / cifra clave:** `font-family: var(--go-font-mono); font-variant-numeric: tabular-nums; letter-spacing: -0.02em`
- **Título de sección:** `font-family: var(--go-font-display); font-weight: 700; text-transform: uppercase`
- Nunca mezclar más de 2 fuentes en una misma pieza
- Naranja **solo** en acentos tipográficos — nunca en texto corrido largo

---

## 4. LOGO — VARIANTES Y USO

### Anatomía del sistema de logo

```
ISOTIPO      = Las dos hojas (símbolo puro, sin texto)
IMAGOTIPO    = "go" + hojas encima (ícono tipográfico)
LOGOTIPO     = "grupo ortiz" (texto solo, Blauer Nue)
COMPLETO     = IMAGOTIPO + LOGOTIPO (vertical u horizontal)
```

### Archivos disponibles
| Archivo | Descripción | Usar sobre |
|---------|-------------|------------|
| `ISOTIPO_GO_NARANJA.png` | Hojas en naranja | Fondo blanco, crema, gris claro |
| `ISOTIPO_GO_GRIS.png` | Hojas en #262626 | Fondo blanco, crema |
| `ISOTIPO_GO_BLANCO.png` | Hojas en blanco | Fondo naranja, negro, oscuro |
| `IMAGOTIPO_GO_NARANJA.png` | "go" + hojas naranja | Fondo blanco o claro |
| `IMAGOTIPO_GO_GRIS.png` | "go" + hojas gris | Fondo blanco o claro |
| `IMAGOTIPO_GO_BLANCO.png` | "go" + hojas blanco | Fondo naranja o negro |
| `LOGOTPOS_GO_NARANJA.png` | "grupo ortiz" naranja | Fondo blanco o claro |
| `LOGOTPOS_GO_GRIS.png` | "grupo ortiz" gris | Fondo blanco o claro |
| `LOGOTPOS_GO_BALNCO.png` | "grupo ortiz" blanco | Fondo naranja o negro |

### Versión app/web (con ícono y texto)
```
IDENTIDAD-04.png  →  Imagotipo naranja (solo "go" + hojas) — uso en UI compacto
IDENTIDAD-05.png  →  Imagotipo gris oscuro — modo monocromático
IDENTIDAD-06.png  →  Imagotipo blanco — sobre fondos oscuros
```

### Fondo del ícono en UI
Cuando el logo se use en contenedor pequeño (nav, favicon, avatar):
- Fondo: `#F97316` (naranja) — **siempre, sin importar modo claro u oscuro**
- Border-radius: `8px` (nav small), `14px` (login/card)
- Logo PNG: versión blanca sobre ese fondo

### Espacio de respeto
- Mínimo: `= altura de la hoja pequeña del isotipo` alrededor del logo completo
- Nunca distorsionar proporciones
- Nunca aplicar efectos (sombra, gradiente, stroke extra)
- Nunca cambiar colores fuera del sistema (naranja, gris, blanco)

---

## 5. COMPONENTES UI

### Botón primario
```css
.btn-primary {
  background: var(--go-orange);
  color: #fff;
  font-family: var(--go-font-display);
  font-weight: 700;
  font-size: 14px;
  letter-spacing: 0.04em;
  border: none;
  border-radius: 8px;
  padding: 12px 24px;
  cursor: pointer;
  transition: background 200ms ease;
}
.btn-primary:hover  { background: #FF7A22; }
.btn-primary:active { background: #D95C00; }
```

### Botón secundario / ghost
```css
.btn-ghost {
  background: transparent;
  color: var(--go-black);
  border: 1.5px solid var(--go-gray-2);
  border-radius: 8px;
  padding: 10px 20px;
  font-weight: 600;
  transition: all 200ms ease;
}
.btn-ghost:hover { border-color: var(--go-orange); color: var(--go-orange); }
```

### Card / tarjeta
```css
.card {
  background: var(--go-white);
  border: 1px solid var(--go-gray-2);
  border-radius: 12px;
  padding: 24px;
  box-shadow: 0 2px 8px rgba(38,38,38,0.06);
}
/* Header de card */
.card-header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 16px;
  padding-bottom: 12px;
  border-bottom: 1px solid var(--go-gray-2);
}
.card-title {
  font-family: var(--go-font-display);
  font-weight: 700;
  font-size: 13px;
  text-transform: uppercase;
  letter-spacing: 0.08em;
  color: var(--go-black);
}
```

### Input / campo de formulario
```css
.input {
  width: 100%;
  padding: 10px 14px;
  border: 1.5px solid var(--go-gray-2);
  border-radius: 8px;
  font-family: var(--go-font-body);
  font-size: 14px;
  color: var(--go-black);
  background: var(--go-white);
  transition: border-color 200ms;
}
.input:focus {
  outline: none;
  border-color: var(--go-orange);
  box-shadow: 0 0 0 3px rgba(251,103,11,0.10);
}
```

### Badge / píldora de estado
```css
/* Señal positiva */
.badge-buy    { background: rgba(0,163,110,0.12); color: #00A36E; border: 1px solid rgba(0,163,110,0.25); }
/* Espera */
.badge-wait   { background: rgba(217,119,6,0.12);  color: #D97706; border: 1px solid rgba(217,119,6,0.25); }
/* Alerta */
.badge-alert  { background: rgba(251,103,11,0.12); color: #FB670B; border: 1px solid rgba(251,103,11,0.25); }

.badge {
  display: inline-flex;
  align-items: center;
  gap: 5px;
  padding: 3px 10px;
  border-radius: 999px;
  font-size: 11px;
  font-weight: 700;
  text-transform: uppercase;
  letter-spacing: 0.08em;
}
```

### Eyebrow (etiqueta de sección)
```css
.eyebrow {
  font-size: 11px;
  font-weight: 700;
  text-transform: uppercase;
  letter-spacing: 0.14em;
  color: var(--go-orange);
}
```

---

## 6. TABLAS

### Tabla estándar (reportes, dashboards)
```css
.go-table {
  width: 100%;
  border-collapse: collapse;
  font-family: var(--go-font-body);
  font-size: 13px;
}
.go-table thead tr {
  border-bottom: 2px solid var(--go-orange);
}
.go-table thead th {
  padding: 10px 12px;
  text-align: left;
  font-family: var(--go-font-display);
  font-weight: 700;
  font-size: 11px;
  text-transform: uppercase;
  letter-spacing: 0.10em;
  color: var(--go-gray-1);
}
.go-table tbody tr {
  border-bottom: 1px solid var(--go-gray-2);
  transition: background 150ms;
}
.go-table tbody tr:hover { background: rgba(251,103,11,0.04); }
.go-table tbody td {
  padding: 10px 12px;
  color: var(--go-black);
  vertical-align: middle;
}
.go-table tbody tr:last-child { border-bottom: none; }

/* Filas alternas */
.go-table.striped tbody tr:nth-child(even) {
  background: var(--go-cream);
}

/* Celda de cifra/precio */
.go-table td.num {
  font-family: var(--go-font-mono);
  font-variant-numeric: tabular-nums;
  text-align: right;
}

/* Celda de delta positivo/negativo */
.go-table td.up   { color: #00A36E; font-weight: 700; }
.go-table td.down { color: #FB670B; font-weight: 700; }
```

### HTML template de tabla
```html
<table class="go-table">
  <thead>
    <tr>
      <th>Producto</th>
      <th class="num">Precio Hoy</th>
      <th class="num">Var. 24h</th>
      <th>Señal</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>PP Spot</td>
      <td class="num">$12.45 MXN/kg</td>
      <td class="num up">+0.8%</td>
      <td><span class="badge badge-buy">● BUY</span></td>
    </tr>
  </tbody>
</table>
```

---

## 7. REPORTES HTML / EMAIL

### Estructura de reporte GO
```html
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <style>
    body {
      margin: 0; padding: 0;
      background: #ECEBE0;
      font-family: 'Conthic', 'Inter', sans-serif;
      color: #262626;
    }
    .wrapper { max-width: 680px; margin: 0 auto; }

    /* Header con logo */
    .report-header {
      background: #262626;
      padding: 28px 40px;
      display: flex;
      align-items: center;
      gap: 16px;
    }
    .report-logo-box {
      width: 48px; height: 48px;
      background: #FB670B;
      border-radius: 10px;
      display: flex; align-items: center; justify-content: center;
    }
    .report-logo-box img { width: 36px; height: 36px; object-fit: contain; }
    .report-brand { color: #fff; }
    .report-brand strong {
      display: block;
      font-size: 18px; font-weight: 700;
      letter-spacing: 0.04em;
    }
    .report-brand small {
      font-size: 11px; color: rgba(255,255,255,0.55);
      text-transform: uppercase; letter-spacing: 0.14em;
    }

    /* Banda naranja de acento */
    .report-accent-bar { height: 4px; background: #FB670B; }

    /* Sección */
    .report-section {
      background: #FFFFFF;
      margin: 0; padding: 32px 40px;
      border-bottom: 1px solid #C5C5C5;
    }
    .report-section-label {
      font-size: 10px; font-weight: 700;
      text-transform: uppercase; letter-spacing: 0.18em;
      color: #FB670B; margin-bottom: 12px;
    }

    /* KPI grande */
    .kpi-value {
      font-family: 'JetBrains Mono', monospace;
      font-size: 42px; font-weight: 700;
      color: #262626; letter-spacing: -0.02em;
    }
    .kpi-label { font-size: 12px; color: #535353; margin-top: 4px; }

    /* Footer */
    .report-footer {
      background: #262626; padding: 20px 40px;
      text-align: center;
      font-size: 11px; color: rgba(255,255,255,0.4);
    }
  </style>
</head>
<body>
  <div class="wrapper">
    <div class="report-header">
      <div class="report-logo-box">
        <img src="cid:logo" alt="GO">
      </div>
      <div class="report-brand">
        <strong>Grupo Ortiz</strong>
        <small>Market Intelligence · Monitor PP/PE</small>
      </div>
    </div>
    <div class="report-accent-bar"></div>

    <div class="report-section">
      <div class="report-section-label">Señal de Compra</div>
      <!-- contenido -->
    </div>

    <div class="report-footer">
      Grupo Ortiz · nexus.go@grupo-ortiz.com · Confidencial
    </div>
  </div>
</body>
</html>
```

---

## 8. PDF / PRINT

### Variables para impresión
```css
@media print {
  body { background: #fff; color: #262626; }

  /* Quitar sombras y transiciones */
  * { box-shadow: none !important; transition: none !important; }

  /* Naranja se imprime bien en mayoría de impresoras */
  .go-accent { color: #FB670B; }

  /* Encabezado de página PDF */
  .pdf-header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    border-bottom: 3px solid #FB670B;
    padding-bottom: 16px;
    margin-bottom: 24px;
  }
  .pdf-footer {
    position: fixed;
    bottom: 0; left: 0; right: 0;
    border-top: 1px solid #C5C5C5;
    padding: 8px 40px;
    font-size: 10px; color: #535353;
    display: flex; justify-content: space-between;
  }

  /* Saltos de página */
  .page-break { page-break-before: always; }
  .no-break { page-break-inside: avoid; }
}
```

### Márgenes de página recomendados
- Carta/A4: `margin: 20mm 25mm` (Word/PDF)
- Header fijo: logo GO izquierda + fecha derecha
- Footer fijo: `Grupo Ortiz Confidencial · Página X de Y`
- Color de línea divisoria encabezado: `#FB670B` 3pt

---

## 9. MODO OSCURO (web apps)

```css
body[data-mode="dark"] {
  --go-bg:      #0A0A0A;
  --go-bg-warm: #111111;
  --go-text:    #FFFFFF;
  --go-text-2:  #A0A0A0;
  --go-text-3:  #707070;
  --go-border:  rgba(255,255,255,0.09);
  /* Naranja NO cambia — se mantiene #FB670B en ambos modos */
  --go-orange:  #FB670B;
}
```

**Regla de oro:** El naranja `#FB670B` es **invariable** — mismo valor en modo claro y oscuro. Solo los neutros se invierten.

---

## 10. DIVISIONES / ICONOS INTERNOS

Grupo Ortiz tiene divisiones de producto con iconos propios ubicados en `04_ELEMENTOS GRAFICOS/ICONOS/`.

| División | Ícono disponible |
|----------|-----------------|
| Arpilla | `ICONOS_DIVICIONES_ARPILLA.png` |
| Cuerda | `ICONOS_DIVICIONES_CUERDA.png` |
| Desechables | `ICONOS_DIVICIONES_DESECHABLES.png` |
| Esquineros | `ICONOS_DIVICIONES_ESQUINEROS.png` |
| Fleje | `ICONOS_DIVICIONES_FLEJE.png` |
| Fletería | `ICONOS_DIVICIONES_FLETERIA.png` |
| Flexibles | `ICONOS_DIVICIONES_FLEXIBLES.png` |
| Rafia | `ICONOS_DIVICIONES_RAFIA.png` |
| Saco | `ICONOS_DIVICIONES_SACO.png` |
| Stretch | `ICONOS_DIVICIONES_STRETCH.png` |

Todos en fondo oscuro con ícono naranja — usar solo en contextos de identidad corporativa.

---

## 11. REGLAS DE ORO (resumen ejecutivo para IA/agentes)

1. **Naranja `#FB670B`** — color de acento universal. Va en: botones primarios, links activos, eyebrows, bordes de tabla, barras de acento, fondo del ícono GO.
2. **Negro `#262626`** — texto principal, fondos oscuros, headers de reporte.
3. **Crema `#ECEBE0`** — fondo preferido de reportes y PDFs (más cálido que blanco puro).
4. **Blauer Nue** — toda tipografía visible de marca (títulos, labels, logo text).
5. **Logo ícono** — siempre sobre fondo naranja `#FB670B` cuando va en contenedor pequeño.
6. **Logo texto** — "grupo ortiz" siempre en minúsculas, nunca en mayúsculas.
7. **Tablas** — línea superior `border-top: 2px solid #FB670B`, encabezados en Blauer Nue uppercase.
8. **Cifras/precios** — siempre en fuente monoespaciada (`JetBrains Mono` o equivalente).
9. **Naranja en modo oscuro** — sin cambio. Mismo hex en ambos modos.
10. **No mezclar** más de 2 pesos de fuente en una misma sección.

---

## 12. RUTAS DE ASSETS

```
new desing/
├── 01_LOGO/
│   ├── ISOTIPO_GO_NARANJA.png      ← hojas solo, naranja
│   ├── ISOTIPO_GO_GRIS.png         ← hojas solo, oscuro
│   ├── ISOTIPO_GO_BLANCO.png       ← hojas solo, blanco (sobre oscuro)
│   ├── IMAGOTIPO_GO_NARANJA.png    ← "go" + hojas, naranja
│   ├── IMAGOTIPO_GO_GRIS.png       ← "go" + hojas, oscuro
│   ├── IMAGOTIPO_GO_BLANCO.png     ← "go" + hojas, blanco
│   ├── LOGOTPOS_GO_NARANJA.png     ← "grupo ortiz" texto, naranja
│   ├── LOGOTPOS_GO_GRIS.png        ← "grupo ortiz" texto, oscuro
│   ├── LOGOTPOS_GO_BALNCO.png      ← "grupo ortiz" texto, blanco
│   └── ARCHIVO/                    ← variantes horizontales + círculo
│
├── 02_TIPOGRAFIA/
│   ├── blauer-nue-font-family.zip  ← PRINCIPAL — instalar primero
│   ├── MorganitePro™.zip           ← Display / titulares
│   └── conthic-font.zip            ← Cuerpo / tablas / reportes
│
├── 03_PALETA DE COLORES/
│   ├── FB670B.png  ← Naranja GO (primario)
│   ├── 262626.png  ← Negro GO
│   ├── 535353.png  ← Gris oscuro
│   ├── C5C5C5.png  ← Gris claro
│   ├── ecebe0.png  ← Crema
│   └── FFFFFF.png  ← Blanco
│
└── 04_ELEMENTOS GRAFICOS/
    └── ICONOS/     ← íconos por división de producto
```

---

*Última actualización: 2026-04-24 · Generado desde activos oficiales de Grupo Ortiz*
