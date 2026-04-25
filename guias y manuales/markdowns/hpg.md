---
marca: "HPG — Hotel Punta Galería"
slug: "hpg"
fuente_pdf: "Manual de marca HPG.pdf"
paginas_fuente: 11
version: "1.0"
fecha_extraccion: "2026-04-25"
aplica_a: ["pdf","reporte","presentacion","web","email","packaging"]
---

# HPG — Hotel Punta Galería — Manual de Marca

## 1. Esencia & Posicionamiento

**Hotel Punta Galería** es una marca de hospitalidad con identidad visual orgánica y natural. Transmite elegancia discreta, conexión con la naturaleza y experiencias de bienestar en *ubicación privilegiada*.

**Web:** www.hotelpuntagaleria.com.mx  
**Contacto:** 443 314 08 36  
**Promesa de marca:** "disfruta de nuestra ubicación privilegiada"

<!-- OCR: revisar — portada y secciones de posicionamiento 100% vectorizadas, texto no extraíble -->

## 2. Logo

### Identificador principal
- Logotipo con nombre **"Klinta Galería"** <!-- OCR: revisar — posible lectura incorrecta del isotipo, confirmar contra PDF pg 1 -->
- Integra elementos visuales naturales (ramas, hojas, formas orgánicas)
- Se presenta en versiones positivo y negativo

### Versiones detectadas
- Logo completo con isotipo + wordmark
- Aplicaciones sobre fondos claros (arena/hueso) y fondos oscuros (verde profundo)

<!-- OCR: revisar — páginas 3-6 solo contienen el logo sin texto legible; confirmar variantes contra PDF original -->

## 3. Paleta de Colores

| Nombre          | Hex       | RGB               | CMYK                    | Pantone (aprox.)  | Uso principal |
|---|---|---|---|---|---|
| Verde Oliva      | `#838c2f` | R:131 G:140 B:47  | C:6 M:0 Y:66 K:45       | Pantone 5777 C    | Color primario, identidad natural |
| Verde Oscuro     | `#626c1f` | R:98 G:108 B:31   | C:9 M:0 Y:71 K:58       | Pantone 582 C     | Variante oscura del primario |
| Verde Bosque     | `#236d00` | R:35 G:109 B:0    | C:68 M:0 Y:100 K:57     | Pantone 364 C     | Acento profundo, elementos destacados |
| Azul Pizarra     | `#323f48` | R:50 G:63 B:72    | C:31 M:13 Y:0 K:72      | Pantone 7546 C    | Fondos oscuros, texto sobre claro |
| Arena Claro      | `#e5e0d8` | R:229 G:224 B:216 | C:0 M:2 Y:6 K:10        | Pantone 7527 U    | Fondos principales, papel, superficies |
| Arena Medio      | `#c7b7a4` | R:199 G:183 B:164 | C:0 M:8 Y:18 K:22       | Pantone 7527 C    | Complementario, texturas, bordes |

### Usos de color
- **Primarios:** Verde Oliva + Arena Claro — identidad natural y cálida
- **Oscuros:** Verde Oscuro + Azul Pizarra — fondos nocturnos, cabeceras
- **Acento:** Verde Bosque — puntos focales, CTAs, detalles
- **Soporte:** Arena Medio — separadores, fondos de tarjeta, texturas

## 4. Tipografía

### Tipografía principal — Brisbane Semibold
- Uso: encabezados, títulos
- Estilo: kerning `-20` (comprimido)
- Carácter: elegante, serif moderna con personalidad

### Tipografía secundaria — Salford Sans VF Family
- Uso: cuerpos de texto, subtítulos
- Carácter: sans-serif variable, alta legibilidad en cuerpo

### Fallbacks sugeridos
```
font-family: 'Brisbane', 'Cormorant Garamond', 'Georgia', serif;        /* títulos  */
font-family: 'Salford Sans', 'Lato', 'Helvetica Neue', sans-serif;      /* cuerpo   */
```

## 5. Elementos Gráficos / Patrones

- Ilustraciones orgánicas con ramas, hojas y formas naturales
- Texturas de papel y arena como fondos de superficie
- Composiciones con espacio respirable — estilo editorial hospitalidad de lujo
- Fotografía de interiores y exteriores del hotel con tratamiento cálido

<!-- OCR: revisar — página 9 contiene referencias visuales con ilustraciones, extraídas solo parcialmente -->

## 6. Tono & Voz

- **Sereno y evocador** — invita al descanso y la experiencia
- **Elegante sin ser distante** — hospitalidad cálida de alta gama
- **Descriptivo y sensorial** — menciona entorno, naturaleza, privilegio de ubicación
- Evitar: lenguaje corporativo frío; exceso de tecnicismos; tono de urgencia comercial

## 7. Aplicaciones

- **Señalética del hotel:** fondos arena/hueso con tipografía Brisbane en verde
- **Material impreso (menús, tarjetas, folletería):** papel texturizado, paleta arena-verde
- **Redes sociales:** fotografías cálidas con overlay sutil verde o arena
- **Web:** fondo `#e5e0d8` (claro) o `#323f48` (oscuro), tipografía legible en Salford Sans
- **Email marketing:** cabecera con logo + paleta arena, cuerpo en Salford Sans
- **Packaging amenidades:** verde oliva + arena, logo centrado

## 8. Restricciones / NO Hacer

- ❌ No usar la paleta de colores fuera del espectro verde-arena-pizarra
- ❌ No mezclar con colores llamativos ajenos (neones, rojos primarios, amarillos brillantes)
- ❌ No usar Brisbane en pesos ligeros para títulos — mantener Semibold
- ❌ No comprimir la tipografía más allá del kerning `-20` establecido
- ❌ No usar fondos con texturas digitales o patrones industriales — contrasta con la identidad natural

## 9. Tokens CSS Sugeridos

```css
/* === Hotel Punta Galería — Design Tokens === */
/* Sub-marca de Grupo Ortiz. En cabeceras corporativas, --go-* manda. */

--hpg-verde-oliva:    #838c2f;
--hpg-verde-oscuro:   #626c1f;
--hpg-verde-bosque:   #236d00;
--hpg-azul-pizarra:   #323f48;
--hpg-arena-claro:    #e5e0d8;
--hpg-arena-medio:    #c7b7a4;

/* Superficies */
--hpg-surface-light:  #e5e0d8;
--hpg-surface-dark:   #323f48;
--hpg-text-primary:   #323f48;
--hpg-text-inverse:   #e5e0d8;

/* Tipografía */
--hpg-font-display:   'Brisbane', 'Cormorant Garamond', Georgia, serif;
--hpg-font-body:      'Salford Sans', Lato, 'Helvetica Neue', sans-serif;
--hpg-letter-spacing-display: -0.02em;  /* kerning -20 */

/* Esquinas */
--hpg-radius:         2px;  /* casi recto — estilo editorial */
```

## 10. Checklist de Uso (para IA/Agente)

- [ ] ¿La paleta se mantiene dentro del espectro verde-arena-pizarra?
- [ ] ¿Los títulos usan Brisbane Semibold con kerning negativo?
- [ ] ¿El cuerpo de texto usa Salford Sans VF?
- [ ] ¿Las imágenes tienen tratamiento cálido (tonos arena/verde)?
- [ ] ¿Se evitan colores ajenos a la identidad natural del hotel?
- [ ] ¿El tono de comunicación es sereno y evocador, no comercial-agresivo?
- [ ] ¿En piezas mixtas con Grupo Ortiz, GO aparece como marca madre en cabecera?
- [ ] <!-- OCR: revisar → confirmar nombre exacto del logotipo (pg 1) contra PDF original -->
- [ ] <!-- OCR: revisar → validar variantes de logo (pgs 3-6) contra PDF original -->
