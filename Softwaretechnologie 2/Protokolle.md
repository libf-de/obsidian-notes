Softwaremanagement & Softwaretechnologie 2
WS 2011/2012
Prof. Aßmann, Dr. Speck

* Datenflussdiagramme
* Petri Netze
* V-Modell XT
** V-Modell XT hat Probleme mit der Synchronisation, da es ein Datenflussdiagramm ist.
* Qualitätssicherung
** (insb. Testen)

---

Softwaretechnologie 2
-
Dr. Santen, Prof. Wünschmann

Stellen Sie sich vor, Sie haben eine zentrale Buchungsstelle und viele kleine Reisebüros, die über diese buchen. Sie sollen das Projekt planen, wie packen Sie das an?<
Wie kann man Anforderungen ermitteln / darstellen? Was hat man alles als ergebnis der Analysephase?
Analysemuster wählen und erklären.
Welche Muster gibt es noch? (Arch.- und Entw.-muster) Nennen Sie je ein Beispiel. Erklären sie >Visitor<. Was wird da gekapselt?
Wie erfolgt die Abbildung von ODBS auf RDBS?

---

Softwaretechnologie 2
-
Dr. Santen

Prozessmodelle nennen und erläutern
Analysemuster nennen, eines erläutern
Architekturmuster nennen, eins erläutern
ein Entwurfsmuster erläutern
CORBA erläutern

---
Softwaretechnologie 2
-
Dr. Santen

Übersicht über den Softwareentwicklungprozess (Phasenmodell, Testen).
Entwurfmuster "Visitor".
CORBA (Aufbau, Verfahren).

---
Softwaretechnologie 2
-
Dr. Santen

Phasenmodelle, unter anderem V-Modell
zu vorgegebenen Klassendiagrammen Muster erkennen (Z.B. Rolle)
Template Method: ob man dieses Muster eher zu Klassenbibliothek, Framework oder Komponenten zuordnen würde
CORBA (IDL, Stubs, Skeletons, ...)
4+1 Sichten erläutern; Unterschied zwischen Analysemodell und Entwurfsmodell

---
Softwaretechnologie 2
-
Prof. Aßmann

Strukturierte Analyse (Datenfluss, ...)
OOA (Use Case)
Entwurfsmuster (Mediator)

---
Softwaretechnologie 2
-
Prof. Aßmann, Dr. Demuth

Requirements-Analysis
V-Modell
Design-Pattern (Template Method)
SA/SD

---
Softwaretechnologie 2
-
Prof. Aßmann, Prof. Liskowsky

Umwandlung Funktionsbäume in Use-Case
Regressionstest
Stakeholder
Problem-Goal-Funktion
Domainanalyse
JUnit
SA Analyse Umwandlung
Akzeptanztest

---
Modul: INF-B-510
Semester: WS 2019
Prüfer: Dr. Sebastian Götz

Lehrveranstaltung: Softwaretechnologie
Prüfer: Dr. Sebastian Götz
Prüfung war sehr angenehm, auch wenn die Hilfestellung nicht sonderlich hilfreich war. Bewertung exakt wie in der Vorlesung beschrieben. Aufgaben 1 & 2 haben den Großteil der Zeit eingenommen.
Fragen:
1. "Toy Box" - eine Box auf die man eine Figur stellt und anschließend Musik zu dieser abspielt
 - Petri Netz mit 2 States modellieren, Lebendigkeit angeben, Skalierung auf L4 lebendigkeit
- wie passt man das auf den Fall an, dass mehr als eine Figur draufgestellt wird ( es soll nur die Figur der ersten Figur abgespielt werden) 
- was ist eine Incidence matrix?
2. Weiter die Toy Box, wie würde man diese Programmieren?
 - ECA für Abspielen, Musikdownload als Stream mit Pipe&Filter, oder Pipe&Filter in ein Repository gespeichert.
3. Programmsicherheit
 - verifikation, validation, was ist defensive Programming
4. GL Isomorphismus
 - Was ist das? Wie würde man in einer größeren Firma anfangen ( Stichwort Generationen, Transitivität etc)
  ---
Modul: INF-BAS3
Semester: SS 2015
Prüfer: Prof. Aßmann

Lehrveranstaltung: Softwaretechnologie
Prüfer: Prof. Aßmann
Alles bezog sich auf eine Industrie 4.0 Anlage.
- Petrinetze: Aufbau, logische Operationen
- Verfeinerung dieser
- reduzible Graphen
- Vorteile/Nachteile dieser
 
---
Modul: INF-BAS3
Semester: WS 2015
Prüfer: Prof Aßmann

Lehrveranstaltung: Softwaretechnologie
Prüfer: Aßmann
Anfangs ein Beispiel von einem Roboterarm der mit einem Handschuh gesteuert wird.

Wie würde man den parallelen Roboter modellieren? -> Petri Netze.
Was kann mit Petri Netzen gezeigt werden? -> Lebendigkeit, Deadlocks, Fairness
Wie lassen sich Petri Netze verfeinern -> Colored PNs die um Seiten erweitert werden können.
Was muss beim Verfeinern beachtet werden? -> Das Interface(Eingänge, Ausgänge) der Seite muss passen, damit sie eingefügt werden kann.
Wo erweitert man Petri Netze? -> An offenen Operatoren, z.B. AND, Or, Xor merge
Wie können Petri Netze komponiert werden? -> Beispiel mit dem Krankenhaus aus der Vorlesung. Transitionen und Plätze haben gleiche Namen, diese bilden ein logisches Objekt.
Wie würde man die Eingaben des Handschuhes an den Roboter weitergeben -> Die Ausgänge des Hanschuh Netzes mit den Eingängen des Roboter Netzes verbinden.
Welche Arten von reduziblen Graphen kennen sie? -> Petri Netze, Data Flow Diagram, State Charts
Was sind die Vorteile von reduziblen Graphen -> Einfacher zu verstehen.
Wie bereitet man ein System für die Akzeptanztests vor? -> Testen der Software mit Unit-Tests, Regression Tests
Wie gehen ein Diff bei XML, oder einem reduziblen Graphen? -> Beides sind Bäume und können daher einfach gedifft werden.
Was ist das Problem von JUnit? -> Die Daten stehen im Code, daher können sie nicht einfach ausgetauscht werden.

---
Modul: INF-B-510
Semester: WS 2018
Prüfer: Dr. Götz

Lehrveranstaltung: Softwaretechnologie
Prüfer: Dr. Götz
1. Petrinetze: 
Erklären Sie die Funktionsweise eines Petrinetzes anhand einer Ampelschaltung(nur Umschalten zwischen Rot und Grün)! 
Erläutere die Lebendigkeiten in dem Netz!
Wie kann man das Petrinetz verfeinern? - Subpages über Transition oder Platz

2. Validation:
Wie kann man Software validieren ? - defensives Programmieren, Testen, interne/externe Reviews, Audits, Paarprogrammierung, Modelchecking

3. Designmethoden:
Erklären Sie Designmethode und Architekturstil am Beispiel ( wie Twitch : Streamingportal für Computerspiele, mit Chatfunktion und Bezahlfunktion)! - Event-condition-action-based Design, Pipe und Filter

4. Graphen:
Wie kann man mit Graphen große Software darstellen ?
Reduziblen Graphen erläutern!
Wie kann man das Formular(Anmeldung zur Prüfung) als Graph darstellen und mit OCL spezifizieren? - Wurzelknoten für Blatt, Kindsknoten für Abschnitte, Inhalte der Boxen mit OCL überprüfen

---

Modul: INF-VERT3
Semester: WS 2018
Prüfer: Dr. Sebastian Götz

Lehrveranstaltung: Softwaretechnologie
Prüfer: Dr. Sebastian Götz
Freundliche Atmosphäre. Es wird einem geholfen, wenn man mal hängt.

INHALT:

1. Wie modelliert man eine "Ultimate Machine" (Maschine, die sich selbst wieder ausschaltet) mit einem Petrinetz?
	→ Zwei Stellen ("ein" & "aus"), die über Transitionen im Kreis verbunden werden.

1.1. Welche Lebendigkeit hat dieses Petrinetz?
	→ L3-Lebendig.
	
1.2. Wie müsste man es erweitern, damit es L4-Lebendig wird?
	→ Quelle einfügen, die Token hinzufügt (nur bei Bedarf!).
	→ Transition von beiden Stellen einfügen, die zu viele Token aus dem System nimmt.
	
1.3. Wie kann man das mathematisch beweisen?
	→ Inzidenzmatrix, die wieder zu M0 führt (wie genau, steht in den Folien).
	
2. Thema Validierung
	→ Analytisches Testen (Statische & dynamische Tests)
	→ Konstruktives Testen (Pair Programming, Reviews, Audits, …)
	→ Graph-Logik-Isomorphismen

3. Fallbeispiel Finnland: Patienten sollen in der Ferne mittels Sensorwesten Physiotherapie machen. Welche Designmethode & welchen Architekturstil würden Sie dafür verwenden? (Hier wäre glaube ich mehreres richtig gewesen)
	→ Event-Condition-Action-oriented Design
	→ Pipes-and-Filter-Architekturstil (Datenorientiert)
	
3.1. Was bedeutet Architektur?
	→ …
	
3.2. Aus was besteht ein Architekturstil?
	→ Komponenten (Filter), Konnektoren (Pipes), Constraints (z.B. Datentypen)