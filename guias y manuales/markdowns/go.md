---
marca: "Grupo Ortiz"
slug: "go"
fuente_pdf: "MANUAL DE MARCA_GO_V3 2.pdf"
paginas_fuente: 14
version: "1.0"
fecha_extraccion: "2026-04-25"
aplica_a: ["pdf","reporte","presentacion","web","email","packaging"]
---

# Grupo Ortiz — Manual de Marca

## 1. Esencia & Posicionamiento

Desde su fundación en **1959**, Grupo Ortiz® se ha caracterizado por una cultura basada en la innovación, creatividad y valores fundamentales como el amor, la integridad y la excelencia. Se consideran una familia, comprometida en hacer lo correcto y en mantener altos estándares en todo lo que hacen. La excelencia no solo define sus productos, sino también quiénes son como organización.

Este manual asegura el uso coherente de los elementos visuales y comunicativos de la marca, manteniendo uniformidad en logotipos, tipografías y colores en todas las plataformas y medios.

**Valores de marca:** Innovación · Creatividad · Amor · Integridad · Excelencia

## 2. Logo

### Identificador principal
- Logotipo wordmark "grupo ortiz" + isotipo (símbolo independiente)
- Se presentan en versión **positivo** (sobre fondo claro) y **negativo** (sobre fondo oscuro/naranja)

### Usos correctos
- Fondo blanco con logo en naranja/gris oscuro
- Fondo naranja con logo en blanco
- Fondo gris oscuro con logo en naranja/blanco

### Restricciones del logo
- **NO deformar** — no estirar ni comprimir
- **NO rotar** — siempre en posición horizontal
- **NO cambiar color** — solo paleta corporativa autorizada
- **NO delinear** — sin stroke ni contorno añadido

### Degradados de fondo autorizados
- `#262626` → `#535353` (gris oscuro a gris)
- `#FB670B` → `#FF9D43` (naranja a naranja claro)

## 3. Paleta de Colores

| Nombre       | Hex       | RGB               | CMYK                  | Pantone     | Uso principal |
|---|---|---|---|---|---|
| Naranja      | `#FB670B` | R:251 G:103 B:11  | C:0 M:70 Y:93 K:0     | Pantone 1585 | Color primario, fondos y títulos destacados |
| Gris Oscuro  | `#262626` | R:38 G:38 B:38    | C:73 M:63 Y:59 K:75   | Pantone 419  | Color primario, fondos principales |
| Gris         | `#535353` | R:83 G:83 B:83    | C:61 M:51 Y:49 K:44   | Pantone 445  | Color secundario, gráficos y acentos |
| Gris Claro   | `#C5C5C5` | R:197 G:197 B:197 | C:26 M:19 Y:29 K:2    | Pantone 1585 | Color secundario, fondos complementarios |
| Blanco       | `#FFFFFF`  | R:255 G:255 B:255 | C:0 M:0 Y:0 K:0       | —           | Texto principal, fondos neutros |
| Naranja Claro| `#FF9D43` | —                 | —                     | —           | Degradado, uso decorativo |

### Usos de color
- **Color primario:** Naranja y Gris Oscuro — fondos principales, títulos destacados y elementos clave
- **Color secundario:** Gris y Gris Claro — complemento en fondos, gráficos y acentos
- **Color de textos:** Blanco y Gris Oscuro — cuerpos principales, subtítulos y párrafos largos
- **Colores complementarios:** Naranja y Blanco — íconos, botones, bordes y textos decorativos

## 4. Tipografía

### Tipografía principal — Morganite Extra Bold
- Uso: títulos, encabezados y elementos destacados
- Estilo: **solo mayúsculas**
- Carácter: moderna, elegante, personalidad fuerte
- Soporte: A B C D E F G H I J K L M N Ñ O P Q R S T U V W X Y Z

### Tipografía secundaria — Helony
- Uso: textos largos, subtítulos, cuerpo de texto
- Soporte: mayúsculas y minúsculas completas con Ñ
- Carácter: legible, equilibrada, complementa a Morganite

### Fallbacks sugeridos
```
font-family: 'Morganite', 'Impact', 'Arial Narrow', sans-serif;   /* títulos */
font-family: 'Helony', 'Helvetica Neue', 'Arial', sans-serif;     /* cuerpo  */
```

## 5. Elementos Gráficos / Patrones

- Degradados de color sobre fotografías (mapa de degradado naranja o gris)
- Fotografías de aplicaciones industriales/comerciales con overlay de color
- Sin patrones de fondo complejos — enfoque en tipografía y color limpio

## 6. Tono & Voz

- **Formal pero cercano** — refleja la tradición familiar de 65+ años
- **Directo y claro** — sin ambigüedades en comunicación corporativa
- **Aspiracional** — transmite excelencia e innovación constante
- Evitar: lenguaje excesivamente técnico sin contexto; informalidad excesiva en piezas corporativas

## 7. Aplicaciones

- **Papelería corporativa:** fondo blanco con logo naranja/gris + degradados de fondo gris o naranja
- **Redes sociales:** composiciones con overlay naranja/gris sobre fotografía
- **Presentaciones:** paleta naranja-gris, Morganite en títulos, Helony en cuerpo
- **Web:** modo claro (fondo blanco, naranja como acento) o modo oscuro (fondo `#262626`, naranja activo)
- **Referencias visuales:** diseños de señalización, banners industriales, tarjetas corporativas

## 8. Restricciones / NO Hacer

- ❌ No deformar, rotar ni escalar el logo desproporcionalmente
- ❌ No cambiar colores del logo fuera de la paleta autorizada
- ❌ No agregar delineados, sombras ni efectos sobre el logotipo
- ❌ No usar tipografías distintas a Morganite/Helony en piezas de marca
- ❌ No usar Morganite en minúsculas en elementos de marca primarios
- ❌ No colocar el logo sobre fondos que comprometan el contraste mínimo

## 9. Tokens CSS Sugeridos

```css
/* === Grupo Ortiz — Design Tokens === */
/* Conviven con --go-* del sistema madre (ver context_design.md) */

--go-naranja:        #FB670B;
--go-naranja-claro:  #FF9D43;
--go-gris-oscuro:    #262626;
--go-gris:           #535353;
--go-gris-claro:     #C5C5C5;
--go-blanco:         #FFFFFF;

/* Degradados */
--go-grad-gris:      linear-gradient(135deg, #262626, #535353);
--go-grad-naranja:   linear-gradient(135deg, #FB670B, #FF9D43);

/* Tipografía */
--go-font-display:   'Morganite', 'Impact', 'Arial Narrow', sans-serif;
--go-font-body:      'Helony', 'Helvetica Neue', Arial, sans-serif;
--go-font-weight-display: 800;  /* Extra Bold */

/* Espaciado (hereda escala de context_design.md) */
--go-radius:         0px;  /* marca corporativa — esquinas rectas */
```

## 10. Checklist de Uso (para IA/Agente)

- [ ] ¿El color principal usado es `#FB670B` (naranja) o `#262626` (gris oscuro)?
- [ ] ¿Los títulos están en Morganite Extra Bold, en MAYÚSCULAS?
- [ ] ¿El cuerpo de texto usa Helony o su fallback?
- [ ] ¿El logo aparece solo en sus versiones positivo/negativo autorizadas?
- [ ] ¿Se evitan degradados no documentados (solo gris↔gris o naranja↔naranja claro)?
- [ ] ¿Las fotografías llevan overlay de color corporativo?
- [ ] ¿Se respetan las restricciones de NO deformar / NO rotar / NO recolorear logo?
- [ ] En cabeceras corporativas y firmas: ¿GO manda sobre sub-marcas? (ver `brand_system.md`)
