(Factory mit Protocol, Structured Factory)
…ist ein Erzeugungsmuster, mit dem man komplexe Objekte Schritt für Schritt konstruieren kann. Das Muster ermöglicht es verschiedene Typen und Darstellungen eines Objekts mit demselben Konstruktionscode zu erzeugen. Es behält einen internen State vor, der den augenblicklichen Konstruktionsstand der komplexen Datenstruktur darstellt - somit werden aktueller Stand, Datenstruktur und Implementation der Datenstruktur verborgen.

## Aufbau
![[Pasted image 20231126163058.png]]
- **Builder** interface: deklariert die Konstruktionsschritte, die alle Builder gemein haben
- **Concrete Builder**s: bieten unterschiedliche Implementationen der Std.-Konstruktionsschritte, und können auch eigene zusätzliche Schritte haben
- **Product**s: resultierende Objekte, Produkte aus unterschiedlichen Buildern müssen *nicht* zur gleichen Klassenhierarchie oder Interface gehören
- **Director**: definiert die Reihenfolge in der die Konstruktionsschritte ausgeführt werden, sodass bestimmte Produktkonfigurationen erstellt und wiederverwendet werden können
- **Client**: muss eines der Builder-Objekte mit dem Director verknüpfen; meist einmalig mittels Parameter, welches dieser dann für alle Building-Prozesse nutzt; kann aber auch erst in der Produktionsmethode übergeben werden, sodass jedes Mal ein anderes Produkt entsteht

## Beispiel
+ Android AlertDialog.Builder()
![[Pasted image 20231126163658.png]]

## Anwendung
- wenn der Code unterschiedliche Darstellungen eines Produkts erzeugen soll
- um [[Composite]]-Bäume und andere komplexe Objekte zu konstruieren

## Beziehungen
- viele Designs beginnen mit [[Factory Method]] und entwickeln sich zu [[Abstract Factory]], [[Prototype]] oder _Builder_
	- [[Abstract Factory]] ist spezialisiert, Familien an verwandten Produkten zu erzeugen und gibt das erzeugte Objekt sofort zurück, während _Builder_ darauf bedacht ist, einzelne komplexe Objekte Schritt für Schritt zu konstruieren. Außerdem können noch weitere Konstruktionsschritte ausgeführt werden bevor das Produkt abgerufen wird.
