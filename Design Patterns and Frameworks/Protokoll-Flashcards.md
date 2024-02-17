Was ist eine Rolle? #flashcard #dpf #roles
Eine Rolle ist eine dynamische Sicht auf ein Objekt und kann sich ändern. Sie gehört zu einem bestimmten Anliegen und wird von Objekten gespielt/übernommen, was bedeutet, dass sie in einen bestimmten Zustand eintreten.
- - -
Welche Role-Constraints gibt es? #flashcard #dpf #roles
- role-use (benötigte Rolle *verwendet* bereitgestellte Rolle)
- role-association (Rollen *kennen* sich gegenseitig)
- role-prohibition (Objekt das Rolle A spielt darf *nicht* gleichzeitig Rolle B spielen)
- role-equivalence (Objekt das Rolle A spielt *muss* auch Rolle B spielen *und umgekehrt*)
- role-implication (Objekt das Rolle A spielt *muss* auch Rolle B spielen)
- role-implication inheritance constraint (Source muss auf *Subklasse* des Targets abgebildet werden)
- - -
Was ist der Unterschied zwischen GenVoca und ROP? #flashcard #dpf #roles 
- GenVoca - statische Rollen, implementiert mittels Mixins, jede Rolle ein Mixin
- ROP - dynamische Rollen, implementiert durch Delegation, jede Rolle ein Role-Object, Zugriff und Verwaltung über Core-Objekt, dieses delegiert Aufrufe an Role Objects
- - -
Varianten des ROP? Welche Pattern enthalten? #flashcard #dpf #roles 
- Deep Roles (Rollen können Rollen spielen; Decorator auf 1. Level)
- Flat Roles (Rollen können keine Rollen spielen)
- - -
Role Model von Chain of Responsibility? #flashcard #dpf #roles 
![[Rollenbasiertes Design/images/Pasted image 20240214124631.png]]
