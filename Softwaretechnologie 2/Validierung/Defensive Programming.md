- Fehler von vornherein vermeiden
- Assertions im Code plazieren (können für Release-Builds idR. vom Compiler entfernt werden)
- Pre-/Post-Condition, Invariante (muss immer gelten)
-  für  sauberen Code assertions in contract layer auslagern

### in Modellen
- Object Constraint Language -> UML-Diagramme
```java
context Person.paySalary(String name)
pre P1: salary >= 0 &&
	exists Company company: company.enrolled.name == name
post P2: salary = salary@pre + 100 &&
	exists Company company:
		company.enrolled.name == name &&
		company.budget = company.budget@pre - 100
```
- Epsilon (->Eclipse)

## Flashcards

Was ist defensives Programmieren? #flashcard #validation #swt2
- Fehler von Anfang an vermeiden durch Assertions im Code -> Stop bei Fehler
- Precondition, Invariant und Postcondition Checks => Contract Layer
- - -