
| Hand-crafted |  | Mass-produced |  |
| ---- | ---- | ---- | ---- |
| **Pros** | **Cons** | **Pros** | **Cons** |
| exactly fit customers requirements | expensive | cheaper | "one size fits all" works for *most* customers |
| products are unique | slower production | faster production | get more than needed, reduces usability |
|  | higher chance of lower quality | improved quality due to standardization |  |
=> *Software Product Lines* zielt auf das Beste von beiden ab, indem:
- individuelle Produkte herleiten
- aus standardisierten Teilen
- basierend auf einer Konfiguration
-> Beispiel: Sandwich

**Hauptidee**: Entwicklung und Wartung von...
- ein Modell, das Gemeinsamkeiten und Variabilität der SPL abdeckt -> [[Feature Modelling]]
- eine Menge an wiederverwendbaren Kernkomponenten
- ein Konfigurationsplan
- ein Mechanismus um Produkte basierend auf einer gegebenen Konfiguration ableitet

## Software Product Line Engineering
![[Pasted image 20240210100608.png]]

- Problem Space -> enthält alle *anforderung*sbezogenen Artefakte
- Solution Space -> enthält alle *implementation*sbezogenen Artefakte
- Domain Engineering -> domainbezogene Tätigkeiten
- Application Engineering -> Tätigkeiten bezogen auf ein konkretes individuelles Produkt

**Probleme**:
- Modellierung und Variabilität behandeln
- Systematische Wiederverwendung von Softwareartefakten

## Flashcards

Was ist das Ziel von Software Product Lines? #flashcard #spl
Erzeugen individueller Produkte aus standardisierten Teilen basierend auf einer Konfiguration
- - -
In welche 4 Quadranten wird SPLE aufgeteilt und was enthalten sie? #flashcard #spl 
- Problem Space -> anforderungsbezogene Artefakte
- Solution Space -> implementationsbezogene Artefakte
- Domain Engineering -> domänebezogene Tätigkeiten
- Application Engineering -> Tätigkeiten bezogen auf konkretes Produkt