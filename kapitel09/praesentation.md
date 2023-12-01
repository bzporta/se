class: center, middle

## [Software Engineering](../../praesentationen.html)

#### Kapitel 9

# Softwaresysteme

Danny Meihöfer - Bjarne Zaremba

---
# Inhalt
***

1. Was sind Systeme?
2. Systemeigenschaften
3. Systemstrukturen
4. Systemthinking
5. Software Systeme
6. Softwaresystembausteine
7. Qualitätsmerkmale von Softwaresystemen
8. Qualitätsmodelle
9. Relevante Qualitätsmerkmale im Detail
10. Metriken zur Messung von Softwarequalität
11. Modellierung und Visualisierung von Softwaresystemen
12. Softwaredokumentation mit arc42

---

class: center, middle

#  Systeme

---

## Sozioökonomische Systeme

Sozioökonomie beschäftigt sich mit dem Zusammenhang zwischen sozialem und wirtschaftlichem Verhalten

Ein Sozioökonomisches System besteht aus mehreren Komponenten

- Soziale Strukturen (z.B. Institutionen)
- Wirtschaftliche Aktivitäten (z.B. Produktion)
- Kulturelle Faktoren (z.B. Religion)
- Politische Rahmenbedingungen (z.B. Gesetze)

Die einzelnen Komponenten beeinflussen sich gegenseitig

- Eine neue Technologie kann die Wirtschaft ankurbeln
- Aber auch Arbeitsplätze schaffen, oder vernichten

Sozioökonomische Systeme sind z.B. Unternehmen und Staaten

Softwaresysteme können sozioökonomische Systeme beeinflussen

---

## Technische Systeme

Technische Systeme sind Systeme, die aus technischen Komponenten bestehen

Um bestimmte Funktionen auszuführen arbeiten die Komponenten zusammen

Komponenten können z.B. sein:
 
- Hardware
- Software
- Daten
- Prozesse
- Personen

---

## Technische Systeme

Für gewöhnlich verarbeiten technische Systeme automatisch Informationen

Es gibt technische Systeme überall. Ein paar Beispiele:

- Verkehrsleitsysteme
- Computer
- Energiesysteme
- Kommunikationssysteme

Softwaresysteme sind technische Systeme

---

## Soziale Systeme

Soziale Systeme basieren auf Verbindungen zwischen sozialen Akteuren

- Das können Personen, Gruppen, oder Organisationen sein

Das System ist durch Beziehungen, Regeln, Normen und Muster der sozialen Interaktionen definiert

Man ist Teil von mehreren sozialen Systemen

- Familie
- Freundeskreis
- Arbeitsplatz
- etc.

In jedem sozialen System unterscheidet sich die soziale Interaktion

Jedes soziale System hat seine eigenen Werte und Normen

Softwaresysteme können soziale Systeme unterstützen


---

## Natürliche Systeme

Natürliche Systeme sind Systeme, die in der Natur vorkommen

- Sie sind nicht vom Menschen geschaffen

Natürliche Systeme bestehen aus komplexen Komponenten

- Ökosysteme
- Wetter
- Klima
- Wasser
- Biologische Systeme
- etc.

Softwaresysteme können natürliche Systeme z.B. überwachen

---

class: center, middle

# Systemeigenschaften

---

## Komplizierte vs. komplexe Systeme

Komplizierte Systeme sind schwer zu verstehen

- Aber sie sind vorhersagbar
- Man kann sie immer "lösen"
- Man muss nur genug Informationen haben
- z.B. ein Auto, oder ein Mischpult

Komplexe Systeme sind unvorhersehbar

- Mehr komplexität = mehr Unberechenbarkeit
- Kein einfacher Zusammenhang zwischen Ursache und Wirkung
- Einflussfaktoren beeinflussen sich gegenseitig
- Können nicht immer "gelöst" werden
- z.B. Wetter, oder ein Ökosystem

Manchmal wird Komplex als Steigerung von Kompliziert verwendet

---

## Adaptive Systeme

Adaptive Systeme sind Systeme, die sich anpassen können

Verändert sich ihre Umgebung, verändern sie sich auch

Für gewöhnlich sind adaptive Systeme komplexe Systeme

Sie können aus Erfahrungen lernen (müssen sie aber nicht)

- z.B. das Ökosystem, Gehirn, oder das Immunsystem

Auch Softwaresysteme können adaptiv sein

- z.B. Künstliche Intelligenz

---

## Lernende Systeme

Lernende Systeme sind Systeme, die aus Erfahrungen lernen

Das Ziel ist es Informationen zu sammeln und zu verarbeiten

- Muster aus den Informationen erkennen
- Durch die Informationen kann das System seine Leistung verbessern

Machine Learning - Künstliche Intelligenz

Ein Beispiel ist ein neurales Netz, dass Bilder / Gesichter erkennen kann

- Es bekommt viele Beispielbilder und lernt daraus Muster zu erkennen
- Wenn es genug gelernt hat, kann es neue Bilder erkennen
- Leistung wird immer besser und genauer

---

## Dynamische Systeme

Dynamische Systeme verändern sich über die Zeit

- Sie sind nicht statisch

Eigenschaften können sich ständig ändern

Die Veränderungen können durch mathematische Gleichungen beschrieben werden

z.B. Wetter

---

## Selektive Systeme

Selektive Systeme, können bestimmte Informationen auswählen

Sie haben bestimmte Algorithmen und Kriterien um Informationen zu Filtern

Ein Beispiel ist ein Suchalgorithmus, oder ein Spamfilter

- Eine große Menge an Informationen wird gefiltert
- Nur die relevanten Informationen werden weitergegeben

Suchmaschinen wie Google können mit machine learning erweitert werden

Die Suchergebnisse werden immer besser

---

class: center, middle

# Systemstrukturen

Die Systemstruktur ergibt sich aus:

- den Elementen
- den Grenzen
- Kontext
- Umgebung
- Eingabe / Ausgabe

---

## System

Ein System kann ein Teilsysten (Subsystem) von einem anderen System sein

Oder ein System kann ein Supersystem von einem anderen System sein

Elemente für die Ein- und Ausgabe werden als Schnittstellen bezeichnet

Der Systemkontext beschreibt die Interaktion eines Systems mit seiner Umgebung

Es ist wichtig die Grenzen (Den Scope) eines Systems zu definieren

- Was soll entwickelt werden?
- Welche anderen Systeme / Schnittstellen müssen berückstichtigt werden?
- Welche anderen Systeme / Schnittstellen müssen NICHT berücksichtigt werden? 

---

## Systemkontext

![:scale 100%](media/syskon.PNG)

---

## Systemkontext

![:scale 100%](media/systemumgebung.png)

---

## Systemthinking

Systemthinking ist ein Denkansatz, der sich mit Systemen beschäftigt

- Es geht darum die Zusammenhänge zwischen den Elementen zu verstehen
- Ein System auf struktureller und dynamischer Ebene zu verstehen

Werkzeuge und Fragestellungen um Eigenschaften von Systemen zu verstehen

-> Lösungen für komplexe Probleme finden

---

### Werkzeuge Systemthinking

**Strukturen identifizieren / Vernetzen**

Der erste Schritt ist das identifizieren der Struktur des Systems

- Welche Elemente gibt es?
- Wie sind sie miteinander verbunden?
- Welche Grenzen hat das System?
- Welche Elemente sind innerhalb der Grenzen?
- Welche Elemente sind außerhalb der Grenzen?
- Was für Einflussfaktoren gibt es?

Die Struktur wird skizziert um ein Verständnis über die Funktionsweise des Systems zu bekommen

Beispiel: Die Zusammenhänge in der Natur

- Man möchte eine Stuhl herstellen
- Dafür muss ein Baum gefällt werden
- Der Baum wird zu Holz verarbeitet
- Das Holz wird zu einem Stuhl verarbeitet

Versteht man die Elemente in kann man besser mit dem System arbeiten

---

### Werkzeuge Systemthinking

**Emergenz**

Emergenz ist ein Phänomen, dass in komplexen Systemen auftritt

- Durch die Synergie / Vernetzung einzelner Elemente entstehen ganz neue Eigenschaften

Emergenz ist ein universales Konzept

Ein Beispiel ist ein Ameisenhaufen

- Die Ameisen sind die Elemente
- Die Ameisen kommunizieren miteinander
- Zusammen bilden sie riesige Straßennetze
- Ein Ameisenhaufen ist ein komplexes System, das weit über Fähigkeiten der einzelnen Ameisen hinausgeht

---

### Werkzeuge Systemthinking

**Synthese**

Synthese ist ein Prozess, der aus mehreren Elementen ein neues Element erzeugt

Das neue Element ist mehr als die Summe seiner Teile

Man muss die Einzelteile und die Gesamtheit verstehen

Das Gegenstück zur Synthese ist die Analyse

- Die Analyse zerlegt ein System in seine Einzelteile
- Die Synthese setzt die Einzelteile wieder zusammen

---

### Werkzeuge Systemthinking

**Feedbackschleifen**

Da alle Elemnente in einem System miteinander verbunden sind, beeinflussen sie sich gegenseitig

Immer wieder gibt es Rückkopplungen zwischen den Elementen

Eine Änderung von A beeinflusst B, was wiederum A beeinflusst

Feedbackschleifen können positiv oder negativ sein

Beispiele für sich selbst balancierende Systeme:

- Jäger und Beute
- Thermostat

Beispiele für unbalancierte Systeme:

- Überfischung

---

### Werkzeuge Systemthinking

**Kausalität**

Kausalität beschreibt die Ursache-Wirkung-Beziehung

Um Feedbackschleifen zu verstehen muss man die Kausalität verstehen

Cause -> Effect

Jedes Ereignis hat eine Ursache

- Die Ursache ist die Wirkung eines anderen Ereignisses

Man muss entschlüsseln, welche Ereignisse zu welchen Wirkungen führen

![:scale 60%](media/kaus.png)

---

### Werkzeuge Systemthinking

**Systemabbildung**

Die Systemabbildung ist eine Schlüsseltechnik des Systemthinkings

Das "mapping" ist eine grafische Darstellung des Systems

- Es zeigt die Elemente und deren Beziehungen
- Es kann aber auch nur einzelne Verhaltensweisen darstellen

![:scale 100%](media/map.png)

---

class: center, middle

# Software Systeme

---

class: center, middle

## Arten von Softwaresystemen

---

## Eingebettete Systeme

*Embedded Systems* sind spezielle Computersysteme, die in andere Systeme eingebettet sind

Sie sind Teil eines größeren Systems und erfüllen eine bestimmte Funktion

Heutzutage sind sie in fast allen elektronischen Geräten zu finden

- Autos
- Waschmaschinen
- Smartphones
- Microcontroller
- Überall

---

## Intelligentes System

Intelligente Systeme sind Systeme, die selbstständig Probleme lösen können

Sie lösen Probleme die "intelligentes" Verhalten erfordern

Sie können oft aus Erfahrungen lernen und sich anpassen

Die Fähigkeit rational zu handeln ist ein wichtiger Bestandteil

Beispiele für intelligente Systeme:

- Künstliche Intelligenz
- Expertensysteme
- Autonome Systeme
- etc.

Die Grenzen zwischen intelligenten Systemen und normalen Softwaresystemen sind fließend

---

## Informationssysteme

Informationssysteme sind Systeme, die Informationen verarbeiten

Sie sammeln, speichern, verarbeiten und verteilen Informationen

Sie sind nicht dazu da, um die Informationen anderweitig zu verarbeiten

Heutzutage sind sie überall und werden immer wichtiger (Digitalisierung)

Beispiele für Informationssysteme:

- Datenbanken
- Suchmaschinen
- Cloud Computing
- etc.

---

class: center, middle

# Softwaresystembausteine

Softwaresysteme bestehen aus vielen Komponenten

- Diese Komponenten haben verschiedene Eigenschaften und Funktionen

---

## Was für Bausteine gibt es?

**Systeme / Subsysteme** - Systeme bestehen teilweise aus anderen Systemen

**Module** - Module sind unabhängige Teile, die eine bestimmte Funktion erfüllen und wiederverwendet werden können

**Pakete** - Pakete sind eine Sammlung von Modulen, oder anderen Paketen

**Klassen / Objekte** - Objekte sind Datenstrukturen, die bestimmte Eigenschaften je nach Klasse haben

**Interface** - Interfaces sind Schnittstellen, die die Kommunikation zwischen verschiedenen Komponenten ermöglichen

**Funktion** - Funktionen sind Teile von Code, die eine bestimmte Aufgabe erfüllen

---

class: center, middle

## Qualitätsmerkmale von Softwaresystemen

Ist mein Softwaresystem gut?

---

## Innere und äußere Qualität

Innere Qualität ist die Perspektive des Entwicklers

- Codequalität
- Wartbarkeit
- Testbarkeit
- Erweiterbarkeit
- Wiederverwendbarkeit
- Verständlichkeit
- Lesbarkeit
- Architektur
- Dokumentation

Äußere Qualität ist die Perspektive des Kunden

- Einfache Verwendung
- Bedienbarkeit
- Benutzerfreundlichkeit
- Zuverlässigkeit
- Robustheit
- Fehlerfreiheit
- Sicherheit

---

## Qualitätsdreieck und Teufelsquadrat

Das Qualitätsdreieck beschreibt die Beziehung zwischen Kosten, Zeit und Qualität

![:scale 80%](media/quali.png)

---

## Qualitätsdreieck und Teufelsquadrat

Das Teufelsquadrat beschreibt die Beziehung zwischen Kosten, Zeit, Qualität und Funktionalität

![:scale 60%](media/quad1.png)

![:scale 60%](media/quad2.png)

Wird eine der Eigenschaften verändert, verändern sich auch die anderen

---

class: center, middle

## Qualitätsmodelle

Man kann die Qualität von Softwaresystemen mit verschiedenen Modellen bewerten

---

## FCM-Modelle

FCM - Factor-Criteria-Metric

Qualitätsmerkmale werden in Faktoren, Kriterien und Metriken unterteilt

FCM-Modelle sind sehr allgemein und können auf alle Softwaresysteme angewendet werden

Faktoren sind die verschiedenen Aspekte, oder Eigenschaften, die die Qualität beeinflussen

Kriterien sind Maßstäbe, oder Standards, mit denen die Faktoren bewertet werden

Metriken sind Messwerte mit denen die Kriterien bewertet werden

Das FCM-Modell hilft dabei Faktoren zu bestimmen und zu bewerten

---

## ISO 25010

ISO 25010 ist ein Qualitätsmodell, dass sich auf Softwareprodukte bezieht

Dieses Modell bestimmt eine Reihe von Qualitätsmerkmalen und deren Unterkriterien

![:scale 100%](media/iso.png)

---

## FURPS

FURPS ist ein weiteres Qualitätsmodell, dass bestimmte Qualitätsmerkmale definiert

FURPS ist ein Akronym für:

- Functionality - Funktionalität
- Usability - Benutzbarkeit
- Reliability - Zuverlässigkeit
- Performance - Leistung
- Supportability - Wartbarkeit

---

## Relevante Qualitätsmerkmale im Detail

### Complexity

- Unterscheidung zwischen inhärenter und unbeabsichtigter Komplexität

**Inhärente Komplexität:**

- Schwierigkeiten, die in einem System von Natur aus vorhanden sind
- Beispiel: Strukturelle Komplexität

**Unbeabsichtigte Komplexität:**

- entsteht durch Entscheidungen, die den Code unnötig kompliziert machen
- Reduzierung der unbeabsichtigten Komplexität nötig

---

**Cynefin-Framework:**

- entwickelt von Dave Snowden
- soll helfen den Kontext von Problemen zu verstehen
- Vier Kontextbereiche:
- Einfach
- Kompliziert
- Komplex
- Chaotisch 
- Cynefin-Framework hilft bei der Entscheidung, wie ein Problem angegangen werden sollte

---

### **Maintainability (Wartbarkeit)**

- Bedeutung für Erfolg und Anpassungsfähigkeit der Software
- Erleichtert das Durchführen von Fehlerbehebungen, Änderungen, …
- Wartbare Systeme sind kosteneffizienter zu pflegen
- Elemente der Wartbarkeit
- Verbesserung der Wartbarkeit

---

### **Observability (Beobachtbarkeit)**

- Verständnis des Systemverhaltens
- Effiziente Fehlerdiagnose
- Zuverlässigkeit

Elemente von Observability:

- Logging
- Monitoring
- Tracing

---

### Reliability (Zuverlässigkeit)

- Vorteile von Reliability

Elemente von Reliability:

- Fehlertoleranz
- Wiederherstellbarkeit
- Stabilität

Best-Practises für Reliability:

- Redunzanz
- Monitoring
- Automatisierte Tests

---

### **Availability (Verfügbarkeit)**

- Vorteile von Availability

Elemente der Avaibility:

- Lastverteilung
- Ausfallsicherheit

Best-Practices für Availability:

- Monitoring
- Automatisierung von Wiederherstellungsprozessen
- Globale Verteilung

---

### **Resilience (Widerstandsfähigkeit)**

- Fähigkeit einer Software, sich nach einem Problem zu erholen und weiter zu funktionieren
- Umgang mit Problemen in der Software, ohne dass diese komplett abstürzt

Einige Aspekte:

- Fehlererkennung
- Fehlertoleranz
- Automatisiertes Testen
- Wiederherstellbarkeit

---

### Performance

- Fähigkeit eines Systems, Ressourcen optimal zu nutzen, effektiv zu arbeiten und eine gute Benutzererfahrung zu bieten

Aspekte:

- Laufzeitgeschwindigkeit
- Ressourcennutzung
- Skalierbarkeit
- Code-Optimierung

---

## Metriken zur Messung von Softwarequalität

- Metriken werden in der Softwareentwicklung genutzt, um die Qualität von Software zu messen
- Verschiedene Arten von Metriken

---

### Konventionelle Metriken

**McCabe-Metrik:**

- auch zyklomatische Komplexität genannt
- misst die Softwarekomplexität durch Analyse des Kontrollflussgraphen

Formel zur Berechnung der zyklomatischen Komplexität:

V(G) = E - N + 2P

Bedeutung:

- E: Anzahl der Kanten im Kontrollflussgraphen
- N: Anzahl der Knoten im Kontrollflussgraphen
- P: Anzahl der Zusammenhangskomponenten (oft als Anzahl der verbundenen Bereiche im Graphen interpretiert)

Allgemein gilt:

- V(G)≤10: Niedrige Komplexität, einfacher Code
- 10<*V*(*G*)≤20: Moderate Komplexität, durchschnittlicher Code.
- *V*(*G*)>20: Hohe Komplexität, möglicherweise schwer verständlicher Code.

---

**Beispiel:** 

```java
def is_prime(n):
    if n <= 1:
        return False
    for i in range(2, n):
        if n % i == 0:
            return False
    return True
```

Hier hat der Kontrollflussgraph drei Entscheidungspunkte (zwei Verzweigungen und eine Schleife). Die Anzahl der Kanten (E) beträgt 7, die Anzahl der Knoten (N) beträgt 6, und es gibt eine Zusammenhangskomponente (P=1). Setzen wir diese Werte in die Formel ein:

*V*(*G*)=7−6+2×1=3

---

### Objektorientierte Metriken

- eignen sich, um Aspekte von objektorientiertem Code zu bewerten

**Lack of Cohesion in Methods:**

- misst das Ausmaß der Kohäsion innerhalb einer Klasse
    - Kohäsion: Methoden in einer Klasse, die auf gemeinsame Daten zugreifen

Formel für Berechnung von LCOM:

LCOM = (m-p) / (p-1)

Mit:

- m: Anzahl der Methoden in der Klasse
- p: Anzahl der Attribute, die von mindestens einer Methode verwendet werden

- Niedriger LCOM-Wert bedeutet gute Kohäsion

---

**Beispiel:**

```java
class ExampleClass:
    def method1(self, a, b):
        return a + b

    def method2(self, c, d):
        return c * d

    def method3(self, e):
        print(e)
```

---

## Modellierung und Visualisierung von Softwaresystemen

**Descriptive-Modelling**

- Beschreibung von Verhalten und Struktur eines Systems
- keine expliziten Regeln oder Vorschriften
- Beispiele: UML-Diagramme, ER-Diagramme, Zustandsdiagramme

**Rule-Based-Modellung**

- Verwendung von Regeln, um die Struktur eines Systems zu modellieren
- Beispiele: Geschäftsregeln, Workflow-Modells, Regelbasierte Systeme

---

### UML (Unified Modelling Language)

- Modellierungssprache, um Systeme zu visualisieren und zu dokumentieren
- UML besteht aus vielen verschiedenen Diagrammtypen
    

**Statische Diagrammtypen:**

- Klassendiagramme
- Objektdiagramme
- Komponentendiagramme

**Dynamische Diagrammtypen:**

- Zustandsdiagramme
- Sequenzdiagramme

---

**Zuordnung der UML-Diagrammtypen zu Phasen der Softwareentwicklung:**

1. Anforderungsanalyse und Spezifikation
    - Use-Case-Diagramme
2. Entwurfsphase
    - Klassendiagramme
    - Sequenzdiagramme
3. Implementierungsphase
    - Komponentendiagramme
4. Testphase
    - Zustandsdiagramme
    - Sequenzdiagramme

---

**Software-Architecture-Documentation**

Inhalt der Dokumentation:

- Einleitung und Ziele
- Kontext und Stakeholder
- Qualitätsziele
- Architektonische Entscheidungen
- Datenmodell
- Laufzeitsicht
- Weitere individuelle Punkte

Tools für die Dokumentation:

- UML-Diagramme
- arc42
- andere Dokumentationswerkzeuge

---

**Softwaredokumentation mit arc42**

- Framework zur Softwaredokumentation

Struktur von arc42 (Gliedert sich in 12 Hauptkapitel auf):

1. Einleitung und Ziele
2. Rahmenbedingungen
3. Lösungsstrategie
4. Grenzen
5. Qualitätsziele
6. Bereiche und Verantwortlichkeiten
7. Bausteinsicht
8. Laufzeitsicht
9. Verteilungssicht
10. Datenperspektive
11. Zuschnitt und Implementierung
12. Qualitätsanforderungen und Tests
---

# Lernfragen

1. Was sind Sozioökonomische Systeme und wie können Softwaresysteme diese beeinflussen?
2. Was ist der Unterschied zwischen natürlichen und technischen Systemen?
3. Was sind komplexe Systeme und wie unterscheiden sie sich von komplizierten Systemen?
4. Was haben adaptive Systeme mit lernenden Systemen zu tun?
5. Was sind typische Systemstrukturen?
6. Was bedeutet Systemthinking?
7. Was für Software Systeme gibt es?
8. Woraus bestehen Softwaresysteme?
9. Wie kann man die Qualität von Softwaresystemen bewerten?
10. Was ist das Cynefin-Framework?
11. Was ist Maintainability?
12. Was ist Observability?
13. Was sind konventionelle Metriken?
14. Was sind objektorientierte Metriken?
15. Was ist UML?
16. Was ist arc42?

---
# Quellen
***

- https://fluxum.substack.com/p/warum-der-unterschied-zwischen-komplex#:~:text=Komplizierte%20Systeme%20k%C3%B6nnen%20analysiert%20werden,die%20Faktoren%20sich%20gegenseitig%20beeinflussen

- https://www.riseup.ai/de/blog/adaptives-machinelles-lernen

- https://t2informatik.de/wissen-kompakt/systemkontext/#:~:text=Systemkontext%20Definition,einer%20Entwicklung%20zu%20beachten%20sind

- https://digitaleneuordnung.de/blog/system-thinking/

- https://www.eveline-lemke.de/2018/08/systems-thinking/

- https://www.studysmarter.de/schule/psychologie/hauptstroemungen-der-psychologie/emergenz/

- https://medium.com/disruptive-design/tools-for-systems-thinkers-the-6-fundamental-concepts-of-systems-thinking-379cdac3dc6a

- https://interim-cio.biz/artikel-projektsteuerung-teufelsquadrat#:~:text=Das%20Teufelsquadrat%20ist%20ein%20anschauliches,Dreieck%20macht%20das%20Modell%20unpraktikabel
---
# Quellen
***

- [https://www.objectsystems.de/die-komplexitaet-von-softwaresystemen.html](https://www.objectsystems.de/die-komplexitaet-von-softwaresystemen.html) [letzte Einsicht: 29.11.23]

- [https://www.praxisframework.org/de/knowledge/complexity](https://www.praxisframework.org/de/knowledge/complexity) [letzte Einsicht: 29.11.23]

- [https://de.wikipedia.org/wiki/Cynefin-Framework](https://de.wikipedia.org/wiki/Cynefin-Framework) [letzte Einsicht: 29.11.23]

- [https://de.wikipedia.org/wiki/Wartbarkeit](https://de.wikipedia.org/wiki/Wartbarkeit) [letzte Einsicht: 30.11.23]

- [https://www.ibm.com/de-de/topics/observability](https://www.ibm.com/de-de/topics/observability) [letzte Einsicht: 30.11.23]

- [https://www.dev-insider.de/was-ist-software-zuverlaessigkeit-a-820767/](https://www.dev-insider.de/was-ist-software-zuverlaessigkeit-a-820767/) [letzte Einsicht: 30.11.23]

- [https://en.wikipedia.org/wiki/High_availability_software](https://en.wikipedia.org/wiki/High_availability_software) [letzte Einsicht: 30.11.23]

- [https://www.bmc.com/blogs/reliability-vs-availability/](https://www.bmc.com/blogs/reliability-vs-availability/) [letzte Einsicht: 30.11.23]
---
# Quellen
***

- [https://www.iks.fraunhofer.de/en/research/resilient-software-systems.html](https://www.iks.fraunhofer.de/en/research/resilient-software-systems.html) [letzte Einsicht: 30.11.23]

- [https://www.dev-insider.de/performance-optimierung-softwareentwicklung-datenbanken-a-ac5fb659720503caf84efd7c6ee0d7bb/](https://www.dev-insider.de/performance-optimierung-softwareentwicklung-datenbanken-a-ac5fb659720503caf84efd7c6ee0d7bb/) [letzte Einsicht: 30.11.23]

- [https://www.dev-insider.de/was-ist-zyklomatische-komplexitaet-a-7fa40c670052685ff1c56d8169a79481/](https://www.dev-insider.de/was-ist-zyklomatische-komplexitaet-a-7fa40c670052685ff1c56d8169a79481/) [letzte Einsicht: 1.12.23]

- Beispiele erstellt von Chat-GPT3.5: https://www.chat.openai.com

- [https://blog.ndepend.com/lack-of-cohesion-methods/](https://blog.ndepend.com/lack-of-cohesion-methods/) [letzte Einsicht: 1.12.23]

- [https://www.infrasoft.at/images/downloads/uebersicht_der_uml_diagramme.pdf](https://www.infrasoft.at/images/downloads/uebersicht_der_uml_diagramme.pdf) [letzte Einsicht: 1.12.23]

- [https://www.arc42.de/](https://www.arc42.de/) [letzte Einsicht: 1.12.23]

- [https://www.innoq.com/en/blog/2022/08/brief-introduction-to-arc42/](https://www.innoq.com/en/blog/2022/08/brief-introduction-to-arc42/) [letzte Einsicht: 1.12.23]