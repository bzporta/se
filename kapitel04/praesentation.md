class: center, middle

## [Software Engineering](../../praesentationen.html)

#### Kapitel x

# Kapitelüberschrift

Max Mustermann

---
# Inhalt
***

1. Einführung

1. Standards

1. Softwaremessung

1. Zusammenfassung

1. Quellen

---
# Einführung

Softwaresysteme sollen "**_fit for purpose_**" sein.

- **Effizient**
- *Zuverlässig*
- Fertigstellung innerhalb eines Zeit- und Kostenrahmens

Die Techniken des Softwarequalitätsmanagements kommen ursprünglich aus der Fertigungsindustrie.

**Qualitätssicherung** ist die Definition von Prozessen und Standards, die zu qualitativ hochwertigen Produkten führen, und die Einführung dieser Qualitätsprozesse in den Fertigungsprozess.

**Qualitätslenkung** ist die Anwendung dieser Qualitätsprozesse, um Produkte auszusieben, die dem geforderten Qualitätsniveau nicht entsprechen.

---
# Einführung

Um die Prozesse in der Softwareentwicklung umzusetzen, stellen die Teams sicher, dass die zuvor festgelegten Standards und Ziele des Unternehmens mit dem Produkt übereinstimmen.

![:scale 20%](media/image.jpg)

![](media/image.jpg)


---
# Standards

Softwarestandards spielen eine wichtige Rolle im Qualitätsmanagement.

1. Standards kapseln Erfahrungen, die für das Unternehmen von großem Wert sind.

2. Standards bieten einen Rahmen für die Definition, was "Qualität" innerhalb des Softwareentwicklungsprojektes bedeutet.

3. Standards tragen zur Kontinuität bei, sodass alle Entwickler nach denselben Verfahren arbeiten.

---

# Standards

Standards müssen sich immer positiv auf die Produktqualität auswirken.

**Produktstandards** sollten dabei so entworfen werden, dass sie kosteneffizient angewendet und geprüft werden können.

**Prozessstandards** sollten die Prozesse definieren, die prüfen, dass die Produktstandards eingehalten werden.  

| Rolle | Aufgabe |
|:------:|:----------:|
| **Auftraggeber** | Erteilt den Auftrag und bezahlt das Projekt |
| **Auftragnehmer** | Nimmt die Anforderungen an das Softwareprodukt entgegen|
| **Benutzer** | Benutzen die Software. Manchmal mit Auftraggeber identisch |
| **Manager** | Treffen während des Projekts organisatorische Entscheidungen |
| **Berater** | Unterstützen den Kunden in der Definition der Anforderungen |
| **Informatiker** | Definieren und entwickeln Software in verschiedenen Rollen mit unterschiedlichen Aufgaben aufgeteilt|

---
# Softwareentwicklung

Entwicklungsmethoden:

- _Prüfen von Code, bevor er eingefügt wird:_  
  Entwickler prüfen den Code ihrer Teammitglieder, bevor der Code in die aktuelle Version eingebracht wird.

- _Probleme beheben, sobald sie auftreten:_  
  Probleme sollten sofort behoben werden, wenn sie entdeckt werden, auch wenn der Code von anderen Entwicklern stammt.

---
# Softwaremessung

Bei der Softwaremessung geht es darum, Merkmale eines Softwaresystems zu quantifizieren.

Code block:

```javascript
function add(a, b)
  return a + b
end
```

---
# Markdown

## Paragraph

Paragraph mit **strong**, *italic*, `code`.

Links so [github](https://github.com/) oder so https://github.com/ .

## Tabelle

|ID|Name|Value|
|--|----|-----|
| 1|foo |   10|
| 2|bar |   20|


---
# Aufzählung

1. Nummer 1
    - bullet 1
    - bullet 2
2. Nummer 2
    1. child 1
    2. child 2
3. Nummer 3

## Enumeration 

* A
* B

---
# Zusammenfassung

- Folien werden mit `---` voneinander abgetrennt (Achtung: kein Leerzeichen am Ende)
- Bilder, Diagramme etc. im `media`-Unterverzeichnis speichern
- Wird die Datei `remark-latest.min.js` heruntergeladen, können die Folien offline bearbeitet werden. Pfad im `script`-Tag anpassen.
- [Remark.js](https://remarkjs.com/)

---
class: center, middle

# Fragen?

---
# Quellen
***

Commands vs. Query vs. Event
https://medium.com/event-driven-utopia/using-commands-events-and-queries-in-microservices-communication-3573f1fcfafe

Synchron vs. Asynchron
https://learn.microsoft.com/en-us/dotnet/architecture/microservices/architect-microservice-container-applications/asynchronous-message-based-communication

Publish-Subscribe
https://learn.microsoft.com/en-us/azure/architecture/patterns/_images/publish-subscribe.png

RequestResponse
https://medium.com/@rohitpatil97/http-request-http-response-context-and-headers-part-iii-5c37bd4cb06b

PushPull
https://www.bwl-lexikon.de/wiki/push-pull-strategie/

https://www.alibabacloud.com/blog/pull-or-push-how-to-select-monitoring-systems_599007

---

class: center, middle

# Software system integration

---

class: center, middle

## Kommunikation

Für die Kommunikation in verteilten Systemen gibt es verschiedene Strukturen

---

### Command

Eine Aufforderung eine bestimmte Funktion auszuführen

- Der Nachrichtenproduzent erwartet, dass der Nachrichtenkonsument etwas tut
- Eventuell erwartet der Produzent eine Antwort von dem Konsumenten
- In der Aufforderung sind alle nötigen Informationen enthalten
- 

---

### Query

Eine Anfrage um Daten von einem Speicher abzurufen

- Queries können mit Parametern ausgestattet werden 
  - Filterung wie z.B. eine Suche nach "Auto blau"
- Abfragesprachen SQL, QBE und XQuery


---

### Event

Eine Nachricht über etwas, das passiert ist

- Der Nachrichtenproduzent erwartet keine Reaktion auf seine Nachricht (Auch keine Antwort)
- Andere Services können dieses Event wahrnemen und darauf reagieren
- Das Event kann mehrere Informationen enthalten
- Events sind nur eine Benachrichtigung für andere
  - Wie andere darauf reagieren ist ihre Sache

- Häufiges Kommunikationsmuster: Publish-Subscribe

---

### Command vs. Query vs. Event

Command | Query | Event
--- | --- | ---
Aufforderung etwas zu tun | Anfrage nach Daten | Benachrichtigung über etwas, das passiert ist
Erwartet eine Antwort | Erwartet eine Antwort | Erwartet keine Antwort
Typischerweise ein Empfänger | Typischerweise ein Empfänger | Typischerweise mehrere Empfänger
Commands für die Zukunft | Queries für die Gegenwart | Events für die Vergangenheit

![:scale 20%](media/commandvseventvsquery.png)

---

### Synchron (RPC)

RPC - Remote Procedure Call

- RPC ist ein Protokoll, das es einem Programm ermöglicht, eine Funktion auf einem anderen Computer auszuführen (Nach dem Client-Server-Modell)
- Synchrone Operation: Der Client wartet auf die Antwort des Servers
- Threads werden blockiert, bis die Antwort des Servers eintrifft
- (Es gibt auch asynchrone RPCs)

![:scale 20%](media/rpc.png)

---

### Asynchron 

- Asynchrone Operation: Der Client wartet nicht auf die Antwort des Servers
- Threads werden nicht blockiert, bis die Antwort des Servers eintrifft
- Der Client kann weiterarbeiten, während der Server die Anfrage bearbeitet
- Der Client kann die Antwort des Servers abrufen, wenn er sie benötigt
- Es kann sein, dass keine Antwort vom Server kommt

Üblicherweise mit Message Broker

Events sind asynchrone Nachrichten


---

class: center, middle

## Patterns

Es gibt verschiedene Patterns, die bei der Kommunikation in verteilten Systemen helfen

---

### Publish-Subscribe

- Eine Nachricht wird nach außen hin veröffentlicht (publish)
- Andere Services können sich für diese Nachricht registrieren (subscribe)
- Wenn die Nachricht veröffentlicht wird, erhalten alle registrierten Services eine Kopie der Nachricht
- Die Services können dann auf die Nachricht reagieren
- In der Regel wird ein Message Broker verwendet
  - Dieser nimmt die Nachrichten entgegen und verteilt sie an die registrierten Services

![:scale 20%](media/publishsubscribe.png)

---

### Message Queueing

Senden von Nachrichten an eine Warteschlange
- Warum? 
  - Entkopplung von Sender und Empfänger
  - Blockieren des Senders, wenn der Empfänger nicht verfügbar ist
    - Weil der Sender auf eine Bestätigung wartet
  - Pufferung von Nachrichten, wenn der Empfänger nicht verfügbar ist
  - Empfänger kann Nachrichten nach einander abarbeiten

  ![:scale 20%](media/messagequeue.jpg)

---

### Requeste-Response Model

Synchrones Kommunikationsmuster

Ein Client sendet eine Anfrage an einen Server und wartet auf eine Antwort vom Server

Webseiten laden normalerweise nach diesem Prinzip

- Oft wird die Antwort im HTTP-Format zurückgegeben
- Das Request-Response Modell ist in HTTP implementiert

![:scale 20%](media/Requestresponse.png)

---

### Push- und Pull-Modell

Push und Pull sind zwei verschiedene Methoden, um Daten zwischen zwei Systemen zu übertragen

Push | Pull
--- | ---
Das System, das die Daten sendet, ist für die Übertragung verantwortlich | Das System, das die Daten empfängt, ist für die Übertragung verantwortlich
Das System, das die Daten sendet, muss wissen, wohin und wann es die Daten senden soll | Das System, das die Daten empfängt, muss wissen, wo und wann es die Daten abrufen soll

---

### Push- und Pull-Modell

Verständnisbeispiel

![:scale 20%](media/pushpull.png)

---

### Push- und Pull-Modell

Softwarebeispiel

![:scale 20%](media/pushpullsoftware.png)

---

### Webhooks

Push-Modell

Webhooks sind eine Form der Event-basierten Kommunikation

Eine Anwendung schickt schickt eine HTTP Anfrage an eine URL, die von einer anderen Anwendung bereitgestellt wird

- Die Anfrage ist im Prinzip ein Event

Der Empfänger fängt sozusagen die Anfrage mit seiner URL ab und kann darauf reagieren

---

class: center,middle

## Protokolle

---

### gRPC

gRPC - Remote Procedure Call

Hochperformantes, offenes RPC-Framework

- Ursprünglich von Google entwickelt
- Basierend auf HTTP/2
- Unterstützt viele Programmiersprachen
- Wird z.B. von Netflix verwendet
