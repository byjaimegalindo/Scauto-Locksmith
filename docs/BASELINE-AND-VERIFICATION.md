# Baseline y verificación técnica

**Fecha:** 2026-08-26  
**Sitio:** https://www.cerrajeros-cerca24-7.com/  
**Wix Site ID:** `f5deb336-2519-4961-8fc3-2a178cd2b94e`

## 1. Baseline encontrado

### Identidad Wix

Antes de la intervención, Site Properties reportaba:

- `businessName`: `cerrajeroscautolocksmith`
- `siteDisplayName`: `Locksmith Cerrajero a Domicilio `
- descripción: `Servicios de cerrajería a tu alcance, siempre contigo.`
- teléfono: no configurado en Site Properties
- dirección: objeto vacío, `isPhysical=false`
- país: `US`
- idioma: `es`
- moneda: `USD`
- zona horaria: `America/New_York`

El teléfono `+1 646 407 7689` ya aparecía en metadatos/schema de páginas, pero no estaba normalizado en la fuente de verdad de Site Properties.

### SEO global

Se encontraron estos tags globales:

- verificación Bing (`msvalidate.01`) — válida y preservada
- verificación Google (`google-site-verification`) — válida y preservada
- `og:image` — válida y preservada
- `description` vacío — eliminado
- `keywords` vacío — eliminado
- `fb_admins_meta_tag` vacío — eliminado

### Páginas estáticas

| Página | ID Wix | Estado baseline |
|---|---|---|
| Home | `c1dmp` | Indexable; title/description mejorables; JSON-LD existente |
| Automotriz | `jhpm6` | Indexable; descripción genérica; JSON-LD existente |
| Blog | `gsxpc` | Indexable; descripción genérica; JSON-LD existente |
| Contacto | `zhs4k` | Indexable; descripción genérica; JSON-LD existente |
| Reserva Online | `sfajx` | Indexable; title/description genéricos; sin JSON-LD propio |
| Thank You | `cfr37` | `noindex` correcto |
| Cart | `kaocc` | `noindex` correcto |
| Search | `yxmfd` | `noindex` correcto |

No se modificaron los `noindex` correctos de páginas utilitarias.

### Wix Bookings

Se encontraron 3 servicios indexables:

1. Cambio de Cerraduras
2. Desbloqueo Automóvil
3. Duplicado de Llaves

Los tres heredaban metadata funcional, pero sin suficiente señal geográfica New York ni consistencia de marca.

### Blog

Se encontraron 3 artículos publicados. Wix ya genera `BlogPosting` estructurado por patrón para cada post. Por ese motivo no se agregó un segundo `BlogPosting` manual: solo se optimizaron title, description, social metadata y focus keywords.

### robots.txt

El `robots.txt` nativo de Wix ya era apropiado y se dejó intacto:

- `Allow: /`
- bloqueo de parámetros de lightbox
- reglas específicas de optimización para `AdsBot-Google-Mobile` y `AdsBot-Google`
- sitemap: `https://www.cerrajeros-cerca24-7.com/sitemap.xml`

### SEO User Config

Configuración verificada:

- `shouldFlattenUrlHierarchy=false`
- `shouldUsePartialRouteMatch=false`

El segundo valor garantiza respuestas 404 reales para URLs inexistentes y evita soft-404 por coincidencia parcial.

### llms.txt

El archivo ya existía, era público y conservaba documentación MCP nativa de Wix. Se decidió **preservar ese contenido** y añadir una capa autoritativa en lugar de reemplazarlo.

## 2. Estado post implementación verificado

### Business Info

- `siteDisplayName`: **SC Auto Locksmith**
- `businessName`: **SC Auto Locksmith**
- teléfono: **+1 646 407 7689**
- descripción: optimizada para servicio móvil 24/7 en New York
- logo: normalizado al asset Wix existente
- dirección: sigue sin falsificarse; `isPhysical=false`

### SEO global

Después de la limpieza solo permanecen:

- Bing verification
- Google verification
- `og:image`

### Páginas optimizadas

| Página | Nuevo title | JSON-LD propio |
|---|---|---:|
| Home | `Cerrajero 24 Horas en New York | SC Auto Locksmith` | Sí |
| Automotriz | `Cerrajero Automotriz 24/7 en New York | SC Auto Locksmith` | Sí |
| Contacto | `Contacto Cerrajero 24/7 en New York | SC Auto Locksmith` | Sí |
| Blog | `Blog de Cerrajería y Seguridad en New York | SC Auto Locksmith` | Sí |
| Reserva | `Reserva Cerrajero a Domicilio en New York | SC Auto Locksmith` | No, deliberado |

Los JSON-LD desplegados fueron verificados dentro del límite técnico de Wix de 4096 bytes por tag:

- Home: 2766 bytes
- Automotriz: 2187 bytes
- Contacto: 1080 bytes
- Blog: 1047 bytes

### Servicios Bookings

Títulos desplegados:

- `Cambio de Cerraduras en New York | SC Auto Locksmith`
- `Desbloqueo de Auto 24/7 en New York | SC Auto Locksmith`
- `Duplicado de Llaves de Auto en New York | SC Auto Locksmith`

Todos tienen descriptions y focus keywords propios.

### Blog posts

Los tres posts tienen metadata propia y siguen heredando `BlogPosting` nativo de Wix. Esta combinación evita duplicación innecesaria de schema y conserva los datos de autor/fecha generados por Wix.

### llms.txt

Verificación final:

- visible públicamente: sí (`hidden=false`)
- bloque MCP Wix: preservado
- bloque `## Datos oficiales y contexto para IA`: presente
- contiene reglas explícitas para no inventar dirección, precios, licencias, certificaciones, tiempos de llegada ni cobertura no declarada

## 3. Limitaciones y decisiones de integridad

Google Search exige `address` como propiedad obligatoria para elegibilidad completa de rich results de `LocalBusiness`. Wix declara este negocio como móvil/no físico y no tiene dirección pública. Se eligió **no falsificar una dirección**. El entity graph usa el tipo semántico `Locksmith`, teléfono, área atendida, horarios y servicios para comprensión de entidad, pero no se promete un rich result local hasta contar con datos físicos válidos cuando corresponda.

## 4. Evidencia de ejecución

Todas las escrituras de SEO individual, Bookings, Blog y `llms.txt` devolvieron HTTP 200. La verificación posterior confirmó que los valores quedaron guardados en Wix. Las páginas estáticas se escribieron tanto en revisión guardada como publicada para mantener consistencia entre editor y sitio live.
