Actúa como un desarrollador Frontend Senior experto en Astro, Tailwind CSS y DaisyUI. Tu objetivo es crear una Landing Page de alto impacto, moderna y completamente responsiva para una clínica odontológica.

Debes estructurar el proyecto utilizando las mejores prácticas de Astro, aprovechando los componentes semánticos de DaisyUI y la librería `astro-icon` para un manejo eficiente de vectores.

### Información de la Clinica:
- Nombre: "Clínica Trinity Especialidades Dentales"
- Doctora: Francela Monge
- Dirección: 800 metros este de la iglesia católica, Tres Ríos, Costa Rica
- Teléfono Whatsapp: 8356-1395

### 🛠️ Detalles Tecnológicos y Configuración:
- Framework: Astro (página estática o híbrida).
- Estilos & UI: Tailwind CSS junto con DaisyUI. Utiliza las clases de componentes de DaisyUI (ej. `btn`, `card`, `navbar`, `hero`, `stat`) para mantener el código limpio y evitar el exceso de clases utilitarias.
- Iconos: Usa la librería `astro-icon`. Representa los iconos usando el componente `<Icon name="..." />`. Usa iconos de Heroicons.
- Interactividad: Utiliza los componentes nativos de DaisyUI que ya manejan interactividad (como el menú de navegación móvil mediante `drawer` o CSS puro, o los acordeones de FAQ mediante `<details class="collapse">`). Evita JavaScript innecesario.

### 🎨 Temas y Estilo Visual (DaisyUI):
- Utiliza el sistema de temas de DaisyUI. Configura un tema limpio y profesional (puede ser basado en el tema `light` modificado o definiendo colores personalizados en `tailwind.config.mjs` para `primary`, `secondary`, `accent`, `neutral` y `base-100`).
- El aspecto debe ser clínico pero acogedor: bordes redondeados estándar de DaisyUI, sombras sutiles y transiciones fluidas en los estados `:hover` de los botones.
- Los colores de la marca con fondo blanco son: #AD2380, #808285 y #FBAC37

### 📐 Estructura de la Landing Page (Secciones usando DaisyUI):
1. **Navbar (`.navbar`):** Adjunto el Logo, enlaces de navegación y un botón `.btn-primary` destacado para "Agendar Cita". Usa un menú responsivo que se oculte en móviles o un componente `.drawer`.
2. **Hero Section (`.hero`):** - Usa la estructura de `.hero` y `.hero-content` de DaisyUI.
   - Título potente y orientado al beneficio ("Sonreír con confianza y sin pena").
   - Dos botones de acción: `.btn-primary` (Agendar Cita) con el icono de Whatsapp y tenga el link de enviar un mensaje a Whatsapp +50683561395 y `.btn-outline` (Ver Servicios).
   - Imagen optimizada del lado derecho en escritorio (usa el componente `<Image />` de Astro).
3. **Diferenciales (`.stats` o `.grid` con `.card`):** 3 o 4 tarjetas rápidas destacando: "Tecnología Avanzada", "Atención Personalizada", "Trabajamos con Amor". Usa `<Icon />` en cada una.
4. **Servicios Principales (Grid de `.card`):** Tarjetas de DaisyUI (`.card .card-compact .bg-base-100 .shadow-xl`) con iconos para: Blanqueamientos, Ortodoncia invisible (alineadores), Restauraciones, Implantes dentales, Coronas y puentes, Cirugías, 
Ortopedia funcional (trainers myobrace). Cada tarjeta con su botón `.btn-link` o `.btn-sm`.
5. **Métricas de Confianza:** Usa el componente `.stats` de DaisyUI (completamente responsivo) para mostrar datos de impacto (ej: "+10 años de experiencia", "5,000+ Sonrisas creadas").
6. **Testimonios:** Un diseño de rejilla o filas usando `.avatar` junto con bloques de texto estilizados para las reseñas de los pacientes.
7. **Footer (`.footer`):** Usa el diseño estructurado de `.footer` de DaisyUI con columnas para enlaces legales, redes sociales (con iconos de `astro-icon`) y copyright.


Además agrega un **Boton de Whatsapp flotante:** que apunte a escribir a Whatsapp a este número: +50683561395 y diga un mensaje para agendar una cita.

### 📂 Requisitos de Código y Salida:
- Divide la estructura en componentes de Astro limpios dentro de `src/components/` (ej: `Navbar.astro`, `Hero.astro`, `Services.astro`, `Contact.astro`) e intégralos en `src/pages/index.astro`.
- Asegúrate de importar correctamente el componente de iconos: `import { Icon } from 'astro-icon/components';` en los componentes que lo requieran.
- El código debe ser semántico, modular, fácil de mantener y 100% Mobile-First.