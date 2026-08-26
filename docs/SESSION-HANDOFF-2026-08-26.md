# Session Handoff — SC Auto Locksmith

**Date:** 2026-08-26  
**Purpose:** Exact checkpoint for resuming the Google Ads setup manually from Wix, with ChatGPT assisting screen by screen.

## Current project state

Site: **SC Auto Locksmith**  
Domain: `https://www.cerrajeros-cerca24-7.com/`  
Wix site ID: `f5deb336-2519-4961-8fc3-2a178cd2b94e`  
Site currency: **USD**

### SEO / GEO / LLM

Completed and already deployed:

- Technical SEO foundation.
- Page metadata optimization.
- Advanced JSON-LD for key pages.
- Wix Business Info normalization.
- `llms.txt` authoritative business block while preserving Wix MCP content.
- robots/sitemap/routing validation.
- Wix Bookings and Wix Blog metadata optimization.
- Google Ads strategy and readiness documentation.

Do **not** redo these items unless a later audit finds a real defect.

## Google Ads — final reset for manual setup

Two Wix-linked Google Ads accounts were removed during the cleanup process and must not be reused from Wix:

1. Previous linked account:
   - Wix Google Ads account ID: `bdec9295-6353-4a7d-9c13-3d1e9ff78144`
   - Google customer ID: `3274880107`

2. Fresh Wix-created account that was created during assisted setup and then deleted so the user can restart manually:
   - Wix Google Ads account ID: `db1bf8aa-42f8-4bf9-bad0-db98426cc00f`
   - Google customer ID: `5615631490`
   - Before deletion: currency `USD`, budget `0`, spent budget `0`, payment status `PENDING_PAYMENT`, account status `ACTIVE`

Immediately before deleting the second account, Wix returned `campaigns: []` — therefore **no campaign existed to delete**.

After deletion, `Get Account For Current Site` returned an empty response `{}`.

Current verified checkpoint:

`ZERO_WIX_GOOGLE_ADS_ACCOUNT_NO_CAMPAIGNS_MANUAL_SETUP_READY`

Meaning:

- No Google Ads account is currently linked to the Wix site.
- No Wix Google Ads campaign exists.
- No advertising spend was activated.
- Site SEO, Analytics, Search Console, GTM, Google verification tags and unrelated integrations were intentionally left untouched.
- The next setup will be performed manually by the user in Wix, with ChatGPT assisting each screen/decision.

## Operating mode from now on

**Manual-first.** Do not automatically create an Ads account, campaign, billing subscription, budget or launch unless the user explicitly changes this instruction.

When the user opens Wix Google Ads, assist step by step:

1. Read the screen/option the user is seeing.
2. Recommend exactly which option/value to choose based on the documented strategy.
3. Wait for the user to complete that screen manually.
4. Continue to the next screen.
5. Keep the campaign strategy consistent; do not improvise away from the plan without evidence.

## Campaign strategy — fixed reference

Working campaign concept:

`SCAL | PMax Leads | Auto Locksmith | ES | NYC | 2026-08`

Strategic direction:

- Campaign type: **Performance Max Leads** if Wix offers it for the new setup.
- Primary landing: `https://www.cerrajeros-cerca24-7.com/automotriz`.
- Primary language: Spanish.
- Business objective: qualified service leads.
- Conversion priority: qualified phone calls first, then booking/service requests, then qualified forms.
- Initial service focus: automotive locksmith intent rather than broad generic traffic.
- Geography: only the real service area; do not target all New York State by default.
- Assets: truthful business copy; use real business imagery where possible.
- Budget: do not invent. Use Wix/Google's live recommendation, then compare it against the business's real acceptable daily spend.
- Launch discipline: build and review before activating spend.
- Do not use unverifiable claims such as “#1”, “guaranteed”, “cheapest”, certifications, or exact arrival times unless documented.

## Supporting documents

- `docs/GOOGLE-ADS-STRATEGY-2026-08-26.md`
- `docs/GOOGLE-ADS-READINESS.md`
- `docs/WIX-GOOGLE-ADS-ACCOUNT-STATUS-2026-08-26.md`
- `CHANGELOG.md`

## Important operating rules

- Do not reconnect either deleted Google Ads account from Wix.
- Do not create anything automatically while manual-first mode is active.
- Do not activate spend before the user reviews and approves the live budget.
- Do not invent a physical address or service coverage.
- Do not alter URLs/slugs merely for Ads.
- Do not disturb the completed SEO/GEO/LLM setup without a concrete reason.
- Do not attempt to bypass Google policy or verification requirements by misrepresenting the business category, destination or services.

## Resume instruction

> Retomemos SC Auto Locksmith desde `docs/SESSION-HANDOFF-2026-08-26.md`. Google Ads en Wix está en cero: sin cuenta vinculada y sin campañas. El montaje será manual por el usuario y ChatGPT asistirá pantalla por pantalla aplicando la estrategia documentada. No crees automáticamente cuenta, campaña, billing ni presupuesto salvo instrucción expresa.
