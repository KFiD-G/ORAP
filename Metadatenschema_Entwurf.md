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
| **Bestehender Name** | Name des Feldes, wie es in der initialen Liste aufgeführt ist. |
| **Definition**  | Definition des Metadatenelements |
| **Entitätentyp** | Art des Elements (Binär, Identifier, Kontrollierte Liste, Zahl, Freitext, Datum) |
| **Wert**        | Bestimmt die Syntax des Wertes nach bestimmten Encoding-Schemen (z. B. ISO-Norm) |
| **Occurence**   | Gibt an, wie oft das Element auftauchen kann (1, 1-n, 0-n) |

---

## Die einzelnen Felder im Metadatenschema

### Identifier
| Element_ID | Name       | Bestehender Name | Definition |
|------------|-----------|-----------------|------------|
| 0          | id_intern | -               | Eindeutiger Identifier für jedes Datum. Dieser Identifier wird fortlaufend vergeben. Liste startet mit 1. |

- **Entitätentyp:** Identifier  
- **Wert:** Zahl (unbegrenzte Ziffernanzahl)  
- **Occurence:** 1  
  

---

### Wikidata Identifier
| Element_ID | Name        | Bestehender Name | Definition |
|------------|------------|-----------------|------------|
| 2          | wikidata_id | wikidata_id     | Eindeutiger Identifier, der von Wikidata kommt. |

- **Entitätentyp:** Wikidata Identifier  
- **Wert:** Beginnt mit `Q`, gefolgt von Ziffern (z. B. `Q30328658`, `Q874251`)  
- **Occurence:** 0-1  
- **Intern/Extern:** Extern  

#### **Aufnahmeregel für Element ID 2**  
- Bei Aufnahme eines neuen Preises erfolgt ein **Abgleich mit Wikidata**, um zu prüfen, ob es bereits einen entsprechenden Eintrag gibt.  
- Falls vorhanden, wird der **Wikidata-Identifier übernommen**.  
- [Wikidata Identifier-Referenz](https://www.wikidata.org/wiki/Wikidata:Identifiers)  


