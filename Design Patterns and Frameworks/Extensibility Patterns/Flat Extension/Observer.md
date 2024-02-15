…ist ein Verhaltensmuster, mit dem Sie einen Subscription-Mechanismus definieren können, um mehrere Objekte über Ereignisse zu benachrichtigen, die mit dem Objekt, das sie beobachten, geschehen.

## Aufbau
![[Observer.svg|600]]
**Unterschied** zu [[Star-Bridge]]: Observer kennt Subject, Hierarchien sind nicht unabhängig

## Ablauf
![[Pasted image 20231126141327.png]]
- `update()` überträgt keine Daten, nur Event
- Observer selbst ruft Daten aus Subject ab -> für Subject egal wie viele Observer existieren

## Beispiel
![[Pasted image 20231126141644.png]]

## Anwendung
- wenn eine State-Änderung eines Objekts die Veränderung von anderen Objekten verlangt, und die tatsächliche Menge an Objekten im Voraus unbekannt/veränderlich ist
- wenn manche Objekte andere Objekte für begrenzte Zeit/in bestimmten Fällen überwachen müssen

## Beziehungen
Ähnlich wie folgende, im Sinne dass Sender und Empfänger auf verschiedene Weisen verbunden werden:
- [[Chain of Responsibility]] gibt Requests entlang einer dynamischen Kette möglicher Empfänger bis einer davon es verarbeitet
- [[Command]] baut unidirektionale Verbindung zwischen Sender und Empfänger auf
- [[7. Semester/Design Patterns and Frameworks/Extensibility Patterns/Flat Extension/Mediator]] zwingt Sender und Empfänger indirekt über Mediator-Objekt zu kommunizieren
- Observer ermöglicht Empfängern dynamisch De-/Abonnieren Requests zu empfangen

---
## Variante Push-Observer
![[Pasted image 20231126141548.png]]
![[Pasted image 20231126141609.png]]

---

## Role-based Design
![[Design Patterns als Role Models#Observer]]