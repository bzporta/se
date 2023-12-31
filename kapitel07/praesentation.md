class: center, middle

## [Software Engineering](../../praesentationen.html)

#### Kapitel 7

# Softwareentwurf

Danny Meihöfer - Bjarne Zaremba

---
# Inhalt
***

1. Was ist ein Softwareentwurf?
2. Die Ziele des Softwareentwurfs
3. Entwurfsprinzipien
4. SOLID-Prinzipien
5. Entwurfsmuster
6. Entkopplungsmuster
7. Entwurf des Datenmodells
8. Domain-Driven-Design
9. Entwurd der Benutzerschnittstelle
10. UI-Modelling
11. Bekannte Regeln zum UI-Modelling

---

class: center, middle

# Softwareentwurf

Laut IEEE1990: "Der Softwareentwurf ist der Prozess der Definition der Architektur, Komponenten, Schnittstellen und anderer Merkmale eines Softwaresystems"

Der Softwareentwurf ist der Bauplan für die Entwicklung einer Software

---

## Prozess

![:scale 90%](media/Waterfall_model-de.svg)

---

## Tätigkeiten im Softwareentwurf

Es gibt das Top-Level-Design und das Detailed-Design

- Top-Level-Design
  - Architektur
  - Organisation
  - Komponenten
  - Schnittstellen
  - Persistenz
  - Verteilung
  - Alles auf hohem Abstraktionsniveau

- Detailed-Design
  - Klassen
  - Methoden
  - Attribute
  - Komponenten detailiert
  - Datenstrukturen
  - Algorithmen
  - Alles auf niedrigem Abstraktionsniveau

---

## Tätigkeiten im Softwareentwurf

Für die Entwicklung eines Softwareentwurfs muss man bestimmte Fragen beantworten:

- Welche Verteilung des Systems wird benötigt?
- Welche Komponenten werden benötigt?
  - Welche Hardware wird eingesetzt?
- Welcher Persistenzmechanismus wird eingesetzt?
- Welche Schnittstellen werden benötigt?
- Welche Betriebssysteme werden unterstützt?
- Welche Programmiersprachen werden eingesetzt?
- Welche Datenstrukturen werden eingesetzt?
- Welche Algorithmen werden eingesetzt?

---

## Entwurfsziele

Das Ziel ist eine gemeinsame Basis für die Entwicklung zu schaffen

Die wichtigen technischen Zusammenhänge und Grundlagen

- Orthogonalität
- Niedrige Kopplung
- Hohe Kohäsion

---

### Orthogonalität

Orthogonalität ist ein Entwurfsprinzip

Die freie Kombinierbarkeit von Komponenten

Ändert man einen Komponenten beeinflusst das nicht die anderen Komponenten

Keine Nebeneffekte

Niedrige Kopplung - Starke Kohäsion

- Klassen verlassen sich nicht auf die Implementierung anderer Klassen
- Es werden keine globalen Daten geteilt
- Verändert man eine Klasse, so hat das keine Auswirkungen auf andere Klassen
- Einzelne Komponenten sind unabhängig und haben nur eine Aufgabe


---

### Niedrige Kopplung

Niedrige Kopplung bei Software bedeutet, dass die einzelnen Komponenten unabhängig voneinander sind

- Zwischen den Komponenten gibt es nur wenige Abhängigkeiten

Gibt es starke Abhängigkeiten kann es sein, dass man das System anders aufteilen sollte

Fokus auf die Verbindung zwischen den Komponenten

Module und Klassen wissen wenig von einander

Prozedural und Objektorientiert

---

### Niedrige Kopplung

![:scale 100%](media/losecoupling.png)

---

### Niedrige Kopplung

Prozedurale und Objekt-orientierte Programmierung sind zwei Programmierstile

Wie werden die Daten und Funktionen organisiert?

Bestimmte Programmiersprachen sind prozedural, objektorientiert, oder beides

Objektorientiert: 

- Daten und Funktionen werden in Objekten zusammengefasst
- Probleme werden durch Interaktion von Objekten gelöst
- Abstraktion von Daten und Funktionen zu Objekten
- Bezug zur realen Welt
- Typische Programmiersprachen: Java, C++, C#, Python

Prozedural:

- Daten und Funktionen werden getrennt voneinander organisiert
- Probleme werden über eine Abfolge von Anweisungen gelöst
- Typische Programmiersprachen: C, Pascal, Fortran

---

### Hohe Kohäsion

Innerhalb einer Komponente sollten die einzelnen Teile eng zusammenhängen

Nicht der Gegensatz zu niedriger Kopplung

- Eine starke Kohäsion kann auch mit einer niedrigen Kopplung einhergehen

Die Komponenten arbeiten eng zusammen um eine Aufgabe zu erfüllen

- Zu einer Komponente gehören nur die Teile, die für die Aufgabe notwendig sind

---

### Hohe Kohäsion

![:scale 75%](media/cohesioncoupling.png)

---

class: center, middle

# Entwurfsprinzipien

---

## Abstraktion 

Abstraktion ist ein Entwurfsprinzip

Verstehen durch systematische Vereinfachung

- Gewinnung von Übersicht, weglassen von Details
- Übersicht über systematische Zusammenhänge

Eine Form der Abstraktion ist z.B. ein UML-Diagramm

![:scale 60%](media/uml_beispiel.png)

---

## Modularität

Die Modularisierung ist eine der Hauptaufgaben des Softwareentwurfs

- Modul = Abgegrenzter Teil eines Systems

Eigenschaften guter Module:

- In sich geschlossen
- Ohne Kenntnis der Implementierung nutzbar
- Kommunikation über Schnittstellen
- Leicht veränderbar
- Korrekt, vollständig, eindeutig, konsistent
- Erlaubt Komposition und Dekomposition
- Kohäsion hoch, Kopplung niedrig

---

## Modularität

![:scale 100%](media/modularität.png)

---

## Law of Demeter

Das Gesetz von Demeter soll (bei vorallem objektorientierung) beschreiben was guter Codestil ist

Erfunden von Ian Holland und Karl Lieberherr

Es gibt eine Liste von Regeln, die sich darauf beziehen wie Objekte miteinander kommunizieren sollen


---

## Law of Demeter

### Regel 1

Die Methode einer Klasse soll nur auf die Methoden der eigenen Klasse zugreifen

```java
class Greetings {
    
    String generalGreeting() {
        return "Welcome" + world();
    }
    String world() {
        return "Hello World";
    }
}
```

---

## Law of Demeter

### Regel 2

Die Methode einer Klasse K soll nur Methoden von Objekten verwenden, die von der Klasse K erzeugt wurden

```java
String getHelloBrazil() {
    HelloCountries helloCountries = new HelloCountries();
    return helloCountries.helloBrazil();
}
```

---

## Law of Demeter

### Regel 3

Die Methode M sollte nur Methoden von Objekten verwenden, die als Parameter an M übergeben wurden

```java
String getHelloIndia(HelloCountries helloCountries) {
    return helloCountries.helloIndia();
}
```

---

## Law of Demeter

### Regel 4

Die Methode der Klasse K soll nur Methoden von Objekten verwenden, die als Instanzvariablen in K gespeichert sind

```java
HelloCountries helloCountries = new HelloCountries();
  
String getHelloJapan() {
    return helloCountries.helloJapan();
}
```

---

## Law of Demeter

### Regel 5

Die Methode einer Klasse K darf Methoden von Objekten verwenden, die statisch und in K definiert sind

```java
static HelloCountries helloCountriesStatic = new HelloCountries();
    
String getHellStaticWorld() {
    return helloCountriesStatic.helloStaticWorld();
}
```

---

## Dependency Injection - Inversion of Control

Mit Dependency Injection wird die Abhängigkeit zwischen zwei Komponenten aufgelöst

Abhängigkeiten werden nicht mehr in der Klasse selbst erzeugt, sondern von außen übergeben

Der Vorteil ist, dass die Klasse nicht mehr von der Implementierung der Abhängigkeit abhängt

Inversion of Control ist eng mit Dependency Injection verbunden

- Die Kontrolle über die Abhängigkeiten wird nach außen verlagert

---

## Dependency Injection - Inversion of Control

```java
class Greetings {
    
    HelloCountries helloCountries;
    
    Greetings(HelloCountries helloCountries) {
        this.helloCountries = helloCountries;
    }
    
    String generalGreeting() {
        return "Welcome" + helloCountries.world();
    }
}
```

Übergabe über Konstruktor, Setter, oder Interface

---

## Seperation of Concerns

Seperation of Concerns - Trennung von Belangen

Ein System wird in verschiedene Teile aufgeteilt

Jeder Teil hat eine eigene Aufgabe

Ein Beispiel ist die Aufteilung eines Systems in Business-Logic und UI

---

## Keep It Simple and Stupid

KISS Prinzip

Dinge sollten so simpel wie möglich gehalten werden

Code sollte so simpel und verständlich wie möglich sein

Komplexer Code ist schwerer zu verstehen und zu warten

Manchmal ist es schwerer Code einfach zu halten

- Komplexe Lösungen machen es aber schwerer den Code zu verstehen
- Erweitern
- Testen

---

## You Ain't Gonna Need It

Dieses Prinzip wird oft mit KISS in Kombination angewendet

YAGNI Prinzip

Laut dem YAGNI Prinzip sollen nur Funktionen implementiert werden, die auch wirklich benötigt werden

- Funktionen die nicht benötigt werden, werden nicht implementiert
- Funktionen die nicht benötigt werden, werden nicht erweitert
- Man beschränkt sich auf das nötigste

Code bleibt einfach und verständlich, weil es nur das nötigste gibt

---

## Don't Repeat Yourself

DRY

Ein weiteres Prinzip, das oft mit KISS und YAGNI kombiniert wird

Code sollte nicht wiederholt werden

- Funktionen sollten nicht mehrfach implementiert werden

Wird Code wiederholt, so muss er an mehreren Stellen geändert werden

- Schwer zu warten
- Schwer zu erweitern
- Schwerer zu testen
- Schwerer zu verstehen

Deshalb werden Redundanzen vermieden

---

## Composition over Inheritance

Komposition über Vererbung

Vererbung wird als eine der wichtigsten Eigenschaften von objektorientierter Programmierung angesehen

Übermäßige Nutzung von vererbung kann aber zu Problemen führen

- Vererbung ist eine starke Kopplung
- Die Klassen sind schwerer zu verstehen
- Die Klassen sind scherer zu verändern

Deshalb kann es von Vorteil sein, wenn man Vererbung durch Komposition ersetzt

Eine Klasse nutzt die Funktionalität einer anderen Klasse, ohne von ihr abzuleiten

---

## Composition over Inheritance

Vererbung:

```java
class Bird extends Animal {
    // Bird-specific code
}
```

Komposition:

```java
class Bird {
    private Animal animal;

    public Bird(Animal animal) {
        this.animal = animal;
    }

    // Bird-specific code using delegation to Animal object
}
```

---

class: center, middle

## Clean Code SOLID-Prinzipien

Die SOLID-Prinzipien sind eine Sammlung von Prinzipien, die von Robert C. Martin entwickelt wurden

Sie sollen helfen Code zu schreiben, der leicht zu verstehen, zu erweitern und zu testen ist

Sauberer Code

---

## Single Responsibility Principle

Eine Klasse hat nur eine Aufgabe

Änderungen beeinflussen möglichst nur die Klasse selbst

Will man eine Änderung vornehmen bei der man viele Klassen verändern muss erhöht sich das Fehlerrisiko

Viele kleine Klassen > Wenige große Klassen

Eine Klasse erfüllt zu viele Aufgaben wenn es mehrere Gründe gibt sie zu ändern

---

## Open-Closed Principle

Eine Klasse soll offen für Erweiterungen sein, aber geschlossen für Änderungen

- Open for extension, closed for modification

Klassen sollen so geschrieben werden, dass sie leicht erweitert werden können

Wird Code, der bereits in Benutzung ist, verändert kann das zu Fehlern führen

Die Verwendung von Vererbung und Interfaces kann helfen das Prinzip umzusetzen

---

## Das Liskovsche Substitutionsprinzip

Abgeleitete Klassen müssen sich wie ihre Basisklassen verhalten

Substitution = Ersetzung

Man sollte also eine abgeleitete Klasse anstelle der Basisklasse verwenden können

Wirft z.B. eine Methode der Basisklasse keine Exception, so muss das auch für die abgeleitete Klasse gelten

---

## Interface Segregation Principle

Interfaces sollten so klein wie möglich sein

- Ein Interface soll nur Funktionen enthalten, die end zusammen gehören

Durch zu große Interfaces wird die Kopplung erhöht

- Mehrere Klassen müssen das Interface implementieren, die nichts miteinander zu tun haben und mehr Funktionen implementieren müssen als nötig

- Verändert man einen Teil des Interfaces, so müssen alle Klassen, die das Interface implementieren, verändert werden

---

## Dependency Inversion Principle

Klassen auf hohem Abstraktionsniveau sollten nicht von Klassen auf niedrigem Abstraktionsniveau abhängen

Im besten Fall gibt es nur Abhängigkeiten zwischen Interfaces

![:scale 100%](media/dip.png)

---

## Dependency Inversion Principle

Ohne Dependency Inversion:

```java
public class EmailService{


	public void sendEmail() {
		// logic to send email
		System.out.println("Sending result through Email");
	}
}


public class SMSService {


	public void sendSMS() {
		// logic to send email
		System.out.println("Sending result through SMS");
	}
}

public class ResultPublisher {


	private SMSService smsService = new SMSService();
	private EmailService emailService = new EmailService();


	public void publishResult() {
		// need to publish result through email and sms both


		smsService.sendSMS();
		emailService.sendEmail();
	}


}
```

---

## Dependency Inversion Principle

Besser mit zwischenschicht - Dependency Inversion:

```java
public interface MessageService {

	public void sendMessage();
}

public class EmailServiceImpl implements MessageService {
	public void sendMessage() {
		// logic to send email
		System.out.println("Sending result through Email");
	}
}

public class SMSServiceImpl implements MessageService {


	public void sendMessage() {
		// logic to send SMS
		System.out.println("sending result through sms");
	}
}
```

---



# Entwurfsmuster (Design Patterns)

- bewährte Lösungsansätze für häufige, oft vorkommende Probleme in der Softwareentwicklung
- Eine Art “Vorlage” zum Lösen eines Problems
- Design Patterns fördern Flexibilität, Erweiterbarkeit und Sicherheit von Software

---

## Entkopplungsmuster

- Entwurfsmuster, die Abhängigkeiten zwischen Komponenten eines Systems verringern sollen
- Stark gekoppelte Systeme sind schwer zu verstehen, zu warten und zu warten
- Interaktion zwischen Komponenten auf “lose Art”

---

### Repository Pattern

**Entwurfsproblem:**

- wird verwendet, um Daten aus verschiedenen Quellen abzurufen, zu löschen oder zu speichern
- Datenzugriffsoperationen sollen nicht direkt im Quellcode stehen
- Datenzugriff soll gekapselt werden

**Herausforderungen, die das Repository-Pattern adressiert:**

- Entkopplung von Datenzugriffslogik
- Testbarkeit
- Wartbarkeit
- Wiederverwendbarkeit

---

**UML-Diagramm:**

![Abb.1: UML-Diagramm des Repository-Patterns](media/repositorypattern.png)

Abb.1: UML-Diagramm des Repository-Patterns

**Anwendungsbeispiele:**

- E-Commerce-Plattform


---

**Implementierungsbeispiele:**

//Live-Coding im Vortrag


---

### Plugin-Pattern

**Entwurfsproblem:**

- Erweiterbarkeit einer Anwendung soll verbessert werden
- Möglichkeit des Hinzufügens neuer Module und Funktionen, ohne dabei den bestehenden Code zu verändern
- Schaffung einer Struktur, die Funktionen modular hinzufügen kann

---

**UML-Diagramm:**

![Abb.2: UML-Diagramm des Plugin-Pattern](media/pluginpattern.png)

Abb.2: UML-Diagramm des Plugin-Pattern

- Schnittstelle “Plugin”
- Klasse “Pluginmanager”


**Anwendungsbeispiel:**

Angenommen, wir haben eine Textverarbeitungsanwendung, die um zusätzliche Funktionen erweitert werden soll. Wir könnten Plugins für Rechtschreibprüfung, Übersetzung und Textformatierung erstellen. Diese Plugins könnten unabhängig voneinander entwickelt und zur Anwendung hinzugefügt oder daraus entfernt werden, ohne den Kern der Textverarbeitungsanwendung zu beeinträchtigen.

---

Implementierungsbeispiel:

//Live-Coding im Vortrag

---

### Bridge-Pattern

**Entwurfsproblem:**

- Trennung von Abstraktion und Implementierung
- Problem: Abstrakte Klasse und Implementierung sind häufig miteinander verbunden
- Bridge-Pattern trennt Abstraktion und Implementierung


---

**UML-Diagramm:** 

![:scale 40%](media/bridgepattern.png)

Abb.3: UML-Diagramm des Bridge-Pattern

- “Abstraction”
- “Implementation”
- “ConcreteImpl”
- Beziehungen:


**Anwendungsbeispiel:**

Angenommen, wir entwickeln eine Grafikbibliothek, bei der Formen auf verschiedenen Plattformen gerendert werden sollen. Das Bridge Pattern könnte verwendet werden, um die Formen von der spezifischen Rendering-Implementierung zu entkoppeln.

---

**Implementierungsbeispiel:**

//Live-Coding

---

### Visitor-Pattern

**Entwurfsproblem:** 

- Erweiterung von Klassen um neue Operationen, ohne den Code der Klassen zu ändern
- Klassen teilen häufig gemeinsame Schnittstellen
- Neue Operationen werden durch Hinzufügen von externen Besuchern erweitert

---

**UML-Diagramm:**

![:scale 50%](media/visitorpattern.png)

Abb.4: UML-Diagramm des Visitor-Patterns

- `Visitor` (Besucher)
- `ConcreteVisitor` (Konkreter Besucher)
- `Element` (Element)
- `ConcreteElement` (Konkretes Element)


**Anwendungsbeispiel:**

Angenommen, wir haben eine hierarchieübergreifende Datenstruktur von geometrischen Formen in einer Grafikanwendung. Die Formen können Kreise, Rechtecke und Dreiecke sein. Wir möchten eine Funktionalität implementieren, die es einem Benutzer ermöglicht, die Fläche jeder Form zu berechnen, ohne den Code der Formklassen zu ändern. Hier kommt das Visitor-Pattern ins Spiel.

---

**Implementierung:**

//Vortrag:Live-Coding

---

## Entwurf des Datenmodells

- wesentlicher Schritt beim Entwurf von Softwareanwendungen
- erfordert tiefes Verständnis der Domäne
- gute Kommunikation mit den Stakeholdern erforderlich

### Domain-Driven-Design

- Methodische Herangehensweise der Softwareentwicklung


---

**Domain vs. Model**

- Domain

- Model

- Zusammenfassung


---

**Entities, Value Objects, Aggregates, Services, Factories**

- Entities

- Value Objects

- Aggregates

- Services (Dienste)

- Factories (Fabriken)

---

**Ubiquitäre Sprache**

- zentrales Konzept im DDD
- soll ein gemeinsames Verständnis zwischen allen Beteiligten schaffen
- alle beteiligten Personen sollen dasselbe Verständnis von den verwendeten Begriffen haben

**Warum ist die ubiquitäre Sprache wichtig?**

- Vermeidung von Missverständnissen
- Einheitliches Verständnis
- Effektivere Kommunikation

**Wie wird die ubiquitäre Sprache entwickelt?**

- Workshops und Meetings
- Dokumentation
- Feedback

---

**Anemic Domain Model**

- Art der Modellierung von Softwareanwendungen
- Trennung von Daten- und Geschäftslogik
- Datenklasse sind lediglich Datenstrukturen
- Geschäftslogik ist eine separate Anwendungsschicht

---

## Entwurf der Benutzerschnittstelle

### UI-Modelling

- Prozess des Entwurfs der Benutzeroberfläche (UI) einer Softwareanwendung
- Benutzerinteraktion soll effektiv und ansprechend gestaltet werden
- es gibt einige, häufig verwendete Schlüsselkonzepte

**Wireframe:**

- erster, grober Entwurf der Benutzerschnittstelle
- enthält die grundlegenden Elemente und Strukturen
- kein visuelles Design und wenig Details
- Helfen die Grundlegende Struktur zu skizzieren, bevor das visuelle Design implementiert wird

---

**Storyboard:**

- Visuelle Erzählungen, die den Ablauf von Benutzerinteraktionen über mehrere Seiten hinweg zeigen
- Illustration vom Benutzerfluss
- Hilfe bei der Visualisierung der gesamten Navigation

**Wireflows:**

- Kombination der Elemente aus Wireframes und Storyboards
- Struktur der Seiten und auch Fluss der Seiten
- helfen den Kontext der Anwendung besser zu verstehen

**Mockups:**

- Detaillierte, visuelle Darstellungen der Benutzeroberfläche mit Design, Farben und UI-Elementen
- enthalten bereits das visuelle Erscheinungsbild
- Endgültige visuelle Erscheinung soll präsentiert werden

**Prototyping**:

- Interaktive Benutzeroberfläche
- Navigation und grundlegende Funktionen sind schon enthalten
- Benutzererlebnis kann simuliert werden
- Testen der Interaktionen
- z.B. mit PowerPoint möglich

---

### Usability

- bezieht sich auf die Benutzerfreundlichkeit eines Produkts
- Wie ist es für einen Benutzer, eine bestimmte Aufgabe mit dem Produkt zu erfüllen?
- konzentriert sich auf Aspekte wie Effizienz, Effektivität und Zufriedenstellung bei der Verwendung des Produkts
- Bsp: Eine Website mit klarer Navigation und einfachen Formularen wird als “usability-freundlich” eingeordnet

---

### User Experience (UX)

- gesamte Erfahrung eines Benutzers mit einem Produkt
- Alle Aspekte
- Bsp.: Website mit klarer Navigation und ansprechenden Produktbildern → Nutzer fühlt sich wohl

---

### Customer Experience (CX)

- Alle Interaktionen, die ein Kunde mit einem Kunden hat
- geht über das Produkt hinaus und umfasst den gesamten Lebenszyklus der Kundenbeziehung
- alle Kontaktpunkte zwischen dem Kunden und dem Unternehmen
- Positive Gesamterfahrung mit dem Kunden soll gefördert werden

---

### ****Nielsen's 10 Usability Heuristic Principles für das UI-Design****

- Grundsätze für das UI-Design
- Richtlinien, mit denen die Benutzerfreundlichkeit von Schnittstellen verbessert werden kann
1. Sichtbarkeit des Systemstatus

2. Übereinstimmung von Systemen und Realität

3. Benutzerkontrolle und Freiheit

4. Konsistenz und Standards

5. Fehlervermeidung

6. Anerkennung statt Erinnerung

7. Flexibilität und Effizienz der Nutzung

8. Ästhetisches und minimalistisches Design

9. Fehlerdiagnose und Wiederherstellung

10. Hilfe und Dokumentation

---

### Shneiderman’s 8 Golden Rules

- Regeln für das UI-Design
1. Klarheit der Dialoge

2. Konsistenz

3. Rückmeldung

4. Dialogsteuerung für den Benutzer

5. Fehlervermeidung und -behandlung

6. Wiedererkennung statt Erinnerung

7. Flexibilität und Effizienz der Nutzung:

8. Ästhetik und minimalistisches Design:


---

### ****Norman's 7 Principles****

- Designer und Forscher, der 7 Prinzipien für gutes Design formuliert hat
1. Sichtbarkeit (Visibility)

2. Feedback

3. Affordanz

4. Rückgängig machen (Undo)

5. Entdeckbarkeit

6. Verständlichkeit

7. Konsistenz

---
class: center, middle

# Fragen?

---

## Lernfragen

1. Was ist ein Softwareentwurf?
2. Was sind die Ziele des Softwareentwurfs?
3. Was ist Orthogonalität im Softwareentwurf?
4. Was ist niedrige Kopplung im Softwareentwurf?
5. Was ist hohe Kohäsion im Softwareentwurf?
6. Was ist Abstraktion im Softwareentwurf?
7. Was sind die SOLID-Prinzipien?
8. Was bedeuter KISS?
9. Wie funktioniert das Repository-Pattern?
10. Was ist Domain-Driven-Design?
11. Was ist der Unterschied zwischen der Domäne und dem Modell?
12. Was ist ubiquitäre Sprache und wozu wird sie benutzt?
13. Nenne eine der 10 Regeln von Nielsen!

---

# Quellen
***

- https://www.freecodecamp.org/news/orthogonality-in-software-engineering/.

- https://media.geeksforgeeks.org/wp-content/uploads/Untitled-28.png

- https://feature-sliced.design/docs/reference/isolation/coupling-cohesion

- https://smits-net.de/images/posts/uml_beispiel.png

- https://files.ifi.uzh.ch/rerg/amadeus/teaching/courses/software_engineering_ws0506/Kapitel_05_Sw_Entwurf.pdf

- https://www.tedinski.com/2018/12/18/the-law-of-demeter.html

- https://stackify.com/dependency-injection/#:~:text=Dependency%20injection%20is%20a%20programming,inversion%20and%20single%20responsibility%20principles.

- https://t2informatik.de/wissen-kompakt/kiss-prinzip/

- https://thevaluable.dev/kiss-principle-explained/

---
# Quellen
***

- https://www.microconsult.de/blog/2019/05/fl_solid-prinzipien/

- https://de.wikipedia.org/wiki/Entwurfsmuster [letzte Einsicht: 16.11.2023]

- https://deviq.com/design-patterns/repository-pattern [letzte Einsicht: 16.11.23]

- Anwendungs- und Codebeispiele wurden von ChatGPT-3.5 erstellt: https://chat.openai.com

- https://de.wikipedia.org/wiki/Br%C3%BCcke_(Entwurfsmuster) [letzte Einsicht: 16.11.23]

- https://www.ionos.de/digitalguide/websites/web-entwicklung/was-ist-das-visitor-pattern/ [letzte Einsicht: 16.11.23]

- https://de.wikipedia.org/wiki/Besucher_(Entwurfsmuster)#:~:text=Der%20Besucher%20 [letzte Einsicht: 16.11.23]

- https://entwickler.de/ddd/einfuhrung-in-die-konzepte-von-domain-driven-design-001 [letzte Einsicht: 17.11.23]

---
# Quellen
***

- https://stackoverflow.com/questions/4166816/domain-driven-design-vs-model-driven-architecture [letzte Einsicht: 17.11.23]

- https://lostechies.com/jimmybogard/2008/05/21/entities-value-objects-aggregates-and-roots/ [letzte Einsicht: 17.11.23]

- https://entwickler.de/software-architektur/eine-gemeinsame-sprache-sprechen [letzte Einsicht: 17.11.23]

- https://en.wikipedia.org/wiki/Anemic_domain_model [letzte Einsicht: 17.11.23]

- https://www.visual-paradigm.com/guide/ux-design/wireframe-vs-storyboard-vs-wireflow-vs-mockup-vs-prototyping/ [letzte Einsicht: 17.11.23]

- https://www.usability.gov/what-and-why/user-interface-design.html [letzte Einsicht: 17.11.23]

- https://www.conductor.com/de/academy/glossar/user-experience/ [letzte Einsicht: 17.11.23]
---
# Quellen 
***

- https://www.oracle.com/de/cx/what-is-cx/ [letzte Einsicht: 17.11.23]

- https://www.nngroup.com/articles/ten-usability-heuristics/

- https://www.cybay.de/blog/die-8-goldenen-regeln-fuer-interface-design [letzte Einsicht: 17.11.23]

- https://www.educative.io/answers/what-are-normans-design-principles [letzte Einsicht: 17.11.23]

---

# Abbildungen
***
Abb.1: [https://www.infoworld.com/article/3107186/how-to-implement-the-repository-design-pattern-in-c.html](https://www.infoworld.com/article/3107186/how-to-implement-the-repository-design-pattern-in-c.html)

Abb.2: Eigene Erstellung

Abb.3: Eigene Erstellung

Abb.4: Eigene Erstellung