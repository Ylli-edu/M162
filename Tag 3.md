# Modul 162: Daten analysieren und modellieren
## Lernjournal – Tag 3: Datentypen und Zeichencodierung

* **Autor:** Ylli Uka
* **Datum:** 23.11.2026
* **Modul:** M162


## 8 Aufgaben zu Unicode

### 1. Wo wird UTF-8 eingesetzt, wo UTF-16?
- **UTF-8:** Webseiten, Internet, E-Mails und Linux-Systeme.
- **UTF-16:** Windows-Systeme und Programmiersprachen wie Java.

### 2. Was bedeutet die Byteorder bei UTF-16?
Die Byteorder bestimmt die Reihenfolge, in der Bytes gespeichert werden.
- **Big Endian:** Wichtigstes Byte zuerst.
- **Little Endian:** Wichtigstes Byte zuletzt.

### 3. Was bedeutet «abwärtskompatibel» bei UTF-8? Gibt es das auch bei UTF-16?
- **UTF-8:** Ist abwärtskompatibel zu ASCII. Alte ASCII-Zeichen funktionieren unverändert.
- **UTF-16:** Ist nicht abwärtskompatibel zu ASCII, da Zeichen mindestens 2 Bytes benötigen.

### 4. Wie beurteilen Sie den Speicherbedarf?

| Codierung | Englisch | Deutsch |
|---|---|---|
| ISO-8859 | 1 Byte | 1 Byte |
| UTF-8 | 1 Byte | Meist 2 Bytes (ä, ö, ü) |
| UTF-16 | 2 Bytes | 2 Bytes |

UTF-8 benötigt bei englischen Texten wenig Speicher. UTF-16 benötigt bei normalen Zeichen meistens 2 Bytes.

### 5. Wann wird ein UTF-16-Code vier Byte lang?
Wenn ein Zeichen ausserhalb der Basic Multilingual Plane (BMP) liegt, z. B. bei vielen Emojis. Dafür werden zwei UTF-16-Codeeinheiten verwendet.

### 6. Wie können Sie in Word ein Zeichen eingeben, dessen Unicode Sie kennen?
Den Unicode als Hexadezimalzahl eingeben und danach **Alt + X** drücken.

Beispiel:
- Eurozeichen: `20AC`
- Danach Alt + X drücken → €

### 7. Was ist das Problem beim Violinschlüssel?
Der Violinschlüssel hat den Unicode `1D11E` und benötigt 4 Bytes in UTF-16. Ausserdem muss die verwendete Schriftart das Musikzeichen unterstützen.

### 8. Wie lautet der Bitcode in UTF-8 für das ®-Zeichen?
- Unicode: `U+00AE`
- UTF-8 (Hex): `C2 AE`
- UTF-8 (Binär): `11000010 10101110`
