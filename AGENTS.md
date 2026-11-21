# Reglas del proyecto

- No cambiar el login ni la sincronización con Supabase, ni `SUPABASE_URL` ni la key.
- Mantener la estética art nouveau nocturno y los 3 temas (`complementarios`, `triada`, `analogos`). Usar siempre las variables CSS del tema (`--primary`, `--secondary`, `--accent-gold`, `--card-elevated`, `--card-bg`, `--border-ornament`, `--ink-dark`, `--ink-muted`, `--aura-glow`, etc.). No usar colores fijos, salvo las categorías.
- Compatibilidad total con datos ya guardados: todo campo nuevo debe tener migración al cargar.
- Los datos se guardan por semana: `appState.weeks[mondayISO].tasks[dayIdx]`. Las fechas se calculan en fecha local (año, mes, día), nunca con `toISOString()`.
- Cada actividad tiene: `id`, `hour`, `endHour`, `text`, `category`, `status` (`pending` | `done` | `missed`), `done` y, si es repetida, `seriesId`. Las prioridades tienen `status` y `done`.
- Todo debe funcionar bien en celular (360px de ancho) y escritorio. Botones táctiles de al menos 40px.
- Español rioplatense. Animaciones con `prefers-reduced-motion` respetado.
- Cada vez que cambie `index.html` (o cualquier archivo que cachee el service worker), subir la versión de caché de `sw.js`.
- Un commit por tanda, con mensaje claro, cuando el usuario lo solicite. Al terminar, resumir qué cambió y qué supuestos se asumieron.
