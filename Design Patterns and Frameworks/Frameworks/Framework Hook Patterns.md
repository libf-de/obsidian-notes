[[Plugins and Extensions Points|Framework variation point]] wird charakterisiert durch T&H metapattern/role model:
![[Pasted image 20240216105232.png]]


■ = black-box
▨ = gray-box
□ = white-box

## Delegation/Aggregation
### 1-T--H (aggregated open role hook) ■
(**H** Teil von **T**; **T** ist core class eines komplexen Objekts)
![[Pasted image 20240216105642.png]]
-> [[Template Class]], [[Dimensional Class Hierarchies]]

### n-T--H (flat extension) ■
(**T** hat *n* **H**-Teile, *n* ist dynamisch; basiert auf [[Star-Bridge]])
![[Pasted image 20240216105841.png]]
-> [[Dimensional Class Hierarchies]], [[Observer]]

## Inheritance
"The object of a plugin (of subclass) replaces the object of the framework (of superclass)"
### H<T □
(**H** erbt von **T**)
![[Pasted image 20240216111923.png]]
-> [[Template Method]]



## Recursion
### 1-H<=T (deep list extension) (▨)
(**T** Teil von **H**, **H** erbt von **T**)
![[Pasted image 20240216110232.png]]
-> [[Decorator]], [[Role Object Pattern]]

### n-H<=T (deep graph extension) (▨)
(**H** hat *n* **T**-Teile, **H** erbt von **T**)
![[Pasted image 20240216110414.png]]
-> [[Composite]], ([[Decorator]]?)

## Unification
"Unification Hooks replace a framework object by a plugin object"

### TH (□)
(**T** == **H**, **TH** Teil von **TH**)
![[Pasted image 20240216110811.png]]

### 1-TH (deep list extension) (▨)
(**T** == **H**, **TH** Teil von **TH**)
![[Pasted image 20240216111314.png|350]]
-> [[Chain of Responsibility]], [[Decorator]]

### n-TH (deep tree extension) (▨)
(**T** == **H**, **TH** hat *n* **TH**-Teile)
![[Pasted image 20240216111459.png]]
-> [[Composite]]

## Extension Object Pattern
### 1-H=T (▨)
(**T** hat 1 **H**-Teil, **T** besitzt **H**)
![[Pasted image 20240216112828.png]]

### n-H=T (▨)
(**T** hat *n* **H**-Teile, **T** besitzt **H**-Teile)
![[Pasted image 20240216112851.png]]

## Layer Pattern
### n-TrH (▨)
(**T2** hat **H**-Teile, **H** und **T2** erben von **T1**, **H** kennt **T1**)
![[Pasted image 20240216113109.png]]