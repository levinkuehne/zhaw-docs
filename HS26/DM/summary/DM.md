# DM — Diskrete Mathematik

> [!info] Kursseite
> https://olodnad.gitlab.io/diskmathzhaw/

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
| Natürliche Zahlen | ℕ | ganze, nicht-negative Zahlen | 1, 2, 3, … |
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
