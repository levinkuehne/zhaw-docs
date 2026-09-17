---
name: Markdown media organization
description: Organize pasted images in Markdown documentation using a local media folder and relative Obsidian references.
applyTo: "**/*.md"
---

# Bilder in Markdown-Dokumenten

- Ablage: `media/`-Ordner auf Modulebene (z. B. `HS26/INCO/media/`), eine Ebene über `unstructured/` und `summary/` — beide referenzieren von dort, keine Duplikate.
- Neu eingefügte oder falsch abgelegte Bilder dorthin verschieben; Ordner bei Bedarf anlegen.
- Referenz: relativer Obsidian-Wikilink inkl. Ordner, z. B. `![[../media/Pasted image 20260917083750.png]]`.
- Keine absoluten Pfade, keine Bilder im Repo-Root oder Sammelordner.
- Dateinamen beibehalten, ausser Umbenennung ist ausdrücklich gewünscht.
- Unreferenziertes Bild (z. B. Duplikat) → nicht kommentarlos verschieben/löschen, erst nachfragen.
- Nach jeder Änderung: Referenzen prüfen, keine toten/veralteten Links.
