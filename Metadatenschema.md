# Offenes Register für Auszeichnungen und Preise (ORAP)

## Metadatenschema  
 
---

## Einleitung
Dieses Dokument beschreibt die Metadatenfelder für wissenschaftliche Preise und Auszeichnungen sowie deren Definitionen.  
Das Schema bildet die Grundlage für eine einheitliche Erfassung, Verwaltung und Nutzung von Informationen zu Preisen.

Es kann genutzt werden, um Preise systematisch zu erfassen, zu kategorisieren und gezielt zu recherchieren. Darüber hinaus ermöglicht es eine einheitliche Darstellung und erleichtert die Weiterverarbeitung der Daten in unterschiedlichen Kontexten.

Das Schema umfasst **22 speziell entwickelte Felder**, die auf die Anforderungen der Erfassung von Preisen zugeschnitten sind.

---
<a name="top"></a>
## Kurzüberblick

| ID   | Name                           | Occurrence | Entitätentyp |
|------|--------------------------------|-----------|--------------|
| 1    | [Identifier](#identifier)                    | 1         | Identifier   |
| 2    | [Wikidata Identifier](#wikidata-identifier)                     | 0-1       | Identifier   |
| 3    | [Bezeichnung des Preises](#bezeichnung-des-preises)          | 1         | Freitext     |
| 3a   | [Sprache der Preisbezeichnung](#sprache-der-preisbezeichnung)     | 1         | Kontrollierte Liste (extern) |
| 3.1   | [Übersetzungen des Preises (EN)](#Übersetzungen-des-Preises)     | 0-1         | Freitext |
| 3.2   | [Übersetzungen des Preises (DE)](#Übersetzungen-des-Preises)     | 0-1         | Freitext |
| 3.1a  | [Provenienzfeld Preis (EN)](#provenienzfelder-für-preisbezeichnungen)     | 0-1        | Freitext                |
| 3.2a  | [Provenienzfeld Preis (DE)](#provenienzfelder-für-preisbezeichnungen)     | 0-1        | Freitext                |
| 4    | [Preisverleiher](#preisverleiher)                  | 1-n       | Freitext     |
| 4a   | [Kategorie des Preisverleihers](#kategorie-des-preisverleihers)              | 1-n       | Kontrollierte Liste |
| 4c   | [Land des Verleihers](#land-des-verleihers)                  | 1-n       | Kontrollierte Liste (extern) |
| 5    | [Webseite](#webseite-der-beschreibung)                   | 1         | Freitext     |
| 6    | [Gegenstand des Preises](#gegenstand-des-preises)                        | 1         | Kontrollierte Liste |
| 7    | [Art des Preises](#Art-des-Preises-oder-der-Auszeichnung)                  | 1         | Kontrollierte Liste |
| 11   | [Frühes Karrierestadium](#preis-für-personen-in-einem-frühen-karrierestadium)                      | 1         | Binär: ja; nein |
| 12   | [Preisgeld](#Dotierung-eines-Preises)                       | 1         | Zahl; Keine Angabe; Kein Preisgeld |
| 12a  | [Währung des Preisgeldes](#preisgeld--währung)              | 1         | Kontrollierte Liste (extern): ISO 4217 |
| 13   | [Einschränkungen bezüglich der Wirkungsstätte](#Einschränkungen-bezüglich-der-Wirkungsstätte)  | 1         | Kontrollierte Liste |
| 13.1 | [Einschränkungen – geografische Gebiete](#Einschränkungen--geografische-Gebiete) | 1         | Kontrollierte Liste (extern) |
| 15 | [Nominierung](#nominierung) | 0-1         | Kontrollierte Liste |
| 16 | [Laufzeitbeginn eines Preises](#Laufzeit-eines-Preises) | 0-1         | Jahr (JJJJ) |
| 17 | [Laufzeitende eines Preises](#Laufzeit-eines-Preises) | 0-1         | Jahr (JJJJ) |

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

[🔝](#top)

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

[🔝](#top)

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

[🔝](#top)

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

[🔝](#top)

---

### Übersetzungen des Preises

| Information         | Beschreibung |
|---------------------|------|
| **Element_ID**  | 3.1  |
| **Name**        | label_uebersetzung_en |
| **Definition**  | Bezeichnung des Preises ins Englische übersetzt, sofern die Originalsprache nicht Englisch ist. |
| **Entitätentyp** | Freitext |
| **Wert**        | Freitext |
| **Occurence**   | 0-1 |

| Information         | Beschreibung |
|---------------------|------|
| **Element_ID**  | 3.2  |
| **Name**        | label_uebersetzung_de |
| **abhängiges Feld** | label_sprache_de |
| **Definition**  | Bezeichnung des Preises ins Deutsche übersetzt, sofern die Originalsprache nicht Deutsch ist. |
| **Entitätentyp** | Freitext |
| **Wert**        | Freitext |
| **Occurence**   | 0-1 |

[🔝](#top)

#### **Aufnahmeregel für Element ID 3.1 und 3.2**
**Name: label_uebersetzung_en; label_uebersetzung_de**  
Preise werden in ihrer Originalbezeichnung erfasst. Ist die Originalbezeichnung auf Deutsch, wird zusätzlich eine englische Übersetzung eingetragen. Ist die Originalbezeichnung auf Englisch, wird zusätzlich eine deutsche Übersetzung eingetragen. Ist die Originalbezeichnung weder auf Deutsch noch auf Englisch, werden sowohl eine deutsche als auch eine englische Übersetzung eingetragen. Die Aufnahme der Übersetzungen wird den offiziellen Webseiten entnommen. Falls dort keine Übersetzung verfügbar ist, wird eine selbsterstellte Übersetzung vom ORAP-Team verwendet.

---

### **Provenienzfelder für Preisbezeichnungen**

| Information        | Beschreibung |
|--------------------|--------------|
| **Element_ID**     | 3.1a         |
| **Name**           | provenienz_uebersetzung_en |
| **Abhängiges Feld**| label_uebersetzung_en |
| **Definition**     | Quelle/Herkunft der englischen Übersetzung der Preisbezeichnung |
| **Entitätentyp**   | Freitext     |
| **Wert**           | Freitext     |
| **Occurence**      | 0-1          |

| Information        | Beschreibung |
|--------------------|--------------|
| **Element_ID**     | 3.2a         |
| **Name**           | provenienz_uebersetzung_de |
| **Abhängiges Feld**| label_uebersetzung_de |
| **Definition**     | Quelle/Herkunft der deutschen Übersetzung der Preisbezeichnung |
| **Entitätentyp**   | Freitext     |
| **Wert**           | Freitext     |
| **Occurence**      | 0-1          |

---

### Preisverleiher

| Information         | Beschreibung |
|------------------|------|
| **Element ID**   | 4 |
| **Name**         | preisverleiher |
| **Definition**   | Ein Preisverleiher ist eine Organisation, Institution, Stiftung, oder eine Gruppe von Personen und/oder Organisationen, die Preise oder Auszeichnungen für herausragende Leistungen, Entdeckungen oder Beiträge im Bereich der wissenschaftlichen Forschung, der Lehre, des Transfers oder anderen akademischen Bereichen vergibt. |
| **Entitätentyp** | Freitext |
| **Wert**         | Freitext |
| **Occurence**    | 1-n |

[🔝](#top)

**Aufnahmeregel für Element ID 4**  
**Name: preisverleiher**  
Preisverleiher werden in ihrer originalsprachigen Bezeichnung aufgenommen. Die Aufnahme erfolgt ohne Artikel. Es kommt vor, dass Verleiher auf der Webseite unterschiedlich angesetzt werden; es soll die gängigste Ansetzungsform gewählt werden.

---

### Kategorie des Preisverleihers

| Information         | Beschreibung |
|------------------|------|
| **Element ID**   | 4a |
| **Name**         | preisverleiher_kat |
| **Abhängiges Feld** | preisverleiher |
| **Entitätentyp** | Kontrollierte Liste |
| **Wert**         | wissenschaftlicher Sektor, wirtschaftlicher Sektor, öffentlicher Sektor, Stiftungen, Sonstige |
| **Occurence**    | 1-n (entsprechend der Anzahl der Preisverleiher) |

[🔝](#top)

**Definitionen der Kategorien:**

#### Wissenschaftlicher Sektor
Organisationen, die primär aus dem Bereich der Wissenschaft und Forschung stammen und deren Hauptziel die Förderung des wissenschaftlichen Fortschritts ist:
- Wissenschaftliche Gesellschaften und Fachgesellschaften (z. B. Deutsche Gesellschaft für Psychologie)
- Akademien (z. B. Deutsche Akademie der Naturforscher Leopoldina)
- Universitäten und Hochschulen (z. B. Technische Universität München)
- Forschungsinstitute (z. B. Max-Planck-Institute, Fraunhofer-Institute)
- Forschungsförderungsorganisationen (z. B. Deutsche Forschungsgemeinschaft)
- Stiftungen mit Fokus auf Wissenschaft (z. B. Alexander von Humboldt-Stiftung)
- Fachzeitschriften (z. B. European Journal of Immunology)

#### Wirtschaftlicher Sektor
Organisationen der Privatwirtschaft mit dem Ziel wirtschaftlichen Erfolgs und der Förderung unternehmerischer Interessen:
- Unternehmen (z. B. Siemens)
- Industrieverbände (z. B. Verband der Chemischen Industrie)
- Wissenschaftsverlage (z. B. Springer Medizin)

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

| Information            | Beschreibung                                                   |
|---------------------|--------------------------------------------------------|
| **Element ID**      | 4c                                                     |
| **Name**            | land_verleiher                                         |
| **Abhängiges Feld** | preisverleiher                                         |
| **Definition**      | Land, in dem der Verleiher des Preises ansässig ist oder seinen Hauptsitz hat. |
| **Entitätentyp**    | Kontrollierte Liste (extern)                           |
| **Wert**            | Ländercode nach ISO-3166-2 (ALPHA-2)                   |
| **Occurence**       | 1-n (entsprechend der Anzahl der Preisverleiher)       |

[🔝](#top)

**Aufnahmeregel für Element ID 4c**

Das Land des Verleihers entspricht dem Land, in dem die Organisation ihren Hauptsitz hat.  
Das Land kann in der Regel im Impressum der Website des Verleihers recherchiert werden.  
Hat der Verleiher mehrere Standorte, wird das Land des Hauptsitzes der Organisation eingetragen.  
Mehrere Werte werden mit Semikolon getrennt.

---

### Webseite der Beschreibung

| Information         | Beschreibung |
|------------------|------|
| **Element ID**   | 5 |
| **Name**         | website_preis |
| **Definition**   | URL einer Website, die vom Preisverleiher betrieben wird und auf welcher der Preis beschrieben ist. |
| **Entitätentyp** | Freitext |
| **Wert**         | URL der Subdomain, des Ordners oder der Website, auf der der Preis beschrieben ist; Eintragung der URL mit http://www… oder https://www… |
| **Occurence**    | 1 |

[🔝](#top)

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

| Information         | Beschreibung |
|------------------|------|
| **Element ID**   | 6 |
| **Name**         | art_flts |
| **Definition**   | Dieses Feld kategorisiert den Gegenstand des Preises und gibt an, ob dieser für Forschung, Lehre, Transfer oder Sonstiges vergeben wurde. |
| **Entitätentyp** | Kontrollierte Liste |
| **Wert**         | Forschung; Lehre; Transfer; Sonstiges |
| **Occurence**    | 1 |

[🔝](#top)

**Definitionen der Werte:**

**Forschung:**  
Ein Preis mit dem Gegenstand „Forschung“ wird als Anerkennung für herausragende oder wegweisende Forschungsergebnisse vergeben.  

**Lehre:**  
Ein Preis mit dem Gegenstand “Lehre” ist eine Anerkennung für herausragende Leistungen in der Lehre im akademischen Kontext.

**Transfer:**  
Ein Preis mit dem Gegenstand “Transfer” würdigt die erfolgreiche Übertragung wissenschaftlicher Erkenntnisse aus dem akademischen Umfeld in die Gesellschaft und Wirtschaft. Er ehrt Leistungen, die sich in der Umsetzung von Forschungsergebnissen in innovative Produkte, Dienstleistungen oder Technologien manifestieren, die Vermittlung von wissenschaftlichem Wissen an die breite Öffentlichkeit fördern und den Dialog zwischen Wissenschaft und Gesellschaft stärken.

**Sonstiges:**  
Ein Preis mit der Kategorie “Sonstiges” fällt in keine der anderen Kategorien, auch nicht in Anteilen. Preise, die nicht Forschung, Lehre oder Transfer zugeordnet werden können, bekommen die Kategorie Sonstiges. Preise, die Anteile an den Kategorien Forschung, Lehre oder Transfer haben, sollen nach den jeweiligen Kategorien aufgenommen werden, wo der Anteil am größten ist. Die Kategorie “Sonstiges” ist für Preise, die eindeutig keine der Kategorien Forschung, Lehre oder Transfer bedienen, sondern, z.B. Kunst.

### Aufnahmeregeln für Element ID 6 und 6a

**Name:** `art_flts`

- **Eindeutige Zuordnung:**  
  Jeder Preis darf nur einer Kategorie zugeordnet werden: Forschung, Lehre, Transfer oder Sonstiges.

- **Mehrfachzuordnung:**  
  Wenn mehrere Kategorien zutreffen, wird diejenige gewählt, auf die der Preis am stärksten zutrifft.

- **Unklare Zuordnung:**  
  Ist keine eindeutige Kategorie erkennbar und deckt der Preis mehrere Bereiche ab, wird standardmäßig „Forschung“ gewählt.

- **Kein Bezug zu den Hauptkategorien:**  
  Wenn keine der drei Hauptkategorien zutrifft, wird „Sonstiges“ verwendet.  

---

### Art des Preises oder der Auszeichnung

| Information         | Beschreibung |
|------------------|------|
| **Element ID**   | 7 |
| **Name**         | art_preis_ausz |
| **Definition**   | Dieses Metadatum legt fest, ob es sich um einen wissenschaftlichen Preis oder um eine wissenschaftliche Auszeichnung handelt. |
| **Entitätentyp** | Kontrollierte Liste |
| **Wert**         | Wissenschaftlicher Preis; Wissenschaftliche Auszeichnung; Akademiemitgliedschaft |
| **Occurence**    | 1 |

[🔝](#top)

**Definition der Werte:**

**Wissenschaftlicher Preis:**  
Ein wissenschaftlicher Preis zeichnet erfolgte wissenschaftliche Leistungen in den Bereichen Forschung, Lehre, Transfer oder Sonstiges aus.  
Er ist meist mit einer Geldprämie, Urkunde oder Medaille verbunden, aber ohne weiterführende Verpflichtungen für die Preisträger*innen.  
Auch Projektförderungen können dazugehören, sofern sie nicht an eine Bewerbung mit Projektbeschreibung geknüpft sind.

**Wissenschaftliche Auszeichnung:**  
Eine wissenschaftliche Auszeichnung würdigt außergewöhnliche Beiträge im akademischen Bereich, oft verbunden mit spezifischen Verpflichtungen.  
Beispiele: Ehrendoktorwürde, Ehrenprofessur, Aufnahme in eine Fachgesellschaft.  
Projektförderungen wie ERC-Grants gelten nur dann als Auszeichnung, wenn sie besonders prestigeträchtig sind.

**Akademiemitgliedschaft:**  
Eine Akademiemitgliedschaft ist die dauerhafte Aufnahme in eine [Akademie der Wissenschaften](https://de.wikipedia.org/wiki/Akademie_der_Wissenschaften), die auf Grundlage besonderer wissenschaftlicher Leistungen erfolgt.   
Zum Beispiel in die Deutsche Akademie der Naturforscher Leopoldina – Nationale Akademie der Wissenschaften.


---

### Preis für Personen in einem frühen Karrierestadium

| Information         | Beschreibung |
|------------------|------|
| **Element ID**   | 11 |
| **Name**         | frueh_karr |
| **Definition**   | Preise und Auszeichnungen für Personen in einem frühen Karrierestadium werden an Wissenschaftler:innen vergeben, die sich in einer Qualifizierungs-, Aufbau- oder Bewährungsphase für den Verbleib in der Wissenschaft befinden. Dazu zählen auch Preise und Auszeichnungen, die an Personen unterhalb eines bestimmten Höchstalters verliehen werden oder ausschließlich Leistungen im Rahmen von Qualifikationsarbeiten würdigen, die vor wenigen Jahren abgeschlossen wurden. Häufig wird der spezielle Adressat*innenkreis bereits im Namen des Preises oder der Auszeichnung angegeben. |
| **Entitätentyp** | Binär |
| **Wert**         | ja; nein |
| **Occurence**    | 1 |

[🔝](#top)

---

### Dotierung eines Preises

| Information         | Beschreibung |
|------------------|------|
| **Element ID**   | 12 |
| **Name**         | preisgeld |
| **Definition**   | Angabe zur Höhe des Preisgeldes |
| **Entitätentyp** | Zahl größer 0 und zwei weitere festgeschriebene Werte |
| **Wert**         | positive ganze Zahl oder „Keine Angabe“ oder „Kein Preisgeld“ |
| **Occurence**    | 1 |

[🔝](#top)

#### Aufnahmeregel für Element ID 12

- **Höchste Dotierung:**  
  Es wird immer das höchste Preisgeld eingetragen, auch wenn es für weitere Plätze geringere Dotierungen gibt.  
  Besteht der Preis aus mehreren Kategorien mit verschiedenen Dotierungen, wird die höchste aufgenommen.

- **Kein Preisgeld:**  
  Wird explizit kein Preisgeld vergeben oder nur eine symbolische Anerkennung (z. B. Urkunde, Medaille), wird „Kein Preisgeld“ eingetragen.

- **Fehlende Angaben:**  
  Wenn keine Information zur Dotierung vorliegt, wird „Keine Angabe“ eingetragen.

- **Nur Preisgeld erfassen:**  
  Nur die Höhe des Preisgeldes wird erfasst. Weitere finanzielle Leistungen (z. B. Reisekosten, Pauschalen) werden **nicht** mitgerechnet.  

---

### Preisgeld – Währung

| Information         | Beschreibung |
|------------------|------|
| **Element ID**   | 12a |
| **Name**         | preisgeld_waehrung |
| **Abhängiges Feld** | preisgeld |
| **Definition**   | Währung des Landes, in welchem der Preis vergeben wird. |
| **Entitätentyp** | Kontrollierte Liste (extern) |
| **Wert**         | Währungsangabe nach ISO 4217:2015 (z. B. USD für US-Dollar), „Keine Angabe“, „Kein Preisgeld“ |
| **Occurence**    | 1 |

[🔝](#top)

---

### Einschränkungen bezüglich der Wirkungsstätte

| Information         | Beschreibung |
|------------------|------|
| **Element ID**   | 13 |
| **Name**         | einschraenkung_wirkungsstaette |
| **Definition**   | Gibt an, ob bei der Vergabe eines Preises Einschränkungen hinsichtlich der Ansässigkeit oder Wirkungsstätte bestehen. |
| **Entitätentyp** | Kontrollierte Liste |
| **Wert**         | Einrichtungs- oder organisationsgebunden; DACH; International; Keine Einschränkung; Sonstiges; Keine Angabe |
| **Occurence**    | 1 |

[🔝](#top)

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

| Information         | Beschreibung |
|------------------|------|
| **Element ID**   | 13.1 |
| **Name**         | einschraenkung_wirkungsstaette_gebiet |
| **Definition**   | Länder, Regionen oder Orte, in denen die Wirkungsstätte liegen muss. |
| **Entitätentyp** | Freitext |
| **Wert**         | Ortsangaben gemäß GeoNames, z. B. „Deutschland, Bayern, München“ |
| **Occurence**    | 1 |

[🔝](#top)

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


#### Mögliche Fälle:

1. **Gebunden an eine konkrete Einrichtung in einem bestimmten Ort:**  
   - `einschraenkung_wirkungsstaette_gebiet`: `Deutschland, Baden-Württemberg, Freiburg`  

2. **Gebunden an eine Organisation, aber ohne geografische Einschränkung:**  
   - `einschraenkung_wirkungsstaette_gebiet`: `Keine Angabe`  

3. **Gebunden an internationale Mitgliedschaft mit weltweiter Bewerbung:**  
   - `einschraenkung_wirkungsstaette_gebiet`: `international`  

> 🔎 Die Angaben in den Feldern `einschraenkung_wirkungsstaette` und `einschraenkung_wirkungsstaette_gebiet` müssen logisch und nachvollziehbar zusammenpassen.

---

### Nominierung

| Information         | Beschreibung |
|------------------|------|
| **Element ID**   | 15 |
| **Name**         | nominierung |
| **Definition**   | Gibt an, ob Eigenbewerbungen möglich sind und/oder wer nominieren darf. |
| **Entitätentyp** | Kontrollierte Liste |
| **Wert**         | Eigenbewerbung und Nominierung; Eigenbewerbung; Nominierung offen; Nominierung eingeschränkt; Nominierung Einrichtung / Gremium; Keine Angabe |
| **Occurence**    | 1 |

[🔝](#top)

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

| Information         | Beschreibung |
|------------------|------|
| **Element ID**   | 16 |
| **Name**         | laufzeit_beginn |
| **Definition**   | Gibt das Jahr an, in dem der Preis erstmals verliehen wurde. |
| **Entitätentyp** | Zahl |
| **Wert**         | JJJJ |
| **Occurence**    | 0-1 |

[🔝](#top)

---

| Information         | Beschreibung |
|------------------|------|
| **Element ID**   | 17 |
| **Name**         | laufzeit_ende |
| **Definition**   | Gibt das Jahr an, in dem der Preis letztmalig verliehen wurde. |
| **Entitätentyp** | Zahl |
| **Wert**         | JJJJ |
| **Occurence**    | 0-1 |

[🔝](#top)

---






















