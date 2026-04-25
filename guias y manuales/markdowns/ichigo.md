---
marca: "Ichigo — Agencia Creativa"
slug: "ichigo"
fuente_pdf: "Ichigo - Manual de identidad.pdf"
paginas_fuente: 6
version: "1.0"
fecha_extraccion: "2026-04-25"
aplica_a: ["pdf","reporte","presentacion","web","email","packaging"]
---

# Ichigo — Agencia Creativa — Manual de Marca

## 1. Esencia & Posicionamiento

**Ichigo** es la agencia creativa de Grupo Ortiz. Su identidad visual refleja creatividad audaz, enfoque digital y producción de contenido para marcas. Es la voz creativa interna del ecosistema GO.

**Descriptor:** Agencia Creativa  
**Posicionamiento:** Creatividad estratégica al servicio de marcas y negocios digitales

## 2. Logo

### Identificador principal
- Logotipo: isotipo + wordmark **"ichigo"** en minúsculas + descriptor "AGENCIA CREATIVA"
- Presenta versión horizontal y variantes de composición

### Versiones del logotipo
- Completo: isotipo + "ichigo" + "AGENCIA CREATIVA"
- Reducido: isotipo + "ichigo" (sin descriptor)
- Solo isotipo para usos en perfil / icono

### Restricciones del logo
- **Opacidad:** no reducir la opacidad del logotipo
- **Rotación:** no rotar el logo
- **Deformación:** no distorsionar proporciones
- **Sombra:** no aplicar drop shadow ni efectos de sombra
- **Omisión:** no usar el wordmark sin el isotipo en aplicaciones principales
- **Cambio de color:** no usar fuera de la paleta autorizada

## 3. Paleta de Colores

| Nombre         | Hex       | RGB              | CMYK                  | Uso principal |
|---|---|---|---|---|
| Amarillo Limón | `#FFD72E` | R:255 G:215 B:46 | C:1 M:14 Y:86 K:0     | Color primario, acento energético y creativo |
| Verde Selva    | `#236D2D` | R:35 G:109 B:45  | C:85 M:32 Y:100 K:22  | Color secundario, profundidad y estabilidad |
| Negro Grafito  | `#282828` | R:40 G:40 B:40   | C:72 M:63 Y:58 K:73   | Fondo principal, texto, fondos oscuros |

### Usos de color
- **Primario:** Amarillo Limón — destacado, CTAs, detalles llamativos, acento sobre negro
- **Secundario:** Verde Selva — equilibrio, naturaleza, contraste con amarillo
- **Base:** Negro Grafito — fondos principales, fondos de pantalla, modo oscuro nativo
- La combinación **negro + amarillo** es la combinación identitaria principal de Ichigo

## 4. Tipografía

### Tipografía principal — ITC Avant Garde Book
- Uso: encabezados, títulos
- Carácter: geométrica, moderna, icónica — referencias al diseño gráfico clásico
- Estilo: Book (regular)

### Tipografía secundaria — ITC Avant Garde Bold
- Uso: subtítulos y cuerpo de texto donde se requiere más peso
- Carácter: misma familia, mayor contundencia

### Fallbacks sugeridos
```
font-family: 'ITC Avant Garde', 'Futura', 'Century Gothic', sans-serif;  /* títulos  */
font-family: 'ITC Avant Garde', 'Gill Sans', Arial, sans-serif;           /* cuerpo   */
```

## 5. Elementos Gráficos / Patrones

- Identidad visual limpia y geométrica — inspirada en diseño de agencia digital
- Composiciones con alto contraste negro/amarillo
- Uso de íconos simples y líneas limpias
- Referencias visuales: posts para redes, banners digitales, identidad de agencia

<!-- OCR: revisar — página 6 de referencias visuales muestra ejemplos de aplicación en redes, extraído parcialmente -->

## 6. Tono & Voz

- **Creativo y directo** — sin rodeos, con personalidad
- **Profesional pero dinámico** — agencia que conoce los medios digitales
- **Audaz** — dispuesto a proponer ideas disruptivas
- Evitar: tono corporativo genérico; exceso de formalidad; lenguaje anticuado

## 7. Aplicaciones

- **Redes sociales:** fondo negro, tipografía Avant Garde, acentos amarillo — posts, historias, portadas
- **Presentaciones para clientes:** modo oscuro nativo (`#282828`), títulos en amarillo, cuerpo en blanco
- **Identidad digital:** favicon/icono con isotipo sobre negro o amarillo
- **Material impreso:** tarjetas de presentación negro mate, detalles amarillo lámina
- **Propuestas creativas:** documento negro + amarillo, tipografía limpia, imágenes de alta calidad

## 8. Restricciones / NO Hacer

- ❌ No aplicar opacidad al logo
- ❌ No rotar el logo en ningún ángulo
- ❌ No deformar el isotipo o el wordmark
- ❌ No agregar sombras o efectos al logotipo
- ❌ No omitir el isotipo en aplicaciones principales
- ❌ No usar colores fuera de la paleta de 3 colores autorizados
- ❌ No usar tipografías con serifa — rompen el carácter geométrico de Avant Garde

## 9. Tokens CSS Sugeridos

```css
/* === Ichigo Agencia Creativa — Design Tokens === */
/* Sub-marca de Grupo Ortiz. En cabeceras corporativas, --go-* manda. */

--ichigo-amarillo:    #FFD72E;
--ichigo-verde:       #236D2D;
--ichigo-negro:       #282828;
--ichigo-blanco:      #FFFFFF;  /* texto sobre negro */

/* Superficies */
--ichigo-surface:     #282828;  /* fondo nativo — modo oscuro */
--ichigo-accent:      #FFD72E;  /* amarillo como acento primario */
--ichigo-accent-alt:  #236D2D;  /* verde como acento secundario */

/* Tipografía */
--ichigo-font-display: 'ITC Avant Garde', 'Futura', 'Century Gothic', sans-serif;
--ichigo-font-body:    'ITC Avant Garde', 'Gill Sans', Arial, sans-serif;
--ichigo-font-weight-title: 400;   /* Book */
--ichigo-font-weight-sub:   700;   /* Bold */

/* Esquinas */
--ichigo-radius:      0px;  /* esquinas rectas — estilo geométrico */
```

## 10. Checklist de Uso (para IA/Agente)

- [ ] ¿El fondo base es Negro Grafito (`#282828`)?
- [ ] ¿El Amarillo Limón (`#FFD72E`) se usa como acento principal sobre negro?
- [ ] ¿Los títulos están en ITC Avant Garde Book?
- [ ] ¿El logo incluye isotipo + wordmark "ichigo" + "AGENCIA CREATIVA" en aplicaciones primarias?
- [ ] ¿Se evitan: opacidad, rotación, deformación, sombras, cambios de color en el logo?
- [ ] ¿El tono es creativo, directo y dinámico — no corporativo genérico?
- [ ] ¿En piezas mixtas con Grupo Ortiz, GO aparece como marca madre en cabecera?
