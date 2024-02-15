...ist ein strukturelles Entwurfsmuster, mit dem Sie *neue Verhaltensweisen* an Objekte *anhängen* können, indem Sie diese Objekte *in* speziellen *Wrapper-Objekten platzieren*, die die Verhaltensweisen enthalten (durch [[Aggregation und Composition|Aggregation oder Composition]]).
Ähnlich wie [[Composite]] in der Hinsicht, dass von einer abstrakten Klasse vererbt wird 
(`mimiced class` => Component, `mimicing class` => Decorator)

## Aufbau 
![[Pasted image 20231124180616.png]]
- **Component**: deklariert _gem. Interface_ für Wrapper und gewrappte Objekte
- **Concrete Component**: Klasse von Objekten die gewrappt wird, definiert _grundlegende Verhaltensweisen_, die von Decorators verändert werden können
- **Base Decorator**: _referenziert_ gewrapptes Objekt `wrappee` vom Typ `Component`; _delegiert_ alle Operationen an gewrapptes Objekt.
- **Concrete Decorators**: definieren _zusätzliches Verhalten_, was dynamisch zu Komponenten hinzugefügt werden kann. `override`_-t Methoden_ aus dem <tt>Base Decorator</tt> und führt _eigenes Verhalten_ vor oder nach Aufruf der Elternmethode aus.
- **Client**: kann `Component`s in (mehrere) Decorator wrappen, solange es mit allen Objekten nur über das `Component`-Interface arbeitet.

## Beispiel
![[Pasted image 20231124181439.png]]
```kotlin
open class DataSourceDecorator(source: DataSource) : DataSource() {
	val wrappee: DataSource = source

	fun writeData(daten: Data) {
		wrappee.writeData(daten)
	}
	…
}

class EncryptionDecorator(source: DataSource) : DataSourceDecorator(source) {
	override fun writeData(daten: Data) {
		val encryptedData = encrypt(daten)
		super.writeData(encryptedData)
	}
	…
}

fun DumbUsage() {
	var source = FileDataSource("output.dat")
	source.writeData(salaryRecords) // write plain data

	source = CompressionDecorator(source)
	source.writeData(salaryRecords) // write compressed data

	source = EncryptionDecorator(source) // Encryption->Compression->FileDataSrc
	source.writeData(salaryRecords) // write compressed and encrypted data
}

fun ConfiguratorUsage() { // Behavior can be altered at runtime
	var source = FileDataSource("output.dat")
	if(enabledCompression) {
		source = CompressionDecorator(source)
	}
	if(enabledEncryption) {
		source = EncryptionDecorator(source)
	}
}
```

## Anwendung
- wenn zur Laufzeit weiteres Verhalten zu Objekten hinzugefügt werden soll, ohne Code kaputt zu machen der diese Objekte verwendet
- wenn das Verhalten eines Objekts nicht (elegant) durch [[Vererbung]] erweitert werden kann,
  z.B. da dies durch `final` unterbunden ist.

[auf refactoring.guru](https://refactoring.guru/design-patterns/decorator)

## Role-based Design
![[Design Patterns als Role Models#Decorator]]