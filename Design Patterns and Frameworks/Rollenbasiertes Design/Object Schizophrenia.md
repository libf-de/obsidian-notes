![[Pasted image 20240216103600.png]]

Tritt auf, wenn ein konzeptuelles Objekt in mehrere Teile aufgespalten wird, da dann die Identität des Objekts auf mehrere Objekte verteilt wird. Somit ist auch unklar, wer den State des zusammengesetzten Objekts verwaltet.

Im [[Role Object Pattern]] wird dies gelöst, indem der Client ausschließlich mit dem Core-Objekt kommuniziert, welches die Aufrufe dann an die entsprechenden Rollen delegiert.