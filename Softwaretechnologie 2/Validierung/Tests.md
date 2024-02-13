## Statische Analyse
- Code wird nicht ausgeführt, nur Metriken (Codezeilen, Komplexität,...) angeschaut
- Kontrollflussanalyse, Abstrakte Interpretation (z.B. Umwandlung in Petrinetz -> dieses überprüfen mittels Software auf Liveness, ...)
- Datenflussanalyse -> bleiben Daten irgendwo stecken?

## Dynamischer Test
-> Unit-Tests, Blackbox-Test (Funktionsaufruf, schauen was zurück kommt)
- Code coverage (Codezeilen, if-Zweige, for-Schleifen, ... abgedeckt?)
- Fault Injection (Fehler bewusst in laufendes System einfügen -> kommt System damit klar? -> Fehlerhafte URLs, SQL injection, Server herunterfahren, …)

## Probleme
- Programmieren unter Druck -> braucht Zeit!
- "A writer never finds his own bugs" (Betriebsblindheit)
- "einfach mal" Bibliothek hinzufügen -> hat auch Abhängigkeiten, überall kommen Möglichkeiten für Sicherheitslücken hinzu -> *Technical Debt* steigt
- Testen ist negativ, desktruktiv -> Man will eigene Arbeit nicht kaputt machen; hat Idee wie etwas benutzt wird, wird beim Test schreiben auch die Richtung nehmen


## Prozess
### Management
![[Pasted image 20231211141032.png]]
Tests sollten im Sinne der Spezifikation sein, nicht einfach zufällig gewählt.

### Cleanroom-Method
Teilt Team auf in Programmierer und Tester - Programmierer darf nicht testen (und umgekehrt).
-> Großteil der Zeit geht für andere Dinge als Programmieren drauf
-> Wartung von Software ist teurer als ursprüngliches Erstellen
-> Effektiv

**Synchronize and stabilize** (MS): Vormittags programmieren, Nachmittags testen Tester


### Testgetriebene Entwicklung
- Tests vor Code schreiben
- Schauen ob der wirklich fehlschlägt!
- Code schreiben
- Überprüfen ob Tests erfolgreich sind

## Debugger
- Breakpoints, Watchpoints, ....
- Dynamic Display Debugger (Frontend für GDB, ...)

## Flashcards

Welche Testarten gibt es und worin unterscheiden sie sich? #flashcard #validation 
statische Tests - Code nicht ausführen, nur anschauen
- Daten-/Kontrollflussanalyse
- symbolische Ausführung, abstrakte Interpretation

dynamische Tests - Code ausführen, schauen was passiert
- Simulation mit konkreten Werten
- Funktionale Tests (Unit-, Integrations-, Akzeptanztests)
- Strukturorientierte Tests (Dead code finden)
- andere: Fault Injection, Regressionstests (Update ohne negative Auswirkungen?)
- - -
Was sind Probleme bei Tests? #flashcard #validation 
- Zeitdruck (Tests müssen geschrieben werden, bringen keine Funktion)
- Betriebsblindheit (man findet eigene Fehler nicht -> separate Tester nötig)
- Was überhaupt testen?
- Tests zeigen nur Vorhandensein von Fehlern, niemals Abwesenheit von Fehlern!
- - -
Was sind Methoden um Probleme bei Tests zu beheben? #flashcard #validation 
- Cleanroom - Unterteilung in Programmierer und Tester
- Test-driven-Development - Tests schreiben, testen, Code schreiben, testen, refactor
- - -
Wie funktioniert ein Debugger? #flashcard #validation 
- führt Programm aus, kann Ablauf stoppen und interne Daten anzeigen
- Breakpoints (bei Erreichen anhalten)
- Watchpoints (bei Variablenänderung anhalten)
- State Monitoring/Change (aktive Variablen-Werte sehen/verändern)
- - -
Was sind Regressionstests? #flashcard #validation 
- Testfälle werden weiterentwickelt, aber auch alte Tests werden weiter verwendet
- Sicherstellen, dass neuer Code keine negativen Auswirkungen auf alten Code hat
- Tests kontinuierlich ausführen => ohne Regressionstests keine Qualität
- Für GUI: Capture & Replay-Tools (Makros aufzeichnen + abspielen)
- - -
