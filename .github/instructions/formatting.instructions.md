---
name: Module notes structuring
description: Keep raw dated notes in unstructured/ and maintain structured summary files per module in summary/.
applyTo: "HS26/**/*.md"
---

# Notizen pro Modul

Pro Modul (`HS26/<Modul>/`): `unstructured/`, `summary/`, `media/`.

## unstructured/

- Eine Datei pro Kalenderwoche: `<Jahr>-KW<Nummer>.md` (z. B. `2026-KW38.md`).
- Frontmatter in jeder Datei:
  ```yaml
  ---
  date: 2026-09-17
  module: INCO
  ---
  ```
- Bildpfade pflegen (siehe `media.instructions.md`).
- Inhalt unangetastet lassen!
- Angepasst werden darf:
  — Gross- und Kleinschreibung
  - Überschriften
  - Reihenfolge, wo sinnvoll
  - Stil (Listen, Tabellen, Formeln, Codeblöcke, Blockquotes (keine Callouts!))


## summary/

- Modulzusammenfassungen werden in `summary/` erstellt.
- Nur auf Anfrage erstellen!
- Falls die Datei schon existiert: **Update: inkrementell mergen**, nicht neu generieren. Bestehendes lesen, nur Neues/Geändertes einordnen, manuelle Ergänzungen erhalten.
- Je nach grösse des Themas:
  - Eine Datei pro Modul, `<Modulkürzel>.md` (z. B. `INCO.md`).
  - Nach Themen splitten (z. B. `Digitaltechnik.md`), `<Modulkürzel>.md` wird Übersicht mit Links.
- Gliederung: thematisch, nicht chronologisch.
- Bilder per relativem Link aus `../media/` übernehmen.
- Manchmal enthalten Bilder Texte / Formeln, welche als Text übernommen werden sollten.
- Keine erfundenen Inhalte. Unklares wörtlich übernehmen statt interpretieren.
- Sprache/Fachbegriffe wie im Original (Deutsch).
- Obsidian-Formatierung nutzen: Callouts (`> [!note]`, `[!warning]`, `[!tip]`, `[!example]`), Tabellen statt Listen wo passend, Codeblöcke für Formeln/Gleichungen.
- Rohnotizen bleiben unverändert als Archiv bestehen.
