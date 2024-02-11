Ein Architektur enthält Konzept-Typen:
- Typen an Komponenten mit
- Typen von Verbindern
- Relation zwischen Kontroll-/Datenfluss bzw. Rahmenbedingungen

"Grobkörnige" Entwufsmuster (z.B. habe nur Prozeduren, Rahmenbed. typsicher, ...)
## Bestandteile
- Vokabular?
- Strukturmuster? (Wie sinnvoll zusammensetzbar)
- Berechnungsmodell? (z.B. nur ordinary differential equations)
- essentielle Invarianten? (Was gilt immer?)
- Beispiele?
- Vor/Nachteile?
---
- Strukturelle Teile: Komponenten, Schnittstellen
- Kontrollfluss
- Datenfluss
- Interaktion zwischen Kontroll-/Datenfluss
- Invarianten
- Analyse-Features (Was kann analysiert werden?)

## Call-Based Architectural Style
- Komponenten sind Prozeduren die sich gegenseitig aufrufen
- **Kontrollfluss** symmetrisch (alle können aufrufen und zurückgeben, keiner hat mehr Kontrolle über Kontrollfluss)
- **Datenfluss** entweder
	- parallel/push-basiert: Aufrufender schiebt Daten in Aufgerufenen
	- antiparallel/pull-basiert: Aufrufender zieht Daten aus Aufgerufenem
-> [[Objektorientierter Entwurf|Objektorientierte]] Frameworks

![[Pasted image 20240207113608.png]]

### Objektorientierter Call-Based Architekturstil
- **Kontrollfluss** symmetrisch und *nicht fixiert* (dynamische Architektur mittels Polymorphie)
- **Datenfluss** kann anti-/parallel sein
![[Pasted image 20240211145124.png]]


## Datenfluss-Basierter Architekturstil
"Pipe-and-Filter"
- wenn Daten in Streams fließen wird aus [[#Call-Based Architectural Style|Call-based Systemen]] ein Stream-basiertes System
- *Komponenten*: Prozesse, *Konnektoren*: Streams
- **Kontrollfluss** asynchron, fortlaufend
- **Datenfluss** kann anti-/parallel sein
-> Linux Pipes; Bildverarbeitungssysteme; DSP; CMS; PowerShell (typisierte Flows, XML)

![[Pasted image 20240211132445.png]]

## Event-basierter Architekturstil
- *Komponenten*: Prozesse oder Prozeduren (-> Listener)
- *Konnektoren*: anonyme Kommunikation über Events
	- asynchron, dynamische Topologie, 
![[Pasted image 20240211134504.png]]


## Workflow-basierte Systeme
Workflow beschreibt Aktionen auf bestimmte Events und Bedingungen (bestimmt durch Decision Analysis, beschrieben durch ECA-Regeln)

- Kontroll- und Datenflussgraph steuert das System
- dieser ersetzt Datenflussgraphen (Pipe&Filter-Systeme) bzw. Kontrollflussgraphen (Call-based)
- im Prinzip Datenflussgraph mit Kontrollflussanweisungen (`if`, `while`, ...)
![[Pasted image 20240211141659.png]]
**Verwendung** in Business- (SAP), Produktionsplanungssoftware

## Communicating State Machines
- Prozessmodellierung mittels State Machines, die auf Events reagieren, Aktionen ausführen und kommunizieren
- Model Checking kann zur Spezifikations-*Validierung* verwendet werden
- Sprachen wie Esterelle, Lotos

**Verwendung** in Telekommunikations- und Embedded-Software.

---
## Regular Batch-/ETL Processing
spezieller Stapelverarbeitungs-Stil, bei dem reguläre Domänen verarbeitet werden
- Datenform mittels Regex, reg. Grammatik, Statechart beschrieben
- oftmals [[Transaktionsorientiert]]

**Verwendung** in Bank-/Geschäftssoftware, z.B. Business Report Generation

## Repository-Systeme
- [[Datenorientierter Entwurf|datenorientierte Verarbeitung]]
- freie Koordinierung der Komponenten
- Kombination mit [[#Call-Based Architectural Style|Call-based]] möglich, oft auch State-Orientiert
![[Pasted image 20240211143922.png]]

## Blackboard-Stil
aktives [[#Repository-Systeme|Repository]] (z.B. benachrichtigt Komponenten bei Änderungen), koordiniert andere Komponenten (-> `event notification` oder Aufruf)
![[Pasted image 20240211144142.png]]
**Verwendung** in Expertensystemen

---
## Objektorientierte Prozesssysteme
[[Objektorientierter Entwurf|Objektorientierte Systeme]] können parallel sein
-> *Actors*
- parallel kommunizierende Prozesse, kommunizieren direkt miteinander
- Unstrukturierte Kommunikation
![[Pasted image 20240211145338.png]]

## Prozessbaum-Systeme
- Prozesse sind in Baumstruktur angeordnet, kommunizieren nur mit direkten Verwandten
![[Pasted image 20240211145432.png]]

---
## Aspektorientierter Architekturstil
- normalerweise haben Entwurfsmethoden einen Aspekt der Entwicklung im Fokus
- aspektorientierte Systeme spezifizieren unterschiedliche Aspekte eines Systems separat
	- Reintegration durch [[Generativer Entwurf|generative]] Aspekt-Weaver
![[Pasted image 20240211154431.png]]

## Layered Architektur
- genereller Ansatz um Komplexität großer Systeme zu reduzieren -> in Schichten zerleg.
- kann mit vielen Architekturstilen kombiniert werden
- **Konnektoren**: Prozeduraufrufe oder Streams
- **Ports**: Komponenten-Interfaces
- **Kontrollfluss** größtenteils synchron
- **Datenfluss** entlang der Schichten und call graphs, hauptsächlich singulär
- Daten- und Kontrollfluss isomorph

**Verwendung** in großen Systemen

Architekturstile oftmals Layer-spezifisch:
![[Pasted image 20240211155536.png]]



---
## Component-Oriented Design
-> Middleware
-> Egal auf welcher Maschine andere Komponenten laufen, deserialisieren, ...

## Transformational Design
## Generative Design
