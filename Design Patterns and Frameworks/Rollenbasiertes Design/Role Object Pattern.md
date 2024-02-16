![[Pasted image 20240216104104.png]]

Client arbeitet lediglich mit Core, um [[Object Schizophrenia]] zu beheben. Core delegiert Aufrufe zu und verwaltet Roles. Rollen werden als Kindklassen von ComponentRole implementiert.

## Varianten
### Deep Roles
Rollen können weitere Rollen spielen / verschachtelt werden
![[Pasted image 20240216121202.png]]

### Flat Roles
Rollen können keine anderen Rollen spielen
![[Pasted image 20240216121244.png]]

### Traded Call
![[Pasted image 20240216121310.png]]
Anfrage wie "gibt es eine Rolle die X bereitstellt" -> Trader sucht passende Rolle

