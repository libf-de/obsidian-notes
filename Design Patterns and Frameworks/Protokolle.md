Modul: INF-BAS3
Semester: SS 2013
Prüfer: Prof. Aßmann

Lehrveranstaltung: Design_Patterns_and_Frameworks
Prüfer: Prof. Aßmann, Dr. Demuth
Role Model (Role Merging, Role Mapping, Role Composition/Decomposition, Was ist eine Rolle?)
Rollen als Composition System
Unterschied zwischen GenVoca und Role Object Pattern
Role Object Pattern (zwei Varianten: Welche beiden Pattern sind jeweils darin enthalten)s
Eclipse (plugin.xml, extensions.xml, Was sind ExtensionPoints, Wir wird ein Plugin geschrieben?)

Atmosphäre: Gut
Zeit: Eingehalten

---

Modul: INF-BAS3
Semester: WS 2015
Prüfer: Aßmann

Lehrveranstaltung: Design_Patterns_and_Frameworks
Prüfer: Aßmann
Es gab ein zentrales Beispiel anhand vom einem Roboter. Im Prinzip ging es darum wie man ihn modellieren kann. Also den Aufbau intern als Decorator, dann noch ein Mediator mit rein damit er sich unterhalten, dann das ganze als bureaucracy. Schließlich kamen noch andere Roboter hinzu, da musste man das bureaucracy dann auf zwei Ebenen erweitern. Dann kamen noch ein paar Fragen zum Unterschied zwischen GenVocca, Mixin Layer und Role Object Pattern dran. Die meisten Patterns sollte man am Beispiel auch aufmalen.

Aßmann hat geholfen wenn man nicht weiter wusste. Die Stimmung war recht entspannt.
Er erwartetet, dass man, nachdem er eine allgemeine Frage stellte, frei recht viel dazu erzählen kann, also auch Dinge die nicht impliziert gefragt wurden.

---

Modul: INF-BAS3
Semester: WS 2015
Prüfer: Prof Aßmann

Lehrveranstaltung: Design_Patterns_and_Frameworks
Prüfer: Aßmann

Anfangs ein Beispiel von einem Roboterarm der mit einem Handschuh gesteuert wird.

Mit welchem Design Pattern lassen sich der Handschuh und der Roboter modellieren? -> Observer
Der Roboter und der Handschuh sind komplexe Objekte, wie lassen sich diese modellieren? -> Role-object Pattern
Role-object Pattern zeichnen und erklären.
Wie können die beiden Role-objects (Roboter und Handschuh) mit einander kommunizieren? -> Mediator auf jeder Rollen Schicht einsetzen, der die Rollen mit einander verbindet.
Die verschiedenen Varianten des Role-object Pattern erklären -> Flat Role-object, Deep Role-object und mit einem Trader Core 
Wie wird beim Role-object Pattern die OS verhindert? -> Alle Aufrufe passieren über den Kern, daher sollte es nicht passieren.
Wie kann man das ganze mit Mixins realisieren? -> GenVoca Pattern 
GenVoca Pattern zeichnen und Unterschiede zum ROP erklären -> ROP kann Rollen dynamisch austauschen, GenVoca ist effizienter. Beim GenVoca Pattern werden ganze Ebenen ausgetauscht.

---

Modul: INF-B-110
Semester: WS 2018
Prüfer: Demuth

Lehrveranstaltung: Design_Patterns_and_Frameworks
Prüfer: Götz
Bei der Prüfung geht es NICHT darum, wie in den Übungen die Design Pattern praktisch auf Szenarien anzuwenden, sondern um die Beziehungen zwischen den Pattern untereinander. Wissen über Rollen und Frameworks ist ebenfalls notwendig, obwohl in der Übung eher weniger stark thematisiert:
1. Einfaches Variability Pattern nennen: z.B. Template Method
2. Dieses Pattern erklären (Bei UML-Skizze ist Struktur nicht aber Namen wichtig)
3. Verwandtes Pattern (nächst Komplexeres) sowie Gemeinsamkeiten und Unterschiede zu Template Method: z.B. Strategy oder Template Class
4. Strategy Pattern erklären
5. Rollen Modell von Strategy
6. Role Constraints aufzählen und erklären
7. Template und Hook bei Role Object Pattern
8. Mini-Connector, den ROP in Framework Darstellt: Expansion Point
9. Pattern, welche bei Tools and Materials die Verbindung zwischen Interaction Part und Functional Part der Tools darstellen: Observer sowie Event Listener
10. Möglichkeiten für Implementierung von Rollen: z.B. Interface, Decorator, Role Object Pattern, GenVoca Pattern, Class Adapter Pattern
11. Nachteile Interface für Implementierung von Rollen: keine Rollenverwaltung zur Laufzeit, Neu-Implementierung in jeder Core-Klasse notwendig

Bei meiner Erstprüfung bin ich u.A. an der Erklärung des MVC-Rollenmodells gescheitert.

---

Modul: INF-VERT3
Semester: WS 2018
Prüfer: Dr. Sebastian Götz

Lehrveranstaltung: Design_Patterns_and_Frameworks
Prüfer: Dr. Sebastian Götz
Freundliche Atmosphäre. Es wird einem geholfen, wenn man mal hängt.

INHALT:

1. Zeichnen Sie eines der grundlegenden Design Pattern zu Variability.
	→ Template Method oder Template Class
	
1.2. Was müsste man ändern, um Bridge zu erhalten?
	→ Zweite Hierarchie & Aggregation dazwischen zeichen
	
1.3. Was ist der Unterschied zwischen den beiden Design Pattern?
	→ Vererbung vs. Aggregation, Intend, Rollen, …
	
1.4. Wie sieht das Rollenmodell von Bridge aus?
	→ Aufzeichnen
	
2. Wie lassen sich Rollen implementieren?
	→ Interfaces, Mixins, ROP, Delegation, Adapter, …
	→ Vor- & Nachteile dieser

2.1. Was sind eigentlich Mixins und wie ist die Relation zwischen Klasse & Mixin?
	→ …
	
2.2. Welches Problem hat man bspw. beim Role Object Pattern?
	→ Object Schizophrenia (erläutern)
	
2.3. Wie ließe sich das im Anwendungsfall (Ferngesteuerte Physiotherapie-Weste) übertragen?
	→ Beteiligte Personen könnten unterschiedliche Rollen haben (aber richtige Antwort wäre wahrscheinlich, dass die Weste verschiedene Rollen annehmen kann (richtige & falsche Bewegung))
	
3. Wo kommt das Role Object Pattern in der Tools & Materials Metapher vor?
	→ Materials erlauben Tools nur Zugriff über definierte Material-Roles

---

Modul: INF-BAS3
Semester: WS 2018
Prüfer: Dr.-Ing. Sebastian Götz

Lehrveranstaltung: Design_Patterns_and_Frameworks
Prüfer: Dr.-Ing. Sebastian Götz
+ Einstieg: Design Patterns für Extensibility
 + grundlegendstes Pattern für Extensibility -> Objectifier
 + Pattern zeichnen und erklären (Struktur ist wichtig; Klassen- und Methodennamen nicht besonders wichtig)

+ Decorator als weiteres Pattern für Extensibility
 + Pattern zeichnen und erklären

+ Decorator als Rollenmodell
 + zeichnen und erklären

+ alle Einschränkungen für Rollen (role constraints) nennen und erklären

+ Wie kann man Rollen implementieren?
 + Interfaces, Mehrfachvererbung, Mixins, Delegation/Multi-Bridges -> Role Object Pattern, Decorator

+ Framework Hook Patterns -> wieder als Beispiel das Decorator Pattern
 + Template -> (konkrete) Komponente; Hook -> Decorator
 + Art des Framework Hook Patterns -> 1-H<=T Pattern -> 1-ObjectRecursion
 + Einteilung des 1-H<=T Patterns (Decorator) als Framework -> Greybox Framework

+ Mixins -> Worauf basieren Mixins bzw. wie können sie implementiert werden?
 + basieren auf Generics/Vererbung mit konkreter ParametrisierungModul: INF-BAS3

---

Semester: WS 2022
Prüfer: Götz

Lehrveranstaltung: Design_Patterns_and_Frameworks
Prüfer: Götz
Prüfer: Götz
Prüfung in Präsenz, angenehme Atmosphäre, Hilfestellungen werden gegeben 

1. Habe ein Klassendiagramm vorgelegt bekommen und ich sollte Design Patterns finden 
2. Das Role Model von chain of responsibility aufmalen
3. Welche Constraint könnte da noch sinnvoll sein? —> role prohibition damit ein predecessor nicht sein eigener successor sein kann
4. Wie kann man Rollen implementieren? —> aufzählen und kurz erklären und nach/vorteile (Multiple Inheritance, Interfaces, Mixins, Role Object Pattern) 
5. Welches Framework pattern für chain of responsibility? --> entweder unification oder inheritance und erklären wieso 
6. Könnte man für einen Mitarbeiter der bei zwei unterschiedlichen Firmen arbeitet das GenVoca Pattern benutzen? —> nein weil es um Types geht ? 

Insgesamt eine sehr gute Note bekommen, auch wenn ich nicht alles wusste :) 