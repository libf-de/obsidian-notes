- Fokus auf Unveränderlichkeit der Daten, Seiteneffekt-freiheit => *Beweisbar*
- Aufruf einer Funktion sollte für gleiche Eingabedaten immer gleiche Ausgabe liefern, diese sollte zB. nicht von einem äußeren State abhängen.
- schrittweise Verfeinerung eines Funktionsbaums (oder 1:1-Mapping eines funktionalen Anforderungsbaums [[ZOPP - Hierarchische Problem-Ziel-Analyse#Hierarchische Funktionale Anforderungsanalyse|hier]])
- Schrittweise Verfeinerung erfolgt i.d.R. top-down
- Funktionen höherer Ordnung rufen Funktionen geringerer Ordnung auf
![[Pasted image 20240207113032.png]]

Dadurch:
![[Architekturstile#Call-Based Architectural Style]]

- Funktionen sind Aktionen wenn sie auf dem sichtbaren State arbeiten (siehe [[Aktionsorientiertes Design]]) -> klar abtrennen von restlicher Logik

- Vorteilhaft für:
	- sicherheitskritische Systeme (Beweise nur möglich, wenn Architektur und Call-Graph statisch sind)
	- embedded- und Echtzeitsysteme (schneller)
	- Hochgeschwindigkeitssysteme (OS, Datenbanken, Compiler, ...)

- nach Funktionsbaum: Implementation in funktionaler Sprache
- **syntaktische** schrittweise Verfeinerung ignoriert die Semantik des verfeinerten Modells?
- **semantische** schrittweise Verfeinerung beweist, dass sich die Semantik des Programms/Modells nicht verändert hat?