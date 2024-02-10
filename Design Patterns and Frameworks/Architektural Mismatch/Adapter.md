…ist ein strukturelles Entwurfsmuster das Objekten mit inkompatiblen Interfaces erlaubt zusammen zu arbeiten.

## Object Adapter
- ist ein [[Proxy]] der *ein Interface/Protokoll/Datenformat* auf ein anderes mappt
- kann keine Kontrollflüsse anpassen! (da nur 1x bekommt, beim Eintritt in adaptierte Klasse)
![[Pasted image 20231129125335.png]]
- **Client**: enthält existierende Business-Logik
- **Client Interface**: beschreibt Protokoll welchem Klassen, die mit dem Client zusammenarbeiten wollen, folgen müssen
- **Service**: eine nützliche (meist 3rd party oder legacy) Klasse, die vom Client nicht direkt verwendet werden kann da Interfaces inkompatibel sind
- **Adapter**: Klasse die sowohl mit `Client` (implementiert `Client Interface`) als auch `Service` (wrappt `Service`-Objekt) arbeiten kann; 
	- *empfängt Aufrufe* vom Client via dem `Client Interface` und 
	- *übersetzt* diese in Aufrufe an das gewrappte `Service`-Objekt 
	  in einem für dieses *geeignete Format*.
- Client-Code wird nicht an bestimmte Adapter-Klasse gebunden solange die Arbeit über das `Client Interface` erfolgt - somit können auch weitere Adapter erstellt werden, ohne dass der Client-Code geändert werden muss.

## Class Adapter
- verwendet *Mehrfachvererbung*, kann daher nicht in allen Programmiersprachen eingesetzt werden
![[Pasted image 20231129130113.png]]
- **(Class) Adapter** muss keine Objekte wrappen, da es von beiden erbt. Adaption erfolgt innerhalb der `override`n Methoden. Resultierender Adapter kann dann **anstatt** einer existierenden Client-Klasse verwendet werden.

## Beispiel
![[Pasted image 20231129130306.png]]
```kotlin
open class RoundHole(radius) {
	fun getRadius() = this.radius
	
	fun fits(peg: RoundPeg)
		= this.getRadius() >= peg.getRadius()
}

class SquarePegAdapter(peg: SquarePeg) : RoundHole() {
	override fun getRadius() {
		return peg.getWidth() * sqrt(2) / 2
	}
}

hole = RoundHole(5)
hole.fits(RoundPeg(5)) //true
hole.fits(SquarePeg(5)) //compiliert nicht, inkompatible types
hole.fits(SquarePegAdapter(SquarePeg(5))) //true
```

## Anwendung
- wenn eine existierende Klasse verwendet werden soll, aber deren Interface nicht mit dem Rest des eigenen Code kompatibel ist
- wenn einige existierende Unterklassen wiederverwendet werden sollen, denen gemeinsame Funktionalität fehlt die nicht zur Oberklasse hinzugefügt werden kann

## Beziehungen
- ähnlich wie [[Decorator]] (erbt Interface von `Goal Class`, jedoch adaptiert Interface - somit können Adapter später in eine Vererbungshierarchie eingesetzt werden; außerdem unterstützt Decorator rekursive Komposition - bei Adapter nicht möglich)
- [[Bridge]] wird idR. vorher entworfen, um Teile eines Programms unabhängig voneinander zu entwickeln. Adapter wird idR. mit einem existierenden Programm verwendet um zwei eigentlich-inkompatible Klassen miteinander arbeiten zu lassen
- Mit *Adapter* wird auf existierendes Objekt mittels anderem Interface zugegriffen. 
  Mit [[Proxy]] bleibt das Interface gleich. 
  Mit [[Decorator]] wird mittels erweitertem Interface auf Objekt zugegriffen.
- [[Facade]] definiert neues Interface für existierende Objekte, kann mit ganzem Subsystem an Objekten arbeiten
  *Adapter* versucht existierende Interfaces nutzbar zu machen, arbeitet idR. mit nur 1 Objekt
- [[Bridge]], [[Strategy]], [[State]] haben ähnliche Strukturen ([[Aggregation und Composition|Composition]]), lösen jedoch unterschiedliche Probleme (Pattern strukturiert nicht nur Code, sondern kommuniziert Problem welches gelöst werden soll mit anderen Programmierern)