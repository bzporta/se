# Kapitel 2 (Verteilte Softwaresysteme, Systemarchitektur verteilter Softwaresysteme, Systemdesign)

**Autoren:** Bjarne Zaremba - Danny Meihöfer

# Lernziele für dieses Kapitel

Nach diesem Kapitel sollen folgende Aspekte klarer geworden sein:
 - Was ist ein verteiltes Softwaresystem?
 - Welche Formen von verteilten Systemen gibt es? <br>
 DANNY DEINE FRAGEN
 - Was ist Skalierungsmuster? 


# **Verteilte Softwaresysteme**

![:scale 50%](media/verteiltesoftwaresysteme_skizze.png)

Abb. 1: Beispiel eines verteilten Systems im Überblick 

 **Beschreibung von Abb. 1:**

- Elektronische Handelsplattform steht dem Kunden als Webschnittstelle zur Verfügung
- Kunde führt Bestellungen, Recherche, etc. über das Internet durch
- Im Unternehmen werden diese Tätigkeiten über mehrere Server verteilt bearbeitet
- Webserver ist Zugangspunkt für den Kunden
- Webserver leitet Anfragen des Kunden an die geeigneten Application Server im Hintergrund weiter
- Auch die Kooperation mit anderen Unternehmen, z.B. eines Zulieferers, ist auch abgedeckt



## Verteilte Softwaresysteme
    
  >"Ein verteiltes System ist eine Sammlung aus Computerprogrammen, die Rechenressourcen über mehrere getrennte Rechenknoten hinweg nutzen, um ein gemeinsames Ziel zu erreichen. Es wird auch als verteiltes Computing oder verteilte Datenbanken bezeichnet und stützt sich auf separate Knoten, um über ein gemeinsames Netzwerk zu kommunizieren und zu synchronisieren. Diese Knoten sind typischerweise separate physische Hardwaregeräte, sie können aber auch separate Softwareprozesse oder andere rekursive gekapselte Systeme darstellen." (https://www.atlassian.com/de/microservices/microservices-architecture/distributed-architecture) [letzte Einsicht: 14. Oktober 2023]
    

## Eigenschaften

- Nutzung gemeinsamer Ressourcen
    - Ein verteiltes System kann Hardware, Software oder Daten gemeinsam nutzen
- Simultane Verarbeitung
    - Mehrere Rechner können dieselben Aufgaben parallel bearbeiten
- Skalierbarkeit
    - Ein verteiltes Softwaresystem kann beliebig in seiner Rechen- und Verarbeitungskapazität skaliert werden
    - Bei Bedarf kann ein verteiltes Softwaresystem sogar auf weitere Rechner ausgeweitet werden
- Transparenz
    - Ein Knoten kann auf andere Knoten im System zugreifen und mit diesen kommunizieren
    - Beispiel (s. Abb.1): Der Application Server des Unternehmens kann mit dem Application Servers des Zulieferers kommunizieren → Fehlende Materialien können einfach nachbestellt werden
- Heterogenität
    - Komponenten eines verteilten Systems können auf unterschiedlicher Hard- und Software laufen
        
        → Ermöglicht Integration verschiedener Technologien Plattformen (Beispiel: Nutzen von Linux und Windows möglich)
        


## Vorteile verteilter Softwaresysteme

- Verbesserung der Zuverlässigkeit und Leistung eines Systems
    - Engpässe und Zentrale Schwachstellen werden beseitigt
- Technologieoffenheit
    - Es können einfach mehrere Technologien und Betriebssysteme angebunden werden
- Redundanz
    - Wenn ein Knoten des Systems ausfällt, dann kann für diese Zeit ein anderer Knoten diese Aufgabe übernehmen
- Geografische Verteilung
    - Globale Verfügbarkeit und geringe Latenz durch Bereitstellung von Diensten in verschiedenen Regionen der Welt
- Bessere Skalierbarkeit
    - Ein verteiltes Softwaresystem kann problemlos an wachsende Anforderungen angepasst werden (indem z.B. mehr Server benutzt werden)
- Bessere Leistung
    - Die benötigte Rechenlast kann auf viele verschiedene Ressourcen aufgeteilt werden



## Nachteile verteilter Softwaresysteme

- Komplexität
    - Entwicklung und Wartung sind aufgrund der Verteilung deutlich komplexer
    - Bezug von Komponenten untereinander kann verloren gehen
- Einhaltung der Konsistenz von Daten
    - Die Aufrechterhaltung der Konsistenz von Daten in einem verteilten Softwaresystem kann sehr schwierig werden
    - Exkurs Konsistenz von Daten: “Als Konsistenz wird in Datenbanken die Korrektheit der dort gespeicherten Daten bezeichnet. Inkonsistente Datenbanken können zu schweren Fehlern führen, falls die darüberliegende Anwendungsschicht nicht damit rechnet” ([https://de.wikipedia.org/wiki/Konsistenz_(Datenspeicherung)](https://de.wikipedia.org/wiki/Konsistenz_(Datenspeicherung)) [letzte Einsicht: 13. Oktober 2023]
- Kommunikationsaufwand
    - Kommunikation zwischen den Komponenten über ein Netzwerk erzeugt Overhead (kann die Leistung beeinträchtigen
        
        → s. Abb1.: Jedes Mal, wenn ein Kunde nach einem Produkt sucht, muss die Anfrage über mehrere Server hinweg verarbeitet werden → Netzwerktraffic 
        

⇒ Die Vorteile überwiegen den Nachteilen


## Wieso benötigt man verteilte Softwaresysteme?

Viele Aufgaben lassen sich auf verteilten Softwaresystemen besser ausführen, als in zentralisierten Systemen. 

**Beispiel für ein verteiltes Softwaresystem: World Wide Web**

- Globale Skalierbarkeit
    - WWW hat Milliarden Benutzer
    - Es lassen sich einfach neue Server und Rechenzentren an verschiedenen globalen Standorten anschließen
- Ausfallsicherheit
    - Das WWW muss eine hohe Ausfallsicherheit bieten. Durch Verteilung wird dies ermöglicht.
- Lastenausgleich
    - Das WWW muss viele Millionen Anfragen parallel verarbeiten. Durch eine Verteilung auf viele verschiedenen Systeme wird die dort entstehende Last gut aufgeteilt

**Beispiel für ein zentralisiertes Softwaresystem: Kleines Büronetzwerk mit wenigen Benutzern**

- Einfachheit und Kosten
- Verwaltung und Wartung
- Geringe Komplexität



## Distributed vs. Decentralized

![:scale 60%](media/distributedvsdecentralized.png)

Abb. 2: Darstellung eines dezentralisierten- und verteilten Systems

### Decentralized (dt.: dezentralisiert):

- bestehen aus unabhängigen Knoten
- Knoten handeln autonom und erfordern keine zentrale Kontrolle
- Jeder Knoten ist gleichberechtigt
- Beispiel: Blockchain-Technologie

### Distributed (dt. verteilt):

- mehrere, miteinander verbundene Knoten, die untereinander kommunizieren, um eine bestimmte Aufgabe zu erfüllen
- Knoten können sich an verschiedene physischen Standorten befinden

### Unterschiede zwischen dezentralisierten- und verteilten Systemen

- Koordinierung
    - verteilte Systeme müssen zwischen einzelnen Knoten kommunizieren, während dezentralisierte Systeme dies in einem geringen Maß tun
- Unabhängigkeit
    - Bei dezentralisierten Systemen ist die Unabhängigkeit größer, während die Knoten in verteilten Systemen abhängig voneinander sind
- Skalierbarkeit
    - Beide Systeme sind skalierbar, aber die Art der Skalierbarkeit unterscheidet sich:
        - Verteilte Systeme können durch Hinzufügen weiterer Knoten erweitert werden
        - Dezentralisierte Systeme behalten die Autonomie der Knoten bei



## Concurrent vs. Parallel

![:scale 60%](media/concurrentvsparallelism.png)

Abb. 3: Unterschied zwischen Concurrency und Parallelism

### Concurrency(dt.: Gleichzeitigkeit):

- Fähigkeit eines Systems, mehrere Aufgaben gleichzeitig auszuführen
- Nur scheinbar gleichzeitig, denn das System wechselt eigentlich zwischen den Aufgaben

⇒ Aufgaben werden scheinbar gleichzeitig ausgeführt, der Prozessor wechselt aber zwischen den einzelnen Aufgaben und es scheint nur, als ob die Aufgaben gleichzeitig ausgeführt werden würden. 

### Parallelism (dt.: Parallelismus):

- Parallel bezieht sich auf die tatsächliche gleichzeitige Ausführung von Aufgaben in einem System
- In einem parallelen System arbeiten mehrere Aufgaben gleichzeitig und unabhängig voneinander
- erfordert bestimmte physische Ressourcen, wie mehrere Prozessoren oder Rechenkerne, die in der Lage sind mehrere Aufgaben gleichzeitig auszuführen
- Beispiel: Supercomputer, da diese aus einer großen Anzahl von Prozessoren bestehen, die Aufgaben gleichzeitig ausführen können


### Unterschied zwischen gleichzeitigen- und parallelen Systemen

- Ressourcen
    - Gleichzeitige Verarbeitung (concurrent) kann auf einem Prozessor betrieben werden, während parallele Verarbeitung (parallel) zwingend mehrere Prozessoren/Kerne benötigt
- Effizienz und Leistung
    - Parallel Verarbeitung bietet höhere Leistungen und Geschwindigkeiten, während gleichzeitige Verarbeitung effizienter für Anwendungen mit vielen Benutzern ist

# Systemdesign

## API Gateway vs. Proxy vs. Reverse Proxy vs. Load Balancer

### API Gateway

![Abb. 4: Beispielhafte Darstellung eines API-Gateways](media/api-gateway.png)

Abb. 4: Beispielhafte Darstellung eines API-Gateways

- Application-Programming-Interface (API)-Management-Tool
- zentraler Einstiegspunkt zwischen Anwendungsnutzer und Backend-Diensten
- hilft bei Konfiguration und Verwaltung von API Endpunkten
- schützt API-Endpunkte vor Angriffen
    - Pufferüberlauf
    - SQL-Einschleusung
    - Cross-Site-Skripting
    - Denial-of-Service
- Verbessert die API-Performance



### Proxy

![Abb. 5: Funktionsweise eines Proxy Servers](media/proxy.png)

Abb. 5: Funktionsweise eines Proxy Servers

Wie funktioniert ein Proxy?

- Agiert als Bindeglied zwischen einem Computer (vom Nutzer) und dem Internet
- vermittelt Informationen zwischen Computer und Internet
- die IP-Adresse und andere Informationen des Computers werden nicht an den Web-Server übermittelt, anstelle dessen treten die Informationen des Proxy-Servers

  ⇒ Mit einem Proxy-Server surft man sicherer im Internet, indem man keine eigenen Informationen zur Verfügung stellt. 



### Reverse-Proxy

![Abb. 6: Funktionsweise eines Reverse-Proxy-Servers](media/reverse-proxy.png)

Abb. 6: Funktionsweise eines Reverse-Proxy-Servers

Wie funktioniert ein Reverse-Proxy?

- sitzt zwischen dem Internet und vor einem oder mehreren Webservern
- bietet Schutz vor Angriffen
- Loadbalancing
- Caching

Unterschied zu normalem Proxy:

- Normaler Proxy sitzt vor dem Nutzer und sorgt dafür, dass kein Webserver jemals mit dem Nutzer direkt kommuniziert
- Ein Reverse-Proxy sitzt vor dem Webserver und sorgt dafür, dass kein Nutzer mit dem Webserver direkt kommunizieren kann



### Load-Balancer

- ein Load-Balancer (dt.: Lastenausgleicher) ist ein Netzwerkgerät, eine Softwareanwendung oder ein Dienst, der eingehenden Netzwerkverkehr auf verschiedene Server oder Rechenressourcen verteilt
    
    → Auslastung der Server soll optimiert werden
    
- werden in Rechenzentren und Netzwerken eingesetzt

Funktionen von Load-Balancern:

- Lastverteilung (Hauptzweck)
    - Netzwerkverkehr, z.B. Webanfragen gleichmäßig auf mehrere Server verteilen
- Verbesserte Verfügbarkeit
    - Loadbalancer können Server überwachen und den Netzwerkverkehr auf andere Server umleiten, falls ein bestimmter Server ausfällt
- Skalierbarkeit
    - Durch Loadbalancer ist es einfach möglich, Ressourcen zu entfernen, bzw. hinzuzufügen



## Skalierungsmuster

### Horizontale vs. vertikale Skalierung

Horizontale Skalierung (Scaling out): 

- Es werden zusätzliche Instanzen, z.B. Knoten, zu einem System hinzugefügt, um die Leistung des Systems zu erhöhen
- Einfach zu skalieren, da nur weitere Ressourcen hinzugefügt werden müssen
- Bietet natürliche Redundanz → Wenn ein Knoten ausfällt, kann ein anderer Knoten übernehmen

Vertikale Skalierung (Scaling up):

- Es werden die Ressourcen einer einzelnen Instanz erhöht, um mehr Leistung im gesamten System zu haben
    
    → durch Hinzufügen von CPU, RAM, Festplattenspeicher, etc.
    
- Komplexe Skalierbarkeit, da eventuell Hardware-Upgrades durchgeführt werden müssen
- Beschränkte Skalierbarkeit → es gibt eine natürliche Obergrenze, an der nicht mehr CPU, … hinzugefügt werden kann



### Replication

Es gibt verschiedene Skalierungsmuster in Bezug auf Replikation. Wichtig für uns ist die Anwendungsreplikation:

- In verteilten Anwendungen werden einzelne Anwendungsinstanzen repliziert werden, um Anforderungen an die Skalierbarkeit des Systems zu erfüllen.
- Loadbalancer werden verwendet, um die Last auf die replizierten Anwendungen zu verteilen



### Partitioning (dt.: Partitionierung)

Partioning im Bezug auf Systemdesign beschreibt die Aufteilung eines größeren Systems oder Anwendung in kleinere Teile oder Partitionen, die voneinander unabhängig sind.

Wichtige Aspekte des Partitionierens:

- Leistungssteigerung
    - Leistung kann gesteigert werden, da verschiedene Partitionen parallel arbeiten können
- Skalierbarkeit
    - Einzelne Teile des Systems können erweitert werden, es muss nicht gleich das ganze System vergrößert werden
- Wartbarkeit
    - kleine Partitionen sind einfacher zu warten, als ein großes System
- Kommunikation zwischen Partitionen
    - es müssen Werkzeuge erstellt werden, die eine Kommunikation unter den einzelnen Partitionen ermöglichen → z.B. durch API-Aufrufe

⇒ Partitionierung wird hauptsächlich bei sehr großen und komplexen Systemen angewendet. 



### (Datenbank-) Sharding

Beim Datenbank-Sharding geht es darum, eine große Datenbank auf meherere Knoten hinweg aufgeteilt und gespeichert wird. 

Herausforderung: Daten müssen konsistent bleiben und dürfen nicht verloren gehen. 

Vorteile von Datenbank-Sharding:

- Verbesserung der Reaktionszeit
    - das Abrufen von Daten geht bei mehreren “kleinen” Datenbanken schneller als bei einer großen Datenbank
- Skalierbarkeit
    - die Datenbank lässt sich Stück für Stück kostengünstig erweitertn
- Weniger Systemausfälle
    - Wenn ein Knoten der Datenbank ausfällt, dann fällt nicht gleich die ganze Anwendung aus, die diese Datenbank benutzt



### Load-Balancing

Technik, die in Netzwerken und Serverumgebungen eingesetzt wird, um eingehenden Datenverkehr auf mehrere Server zu verteilen. Dabei gibt es verschiedene Load-Balancing-Algorithmen:

- Round Robin
    - einfacher Algorithmus
    - Eingehende Anfragen werden einfach an den nächsten Server in der Reihe weitergeleitet
    - gleichmäßige Verteilung der Last
    - die tatsächliche Auslastung der einzelnen Server wird aber nicht berücksichtigt
- Least Connections (Least Connections First)
    - Anfragen werden an den Server weitergeleitet, der die aktuell geringste Anzahl an aktiven Verbindungen hat
    - Belastungen auf den einzelnen Servern werden ausgeglichen
- Weighted Round Robin
    - Erweiterung des Round-Robin-Algorithmus
    - den Servern werden Gewichtungen zugewiesen, Server mit einer höheren Gewichtung bekommen dementsprechend mehr Anfragen
- Weighted Least Connections
    - Erweiterung des Least-Connections-Algorithmus
    - Server bekommt Gewichtung
    - Anfragen werden an den Server mit der niedrigsten Anzahl an Verbindungen weitergeleitet, es wird aber auch die Gewichtung des Servers berücksichtigt
- IP-Hash
    - Es wird ein Hash-Wert der IP-Adresse der Anfrage gebildet
    - Verbindung wird an den Server mit dem ähnlichsten Hash-Wert weitergeleitet
    
      → Es wird sichergestellt, dass Anfragen von denselben Clients immer an denselben Server weitergeleitet werden
    
- Random
    - Zufällige Verteilung der Anfragen
- Least Bandwidth Used
    - Verbindungen werden an den Server, der die geringste Bandbreite nutzt, weitergeleitet
    - kann in Umgebungen wichtig sein, bei denen die Netzwerkbandbreite ein limitierender Faktor ist



### Caching (dt.: Zwischenspeichern)

Caching ist eine Technik, bei der Daten vorübergehend in einem schnelleren Speicherbereich gespeichert werden, um eine schnellere Verfügbarkeit zu gewährleisten.

Es gibt verschiedene Caching-Typen:

- Lokales Caching
    - Erfolgt auf Ebene des Benutzers
    - Zwischenspeichern von Daten auf dem Gerät oder innerhalb der Anwendung
    - Beispiel: Browsercache, Zwischenspeicherung in mobilen Apps
- Verteiltes Caching
    - Daten und Ressourcen werden in gemeinsam genutzten Cache-Speicherbereichen gespeichert → diese werden von mehreren Servern genutzt
    - Skalierbarkeit und Leistung werden verbessert, da häufig benötigte Daten nur einmal abgerufen werden müssen
    - Bekannte Caching-Frameworks: Redis, Memcached
- Hierarchisches Caching
    - Verwendung mehrerer Caches in einer hierarchischen Struktur
    - Zugriff auf Daten wird optimiert
    - wird oft in CDN’s eingesetzt
- Web-Caching
    - bezieht sich auf die Speicherung von HTML-Seiten, Bildern und CSS-Dateien
    - Speicherung mithilfe von Proxys, CDN’s und Webbrowsern
    - Ladezeit wird verkürzt und Serverlast verringert



### Skalierungswürfel (auch Cube Model for Scalability)

Der Skalierungswürfel wird in der Informatik benutzt, um verschiedene Arten der Skalierung von Systemen zu kategorisieren bzw. zu visualisieren.

Der Würfel hat drei Dimensionen:

- X-Achse: Horizontale Skalierung
    - es werden zusätzliche Instanzen hinzugefügt, um die Leistung eines Systems zu erhöhen
- Y-Achse: Vertikale Skalierung
    - es wird die Leistung eines Systems erhöht, indem mehr Ressourcen, wie z.B. CPU oder RAM hinzugefügt werden
- Z-Achse: Skalierung über verschiedene Dimensionen
    - Funktionale Zerlegung: Anwendung wird in verschiedene Dienste aufgeteilt, die unabhängig voneinander skaliert werden können



## Referenzen

- [https://www.atlassian.com/de/microservices/microservices-architecture/distributed-architecture](https://www.atlassian.com/de/microservices/microservices-architecture/distributed-architecture) [letzte Einsicht: 13. Oktober 2023]

- Schill, A. und Springer, T. (2012) *Verteilte Systeme: Grundlagen und Basistechnologien*. 2. Auflage. Springer.

- [https://medium.com/delta-exchange/centralized-vs-decentralized-vs-distributed-41d92d463868](https://medium.com/delta-exchange/centralized-vs-decentralized-vs-distributed-41d92d463868) [letzte Einsicht: 14. Oktober 2023]

- [https://blog.iron.io/concurrent-vs-parallel-tasks-for-a-worker-system/](https://blog.iron.io/concurrent-vs-parallel-tasks-for-a-worker-system/) [letzte Einsicht: 14. Oktober 2023]

- [https://www.softwareag.com/de_de/resources/api/article/api-gateway.html](https://www.softwareag.com/de_de/resources/api/article/api-gateway.html) [letzte Einsicht: 14. Oktober 2023]

- [https://docs.netscaler.com/de-de/citrix-application-delivery-management-service/api-gateway.html](https://docs.netscaler.com/de-de/citrix-application-delivery-management-service/api-gateway.html) [letzte Einsicht: 14. Oktober 2023]

- [https://studyflix.de/informatik/was-ist-ein-proxy-server-5962](https://studyflix.de/informatik/was-ist-ein-proxy-server-5962) [letzte Einsicht: 14. Oktober 2023]

- [https://www.cloudflare.com/de-de/learning/cdn/glossary/reverse-proxy/](https://www.cloudflare.com/de-de/learning/cdn/glossary/reverse-proxy/) [letzte Einsicht: 14. Oktober 2023]

- [https://aws.amazon.com/de/what-is/database-sharding/](https://aws.amazon.com/de/what-is/database-sharding/) [letzte Einsicht: 15. Oktober 2023]

- Es wurden Zusammenfassungen mit Chat-GPT-3.5 erstellt, um einen ersten Überblick über das Thema zu bekommen: https://chat.openai.com


## Abbildungen

- Abb. 1: Schill, A. und Springer, T. (2012) *Verteilte Systeme: Grundlagen und Basistechnologien*. 2. Auflage. Springer

- Abb. 2: [https://medium.com/delta-exchange/centralized-vs-decentralized-vs-distributed-41d92d463868](https://medium.com/delta-exchange/centralized-vs-decentralized-vs-distributed-41d92d463868) [letzte Einsicht: 14. Oktober 2023]

- Abb. 3: [https://blog.iron.io/concurrent-vs-parallel-tasks-for-a-worker-system/](https://blog.iron.io/concurrent-vs-parallel-tasks-for-a-worker-system/) [letzte Einsicht: 14. Oktober 2023]

- Abb. 4: [https://docs.netscaler.com/de-de/citrix-application-delivery-management-service/api-gateway.html](https://docs.netscaler.com/de-de/citrix-application-delivery-management-service/api-gateway.html) [letzte Einsicht: 14. Oktober 2023]

- Abb. 5: [https://studyflix.de/informatik/was-ist-ein-proxy-server-5962](https://studyflix.de/informatik/was-ist-ein-proxy-server-5962) [letzte Einsicht: 14. Oktober 2023]

- Abb. 6: [https://www.cloudflare.com/de-de/learning/cdn/glossary/reverse-proxy/](https://www.cloudflare.com/de-de/learning/cdn/glossary/reverse-proxy/) [letzte Einsicht: 14. Oktober 2023]
