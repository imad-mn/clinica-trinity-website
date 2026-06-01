# Análisis UI/UX — Clínica Trinity (Odontología)
El sitio está bien construido con buenas bases. Aquí las áreas de mejora organizadas por impacto:

## Problemas de Alta Prioridad
1. No hay imagen real en el Hero
El Hero tiene un placeholder (rounded-3xl gradient background). Para una clínica odontológica, esto es crítico: la gente confía en caras reales. Opciones:

Foto del doctor/equipo sonriendo
Foto de la clínica moderna interior
Paciente feliz post-tratamiento (con permiso)
2. Sin fuente tipográfica personalizada
Actualmente usa solo Tailwind defaults (system font). Para una clínica que quiere transmitir profesionalismo y calidez, se recomienda una pareja de Google Fonts:

Headings: Playfair Display o DM Serif Display — elegancia y confianza
Body: Inter o DM Sans — legibilidad moderna
3. Color primario #AD2380 (magenta) no es convencional para odontología
El magenta es poco común en salud dental. Los pacientes asocian odontología con azul (confianza, limpieza) o verde (salud). El magenta puede funcionar como diferenciador de marca, pero necesita más contexto visual (fotos, texturas) para que no se sienta frío o ajeno.

4. Sin sección de credenciales/confianza ("Trust Section")
Para cualquier servicio médico, los pacientes necesitan saber:

Años de experiencia del doctor
Número de pacientes atendidos
Certificaciones/colegios profesionales
Antes/después de tratamientos
Actualmente la sección "Differentials" tiene 3 items pero son muy genéricos ("Trabajamos con Amor").

## Problemas de Media Prioridad
5. Testimonios usan iniciales, no fotos
Los avatares con iniciales (JR, MC) reducen credibilidad. Las clínicas líderes usan fotos reales de pacientes o al menos Google Reviews embebidas.

6. Las estrellas de testimonios son ★ texto, no iconos SVG
Inconsistente con el sistema de iconos Heroicons del resto del sitio. Cambiar a <Icon name="heroicons:star-solid" />.

7. Hero CTA duplicado
Hay 3 formas de agendar cita visibles casi simultáneamente: botón en Navbar, botón en Hero, y el WhatsApp flotante. En mobile esto se convierte en 4 elementos. Simplificar la jerarquía de CTAs.

8. Sección de servicios sin precios ni anclas de acción
Cada card de servicio tiene título + descripción pero ningún CTA. Para una clínica, agregar "Consultar precio" o un enlace a WhatsApp por servicio aumenta conversión.

9. Sin sección de ubicación/mapa
El footer menciona "Tres Ríos, Costa Rica" pero no hay mapa ni dirección detallada. Para una clínica, la ubicación es factor decisivo.

## Mejoras de Baja Prioridad
10. Fuentes cargadas sin font-display: swap
Si se agregan Google Fonts, asegurarse de usar &display=swap para evitar FOIT (Flash of Invisible Text).

11. prefers-reduced-motion no está implementado
Las animaciones de hover en cards y la navbar no respetan esta preferencia del sistema operativo.

12. Meta tags de SEO incompletos
El Layout acepta title y description opcionales, pero no hay og:image, og:type, ni schema.org para DentalClinic (rich results en Google).

13. El WhatsApp flotante no tiene aria-label
Solo tiene el ícono SVG sin texto accesible.
