# Changelog

## 2026-08-26 — SEO / GEO / LLM foundation + Google Ads readiness

### Wix Business Info

- Normalizado `businessName` a `SC Auto Locksmith`.
- Normalizado `siteDisplayName` a `SC Auto Locksmith`.
- Añadido teléfono oficial `+16464077689` a Site Properties.
- Añadido logo existente como business logo.
- Reescrita descripción del negocio con foco en servicio móvil 24/7 en New York.
- Dirección física no añadida: Wix declara `isPhysical=false` y no existe dirección pública configurada.

### Site-wide SEO

- Preservada verificación de Google.
- Preservada verificación de Bing.
- Preservada imagen social global.
- Eliminados `keywords`, `description` y `fb_admins_meta_tag` vacíos.

### Static pages

Optimización guardada y publicada en:

- Home (`c1dmp`)
- Automotriz (`jhpm6`)
- Contacto (`zhs4k`)
- Blog (`gsxpc`)
- Reserva Online (`sfajx`)

Se actualizaron title, meta description, OG, Twitter metadata y focus keywords. Se añadió JSON-LD propio en Home, Automotriz, Contacto y Blog.

### Wix Bookings

Optimización SEO propia en:

- Cambio de Cerraduras
- Desbloqueo Automóvil
- Duplicado de Llaves

### Wix Blog

Optimización de metadata y focus keywords para los 3 artículos existentes. Se preservó el `BlogPosting` nativo de Wix.

### GEO / LLM

- Preservado el bloque MCP nativo de Wix en `llms.txt`.
- Añadido bloque de datos oficiales, URLs canónicas, redes oficiales y reglas anti-alucinación.
- Confirmado `llms.txt` visible.

### Crawling / routing

- `robots.txt` default de Wix mantenido sin cambios.
- Sitemap confirmado.
- Optimización de AdsBot-Google confirmada.
- `shouldFlattenUrlHierarchy=false` confirmado.
- `shouldUsePartialRouteMatch=false` confirmado.

### Google Ads

- Auditado flujo Wix Google Ads.
- Detectada ruta vigente de App Installer.
- Documentado requisito de Google Advanced Verification para Locksmith Services en USA.
- Preparada arquitectura `PERFORMANCE_MAX_LEADS`, search themes, negativos, assets, conversion hierarchy y flujo de launch.
- No se activó gasto ni se inventó presupuesto.

### Nota de implementación

La primera versión ampliada del JSON-LD de Home excedió el límite Wix de 4096 bytes por tag y fue rechazada antes de escribirse. Se compactó el graph a 2766 bytes manteniendo la semántica principal; la versión final fue aceptada con HTTP 200 y verificada posteriormente.
