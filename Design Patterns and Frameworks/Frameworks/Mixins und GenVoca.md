Ein Mixin ist eine unvollständige Klasse zur Erweiterung einer anderen Klasse.
Sie können zur Umsetzung von (statischen) [[Design Patterns and Frameworks/Rollenbasiertes Design/Role|Rollen]] und Facets verwendet werden.

```c++
template <class S>
class EmployeeMixin extends S {
	Salary salary;
	Employer emp;
}

EmployeeMixin<Person> employeeOfPerson;
```

## GenVoca
Durch die Verschachtelung von Mixin-Parametrisierungen entsteht GenVoca:
```c++
template <class S> class ParentMixin extends S {
Child child;
Money kindergeld;
}
template <class S> class HobbyMixin extends S {
Hobby hobby;
}

HobbyMixin<ParentMixin<Person>>> assmann;
ParentMixin<HobbyMixin<Person>>> assmann2;
// Reihenfolge ist wichtig; assmann != assmann2
```

## GenVoca Variations
Existieren verschiedene Varianten einer *Abstraktionsschicht* drücken Parametrisierungen Konfigurationen einer Produktlinie aus:
![[Pasted image 20240216115039.png]]

## Mixin Layers
(GenVoca kümmert sich um Stapeln von Parametrisierungen; MixinLayer gruppiert alle Rollen einer Abstraktionsschicht zusammen und bildet ganze Schichten)
![[Pasted image 20240216120500.png]]
![[Pasted image 20240216120353.png]]
MixinLayers ermöglichen konsequenten Austausch von ganzen Schichten und somit ihren zugehörigen Rollen: 
```c++
WorkAsHobby<Deliberate<FatherLayer<FullTime>>>> assmann;
```

