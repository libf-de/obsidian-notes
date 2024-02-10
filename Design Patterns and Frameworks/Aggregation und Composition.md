![[Pasted image 20231124174601.png]]
```kotlin
class Client {
	val service: Service
}
```

Objekt `Client` enthält Objekt(e) `Service`,
- **Aggregation**: `Service` kann auch ohne `Client` existieren (schwache Verbindung)
- **Composition**: `Service` kann *nicht* ohne `Client` existieren, 
  `Client` verwaltet Lifecycle von `Service`  (starke Verbindung)

"Gegenspieler": [[Vererbung]]