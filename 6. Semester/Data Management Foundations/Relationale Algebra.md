#TODO Abschreiben, aufteilen

## Motivation
![[Pasted image 20230502114138.png]]
Formale Sprache für den Berechnungsweg von Anfrageergebnissen; Internrepräsentation für DB-Anfragen
- Mathematische Rechenregeln/Umformungen ermöglichen Abfrageoptimierungen
- **Grenzen**: Relationale Algebra enthält keine Operationen zum Erzeugen/Löschen von Relationen und Einfügen/Löschen/Verändern von Tupeln
- -> Es wird vorausgesetzt, dass Relationen/Tupel schon irgendwie existieren

## Algebra
- Gegeben Menge $N$: Menge der Relationen
- Operationen $op_{j}: \; N^{k} \rightarrow N$ (Abgeschlossenheit)

## Basisoperationen
- Gegeben 2 Relationen $R(A_{1},…,A_{r})$ und $S(B_{1},…,B_{s})$ mit Grad $r$ und $s$ dann sind
   $R' := {<op>}_{<Param>}(R)$ sowie
   $R'' := R {<op>}_{<Param>} S$
   wieder Relationen

### Projektion
![[Pasted image 20230502115008.png]]
#TODO abschreiben
- Wählt bestimmte Spalten aus Relation aus und gibt diese als neue Relation aus
- *Keine Duplikate auf relationaler-Algebra-Ebene*: Da Dubletten (identische Tupel) in Relationen nicht vorkommen dürfen, enthält die Projektion i.A. weniger Tupel als die ursprüngliche Relation - *ist in SQL standardmäßig nicht so!*

>[!example] Projektion in SQL: `SELECT`
>Ohne Duplikat-Elemination:
>```sql
SELECT Name, Ort FROM Studenten
>```
>Mit Duplikat-Elemination:
>```sql
SELECT DISTINCT Name, Ort FROM Studenten
>```


### Selektion (Restriktion)
![[Pasted image 20230502115247.png]]
- Wählt bestimmte Zeilen aus einer Relation aus und gibt diese als neue Relation aus

>[!example] Selektion in SQL: `SELECT` mit `WHERE`
>Selektion: $\sigma_{Name='Schmidt'}(Studenten)$
>```sql
SELECT * FROM Studenten WHERE Name='Schmidt'
>```
>
> Projektion+Selektion: $\pi_{Name,Vorname,Ort}(\sigma_{Name='Schmidt'}(Studenten))$
> ```sql
SELECT Name, Vorname, Ort FROM Studenten WHERE Name='Schmidt'
> ``` 


### Kartesisches Produkt
![[Pasted image 20230502115945.png]]

### Vereinigung
![[Pasted image 20230502120008.png]]

### Differenz
![[Pasted image 20230502120022.png]]

### (Umbenennen von Relationen und Attributen)
![[Pasted image 20230502120053.png]]

## Abgeleitete Operationen

### Durchschnitt
![[Pasted image 20230502121119.png]]

### Division
![[Pasted image 20230502121144.png]]
"Welche R-Tupel haben alle Ausprägungen aus der S-Relation?"
![[Pasted image 20230502121327.png|500]]
- Eingesetzt, wenn Frage "für alle" enthält (Welche Mitarbeiter arbeiten an *allen* Projekten?)

### Natürlicher Verbund
![[Pasted image 20230502121530.png]]
>[!example]- Beispiel
>![[Pasted image 20230502121651.png]]

### Theta-Join (Verbund)
![[Pasted image 20230502121756.png]]

### Equi-Join
Theta-Join mit $\Theta$ gleich "="
![[Pasted image 20230502122003.png]]
