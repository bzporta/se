# Softwareentwurf

**Autoren:** Danny Meihöfer - Bjarne Zaremba

## Lernziele für dieses Kapitel

Nach diesem Kapitel sollen folgende Aspekte klarer geworden sein:

- Was ist ein Softwareentwurf?
- Was sind die Ziele eines Softwareentwurfs?
- Was für Entwurfsprinzipien gibt es?
- Was sind die SOLID-Prinzipien?
- Welche Entwurfsmuster gibt es?
- Was ist das Domain-Driven-Design?
- Wie entwierft man ein Datenmodell?
- Wie wird eine Benutzerschnittstelle entworfen und welche Regeln gilt es zu beachten?

## Softwareentwurf

Die IEEE1990 definiert den Begriff Softwareentwurf wie folgt: "Der Softwareentwurf ist der Prozess der Definition der Architektur, Komponenten, Schnittstellen und anderer charakteristischer Merkmale eines Systems oder einer Komponente." 

Man kann den Softwraeentwurf also als Bauplan für die Entwicklung einer Software sehen. Der Entwurf ist dabei die Grundlage für die Implementierung.

Die Entwicklung einer Software besteht aus vielen Schritten. Die Erstellung eines Softwareentwurfs ist einer der ersten Schritte.

![:scale 90%](media/Waterfall_model-de.svg)

### Tätigkeiten im Softwareentwurf

Der Softwareentwurf besteht aus mehreren Tätigkeiten, die man in das Top-Level-Design und das Detailed-Design unterteilen kann.

Das Top-Level-Design beschreibt die Architektur der Software. Es wird festgelegt, welche Komponenten es gibt und wie diese zusammenarbeiten. Das Top-Level-Design ist die Grundlage für das Detailed-Design. Folgende Aspekte gehören zu dem Top-Level-Design:

- Architektur
- Organisation
- Komponenten
- Schnittstellen
- Persistenz
- Verteilung
- Alles auf hohem Abstraktionsniveau

Beim Detailed Design geht es um genauere und detailliertere Aspekte der Software. Folgende Aspekte gehören zum Detailed Design:

- Klassen
- Methoden
- Attribute
- Komponenten detailiert
- Datenstrukturen
- Algorithmen
- Alles auf niedrigem Abstraktionsniveau

Es geht nicht um konkrete Implementierungen, sondern um die Struktur der Software und eine Beschreibung der Komponenten.

### Entwurfsprinzipien

Das Hauptziel des Softwareentwurfs ist es, dass man als Team eine gemeinsame Basis für die nächsten Schritte der Entwicklung hat. Um mit der Umsetzung der Pläne anzufangen.

Die wichtigsten Aspekte auf die dabei klar werden müssen sind die Orthogonalität, die Kohäsion und die Kopplung.

#### Orthogonalität

Den Begriff Orthogonalität kennt man vielleicht aus der Mathematik. Dort bedeutet er, dass zwei Vektoren orthogonal zueinander sind, wenn sie senkrecht aufeinander stehen. In der Softwareentwicklung geht es nicht um Vektoren, sondern um Komponenten eines Softwaresystems. Diese Komponenten sind orthogonal zueinander, wenn sie unabhängig voneinander sind. Das bedeutet, dass eine Änderung an einer Komponente keine Auswirkungen auf eine andere Komponente hat. Das bedeutet auch, dass Komponenten keine doppelten Aufgaben haben und keine Nebeneffekte erzeugen. 

- Klassen sollten sich nicht auf die Implementierung anderer Klasen verlassen müssen
- Globale Daten sollen vermieden werden
- Verändert man eine Klasse hat das keine Auswirkungen auf andere Klassen
- Einzelne Komponenten sind unabhängig voneinander und haben jeweils nur eine Aufgabe

#### Niedrige Kopplung

Eine niedrige Kopplung ist immer wichtig für eine gute Software. Niedrige Kopplung bedeutet, dass die einzelnen Komponenten einer Software so unabhängig voneinander isnd wie möglich. Es gibt wenig Abhängigkeiten und eine Änderung an einer einzlnen Komponente hat keine Auswirkungen auf andere Komponenten. Wird dieses Ziel nicht verfolgt und haben Komponnten starke abhängigkeiten führt das im Laufe der Entwicklung und vorallem in der Wartung eines Systems zu Problemen. Starke Abhängigkeiten führen zum Beispiel dazu, dass man für eine kleine Änderung viele einzelne Komponenten anpassen muss. Das ist aufwendig und fehleranfällig.

![:scale 100%](media/losecoupling.png)

Es gibt verschiedene Programmierstile, die mit der Kopplung unterschiedlich umgehen. 

Besonders bekannt ist die Objektorientierung. Hier werden Daten und Funktionen zusammen in Objekte zusammengefasst. Dieses System lehnt sich daran an wie in der realen Welt Objekte miteinander interagieren. Die Aufgaben, oder Probleme, die eine Software lösen soll wird hier durch Interaktionen zwischen den Objekten gelöst. Da dieser Stil sich an der realen Welt orientiert ist er sehr intuitiv und leicht zu verstehen. Es gibt aber auch Nachteile. Die Objekte sind oft relativ stark miteinander verbunden. Eine Änderung an einem Objekt kann Auswirkungen auf andere Objekte haben. Das kann zu Problemen führen. Bestimmte Programmiersprachen eignen sich besonders gut für diesen Stil. Dazu gehören beispielsweise Java, Python und C++.

Auf der anderen Seite gibt es die prozedurale Programmierung. Hier werden Daten und Funktionen nicht zusammengefasst. Sie sind getrennt und es gibt keine Objekte. Hier werden die Probleme in einzelne Schritte zerlegt. Diese Schritte werden dann in Funktionen zusammengefasst. Die Funktionen können dann in anderen Funktionen aufgerufen werden. Programmiersprachen die sich besonders gut für diesen Stil eigenen sind beispielsweise C und Pascal.

#### Hohe Kohäsion

Hohe Kohäsion ist eine weitere wichtige Eigenschaften einer guten Software. Während mehrere Komponenten eine möglichst niedrige Kopplung haben sollten, sollten die Komponenten in sich selbst eine hohe Kohäsion haben. Das bedeutet wenn eine Komponente aus mehreren Teilen besteht, sollten diese Teile möglichst eng zusammenarbeiten und eine gemeinsame Aufgabe erfüllen. Es gehören keine Teile zu einer Komponente, die nicht für die übergeordnete Aufgabe benötigt werden.

![:scale 75%](media/cohesioncoupling.png)

### Entwurfsprinzipien

Bei dem Erstellen eines Softwareentwurfs sollte aus viele Aspekte geachtet werden. Im folgenden werden ein paar der wichtigen Aspekte vorgestellt.

#### Abstraktion 

Das erste Prinzip ist die Abstraktion. Ein Entwurf soll durch Vereinfachung verständlich gemacht werden. Das ermöglicht allen Beteiligten eine schnelle Übersicht über das System zu bekommen. Die Details werden dabei so weit es geht weg gelassen.

Dabei sollen Beispielsweise die systematischen Zusammenhänge zwischen den Komponenten dargestellt werden. Eine bekannte Form der Abstraktion sind zum Beispiel UML-Diagramme. Diese Diagramme zeigen die Zusammenhänge zwischen den Komponenten und deren Beziehungen und die groben Aspekte einzelner Komponenten.

So kann ein UML-Diagramm für eine Klasse aussehen:

![:scale 60%](media/uml_beispiel.png)

#### Modularisierung

Bei der Modularisierung handelt es sich um eine der Hauptaufgaben eines Softwareentwurfs. Dabei geht es hauptsächlich um die Aufteilung der Software in einzelne Komponenten. Jeder einzelne abgegrenzte Teil eines Systems ist ein Modul. Für gute Module gibt es einige Kriterien, die erfüllt sein sollten. Ein gutes Modul ist in sich selbst geschlossen. Das bedeutet, dass es keine, oder möglichst wenige Abhängigkeiten zu anderen Modulen gibt. Außerdem sollte ein Modul von anderen benutztwerden können, ohne dass sie die konkrete implementierung vorher wissen müssen. Da Module oft miteinander kommunizieren müssen ist es wichtig, dass die Schnittstellen zwischen den Modulen klar definiert sind. Selbstverständlich muss jedes Modul korrekt funktionieren und absolut zuverlässig sein. Die Kohäsion sollte hoch sein und die Kopplung niedrig.

![:scale 100%](media/modularität.png)

#### Law of Demeter

Das Gesetz von Demeter wurde aufgestellt um festzulegen, was guter Codestil ist. Es wurde von Ian Holland und Karl Liebherr aufgestellt. Genauer genommen ist es eine Liste von Regeln die beschreiben wie verschiedene Programmteile miteinander interagieren und kommunizieren sollen.


**Regel 1:** Eine Methode einer Klasse sollte nur auf andere Methoden der eigenen Klasse zugreifen. 

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

**Regel 2:** Eine Methode einer Klasse K soll nur Methoden von Objekten verwenden, die von der Klasse K erzeugt wurden

```java
String getHelloBrazil() {
    HelloCountries helloCountries = new HelloCountries();
    return helloCountries.helloBrazil();
}
```

**Regel 3:** Die Methode M sollte nur Methoden von Objekten verwenden, die als Parameter an M übergeben wurden

```java
String getHelloIndia(HelloCountries helloCountries) {
    return helloCountries.helloIndia();
}
```

**Regel 4:** Die Methode der Klasse K soll nur Methoden von Objekten verwenden, die als Instanzvariablen in K gespeichert sind

```java
HelloCountries helloCountries = new HelloCountries();
  
String getHelloJapan() {
    return helloCountries.helloJapan();
}
```

**Regel 5:** Die Methode einer Klasse K darf Methoden von Objekten verwenden, die statisch und in K definiert sind

```java
static HelloCountries helloCountriesStatic = new HelloCountries();
    
String getHellStaticWorld() {
    return helloCountriesStatic.helloStaticWorld();
}
```

Diese Regeln sollen sicherstellen, dass die einzelnen Komponenten einer Software möglichst unabhängig voneinander sind. Das ist wichtig, damit eine Änderung an einer Komponente keine Auswirkungen auf andere Komponenten hat.

#### Dependency Injection - Inversion of Control

Dependency Injection ist auch eine Vorgehensweise mit der die Abhängigkeiten zwischen mehreren Komponenten veringert werden soll. Dabei werden die Abhängigkeiten einer Komponente nicht von der Komponente selbst fest gelegt, sondern von einer anderen Komponente. Der Vorteil davon ist, dass die Komponente selbst, dann nichtmehr von der Implementierung der anderen Kmponente abhängt. Inversion of Control ist eng damit verbunden. Das bedeutet hier auch einfach, dass die Kontrolle über die Abhängigkeiten nach außen verlagert werden.

Die Abhängigkeit kann zum Beipsiel über den Konstruktor weiter gegeben werden. Das sieht dann so aus:

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

Alternativ kann die Abhängigkeit auch über eine Setter-Methode gesetzt werden oder über Interfaces bestimmt werden.

#### Seperation of Concerns

Seperation of Concerns bedeutet "Trennung von Belangen". Die Essenz dieser Aussage ist, dass jeder einzelne Teil in einem System nur eine einzelne Aufgabe haben soll und zu einer Komponente gehören auch nur Teile die zu der Lösung dieser Aufgabe beitragen. Ein Beispiel dafür ist die Aufteilung eines Systems in Business Logic und UI Logic (Präsentationslogik). Jeder Teil ist nur für eine Aufgabe verantwortlich. Diese Aufteilung ist auch wieder wichtig damit nicht zu viele Abhängigkeiten entstehen. Ist eine Komponente für mehrere Aufgaben zuständig, oder sogar mehrere Komponenten für die gleiche Aufgaben entstehen viele unnötige Abhängigkeiten. Außerdem ist ein Modul leichter zu verstehen wenn es nur einen Zweck erfüllt.

#### Keep It Simple and Stupid (KISS)

Das KISS Prinzip sagt aus, dass Code so simpel und verständlich wie möglich sein sollte. Die höchste priorität ist, das andere den Code verstehen können, weil man immer davon ausgehen muss, dass andere an seinem Code weiter arbeiten und ihn verstehen müssen. Komplexer code kann nur schwer von anderen verstanden und gewartet werden. Manchmal ist es schwer den Code so einfach zu halten wie man es sich vorstellt, aber es ist wichtig, darauf zu achten. Man kann sich die erhöhen des Aufwands exponentiell vorstellen. Je komplexer der Code ist, desto mehr Aufwand ist nötig um ihn zu verstehen und zu warten und unverständlicher Code erweitert wird, wird er meistens nur unverständlicher.

#### You Ain't Gonna Need It (YAGNI)

In Kombination mit dem KISS Prinzip wird oft das YAGNI Prinzip verwendet. Laut diesem Prinzip soll auch darauf geachtet werden, dass nur der Code implementiert wird, den man auch wirklich braucht. Funktionen, die man nicht braucht werden weder implementiert noch erweitert, da das nur zu Aufwand führt. Beschränkt man sich beim Code auf das nötigste bleibt der Code auch kompakter und verständlicher.

#### Don't Repeat Yourself (DRY)

Zu KISS und YAGNI kommt nocht das DRY Prinzip. Funktionen, oder noch genereller, Code sollte nie wiederholt werden. Wiederholter Code führt zu unnötigem Aufwand und macht den Code unübersichtlich. Wird der Code an einer Stelle geändert, muss er an allen anderen Stellen auch geändert werden. Das ist fehleranfällig und aufwendig. Das Warten wird schwerer, das erweitern wird schwierig, das testen wird schwierig und der Code wird schwerer zu verstehen.

#### Composition over Inheritance

Eine der wichtigsten Grundlagen der Programmierung ist die Vererbung. Klassen können Eigenschaften von anderen Klassen erben, wie zum Beispiel Methoden, oder Attribute. Diese Möglichkeit ist sehr mächtig, aber wenn man sie zu oft benutzt macht auch sie den Code unübersichtlicher und birgt noch andere Risiken. Die Vererbung ist eine starke Kopplung. Die Klassen sind also voneinander Abhängig. Außerdem ist ein System aus Vererbungen schwerer zu verstehen, da man einen Überblick über viele Klassen braucht, der manchmal kaum möglich ist. Es gibt aber andere Möglichkeiten die Funktionen anderer Klassen zu nutzen ohne sie zu erben.

Vererbung sieht so aus:

```java
class Bird extends Animal {
    // Bird-specific code
}
```

Mit schlauer Komposition sieht das so aus:

```java
class Bird {
    private Animal animal;

    public Bird(Animal animal) {
        this.animal = animal;
    }

    // Bird-specific code using delegation to Animal object
}
```

Die Funktion der anderen Klasse wird einfach übergeben, indem ein Objekt im Konstruktor mit gegeben wird.

### Clean Code Solid Prinzipien

Die SOLID-Prinzipien sind eine Sammlung von Prinzipien, die von Robert C. Martin aufgestellt wurden. Sie sollen dabei helfen, dass der Code leichter zu verstehen, zu erweitern und zu warten ist. SOLID ist ein Akronym für die einzelnen Prinzipien. Sauberer Code ist Code, der leicht zu verstehen ist und leicht erweitert werden kann. Das erste Princip ist das Single Responsibility Principle.

#### Single Responsibility Principle

Eine Klasse hat nur eine Aufgabe. Dieses Prinzip ähnelt dem Seperation of Concerns Prinzip. Eine Klasse sollte nur eine Aufgabe haben und eine Änderung an einer Klasse sollte auch nur diese eine Klasse verändern. Andernfalls kann es passieren, dass man an einer Klasse arbeitet und plötzlich eine andere Klasse nichtmehr funktioniert. Das Fehlerrisiko wird viel höher. Deshalb ist es für gewöhnlich besser viele kleine Klassen zu machen mit jeweils einer Aufgabe, als eine große Klasse mit vielen Aufgaben. Wenn man eine Klasse aus vielen Gründen verändern muss, weiß man, dass sie zu viele Funktionen hat.

#### Open Closed Principle

Das Open Closed Prinzip sagt aus, dass eine Klasse offen für Erweiterung, aber geschlossen für Änderungen sein sollte. Eine Klasse soll also so erstellt werden, dass sie von anderen leicht erweitert werden kann. Der bereits bestehende Code soll aber nicht verändert werden, da es immer sein kann, dass eine andere Komponente sich auf einen Teil des Codes verlässt, der durch die Änderung nicht mehr funktioniert. Erweiterungen können gut über Vererbung und Interfaces umgesetzt werden.

#### Liskov Substitution Principle

Laut diesem Prinzip muss sich eine abgeleitete Klasse immer wie die Basisklasse verhalten. Man sollte Objekte der verschiedenen Klassen also immer miteinander ersetzen können (Substitution = Ersetzen). Zum gleichen Verhalten gehört zum Beispiel, dass wenn eine Basisklasse keine Exception wirft, wirft die abgeleitet Klasse auch keine Exception. 

#### Interface Segregation Principle

Dieses Prinzip ähnelt dem Single Responsibility Principle. Es sagt aus, dass Interfaces nicht zu viele Funktionen haben sollten. Ein Interface sollte nur eine Aufgabe haben. Das ist wichtig, damit eine Klasse nicht gezwungen ist, Funktionen zu implementieren, die sie nicht braucht. Das Interface sollte also nur die Funktionen enthalten, die die Klasse braucht. Genau wie beim Single Responsibility Principle ist es besser viele kleine Interfaces zu haben, als ein großes Interface mit vielen Funktionen.

#### Dependency Inversion Principle

Eine Klasse auf hohem Abstraktionsniveau sollte von Klassen abhängen, die ein niedriges Abstraktionsniveau haben. Das ist wichtig, weil sonst eine extrem enge Kopplung entsteht.

![:scale 100%](media/dip.png)

An einem Beispiel kann man besonders gut sehen was das Problem ist wenn man nicht auf dieses Prinzip achtet.

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

In dem obigen Beispiel sind die Klassen sehr Abhängig von einander. Man kann keine der oberen Klassen verändern, ohne dass man auch die anderen Klassen verändern muss.

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

Hier kann der Result Publisher einfach mehrere MessageServices verwenden, ohne dass er von der Implementierung abhängig ist.



## Entwurfsmuster

- bewährte Lösungsansätze für häufige, oft vorkommende Probleme in der Softwareentwicklung
- Eine Art “Vorlage” zum Lösen eines Problems
- Design Patterns fördern Flexibilität, Erweiterbarkeit und Sicherheit von Software


## Entkopplungsmuster

- Entwurfsmuster, die Abhängigkeiten zwischen Komponenten eines Systems verringern sollen
- Stark gekoppelte Systeme sind schwer zu verstehen, zu warten und zu warten
- Interaktion zwischen Komponenten auf “lose Art”


### Repository Pattern

**Entwurfsproblem:**

- wird verwendet, um Daten aus verschiedenen Quellen abzurufen, zu löschen oder zu speichern
- Datenzugriffsoperationen sollen nicht direkt im Quellcode stehen
    - klare Trennung zwischen den Verantwortlichkeiten
- Datenzugriff soll gekapselt werden
    - Änderungen in der Datenzugriffsschicht haben minimale Auswirkung auf den Code

**Herausforderungen, die das Repository-Pattern adressiert:**

- Entkopplung von Datenzugriffslogik
    - Direkte Datenbankzugriffe und Datenoperationen sollen vermieden werden
- Testbarkeit
    - Mocken ist einfacher, wenn Datenzugriffe nicht direkt im Code stehen
- Wartbarkeit
    - Repository-Pattern vereinfacht kleine Änderungen in der Datenzugriffsschicht, ohne dafür den gesamten Code verändern zu müssen
- Wiederverwendbarkeit
    - Gleiche Datenzugriffslogik kann an verschiedenen Stellen der Anwendung wieder benutzt werden


**UML-Diagramm:**

![Abb.1: UML-Diagramm des Repository-Patterns](media/repositorypattern.png)

Abb.1: UML-Diagramm des Repository-Patterns



**Anwendungsbeispiele:**

- E-Commerce-Plattform
    - In einer E-Commerce-Anwendung könnten Repositories für den Zugriff auf Produkte, Bestellungen und Kundeninformationen dienen. Dies ermöglicht eine effiziente Handhabung von Datenzugriffsoperationen und trägt zur Skalierbarkeit der Anwendung bei.



**Implementierungsbeispiele:**

```java
// Repository Interface
public interface ArticleRepository {
    Article findById(int articleId);
    List<Article> findAll();
    void save(Article article);
    void delete(int articleId);
}

// Concrete Repository
public class ArticleRepositoryImpl implements ArticleRepository {
    private List<Article> articles = new ArrayList<>();

    @Override
    public Article findById(int articleId) {
        return articles.stream()
            .filter(article -> article.getId() == articleId)
            .findFirst()
            .orElse(null);
    }

    @Override
    public List<Article> findAll() {
        return new ArrayList<>(articles);
    }

    @Override
    public void save(Article article) {
        if (!articles.contains(article)) {
            articles.add(article);
        }
    }

    @Override
    public void delete(int articleId) {
        articles.removeIf(article -> article.getId() == articleId);
    }
}

// Article-Klasse (nur als Beispiel)
public class Article {
    private int id;
    private String title;
    private String content;

    // Konstruktor, Getter und Setter
}
```

Nutzung:

```java
public class ArticleService {
    private ArticleRepository articleRepository;

    // Konstruktorinjektion des ArticleRepository-Interfaces
    public ArticleService(ArticleRepository articleRepository) {
        this.articleRepository = articleRepository;
    }

    public Article findArticleById(int articleId) {
        return articleRepository.findById(articleId);
    }

    public List<Article> findAllArticles() {
        return articleRepository.findAll();
    }

    public void saveArticle(Article article) {
        articleRepository.save(article);
    }

    public void deleteArticle(int articleId) {
        articleRepository.delete(articleId);
    }
}
```

In diesem Beispiel ermöglicht das Repository Pattern dem **`ArticleService`**, mit Artikeldaten zu arbeiten, ohne die genaue Implementierung des Datenzugriffs zu kennen. Falls die Datenquelle geändert werden muss (z. B. von einer Datenbank zu einer externen API), sind nur Änderungen im **`ArticleRepository`** erforderlich, während der **`ArticleService`** unverändert bleibt.


### Plugin-Pattern

**Entwurfsproblem:**

- Erweiterbarkeit einer Anwendung soll verbessert werden
- Möglichkeit des Hinzufügens neuer Module und Funktionen, ohne dabei den bestehenden Code zu verändern
    - Oft müssen Änderungen im ganzen Code durchgeführt werden, wenn man bestimmte Funktionalitäten im Code ergänzen will. Das Plugin-Pattern soll dies verhindern.
- Schaffung einer Struktur, die Funktionen modular hinzufügen kann


**UML-Diagramm:**

![Abb.2: UML-Diagramm des Plugin-Pattern](media/pluginpattern.png)

Abb.2: UML-Diagramm des Plugin-Pattern

- Schnittstelle “Plugin”
    - definiert die Struktur eines Plugins → Garantie, dass die erstellte neue Funktion zur Architektur der Software passt
- Klasse “Pluginmanager”
    - Verwaltete die Plugins → Plugins können über Methode hinzugefügt werden


**Anwendungsbeispiel:**

Angenommen, wir haben eine Textverarbeitungsanwendung, die um zusätzliche Funktionen erweitert werden soll. Wir könnten Plugins für Rechtschreibprüfung, Übersetzung und Textformatierung erstellen. Diese Plugins könnten unabhängig voneinander entwickelt und zur Anwendung hinzugefügt oder daraus entfernt werden, ohne den Kern der Textverarbeitungsanwendung zu beeinträchtigen.


Implementierungsbeispiel:

```java
// Plugin-Schnittstelle
public interface TextPlugin {
    void processText(String text);
}

// Plugin-Implementierungen
public class SpellCheckerPlugin implements TextPlugin {
    @Override
    public void processText(String text) {
        // Implementierung der Rechtschreibprüfung
        // ...
    }
}

public class TranslationPlugin implements TextPlugin {
    @Override
    public void processText(String text) {
        // Implementierung der Übersetzung
        // ...
    }
}

// Plugin-Manager
public class PluginManager {
    private List<TextPlugin> plugins = new ArrayList<>();

    public void addPlugin(TextPlugin plugin) {
        plugins.add(plugin);
    }

    public void removePlugin(TextPlugin plugin) {
        plugins.remove(plugin);
    }

    public void executeAll(String text) {
        for (TextPlugin plugin : plugins) {
            plugin.processText(text);
        }
    }
}
```

Benutzung:

```java
public class TextProcessor {
    public static void main(String[] args) {
        // Textverarbeitungsanwendung
        PluginManager pluginManager = new PluginManager();

        // Hinzufügen von Plugins zur Anwendung
        pluginManager.addPlugin(new SpellCheckerPlugin());
        pluginManager.addPlugin(new TranslationPlugin());

        // Textverarbeitung mit allen Plugins
        String inputText = "Hello, how are you?";
        pluginManager.executeAll(inputText);
    }
}
```

In diesem Beispiel können neue Textverarbeitungsfeatures einfach hinzugefügt oder entfernt werden, indem neue Implementierungen der **`TextPlugin`**-Schnittstelle erstellt und dem **`PluginManager`** hinzugefügt oder daraus entfernt werden. Dies erleichtert die Erweiterung der Anwendung ohne direkte Modifikation des bestehenden Codes.


### Bridge-Pattern

**Entwurfsproblem:**

- Trennung von Abstraktion und Implementierung
- Problem: Abstrakte Klasse und Implementierung sind häufig miteinander verbunden
    - Wenn ich in der abstrakten Klasse oder der Implementierung dieser etwas ändere, muss ich diese Änderungen auch an der jeweils anderen Stelle umsetzen → erheblicher Mehraufwand
- Bridge-Pattern trennt Abstraktion und Implementierung
    - Änderungen an der Abstraktion oder der Implementierung können dann unabhängig voneinander gemacht werden


**UML-Diagramm:** 

![Abb.3: UML-Diagramm des Bridge-Pattern](media/bridgepattern.png)

Abb.3: UML-Diagramm des Bridge-Pattern

- “Abstraction”
    - hält Referenz auf das “Implementation”-Interface
    - enthält Methode “operation”, die von den Klassen implementiert wird
- “Implementation”
    - wird von den konkreten Implementierungen implementiert
- “ConcreteImpl”
    - Konkrete Implementierung des Interfaces
- Beziehungen:
    - Abstraction hält lose Referenz auf das “Implementation”-Interface → ermöglicht die lose Kopplung


**Anwendungsbeispiel:**

Angenommen, wir entwickeln eine Grafikbibliothek, bei der Formen auf verschiedenen Plattformen gerendert werden sollen. Das Bridge Pattern könnte verwendet werden, um die Formen von der spezifischen Rendering-Implementierung zu entkoppeln.


Implementierungsbeispiel:

```java
// Implementierungsschnittstelle
public interface DrawingAPI {
    void drawCircle(int radius, int x, int y);
    void drawSquare(int side, int x, int y);
}

// Abstrakte Klasse (Abstraktion)
public abstract class Shape {
    protected DrawingAPI impl;

    protected Shape(DrawingAPI impl) {
        this.impl = impl;
    }

    public abstract void draw();
}

// Implementierung (Concrete Implementor)
public class DrawingAPI1 implements DrawingAPI {
    @Override
    public void drawCircle(int radius, int x, int y) {
        System.out.println("API1: Drawing circle with radius " + radius + " at position (" + x + "," + y + ")");
    }

    @Override
    public void drawSquare(int side, int x, int y) {
        System.out.println("API1: Drawing square with side " + side + " at position (" + x + "," + y + ")");
    }
}

// Konkrete Klasse (Abstraktion)
public class Circle extends Shape {
    private int radius;
    private int x;
    private int y;

    public Circle(int radius, int x, int y, DrawingAPI impl) {
        super(impl);
        this.radius = radius;
        this.x = x;
        this.y = y;
    }

    @Override
    public void draw() {
        impl.drawCircle(radius, x, y);
    }
}
```

Nutzung des Bridge-Patterns:

```java
public class Client {
    public static void main(String[] args) {
        // Initialisierung mit einer spezifischen Implementierung
        DrawingAPI drawingAPI1 = new DrawingAPI1();

        // Verwendung der Abstraktion mit der Implementierung
        Shape circle = new Circle(5, 10, 15, drawingAPI1);
        circle.draw();
    }
}
```

In diesem Beispiel kann die Implementierung (**`DrawingAPI1`**) leicht ausgetauscht werden, ohne Änderungen an der Abstraktion (**`Circle`**) vornehmen zu müssen. Dies ermöglicht eine flexible und leicht wartbare Struktur für die Grafikbibliothek.



### Visitor-Pattern

**Entwurfsproblem:** 

- Erweiterung von Klassen um neue Operationen, ohne den Code der Klassen zu ändern
- Klassen teilen häufig gemeinsame Schnittstellen
- Neue Operationen werden durch Hinzufügen von externen Besuchern erweitert
    - Die innere Struktur der Klassen wird aber nicht verändert


**UML-Diagramm:**

![Abb.4: UML-Diagramm des Visitor-Patterns](media/visitorpattern.png)

Abb.4: UML-Diagramm des Visitor-Patterns

- **`Visitor` (Besucher):**
    - Das Besucher-Interface, das eine Methode **`visit()`** für jeden konkreten Elementtyp definiert.
    - Durch diese Methode kann der Besucher spezifische Operationen auf den konkreten Elementen ausführen.
- **`ConcreteVisitor` (Konkreter Besucher):**
    - Eine konkrete Implementierung des Besucher-Interfaces.
    - Implementiert die spezifischen **`visit()`**Methoden für jeden konkreten Elementtyp.
- **`Element` (Element):**
    - Das Element-Interface, das eine Methode **`accept()`** definiert, die einen Besucher akzeptiert.
    - Durch die **`accept()`**Methode kann der Besucher auf das Element zugreifen und die **`visit()`**Methode aufrufen.
- **`ConcreteElement` (Konkretes Element):**
    - Eine konkrete Implementierung des Element-Interfaces.
    - Implementiert die **`accept()`**Methode, die den Besucher akzeptiert.


**Anwendungsbeispiel:**

Angenommen, wir haben eine hierarchieübergreifende Datenstruktur von geometrischen Formen in einer Grafikanwendung. Die Formen können Kreise, Rechtecke und Dreiecke sein. Wir möchten eine Funktionalität implementieren, die es einem Benutzer ermöglicht, die Fläche jeder Form zu berechnen, ohne den Code der Formklassen zu ändern. Hier kommt das Visitor-Pattern ins Spiel.



**Implementierung:**


```java
// Element: Das abstrakte Element, das von Besuchern akzeptiert wird.
public interface Shape {
    void accept(Visitor visitor);
}

// ConcreteElement1: Konkrete Implementierung eines Elements (z.B., Kreis).
public class Circle implements Shape {
    private double radius;

    public Circle(double radius) {
        this.radius = radius;
    }

    public double getRadius() {
        return radius;
    }

    @Override
    public void accept(Visitor visitor) {
        visitor.visit(this);
    }
}

// ConcreteElement2: Konkrete Implementierung eines Elements (z.B., Rechteck).
public class Rectangle implements Shape {
    private double width;
    private double height;

    public Rectangle(double width, double height) {
        this.width = width;
        this.height = height;
    }

    public double getWidth() {
        return width;
    }

    public double getHeight() {
        return height;
    }

    @Override
    public void accept(Visitor visitor) {
        visitor.visit(this);
    }
}

// Visitor: Das Besucher-Interface mit einer Methode für jedes Element.
public interface Visitor {
    void visit(Circle circle);
    void visit(Rectangle rectangle);
}

// ConcreteVisitor: Konkrete Implementierung des Besuchers (z.B., Flächenberechnung).
public class AreaVisitor implements Visitor {
    private double totalArea;

    public double getTotalArea() {
        return totalArea;
    }

    @Override
    public void visit(Circle circle) {
        // Berechnung der Kreisfläche: π * r^2
        totalArea += Math.PI * Math.pow(circle.getRadius(), 2);
    }

    @Override
    public void visit(Rectangle rectangle) {
        // Berechnung der Rechteckfläche: width * height
        totalArea += rectangle.getWidth() * rectangle.getHeight();
    }
}

// ObjectStructure: Die Struktur, die Elemente enthält und Besucher akzeptiert.
public class Drawing implements Shape {
    private List<Shape> shapes = new ArrayList<>();

    public void addShape(Shape shape) {
        shapes.add(shape);
    }

    @Override
    public void accept(Visitor visitor) {
        for (Shape shape : shapes) {
            shape.accept(visitor);
        }
    }
}

// Beispielanwendung:
public class Client {
    public static void main(String[] args) {
        // Erstellung der Objektstruktur
        Drawing drawing = new Drawing();
        drawing.addShape(new Circle(5.0));
        drawing.addShape(new Rectangle(3.0, 4.0));

        // Erstellung eines Besuchers
        AreaVisitor areaVisitor = new AreaVisitor();

        // Anwendung des Besuchers auf die Objektstruktur
        drawing.accept(areaVisitor);

        // Ausgabe der Gesamtfläche
        System.out.println("Gesamtfläche: " + areaVisitor.getTotalArea());
    }
}
```

In diesem Beispiel ermöglicht das Visitor-Pattern die Erweiterung der Funktionalität, indem ein neuer Besucher (**`AreaVisitor`**) hinzugefügt wird, ohne die Klassen der konkreten Elemente (**`Circle`**, **`Rectangle`**) zu ändern. Der Besucher kann verschiedene Operationen für jedes konkrete Element ausführen, und die Objektstruktur (**`Drawing`**) ermöglicht es, Besucher zu akzeptieren und auf allen Elementen anzuwenden.


## Entwurf des Datenmodells

- wesentlicher Schritt beim Entwurf von Softwareanwendungen
- erfordert tiefes Verständnis der Domäne
- gute Kommunikation mit den Stakeholdern erforderlich


### Domain-Driven-Design

- Methodische Herangehensweise der Softwareentwicklung
    - Komplexität der Geschäftsbereiche soll modelliert werden


**Domain vs. Model**

- Domain
    - bezieht sich auf realen Geschäftsbereich, dass von der Softwareanwendung adressiert wird
    - Domain ist der Fokus von DDD
    - Ziel: Komplexen Anforderungen der Domäne zu verstehen → Modell schaffen, was die Anforderungen umsetzt
- Model
    - Repräsentiert abstrakte Darstellung der Domäne in der Software
    - Modell ist Ergebnis des DDD-Prozesses, bei der die Struktur mithilfe von Entitäten, Value Objects, Aggregates und Services festgelegt wird
    - Ziel: Modell zu schaffen, dass die Anforderungen der Domain erfüllt, aber auch flexible in der Zukunft erweiterbar ist
- Zusammenfassung
    - Domain ist Geschäftsbereich, den die Software adressiert
    - Modell ist die technische Umsetzung in der Software


Entities, Value Objects, Aggregates, Services, Factories

- Entities
    - Objekte, mit einer eindeutigen Identifikation, die über die Zeit beständig bleibt
    - Zustandsänderungen sind möglich
    - Zum Beispiel: Ein User in einem sozialen Netzwerk kann eine Entity sein → User hat eindeutige Benutzer-ID, bleibt über die Zeit identifizierbar und kann durch Aktualisierung seines Profils eine Zustandsänderung herbeiführen
- Value Objects
    - Objekte ohne eigene Identität
    - Definiert durch Attribute, welche unveränderlich sind
    - Z.B. Eine “Color” → Nicht veränderbar, festgelegte RGB-Werte
- Aggregates
    - Gruppen von Entities, die als eine Einheit betrachtet werden
    - Es gibt eine Wurzelentität, die alle Änderungen an den Entities verwaltet, um Konsistenz sicherzustellen
    - Z.B. Eine “Order”-Aggregate, die die Entity “OrderItem” und das Value Object “Shipping Adress” beeinhaltet
- Services (Dienste)
    - enthalten Geschäftslogiken, die nicht zu einer Entity oder einem Value Object gehören → häufig Prozesse
    - Services können wiederverwendet werden
    - z.B. “PaymentService” kann Logiken für die Zahlung enthalten
- Factories (Fabriken)
    - Factories sollen komplexe Objekte erstellen
    - kümmern sich um die richtige Konfiguration der erstellten Objekte
    - z.B.: “OrderFactory” könnte Bestellobjekte erstellen, und darauf achten, dass alle erforderlichen Attribute vorhanden sind



**Ubiquitäre Sprache**

- zentrales Konzept im DDD
- soll ein gemeinsames Verständnis zwischen allen Beteiligten schaffen
    - dazu gehören Stakeholder, Entwickler, Fachexperten, …
- alle beteiligten Personen sollen dasselbe Verständnis von den verwendeten Begriffen haben

**Warum ist die ubiquitäre Sprache wichtig?**

- Vermeidung von Missverständnissen
    - Risiko von Missverständnissen wird durch eine gemeinsam festgelegte Kommunikation verringert
    - Alle Personen wissen, was bestimmte Begriffe bedeuten
- Einheitliches Verständnis
    - Alle Begriffe sind klar definiert und führen so einem gemeinsamen Verständnis dieser.
- Effektivere Kommunikation
    - Begriffserklärungen entfallen, wenn jede beteiligte Person ein Verständnis von den verwendeten Begriffen hat.

Wie wird die ubiquitäre Sprache entwickelt?

- Workshops und Meetings
    - Workshops und Meetings zwischen Entwicklern und Fachexperten fördern Austausch von Ideen und es entsteht eine gemeinsame Sprache.
- Dokumentation
    - Ubiquitäre Sprache wird dokumentiert und ist dann Bestandteil der Projektdokumentation → Alle Teammitglieder haben Zugriff
- Feedback
    - Rückmeldungen von allen Beteiligten einholen, um eventuelle Missverständnisse zu klären → Ubiquitäre Sprache wird kontinuierlich verbessert.



**Anemic Domain Model**

- Art der Modellierung von Softwareanwendungen
- Trennung von Daten- und Geschäftslogik
- Datenklasse sind lediglich Datenstrukturen
- Geschäftslogik ist eine separate Anwendungsschicht



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



### Usability

- bezieht sich auf die Benutzerfreundlichkeit eines Produkts
- Wie ist es für einen Benutzer, eine bestimmte Aufgabe mit dem Produkt zu erfüllen?
- konzentriert sich auf Aspekte wie Effizienz, Effektivität und Zufriedenstellung bei der Verwendung des Produkts
- Bsp: Eine Website mit klarer Navigation und einfachen Formularen wird als “usability-freundlich” eingeordnet



### User Experience (UX)

- gesamte Erfahrung eines Benutzers mit einem Produkt
- Alle Aspekte
    - Interaktionen, Emotionen, psychisches Wohlbefinden des Benutzers
- Bsp.: Website mit klarer Navigation und ansprechenden Produktbildern → Nutzer fühlt sich wohl



### Customer Experience (CX)

- Alle Interaktionen, die ein Kunde mit einem Kunden hat
- geht über das Produkt hinaus und umfasst den gesamten Lebenszyklus der Kundenbeziehung
- alle Kontaktpunkte zwischen dem Kunden und dem Unternehmen
    - Marketing, Verkauf, Kundenservice, Unterstützung
- Positive Gesamterfahrung mit dem Kunden soll gefördert werden



### Nielsen's 10 Usability Heuristic Principles für das UI-Design

- Grundsätze für das UI-Design
- Richtlinien, mit denen die Benutzerfreundlichkeit von Schnittstellen verbessert werden kann
1. Sichtbarkeit des Systemstatus
    - Benutzer muss immer darüber informiert werden, was gerade passiert
2. Übereinstimmung von Systemen und Realität
    - Darstellung von Informationen im System sollte mit der realen Welt übereinstimmen
3. Benutzerkontrolle und Freiheit
    - Benutzer muss jederzeit den Systemvorgang abbrechen können
4. Konsistenz und Standards
    - Konsistente Standards sollten sich über die gesamte Anwendung ziehen
5. Fehlervermeidung
    - System sollte selbstständig Benutzerfehler vermeiden oder auftretende Fehler verzeihen
6. Anerkennung statt Erinnerung
    - Informationen sollten nicht vom Benutzer aus dem Gedächtnis abgerufen werden müssen, sondern direkt verfügbar sein
7. Flexibilität und Effizienz der Nutzung
    - Verschiedene Wege zur Bearbeitung von Aufgaben sollten geboten werden
8. Ästhetisches und minimalistisches Design
    - keine unnötigen Informationen oder Designs
9. Fehlerdiagnose und Wiederherstellung
    - Fehlermeldungen sollen klare Informationen über den Fehler und die Behebung des Fehlers bieten
10. Hilfe und Dokumentation
    - System sollte keine umfangreiche Dokumentation erfordern
    - Hilfe, wenn notwendig, sollte leicht auffindbar sein



### Shneiderman’s 8 Golden Rules

- Regeln für das UI-Design
1. Klarheit der Dialoge
    - Klare, prägnante und einfache Sprache
    - Informationen sollen leicht zugänglich sein
2. Konsistenz
    - Konsistente Standards sollten innerhalb der Anwendung und zu anderen Anwendungen beibehalten werden
3. Rückmeldung
    - System muss Benutzer sofortige Rückmeldung über den Systemzustand geben
4. Dialogsteuerung für den Benutzer
    - Benutzer sollte Kontrolle über das System haben → System sollte nicht den Benutzer “diktieren”
5. Fehlervermeidung und -behandlung
    - Design sollte Benutzerfehler vermeiden und Fehlerbehandlung anbieten
6. Wiedererkennung statt Erinnerung
    - Benutzer sollten nicht gezwungen sein, Erinnerungen aus dem Gedächtnis abzurufen
7. Flexibilität und Effizienz der Nutzung:
    - Das System sollte verschiedene Wege bieten, um Aufgaben zu erledigen, und effiziente Wege für erfahrene Benutzer unterstützen.
8. Ästhetik und minimalistisches Design:
    - Informationen sollten klar und prägnant präsentiert werden, und das Design sollte frei von unnötigem Schnickschnack sein.



### Norman's 7 Principles

- Designer und Forscher, der 7 Prinzipien für gutes Design formuliert hat
1. **Sichtbarkeit (Visibility):**
    - Die Funktionen und Möglichkeiten des Systems sollten für den Benutzer sichtbar und leicht verständlich sein.
2. **Feedback:**
    - Das System sollte dem Benutzer unmittelbares Feedback über den aktuellen Zustand und die Auswirkungen seiner Aktionen geben.
3. **Affordanz:**
    - Das Design sollte dem Benutzer klare Hinweise darauf geben, wie es verwendet werden kann (z. B. Schaltflächen sollten wie Schaltflächen aussehen).
4. **Rückgängig machen (Undo):**
    - Benutzer sollten in der Lage sein, ihre Aktionen rückgängig zu machen, falls sie einen Fehler gemacht haben oder ihre Aktion rückgängig machen möchten.
5. **Entdeckbarkeit:**
    - Wichtige Funktionen und Optionen sollten leicht auffindbar und entdeckbar sein, ohne dass der Benutzer sie aktiv suchen muss.
6. **Verständlichkeit:**
    - Das Design sollte selbst für neue Benutzer leicht verständlich sein, ohne dass umfangreiche Erklärungen erforderlich sind.
7. **Konsistenz:**
    - Das Design sollte konsistent sein, sowohl innerhalb der Anwendung als auch im Vergleich zu anderen Anwendungen, um Verwirrung zu vermeiden.


## Abbildungen

- https://www.microconsult.de/blog/2019/05/fl_solid-prinzipien/

- https://www.tedinski.com/2018/12/18/the-law-of-demeter.html

- https://feature-sliced.design/docs/reference/isolation/coupling-cohesion

- https://www.freecodecamp.org/news/orthogonality-in-software-engineering/.

- https://smits-net.de/images/posts/uml_beispiel.png

- https://www.infoworld.com/article/3107186/how-to-implement-the-repository-design-pattern-in-c.html](https://www.infoworld.com/article/3107186/how-to-implement-the-repository-design-pattern-in-c.html)


## Referenzen

- https://www.freecodecamp.org/news/orthogonality-in-software-engineering/.

- https://media.geeksforgeeks.org/wp-content/uploads/Untitled-28.png

- https://feature-sliced.design/docs/reference/isolation/coupling-cohesion

- https://smits-net.de/images/posts/uml_beispiel.png

- https://files.ifi.uzh.ch/rerg/amadeus/teaching/courses/software_engineering_ws0506/Kapitel_05_Sw_Entwurf.pdf

- https://www.tedinski.com/2018/12/18/the-law-of-demeter.html

- https://stackify.com/dependency-injection/#:~:text=Dependency%20injection%20is%20a%20programming,inversion%20and%20single%20responsibility%20principles.

- https://t2informatik.de/wissen-kompakt/kiss-prinzip/

- https://thevaluable.dev/kiss-principle-explained/

- https://www.microconsult.de/blog/2019/05/fl_solid-prinzipien/

- https://de.wikipedia.org/wiki/Entwurfsmuster [letzte Einsicht: 16.11.2023]

- https://deviq.com/design-patterns/repository-pattern [letzte Einsicht: 16.11.23]

- Anwendungs- und Codebeispiele wurden von ChatGPT-3.5 erstellt: https://chat.openai.com

- https://de.wikipedia.org/wiki/Br%C3%BCcke_(Entwurfsmuster) [letzte Einsicht: 16.11.23]

- https://www.ionos.de/digitalguide/websites/web-entwicklung/was-ist-das-visitor-pattern/ [letzte Einsicht: 16.11.23]

- https://de.wikipedia.org/wiki/Besucher_(Entwurfsmuster)#:~:text=Der%20Besucher%20 [letzte Einsicht: 16.11.23]

- https://entwickler.de/ddd/einfuhrung-in-die-konzepte-von-domain-driven-design-001 [letzte Einsicht: 17.11.23]

- https://stackoverflow.com/questions/4166816/domain-driven-design-vs-model-driven-architecture [letzte Einsicht: 17.11.23]

- https://lostechies.com/jimmybogard/2008/05/21/entities-value-objects-aggregates-and-roots/ [letzte Einsicht: 17.11.23]

- https://entwickler.de/software-architektur/eine-gemeinsame-sprache-sprechen [letzte Einsicht: 17.11.23]

- https://en.wikipedia.org/wiki/Anemic_domain_model [letzte Einsicht: 17.11.23]

- https://www.visual-paradigm.com/guide/ux-design/wireframe-vs-storyboard-vs-wireflow-vs-mockup-vs-prototyping/ [letzte Einsicht: 17.11.23]

- https://www.usability.gov/what-and-why/user-interface-design.html [letzte Einsicht: 17.11.23]

- https://www.conductor.com/de/academy/glossar/user-experience/ [letzte Einsicht: 17.11.23]

- https://www.oracle.com/de/cx/what-is-cx/ [letzte Einsicht: 17.11.23]

- https://www.nngroup.com/articles/ten-usability-heuristics/

- https://www.cybay.de/blog/die-8-goldenen-regeln-fuer-interface-design [letzte Einsicht: 17.11.23]

- https://www.educative.io/answers/what-are-normans-design-principles [letzte Einsicht: 17.11.23]