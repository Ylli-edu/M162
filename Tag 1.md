# Modul 162: Daten analysieren und modellieren

## Lernjournal – Tag 1: Einführung, Datenstrukturen, Merkmalstypen & Skalentypen

* **Autor:** Ylli Uka
* **Datum:** 09.11.2026
* **Modul:** M162 – Daten analysieren und modellieren

---

## 1. Grundlagen: Daten, Nachricht, Information & Wissen

* **Daten:** Einzelne Zeichen oder Zahlen ohne weiteren Zusammenhang (z. B. `162`).
* **Nachricht:** Daten, die in einer bestimmten Form übermittelt werden (z. B. `Felix ist 162 cm gross.`).
* **Information:** Daten, die für jemanden eine Bedeutung haben (z. B. `Felix ist grösser als 150 cm.`).
* **Wissen:** Wenn man verschiedene Informationen miteinander verbindet und daraus etwas ableiten kann (z. B. `Felix erfüllt die Mindestgrösse für die Achterbahn.`).

---

## 2. Datenstrukturen & Datenverwaltung

### 2.1 Datenstrukturen
* **Unstrukturierte Daten:** Haben keine feste Ordnung oder ein bestimmtes Format (z. B. Papierzettel oder freier Text). Man kann sie einfach erfassen, aber nur schwer auswerten.
* **Wenig strukturierte Daten:** Sind bereits etwas geordnet (z. B. alphabetisch sortierte Visitenkarten).
* **Strukturierte Daten:** Haben eine klare, vorher festgelegte Struktur, zum Beispiel in einer Datenbank. Das Einrichten braucht zuerst mehr Aufwand. Dafür kann man die Daten später schnell suchen, abfragen und ändern.

### 2.2 Datenverwaltung
1. **Initialisieren:** Festlegen, wie die Daten aufgebaut sind und welche Formate verwendet werden (z. B. Text, Zahl oder Datum).
2. **Erfassen:** Neue Datensätze hinzufügen.
3. **Mutieren:** Vorhandene Datensätze suchen und ändern.
4. **Auswerten:** Daten suchen, filtern, vergleichen und analysieren.
5. **Löschen:** Datensätze vollständig entfernen.

### 2.3 Qualitative Vergleichstabelle
| Tätigkeit | Unstrukturierte Daten | Wenig strukturierte Daten | Strukturierte Daten | Begründung |
| :--- | :--- | :--- | :--- | :--- |
| **Initialisieren** | sehr einfach | einfach | sehr schwierig | Bei Datenbanken muss man zuerst genau festlegen, wie die Daten aufgebaut sind. |
| **Erfassen** | sehr einfach | einfach | mittelschwierig | Freie Texte kann man sofort eingeben. Bei strukturierten Daten müssen Formate und Regeln eingehalten werden. |
| **Mutieren** | sehr schwierig | mittelschwierig | einfach | In einer Datenbank kann man Daten gezielt über einen Schlüssel oder eine ID ändern. In freien Texten muss man sie zuerst mühsam suchen. |
| **Auswerten** | sehr schwierig | mittelschwierig | sehr einfach | Datenbanken können Daten automatisch mit Abfragen oder Filtern auswerten. Bei freien Texten muss man vieles von Hand machen. |
| **Löschen** | sehr schwierig | mittelschwierig | sehr einfach | In einer Datenbank kann man Datensätze gezielt löschen. Bei unstrukturierten Daten muss man die Dateien von Hand durchsuchen. |

### 2.4 Redundanz
* **Unerwünschte Redundanz:** Dieselben Daten werden mehrfach gespeichert. Wenn man sie an einer Stelle ändert und an einer anderen nicht, entstehen unterschiedliche oder falsche Daten.
* **Erwünschte Redundanz:** Daten werden absichtlich kopiert, zum Beispiel bei Backups. So sind sie besser geschützt, falls etwas ausfällt.

---

## 3. Merkmalstypen

Ein Merkmal beschreibt eine Eigenschaft einer Untersuchungseinheit:

* **Häufbar:** Es können mehrere Werte gleichzeitig zutreffen (z. B. Sprachkenntnisse oder Hobbys).
* **Nicht häufbar:** Es kann genau ein Wert zutreffen (z. B. Geburtsdatum).
* **Diskret:** Es gibt einzelne, abzählbare Werte oder ganze Zahlen (z. B. Anzahl Tore oder Teilnehmer).
* **Stetig:** Es handelt sich um einen Messwert, der auch Zwischenwerte haben kann (z. B. Körpergrösse, Gewicht oder Zeit).

<img width="908" height="234" alt="Screenshot 2026-11-09 135809" src="https://github.com/user-attachments/assets/0e6e8ce9-2a2e-4e72-a5fc-217f0c272059" />

| Merkmalstyp | Beschreibung | Beispiele aus dem Unterricht |
| :--- | :--- | :--- |
| **Häufbar** | Mehrere Nennungen sind möglich | Hobby, Berufsausbildung |
| **Diskret** | Einzelne, abzählbare Werte | Geschlecht, Teilnehmeranzahl, Haarfarbe |
| **Stetig** | Messwerte mit möglichen Zwischenwerten | Gewicht, Strecke, Zeitintervall, Wasserpegel |

---

## 4. Skalentypen

Die Skala zeigt, welche Vergleiche und Berechnungen mit den Daten möglich sind:

* **Nominalskala:** Werte werden nur in Kategorien eingeteilt. Es gibt keine Rangfolge. Man kann nur sagen, ob etwas gleich oder unterschiedlich ist ($=, \\neq$).
* **Ordinalskala:** Die Werte haben eine Reihenfolge. Wie gross die Abstände zwischen ihnen sind, kann man aber nicht genau sagen ($<, >$).
* **Kardinalskala (metrisch):** Die Abstände zwischen den Werten sind genau messbar. Deshalb sind mathematische Berechnungen möglich ($+, -, \\bar{x}$).

<img width="906" height="236" alt="Screenshot 2026-11-09 141121" src="https://github.com/user-attachments/assets/1c4a9e8f-87fc-40b2-9ec8-ee0c0aa9b17b" />

| Skalentyp | Operationen | Beispiele aus dem Unterricht |
| :--- | :--- | :--- |
| **Nominalskala** | Kategorien | Geschlecht, Kontonummer, Haarfarbe, Telefonnummer |
| **Ordinalskala** | Rangfolge | Zufriedenheit (1–5), Militärischer Dienstrang, Präferenzrangfolge |
| **Kardinalskala (metrisch)** | Messbar | Zeitdauer, Streckenlänge, Gewicht, Körpergrösse |

---

## 5. Anwendung: Fragebogen (Aufgabe 3 – Thema: Cristiano Ronaldo)

In Aufgabe 3 haben wir einen Fragebogen zum Thema Cristiano Ronaldo erstellt. Dabei sollten die verschiedenen Merkmalstypen und Skalentypen vorkommen:

* **Aus welchem Land kommt Ronaldo?:** Nominalskala & nicht häufbares Merkmal (Einzelauswahl).
* **Wie viele Kinder hat Ronaldo?:** Kardinalskala & diskretes Merkmal (Ganzzahlen).
* **Wie schwer ist Ronaldo?:** Kardinalskala & stetiges Merkmal (Messwerte mit Kommas).

---

## 6. Abschlussaufgabe: Suchmaschinen

### 6.1 Wie findet Google so schnell Webseiten?

HTML besteht zwar aus Text, hat aber eine klare Struktur:

* **Titel:** Zeigt, worum es auf der Seite geht.
* **Überschriften:** Teilen den Inhalt auf.
* **Absätze:** Enthalten den Text.
* **Links:** Verbinden Webseiten.

Google nutzt sogenannte Crawler, um Webseiten zu durchsuchen. Die Informationen werden in einem Suchindex gespeichert. So findet Google bei einer Suche schnell passende Ergebnisse.

### 6.2 Vergleich der Suchmaschinen

| Suchmaschine | Besonderheit |
| :--- | :--- |
| **Google** | Eigener Suchindex und eigene Sortierung der Ergebnisse. |
| **Bing** | Suchmaschine von Microsoft mit eigenem Suchindex. |
| **DuckDuckGo** | Legt viel Wert auf Datenschutz und verwendet unter anderem Suchergebnisse von Bing. |

### 6.3 Woher kommen die Unterschiede?

Die Suchmaschinen zeigen nicht immer dieselben Ergebnisse. Das liegt daran, dass sie:

* unterschiedliche Daten sammeln,
* eigene Regeln zum Sortieren verwenden,
* Webseiten unterschiedlich bewerten,
* Standort und Sprache berücksichtigen.

**Fazit:** Obwohl man überall denselben Begriff eingibt, können unterschiedliche Ergebnisse erscheinen, weil jede Suchmaschine anders arbeitet.

---

## 🧠 Was habe ich heute gelernt?

* Ich kenne den Unterschied zwischen **Daten, Nachrichten, Informationen und Wissen** und weiss, was sie in der Informatik bedeuten.
* Ich verstehe die Vor- und Nachteile von **unstrukturierten, wenig strukturierten und strukturierten Daten** beim Einrichten, Erfassen, Ändern, Auswerten und Löschen.
* Ich kann **unerwünschte Redundanz** (wenn Daten widersprüchlich werden können) von **erwünschter Redundanz** (z. B. Backups) unterscheiden.
* Ich kann erkennen, ob ein Merkmal **häufbar** oder **nicht häufbar** ist und ob die Daten **diskret** oder **stetig** sind.
* Ich kenne die drei Skalentypen (**Nominal-, Ordinal- und Kardinalskala**) und weiss, welche mathematischen Operationen damit möglich sind.
* Ich kann einen Fragebogen so aufbauen, dass die geforderten Merkmalstypen und Skalentypen vorkommen.
