---
version: "1.1"
fecha: "2026-05-22"
aplica_a: ["web"]
fuente_canonica: "multi_mkt_study_v2 + ventas_rafias_go"
componentes: ["topbar", "sidebar-colapsable", "main"]
---

# GO UI Shell — Componente Reutilizable

> Shell UI estandar para web del ecosistema Grupo Ortiz. Inspirado en skywork.ai / Linear / Stripe.
> v1.1: sidebar colapsable como componente plug-and-play, listo para reciclar 100% en cualquier proyecto GO.
> Fuentes: `multi_mkt_study_v2/static/` + `ventas_rafias_go/rafias-agent/api/static/`

## Quick Start — adoptar en proyecto nuevo (3 pasos)

1. Pegar bloque CSS (seccion 4) en `static/css/<tu>.css` — modulo dedicado o append
2. Agregar HTML del sidebar (seccion 3) al template + invocar JS de toggle (seccion 5)
3. Definir array `navItems` con tus rutas y mapear a SVG icons del catalogo (seccion 6)

Listo. El sidebar es responsive, accesible, persiste estado y emite eventos para charts.

---

## 1. Proposito

Shell visual + interaccion consistente entre proyectos:

| Componente | Estado | Donde |
|---|---|---|
| **Topbar sticky** | v1.0 | Recomendado, opcional si proyecto tiene header propio |
| **Sidebar colapsable** | v1.1 | **OBLIGATORIO** para apps con navegacion entre vistas |
| **Main content** | v1.0 | Implicito, ancho via grid o flex |
| **Skip link** | v1.0 | Accesibilidad |

---

## 2. Reglas de adopcion (NO violar)

| Regla | Por que |
|---|---|
| Brand SOLO en topbar | No duplicar logo en sidebar |
| Iconos SVG 20x20 stroke 1.5 round | Consistencia visual cross-proyecto |
| Iconos NO se mueven al colapsar | Solo el `.nav-label` fade-out. Cero shift en `gap`, `margin`, `padding` |
| Activo expandido: naranja solido | `background: var(--go-orange); color: #fff` |
| Activo colapsado: transparent + box-shadow inset | `box-shadow: inset 3px 0 0 var(--accent)`. Sin background. Sin shift |
| Altura usa flex fill | NUNCA `calc(100vh - <magic number>)` |
| Errores dark mode con opacidad | `rgba(220,38,38,0.12)`, NO colores solidos claros |
| Anchors `<a>` no buttons en nav | Comportamiento navegacion estandar + SEO |
| Estado en `localStorage` | Key: `sidebar_collapsed` (string `'1'` / `'0'`) |
| Toggle dispatch `resize` | Charts/widgets dependientes del ancho se re-pintan |

---

## 3. HTML — estructura base

### Container app (puede usar grid O flex+position-fixed)

```html
<!-- Opcion A: flex + position-fixed (multi_mkt_study_v2) -->
<div class="app-layout">
  <aside class="sidebar" id="sidebar" role="navigation" aria-label="Navegacion principal">
    <!-- contenido inyectado por JS — ver "Render template" -->
  </aside>
  <main class="main" id="main-content" role="main"></main>
</div>

<!-- Opcion B: grid (ventas_rafias_go) -->
<!-- #sidebar y #content son grid-areas, el ancho se controla via --sidebar-w -->
```

### Sidebar render template (JS injecta)

```html
<aside class="sidebar" id="sidebar" role="navigation" aria-label="Navegacion principal">
  <!-- Boton plegar/expandir — chevron rota 180deg al colapsar -->
  <button class="sidebar-collapse-btn" id="sidebar-collapse-btn"
          type="button" aria-label="Plegar menu" aria-expanded="true" aria-controls="sidebar">
    <svg width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="currentColor"
         stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
      <polyline points="15 18 9 12 15 6"/>
    </svg>
  </button>

  <ul class="sidebar-nav">
    <li><a href="#/dashboard" data-view="dashboard" data-label="Dashboard"
           class="active" aria-current="page" title="Dashboard">
      <span class="nav-icon" aria-hidden="true"><!-- SVG --></span>
      <span class="nav-label">Dashboard</span>
    </a></li>
    <!-- ...mas items -->
  </ul>

  <!-- Footer opcional, NO obligatorio. Si no se usa, omitir. -->
  <div class="sidebar-footer">
    <!-- Cualquier contenido — branding, version, links — segun proyecto -->
  </div>
</aside>
```

### Topbar (opcional — si proyecto tiene header propio compatible, omitir)

```html
<header class="topbar" role="banner">
  <div class="topbar-left">
    <button class="topbar-toggle" id="sidebar-toggle" aria-label="Colapsar menu"
            aria-expanded="true" aria-controls="sidebar">
      <svg width="18" height="18" viewBox="0 0 18 18" fill="none" stroke="currentColor" stroke-width="1.5">
        <line x1="2" y1="4" x2="16" y2="4"/>
        <line x1="2" y1="9" x2="16" y2="9"/>
        <line x1="2" y1="14" x2="16" y2="14"/>
      </svg>
    </button>
    <div class="topbar-brand">GO <em>{proyecto}</em></div>
    <nav class="topbar-breadcrumb" id="view-title">Dashboard</nav>
  </div>
  <div class="topbar-right">
    <input type="search" id="global-search" class="topbar-search"
           placeholder="Buscar..." aria-label="Busqueda global">
    <span id="header-user" class="topbar-user"></span>
    <button class="topbar-logout" onclick="window.logout()">Salir</button>
  </div>
</header>
```

---

## 4. CSS — bloque completo copy-paste

```css
/* ── Variables base — extender de context_design.md GO ─────────────────── */
:root {
  --sidebar-w: 248px;
  --sidebar-collapsed: 64px;
  --topbar-h: 56px;
  --font-display: 'Blauer Nue', system-ui, sans-serif;
  /* Tokens GO esperados: --go-orange (#FB670B), --go-black, --go-white,
     --go-orange-tint (rgba(251,103,11,0.10)), --accent, --accent-tint,
     --shadow-lg */
}

/* ── Sidebar container ─────────────────────────────────────────────────── */
.sidebar {
  width: var(--sidebar-w);
  background: var(--go-black);
  color: var(--go-white);
  border-right: 1px solid rgba(255,255,255,0.06);
  padding: 16px 12px;
  position: fixed; /* Opcion A. Para grid: omitir position+top+left+bottom */
  top: var(--topbar-h); left: 0; bottom: 0;
  z-index: 100;
  display: flex; flex-direction: column;
  overflow-x: hidden; overflow-y: auto;
  transition: width 220ms cubic-bezier(0.4, 0, 0.2, 1);
}

.sidebar.collapsed { width: var(--sidebar-collapsed); }

/* ── Boton plegar/expandir ─────────────────────────────────────────────── */
.sidebar-collapse-btn {
  width: 28px; height: 28px;
  border-radius: 6px;
  background: transparent;
  border: 1px solid rgba(255,255,255,0.12);
  color: rgba(255,255,255,0.55);
  cursor: pointer;
  display: inline-flex; align-items: center; justify-content: center;
  margin: 0 0 10px;
  align-self: flex-end;
  transition: color 180ms cubic-bezier(0.4,0,0.2,1),
              border-color 180ms cubic-bezier(0.4,0,0.2,1),
              background 180ms cubic-bezier(0.4,0,0.2,1),
              transform 220ms cubic-bezier(0.4,0,0.2,1);
}
.sidebar-collapse-btn:hover {
  color: var(--accent, var(--go-orange));
  border-color: var(--accent, var(--go-orange));
  background: var(--accent-tint, rgba(251,103,11,0.10));
}
.sidebar-collapse-btn:focus-visible {
  outline: 2px solid var(--accent, var(--go-orange));
  outline-offset: 2px;
}
.sidebar.collapsed .sidebar-collapse-btn {
  transform: rotate(180deg);
  align-self: center;
}

/* ── Nav list ──────────────────────────────────────────────────────────── */
.sidebar-nav { list-style: none; flex: 1; padding: 0; margin: 0; }
.sidebar-nav li { margin-bottom: 4px; }

.sidebar-nav a {
  display: flex; align-items: center; gap: 12px;
  padding: 8px 12px;
  border-radius: 8px;
  color: rgba(255,255,255,0.7);
  font-family: var(--font-display);
  font-size: 14px; font-weight: 500;
  text-decoration: none;
  white-space: nowrap;
  transition: color 180ms cubic-bezier(0.4,0,0.2,1),
              background 180ms cubic-bezier(0.4,0,0.2,1);
}
.sidebar-nav a:hover {
  background: var(--accent-tint, rgba(251,103,11,0.10));
  color: var(--accent, var(--go-orange));
}
.sidebar-nav a.active {
  background: var(--go-orange, var(--accent));
  color: #fff;
  font-weight: 600;
}
.sidebar-nav a.active[aria-current="page"] { font-weight: 600; }

/* ── Icon + label ──────────────────────────────────────────────────────── */
.nav-icon {
  display: inline-flex; align-items: center; justify-content: center;
  width: 20px; height: 20px;
  flex-shrink: 0;
  opacity: 0.7;
  transition: opacity 180ms cubic-bezier(0.4,0,0.2,1);
}
.sidebar-nav a.active .nav-icon { opacity: 1; }
.nav-icon svg { width: 20px; height: 20px; display: block; }

.nav-label { transition: opacity 150ms ease; }

/* ── Estado colapsado ──────────────────────────────────────────────────── */
.sidebar.collapsed .sidebar-nav a {
  gap: 0;
  justify-content: center;
  padding: 10px 0;
}
.sidebar.collapsed .sidebar-nav a.active {
  background: transparent;
  color: var(--accent, var(--go-orange));
  box-shadow: inset 3px 0 0 var(--accent, var(--go-orange));
}
.sidebar.collapsed .sidebar-nav a.active .nav-icon {
  opacity: 1;
  color: var(--accent, var(--go-orange));
}
.sidebar.collapsed .nav-label {
  opacity: 0;
  width: 0;
  overflow: hidden;
  display: inline-block;
  transition: opacity 120ms ease, width 0ms 120ms;
}

/* ── Tooltip colapsado al hover ────────────────────────────────────────── */
.sidebar.collapsed .sidebar-nav a { position: relative; }
.sidebar.collapsed .sidebar-nav a:hover::after {
  content: attr(data-label);
  position: absolute;
  left: calc(var(--sidebar-collapsed) + 10px);
  top: 50%;
  transform: translateY(-50%);
  background: var(--go-black);
  color: #fff;
  padding: 5px 11px;
  border-radius: 6px;
  font-size: 12px;
  font-weight: 600;
  white-space: nowrap;
  z-index: 300;
  pointer-events: none;
  box-shadow: var(--shadow-lg, 0 8px 32px rgba(0,0,0,0.50));
  border: 1px solid rgba(255,255,255,0.08);
}

/* ── Footer opcional ───────────────────────────────────────────────────── */
.sidebar-footer {
  padding-top: 12px;
  border-top: 1px solid rgba(255,255,255,0.10);
  font-size: 12px;
  color: rgba(255,255,255,0.55);
}
.sidebar.collapsed .sidebar-footer {
  opacity: 0;
  pointer-events: none;
  transition: opacity 120ms ease;
}

/* ── Main content (Opcion A flex+position-fixed) ──────────────────────── */
.app-layout { display: flex; min-height: calc(100vh - var(--topbar-h)); }
.main {
  margin-left: var(--sidebar-w);
  flex: 1;
  min-height: calc(100vh - var(--topbar-h));
  padding: 20px 24px;
  transition: margin-left 220ms cubic-bezier(0.4, 0, 0.2, 1);
}
.sidebar.collapsed ~ .main { margin-left: var(--sidebar-collapsed); }

/* ── Accesibilidad ─────────────────────────────────────────────────────── */
.skip-link {
  position: fixed;
  top: -100px; left: 50%;
  transform: translateX(-50%);
  z-index: 9999;
  background: var(--go-orange, #FB670B);
  color: #fff;
  padding: 8px 20px;
  border-radius: 0 0 8px 8px;
  font-weight: 600;
  transition: top 150ms ease;
}
.skip-link:focus { top: 0; }

:focus-visible {
  outline: 2px solid var(--accent, var(--go-orange));
  outline-offset: 2px;
}
:focus:not(:focus-visible) { outline: none; }

/* ── Reduced motion ────────────────────────────────────────────────────── */
@media (prefers-reduced-motion: reduce) {
  .sidebar,
  .sidebar-collapse-btn,
  .sidebar-nav a,
  .nav-icon,
  .nav-label,
  .main { transition: none !important; }
}
```

---

## 5. JavaScript — toggle + state restore + aria sync

```javascript
(function() {
  'use strict';

  // ── Render helper (proyecto define navItems + iconos) ────────────────
  function renderSidebar(navItems, iconCatalog) {
    var sidebar = document.getElementById('sidebar');
    if (!sidebar) return;
    if (!sidebar.classList.contains('sidebar')) sidebar.classList.add('sidebar');

    sidebar.innerHTML =
      '<button class="sidebar-collapse-btn" id="sidebar-collapse-btn" type="button" ' +
        'title="Plegar menu" aria-label="Plegar menu" aria-expanded="true" aria-controls="sidebar">' +
        '<svg width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="currentColor" ' +
          'stroke-width="2" stroke-linecap="round" stroke-linejoin="round">' +
          '<polyline points="15 18 9 12 15 6"/></svg>' +
      '</button>' +
      '<ul class="sidebar-nav">' +
        navItems.map(function(i) {
          return '<li><a href="#' + i.id + '" data-view="' + i.id + '" ' +
                    'data-label="' + i.label + '" title="' + i.label + '">' +
                    '<span class="nav-icon" aria-hidden="true">' +
                      (iconCatalog[i.icon] || '') +
                    '</span>' +
                    '<span class="nav-label">' + i.label + '</span>' +
                 '</a></li>';
        }).join('') +
      '</ul>';
  }

  // ── State restore al cargar ──────────────────────────────────────────
  function applyState() {
    var sidebar = document.getElementById('sidebar');
    var collapsed = localStorage.getItem('sidebar_collapsed') === '1';
    if (sidebar) sidebar.classList.toggle('collapsed', collapsed);
    document.body.classList.toggle('sidebar-collapsed', collapsed);
    syncAria(collapsed);
  }

  function syncAria(collapsed) {
    var btn = document.getElementById('sidebar-collapse-btn');
    if (btn) {
      btn.setAttribute('aria-expanded', collapsed ? 'false' : 'true');
      btn.setAttribute('aria-label', collapsed ? 'Expandir menu' : 'Plegar menu');
      btn.setAttribute('title', collapsed ? 'Expandir menu' : 'Plegar menu');
    }
    var topbar = document.getElementById('sidebar-toggle');
    if (topbar) topbar.setAttribute('aria-expanded', collapsed ? 'false' : 'true');
  }

  // ── Toggle ───────────────────────────────────────────────────────────
  window.toggleSidebar = function() {
    var sidebar = document.getElementById('sidebar');
    if (!sidebar) return;
    var collapsed = sidebar.classList.toggle('collapsed');
    document.body.classList.toggle('sidebar-collapsed', collapsed);
    localStorage.setItem('sidebar_collapsed', collapsed ? '1' : '0');
    syncAria(collapsed);
    // Re-dispatch resize para charts/widgets dependientes del ancho
    setTimeout(function(){ window.dispatchEvent(new Event('resize')); }, 250);
  };

  // ── Bind eventos ─────────────────────────────────────────────────────
  function bindToggles() {
    document.addEventListener('click', function(e) {
      if (e.target.closest('#sidebar-collapse-btn, #sidebar-toggle')) {
        e.stopPropagation();
        window.toggleSidebar();
      }
    });
  }

  // ── Nav click handler ───────────────────────────────────────────────
  function bindNav(onNavigate) {
    var sidebar = document.getElementById('sidebar');
    if (!sidebar) return;
    sidebar.addEventListener('click', function(e) {
      var link = e.target.closest('.sidebar-nav a');
      if (link) {
        e.preventDefault();
        var view = link.dataset.view;
        // Marcar activo
        sidebar.querySelectorAll('.sidebar-nav a').forEach(function(a) {
          var isActive = a.dataset.view === view;
          a.classList.toggle('active', isActive);
          if (isActive) a.setAttribute('aria-current', 'page');
          else a.removeAttribute('aria-current');
        });
        if (typeof onNavigate === 'function') onNavigate(view);
      }
    });
  }

  // ── Logout (opcional, expone window.logout) ──────────────────────────
  window.logout = function() {
    localStorage.removeItem('access_token');
    document.cookie = 'csrf_token=; Path=/; Max-Age=0; SameSite=Lax';
    window.location.replace('/login');
  };

  // ── Init publico ─────────────────────────────────────────────────────
  window.GoShell = {
    renderSidebar: renderSidebar,
    applyState: applyState,
    bindToggles: bindToggles,
    bindNav: bindNav,
    toggleSidebar: window.toggleSidebar,
  };
})();
```

### Uso minimo en proyecto:

```javascript
// 1. Definir nav items con catalog de iconos
var navItems = [
  { id: 'dashboard', label: 'Dashboard', icon: 'grid' },
  { id: 'inventario', label: 'Inventario', icon: 'box' },
  // ...
];
var iconCatalog = { /* ver seccion 6 */ };

// 2. Render + bind
GoShell.renderSidebar(navItems, iconCatalog);
GoShell.applyState();
GoShell.bindToggles();
GoShell.bindNav(function(view) {
  // Tu router carga la vista aqui
  loadView(view);
});
```

---

## 6. SVG Icon Catalog (20x20, stroke 1.5)

Set base reutilizable. Cualquier proyecto debe usar estos o agregar similares al catalogo (PR a este doc).

```javascript
var iconCatalog = {
  // Dashboard
  grid: '<svg viewBox="0 0 20 20" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"><rect x="2" y="2" width="7" height="7" rx="1"/><rect x="11" y="2" width="7" height="7" rx="1"/><rect x="2" y="11" width="7" height="7" rx="1"/><rect x="11" y="11" width="7" height="7" rx="1"/></svg>',
  // Inventario / Caja / 3D
  box: '<svg viewBox="0 0 20 20" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"><path d="M17 13.5V6.5a1.7 1.7 0 0 0-.85-1.47l-5.3-3.03a1.7 1.7 0 0 0-1.7 0L3.85 5.03A1.7 1.7 0 0 0 3 6.5v7a1.7 1.7 0 0 0 .85 1.47l5.3 3.03a1.7 1.7 0 0 0 1.7 0l5.3-3.03A1.7 1.7 0 0 0 17 13.5z"/><polyline points="3.3 5.8 10 10 16.7 5.8"/><line x1="10" y1="18.5" x2="10" y2="10"/></svg>',
  // Preordenes / Listas
  clipboard: '<svg viewBox="0 0 20 20" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"><rect x="4" y="4" width="12" height="14" rx="1.5"/><rect x="7" y="2" width="6" height="3.5" rx="1"/><line x1="7" y1="10" x2="13" y2="10"/><line x1="7" y1="13" x2="13" y2="13"/></svg>',
  // Produccion / Logistica
  truck: '<svg viewBox="0 0 20 20" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"><rect x="1.5" y="5" width="11" height="9" rx="1"/><path d="M12.5 8H16l2.5 2.5V14h-6V8z"/><circle cx="5.5" cy="15.5" r="1.7"/><circle cx="14.5" cy="15.5" r="1.7"/></svg>',
  // Admin / Permisos
  shield: '<svg viewBox="0 0 20 20" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"><path d="M10 18s7-3.5 7-9V4l-7-2.5L3 4v5c0 5.5 7 9 7 9z"/><polyline points="7.2 9.5 9.2 11.5 13 7.7"/></svg>',
  // Competidores / Target
  target: '<svg viewBox="0 0 20 20" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"><circle cx="10" cy="10" r="8"/><circle cx="10" cy="10" r="3"/><line x1="10" y1="2" x2="10" y2="6"/><line x1="10" y1="14" x2="10" y2="18"/><line x1="2" y1="10" x2="6" y2="10"/><line x1="14" y1="10" x2="18" y2="10"/></svg>',
  // Insights / IA
  star: '<svg viewBox="0 0 20 20" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"><path d="M10 2l2.5 5 5.5.8-4 3.9.9 5.5-4.9-2.6-4.9 2.6.9-5.5-4-3.9 5.5-.8z"/></svg>',
  // Reportes / Charts
  chart: '<svg viewBox="0 0 20 20" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"><rect x="2" y="8" width="4" height="10" rx="1"/><rect x="8" y="4" width="4" height="14" rx="1"/><rect x="14" y="6" width="4" height="12" rx="1"/></svg>',
  // Simulacion / Play
  play: '<svg viewBox="0 0 20 20" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"><polygon points="4,2 18,10 4,18"/></svg>',
  // Chat / Mensaje
  chat: '<svg viewBox="0 0 20 20" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"><path d="M16 3H4a2 2 0 00-2 2v8a2 2 0 002 2h3l3 3 3-3h3a2 2 0 002-2V5a2 2 0 00-2-2z"/></svg>',
  // Settings / Config
  gear: '<svg viewBox="0 0 20 20" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"><circle cx="10" cy="10" r="3"/><path d="M16 12.5a1.5 1.5 0 0 0 .3 1.65l.06.06a1.8 1.8 0 1 1-2.54 2.54l-.06-.06a1.5 1.5 0 0 0-1.65-.3 1.5 1.5 0 0 0-.9 1.37V18a1.8 1.8 0 0 1-3.6 0v-.09a1.5 1.5 0 0 0-1-1.37 1.5 1.5 0 0 0-1.65.3l-.06.06a1.8 1.8 0 1 1-2.54-2.54l.06-.06a1.5 1.5 0 0 0 .3-1.65 1.5 1.5 0 0 0-1.37-.9H2a1.8 1.8 0 0 1 0-3.6h.09a1.5 1.5 0 0 0 1.37-1 1.5 1.5 0 0 0-.3-1.65l-.06-.06a1.8 1.8 0 1 1 2.54-2.54l.06.06a1.5 1.5 0 0 0 1.65.3H7.5a1.5 1.5 0 0 0 .9-1.37V2a1.8 1.8 0 0 1 3.6 0v.09a1.5 1.5 0 0 0 .9 1.37 1.5 1.5 0 0 0 1.65-.3l.06-.06a1.8 1.8 0 1 1 2.54 2.54l-.06.06a1.5 1.5 0 0 0-.3 1.65V7.5a1.5 1.5 0 0 0 1.37.9H18a1.8 1.8 0 0 1 0 3.6h-.09a1.5 1.5 0 0 0-1.37.9z"/></svg>',
};
```

---

## 7. Variables CSS requeridas (extender de `context_design.md`)

| Variable | Valor sugerido | Uso |
|---|---|---|
| `--sidebar-w` | `248px` | Ancho expandido |
| `--sidebar-collapsed` | `64px` | Ancho colapsado |
| `--topbar-h` | `56px` | Alto topbar |
| `--go-black` | `#262626` | Fondo sidebar |
| `--go-white` | `#FFFFFF` | Texto sobre activo |
| `--go-orange` | `#FB670B` | Activo expandido bg, hover accent |
| `--accent` | `var(--go-orange)` | Alias |
| `--accent-tint` | `rgba(251,103,11,0.10)` | Hover bg |
| `--font-display` | `'Blauer Nue', sans-serif` | Nav items typo |
| `--shadow-lg` | `0 8px 32px rgba(0,0,0,0.50)` | Tooltip colapsado |

---

## 8. Accesibilidad — checklist obligatorio (WCAG AA)

- [ ] `skip-link` como primer hijo de `<body>` (`href="#main-content"`)
- [ ] `<aside role="navigation" aria-label="Navegacion principal">`
- [ ] Boton plegar con `aria-expanded`, `aria-controls="sidebar"`, `aria-label` dinamico ("Plegar menu" / "Expandir menu")
- [ ] Item activo: `aria-current="page"`
- [ ] `:focus-visible` con outline acento 2px (no `:focus`)
- [ ] Color no es unico indicador (icono + texto + barra acento)
- [ ] Contraste minimum 4.5:1 (verificar #FB670B sobre #262626 = 5.4:1 OK)
- [ ] `prefers-reduced-motion`: transitions disabled
- [ ] Tab nav funcional, Esc cierra dropdowns

---

## 9. Tests de aceptacion (manual checklist por proyecto)

1. ✅ Carga inicial: sidebar visible, item de la vista actual con `.active` (naranja sólido)
2. ✅ Click chevron `<` arriba: sidebar colapsa a 64px, chevron rota a `>`, labels desaparecen
3. ✅ En colapsado, click chevron `>`: expande, chevron rota a `<`
4. ✅ Hover icono colapsado: aparece tooltip a la derecha con el label
5. ✅ Estado persiste tras reload (localStorage `sidebar_collapsed`)
6. ✅ Tab navigation: foco visible con outline naranja, navega entre items
7. ✅ Item activo cambia al navegar (`aria-current="page"`)
8. ✅ Mobile (<768px): sidebar full-width drawer (proyecto define media query)
9. ✅ `window.resize` event dispatcheado al toggle (charts re-pintan)
10. ✅ `prefers-reduced-motion`: animaciones disabled

---

## 10. Customizacion permitida vs prohibida

### ✅ Permitido (cada proyecto puede ajustar)

- Lista de `navItems` (rutas, labels, iconos)
- Iconos del catalogo (agregar nuevos respetando 20x20 stroke 1.5)
- Color de fondo del sidebar (mantener oscuro + contraste 4.5+)
- Brand text en topbar
- Contenido del footer del sidebar (o omitirlo)
- Logout handler (`window.logout`)
- Ancho expanded (`--sidebar-w`) — recomendado 240-260px

### ❌ Prohibido (rompe consistencia entre proyectos)

- Cambiar la clase `.sidebar-nav a.active` color (DEBE ser naranja `#FB670B` solido expanded)
- Layout shift al colapsar (`gap`, `padding`, `margin` del activo)
- Indicador activo colapsado distinto a `box-shadow: inset 3px 0 0 acento`
- Iconos con `stroke-width` distinto a 1.5
- Iconos `viewBox` distinto a `0 0 20 20`
- Reemplazar `<a>` por `<button>` en nav (rompe SEO + comportamiento estandar)
- Persistencia de estado en sessionStorage (debe ser localStorage)

---

## 11. Proyectos que usan este shell

| Proyecto | Version | Estado | Notas |
|---|---|---|---|
| `multi_mkt_study_v2` | 1.0 | Implementado 2026-05-22 | Topbar + sidebar + main (flex+fixed) |
| `ventas_rafias_go` | 1.1 | Implementado 2026-05-22 | Sidebar colapsable (grid layout, sin topbar shell) |
| `automatizacion ventas sacos` | — | Semilla creada, pendiente aplicar | Owner: Carlos Jaramillo |
| `charolas` | — | Pendiente evaluar | |
| `market_intelligence` | — | Pendiente evaluar | |

---

## 12. Procedimiento de adopcion (proyecto nuevo)

1. Verificar tokens GO presentes (`context_design.md` cargado)
2. Crear `static/css/<proyecto>.css` o append en CSS principal — pegar bloque seccion 4
3. Agregar `<aside id="sidebar" class="sidebar">` en HTML donde corresponda
4. Crear `static/js/shell.js` con bloque seccion 5 (o append en JS principal)
5. Definir `navItems` segun rutas del proyecto + reusar iconos catalog
6. Llamar `GoShell.renderSidebar(navItems, iconCatalog)`, `applyState()`, `bindToggles()`, `bindNav(routerFn)`
7. Verificar tests de aceptacion (seccion 9) — manual o automatizado
8. Commit con mensaje: `feat(ui): aplicar GO UI Shell v1.1 (sidebar)`
9. Actualizar tabla seccion 11 con tu proyecto

---

## 13. Changelog

| Version | Fecha | Cambios |
|---|---|---|
| 1.0 | 2026-05-22 | Extraido de `multi_mkt_study_v2`. Topbar + sidebar + main + utilidades |
| 1.1 | 2026-05-22 | Sidebar promovido a componente plug-and-play. Agregado boton plegar/expandir (`.sidebar-collapse-btn`) con chevron rotativo. Agregado `GoShell` JS API publico. Catalog de iconos. Customizacion permitida vs prohibida. Tests de aceptacion. Verificado en `ventas_rafias_go` |

---

## 14. Referencias

- Fuente HTML: `multi_mkt_study_v2/static/index.html`
- Fuente CSS: `multi_mkt_study_v2/static/css/style.css` (líneas 256-365)
- Implementacion sidebar colapsable + boton: `ventas_rafias_go/rafias-agent/api/static/css/app.css` (líneas 260-330) + `js/app.js` `_renderSidebar()`
- Tokens GO base: `context_design.md` raiz `IDENTIDAD DE MARCA/`
