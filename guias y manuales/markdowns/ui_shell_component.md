# GO UI Shell — Componente Reutilizable

> Version: 1.0 | Fecha: 2026-05-22 | Aplica a: web
> Fuente: multi_mkt_study_v2 — static/index.html + static/css/style.css

## Proposito

Shell UI estandar para aplicaciones web del ecosistema Grupo Ortiz. Inspirado en skywork.ai. Consiste en:

1. **Topbar** full-width sticky (56px) con logo, breadcrumb, busqueda, usuario
2. **Sidebar** colapsable (248px → 64px) con SVG icons + texto
3. **Main content** area con transicion suave de margen

## Reglas de implementacion

1. **Brand en topbar solamente.** No duplicar logo en sidebar.
2. **SVG icons** inline, 20x20 viewBox, `stroke="currentColor"`, `stroke-width="1.5"`, `stroke-linecap="round"`, `stroke-linejoin="round"`.
3. **Iconos NO se mueven al colapsar.** Solo el texto desaparece con fade. Cero cambios de `justify-content`, `margin`, `padding` en el link activo durante colapso.
4. **Indicador activo colapsado:** `box-shadow: inset 3px 0 0 var(--go-accent)` + color del icono cambia a accent. Sin background. Sin cambios de layout.
5. **Altura chat:** usar flex fill (`height: 100%`), NUNCA `calc(100vh - <magic number>)`.
6. **Colores error dark mode:** siempre con opacidad (`rgba(220,38,38,0.12)`), nunca colores solidos claros.

## CSS Variables requeridas

```css
:root {
  --sidebar-w: 248px;
  --sidebar-collapsed: 64px;
  --topbar-h: 56px;
  --font-heading: 'Blauer Nue', system-ui, sans-serif;
  --go-text-3: #5F5E58; /* modo claro */
  /* dark mode: --go-text-3: #5F5E58; */
}
```

## Estructura HTML

```html
<a href="#main-content" class="skip-link">Ir al contenido</a>

<header class="topbar" role="banner">
  <div class="topbar-left">
    <button class="topbar-toggle" id="sidebar-toggle" aria-label="Colapsar menu" aria-expanded="true" aria-controls="sidebar">
      <svg width="18" height="18" viewBox="0 0 18 18" fill="none" stroke="currentColor" stroke-width="1.5">
        <line x1="2" y1="4" x2="16" y2="4"/><line x1="2" y1="9" x2="16" y2="9"/><line x1="2" y1="14" x2="16" y2="14"/>
      </svg>
    </button>
    <div class="topbar-brand">GO <em>MI</em> v2</div>
    <nav class="topbar-breadcrumb" id="view-title">Dashboard</nav>
  </div>
  <div class="topbar-right">
    <input type="search" id="global-search" class="topbar-search" placeholder="Buscar..." aria-label="Busqueda global">
    <span id="header-user" class="topbar-user"></span>
    <button class="topbar-logout" onclick="window.logout()">Salir</button>
  </div>
</header>

<div class="app-layout">
  <aside class="sidebar" id="sidebar" role="navigation" aria-label="Navegacion principal">
    <ul class="sidebar-nav">
      <!-- Items con SVG icons inline -->
    </ul>
    <div class="sidebar-footer">...</div>
  </aside>
  <main class="main" id="main-content" role="main"></main>
</div>
```

## SVG Icons Catalog

| Vista | SVG path |
|-------|----------|
| Dashboard | 4-rect grid 2x2 |
| Productos | Folder with tab |
| Competidores | Crosshair/target circles |
| Insights IA | 4-point star |
| Encuestas | Clipboard with lines |
| Reportes | 3-bar ascending chart |
| Simulacion | Play triangle |
| Chat | Chat bubble with tail |
| Admin | Gear/settings circle |

Todos: `viewBox="0 0 20 20"` con paths estandar.

## Scripts JS requeridos

```javascript
// Sidebar collapse toggle + state restore
(function() {
  var sidebar = document.getElementById('sidebar');
  var toggle = document.getElementById('sidebar-toggle');
  if (localStorage.getItem('sidebar_collapsed') === 'true') {
    sidebar.classList.add('collapsed');
    toggle.setAttribute('aria-expanded', 'false');
  }
  toggle.addEventListener('click', function() {
    var collapsed = sidebar.classList.toggle('collapsed');
    localStorage.setItem('sidebar_collapsed', collapsed);
    toggle.setAttribute('aria-expanded', !collapsed);
    setTimeout(function() { window.dispatchEvent(new Event('resize')); }, 250);
  });
})();

window.logout = function() {
  localStorage.clear();
  document.cookie = 'csrf_token=; Path=/; Max-Age=0; SameSite=Lax';
  window.location.replace('/login');
};
```

## Accesibilidad minima

- `skip-link` como primer hijo del body
- `:focus-visible` con outline naranja 2px
- `aria-current="page"` en link activo del sidebar
- `role="banner"` en topbar, `role="navigation"` en sidebar, `role="main"` en content
- `aria-label` en busqueda y toggle
- `aria-expanded` + `aria-controls` en boton de colapso

## Proyectos que usan este shell

| Proyecto | Estado |
|----------|--------|
| multi_mkt_study_v2 | Implementado 2026-05-22 |
| ventas_rafias_go | Semilla creada, pendiente aplicar |
| automatizacion ventas sacos | Semilla creada, pendiente aplicar |

## Changelog

- 2026-05-22 — v1.0 extraido de multi_mkt_study_v2
