# Modul 162: Daten analysieren und modellieren

## Lernjournal – Tag 1: Einführung, Datenstrukturen, Merkmalstypen & Skalentypen

* **Autor:** Ylli Uka
* **Datum:** 09.11.2026
* **Modul:** M162 – Daten analysieren und modellieren

---

## 1. Grundlagen: Daten, Nachricht, Information & Wissen

* **Daten:** Zeichen oder Symbole ohne Kontext (z. B. `162`).
* **Nachricht:** Übermittelte Daten mit syntaktischer Struktur (z. B. `Felix ist 162 cm gross.`).
* **Information:** Daten, die im Empfänger-Kontext eine Bedeutung erhalten (z. B. `Felix ist grösser als 150 cm.`).
* **Wissen:** Verknüpfung von Informationen zu einer Handlungsgrundlage (z. B. `Felix erfüllt die Mindestgrösse für die Achterbahn.`).

---

## 2. Datenstrukturen & Datenverwaltung

### 2.1 Datenstrukturen
* **Unstrukturierte Daten:** Keine feste Ordnung oder Formatierung (z. B. Papierzettel, freier Text). Sehr einfache Erfassung, aber extrem schwer auszuwerten.
* **Wenig strukturierte Daten:** Leicht vorgeordnete Daten (z. B. alphabetisch sortierte Visitenkarten).
* **Strukturierte Daten:** Vorgegebenes Datenbank. Höherer Vorab-Aufwand bei der Modellierung, dafür sehr schneller Zugriff, Abfrage und Mutation.

### 2.2 Datenverwaltung 
1. **Initialisieren:** Datenstruktur, Datenmodell und Formate (Text, Zahl, Datum) definieren.
2. **Erfassen:** Neue Datensätze hinzufügen.
3. **Mutieren:** Datensätze suchen und anpassen.
4. **Auswerten:** Daten suchen, filtern, vergleichen und analysieren.
5. **Löschen:** Datensätze vollständig entfernen.


### 2.3 Redundanz
* **Unerwünschte Redundanz:** Mehrfaches Speichern gleicher Daten. Bei Änderungen entstehen Inkonsistenzen und die Datenintegrität wird verletzt.
* **Erwünschte Redundanz:** Gezielte Duplizierung (z. B. Backups) zur Erhöhung der Ausfallsicherheit.

---

## 3. Merkmalstypen

Ein Merkmal beschreibt eine Eigenschaft einer Untersuchungseinheit:
* **Häufbar:** Mehrere Werte gleichzeitig möglich (z. B. Sprachkenntnisse, Hobbys).
* **Nicht häufbar:** Genau ein Wert trifft zu (z. B. Geburtsdatum).
* **Diskret:** Abzählbare, getrennte Werte / ganze Zahlen (z. B. Anzahl Tore, Teilnehmeranzahl).
* **Stetig:** Kontinuierlicher Messwert aus einem Stufenlosbereich (z. B. Körpergrösse, Gewicht, Zeit).

<img width="908" height="234" alt="Screenshot 2026-11-09 135809" src="https://github.com/user-attachments/assets/0e6e8ce9-2a2e-4e72-a5fc-217f0c272059" />


| Merkmalstyp | Beschreibung | Beispiele aus dem Unterricht |
| :--- | :--- | :--- |
| **Häufbar** | Mehrfachnennung möglich | Hobby, Berufsausbildung |
| **Diskret** | Abzählbare Einzelwerte | Geschlecht, Teilnehmeranzahl, Haarfarbe |
| **Stetig** | Kontinuierliche Messwerte | Gewicht, Strecke, Zeitintervall, Wasserpegel |

---

## 4. Skalentypen

Die Skalierung legt fest, welche mathematischen Vergleiche und Berechnungen zulässig sind:
* **Nominalskala:** Reines Kategorisieren ohne Rangfolge. Nur Gleichheit/Ungleichheit zulässig ($=, \neq$).
* **Ordinalskala:** Rangfolge vorhanden, aber Abstände nicht exakt messbar ($<, >$).
* **Kardinalskala (metrisch):** Exakte messbare Abstände, alle mathematischen Operationen zulässig ($+, -, \bar{x}$).

<img width="906" height="236" alt="Screenshot 2026-11-09 141121" src="https://github.com/user-attachments/assets/1c4a9e8f-87fc-40b2-9ec8-ee0c0aa9b17b" />


| Skalentyp | Operationen | Beispiele aus dem Unterricht |
| :--- | :--- | :--- |
| **Nominalskala** | Kategorien  | Geschlecht, Kontonummer, Haarfarbe, Telefonnummer |
| **Ordinalskala** | Rangfolge  | Zufriedenheit (1–5), Militärischer Dienstrang, Präferenzrangfolge |
| **Kardinalskala (metrisch)** | Messbar  | Zeitdauer, Streckenlänge, Gewicht, Körpergrösse |

---

## 5. Anwendung: Fragebogen (Aufgabe 3 – Thema: Cristiano Ronaldo)

In Aufgabe 3 wurde ein Fragebogen zum Thema Cristiano Ronaldo entwickelt, um alle geforderten Merkmal- und Skalentypen korrekt abzudecken:

* **Aus welchem Land kommt Ronaldo?:** Nominalskala & nicht häufbares Merkmal (Einzelauswahl).
* **Wie viele Kinder hat Ronaldo?:** Kardinalskala & diskretes Merkmal (Ganzzahlen).
* **Wie schwer ist Ronaldo?:** Kardinalskala & stetiges Merkmal (Messwerte mit Kommas).

---

## 🧠 Was habe ich heute gelernt?

* Ich kenne den Unterschied zwischen **Daten, Nachrichten, Informationen und Wissen** sowie deren Bedeutung in der Informatik.
* Ich verstehe die Vor- und Nachteile von **unstrukturierten, wenig strukturierten und strukturierten Daten** bei Initialisierung, Erfassung, Mutation, Auswertung und Löschung.
* Ich kenne den Unterschied zwischen **unerwünschter Redundanz** (Inkonsistenzgefahr) und **erwünschter Redundanz** (Ausfallsicherheit).
* Ich kann unterscheiden, ob ein Merkmal **häufbar** oder **nicht häufbar** ist sowie ob es sich um **diskrete** oder **stetige** Daten handelt.
* Ich kenne die drei Skalentypen (**Nominal-, Ordinal- und Kardinalskala**) und weiss, welche mathematischen Operationen jeweils zulässig sind.
* Ich kann einen strukturierten Fragebogen so aufbauen, dass alle geforderten Merkmal- und Skalentypen gezielt abgedeckt werden.

