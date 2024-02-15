…ist ein Verhaltensmuster, mit dem Sie Anfragen entlang einer Kette von Handlern weiterleiten können. Nach Erhalt einer Anforderung entscheidet jeder Handler, ob er die Anforderung bearbeitet oder an den nächsten Handler in der Kette weitergibt, je nachdem ob "er das Problem lösen kann". 
Es gibt kein "Kernobjekt", alle erben rekursiv von einer Oberklasse; alle wissen dass sie irgendeine andere Klasse verstecken (<-> [[Object Recursion]]).

## Problemstellung
![[Pasted image 20231124183458.png]]
![[Pasted image 20231124183506.png]]
"Für Hilfe für x, drücken Sie die 1. Für y, drücken Sie die 2. …"

## Aufbau
![[Pasted image 20231124183616.png]]
- **Handler**: deklariert das gemeinsame Interface. Enthält meist nur `handle(request)`, manchmal auch `setNext(handler)`
- **Base Handler**: optionale Klasse für gemeinsamen Boilerplate-Code aller Handlerklassen. Enthält meist Referenz zum nächsten Handler `next` und implementiert Standardverhalten "delegiere zum Nächsten, falls existent".
- **Concrete Handler**: enthalten Code zur tatsächlichen `request`-Verarbeitung. Bei Erhalt muss jeder Handler entscheiden ob er diesen Verarbeitet und ob er diesen entlang der Kette weitergibt. Sind zumeist in sich geschlossen (self-contained) und immutable und nehmen erforderliche Daten nur einmal über den Konstruktor entgegen.
- **Client**: erzeugt diese Ketten einmalig oder dynamisch. `request`s können an beliebigen Handler in der Kette gesendet werden, muss nicht der Erste sein.

## Beispiel
![[Pasted image 20231124184349.png]]
![[Pasted image 20231124184358.png]]

## Anwendung
- wenn unterschiedliche Request-Arten auf unterschiedliche Weisen verarbeitet werden sollen, aber exakte Typen und jeweilige Reihenfolgen im Voraus nicht bekannt sind.
- wenn es wichtig ist, mehrere Handler in einer bestimmten Reihenfolge auszuführen.
- wenn sich Handler und ihre Reihenfolge zur Laufzeit ändern sollen

[auf refactoring.guru](https://refactoring.guru/design-patterns/chain-of-responsibility)

---
## Role-based Design
![[Design Patterns als Role Models#Chain of Responsibility]]