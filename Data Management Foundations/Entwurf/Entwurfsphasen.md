## Konzeptuelles Schema
[[Entity-Relationship-Modell]]
![[Pasted image 20230418112718.png]]

## Logisches Schema
(Relational)
```c
Student(MatrikelNr, Name)
Vorlesungsbesucher(MatrikelNr, VorlNr)
Vorlesung(VorlNr, Titel)
```

## Physisches Schema
```sql
CREATE TABLE Student(
MatrikelNr INT PRIMARY KEY,
Name VARCHAR(30) NOT NULL)
ENGINE = InnoDB

CREATE INDEX Student_Name_Idx ON Studenten(Name);

CREATE TABLE Vorlesung…

CREATE TABLE Vorlesungsbesucher
```