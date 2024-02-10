Eine große bzw. mehrere eng verwandte Klassen werden in zwei separate Hierarchien - Abstraktion und Implementation - aufgeteilt, die unabhängig voneinander entwickelt werden können (siehe [[#Struktur]]).
## Problem
![[Pasted image 20231109133408.png]]
Es existiert bereits eine `Shape`-Klasse mit zwei Subklassen `Circle` und `Square`, nun soll die Klassenhierarchie noch um Farben ergänzt werden, `Red` und `Blue`. Sollen neue Formen und Farben hinzugefügt werden wächst die Hierarchie exponentiell an -> nicht gut.
-> Versuch, `Shape`in zwei unabhängigen Dimensionen (Form und Farbe) zu erweitern

## Lösung
-> Composition statt Vererbung
![[Pasted image 20231109133850.png]]

## Anwendung
- wenn eine große, monolithische Klasse mit _mehreren Varianten einer Funktion aufgeteilt_ werden soll (z.B. mehrere Datenbankserver verwendet werden können)
- wenn eine Klasse in _mehrere, unabhängige Richtungen erweitert_ werden soll
- wenn die _Implementationen zur Laufzeit gewechselt_ werden sollen

## Struktur
![[Pasted image 20231109134352.png]]

## Beispiel
![[Pasted image 20231109134451.png]]
[Bridge auf refactoring.guru](https://refactoring.guru/design-patterns/bridge)

## …als Implementation von Facet Classifications
- Facet (<-> Dimension)
	- Facets beeinflussen sich nicht gegenseitig, sind unabhängig voneinander
	- alle Facet-Klassen sind abstrakt
	- vereinfachen Vererbungshierarchien, indem unnötige Aspekte vernachlässigt werden können (Separation of Concerns)
- Facets in Modellierung erkennen:
	- wenn eine Klasse mehrere verschiedene Teilbereiche hat **und**
	- wenn keine Klasse existiert, deren Erben die Klasse nicht aufteilen

![[Pasted image 20231123120805.png]]

#### Multi-Bridge mit Core-Facet
- `Animal` als Core-Facet, alle anderen sind Hook-Klassen
- Boden ("Don't know") verschwindet -> Multiplizität (1 oder 0..1)
![[Pasted image 20231123121712.png|350]]

#### Multi-Bridge ohne Core
- Eine Primär-Facet auswählen, andere mit n-Bridges verbinden
- Problem: Primär-Facet *kennt* die anderen
![[Pasted image 20231123121835.png|350]]

### Geschichtete Objekte / Chain-Bridge
![[ChainBridgeWithCore.svg]]
- obere Schichten (links) sind abhängig von unteren Schichten (rechts).
- Jede Bridge befasst sich nur mit ihrer nächsten -> Separation of Concerns.
- mit Core wäre noch eine Facet zwischen Animal und Everywhere.

#### DataGenerator-Beispiel
Als normale Bridge:
![[Pasted image 20231123124554.png|450]]

Als 2-Chain-Bridge:
![[Pasted image 20231123124533.png|450]]

### Vor-/Nachteile
+dynamisch variierbar
+weniger Klassen (siehe [[#Problem]])
-Kein Typ-Checking
-Keine Kontrolle über mögliche Kombinationen möglich (illegale/undefinierte)
-Objekt-Schizophrenie, Management von z.B. hash-Codes nötig ("ich" bin Teil eines größeren Objekts; ein Hash pro logischem Objekt gewünscht)
-Speicherverbrauch, Geschwindigkeit