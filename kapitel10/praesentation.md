class: center, middle

## [Software Engineering](../../praesentationen.html)

#### Kapitel 10

# Softwareprüfung 

Bjarne Zaremba - Danny Meihöfer

---
# Inhalt
***

1. Alpha- und Beta-Tests

1. A/B-Tests

1. Sicherheitstests

1. Relevante Werkzeuge für die Softwareprüfung

1. Flaky-Tests

1. Funktionsorientierte Tests

1. Strukturorientierte Tests

1. Zusammenfassung

---
class: center, middle
## Alpha and Beta Testing

---

### Alpha-Testing

**Definition und Zweck:**

- erste umfassende Testphase, bei der die Software intern von den Entwicklern getestet wird
- Fehler sollen gefunden werden, bevor die Software von externen Testern getestet wird
- Grundlegende Fehler sollen behoben werden

**Alpha-Testing im Softwareentwicklungszyklus:**

- Tests erfolgen vor Beginn der Beta-Phase → Software soll vorher auf Herz und Nieren geprüft werden
- Entwickler testen die Software und Besprechen internes Feedback
- Fokus: Sicherung der Softwarequalität und Vermeidung kritischer Fehler

**Herausforderungen:**

- Zeitaufwendig → interne Ressourcen werden benötigt
- Mangel an externem Feedback

---

**Vorteile von Alpha-Testing:**

- Identifikation grundlegender Fehler vor externem Feedback
- Höhere Wahrscheinlichkeit der Fehlerbehebung vor Start der Beta-Phase

**Zusammenfassung:**

- Alpha-Testing stellt die grundlegende Funktionsweise eines Softwareprodukts sicher
- Durch die interne Testung können Entwickler noch Fehler beheben, bevor die Software weiteren Tests unterzogen wird

---

### Beta-Testing

**Definition und Zweck:**

- Vorläufige Softwareversion wird an eine begrenzte Anzahl externer Benutzer ausgeliefert
- Benutzerfeedback sammeln
- Akzeptanz validieren
- Probleme in der “realen Welt” sollen identifiziert werden

---

**Arten des Beta-Testings:**

Offenes Beta-Testing:

- Software ist öffentlich zugänglich
- jeder Interessierte kann am Beta-Testing teilnehmen

   → breite Abdeckung von Benutzerperspektiven

Geschlossenes Beta-Testing:

- nur ausgewählte Benutzer erhalten Zugriff
- spezifische Testgruppe

    → gezielteres Feedback von einzelnen Benutzergruppen möglich

weitere Testarten:

- Gezielte Betatests → Testen von bestimmten Komponenten der Software
- Technische Betatests
- Betatests nach der Veröffentlichung

---

**Beta-Testing im Softwareentwicklungszyklus:**

- Bindeglied zwischen der internen Testung (Alphatests) und der Markteinführung
- Leistungsfähigkeit und Benutzerfreundlichkeit wird von realen Benutzern getestet
- durch echtes Benutzerfeedback können Entwickler die Software noch besser optimieren

**Beispiel für Betatests: Microsoft-Windows-Insider-Program:**

- Registrierung/Bewerbung bei Microsoft (halboffener Betatest)
- Vorabzugriff auf neue Versionen des Windows-Betriebssystems

     → wertvolles Feedback für Microsoft vor offizieller Markteinführung der neuen Version

**Vorteile von Beta-Testing:**

- Vielfältiges Feedback → Unterschiedliche Benutzerperspektiven
- Benutzerakzeptanz → kann nur schlecht in Alpha-Tests simuliert werden
- Fehlerbehebung → Identifikation von Fehlern, die in der Alpha-Phase nicht gefunden wurden

---

### Zusammenfassung Alpha- und Betatests

![Abb.1: Entwicklungsphasen eines Softwareproduktes](media/entwicklungsphasen.png)

Abb.1: Entwicklungsphasen eines Softwareproduktes

- Alpha-Tests werden intern durchgeführt → Sicherstellung, dass Software grundlegend funktioniert
- Beta-Tests werden ausgewählten (geschlossener Betatest) oder allen Benutzern (offener Betatest) zur Verfügung gestellt

       → echtes Benutzerfeedback durch Tests in der realen Welt

---

### A/B-Tests (auch bekannt: Split-Testing)

![:scale 80%](media/ab_testing.2_%20Funktionweise%20von%20A_B-Testing)

Abb.2: Funktionweise von A/B-Testing

---

**Definition und Zweck:**

- Methode, bei der zwei oder mehr Varianten eines Softwareprodukts (z.B. Website, App, …) erstellt und gleichzeitig getestet werden
    
    → Welche Variante des Produkts liefert bessere Ergebnisse?
    
- Treffen von datengesteuerten Entscheidungen um Benutzererfahrung zu verbessern und geschäftliche Ziele zu erreichen

**Vorgehensweise im A/B-Testing:**

- Identifikation des Ziels: Was soll getestet/verbessert werden? //Notiz: z.B. Wirksamkeit einer Schaltfläche, verschiedene Farbpaletten
- Unterteilung der Zielgruppe: Zielgruppe soll in sinnvolle Teile geteilt werden //Notiz: Meistens: Halbierung der Zielgruppe
- Erstellung von Varianten: Entwicklung von Version A und Version B
- Zufällige Zuweisung der Varianten zu den Zielgruppen
- Auswertung der Testdaten: Welche Variante hat bessere Daten im Hinblick auf das Ziel geliefert?

---

**Fiktives Beispiel: Amazon:**

- Amazon testet die Wirkung einer Farbveränderung des “Sofortkaufen”-Buttons, um festzustellen, ob eine andere Farbe das Nutzerverhalten verbessert

**Vorteile von A/B-Tests:**

- Datengestützte Entscheidungen: Keine Annahmen, sondern Entscheidungen basieren auf Daten
- Kontinuierliche Verbesserung: A/B-Tests sind iterativ (können immer wieder durchgeführt werden) → ständige Optimierung

---
class: center, middle

## Sicherheitstests

---

### Sicherheitslücke vs. Schwachstelle

**Sicherheitslücke:**

- Schwachstelle im System, die von Angreifern ausgenutzt werden kann, um unbefugten Zugriff zu erlangen
- resultiert aus Kombination aus Fehlern und unzulässigen Sicherheitsvorkehrungen
- Schließung der Sicherheitslücke erfordert konkrete Maßnahme

**Schwachstelle:**

- allgemeine Bezeichnung für eine Unsicherheit im System, die zu einer Sicherheitslücke führen kann
- Schwäche oder Fehler, der nicht beabsichtigt war
- Verschiedene Formen: Designschwächen, Implementierungsfehler, menschliche Fehler

→ Schwachstelle ist allgemeine Definition für eine Unsicherheit im System, Sicherheitslücke ist eine konkret ausgenutzte Schwachstelle. 

---

### Penetrationstest (kurz Pentest oder Ethical Hacking)

**Definition und Ziel:**

- autorisierte, aggressive Methode, die einen Hackerangriff auf ein System simuliert
- dient zur Bewertung der Sicherheit eines Systems
- Verwendung von Methoden, die auch von echten Hackern genutzt werden
- Ziel: Identifikation von Sicherheitslücken, bevor diese von echten Hackern gefunden werden

**Relevanz und Notwendigkeit:**

- Penetrationstest entscheidend, um Angriffsfläche von Software zu minimieren
- Regulatorische Anforderungen und Kundenvertrauen sind Gründe, um Pentests durchzuführen

---

**Tools und Techniken:**

- Social Engineering → Informationserhalt durch soziale Interaktion mit den Benutzern der Anwendung
- Exploitation von Software-Schwachstellen → Ausnutzen von Schwachstellen in der Software, um unbefugten Zugriff zu erlangen
- Password-Cracking → Systematisches Ausprobieren oder Anwenden von Techniken (z.B. Brute-Force), um Zugriff zum System zu erlangen

**Risiken, Rechtliches und Ethik:**

- Unzureichende Planung kann zu Systemausfällen kommen → Datenverluste
- Klare ethische Richtlinie erforderlich → Kein Überschreiten von rechtlichen und moralischen Grenzen

---

### **Static Application Security Testing (SAST) (Statische Codeanalyse)**

**Definition und Ziel:**

- Methode zur Identifikation von Sicherheitslücken im Quellcode der Anwendung → noch vor dem Kompilieren des Codes
- Schwachstellen und Risiken sollen möglichst früh erkannt werden
- bereits Code in einer sehr frühen Entwicklungsphase kann so auf Sicherheitslücken untersucht werden
- Code wird automatisiert durch Tool analysiert

**Mögliche Schwachstellen, die mit SAST gefunden werden können:**

- Cross-Site-Scripting
- SQL-Injection
- Buffer Overflow
- unsichere API-Aufrufe

---

**Vorteile von SAST:**

- Frühe Erkennung → Schwachstellen können bereits in der Entwicklungsphase erkannt und direkt behoben werden
- Integration in den Entwicklungsprozess → Sicherheit wird zu integralem Bestandteil der Softwareentwicklung
- Codequalität → SAST verbessert nicht nur die Sicherheit, sondern auch die Qualität des Codes

---

### **Dynamic Application Security Testing (DAST) (Dynamische Codeanalyse)**

**Definition und Ziel:** 

- Verfahren (Penetrationstest), der eine Anwendung während des aktiv-laufenden Prozesses untersucht (dynamisch)
- Simulation von realen Angriffsszenarien
- benötigt keinen Zugriff auf den Quellcode der Anwendung (im Gegensatz zu SAST)
- Anwendung wird “von Außen” bewertet → sehr realitätsnah

**Vorteile von DAST:**

- Realitätsnahe Tests → es wird in der tatsächlichen Umgebung getestet
- Schnelle Implementierung → DAST benötigt keinen Zugriff auf den Quellcode
- Integration in den Entwicklungsprozess → kann in den CI/CD-Prozess integriert werden
- Rate der falschpositiven Ergebnisse ist sehr gering
- kann während der Entwicklung, aber auch danach weiter genutzt werden

---

**Nachteile von DAST:**

- Skalierbarkeit → da DAST auf spezielle Angriffe eingerichtet wird, können die Tests nur von Sicherheitsexperten angepasst werden
- Langsam → DAST-Tools brauchen meistens 5-7 Tage
- Spät im Lebenszyklus → können erst bei lauffähiger Version der Anwendung eingesetzt werden (im Gegensatz zu SAST)
- Basiert auf bekannten Fehlern → neuartige Fehler werden erst spät erkannt

---
class: center, middle

## Relevante Werkzeuge

---

### Testautomatisierung

**Definition und Ziel:**

- Einsatz von Softwarewerkzeugen, um Testfälle automatisch auszuführen und Ergebnisse mit erwarteten Ergebnissen zu vergleichen
- Manueller Testaufwand wird reduziert → Ressourcen können anderweitig eingesetzt werden

**Vorteile von Testautomatisierung:**

- Effizienzsteigerung
- Wiederholbarkeit → Tests können immer wieder durchgeführt werden und müssen nicht manuell jedes Mal neu getestet werden

---

**Relevante Tools:**

Selenium:

- Open-Source-Framework zum Testen von Webanwendungen
- Automatisierung von Klicken, Navigieren und Formularausfüllen
- in vielen Sprachen unterstützt (Java, Python, C#, …)

Appium:

- Testautomatisierung für mobile Anwendungen
- “Selenium für Apps”
- Automatisierung von Touch-Gesten und Bildschirmnavigation

JUnit:

- Testen von Java-Anwendungen
- Automatisierung von Unit-Tests, Integrationstests und funktionalen Tests

pytest:

- Framework für Python
- Akzeptanztestgetriebene Entwicklung (ATDD)

---

### Test-Data-Generation

**Definition und Ziel:**

- Erstellung von realistischen Testdaten zum Gebrauch in Testumgebungen
- Realistische Testdaten sind wichtig, damit die Software unter verschiedenen Bedingungen funktioniert

---

**Tools zur automatisierten Erstellung von Testdaten:**

Mockaroo:

- Generierung von großen Mengen an Daten
- umfangreiche Liste von Datentypen bereits vorhanden (Namen, Adressen, komplexe JSON-Objekte)
- Skalierbarkeit → große Mengen an Daten können schnell generiert werden
- Daten können einfach in verschiedene Formate exportiert werden

Faker:

- Bibliothek für Python, mit der einfache Testdaten (Passwörter, Emails, …) generiert werden können
- Java-Äquivalent: JavaFaker

---

## Flaky-Tests

**Definition:**
- Flaky-Tests sind zufällig fehlgeschlagene Tests
- Flaky-Tests liefern bei gleichen Bedingungen (keine Änderungen am Code) unterschiedliche Ergebnisse

**Warum entstehen Flaky-Tests?**
- zufällige Verzögerungen
- Nebeneffekte von vorherigen Tests
- keine Wartezeiten in der Testautomatisierung

---

**Auswirkungen auf die Testumgebung:**
- Konsequenzen → Testautomatisierung unzuverlässig → Entwickler vertrauen den Tests nicht mehr
- Zeitverlust → Entwickler müssen die Ursachen des Fehlschlagens der Tests finden

**Vermeidung des Auftretens von Flaky-Tests:**
- Stabile Testumgebung → Klare Zustände, Minimierung von Nebeneffekten
- Korrekte Wartezeiten → Realistische Wartezeiten, Keine “harten” Wartezeiten
- Testisolierung → Testdaten separieren, Unabhängigkeit zwischen den Tests
- Automatisierte Testwiederholung einrichten

---
class: center, middle

## Funktionsorientierter Test (Black-Box-Test)

---

**Definition:**

- Testverfahren, bei dem Testfälle nur über die Spezifikation der Software erstellt werden
- innere Struktur (Code und Architektur) bleiben unbeachtet → Black-Box
- Fokus auf dem Verhalten der Software nach außen

**Ziel:**

- Aufdecken von Implementierungslücken → prüft das, was in der Spezifikation angegeben wird
- Blackbox-Tests belegen die mögliche Wahrscheinlichkeit von Fehlern

**Nachteile von Black-Box-Tests:**

- Aufwendige Testfallableitung → Testfälle müssen aus einer informellen Spezifikation abgeleitet werden
- Begrenzte Systemabdeckung → Nur die Teile, die in der Spezifikation erwähnt werden, werden auch getestet
- Keine Garantie für Fehlerfreiheit

---
class: center, middle

### Verfahren zur Testfallermittlung

---

**Äquivalenzklassenbildung:**

- Eingabewerte werden in Gruppen unterteilt
- Voraussetzung: Alle Werte einer Gruppe verhalten sich gleich
- Effiziente Testfallerstellung

**Vorgehensweise:**

- Identifikation relevanter Äquivalentklassen → Gemeinsamkeiten zwischen den möglichen Eingabewerten identifizieren
- Auswahl von repräsentativen Werten für jede Äquivalenzklasse → Ein Testfall pro Wert aus jeder Äquivalenzklasse

Beispiel: Eingabefeld für eine Altersüberprüfung

- Spezifische Aktionen, je nach Alter des Benutzers
- Äquivalentklassen:
    - Benutzer unter 18 Jahre (Mindestalter)
    - Benutzer im Alter von 18 bis 65 Jahren (Standardalter)
    - Benutzer über 65 Jahre (Seniorenalter)

---

**Grenzwertanalyse:**

- Testfälle sollen speziell an den Grenzen der Eingabedaten erstellt werden
    
    → Fehler treten häufig in diesen kritischen Bereichen auf
    
- Grenzwerte liegen an den Rändern der zuvor gebildeten Äquivalenzklassen
- auf Basis der Grenzwerte werden dann Testfälle erstellt

Beispiel: Mindestalter für die Nutzung einer Anwendung

- Software erfordert, dass Benutzer mindestens 18 Jahre alt sein muss
- Grenzwerte: 17 Jahre (fehlschlagender Test), 18 Jahre (erfolgreicher Test), 19 Jahre (erfolgreicher Test)

→ Durch Grenzwertanalyse wird sichergestellt, dass die Software auch in kritischen Bereichen richtig funktioniert.

---
class: center, middle

## Strukturorientierter Test (White-Box-Test)

---

**Definition:**

- Test, bei dem die innere Struktur einer Software analysiert wird (im Gegensatz zum Black-Box-Test)
- Interner Code und Softwarearchitektur wird berücksichtigt
- Sicherstellung, dass alle Anweisungen im Code funktionieren

**Vorteile:**

- Frühe Fehlererkennung
- Maximale Codeabdeckung
- Transparente Fehleranalyse

**Nachteile:**

- Aufwendige Durchführung
- Abhängig von der Codequalität
- Benutzererwartung wird nicht berücksichtigt

---

### Verfahren zur Testfallermittlung

**Statement-Coverage:**

- Sicherstellung, dass jede Anweisung im Code mindestens einmal ausgeführt wird
- Testfälle stellen sicher, dass jede Anweisung aufgerufen wird
- Beispiel: Angenommen, es gibt eine Funktion mit drei Zeilen Code. Ein Testfall wird erstellt, um sicherzustellen, dass jede dieser Zeilen mindestens einmal während des Tests ausgeführt wird.

**Branch-Coverage:**

- Stellt sicher, dass alle Entscheidungspunkte/Abzweigungen im Code durchlaufen werden
- Testfälle werden so entwickelt, dass alle Entscheidungspunkte einmal durchlaufen werden
- Beispiel: Eine Funktion enthält eine if-else-Anweisung. Testfälle werden erstellt, um sicherzustellen, dass sowohl der Zweig innerhalb der if-Anweisung als auch der Zweig innerhalb der else-Anweisung durchlaufen werden.

---

**Path-Coverage:**

- anspruchsvoller als Branch-Coverage
- stellt sicher, dass alle möglichen Pfade im Code durchlaufen werden
- Alle Kombinationen von Anweisungen und Verzweigungen werden getestet
- Beispiel: Eine komplexe Funktion hat verschiedene Pfade, abhängig von den Eingabeparametern. Testfälle werden entwickelt, um sicherzustellen, dass jeder mögliche Pfad durchlaufen wird.

**Condition-Coverage:**

- jeder logische Ausdruck im Code wird betrachtet
- jeder Ausdruck wird sowohl mit falsch als auch mit wahr getestet
- Beispiel: In einer Funktion gibt es eine logische Bedingung. Testfälle werden erstellt, um sicherzustellen, dass diese Bedingung sowohl als wahr als auch als falsch getestet wird.

---

## Zusammenfassung

- Alpha-Tests: Interne, erste umfassende Testphase
- Beta-Tests: Auslieferung einer vorläufigen Version an externe Benutzer
- A/B-Tests: Testen von Varianten für datengestützte Entscheidungen
- Sicherheitstest
    - Penetrationstests: Simuliert autorisierte Hackerangriffe
    - SAST: Identifikation von Sicherheitslücken im Quellcode vor dem Kompilieren
    - DAST: Simuliert Angriffe während des laufenden Prozesses
- Black-Box-Tests: Testverfahren ohne Kenntnis der inneren Struktur
- White-Box-Tests: Testverfahren mit Kenntnis der inneren Struktur

---

# Lernfragen

1. Was ist der Unterschied zwischen Alpha- und Beta-Tests?
1. Was ist ein A/B-Test?
1. Was ist ein Penetrationstest?
1. Was ist ein SAST?
1. Was ist ein DAST?
1. Welche Werkzeuge gibt es für die Softwareprüfung?
1. Was sind Flaky-Tests?
1. Was sind funktionsorientierte Tests?
1. Was sind strukturorientierte Tests?


---
# Quellen
***

- [https://www.guru99.com/de/alpha-beta-testing-demystified.html](https://www.guru99.com/de/alpha-beta-testing-demystified.html) [letzte Einsicht: 05.12.23]
- [https://www.seo-analyse.com/seo-lexikon/e/entwicklungsstadium](https://www.seo-analyse.com/seo-lexikon/e/entwicklungsstadium) [letzte Einsicht: 05.12.23]
- [https://de.wikipedia.org/wiki/Betatest](https://de.wikipedia.org/wiki/Betatest) [letzte Einsicht: 05.12.23]
- [https://www.computerweekly.com/de/definition/Betatest](https://www.computerweekly.com/de/definition/Betatest) [letzte Einsicht: 05.12.23]
- [https://www.zaptest.com/de/beta-tests-was-es-ist-arten-prozesse-ansaetze-tools-im-vergleich-zu-alpha-tests-und-mehr](https://www.zaptest.com/de/beta-tests-was-es-ist-arten-prozesse-ansaetze-tools-im-vergleich-zu-alpha-tests-und-mehr) [letzte Einsicht: 05.12.23]
- [https://www.optimizely.com/de/optimization-glossary/ab-testing/](https://www.optimizely.com/de/optimization-glossary/ab-testing/) [letzte Einsicht: 05.12.23]
- [https://gruenderplattform.de/unternehmensfuehrung/ab-testing](https://gruenderplattform.de/unternehmensfuehrung/ab-testing) [letzte Einsicht: 05.12.23]
- Beispiel wurden mithilfe von ChatGPT-3.5 erstellt: [https://chat.openai.com/](https://chat.openai.com/)
- [https://www.pcspezialist.de/blog/2021/02/05/schwachstellen/](https://www.pcspezialist.de/blog/2021/02/05/schwachstellen/) [letzte Einsicht: 05.12.23]
- [https://www.security-insider.de/was-ist-eine-sicherheitsluecke-a-648842](https://www.security-insider.de/was-ist-eine-sicherheitsluecke-a-648842) [letzte Einsicht: 05.12.23]

---

# Quellen

- [https://it-service.network/it-lexikon/penetrationstest](https://it-service.network/it-lexikon/penetrationstest) [letzte Einsicht: 05.12.23]
- [https://www.security-insider.de/was-ist-ein-penetrationstest-a-667683/](https://www.security-insider.de/was-ist-ein-penetrationstest-a-667683/) [letzte Einsicht: 05.12.23]
- [https://www.synopsys.com/glossary/what-is-sast.html](https://www.synopsys.com/glossary/what-is-sast.html) [letzte Einsicht: 05.12.23]
- [https://www.secodis.com/statisches-application-security-testing-sast/](https://www.secodis.com/statisches-application-security-testing-sast/) [letzte Einsicht: 05.12.23]
- [https://en.wikipedia.org/wiki/Dynamic_application_security_testing](https://en.wikipedia.org/wiki/Dynamic_application_security_testing) [letzte Einsicht: 05.12.23]
- [https://www.rapid7.com/de/cybersecurity-grundlagen/dast](https://www.rapid7.com/de/cybersecurity-grundlagen/dast) [letzte Einsicht: 05.12.23]
- [https://www.dev-insider.de/was-ist-dast-a-517156f0cc989cb6ce982ab2435c2150/](https://www.dev-insider.de/was-ist-dast-a-517156f0cc989cb6ce982ab2435c2150/) [letzte Einsicht: 05.12.23]
- [https://q-centric.com/blogs/die-besten-tools-fuer-die-testautomatisierung-2021](https://q-centric.com/blogs/die-besten-tools-fuer-die-testautomatisierung-2021) [letzte Einsicht: 06.12.23]
- [https://www.testautomatisierung.org/lexikon/selenium/](https://www.testautomatisierung.org/lexikon/selenium/) [letzte Einsicht: 06.12.23]
- [https://www.testautomatisierung.org/lexikon/appium/](https://www.testautomatisierung.org/lexikon/appium/) [letzte Einsicht: 06.12.23]
- [https://testsigma.com/blog/test-data-generation-tools/](https://testsigma.com/blog/test-data-generation-tools/) [letzte Einsicht: 06.12.23]

---

# Quellen

- [https://sonery.medium.com/generate-mock-data-of-any-format-with-mockaroo-9345facabc1e](https://sonery.medium.com/generate-mock-data-of-any-format-with-mockaroo-9345facabc1e) [letzte Einsicht: 07.12.23]
- [https://faker.readthedocs.io/en/master/](https://faker.readthedocs.io/en/master/) [letzte Einsicht: 07.12.23]
- [https://www.jetbrains.com/de-de/teamcity/ci-cd-guide/concepts/flaky-tests](https://www.jetbrains.com/de-de/teamcity/ci-cd-guide/concepts/flaky-tests) [letzte Einsicht: 08.12.23]
- [https://www.datadoghq.com/knowledge-center/flaky-tests/](https://www.datadoghq.com/knowledge-center/flaky-tests/) [letzte Einsicht: 08.12.23]
- [https://www.software-testing.academy/black-box-test.html](https://www.software-testing.academy/black-box-test.html) [letzte Einsicht: 08.12.23]
- [https://blog.milsystems.de/2012/03/durchfuehrung-von-aequivalenzklassentest-und-grenzwertanalyse-nach-istqb-teil-1/](https://blog.milsystems.de/2012/03/durchfuehrung-von-aequivalenzklassentest-und-grenzwertanalyse-nach-istqb-teil-1/) [letzte Einsicht: 08.12.23]
- [https://de.wikipedia.org/wiki/Dynamisches_Software-Testverfahren](https://de.wikipedia.org/wiki/Dynamisches_Software-Testverfahren) [letzte Einsicht: 08.12.23]
- [https://expleoacademy.com/dach/service/glossar/erklaerung/grenzwertanalyse](https://expleoacademy.com/dach/service/glossar/erklaerung/grenzwertanalyse) [letzte Einsicht: 08.12.23]
- [https://www.pw-akademie.eu/glossar/grenzwertanalyse/](https://www.pw-akademie.eu/glossar/grenzwertanalyse/) [letzte Einsicht: 08.12.23]
- [https://aqua-cloud.io/de/what-is-white-box-testing/](https://aqua-cloud.io/de/what-is-white-box-testing/) [letzte Einsicht: 08.12.23]

---

# Quellen

- [https://www.zaptest.com/de/white-box-tests-was-es-ist-wie-es-funktioniert-herausforderungen-metriken-tools-und-mehr](https://www.zaptest.com/de/white-box-tests-was-es-ist-wie-es-funktioniert-herausforderungen-metriken-tools-und-mehr) [letzte Einsicht: 08.12.23]
- [https://www.zyxware.com/articles/4161/what-is-statement-coverage-in-testing](https://www.zyxware.com/articles/4161/what-is-statement-coverage-in-testing) [letzte Einsicht: 08.12.23]


---
# Abbildungen


- Abb.1: [https://t2informatik.de/wissen-kompakt/alpha-version/](https://t2informatik.de/wissen-kompakt/alpha-version/) [letzte Einsicht: 05.12.23]
- Abb.2: [https://cxl.com/blog/ab-testing-guide/](https://cxl.com/blog/ab-testing-guide/) [letzte Einsicht: 05.12.23]
