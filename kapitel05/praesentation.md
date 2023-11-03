class: center, middle

## [Software Engineering](../../praesentationen.html)

#### Kapitel 5 - DevOps

# DevOps

Danny Meihoefer - Bjarne Zaremba

---
# Inhalt
***

1. Was ist DevOps (Ziele, Kultur, Best Practices, Tools)
2. Continuous Integration / Continuous Delivery / Continuous Deployment
3. Deployment strategies
4. CI/CD Tools
5. Secrets managment
6. SPACE Framework
7. DevEx Framework
8. DORA Metriken
9. DevSecOps
10. Threat Modeling (STRIDE)

---

class: center, middle

## DevOps

---

### Was ist DevOps?

DevOps ist eine Kombination aus den Begriffen Development und Operations

Darunter versteht man eine enge Zusammenarbeit zwischen den Bereichen Entwicklung und Betrieb

DevOps ist allerdings kein bestimmtes Tool, sondern eine Art Kultur

Es ist eine Kombination aus Entwicklung und Betrieb
- Mischung aus Praktiken, Tools und Philosophien

Beschleunigt die Softwareentwicklung und die Softwareauslieferung

DevOps basiert auf den Prinzipien:

- Kultur
- Best Practices
- Tools

---

## DevOps

![:scale 100%](media/Devops.svg)

---

### DevOps - Kultur

In der DevOps-Kultur geht es um:

- Automatisierung
- Kommunikation
- Gemeinsame Verantwortung
- Enge Zusammenarbeit
- Transparenz

Das wird erreicht indem die Entwicklung und der Betrieb als ein Team arbeiten

Wichtig ist dafür ein sicheres Umfeld zu schaffen, in dem Fehler erlaubt sind (Trial and Error)

Kontinuirlicher Lernprozess

---

### DevOps - Teams

DevOps Teams sind wichtig um die Vorteile von DevOps zu erreichen

Cross-Funktionale Teams

- Mitglieder mit unterschiedlichen Fähigkeiten
- Entwickler, Betreiber, Tester, ...

Automatisierungsexperten

- Automatisierung von Prozessen
- Beschleunigung der Entwicklungs- und Bereitstellungsprozesse

Site Reliability Engineers

- Verantwortlich für die Verfügbarkeit und Zuverlässigkeit der Software

Eine Führungskraft

- Verantwortlich für die Koordination der Teams

---

### DevOps - Best Practices

Die DevOps Praktiken unterscheiden sich von Unternehmen zu Unternehmen

Auch einzelne Teams können unterschiedliche Praktiken haben

Die Praktiken sind aber immer auf die Ziele von DevOps ausgerichtet

Wichtige Praktiken sind:

- Einbeziehung der Entwickler in den Betrieb
- Einbeziehung der Betreiber in die Entwicklung
- Versionskontrolle
- Agilität durch eine gute Infrastruktur
- Möglichst viel Automatisierung
- Continuous Integration / Continuous Delivery / Continuous Deployment
- Einheitliche Tools und Platformen

---

### DevOps - Vorteile

DevOps bietet für verschiedene Bereiche Vorteile:

- Geringes Risiko bei Änderungen
- Bessere Qualität der Produkte
- Geringere Veröffentlichungskosten
- Schneller auf dem Markt
- Weniger Zeitverlust durch Fehler
  - Mehr Zeit für die eigentliche Arbeit
- Höhere Einnahmen
- Stabile Infrastruktur
- Mitarbeiterzufriedenheit
-

---

### DevOps - Ziele

Die Ziele von DevOps sind:

- Schnellere Bereitstellung von Software
- Höhere Zuverlässigkeit von Software-Releases
- Bessere Zusammenarbeit zwischen Teams
    - Besonders zwischen Entwicklung und Betrieb
- Automatisierung von Prozessen
- Bessere Skalierbarkeit
- Höhere Qualität
- Kosteneffizienz
- Kontinuierliche Verbesserung

---


### DevOps - Pipelines

DevOps Pipelines sind ein wichtiger Bestandteil von DevOps

Eine Pipeline ist eine Reihe von Schritten, die automatisiert werden

Vergleichbar mit einer Fließbandproduktion

Es gibt typische Komponenten in einer Pipeline:

![:scale 150%](media/pipeline.png)

---

### DevOps - Continuous Integration (CI) / Continuous Deployment (CD)

Continuous Integration - Kontinuierliche Integration

Veränderungen am Code werden automatisch und regelmäßig in das Hauptprojekt integriert

- Integrations ins Hauptrepository

Continuous Deployment - Kontinuierliche Bereitstellung

- Softwareupdates werden automatisch und regelmäßig bereitgestellt
- Häufigere Updates verbessert die Feedbackschleife
  - Feedback kann öfter und schneller eingearbeitet werden

---

### DevOps - Continuous Delivery (CD)

Continuous Delivery - Kontinuierliche Auslieferung

- Softwareupdates werden nicht automatisch bereitgestellt
- Sie werden aber automatisch vorbereitet

Das beduetet, dass die Software jederzeit ausgeliefert werden könnte

![:scale 100%](media/cicd.png)

---

### Releasing vs Deploying

Release bedeutet die Software wird für den Endbenutzer veröffentlicht

Beim Deploying wird die Software nur in eine bestimmte Umgebung ausgeliefert

- Diese muss nicht für den Endbenutzer zugänglich sein
- Ein Beispiel dafür kann eine Testumgebung sein

---

### Semantic Versioning

Semantic Versioning ist ein System zur Versionsnummerierung

- Wie sollen Versionsnummern vergeben werden?

Eine Versionsnummer besteht aus drei Teilen:

- Major, Minor, Patch
- Major: Große grundlegende Änderungen
  - Nicht kompatibel mit vorherigen Versionen
  - 2.1.5 -> 3.0.0
- Minor: Neue Funktionen und Verbesserungen
  - Kompatibel mit vorherigen Versionen
  - 2.1.5 -> 2.2.0
- Patch: Fehlerbehebungen
  - Kompatibel mit vorherigen Versionen
  - Behebung von Bugs und Sicherheitslücken
  - 2.1.5 -> 2.1.6

---

class: center, middle

## Deployment strategies

Es gibt verschiedene Strategien für die Auslieferung von Software

---

### Blue-Green Deployment

Strateegie um die Ausfallzeit bei Updates zu minimieren

- Es gibt zwei Umgebungen
  - Blue und Green

1. Die aktuelle Version läuft in der Blue-Umgebung
2. Die neue Version wird in der Green-Umgebung bereitgestellt
3. Die Green-Umgebung wird getestet
4. Die Green-Umgebung wird zur aktuellen Version
  
  - Mit Hilfe eines Load Balancers wird der Traffic auf die Green-Umgebung umgeleitet

5. Die Blue-Umgebung wird inaktiv gesetzt und kann für das nächste Update verwendet werden

---

### Blue-Green Deployment

![:scale 100%](media/bluegreen.jpg)

---
### Canary 

Canary Deployment ist eine Strategie um die Auswirkungen von Updates zu testen

- Früher wurden Kanarienvögel im Vorfeld von Bergleuten in Minen eingesetzt um die Luftqualität zu testen (Starben sie war die Luftqualität schlecht)

Software wird zuerst nur an einen kleinen Teil der Benutzer (Canary User) ausgeliefert

- Die kleine Gruppe kann die Software testen und Feedback geben

![:scale 80%](media/canary.jpg)

---

### Feature Flags

Feature Flags ermöglichen es bestimmte Features zu aktivieren oder zu deaktivieren

Einzelne Gruppen von Benutzern können bestimmte Features testen

- Kontrolliertes testen

Über eine einzelne Konfigurationsdatei können Features aktiviert oder deaktiviert werden

![:scale 90%](media/featureflags.svg)

---

class: center, middle

## CI/CD Tools

CI/CD Tools sind wichtig für die Automatisierung von Prozessen

Workflowautomatisierung

Beispiele für CI/CD Tools: Jenkins, GitLab CI, CircleCI, Travis CI, ...

---

### CI Server

Eins der gängigsten CI Tools ist Jenkins

Jenkins ermöglicht:

- Automatisierung von Builds
- Automatisierung von Tests
- Automatisierung von Deployments
- Automatisierung von anderen Prozessen
- Überwachung von Prozessen

Jenkins kann zum Beispiel Veränderungen in einem Git Repository erkennen und automatisch einen Build starten

![:scale 90%](media/jenkins.png)

---

### CI Server

![:scale 100%](media/jenkinsworkflow.png)

---

## Secrets managment

Secrets sind sensible Daten, die nicht öffentlich zugänglich sein sollten

- Passwörter, API Keys, ...

Diese sollten nicht Hardcoded in den Quellcode geschrieben werden

Secrets Management Tools ermöglichen, dass diese Daten sicher verwaltet werden ohne die Workflowautomatisierung zu beeinträchtigen

Alle Secrets werden über ein zentrales Tool verwaltet

- Eine Anfrage an das Tool liefert z.B. das Passwort für eine Datenbank

---

## CAMS, CALMS, CALMAS

- verschiedene Modelle im Kontext von DevOps zur Verbesserung der Zusammenarbeit in IT-Organisationen

---

### CAMS (Culture, Automation, Measurement, Sharing)

- Culture (dt. Kultur)

- Automation (Automatisierung)
  
- Measurement (Messung)
   
- Sharing (Teilen)
 

---

### CALMS (Culture, Automation, Lean, Measurement, Sharing)

- Erweiterung zu CAMS → Lean kommt hinzu
- Lean (Schlanke Prozesse)

---

### CALMAS (Culture, Automation, Lean, Measurement, Agile, Sharing)

- Erweiterung zu CAMS und CALMS → Agile kommt hinzu
- Agile (Agilität)
    

---

## SPACE Framework

- Methode, um die Servicequalität in der IT-Serviceverwaltung zu verbessern
SPACE ist Abkürzung für folgende Hauptdimensionen:
- Software
    
- Process (Prozess)
    
- Automation (Automatisierung)

- Culture (Kultur)
 
- Environment (Umgebung)

Fazit: SPACE-Framework soll Unternehmen bei der Bewertung und Verbesserung dieser Punkte helfen.

⇒ Qualität der IT-Services und Kundenzufriedenheit kann gesteigert werden.

---

## DevEx Framework (Developer Experience Framework)

- die Entwicklererfahrung von Entwicklern in Softwareentwicklungsteams soll verbessert werden
- DevEx ist die Art und Weise, wie Entwickler die Tools, Prozesse und Umgebungen wahrnehmen, die sie bei der Arbeit verwenden
- Effizienz und Zufriedenheit der Entwickler soll gesteigert werden

Wichtige Aspekte des DevEx Frameworks:

- Werkzeuge und Infrastruktur

- Dokumentation und Schulung

- Automatisierung und Wiederverwendbarkeit

- Feedback-Mechanismen

- Kollaboration und Kommunikation

- Kultur und Wertorientierung


---

## DORA Metriken

- Gruppe von Metriken, die Effizienz, Geschwindigkeit und Qualität von Softwareentwicklungen messen sollen
- Von der DORA (DevOps Research and Assessment Group) erstellt
---
### Deployment Frequency (Bereitstellungshäufikeit)

- misst, wie häufig Änderungen, Funktionen und Updates in der Produktionsumgebung veröffentlicht werden
- Hohe Deployment Frequency → Hohe Agilität des Teams

---

 

### Change Lead Time (Änderungsdurchlaufzeit)

- misst die durchschnittliche Zeit zwischen einem Commit und der Freigabe des Codes für die Produktionsumgebung
- Je kürzer die Change Lead Time ist, desto schneller kann das Team auf Feedback des Marktes eingehen und Softwareverbesserungen durchführen
- Benchmarks
    - **Hervorragend:** Weniger als eine Stunde
    - **Hoch:** Zwischen einem Tag und einer Woche
    - **Mittel:** Zwischen einem Monat und einem halben Jahr
    - **Gering:** Mehr als sechs Monate
- Separate Testteams in einem Unternehmen können sich negativ auf die Change Lead Time auswirken

---

### Change Failure Rate (Änderungsausfallrate)

- Prozentsatz der Bereitstellungen, die einen Fehler verursachen, der eine sofortige Behebung benötigt
- Je niedriger die Change Failure Rate, desto mehr Zeit hat das Team sich mit neuen Features anstatt mit dem Beheben von Fehlern zu beschäftigen
- Benchmark
    - **Hervorragend:** 0 - 15 %
    - **Hoch:** 16 - 30 %
    - **Mittel:** 16 - 30 %
    - **Gering:** 16 - 30 %

---

### Mean Time to Restore (Mittlere Wiederherstellungszeit)

- Zeit, die ein Team benötigt, um einen Service wiederherzustellen, der den Betrieb der Anwendung beeinträchtigt
- Fehler kann alles ein
- Benchmark
    - **Hervorragend:** Weniger als eine Stunde
    - **Hoch:** Weniger als ein Tag
    - **Mittel:** Zwischen einem Tag und einer Woche
    - **Gering:** Mehr als sechs Monate

---

## DevSecOps

- Erweiterung von DevOps um die Sicherheit im gesamten Softwareprozess

- “Security by Design”

- Fordert intensive Zusammenarbeit zwischen den verschiedenen Teams


---

### Shift-Left-Testing

- Ansatz, Sicherheitstests weiter nach “links” im Softwareentwicklungsprozess zu schieben

- Kosteneffiziente Behebung von Sicherheitslücken


---

 

### Sicherheitsziele der Kryptographie

- Grundlegende Prinzipien, die durch den Einsatz von kryptographischer Techniken erreicht werden können

Sicherheitsziele:

- Authentizität

- Integrität

- Verbindlichkeit

- Vertraulichkeit

- Verfügbarkeit

- Autorisierung


---

### Threat Modeling (Bedrohungsmodellierung)

- Ansatz zum Erkennen und Bewerten von Sicherheitsbedrohungen in einer Anwendung oder einem System
- Durch Modellierung werden potenzielle Schwachstellen erkannt
- STRIDE ist ein Akronym, welches die 6 Hauptkategorien zusammenfasst

---

### STRIDE

- Spoofing (Täuschung)

- Tampering (Manipulation)

- Repudiation (Abstreitbarkeit)

- Information Disclosure (Informationsweitergabe)

- Denial of Service (Verweigerung des Dienstet)

- Elevation of Privilege (Erhöhung von Berechtigungen)
---

## Verständnisfragen

1. Was ist DevOps?
2. Was sind die Ziele von DevOps?
3. Was sind DevOps Pipelines?
4. Was bedeutet Continuous Integration, Continuous Delivery und Continuous Deployment?
5. Wie geht semantic versioning?
6. Was ist ein Blue-Green Deployment?
7. Was sind CI/CD Tools?
8. Was ist Secrets Management?
9. Für was steht "CAMS"?
10. Wozu wird das DevEx Framework benutzt?
11. Nenne und beschreibe eine der DORA Metriken!
12. Für was steht "DORA"?
13. Was ist DevSecOps?
14. Nenne und beschreibe ein Sicherheitsziel der Kryptographie!
15. Was ist "STRIDE"?

---

# Quellen
***

https://www.tibco.com/de/reference-center/what-is-devops

https://jfrog.com/de/devops-tools/what-is-devops/

https://www.abtasty.com/de/blog/blue-green-deployments/

https://semaphoreci.com/blog/what-is-canary-deployment

https://www.jenkins.io/

https://www.qrpinternational.ch/blog/faq/was-sind-die-5-calms-devops/ [letzte Einsicht: 02.11.2023]

https://www.educative.io/answers/what-is-the-cams-principle-in-devops [letzte Einsicht: 02.11.2023]

CALMAS → Chat-GPT-3.5: https://chat.openai.com/

https://www.red-gate.com/blog/database-devops/what-is-the-space-developer-productivity-framework [letzte Einsicht: 02.11.2023]
---
# Quellen 
***

https://shiftmag.dev/dora-space-gsm-or-devex-how-to-measure-developer-productivity-1304/ [letzte Einsicht: 02.11.2023]

https://www.splunk.com/de_de/data-insider/devops-research-and-assessment-metrics.html [letzte Einsicht: 03.11.2023]

https://www.ibm.com/de-de/topics/devsecops# [letzte Einsicht: 03.11.2023]

https://www.testim.io/blog/shift-left-testing-guide/ [letzte Einsicht: 03.11.2023]

https://www.identible.de/glossar/sicherheitsziele.html [letzte Einsicht: 03.11.2023]

https://www.softwaresecured.com/stride-threat-modeling/ [letzte Einsicht: 03.11.2023]