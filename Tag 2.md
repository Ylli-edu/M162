# Modul 162: Daten analysieren und modellieren

## Lernjournal – Tag 2: Datentypen, Zahlensysteme & Zahlenumwandlung (Teil 1)

* **Autor:** Ylli Uka
* **Datum:** 09.11.2026
* **Modul:** M162 – Daten analysieren und modellieren

## 1. Digitale Datenverarbeitung & Dateiinterpretation

Der Mikroprozessor im PC arbeitet rein digital und kennt auf Hardwareebene nur zwei Zustände: $0$ und $1$ (Bits). Ob eine Folge von Nullen und Einsen als Textdokument (`.docx`), Musikdatei (`.mp3`) oder Bild (`.jpg`) dargestellt wird, entscheidet nicht die Hardware, sondern die **Software** (Betriebssystem und Anwendungsprogramme) anhand der **Dateiendung** sowie der **Header-Informationen (Magic Bytes)** innerhalb der Datei.

### Experiment: Dateiendung ändern (`Matterhorn.jpg` $\rightarrow$ `Matterhorn.txt`)

1. **Doppelklick auf `Matterhorn.jpg`:** Das Betriebssystem erkennt die Endung `.jpg` und öffnet die Datei mit der Standard-Fotoanzeige-App. Die Binärdaten werden als Pixel/Farbwerte interpretiert und als Bild des Matterhorns angezeigt.
2. **Umbenennen in `Matterhorn.txt` & Doppelklick:** Das Betriebssystem öffnet die Datei nun mit einem Texteditor (z. B. Notepad). Der Editor versucht, die identischen Binärdaten als Zeichencodes (z. B. ASCII/UTF-8) zu interpretieren. Das Ergebnis ist unleserlicher Zeichensalat („Mojibake“), da Bildkompressionsdaten keine sinnvollen Textzeichen ergeben.
3. **Wer entscheidet über die Interpretation?** Das **Betriebssystem** weist anhand der Dateiendung das zuständige Programm zu, und das jeweilige **Anwendungsprogramm (Parser)** entscheidet, nach welchem Regelwerk (Dateiformat-Spezifikation) die Bits und Bytes interpretiert werden.

## 2. Wichtige Zahlensysteme in der Informatik

Um Missverständnisse zwischen verschiedenen Zahlensystemen zu vermeiden, wird die Basis oft als tiefgestellter Buchstabe (Index) oder Präfix angegeben:

| System | Bezeichnung | Basis | Zeichenvorrat | Beispiel & Notation | Bemerkung | 
| ----- | ----- | ----- | ----- | ----- | ----- | 
| **BIN** | Binärsystem / Dualsystem | $2$ | `0, 1` | $0110'1011_B$ | Arbeitssprache des Mikroprozessors. $4\text{ Bit}$ entsprechen genau einer HEX-Ziffer ($1111_B = \text{F}_H$). | 
| **DEZ** | Dezimalsystem / Zehnersystem | $10$ | `0–9` | $2025_D$ | Unser gewohntes Alltagssystem. | 
| **HEX** | Hexadezimalsystem | $16$ | `0–9`, `A–F` | $\text{FF3C}_H$ oder `0xFF3C` | Platzsparende Darstellung von Bitkombinationen (z. B. MAC-, IPv6- oder Speicheradressen). $\text{A}=10_D \dots \text{F}=15_D$. | 

## 3. Aufgaben zu Zahlenumwandlung (Unsigned)

*Hinweis: „Unsigned“ (vorzeichenlos) bedeutet, dass alle Bits zur Darstellung positiver ganzer Zahlen (inklusive $0$) genutzt werden.*

1. **Wandle die Dezimalzahl $27$ in sein binäres „Unsigned“-Äquivalent um.**
   * **Rechenweg:** Zerlegung in Zweierpotenzen: $27 = 16 + 8 + 2 + 1 = 1 \cdot 2^4 + 1 \cdot 2^3 + 0 \cdot 2^2 + 1 \cdot 2^1 + 1 \cdot 2^0$
   * **Lösung:** $11011_B$ (als 8-Bit-Byte: $0001'1011_B$)

2. **Welchem Dezimalwert entspricht unsigned $1001'0011_B$?**
   * **Rechenweg:** Addition der Stellenwerte von links ($2^7$) nach rechts ($2^0$):
     $$1 \cdot 128 + 0 \cdot 64 + 0 \cdot 32 + 1 \cdot 16 + 0 \cdot 8 + 0 \cdot 4 + 1 \cdot 2 + 1 \cdot 1 = 128 + 16 + 2 + 1$$
   * **Lösung:** $147_D$

3. **Welchem hexadezimalen Wert entspricht unsigned $1011'0111_B$?**
   * **Rechenweg:** Aufteilung in zwei 4-Bit-Blöcke (Nibbles):
     * Linkes Nibble: $1011_B = 8 + 2 + 1 = 11_D = \text{B}_H$
     * Rechtes Nibble: $0111_B = 4 + 2 + 1 = 7_D = 7_H$
   * **Lösung:** $\text{B7}_H$ (bzw. `0xB7`)

4. **Das letzte Oktett einer IP-Adresse lautet in Hexadezimal $\text{3D}$. Welchem Binärwert entspricht dies?**
   * **Rechenweg:** Jede HEX-Ziffer einzeln in $4\text{ Bit}$ umwandeln:
     * $3_H = 3_D = 0011_B$
     * $\text{D}_H = 13_D = 8 + 4 + 1 = 1101_B$
   * **Lösung:** $0011'1101_B$ (ohne führende Nullen: $111101_B$)

## 4. Von „Unsigned“ zu „Signed“ (Vorzeichenbehaftete Zahlen)

* **Unsigned (Natürliche Zahlen inkl. $0$):** Vergleichbar mit der **Kelvin-Skala** (beginnt beim absoluten Nullpunkt $0\text{ K}$, keine negativen Werte).
* **Signed (Ganze Zahlen):** Vergleichbar mit der **Celsius-Skala** (besitzt positive und negative Werte, z. B. $-273\,^\circ\text{C}$ bis $+100\,^\circ\text{C}$).

In der Informatik wird für negative Ganzzahlen das **Zweierkomplement** verwendet. Dabei erhält das höchstwertige Bit ganz links (MSB – *Most Significant Bit*) eine **negative Wertigkeit**:

| Darstellung (4-Bit Beispiel) | Binärstelle $3$ | Binärstelle $2$ | Binärstelle $1$ | Binärstelle $0$ | Beispiel `1011` | 
| ----- | ----- | ----- | ----- | ----- | ----- | 
| **Unsigned** (Wertigkeit) | $+8$ | $+4$ | $+2$ | $+1$ | $8 + 0 + 2 + 1 = \mathbf{11_D}$ | 
| **Signed** (Wertigkeit) | $-8$ | $+4$ | $+2$ | $+1$ | $-8 + 0 + 2 + 1 = \mathbf{-5_D}$ | 

### Aufgaben zu Zahlenumwandlung (Signed)

1. **Wandle die Dezimalzahl $27$ in sein binäres 8-Bit-„Signed“-Äquivalent um.**
   * **Rechenweg:** Da $+27$ positiv ist, ist das Vorzeichenbit (ganz links) $0$. Die Darstellung entspricht der Unsigned-Variante:
     $$0 \cdot (-128) + 0 \cdot 64 + 0 \cdot 32 + 1 \cdot 16 + 1 \cdot 8 + 0 \cdot 4 + 1 \cdot 2 + 1 \cdot 1 = 27_D$$
   * **Lösung:** $0001'1011_B$

2. **Welchem Dezimalwert entspricht signed $1001'0011_B$?**
   * **Rechenweg:** Das MSB (ganz links) ist $1$, somit hat diese Stelle den Wert $-128$:
     $$1 \cdot (-128) + 0 \cdot 64 + 0 \cdot 32 + 1 \cdot 16 + 0 \cdot 8 + 0 \cdot 4 + 1 \cdot 2 + 1 \cdot 1 = -128 + 16 + 2 + 1 = -128 + 19$$
   * **Lösung:** $-109_D$

## 5. Übersicht der Datentypen

Beim Erstellen einer Variable in einem Programm, einer Tabellenkalkulation oder einer Datenbank muss der passende Datentyp festgelegt werden. Man unterscheidet zwischen **numerischen** und **alphanumerischen** Codes:

### Einfache numerische Datentypen

* **`INTEGER` (`signed int`):** Ganze Zahlen mit Vorzeichen (z. B. `... -2, -1, 0, 1, 2 ...`).
  * *Hinweis zu Java:* `int` = $32\text{ Bit}$; `long` = $64\text{ Bit}$.
* **`INTEGER` (`unsigned int`):** Ganze positive Zahlen ohne Vorzeichen (z. B. `0, 1, 2 ...`).
* **`FLOAT` (`float`):** Fliesskommazahlen (z. B. `-2.1426`, $+0.1393 \cdot 10^{+3}$, $-0.725 \cdot 10^{-3}$).
  * **Normalisiertes Float-Format (IEEE 754, 32 Bit):** $x = v \cdot m \cdot b^e$
    * $v = 1\text{ Bit}$ Vorzeichen
    * $m = 23\text{ Bit}$ Mantisse
    * $b = \text{Basis } 2$
    * $e = 8\text{ Bit}$ Exponent
  * *Hinweis zu Java:* `float` = $32\text{ Bit}$; `double` = $64\text{ Bit}$.
* **`BOOLEAN` (`boolean`):** Logischer Datentyp für Wahrheitswerte (`true` / `false`).

### Einfache alphanumerische Datentypen

* **`CHARACTER` (`char`):** Einzelnes Textzeichen bzw. alphanumerisches Zeichen (z. B. `'A'`, `'b'`, `'0'`, `'?'`, `'+'`).
* *(Weitere Typen wie Aufzählungstypen/Enums oder Pointer sind im Modul 162 nicht relevant.)*

### Zusammengesetzte Datentypen

* **`STRING` / `VARCHAR` (`ARRAY OF CHARACTER`):** Zeichenkette / Textzeile aus mehreren aneinandergereihten Characters (z. B. `"Hello World!"`).
