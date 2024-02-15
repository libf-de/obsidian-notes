Wie [[Template Method]], jedoch...
- werden **alle** _abstrakten Schritte_ in separate `abstract HookClass` _ausgelagert_ von welcher die konkreten Implementierungen vererben. Die `TemplateClass` ist _nicht abstrakt_. 
- Hook-Objekte können _zur Laufzeit_ ausgetauscht werden
- Konsistenter Tausch mehrerer Methoden eines Algorithmus?

![[Template Class.drawio.png]]

## Beziehungen
Die Template Class ist Basis für...
- [[Bridge]]
- [[Builder]]
- [[Command]]
- [[Iterator]]
- [[Observer]]
- [[Prototype]]
- [[State]]
- [[Strategy]]
- [[Visitor]]

## Role-based Design
![[Design Patterns als Role Models#Template Class]]