## Idee
![[Pasted image 20231109121700.png]]

**Problem**: Viel Code-Duplikation, da sich Implementationen nur in "Feinheiten unterscheiden"
**Lösung**: Algorithmus in Schritte/Methoden unterteilen, diese in _eine Template Method_ packen die alle Schritte durchgeht. Schritte können abstrakt (-> Feinheiten) oder konkret (-> Gemeinsamkeiten) sein.
## Aufbau
![[Pasted image 20231109121632.png]]

## Anwendung
- wenn Clients nur _bestimmte Schritte_ eines Algorithmus _erweitern_ sollen, aber nicht den ganzen Algorithmus / seine Struktur
- wenn man _mehrere Klassen_ hat, die _fast identische Algorithmen mit kleinen Unterschieden_ haben.

## Beziehungen
- [[Objectifier]] lagert lediglich die Feinheiten in eine separate Klasse/Objekt aus, es existiert nicht zwangsläufig eine `templateMethod()`, die die Einzelschritte aufruft.
- [[Template Class]] kombiniert _Template Method_ und [[Objectifier]]
- [[Factory Method]] ist eine Spezialisierung der Template Method
- Template Method basiert auf Vererbung
	- Teile eines Algo. können durch _Erweiterung_ dieser in einer Subklasse geändert werden
	- Arbeitet auf _Klassen-Level_, somit _statisch_
- [[Strategy]] basiert auf [[Vererbung]]
	- Teile des Verhaltens eines Objekts können durch _Zuweisung/Übergeben von Strategien_ verändert werden
	- Arbeitet auf _Objekt/Instanz-Level_, Verhalten kann _zur Laufzeit_ verändert werden

## Role-based Design
![[Design Patterns als Role Models#Template Method]]