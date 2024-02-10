> [!definition] Verifikation
Beweis dass die Implementierung der Spezifikation entspricht, mittels formalem/mathematischem Beweis

> [!definition] Validierung
 > Plausibilitätsprüfung von korrektem Verhalten
 > -> defensive programming, z.B. Reviews, (Unit-)Tests, Code Coverage Analysis
 

> [!example] Test
> Validierung des zu testenden Systems unter bekannten Umständen, mit dem Ziel Bugs zu finden
> => Testen zeigt nur Anwesenheit von Bugs, niemals ihre Abwesenheit

## TL;DR:
- Trennung von Produzent und Kontrolleur wichtig
- Defensive Programming ist gut
- Test-first-Entwicklung produziert stabile Produkte
- Ohne Regressionstests keine Qualität
- Mock-Klassen simulieren Class-Under-Test, verwirklichen ihr Lebenszyklus-Protokoll
- Test tools helfen Anwendungstests zu automatisieren


```ccard
type: folder_brief_live
```