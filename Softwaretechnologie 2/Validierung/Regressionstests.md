kontinuierliches Wieder-Ausführen einer Test-Suite - ist durch die Änderung etwas kaputt gegangen?

-> z.B. mittels diff, im einfachsten Fall

## Coverage patterns
1. alles immer testen
2. risikoreiche use-cases
3. nur meist-ausgeführter Code
4. nur geänderter Code
5. nur geänderter Code und Code der darauf aufbaut/abhängt

## GUI-Tests
Capture-Replay-Tools - nehmen Benutzereingaben auf und spielen sie ab

## FIT-Testing-Framework
Framework um Unit Tests herum, die die Ausgabe für's Management verständlich macht

## Außerdem nötig...
- Trennung von Testdaten und Testcases
- Stubs (leere Implementierung der Class-Under-Test), Mocks (Dummy, der das Protokoll der Class-Under-Test implementiert/prüft)
