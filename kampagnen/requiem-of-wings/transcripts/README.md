# Transkripte – Requiem of Wings

Roh-Material aus den Sessions: Voll-Transkripte (z.B. aus Aufnahmen) oder
händische Mitschriften. Diese Dateien sind **Quellen**, nicht die kuratierte
Session-Story — die liegt in `../sessions/`.

## Wofür sind die da?
- **Manuelle Pflege:** Raffi liest sie, um die `sessions/`-Files nachzuziehen,
  oder lässt sich von Biblo gezielt Stellen rauspicken ("zitier mal was Lazar
  beim Maskenball gesagt hat").
- **Last-Resort-Lookup für Biblo:** Biblo greift hier nur ran, wenn die
  kuratierte `sessions/<nr>.md` eine Frage nicht abdeckt — nicht als Default.
  So bleibt das Token-Budget klein.

## Konvention
- Dateiname: `<session-nr>-<slug>.md`, gleicher Slug wie die kuratierte Session.
  Beispiel: `001-masks-and-monsters.md` ↔ `../sessions/001-masks-and-monsters.md`.
- Format ist egal (Fließtext, bullets, copy-paste vom Discord) — Hauptsache lesbar.
- Out-of-Game / Privatsachen rauseditieren bevor committed wird.

## Workflow nach einer Session
1. Transkript/Mitschrift hier reinkippen unter passendem Namen.
2. Eintrag in `_kontext/manifest.md` ergänzen, sonst sieht Biblo's Tool-Use
   die Datei nicht.
3. Optional: Biblo bitten, die `sessions/<nr>.md` aus dem Transkript
   nachzuziehen ("update Session 003 aus dem Transkript").
