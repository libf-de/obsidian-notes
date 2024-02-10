...ist ein strukturelles Entwurfsmuster, mit dem Sie Objekte in *Baumstrukturen* zusammenstellen und dann mit diesen Strukturen arbeiten können, als wären sie *individuelle Objekte*.

- Ähnlich wie in [[Object Recursion]] spezifiziert eine abstrakte Oberklasse gemeinsame Funktionen für zwei Arten an Unterklassen
- Composite hält *geheim* an welcher *Unterklasse* und ob an einem *Blatt oder Verzweigung* gearbeitet wird

## Aufbau
![[Pasted image 20231124171433.png]]
- **Component interface**: beschreibt gemeinsame Operationen der Baumelemente
- **Leaf**: basic Baumelement, hat keine Unterelemente; übernehmen idR. meiste Arbeit
- **Composite**: hat Unterelemente, kennt und arbeitet mit diesen aber *nur über Component-Interface*; delegiert Arbeit an Unterelemente, verarbeitet Zwischenergebnisse und gibt Endergebnis an Client zurück
- **Client**: arbeitet mit allen Elementen mittels des Component Interfaces, kommt somit mit einfachen und komplexen Elementen zurecht
## Beispiel
![[Composite 2023-11-24 17.22.35.excalidraw|100%]]

## Verwendung
- um *baumartige Strukturen* aufzubauen und darüber zu iterieren, da mit Verzweigungen und Blättern *gleichermaßen umgegangen* werden kann
- für erweiterbare Teile eines Frameworks
- Kernelement der funktionalen Programmierung (da Rekursion)

[auf refactoring.guru](https://refactoring.guru/design-patterns/composite)