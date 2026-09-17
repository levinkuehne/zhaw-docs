---
name: Markdown media organization
description: Organize pasted images in Markdown documentation using a local media folder and relative Obsidian references.
applyTo: "**/*.md"
---

# Bilder in Markdown-Dokumenten

- Lege Bilder, die in einer Markdown-Dokumentation verwendet werden, in einem `media/`-Ordner neben der jeweiligen Markdown-Datei ab.
- Verschiebe neu eingefügte oder am falschen Ort liegende Bilddateien in diesen `media/`-Ordner. Erstelle den Ordner, falls er noch nicht existiert.
- Referenziere Bilder mit einem relativen Obsidian-Wikilink einschließlich des Ordners, zum Beispiel `![[media/Pasted image 20260917083750.png]]`.
- Verwende keine absoluten Pfade und lasse verwendete Bilder nicht im Repository-Root oder in einem globalen Sammelordner liegen.
- Behalte die Dateinamen der Bilder bei, sofern keine Umbenennung ausdrücklich gewünscht ist.
- Prüfe nach der Änderung, dass jede Bildreferenz auf eine tatsächlich vorhandene Datei zeigt und keine veraltete Referenz zurückbleibt.
