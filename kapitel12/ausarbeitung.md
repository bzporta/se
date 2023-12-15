# Softwarewartung

**Autor:** Bjarne Zaremba - Danny Meihöfer

# Softwarewartung
## Definition

Die Softwarewartung ist der kontinuierliche Prozess der Pflege und Aktualisierung von Softwareanwendungen nach ihrer Bereitstellung. Das Hauptziel besteht darin, die Leistungsfähigkeit, Sicherheit und Funktionalität der Software sicherzustellen. Dieser Prozess beinhaltet eine Vielzahl von Tätigkeiten, darunter das Beheben von Fehlern, die Verbesserung der Software und das Hinzufügen neuer Funktionen.

## Legacy-Code

Legacy-Code bezieht sich auf veralteten Quellcode, der schwer verständlich ist und nicht den aktuellen Standards entspricht, jedoch für die Anwendung von wesentlicher Bedeutung ist. Die Merkmale von Legacy-Code umfassen den Einsatz veralteter Technologien, mangelnde Dokumentation, schwer verständlichen Code und eine unzureichende Testabdeckung, was ein potenzielles Sicherheitsrisiko darstellt.

## Evolution von Software

### Ursachen für Änderungen an der Software

Die Evolution von Software wird durch verschiedene Ursachen vorangetrieben, darunter Fehlerbehebungen, Änderungen der Anforderungen, technologische Weiterentwicklung, Leistungsverbesserungen, Sicherheitsaktualisierungen, regulatorische Anforderungen, Umgebungsänderungen und die Verbesserung der Benutzererfahrung (UX).

### Arten von Änderungen an Software

Es gibt vier Haupttypen von Softwarewartung:

1. **Korrektive Wartung:**
   - Behebung von Fehlern, die nach der Bereitstellung der Software auftreten und die Funktionalität einschränken.

2. **Präventive Wartung:**
   - Behebung von Problemen, die zwar aktuell noch keine Probleme verursachen, aber in der Zukunft zu Schwierigkeiten führen könnten.

3. **Perfektionierende Wartung:**
   - Verbesserung der Softwareleistung.
   - Hinzufügen kleiner neuer Funktionen.
   - Entfernen ineffektiver Funktionen.
   - Performanceoptimierungen und Strukturverbesserungen (Refactoring, Reengineering).

4. **Adaptive Wartung:**
   - Anpassung der Software an veränderte Umgebungen, andere Plattformen oder externe Schnittstellen.

## Sanierung von Software

### Bad Code Smells

- Doppelter Code (Duplicated Code) → Wiederholung von Codeblöcken → führen zu Wartbarkeitsproblemen

```python
def calculate_area_of_square(side_length):
    return side_length * side_length

def calculate_area_of_rectangle(length, width):
    return length * width
```

- Lange Methoden (Long Method) → Methoden sind schwierig zu verstehen und zu testen

```python
def complex_calculation(x, y, z, a, b, c):
    # Lange Methode mit vielen Berechnungen
    result = x * y + z / a - b * c
    return result
```

- Große Klassen (Large Class) → Klassen, die zu viele Verantwortlichkeiten, Methoden und Eigenschaften haben

```python
class LargeClass:
    def method1(self):
        # ...

    def method2(self):
        # ...

    # ... (viele weitere Methoden)
```

- Unsinnige Namen (Meaningless Names) → Namen, die die Funktion der Methode nicht beschreiben

```python
def xyz(a, b):
    return a + b

result = xyz(3, 4)
```

- Unbenutzter Code (Dead Code)

```python
def unused_function():
    print("Dieser Code wird nie aufgerufen.")

# Rest des Programms ohne Verweis auf unused_function
```



### Anti-Patterns

- Big Ball of Mud → Unstrukturierter Code ohne klare Architektur, der schwer zu verstehen ist

```python
# Unstrukturierter Code ohne klare Architektur
# ...

if condition:
    # Unzusammenhängende Logik
    # ...

for item in collection:
    # Weitere Code-Segmente ohne klare Struktur
    # ...
```

- Spaghetti Code → Verwirrter und unlesbarer Code (viele Verzweigungen, fehlende Struktur)

```python
def spaghetti_code(x):
    if x > 0:
        print("Positive Zahl")
        if x % 2 == 0:
            print("Gerade Zahl")
        else:
            print("Ungerade Zahl")
    else:
        print("Negative oder Null")
```

- Golden Hammer → Übermäßiger Einsatz eines vermeintlich universellen Ansatzes für alle Probleme, unabhängig von der Passung

```python
def universal_solution():
    # Übermäßige Verwendung eines allgemeinen Ansatzes
    # für verschiedene Problemstellungen
    # ...

# Anstatt spezifische Lösungen zu implementieren
```

- Copy-Paste-Programming → Unkritische Wiederholung von Code ohne sorgfältige Abstraktion, was zu Redundanzen und Ineffizienzen führen kann

```python
def calculate_area_of_square(side_length):
    return side_length * side_length

def calculate_area_of_rectangle(length, width):
    return length * width

# Copy-Paste-Programmierung anstelle von Abstraktion
```

## Software-System-Management

### Logging vs. Monitoring vs. Observability

**Logging:**

- Systematisches Auszeichnen von Ereignissen, Status und Fehlermeldungen zur Laufzeit eines Programms
- wird in Dateien oder Datenbanken gespeichert

```python
import logging

logging.basicConfig(filename='app.log', level=logging.INFO)
logging.info('Anwendung gestartet...')
```

**Monitoring:**

- Kontinuierliche Überwachung von Ressourcen, Leistung und Aktivitäten eines Systems in Echtzeit
- Probleme und Unregelmäßigkeiten können früh erkannt werden
- CPU, Speicher, Netzwerk

Beispiel (Prometheus in Kubernetes):

```yaml
apiVersion: monitoring.coreos.com/v1
kind: ServiceMonitor
metadata:
  name: example-app-monitor
  labels:
    release: monitoring
spec:
  selector:
    matchLabels:
      app: example-app
  endpoints:
  - port: web
    path: /metrics
```

**Observability:**

- geht über Logging und Monitoring hinaus
- Fähigkeit, den internen Zustand eines Systems basierend auf externen Beobachtungen zu verstehen
- ganzheitlicher Einblick
- Metriken, Protokolle, Traces

Beispiel (Jaeger Tracing in Microservices):

```yaml
services:
  - name: example-service
    ports:
      - 8080:8080
    environment:
      - JAEGER_AGENT_HOST=jaeger-agent
      - JAEGER_AGENT_PORT=6831
```

### Observability-Konzepte

**Metrics:**

Quantitative Messwerte liefern Informationen über die Leistung eines Systems. Sie sind oft numerische Werte oder aggregierte Daten über einen bestimmten Zeitraum. Ein Beispiel in einem Webanwendungs-Server könnte die Anzahl der HTTP-Anfragen pro Sekunde, die durchschnittliche Antwortzeit pro Anfrage und die Auslastung der CPU sein. Dies ermöglicht es Entwicklern, die Effizienz der Anwendung zu überwachen.

**Logs (Protokolle):**

Logs erfassen ereignisbasierte Informationen über Aktivitäten in einem System. Wichtige Ereignisse, Fehlerzustände und Warnungen werden aufgezeichnet, um bei der Fehlersuche und Analyse von Problemen zu helfen. Ein Beispiel ist ein Webserver, der Protokolle generiert, die jede empfangene HTTP-Anfrage, den zugehörigen Statuscode und eventuelle Fehlerinformationen aufzeichnen. Das ermöglicht Entwicklern die Identifikation potenzieller Fehlerquellen.

**Traces (Spuren):**

Traces ermöglichen die Verfolgung der Ausführung eines Vorgangs durch ein verteiltes System hinweg. Sie zeigen, wie Ressourcen zwischen verschiedenen Komponenten eines verteilten Systems genutzt werden. In Microservice-Architekturen kann eine Anfrage durch verschiedene Dienste hindurch verfolgt werden, wobei jeder Dienst seine eigenen Spuren hinterlässt. Dies hilft Entwicklern, Engpässe in der Verarbeitung der Anfrage zu identifizieren.

---

#### Werkzeuge

**Prometheus:**

Prometheus ist ein Open-Source-System für das Monitoring von IT-Systemen. Es sammelt Metriken über ein Pull-Modell von Bibliotheken und speichert diese in einer Zeitreihendatenbank.

**Grafana:**

Grafana ist eine Open-Source-Plattform für das Monitoring und Visualisieren von Zeitreihendaten. Es ermöglicht die Erstellung von Dashboards, Diagrammen und Warnungen. Die Integration mit Prometheus wird unterstützt.

![Beispiel eines Grafana-Dashboards](Kapitel%2012%20-%20Wartung%20von%20Software%205ec694189cc046529f93e192b9e42a45/Untitled%201.png)

**Jaeger:**

Jaeger ist ein Open-Source-Werkzeug für das Tracing von Anwendungen in verteilten Systemen. Es verfolgt Ausführungspfade über mehrere Dienste hinweg und bietet eine Web-Benutzeroberfläche.

![Beispieldashboard Jaeger](Kapitel%2012%20-%20Wartung%20von%20Software%205ec694189cc046529f93e192b9e42a45/Untitled%202.png)

---

## Technische Schulden

### Definition

Technische Schulden entstehen, wenn kurzfristige Lösungen und Kompromisse eingeführt werden, um Zeit zu sparen. Diese führen zu langfristigen "Schulden" in Bezug auf Codequalität und Wartbarkeit. Technische Schulden sind die Summe von Entscheidungen, die zu einem späteren Zeitpunkt verbessert oder korrigiert werden müssen.

### Ursachen und Entstehung

- **Zeitdruck:** Entwickler stehen unter Zeitdruck und greifen auf schnellere Lösungen zurück.
- **Mangelnde Ressourcen:** Zu wenig Personal oder Budget können zu Kompromissen führen.
- **Unklare Anforderungen:** Unklare Anforderungen führen zu Entscheidungen, die später überarbeitet werden müssen.
- **Fehlende Planung:** Fehlende Architekturüberlegungen führen zu schnellen Entscheidungen.

### Risiken und Folgen

- **Verlangsamte Entwicklung:** Entwickler müssen im Nachhinein mehr Zeit für Wartung und Überarbeitung des Codes aufwenden.
- **Erhöhte Fehleranfälligkeit:** Unzureichend getesteter oder schlecht strukturierter Code birgt ein höheres Risiko von Fehlern und Softwarefehlern.
- **Schwierige Skalierbarkeit:** Bei undurchsichtiger Codebasis ist ein Skalieren der Anwendung nur schwer möglich.
- **Schwierige Zusammenarbeit:** Der Code kann für Entwickler schwer zu verstehen sein, was die Zusammenarbeit erschwert und die Einarbeitung neuer Teammitglieder erschwert.

### Arten von technischen Schulden

**Architectural Debt:**

Veraltete oder unzureichende Architekturentscheidungen müssen im Nachgang korrigiert werden, was zu einer Verschwendung von Ressourcen führt.

**Documentation Debts:**

Fehlende, ungenaue oder veraltete Dokumentation beeinträchtigt die Wartbarkeit und führt zu einer Verschwendung von Ressourcen durch längeres Einlesen in den Code.

**Implementation Debts:**

Kompromisse bei der Implementierung, zum Beispiel nicht optimale Algorithmen.

**Testing Debt:**

Unzureichende Testabdeckung, keine Regressionstests, ineffektive Teststrategien.

---

## Technical-Debt-Management

### Umgang mit technischen Schulden

#### Operativer Umgang

- **Automatisierung:** Wiederkehrende Aufgaben können automatisiert werden, um Fehler zu vermeiden.
- **Inkrementelle Verbesserungen:** Verbesserungen/Beseitigungen sollten schrittweise geplant werden.
- **Priorisierung:** Wichtige Beseitigungen sollten schneller umgesetzt werden.
- **Refactoring:** Refactoring verbessert den Code.

#### Konzeptioneller Umgang

- **Entwicklungsrichtlinien:** Diese minimieren die Entstehung neuer technischer Schulden.
- **Schulungen:** Schulungen fördern bewährte Praktiken und verbessern das Verständnis für hochqualitativen Code.
- **Code Reviews:** Mehrere Entwickler gewährleisten die Codequalität.

### Erkennung von technischen Schulden

#### Metriken

- **Code Coverage:** Anteil des Codes, der durch Tests abgedeckt wird.
- **Code Complexity:** Misst die Komplexität des Codes mithilfe von zyklomatischen Metriken.
- **Bugs und Fehlermeldungen:** Anzahl der gemeldeten Fehler und deren Schweregrad.
- **Duplicated Code:** Anteil des duplizierten Codes.

#### Werkzeuge

**SonarQube:**

SonarQube ist ein Code-Analysewerkzeug, das eine Vielzahl von Metriken und Statistiken über Code liefert. Es identifiziert Code-Smells, Duplikate, Code Coverage, Bugs und Security Issues.



# Quellen

- [https://softwarewartung.net/definition.html](https://softwarewartung.net/definition.html) [letzte Einsicht: 14.12.23]
- [https://t2informatik.de/wissen-kompakt/legacy-code](https://t2informatik.de/wissen-kompakt/legacy-code) [letzte Einsicht: 14.12.23]
- [https://blog.codacy.com/code-smells-and-anti-patterns](https://blog.codacy.com/code-smells-and-anti-patterns) [letzte Einsicht: 14.12.23]
- [https://swc-public.pages.rwth-aachen.de/smells/code-smells/](https://swc-public.pages.rwth-aachen.de/smells/code-smells/) [letzte Einsicht: 14.12.23]
- Codebeispiele, sowie teilweise die Ausarbeitung wurden mit ChatGPT-3.5 erstellt: [https://chat.openai.com/](https://chat.openai.com/) [letzte Einsicht: 14.12.23]
- [https://rvprasad.medium.com/logging-monitoring-and-observability-219c043b5c81](https://rvprasad.medium.com/logging-monitoring-and-observability-219c043b5c81) [letzte Einsicht: 14.12.23]
- [https://thenewstack.io/observability-working-with-metrics-logs-and-traces/](https://thenewstack.io/observability-working-with-metrics-logs-and-traces/) [letzte Einsicht: 14.12.23]
- [https://prometheus.io/](https://prometheus.io/) [letzte Einsicht: 14.12.23]
- [https://de.wikipedia.org/wiki/Prometheus_(Software)](https://de.wikipedia.org/wiki/Prometheus_(Software)) [letzte Einsicht: 14.12.23]
- [https://grafana.com/](https://grafana.com/) [letzte Einsicht: 14.12.23]
- [https://www.redhat.com/de/topics/data-services/what-is-grafana](https://www.redhat.com/de/topics/data-services/what-is-grafana) [letzte Einsicht: 14.12.23]
- [https://www.jaegertracing.io/](https://www.jaegertracing.io/) [letzte Einsicht: 14.12.23]
- [https://aws.amazon.com/de/what-is/jaeger/](https://aws.amazon.com/de/what-is/jaeger/) [letzte Einsicht: 14.12.23]
- [https://t2informatik.de/wissen-kompakt/technische-schulden/](https://t2informatik.de/wissen-kompakt/technische-schulden/) [letzte Einsicht: 15.12.23]
- [https://www.computerwoche.de/a/was-sind-technische-schulden,3551965](https://www.computerwoche.de/a/was-sind-technische-schulden,3551965) [letzte Einsicht: 15.12.23]
- [https://brainhub.eu/library/how-to-deal-with-technical-debt](https://brainhub.eu/library/how-to-deal-with-technical-debt) [letzte Einsicht: 15.12.23]
- [https://www.cio.com/article/472768/5-tips-for-tackling-technical-debt.html](https://www.cio.com/article/472768/5-tips-for-tackling-technical-debt.html) [letzte Einsicht: 15.12.23]
- [https://mindnow.io/de/blog/technische-schulden](https://mindnow.io/de/blog/technische-schulden) [letzte Einsicht: 15.12.23]
- [https://entwickler.de/programmierung/der-umgang-mit-technischen-schulden](https://entwickler.de/programmierung/der-umgang-mit-technischen-schulden) [letzte Einsicht: 15.12.23]
- [https://www.sonarsource.com/products/sonarqube/](https://www.sonarsource.com/products/sonarqube/) [letzte Einsicht: 15.12.23]
- [https://de.wikipedia.org/wiki/SonarQube](https://de.wikipedia.org/wiki/SonarQube) [letzte Einsicht: 15.12.23]

# Abbildungsverzeichnis

Abb.1: [https://softwarewartung.net/definition.html](https://softwarewartung.net/definition.html) [letzte Einsicht: 14.12.23]

Abb.2: [https://grafana.com/oss/grafana/](https://grafana.com/oss/grafana/) [letzte Einsicht: 14.12.23]

Abb.3: [https://www.netways.de/blog/2020/01/09/from-monitoring-to-observability-distributed-tracing-with-jaeger/](https://www.netways.de/blog/2020/01/09/from-monitoring-to-observability-distributed-tracing-with-jaeger/) [letzte Einsicht: 14.12.23]
