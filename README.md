# SC Auto Locksmith — SEO / GEO / Google Ads Readiness

Repositorio técnico de control para **SC Auto Locksmith** y el sitio Wix **https://www.cerrajeros-cerca24-7.com/**.

## Objetivo

Centralizar la preparación técnica de SEO tradicional, SEO local, GEO/LLM, datos estructurados y readiness para Google Ads, dejando una trazabilidad reproducible de los cambios aplicados en Wix.

## Identificación del proyecto

- **Sitio:** SC Auto Locksmith
- **Dominio:** https://www.cerrajeros-cerca24-7.com/
- **Wix Site ID:** `f5deb336-2519-4961-8fc3-2a178cd2b94e`
- **Idioma principal:** español (`es-US`)
- **Mercado:** New York, United States
- **Moneda Wix:** USD
- **Teléfono oficial configurado:** `+1 646 407 7689`
- **Modelo operativo:** servicio móvil; Wix no tiene una dirección física pública configurada.

## Estado al 26 de agosto de 2026

### SEO / GEO / LLM

**Implementado y verificado en Wix:**

- Identidad de negocio normalizada a **SC Auto Locksmith** en Site Properties.
- Teléfono oficial incorporado a la fuente de verdad de Wix.
- Descripción del negocio optimizada para cerrajería móvil 24/7 en New York.
- Meta tags globales depurados conservando las verificaciones de Google/Bing y la imagen social.
- SEO individual optimizado en Home, Automotriz, Contacto, Blog y Reserva Online.
- SEO individual optimizado en 3 servicios de Wix Bookings.
- SEO individual optimizado en 3 artículos existentes del blog.
- Focus keywords definidos por intención y página.
- JSON-LD desplegado en Home, Automotriz, Contacto y Blog.
- Home modelada semánticamente como `Locksmith` + `Organization`, sin inventar dirección física.
- `llms.txt` enriquecido con una capa de datos oficiales para agentes de IA, preservando el bloque MCP nativo de Wix.
- `robots.txt` nativo verificado: sitemap presente y reglas específicas para AdsBot-Google activas.
- Configuración SEO de rutas verificada: 404 real (`shouldUsePartialRouteMatch=false`) y sin cambios masivos de URL.

### Google Ads

La arquitectura queda preparada, pero **no debe considerarse una campaña autorizada para servir todavía** por dos condiciones externas:

1. Google restringe los anuncios de **locksmith services en Estados Unidos** y exige **Advanced Verification** antes de permitir que los anuncios se publiquen.
2. La activación de una campaña requiere un presupuesto diario explícito; ese valor no se inventa ni se asigna automáticamente.

La integración Wix Google Ads fue auditada y se identificó el endpoint actual de instalación, pero la instalación automática no se completó desde el entorno de esta sesión. Ver `docs/GOOGLE-ADS-READINESS.md`.

## Documentación

- `docs/BASELINE-AND-VERIFICATION.md` — estado encontrado, hallazgos y verificación post implementación.
- `docs/SEO-GEO-LLM-IMPLEMENTATION.md` — matriz de cambios y decisiones técnicas.
- `docs/GOOGLE-ADS-READINESS.md` — arquitectura de campaña, conversiones, compliance y checklist de lanzamiento.
- `schema/home.jsonld` — esquema desplegado en Home.
- `schema/automotriz.jsonld` — esquema desplegado en la landing Automotriz.
- `llms/authoritative-context.md` — bloque semántico añadido a `llms.txt`.
- `CHANGELOG.md` — registro de cambios.

## Principios de implementación

- No se cambiaron slugs ni URLs existentes.
- No se inventaron dirección, licencias, certificaciones, precios ni tiempos de llegada.
- Se preservaron verificaciones de motores de búsqueda.
- Se mantuvo el `robots.txt` nativo de Wix porque ya contiene reglas adecuadas para indexación, sitemap y AdsBot.
- En blog se conserva el `BlogPosting` nativo de Wix para evitar duplicidad de schema.
- El marcado `Locksmith` de Home tiene finalidad semántica y de entity understanding. Google exige una dirección física para elegibilidad completa de rich results de `LocalBusiness`; como Wix declara el negocio como no físico, no se falsificó ese campo.

## Próximo gate de producción

Completar **Google Advanced Verification para Locksmith (US)**, terminar la instalación/cuenta Google Ads en Wix, obtener recomendaciones de presupuesto/geo/assets desde la API de Wix/Google y crear primero la campaña en `PAUSED`. Solo después de aprobar un presupuesto diario concreto debe ejecutarse el launch.
