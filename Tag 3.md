# Modul 162: Daten analysieren und modellieren

## Lernjournal – Tag 3: Datenstruktur JSON

- **Autor:** Ylli Uka
- **Datum:** 23.11.2026
- **Modul:** M162

---

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

Den Unicode als Hexadezimalzahl eingeben und danach **Alt + C** drücken.

**Beispiel:**

- Eurozeichen: `20AC`
- Danach Alt + C drücken → €

### 7. Was ist das Problem beim Violinschlüssel?

Der Violinschlüssel hat den Unicode `1D11E` und benötigt 4 Bytes in UTF-16. Ausserdem muss die verwendete Schriftart das Musikzeichen unterstützen.

### 8. Wie lautet der Bitcode in UTF-8 für das ®-Zeichen?

- Unicode: `U+00AE`
- UTF-8 (Hex): `C2 AE`
- UTF-8 (Binär): `11000010 10101110`

---

## Datenstrukturen (Selbständig erarbeiten)

### 3. Hashmap (Hashtabelle)

- Speichert Daten mithilfe eines Schlüssels (Key).
- Eine Hashfunktion findet schnell den Speicherort der Daten.
- Beispiel: Name eingeben → Telefonnummer wird gefunden.
- Vorteil: Sehr schnelles Suchen.

### 4. Binary Search Tree (Binärer Suchbaum)

- Eine Baumstruktur zum Speichern und Suchen von Werten.
- Kleinere Zahlen kommen nach links, grössere nach rechts.
- Beispiel: Wörterbuchsuche.
- Vorteil: Werte können schnell gefunden werden.

### 5. Linked List (Verkettete Liste)

- Besteht aus mehreren miteinander verbundenen Elementen.
- Jedes Element verweist auf das nächste Element.
- Beispiel: Gekoppelte Eisenbahnwagen.
- Vorteil: Elemente können einfach hinzugefügt oder entfernt werden.

### 6. Stack (Stapelspeicher)

- Funktioniert nach dem Prinzip FILO (First In, Last Out).
- Das zuletzt gespeicherte Element wird zuerst wieder entfernt.
- Beispiel: Kartoffelchipsschachtel.
- Vorteil: Einfaches Verwalten von Daten in einer bestimmten Reihenfolge.

### 7. Heap (Halde / Haufen)

- Ist ein vollständiger Binärbaum.
- Wird für Prioritätswarteschlangen verwendet.
- Es gibt Min-Heap (kleinster Wert zuerst) und Max-Heap (grösster Wert zuerst).
- Vorteil: Elemente mit hoher Priorität können schnell gefunden werden.

### 8. FIFO / Queue (Warteschlange)

- Funktioniert nach dem Prinzip First In, First Out.
- Das Element, das zuerst hineinkommt, wird auch zuerst entfernt.
- Beispiel: Warteschlange an der Kasse.
- Vorteil: Daten werden in der richtigen Reihenfolge verarbeitet.


### 9. HTML, JavaScript und JSON

**HTML**
- HTML ist die Grundstruktur einer Webseite.
- HTML-Dateien haben die Endung `.html` und werden im Browser angezeigt.
- Mit dem `<script>`-Tag kann JavaScript direkt in HTML eingebunden werden.

**JSON in HTML verwenden**
- JSON-Daten können in JavaScript gespeichert und verarbeitet werden.
- Mit `console.log()` können Daten in der Browser-Konsole angezeigt werden.
- Mit `document.write()` können Daten direkt auf der Webseite ausgegeben werden.
- Mit `[0]` greift man auf das erste Element eines Arrays zu.
- Mit `.name` kann man auf einen bestimmten Wert eines Objekts zugreifen.
- JSON direkt in HTML eingebunden nennt man auch Embedded JSON oder Inline JSON.

**Fetch-API**
- Mit der Fetch-API können Daten von externen Quellen abgerufen werden.
- Beispiel: Wetterdaten von OpenWeatherMap.
- Die API liefert die Daten im JSON-Format zurück.
- Mit `response.json()` werden die empfangenen Daten als JSON verarbeitet.
- Anschliessend können einzelne Werte wie Temperatur, Wetterbeschreibung oder Stadtname ausgelesen und angezeigt werden.

**Wichtige Begriffe**
- API: Schnittstelle zum Austausch von Daten zwischen Programmen.
- Fetch: Ruft Daten von einer externen Quelle ab.
- JSON: Format zur Speicherung und Übertragung von Daten.
- JavaScript: Programmiersprache, die im Browser ausgeführt werden kann.
