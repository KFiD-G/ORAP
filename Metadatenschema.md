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
   - [Kategorie des Preisverleihers](#kategorie-des-preisverleihers)
   - [Land des Verleihers](#land-des-verleihers)
   - [Webseite der Beschreibung](#webseite-der-beschreibung)
   - [Gegenstand des Preises](#gegenstand-des-preises)
   - [Art des wissenschaftlichen Preises / Art der wissenschaftlichen Auszeichnung](#Art-des-wissenschaftlichen-Preises-/-Art-der-wissenschaftlichen-Auszeichnung)
   - [Preis für Personen in einem frühen Karrierestadium](#preis-für-personen-in-einem-frühen-karrierestadium)
   - [Dotierung eines Preises](#Dotierung-eines-Preises)
   - [Preisgeld – Währung](#Preisgeld-/-Währung)
   - [Einschränkungen bezüglich der Wirkungsstätte](#Einschränkungen-bezüglich-der-Wirkungsstätte)
   - [Einschränkungen – geografische Gebiete](#Einschränkungen-/-geografische-Gebiete)
   - [Nominierung](#Nominierung)
   - [Laufzeit eines Preises](#Laufzeit-eines-Preises) 

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
| 1    | [kf_prize_id](#identifier)                    |          | 1         | Identifier   |
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

### Land des Verleihers

| Attribut            | Wert                                                   |
|---------------------|--------------------------------------------------------|
| **Element ID**      | 4c                                                     |
| **Name**            | land_verleiher                                         |
| **Abhängiges Feld** | preisverleiher                                         |
| **Definition**      | Land, in dem der Verleiher des Preises ansässig ist oder seinen Hauptsitz hat. |
| **Entitätentyp**    | Kontrollierte Liste (extern)                           |
| **Wert**            | Ländercode nach ISO-3166-2 (ALPHA-2)                   |
| **Occurence**       | 1-n (entsprechend der Anzahl der Preisverleiher)       |

**Aufnahmeregel für Element ID 4c**

Das Land des Verleihers entspricht dem Land, in dem die Organisation ihren Hauptsitz hat.  
Das Land kann in der Regel im Impressum der Website des Verleihers recherchiert werden.  
Hat der Verleiher mehrere Standorte, wird das Land des Hauptsitzes der Organisation eingetragen.  
Mehrere Werte werden mit Semikolon getrennt.

---

### Webseite der Beschreibung

| Attribut         | Wert |
|------------------|------|
| **Element ID**   | 5 |
| **Name**         | website_preis |
| **Definition**   | URL einer Website, die vom Preisverleiher betrieben wird und auf welcher der Preis beschrieben ist. |
| **Entitätentyp** | Freitext |
| **Wert**         | URL der Subdomain, des Ordners oder der Website, auf der der Preis beschrieben ist; Eintragung der URL mit http://www… oder https://www… |
| **Occurence**    | 1 |

**Aufnahmeregel für Element ID 5**

**Vollständige URL:**  
Die URL der Website des Preises wird vollständig und inklusive aller relevanten Bestandteile (z. B. Protokoll, Domain, Subdomain, Unterordner) aufgenommen.  
Beispiel: `https://www.nobelprize.org/prizes/chemistry/`

**Preis mit eigener Domain, Subdomain oder Unterordner:**  
Wenn der Preis eine eigene Domain, Subdomain oder einen spezifischen Unterordner hat, wird diese vollständige URL aufgenommen.  
Beispiel: `https://www.luther-gesellschaft.de/martin-luther-preis.html`

**Mehrere Webseiten:**  
Wenn der Preis auf mehreren Webseiten beschrieben wird, wird die Hauptseite aufgenommen, die den Preis allgemein beschreibt.  
Unterseiten, die z. B. nur Preisträger*innen oder Details auflisten, werden nicht eingetragen.  
Beispiel:  
✔ `https://www.luther-gesellschaft.de/martin-luther-preis.html`  
✘ `https://www.luther-gesellschaft.de/martin-luther-preis/preistraeger.html`

**Keine URL verfügbar:**  
Ist keine spezifische URL für den Preis vorhanden, wird keine Sekundärquelle angegeben.  
In diesem Fall bleibt das Feld leer.

---

### Gegenstand des Preises

| Attribut         | Wert |
|------------------|------|
| **Element ID**   | 6 |
| **Name**         | art_flts |
| **Definition**   | Dieses Feld kategorisiert den Gegenstand des Preises und gibt an, ob dieser für Forschung, Lehre, Transfer oder Sonstiges vergeben wurde. |
| **Entitätentyp** | Kontrollierte Liste (intern) |
| **Wert**         | Forschung; Lehre; Transfer; Sonstiges |
| **Occurence**    | 1 |

**Definitionen der Werte:**

**Forschung:**  
Ein Preis mit dem Gegenstand „Forschung“ wird als Anerkennung für herausragende oder wegweisende Forschungsergebnisse vergeben.  
Diese Arbeiten müssen einen bedeutenden Beitrag zur Erweiterung des Wissens im jeweiligen Fachgebiet leisten.  
Kriterien: Innovationsgrad, wissenschaftliche Qualität, Relevanz und Originalität, Publikation in anerkannten Journalen, Anerkennung durch Fachgemeinschaft.

**Lehre:**  
Ein Preis mit dem Gegenstand „Lehre“ würdigt herausragende Leistungen in der akademischen Lehre.  
Kriterien: Innovation der Lehrmethoden, didaktische Qualität, Förderung kritischen Denkens, Studierendenrückmeldungen, Einfluss auf Lehrkultur.

**Transfer:**  
Ein Preis mit dem Gegenstand „Transfer“ würdigt die Übertragung wissenschaftlicher Erkenntnisse in Gesellschaft und Wirtschaft.  
Kriterien: Umsetzung von Forschung in Produkte/Dienstleistungen, Wissenschaftskommunikation, Reichweite, Relevanz, Innovation, Nachhaltigkeit.

**Sonstiges:**  
Ein Preis, der keiner der Kategorien Forschung, Lehre oder Transfer eindeutig zugeordnet werden kann.  
Bezieht sich z. B. auf Kunstpreise oder andere fachfremde Bereiche.

### Aufnahmeregeln für Element ID 6 und 6a

**Name:** `art_flts` und `art_flts_sonstiges`

- **Eindeutige Zuordnung:**  
  Jeder Preis darf nur einer Kategorie zugeordnet werden: Forschung, Lehre, Transfer oder Sonstiges.

- **Mehrfachzuordnung:**  
  Wenn mehrere Kategorien zutreffen, wird diejenige gewählt, auf die der Preis am stärksten zutrifft.

- **Unklare Zuordnung:**  
  Ist keine eindeutige Kategorie erkennbar und deckt der Preis mehrere Bereiche ab, wird standardmäßig „Forschung“ gewählt.

- **Kein Bezug zu den Hauptkategorien:**  
  Wenn keine der drei Hauptkategorien zutrifft, wird „Sonstiges“ verwendet.  
  Dann ist ein erläuternder Eintrag im Feld `art_flts_sonstiges` erforderlich.

---

### Art des wissenschaftlichen Preises / Art der wissenschaftlichen Auszeichnung

| Attribut         | Wert |
|------------------|------|
| **Element ID**   | 7 |
| **Name**         | art_preis_ausz |
| **Definition**   | Dieses Metadatum legt fest, ob es sich um einen wissenschaftlichen Preis oder um eine wissenschaftliche Auszeichnung handelt. |
| **Entitätentyp** | Kontrollierte Liste (intern) |
| **Wert**         | Wissenschaftlicher Preis; Wissenschaftliche Auszeichnung |
| **Occurence**    | 1 |

**Definition der Werte:**

**Wissenschaftlicher Preis:**  
Ein wissenschaftlicher Preis zeichnet erfolgte wissenschaftliche Leistungen in den Bereichen Forschung, Lehre, Transfer oder Sonstiges aus.  
Er ist meist mit einer Geldprämie, Urkunde oder Medaille verbunden, aber ohne weiterführende Verpflichtungen für die Preisträger*innen.  
Auch Projektförderungen können dazugehören, sofern sie nicht an eine Bewerbung mit Projektbeschreibung geknüpft sind.

**Wissenschaftliche Auszeichnung:**  
Eine wissenschaftliche Auszeichnung würdigt außergewöhnliche Beiträge im akademischen Bereich, oft verbunden mit spezifischen Verpflichtungen.  
Beispiele: Ehrendoktorwürde, Ehrenprofessur, Aufnahme in eine Akademie oder Gesellschaft.  
Projektförderungen wie ERC-Grants gelten nur dann als Auszeichnung, wenn sie besonders prestigeträchtig sind.

---

### Preis für Personen in einem frühen Karrierestadium

| Attribut         | Wert |
|------------------|------|
| **Element ID**   | 11 |
| **Name**         | frueh_karr |
| **Definition**   | Preise und Auszeichnungen für Personen in einem frühen Karrierestadium werden an Wissenschaftler:innen vergeben, die sich in einer Qualifizierungs-, Aufbau- oder Bewährungsphase für den Verbleib in der Wissenschaft befinden. Dazu zählen auch Preise und Auszeichnungen, die an Personen unterhalb eines bestimmten Höchstalters verliehen werden oder ausschließlich Leistungen im Rahmen von Qualifikationsarbeiten würdigen, die vor wenigen Jahren abgeschlossen wurden. Häufig wird der spezielle Adressat*innenkreis bereits im Namen des Preises oder der Auszeichnung angegeben. |
| **Entitätentyp** | Binär |
| **Wert**         | ja; nein |
| **Occurence**    | 1 |

---

### Dotierung eines Preises

| Attribut         | Wert |
|------------------|------|
| **Element ID**   | 12 |
| **Name**         | preisgeld |
| **Definition**   | Angabe zur Höhe des Preisgeldes |
| **Entitätentyp** | Zahl größer 0 und zwei weitere festgeschriebene Werte |
| **Wert**         | positive ganze Zahl oder „Keine Angabe“ oder „Kein Preisgeld“ |
| **Occurence**    | 1 |

#### Aufnahmeregel für Element ID 12

- **Höchste Dotierung:**  
  Es wird immer das höchste Preisgeld eingetragen, auch wenn es für weitere Plätze geringere Dotierungen gibt.  
  Besteht der Preis aus mehreren Kategorien mit verschiedenen Dotierungen, wird die höchste aufgenommen. In diesem Fall wird im Feld `preisgeld_zusatz` der Zusatz „bis zu“ ergänzt.

- **Kein Preisgeld:**  
  Wird explizit kein Preisgeld vergeben oder nur eine symbolische Anerkennung (z. B. Urkunde, Medaille), wird „Kein Preisgeld“ eingetragen.

- **Fehlende Angaben:**  
  Wenn keine Information zur Dotierung vorliegt, wird „Keine Angabe“ eingetragen.

- **Nur Preisgeld erfassen:**  
  Nur die Höhe des Preisgeldes wird erfasst. Weitere finanzielle Leistungen (z. B. Reisekosten, Pauschalen) werden **nicht** mitgerechnet.  
  Diese können im Feld `preisgeld_zusatz` dokumentiert werden, z. B.:  
  `Reisekostenzuschuss; Druckkostenzuschuss`

---

### Preisgeld – Währung

| Attribut         | Wert |
|------------------|------|
| **Element ID**   | 12a |
| **Name**         | preisgeld_waehrung |
| **Abhängiges Feld** | preisgeld |
| **Definition**   | Währung des Landes, in welchem der Preis vergeben wird. |
| **Entitätentyp** | Kontrollierte Liste (extern) |
| **Wert**         | Währungsangabe nach ISO 4217:2015 (z. B. USD für US-Dollar), „Keine Angabe“, „Kein Preisgeld“ |
| **Occurence**    | 1 |

---

### Einschränkungen bezüglich der Wirkungsstätte

| Attribut         | Wert |
|------------------|------|
| **Element ID**   | 13 |
| **Name**         | einschraenkung_wirkungsstaette |
| **Definition**   | Gibt an, ob bei der Vergabe eines Preises Einschränkungen hinsichtlich der Ansässigkeit oder Wirkungsstätte bestehen. |
| **Entitätentyp** | Kontrollierte Liste (intern) |
| **Wert**         | Einrichtungs- oder organisationsgebunden; DACH; International; Keine Einschränkung; Sonstiges; Keine Angabe |
| **Occurence**    | 1 |

**Definitionen der Werte:**

- **Einrichtungs- oder organisationsgebunden:**  
  Der Preis ist nur für Personen vorgesehen, die einer bestimmten Einrichtung oder Organisation angehören.

- **DACH:**  
  Der Preis richtet sich an Personen in Deutschland, Österreich und/oder der Schweiz.

- **International:**  
  Der Preis ist für Personen in bestimmten Ländern oder Regionen vorgesehen. Mehrere Länder können genannt werden.

- **Keine Einschränkung:**  
  Es gibt keine geografischen Einschränkungen.

- **Sonstiges:**  
  Es liegt eine andere Form der Einschränkung vor.

- **Keine Angabe:**  
  Es liegen keine Angaben zur Einschränkung vor.

---

### Einschränkungen – geografische Gebiete

| Attribut         | Wert |
|------------------|------|
| **Element ID**   | 13.1 |
| **Name**         | einschraenkung_wirkungsstaette_gebiet |
| **Definition**   | Länder, Regionen oder Orte, in denen die Wirkungsstätte liegen muss. |
| **Entitätentyp** | Freitext |
| **Wert**         | Ortsangaben gemäß GeoNames, z. B. „Deutschland, Bayern, München“ |
| **Occurence**    | 1 |

#### Aufnahmeregeln für Element ID 13 und 13.1

- **Hierarchische Struktur geografischer Angaben:**  
  Gebiete werden vom Allgemeinen zum Spezifischen angegeben und durch Kommas getrennt.  
  *Beispiel:* `Deutschland, Hessen, Frankfurt`

- **Gleichrangige geografische Einheiten:**  
  Werden durch ein Semikolon getrennt.  
  *Beispiel:* `Deutschland; Frankreich; Irland`

- **Mehrere geografische Bezüge:**  
  Werden jeweils in einer neuen Zeile angegeben, beginnend mit dem größten Bezug.  
  *Beispiel:*  
  ```
  Deutschland, Hessen, Frankfurt  
  Deutschland, Brandenburg, Potsdam
  ```
  (nicht: `Deutschland, Hessen, Brandenburg, Frankfurt, Potsdam`)

- **Allgemeine geografische Begriffe:**  
  Begriffe wie „Schwellenländer“, „globale Südregionen“, „Lateinamerika“ oder „osteuropäische Länder“ dürfen direkt eingetragen werden.

- **Keine Angabe vorhanden:**  
  Wenn keine geografische Einschränkung bekannt ist, wird „Keine Angabe“ eingetragen.

#### Besondere Hinweise bei „Einrichtungs- oder organisationsgebunden“

Wenn dieses Kriterium ausgewählt wird, ist zusätzlich das Feld `einschraenkung_wirkungsstaette_selbstbezeichnung` verpflichtend auszufüllen.

#### Mögliche Fälle:

1. **Gebunden an eine konkrete Einrichtung in einem bestimmten Ort:**  
   - `einschraenkung_wirkungsstaette_gebiet`: `Deutschland, Baden-Württemberg, Freiburg`  
   - `einschraenkung_wirkungsstaette_selbstbezeichnung`: `Universität Freiburg`

2. **Gebunden an eine Organisation, aber ohne geografische Einschränkung:**  
   - `einschraenkung_wirkungsstaette_gebiet`: `Keine Angabe`  
   - `einschraenkung_wirkungsstaette_selbstbezeichnung`: Name der Organisation

3. **Gebunden an internationale Mitgliedschaft mit weltweiter Bewerbung:**  
   - `einschraenkung_wirkungsstaette_gebiet`: `international`  
   - `einschraenkung_wirkungsstaette_selbstbezeichnung`: Name der Organisation

> 🔎 Die Angaben in den Feldern `einschraenkung_wirkungsstaette`, `einschraenkung_wirkungsstaette_gebiet` und `einschraenkung_wirkungsstaette_selbstbezeichnung` müssen logisch und nachvollziehbar zusammenpassen.

---

### Nominierung

| Attribut         | Wert |
|------------------|------|
| **Element ID**   | 15 |
| **Name**         | nominierung |
| **Definition**   | Gibt an, ob Eigenbewerbungen möglich sind und/oder wer nominieren darf. |
| **Entitätentyp** | Kontrollierte Liste (intern) |
| **Wert**         | Eigenbewerbung und Nominierung; Eigenbewerbung; Nominierung offen; Nominierung eingeschränkt; Nominierung Einrichtung / Gremium; Keine Angabe |
| **Occurence**    | 1 |

#### Definitionen der Werte:

- **Eigenbewerbung und Nominierung**  
  Sowohl Eigenbewerbungen als auch Nominierungen sind erlaubt – ohne Einschränkung hinsichtlich der nominierenden Person.

- **Eigenbewerbung**  
  Nur Eigenbewerbungen sind möglich. Eine Nominierung durch Dritte ist nicht erforderlich.

- **Nominierung offen**  
  Kandidat*innen können von beliebigen Personen oder Einrichtungen vorgeschlagen werden (z. B. Wissenschaftler*innen, Universitäten).  
  Eigenbewerbungen sind **nicht** erlaubt.

- **Nominierung eingeschränkt**  
  Nur bestimmte Personen oder Gruppen dürfen nominieren (z. B. frühere Preisträger*innen, Mitglieder bestimmter Fachgesellschaften).

- **Nominierung Einrichtung / Gremium**  
  Nur institutionelle Nominierungen sind zulässig (z. B. durch Universitäten oder Auswahlgremien).  
  Die Nominierung selbst stellt bereits eine Form der Auszeichnung dar.

- **Keine Angabe**  
  Es liegen keine öffentlich zugänglichen Informationen zur Nominierung vor.

#### Aufnahmeregel für Element ID 15

Die Abgrenzung zwischen „Nominierung eingeschränkt“ und „Nominierung Einrichtung / Gremium“ ist nicht immer eindeutig:

- Wenn nur Mitglieder der verleihenden Organisation nominieren dürfen → **„Nominierung eingeschränkt“**
- Wenn ausschließlich eine bestimmte Einrichtung oder ein offizielles Gremium nominieren darf → **„Nominierung Einrichtung / Gremium“**

Wenn sowohl Eigenbewerbungen als auch Nominierungen erlaubt sind, auch wenn nur bestimmte Personen nominieren dürfen, wird **„Eigenbewerbung und Nominierung“** verwendet.

---

### Laufzeit eines Preises

| Attribut         | Wert |
|------------------|------|
| **Element ID**   | 16 |
| **Name**         | laufzeit_beginn |
| **Definition**   | Gibt das Jahr an, in dem der Preis erstmals verliehen wurde. |
| **Entitätentyp** | Zahl |
| **Wert**         | JJJJ |
| **Occurence**    | 0-1 |

---

| Attribut         | Wert |
|------------------|------|
| **Element ID**   | 17 |
| **Name**         | laufzeit_ende |
| **Definition**   | Gibt das Jahr an, in dem der Preis letztmalig verliehen wurde. |
| **Entitätentyp** | Zahl |
| **Wert**         | JJJJ |
| **Occurence**    | 0-1 |

---






















