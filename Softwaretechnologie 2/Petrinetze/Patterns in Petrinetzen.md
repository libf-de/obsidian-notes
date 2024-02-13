## Puffer-Pattern
### Reservoir-Place
generiert keine Objekte
![[Pasted image 20231207124419.png]]

### Quelle / Permanent aktive Transaktion
Generiert Objekte (Objektquelle, Eventquelle)
![[Pasted image 20231207124456.png]]

### Prozess
sequentiell
![[Pasted image 20231207124522.png]]


### Zwischenarchiv (Intermediate Archive)
Puffer
![[Pasted image 20231207124618.png]]

### Archiv
Speichert Objekte, kann $k-$bounded sein
![[Pasted image 20231207124656.png]]

### Senke
Löscht/zerstört Objekte
![[Pasted image 20231207124731.png]]

## Synchronisations-Patterns
### Barrier
Koppelt Prozesse mit paralleler Fortführung
![[Pasted image 20231207125014.png]]

### n-Barrier
Brücken: Transitionen zwischen Phasen
![[Pasted image 20231207125057.png]]

## Verzögerungs-Patterns
### Delay-Token hinzufügen
verhält sich wie ein Semaphor
![[Pasted image 20231207125308.png]]

### Circular Delay Net hinzufügen
verhält sich wie ein Splitter?
![[Pasted image 20231207125356.png]]

## Komplexe Transitionsoperatoren Join/Split aus YAWL
![[Pasted image 20231207125449.png]]

## Parallelismus-Patterns - Transitional Operators
![[Pasted image 20231207125535.png]]
![[Pasted image 20231207125609.png]]
![[Pasted image 20231207125625.png]]

## Kommunikations-Pattern
### Producer/Consumer direkt
![[producer-consumer-direct.gif]]

### Producer/Consumer mit Buffer
![[producer-consumer-buffer.gif]]
Zusätzlich kann `buffer` ein Bound haben (1…n)

### Producer/Consumer mit Buffer und indeterminist. Zustellung
-> Buffer mit OR-Split
![[Pasted image 20231207130932.png]]

### Producer/Consumer mit Buffer und Broadcast-Kommunikation
-> Buffer mit AND-Split
![[Pasted image 20231207131042.png]]

## Semaphore
Binäre oder Zählende Semaphore bieten `lock` und `free`-Operationen als Transitions an
Unterschieden durch Kapazität/Bound des Semaphore-Place
![[semaphore.gif]]

## Flashcards

Wie sieht eine Quelle und eine Senke in einem Petrinetz aus? #flashcard #petrinetze
Quelle - generiert Tokens - Transition ohne eingehende Kante
Senke - zerstört Tokens - Transition ohne ausgehende Kante
- - -
