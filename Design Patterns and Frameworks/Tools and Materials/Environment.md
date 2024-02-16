Initialisiert alles, zeigt alles an und wartet auf Tool-Start
![[Pasted image 20240216152700.png]]

## Tool Coordinator-Pattern
Tool Coordinator ist…
- ein globales Objekt, dass Tools und zugehörige Materials gruppiert (-> Tool-Material-Map und Tool Factory)
- ein Mediator zwischen FPs und anderen Tools
	- normalerweise kommunizieren FPs mit ihren Supertools und zugehörigen IPs
	- bauen Materials auf anderen Materials auf, müssen weitere Tools benachr. werden
	- TC verwendet Map um nötige Tools zu benachrichtigen

**Beispiel:** Excel mit Summe von Zellen (Aggregated Cell) - Merken welche Zellen von AggregatedCell referenziert werden - übernimmt ToolCoordinator
![[Pasted image 20240216153412.png]]

## Constrained Material Container-Pattern
- **Problem**: Materials hängen von einander ab (haben semantische Überschneidung)
- **Beispiel**: *CalendarTool* sollte Meetings als einzelne Daten erfassen, *MeetingScheduler* sollte Meetings blockieren wenn einzelne Daten im Kalender auftauschen
- **Lösung**: Materials, die von einander abhängen, in einen *Material Container* stecken; ein *constraint object* assoziieren dass die Abhängigkeiten aufrechterhält
-> Container kapselt Lese-/Schreibzugriff auf Materials
- CMC muss Mapping von ToolCoordinator abrufen, um verfügbare Tools zu kennen um nötige Constraints zu aktivieren -> *unschöne Abhängigkeit* :(