# DM — Diskrete Mathematik

> [!info] Kursseite
> https://olodnad.gitlab.io/diskmathzhaw/

## Spick: Symbolübersicht

### Junktoren

| Symbol  | Name        | Gesprochen             | Wahr, wenn …                                          | Mengen-Pendant        |
| ------- | ----------- | ---------------------- | ----------------------------------------------------- | --------------------- |
| ¬𝐴     | Negation    | nicht 𝐴               | 𝐴 falsch ist                                         | 𝐶 \ 𝐴 (Differenz)   |
| 𝐴 ∧ 𝐵 | Konjunktion | 𝐴 und 𝐵              | beide wahr sind                                       | 𝐴 ∩ 𝐵 (Schnitt)     |
| 𝐴 ∨ 𝐵 | Disjunktion | 𝐴 oder 𝐵             | mindestens eines wahr ist                             | 𝐴 ∪ 𝐵 (Vereinigung) |
| 𝐴 ⇒ 𝐵 | Implikation | 𝐴 impliziert 𝐵       | ¬𝐴 ∨ 𝐵 wahr ist (nur falsch bei 𝐴 wahr, 𝐵 falsch) | 𝐴 ⊆ 𝐵 (Teilmenge)   |
| 𝐴 ⇔ 𝐵 | Äquivalenz  | 𝐴 genau dann, wenn 𝐵 | beide denselben Wahrheitswert haben                   | 𝐴 = 𝐵 (Gleichheit)  |
| :⇔ / := | Definition  | "ist definiert als"    | —                                                     | —                     |

**Bindungsstärke**: ¬ > ∧, ∨ > ⇒, ⇔

| 𝐴 | 𝐵 | ¬𝐴 | 𝐴 ∧ 𝐵 | 𝐴 ∨ 𝐵 | 𝐴 ⇒ 𝐵 | 𝐴 ⇔ 𝐵 |
| --- | --- | --- | --- | --- | --- | --- |
| w | w | f | w | w | w | w |
| w | f | f | f | w | **f** | f |
| f | w | w | f | w | w | f |
| f | f | w | f | f | w | w |

### Quantoren

| Symbol | Name | Bedeutung | Wirkt wie |
| --- | --- | --- | --- |
| ∀𝑥 𝐴(𝑥) | Allquantor | für **alle** 𝑥 gilt 𝐴(𝑥) | grosses ∧ (Und über alle 𝑥) |
| ∃𝑥 𝐴(𝑥) | Existenzquantor | es **existiert** (mind.) ein 𝑥 mit 𝐴(𝑥) | grosses ∨ (Oder über alle 𝑥) |
| ∀𝑥 ∈ 𝑀 𝐴(𝑥) | eingeschränkt | ∀𝑥 (𝑥 ∈ 𝑀 **⇒** 𝐴(𝑥)) | 𝐴(𝑥₁) ∧ … ∧ 𝐴(𝑥ₙ) |
| ∃𝑥 ∈ 𝑀 𝐴(𝑥) | eingeschränkt | ∃𝑥 (𝑥 ∈ 𝑀 **∧** 𝐴(𝑥)) | 𝐴(𝑥₁) ∨ … ∨ 𝐴(𝑥ₙ) |

- **Negation**: ¬∀𝑥 𝐴(𝑥) ⇔ ∃𝑥 ¬𝐴(𝑥) und ¬∃𝑥 𝐴(𝑥) ⇔ ∀𝑥 ¬𝐴(𝑥) (Quantor kippen, ¬ nach innen)
- ∀ verträgt sich mit ∧, ∃ verträgt sich mit ∨ (aufteilen erlaubt)
- **Reihenfolge zählt**: ∀𝑦 ∃𝑥 (𝑥 = 𝑦) ist wahr, ∃𝑥 ∀𝑦 (𝑥 = 𝑦) ist falsch

### Mengen

| Symbol             | Name                         | Definition / Bedeutung                   | Logik dahinter                  |
| ------------------ | ---------------------------- | ---------------------------------------- | ------------------------------- |
| 𝑥 ∈ 𝐴 / 𝑥 ∉ 𝐴  | Element / kein Element       | 𝑥 ist (nicht) in 𝐴                     | —                               |
| ∅                  | leere Menge                  | Menge ohne Elemente (es gibt genau eine) | ∀𝑥 (𝑥 ∉ ∅)                    |
| 𝐴 = 𝐵            | Gleichheit (Extensionalität) | gleiche Elemente                         | ∀𝑥 (𝑥 ∈ 𝐴 ⇔ 𝑥 ∈ 𝐵)         |
| 𝐴 ⊆ 𝐵            | Teilmenge                    | alle Elemente von 𝐴 sind in 𝐵          | ∀𝑥 (𝑥 ∈ 𝐴 ⇒ 𝑥 ∈ 𝐵)         |
| 𝐴 ⊂ 𝐵            | echte Teilmenge              | 𝐴 ⊆ 𝐵 und 𝐴 ≠ 𝐵                      | —                               |
| {𝑥 ∈ 𝐴 ∣ 𝐸(𝑥)} | Aussonderung                 | alle 𝑥 aus 𝐴 mit Eigenschaft 𝐸        | 𝑎 ∈ … :⇔ 𝑎 ∈ 𝐴 ∧ 𝐸(𝑎)      |
| {𝑡(𝑥) ∣ 𝑥 ∈ 𝐴} | Ersetzung                    | 𝑡 auf jedes 𝑥 ∈ 𝐴 anwenden            | 𝑎 ∈ … ⇔ ∃𝑥 ∈ 𝐴 (𝑎 = 𝑡(𝑥)) |
| 𝐴 ∪ 𝐵            | Vereinigung                  | in 𝐴 **oder** 𝐵                        | 𝑥 ∈ 𝐴 ∨ 𝑥 ∈ 𝐵               |
| 𝐴 ∩ 𝐵            | Schnittmenge                 | in 𝐴 **und** 𝐵                         | 𝑥 ∈ 𝐴 ∧ 𝑥 ∈ 𝐵               |
| 𝐴 \ 𝐵            | Differenz ("𝐴 ohne 𝐵")     | in 𝐴, aber nicht in 𝐵                  | 𝑥 ∈ 𝐴 ∧ 𝑥 ∉ 𝐵               |
| ⋃_{𝐴∈𝑀} 𝐴       | beliebige Vereinigung        | in **mindestens einer** Menge aus 𝑀     | ∃𝐴 ∈ 𝑀 (𝑥 ∈ 𝐴)              |
| ⋂_{𝐴∈𝑀} 𝐴       | beliebiger Schnitt (𝑀 ≠ ∅)  | in **allen** Mengen aus 𝑀               | ∀𝐴 ∈ 𝑀 (𝑥 ∈ 𝐴)              |
| 𝐴 ∩ 𝐵 = ∅        | disjunkt                     | keine gemeinsamen Elemente               | —                               |

### Gesetze (gelten für Logik und Mengen gleich)

| Gesetz            | Logik                                  | Mengen                                     |
| ----------------- | -------------------------------------- | ------------------------------------------ |
| Idempotenz        | 𝐴 ∧ 𝐴 ⇔ 𝐴, 𝐴 ∨ 𝐴 ⇔ 𝐴             | 𝐴 ∩ 𝐴 = 𝐴, 𝐴 ∪ 𝐴 = 𝐴                 |
| Kommutativität    | 𝐴 ∧ 𝐵 ⇔ 𝐵 ∧ 𝐴                      | 𝐴 ∩ 𝐵 = 𝐵 ∩ 𝐴 (analog ∪)               |
| Assoziativität    | 𝐴 ∧ (𝐵 ∧ 𝐶) ⇔ (𝐴 ∧ 𝐵) ∧ 𝐶        | 𝐴 ∩ (𝐵 ∩ 𝐶) = (𝐴 ∩ 𝐵) ∩ 𝐶 (analog ∪) |
| Distributivität   | 𝐴 ∧ (𝐵 ∨ 𝐶) ⇔ (𝐴 ∧ 𝐵) ∨ (𝐴 ∧ 𝐶) | 𝐴 ∩ (𝐵 ∪ 𝐶) = (𝐴 ∩ 𝐵) ∪ (𝐴 ∩ 𝐶)     |
|                   | 𝐴 ∨ (𝐵 ∧ 𝐶) ⇔ (𝐴 ∨ 𝐵) ∧ (𝐴 ∨ 𝐶) | 𝐴 ∪ (𝐵 ∩ 𝐶) = (𝐴 ∪ 𝐵) ∩ (𝐴 ∪ 𝐶)     |
| De Morgan         | ¬(𝐴 ∧ 𝐵) ⇔ ¬𝐴 ∨ ¬𝐵                 | 𝐶 \ (𝐴 ∩ 𝐵) = (𝐶 \ 𝐴) ∪ (𝐶 \ 𝐵)     |
|                   | ¬(𝐴 ∨ 𝐵) ⇔ ¬𝐴 ∧ ¬𝐵                 | 𝐶 \ (𝐴 ∪ 𝐵) = (𝐶 \ 𝐴) ∩ (𝐶 \ 𝐵)     |
| Doppelte Negation | ¬¬𝐴 ⇔ 𝐴                              | —                                          |
| Kontraposition    | (𝐴 ⇒ 𝐵) ⇔ (¬𝐵 ⇒ ¬𝐴)                | —                                          |
| Transitivität     | (𝐴 ⇒ 𝐵) ∧ (𝐵 ⇒ 𝐶) ⇒ (𝐴 ⇒ 𝐶)      | 𝐴 ⊆ 𝐵 ∧ 𝐵 ⊆ 𝐶 ⇒ 𝐴 ⊆ 𝐶                |
| Modus Ponens      | aus 𝐴 und 𝐴 ⇒ 𝐵 folgt 𝐵            | —                                          |

> [!tip] De Morgan in einem Satz
> Negation nach innen ziehen und dabei ∧ ↔ ∨ (bzw. ∀ ↔ ∃, ∩ ↔ ∪) vertauschen.

### Zahlen & Operatoren

| Symbol | Bedeutung |
| --- | --- |
| ℕ ⊂ ℤ ⊂ ℚ ⊂ ℝ | natürliche (inkl. 0) ⊂ ganze ⊂ rationale ⊂ reelle Zahlen |
| ∑_{𝑖=𝑘}^{𝑛} 𝑥ᵢ | Summe (for-loop mit +), leer = 0 |
| ∏_{𝑖=𝑘}^{𝑛} 𝑥ᵢ | Produkt (for-loop mit ·), leer = 1 |
| (𝑧₁…𝑧ₙ)_𝑏 | Numeral zur Basis 𝑏: ∑ 𝑧ᵢ · 𝑏^(𝑛−𝑖) |

## Organisatorisch

> [!warning] Semesterendprüfung (SEP)
> - Zählt **100%** (keine Abgaben, keine weitere Benotung)
> - 90-minütig, Closed Book, mit 5x A4 Blätter (10 Seiten) Spickzettel erlaubt
> - Taschenrechner und leeres A4 Notizpapier erlaubt
> - Abzinsungs- und Rentenbarwertfaktorentabelle wird gestellt
> - Durchführung: Moodle-Prüfung (ZHAW Exam Moodle) im Safe Exam Browser
> - Kurztest in Semesterwoche 10 (Moodle), zählt 20% wenn er den Schnitt der SEP hochzieht — sonst zählt nur die SEP
> - Testklausur im zweiten Semesterteil, um zu prüfen, ob Moodle funktioniert

> [!note] Einführung
> DM ist "Mathe für Informatiker": Zahlentheorie (Kryptografie), Relationen (Datenbanken), Induktion, Rekursion, Korrektheitsbeweise.

## Zahlenmengen

| Menge | Symbol | Bedeutung | Beispiel |
| --- | --- | --- | --- |
| Natürliche Zahlen | ℕ | ganze, nicht-negative Zahlen (inkl. 0) | 0, 1, 2, 3, … |
| Ganze Zahlen | ℤ | ganze, positive & negative Zahlen | -1, 0, 1, 2, … |
| Rationale Zahlen | ℚ | Zahlen, die als Bruch dargestellt werden können | 1/3 |
| Reelle Zahlen | ℝ | Dezimalzahlen | 0.333…, π |

- Primzahlen sind eine Teilmenge von ℕ.
- Zwischen zwei rationalen (bzw. reellen) Zahlen gibt es immer unendlich viele weitere rationale (bzw. reelle) Zahlen.
- Für reelle Zahlen gibt es keinen algebraischen Grund (zum Lösen von Gleichungen) — sie werden für die Analysis gebraucht.

### Grössenvergleiche

| Notation | Bedeutung |
| --- | --- |
| 𝑥 < 𝑦 | 𝑥 ist kleiner als 𝑦 |
| 𝑥 > 𝑦 | 𝑥 ist grösser als 𝑦 |
| 𝑥 ≤ 𝑦 | 𝑥 ist kleiner oder gleich 𝑦 |
| 𝑥 ≥ 𝑦 | 𝑥 ist grösser oder gleich 𝑦 |
| max(𝑥1,…,𝑥𝑛) | die grösste Zahl aus 𝑥1,…,𝑥𝑛 |
| min(𝑥1,…,𝑥𝑛) | die kleinste Zahl aus 𝑥1,…,𝑥𝑛 |

### Addition und Multiplikation

> [!tip] Sigma (∑) ist ein for-loop
> Analog dazu ist Pi (∏) eine Schleife über Produkte.

| Notation | Bedeutung |
| --- | --- |
| 𝑥+𝑦 | Summe von 𝑥 und 𝑦 |
| ∑𝑛𝑖=𝑘 𝑥𝑖 | 𝑥𝑘+𝑥𝑘+1+⋯+𝑥𝑛−1+𝑥𝑛 (0, falls 𝑛<𝑘) |
| 𝑥−𝑦 | Differenz von 𝑥 und 𝑦 |
| −𝑥 | eindeutig bestimmte Zahl mit 𝑥+(−𝑥)=0 |
| 𝑥⋅𝑦 oder 𝑥𝑦 | Produkt von 𝑥 mit 𝑦 |
| ∏𝑛𝑖=𝑘 𝑥𝑖 | 𝑥𝑘⋅𝑥𝑘+1⋅⋯⋅𝑥𝑛−1⋅𝑥𝑛 (respektive 1, falls 𝑛<𝑘) |
| 𝑥𝑛 | ∏𝑛𝑖=1 𝑥 (respektive 1, falls 𝑛=0) |
| 𝑥−1, 1/𝑥 | eindeutig bestimmte Zahl mit 𝑥⋅𝑥−1=1, falls 𝑥≠0 |

> [!example] Übung: ∑ von 1 bis 5
> ```
> ∑(i=1..5) i = 1 + 2 + 3 + 4 + 5 = 15
> ```

> [!example] Übung: ∑ von 1 bis 10 von max(5, i)
> ```
> ∑(i=1..10) max(5,i) = 5+5+5+5+5+6+7+8+9+10 = 65
> ```

> [!example] Übung: ∏ von Summen
> ```
> ∏(i=1..3) ∑(j=1..i) j^i
> = ∑(j=1..1) j^1 · ∑(j=1..2) j^2 · ∑(j=1..3) j^3
> = (1^1) · (1^2+2^2) · (1^3+2^3+3^3)
> = 1 · 5 · 36
> = 180
> ```

### Abgeschlossenheit

Die Zahlenmengen ℕ, ℤ, ℚ und ℝ sind bezüglich der Addition und der Multiplikation abgeschlossen:

- Wenn 𝑥 und 𝑦 in ℕ sind, dann sind auch 𝑥+𝑦 sowie 𝑥⋅𝑦 in ℕ.
- Wenn 𝑥 und 𝑦 in ℤ sind, dann sind auch 𝑥+𝑦 sowie 𝑥⋅𝑦 in ℤ.
- Wenn 𝑥 und 𝑦 in ℚ sind, dann sind auch 𝑥+𝑦 sowie 𝑥⋅𝑦 in ℚ.
- Wenn 𝑥 und 𝑦 in ℝ sind, dann sind auch 𝑥+𝑦 sowie 𝑥⋅𝑦 in ℝ.

## Darstellung von Zahlen

- **Syntax** = Text, Programmiersprache, Art wie man Zahlen aufschreibt
- **Semantik** = Bedeutung (von Text, Programmiersprache, ...)

Zahlen können auf verschiedene Arten dargestellt werden, z.B. "6", "(110)₂", "12/2", "VI".

### Zahlensystem

Ein Zahlensystem ist ein Darstellungssystem für Zahlen mit drei Bestandteilen:
1. Eine Menge von Zeichen/Symbolen, die **Ziffern**, um Zahlen als Zeichenketten darzustellen.
2. Regeln, die definieren, welche Zeichenketten gültige Zahlen darstellen — diese Zeichenketten sind die **Numerale** des Systems.
3. Eine Spezifikation, wie man Numerale (Zeichenketten) als Zahlen (Quantitäten) **interpretiert**.

### Stellenwertsystem

> [!note] Definition
> - **Basis** 𝑏: eine natürliche Zahl 𝑏 ≥ 2, auf der das System basiert.
> - **Ziffern**: für jede Zahl zwischen 0 und 𝑏−1 eine Ziffer.
> - **Numerale**: bestehen aus 0 und allen (endlichen) Zeichenketten aus Ziffern, deren erste Ziffer von 0 verschieden ist ("5" und "123" sind Numerale, aber nicht "001").
> - **Interpretation** als (natürliche) Zahl:
> ```
> (z₁...zₙ)_b := ∑(i=1..n) zᵢ · b^(n-i)
> ```

> [!example] Beispiele
> ```
> (234)₁₀ = 2·10² + 3·10¹ + 4·10⁰
> (1011)₂ = 1·2³ + 0·2² + 1·2¹ + 1·2⁰ = (11)₁₀
> ```

Für negative und rationale Zahlen:
- **Ganze Zahlen**: zusätzliches Symbol, das Minuszeichen "−".
- **Rationale Zahlen**: Dezimaltrennzeichen "." — die Ziffern rechts davon repräsentieren negative Potenzen der Basis.

```
(z₁...zₙ.y₁...yₖ)_b := ∑(i=1..n) zᵢb^(n-i) + ∑(j=1..k) yⱼb^(-j)
```

> [!example] Beispiele
> ```
> 1/3 = (0.333...)₁₀ = (0.1)₃
> 17/6 = (2.D5)₁₆
> ```

#### Grenzen vom Stellenwertsystem

- Reelle Zahlen, die sich nicht als Brüche ausdrücken lassen (z.B. √2 oder 𝜋), können mit Stellenwertsystemen nicht vollständig dargestellt werden.
- Nicht einmal alle rationalen Zahlen haben zu jeder Basis eine endliche Darstellung im entsprechenden Stellenwertsystem.
- Jede rationale Zahl kann aber zu einer geeigneten Basis endlich im entsprechenden Stellenwertsystem dargestellt werden.

### Dezimalsystem

- Standardmässig nutzen wir das **Dezimalsystem** mit Basis 10 und den Ziffern 0,…,9.
- Weil das Dezimalsystem unser "Standardsystem" ist, lassen wir die Bezeichnung der Basis üblicherweise weg: anstelle von (123)₁₀ schreiben wir einfach 123, beziehen uns aber trotzdem auf die mathematische Zahl (123)₁₀ (Quantität) und nicht auf das Numeral "123" (Zeichenkette).
- Zahlen in anderen Basen kennzeichnen wir entsprechend weiterhin.

### Binär, Oktal und Hexadezimal

- **Binärsystem**: Basis 2, Ziffern 0,1.
- **Oktalsystem**: Basis 8, Ziffern 0,…,7.
- **Hexadezimalsystem**: Basis 16, Ziffern 0,…,9,A,B,C,D,E,F.

> [!example] Übung: Numerale interpretieren
> ```
> (1A1A)₁₆ = 1·16³ + 10·16² + 1·16 + 10 = 6682
> (101.01)₂ = (1·2² + 0·2¹ + 1·2⁰) + (0·2⁻¹ + 1·2⁻²) = 5 + 0.25 = 5.25
> (210.2)₃ = (2·3² + 1·3¹ + 0·3⁰) + (2·1/3) = 21 + 0.6̄ = 21.6̄
> ```

## Aussagen und Prädikate

> [!note] Definition (Aussage)
> Eine **Aussage** ist ein mathematisches Objekt, welchem ein Wahrheitswert "wahr" oder "falsch" zugeordnet werden kann. Man weiss nicht zwingend, ob die Aussage stimmt — sie muss aber eindeutig wahr oder falsch sein. `x > 5` ist z.B. keine Aussage, weil es von 𝑥 abhängt.

> [!example] Beispiele von Aussagen
> - 3 < 5 (wahre Aussage)
> - 3 + 4 = 106 (falsche Aussage)
> - Es gibt unendlich viele natürliche Zahlen (wahre Aussage)
> - Alle natürlichen Zahlen sind Primzahlen (falsche Aussage)
> - Jede natürliche Zahl ist entweder durch 2 oder durch 3 teilbar (falsche Aussage)

> [!note] Definition (Prädikat)
> Es sei 𝑛 eine natürliche Zahl. Ein Ausdruck, in dem 𝑛 viele (verschiedene) Variablen frei vorkommen und der bei Belegung (= Ersetzen) aller freien Variablen in eine Aussage übergeht, nennen wir ein 𝑛-stelliges **Prädikat**.
> - Aussagen sind 0-stellige Prädikate.
> - Belegt man in einem (𝑛+1)-stelligen Prädikat eine Variable mit einem geeigneten Wert, so erhält man ein 𝑛-stelliges Prädikat.
> - Ist 𝐴(𝑥) ein Prädikat und 𝑦 ein Wert, für den 𝐴(𝑦) eine wahre Aussage ist, sagt man auch "𝐴 trifft auf 𝑦 zu" oder "𝑦 erfüllt 𝐴". Beispiel: das Prädikat 𝐴(𝑥):="𝑥>5" trifft auf die Zahl 7 zu, weil 𝐴(7) eine wahre Aussage ist.
> - Prädikate können als (mathematische) Eigenschaften der Objekte betrachtet werden, die sie erfüllen.

> [!example] Beispiele von Prädikaten
> - "𝑥 > 3" (1-stelliges Prädikat)
> - "𝑥 + 𝑦 = 𝑧" (3-stelliges Prädikat)
> - "𝑥 ist eine natürliche Zahl" (1-stelliges Prädikat)

## Junktoren

Aus bestehenden Prädikaten (Aussagen) lassen sich durch sinnvolles Verknüpfen neue Prädikate (Aussagen) konstruieren, z.B.:
- "Es ist nicht der Fall, dass 𝑥 eine Primzahl ist"
- "21 > 7 **und** 21 ist keine Primzahl"
- "𝑥 > 0 **oder** 𝑥 = 0 **oder** 𝑥 < 0"
- "**Wenn** 𝑥 eine Primzahl ist **und** 𝑥 > 2, **dann folgt** 𝑥 ist ungerade"

### Negation

> [!note] Definition
> Die Negation ¬𝐴 (gesprochen: Nicht 𝐴) ist für jede Belegung genau dann wahr, wenn 𝐴 falsch ist.

> [!example] Beispiel
> ¬(𝑥 < 𝑦) ist genau dann wahr, wenn 𝑥 ≥ 𝑦 wahr ist.

> [!tip] Wichtige Eigenschaft
> **Doppelte Negation**: 𝐴 und ¬¬𝐴 sind äquivalent (d.h. haben die gleichen Wahrheitswerte für jede Belegung).

### Konjunktion

> [!note] Definition
> Die Konjunktion 𝐴 ∧ 𝐵 (gesprochen: 𝐴 und 𝐵) ist für jede Belegung genau dann wahr, wenn sowohl 𝐴 als auch 𝐵 wahr ist.

> [!example] Beispiel
> (𝑥 ≤ 𝑦) ∧ (𝑥 ≠ 𝑦) ist genau dann wahr, wenn 𝑥 < 𝑦 wahr ist.

> [!tip] Wichtige Eigenschaften
> - **Assoziativität**: 𝐴 ∧ (𝐵 ∧ 𝐶) und (𝐴 ∧ 𝐵) ∧ 𝐶 sind äquivalent.
> - **Kommutativität**: 𝐴 ∧ 𝐵 und 𝐵 ∧ 𝐴 sind äquivalent.
> - **Idempotenz**: 𝐴 ∧ 𝐴 und 𝐴 sind äquivalent.

### Disjunktion

> [!note] Definition
> Die Disjunktion 𝐴 ∨ 𝐵 (gesprochen: 𝐴 oder 𝐵) ist für jede Belegung genau dann wahr, wenn 𝐴 wahr ist oder 𝐵 wahr ist (oder beide wahr sind).

> [!example] Beispiel
> 𝑥 ≤ 𝑦 ist genau dann wahr, wenn (𝑥 < 𝑦) ∨ (𝑥 = 𝑦) wahr ist.

> [!tip] Wichtige Eigenschaften
> - **Assoziativität**: 𝐴 ∨ (𝐵 ∨ 𝐶) und (𝐴 ∨ 𝐵) ∨ 𝐶 sind äquivalent.
> - **Kommutativität**: 𝐴 ∨ 𝐵 und 𝐵 ∨ 𝐴 sind äquivalent.
> - **Idempotenz**: 𝐴 ∨ 𝐴 und 𝐴 sind äquivalent.

### Implikation

> [!note] Definition
> Die Implikation 𝐴 ⇒ 𝐵 (gesprochen: 𝐴 impliziert 𝐵) ist für jede Belegung genau dann wahr, wenn ¬𝐴 ∨ 𝐵 wahr ist.
>
> wenn 𝐵 nicht wahr ist, kann das nur sein, weil 𝐴 nicht wahr ist.

> [!tip] Wichtige Eigenschaften
> - Wenn 𝐴 falsch ist, dann ist 𝐴 ⇒ 𝐵 (unabhängig vom Wahrheitsgehalt von 𝐵) wahr.
> - Wenn 𝐵 wahr ist, dann ist 𝐴 ⇒ 𝐵 (unabhängig vom Wahrheitsgehalt von 𝐴) wahr.
> - **Kontraposition**: 𝐴 ⇒ 𝐵 und ¬𝐵 ⇒ ¬𝐴 sind äquivalent.
> - **Transitivität**: Aus 𝐴 ⇒ 𝐵 und 𝐵 ⇒ 𝐶 folgt 𝐴 ⇒ 𝐶.
> - **Modus Ponens**: Aus 𝐴 und 𝐴 ⇒ 𝐵 folgt 𝐵.
> - **Äquivalenz**: Zwei Prädikate 𝐴 und 𝐵 sind genau dann äquivalent, wenn 𝐴 ⇒ 𝐵 und 𝐵 ⇒ 𝐴 gilt. In diesem Fall schreiben wir 𝐴 ⇔ 𝐵.

### Mischen von Junktoren

> [!info] Syntaktische Konventionen
> - ¬ bindet stärker als ∧ und ∨.
> - ∧ und ∨ binden stärker als ⇒ und ⇔.

> [!tip] Regeln von De Morgan
> ```
> ¬(A ∧ B)  ⇔  ¬A ∨ ¬B
> ¬(A ∨ B)  ⇔  ¬A ∧ ¬B
> ```

> [!tip] Distributivität
> ```
> A ∧ (B ∨ C)  ⇔  (A ∧ B) ∨ (A ∧ C)
> A ∨ (B ∧ C)  ⇔  (A ∨ B) ∧ (A ∨ C)
> ```

## Quantoren

Quantoren formalisieren Aussagen wie "für alle 𝑥 gilt …" oder "es gibt ein 𝑥 mit …".

> [!note] Definition (Quantoren)
> - ∀𝑥 𝐴(𝑥): Für **alle** (möglichen Werte) 𝑥 gilt 𝐴(𝑥) — **Allquantor**
> - ∃𝑥 𝐴(𝑥): Es **existiert** ein (Wert) 𝑥 mit 𝐴(𝑥) — **Existenzquantor**
>
> Mehrere gleichartige Quantoren kürzt man ab: ∀𝑥∀𝑦(…) = ∀𝑥,𝑦(…), ∃𝑥∃𝑦(…) = ∃𝑥,𝑦(…).

> [!example] Beispiele
> ```
> ∃x (x = 2)        wahr   (x = 2 existiert)
> ∀x (x = 2)        falsch (nicht alles ist 2)
> ∀y ∃x (x = y)     wahr   (zu jedem y gibt es ein x, nämlich y selbst)
> ∃x ∀y (x = y)     falsch (kein x ist gleich allen y)
> ```
> → Die **Reihenfolge** verschiedener Quantoren ist entscheidend.

### Eingeschränkte Quantoren

> [!note] Definition
> Es sei 𝑀 eine Menge und 𝐴(𝑥) ein Prädikat:
> ```
> ∃x ∈ M A(x)  :⇔  ∃x (x ∈ M ∧ A(x))
> ∀x ∈ M A(x)  :⇔  ∀x (x ∈ M ⇒ A(x))
> ```

> [!warning] Nicht verwechseln
> In der **Definition** steht bei ∃ ein ∧ und bei ∀ ein ⇒. Ausgeschrieben über eine endliche Menge wird aber ∀ zu einer **Und**- und ∃ zu einer **Oder**-Kette:
> ```
> M = {a, b, c}
> ∀x ∈ M A(x)  ⇔  A(a) ∧ A(b) ∧ A(c)
> ∃x ∈ M A(x)  ⇔  A(a) ∨ A(b) ∨ A(c)
> ```

Quantoren wirken also wie Junktoren, die (möglicherweise **unendlich**) viele Prädikate verknüpfen. Genau deshalb braucht man sie: eine unendliche Menge lässt sich nicht mit endlich vielen ∧/∨ ausschreiben.

### Quantoren und Junktoren

> [!tip] Regeln
> ```
> ¬∀x A(x)            ⇔  ∃x ¬A(x)
> ¬∃x A(x)            ⇔  ∀x ¬A(x)
> ∀x (A(x) ∧ B(x))    ⇔  (∀x A(x)) ∧ (∀x B(x))
> ∃x (A(x) ∨ B(x))    ⇔  (∃x A(x)) ∨ (∃x B(x))
> ```
> "Nicht alle 𝑥 erfüllen 𝐴" heisst: es existiert ein 𝑥, das 𝐴 **nicht** erfüllt (De Morgan für Quantoren).

### Leere Quantoren

Quantoren über eine Variable, die im Prädikat gar nicht vorkommt, kann man weglassen. Ist 𝐵 ein Prädikat ohne 𝑥:

```
∀x B             ⇔  B
∃x B             ⇔  B
∀x (A(x) ∧ B)    ⇔  (∀x A(x)) ∧ B
∃x (A(x) ∧ B)    ⇔  (∃x A(x)) ∧ B
```

> [!example] Anzahlen ausdrücken: "genau ein 𝑥 erfüllt 𝐵"
> ```
> ∃x B(x)  ∧  ¬(∃x,y (B(x) ∧ B(y) ∧ x ≠ y))
> └ Anzahl ≥ 1 ┘   └──── nicht (Anzahl ≥ 2) ────┘
> ```

## Mengen

### Mengen und Elemente

- Mengen sind der primitive Datentyp der Mathematik: sie fassen mathematische Objekte (die **Elemente**) zu einem neuen Ganzen zusammen.
- 𝑦 ∈ 𝑋: 𝑦 ist Element von 𝑋. 𝑦 ∉ 𝑋: 𝑦 ist kein Element von 𝑋.
- Mengen können beliebige Objekte enthalten, auch andere Mengen — aber **keine Menge enthält sich selbst**.
- Konvention: Mengen mit Grossbuchstaben, Elemente mit Kleinbuchstaben (wenn möglich).
- Endliche Mengen schreibt man mit geschweiften Klammern: {1, 2, 3}.

### Extensionalität

> [!note] Extensionalitätsprinzip
> Zwei Mengen sind genau dann gleich, wenn sie die gleichen Elemente enthalten:
> ```
> A = B  ⇔  ∀x (x ∈ A ⇔ x ∈ B)
> ```

- Mengen haben **keine Reihenfolge** und **keine Duplikate**: {1, 2} = {2, 1} = {1, 2, 2}. (Listen erfüllen das nicht.)
- Daraus folgt: es gibt nur **eine einzige** leere Menge ∅.

### Teilmengen

> [!note] Definition (Teilmenge)
> 𝐴 ist **Teilmenge** von 𝐵 (𝐴 ⊆ 𝐵), falls alle Elemente von 𝐴 auch Elemente von 𝐵 sind:
> ```
> A ⊆ B  ⇔  ∀x (x ∈ A ⇒ x ∈ B)
> ```
> Gilt zusätzlich 𝐴 ≠ 𝐵, ist 𝐴 eine **echte** Teilmenge: 𝐴 ⊂ 𝐵.

> [!tip] Extensionalität mit Teilmengen
> ```
> A = B  ⇔  A ⊆ B ∧ B ⊆ A
> ```
> So beweist man Mengengleichheit: beide Richtungen zeigen.

> [!example] Beweis: Es gibt nur eine leere Menge
> - Für jede Menge 𝐴 gilt ∅ ⊆ 𝐴, denn ∀𝑥 (𝑥 ∈ ∅ ⇒ 𝑥 ∈ 𝐴) ist wahr — die Prämisse 𝑥 ∈ ∅ ist immer falsch, also ist die Implikation immer wahr.
> - Wären ∅₁ und ∅₂ beide leer, dann gilt ∅₁ ⊆ ∅₂ und ∅₂ ⊆ ∅₁, also ∅₁ = ∅₂.

## Aussonderung und Ersetzung

### Aussonderungsprinzip

Aus einer Menge 𝐴 die Elemente mit einer Eigenschaft 𝐸(𝑥) herausfiltern (wie `filter`):

> [!note] Notation (Aussonderung)
> ```
> a ∈ {x ∈ A | E(x)}  :⇔  a ∈ A ∧ E(a)
> ```

> [!example] Beispiel
> ```
> G = {x ∈ ℕ | "x ist gerade"}
>   = {x ∈ ℕ | ∃y ∈ ℕ (x = 2y)}
> ```

> [!example] Übung: ∅ durch Aussonderung beschreiben
> ```
> ∅ = {x ∈ A | x ≠ x}      (für eine beliebige Menge A)
> ```

### Ersetzungsprinzip

Auf jedes Element 𝑥 ∈ 𝐴 einen Ausdruck 𝑡(𝑥) anwenden (wie `map`):

> [!note] Notation (Ersetzung)
> ```
> a ∈ {t(x) | x ∈ A}  ⇔  ∃x ∈ A (a = t(x))
> ```

> [!example] Beispiele
> ```
> {x² | x ∈ ℕ}                        Quadratzahlen
> {2x + 1 | x ∈ ℕ}                    ungerade natürliche Zahlen
> {a/b | a ∈ ℤ, b ∈ ℤ, b ≠ 0}         rationale Zahlen ℚ
> {{x ∈ ℕ | x < y} | y ∈ ℕ}           "Anfangsabschnitte" von ℕ
>   = {∅, {0}, {0,1}, {0,1,2}, …}      (Menge von Mengen)
> ```

> [!example] Übung: natürliche Zahlen ≠ 1, die keine Primzahlen sind
> ```
> {xy | x, y ∈ ℕ ∧ x ≠ 1 ∧ y ≠ 1}
> ```

## Vereinigung, Schnitt und Differenz

> [!tip] Merkregel
> | | endlich viele Mengen | beliebig viele Mengen |
> | --- | --- | --- |
> | Vereinigung ∪ | Oder (∨) | Existenzquantor (∃) |
> | Schnitt ∩ | Und (∧) | Allquantor (∀) |

### Vereinigung

> [!note] Definition (endliche Vereinigung)
> Die **Vereinigung** enthält genau die Elemente, die in mindestens einer der Mengen sind:
> ```
> A ∪ B              := {x | x ∈ A ∨ x ∈ B}
> A₁ ∪ A₂ ∪ … ∪ Aₙ   := {x | x ∈ A₁ ∨ x ∈ A₂ ∨ … ∨ x ∈ Aₙ}
> ```

> [!note] Definition (beliebige Vereinigung)
> Es sei 𝑀 eine beliebige Menge (von Mengen):
> ```
> ⋃_{A∈M} A  := {x | ∃A ∈ M (x ∈ A)}
> ```
> Indexiert (𝑀 = {𝐴ᵢ ∣ 𝑖 ∈ 𝐼}): ⋃_{𝑖∈𝐼} 𝐴ᵢ = {𝑥 ∣ ∃𝑖 ∈ 𝐼 (𝑥 ∈ 𝐴ᵢ)}

> [!example] Beispiele
> ```
> {1,2,3} ∪ {2,3,4,5} = {1,2,3,4,5}
> ℤ = {−n | n ∈ ℕ} ∪ ℕ
> ℕ = {2n | n ∈ ℕ} ∪ {2n+1 | n ∈ ℕ}
>
> Aᵢ := {i, −i}  (z.B. A₀ = {0}, A₃ = {−3, 3})
> ⋃_{i∈ℕ} Aᵢ = ℤ     (jedes z ∈ ℤ liegt in A_|z|)
> ```

> [!tip] Eigenschaften von ∪
> - Idempotenz: 𝐴 ∪ 𝐴 = 𝐴
> - Kommutativität: 𝐴 ∪ 𝐵 = 𝐵 ∪ 𝐴
> - Assoziativität: 𝐴 ∪ (𝐵 ∪ 𝐶) = (𝐴 ∪ 𝐵) ∪ 𝐶
> - 𝐴 ⊆ 𝐴 ∪ 𝐵
> - 𝐴 ⊆ 𝐵 ⇔ 𝐵 = 𝐴 ∪ 𝐵

### Schnittmenge

> [!note] Definition (endliche Schnittmenge)
> Die **Schnittmenge** enthält genau die Elemente, die in allen Mengen sind:
> ```
> A ∩ B              := {x | x ∈ A ∧ x ∈ B}
> A₁ ∩ A₂ ∩ … ∩ Aₙ   := {x | x ∈ A₁ ∧ x ∈ A₂ ∧ … ∧ x ∈ Aₙ}
> ```

> [!note] Definition (beliebige Schnittmenge)
> Es sei 𝑀 eine **nichtleere** Menge (von Mengen):
> ```
> ⋂_{A∈M} A  := {x | ∀A ∈ M (x ∈ A)}
> ```
> Indexiert: ⋂_{𝑖∈𝐼} 𝐴ᵢ = {𝑥 ∣ ∀𝑖 ∈ 𝐼 (𝑥 ∈ 𝐴ᵢ)}

> [!example] Beispiele
> ```
> {1,2,3} ∩ {2,3,4,5} = {2,3}
> ℕ = {r ∈ ℝ | r ≥ 0} ∩ ℤ
> ∅ = {2n | n ∈ ℕ} ∩ {2n+1 | n ∈ ℕ}
>
> Aᵢ := {0, …, i}             ⋂_{i∈ℕ} Aᵢ = {0}
> Aᵢ := {n ∈ ℕ | n ≠ 2i}      ⋂_{i∈ℕ} Aᵢ = {2n+1 | n ∈ ℕ}
> ```

> [!tip] Eigenschaften von ∩
> - Idempotenz: 𝐴 ∩ 𝐴 = 𝐴
> - Kommutativität: 𝐴 ∩ 𝐵 = 𝐵 ∩ 𝐴
> - Assoziativität: 𝐴 ∩ (𝐵 ∩ 𝐶) = (𝐴 ∩ 𝐵) ∩ 𝐶
> - 𝐴 ∩ 𝐵 ⊆ 𝐴
> - 𝐴 ⊆ 𝐵 ⇔ 𝐴 ∩ 𝐵 = 𝐴

### Disjunkte Mengen

> [!note] Definition (disjunkt)
> - 𝐴 und 𝐵 heissen **disjunkt**, wenn 𝐴 ∩ 𝐵 = ∅ (keine gemeinsamen Elemente).
> - 𝑀 = {𝐴ᵢ ∣ 𝑖 ∈ 𝐼} heisst **paarweise disjunkt**, wenn aus 𝑖 ≠ 𝑗 stets 𝐴ᵢ ∩ 𝐴ⱼ = ∅ folgt.

> [!warning] Achtung
> {1,2}, {2,3}, {4,5} sind **nicht** paarweise disjunkt, obwohl {1,2} ∩ {2,3} ∩ {4,5} = ∅ gilt.
>
> 𝑀 ist genau dann paarweise disjunkt, wenn jedes 𝑥 ∈ ⋃_{𝑖∈𝐼} 𝐴ᵢ in **genau einem** 𝐴ᵢ liegt.

### Differenzmenge

> [!note] Definition (Differenz)
> ```
> A \ B := {x ∈ A | x ∉ B}      ("A ohne B")
> ```
> Alles aus 𝐴, das nicht in 𝐵 ist — also auch ohne den gemeinsamen Teil 𝐴 ∩ 𝐵.

> [!example] Beispiele
> ```
> ℤ \ ℕ = {k ∈ ℤ | k < 0}
> ℚ \ ℝ = ∅
> ℕ \ {2n | n ∈ ℕ} = {2n+1 | n ∈ ℕ}
> ```

### Interaktion von ∩, ∪ und \

> [!tip] Satz
> Die Identitäten folgen direkt aus den entsprechenden logischen Äquivalenzen:
> ```
> De Morgan:        C \ (A ∩ B) = (C \ A) ∪ (C \ B)
> De Morgan:        C \ (A ∪ B) = (C \ A) ∩ (C \ B)
> Distributivität:  A ∪ (B ∩ C) = (A ∪ B) ∩ (A ∪ C)
> Distributivität:  A ∩ (B ∪ C) = (A ∩ B) ∪ (A ∩ C)
> ```
