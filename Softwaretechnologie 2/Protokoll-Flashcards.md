Petrinetz für eine Toybox, die Musik abspielt wenn Figur darauf steht? #flashcard #swt2 #petrinetze 
![[Protokoll-Flashcards 2024-02-18 11.46.15.excalidraw.png]]
%%[[Protokoll-Flashcards 2024-02-18 11.46.15.excalidraw.md|🖋 Edit in Excalidraw]], and the [[Protokoll-Flashcards 2024-02-18 11.46.15.excalidraw.dark.png|dark exported image]]%%
(Grün = Zusatz zum L4-live-machen)
- - -
Mit welchen Entwurfstilen könnte man eine Toybox umsetzen? #flashcard #swt2 
ECA zum abspielen, Pipe&Filter für Download und Speicherung in Repository
- - -
Beispiele für Verifikation (QA)? #flashcard #swt2
formaler/mathematischer *Beweis* dass Implementierung Spezifikation entspricht
z.B. Model checking (PN), HOARE-Kalkül
- - -
Was ist Validierung (QA)? Beispiele? #flashcard #swt2 
Plausibilitätsprüfung von korrektem Verhalten
z.B. (Unit-)Tests, Code Coverage Analysis, Reviews, defensive Programming
- - -
(was ist [[Defensive Programming]])
- - -
Was ist ein Graph-Logik-Isomorphismus? #flashcard #swt2 
Graphen können Logik darstellen und umgekehrt, somit können Graph-Algorithmen für Logikabfragen auf Graph-basierten Spezifikationen verwendet werden oder Graph Rewrite Systems zum Schlussfolgern (transitive Hülle)
- - -
Was ist die transitive Hülle? #flashcard #swt2 
In einem Graphen ist die transitive Hülle alle (auch über weitere Knoten) erreichbare Knoten
- - -
Was ist ein Graph-Rewrite-System? #flashcard #swt2 
Ein Graph-Rewrite-System ist ein Regelsatz, nach dem neue Kanten in einem Graph erzeugt werden, bspw. kann so Same Generation Algorithmus umgesetzt werden (dann rekursiv)
- - -
([[Edge-Addition-Rewrite-System]])
- - -
Was kann mit Petrinetzen gezeigt werden? #flashcard #swt2 #petrinetze 
- Lebendigkeit
- Deadlocks/-freiheit
- Fairness
- - -
Wie lassen sich Petrinetze verfeinern? #flashcard #swt2 #petrinetze 
Colored PNs lassen sich um Seiten verfeinern, mit In- & Out-Ports als Interface, dieses muss passen.
Transition page - Transition als Interface; Place page - Place als Interface
- - -
Wie lassen sich Petrinetze komponieren? #flashcard #swt2 #petrinetze 
Transitionen und Plätze haben gleiche Namen, diese bilden ein logisches Objekt.
- - -
Wie modelliert man in einem PN den Datenaustausch zwischen Komponenten? #flashcard #swt2 #petrinetze 
Ein- und Ausgänge verbinden
- - -
Beispiele für reduzible Graphen? Vorteile? #flashcard #swt2 
- Petrinetze, Datenfluss-Diagramm, State Charts
- lassen sich einfacher überschauen / verstehen
- - -
Vorbereitungen für Akzeptanztests? #flashcard #swt2 
Software testen mit Unit- und Regressionstests
- - -
Problem von JUnit? #flashcard #swt2 
Daten stehen im Code, können nicht einfach ausgetauscht werden
- - -
Erkläre ECA-Design #flashcard #swt2 
- Event-Condition-Action-Regeln bestimmen System (auf welches Ereignis unter welchen Bedingungen folgt welche Aktion?)
- Verwendung wenn das System ein Zustandssystem ist, in welchem Aktionen die Zustandsübergänge bilden und die Aktionen von (externen) Ereignissen ausgelöst werden.
- - -
Woraus besteht ein Architekturstil? #flashcard #swt2 
Komponenten (Filter), Konnektoren (Pipes), Constraints (z.B. Datentypen)
- - -
