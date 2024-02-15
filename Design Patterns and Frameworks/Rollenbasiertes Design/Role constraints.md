## role-use
![[Pasted image 20240214114559.png]]
a required role (links) uses a provided role (rechts)
=> Übersetzung als Delegation möglich (unterschiedliche Klassen)

## role-implication (a<b)
![[Pasted image 20240214114657.png]]
object that plays role a must also play role b
=> lässt Spielraum welche Klasse die Rolle implementiert: 
-> gleiche Klasse (effizienter, verhintert object schizophrenia) oder Subklasse (bessere Austauschbarkeit zur Laufzeit)

## role-prohibition
![[Pasted image 20240214114741.png]]
object that plays a must not play b
=> dürfen nicht in eine Klasse

## role-association
![[Pasted image 20240214114826.png]]
object that plays a knows an object playing b
=> ebenfalls Delegation?

## role-equivalence (a<>b)
![[Pasted image 20240214114912.png]]
object that plays role a must also play role b *and vice versa*
=> same implementation class

## role-implication inheritance constraint
![[Pasted image 20240214114949.png]]
role implication that also applies to subclasses of the roles
(a role-implication constraint, stressing that the source can be mapped to a subclass of the target)
=> Source muss auf Subklasse des Targets abgebildet werden