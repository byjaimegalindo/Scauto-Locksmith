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
- Confirmado con documentación vigente de Wix que las nuevas campañas de leads creadas desde Google Ads con Wix usan **Performance Max Leads** y que las Smart campaigns nuevas ya no están disponibles.
- Investigada y documentada estrategia de lanzamiento para primera campaña: `PMAX Leads | Auto Locksmith | ES | NYC`.
- Landing primaria definida: `/automotriz`.
- Llamadas definidas como conversión de mayor valor, seguidas de booking y formularios cualificados.
- Preparados 10 search themes de alta intención para el límite actual de la UI de Wix.
- Definido uso de call button con `+1 646 407 7689`; descartada estrategia call-only porque Google eliminó la creación de nuevos call-only ads en febrero de 2026.
- Definida estrategia geo de cobertura real, evitando targeting de todo New York State sin justificación operativa.
- Definidas reglas de learning window Day 0 / 7 / 14 / 28 y criterio de no fragmentar presupuesto en múltiples campañas al inicio.
- Documentadas referencias oficiales Google/Wix y benchmark externo de home services únicamente como contexto de presupuesto, no como forecast.
- Creado `docs/GOOGLE-ADS-STRATEGY-2026-08-26.md` como build sheet para la sesión de montaje.
- No se activó gasto ni se inventó presupuesto de producción.

### Google Ads — clean Wix reset

- Por instrucción expresa del usuario, se eliminó la cuenta Google Ads previamente vinculada al sitio mediante la API oficial de Wix.
- Cuenta Wix eliminada: `bdec9295-6353-4a7d-9c13-3d1e9ff78144`.
- Google customer ID eliminado del setup Wix: `3274880107`.
- La cuenta eliminada figuraba `ACTIVE`, moneda `USD` y payment status `PENDING_PAYMENT` al momento del reset.
- Se ejecutó nuevamente el instalador oficial de Wix Google Ads después de la eliminación.
- Se realizó comprobación final: **no existe ninguna cuenta Google Ads vinculada actualmente al sitio**.
- Estado final documentado: `CLEAN_NO_ACCOUNT_LINKED_WIX_INTEGRATION_READY`.
- Se mantiene instalada la integración de Wix para crear una nueva cuenta desde cero en la próxima sesión.
- No se eliminaron ni modificaron SEO, Analytics, Search Console, GTM, tags ni otras integraciones no pertenecientes al reset de Google Ads.
- No se creó una nueva cuenta y no se activó gasto publicitario.

### Nota de implementación

La primera versión ampliada del JSON-LD de Home excedió el límite Wix de 4096 bytes por tag y fue rechazada antes de escribirse. Se compactó el graph a 2766 bytes manteniendo la semántica principal; la versión final fue aceptada con HTTP 200 y verificada posteriormente.
