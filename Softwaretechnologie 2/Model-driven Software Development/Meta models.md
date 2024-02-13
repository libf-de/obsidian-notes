- "Meta" = beschreiben => **Metamodelle beschreiben Modelle** */ modellieren Sprache*
- Modelle eines Meta-Modells sind in der Sprache des Meta-Modells geschrieben
- 
- Sprache eines Metamodells ist ein Meta-Meta-Modell
- Da diese Sprache Sprachen beschreiben kann ist Meta-Meta-Modell höchstes Level
![[Pasted image 20240210110312.png]]

```
Die Metamodell-Pyramide, auch bekannt als die Vier-Ebenen-Metamodell-Hierarchie, ist ein Konzept aus dem Bereich der Modellierung und Softwareentwicklung. Sie wird verwendet, um verschiedene Abstraktionsebenen in der Modellierung von Daten, Systemen oder Softwarearchitekturen zu beschreiben. Diese Hierarchie hilft, die Beziehung zwischen realen Systemen, deren Modellierung und der Modellierungssprache selbst zu verstehen. Hier sind die vier Ebenen:

1. **M0-Ebene: Instanzebene (Objektebene)**  
    Auf der untersten Ebene befinden sich die konkreten Daten, Instanzen oder Objekte, die in der realen Welt oder in einem Softwaresystem existieren. Beispiele dafür könnten konkrete Kundenobjekte in einer Datenbank sein.
    
2. **M1-Ebene: Modellebene**  
    Auf dieser Ebene werden Modelle oder Schemata definiert, die die Struktur und das Verhalten der Instanzen auf der M0-Ebene beschreiben. Modelle auf der M1-Ebene folgen einer bestimmten Modellierungssprache oder einem Schema, um die Instanzen (M0) zu organisieren und zu definieren. Ein Beispiel wäre ein UML-Diagramm, das die Klassenstruktur eines Software-Systems abbildet.
    
3. **M2-Ebene: Metamodell-Ebene**  
    Die M2-Ebene definiert die Sprache oder das Schema, das verwendet wird, um die Modelle auf der M1-Ebene zu erstellen. Ein Metamodell beschreibt, wie Modelle konstruiert werden sollten, einschließlich der Elemente und Regeln, die verwendet werden können. Ein Beispiel hierfür ist die UML-Spezifikation selbst, die definiert, wie UML-Diagramme aufgebaut sein sollten.
    
4. **M3-Ebene: Meta-Metamodell-Ebene**  
    Auf der höchsten Ebene befindet sich das Meta-Metamodell, das die Struktur und Regeln definiert, nach denen Metamodelle (M2) gebildet werden. Diese Ebene bietet die grundlegendsten Konstrukte und Prinzipien, die für die Definition von Metamodellen benötigt werden. Ein oft zitiertes Beispiel auf dieser Ebene ist das MOF (Meta Object Facility), das ein Standard für die Definition von Metamodellen ist.
    

Diese Hierarchie ermöglicht es, eine klare Trennung zwischen den Daten (Instanzen), den Modellen, die diese Daten beschreiben, den Metamodellen, die die Modelle beschreiben, und den Meta-Metamodellen, die die Grundlage für die Metamodelle bilden, zu schaffen. Sie spielt eine wesentliche Rolle in der modellgetriebenen Entwicklung (Model-Driven Engineering, MDE), wo sie dazu dient, die Komplexität von Systemen zu reduzieren und die Wiederverwendbarkeit von Modellen und Metamodellen zu fördern.
```

## Modelle als Instanzen von Meta-Modellen
- typischerweise sind Modelle [[Grundlegende Graph-Klassen#Link Tree|Bäume mit überlagertem Graphen]]
- primäre Baumstruktur sammelt alle Definitionen (containment references)
- sekundärer Graph beschreibt Zusammenhänge, z.B. use-relations (non-containment ref.)

## Flashcards

Was sind Metamodelle? #flashcard #model-driven
- Metamodelle beschreiben Modelle/modellieren Sprache
- Sprache eines Metamodells ist ein Meta-Meta-Modell (höchstes Level)
---