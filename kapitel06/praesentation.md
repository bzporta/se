class: center, middle

## [Software Engineering](../../praesentationen.html)

#### Kapitel 6

# Softwarelogik und Softwarearchitektur

Danny Meihöfer - Bjarne Zaremba

---
# Inhalt
***

1. Arten von Softwarelogik
2. Softwarearchitekturen
3. Systemarchitekturen

---

class: center, middle

# Arten von Softwarelogik

Software besteht aus verschiedenen Arten von Logik

Bestimmte Teile der Software haben verschieden Anforderungen und Aufgaben

Viele der Teile sind voneinander abhängig

---

## Domänenlogik

Die Domänen Logik (Domain Logic) ist der Teil der Software, der sich mit den Regeln in einer Domäne beschäftigt

Was ist eine Domäne?

-Eine Domäne ist ein Bereich in dem sich die Software bewegt

-Die Domäne representiert das Problem, das die Software lösen soll

Das sind Beispiele für mögliche Domänen im Gesundheitswesen:

- Patientenverwaltung, Terminplanung, Rechnungsverwaltung, etc..

Zur Domänenlogik gehören z.B. Algorithmen zur Berechnung von Werten, die in der Domäne benötigt werden

- Berechnung des Body Mass Index (BMI) eines Patienten

Im Internet ist eine Domain auch eine Adresse wie `www.google.de`


---

## Geschäftslogik

Geschäftslogik (business Logic) ist der Teil der Software, der bestimmt wie eine Software mit den Daten umgeht

Die Geschäftslogik folgt den Geschäftsregeln, um dem Workflow die das Unternehmen erwartet zu entsprechen

Geschäftsregeln Warenkorb:

- Der Kunde kann verfügbare Artikel in den Warenkorb legen
- Der Kunde kann die Anzahl der Artikel im Warenkorb ändern
- Der Kunde kann Artikel aus dem Warenkorb entfernen
- Der Preis des Warenkorbs wird automatisch berechnet
- Bestellt der Kunde, bekommt das Unternehmen eine Bestellung

In diesem Beispiel steuert die Geschäftslogik den Workflow des Warenkorbs

- Wie kann der Kunde den Warenkorb benutzen
- Welche Daten bekommt das Unternehmen bei einer Bestellung

Die Begriffe Geschäfts- und Domänenlogik werden oft synonym verwendet

---

## Präsentationslogik

Die Präsentationslogik ist der Teil der Software, der sich mit der Darstellung und Benutzerinteraktion beschäftigt

Dazu gehört zum Beispiel das erstellen einer korrekten UI

- Benutzerfreundlichkeit
- Datenanzeige/ Formatierung
- Benutzerinteraktion usw. 

---

## Steuerungslogik

Die Steuerungslogik arbeitet eng mit der Präsentationslogik zusammen

Die Algorithmen der Steuerungslogik reagieren auf Benutzerinteraktionen

Sie können aber auch automatisch ausgeführt werden

Drückt der Benutzer zum Beipiel auf einen Speichern-Button, wird die Steuerungslogik ausgeführt, die die Daten speichert

---

## Validierungslogik

Die Validierungslogik ist der Teil der Software der die Daten auf Korrektheit überprüft

Dazu gehören auch die Validierung von Benutzereingaben

Ein Beispiel könnte eine Funktion sein, die überprüft ob eine E-Mail Adresse gültig ist, indem sie das Format der E-Mail Adresse überprüft (z.B. @ Zeichen)

---

## Infrastrukturlogik

Die Infrastrukturlogik ist der Teil der Software, der sich mit der Verwaltung der Infrastruktur beschäftigt

Ressourcen der Infrastruktur sind z.B. Datenbanken, Dateisysteme, Netzwerke und Server

Diese werden über Code verwaltet (Auch Infrastructure as Code genannt (IaC))

Besonders in modernen Cloud Anwendungen ist die Infrastrukturlogik sehr wichtig

Beispielaufgaben der Infrastrukturlogik:

- Infrastukrurressourcen bereitstellen
- Skalierung
- Verbindungen zu anderen Systemen herstellen

---

### Persistenz

Persistant IaC ist eine Art der Infrastrukturlogik

Sie kümmert sich um die Verwaltung von Ressourcen, die Dauerhaft verfügbar sein müssen

Datenbanken müssen beispielsweise oft dauerhaft verfügbar sein

---

### Cache 

Die Cache Infrastrukturlogik kümmert sich um die Verwaltung von Ressourcen, die nicht dauerhaft verfügbar sein müssen

Der Cache ist eine temporäre Speicherung von Daten, die oft benötigt werden

Die Infrastrukturlogik muss dafür sorgen, dass dieser möglichst effizient genutzt wird

Beispiele für Aufgaben der Cache Infrastrukturlogik:

- Welche Daten werden gecached
- Wie lange werden die Daten gecached
- Welche Daten müssen aus dem Cache gelöscht werden
- Verteiltes Caching
- Fehlerbehandlung im Cache
- Überwachung und Optimierung
- Sicherheit

---

### Transaktion

Um Transaktionen durchzuführen benötigt eine Anwendung eine ganz eigene Infrastruktur für die Transaktionen.

Die Infrastrukturlogik muss dafür sorgen, dass die Transaktionen korrekt durchgeführt werden

Transaktionen müssen den ACID Prinzipien folgen

- Atomicity (Atomarität)
  - Vollständig, oder gar nicht
- Consistency (Konsistenz)
  - Daten müssen nach der Transaktion konsistent sein
- Isolation (Isolation)
  - Transaktionen dürfen sich nicht gegenseitig beeinflussen
- Durability (Dauerhaftigkeit)
  - Transaktionen müssen dauerhaft sein

---
class: center, middle

## Softwarearchitekturen

Die Architektur einer Software beschreibt die Struktur der Software

Sie ist kein detailierter Entwurf, sondern eine grobe Übersicht über die Komponenten und die Verbindungen zwischen ihnen

---

## Schichtenarchitektur - Layered Architecture

Eine Anwendung wird in mehrere Schichten aufgeteilt

Jede Schicht hat eine bestimmte Aufgabe

Die meisten Schichtenarchitekturen haben drei Schichten

- Client - Präsentationsschicht - UI
- Server - Logik
- Datenbank/Infrastruktur - Persistenz

Es gibt auch Architekturen mit mehr als drei Schichten

An diesem Modell erkennt man gut wie unterschiedliche Arten von Logik in einer Software zusammenarbeiten

---

## Schichtenarchitektur - Layered Architecture

![:scale 90%](media/layered-architecture.png)

---

### Schichtenarchitektur - Vor- und Nachteile

Vorteile:

- Leicht zu verstehen
- Leicht umzusetzen
- Man kann einzelne Schichten verändern

Nachteile:

- Schlechte Performance
  - Daten müssen zwischen den Schichten übertragen werden
- Schwierige Erweiterbarkeit
- Begrenzte Skalierbarkeit


---

### Azyklische Abhängigkeiten

Möchte man Komponenten unabängig voneinander entwickeln, müssen sie azyklisch sein

Das bedeutet, dass keine Komponente von einer anderen abhängig sein darf

Eine Änderung an einer Komponente darf keine Änderungen an einer anderen Komponente erfordern

Einige Abhängigkeiten sind aber unvermeidbar

Zyklische Abhängigkeiten können zu Problemen führen

- Komponenten können nicht unabhängig voneinander entwickelt werden
- Extreme erhöhung des Aufwands bei Änderungen

---

## Domänenzentrierte Software-Architekturen

- Strukturierung von Software mit Fokus auf Domäne (Geschäftsproblem)

---

### Onion-Architekur

- Spezielle Form der domänenzentrierten Architektur
- Trennung der Domänenlogik und der technischen Aspekte durch verschiedene Schichten (wie bei einer Zwiebel)
- Wartbarkeit und Testbarkeit der Software wird verbessert

![:scale 100%](media/Onion.png)

Abb. 1: Darstellung der Onion-Architektur

---

#### Schichten der Onion-Architektur

- Domänenmodell (Kern)

- Domänenservices

- Applikationsservices

- Infrastrukturschicht


---

#### Vorteile der Onion-Architektur

- Klare Trennung der Verantwortlichkeiten

- Gute Testbarkeit

- Flexibilität


---

#### Code-Beispiel der Onion-Architektur

(Live-Coding während des Vortrages)

---

### Ports and Adapters Architecture (Hexagonale Architektur)

- Architektur soll Abhängigkeiten in Softwareprojekten reduzieren
- Domänenlogik wird in den Mittelpunkt gestellt und sie von äußeren Einflüssen zu entkopppeln

![Abb. 2: Darstellung der hexagonalen Architektur](media/Hexagonal.png)

Abb. 2: Darstellung der hexagonalen Architektur

---

#### Kernlogik (Core-Logic)

- zentrale Element der hexagonalen Architektur

- Kern enthält die Domänenlogik

- Kern ist unabhängig vom Rest

- Vorteile, u.a. Flexibilität, Wartbarkeit, Verständlichkeit

---

#### Ports

- Schnittstellen oder Abstraktionen
   
- Trennen die Kernlogik klar von der “äußeren Welt”

- Verträge, mit der die Kernlogik mit externen Teilen der Anwendung kommuniziert

---

#### 2 Arten von Ports

**Inbound Ports:**

- Schnittstelle, die für die Kommunikation der äußeren Welt mit der Kernlogik verantwortlich sind

- Definition von Anfragen und Befehlen

- Beispiele: Service- und Controllerschnittstellen

```java
// Beispiel für einen Inbound Port
public interface OrderInputPort {
    void placeOrder(Order order);
}
```

→ Äußere Welt kann eine Bestellung in die Anwendung stellen

---

**Outbound Ports:**

- Schnittstelle, die den Zugriff der Kernlogik auf externe Ressourcen ermöglicht

- Definieren, wie die Kernlogik mit der Umgebung kommuniziert

- Beispiel sind Repository- und Notification-Schnittstellen

```java
// Beispiel für einen Outbound Port
public interface OrderOutputPort {
    void notifyOrderPlaced(Order order);
}
```

→ Benachrichtigung von der Kernlogik, wenn Order erfolgreich angekommen ist. Die konkrete Implementierung ist dabei aber unabhängig von der Kernlogik.

---

#### Adapters

- Konkrete Implementierungen der Ports

- Setzen die eigentliche Kommunikation zwischen Logik und äußeren Welt um

---

#### 2 Arten von Adaptern:

**Driving Adapters (Primary Adapters)**

- Interaktion mit Nutzern oder anderen Anwendungen
    - Implementierung der Inbound Ports
    - leiten Befehle an die Kernlogik weiter
    - Integration der Anwendung in externe Systeme

Beispiel:

```java
// Beispiel für einen Driving Adapter
public class OrderController implements OrderInputPort {
    private OrderService orderService;

    @Override
    public void placeOrder(Order order) {
        // Der Driving Adapter leitet die Anfrage an die Kernlogik über den OrderService weiter
        orderService.processOrder(order);
    }
}
```

→ Order Controller ist ein Driven Adapter, der die Inbound Port OrderInputPort implementiert.

---

**Driven Adapters (Secondary Adapters)**

- Kommunikation mit externen Ressourcen
    - z.B. Datenbanken, APIs, Messaging-Systeme
- Implementieren die Outbound-Ports
    - Kernlogik kann Informationen an die äußere Welt weitergeben

Beispiel:

```java
// Beispiel für einen Driven Adapter
public class DatabaseOrderRepository implements OrderOutputPort {
    @Override
    public void notifyOrderPlaced(Order order) {
        // Der Driven Adapter speichert die Bestellung in der Datenbank
        // Die konkrete Implementierungsdetails der Datenbankanbindung werden hier gehandhabt
    }
}
```

---

#### Codebeispiel der hexagonalen Architektur:

// Live-Coding im Vortrag


---

### **Clean Architecture als Realisierung der hexagonalen Architektur**

- Weiterentwicklung der hexagonalen Architektur


**Gemeinsame Prinzipien der beiden Architekturen:**

- Unabhängig von externen Details
- Trennung von Verantwortlichkeiten
- Vorhandensein von Ports und Adaptern

---

**Clean-Architektur als Weiterentwicklung:**

- Schichtenmodell
    
- Abhängigkeitsrichtung
    
- Betonung der Testbarkeit

- Bessere Erweiterbarkeit


<br>
<br>

**Fazit:**

- Clean-Architektur als konkrete Implementierung der hexagonalen Architektur
- Zusätzlich Strukturierungselemente durch das Aufteilen in Schichten
- Software soll robust, flexibel und leicht-testbar sein

---

## Abbildung der Softwarearchitektur auf die Systemarchitektur

- Beinhaltet die Strukturierung der Softwarearchitektur auf die physische Infrastruktur eines Systems

---

### Multi-Tier Architekturen

- Softwareanwendung wird in mehrere Schichten und Ebenen geteilt, um Wartbarkeit zu vereinfachen

- Unterscheidung zwischen Tier- und Layer-Schichten

---

**Tiers (Stufen):**

- Physische Ebenen und Schichten der Software

- Presentation-, Application- und Data-Tier sind häufige Tiers

- Unterscheidung zwischen Client-Side-Tiers und Server-Side-Tiers

**Layers (Schichten):**

- Logische Unterteilung der Software

- Repräsentieren verschiedene Aspekte der Software


---

#### [Zwei/Drei/Vier]-Stufen-Architektur

**2-Stufen-Architektur:**

- besteht aus 2 Haupt-Ebenen

- Beispiel: Desktop-Anwendung, bei denen die Benutzeroberfläche und die Datenbank auf einem lokalen Gerät laufen

**3-Stufen-Architektur:**

- besteht aus 3 Haupt-Ebenen

- Beispiel: Webbasierte Anwendungen


**4-Stufen-Architektur:**

- besteht aus 4 Haupt-Ebenen

- Beispiel: Umfangreiche Unternehmenssysteme

---

## Verständnissfragen

1. Was ist eine Domäne?
2. Wofür sorgen Domänen und Geschäftslogik?
3. Was hat der Benutzer mit der Präsentationslogik zu tun?
4. Was ist die Aufgabe der Steuerungslogik?
5. Warum ist die Infrastrukturlogik in modernen Cloud Anwendungen so wichtig?
6. Was ist das Schichtenmodell?
7. Nenne und beschreibe eine Schicht der Onion-Architektur!
8. Was ist ein Vorteil der Onion-Architektur?
9. Was ist der Unterschied zwischen der Onion- und der hexagonalen Architektur?
10. Was ist die Aufgabe von Ports im Zusammenhang mit der hexagonalen Architektur?
11. Wie unterscheidet sich die hexagonale Architektur von der Clean-Architektur?
12. Was sind Tiers? Was sind Layers?
13. Aus welchen Schichten besteht die 3-Stufen-Architektur?

---

# Quellen
***

https://medium.com/@mani_c/domain-logic-data-gateways-and-mapping-relationships-e7260a072c47

https://www.easytechjunkie.com/what-is-control-logic.htm?utm_content=cmp-true

https://resource.flexrule.com/knowledge-base/validation-logic/

https://www.techtarget.com/searchitoperations/definition/Infrastructure-as-Code-IAC#:~:text=Examples%20of%20infrastructure%2Das%2Dcode,Puppet%2C%20SaltStack%20and%20HashiCorp%20Terraform.

https://www.softselect.de/business-software-glossar/schichtenarchitektur#:~:text=Eine%20Schichtenarchitektur%20oder%20mehrschichtige%20Applikation,Schichten%20des%20Ganzen%20zu%20fungieren.

https://entwickler.de/software-architektur/weg-vom-schichtenmodell

https://herbertograca.com/2017/08/03/layered-architecture/

https://www.heise.de/blog/Zyklische-Abhaengigkeiten-eine-Architektur-Todsuende-4061803.html

---

# Quellen
***

https://www.innoq.com/de/blog/2018/02/ddd-mit-onion-architecture-umsetzen/

https://hashdork.com/de/onion-architecture/

Codebeispiele erstellt von Chat-GPT-3.5: https://chat.openai.com

https://entwickler.de/software-architektur/noch-ungewohnt

https://de.wikipedia.org/wiki/Hexagonale_Architektur

https://logistikknowhow.com/it-und-software/definition-des-software-architektur-prinzips-clean-architecture/

https://de.wikipedia.org/wiki/Schichtenarchitektur

---

# Abbildungen
***

Abb. 1: https://www.innoq.com/de/blog/2018/02/ddd-mit-onion-architecture-umsetzen/

Abb. 2: https://entwickler.de/software-architektur/noch-ungewohnt