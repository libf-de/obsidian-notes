*Role Models erfassen Absicht (intent) von Design Patterns (siehe [[#Template Class]])*

## Überlagerung
Überlagerung von [[#Observer]] und [[Composite]] mittels Role equivalence:
![[Pasted image 20240214125201.png]]


## Observer
![[Pasted image 20240214124437.png]]
[[Observer#Aufbau|Pattern]]

## Event Notification
![[Pasted image 20240214124524.png]]

## Chain of Responsibility
![[Pasted image 20240214124631.png]]
[[Chain of Responsibility#Aufbau|Pattern]]

## Composite
![[Pasted image 20240214124724.png]]
(Root role nicht in GOF) -> [[Composite#Aufbau|Pattern]]

## Adapter
![[Pasted image 20240214124851.png]]
#todo object/class adapter
[[Adapter|Pattern]]

## Decorator
![[Pasted image 20240214124948.png]]
 [[Decorator#Aufbau|Pattern]]

## Mediator
![[Pasted image 20240214125004.png]]
[[Mediator#Aufbau|Pattern]]

---
## Derived Method
- *kernel method* - implements feature directly on attributes, calls no other method
- *derived method* - implements by calling only kernel methods
- Caller and callee role have to be bound to the same class (as the purpose is to have class-internal method calls)
![[Pasted image 20240214125740.png]]

## Template Method
![[Pasted image 20240214125928.png]]
- Vererbungshierarchie im Hook rechts (durch [[Role constraints#role-implication inheritance constraint|role-implication inheritance constraint]])
- Template-Role impliziert keine Vererbungshierarchie links
[[Template Method#Aufbau|Pattern]]

---
## Objectifier
![[Pasted image 20240214130257.png]]
[[Objectifier|Pattern]]
## Strategy
![[Pasted image 20240214130344.png]]
[[Strategy|Pattern]]

## Template Class
![[Pasted image 20240214130545.png]]
- HookM impliziert Vererbungshierarchie rechts
- keine Client/Algorithm-Role, sonst Strategy
[[Template Class|Pattern]]

## Dimensional Class Hierarchies
![[Pasted image 20240214130820.png]]
-> Template Class mit Vererbungshierarchie-Constraint links
[[Dimensional Class Hierarchies|Pattern]]
## Bridge
![[Pasted image 20240214130927.png]]
-> DimHier. mit Abstraction/Implementation statt Template/Hook
[[Bridge#Lösung|Pattern]]

---
## Factory Method
![[Pasted image 20240214131054.png]]
-> Template Method mit einem creational role model
[[Factory Method#Aufbau|Pattern]]

---
## Optimierung von Patterns
am Beispiel von MVC - ursprünglich fast alle Rollen in separaten Klassen
![[Pasted image 20240214131745.png]]
Model und Controller zusammenführen; Strategy durch TemplateMethod ersetzen:
![[Pasted image 20240214131910.png]]
