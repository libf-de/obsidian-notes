ähnlich wie [[Funktionsorientierter Entwurf]], jedoch arbeiten Aktionen auf einem State in einem imperativen, state-orientiertem Stil

**Verwendung** wenn das System ein Zustandssystem ist, in welchem Aktionen die Zustandsübergänge bilden.

**Architekturstile**: [[Architekturstile#Call-Based Architectural Style|Call-Based Arch.]], [[Architekturstile#Datenfluss-Basierter Architekturstil|Datenfluss-basierte Systeme (P&F, Streams)]]

**Beispiele**
- Petrinetze
- Use-case-basierte Entwicklung
- Datenfluss-basierte Entwicklung SA, SA/SD

## Flashcards

Für welche Anwendungen aktionsorientierten Entwurf? #flashcard #entwurfsmethoden 
Wenn System einen State hat, auf dem Aktionen ausgeführt werden. 
Bspw. Smarthome Lichtschalter, Petrinetze,
- - -
Was unterscheidet funktions- und aktionsorientierten Entwurf? #flashcard #entwurfsmethoden 
Beim aktionsorientiertem Entwurf liegt der Fokus mehr auf dem State des Systems; Aktionen *benötigen* einen State auf dem sie arbeiten.
Beim funktionsorientiertem Entwurf könnte ein State mitgegeben werden, ist aber kein Kernaspekt.
- - -
Aktionsorientierter Entwurf -> Architekturstile? #flashcard #entwurfsmethoden 
Call-based oder Datenfluss-based