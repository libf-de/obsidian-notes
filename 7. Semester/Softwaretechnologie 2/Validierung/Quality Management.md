![[Pasted image 20231211132456.png]]

#exam
Aufgebaut in
- konstruktiver Qualitätssicherung
	- von vornherein Fehler vermeiden (z.B. defensives Programmieren)
- analytische Qualitätssicherung
	- Fehler passieren -> Analysieren, Fehler finden + beheben

## Validierungs-/Verifikations-Techniken
(Abstraktion vom Code)
![[Pasted image 20231211132911.png]]
- Tracer -> Welche Funktion läuft wie lang?
- Review/Audit -> Artefakte, Doku werden an Dritte übergeben, nach vorgegebenen Richtlinien beurteilt
- Abstract Interpretation -> Code durchgehen mit Wertebereichen statt konkreten Werten, welche Pfade des Kontrollflusses werden abgedeckt? (immer, nie ausgeführt)
- Model checking -> versuchen Gegenbeispiele zu finden (dass Implementierung nicht Spezifikation entspricht); System wird in Zustandsautomat überführt+ausgeführt