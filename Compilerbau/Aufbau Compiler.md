Drei Phasen:
```mermaid
graph LR
Frontend--> |IR|Middle-End
Middle-End--> |IR|Backend
```
(IR=Intermediate representation; Ziel: $n * m$-Compiler mit $n+m$ Komponenten bauen)

## Frontend
- Gültiger Code --> IR, typischerweise target-unabhängig
- Komplexität $O(n) - O(n \log n)$

### Aufbau
```mermaid
graph LR
LA[Lexical<br>analysis]--> |Tokens|SA[Syntax<br>analysis]
SA--> |ST|SE[Semantic<br>analysis]
SE--> |ST|IR[IR-<br>generation]
IR--> DD[...]
```
- Lexical ([[Scanner]]): Mappt Zeichenstrom in Wörter (tokens)
- Syntax (parser): Erkennt _Sätze aus tokens_ einer Grammatik, erzeugt Syntax-Tree (ST)
- Semantic analysis: Fügt Informationen und Checks hinzu (Typen, Deklarationen,…)
- IR-Generierung: Abstrakte Repräsentation des Codes, geeigenet zur Codegeneration (z.B. ST)


## Middle-End
- Optimierung

### Aufbau
```mermaid
graph LR
DD[...]--> IR[IR-<br>generation]
IR--> |IR|IO[IR-<br>optimization]
```
- IR-Optimierung: Vereinfachungen und Verbesserungen (z.B. Redundanzen entfernen)


## Backend
- IR --> Target-Code (-> target-abhängig)
- Komplexität typ. NP-vollständig

```mermaid
graph LR
DD[...]--> |Optimized<br>IR|CS[Code<br>selection]
CS--> |IR|RA[Register<br>allocation]
RA--> |IR|SC[Scheduling]
SC--> |Machine<br>code|DO[...]
```
- Code selection: Welche Instruktionen sollen IR implementieren?
- Register allocation: In welchen Registern Variablen platzieren?
- Scheduling: Wann Instruktionen ausführen? (Ordnen des Assembly-Codes unter Berücksichtigungen der Schnittstellen und Einschränkungen)