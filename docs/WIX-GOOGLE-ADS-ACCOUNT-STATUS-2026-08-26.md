# Wix Google Ads Account Status — 2026-08-26

## Project

- Site: SC Auto Locksmith
- Domain: https://www.cerrajeros-cerca24-7.com/
- Wix site ID: `f5deb336-2519-4961-8fc3-2a178cd2b94e`
- Currency for future Wix-managed setup: USD

## Current state — clean Wix start

The previously linked Google Ads account was explicitly removed at the user's request so the advertising setup can be rebuilt from Wix from zero.

Actions completed through Wix on 2026-08-26:

- Read the Google Ads account currently linked to this Wix site.
- Deleted the linked Wix Google Ads account mapping using the official Wix Google Ads Account API.
- Removed Google Ads account ID `bdec9295-6353-4a7d-9c13-3d1e9ff78144` / Google customer ID `3274880107` from this Wix site's Google Ads setup.
- The removed account had currency `USD`, account status `ACTIVE`, and payment status `PENDING_PAYMENT` at the time of removal.
- Re-ran the Wix Google Ads installer after deletion. The integration is installed and ready for a new Wix-native account setup.
- No replacement Google Ads account has been created yet.
- No campaign exists from this reset operation.
- No advertising spend was activated.

## Intended next state

The project is intentionally parked in this state:

`NO_GOOGLE_ADS_ACCOUNT_LINKED_READY_FOR_NEW_WIX_ACCOUNT`

The next paid-media session should begin inside Wix by creating a completely new Google Ads account from the Wix-managed flow in USD, then configuring billing, conversion actions, targeting, assets and the first PMAX Leads campaign.

## Next Wix-native build sequence

1. Create a fresh Google Ads account from Wix in USD.
2. Complete Wix/Google billing for that new account.
3. Read the new account's conversion actions.
4. Confirm the real operational geo area before spending.
5. Generate/review PMAX Leads text assets and search themes.
6. Use approved real business imagery.
7. Obtain the live Google/Wix budget recommendation.
8. Create the campaign as `PAUSED`.
9. Review campaign assets, geo, conversions and daily budget.
10. Launch only after explicit budget approval and any Google compliance requirements presented to the new account are satisfied.

## Policy note

Using Google Ads through Wix simplifies account and campaign management, but it does not override Google policy requirements attached to the advertised vertical. If Google presents an advertiser/locksmith verification gate on the new Wix-created account, it must be completed rather than bypassed.

## Campaign strategy source

See:

- `docs/GOOGLE-ADS-STRATEGY-2026-08-26.md`
- `docs/GOOGLE-ADS-READINESS.md`
