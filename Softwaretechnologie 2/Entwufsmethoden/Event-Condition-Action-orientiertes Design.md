=> [[Architekturstile#Event-basierter Architekturstil|Event-basierter]], [[Architekturstile#Workflow-basierte Systeme|Workflow-basierter]] oder [[Architekturstile#Communicating State Machines|Communicating State Machines]] Architekturstil

- Event-Condition-Action-Regeln bestimmen System (auf welches Ereignis unter welchen Bedingungen folgt welche Aktion?)

**Verwendung** wenn das System ein Zustandssystem ist, in welchem Aktionen die Zustandsübergänge bilden und die Aktionen von (externen) Ereignissen ausgelöst werden.

**Unterscheidung zu [[Aktionsorientierter Entwurf]]**:
- Aktionsorientierter Entwurf wenn System nach Start geregelten, schrittweisen Ablauf hat
- ECA, wenn System zufällige, unregelmäßige Start"impulse" hat (z.B. Smarthome Lichtschalter, ...)
