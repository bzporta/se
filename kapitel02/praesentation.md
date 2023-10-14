class: center, middle

## [Software Engineering](../../praesentationen.html)

#### Kapitel 2

# Verteilte Softwaresysteme - Systemarchitektur - Systemdesign

Bjarne Zaremba - Danny Meihöfer

---
# Inhalt
***

1. Einführung Verteilte Softwaresysteme

2. Systemarchitektur verteilter Softwaresysteme

3. Systemdesign

4. Zusammenfassung

5. Quellen

---

# Lernziele für dieses Kapitel 

---

# **Verteilte Softwaresysteme**

![Abb. 1: Beispiel eines verteilten Systems im Überblick ](media/verteiltesoftwaresysteme_skizze.png)

Abb. 1: Beispiel eines verteilten Systems im Überblick 

---

  
  ## **Verteilte Softwaresysteme** <br> 
  > "Ein verteiltes System ist eine Sammlung aus Computerprogrammen, die Rechenressourcen über mehrere getrennte Rechenknoten hinweg nutzen, um ein gemeinsames Ziel zu erreichen. Es wird auch als verteiltes Computing oder verteilte Datenbanken bezeichnet und stützt sich auf separate Knoten, um über ein gemeinsames Netzwerk zu kommunizieren und zu synchronisieren. Diese Knoten sind typischerweise separate physische Hardwaregeräte, sie können aber auch separate Softwareprozesse oder andere rekursive gekapselte Systeme darstellen." <br> https://www.atlassian.com/de/microservices/microservices-architecture/distributed-architecture [letzte Einsicht: 14. Oktober 2023]


---

## Eigenschaften

- Nutzung gemeinsamer Ressourcen

- Simultane Verarbeitung

- Skalierbarkeit

- Transparenz

- Heterogenität
  
---

## Vorteile verteilter Softwaresysteme

- Verbesserung der Zuverlässigkeit und Leistung eines Systems
  
- Technologieoffenheit
    
- Redundanz
    
- Geografische Verteilung
   
- Bessere Skalierbarkeit
  
- Bessere Leistung
    

---

## Nachteile verteilter Softwaresysteme

- Komplexität

- Einhaltung der Konsistenz von Daten

- Kommunikationsaufwand

⇒ Die Vorteile überwiegen den Nachteilen

---

## Wieso benötigt man verteilte Softwaresysteme?

Viele Aufgaben lassen sich auf verteilten Softwaresystemen besser ausführen, als in zentralisierten Systemen. 

Beispiel für ein verteiltes Softwaresystem: World Wide Web

- Globale Skalierbarkeit

- Ausfallsicherheit

- Lastenausgleich


Beispiel für ein zentralisiertes Softwaresystem: Kleines Büronetzwerk mit wenigen Benutzern

- Einfachheit und Kosten

- Verwaltung und Wartung

- Geringe Komplexität

---

## Distributed vs. Decentralized

![:scale 60%](media/distributedvsdecentralized.png) 

Abb. 2: Darstellung eines dezentralisierten- und verteilten Systems

---

## Unterschiede zwischen dezentralisierten- und verteilten Systemen

- Koordinierung

- Unabhängigkeit
    
- Skalierbarkeit
---

## Concurrent vs. Parallel

![:scale 100%](media/concurrentvsparallelism.png)

Abb. 3: Unterschied zwischen Concurrency und Parallelism

---

## Unterschied zwischen gleichzeitigen- und parallelen Systemen

- Ressourcen
    
- Effizienz und Leistung
    

---

### Quellen

- [https://www.atlassian.com/de/microservices/microservices-architecture/distributed-architecture](https://www.atlassian.com/de/microservices/microservices-architecture/distributed-architecture) [letzte Einsicht: 13. Oktober 2023]
- Schill, A. und Springer, T. (2012) *Verteilte Systeme: Grundlagen und Basistechnologien*. 2. Auflage. Springer.
- [https://medium.com/delta-exchange/centralized-vs-decentralized-vs-distributed-41d92d463868](https://medium.com/delta-exchange/centralized-vs-decentralized-vs-distributed-41d92d463868) [letzte Einsicht: 14. Oktober 2023]
- [https://blog.iron.io/concurrent-vs-parallel-tasks-for-a-worker-system/](https://blog.iron.io/concurrent-vs-parallel-tasks-for-a-worker-system/) [letzte Einsicht: 14. Oktober 2023]

---

### Abbildungsverzeichnis 

- Abb. 1: Schill, A. und Springer, T. (2012) *Verteilte Systeme: Grundlagen und Basistechnologien*. 2. Auflage. Springer
- Abb. 2: [https://medium.com/delta-exchange/centralized-vs-decentralized-vs-distributed-41d92d463868](https://medium.com/delta-exchange/centralized-vs-decentralized-vs-distributed-41d92d463868) [letzte Einsicht: 14. Oktober 2023]
- Abb. 3: [https://blog.iron.io/concurrent-vs-parallel-tasks-for-a-worker-system/](https://blog.iron.io/concurrent-vs-parallel-tasks-for-a-worker-system/) [letzte Einsicht: 14. Oktober 2023]
