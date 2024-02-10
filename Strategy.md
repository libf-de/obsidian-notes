#GOF Variante von [[Template Class]], verwendet Rollen _Client_ und _Algorithm_

---
![[Pasted image 20231109132327.png]]
- Im Gegensatz zur [[Template Method]] wird der ganze Algorithmus ausgelagert.
- Im Gegensatz zur [[Template Class]] ist die **Intention** eine andere - Methoden/Algorithmen sollen in der _Template Class verdinglicht_ werden; bei **Strategy** sollen sie _austauschbar_ sein.

![[Pasted image 20231109132918.png]]
Client => Template Class
Strategy Class => Hook Class