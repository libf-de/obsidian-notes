## Structured Tool Pattern
- Strukturieren in Atomic tools, Composed Tools (mit Subtools), recursively composed tools ([[Composite]] pattern)
- Subtools werden zusammengesetzt, arbeiten auf ihren eigenen Materials oder auf dem gleichen wie Supertool mit weniger/einfacheren Rollen
- Rollenhierarchie öffnet Material-Features nur wie benötigt (gute Information Hiding)
![[Pasted image 20240216150849.png]]

## Separation of Function and Interaction
- Trennung in User Interface (mehrere IP) und Anwendungslogik (ein FP) (-> refined MVC)
- Functional Part (FP) - Bearbeitung des Materials, Zugriff auf M via [[TAM und Rollen|Material-Roles]]
- Interaction Part (IP) - reagiert auf Nutzereingaben, mögl. Modeless, ersetzbar ohne FP zu verändern
- Kopplung von IP/FP bspw. mit Observer:
![[Pasted image 20240216152102.png]]
- **Vertikale Tool-Decomposition** durch Strukturierung in Subtools mit Bridge, Composite,...
- **Horizontale Tool-Decomposition** in IP und FP

## Subtools erzeugen
![[Pasted image 20240216152354.png]]
0. Super-FP möchte neues Sub-FP erzeugen
1. Super-FP benachrichtigt Super-IP
2. Super-IP erzeugt ggf. ein/mehrere Sub-IP...
3. ...und verbindet sie als Observer mit Sub-FP