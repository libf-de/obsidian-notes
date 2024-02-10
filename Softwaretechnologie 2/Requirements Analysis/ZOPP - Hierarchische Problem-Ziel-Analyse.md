(oder auch ZOPP - Ziel Orientierte ProjektPlanung)

## Struktur
1. Stakeholder analysis
2. Hierarchische Problemanalyse (Ist-Analyse)
3. Hierarchische Zielanalyse (Soll-Analyse)
4. Hierarchische Funktionale-Anforderungsanalyse
5. Nicht-Funktionale Anforderungsanalyse
6. Erfolgskriterien-Analyse
7. Hierarisches Konstruieren von Akzeptanztests
*Ziel:* Teile-und-Herrsche (großes Problem in Teilprobleme zerlegen)

## Hierarchische Problemanalyse
1. Phase - Problemhierarchie
	- Probleme und Problem-Domänen suchen/finden (-> Mindmap/Baum)
		- Probleme negativ formulieren
	- Hauptproblem identifizieren
	- Problembaum aufstellen - Haupt- und Unterprobleme anordnen
2. Ursache-Wirkungsanalyse
	- Gründe für Hauptproblem finden (wichtiger)
		- Probleme können mittels "Warum"-Fragen zerlegt werden
	- Grundursachen für Probleme finden (am wichtigsten)
	- Folgen des Hauptproblems finden
3. Prioritätensetzung
	- Unterprobleme priorisieren
	- Überprüfen ob Hierarchie vollständig und widerspruchsfrei ist

![[Pasted image 20231210115325.png]]
1. Problemhierarchie

![[Pasted image 20231210115350.png]]
2. Ursache-Wirkungsanalyse

![[Pasted image 20231210115443.png]]
2. Ursache-Wirkungsgraph

> [!information] Ziele
> in 4 Klassen unterteilen:
> - Erwünscht (SOLLTE)
> - Verpflichtend (MUSS)
> - Zusätzlich (KANN)
> - Nicht-Ziel (NIEMALS)

![[Pasted image 20231210120247.png]]
3. Zielbaum, Priorisierung aus Problembaum übernehmen

## Hierarchische Funktionale Anforderungsanalyse
Ziele <> Anforderungen…gewünschte Features um Probleme zu löschen, Ziele zu erreichen
Spezifizierung durch:
- use case Diagramme
- Text, Listen
- Funktionsbäume/-netze
- Datenflussdiagramm
- Petrinetz
- Logik

![[Pasted image 20231210120633.png]]
Funktionsbaum

## Nicht-Funktionale Eigenschaften
Kategorien/Sichten von Anforderungen
- Darstellung
	- Operative
	- Quantitativ
	- Qualitativ
	- Deklarativ
- Zufriedenstellung
	- Hart
	- Weich
- Art
	- Funktion
	- Daten
	- Leistung
	- spezielle Eigenschaft
	- Beschränkung
	- Semi-Funktional (<- ist Eigenschaft essentiell für Betrieb)

Kategorien von Nicht-Funktionalen Anforderungen
- Stakeholder (Entwicklerqualitäten, Geschäftsqualität, Benutzungsqualität)
- Messbarkeit (Verifizierbarkeit (Spezifikation zur Überprüfung ex.))
- Kosten-Nutzen-Relation 

## Kontextmodell
Schnittstellen zur Außenwelt

## Erfolgskriterien
-> Grundlage für Akzeptanztests/-kriterien
![[Pasted image 20231210121715.png]]

## Akzeptanztests
![[Pasted image 20231210121824.png]]

## Software Requirements Specification (SRS)
All das landet hier :)

## Anforderungs-Management
### Extreme Programming
Anforderung mittels Story-Cards verwalten (enthalten eine Kundenanforderung in Klartext, eine Anforderung nach der anderen umsetzen) -> funktioniert nur im Kleinen

### Scrum
![[Pasted image 20231210122151.png]]

### Requirement Management System (Professionell)
Anforderungen in Datenbank (unternehmensweit) verwalten; Kunde kann Datenbank einsehen und bearbeiten/priorisieren