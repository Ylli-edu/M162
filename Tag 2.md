# Modul 162: Daten analysieren und modellieren

## Lernjournal – Tag 2: Datentypen und Zahlensysteme

* **Autor:** Ylli Uka
* **Datum:** 09.11.2026
* **Modul:** M162 – Daten analysieren und modellieren

## 1. Wie liest ein Computer Dateien?

Ein Computer arbeitet mit Bits. Ein Bit kann entweder `0` oder `1` sein. Aus vielen Bits bestehen alle Daten auf dem Computer – zum Beispiel Bilder, Musik und Texte.

Die Bits allein sagen aber nicht, ob es ein Bild oder ein Text ist. Ein Programm muss wissen, wie es die Daten lesen soll. Dafür sind unter anderem das Dateiformat und das verwendete Programm wichtig.

### Experiment: Eine Bilddatei umbenennen

Ich ändere den Namen der Datei `Matterhorn.jpg` zu `Matterhorn.txt`.

1. **Die Datei heisst `Matterhorn.jpg`:** Beim Öffnen startet normalerweise ein Bildprogramm. Es liest die Daten als Bild und zeigt Farben und Pixel an.
2. **Die Datei heisst `Matterhorn.txt`:** Beim Öffnen startet normalerweise ein Texteditor. Er versucht, die Daten als Text zu lesen. Weil es eigentlich ein Bild ist, erscheinen oft unlesbare Zeichen.
3. **Was passiert dabei?** Das Betriebssystem wählt anhand der Dateiendung meistens ein Programm aus. Das Programm liest und interpretiert die Daten. Wenn ich nur den Dateinamen ändere, wird der Inhalt der Datei nicht automatisch umgewandelt.

## 2. Zahlensysteme

In der Informatik begegnen mir vor allem drei Zahlensysteme:

| System | Basis | Verwendete Zeichen | Beispiel | Einfach erklärt |
| --- | ---: | --- | --- | --- |
| **Binär (BIN)** | 2 | `0` und `1` | `0110'1011₂` | Computer arbeiten intern mit Bits. |
| **Dezimal (DEZ)** | 10 | `0` bis `9` | `2025₁₀` | Das ist das Zahlensystem, das wir im Alltag verwenden. |
| **Hexadezimal (HEX)** | 16 | `0` bis `9` und `A` bis `F` | `FF3C₁₆` oder `0xFF3C` | Damit kann man Binärzahlen kürzer aufschreiben. |

Bei Hexadezimalzahlen stehen die Buchstaben für Zahlen: `A = 10`, `B = 11`, `C = 12`, `D = 13`, `E = 14` und `F = 15`.

Eine Hexadezimalziffer entspricht genau vier Bits. Zum Beispiel ist `1111₂` gleich `F₁₆`.

## 3. Zahlen umwandeln: Unsigned

**Unsigned** bedeutet «ohne Vorzeichen». Die Zahl kann also nicht negativ sein. Alle Bits werden verwendet, um den Zahlenwert darzustellen.

### Aufgabe 1: Dezimalzahl 27 in Binär umwandeln

Ich zerlege 27 in Zweierpotenzen:

`27 = 16 + 8 + 2 + 1`

Die passenden Bits dazu sind `11011₂`.

**Lösung:** `11011₂` oder als 8-Bit-Zahl `0001'1011₂`.

### Aufgabe 2: Binärzahl `1001'0011₂` in Dezimal umwandeln

Jede Stelle hat einen bestimmten Wert. Von rechts nach links sind das bei 8 Bit `1, 2, 4, 8, 16, 32, 64, 128`.

Bei `1001'0011₂` addiere ich die Werte der Stellen, an denen eine `1` steht:

`128 + 16 + 2 + 1 = 147`

**Lösung:** `147₁₀`.

### Aufgabe 3: Binärzahl `1011'0111₂` in Hexadezimal umwandeln

Ich teile die Binärzahl in zwei Gruppen mit je vier Bits:

* `1011₂` ist `B₁₆`.
* `0111₂` ist `7₁₆`.

**Lösung:** `B7₁₆` oder `0xB7`.

### Aufgabe 4: Hexadezimalzahl `3D₁₆` in Binär umwandeln

Ich wandle jede Hexadezimalziffer in vier Bits um:

* `3₁₆` wird zu `0011₂`.
* `D₁₆` wird zu `1101₂`.

**Lösung:** `0011'1101₂`.

## 4. Zahlen mit Vorzeichen: Signed

**Signed** bedeutet, dass eine Zahl positiv, negativ oder null sein kann. Dafür wird häufig das Zweierkomplement verwendet.

Bei einer 8-Bit-Zahl hat das linke Bit eine besondere Bedeutung. Ist es `0`, ist die Zahl normalerweise positiv oder null. Ist es `1`, ist die Zahl negativ.

Zum Beispiel kann dieselbe 4-Bit-Folge je nach Interpretation einen anderen Wert haben:

| Binärzahl | Als Unsigned | Als Signed (Zweierkomplement) |
| --- | ---: | ---: |
| `1011₂` | 11 | -5 |

### Aufgabe 1: Dezimalzahl 27 als 8-Bit-Signed-Zahl

27 ist positiv, darum beginnt die Binärzahl mit `0`. Die Binärdarstellung ist dieselbe wie bei Unsigned, nur mit acht Bits aufgeschrieben.

**Lösung:** `0001'1011₂`.

### Aufgabe 2: Binärzahl `1001'0011₂` als Signed-Zahl

Das linke Bit ist `1`, darum ist die Zahl im 8-Bit-Zweierkomplement negativ. Ich rechne mit den Stellenwerten:

`-128 + 16 + 2 + 1 = -109`

**Lösung:** `-109₁₀`.

## 5. Datentypen

Ein Datentyp sagt einem Programm, welche Art von Wert in einer Variable gespeichert wird. Zum Beispiel eine ganze Zahl, einen Text oder einen Wahrheitswert.

### Zahlen und Wahrheitswerte

* **`INTEGER` / `int`:** Ganze Zahlen, zum Beispiel `-2`, `0` oder `15`.
  * In Java ist ein `int` 32 Bit gross. Ein `long` ist 64 Bit gross.
* **Unsigned Integer:** Ganze Zahlen ohne negative Werte, zum Beispiel `0`, `1` oder `15`. Nicht jede Programmiersprache unterstützt diesen Datentyp gleich.
* **`FLOAT` / `float`:** Zahlen mit Nachkommastellen, zum Beispiel `3.14` oder `-0.5`.
  * Ein `float` hat normalerweise 32 Bit. Davon sind 1 Bit für das Vorzeichen, 8 Bit für den Exponenten und 23 Bit für die Nachkommastellen der Binärdarstellung reserviert.
  * In Java ist `float` 32 Bit und `double` 64 Bit gross.
* **`BOOLEAN` / `boolean`:** Ein Wahrheitswert. Er ist entweder `true` (wahr) oder `false` (falsch).

### Zeichen und Texte

* **`CHARACTER` / `char`:** Ein einzelnes Zeichen, zum Beispiel `'A'`, `'7'` oder `'?'`.
* **`STRING` / `VARCHAR`:** Mehrere Zeichen zusammen, also ein Text. Zum Beispiel `"Hallo Welt!"`.

## Mein Fazit

Heute habe ich gelernt, dass Computer Daten intern als Bits speichern. Je nachdem, wie ein Programm die Bits liest, können sie zum Beispiel ein Bild, Text oder eine Zahl darstellen. Ausserdem weiss ich jetzt, wie man zwischen Binär-, Dezimal- und Hexadezimalzahlen umwandelt und wofür verschiedene Datentypen gebraucht werden.
