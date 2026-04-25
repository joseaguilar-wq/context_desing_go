---
marca: "Todo Pal Negocio®"
slug: "todo-pal-negocio"
fuente_pdf: "Manual de identidad.pdf"
paginas_fuente: 11
version: "1.0"
fecha_extraccion: "2026-04-25"
aplica_a: ["pdf","reporte","presentacion","web","email","packaging"]
---

# Todo Pal Negocio® — Manual de Marca

## 1. Esencia & Posicionamiento

**Todo Pal Negocio®** es una marca de impulso comercial con energía, humor y accesibilidad. Comunica ofertas, promociones y oportunidades de negocio de forma directa, llamativa y sin complicaciones. El tono es coloquial y cercano — como un amigo que te avisa de un buen negocio.

**Registro de marca:** Todo Pal Negocio® (marca registrada)
**Promesa de marca:** "Ahorro de locura — ven y compruébalo"
**Carácter:** Directo · Accesible · Festivo · Comercial

<!-- OCR: revisar — PDF completamente vectorizado (texto en paths), extracción por análisis de trazos -->

## 2. Logo

### Identificador principal
- Logotipo: **"todo pal negocio®"** en minúsculas + símbolo de marca registrada
- Integra elemento gráfico de energía (rayo, estrellas o formas dinámicas)
- Presentado con paleta rojo-amarillo de alto contraste

### Versiones detectadas
- Logo completo con isotipo + wordmark
- Variantes sobre fondos oscuros y claros

<!-- OCR: revisar — páginas 1-6 contienen solo el logo sin texto legible; confirmar variantes exactas contra PDF original -->

## 3. Paleta de Colores

> ⚠️ **Nota metodológica:** esta paleta fue extraída mediante análisis de **drawing paths vectoriales** con pymupdf (el texto está 100% convertido a paths). Los colores están validados por frecuencia de aparición en páginas de branding (pg 6-9). Se recomienda validar visualmente contra el PDF original.
> <!-- OCR: revisar — colores obtenidos de paths PDF, no de texto legible -->

### Paleta corporativa principal (pg 6 — paleta de marca)

| Nombre              | Hex       | Uso principal |
|---|---|---|
| Rojo Principal      | `#E2032C` | Color dominante, logos, fondos de portada, CTAs |
| Amarillo Corporativo| `#FBBE27` | Contraste con rojo, acento energético, textos sobre rojo |
| Amarillo Claro      | `#FCD722` | Variante del amarillo, degradados y detalles |
| Azul Oscuro         | `#394652` | Fondos secundarios, texto, contraste frío |

### Paleta extendida (recurrente en todo el documento)

| Nombre          | Hex       | Uso |
|---|---|---|
| Azul Medio      | `#55707A` | Fondos alternos, detalles |
| Azul Gris       | `#788E9B` | Texto sobre fondos oscuros, complementario |
| Gris Claro      | `#BAC0C5` | Fondos neutros, divisores |
| Negro Suave     | `#211F1F` | Texto principal, fondos muy oscuros |

### Usos de color
- **Pareja dominante:** Rojo `#E2032C` + Amarillo `#FBBE27` — identidad visual central, máximo contraste y energía
- **Fondos oscuros:** Azul Oscuro `#394652` para secciones formales o secundarias
- **Textos:** Negro Suave `#211F1F` sobre fondos claros; Amarillo o Blanco sobre rojo

## 4. Tipografía

### Tipografía principal — Eigerdals Black
- Uso: títulos de ofertas, encabezados de impacto, "PROMOCIONES DE LOCURA"
- Carácter: ultra-bold, condensada, máxima legibilidad a distancia
- Estilo: Black (peso máximo)

### Tipografía secundaria — Como Family
- Uso: cuerpo de texto, subtítulos, descripciones
- Estilo: kerning `-28` (ligeramente comprimido)
- Carácter: legible, neutral, complementa el peso de Eigerdals

### Fallbacks sugeridos
```
font-family: 'Eigerdals', 'Impact', 'Arial Black', sans-serif;     /* títulos  */
font-family: 'Como', 'Trebuchet MS', Arial, sans-serif;            /* cuerpo   */
```

## 5. Elementos Gráficos / Patrones

- Rayas y formas geométricas de alto contraste rojo/amarillo
- Stickers con precios tachados y porcentajes de descuento
- Composiciones estilo cartel comercial / publicidad de mercado
- Referencias visuales: carteles de supermercado, redes sociales de ofertas, banners de precio

## 6. Tono & Voz

- **Directo y coloquial** — habla como la gente, sin tecnicismos
- **Energético y festivo** — cada comunicación es una oportunidad
- **Orientado a la acción** — "ven y compruébalo", "ahorro de locura"
- **Confiable por precio** — transparencia en oferta, no en corporativismo
- Evitar: lenguaje formal o corporativo; palabras largas o complicadas; tono neutro o frío

## 7. Aplicaciones

- **Carteles de punto de venta (POP):** rojo + amarillo, Eigerdals Black, precios grandes
- **Redes sociales:** composiciones dinámicas con rayas y stickers de precio
- **Banners digitales:** alta visibilidad, poco texto, precio/descuento como protagonista
- **Folletería de ofertas:** estilo supermercado/mayoreo, paleta rojo-amarillo-azul
- **Email de promociones:** asunto impactante, diseño tipo cartel, CTA en amarillo sobre rojo

## 8. Restricciones / NO Hacer

- ❌ No usar colores pasteles o desaturados — rompen la energía de la marca
- ❌ No usar tipografías ligeras o serif — la marca es contundente y directa
- ❌ No comunicar con tono formal o corporativo
- ❌ No perder el símbolo ® del nombre de la marca
- ❌ No usar la paleta de otro producto del portafolio GO en piezas de Todo Pal Negocio

## 9. Tokens CSS Sugeridos

```css
/* === Todo Pal Negocio — Design Tokens === */
/* Sub-marca de Grupo Ortiz. En cabeceras corporativas, --go-* manda. */
/* ⚠️ Colores extraídos de paths vectoriales — validar contra PDF original */
/* Namespace canónico: --todo-pal-negocio-* | Shorthand: --tpn-* (aliases) */

/* Tokens canónicos (namespace completo) */
--todo-pal-negocio-primary:  #E2032C;
--todo-pal-negocio-accent:   #FBBE27;
--todo-pal-negocio-dark:     #394652;
--todo-pal-negocio-font:     'Eigerdals', Impact, 'Arial Black', sans-serif;

/* Aliases cortos (uso en CSS práctico) */
--tpn-rojo:           #E2032C;
--tpn-amarillo:       #FBBE27;
--tpn-amarillo-alt:   #FCD722;
--tpn-azul-oscuro:    #394652;
--tpn-azul-medio:     #55707A;
--tpn-azul-gris:      #788E9B;
--tpn-gris-claro:     #BAC0C5;
--tpn-negro:          #211F1F;

/* Pareja de impacto */
--tpn-primary:        #E2032C;   /* rojo */
--tpn-accent:         #FBBE27;   /* amarillo */

/* Tipografía */
--tpn-font-display:   'Eigerdals', Impact, 'Arial Black', sans-serif;
--tpn-font-body:      'Como', 'Trebuchet MS', Arial, sans-serif;
--tpn-font-weight-display: 900;   /* Black */
--tpn-letter-spacing-body: -0.028em;  /* kerning -28 */

/* Esquinas */
--tpn-radius:         6px;  /* ligeramente redondeado — accesible y dinámico */
```

## 10. Checklist de Uso (para IA/Agente)

- [ ] ¿La combinación dominante es Rojo `#E2032C` + Amarillo `#FBBE27`?
- [ ] ¿Los títulos usan Eigerdals Black para máximo impacto visual?
- [ ] ¿El nombre incluye el símbolo ® en aplicaciones de marca?
- [ ] ¿El tono es directo, coloquial y orientado a la acción comercial?
- [ ] ¿Se evitan colores pasteles, tipografías ligeras y tono corporativo?
- [ ] ¿Las piezas tienen energía visual alta (contraste, dinamismo, precio visible)?
- [ ] ¿En piezas mixtas con Grupo Ortiz, GO aparece como marca madre en cabecera?
- [ ] <!-- OCR: revisar → validar paleta completa visualmente contra PDF original pg 6 -->
- [ ] <!-- OCR: revisar → confirmar variantes de logo contra PDF original pgs 1-5 -->
