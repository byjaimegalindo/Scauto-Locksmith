# Google Ads Readiness — SC Auto Locksmith

**Fecha:** 2026-08-26  
**Sitio:** https://www.cerrajeros-cerca24-7.com/  
**Moneda prevista:** USD

## Resumen ejecutivo

El sitio ya quedó preparado en SEO, entity data, Wix Business Info, landing metadata, schema, robots y llms.txt. Sin embargo, un negocio de **locksmith en Estados Unidos** tiene una condición regulatoria de Google Ads que no se puede omitir: **Advanced Verification**.

Google mantiene a Locksmith Services (United States / Canada) dentro de “Other restricted businesses: Local services”. En Estados Unidos la cuenta debe completar Advanced Verification antes de que los anuncios de cerrajería puedan servir.

Fuente oficial:

- https://support.google.com/adspolicy/answer/13527633?hl=en
- https://support.google.com/adspolicy/answer/16114090?hl=en

No se debe intentar eludir esta verificación modificando artificialmente el destino, categoría o copy de la campaña.

## Estado de la integración Wix Google Ads

### Detectado

El sitio no mostraba la app Google Ads dentro de la lista de apps instaladas al iniciar la auditoría.

La receta actual de Wix exige este orden:

1. instalar Wix Google Ads;
2. crear/vincular el Google Ads account;
3. consultar conversion actions;
4. generar assets, geos y budget recommendations;
5. crear campaña inicialmente `PAUSED`;
6. revisar budget/assets;
7. ejecutar Launch.

Se detectó que la receta de alto nivel de Wix contenía una ruta antigua para el instalador. La documentación de método vigente indica:

```text
POST https://www.wixapis.com/_serverless/pa-google/v1/install-if-not-installed
```

La operación automática de instalación no pudo completarse desde el entorno de esta sesión. No se simuló una instalación ni se marcó la cuenta como creada.

## Bloqueadores reales antes de “Launch”

### Gate A — Advanced Verification

**Obligatorio para locksmith services en USA.** Debe quedar aprobado por Google.

### Gate B — presupuesto explícito

Wix/Google devuelve presupuesto recomendado en micros, pero la campaña no debe lanzarse con una cifra inventada. Se necesita un daily budget final y explícito en USD.

### Gate C — geografía operativa exacta

El sitio declara “New York”, pero Wix no tiene una dirección física pública y el negocio es móvil. Antes de activar gasto se debe confirmar si la cobertura significa:

- New York City;
- boroughs concretos;
- un radio/área específica;
- o New York State.

No se debe pagar tráfico fuera de la cobertura real.

## Arquitectura recomendada en Wix: Performance Max Leads

Para el primer ciclo se recomienda **`PERFORMANCE_MAX_LEADS`**, porque el objetivo del sitio es captación de contactos/llamadas/reservas, no ecommerce.

### Objetivo

**Lead generation** con prioridad:

1. llamadas;
2. solicitud/reserva online;
3. contacto/form submission;
4. posteriormente, leads cualificados/offline conversion si el flujo lo permite.

### Landing principal

**Primaria:** `https://www.cerrajeros-cerca24-7.com/automotriz`

Motivo: es la landing más específica, tiene intención transaccional clara, schema `Service`, teléfono, 24/7 y servicios concretos de apertura/llaves.

**Secundaria/general:** `https://www.cerrajeros-cerca24-7.com/`

Debe usarse para cobertura residencial/comercial o una campaña general posterior.

## Search themes iniciales — español

Se preparan como señales, no como promesa de match exacto:

```text
cerrajero 24 horas new york
cerrajero cerca de mi
cerrajero a domicilio new york
cerrajero automotriz new york
cerrajero de autos new york
locksmith new york
locksmith near me
apertura de autos new york
desbloqueo de auto new york
llaves perdidas auto new york
duplicado de llaves de auto
programacion de llaves con chip
smart key locksmith
car key replacement new york
cambio de cerraduras new york
```

Tras el launch, deben revisarse Search Terms reales y calidad de lead, no solo clicks.

## Negativos / exclusiones iniciales

Prioridad de exclusión si aparecen en términos de búsqueda:

```text
empleo
trabajo
jobs
salary
curso
cursos
training
certification
DIY
how to
tutorial
gratis
free
maquina para copiar llaves
locksmith tools
wholesale
```

No conviene sobre-negativizar antes de obtener datos reales.

## Asset group — directrices

### Business name

`SC Auto Locksmith`

### Mensaje central

Servicio móvil de cerrajería 24/7 en New York, con foco inicial en cerrajería automotriz: apertura de autos, llaves perdidas, duplicado, programación de chip/smart keys y controles.

### CTA recomendado

`CONTACT_US`

### Headlines base para evaluación de Wix/Google

Deben validarse después con `text-asset-suggestions` y políticas:

```text
Cerrajero 24/7 en New York
Cerrajero Automotriz 24/7
Apertura de Autos Sin Daños
¿Perdiste las Llaves del Auto?
Duplicado de Llaves de Auto
Programación de Llaves Chip
Smart Keys y Controles
Servicio Móvil de Cerrajería
SC Auto Locksmith
Solicita Servicio Ahora
```

### Long headline base

`Cerrajero automotriz móvil 24/7 en New York para apertura, llaves, chip y controles`

### Descriptions base

```text
Servicio móvil para apertura de autos, llaves perdidas, duplicado y programación.
Contacta a SC Auto Locksmith para atención de cerrajería automotriz en New York.
```

No se deben usar claims como “#1”, “garantizado”, “el más barato”, tiempos exactos de llegada o certificaciones no verificadas.

## Imágenes

**No generar automáticamente assets de Local Services Ads para New York.** Desde agosto de 2026, las políticas de Local Services Ads introducen restricciones sobre imágenes generadas/editadas con IA en New York State. Para mantener máxima compatibilidad, usar fotografías reales del negocio/equipo/vehículos/trabajo y assets propios.

Fuente oficial de referencia:

- https://support.google.com/adspolicy/answer/6245891?hl=en

Para PMAX ordinario deben seguirse igualmente las políticas generales de assets y representación veraz.

## Conversion tracking

Al existir la cuenta Google Ads, ejecutar inmediatamente:

```text
GET /accounts/current-site/conversion-actions
```

Validar que las conversiones orientadas a lead estén disponibles y evitar optimizar hacia Page View como objetivo principal cuando existan señales más valiosas.

Prioridad esperada:

```text
Phone Call / click-to-call
Booking / lead submission
Contact form
WhatsApp click (si está disponible como evento/conversión válida)
```

No marcar “Page View” como conversión primaria de negocio si eso distorsiona el aprendizaje de la campaña.

## Budget

No se fija manualmente en este documento. Una vez exista la cuenta, utilizar:

```text
POST /google-ads/v1/budget-recommendation
campaignType: PERFORMANCE_MAX_LEADS
currency: USD
countryCodes: US
languageCodes: es
```

Presentar opciones low/recommended/high convertidas de micros a USD/día y elegir el presupuesto antes del Launch.

## Flujo exacto de salida a producción

1. Completar Advanced Verification de Google para locksmith US.
2. Instalar/verificar Wix Google Ads.
3. Crear o detectar la cuenta Google Ads en USD.
4. Leer conversion actions.
5. Resolver geo target exacto mediante `geo-options`.
6. Generar `text-asset-suggestions`.
7. Usar fotografías reales y assets aprobados.
8. Generar `search-theme-suggestions`.
9. Generar `budget-recommendation`.
10. Crear la campaña `PERFORMANCE_MAX_LEADS` con `status=PAUSED`.
11. Verificar assets, geo, conversiones, URL final y presupuesto diario.
12. Ejecutar Launch únicamente después de Advanced Verification + budget explícito.
13. Esperar fase de aprendizaje y medir leads reales, no solo CTR/clicks.

## KPIs de control

Primarios:

- leads válidos;
- costo por lead válido;
- llamadas con intención comercial;
- reservas/form submissions;
- tasa de conversión landing → lead.

Secundarios:

- clicks;
- CTR;
- CPC;
- impression share cuando sea aplicable;
- search terms relevantes/no relevantes.

## Criterio de optimización post-launch

No efectuar cambios bruscos durante la fase inicial de aprendizaje salvo errores de política, geografía, presupuesto o tráfico evidentemente irrelevante. Crear un baseline de 7/14/28 días y documentar ajustes sobre evidencia de conversiones.
