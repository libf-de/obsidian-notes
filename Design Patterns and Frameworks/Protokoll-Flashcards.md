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
- - -
Wie wird beim ROP Object Schizophrenia verhindert? #flashcard #roles #dpf 
Alle Aufrufe laufen über das Core-Object, was diese dann an die Rollen delegiert.
- - -
Beispiele für Variability Pattern? #flashcard #dpf 
- TemplateMethod
- TemplateClass
- Strategy
- Bridge
- - -
Struktur+Role Model von Template Method? #flashcard #dpf
![[Variability Patterns/images/Pasted image 20231109121632.png]]
![[Rollenbasiertes Design/images/Pasted image 20240214125928.png]]
- - -
Struktur+Role Model von Strategy? #flashcard #dpf 
![[Variability Patterns/images/Pasted image 20231109132327.png]]
![[Rollenbasiertes Design/images/Pasted image 20240214130344.png]]
- - -
Struktur+Role Model von Chain of Responsibility? #flashcard #dpf 
![[Extensibility Patterns/Recursive Extension/images/Pasted image 20231124183616.png]]
![[Rollenbasiertes Design/images/Pasted image 20240214124631.png]]
- - -
Welche Arten an Mini-Connectors gibt es? #flashcard #dpf 
- Expansion Point
- Variation Point
- - -
Wie können Roles implementiert werden? Vor-/Nachteile? #flashcard #dpf #roles 
- Interfaces (jede Rolle nur 1x spielbar, Codeduplikation, statisch)
- Mehrfachvererbung (jede Rolle nur 1x spielbar, statisch, Sprachsupport)
- Mixins/GenVoca (Rollen mehrfach spielbar, statisch)
- Role Object Pattern
- - -
Struktur+Role Model von Bridge? #flashcard #dpf 
![[Variability Patterns/images/Pasted image 20231109133850.png]]
![[Rollenbasiertes Design/images/Pasted image 20240214130927.png]]
- - -
Was sind Mixins? Zusammenhang Class/Mixin? #flashcard #dpf 
Mixin ist eine unvollständige Klasse zur Erweiterung einer anderen Klasse.
- - -
Wo kommt das ROP in Tools&Materials-Metapher vor? #flashcard #dpf 
- - -
Welche Extension-Patterns gibt es? #flashcard #dpf 
- Composite
- Decorator
- Chain of Responsibility
- Observer
- Proxy
- - -
Struktur+Role Model von Composite? #flashcard #dpf 
![[Extensibility Patterns/Recursive Extension/images/Pasted image 20231124171433.png]]
![[Rollenbasiertes Design/images/Pasted image 20240214124724.png]]
- - -
Struktur+Role Model von Decorator? #flashcard #dpf
![[Extensibility Patterns/Recursive Extension/images/Pasted image 20231124181439.png]]
![[Rollenbasiertes Design/images/Pasted image 20240214124948.png]]
- - -
