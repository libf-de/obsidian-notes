## Verlustfreie Join-Operationen
Eine Join-Operation zwischen R und S heißt verlustfrei, wenn jeder Datensatz aus R und jeder Datensatz aus S in der Ergebnisrelation enthalten ist.
- Die inverse Operation Projektion erzeugt dann wieder R und S aus dem Join-Ergebnis  
- Tupel, denen bei Join-Operationen die entsprechenden Tupel in der anderen Tabelle fehlen, mit denen sie verknüpft werden können, heißen auch „Dangling Tupel“ bzw. Datensätze  
- Um sie in die Ergebnismenge mit aufnehmen zu können, werden die Outer-Join-Operatoren benötigt  
▪ Inner Joins sind in der Regel verlustbehaftet!

$$
\tiny \textifsym{d|><|d}
$$