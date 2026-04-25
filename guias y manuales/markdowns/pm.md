---
marca: "Plaza Madero"
slug: "pm"
fuente_pdf: "BRANDBOOK PM.pdf"
paginas_fuente: 13
version: "1.0"
fecha_extraccion: "2026-04-25"
aplica_a: ["pdf","reporte","presentacion","web","email","packaging"]
---

# Plaza Madero — Manual de Marca

## 1. Esencia & Posicionamiento

Plaza Madero es el **epicentro de la tecnología** — un espacio que une la tecnología y el hombre en un punto de encuentro. La marca transmite modernidad, accesibilidad tecnológica y conexión humana.

**Concepto de marca:** Encuentro entre tecnología y personas
**Tagline / Slogan:** *"el epicentro de la tecnología"*

## 2. Logo

### Identificador principal
- Logotipo wordmark **"PLAZA MADERO"** con tipografía Menseal Regular
- El símbolo incorpora **dos flechas** que representan el encuentro entre tecnología y hombre
- Un **espacio negativo** simboliza ese punto de encuentro

### Versiones
- Positivo (sobre fondos claros)
- Negativo (sobre fondos oscuros)
- Versión solo isotipo (flechas)

### Restricciones del logo
- Respetar proporciones originales — no escalar asimétricamente
- No separar el isotipo del wordmark en aplicaciones primarias
- No usar fuera de la paleta autorizada

<!-- OCR: revisar — páginas 1-8 con diseño 100% vectorizado, texto extraído parcialmente -->

## 3. Paleta de Colores

| Nombre       | Hex       | RGB                 | CMYK                  | Pantone        | Uso principal |
|---|---|---|---|---|---|
| Dorado Arena | `#D6B78D` | R:214 G:183 B:141   | C:0 M:15 Y:34 K:16    | Pantone 728 C  | Color primario cálido, fondos y detalles |
| Azul Lavanda | `#7C90E5` | R:124 G:144 B:229   | C:46 M:37 Y:0 K:10    | Pantone 2715 C | Color primario frío, acento tecnológico |
| Negro Profundo | `#222524` | R:34 G:37 B:36     | C:8 M:0 Y:3 K:85      | Pantone Black 7 C | Fondos oscuros, texto principal |
| Blanco Humo  | `#F5F7F0` | R:245 G:247 B:240   | C:1 M:0 Y:3 K:3       | Pantone 663 C  | Fondos claros, espacios negativos |
| Lima Eléctrico | `#CCFF50` | R:204 G:255 B:80   | C:20 M:0 Y:69 K:0     | Pantone 375 C  | Acento energético, CTAs, elementos destacados |
| Café Topo    | `#9B8B78` | R:155 G:139 B:120   | C:0 M:10 Y:23 K:39    | Pantone 7530 C | Complementario, texto secundario |

### Usos de color
- **Primarios:** Dorado Arena + Azul Lavanda — identidad visual distintiva tech-humano
- **Fondos:** Negro Profundo (modo oscuro) / Blanco Humo (modo claro)
- **Acento:** Lima Eléctrico — botones, highlights, elementos interactivos
- **Texto y soporte:** Café Topo para jerarquías secundarias

## 4. Tipografía

### Tipografía de logo — Menseal Regular
- Uso exclusivo: wordmark del logotipo
- Carácter: moderna, geométrica

### Tipografía de slogan — Articular SF Regular
- Uso: slogan *"el epicentro de la tecnología"*, subtítulos, textos de apoyo
- Carácter: limpia, legible, tecnológica

### Fallbacks sugeridos
```
font-family: 'Menseal', 'Futura', 'Century Gothic', sans-serif;    /* logo/display */
font-family: 'Articular SF', 'SF Pro', 'Helvetica Neue', sans-serif; /* cuerpo    */
```

## 5. Elementos Gráficos / Patrones

- Símbolo de flechas en espejo como elemento gráfico standalone
- Composiciones de espacio negativo — formas geométricas limpias
- Paleta dual cálido/frío (dorado + azul) como recurso de contraste visual
- Acentos Lima Eléctrico para puntos de atención en composiciones oscuras

<!-- OCR: revisar — páginas de aplicaciones (pg 11-13) con imágenes referenciales -->

## 6. Tono & Voz

- **Tecnológico pero accesible** — tecnología al alcance de las personas
- **Moderno y directo** — sin tecnicismos innecesarios
- **Aspiracional** — transmite estar en el centro de lo que importa
- Evitar: lenguaje excesivamente corporativo; comunicación fría sin conexión humana

## 7. Aplicaciones

- **Señalética:** fondo negro profundo, wordmark en blanco/dorado
- **Redes sociales:** composiciones oscuras con acento Lima Eléctrico
- **Web:** modo oscuro (fondo `#222524`) con acentos `#7C90E5` y `#CCFF50`
- **Papelería:** fondo blanco humo, logo en negro profundo
- **Packaging / digital displays:** fondos oscuros con degradado dorado-azul

## 8. Restricciones / NO Hacer

- ❌ No alterar las proporciones del símbolo de flechas
- ❌ No usar colores fuera de la paleta de 6 colores autorizados
- ❌ No combinar Menseal con tipografías decorativas ajenas a la marca
- ❌ No usar el Lima Eléctrico (`#CCFF50`) como color de fondo principal — solo acento
- ❌ No eliminar el espacio negativo del símbolo en versiones reducidas

## 9. Tokens CSS Sugeridos

```css
/* === Plaza Madero — Design Tokens === */
/* Sub-marca de Grupo Ortiz. En cabeceras corporativas, --go-* manda. */

--pm-dorado:         #D6B78D;
--pm-azul:           #7C90E5;
--pm-negro:          #222524;
--pm-blanco-humo:    #F5F7F0;
--pm-lima:           #CCFF50;
--pm-cafe:           #9B8B78;

/* Tipografía */
--pm-font-display:   'Menseal', 'Futura', 'Century Gothic', sans-serif;
--pm-font-body:      'Articular SF', 'SF Pro', 'Helvetica Neue', sans-serif;

/* Superficies */
--pm-surface-dark:   #222524;
--pm-surface-light:  #F5F7F0;
--pm-accent:         #CCFF50;

/* Esquinas */
--pm-radius:         4px;  /* ligeramente redondeado — tech moderno */
```

## 10. Checklist de Uso (para IA/Agente)

- [ ] ¿El tagline presente es *"el epicentro de la tecnología"*?
- [ ] ¿Se respeta la dualidad cálido/frío (dorado + azul) en la composición?
- [ ] ¿El Lima Eléctrico (`#CCFF50`) se usa como acento, no como fondo dominante?
- [ ] ¿La tipografía del logo es Menseal y el slogan/cuerpo usa Articular SF?
- [ ] ¿El símbolo de flechas mantiene su espacio negativo intacto?
- [ ] ¿En modo oscuro, el fondo base es `#222524`?
- [ ] ¿En piezas mixtas con Grupo Ortiz, GO aparece como marca madre en cabecera?
- [ ] <!-- OCR: revisar → validar colores exactos contra PDF original pg 10 -->
