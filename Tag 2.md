# Modul 162: Daten analysieren und modellieren
## Lernjournal – Tag 2: Datentypen, Zahlensysteme & Zeichencodierung

* **Autor:** Ylli Uka
* **Datum:** 09.11.2026
* **Modul:** M162 – Daten analysieren und modellieren

---

## 1. Wie der PC Daten liest (0 und 1)
Der Prozessor im Computer arbeitet digital und versteht eigentlich nur **0 und 1** (Strom aus / Strom an). Egal ob Word-Dokument, Musikdatei (MP3) oder Foto (JPG) – auf der Festplatte sind alles nur Nullen und Einsen.

### Experiment: `Matterhorn.jpg` umbenennen in `Matterhorn.txt`
* **Was passiert beim Doppelklick?** Windows öffnet die Datei plötzlich mit dem Texteditor (Notepad) statt mit der Foto-App, und man sieht nur komischen Zeichensalat.
* **Wer entscheidet, was die Bits bedeuten?** Das Betriebssystem bzw. das Programm (oft anhand der **Dateiendung** oder des **Datentyps** im Code) entscheidet, ob die `0` und `1` als Bildpixel, Ton, Zahl oder Textzeichen interpretiert werden.

---

## 2. Zahlensysteme in der Informatik

| System | Basis | Zeichenvorrat | Beispiel | Wofür braucht man es? |
| :--- | :---: | :--- | :--- | :--- |
| **Binär (BIN)** | $2$ | `0, 1` | $0110'1011_B$ | So arbeitet der Prozessor direkt. |
| **Dezimal (DEZ)** | $10$ | `0–9` | $2025_D$ | Unser normales Zahlensystem im Alltag. |
| **Hexadezimal (HEX)** | $16$ | `0–9`, `A–F` | $\text{FF3C}_H$ / `0xFF3C` | Abkürzung für Binär (**1 HEX-Ziffer = 4 Bit**), z. B. für MAC-Adressen, IPv6, Farben. |

* **HEX-Werte merken:** $\text{A} = 10$, $\text{B} = 11$, $\text{C} = 12$, $\text{D} = 13$, $\text{E} = 14$, $\text{F} = 15$ ($1111_B = \text{F}_H$).

### Aufgaben zu Zahlenumwandlung (Unsigned)

1. **Dezimalzahl $27$ in binäres „Unsigned“-Äquivalent umwandeln:**
   * Zerlegen in Zweierpotenzen: $27 = 16 + 8 + 2 + 1$
   * **Ergebnis:** **$0001'1011_B$** (bzw. $11011_B$)

2. **Welchem Dezimalwert entspricht unsigned $1001'0011_B$?**
   * Stellenwerte zusammenzählen: $128 + 16 + 2 + 1$
   * **Ergebnis:** **$147_D$**

3. **Welchem hexadezimalen Wert entspricht unsigned $1011'0111_B$?**
   * In zwei 4-Bit-Blöcke teilen:
     * Linker Block: $1011_B = 8 + 2 + 1 = 11_{10} = \text{B}_H$
     * Rechter Block: $0111_B = 4 + 2 + 1 = 7_{10} = 7_H$
   * **Ergebnis:** **$\text{B7}_H$** (bzw. `0xB7`)

4. **Letztes Oktett einer IP-Adresse ist Hex $\text{3D}$. Welchem Binärwert entspricht dies?**
   * Jede HEX-Ziffer in 4 Bits umwandeln:
     * $3_H = 0011_B$
     * $\text{D}_H = 13_{10} = 8 + 4 + 1 = 1101_B$
   * **Ergebnis:** **$0011'1101_B$**

---

## 3. Unsigned vs. Signed (Ganze Zahlen mit Vorzeichen)
* **Unsigned (ohne Vorzeichen):** Nur positive Zahlen ab $0$ (wie Kelvin ab $0\text{ K}$). Alle Bits zählen normal plus.
* **Signed (mit Vorzeichen / Zweierkomplement):** Kann auch Minus-Zahlen darstellen (wie Celsius unter $0^\circ\text{C}$). Das **allererste Bit links** hat einen **Minus-Wert** (bei 8 Bit ist das $-128$, bei 4 Bit $-8$).

### Aufgaben zu Zahlenumwandlung (Signed)

1. **Dezimalzahl $27$ in binäres 8-Bit „Signed“-Äquivalent umwandeln:**
   * Da $27$ positiv ist, bleibt das Vorzeichenbit vorne $0$:
   * **Ergebnis:** **$0001'1011_B$**

2. **Welchem Dezimalwert entspricht signed $1001'0011_B$?**
   * Vorderstes Bit ist $1 \rightarrow$ zählt $-128$. Rest wird normal addiert:
   * $-128 + 16 + 2 + 1 = -128 + 19$
   * **Ergebnis:** **$-109_D$**

---

## 4. Datentypen im Überblick

### Einfache & zusammengesetzte Datentypen
* **`signed int` (INTEGER):** Ganze Zahlen mit Minus und Plus (z. B. `-2, -1, 0, 1, 2`). *(Java: `int` = 32 Bit, `long` = 64 Bit)*
* **`unsigned int` (INTEGER):** Nur positive ganze Zahlen ab $0$ (`0, 1, 2...`).
* **`float` (FLOAT):** Fliesskommazahlen (z. B. `-2.1426`). Aufbau (32 Bit): $1\text{ Bit}$ Vorzeichen ($v$), $23\text{ Bit}$ Mantisse ($m$), $8\text{ Bit}$ Exponent ($e$) $\rightarrow x = v \cdot m \cdot 2^e$. *(Java: `float` = 32 Bit, `double` = 64 Bit)*
* **`boolean` (BOOLEAN):** Wahrheitswert (`true` oder `false`).
* **`char` (CHARACTER):** Ein einzelnes Zeichen (`'A'`, `'?'`, `'5'`).
* **`string` / `varchar`:** Textzeile, also eine Kette aus vielen `char` (z. B. `"Hello World!"`).

### Welcher Datentyp eignet sich wofür?

| Beispiel | Datentyp | Warum? |
| :--- | :--- | :--- |
| **Ameiseninvasion zählen** | `unsigned int` | Nur positive ganze Zahlen (keine halben oder minus Ameisen). |
| **Text schreiben** | `string` / `varchar` | Viele Zeichen (`char`) aneinandergehängt. |
| **Etagen zählen (inkl. Tiefgarage)** | `signed int` | Braucht auch Minus-Zahlen (z. B. `-1`, `-2` für Untergeschosse). |
| **Go oder NoGo entscheiden** | `boolean` | Gibt nur zwei Möglichkeiten: `true` (Go) oder `false` (NoGo). |
| **Geburtstagstorte teilen** | `float` | Es gibt Kommazahlen / Brüche (z. B. $1/3 = 0.333...$). |

---

## 5. Aufgaben zu Datentypen und Wertebereichen

1. **Wertebereich 16-Bit `unsigned int`:**
   * Möglichkeiten: $2^{16} = 65'536$
   * Bereich: **$0$ bis $65'535$** (weil die $0$ auch mitzählt).

2. **Wertebereich 16-Bit `signed int`:**
   * Hälfte ins Minus, Hälfte ins Plus:
   * Bereich: **$-32'768$ bis $+32'767$**

3. **Wie viele Zeichen sind bei 8-Bit `char` möglich?**
   * $2^8 =$ **$256$ Zeichen** (Zahlenwerte $0$ bis $255$).

4. **Minimale Anzahl Bits für $0_D$ bis $999'999_D$ (1 Mio. Werte):**
   * $2^{19} = 524'288$ (reicht nicht) | $2^{20} = 1'048'576$ (reicht!)
   * **Lösung:** **$20\text{ Bit}$**

5. **Minimale Anzahl Bits für $-999_D$ bis $+999_D$:**
   * Man braucht $999 + 1 \text{ (für 0)} + 999 = 1'999$ Werte.
   * $2^{10} = 1'024$ (zu wenig) | $2^{11} = 2'048$ (reicht für $-1024$ bis $+1023$)
   * **Lösung:** **$11\text{ Bit}$**

6. **Redundanz bei Werten $0$ bis $999$ ($1'000$ Werte) in $16\text{ Bit}$:**
   * Nötig wären nur $10\text{ Bit}$ ($2^{10} = 1'024$). Reserviert sind $16\text{ Bit}$.
   * **Redundanz (unbenutzter Platz):** $16\text{ Bit} - 10\text{ Bit} =$ **$6\text{ Bit}$**

7. **Binärzahl $101101_B$ normalisieren:**
   * Komma nach links schieben, bis vorne nur noch eine `1` steht (5 Stellen):
   * **Lösung:** **$1.01101_B \cdot 2^5$**

8. **IEEE-754 `float` (32 Bit) mit $300'000'000 + 1$:**
   * **Gespeicherter Wert:** Bleibt bei **$300'000'000$**.
   * **Begründung:** Ein 32-Bit-Float kann nur ca. 7 Stellen genau speichern (23 Bit Mantisse). Bei so grossen Zahlen sind die Abstände zwischen zwei speicherbaren Zahlen grösser als $1$ – die $+1$ geht durch Rundung verloren.

9. **Speicherbedarf `boolean` bei $100'000$ Kunden:**
   * **Theoretisch minimal ($1\text{ Bit}$ pro Kunde):** $100'000\text{ Bit} \div 8 =$ **$12'500\text{ Byte}$** ($\approx 12.2\text{ KB}$)
   * **Real ($1\text{ Byte}$ pro Kunde):** $100'000 \cdot 1\text{ Byte} =$ **$100'000\text{ Byte}$** ($\approx 97.7\text{ KB}$)

10. **Wochentag (1–7) als 4-Byte `INTEGER` bei 5 Mio. Datensätzen:**
    * **Bewertung:** **Unzweckmässig / Platzverschwendung.**
    * Für 1 bis 7 reichen theoretisch $3\text{ Bit}$. Selbst mit $1\text{ Byte}$ (`TINYINT`) würde man $3\text{ Byte}$ pro Eintrag sparen – bei 5 Mio. Zeilen wären das **$15\text{ MB}$ unnötiger Speicher**.

---

## 6. Zeichencodierung: ASCII, ISO-8859 & Unicode

### Von ASCII zu Unicode
* **7-Bit ASCII (1963):** Kann $2^7 = 128$ Zeichen (englische Buchstaben, Zahlen, Steuerzeichen). **Problem:** Keine Umlaute (`ä, ö, ü`) oder fremde Schriften.
* **8-Bit / ISO-8859:** Erweitert auf $256$ Zeichen. Zeichen $0$–$127$ sind gleich wie ASCII, $128$–$255$ je nach Region (z. B. **ISO-8859-1 / Latin-1** für Westeuropa). **Problem:** Falsche Tabelle = Zeichensalat (`OlivenÃ¶l` statt `Olivenöl`). Chinesisch (über $3'500$ Zeichen) passt gar nicht rein.
* **Unicode:** Löst das Problem weltweit. Jedes Zeichen hat einen eigenen **Codepunkt** (z. B. `U+00DF` für `ß`, `U+20AC` für `€`). Aktuell (V16.0) sind $154'998$ Zeichen in 168 Schriftsystemen zugewiesen (möglich sind über 1.1 Mio. Codepunkte).

### UTF-8 vs. UTF-16
* **UTF-8 (Standard im Internet):**
  * Braucht **1 bis 4 Byte** pro Zeichen (dynamische Länge).
  * **Abwärtskompatibel zu ASCII:** Normale Zeichen (`0`–`127`) brauchen **1 Byte** und sind identisch mit ASCII. Umlaute (`ä`) brauchen **2 Byte**, das `€`-Zeichen **3 Byte**.
  * *Erkennung im Binärcode:* `0xxxxxxx` (1 Byte), `110xxxxx 10xxxxxx` (2 Byte), `1110xxxx 10xxxxxx 10xxxxxx` (3 Byte), `11110xxx ...` (4 Byte).
* **UTF-16:**
  * Braucht bei uns **2 Byte** (16 Bit) pro Zeichen; seltene Zeichen (Emojis, Musiknoten) brauchen **4 Byte** (über *Surrogate-Paare* `D800`–`DFFF`).
  * **Byteorder (Endianness):** Zeigt am Dateianfang (BOM), welches Byte zuerst kommt:
    * **Big Endian (BE):** Grosses Byte zuerst (`FE FF`).
    * **Little Endian (LE):** Kleines Byte zuerst (`FF FE`).

### Fallbeispiel `"€URO"` im Vergleich

| Codierung | Hex-Darstellung | Bytes total | Bemerkung |
| :--- | :--- | :---: | :--- |
| **ANSI-ASCII** | `80` `55` `52` `4F` | **4 Byte** | Jedes Zeichen 1 Byte (`€` = `0x80`). |
| **UTF-8** | `E2 82 AC` `55` `52` `4F` | **6 Byte** | `€` braucht 3 Byte, `U R O` je 1 Byte (wie ASCII). |
| **UTF-16-BE** | `FE FF` `20 AC` `00 55` `00 52` `00 4F` | **10 Byte** | Startet mit BOM `FE FF`, dann je 2 Byte (grosses Byte vorn). |
| **UTF-16-LE** | `FF FE` `AC 20` `55 00` `52 00` `4F 00` | **10 Byte** | Startet mit BOM `FF FE`, Bytes pro Zeichen gedreht. |

---

## 7. Aufgaben zu Unicode (Lösungen)

1. **Wo wird UTF-8 eingesetzt, wo UTF-16?**
   * **UTF-8:** Internet/Webseiten (HTML), Linux, macOS, E-Mails, JSON.
   * **UTF-16:** Intern in Windows, Java, C# und JavaScript.

2. **Was bedeutet Byteorder bei UTF-16?**
   * Die Reihenfolge, in der die 2 Bytes eines Zeichens gespeichert werden (Big Endian = höherwertiges Byte zuerst vs. Little Endian = niederwertiges Byte zuerst).

3. **Was heisst «abwärtskompatibel» bei UTF-8 (gilt das auch für UTF-16)?**
   * Alte reine ASCII-Texte sind automatisch gültiges UTF-8 (gleiche Bitcodes). Bei **UTF-16 gilt das nicht**, weil dort jedes Zeichen mindestens 2 Byte belegt.

4. **Speicherbedarf bei deutschem/englischem Text (ISO-8859 vs. UTF-8 vs. UTF-16):**
   * **ISO-8859:** Am kleinsten (immer 1 Byte).
   * **UTF-8:** Fast gleich klein (1 Byte pro Buchstabe, nur Umlaute brauchen 2 Byte).
   * **UTF-16:** Am grössten (braucht fast doppelt so viel Platz, da jedes Zeichen 2 Byte belegt).

5. **Wann wird ein UTF-16-Code 4 Byte lang?**
   * Bei Zeichen über `U+FFFF` (z. B. Emojis 😀 oder Musiknoten), die über zwei 16-Bit-Blöcke (Surrogates) zusammengesetzt werden.

6. **Wie gibt man in Word ein Zeichen per Unicode ein (z. B. `€` = `20AC`)?**
   * `20AC` eintippen und direkt danach **`Alt` + `C`** (bzw. **`Alt` + `X`**) drücken.

7. **Problem beim Violinschlüssel (`U+1D11E`) in Word:**
   * Der Code ist 5-stellig (über `FFFF`). Normale Schriftarten (wie Arial/Calibri) haben dieses Zeichen nicht gespeichert – es erscheint dann oft nur ein leeres Kästchen (`□`), solange man keine spezielle Musik-Schriftart wählt.

8. **UTF-8 Bitcode für `®` (`U+00AE`):**
   * Hex: `0xC2 0xAE`
   * Binär: **`11000010 10101110`**

## Was habe ich heute gelernt?

Heute habe ich verstanden, wie der Computer im Hintergrund überhaupt Daten speichert – nämlich nur als `0` und `1` (Binär). Damit wir Menschen uns keine ewig langen Bit-Ketten merken müssen, nutzt man Hexadezimal als praktische Abkürzung (4 Bits = 1 HEX-Zeichen).

Ausserdem weiss ich jetzt:
* **Unsigned vs. Signed:** Ohne Vorzeichen sind alle Zahlen positiv, mit Vorzeichen bestimmt das erste Bit ganz links, ob die Zahl ins Minus geht (Zweierkomplement).
* **Datentypen:** Je nachdem, was man speichern will (nur ganze Zahlen, Kommazahlen, Ja/Nein oder Text), muss man den passenden Datentyp wählen, damit der Speicher nicht unnötig verschwendet wird.
* **Textcodierung:** Der alte 7-Bit-ASCII-Code reicht nur für englische Zeichen. Für Umlaute, Emojis und andere Sprachen braucht es Unicode – und heute ist **UTF-8** der Standard im Web, weil es speichersparend und abwärtskompatibel zu ASCII ist.
