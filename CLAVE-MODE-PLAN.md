# Clave Video — Modo Clave (plan de desarrollo)

Trabajo aislado en `zapia/clave-mode`. No reemplazar la APK de prueba que el usuario confirmó que carga y reproduce en segundo plano hasta validar cada fase.

## Auditoría de funciones existentes en la base LibreTube

- Inicio configurable por secciones (`HOME_TAB_CONTENT`); feed, tendencias, suscripciones y listas ya existen.
- Continuar viendo e historial local ya guardan progreso de reproducción.
- Cola de reproducción y listas locales ya existen; evitar crear duplicados con otros nombres.
- Reproducción de fondo/solo audio, controles de pantalla bloqueada y temporizador existen.
- Selector manual de calidad y descargas ya existen; es preferible mejorar accesos rápidos/modo ahorro en vez de duplicar.
- SponsorBlock ya está integrado; depende de la disponibilidad de segmentos/API.
- Promos y botón de WhatsApp de La Clave ya están aplicados en el fork.

## Funciones propias a implementar

1. **ClaveMix**: creador de tandas temáticas a partir de listas guardadas y cola del reproductor; controles para guardar, reordenar, iniciar y continuar la tanda. No debe auto-reproducir contenido no solicitado.
2. **Retomar donde quedaste**: mejorar la tarjeta de continuación mostrando título, progreso y acceso directo. Reutilizar posición/historial existentes; no agregar una segunda base de historial.
3. **Modo señal/datos bajos**: opción de calidad preferida y acceso rápido a solo audio. No fingir detección automática de mala señal si el reproductor no expone una medición fiable; fallback manual disponible.
4. **Marcadores con nota**: guardar video, tiempo, título y nota local; abrir el video directamente en el instante guardado; edición y borrado.
5. **Rutas de aprendizaje**: listas locales ordenadas con descripción, progreso por video y acción de continuar. Reutilizar listas y posiciones cuando sea posible.
6. **Sección La Clave**: espacio separado del feed normal para contenido elegido por el usuario/promos cerrables; no interrumpir reproducción ni bloquear navegación.
7. **Pulido**: Inicio personalizado con accesos claros a música, videos y suscripciones; mejor manejo/visualización de cola, audio-only, descargas, SponsorBlock.

## Fases y verificación

- Fase A: estabilizar la base que el usuario ya probó; compilar y validar que inicio, búsqueda, abrir video, reproducción y segundo plano siguen funcionando.
- Fase B: accesos de Inicio, retomar progreso y listas/ClaveMix.
- Fase C: marcadores con nota y rutas de aprendizaje, persistencia local y migración Room sin perder datos.
- Fase D: modo datos bajos y sección La Clave.
- Cada fase debe compilar y probar regresiones; no describirla como validada en dispositivo salvo prueba real en teléfono.

## Riesgos y límites

YouTube y el extractor pueden cambiar; no prometer disponibilidad continua. No eludir anuncios, DRM, autenticación ni controles de acceso. Conservar licencias GPL y publicar el código fuente correspondiente al distribuir la app.
