# Implementación SEO / GEO / LLM

**Proyecto:** SC Auto Locksmith  
**Dominio:** https://www.cerrajeros-cerca24-7.com/  
**Fecha:** 2026-08-26

## Objetivo técnico

Preparar el sitio para tres capas complementarias de descubrimiento:

1. **SEO clásico:** titles, descriptions, indexabilidad, canonicals, sitemap, focus keywords y consistencia semántica.
2. **SEO local / entity SEO:** identidad del negocio, teléfono, área de servicio, tipo `Locksmith`, servicios y relaciones entre entidades.
3. **GEO / LLM:** `llms.txt`, MCP nativo de Wix, páginas canónicas, entity graph y reglas de precisión para agentes generativos.

## Identidad normalizada

Site Properties de Wix quedó como fuente de verdad:

```text
Business name: SC Auto Locksmith
Site display name: SC Auto Locksmith
Phone: +1 646 407 7689
Country: US
Language: es
Currency: USD
Time zone: America/New_York
Business model: mobile service / no public physical address
```

La descripción se normalizó a:

> Servicio móvil de cerrajería 24/7 en New York para autos, hogares y negocios. Apertura sin daños, cambio de cerraduras, duplicado y programación de llaves.

## Matriz de SEO por página

### Home — `/`

**Title**  
`Cerrajero 24 Horas en New York | SC Auto Locksmith`

**Description**  
`Cerrajero móvil 24/7 en New York para autos, hogares y negocios. Apertura sin daños, cambio de cerraduras, duplicado y programación de llaves.`

**Focus keywords**

- cerrajero 24 horas en New York — principal
- cerrajero a domicilio New York
- locksmith New York
- cerrajero cerca de mí
- cerrajero 24/7

**Schema:** `Locksmith` + `Organization`, `WebSite`, `WebPage`, `OfferCatalog`, `Service`, `ContactPoint`, `OpeningHoursSpecification`.

### Automotriz — `/automotriz`

**Title**  
`Cerrajero Automotriz 24/7 en New York | SC Auto Locksmith`

**Description**  
`Cerrajero automotriz móvil 24/7 en New York. Apertura de autos sin daños, llaves perdidas, duplicado, chip, smart keys y controles remotos.`

**Focus keywords**

- cerrajero automotriz en New York — principal
- cerrajero de autos New York
- apertura de autos New York
- duplicado llaves auto
- programación llaves con chip

**Schema:** `Service`, `WebPage`, `BreadcrumbList`, canal telefónico, horario 24/7 y catálogo de servicios automotrices.

### Contacto — `/contacto`

**Title**  
`Contacto Cerrajero 24/7 en New York | SC Auto Locksmith`

**Description**  
`Contacta a SC Auto Locksmith para cerrajería móvil 24/7 en New York. Atención para autos, hogares y negocios. Llama o solicita servicio online.`

**Schema:** `ContactPage`, `ContactPoint`, `BreadcrumbList`.

### Blog — `/blog`

**Title**  
`Blog de Cerrajería y Seguridad en New York | SC Auto Locksmith`

**Description**  
`Consejos sobre llaves de auto, cerraduras, seguridad y emergencias. Guías de SC Auto Locksmith para resolver dudas de cerrajería en New York.`

**Schema:** `Blog`, `CollectionPage`, `BreadcrumbList`.

Los posts individuales siguen usando el `BlogPosting` que Wix genera de forma nativa.

### Reserva Online — `/reserva-online`

**Title**  
`Reserva Cerrajero a Domicilio en New York | SC Auto Locksmith`

**Description**  
`Solicita online un cerrajero a domicilio en New York. Reserva atención para cerraduras, desbloqueo de autos y duplicado de llaves con SC Auto Locksmith.`

No se añadió schema manual innecesario: Wix Bookings y el flujo de reservas ya aportan su propia semántica funcional.

## Servicios Wix Bookings

### Cambio de Cerraduras

- Title: `Cambio de Cerraduras en New York | SC Auto Locksmith`
- Main focus: `cambio de cerraduras New York`

### Desbloqueo Automóvil

- Title: `Desbloqueo de Auto 24/7 en New York | SC Auto Locksmith`
- Main focus: `desbloqueo de auto New York`

### Duplicado de Llaves

- Title: `Duplicado de Llaves de Auto en New York | SC Auto Locksmith`
- Main focus: `duplicado de llaves de auto New York`

## Artículos del blog

### Servicios de Cerrajería Automotriz

- SEO title: `Cerrajería Automotriz: Seguridad y Confianza | SC Auto Locksmith`
- Main focus: `servicios de cerrajería automotriz`

### Cerrajeros en Redes Sociales

- SEO title: `Cerrajeros y Redes Sociales: Servicio Moderno | SC Auto Locksmith`
- Main focus: `cerrajeros en redes sociales`

### Consejos de Cerrajería Automotriz

- SEO title: `Consejos de Cerrajería Automotriz para tu Auto | SC Auto Locksmith`
- Main focus: `consejos cerrajería automotriz`

## JSON-LD: decisiones de arquitectura

### Por qué `Locksmith`

Schema.org define `Locksmith` como subtipo de `HomeAndConstructionBusiness` / `LocalBusiness`. Se usa el subtipo específico para reforzar la comprensión de entidad.

### Por qué no hay `address`

Wix Site Properties reporta la dirección como vacía y `isPhysical=false`. Google Search exige `address` para elegibilidad completa de rich results de `LocalBusiness`, pero introducir una dirección falsa dañaría la integridad de datos y podría crear inconsistencias con Google Business Profile, Google Ads y verificaciones futuras.

Por tanto:

- se usa `Locksmith` para clasificación semántica;
- se declara `areaServed: New York`;
- se declara el teléfono oficial;
- se declara atención 24/7 según el contenido existente;
- no se declara una ubicación física inexistente/no publicada.

### Reutilización de IDs

Los graphs usan IDs estables:

```text
https://www.cerrajeros-cerca24-7.com/#organization
https://www.cerrajeros-cerca24-7.com/#website
https://www.cerrajeros-cerca24-7.com/#webpage
https://www.cerrajeros-cerca24-7.com/automotriz#service
```

Esto permite relacionar proveedor, sitio, página y servicios sin crear entidades duplicadas.

## Meta social

Para las páginas optimizadas se sincronizaron:

- `<title>`
- meta description
- `og:title`
- `og:description`
- `twitter:title`
- `twitter:description`

La imagen social global de Wix se preservó.

## Global tags

Se mantuvieron intactos:

- Google Site Verification
- Bing Site Verification
- `og:image`

Se eliminaron los tags globales vacíos/obsoletos que no aportaban valor (`keywords`, description vacío, Facebook admins vacío).

## robots.txt

No se tocó. El default de Wix ya es superior a un archivo artesanal para este caso porque incluye:

- crawling general habilitado;
- reglas para rutas internas de Wix;
- tratamiento específico de AdsBot-Google;
- sitemap oficial.

Modificarlo sin necesidad aumentaría riesgo y no aportaría ranking.

## llms.txt / GEO

Se preservó la documentación MCP generada por Wix y se añadió una sección propia con:

- nombre oficial;
- URL oficial;
- teléfono;
- área de servicio;
- naturaleza móvil del negocio;
- disponibilidad 24/7 declarada;
- URLs canónicas de servicios y contacto;
- redes sociales oficiales;
- reglas anti-alucinación para precios, licencias, certificaciones, dirección, tiempos de llegada y cobertura.

Esto ofrece a agentes de IA una capa de verdad explícita sin eliminar la capacidad MCP del sitio.

## Indexabilidad

Se conservaron `noindex` en:

- Thank You
- Cart
- Search

Las páginas transaccionales útiles permanecen indexables.

## URLs

No se modificaron slugs, canonicals ni jerarquía. `shouldFlattenUrlHierarchy=false` se conserva para no alterar arquitectura. `shouldUsePartialRouteMatch=false` se conserva para 404 correctos.

## Validación técnica

La API de Wix confirmó HTTP 200 en todas las escrituras finales. Los JSON-LD propios quedaron debajo del límite de 4096 bytes por tag impuesto por Wix.
