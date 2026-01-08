<p align="left">
  <img src="https://kfid-online.de/images/layout/logo.svg" alt="KFiD-Logo" height="105">
  <img src="https://www.dfg.de/resource/image/196780/16x9/858/483/997695aec2153bd470ba051b9c03126e/56F3A561520B4EEF676078FA8168105D/logo-blau-267.png" alt="DFG-Logo" height="140">
</p>

---

[![CC0 1.0](https://licensebuttons.net/l/zero/1.0/88x31.png)](https://creativecommons.org/publicdomain/zero/1.0/)

# ORAP – Offenes Register für Auszeichnungen und Preise

**ORAP ist ein Community-getriebenes Projekt – wir freuen uns über Ihre Beteiligung und Ihr Feedback!**

### **Was ist ORAP?**
Das **Offene Register für Auszeichnungen und Preise (ORAP)** ist ein zentrales, öffentlich zugängliches Angebot, das qualitätsgesicherte Metadaten über wissenschaftliche Preise und Auszeichnungen bereitstellt. Ziel ist es, eine verlässliche und kuratierte Liste von Preisen und Auszeichnungen anzubieten und diese gemeinsam mit der Community laufend zu aktualisieren und zu erweitern.

### **Warum wurde ORAP entwickelt?**

Zur Unterstützung der Datenverarbeitung in Hochschulen und außeruniversitären Forschungseinrichtungen baut die **[Kommission für Forschungsinformationen in Deutschland (KFiD)](https://kfid-online.de/)** verschiedene Angebote und Ressourcen auf. Ein besonderer Fokus liegt dabei auf sogenannten **Stammdatenangeboten**, die als verlässliche Basis für Informationsinfrastrukturen dienen.

ORAP wurde initiiert, um eine qualitätsgesicherte Sammlung von Informationen zu wissenschaftlichen Preisen bereitzustellen. Die Geschäftsstelle der KFiD übernimmt hierbei die Kuratierung und Qualitätssicherung der Daten. Die Entwicklung und Pflege von ORAP erfolgt in enger Zusammenarbeit mit der Community und wird in Kooperation mit der **[Deutschen Forschungsgemeinschaft (DFG)](https://www.dfg.de/de)** bereitgestellt, um eine nachhaltige und vertrauenswürdige Datenquelle zu schaffen. 

Eine Einführung in ORAP und seine Entstehung bietet dieses **Hintergrunddokument** **<-- Hier noch Link einfügen ---**.

### **Welche Probleme löst ORAP?**
- **Zentrale Sammlung und Strukturierung**: Bisher existieren verstreute, oft unvollständige Listen von wissenschaftlichen Preisen. ORAP schafft eine **einheitliche und gut strukturierte** Sammlung.
- **Persistente IDs**: Alle enthaltenen Preise und Auszeichnungen haben einen Identifikator (`kf_prize_id`).
- **Qualitätsgesicherte Metadaten**: Alle Einträge werden bei der Aufnahme überprüft und mit Metadaten versehen. 
- **Standardisierte Metadaten**: Alle Preise und Auszeichnungen werden der Aufnahme kategorisiert, um eine **gezielte Auswahl** von Preisen und Auszeichnungen zu ermöglichen.
- **Erleichterung für Hochschulen & Forschungseinrichtungen**: Die Informationen helfen Einrichtungen beim **Aufbau verlässlicher Informationsinfrastrukturen**, ohne dass sie eigene Recherchen durchführen müssen.


### **[Metadatenfelder](Metadatenschema.md)**
Einige der wichtigsten Metadatenfelder in ORAP sind:
- **Identifier** (ORAP & Wikidata)
- **Bezeichnung des Preises** (Originalsprache)
- **Gegenstand des Preises**
- **Preis für Personen in einem frühen Karrierestadium**
- **Preisgeld**
- **Einschränkungen der Zielgruppe**
- **Nominierungsverfahren**
- **Laufzeit**
- **Preisverleiher**
- **Kategorie des Preisverleihers**
- **Land des Preisverleihers**


Eine vollständige Liste aller Metadatenfelder finden Sie hier:  
- **[Metadatenschema der Liste der wissenschaftlichen Preise und Auszeichnungen (Version 1.0.0)](Metadatenschema.md)**

## Format der Liste
Die ORAP-Daten werden in folgenden Formaten zur Verfügung gestellt:

- **CSV (tab-getrennt)** – geeignet für die Verarbeitung in Tabellenkalkulationen und Datenbanken.

- **Excel (XLSX)** – für komfortables Arbeiten in Microsoft Excel oder anderen kompatiblen Programmen.

## Versionierung

Die Kuratierung und Weiterentwicklung der ORAP-Datenbestände durch die Geschäftsstelle der KFiD wird über eine dreistufige Versionierung dokumentiert. Ziel ist es, Änderungen transparent und für alle Nutzerinnen und Nutzer nachvollziehbar zu machen.

Die Versionsnummer besteht aus drei Teilen:

**Major.Minor.Patch**  
Beispiel: Version 1.0.2

**Major-Version**  
Eine Major-Version wird vergeben, wenn grundlegende Änderungen vorgenommen werden. Dazu zählen insbesondere strukturelle Anpassungen am Metadatenschema, geänderte Metadatenfelder sowie andere Änderungen, die nicht mehr abwärtskompatibel sind.

**Minor-Version**  
Eine Minor-Version wird vergeben, wenn neue Inhalte ergänzt werden. Dazu gehören beispielsweise neue Preise und Auszeichnungen, neue Metadatenfelder, zusätzliche Informationen zu bestehenden Einträgen oder kleinere Erweiterungen, die vollständig abwärtskompatibel bleiben.

**Patch-Version**  
Eine Patch-Version wird vergeben, wenn Fehler korrigiert oder kleine Anpassungen vorgenommen werden. Dazu können Korrekturen von Schreibweisen, Formatfehlern oder anderen kleinen Unstimmigkeiten gehören. Patch-Versionen sind immer abwärtskompatibel.

Alle Änderungen werden in der Datei `CHANGELOG.md` dokumentiert. Zusätzlich werden veröffentlichte Versionen als GitHub Releases bereitgestellt. Ein Release enthält die ORAP-Daten als CSV- und Excel-Datei sowie das Metadatenschema in der jeweils gültigen Fassung.

## **Nutzung**

### **Wie können die Daten heruntergeladen werden?**

Die aktuellen Daten sind als CSV- und Excel-Dateien über die folgenden Links verfügbar. Die Dateien werden direkt aus dem öffentlichen Google-Sheets-Tabellenblatt *„ORAP öffentlich“* generiert und enthalten stets den aktuellsten Stand der Daten.

- **[Liste der wissenschaftlichen Preise und Auszeichnungen (CSV, tab-getrennt, UTF-8, Version 1.0.0)](https://docs.google.com/spreadsheets/d/1y8Fq4rr-NrYsZfgAXA-ng5jfeSkWYXNZ3uBxLPD8F24/export?format=csv&gid=1417429135)**
- **[Liste der wissenschaftlichen Preise und Auszeichnungen (Excel, Version 1.0.0)](https://docs.google.com/spreadsheets/d/1y8Fq4rr-NrYsZfgAXA-ng5jfeSkWYXNZ3uBxLPD8F24/export?format=xlsx&gid=1417429135)**

Die CSV-Datei wird tabulatorgetrennt und in UTF-8 bereitgestellt, um Konflikte mit Semikolons in Textfeldern zu vermeiden.

*Hinweis: Beim Öffnen der CSV-Datei in Excel wird empfohlen, die Datei über „Daten → Aus Text/CSV“ zu importieren und UTF-8 als Codierung auszuwählen, da ein direkter Doppelklick zu Darstellungsproblemen bei Umlauten führen kann.*


### **Lizenzierung**
ORAP wird unter der [**CC0-Lizenz**](https://creativecommons.org/publicdomain/zero/1.0/deed.de) veröffentlicht.

### **Zitiervorschlag**
KFiD – Kommission für Forschungsinformationen in Deutschland (2025): Offenes Register für Auszeichnungen und Preise, Berlin. [Hier noch DOI einfügen]

## **Mitmachen**
Die Community ist eingeladen, sich an der Pflege und Erweiterung von ORAP zu beteiligen. Hier ein paar Möglichkeiten: 

### **Meldung von Preisen und Auszeichnungen**
Sie möchten einen Preis oder eine Auszeichnung zur Aufnahme in das Register vorschlagen?  
**Nutzen Sie dazu bitte dieses [Formular](https://form-interface-5d7ffe.zapier.app/)**.

### **Pflege**
Trotz aller Sorgfalt können Einträge im Register im Laufe der Zeit veralten oder vereinzelt Fehler aufweisen. Wir sind daher auf Hinweise aus der Community angewiesen. 
Sie haben in GitHub die Möglichkeit ein neues Issue anzulegen, um auf **Korrekturbedarf** hinzuweisen. Bitte nennen Sie dabei immer den Identifier des Preises bzw. der Auszeichnung (`kf_prize_id`). Alternativ können Sie auch dieses **[Formular](https://form-interface-5d7ffe.zapier.app/)** verwenden.

### **Datenspende**
Betreiben Sie an Ihrer Einrichtung bereits ein Forschungsinformationssystem mit vielen Preisen und Auszeichnungen? Wenn Sie Ihre Sammlung in ORAP einspeisen möchten, kontaktieren Sie uns unter **[orap@kfid-online.de](mailto:orap@kfid-online.de)**.

### ORAP-Community-Austausch ###
Um die Community zu stärken und zu vernetzen, werden virtuelle Austauschtermine stattfinden. Auf diesem Wege kann die Weiterentwicklung von ORAP diskutiert werden.

## **Roadmap: Geplante Weiterentwicklungen**
- Zuordnung der Preise zu DESTATIS-Fächergruppen
- Wikidata-IDs für Preisverleiher
- Deutsche und englische Bezeichnungen für alle Preisverleiher 

## **Kontakt**
Bei Fragen oder Anregungen erreichen Sie uns unter:  
**[orap@kfid-online.de](mailto:orap@kfid-online.de)**






