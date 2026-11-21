# DDH Roleplay ER:LC status — GitHub-only

Bestanden:
- `index.html` — de website
- `.github/workflows/update-erlc.yml` — haalt elke 5 minuten ER:LC-status op
- `status.json` — wordt automatisch door GitHub Actions aangemaakt en bijgewerkt

## Installeren
1. Zet `index.html` in de hoofdmap van je GitHub-repository.
2. Zet `.github/workflows/update-erlc.yml` op exact dat pad.
3. Open je repository: **Settings → Secrets and variables → Actions → New repository secret**.
   - Name: `ERLC_API_KEY`
   - Secret: je ER:LC Server-Key
4. Open **Settings → Pages** en kies **Deploy from a branch**, branch `main`, folder `/ (root)`.
5. Open **Actions**, kies **Update ERLC server status**, klik **Run workflow**.
6. Wacht tot de actie groen is en open je GitHub Pages-site.

De site zelf gebruikt alleen `index.html` en `status.json`. De ER:LC-sleutel staat als GitHub Secret in Actions en komt niet in de browser terecht.
GitHub Actions draait volgens de planning ongeveer elke 5 minuten; handmatig verversen op de website haalt de laatst gepubliceerde status op, niet direct een nieuwe ER:LC API-aanvraag.
