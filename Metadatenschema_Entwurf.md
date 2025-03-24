# Offenes Register für wissenschaftliche Auszeichnungen und Preise (ORAP)

## Metadatenschema  
**Februar 2025**  
 

---

## Inhaltsverzeichnis
1. [Einleitung](#einleitung)
2. [Kurzüberblick](#kurzüberblick)
3. [Informationen über jedes Element im Metadatenschema](#informationen-über-jedes-element-im-metadatenschema)
4. [Die einzelnen Felder im Metadatenschema](#die-einzelnen-felder-im-metadatenschema)  
   - [Identifier](#identifier)
   - [Wikidata Identifier](#wikidata-identifier)
   - [Bezeichnung des Preises](#bezeichnung-des-preises)
   - [Sprache der Preisbezeichnung](#sprache-der-preisbezeichnung)
   - [Übersetzungen des Preises](#übersetzungen_des_preises)
   - [Preisverleiher](#preisverleiher)
   - [Kategorie des Preisverleihers](#kategorie_des_preisverleihers) 

---

## Einleitung
Dieses Dokument beschreibt die Metadatenfelder für wissenschaftliche Preise und Auszeichnungen sowie deren Definitionen.  
Das Schema bildet die Grundlage für eine einheitliche Erfassung, Verwaltung und Nutzung von Informationen zu Forschungspreisen.

Es kann genutzt werden, um Forschungspreise systematisch zu erfassen, zu kategorisieren und gezielt zu recherchieren. Darüber hinaus ermöglicht es eine einheitliche Darstellung und erleichtert die Weiterverarbeitung der Daten in unterschiedlichen Kontexten.

Das Schema umfasst **16 speziell entwickelte Felder**, die auf die Anforderungen der Erfassung von Forschungspreisen zugeschnitten sind.

---

## Kurzüberblick

| ID   | Name                           | Attribut | Occurrence | Entitätentyp |
|------|--------------------------------|----------|-----------|--------------|
| 1    | kf_prize_id                    |          | 1         | Identifier   |
| 2    | wikidata_id                     |          | 0-1       | Identifier   |
| 3    | label_sprache_original          |          | 1         | Freitext     |
| 3a   | label_sprache_original_code     | ja       | 1         | Kontrollierte Liste (extern) |
| 4    | preisverleiher                  |          | 1-n       | Freitext     |
| 4a   | preisverleiher_kat              | ja       | 1-n       | Kontrollierte Liste (intern) |
| 4c   | land_verleiher                  | ja       | 1-n       | Kontrollierte Liste (extern) |
| 5    | website_preis                   |          | 1         | Freitext     |
| 6    | art_flts                        |          | 1         | Kontrollierte Liste (intern) |
| 7    | art_preis_ausz                  |          | 1         | Kontrollierte Liste (intern) |
| 11   | frueh_karr                      |          | 1         | Binär: ja; nein |
| 11a  | frueh_karr_zusatz               | ja       | 1-4       | Kontrollierte Liste (intern) |
| 12   | preisgeld                       |          | 1         | Zahl; Keine Angabe; Kein Preisgeld |
| 12a  | preisgeld_waehrung              | ja       | 1         | Kontrollierte Liste (extern): ISO 4217 |
| 13   | einschraenkung_wirkungsstaette  |          | 1         | Kontrollierte Liste (intern) |
| 13.1 | einschraenkung_wirkungsstaette_gebiet |    | 1         | Kontrollierte Liste (extern) |

---

## Informationen über jedes Element im Metadatenschema

| Information      | Beschreibung |
|-----------------|-------------|
| **Element_ID**  | Eindeutiger Identifier für ein Metadatenelement |
| **Name**        | Name des Feldes, wie es in der Liste benutzt wird. |
| **Definition**  | Definition des Metadatenelements |
| **Entitätentyp** | Art des Elements (Binär, Identifier, Kontrollierte Liste, Zahl, Freitext, Datum) |
| **Wert**        | Bestimmt die Syntax des Wertes nach bestimmten Encoding-Schemen (z. B. ISO-Norm) |
| **Occurence**   | Gibt an, wie oft das Element auftauchen kann (1, 1-n, 0-n) |

---

## Die einzelnen Felder im Metadatenschema

### Identifier

| Information         | Beschreibung |
|---------------------|------|
| **Element_ID**      | 1  |
| **Name**           | kf_prize_id |
| **Definition**      | Eindeutiger Identifier für jedes Datum. Dieser Identifier ist eine fortlaufende Zahl. |
| **Entitätentyp**    | Identifier |
| **Wert**           | Zahl (unbegrenzte Ziffernanzahl) |
| **Occurence**      | 1 |

---

### Wikidata Identifier

| Information         | Beschreibung |
|---------------------|------|
| **Element_ID**  | 2  |
| **Name**        | wikidata_id |
| **Definition**  | Eindeutiger Identifier, der von Wikidata kommt. |
| **Entitätentyp** | Identifier |
| **Wert**        | Beginnt mit `Q`, gefolgt von Ziffern (z. B. `Q30328658`, `Q874251`)  |
| **Occurence**   | 0-1  |


#### **Aufnahmeregel für Element ID 2**  
- Bei Aufnahme eines neuen Preises erfolgt ein **Abgleich mit Wikidata**, um zu prüfen, ob es bereits einen entsprechenden Eintrag gibt.
- Falls vorhanden, wird der **Wikidata-Identifier übernommen**.  
- [Wikidata Identifier-Referenz](https://www.wikidata.org/wiki/Wikidata:Identifiers)  

---

### Bezeichnung des Preises

| Information         | Beschreibung |
|---------------------|------|
| **Element_ID**  | 3  |
| **Name**        | label_sprache_original |
| **Definition**  | Bezeichnung des Preises in der Originalsprache. |
| **Entitätentyp** | Freitext |
| **Wert**        | Freitext  |
| **Occurence**   | 1  |

#### **Aufnahmeregel für Element ID 3**
**Name: label_sprache_original**  
Preise werden in ihrer originalsprachigen Bezeichnung aufgenommen. Die Aufnahme erfolgt ohne Artikel. Es kommt vor, dass Preise auf der Webseite unterschiedlich angesetzt werden; es soll die gängigste Ansetzungsform gewählt werden.

---

### Sprache der Preisbezeichnung

| Information         | Beschreibung |
|---------------------|------|
| **Element_ID**  | 3a  |
| **Name**        | label_sprache_original_code |
| **abhängiges Feld** | label_sprache_original |
| **Definition**  | Auszeichnung der Sprache, in der die Preisbezeichnung im Original vorliegt. |
| **Entitätentyp** | Kontrollierte Liste (extern) |
| **Wert**        | Sprachcode nach ISO-639-1  |
| **Occurence**   | 1  |

#### **Aufnahmeregel für Element ID 3a**
**Name: label_sprache_original_code**   
Vergabe des zweistelligen Sprachencodes nach ISO-639-1.

---

### Übersetzungen des Preises

| Information         | Beschreibung |
|---------------------|------|
| **Element_ID**  | 3.1  |
| **Name**        | label_uebersetzung_en |
| **Definition**  | Bezeichnung des Preises übersetzt in die englische Sprache, wenn Feld label_sprache_original_code nicht EN ist. |
| **Entitätentyp** | Freitext |
| **Wert**        | Freitext |
| **Occurence**   | 0-1 |

| Information         | Beschreibung |
|---------------------|------|
| **Element_ID**  | 3.2  |
| **Name**        | label_uebersetzung_de |
| **abhängiges Feld** | label_sprache_de |
| **Definition**  | Bezeichnung des Preises ins Englische übersetzt, wenn Feld label_sprache_original_code nicht DE ist. |
| **Entitätentyp** | Freitext |
| **Wert**        | Freitext |
| **Occurence**   | 0-1 |

#### **Aufnahmeregel für Element ID 3.1 und 3.2**
**Name: label_uebersetzung_en; label_uebersetzung_de**  
Preise werden in ihrer Originalbezeichnung erfasst. Ist die Originalbezeichnung auf Deutsch, wird zusätzlich eine englische Übersetzung eingetragen. Ist die Originalbezeichnung auf Englisch, wird zusätzlich eine deutsche Übersetzung eingetragen. Ist die Originalbezeichnung weder auf Deutsch noch auf Englisch, werden sowohl eine deutsche als auch eine englische Übersetzung eingetragen. Die Aufnahme der Übersetzungen wird den offiziellen Webseiten entnommen. Falls dort keine Übersetzung verfügbar ist, bleiben die entsprechenden Felder leer.

---

### Preisverleiher

| Attribut         | Wert |
|------------------|------|
| **Element ID**   | 4 |
| **Name**         | preisverleiher |
| **Definition**   | Ein Preisverleiher ist eine Organisation, Institution, Stiftung, oder eine Gruppe von Personen und/oder Organisationen, die Preise oder Auszeichnungen für herausragende Leistungen, Entdeckungen oder Beiträge im Bereich der wissenschaftlichen Forschung, der Lehre, des Transfers oder anderen akademischen Bereichen vergibt. |
| **Entitätentyp** | Freitext |
| **Wert**         | Freitext |
| **Occurence**    | 1-n |

**Aufnahmeregel für Element ID 4**  
**Name: `preisverleiher`**  
Ein Preisverleiher wird ohne Artikel in seiner deutschsprachigen Bezeichnung erfasst, sofern diese auf der Website angegeben ist.  
Ist keine deutsche Bezeichnung verfügbar, aber eine englische, wird stattdessen die englische Version aufgenommen.  
Falls weder eine deutsche noch eine englische Bezeichnung vorliegt, wird die Originalbezeichnung verwendet.  
Als Ansetzungsform soll die Version der Website (Impressum, sofern vorhanden) genutzt werden.  
Drittquellen (z. B. Wikidata) sind häufig nicht so aktuell wie die Website.  
Sind mehrere Preisverleiher vorhanden, werden diese durch Semikolon getrennt.

---

### Kategorie des Preisverleihers

| Attribut         | Wert |
|------------------|------|
| **Element ID**   | 4a |
| **Name**         | preisverleiher_kat |
| **Abhängiges Feld** | preisverleiher |
| **Entitätentyp** | Kontrollierte Liste (intern) |
| **Wert**         | wissenschaftlicher Sektor, wirtschaftlicher Sektor, öffentlicher Sektor, Stiftungen, Sonstige |
| **Occurence**    | 1-n (entsprechend der Anzahl der Preisverleiher) |

**Definitionen der Kategorien:**

#### Wissenschaftlicher Sektor
Organisationen, die primär aus dem Bereich der Wissenschaft und Forschung stammen und deren Hauptziel die Förderung des wissenschaftlichen Fortschritts ist:
- Wissenschaftliche Gesellschaften und Fachgesellschaften (z. B. Deutsche Gesellschaft für Psychologie)
- Akademien (z. B. Deutsche Akademie der Naturforscher Leopoldina)
- Universitäten und Hochschulen (z. B. Technische Universität München)
- Forschungsinstitute (z. B. Max-Planck-Institute, Fraunhofer-Institute)
- Forschungsförderungsorganisationen (z. B. Deutsche Forschungsgemeinschaft)
- Stiftungen mit Fokus auf Wissenschaft (z. B. Alexander von Humboldt-Stiftung)
- Wissenschaftsverlage und Fachzeitschriften (z. B. Springer Nature)

#### Wirtschaftlicher Sektor
Organisationen der Privatwirtschaft mit dem Ziel wirtschaftlichen Erfolgs und der Förderung unternehmerischer Interessen:
- Unternehmen (z. B. Siemens)
- Industrieverbände (z. B. Verband der Chemischen Industrie)

#### Öffentlicher Sektor
Staatliche und supranationale Organisationen mit öffentlichen Aufgaben:
- Bundes- und Landesbehörden (z. B. BMBF)
- Supranationale Organisationen (z. B. Europäische Kommission)

#### Stiftungen
Organisationen mit gemeinnützigem Zweck (außerhalb von Wissenschaft), z. B. in den Bereichen:
- Kultur
- Soziales
- Gesundheit
- Umwelt  
Stiftungen mit Wissenschaftsbezug zählen zum „wissenschaftlichen Sektor“.

#### Sonstige
Organisationen, die keiner der oben genannten Kategorien zugeordnet werden können, z. B.:
- Berufsorganisationen

**Aufnahmeregel für Element ID 4a**  
**Name: `preisverleiher_kat`**  
Jeder Preisverleiher wird einer der oben genannten Kategorien zugeordnet.  
Liegen mehrere Preisverleiher vor, erfolgt die Aufnahme der Kategorien in der Reihenfolge, wie sie im Feld `preisverleiher` erscheinen.  
Kategorien für mehrere Preisverleiher werden durch Semikolon getrennt.

---







