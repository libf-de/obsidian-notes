Beim Code schreiben muss Variabiltät berücksichtigt werden -> kann durch Sprachfunktionen oder Tools erreicht werden
## Language-based Variability

### Grundlegende Sprachfunktionen
#### Parameter
-> mittels globale Variablen/Methodenparameter + `if`-Statements
<span style="color: lime">(+)</span> bekannt, einfach zu verwenden, feingranular, können alle Sprachen
<span style="color: red">(-)</span> jeder bekommt ganze Codebase, Feature-Code verstreut, schwer zu Analysieren, funktioniert nicht für nicht-Code-Artefakte

#### Design Patterns
##### Observer
-> Features als Observer, die sich im Kern registrieren
<span style="color: red">(-)</span> benötigt Verwaltungscode zum hinzufügen/entfernen von Observern

##### Template Method
-> Features in separaten Unterklasssen implementieren
<span style="color: lime">(+)</span> Gut für alternative/optionale Features
<span style="color: red">(-)</span> Nicht geeignet um mehrere Features zu kombinieren
<span style="color: cyan">(~)</span> Grundlage für *white-box frameworks* (Vererbungs-basiert)

##### Strategy
-> wie [[#Template Method]], nur mittels Delegation
<span style="color: cyan">(+/-)</span> wie Template Method
<span style="color: lime">(+)</span> Kombinationen mehrerer Features unterstützt
<span style="color: cyan">(~)</span> Grundlage für *black-box frameworks* (Delegation-basiert)

##### Decorator
-> Features in Decorator-Objekte verpacken
<span style="color: lime">(+)</span> Features können zur Laufzeit hinzugefügt/entfernt werden

#### Frameworks
-> Features als Plugins des Frameworks implementieren
- *white-box framework*: plugins => Subclasses
- *black-box framework*: plugins => Objects mit Callback-Methoden
<span style="color: lime">(+)</span> Strukturierte Herangehensweise, gute Information Hiding
<span style="color: lime">(+)</span> nur Code des Produkts wird geliefert
<span style="color: red">(-)</span> Plugins frameworkspezifisch, Wiederverwendung woanders schwierig
<span style="color: red">(-)</span> hoher Erstaufwand (Framework entwickeln)
<span style="color: red">(-)</span> Weiterentwicklung schwierig
<span style="color: red">(-)</span> keine feingranulare Variabilität

#### Components & Services
-> Komponenten zur Wiederverwendung gemacht, mit expliziten Interfaces die zeigen was sie bereitstellen und verlangen
<span style="color: lime">(+)</span> Strukturiert, bekannt, gute Information hiding
<span style="color: lime">(+)</span> nur Code des Produkts wird geliefert
<span style="color: lime">(+)</span> bieten Wiederverwendbarkeit über die SPL hinaus
<span style="color: red">(-)</span> Glue-Code nötig
<span style="color: red">(-)</span> Weiterentwicklung schwierig
<span style="color: red">(-)</span> keine feingranulare Variabilität

### Erweiterte Sprachfunktionen
#### Feature-orientierte Programmierung
=> Features auf *Feature-Module/layers/class refinements* gemappt -> Menge an Klassen deren Objekte zusammenarbeiten um das Feature bereitzustellen
- z.B. Jak
- Produktableitung wird zur Feature-Modul-Composition
<span style="color: lime">(+)</span> Gute Sep. of Concerns, Feature-Tracability
<span style="color: red">(-)</span> Spracherweiterung nötig, keine Interfaces zwischen Feature-Modulen

#### Aspekt-orientierte Programmierung
#### Role-orientierte Programmierung
#### Delta-orientierte Programmierung


## Tool-driven Variability
### Version Control Systems (VCS)
- erlaubt Historie an Code-Revisions (*variability in time*)
- erlaubt mehrere Branches, z.B. Varianten (*variability in space*)
- für SPL: ein Branch für jedes Feature; zur Produktableitung Branches mergen
<span style="color: lime">(+)</span> Ausgewachsene Tools, bekannt
<span style="color: lime">(+)</span> Funktioniert für Code und nicht-Code-Artefakte
<span style="color: red">(-)</span> keine strukturierte Wiederverwendung (sondern Copy & Paste)
<span style="color: red">(-)</span> Mergen ist fehleranfällig

### Build-Systeme
- größere Softwareprodukte werden mit einem Build-System erstellt
- Beispiele: `shell scripts`, `make`, `ant`, `maven`, `gradle`, …
- *Idee*: *Featureauswahl* eines Produkts dem Buildscript als *Parameter* übergeben, dieses compiliert, linkt und verpackt die nötigen Quelldateien
<span style="color: lime">(+)</span> bekannt, etablierte Tools
<span style="color: lime">(+)</span> Funktioniert für Code und nicht-Code-Artefakte
<span style="color: red">(-)</span>  Variabilität nur auf Datei-Level
<span style="color: red">(-)</span> keine Modularität

### Präprozessoren
- verändern Quellcode vor Compilierung
- bekanntester: C's cpp
	- `#include` inlines files
	- `#define` erlaubt Definition von Variablen
	- `#ifdef`/`#ifndef` erlaubt bedingtes in-/exkludieren von Code basierend auf diesen Variablen
<span style="color: lime">(+)</span> aktueller (de-facto) Standard
<span style="color: lime">(+)</span> Statement-Level Variabiltät
<span style="color: red">(-)</span> schlechte Separation of Concerns
<span style="color: red">(-)</span> schlechte Modularität
<span style="color: red">(-)</span> fehleranfällig

