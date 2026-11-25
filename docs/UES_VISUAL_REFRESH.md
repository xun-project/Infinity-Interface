# UltraNote visual refresh — legacy Infinity mining pool

This branch applies the newer UltraNote navy/cyan/violet visual identity to the existing XUNI mining-pool interface. It does **not** convert the project into a UES pool, ecosystem homepage or explorer.

## Changes
- `themes/custom.css` — responsive neon-blue dashboard shell, controls, cards, table and chart surrounds, banner, navigation, accessibility and reduced-motion styling.
- `index.html` — loads the visual layer last, updates the title/header and makes the legacy-XUNI status explicit.
- `admin.html` and `themes/admin-refresh.css` — corresponding admin shell visual refresh.

## Invariants
- Preserve API endpoint, RPC, wallet lookup, cookies, translations, polling logic, market chart calculations and route fragments.
- Leave all XUNI addresses, historic network data and existing pool configuration untouched. UES is not launched; never display invented live UES mining data, UES wallet functionality or exchange rates.
- Do not alter `config.js`, `js/common.js` or pool implementation for this design pass.
- This is a front-end styling update; no deployment or functional verification has been performed.

## Review / manual smoke tests
1. Compare desktop (1440px), tablet (768px), phone (390px) and 320px widths. No horizontal overflow, clipped navigation or inaccessible form controls.
2. Verify dashboards, charts and pool stats update against a permitted local or synthetic API fixture (do not activate the old endpoint during review).
3. Verify worker stats wallet lookup, blocks, payments, top miners, resources, language selector, mining calculator and mobile navbar.
4. Test admin login/authorization in an appropriate safe test deployment; this UI change does not add or improve authentication.
5. Confirm no UES live status is shown, no hardcoded data fabricated and all links retain previous behavior. Confirm no user secrets or wallet credentials are requested.
6. Check heading semantics, focus outlines, color contrast, zoom at 200%, reduced motion, and browser console/network errors.
7. Review external legacy endpoints and outdated dependencies separately as security/retirement work; do not silently redirect or reactivate them.

## Future architectural decision
If the intention is the **new UES marketing website**, make it a separate site/repository, or explicitly approve replacing the old pool UI after verifying no active dependencies. Do not reinterpret this old mining dashboard as a live UES service.
