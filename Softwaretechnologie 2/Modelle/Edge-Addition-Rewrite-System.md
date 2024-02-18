- fügt neue Kanten zu einem Graphen hinzu (müssen nicht permanent sein -> [[Grundlegende Graph-Klassen#Link Tree|Link Tree]])
- deklarativ (kein Kontrollfluss spezifizitert)
- **konfluent** (Regel-Reihenfolge egal)
- **rekursiv** (Regeln werden immer wieder angewendet)
- **terminierend** (terminiert, wenn alle möglichen Kanten hinzugefügt wurden)

Datalog-Problemarten:
- **S**ingle Source **M**ultiple Target **P**ath **P**roblem - `descendant(Adam,X)?`
- **M**ultiple Source **S**ingle Target **P**ath **P**roblem - `descendant(X,Adam)?`
- **M**ultiple Source **M**ultiple Target **P**ath **P**roblem - `descendant(X,Y)?`

## Flashcards

Eigenschaften Edge-Addition-Rewrite-System? #flashcard #swt2 #ears
- **konfluent** (Regel-Reihenfolge egal)
- **rekursiv** (Regeln werden immer wieder angewendet)
- **terminierend** (terminiert, wenn alle möglichen Kanten hinzugefügt wurden)
- - -
