Ähnlich wie [[Template Method]], [[Objectifier]] und [[Strategy]], jedoch ist nun Rekursion in den Abhängigkeiten zwischen den Klassen erlaubt (über Vererbung und Aggregation)

- einfaches (Sub)Pattern, in dem eine *abstrakte Oberklasse* eine *gemeinsame Umgebung* für zweierlei Unterklassen (`Terminator` und `Recurser`) festlegt. Beide Arten können daher mittels des Interfaces der abstrakten Oberklasse *gleich behandelt* werden.

![[Pasted image 20231124165713.png]]

- Aggregation kann sein...
	- 1:1 (Listen, 1-Rekursion)
	- 1:* (Bäume, n-Rekursion)
	- \*:\* (DAGs oder Graphen, n-Rekursion)
![[Pasted image 20231124170115.png]]