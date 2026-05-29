# Landing Page Clínica Trinity — Diseño

**Fecha:** 2026-05-28  
**Proyecto:** clinica-trinity-website  
**Stack:** Astro 6.4.2 · Tailwind CSS v4.3 · DaisyUI v5.5 · astro-icon 1.1.5

---

## Contexto

Clínica Trinity Especialidades Dentales necesita una landing page de alto impacto para atraer pacientes en Tres Ríos, Costa Rica. El sitio debe transmitir profesionalismo, calidez y confianza, con un llamado a acción claro hacia WhatsApp para agendar citas. El proyecto ya tiene Astro, Tailwind CSS v4 y DaisyUI v5 instalados; solo requiere construir los componentes desde cero.

---

## Información de la Clínica

- **Nombre:** Clínica Trinity Especialidades Dentales
- **Doctora:** Francela Monge
- **Dirección:** 800 metros este de la iglesia católica, Tres Ríos, Costa Rica
- **WhatsApp:** +506 8356-1395
- **Facebook:** https://www.facebook.com/DraFranselaMonge
- **Instagram:** https://www.instagram.com/clinicadental_trinity/
- **Logo:** `/public/Clinica Trinity.png`

---

## Tema y Colores

**Enfoque:** Variables CSS de DaisyUI v5 definidas en `src/styles/global.css` bajo `[data-theme="trinity"]`. Sin `tailwind.config.mjs`.

```css
[data-theme="trinity"] {
  --color-primary: #AD2380;
  --color-secondary: #808285;
  --color-accent: #FBAC37;
  --color-base-100: #FFFFFF;
}
```

El `<html>` lleva `data-theme="trinity"`. Todos los componentes DaisyUI heredan los colores automáticamente.

---

## Arquitectura de Archivos

```
src/
├── layouts/
│   └── Layout.astro          # HTML shell, <head>, metadatos, importa global.css
├── pages/
│   └── index.astro           # Orquesta todos los componentes
├── components/
│   ├── Navbar.astro
│   ├── Hero.astro
│   ├── Differentials.astro
│   ├── Services.astro
│   ├── Stats.astro
│   ├── Testimonials.astro
│   ├── Footer.astro
│   └── WhatsAppButton.astro
└── styles/
    └── global.css            # Tema + @import tailwindcss + @plugin daisyui
```

---

## Secciones

### 1. Navbar (`Navbar.astro`)

- Componente `.navbar` de DaisyUI
- Logo: `<img src="/Clinica Trinity.png" />` a la izquierda
- Links de navegación: Inicio · Servicios · Nosotros · Contacto
- Botón `.btn-primary` "Agendar Cita" visible en desktop
- Menú móvil: drawer DaisyUI (CSS puro, sin JS)
- Sticky en top con sombra sutil

### 2. Hero (`Hero.astro`)

- Estructura `.hero` + `.hero-content` de DaisyUI
- Layout: texto izquierda, imagen derecha (en desktop); apilado en móvil
- **Título:** "Sonreír con confianza y sin pena"
- **Subtítulo:** "En Clínica Trinity te ofrecemos atención dental especializada con tecnología moderna y el calor humano que mereces. Ubicados en Tres Ríos, Costa Rica."
- **CTA primario:** `.btn-primary` "Agendar Cita por WhatsApp" con ícono WhatsApp → `https://wa.me/50683561395?text=Hola,%20me%20gustaría%20agendar%20una%20cita`
- **CTA secundario:** `.btn-outline` "Ver Servicios" → anchor `#servicios`
- **Imagen:** Placeholder con gradiente de colores de marca (`bg-gradient-to-br from-primary/20 to-accent/20`) + ícono SVG de diente. Se reemplaza después con `<Image />` de Astro.

### 3. Diferenciales (`Differentials.astro`)

- Grid de 3 `.card` con fondo `bg-base-100` y `shadow-md`
- Cada card: ícono Heroicon (`.text-primary`), título, descripción
- Contenido:
  1. **Tecnología Avanzada** — `heroicons:cpu-chip` — "Equipos de última generación para diagnósticos precisos y tratamientos más cómodos."
  2. **Atención Personalizada** — `heroicons:user-circle` — "Cada paciente es único. Te escuchamos y diseñamos el plan ideal para tu sonrisa."
  3. **Trabajamos con Amor** — `heroicons:heart` — "La Dra. Francela Monge y su equipo te cuidan con dedicación y calidez en cada visita."

### 4. Servicios (`Services.astro`)

- Sección con id `servicios` (anchor desde Hero)
- Grid responsivo: 1 col mobile → 2 cols tablet → 3 cols desktop
- Componente `.card .card-compact .bg-base-100 .shadow-xl` de DaisyUI
- 7 tarjetas **solo informativas** (sin botón de acción):
  1. Blanqueamientos — `heroicons:sparkles`
  2. Ortodoncia invisible (alineadores) — `heroicons:adjustments-horizontal`
  3. Restauraciones — `heroicons:wrench-screwdriver`
  4. Implantes dentales — `heroicons:bolt`
  5. Coronas y puentes — `heroicons:trophy`
  6. Cirugías — `heroicons:scissors`
  7. Ortopedia funcional (Myobrace) — `heroicons:face-smile`

### 5. Métricas de Confianza (`Stats.astro`)

- Componente `.stats .stats-vertical sm:stats-horizontal` de DaisyUI
- 3 métricas:
  - **+10 años** de experiencia
  - **5,000+** Sonrisas creadas
  - **100%** Compromiso con tu salud
- Fondo `bg-primary text-primary-content` para contraste visual

### 6. Testimonios (`Testimonials.astro`)

- Grid de 3 cards con `.avatar` (iniciales como placeholder) + texto de reseña + nombre
- Contenido de ejemplo (reemplazable):
  1. *"Llegué con miedo al dentista y la Dra. Francela me hizo sentir en casa. Mi sonrisa cambió completamente."* — María G.
  2. *"El proceso con alineadores fue increíble. Profesionales, puntuales y muy atentos."* — Carlos R.
  3. *"Llevé a mis hijos y el trato fue excelente. Los niños salieron felices. ¡100% recomendados!"* — Ana P.
- Estrellas con `heroicons:star-solid` en color `text-accent`

### 7. Footer (`Footer.astro`)

- Componente `.footer` de DaisyUI con 3 columnas:
  - **Col 1 — Info:** Nombre clínica, dirección, teléfono
  - **Col 2 — Navegación:** Inicio · Servicios · Nosotros · Contacto
  - **Col 3 — Redes:** Facebook (`simple-icons:facebook`) + Instagram (`simple-icons:instagram`)
- Fondo `bg-neutral text-neutral-content`
- Copyright al pie

### 8. Botón WhatsApp Flotante (`WhatsAppButton.astro`)

- Posición `fixed bottom-6 right-6 z-50`
- Círculo verde (#25D366) con ícono WhatsApp
- Link: `https://wa.me/50683561395?text=Hola,%20me%20gustaría%20agendar%20una%20cita`
- Animación `hover:scale-110` con `transition-transform`
- Visible en todas las secciones

---

## Decisiones Técnicas

- **Sin JavaScript manual:** Toda interactividad (drawer móvil, acordeones) usa CSS nativo de DaisyUI
- **Iconos:** `astro-icon` con Heroicons. Import: `import { Icon } from 'astro-icon/components'`
- **Imagen Hero:** Placeholder CSS hasta recibir foto real; luego reemplazar con `<Image />` de Astro
- **Redes sociales:** URLs reales de Facebook e Instagram proporcionadas por el cliente
- **WhatsApp:** Mensaje pre-llenado en español en todos los CTAs
- **Mobile-First:** Clases Tailwind base para móvil, `sm:` / `md:` / `lg:` para escalado

---

## Verificación

1. `npm run dev` — verificar que el servidor corre en localhost:4321
2. Revisar en móvil (375px): navbar drawer, hero apilado, grid de 1 columna
3. Revisar en desktop (1280px): hero split, grids de 3 columnas, navbar horizontal
4. Verificar que el botón WhatsApp flotante aparece en todas las secciones
5. Verificar que los links de WhatsApp abren con el mensaje pre-llenado correcto
6. Verificar que Facebook e Instagram abren en nueva pestaña
7. `npm run build` — confirmar build estático sin errores
