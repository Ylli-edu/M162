# Modul 162: Daten analysieren und modellieren
## Lernjournal – Tag 2: Datentypen und Zeichencodierung

* **Autor:** Ylli Uka
* **Datum:** 09.11.2026
* **Modul:** M162

---

## 1. Wie der Computer Daten speichert

Ein Computer speichert Daten mit **0 und 1**. Bilder, Texte und Musik sehen für den Computer also alle wie eine lange Reihe von Nullen und Einsen aus. Das Programm muss wissen, wie es diese Daten lesen soll.

### Versuch mit `Matterhorn.jpg`

Ich habe die Datei in `Matterhorn.txt` umbenannt.

**Was passiert beim Öffnen?**

Der Computer öffnet sie jetzt wahrscheinlich mit einem Textprogramm. Dort sieht man keine normale Schrift, sondern Zeichen-Salat. Die Datei ist immer noch ein Bild. Nur der Name wurde geändert.

**Wer entscheidet, was die Daten bedeuten?**

Das Programm. Es schaut zum Beispiel auf die Dateiendung oder auf den Inhalt der Datei.

---

## 2. Zahlensysteme

| Zahlensystem | Verwendet | Beispiel | Erklärung |
| --- | --- | --- | --- |
| Binär | `0` und `1` | `0110'1011` | Damit rechnet der Computer. |
| Dezimal | `0` bis `9` | `2025` | Das normale Zahlensystem für uns. |
| Hexadezimal | `0` bis `9`, `A` bis `F` | `FF3C` | Eine kürzere Schreibweise für Binärzahlen. Eine Hex-Ziffer steht für 4 Bit. |

Bei Hexadezimal sind `A = 10`, `B = 11`, `C = 12`, `D = 13`, `E = 14` und `F = 15`.

### Zahlen umwandeln: unsigned

**1. 27 als Binärzahl**

27 = 16 + 8 + 2 + 1

**Lösung: `0001'1011`**

**2. `1001'0011` als Dezimalzahl**

128 + 16 + 2 + 1 = 147

**Lösung: 147**

**3. `1011'0111` als Hexadezimalzahl**

Teile die Zahl in zwei Vierergruppen: `1011` und `0111`.

`1011` ist `B` und `0111` ist `7`.

**Lösung: `B7`**

**4. Hexadezimal `3D` als Binärzahl**

`3` wird zu `0011`. `D` wird zu `1101`.

**Lösung: `0011'1101`**

---

## 3. Unsigned und signed

- **Unsigned** bedeutet ohne Minuszahlen. Damit speichert man Zahlen ab 0.
- **Signed** bedeutet mit Minus- und Pluszahlen. Bei 8 Bit hat das linke Bit den Wert `-128`. Die anderen Bits zählen normal.

### Zahlen umwandeln: signed

**1. 27 als 8-Bit-Zahl**

27 ist positiv. Vorne steht darum eine `0`.

**Lösung: `0001'1011`**

**2. `1001'0011` als Dezimalzahl**

Das linke Bit zählt `-128`. Die restlichen Bits ergeben 16 + 2 + 1.

-128 + 16 + 2 + 1 = -109

**Lösung: -109**

---

## 4. Datentypen

- **`int`**: Ganze Zahlen, zum Beispiel `-2`, `0` oder `12`.
- **`unsigned int`**: Ganze Zahlen ab `0`.
- **`float`**: Zahlen mit Komma, zum Beispiel `2.5`.
- **`boolean`**: `true` oder `false`.
- **`char`**: Ein einzelnes Zeichen, zum Beispiel `'A'`.
- **`string`**: Mehrere Zeichen, zum Beispiel `"Hallo"`.

### Welcher Typ passt?

| Aufgabe | Datentyp | Grund |
| --- | --- | --- |
| Ameisen zählen | `unsigned int` | Es gibt keine minus Ameisen. |
| Text speichern | `string` | Text besteht aus mehreren Zeichen. |
| Stockwerke zählen, auch Keller | `signed int` | Kellerstockwerke können als Minuszahl geschrieben werden. |
| Go oder NoGo speichern | `boolean` | Es gibt zwei Möglichkeiten. |
| Kuchen aufteilen | `float` | Es können Kommazahlen vorkommen. |

---

## 5. Wertebereiche und Speicher

**1. Wertebereich von 16-Bit unsigned**

Es gibt `2^16 = 65'536` verschiedene Werte.

**Lösung: 0 bis 65'535**

**2. Wertebereich von 16-Bit signed**

**Lösung: -32'768 bis 32'767**

**3. Wie viele Werte passen in 8 Bit?**

`2^8 = 256`

**Lösung: 256 Werte**

**4. Wie viele Bits braucht man für die Zahlen 0 bis 999'999?**

19 Bit reichen nicht. Mit 20 Bit gibt es genug Möglichkeiten.

**Lösung: 20 Bit**

**5. Wie viele Bits braucht man für -999 bis +999?**

Es sind 1'999 Zahlen. 10 Bit reichen nicht, 11 Bit reichen.

**Lösung: 11 Bit**

**6. Wie viele Bits sind bei 16 Bit ungenutzt, wenn Werte von 0 bis 999 gespeichert werden?**

Für 1'000 Werte braucht man mindestens 10 Bit. Es bleiben `16 - 10 = 6` Bit übrig.

**Lösung: 6 Bit**

**7. Binärzahl `101101` normalisieren**

Das Komma wird fünf Stellen nach links verschoben.

**Lösung: `1.01101 × 2^5`**

**8. Was passiert bei `300'000'000 + 1` mit einem 32-Bit-float?**

Ein Float kann grosse Zahlen nicht ganz genau speichern. Bei dieser Zahl ist der Abstand zwischen gespeicherten Werten grösser als 1.

**Lösung: Das Ergebnis bleibt normalerweise 300'000'000.**

**9. Speicher für 100'000 Boolean-Werte**

Wenn jeder Wert 1 Bit braucht, sind es `100'000 ÷ 8 = 12'500` Byte. Wenn jeder Wert 1 Byte braucht, sind es `100'000` Byte.

**Lösung: mindestens 12'500 Byte; bei 1 Byte pro Wert 100'000 Byte.**

**10. Wochentag als 4-Byte-Zahl bei 5 Millionen Einträgen**

Für die Zahlen 1 bis 7 reichen 3 Bit. Ein 4-Byte-Integer ist dafür ziemlich gross. Mit einem 1-Byte-Typ spart man 3 Byte pro Eintrag.

**Lösung: 5 Millionen × 3 Byte = 15 Millionen Byte (ungefähr 15 MB) gespart.**

---

## 6. Zeichencodierung

Zeichencodierungen legen fest, welche Zahlen für welche Zeichen stehen.

- **ASCII** kann 128 Zeichen darstellen. Umlaute und viele andere Zeichen fehlen.
- **ISO-8859-1** kann 256 Zeichen darstellen und enthält zum Beispiel deutsche Umlaute. Es kann aber nicht alle Zeichen darstellen.
- **Unicode** hat Codes für Zeichen aus vielen Sprachen. Zum Beispiel ist `ß` der Code `U+00DF` und `€` ist `U+20AC`.

### UTF-8 und UTF-16

- **UTF-8** braucht je nach Zeichen 1 bis 4 Byte. Englische Buchstaben brauchen 1 Byte. Umlaute brauchen meistens 2 Byte, `€` braucht 3 Byte. UTF-8 ist mit ASCII kompatibel.
- **UTF-16** braucht meistens 2 Byte pro Zeichen. Seltene Zeichen, zum Beispiel manche Emojis, brauchen 4 Byte.
- Bei UTF-16 gibt es Big Endian und Little Endian. Das beschreibt, in welcher Reihenfolge die Bytes gespeichert werden.

### Beispiel: `€URO`

| Codierung | Bytes | Anzahl |
| --- | --- | ---: |
| Windows-1252 | `80 55 52 4F` | 4 Byte |
| UTF-8 | `E2 82 AC 55 52 4F` | 6 Byte |
| UTF-16-BE mit BOM | `FE FF 20 AC 00 55 00 52 00 4F` | 10 Byte |
| UTF-16-LE mit BOM | `FF FE AC 20 55 00 52 00 4F 00` | 10 Byte |

Die Bytes `80` für das Euro-Zeichen gelten hier für **Windows-1252**, nicht für ASCII.

---

## 7. Aufgaben zu Unicode

**1. Wo wird UTF-8 und wo UTF-16 verwendet?**

UTF-8 wird oft für Webseiten und Dateien im Internet verwendet. UTF-16 wird zum Beispiel in Java und in vielen Windows-Programmen verwendet.

**Lösung: UTF-8 ist im Web sehr verbreitet. UTF-16 wird unter anderem von Java verwendet.**

**2. Was bedeutet Byteorder?**

Es bedeutet, in welcher Reihenfolge die Bytes gespeichert werden.

**Lösung: Big Endian speichert das grosse Byte zuerst, Little Endian das kleine Byte zuerst.**

**3. Was bedeutet, dass UTF-8 mit ASCII kompatibel ist?**

Die normalen ASCII-Zeichen haben in UTF-8 dieselben Werte und brauchen 1 Byte.

**Lösung: ASCII-Text kann auch als UTF-8 gelesen werden. Bei UTF-16 ist das nicht so.**

**4. Welche Codierung braucht am wenigsten Speicher für deutschen und englischen Text?**

ISO-8859-1 braucht für die Zeichen, die es unterstützt, 1 Byte. UTF-8 braucht für normale englische Zeichen auch 1 Byte, für Umlaute aber mehr. UTF-16 braucht meistens 2 Byte.

**Lösung: Für einfache Texte ist ISO-8859-1 oft kleiner. UTF-8 ist praktisch und braucht für englischen Text ebenfalls wenig Speicher.**

**5. Wann braucht ein Zeichen in UTF-16 4 Byte?**

Bei Zeichen über `U+FFFF`, zum Beispiel bei manchen Emojis.

**Lösung: Solche Zeichen werden mit zwei 16-Bit-Teilen gespeichert.**

**6. Wie kann man in Word das Euro-Zeichen mit seinem Unicode eingeben?**

`20AC` schreiben und danach `Alt` + `X` drücken.

**Lösung: `20AC` + `Alt` + `X` ergibt `€`.**

**7. Was kann beim Violinschlüssel `U+1D11E` passieren?**

Nicht jede Schriftart hat dieses Zeichen. Dann sieht man vielleicht nur ein leeres Kästchen.

**Lösung: Man braucht eine Schriftart, die das Zeichen unterstützt.**

**8. Wie sieht `®` in UTF-8 aus?**

**Lösung in Hex: `C2 AE`**  
**Lösung in Binär: `11000010 10101110`**

---

## Was habe ich heute gelernt?

Der Computer speichert Daten als Nullen und Einsen. Mit verschiedenen Zahlensystemen kann man diese Daten unterschiedlich aufschreiben.

Ich habe auch gelernt, dass es verschiedene Datentypen gibt. Man muss den passenden Typ wählen, je nachdem, was man speichern will.

Für Text gibt es verschiedene Codierungen. UTF-8 wird im Internet oft verwendet und kann auch Umlaute und Emojis speichern.
