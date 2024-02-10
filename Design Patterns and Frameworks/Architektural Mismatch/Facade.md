…ist ein strukturelles Entwurfsmuster, das ***eine* vereinfachte Schnittstelle** zu einer Bibliothek, einem Framework oder einem anderen **komplexen Satz von Klassen** bietet.

## Aufbau
![[Pasted image 20231129132338.png]]
- **Facade**: bietet einfachen Zugriff auf bestimmten Teil der Funktionalität des Subsystems, weiß wohin Client-Request geleitet werden muss und "wie alle beweglichen Teile zu bedienen sind"
- **Additional Facade**: kann verwendet werden um eine einzelne `Facade` nicht mit unverbundenen Features vollzustopfen die eine weitere Komplexstruktur bilden würden.
- **Complex Subsystem**: besteht aus etlichen Objekten - um damit etwas sinnvolles zu machen müsste man sich tief in die Implementierung einlesen (Objekte in richtiger Reihenfolge initialisieren, Daten im korrekten Format übergeben, ...). Kennt Existenz der `Facade` nicht, da diese direkt mit dem System zusammen arbeitet.
- **Client**: verwendet `Facade` statt Subsystem direkt selbst aufzurufen

## Beispiel
![[Pasted image 20231129133013.png]]
```kotlin
class VideoConverter { //<--- Facade here
	fun convert(filename: String, format: String): File {
		val vFile = VideoFile(filename)
		val sourceCodec = CodecFactory().extract(vFile)
		val destCodec = when(format) {
			"mp4" -> MPEG4CompressionCodec()
			else -> OggCompressionCodec()
		}
		val buffer = BitrateReader.read(filename, sourceCodec)
		var result = BitrateReader.convert(buffer, destCodec)
		result = AudioMixer().fix(result)
		return File(result)
	}
}

fun main() { //<--- verwendet Facade anstatt VideoFile, CodecFactory,...
	val convertor = VideoConverter()
	val mp4 = convertor.convert("funny-video.ogg", "mp4")
	mp4.save()
}
```

## Anwendung
- wenn ein begrenztes, aber einfach zu handhabendes Interface zu einem komplexen Subsystem gebraucht wird
- wenn ein Subsystem in Schichten strukturiert werden soll


## Beziehungen
- *Facade* definiert neues Interface, während [[Adapter]] existierende Interfaces nutzbar macht
- [[Abstract Factory]] ist eine Alternative wenn nur verborgen werden soll wie das Subsystem Objekte erstellt (die dann dem Client übergeben werden)
- *Facade* und [[7. Semester/Design Patterns and Frameworks/Extensibility Patterns/Flat Extension/Mediator]] haben ähnliche Aufgaben: Zusammenarbeit zwischen eng gekoppelten Klassen organisieren (Mediator zentralisiert Kommunikation zwischen Objekten, Subsystem kennt Existenz des Mediators)
- *Facade* und [[Proxy]] ähneln sich im Sinne dass beide ein komplexes Objekt selbst erstellen und dann vorhalten/zwischenspeichern. Proxy hat jedoch das gleiche Interface wie das Service-Objekt, was sie austauschbar macht.