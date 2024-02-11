Daten und (zugehörige) Aktionen werden zu Objekten gruppiert und zusammen entwickelt

**Verwendung** wenn Fokus auf Objekten (+Aktionen, Attributen) des Systems liegt; wenn reale Objekte simuliert werden sollen

**Architekturstile**: [[Architekturstile#Call-Based Architectural Style]]

## Call-Based-Architekturstil
- Kontrollfluss symmetrisch (calls, returns), *nicht fixiert* (dyn. Architektur via Polymorphie)
- Datenfluss kann parallell (push-based) oder antiparallel (pull-based) sein

## Aktor-/Prozess-Systeme
"selbstständig agierende Objekte" 
- statt `main()` -> ...
- in jedem Objekt while(true) laufend, ...
- z.B. Simulation