(Clone)
…ist ein Erzeugungsmuster, mit dem Sie vorhandene Objekte kopieren können, ohne Ihren Code von deren Klassen abhängig zu machen.

## Aufbau
![[Pasted image 20231126153654.png]]
- **Prototype** interface: deklariert Klon-Methoden, typischerweise eine `clone()`
- **Concrete Prototype**: implementiert Klonmethode(n), behandelt evtl. EdgeCases wie das Klonen verlinkter Objekte, Auflösen rekursiver Abhängigkeiten, etc.
- **Client**: kann eine Kopie jedes Objekts erzeugen, das dem Prototype-Interface genügt

## Beispiel
![[Pasted image 20231126153932.png]]

[auf refactoring.guru](https://refactoring.guru/design-patterns/prototype)
