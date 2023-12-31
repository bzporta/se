class: center, middle

## [Software Engineering](../../praesentationen.html)

#### Kapitel 1

# Kapitelüberschrift

Danny Meihöfer - Bjarne Zaremba

---

# Inhalt

***

1. Einführung

1. Standards

1. Softwaremessung

1. Zusammenfassung

1. Quellen

---

# Verteilte Systeme

Verteilte Systeme sind Systeme, die aus mehreren Komponenten bestehen, die auf mehreren Rechnern laufen

Die Komponenten sind über ein Netzwerk verbunden

Diese Geräte teilen sich die Arbeit auf

Durch die kooperative Arbeit der Geräte können komplexe Aufgaben einfacher als mit einem einzelnen Gerät gelöst werden

Wie ist die Struktur eines verteilten Systems?

---

# Client Server

Was ist ein Client?

- Ein Client ist ein Endnutzergerät, oder eine Anwendung, die auf die Dienste, Ressourcen oder Informationen zugreift, die von einem Server bereitsgestellt werden kommuniziert
- Oft bieten Clients eine grafische Benutzeroberfläche, die es dem Benutzer ermöglicht, mit dem Server zu interagieren

Was ist ein Server?

- Ein Server ist ein Computer, oder eine Anwendung die Dienste, Ressourcen oder Informationen für Clients bereitstellt
- Server können auch mit anderen Servern kommunizieren

![:scale 20%](media/ClientServer.svg)
  
---

# Client Server Anwendungsbeispiele

Webserver

- Ein Webserver ist ein Computer, der Webseiten und andere Dateien über das HTTP-Protokoll an Clients sendet
- Webserver sind in der Regel mit einem Webhosting-Service verbunden, der die Speicherung von Dateien auf dem Server ermöglicht
- Webserver können auch nur in lokalen Netzwerken verwendet werden

Email Server

- Email Server sind Computer, die für die Verwaltung und Zustellung von E-Milas zuständig sind
- Sie empfangen, speichern und versenden E-Mails

Datenbanken

- Viele Clients können auf eine Datenbank zugreifen, um Daten zentral zu speichern und abzurufen

---

# Webanwendungen

Webanwendungen sind Anwendungen, die über einen Webbrowser aufgerufen werden können

Oft Läuft die Anwendung auf einem Server und der Browser dient als Client

Für Webanwendungen werden verschiedene Webarchitekturen verwendet

---

# Webarchitekturen

---

# Webarchitekturen - MPA

MPA - Multi-page Application

- **Eine MPA ist eine Webanwendung, die aus mehreren HTML-Seiten besteht**
- Jede Seite wird vom Server geladen, wenn der Benutzer sie anfordert
- Dadurch, dass die ganze Seite oft neu geladen werden muss, ist die Anwendung langsamer
- Die Amazone-Webseite ist ein Beispiel für eine MPA

---

# Webarchitekturen - SPA

SPA - Single-page Application

- **Eine SPA ist eine Webanwendung, die nur aus einer HTML-Seite besteht**
- Es gibt keine Neuladungen der Seite, wenn der Benutzer mit der Anwendung interagiert
- Beim ersten Aufruf der Seite wird die ganze Anwendung geladen
- Nur die upgedateten Daten werden vom Server geladen
- Dadurch ist die Anwendung schneller
- Aber die Anwendung ist komplexer zu entwickeln
- Google Maps ist ein Beispiel für eine SPA

---

# Webarchitekturen - PWA

PWA - Progressive Web Application

- **Eine PWA ist eine Webanwendung die sich wie eine native Anwendung verhält**
- Sie kann auf verschiedenen Geräten und Betriebssystemen verwendet werden
- So kann man z.B. eine PWA auf dem Smartphone installieren
- Sie kann offline verwendet werden (Meistens mit eingeschränkter Funktionalität)

- Die Performance einer PWA ist oft schlechter als die einer nativen Anwendung

- Twitter ist ein Beispiel für eine PWA

---

# Peer to Peer

Peer to Peer

- Peer to Peer ist ein dezentrales Kommunikationsmodell
- Jeder Host kann gleichzeitig Server und Client sein
- Ressourcen werden direkt von einem Host zum anderen übertragen

![:scale 20%](media/PeerToPeer.svg)
---

# Peer to Peer Anwendungsbeispiele

Filesharing

- Filesharing ist ein Prozess, bei dem Benutzer Dateien direkt von anderen Benutzern herunterladen können
- Filesharing ist ein Peer-to-Peer-Modell, da die Dateien direkt von einem Benutzer zum anderen übertragen werden

Videokonferenzen

- Videokonferenzen sind ein Peer-to-Peer-Modell, da die Daten direkt von einem Benutzer zum anderen übertragen werden
- Ein Beispiel ist Skype

---

# Event-driven Architecture

Eventgesteuerte Architektur

- **Eine eventgesteuerte Architektur ist ein Architekturmuster, bei dem die Kommunikation zwischen Komponenten durch Ereignisse / Events gesteuert wird**
- Eine Komponente sendet ein Event aus
  - Ein Event ist eine Nachricht, die angibt, dass etwas passiert ist
  - Ein Event kann Daten enthalten

- Eine andere Komponente empfängt das Event und reagiert darauf in Echzeit

![:scale 20%](media/event-driven-architecture-broker-diagram.svg)
---

# Event-driven Architecture - Vorteile

- **Skalierbarkeit und fleixibilität**
  - Die Komponenten können unabhängig voneinander skaliert und entwickelt werden
  - Die Komponenten müssen sich nicht gegenseitig kennen 
  - Die Komponenten können auf verschiedenen Servern laufen


# Event types

---

# Message Broker

Message Broker sind Softwarekomponenten, die die Kommunikation zwischen Komponenten in einer eventgesteuerten Architektur verwalten

Sie sind für die Verteilung der Events verantwortlich

Der Vorteil ist, dass die Komponenten nicht direkt miteinander kommunizieren müssen

![:scale 20%](media/event-driven-architecture-broker-diagram.svg)

---

# Message Broker Modelle

Es gibt zwei typische Message Broker Modelle
1. Publish-Subscribe
2. Point-to-Point

![:scale 20%](media/PointToPoint.JPG)

Man kann vorgefertihte Message Broker verwenden, oder einen eigenen entwickeln

Vorgefertigte Message Broker sind z.B. RabbitMQ, Apache Kafka, Apache ActiveMQ

---

# ESB - Enterprise Service Bus

Ein ESB ist eine Softwarearchitektur, die die Kommunikation zwischen Komponenten in einer eventgesteuerten Architektur verwaltet

Middleware zwischen Anwendungen

Eine ESB ist ein Message Broker, der zusätzliche Funktionen bietet

Er kann Nachrichten transformieren, filtern und routen

![:scale 20%](media/Enterprise_Service_Bus.png)


# MQ - Message Queue

Eine Message Queue ist eine Warteschlange, die Nachrichten speichert, bis sie von einer Komponente abgerufen werden

Es können also mehrer Events in einer Warteschlange gespeichert werden, die nach und nach abgearbeitet werden

Beispiel: Ein Pizzaladen. Die Bestellungen werden in einer Warteschlange gespeichert und nach und nach abgearbeitet. Die Kunden müssen nicht warten, bis eine Bestellung fertig ist, um ihre Bestellung aufzugeben.

![:scale 20%](media/MessageQueue.jpg)

---

# Modulare Architektur

- Modulare Architektur ist ein Architekturmuster, bei dem eine Anwendung in unabhängige Module unterteilt wird

- Jedes Modul hat eine eigene Funktionalität

- Die Module interagieren über Schnittstellen miteinander

- Die Module können unabhängig voneinander entwickelt werden

**Eine Anwendung besteht aus mehreren Modulen, die zusammenarbeiten**

---

# Modulare Architektur - Vorteile

- **Weiterentwicklung**
  - Die Module können unabhängig voneinander gewartet werden
  - Die Module können unabhängig voneinander getestet werden
  - Die Module können unabhängig voneinander entwickelt werden (Skalierbarkeit)

- **Wiederverwendbarkeit**
  - Die Module können in anderen Anwendungen wiederverwendet werden


---

# SOA - Serviceorientierte Architektur

- **Eine serviceorientierte Architektur ist eine Architektur, bei der die Anwendung in unabhängige Services unterteilt wird**
- Jeder Service hat eine eigene Funktionalität und ist **unabhängig** von den anderen Services
- Die Services können miteinander interagieren
- Die Services können von anderen Anwendungen verwendet werden

**Eine Anwendung besteht aus mehreren Services, die zusammenarbeiten**
**Ein Service ist eine unabhängige Anwendung**

---

# SOA - Vorteile

- **Wiederverwendbarkeit**
  - Services können wiederverwendet werden
  - Services können in anderen Anwendungen verwendet werden

- **Kapselung**
  - Services sind unabhängig voneinander
  - Services können leichter entwickelt und getestet werden

- **Skalierbarkeit**
  - Services können unabhängig voneinander skaliert werden

- **Einfache Wartung**
  - Services können leichter gewartet werden

---

# SOA - Nachteile

- **Komplexität**
  - Die Architektur ist komplexer

- **Performance**
  - Die Kommunikation zwischen den Services kann zu Performanceproblemen führen

---

# Service Discovery

Dammit Services miteinander kommunizieren können, müssen sie sich finden
- Man könnte die URLs der Services hardcoden
- Die URLs können sich aber ändern
- Es ist also besser, wenn die Services sich selbst finden

Service Discovery ist ein Prozess, bei dem Services automatisch gefunden werden

Services können sich bei einem Service Discovery Service registrieren

Andere Services können die Services über den Service Discovery Service finden

Die Service Discovery können Client- oder Serverseitig sein

Es gibt vorgefertigte Service Discovery Services, z.B. Consul, Eureka, Zookeeper

---

# Microservices

Microservices ähneln SOA

Microservices sind eine Architektur, bei der die Anwendung in unabhängige Services unterteilt wird

Jeder Service hat eine eigene Funktionalität und ist **unabhängig** von den anderen Services

Aber Microservices sind kleiner als Services in SOA

Microservices sind nicht unbedingt dafür gedacht, von anderen Anwendungen verwendet zu werden

---

# Monolith vs Distributed Monolith

Eine Monolithische Anwendung ist eine Anwendung, die aus einer einzigen Komponente besteht

Eine verteilte Monolithische Anwendung ist wie bei Microservices in mehrere Komponenten unterteilt
- Die Komponenten sind aber nicht unabhängig voneinander
- Die Vorteile von Microservices sind nicht gegeben (Skalierbarkeit, Wiederverwendbarkeit, Kapselung)
- Es kann sogar schwieriger sein, eine verteilte Monolithische Anwendung zu entwickeln, als eine Monolithische Anwendung
- Und es kann zu Performanceproblemen kommen

---

# Choreography Pattern vs Orchestration Pattern

**Wie kommunizieren die Services miteinander?**

Choreography Pattern
- Ändert sich ein Zustand in einem Service, sendet er ein Event aus
- Andere Services empfangen das Event und reagieren darauf

Vorteile:
- Unabhängigkeit der Services
- Einfache Wartung
- Dezentrale Kommunikation

Nachteile:
- Komplexität
- Nachvollziehbarkeit
- Workflows sind schwer zu implementieren

![:scale 20%](media/ChoreographyPattern.png)

---

# Orchestration Pattern

**Wie kommunizieren die Services miteinander?**

Orchestration Pattern
- Ein Service ist für die Kommunikation zwischen den Services verantwortlich
- Er sendet Nachrichten an die Services und empfängt Nachrichten von den Services
- Er kann z.B. einen Workflow definieren

Vorteile:
- Einfache Kommunikation
- Centralisierte Kommunikation
- Nachvollziehbarkeit
- Workflows sind leicht zu implementieren

Nachteile:
- Abhängigkeit der Services
- Single Point of Failure

![:scale 1%](media/OrchestrationPattern.png)

---

# Service Mesh

Ein Service Mesh lagert die Kommunikation zwischen den Services aus

Jede Art von Kommunikation zwischen den Servises muss über den Service Mesh laufen

Jeder Service hat einen Proxy, der die Kommunikation übernimmt

Über Proxys können Nachrichten gefiltert, transformiert und geroutet werden

![:scale 20%](media/Service-mesh_Medium.jpg)

---

# Verständnisfragen

1. Was sind verteilte Systeme?
2. Was ist ein Client?
3. Was ist ein Server?
4. Was ist eine Webanwendung?
5. Was für Webarchitekturen gibt es?
6. Was bedeutet Peer to Peer?
7. Was ist ein Event?
8. Was macht ein Message Broker?
9. Was ist ein ESB?
10. Was sind die Vorteile einer modularen Architektur?
11. Was sind die Unterschiede zwischen SOA und Microservices?
12. Was ist Service Discovery?
13. Was ist ein Monolith?
14. Was sind die Nachteile eines Distributed Monolith?
15. Was sind die Unterschiede zwischen Choreography Pattern und Orchestration Pattern?
16. Was ist ein Service Mesh?




---
# Quellen

***

Systemarchitekturen

<https://www.ionos.de/digitalguide/server/knowhow/client-server-modell/>

https://www.tibco.com/reference-center/what-is-event-driven-architecture#:~:text=Event%2Ddriven%20architecture%20(EDA),time%20or%20near%20real%20time.

Message Broker Bild
https://medium.com/tech-sauce/introduction-to-message-queuing-4a7ab8968b59

https://medium.com/must-know-computer-science/system-design-message-queues-245612428a22

Webarchitekturen
https://www.linkedin.com/pulse/mpa-spa-pwa-whats-difference-how-does-work-together-marek-kubacak

Modulare Architektur
https://triare.net/insights/modular-architecture-2/#:~:text=What%20is%20modular%20software%20architecture%3F,to%20explain%20in%20this%20example.

Serviceorientierte Architektur
https://saipraveenblog.wordpress.com/2014/10/06/service-discovery-in-soamsa/

ServiceDiscovery
https://www.youtube.com/watch?v=GboiMJm6WlA

Monolith vs Distributed Monolith vs Microservices
https://scoutapm.com/blog/distributed-monoliths-vs-microservices#h_268859552881644344655113

Choreography Pattern vs Orchestration Pattern
https://temporal.io/blog/to-choreograph-or-orchestrate-your-saga-that-is-the-question

https://www.linkedin.com/pulse/microservices-orchestration-vs-choreography-sachin-gupta




---
