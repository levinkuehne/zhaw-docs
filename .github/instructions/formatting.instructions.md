---
name: Module notes structuring
description: Keep raw dated notes in unstructured/ and maintain structured summary files per module in summary/.
applyTo: "HS26/**/*.md"
---

# Notizen pro Modul

Pro Modul (`HS26/<Modul>/`): `unstructured/`, `summary/`, `media/`.

## unstructured/

- Eine Datei pro Kalenderwoche: `<Jahr>-KW<Nummer>.md` (z. B. `2026-KW38.md`).
- Frontmatter statt Text im Inhalt:
  ```yaml
  ---
  date: 2026-09-17
  module: INCO
  ---
  ```
- Inhalt unangetastet lassen
— Gross- und Kleinschreibung / Überschriften / Reihenfolge / Stil (Beispielsweise auch Listen, Tabellen, Formeln, Codeblöcke, Blockquotes) darf angepasst werden, wenn es der Lesbarkeit dient, aber keine Inhalte ändern.
- Blockquotes nur als einfaches `>`, keine Callouts (kein `[!note]`/`[!tip]`/etc.) — Callouts sind `summary/` vorbehalten.
- Bildpfade pflegen (siehe `media.instructions.md`).


## summary/

- Standard: eine Datei pro Modul, `<Modulkürzel>.md` (z. B. `INCO.md`).
- Zu gross → nach Themen splitten (z. B. `Digitaltechnik.md`), `<Modulkürzel>.md` wird Übersicht mit Links.
- **Trigger: nur auf explizite Aufforderung** ("strukturiere INCO", Meldung gegen Modulende). Nicht automatisch bei jeder Rohnotiz — unnötiger Aufwand.
- **Update: inkrementell mergen**, nicht neu generieren. Bestehendes lesen, nur Neues/Geändertes einordnen, manuelle Ergänzungen erhalten.
- Gliederung: thematisch, nicht chronologisch.
- Duplikate/Roh- vs. Reinschrift-Varianten zusammenführen, Inhalt vollständig behalten.
- Bilder per relativem Link aus `../media/` übernehmen.
- Keine erfundenen Inhalte. Unklares wörtlich übernehmen statt interpretieren.
- Sprache/Fachbegriffe wie im Original (Deutsch).
- Obsidian-Formatierung nutzen: Callouts (`> [!note]`, `[!warning]`, `[!tip]`, `[!example]`), Tabellen statt Listen wo passend, Codeblöcke für Formeln/Gleichungen.
- Rohnotizen bleiben unverändert als Archiv bestehen.
