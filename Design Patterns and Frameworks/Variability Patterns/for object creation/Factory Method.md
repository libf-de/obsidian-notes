…ist ein Entwurfsmuster, das eine Schnittstelle für die Erstellung von Objekten in einer Oberklasse bietet, es aber Unterklassen ermöglicht, den Typ der erstellten Objekte zu ändern.
## Problem
Kopplung zwischen Objekterstellung und Arbeit mit diesen macht Erweiterbarkeit/Variabilität einer Anwendung schwierig.

## Aufbau
![[Pasted image 20231126144216.png]]
- **Product**: definiert das Interface, welches alle Objekte gemeinsam haben die vom Creator und seinen Unterklassen erzeugt werden können
- **Concrete Product**: unterschiedliche Implementationen des Product-Interfaces
- **Creator**: 
	- return-Type **muss** dem Product-*Interface* entsprechen!
	- deklariert die Factory Method die neue Product-Objekte erzeugt, diese kann auch abstrakt sein, sodass alle Subklassen diese selbst implementieren müssen; falls nicht, erzeugt die Basisimplementierung ein Standard-Product
	- typischerweise ist der Creator nicht ausschließlich für die Product-Erzeugung zuständig sondern enthält weitere Kern-Business-Logik, die mit Products arbeitet - das Pattern dient der Entkopplung von Erzeugung und gemeinsamer Verarbeitungslogik.
- **Concrete Creator**: überschreiben Basis-Factory-Method, sodass anderer Product-Typ erzeugt wird; muss nicht zwangsläufig immer neue Instanzen erzeugen, kann auch existierende Objekte zurückgeben

## Beispiel
![[Pasted image 20231126144940.png]]
```kotlin
abstract class Dialog {
	abstract fun createButton(): Button
	
	fun render() {
		val okButton = createButton() //Factory Method used *here*
		okButton.onClick(::closeDialog)
		okButton.render()
	}
	...
}

class Application {
	var dialog: Dialog

	init {
		val config = readConfig()
		dialog = when(config.OS) {
			"Windows" -> WindowsDialog() //FactoryMethod *not* used here
			"Web" -> WebDialog()
			else -> throw Exception("unknown OS")
		}
	}
	...
}
```

## Anwendung
- wenn genaue Typen und Abhängigkeiten mit denen gearbeitet werden soll nicht im Voraus bekannt sind
- wenn Usern einer Lib/Framew. ermöglicht werden soll interne Komponenten zu erweitern
- wenn Systemresourcen gespart werden sollen, indem existierende Objekte wiederverwendet werden anstatt sie jedes Mal neu zu erzeugen

## Flexible Erzeugung mittels Reflection
- Konstruktor kann Objekte statisch unbekannter Klassen erzeugen, indem Reflection:
	- Klassenname + zugehöriges Klassenobjekt findet
	- dann Klassenobjekt klont
!! Reflection ist zumeist langsam !!

```java
void createProduct(String className) {
	...
	house = (Building) Class.forName(className).newInstance();
	...
}
```

## in parallelen Klassenhierarchien
- eine Klassenhierarchie bietet [[Factory Method|FMs]] an um Objekte einer zweiten Hierarchie zu erzeugen
- auf jeder Ebene ist die FM in einer parallelen Klasse auf gleicher (Abstraktions-)Ebene implem.
- Parallelismus-Constraint hier = jedes lesbare Objekt muss parallelen Manipulator erzeugen:
![[Pasted image 20231126150224.png]]

## Beziehungen
Eine FactoryMethod ist eine HookMethod, verwendet von einer [[Template Method]], die ein Product zurückgibt.