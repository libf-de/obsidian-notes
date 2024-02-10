#VL2

Daten als Datenstrom (Sequenz von _Symbolen_) auffassen, _Symbole_ werden digital durch Bits repräsentiert.

Relevant für Datenkompression sind _Häufigkeiten_ verwendeter Symbole und -ketten sowie _Abhängigkeiten_ d. Symbole untereinander

**Ansatz**: Daten durch stochastisches Modell repräsentieren
=> Modell bildet nicht reale Daten ab, sondern wesentliche, für Datenkompression relevante Aspekte

### Mathematisches Modell
- Menge möglicher Symbole **=** Alphabet einer Zufallsgröße
- rel. Häufigkeit eines Symbols **=** $\mathbb{W}$ für Ereignis, dass ZG = Symbol
- Erzeugung eines Symbols **=** einmaliges Zufallsexperiment, durch ZG beschrieben
- Erzeugung Symbolfolge **=** mehrere Zuf.Exp., durch ZG-Folge beschrieben

> [!info]- Beispiel
-> Datenmenge aus 10000 Zeichen binär abspeichern
>
> #### Variante 1
> Kanonische Binärdarstellung (1 = `00`, 2 = `01`, 3 = `10`, 4 = `11`,...)
> -> 20000 Bit total, 2 Bit/Zeichen
>
> #### Variante 2
> Häufige Zeichen durch kurze Codewörter und seltene Zeichen durch lange Codewörter repräsentieren (1 = `0`, 2 = `10`, 3 = `110`, 4 = `111`,…)
> -> 17500 Bit total, 1,75Bit/Zeichen

