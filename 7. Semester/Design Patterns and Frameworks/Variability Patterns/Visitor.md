Trennt Algorithmen von den Objekten, auf denen sie arbeiten.

## Problem
Ein Grafikprogramm soll Zeichungen in XML-Dateien exportieren. Es gibt verschiedene `Shapes`, z.B. `Dot`, `Circle`, `Rectangle`, `CompoundShape`. Allerdings ist die primäre Aufgabe der `Shape`-Objekte nicht, in XML exportiert zu werden - die Implementation sollte also nicht unbedingt dort erfolgen. Auch würde dies nicht ermöglichen später einfach weitere Formate exportieren zu können, z.B. in SVG.

## Lösung
Das neue Verhalten in eine separate `Visitor`-Klasse platzieren, die das jeweilige Objekt als Argument übergeben bekommt. Da es mehrere Arten von `Shape`s gibt, bekommt jedes seine eigene Methode im `Visitor`:
![[Pasted image 20231109142644.png]]
Jedes concrete object muss `accept` so implementieren, dass es die dem Objekt entsprechende Funktion im Visitor aufruft und dieser eine Referenz zu sich selbst übergibt, bspw. um die Position des `Dot` abzurufen:
```kotlin
class Dot : Shape() {
	fun accept(v: Visitor) {
		v.visitDot(this)
	}
}
```

Die Anwendung kann dann einfach alle Shapes durchlaufen und exportieren:
```kotlin
var allShapes: List<Shape>

fun exportGraphic() {
	val exportXmlVisitor = XMLExportVisitor()
	
	for (shape: Shape in allShapes) {
		shape.accept(exportXmlVisitor)
	}
}
```

Somit können einfach neue Shapes hinzugefügt werden, in weitere Formate exportiert werden, und es liegt kein Export-spezifischer Code in den Shapes.

Ablauf:
![[Visistor Ablauf.svg]]
## Anwendung
- wenn eine Operation auf alle Objekte einer komplexen Struktor (z.B. Baumstruktur) angewendet werden soll
- wenn Business-Logik von Zusatzfunktionen bereinigt werden soll
- wenn ein Verhalten nur in manchen Klassen einer Hierarchie sinnvoll ist, aber nicht im Rest

## Beziehungen
- [[Dimensional Class Hierarchies]] - explizite Referenz zu Hook wird im Visitor durch Argument im Funktionsaufruf ersetzt