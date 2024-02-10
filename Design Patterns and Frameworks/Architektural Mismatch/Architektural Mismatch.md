## Ursachen
unterschiedliche Annahmen über....
- das **Component Model** (Infrastruktur, Kontrollmodell, Datenmodell)
	- trägt Informationen und Constraints über Charakter der Komponenten zusammen (Charakter der *Interfaces*, *Austauschbarkeit* der Komponenten)
	- Komponenten nehmen eine bestimmte Infrastruktur an -> nicht unbedingt verfügbar (Annahme Ausführung auf Windows-Infrastruktur, andere nimmt Linux an, etc.)
	- **Kontrollmodell**: Komponenten haben unterschiedliche Vorstellung "wer" die Hauptkontrolle hat; mehrere Komponenten können eine ständig lfd. Event-Loop haben
	  ![[Pasted image 20231129122853.png|200]]
	- **Datenmodell**: Unterschiedliche Strukturierung der Daten
	  ![[Pasted image 20231129123155.png|200]]
- die **Konnektoren** (Protokolle, Datenmodelle)
	- **Protokolle**: manche Tools arbeiten asynchron -> legt Werkzeugen Concurrency auf, wenn sich Nachrichten verschiedener Tools kreuzen
	  ![[Pasted image 20231129123451.png]]
	  - **Datenformat**: unterschiedliche Annahmen was über Channel gesendet wird (Strings, C data, C++ data, ...) -> Übersetzung nötig, kann Bottleneck werden!
- die **globale Architektur-Struktur**
	- datenbankorientierte Architektur (repository style, SSOT)
	  VERSUS
	- shared-nothing-Architektur (wer neuste Daten hat muss herausgefunden werden)
- den **Konstruktionsprozess**
	- library infrastructure, generic language (C++), Toolspezifische Sprachen

## Lösungsansätze
- Alle Architektur-Annahmen explizit machen (-> modellieren)
	- Problem: Wie dokumentieren/spezifizieren? -> viele obrige Probleme nicht formalisiert
- Komponenten unabhängig voneinander machen
- Verbindungstechniken anbieten um Sprachübersetzungs-Komponenten zu erstellen (compiler construction, compiler generators, XML, ...)
- Explizite Unterscheidung von Architektur-Patterns (-> explizite Konnektoren)
- *Lösung*: Design Patterns dienen all diesen Zwecken

> [!summary] Zusammenfassung
> - Architektur-Mismatch zwischen Komponenten und Tools besteht aus unterschiedlichen Annahmen über Komponenten, Verbindungen, Architekturen und Building-Prozedur
> - Extensibility- und Kommunikationspattern können solche Mismatches überbrücken
> - Mit Glue-Patterns verbessert sich die Wiederverwendung erheblich


```ccard
type: folder_brief_live
```
 
