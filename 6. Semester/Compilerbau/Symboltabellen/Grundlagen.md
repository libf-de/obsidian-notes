= Mapping von Name zu Objekt
- erstellt in [[Semantische Analyse]], mit Informationen von lexikalischer und Syntaxanalyse
- Stack an Maps, eine für jeden Scope (global, local, …)

### Objektattribute
Name, Typ, Größe, Alignment sowie *Sprachenspezifische Attribute*:
- `volatile` = Wert kann ändern, ohne dass dies durch "nahen" Code passiert.
- `register` -> es ex. keine Adresse (-> Pointer!)
![[Pasted image 20230524112505.png]]

### Operationen
![[Pasted image 20230524112607.png]]

