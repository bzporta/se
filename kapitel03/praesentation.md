class: center, middle

## [Software Engineering](../../praesentationen.html)

#### Kapitel 3

# Versionskontrollsysteme - AI-driven development - Code-Handling

Bjarne Zaremba - Danny Meihöfer

---
# Inhalt
***

1. Versionskontrollsysteme
2. Ai-Driven-Development
3. Code-Reading
4. Bug-Report-Writing
5. Debugging
6. Agile Testing-Workflows
7. Pair-Programming
8. Code-Reviews
9. Refactoring
10. Lernfragen



---


## Lernziele für dieses Kapitel
- Was sind Versionsverwaltungssysteme?
- Was sind Remote Repositories?
- Wie benutze ich Git?
  - Was für Arbeitsabläufe gibt es?
- Was ist AI-Driven Development?

---

class: center, middle
## Version control systems

---


### Wofür braucht man Versionverwaltung?

Kollaboration
  - Teilen von Sourcecode + gemeinsames arbeiten am Sourcecode

Dokumentation
  - Protokollieren von Änderungen in Dateien/Verzeichnissen
  - Wer hat was wann geändert?

Sicherheit
  - immer eine Kompilierbare Version
  - Es existieren Sicherungskopieren
  - Wiederherstellen alter Versionen möglich

---

### Local Version Control Systems - Lokale Versionsverwaltung

- Dokumentation

- Sicherheit (mit Einschränkungen)

![:scale 60%](media/LocalVersioncontrol.png)

---

### Centralized Version Control Systems - Zentrale Versionsverwaltung

- Dokumentation

- Kollaboration

- Unterschiedliche Versionsstände nur auf zentralem Server (Repository)

- Verbindung zum Server notwendig

![:scale 60%](media/CentralizedVersionControl.png)

---

### Distributed Version Control Systems - Dezentrale Versionsverwaltung

- Dokumentation

- Kollaboration

- Sicherheit
  - Lokaler Klon
  - Keine Verbindung zum Server (Remote Repository) notwendig
  - Komplette Historie

![:scale 30%](media/DistributedVersionControl.png)

---

## GIT

- Software für Dezentrale Versionsverwaltung

- Freie Softwaresammlung (Open Source)

- Konsolenanwendung 
  - Grafische Benutzeroberfläche (GUI) verfügbar
  - Die meisten Funktionen werden über die Konsole ausgeführt

- Linux 
  - in der Regel integriert

- Windows/Mac
  - GIT SCM -> Linux Konsole enthalten

![:scale 20%](media/GitLogo.png)

---

## Git

### Eine kurze Git-Historie

- Entwicklung des Linux-Kernels
  - 1991-2002: Änderugen am Kernel wurden als Patches  verteilt
  - 2002: Einsatz von BitKeeper
  - 2005: Beziehung zwischen der Linux Community und dem kommerziellen Unternehmen, welches Bitkeeper entwickelte zerbrac. Bitkeeper war nicht mehr kostenlos
  - Linus Torvalds und die Linux Community entwickeln ein eigenes besseres BitKeeper -> Git
    - Einfache und effiziente Arbeitsweise nach dem ***KISS-Prinzip***
    - Kein zentraler Server benötigt
    - Unterstützung vieler Übertragungsprotokolle
    - Absicherung
    - Umfangreiche Arbeiten ohne Internetzugang möglich

![:scale 20%](media/GitLogo.png)

---

### Git Grundlagen

#### Anlegen eines Repositories

1. Repository erstellen mit               $ git init "verzeichniss"

2. Bestehendes Git-Repository klonen mit  $ git clone "repo"

---

### Git Grundlagen

#### git commit

- Commits sind Schappschüsse von allen getrackten Daten
- Bei jedem Commit wird ein Abbild von allen Dateien erstellt
- git commit verschiebt die Änderungen vom Staging Bereich in das lokale Repository
- Jeder Commit bekommt eine einzigartige Commit ID 
- git commit -m "Nachricht" erstellt einen neuen Commit mit der Commitnachricht

![:scale 80%](media/gitcommit.png)

---

### Git Grundlagen

#### git commit - Die commit Nachricht

Jeder Commit bekommt eine Commit Nachricht, die die Änderungen beschreibt

- Mit git commit -m ***"Nachricht"*** erstellt man einen neuen Commit mit der Commitnachricht
- Wird nicht direkt eine Nachricht angegeben, öffnet sich ein Editor in dem die Nachricht eingegeben werden kann

---

### Git Grundlagen

#### git commit - Die commit Nachricht

Für die Commit Nachricht gibt es generelle Konventionen:

- Die erste Zeile sollte eine kurze Zusammenfassung sein (max. 72 Zeichen pro Zeile)
- Nach der ersten Zeile sollte eine Leerzeile folgen
- Danach kann eine ausführlichere Beschreibung folgen (max. 72 Zeichen)
  - Die Beschreibung sollte erklären welche und warum die Änderungen gemacht wurden (nicht wie)
- Die Commit Nachricht sollte in der Gegenwartsform und im Imperativ geschrieben werden
  - "Add feature" statt "Added feature"
  - "Fix bug" statt "Fixed bug"
- Die Commits die von Git selbt erstellt werden sehen folgen diesem Schema
- Stichpunkte sind auch möglich (mit "- Info")


---
### Git Grundlagen

#### git commit - Die commit Nachricht

Welche Infos gehören in die Commit Nachricht?
- Was wurde geändert?
- Warum wurde es geändert?
- Was für Auswirkungen hat die Änderung?

Woran muss man denken?
- Der Reviewer muss die Änderungen verstehen können
- Der Reviewer kennt den Kontext nicht
- Der Code ist nicht selbsterklärend
- Die Zusammenfassung in der ersten Zeile ist am wichtigsten

Man kann die allgemeinen Guidelines hier genauer nachlesen: https://gist.github.com/robertpainsi/b632364184e70900af4ab688decf6f53

---

### Git Grundlagen

#### Lokaler Umgang mit Daten

- Working Directory
  - Abbild einer konkreten Version des Projektes an der man arbeiten kann

- Staging Area
  - Enthält die Informationen über Änderungen für den nächsten Commit

- Local Repository
  - Komprimierte Datenbank mit Historie
  - Metadaten (Wer, was, etc.)
  - Commited
    - Alles was Commited ist, ist sicher in der Datenbank gespeichert 

---

### Git Grundlagen

#### Lokaler Umgang mit Daten

![:scale 80%](media/localrepo.png) 

---

### Git Grundlagen

#### Umgang mit Remote Repository

![:scale 100%](media/RemoteRepo.png)

---

### Git Grundlagen

#### Umgang mit Remote Repository

git add "file" | git add . 

- Mit git add werden ungetrackte Dateien dem Staging Bereich hinzugefügt

git push "remote" "branch" | git push

- Mit git push werden die Änderungen vom lokalen Repository auf das Remote Repository übertragen

git pull "remote" "branch" | git pull

- Mit git pull werden die Änderungen vom Remote Repository auf das lokale Repository übertragen

git fetch "remote" "branch" | git fetch

- Mit git fetch werden die Änderungen vom Remote Repository auf das lokale Repository übertragen

---

### Git Grundlagen 

#### git diff

- git diff "commit1" "commit2" | git diff "commit" | git diff

- Der diff Befehl zeigt Änderungen zwischen commits und zwischen dem Working Directory und der Staging area

- Es können zum Beispiel die codes der zu vergleichenen commits als Argumente mit gegeben werden

![:scale 70%](media/gitdiff.png)

---

### Git Grundlagen

#### git checkout

- git checkout "commit" | git checkout "branch"
- Mit dem Checkout-Befehl kopiert man die Dateien eines beliebigen Commits in den eigenen Workspace.
- Man kann auch zu Commits von anderen Branches wechseln
- Als Befehlsargumente kann man entweder die Namen der Tags, der Branches, oder die ID des Commits angeben
- Außerdem können bestimmte Dateien eines Commits geladen werden, wenn man die Dateinamen angibt

![:scale 60%](media/gitcheckout.png)

---

### Git Grundlagen

#### git reset

- git reset "commit" | git reset --soft "commit" | git reset --mixed "commit" | git reset --hard "commit"
- git reset verschiebt den Zeiger des aktuellen Branches auf einen anderen Commit
- Es gibt drei verschiedene Modi
  - --soft
    - Der Zeiger wird verschoben, aber die Änderungen bleiben im Staging Bereich
  - --mixed
    - Der Zeiger wird verschoben und die Änderungen werden aus dem Staging Bereich entfernt
  - --hard
    - Der Zeiger wird verschoben und die Änderungen werden aus dem Staging Bereich entfernt und aus dem Workspace gelöscht

---

### Git Grundlagen

#### git reset

![:scale 90%](media/gitreset.JPG)

---

### Git Grundlagen

#### git merge

- git merge "branch" | git merge "commit"
- git merge erzeugt einen neuen Commit, der die Änderungen mehrerer Commits zusammenführt
- Merge-Konflikte entstehen wenn zwei Commits die gleiche Datei verändern
- Merge-Konflikte werden versucht automatisch zu lösen, wenn das nicht möglich ist, muss der Nutzer die Konflikte manuell lösen

- Es gibt zwei verschiedene Modi
  - Fast-Forward
    - Die Commits werden einfach hintereinander gehängt
    - Nur möglich wenn ein linearer Commit-Verlauf vorliegt
  - 3-Way-Merge
    - Es wird ein neuer Commit erzeugt, der die Änderungen der beiden zu mergenden Commits zusammenführt

---

### Git Grundlagen

#### git merge

Ein Branch

![:scale 40%](media/gitmerge1.jpg)

Zwei Branches

![:scale 40%](media/gitmerge2.jpg)

---

### Git Grundlagen

#### git Cherry pick

- git cherry-pick "commit"
- git cherry-pick erzeugt einen neuen Commit, der die Änderungen eines anderen Commits übernimmt
- Damit kann man einzelne Commits aus anderen Branches übernehmen

![:scale 90%](media/gitcherrypick.jpg)

---

### Git Grundlagen

#### git rebase

- git rebase "branch"
- git rebase verschiebt die Commits eines Branches auf einen anderen Branch
- Alternative zu git merge 
- Erzeugt einen linearen Commit-Verlauf

![:scale 90%](media/gitrebase.jpg)

---

### Git Grundlagen

#### git branch

git branch "name" | git branch

Arbeiten mehrere Entwickler an einem Projekt, ist es sinnvoll, dass für jeden Entwickler, oder für jedes Feature ein eigener Branch erstellt wird.

Jeder Branch hat eine eigene Historie und beeinträchtigt die anderen nicht

- git branch "name" erstellt einen neuen Branch mit dem gewünchten Namen
- git branch zeigt alle Branches an

---

### Git Grundlagen

#### git branch

![:scale 100%](media/gitbranch.svg)


---

### Git Grundlagen

#### git switch

- git switch "branch"
- git switch wechselt den aktuellen Branch
- git switch -c "branch" erstellt einen neuen Branch und wechselt zu diesem

Switch ist eine neuere Version von checkout

---
class: center, middle

## Multirepos vs. Monorepos
Zwei verschiedene Ansätze zur Verwaltung von Sourcecode

![:scale 100%](media/monovsmultirepo.png)

---

### Multirepos

- Ein Projekt besteht aus mehreren Repositories
- Ein Repository enthält nur einen Teil des Projektes
- Im Extremfall haben alle Bibliotheken und Dienste ein eigenes Repository
- Das Projekt wir in mehrere Projekte aufgeteilt

![:scale 100%](media/multirepo.png)

---

### Multirepos

#### Vorteile

- Jedes Repository kann unabhängig und isoliert von den anderen Repositories entwickelt werden
- Versionen können unabhängig voneinander veröffentlicht werden
- Zugriffsrechte können für jedes Repository einzeln vergeben werden

#### Nachteile

- Abhängigkeiten zwischen den Repositories müssen verwaltet werden
- Die Abhängigkeiten müssen in den Repositories dokumentiert werden
- Die Teams sind getrennt und müssen sich absprechen

---

### Monorepos

- Ein Projekt besteht aus einem Repository
- Alle Teile des Projektes werden in einem Repository verwaltet
- Im Extremfall ist das gesamte Projekt in einem Repository

![:scale 60%](media/monorepo.png)

---

### Monorepos 

#### Vorteile

- Alle Teile des Projektes sind in einem Repository
- Über ein Repository hat man Zugriff auf das gesamte Projekt und alle Abhängigkeiten
- Einsicht in das gesamte Projekt
- Issues können über das gesamte Projekt hinweg verfolgt werden
- Teams können sich besser absprechen

#### Nachteile

- Langsamere Entwicklungszyklen
  - Einzelne Teile des Projektes können nicht unabhängig voneinander veröffentlicht werden
- Zugriffsrechte können nur für das gesamte Projekt vergeben werden
- Erfordert eine gute Strukturierung des Projektes
- Erfordert den Download des gesamten Projektes

---

### Submodules

- Submodules sind Repositories, die in einem anderen Repository eingebunden sind
- Der Inhalt des Submodules wird in einem Unterordner des Hauptrepositories gespeichert
- Der Vorteil ist die Trennung der Repositories
  - Zwei Repositories funktionieren miteinander
  - Wird ein Commit in einem Repository gemacht, wird das andere Repository nicht automatisch aktualisiert
  - Getrennte Versionsgeschichte
  - Einfaches aktuallisieren des Submodules
  - Vorteil für das Einbinden von Tools und Bibliotheken

- Wie füge ich ein Submodule hinzu?
  - git submodule add "url"

---

### Pull requests

- Pull requests sind Features von Git-Hosting-Plattformen wie z.B. GitHub oder GitLab
- Arbeitet man an einem Projekt mit mehreren Entwicklern, auf verschiedenen Branches ist es sinnvoll, dass die Änderungen von anderen Entwicklern vor dem Zusammenführen geprüft werden

Prozess:
1. Entwickler erstellt einen neuen Branch
2. Entwickler arbeitet an dem Branch
3. Entwickler erstellt einen Pull Request
4. Der Entwickler und andere Entwickler prüfen den Pull Request
5. Der Pull Request wird akzeptiert und der Branch wird in den Master gemerged, oder der Pull Request wird abgelehnt und der Branch wird nicht gemerged

---

class: center, middle

## Branching Strategien
Bekannte Branching Strategien für die Entwicklung mit Git im Überblick

---

## Branching Strategien

### Trunk Based Development

- Es gibt nur einen Branch
- Alle Entwickler arbeiten auf dem Branch
- Es gibt keine, oder maximal sehr kleine extra Branches für Features
- Es gibt keine Branches für Releases
- Es wird häufig commited und gepusht

![:scale 70%](media/trunkbased.png)

---

## Branching Strategien

### Trunk Based Development

#### Vorteile

- Einfach zu verstehen
- Nicht so große Konflikte beim Zusammenführen von Branches, da öfter zusammengeführt wird
- Kleine Änderungen können schnell veröffentlicht werden

#### Nachteile

- Keine, oder wenig Isolation von Features
  - Komplexe Features können nicht unabhängig voneinander entwickelt werden
- Keine, oder wenig Isolation von Releases
- Wenig experimentieren
  - Neue Features können nicht einfach ausprobiert werden

---

## Branching Strategien

### Long Lived Branches

- Es gibt einen Master Branch
- Von dem Master Branch werden für jedes Feature Branches abgezweigt
- Die Features werden wenn sie fertig sind in den Master Branch gemerged
- Mehrere Features können gleichzeitig entwickelt werden
- Viele Branching Strategien basieren auf dieser Strategie

---

## Branching Strategien

### Long Lived Branches

#### Vorteile

- Isolation von Features
  - Features können unabhängig voneinander entwickelt werden
- Isolation von Releases
- Große Änderungen können in einem Branch entwickelt werden, ohne den Master Branch zu beeinträchtigen

#### Nachteile

- "Merge Hell" Große Konflikte beim Zusammenführen von Branches
- Lange Entwicklungszyklen
  - Features können erst veröffentlicht werden, wenn sie fertig sind
- Kommunikation zwischen den Entwicklern ist wichtig
  - Es kann passieren, dass zwei Entwickler an dem gleichen Feature arbeiten, oder andere Missverständnisse entstehen
- Unübersichtlich wenn viele Branches existieren

---

## Branching Strategien

### Git Flow

- Git Flow ist eine Branching Strategie, die auf Long Lived Branches basiert
- Zusammenspiel aus: 
  - Feature Branches
  - Release Branches
  - Hotfix Branches
  - Master Branch
  - Develop Branch

**Wie sieht das aus?**

---

## Branching Strategien

### Git Flow

![:scale 70%](media/gitflow.png)

---

## Branching Strategien

### Github Flow

- Github Flow ist eine Simplere alternative zum Git Flow
- Er wird oft für kleinere Teams und Projekte verwendet
- Nur Master Branch + Feature Branches
- Feature Branches werden direkt in den Master Branch gemerged
- Releases werden direkt vom Master Branch abgezweigt und mit einem Tag versehen
- Hotfixes werden direkt in den Master Branch gemerged

Wie sieht das aus?
---

## Branching Strategien

### Github Flow

![:scale 70%](media/Githubflow.jpg)

---
class: center, middle

## Merging Strategien
Um die Zusammenführung von Branches zu vereinfachen, gibt es verschiedene Merging Strategien

---

## Merging Strategien

### Merge Commit

git merge "branch" | git merge "commit"

Der Merge Commit ist die Standard Merge Strategie von Git
- Es wird ein neuer Commit erzeugt, der die Änderungen der beiden zu mergenden Branches zusammenführt
- Merge-Konflikte werden versucht automatisch zu lösen, wenn das nicht möglich ist, muss der Nutzer die Konflikte manuell lösen
- Die Historie beider Branches bleibt erhalten

Before | After 
--- | ---
![:scale 70%](media/mergebefore.png) | ![:scale 70%](media/mergeafter.png)

---

## Merging Strategien

### Fast Forward

- Fast Forward bedeutet, dass die Commits eines Branches einfach hintereinander gehängt werden
- Ist nur möglich wenn ein linearer Commit-Verlauf vorliegt

Before | After 
--- | ---
![:scale 130%](media/fastbefore.png) | ![:scale 130%](media/fastafter.png)

---

## Merging Strategien

### Squash and Merge

git merge --squash "branch" | git merge --squash "commit"

- Squash and Merge ist eine Merge Strategie von GitHub
- Es wird ein neuer Commit erzeugt, der die Änderungen der beiden zu mergenden Branches zusammenführt
- **Alle Commits des zu mergenden Branches werden zu einem Commit zusammengefasst**
  - Nicht wie beim Rebase
  - Historie geht verloren

---

## Merging Strategien

### Squash and Merge

![:scale 100%](media/mergesquash.png)

---

## Merging Strategien

### Rebase und Merge

- Wenn man viele Branches hat, kann es passieren, dass die Historie sehr unübersichtlich wird

![:scale 60%](media/mergemania.JPG)

---

## Merging Strategien

### Rebase und Merge

git rebase "branch" | git rebase "commit" 

- git rebase master verschiebt die Commits auf dem aktuellen Branch auf den Master Branch
- Üblicherweise sowas wie git checkout feature; git rebase master

- Rebase und Merge ist eine Merge Strategie von GitHub

- Die Historie wird linearisiert (Eine Linie)

- Alle Commits des zu mergenden Branches werden an den anderen Branch angehängt

- Optional mit Squash and Merge kombinierbar

---

## Merging Strategien

### Rebase und Merge

Mit normalem Merge | Mit Rebase und Merge
--- | ---
![:scale 60%](media/mergenormal.jpg) | ![:scale 60%](media/mergerebase.png)

---
class: center, middle

## AI-driven development

---

## AI-driven development

### Was ist AI-driven development?

Künstliche Intelligenz (KI) ist ein Teilgebiet der Informatik, welches sich mit der Automatisierung intelligenten Verhaltens und dem maschinellen Lernen befasst

AI-driven development ist die Anwendung von KI in der Softwareentwicklung

Was können die AI-Tools?
- Code generieren
- Code analysieren
  - Fehler finden
  - Code verbessern
  - Code dokumentieren
  - Code optimieren
- Code testen
- Code übersetzen (z.B. von Java nach C#)

---

## AI-driven development

### Conversational AI vs. Generative AI

Aspekt | Conversational AI | Generative AI
--- | --- | ---
Focus | Menschliche Interaktion und Kommunikation | Generieren von kreativen und originellen Inhalten
Anwendungen | Chatbots, Sprachassistenten, etc. | Textgenerierung, Bildgenerierung, etc.
Input | Versteht menschliche Sprache | Lernt Mustern aus Daten und generiert neue Daten
Output | Antwort auf eine Nachricht mit Kontext | Generiert neue Daten, basierend auf den gelernten Mustern
Beispiele | Siri, Alexa, Google Assistant | Deepfakes, Textgenerierung, Bildgenerierung

---

## AI-driven development

### Prompt Engineering

Die Qualität der generierten Daten hängt von der Qualität des Inputs ab

Ein Prompt ist ein Input für ein AI-Tool
- Ein Prompt kann ein Text, ein Bild, oder ein Code sein
- Ein Prompt kann eine Frage, oder eine Anweisung sein
- Ein Prompt kann eine Beschreibung sein, oder ein Beispiel
- Ein Prompt kann eine Kombination aus allem sein

Anhand der Prompts lernt das AI-Tool Muster und generiert neue Daten

Prompt Engineers erstellen Prompts für AI-Tools
- Prompts müssen gut formuliert sein
- Prompts müssen gut strukturiert sein

Oft müssen Prompts mehrmals angepasst werden, bis das AI-Tool die gewünschten Ergebnisse liefert

![:scale 60%](media/copilot.png)

---

## AI-driven development

### AI-Tools für Softwareentwicklung

Es gibt viele AI-Tools für die Softwareentwicklung

Zwei der bekanntesten sind:
- GitHub Copilot
- Chat GPT

Beide Tools können Text und Code generieren
- Die Anwendungsfälle sind aber unterschiedlich

---

## AI-driven development

### AI-Tools für Softwareentwicklung

#### GitHub Copilot

Github Copilot ist ein AI-Tool, welches von GitHub entwickelt wurde
- Es basiert auf OpenAI Codex
- Generative AI

Der Copilot schlägt Entwicklern Code in der IDE vor
- Der Entwickler kann den Code dann übernehmen, oder nicht
- Der Copilot lernt aus dem Code des Entwicklers und schlägt immer besseren Code vor
- Der Copilot kann auch Code aus anderen Repositories vorschlagen
- Der Copilot erkennt Muster im eigenen Code und schlägt Code vor, der diese Muster verwendet

Neben Code kann der Copilot auch Kommentare und Dokumentation vorschlagen

---

## AI-driven development

### AI-Tools für Softwareentwicklung

#### GitHub Copilot

- Der Copilot wurde mit Prompts trainiert, die von GitHub und OpenAI erstellt wurden
- Die Daten basieren unter anderem auf öffentlichen GitHub Repositories
  - Neben Code können auch viele anderen Informationen aus den Repositories gelernt werden

![:scale 40%](media/Copilot.png)

---

## AI-driven development

### AI-Tools für die Softwareentwicklung

#### Chat GPT

Chat GPT ist ein AI-Tool, welches von OpenAI entwickelt wurde

- Generative AI und Conversational AI

Chat GPT kann Text generieren

- Der Nutzer gibt einen Text vor und Chat GPT generiert einen neuen Text
- Man kann Chat GPT auch Fragen stellen, oder sich mit ihm unterhalten

![:scale 20%](media/chatgptlogo.png)

---

## AI-driven development

### AI-Tools für die Softwareentwicklung

#### Chat GPT

Die Daten basieren vorallem aus dem Internet

- Durch die große Menge an Daten kann Chat GPT sehr gut lernen
- Vielseitigkeit der Daten = Vielseitigkeit von Chat GPT

Es gibt ChatGpt Api's für verschiedene Programmiersprachen

- Mit den Api's können Entwickler Chat GPT in ihre Programme einbinden
- Benutzerdefinierte Prompts können erstellt werden
- Daten können automatisch analysiert und generiert werden

![:scale 15%](media/chatgptlogo.png)

---

## Best Practices for googling

Das nachgucken von Dokumentation ist ein wichtiger Teil der Softwareentwicklung

Google ist dafür das perfekte Mittel

- Oft muss man nach einer Lösung für ein Problem suchen
- Manchmal ist es schneller nach einer Lösung zu googlen, als sie selbst zu entwickeln
- Manchmal ist es schneller nach einer Lösung zu googlen, als die Dokumentation zu lesen

Die Qualität der Suchergebnisse hängt von der Suchanfrage ab

- Eine undeutliche Suchanfrage liefert schlechte Ergebnisse

![:scale 15%](media/googlelogo.png)

---

## Best Practices for googling

**Wie google ich richtig?**

- Eine gute Suchanfrage ist simpel und präzise
- Vermeide wiederholte und unwichtige Wörter
- Manchmal ist es besser die Suche auf zu teilen
- Eine gute Suchanfrage enthält nur die wichtigsten Informationen
- Automatische Vervollständigung ist hilfreich

**Remember!**

- Jedes Wort in der Suchanfrage ist wichtig
  - Die Reihenfolge der Wörter ist wichtig
  - Ein einziges Wort kann den Unterschied zwischen guten und schlechten Ergebnissen machen
- Unwichtig sind Dinge wie:
  - Rechtschreibung
  - Groß- und Kleinschreibung
  - Satzzeichen
  Solange es nicht zu Missverständnissen führt
- Denke kritisch
  - Nicht alles was im Internet steht ist wahr, aktuell, oder gut
  - Nutze die Möglichkeit mehrere Quellen zu vergleichen

![:scale 15%](media/googlelogo.png)

---

## Best Practices for googling

### Search Operators

Es gibt viele Suchoperatoren, die die Suche verbessern können

Beispiele für Suchoperatoren:

- Anführungszeichen ""
  - "Suche nach einem bestimmten Wort"
- Minus -
  - Bestimmte Wörter in der Suche ausschließen
- Sternchen *
  - Platzhalter für ein Wort

Eine Liste mit vielen weiteren Suchoperatoren gibt es hier: https://blog.hubspot.de/marketing/google-suchoperatoren

---

## Code-Reading

### Wieso ist Code-Reading wichtig?

- Arbeiten im Team

- Geben von Code-Reviews
   
- Effizienz
    

---

### Wie liest man Code?

- Verstehen des Kontexts
    
- Variablen und Funktionen
    
- Kommentare
    
- Abhängigkeiten von externen Modulen und Bibliotheken
   
- Tests
    
- Debugging
    
- Tools
    
- Diskussion mit Kollegen

---

## Schreiben von Bug-Reports

### Was ist ein Bug-Report?

Dokument, dass Fehler, Probleme oder Mängel in einer Softwareanwendung oder einem System beschreibt.

---

### Wie schreibe ich einen guten Bug-Report?

Ein Bug-Report sollte folgenden Inhalt haben:

- Titel
   
- Priorität
    
- Beschreibung des Fehlers
    
- Umgebung
    
- Reproduktionsschritte
    
- Erwartetes Ergebnis

- Aktuelles Ergebnis

- Anhänge
    

---

## Debugging

Debugging beinhaltet das Identifizieren und Beheben von Fehlern (Bugs) in einem Programm. 

### Ursachenanalyse (Root-Cause-Analysis, kurz: RCA)

Fehlerbehebungsmethode, mit der die Ursache von Bugs identifiziert und behoben werden kann, anstatt nur Symptome zu behandeln.

Eine Ursachenanalyse hat meistens folgende Schritte:

1. Problem definieren und Warnungen einrichten
    
2. Sammeln und Analysieren der Daten
    
3. Ursachen ermitteln
    
4. Lösungen implementieren und Aktionen dokumentieren
   

---

### Debugging vs. Testen

Die Hauptunterschiede zwischen Debugging und Testen sind:

- Ziel
    
- Reihenfolge
  
- Ansatz
  
- Tools und Techniken


---

### Rubber-Duck-Debugging(dt.: Gummienten-Debugging)

- Einfache Methode, um Fehler in einer Software zu finden

Wie funktioniert das?

1. Besorge dir eine Gummiente
2. Stelle die Gummiente auf deinen Tisch und informiere sie darüber, dass du gerne mit ihr ein bisschen Code angucken möchtest.
3. Erkläre der Ente was dein Code machen soll und erkläre ihn ihr detailliert.
4. Irgendwann stellst du fest, dass dein Code einen Fehler oder Sonstiges hat.

---

### Time-Travel-Debugging (TTD) (dt.: Zeitreisen-Debugging)

- fortgeschrittene Methode des Debuggings
- Code wird Schritt-für-Schritt in umgekehrter Reihenfolge durchlaufen, um genauen Zeitpunkt des Auftretens des Fehlers zu finden

Einige Vorteile von TTD:

- Effizienz
    
- Rückwärtsausführung
    

Einige Nachteile von TDD:

- Overhead
    
- Nicht immer anwendbar

- Komplexität
    

---

## Logging / Tracing


### Logging

- Aufzeichnen von Ereignissen in einer Softwareanwendung

- soll Informationen über Ausführung und Verhalten protokollieren

- Log-Nachrichten
    
- Log-Level

---

### Tracing

- erweiterte Form des Loggings

- Detaillierte Informationen über den Verlauf von Anfragen

- Gesamter Lebenszyklus einer Anfrage kann verfolgt werden

---

### Warum sind Logging und Tracing wichtig?

- Fehlerdiagnose
    
- Peformance-Optimierung
    
- Sicherheitsüberwachung

---

### Beispiel eines Debugging-Zyklus

Das folgende Beispiel wurde mit Chat-GPT-3.5 erstellt:

```jsx
def add_numbers(a, b):
    result = a + b
    return result

num1 = 5
num2 = 7
result = add_numbers(num1, num2)
print("Das Ergebnis der Addition ist:", result)
```

Debugging-Prozess:

1. Setzen von Breakpoints

2. Starten des Debugging-Modus

3. Überprüfen von Variablen

4. Schritt-für-Schritt-Ausführung

5. Identifizieren des Problems

6. Beheben des Problems


---

### Debugging-Werkzeuge

Sprachenspezifische Debugging-Tools:

- Java: Eclipse Debugger, IntelliJ Debugger

- Python: pdb (in Python eingebautes Debugging-Tool)

- C/C++: GNU Debugger, Visual Studio Debugger

Allgemeine Debugging-Tools:

- Visual Studio Code

- PyCharm

- IntelliJ IDEA

---

## Agile Testing Workflows

Effiziente Testworkflows sind von entscheidender Bedeutung, wenn es um eine schnelle Entwicklung einer Software geht, diese aber trotzdem eine hohe Qualität haben soll.



---
## Ansätze zur Softwareentwicklung

### Test-Driven-Development (TDD)

- es werden zuerst Tests entwickelt
  
- dann Implementierung des Codes, der den Test besteht

- Motivation
    
- Ablauf
    
- Frameworks

---

### Behavior-Driven-Development (BDD)

- Erweiterung von TDD

- Fokus liegt auf dem Verhalten der Software

- Tests werden in einer natürlichen Sprache verfasst

- Motivation

- Ablauf

- Frameworks

---

### Acceptance-Test-Driven-Development (ATDD)

- Tests werden basierend auf den Akteptanzkriterien des Benutzers geschrieben
- Motivation

- Ablauf

- Frameworks
    

---

### Test Doubles

- sollen bestimmte Abhängigkeiten beim Testen ersetzen oder simulieren
- Mocks

- Fakes

- Stubs

- Spy

- Frameworks

---

## Pair-Programming

### Ablauf

- 2 Programmierer arbeiten zusammen an der selben Aufgabe

Klare Rollenverteilung:

- Driver
   
- Navigator
    
- Rollen wechseln alle paar Minuten

---

### Best Practices

- Klare Verteilung der Rollen

- Rollen alle paar Minuten tauschen
- Kommunikation
    
- Respekt und Empathie
    
- Pausen
    
- Ziele
    

---

### Tools für Pair-Programming

- Live Share (VS Code): Extension für VS Code ermöglicht den Entwicklern in Echtzeit zusammen zu entwickeln

- Replit: Online-Tool, welches ohne Installation zum Zusammenarbeiten genutzt werden kann

---

## Code-Reviews

In Code-Reviews überprüfen Entwickler den geschriebenen Code ihrer Kollegen. Hiermit soll die Qualität und Zuverlässigkeit des Codes sichergestellt werden.

---

### Conventional Comments

- Methode, um in Code-Reviews klare Rückmeldungen zu geben

- können in Form von Kommentaren im Code oder in einem Code-Review-Tool (z.B. GitHub) verwendet werden

**Konvention:**

Aufbau: label [decorations]: subject

- Label: Welche Art von Kommentar?
    
- Decorations (Optional): Ergänzend zum Label: non-blocking, blocking, if minor

- Subject: Hauptnachricht des Kommentares

- Weiterführende Infos: https://conventionalcomments.org/ [letzte Einsicht: 17. Oktober 2023]

---

### Best-Practices

- Begrenzte Anzahl der Reviewer
    
- Konstruktive Kommentare
    
- Versionskontrolle
    

---

## Refactoring

- Umstrukturierung von Code, ohne die ursprüngliche Funktionalität zu verändern

### Ziel des Refactorings

- Code soll verbessert werden
    
- Code soll effizienter werden

- Fehler können leichter gefunden und behoben werden

---

### Refactoring-Patterns

- Extract-Methode
    
- Variablen umbennen
    
- Move-Methode
    
- Extract Class
    
- Factory-Pattern einführen
    
- Entfernung von doppeltem Code
    
- Integration bewährter Design-Pattern
    

---

## Werkzeuge

- Werkzeuge sollen Entwicklungsprozesse in der Softwareentwicklung optimieren

- Qualität der Software wird durch Einsatz von Werkzeugen verbessert

---

### Testing/Build-Werkzeuge

- GitHub Actions
    
- Jenkins
    

---

### Bug- und Worktracking

- Jira
   
- Trello
   
- YouTrack
    
- Bugzilla
    

---

## Lernfragen

1. Was ist ein Versionsverwaltungssystem?
2. Was ist der Unterschied zwischen einem zentralen und einem dezentralen Versionsverwaltungssystem?
3. Wer hat Git entwickelt?
4. Wie kann man Git steuern?
5. Wie kann man eine Änderung auf das Remote Repository übertragen?
6. Wie macht man einen Commit und was sollte in der Commit Nachricht stehen?
7. Wie erstellt man Branches und wechselt zwischen ihnen?
8. Was ist der Unterschied zwischen einem Merge und einem Rebase?
9. Was ist der Unterschied zwischen einem Monorepo und einem Multirepo?
10. Warum sind pull requests sinnvoll?
11. Was ist eine Branching Strategie?
12. Was ist der Unterschied zwischen Git Flow und Github Flow?
13. Worauf muss man achten, wenn man AI Tools benutzt?
14. Wie sollte eine Google Suchanfrage aussehen?
15. Was ist beim Lesen von Code wichtig?
16. Wie ist ein guter Bug-Report aufgebaut?
17. Wie funktioniert eine Ursachenanalyse (RCA) im Kontext des Debuggings?
18. Was ist der Unterschied zwischen Debugging und Testen?

---

## Lernfragen 

19. Wie funktioniert Rubber-Duck-Debugging?
20. Was ist Logging?
21. Nenne mir ein Debugging-Werkzeug, welches man allgemein einsetzen kann!
22. Nenne und beschreibe einen agilen Testing-Workflow!
23. Wie funktioniert Pair-Programming?


---

## Quellen

Mono- vs Multirepos
https://kinsta.com/de/blog/monorepo-vs-multi-repo/

Gitbefehle
https://marklodato.github.io/visual-git-guide/index-en.html

Gitflow
https://lucamezzalira.com/2014/03/10/git-flow-vs-github-flow/

Githubflow
https://www.abtasty.com/blog/git-branching-strategies/#github-flow

Merges
https://www.atlassian.com/de/git/tutorials/using-branches/git-merge

Mergesquash
https://lukemerrett.com/different-merge-types-in-git/

Rebase
https://hackernoon.com/git-merge-vs-rebase-whats-the-diff-76413c117333

Conversational vs Generative AI 
https://www.datasciencecentral.com/a-complete-guide-conversational-ai-vs-generative-ai/#:~:text=Conversational%20AI%20is%20characterized%20by,art%2C%20music%2C%20and%20texts.

Copilot 
https://github.com/features/copilot

Google
https://www.google.de/?hl=de

---
## Quellen 

https://builtin.com/software-engineering-perspectives/reading-code [letzte Einsicht: 16. Oktober 2023]

https://orangesoft.co/blog/how-to-write-a-bug-report [letzte Einsicht: 16. Oktober 2023]

https://www.elastic.co/de/what-is/root-cause-analysis [letzte Einsicht: 16. Oktober 2023]

https://www.geeksforgeeks.org/differences-between-testing-and-debugging/ [letzte Einsicht: 16. Oktober 2023]

https://rubberduckdebugging.com/ [letzte Einsicht: 16. Oktober 2023]

https://www.ip-insider.de/was-ist-logging-event-log-management-a-efd311ecd8621b98baa59d2405d870ad/ [letzte Einsicht: 16. Oktober 2023]

https://de.ryte.com/wiki/Test_Driven_Development#:~:text=Test%20Driven%20Development%20 [letzte Einsicht: 16. Oktober 2023]

https://www.softwaretestingmagazine.com/knowledge/unit-testing-fakes-mocks-and-stubs/ [letzte Einsicht: 16. Oktober 2023]

---

## Quellen

https://dev.to/documatic/pair-programming-best-practices-and-tools-154j#best-practices-for-pair-programming [letzte Einsicht: 17. Oktober 2023]

https://conventionalcomments.org/ [letzte Einsicht: 17. Oktober 2023]

https://www.computerweekly.com/de/definition/Refactoring [letzte Einsicht: 19. Oktober 2023]

https://dzone.com/refcardz/refactoring-patterns [letzte Einsicht: 19. Oktober 2023]