- ähnlich wie [[Funktionales Design]], jedoch hat das System einen State

## Call-Based Architekturstil
- Komponenten bezeichnen Prozeduren die sich gegenseitig aufrufen
- Kontrollfluss symmetrisch
- Datenfluss kann parallel (push-basiertes System) oder antiparallel (pull-based Sys.) sein
-> Pascal, Delphi, ...
## Datenfluss-Basierter Architekturstil
"Pipe-and-Filter"
- Komponenten: Prozesse, Konnektoren: Streams
-> Linux Pipes; Bildverarbeitungssysteme; DSP; CMS; PowerShell (typisierte Flows, XML)

## Event-Condition-Aktionsorientiertes Design
- ECA-Regeln
- Teile (finde Regeln für Kontexte) und Herrsche (gruppiere Regeln um Module zu beherrs.)
- Verwenden, wenn System in einem State-Raum arbeitet, wo Aktionen Transitionen darstellen und Aktionen von Events ausgelöst werden

### Event-basierter Architekturstil
- Komponenten: Prozesse/Prozeduren
- Konnektoren: anonyme Kommunikation durch Events
	- dynamische Topologie: Listener können sich dynamisch an-/abmelden
	- Listener werden implizit durch Events aufgerufen
-> Android Intents, JBoss Rules

## Workflow-Basierte Systeme
-> YAWL
