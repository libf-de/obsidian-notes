## Petrinetze
- [[Grundlagen Petrinetze|Grundlegende Syntax und Semantik]]
- [[Patterns in Petrinetzen|Muster]]
	- [[Patterns in Petrinetzen#Quelle / Permanent aktive Transaktion|Quellen]]
	- [[Patterns in Petrinetzen#Senke|Senken]]
	- [[Patterns in Petrinetzen#Komplexe Transitionsoperatoren Join/Split aus YAWL|AND-Join]]
- [[Colored Petri Nets (CPN)#Verfeinerung|Refinement]]
	- [[Colored Petri Nets (CPN)#Punktweise Verfeinerung|Place, Transition]]
	- [[Colored Petri Nets (CPN)#Hyperedge Verfeinerung|Region-Pages]]
- [[Verhaltenseigenschaften|Eigenschaften]]
	- [[Verhaltenseigenschaften#Boundedness und Sicherheit|Boundedness]]
	- [[Verhaltenseigenschaften#Liveness|Lifeness]] ([[Verhaltenseigenschaften#Transition|L0 bis L4]])
- Berechnung der Eigenschaften
	- [[Verhaltenseigenschaften#…mittels Inzidenzmatrix|Überführung in Matrizen]]
	- ****Pathfinding!!!***

## Anforderungsmanagement und Qualitätssicherung
- Anforderungsmanagement
	- [[Machbarkeitsstudie|Feasibility Study]]
	- [[ZOPP - Hierarchische Problem-Ziel-Analyse|ZOPP]]
- [[Quality Management|Qualitätssicherung]]
	- Analytischer Weg: Fehler finden
		- [[Tests]] -> [[Regressionstests]], [[Akzeptanztests|Systemtests]], ...
		- [[Validierung mit Inspections und Reviews#Internal Reviews|Internal]]/[[Validierung mit Inspections und Reviews#External Reviews|External Reviews]], [[Validierung mit Inspections und Reviews#Audits|Audits]]
	- Konstruktiver Weg: Fehler vermeiden
		- [[Defensive Programming]] -> ***Contract Layer***
		- [[Validierung mit Inspections und Reviews#Pair Programming|Pair Programming]]

## Umgang mit großen Modellen
- [[Grundlegende Graph-Klassen|Grundlegende Klassen von Graphen]] ([[Grundlegende Graph-Klassen#Liste|Liste]], [[Grundlegende Graph-Klassen#Bäume|Baum]], ...)
- Automatische Analyse und Anpassung des Graphen um Komplexität zu reduzieren
- [[Grundlegende Graph-Klassen#Reduzibler Graph|Reduzible Graphen]]
- Umsetzung mit Graphersetzungssystemen (GRS) oder Logik
	- [[Graph-Logik-Isomorphismus]]
	- Same Generation Algorithmus zum Finden von Layern
		- Umsetzung als Logikprogramm
		- Umsetzung als Edge-Addition-Rewrite-System -> terminiert, konfluent
- Pfadanalyse, Erreichbarkeitsanalyse
	- transitive Hülle

## Entwurfsmethoden
- Entwurfsmethoden geben Architekturstile vor
- [[Funktionsorientierter Entwurf|Funktionsorientierter Entwurf]] -> [[Architekturstile#Call-Based Architectural Style]]
- [[Aktionsorientierter Entwurf|Aktionsorientierter Entwurf]] -> **Tom DeMarco SA/SD** -> **DFDs, Data Dictionary**
- **ECA-orientierter Entwurf** -> **Rule-based Architectural Style**
- [[Datenorientierter Entwurf|Datenorientierter Entwurf]] -> **Repository, Blackboard, ...**
- **Model-driven Software Development**
	- [[Meta models|Metamodellierung, Meta-Pyramide]]
	- [[Model-driven Architecture]] -> CIM, PIM, PSM, Code -> Modelltransformationen
	- [[Domain Specific Languages|DSLs]]
- **Software Product Lines**
	- [[Grundlagen SPL|Problem-/Lösungswelt <-> Application/Domain Engineering]]
	- [[Variabilität#Language-based Variability|Language-based Variability]] oder [[Variabilität#Tool-driven Variability|Tool-based Variability]]