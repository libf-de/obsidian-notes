(Factory Class)
…ist ein Entwurfsmuster, mit dem Sie Familien verwandter Objekte erstellen können, ohne deren konkrete Klassen anzugeben.

## Problem
- Familie an verwandten Produkten, z.B. `Chair`+`Sofa`+`CoffeeTable`
- Mehrere Varianten dieser Familie, z.B. obrige als `Modern`, `Victorian`, `ArtDeco`
![[Pasted image 20231126150910.png]]
Es sollen nun individuelle Einrichtungsobjekte erzeugt werden, sodass diese zu anderen Objekten der gleichen Familie passen (Einrichtungsstil soll gleich bleiben).

## Aufbau
![[Pasted image 20231126151345.png]]
- **Factory(Class)**: gruppiert [[Factory Method|FM]]s (Familie polymorpher Konstruktoren) zu einer Klasse
- **Abstract Product**s: deklarieren Interfaces für eine Menge von unterschiedlichen, aber verwandten Produkten die eine (Produkt)Familie bilden
- **Concrete Product**s: verschiedene Implementationen der abstrakten Products, gruppiert nach Varianten. Jedes abstrakte Product (`Chair`/`Sofa`) muss in allen gegebenen Varianten (`Victorian`/`Modern`) implementiert sein!
- **Abstract Factory**: Interface, das eine Menge an Methoden deklariert um jedes der AbstractProducts zu erzeugen
- **Concrete Factory**s: implementieren Erzeugermethoden der AbstractFactory. Jede CF korrespondiert mit einer spezifischen Produktvariante und erzeugt nur Produkte dieser.
  Auch wenn hier konkrete Produkte instanziiert werden müssen abstrakte Produkte returned werden, da der Client nicht zwischen den Produktvariationen unterscheiden (müssen) sollte.

## Beispiel
![[Pasted image 20231126152129.png]]
```kotlin
class Application(factory) {
	private var factory: GUIFactory = factory
	private var button: Button

	fun createUI() {
		this.button = factory.createButton() // Client unterscheidet nicht
		                        // zwischen unterschiedlichen Button-Typen
	}

	fun paint() {
		this.button.paint()
	}
}

fun ApplicationConfiguratorMain() {
	val factory = when(config.OS) {
		"Windows" -> WinFactory()
		"Mac" -> MacFactory()
		else -> throw Exception("unknown OS")
	}
	
	val app = Application(factory)
	...
}
```

## Anwendung
- wenn Code mit unterschiedlichen Familien verwandter Produkte arbeiten soll - dieser jedoch nicht von den konkreten Klassen abhängen soll, da sie im Voraus unbekannt sein können oder zukünftige Erweiterbarkeit ermöglicht werden soll.
- wenn Klassen mit mehreren [[Factory Method]]s existieren und diese den Hauptzweck der jeweiligen Klasse verwaschen
- Vorlesungsbeispiele
	- für Window-/Widget-Styles (Swing, AWT, …)
	- in Office-Systemen für unterschiedliche Typen ähnlicher Dokumente
	- in Business-Systemen für Produktfamilien
	- für Tools in mehreren Sprachen
	- verwandt mit [[Tools and Materials]]

## Pragmatismen
- Eine Factory(Class) befasst sich mit  $3+x$ Vererbungshierarchien (Factory, Products 1…n)
- Die $n$ Produkthierarchien müssen parallel gepflegt werden (-> Parallelhierarchien)
- Das Factory-Pattern stellt sich er dass alle Objekte mit Parallelitäts-Constraint erzeugt werden

## Varianten
### Prototype Factory
- `ConcreteFactory`s müssen nicht erzeugt werden, eine Instanz genügt wenn [[Prototype]]n der Produkte existieren
- Um neue zu erzeugen klont die ConcreteFactory die Menge an Produkten
- Variabilität wird durch Klonen behandelt
- v.a. nützlich wenn Produkte komplexen Standard-State haben oder sich kaum unterscheiden
> [!information]- Struktur
> ![[Pasted image 20231126154418.png]]

### Factory mit interpretiver Factory Method
Sollen weitere FMs hinzugefügt werden, wird dies mühsam, da die AbstractFactory und alle konkreten Fabriken bearbeitet werden müssen -> eine Factory Method mit String-Parameter:
```kotlin
class AbstractFactory {
	abstract fun createProduct(what: String): Product
}

class ConcreteFactory : AbstractFactory() {
	override fun createProduct(what: String): Product {
		return when(what) {
			"p1" -> P1()
			...
		}
	}
}
```
> [!information]- Struktur
> ![[Pasted image 20231126154840.png]]



