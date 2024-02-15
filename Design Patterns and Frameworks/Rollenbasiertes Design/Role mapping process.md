- Klassen kombinieren [[Role types]] bzw. gruppieren Rollen zu Objekten.
- Klassenmodelle setzen sich aus [[Role model]]s zusammen.
- In unvollständigen Klassenmodellen können Role Types offen gelassen werden für weitere Composition

## Schritte
1. Role models erstellen (Rollen getrennt halten; Role constraints finden die beschränken welche Objekte welche Rollen ausführen)
2. Role models zusammenführen (und neue Constraints zwischen Rollen unterschiedlicher Modelle einführen)
3. Role models auf Klassendiagramm abbilden (indem Rollen zu Klassen zusammengeführt werden, unter Beachtung der Constraints)

Wie Constraints sich auswirken siehe [[Role constraints]]

## Implementation per Hand
![[Pasted image 20240214121537.png]]

### mit Interfaces
![[Pasted image 20240214122622.png|350]]
```java
public class Figure implements FigureHierarchy.Figure, FigureHierarchy.Child, ...
```

### mit Mehrfachvererbung
![[Pasted image 20240214122511.png|350]]
- 2 Klassenarten: Standard (muss erben von...) und Role Klassen
- Nachteil: Standardklasse kann nur 1x von Role-Klasse erben

### mit Mixin-Klassen
![[Pasted image 20240214122157.png|350]]
- Role Type ähnelt einer Mixin-Klasse (a superclass parameterizing a generic super declaration of a base class)
- Features eines Mixin werden umbenannt wenn es 2x vererbt wird
- Muss von Sprache unterstützt werden

### mit Delegation / Multi-Bridge / Role Object Pattern
![[Pasted image 20240214122452.png]]
- Role object stellt nur eine Role dar, eine Role-Klasse nur einen Role-Typ
- Ein Kernobjekt fasst alle Role-Objects zusammen






- mit Interfaces
- mit Mehrfachvererbung
- mit Mixin Classes
- mit Delegation / Role Object Pattern