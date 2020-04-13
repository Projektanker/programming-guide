Programming Guide
======
- [Code Design](#code-design)
    - [SOLID Prinzipien](#solid-prinzipien)
        - [**S**ingle Responsibility Principle](#single-responsibility-principle)
        - [**O**pen Closed Principle](#open-closed-principle)
        - [**L**iskov Substituion Principle](#liskov-substituion-principle)
        - [**I**nterface Segregation Principle](#interface-segregation-principle)
        - [**D**ependency Inversion Principle](#dependency-inversion-principle)

    - [UML Klassendiagramme](#uml-klassendiagramme)
        - [UML - klassenspzifische Angaben](#uml---klassenspzifische-angaben)
        - [Vererbung / Verbindungen zwischen Klassen / Multiplizitäten](#vererbung-verbindungen-zwischen-klassen-multiplizitäten)

    - [Design Patterns](#design-patterns)
        - [Erzeugungsmsuter](#erzeugungsmsuter)
            - [Factory Method Pattern](#factory-method-pattern)
            - [Abstract Factory Pattern](#abstract-factory-pattern)
            - [Singleton Pattern](#singleton-pattern)
        - [Strukturmuster](#strukturmuster)
            - [Adapter Pattern](#adapter-pattern)
            - [Composite Pattern](#composite-pattern)
            - [Decorator Pattern](#decorator-pattern)
            - [Facade Pattern](#facade-pattern)
            - [Flyweight Pattern](#flyweight-pattern)
            - [Proxy Pattern](#proxy-pattern)
        - [Verhaltensmuster](#verhaltensmuster)
            - [Command Pattern](#command-pattern)
            - [Iterator Pattern](#iterator-pattern)
            - [Mediator Pattern](#mediator-pattern)
            - [Memento Patttern](#memento-patttern)
            - [Observer Pattern](#observer-pattern)
            - [Strategy Pattern](#strategy-pattern)
            - [Template Method Pattern](#template-method-pattern)
            - [State Pattern](#state-pattern)
- [C\#](#c)
    - [Threads](#threads)
- [Mathmatics](#mathematics)

- [Unity](#unity)
    - [Unity Shortcuts](#unity-shortcuts)
    - [Style Guide](#style-guide)
        - [Welche Klassen/Scripte machen Sinn?](#welche-klassenscripte-machen-sinn)
        - [Welche Szenen machen Sinn?](#welche-szenen-machen-sinn)
        - [Controller](#controller)
        - [Refactoring](#refactoring)
        - [Reusability](#reusability)
    - [Delegaten/Lambda Expressions](#delegatenlambda-expressions)
        - [Delegaten](#delegaten)
        - [Lambda Expressions](#lambda-expressions)
        - [Events](#events)
    - [Performance](#performance)
        - [Allgemein](#allgemein)
        - [Math-Functions](#math-functions)
        - [Object-Pooling](#object-pooling)
    - [Special Folders](#special-folders)
        - [StreamingAssets](#streamingassets)
        - [Scripts/Editor](#scriptseditor)
        - [Resources](#resources)
        - [Plugins](#plugins)
    - [Deklarationen](#deklarationen)
        - [Static](#static)
        - [Enum](#enum)
    - [Events](#events-1)
        - [Allgemein](#allgemein-1)
        - [Deklaration](#deklaration)
        - [Aufruf](#aufruf)
        - [Registrierung des Handlers](#registrierung-des-handlers)
        - [Registrierung eines Handlers auf mehreren Objekte](#registrierung-eines-handlers-auf-mehreren-objekte)
    - [Mathfunctions](#mathfunctions)
        - [Allgemein](#allgemein-2)
        - [Winkel](#winkel)
        - [Distanzen](#distanzen)
    - [MonoBehaviour](#monobehaviour)
        - [Flowchart](#flowchart)
        - [Mouse Input](#mouse-input)

    - [Visual](#visual)
        - [Rotationen](#rotationen)
            - [Quaternion vs. Euler](#quaternion-vs.-euler)
            - [Space](#space)
            - [Mathfunctions](#mathfunctions-1)
            - [LookAt](#lookat)
            - [Rotationen Damping](#rotationen-damping)
        - [Animationen](#animationen)
            - [Anlegen von Animations Clips](#anlegen-von-animations-clips)
            - [Bearbeiten von Animations Clips](#bearbeiten-von-animations-clips)
            - [Anlegen von Propertys in Clips](#anlegen-von-propertys-in-clips)
            - [Erstellen von Keyframes](#erstellen-von-keyframes)
            - [Bearbeiten von Keyframes (Preview-Mode)](#bearbeiten-von-keyframes-preview-mode)
            - [Animator Probleme](#animator-probleme)
        - [Materials](#materials)
            - [Material Charts](#material-charts)
        - [Texturen](#texturen)
            - [Import](#import)
            - [Rendertexturen](#rendertexturen)
        - [Level of Detail -- LOD](#level-of-detail-lod)
            - [Naming](#naming)

    - [Datenverarbeitung](#datenverarbeitung)
        - [XML](#xml)
            - [Aufbau XML](#aufbau-xml)
            - [Datenklasse in Unity anlegen](#datenklasse-in-unity-anlegen)
            - [Einlesen XML in Unity](#einlesen-xml-in-unity)

    - [AI](#ai)
        - [NavMesh](#navmesh)
        - [Setup](#setup)
        - [Setup Area](#setup-area)
        - [NavMeshAgent](#navmeshagent)
        - [Obstacles](#obstacles)
        - [NavMesh Link](#navmesh-link)

    - [Builds](#builds)

    - [Third PartyPlugins](#third-partyplugins)
        - [ILocalization](#i2-localization)
            - [Setup](#setup-1)
            - [Sprachen einstellen](#sprachen-einstellen)
            - [Übersetzungen definieren](#übersetzungen-definieren)
            - [Update](#update)
    
- [Visual Studio](#visual-studio)
    - [Shortcuts Text](#shortcuts-text)
    - [Navigation & Windows](#navigation-windows)
    - [Running, Debugging & Compiling](#running-debugging-compiling)
    - [Code Snippets](#code-snippets)
    - [Extensions](#extensions)
        
- [Tipps und Tricks](#tipps-und-tricks)
    - [View und Engine](#view-und-engine)

- [Anhang](#anhang)
    - [Tutorials](#tutorials)

Code Design
===========

SOLID Prinzipien
----------------

### **S**ingle Responsibility Principle

-   Eine Klasse hat nur eine Verantwortung
-   Sollte nur einen Grund zur Klassenveränderung
-   Probleme:
    -   Was genau ist unter EINER Verantwortung zu verstehen?
    -   Lösung: Verantwortung muss definiert werden

### **O**pen Closed Principle

-   Code sollte offen für Erweiterungen sein, aber geschlossen für
    Modifikation (neuen Code hinzufügen ohne alten zu verändern)
-   **Vererbung** ist wichtig für dieses Prinzip (**Abstrakte** Klassen
    erstellen, von denen geerbt werden kann, um spezifische Methoden
    oder Eigenschaften zu implementieren)
-   Weitere Lösungen:
    -   Interfaces
    -   Möglichst viele Abstraktion einführen

-   **Wichtig**: Nicht übertreiben! Abstraktion erhöht die Komplexität!

### **L**iskov Substituion Principle

-   Unterklasse sollte Funktionalität der Oberklasse nur erweitern,
    nicht verändern oder einschränken **oder**
-   Unterklasse sollte immer so verwendbar sein, wie die Oberklasse

### **I**nterface Segregation Principle

-   Zu große Schnittstellen sollten in kleiner aufgeteilt werden
-   **Vorteile**: schlanke Interfaces, jedes Interface hat eine
    Zuständigkeit, leichtere Wartung, Klassen implementieren nur das
    nötigste

### **D**ependency Inversion Principle

-   Klassen höhere Ebene sollten nicht von Klassen niederer Ebene
    abhängen. (Abstraktion mittels Interfaces)
-   Schnittstellen sollten nicht von Details abhängen, sondern von den
    Details der Schnittstelle

-   **Vorteile:**
    -   Erweiterung oder Austausch der unteren Ebene ohne Änderungen an
        der höheren Ebene
    -   Höhere Ebene muss viel weniger über untere Ebene wissen, da
        Interface alles bereitstellt

UML Klassendiagramme
--------------------

-   Unified Modelling Language
    -   Besteht aus zahlreichen Digrammtypen
    -   Softwaresysteme aus unterschiedlichen Perspektiven darstelllen

-   UML-Klassendiagramme stellen statische Struktur eines Systems dar
    -   Beispielsweise erstellbar bei: <https://www.draw.io>

### UML - klassenspzifische Angaben

-   Zugriffsmodifikatoren
    -   public: +
    -   protected: \#
    -   private: -
    -   internal: \~

-   Variablen/Eigenschaften:
    -   Kleingeschrieben: Variable
    -   Großgeschrieben: Property

-   Variablen, Properties oder ähnliches kann auch vor der Angabe
    deklariert werden
    -   Bsp: \<\<Property\>\> + Name
    -   \<\<Abstract\>\> class
    -   \<\<Variable\>\> + name

### Vererbung / Verbindungen zwischen Klassen / Multiplizitäten

-   **Verberbung** wird als Pfeil mit Keyword „extends dargestellt"
-   **Assoziation** wird mit einer einfachen Verbindung zwischen zwei
    Klassen dargestellt
-   **Composition** wird als Pfeil mit ausgemalter Raute dargestellt
    (Teil-Ganze-Beziehung)
    -   Def. Composition: Die abhängige Klasse kann nur existieren, wenn
        die andere Klasse existiert Bsp.: Zoo Toilette

-   **Aggregation** wird als Pfeil mit nicht ausgemalter Raute
    dargestellt (Teil-Ganze-Beziehung)
    -   Def. Aggregation: Die abhängige Klasse kann auch ohne die andere
        Klasse existieren

-   **Multiplizitäten** drücken aus, wie viele Objekte einer Klasse A
    mit Objekten einer Klasse B in Verbindung stehen können
    -   Dabei können an die Assoziationen die Mengen geschreiben werden
    -   Bsp.: 1 Person besitzt mind. 1 bis unendlich viele Autos
    ![](.//media/image1.PNG)

Design Patterns
---------------

-   Warum? Wartbarkeit des Codes nachfolgende Besipiele sind
    Best-Practice-Lösung
-   Buch: Design Patterns -- Elements of Reusable Object-Oriented
    Software
-   Kategorien
    -   Erzeugungsmuster
        -   Zweck: Erzeugen voon Objekten
        -   Prinzip:
            -   Client benötigt Objekt von bestimmten Typ
            -   Erzeugerklasse wird beauftragt, Objekt zu erzeugen
            -   Client benötigt keine Infos über Erzeugung

    -   Strukturmuster
    -   Verhaltensmuster

###  Erzeugungsmsuter

#### Factory Method Pattern

-   **Zweck**: Sinnvoll, wenn erst zur Laufzeit des Programms Klassen
    ausgewählt und Objekte davon erzeugt werden sollen
-   **Anwendungsfall**: Wenn zur Zeit der Programmierung noch **nicht**
    klar ist, welches konkrete Objekt benötigt wird
-   UML:![](.//media/image2.PNG)

-   Vorteile:
    -   Erweiterbarkeit
    -   Wiederverwendbarkeit
    -   Client ist entkoppelt

-   Nachteile:
    -   Zwei Vererbungshierarchien

#### Abstract Factory Pattern

-   **Zweck:** s. [Factory Method Pattern](#factory-method-pattern) -
    Unterschied: Nicht nur ein Produkt, sondern Produkfamilie erzeugen
-   **Anwendungsfall:** s. [Factory Method
    Pattern](#factory-method-pattern)

-   UML:![](.//media/image3.PNG)

-   Vorteile:
    -   Client komplett enkoppelt
    -   Erweiterbarkeit

-   Nachteile:
    -   Erweiterbarkeit
        -   Neue Produkte in der Produktfamilie hinzuzufügen ist
            schwierig bricht mit bestehendem Code

#### Singleton Pattern

-   **Zweck:** Es darf von einer Klasse nur eine Instanz erzeugt werden
-   **Anwendungsfall:** Für eine Aufgabe, bei der nur ein Objekt
    benötigt wird (Controller)
-   UML:![](.//media/image4.png)

-   Kategorien:
    -   Basic Singleton
    -   Lazy Singleton -- erweiterter Basic Singleton, **Instance wird
        nur angelegt, wenn sie wirklich benötigt wird,** Instanz wird im
        getInstance() erstellt
    -   Threadsafe Singleton -- erstellen von
        -   Private static object lockobjet = new object();
        -   In getInstance Methode:

> *lock (lockobject)*
>   *{*
>       *If (instance==null)*
>           *Instance = new Singleton();*
>   *}*

-   Vorteile:

    -   Ersetzt global zugägnliche Variablen

    -   Verhindert, dass unnötig viele Objekte erstellt werden

-   Nachteile:

    -   Bedingungslose und globale Verfügung

    -   Wartbarkeit

### Strukturmuster

**Zweck:** Zusammensetzung von Objekten und Klassen, um größere
Strukturen zu bilden

#### Adapter Pattern

-   **Zweck:** dient der Übersetzung einer Schnittstelle in eine andere.
    Dadurch wird Kommunikation von Klassen mit **zueinander
    inkompatiblen Schnittstellen** möglich.

-   **Anwendungsfall:** Wenn bestimmte Klassen zur Wiederverwendung
    konzipiert wurden (Klassenbibliotheken)

-   ![](.//media/image5.png){width="6.3in"
    height="2.8777777777777778in"}UML:

-   **Wichtig:** Aufwand abschätzen! Wenn zu groß, Klasse neu schreiben
    und direkt Interface implementieren

-   Vorteile:

    -   Wiederverwendbarkeit und Flexibilität erhöht

    -   Verbindung von zwei inkompatiblen Interfaces

-   Nachteile:

    -   Arbeitsaufwand entlang einer Adapterkette kann hoch sein

#### Composite Pattern

-   **Zweck:** stellt einen Mechanismus zur Verfügung, einfache und
    komplex zusammengesetzte Objekte **einheitlich zu behandeln**.
    Objekte werden zu sogennanten **Baumstrukturen** zusammengefügt, um
    Teil-Ganze Hierarchien zu repräsentieren.

-   **Anwendungsbeispiel:** Filesystem (Diretory = Composite / File =
    Leaf)

-   ![](.//media/image6.png){width="4.8805555555555555in"
    height="2.703472222222222in"}UML:

-   Vorteile:

    -   Einheitliche Behandlung von Primitiven und Kompositionen

    -   Flexibilität und Erweiterbarkeit

    -   Verschachteltet Strukturen mit beliebiger Tiefe möglich

-   Nachteile:

    -   Entwurf zu allgemein erschwert beschränken der Komposition auf
        bestimmte Klassen

#### Decorator Pattern

-   **Zweck:** Flexible Alternative zur Unterklassenbildung, um eine
    Klasse mit zusätzlichen Funktionaltitäten zur Laufzeit zu erweitern
    (**ohne Vererbung**)

-   ![](.//media/image7.png){width="6.3in" height="3.4125in"}UML:

-   Vorteile:

    -   Extrem große Klassenhierarchien verhindern

    -   Geringerer Wartungsaufwand

    -   Dynamik und Flexibilität

-   Nachteile:

    -   Aufruf einer Basisfunktionalität muss zweimal ausgeführt werden

> Dekorator ist nur ein Wrapper

#### Facade Pattern

-   **Zweck:** bietet eine einheiltiche und meist verinfachte
    Schnittstelle zu einer Menge von Schnittstellen eines Subsystems --
    vor allem bei komplexen Subsystemen sehr gut

-   ![](.//media/image8.png){width="3.566666666666667in"
    height="3.1284722222222223in"}UML:

-   Vorteile:

    -   Lose Kopplung zwischen Client und Subsystem

    -   Senkt Komplexität

-   Nachteile:

    -   Zusätzliche Schichte beeinflusst eventuell Performance

    -   Entwickler müssen lernen, die neue Schnittstelle zu nutzen

#### Flyweight Pattern

-   **Zweck:** Methode zur Speicheroptimierung, wenn von einer Klasse
    sehr viele Objekte erstellt werden, die sich bestimmte variable
    Informationen teilen

> die geteilten Informationen = intrinsische Werte Flyweight Objekte
>
> die außengespeicherten Informationen = extrinsische Werte werden in
> effizienteren Datenstrukturen gespeichert und an Methoden übergeben

-   **Anwendungsfall:**

    -   Anzahl der erzeugten Objekte ist sehr hoch (100k -- 1b oder
        mehr)

    -   Erzeugung der vielen Objekte ist kompliziert und kostet
        Performance

    -   ![](.//media/image9.png){width="5.15625in"
        height="2.9875in"}Objekte besitzen Eigenschaften, die sie sich
        mit anderen Objekten teilen können

-   UML:

-   Vorteile

    -   Sparen von Speicherplatz

-   Nachteile:

    -   Allgemeine Codekomplexität wird erhöht

    -   Vergeudung von CPU-Zeit

#### Proxy Pattern

-   **Zweck:** sorgt dafür, dass der Client nicht direkt mit dem
    Zielobjekt kommuniziert, sondern stattdessen mit dem Proxy, welcher
    dann auf das Zielobjekt zugreift

-   **Anwendungsfälle:**

    -   Schutz-Proxy: Zielobjekt des Clients wird um Schutzebene
        erweitert

    -   Virtuelles-Proxy: verbessert Performance, Objekterstellung wird
        erst dann erstellt, wenn es wirklich benötigt wird0

    -   Remote-Proxy

    -   Dynamisches-Proxy

-   ![](.//media/image10.png){width="5.372916666666667in"
    height="2.8340277777777776in"}UML:

-   Decorator vs. Proxy:

    -   Proxy behält Schnittstelle bei

    -   Decorator fügt zusätzliche Funktionaltitäten hinzu

-   Adapter vs. Proxy

    -   Adapter ändert häufig die Schnittstelle

    -   Proxy stellt immer die vollständige Schnittstelle zur Verfügung

-   Vorteile:

    -   Zusätzliche Ebene der Kontrolle

    -   Steigert Performance des Softwaresystems

-   Nachteile

    -   Komplexität wird erhöht

    -   Geschwindigkeitseinbußen (gerade beim Schutz-Proxy)

    -   Notwenidgkeit die Schnittstelle des Subjekts vollständig im
        Proxy zu implementieren

### Verhaltensmuster

**Zweck:** es geht um die Beziehung, die Interaktion und das Verhalten
von Objekten untereinander

#### Command Pattern

-   **Zweck:** Befehle werden in extra Objekten gekapselt.

> Clients mit verschiedenen Anfragen können parametrisiert werden
>
> Operationen können in eine schlange eingereiht werden
>
> Logbuchführung
>
> Operationen rückgängig machen

-   **Anwendungsfälle:** GUIs, Transaktionssysteme, Befehle zeitlich
    verzögert ausführen

-   ![](.//media/image11.png){width="4.552083333333333in"
    height="2.4208333333333334in"}UML:

> Kann n-ConcreteCommands beinhalten

-   Vorteile:

    -   Wiederverwendbarkeit

    -   Einfache Implementierung der Rückgängig-Funktion

    -   Einfache Protokollierung

    -   Flexibilität

-   Nachteile:

    -   Hohe Klassenanzahl

#### Iterator Pattern

-   **Zweck:** Bereitstellung einer Standardmethode, um eine Gruppe von
    Objekten zu durchlaufen

-   **Anwendungsfälle:**

    -   Zugriff auf Inhalte von Aggregatobjekten (Kümmern sich um
        Datenhaltung), ohne über die interne Darstellung mehr zu wissen

    -   Mehrere Iterationswege zur Verfügung stellen

    -   Durchlaufen von Bäumen, Ergebnisse von Webservices, Cursor auf
        Datenbanken etc.

-   ![](.//media/image12.png){width="5.559027777777778in"
    height="2.7625in"}UML:

    -   Iterator-Methoden Beispiel Methoden

-   Vorteile:

    -   Aggregatobejkt kann auf verschiedene Arten durchlaufen werden

    -   Komplexe Datenstrukture kann vor Clients verborgen werden

    -   Eihnheitliche Schnittstelle, um Datenstrukturen zu durchlaufen

    -   Vereinfacht den Code von Aggregatobjekten

-   Nachteile

    -   Bei einfachen Aggreagtobjekten oft zu komplex

#### Mediator Pattern

-   **Zweck:** Verhindert eine enge Kopplung zwischen verschiedenen
    Objekten, die miteinander kommunizieren müssen. Stellt
    Mediator-Objekt (Vermittler) zur Verfügung, welche die Kommunikation
    zwischen den Objekten übernimmt.

-   **Anwendungsfälle:** Chatroom, Flug-Verkehr-Controller, User in
    Online-Spielen

-   ![](.//media/image13.png){width="4.968055555555556in"
    height="2.8402777777777777in"}UML:

-   Vorteile:

    -   Bessere Wiederverwendbarkeit

    -   LoseKopplung

    -   Änderung des kooperativen Verhaltens kann unabhängig
        durchgeführt werde

-   Nachteile:

    -   Komplexität

#### Memento Patttern

-   **Zweck:** Interner Zustand eines Objektes wird erfasst und
    externalisiert. Objekt kann dadurch zu späterem Zeitpunkt in diesen
    Zustand zurückversetzt werden.

    -   Extra Klasse (Caretaker) sorgt für Aufbewahrung hat keinen
        Zugriff auf Inhalt des Mementos

-   **Anwendungsfall:** Undo-Funktionalität ( z.B.: Text-Verarbeitung),
    Lautstärkeverstellung mit Inkrementierung

-   UML:

    -   Caretaker ruft „createMemento" auf

-   Vorteile:

    -   Speicherung des Objektzustands, ohne Kapselung zu
        beeinträchtigen

    -   Wiederherstellungsmechanismus

    -   Vereinfacht Implementierung der Klasse Originator

-   Nachteil:

    -   Kann sehr aufwendig sein (abhängig von Daten bzw. Zuständen)

#### Observer Pattern

-   **Zweck:** Definiert eine Abhängigkeit zwischen einem und beliebig
    vielen anderen Objekten. Ändert sich der Zustand des einen Objekts,
    werden alle anderen Objekte (Observer) automatisch benachrichtigt
    und aktualisiert.

-   **Prinzip:**

    -   Objekt interessiert sich für den Zustand eines anderen Objekts

    -   Mechanismus: Objekt (Observer) registriert sich bei jeweiligen
        Objekt

> sobald sich Zustand beim beobachteten Objekt ändert, wird
> update()-Methode des Beobachters aufgerufen

-   **Anwednungsfall:** Newsletter, Facebook Beitragsverfolgung,
    WhatsApp Gruppen, Grafische Elemente einer Benutzeroberfläche

-   ![](.//media/image14.png){width="4.979166666666667in"
    height="3.0388888888888888in"}UML:

-   Vorteile:

    -   Zustandskonsistenz

    -   Observer können jederzeit hinzugefügt oder entfernt werden

    -   Subjekt und Beobachter sind lose gekoppelt

-   Nachteile:

    -   Hohe Anzahl an Beobachtern bei Änderungen hohe Änderungskosten
        (Rechenleistung)

    -   Quellcode des Subjekts zeigt nicht, welche Beobachter genau
        informiert werden

#### Strategy Pattern

-   **Zweck:** Definiert einen Familie von Algorithmen, die einzeln als
    Klasse gekapselt und austauschbar sind. Somit kann zur Laufzeit der
    gewünschte Algorithmus ausgeführt werden.

-   ![](.//media/image15.png){width="4.991666666666666in"
    height="2.334722222222222in"}**Anwendungsfälle:** Dokumente/
    Grafiken in verschiednen Formaten speichern, Sortierung von
    Collections

-   UML:

-   Vorteile:

    -   Erweiterbarkeit

    -   Algorithmen können zur Laufzeit gewechselt werden

    -   Algorithmen sind in eigenen Klassen gekapselt

-   Nachteil:

    -   Zusätzlicher Kommunikationsaufwand zwischen Strategie und
        Kontext

#### Template Method Pattern

-   **Zweck:** Sorgt dafür, dass Teilschritte eines Algorithmus variabel
    gehalten werden kann.

-   ![](.//media/image16.png){width="4.0368055555555555in"
    height="2.261111111111111in"}**Anwendungsfälle:** Planungsprogramme

-   UML:

-   Strategy Pattern vs. Template Method Pattern:

    -   Strategy Pattern: Gesamten Algorithmus austauschen

    -   Template Method Pattern: Teile des Algorithmus tauschen

-   Vorteile:

    -   Keine Redundanz

    -   Flexibilität

-   Nachteil:

    -   Das verstehen der genauen Ablaufreihenfolde kann manchmal
        verwirrend sein, da in ConcreteClass genauer Ablauf steht

#### State Pattern

-   **Zweck:** Kann das Verhalten eines Objekts zur Laufzeit ändern,
    wenn sich der interne Zustand des Objekts geändert hat. Es wird dann
    so aussehen, als ob das Objekt seine Klasse gewechselt hat.

    -   **Vorraussetzungen:**

        -   Objekt muss Zustände annehmen können, die sich **deutlich**
            voneinander unterscheiden

        -   Objekt kann immer nur **genau einen Zustand** haben

-   ![](.//media/image17.png){width="4.9847222222222225in"
    height="2.3243055555555556in"}UML:

-   Vorteile:

    -   Erweiterbarkeit

    -   Übersichtlichkeit

-   Nachteile:

    -   Bei einfachen Zuständen zu großer Implementierungsaufwand

C\#
===

Threads
-------

-   Threads ermöglichen das parallele Ausführen von Code führt zu
    besserer Performance

-   Threads werden dadurch unabhängig voneinander ausgeführt

-   In Threads werden Aufagben ausgelagert, die viel Performance
    brauchen führt zu einem weiteren flüssigen Verlauf

Interfaces
----------

-   Unterschied explizites und implizites Interface:

    -   Explizit: implementierte Methoden sind private

    -   Implizit : implementierte Methoden sind public

-   Hat eine Klasse zwei unterschiedliche Zugriffe von außen, sollten
    zwei unterschiedliche Interfaces implementiert werden (**Implizit
    ist der saubere Weg**)

### Explicit Interfaces

-   Nutzung: am besten vermeiden, da es **oft** gegen [Interface
    Segregation Principle](#interface-segregation-principle) verstößt

### Implicit Interfaces

-   „Normale" Nutzung von Interfaces

-   Reicht meistens aus

Testing
-------

### Unit Tests

-   Testet eine bestimmten Code-Teil, Klasse oder mehrere Klassen ohne
    die externen Abhängigkeiten (Datenbanken etc.)

-   Schnell und einfach zu schreiben, liefern schnelle Ergebnisse

### Integration Tests

-   Testet einen Code-Teil, Klasse oder mehrere Klassen mit den externen
    Abhängigkeiten

-   Dauern etwas länger, sollten nur für die Teile des Codes benutzt
    werden, wo die Unit Tests nicht mehr ausreichen

### End-To-End Tests

-   User-Interface Tests für mich eher unwichtig

[]{#_Toc36800196 .anchor}

Mathmatics
==========

Bayesche Netze
--------------

### Gibbs Sampling

-   Gibbs Sampling ist eine Methode zur Annäherung an die reale
    Wahrscheinlichkeit

![](.//media/image18.PNG){width="4.79375in"
height="3.7729166666666667in"}Wie funktioniert Gibbs Sampling? -- Ein
Beispiel mit Topic Model

-   Jedes Topic ist in den Kästen zu sehen.

-   Jeder kreis auf den Wörtern die Zuordnung zu den Topics

-   ![](.//media/image19.PNG){width="1.6645833333333333in"
    height="0.3923611111111111in"}Man startet mit der Änderung einer
    Topic Zuordnung eines einzelnen Wortes

-   ![](.//media/image20.PNG){width="4.132638888888889in"
    height="2.2180555555555554in"}Dann werden alle Topics und alle
    Wörter in die Berechnung mit einbezogen, um zu errechnen, welchem
    Topic das Wort „record" am wahrscheinlichsten angehört

-   ![](.//media/image21.PNG){width="4.223611111111111in"
    height="2.870138888888889in"}Formel:

-   ![](.//media/image22.PNG){width="4.5443438320209975in"
    height="3.3065715223097114in"}Man beginnt jetzt ein Wort zu samplen
    ( anderes Beispiel als oben)

-   Trade war dem Topic 2 zugeordnet. Jetzt wird diese Zuordnung
    entfernt, und die Daten in der Tabelle aktualisiert. D.h. die „2"
    bei trade wird zu ?, und der Count bei „trade" -- Topic 2 wird zu
    „7"

-   ![](.//media/image23.PNG){width="4.020833333333333in"
    height="1.6520833333333333in"}Im nächsten Schritt, schaut man sich
    an, wie sehr das Dokument das jeweilig Topic „mag" (repräsentiert
    als blaue Streifen)

-   ![](.//media/image24.PNG){width="3.427561242344707in"
    height="1.0001399825021873in"}Wird in der Formel bei den rot
    markiertern Variablen repräsentiert

-   ![](.//media/image25.PNG){width="4.123611111111111in"
    height="1.3604166666666666in"}![](.//media/image26.PNG){width="2.560416666666667in"
    height="0.6305555555555555in"}Nun schaut man sich noch den hinteren
    Teil der Gleichung an. Hierfür wird die absolute Anzahl des Wortes
    benutzt, welches dem jeweiligen Topic zugeordnet wird. Daraus ergibt
    sich dann eine Fläche. Diese repräsentiert die Wahrscheinlichkeit
    der Zuordnung zu diesem Thema.

-   ![](.//media/image27.PNG){width="4.955555555555556in"
    height="3.282638888888889in"}Nun wird zufällig zwischen diesen drei
    Flächen ausgewählt, wobei Topic 1 die größte Fläche hat. Angenommmen
    man trifft diese. Danach werden die Daten aktualisiert. „trade" wird
    dem Topic 1 zugeordnet und der Count steigt von 10 auf 11.

-   Topic Selection mittels Gibbs-Sampling:
![](.//media/image28.PNG)

Unity
=====

Unity Shortcuts
---------------

//TODO: Table
-   Select MainCamera Strg + Shift + F Align Camera with Scene View

-   Y Toggle Pivot Mode

-   X Toggle Local/World-Space

-   Strg + Shift + P Pause

-   Strg + Shift + N Create Empty GameObjcet

-   Alt + Shift + N Create Empty GameObject als Child des ausgewählten

-   Strg + Z Undo

-   Strg + Y Redo

-   Hovering Window + Shift + Space Maximize or Minimize Window

Style Guide
-----------

### Welche Klassen/Scripte machen Sinn?

-   Controller führen mehrere kleinere Scripte zusammen
-   Bsp.: AppController: genreller Start der Anwendung, Initalisieren,
    Laden der Szenen

### Welche Szenen machen Sinn?

-   Boot Szene für Start
-   Nachladen der ersten Szene (meist additiv)
-   Bei unterschiedlichem Content einzelne Content Szenen

### Controller

-   Auf das Minimum reduzieren
-   Controller arbeiten Script übergreifend
-   Führen Scripte zusammen
-   Side-Referenzen möglichst nur zum nächst höheren Controller oder zu
    anderen Controllern

### Refactoring

### Reusability

-   Code mit so wenig Side-Referenzen wie möglich
-   Optimalfall: in sich abgeschlossen mit allgemein gültigen Variablen
    Namen
-   Schlecht: DistanceCameraToWorld Besser: DistanceCameraToTarget

Delegaten/Lambda Expressions
----------------------------

### Delegaten

-   Datentyp, in den man Methodenreferenzen speichern kann
    (Methodenzeiger)
-   Referenz zu einer (oder mehreren) Methoden Ausführung mit variablen
    Aufruf
-   Deklaration:
    - public delegate int Rechenoperation (int x, int y)

-   public delegate Rückgabewert Methodenname (Parameterliste)
-   In Delegaten können nur Funktionen geschrieben werden, die mit
    beidem übereinstimmen
-   Bsp.:

> Rechenoperation op = new Rechenoperation(Addition);
>
> Debug.Log(op(10,5));
>
> private int Addition(int x, int y)
>
> {
>
> return x + y;
>
> }

-   In op werden alle Operationen ausgeführt, die wir dem Delegaten
    übergeben haben

### Lambda Expressions

-   Werden benutzt, um einfache Methoden mit return-Statement auf eine
    Zeile zu reduzieren
-   „=\>" Lambda Operator
-   Bsp.:

> delegate int ScoreDelegate(PlayerStats stats);
>
> ScoreDelegate scoreCalculator = stats =\> stats.kills;

-   Lambda-Anweisung entspricht:

> int ScoreByKillcount(PlayerStats stats)
>
> {
>
> return stats.kills;
>
> }

### Events

-   Actions sind Delegaten mit void als Return Typ (Action\<T\> ,
    delegate with void return type, custom parameters)
-   Func sind Delgaten mit custom ReturnTyp und keinem oder Custom
    Parametern (Func\<T\>, delegate with custom return type, no paramter
    / Func\<T1,T2\>, delegate with custom return type, custom parameters
    last parameter = return type)

Performance
-----------

### Allgemein

-   Update-Methode nicht überladen
-   For \> foreach
-   Direkte Referenz \> GetComponent \> Find...
-   Array \> List List aber dynamisch

### Math-Functions

-   Potenzen besser als Wurzeln
    - Vector3.SqrMagnitude(Position1 - Position2) \> 5² Besser als Distance
-   Multiplikation besser als Division

### Object-Pooling

-   Performance sparende Variante von Instantiate ist sog.
    „Objekt-Pooling"
-   Empty Gameobject „ObjectPool" erstellen
-   Child Emptys mit jeweiligen Pool Namen
-   Creat Script zum halten der Objekte
    -   Objekte sind von Anfang in der Szene, werden bei Bedarf Aktiv gesetzt und platziert
-   Wenn letztes Objekt benutzt worden ist, erstes Objekt
    wiederverwenden
-   Spart enorm viel Rechenleistung und müllt RAM nicht zu
-   [Tutorial](#_Object_Pooling)

Special Folders
---------------

### StreamingAssets

-   StreamingAssets ist für alle Daten reserviert, die während der
    Laufzeit geladen werden sollen
-   Kein Zugriff im Editor

### Scripts/Editor

-   Skripte die im Buiild ignoriert werden

### Resources

-   Assets, die während der Runtime geladen werden können

### Plugins

-   Third Party Plugins verwenden Ordner für Zugriff auf deren Libs

Deklarationen
-------------

### Static

-   Definiert eine Instanz einmalig
-   Zugriff von allen anderen Instanzen möglich
-   Übergehen von visueller Referenzierung durch Singelton Pattern

public static Controller Instance;

void Awake()

{

if (Instance != null)

{

Destroy(this.gameObject);

}

Instance = this;

}

-   Objekt der Klasse sollte nur einmal in Szene vorhanden sein

### Enum

-   Aufzählung von Konstanten z.B. Zustände oder Mode's

> public enum CameraState { TooClose = 0, IsOrbiting = 1, IsFollowing =
> 2, TooFar = 3 }

Events
------

### Allgemein

-   Events feuern, sobald etwas passiert ist siehe Aufruf

### Deklaration

> public Action OnHotspotTapped;

### Aufruf

-   Bei Aufruf if Abfrage, ob Event != null Abfangen von null-ref

> void OnMouseDown()
>
> {
>
> If (OnHotspotTapped != null)
>
> {
>
> OnHotspotTapped(); wird abgefeuert
>
> }
>
> }

### Registrierung des Handlers

-   Handler muss reigstriert sein Ziel des abfeuerns

-   Auf ein Event können mehrere Eventhandler registriert werden

> hotspotView.OnHotspotTapped += OnHotspotTappedHandler;

-   Aufruf der Handler Methode

> private void OnHotspotTappedHandler()
>
> {
>
> DoSmth();
>
> }

### Registrierung eines Handlers auf mehreren Objekte

-   Controller handelt jedes Event mit dem gleichen Methoden Aufruf

> private List\<HotspotView\> hotspotViews;
>
> for (int i = 0; i \< hotspotViews.Count; i++)
>
> {
>
> hotspotViews\[i\].OnHotspotTapped += OnHotspotTappedHandler;
>
> }

1.  

    1.  
    2.  
    3.  
    4.  

Mathfunctions
-------------

### Allgemein

-   Clamp (zu beschränkender Wert, Min, Max)

> rotX = Mathf.Clamp(rotX, RotationLockMin, RotationLockMax);

### Winkel

-   Deg2Rad
-   Rad2Deg
-   Negative Winkel berechnen

> rotX = (rotX \> 180) ? rotX - 360 : rotX;

-   LerpAngle für Winkel Rotationen

### Distanzen

-   Vector3.Distance Wurzelberechnung wenig performant
-   Vector3.SqrMagnitude Quadrat Entfernung performanter

If (Vector3.SqrMagnitude(Position1 - Position2) \> 5²)

MonoBehaviour
-------------

### Flowchart

![](.//media/image29.png)

1.  

    1.  
    2.  
    3.  
    4.  

### Mouse Input

-   Methoden: OnMouseOver, OnMouseEnter, OnMouseDown, OnMouseDrag,
    OnMouseUp, OnMouseExit
-   Input lesen - Bsp.: Input. GetAxis(„Mouse X"), Input.GetAxis(„Mouse
    Y")

Visual
======

Rotationen
----------

### Quaternion vs. Euler

-   Quaterninon ist Winkelangabe im Raum der komplexen Zahlen Vorteil:
    kein Gimbal lock
-   Euler hat bei Bewegungen von zwei Achsen Problem von Gimbal Lock
    Mögliche Lösung über zwei Objekte

### Space

-   Rotationen lassen sich mit der Welt als Bezug oder mit Bezug zum
    Parent Objekt ausführen Rotate ( Rotationsachse, Winkel, Space)
-   EulerAngles haben Bezug zur Welt Editor hat Angabe
-   localEulerAngles haben Bezug auf Parent

### Mathfunctions

-   Für Rotationen mit Lerp Mathf.LerpAngle benutzen jede Achse einzeln

### LookAt

-   Für Rotationen mit LookAt beachten, dass diese bei einer Drehung \>
    180 Grad oft Probleme mit Gimbal Lock bekommen
-   Alternative zu LookAt

> transform.rotation = Quaternion.LookRotation(transform.position -
> Camera.main.transform.position);

### Rotationen Damping

-   In Update Faktor, um den gedreht wird mit Wert \< 1 multiplizieren

> axisY \*= RotationDampingFactorVertical;

Animationen
-----------

### Anlegen von Animations Clips

-   Auf GameObject klicken
-   Strg + 6 öffnet Aninmations Fenster
-   Klick „Create" erstellt Animations Clip und Controller für das
    jeweilige Objekt
-   Falls Clip offen oben links in Fenster auf den aktuellen Clipnamen
    klicken Dropdown „Create New Clip"

### Bearbeiten von Animations Clips

-   Clip in Ordner Struktur finden
-   Strg + 6 öffnet Aninmations Fenster
-   Clip anklicken ändern

### Anlegen von Propertys in Clips

-   Klick „Add Property" Auswählen von zu animierendem Wert
-   Z.B.: Transform Scale
-   In Properties können auch CildrenObjecte Hinzugefügt werden

### Erstellen von Keyframes

-   Rechtklick auf Zeit "Add Keyframe"
-   Verschieben durch ziehen der Keyframes
-   Oder Preview Mode s. 1.8.5.

### Bearbeiten von Keyframes (Preview-Mode)

-   Preview Mode aktivieren: oben links im Animations Fenster auf
    Preview klicken
-   Zeitmarker verschieben Werte beim GameObject eingeben (sollten nun
    rot hinterlegt sein)
-   Rechtklick auf Werte Add/Update Keyframes

### Animator Probleme

-   Animator blockiert Scripte, die auf Transform oder ähnliches
    zugreifen wollen
    -   Animator während Runtime ausschalten

Materials
---------

### Material Charts 

-   Link : [Material
    Charts](https://docs.unity3d.com/Manual/StandardShaderMaterialCharts.html)

Texturen
--------

### Import

-   Nicht vergessen Settings zu setzen

### Rendertexturen

-   Sind Texturen, die einen Camera Input live umsetzen können und
    anschließend als normale Textur eingesetzt werden können
-   [Tutorial](#tutorials)

Level of Detail -- LOD
----------------------

### Naming

-   Wenn das Model erstellt wird, ist folgendes Naming für Unity
    wichtig:
    -   Modelname\_LOD0 für detailreichstes Model
    -   Modelname\_LOD1 für weniger Details
    -   Etc.

-   Modelle liegen unter Parent Object wenn die Gruppe nach Unity
    exportiert wird, erkennt Unity dies automatisch und erstellt eine
    LOD Group

Datenverarbeitung
=================

XML
---

### Aufbau XML

-   XML wie HTML angelegt

-   Textdokument für Daten → Datentypen werden selber definiert

> \<?xml version=\"1.0\" encoding=\"utf-8\"?\>
>
>     \<root\>
>
>         \<projects\>
>
>             \<project\>
>
>                 .
>
>                 .
>
>                 .
>
>             \</project\>
>
>         \</projects\>
>
> \</root\>

### Datenklasse in Unity anlegen

-   Unity Scripts Data Ordner erstellen

-   Oberste Klasse anlegen: ProjectsData

-   Namespace für Datenklasse:

> using System.Collections.Generic;
>
> using System.Xml.Serialization;
>
> using System;

-   Code für oberste Datenklasse:

> \[Serializable\]
>
> \[XmlRoot(\"root\")\]
>
> public class ProjectsData
>
> {
>
> \[XmlArray(\"projects\")\]
>
> \[XmlArrayItem(\"project\")\]
>
> public List\<ProjectData\> Projects;
>
> }

-   XmlArrayItem als Klasse Anlegen

> \[Serializable\]
>
> public class ProjectData
>
> {
>
> \[XmlElement(\"id\")\]
>
> public string Id;
>
> \[XmlElement(\"name\")\]
>
> public string Name;
>
> public string Image;
>
> public string customer;
>
> \[XmlArray(\"challenges\")\]
>
> \[XmlArrayItem(\"challenge\")\]
>
> public List\<ChallengeData\> challenges;
>
> \[XmlArray(\"customerValues\")\]
>
> \[XmlArrayItem(\"customerValue\")\]
>
> public List\<CustomerValueData\> customerValues;
>
> }

-   Alle weiteren XmlArrayItems als einzelne Klassen anlegen

### Einlesen XML in Unity

-   Unity Scripts Ordner Controller anelgen

-   Klasse AppController anlegen

> void Start ()
>
> {
>
> string xmlName;
>
> // XML Datei Aus StreamingAssets Ordner (Pfad gültig für alle
> Plattformen)
>
> xmlName = Application.streamingAssetsPath + \"/content.xml\";
>
> // Asset Loader lädt File
>
> AssetLoader xmlLoader = new AssetLoader(\"file:///\" + xmlName,
> xmlName);
>
> // Funktion zum Check für Abschluss
>
> xmlLoader.OnComplete = OnXmlLoadingCompletedHandler;
>
> // Asynchrones Laden des Assets
>
> LoadingManager.Instance.LoadAssetAsync(xmlLoader);
>
> }
>
> private void OnXmlLoadingCompletedHandler(Loader loader)
>
> {
>
> AssetLoader xmlLoader = loader as AssetLoader;
>
> DeserializeContentXml(xmlLoader.Request.bytes);
>
> }
>
> // Funktion zum Auslesen der XML und Einpflegen
>
> public void DeserializeContentXml(byte\[\] byteArray)
>
> {
>
> XmlSerializer serializer = new XmlSerializer(typeof(ProjectsData));
>
> MemoryStream memoryStream = new MemoryStream(byteArray);
>
> // Daten in selbst definierte Klasse einpflegen s.o.
>
> data = (ProjectsData)serializer.Deserialize(memoryStream);
>
> Debug.Log(data.Projects.Count);
>
> }

AI
==

NavMesh
-------

### Setup 

-   Empty GameObject erstellen
-   Nav Mesh Surface hinzufügen
-   AgentType: Agent auswählen, neuen Agent erstellen
-   Include Layer: Layer deaktivieren, die nicht in NavMesh Bake sein
    sollen
-   Use Geometry : Render Meshes oder Physics Colliders

### Setup Area

-   Um bestimmte Meshes aus dem NavMesh zu nehmen oder einen anderen
    Area Type zu geben Add Component NavMeshModifier
-   Override Area Area Type ändern

### NavMeshAgent

-   Angular Speed : Geschwindigkeit der Rotation zum neuen Ziel
-   Acceleration: Geschwindigekit für Start der Bewegung und
    Bewegunsänderungen
-   Stopping Distance: Distanz von Ziel bis Agent stoppt

### Obstacles

-   Add Component NavMeshObstacle
-   Carve unchecked: Route wird nicht um Object herum berechnet Agent
    versucht hindurch zu laufen
-   Carve checked: Route von Agent wird um Object herum berechnet
-   Carve Only Stationary checked: Berechnet kein neues NavMesh, sobald
    sich Obstacle bewegt

### NavMesh Link

-   Verlinkt NavMeshes miteinander Link = Teleport
-   Width: Breite des Links

Builds
======

Third PartyPlugins
==================

I2 Localization
---------------

### Setup

-   Resources/I2Languages für Setup
-   Move to Spreadsheets Google
-   Web Service URL Install
-   Script Umbennen
-   Veröffentlichen Als Web-App einrichten
-   Instruktionen folgen für einrichten

### Sprachen einstellen

-   Languages Liste ausklappen Sprache wählen Add

### Übersetzungen definieren

-   Google Spreadsheets eintragen

### Update

-   Spreadsheets Import Replace/Merge
-   Auto Update Frequency for Build or Editor

Visual Studio
=============

Shortcuts Text
--------------

|Was macht der Shortcut?                    |Windows                                   |Mac                                     |
|-------------------------------------------|----------------------------------------- |----------------------------------------|
|  Zur Referenz springen                    |F12                                       |Fn + F12                                |    
|  Zum nächsten Wort springen               |Strg + → / Strg + ←                       |alt + → / alt + ←                       |
|  Zum Anfang/ Ende der Zeile springen      |Home / End                                |Fn + / Fn +                             |
|  Runter-/Hochscrollen                     |Page Down/ Page Up                        |Fn + ↑ / Fn + ↓                         |
|  Zum Anfang / Ende der Datei springen     |Strg + Home / Strg + End                  |Fn + alt + ↑ / Fn + alt + ↓             |
|  Duplizieren                              |Strg + D                                  |Cmd + D                                 |
|  Löschen eines Wortes                     |Strg + Backspace / Strg+ Entf             |Alt + Backspace / fn + alt + Backspace  |
|  Ganze Zeile löschen                      |Strg + L / Strg + X                       |Ctrl + Backspace                        |
|  Dokument formatieren                     |Strg + K, Strg + D / Strk + K, Strg + F   |                                        |
|  Auskommentieren                          |Strg + K, Strg + C                        |                                        |
|  Auskommentieren aufheben                 |Strg + K , Strg + U                       |                                        |
|  Umschließen mit ...                      |Strg + K, Strg + S                        |                                        |
|  Variable in allen Projektdateien umbennen|Strg + R, Strg + R                        |                                        |
|  Bookmark toggle                          |Strg + K, Strg + K                        |                                        |
|  Bookmark Window                          |Strg + W, B                               |                                        |
|  Bereich klappen toggle                   |Strg + M, Strg + M                        |Shift + alt + Cmd +  ←                  |

|  Was macht der Shortcut?                  | Windows            |Mac   |
|  -----------------------------------------| ------------------ |------|
|  Finden-Dialog anzeigen                   | Strg + F           |      |
|  Finden in Dateien -- Dialog anzeigen     | Shift + Strg + F   |      |
|  Nächstes/ vorheriges Ergebnis der Suche  | F3 / Shift + F3    |      |
|  Ersetzen- Dialog                         | Strg + H           |      |
|  Ergebnis ersetzen                        | Alt + R            |      |
|  Alles ersetzen                           | Alt + A            |      |
|

Navigation & Windows
--------------------

|  Was macht der Shortcut?           | Windows              | Mac                 |  
|  ----------------------------------| ---------------------| --------------------|
|  Switch durch offene Tabs          | Strg + Tab           | Ctrl + Tab          |  
|  Reverse Switch durch offene Tabs  | Shift + Strg + Tab   | Shift + Ctrl + Tab  |
|  Nächster Tab                      | Strg + F6            | Cmd + alt + 9       |  
|  Vorheriger Tab                    | Strg + Shift + F6    | Cmd + alt + 8       |  
|  Tab schließen                     | Strg + F4            |                     |  
|  Alle offenen Tabs schließen       | Alt + L + W          |                     |  
|  Navigator Suche                   | Strg + ,             |                     |   
|  Fullscreen Editor                 | Shift + alt + Enter  |                     |  

Running, Debugging & Compiling
------------------------------

|  Was macht der Shortcut?                            | Windows           | Mac     |
|  ---------------------------------------------------| ------------------| -----   |
|  Run Application                                    | Strg + F5         |         |
|  Run Debug Mode                                     | F5                |         |
|  Stop Debug                                         | Shift + F5        |         |
|  Breakpoint toggle                                  | F9                |         |
|  Step over Method                                   | F10               |         |
|  Step into Method                                   | F11               |         |
|  Step out of Method                                 | Shift + F11       |         |
|  Compile Application                                | Strg + Shift + B  |         |
|  Zum nächsten Error springen (bei Compile Fehlern)  | F8                |         |

Code Snippets
-------------

|  Was macht der Shortcut?            |            | 
|  -----------------------------------| -----------|
|  Klasse erstellen                   | class      | 
|  Konstruktor erstellen              | ctor       | 
|  Property erstellen                 | prop       | 
|  Property mit private field         | propfull   | 
|  Equals Methode                     | equals     | 
|  For-Loop                           | for        | 
|  For-Loop mit Dekrementer Variable  | forr       | 
|  Foreach- Loop                      | foreach    | 
|  While-Loop                         | while      | 
|  Do-Loop                            | do         | 
|  Try-/Catch -- Block                | try        | 
|  Try-/Finally-Block                 | tryf       | 
|  Interface                          | interface  |
|  Console Write Line                 | cw         | 

Extensions
----------

-   Productivity Power Tools

Tipps und Tricks
================

View und Engine
---------------

-   View und Engine so viel wie möglich trennen
-   Klassen
-   lookAt vermeiden Besser : eulerAngles = Vector3.up\*180
-   Sqr Distance besser als Distance

Anhang
======

Tutorials
---------

-   [Object Pooling](https://www.youtube.com/watch?v=tdSmKaJvCoA)

-   [Rendertexture -
    MiniMap](https://www.youtube.com/watch?v=28JTTXqMvOU)
