…ist ein strukturelles Entwurfsmuster, mit dem Sie einen Ersatz oder Platzhalter für ein anderes Objekt bereitstellen können. Ein Proxy steuert den Zugriff auf das ursprüngliche Objekt und ermöglicht es Ihnen, etwas auszuführen, bevor oder nachdem die Anfrage an das ursprüngliche Objekt weitergeleitet wird.
Es ähnelt dem [[Decorator]], jedoch erweitert es flach, da es eine direkte Referenz auf den Service hat, nicht auf das Interface. Im Gegensatz zu [[Chain of Responsibility]] können Proxys daher nicht verkettet werden.

## Aufbau
![[Pasted image 20231126125014.png]]
- **Service Interface**: bestimmt Funktionen, die Proxy bereitstellen muss, um sich als Service auszugeben
- **Service**: Klasse, die eigentliche Business-Logik enthält
- **Proxy**: referenziert Service, nachdem Requests in der eigenen Logik verarbeitet wurden werden diese an Service weitergegeben, verwalten idR. Lifecycle ihres Service-Objekts
- **Client**: sollte mittels des Interfaces mit Service bzw. Proxy arbeiten, sodass jeder Service einfach durch einen Proxy ausgetauscht werden kann

## Beispiel
<small>Fehler auf refactoring.guru: Proxy hält Referenz zu Service, nicht zu Interface!!!</small>
![[Pasted image 20231126125403.png]]
```kotlin
class CachedYouTubeClass(svc: ThirdPartyYouTubeLib): ThirdPartyYouTubeLib() {
	private var service: ThirdPartyYouTubeLib = svc
	private var listCache = null
	var needReset: Boolean = false
	
	override fun listVideos() {
		if (listCache == null || needReset)
			listCache = service.listVideos()
		return listCache
	}
	
	...
}

class YouTubeManager(svc: ThirdPartyYouTubeLib) {
	protected var service: ThirdPartyYouTubeLib = svc
	
	fun renderListPanel() {
		list = service.listVideos()
		...
	}	
}

fun Application() {
	val aYouTubeService = ThirdPartyYouTubeClass()
	val aYouTubeProxy = CachedYouTubeClass(aYouTubeService)
	val manager = YouTubeManager(aYouTubeProxy) // Can take Service OR Proxy!
	manager.reactOnUserInput()
}
```


## Anwendung
- lazy initialization (großes Serviceobjekt was nur gelegentlich gebraucht wird) "_virtual proxy_"
- Zugriffskontrolle (nur best. Clients sollten ein Serviceobjekt verw. können) "_protection proxy_"
- Lokale Ausführung eines entfernten Services "_remote proxy_"
- Protokollierung der Anfragen an ein Serviceobjekt 
- Zwischenspeicherung/Caching der Anfrageresultate "_caching proxy_"
- Smart reference (großes Serviceobjekt löschen sobald kein Client mehr vorh.) "_filter proxy_"
- Indirection-/Facade Proxy (alle Referenzen zu Objekt zus.führen um austauschbar zu machen)

## Beziehungen
![[Proxy 2023-11-26 13.18.51.excalidraw|100%]]
