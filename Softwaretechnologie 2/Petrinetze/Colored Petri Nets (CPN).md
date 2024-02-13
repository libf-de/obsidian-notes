- Tokens sind typisiert ("colored")
- Typen sind durch Datenstruktur-Sprache beschrieben (Java, ML, UML, Grammatik, ...)
- Vollautomatische Code-Generation möglich, u.a. in Java und ML
- Netz-Simulator erlaubt Debugging des Netzes
- Beweis von Features des PNs möglich -> besser geeignet als UML für sicherheitskrit. Syst.

## Annotations
Places werden annotiert mit…
- **Token-Typen**: `(STRING x STRING)`
- **Kardinalität** von Objekten: `2'("Uwe", "Assmann")`

Kanten werden annotiert mit…
- **Typvariablen** die gegen Token-Objekte vereinigt werden: `(X,Y)`
- **Guards**: `[ X == 10 ]`
- **If-Then-Else Statements**: `if X < 20 then Y := 4 else Y := 7`
- **Switch Statements**
- **Boolean-Funktionen** die Bedingungen prüfen

## Verfeinerung
### Modularität
- Ein **Subnetz** wird *Page* (Module) genannt
	- Jede Page hat Ports nach außen; diese markieren ein-/ausgehende Transitionen/Places
- **Transition page**: Interface enthält Transitionen (transition ports)
- **Place/State page**: Interface enthält Places (place ports)
- **Net Class**: eine benannte Page die eine Art Vorlage oder Klasse ist; kann zu einem Netz-Objekt instantiiert werden -> Wiederverwendung möglich!
![[Pasted image 20231207122717.png]]

### Hierarchisch
Places und Transitions können hierarchisch verfeinert werden, durch zwei punktweise Verfeinerungen:
- Transition durch eine Transition Page ersetzen
- State durch State Page ersetzen
Dabei gilt, dass die Einbettung/Einbettungskanten erhalten bleiben müssen!

CPNs können als hierarchischer/reduzibler Graph angeordnet werden
- somit große Spezifizierungen möglich, mit immernoch guter Übersicht
- Teilnetze, die sich aus Verfeinerungen ergeben, sind auch Place-/Transition-Pages

### Verfeinerungsarten
#### Punktweise Verfeinerung
- **Transition refining page** - verfeinert eine Transition/Transition-Ports
- **Place/State refining page** - verfeinert einen Place/Place-Ports
![[Pasted image 20231207124039.png]]

#### Hyperedge Verfeinerung
Hyperedges und Regionen in PN können verfeinert werden:
![[Pasted image 20231207124225.png]]

## Flashcards

Was haben CPNs was PNs nicht haben? #flashcard #petrinetze 
- typisierte Plätze und Kanten (-> gefärbt)
- Places und Transitionen können verfeinert werden; CPN = reduzibler Graph:
- Pages = Subnetze: hat Ports (Ein-/Ausgehende Transitionen/Places)
	- kann hierarchisch aufgebaut werden
	- Transition Page (Ports = Transitionen), Place Page (Ports = Places), Region Pages
- - -
Wofür werden CPNs eingesetzt? #flashcard #petrinetze 
- Modellierung von parallelen Systemen, da modular und reduzierbar
- Bewesen von Liveness, Fairness, k-boundedness, Deadlock/-freiehit
- - -
