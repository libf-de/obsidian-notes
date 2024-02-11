=> [[Architekturstile#Call-Based Architectural Style|Call-Based Architectural Style]]
- Entwurf von Funktionen, die Eingaben zu Ausgaben umwandeln
- Minimaler System-State (sonst [[Aktionsorientierter Entwurf]])
- Übergabe von Informationen i.d.R. mittels Parameter oder shared memory
- Aufruf einer Funktion sollte für gleiche Eingabedaten immer gleiche Ausgabe liefern (zeitunabhängig)
- somit Fokus auf Unveränderlichkeit der (Eingabe)Daten, Seiteneffekt-freiheit => *Beweisbar*
- schrittweise Verfeinerung eines Funktionsbaums (oder 1:1-Mapping eines funktionalen Anforderungsbaums [[ZOPP - Hierarchische Problem-Ziel-Analyse#Hierarchische Funktionale Anforderungsanalyse|hier]])

**Verwendung** wenn System viele unterschiedliche Funktionen hat.


---

- Schrittweise Verfeinerung erfolgt i.d.R. top-down; Funktionen werden zu Modulen oder Komponenten gruppiert
- Funktionen höherer Ordnung rufen Funktionen geringerer Ordnung auf


Dadurch:
![[Architekturstile#Call-Based Architectural Style]]

- Funktionen sind Aktionen wenn sie auf dem sichtbaren State arbeiten (siehe [[Akt
- ionsorientierter Entwurf]]) -> klar abtrennen von restlicher Logik

- Vorteilhaft für:
	- sicherheitskritische Systeme (Beweise nur möglich, wenn Architektur und Call-Graph statisch sind)
	- embedded- und Echtzeitsysteme (schneller)
	- Hochgeschwindigkeitssysteme (OS, Datenbanken, Compiler, ...)

- nach Funktionsbaum: Implementation in funktionaler Sprache
- **syntaktische** schrittweise Verfeinerung ignoriert die Semantik des verfeinerten Modells?
- **semantische** schrittweise Verfeinerung beweist, dass sich die Semantik des Programms/Modells nicht verändert hat?