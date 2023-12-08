# Kapitel 10 - Softwareprüfung

**Autoren:** Bjarne Zaremba - Danny Meihöfer

## Lernziele für dieses Kapitel

Nach diesem Kapitel sollen folgende Aspekte klarer geworden sein:

- Was ist Alpha- und Beta-Testing?
- Was ist A/B-Testing?
- Was ist Penetrationstest?
- Was ist SAST und DAST?
- Welche Tools gibt es für die Testautomatisierung?
- Was ist Testdatengenerierung?
- Wie kann ich Testdaten generieren?
- Was sind Flaky Tests?
- Was ist Black-Box-Testing?
- Was ist White-Box-Testing?


## Einleitung
Diese Ausarbeitung behandelt das Kapitel 10 zum Thema Softwareprüfung im Bereich Software Engineering. Die Präsentation wurde von Bjarne Zaremba und Danny Meihöfer erstellt.

---

### 1. Alpha- und Beta-Tests

#### Alpha-Testing

**Definition und Zweck:**
- Erste umfassende Testphase, bei der die Software intern von den Entwicklern getestet wird.
- Fehler sollen gefunden werden, bevor die Software von externen Testern getestet wird.
- Grundlegende Fehler sollen behoben werden.

**Alpha-Testing im Softwareentwicklungszyklus:**
- Tests erfolgen vor Beginn der Beta-Phase → Software soll vorher auf Herz und Nieren geprüft werden.
- Entwickler testen die Software und besprechen internes Feedback.
- Fokus: Sicherung der Softwarequalität und Vermeidung kritischer Fehler.

**Herausforderungen:**
- Zeitaufwendig → Interne Ressourcen werden benötigt.
- Mangel an externem Feedback.

**Vorteile von Alpha-Testing:**
- Identifikation grundlegender Fehler vor externem Feedback.
- Höhere Wahrscheinlichkeit der Fehlerbehebung vor Start der Beta-Phase.

**Zusammenfassung:**
- Alpha-Testing stellt die grundlegende Funktionsweise eines Softwareprodukts sicher.
- Durch die interne Testung können Entwickler noch Fehler beheben, bevor die Software weiteren Tests unterzogen wird.

#### Beta-Testing

**Definition und Zweck:**
- Vorläufige Softwareversion wird an eine begrenzte Anzahl externer Benutzer ausgeliefert.
- Benutzerfeedback sammeln.
- Akzeptanz validieren.
- Probleme in der “realen Welt” sollen identifiziert werden.

**Arten des Beta-Testings:**
- Offenes Beta-Testing:
  - Software ist öffentlich zugänglich.
  - Jeder Interessierte kann am Beta-Testing teilnehmen.
  - Breite Abdeckung von Benutzerperspektiven.

- Geschlossenes Beta-Testing:
  - Nur ausgewählte Benutzer erhalten Zugriff.
  - Spezifische Testgruppe.
  - Gezielteres Feedback von einzelnen Benutzergruppen möglich.

**Beta-Testing im Softwareentwicklungszyklus:**
- Bindeglied zwischen der internen Testung (Alphatests) und der Markteinführung.
- Leistungsfähigkeit und Benutzerfreundlichkeit werden von realen Benutzern getestet.
- Durch echtes Benutzerfeedback können Entwickler die Software weiter optimieren.

**Beispiel für Betatests: Microsoft-Windows-Insider-Program:**
- Registrierung/Bewerbung bei Microsoft (halboffener Betatest).
- Vorabzugriff auf neue Versionen des Windows-Betriebssystems.
- Wertvolles Feedback für Microsoft vor offizieller Markteinführung der neuen Version.

**Vorteile von Beta-Testing:**
- Vielfältiges Feedback → Unterschiedliche Benutzerperspektiven.
- Benutzerakzeptanz → Kann nur schlecht in Alpha-Tests simuliert werden.
- Fehlerbehebung → Identifikation von Fehlern, die in der Alpha-Phase nicht gefunden wurden.

**Zusammenfassung Alpha- und Betatests:**
![Abb.1: Entwicklungsphasen eines Softwareproduktes](media/entwicklungsphasen.png)
- Alpha-Tests werden intern durchgeführt → Sicherstellung, dass Software grundlegend funktioniert.
- Beta-Tests werden ausgewählten (geschlossener Betatest) oder allen Benutzern (offener Betatest) zur Verfügung gestellt → Echtes Benutzerfeedback durch Tests in der realen Welt.

### 2. A/B-Tests (auch bekannt: Split-Testing)

![Abb.2: Funktionweise von A/B-Testing](media/ab_testing.2_%20Funktionweise%20von%20A_B-Testing)

**Definition und Zweck:**
- Methode, bei der zwei oder mehr Varianten eines Softwareprodukts (z.B. Website, App, …) erstellt und gleichzeitig getestet werden.
  - Welche Variante des Produkts liefert bessere Ergebnisse?
- Treffen von datengesteuerten Entscheidungen, um Benutzererfahrung zu verbessern und geschäftliche Ziele zu erreichen.

**Vorgehensweise im A/B-Testing:**
- Identifikation des Ziels: Was soll getestet/verbessert werden?
- Unterteilung der Zielgruppe: Zielgruppe soll in sinnvolle Teile geteilt werden.
- Erstellung von Varianten: Entwicklung von Version A und Version B.
- Zufällige Zuweisung der Varianten zu den Zielgruppen.
- Auswertung der Testdaten: Welche Variante hat bessere Daten im Hinblick auf das Ziel geliefert?

**Fiktives Beispiel: Amazon:**
- Amazon testet die Wirkung einer Farbveränderung des “Sofortkaufen”-Buttons, um festzustellen, ob eine andere Farbe das Nutzerverhalten verbessert.

**Vorteile von A/B-Tests:**
- Datengestützte Entscheidungen: Keine Annahmen, sondern Entscheidungen basieren auf Daten.
- Kontinuierliche Verbesserung: A/B-Tests sind iterativ (können immer wieder durchgeführt werden) → ständige Optimierung.

### 3. Sicherheitstests

**Definition und Zweck:**
- Prüfung der Sicherheitsaspekte eines Softwareprodukts.
- Identifikation von Sicherheitslücken und Schwachstellen.
- Schutz vor Angriffen und Datenverlust.

**Arten von Sicherheitstests:**
1. **Penetrationstests:**
   - Simulation von Angriffen auf das System.
   - Ziel: Identifikation von Schwachstellen, die von Angreifern ausgenutzt werden könnten.

2. **Authentifizierungstests:**
   - Überprüfung der Sicherheit von Benutzeranmeldungen und Zugriffskontrollen.
   - Schutz vor unbefugtem Zugriff.

3. **Verschlüsselungstests:**
   - Überprüfung der Wirksamkeit von Verschlüsselungstechnologien.
   - Schutz von sensiblen Daten.

4. **Code-Analyse:**
   - Prüfung des Quellcodes auf mögliche Sicherheitslücken.
   - Identifikation und Behebung von potenziellen Bedrohungen.

**Beispiel: Ethical Hacking:**
- Unternehmen beauftragen ethische Hacker, um Sicherheitslücken zu finden und zu beheben, bevor böswillige Hacker diese ausnutzen können.

**Vorteile von Sicherheitstests:**
- Früherkennung von Sicherheitslücken: Behebung bevor Software in den Produktivbetrieb geht.
- Schutz sensibler Daten: Verhindern von Datenlecks und unbefugtem Zugriff.

### 4. Relevante Werkzeuge für die Softwareprüfung

**Statische Analysetools:**
- Prüfung des Quellcodes ohne Ausführung.
- Identifikation von potenziellen Problemen, bevor der Code ausgeführt wird.
- Beispiel: SonarQube.

**Dynamische Analysetools:**
- Analyse des Codes während der Ausführung.
- Identifikation von Fehlern und Leistungsproblemen in einer realen Umgebung.
- Beispiel: Selenium.

**Testautomatisierungstools:**
- Automatisierung von Testprozessen, um Zeit zu sparen und menschliche Fehler zu reduzieren.
- Beispiel: JUnit, TestNG.

**Performance-Testtools:**
- Überprüfung der Leistungsfähigkeit einer Anwendung unter verschiedenen Bedingungen.
- Beispiel: Apache JMeter.

### 5. Flaky-Tests

**Definition und Ursachen:**
- Flaky-Tests sind Tests, die bei mehrmaligem Ausführen unterschiedliche Ergebnisse liefern.
- Ursachen können externe Faktoren wie Netzwerkverzögerungen, zufällige Fehlertoleranz und nicht deterministisches Verhalten von Code sein.

**Probleme durch Flaky-Tests:**
- Zeitverlust: Entwickler müssen Zeit für die Fehleranalyse aufwenden.
- Geringere Zuverlässigkeit: Flaky-Tests führen zu Unsicherheit über die tatsächliche Qualität der Software.

**Lösungsansätze:**
- Identifikation von Flaky-Tests durch wiederholte Ausführung.
- Analyse der Ursachen und Behebung der zugrunde liegenden Probleme.

### 6. Funktionsorientierte Tests

**Definition und Zweck:**
- Tests, die die funktionalen Anforderungen einer Software überprüfen.
- Ziel: Sicherstellen, dass die Software gemäß den Spezifikationen funktioniert.

**Beispiele funktionsorientierter Tests:**
- Unit-Tests: Überprüfung einzelner Units (kleinste Teile) des Codes.
- Integrationstests: Prüfung der Interaktion zwischen verschiedenen Units.
- Systemtests: Gesamtheitliche Überprüfung der Anwendung.

**Zusammenfassung:**
- Funktionsorientierte Tests spielen eine entscheidende Rolle bei der Sicherstellung, dass eine Software ihren funktionalen Anforderungen entspricht.
- Unterschiedliche Testarten ermöglichen eine umfassende Überprüfung verschiedener Aspekte der Software.

### 7. Strukturorientierte Tests

**Definition:**

Ein strukturorientierter Test, auch als White-Box-Test bekannt, ist ein Testansatz, bei dem die interne Struktur einer Software analysiert wird. Im Gegensatz zum Black-Box-Test, bei dem nur die funktionalen Aspekte der Software überprüft werden, berücksichtigt der strukturorientierte Test den internen Code und die Softwarearchitektur. Das Hauptziel besteht darin, sicherzustellen, dass alle Anweisungen im Code ordnungsgemäß funktionieren.

**Vorteile:**

- **Frühe Fehlererkennung:** Durch die Analyse der internen Struktur können potenzielle Fehler frühzeitig im Entwicklungsprozess identifiziert und behoben werden.

- **Maximale Codeabdeckung:** Der White-Box-Test zielt darauf ab, jede Anweisung im Code abzudecken, was zu einer maximalen Testabdeckung führt.

- **Transparente Fehleranalyse:** Durch den Einblick in die interne Struktur der Software ist es einfacher, Fehler zu analysieren und zu verstehen.

**Nachteile:**

- **Aufwendige Durchführung:** Der White-Box-Test erfordert einen detaillierten Einblick in den Code, was zeitaufwändig sein kann.

- **Abhängig von der Codequalität:** Die Effektivität des Tests hängt stark von der Qualität des Codes ab.

- **Benutzererwartung wird nicht berücksichtigt:** Da der Fokus auf der internen Struktur liegt, kann der Test die Benutzererwartungen möglicherweise nicht vollständig abdecken.

---

#### Verfahren zur Testfallermittlung

**Statement-Coverage:**

- Sicherstellung, dass jede Anweisung im Code mindestens einmal ausgeführt wird.
- Testfälle werden entwickelt, um sicherzustellen, dass jede Anweisung aufgerufen wird.
- Beispiel: Angenommen, es gibt eine Funktion mit drei Zeilen Code. Ein Testfall wird erstellt, um sicherzustellen, dass jede dieser Zeilen mindestens einmal während des Tests ausgeführt wird.

**Branch-Coverage:**

- Stellt sicher, dass alle Entscheidungspunkte/Abzweigungen im Code durchlaufen werden.
- Testfälle werden so entwickelt, dass alle Entscheidungspunkte einmal durchlaufen werden.
- Beispiel: Eine Funktion enthält eine if-else-Anweisung. Testfälle werden erstellt, um sicherzustellen, dass sowohl der Zweig innerhalb der if-Anweisung als auch der Zweig innerhalb der else-Anweisung durchlaufen werden.

**Path-Coverage:**

- Anspruchsvoller als Branch-Coverage.
- Stellt sicher, dass alle möglichen Pfade im Code durchlaufen werden.
- Alle Kombinationen von Anweisungen und Verzweigungen werden getestet.
- Beispiel: Eine komplexe Funktion hat verschiedene Pfade, abhängig von den Eingabeparametern. Testfälle werden entwickelt, um sicherzustellen, dass jeder mögliche Pfad durchlaufen wird.

**Condition-Coverage:**

- Jeder logische Ausdruck im Code wird betrachtet.
- Jeder Ausdruck wird sowohl mit falsch als auch mit wahr getestet.
- Beispiel: In einer Funktion gibt es eine logische Bedingung. Testfälle werden erstellt, um sicherzustellen, dass diese Bedingung sowohl als wahr als auch als falsch getestet wird.


---

## Fazit
Die Softwareprüfung ist ein wesentlicher Bestandteil des Softwareentwicklungszyklus. Alpha- und Beta-Tests gewährleisten die Funktionsfähigkeit und Benutzerakzeptanz, A/B-Tests ermöglichen datengesteuerte Verbesserungen, Sicherheitstests schützen vor Bedrohungen, und verschiedene Tools unterstützen Entwickler bei der effizienten Durchführung von Tests. Die Identifikation und Behebung von Flaky-Tests sowie die Durchführung funktionsorientierter Tests sind ebenfalls von großer Bedeutung.

Abschließend ist zu betonen, dass eine umfassende Softwareprüfung die Qualität, Sicherheit und Benutzerfreundlichkeit eines Softwareprodukts sicherstellt und somit einen erfolgreichen Einsatz in der realen Welt ermöglicht.


## Bilder

- Abb.1: [https://t2informatik.de/wissen-kompakt/alpha-version/](https://t2informatik.de/wissen-kompakt/alpha-version/) [letzte Einsicht: 05.12.23]
- Abb.2: [https://cxl.com/blog/ab-testing-guide/](https://cxl.com/blog/ab-testing-guide/) [letzte Einsicht: 05.12.23]


## Referenzen

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
- [https://www.zaptest.com/de/white-box-tests-was-es-ist-wie-es-funktioniert-herausforderungen-metriken-tools-und-mehr](https://www.zaptest.com/de/white-box-tests-was-es-ist-wie-es-funktioniert-herausforderungen-metriken-tools-und-mehr) [letzte Einsicht: 08.12.23]
- [https://www.zyxware.com/articles/4161/what-is-statement-coverage-in-testing](https://www.zyxware.com/articles/4161/what-is-statement-coverage-in-testing) [letzte Einsicht: 08.12.23]
