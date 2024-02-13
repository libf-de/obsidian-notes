> [!warning] Tupel $(P, T, F, W, m_0)$
> $$
\begin{align}
P \text{ … Places } \qquad & P \cap T = \not{0}\\
T \text{ … Transitions } \qquad \\
F \text{ … Flow Relations } \qquad & F \subseteq (P \times T) \cup (T \times P)\\
W \text{ … (Relation) Weight} \qquad & W:\;F \rightarrow \mathbb{N}_{0} \text{ wobei}\\
& W(p,t) = 0 \equiv (p,t) \not\in F,\; p \in P \text{ und } t \in T \text{ und} \\
& W(t,p) = 0 \equiv (t,p) \not\in F, p \in P \text{ und } t \in T\\
m_0 \text{ … Start Marking} \qquad & m_0:\; P \rightarrow \mathbb{N}_0
\end{align}
$$

![[Pasted image 20231207111245.png]]

## Marking m(p) und Weight W(f)
- Eine **marking** $m(p) \rightarrow \mathbb{N}_0,\; p \in P$ weist einem Place einen nicht-negativen Integer zu
	- Die *Anzahl an Tokens an einem Place*
- Ein **weight** $W(f) \rightarrow \mathbb{N}_0, \; f \in F$ weist einem Arc einen nicht-negativen Integer zu,
	- Wie viele *Token sie tragen* können
![[Pasted image 20231207111557.png]]

## Enabled
- Eine Transition $t \in T$ ist **enabled**, wenn:
	$m(p) - W(p,t) > 0, \forall p \in P$
(Wenn alle Places vor den eingehenden Arcs jeweils mindestens $n$ Token enthalten, 
wobei $n$ das Weight der eingehenden Arcs ist.)
![[Pasted image 20231207111828.png]]


## Firing
- Ist eine Transition *enabled*, **kann** sie feuern oder auch nicht
- Wenn eine Transition $t \in T$ **feuert**...
	- werden $N$ Token aus den eingehenden Places entfernt: $m(p) = m(p) - W(p,t),\; \forall p \in P$
	- werden $M$ Token zu den ausgehenden Places addiert: $m(p) = m(p) + W(t, p), \; \forall p \in P$
**Token werden konsumiert/generiert, sie "fließen" NICHT!**
![[firing-petrinets.png]]


## Arten von Petrinetzen
- **Petrinetz (PN)** ist ein *gerichteter*, *bipartiter Graph* mit 2 Knotenarten:
	1. Places (Kreise)
	2. Transitionen (Kästen)
- **Integer PN** ist ein *gerichteter*, *gewichteter*, *bipartiter Graph* mit Integer-Tokens
	- Places können mehrere Tokens enthalten
	- Places können eine Kapazität haben ($\text{bound} = k$)
	- $k$ Tokens in einem Place zeigen an dass $k$ Items verfügbar sind
- **Elementary PN** (boolean net, predicate/transition- oder condition/event-Netze)
	- Boolean-Tokens, ein Token pro Place ($\text{bound} = 1$)
	- Arcs haben *kein Gewicht*
	- Vorhandensein eines Tokens = Bedingung/Predicate ist $true$
	- *Feuern* einer Transition = aus den Eingabe- werden Ausgabe-Predicates gefolgert
- **High-Level PN** (Colored PN, CPN) erlaubt typisierte Places und Arcs
	- sind modular, Places und Transitions können refined werden
	- CPNs sind reduzierbare Graphen
	- obere Schichten eines reduzierbaren CPN = *channel agency nets* (Places werden als Kanäle zwischen Komponenten interpretiert)
	![[Pasted image 20231207113304.png]]

## Anwendung
- Verhaltens-Spezifizierung in UML (statt einer statechart/dataflow diagram/...); CPLs sind:
	- Modellierung paralleler Systeme natürlich
	- Kompakt und Modular, reduzierbar
	- geeignet für aspektorientierte Komposition, speziell parallele Protokolle
	- können verwendet werden um Code zu generieren
	- Beweisen von Eigenschaften:
		- **Liveness** (Netz feuert mindestens $n$ Mal)
		- **Fairness** (Alle Teile des Netzes sind gleich ausgelastet)
		- **K-boundedness**: Anzahl an Tokens die ein Place enthalten kann durch $k$ begrenzt
		- **Deadlock**: Netz kann nicht fortfahren, wurde nicht korrekt beendet
		- **Deadlock-freeness**: Netz enthält keine Deadlocks
- Verhaltensbeschreibung von Komponenten (-> Passen Komponenten zusammen?)
	- Problem: generelle Passform von Komponenten nicht entscheidbar
	- Lösung:
		- Verhalten zweier Komponenten mittels zwei CPNs beschreiben
		- Verbinden ihrer Ports
		- Liveness des verbundenen Netzes überprüfen -> nicht live = unpassend!


## Im Vergleich zu Automaten
**Petrinetze**
- Tokens stellen parallelen, verteilten, globalen State dar
- Können *verteilt* "geschalten" werden

**Automaten**
- *sequentiell*, ein globaler State ("ein Token"), können nur *zentral* "geschalten" werden

## Flashcards

Welchen Vorteil bietet ein Petrinetz gegenüber z.B. einem Automaten? #flashcard #petrinetze
In Petrinetzen sind Parallelismus und Synchronisierung modellierbar, während ein Automat sequenziell arbeitet und einen globalen Zustand hat.
- - -
Was passiert wenn in einem PN eine Transition feuert? #flashcard #petrinetze
Eine Transition kann dann feuern, wenn in *allen* eingehenden Places für das jeweilige Kantengewicht genügend Token vorhanden sind.
Feuert die Transition, werden entsprechend des jeweiligen eingehenden Kantengewichts Token aus den eingehenden Places entfernt und entsprechend der ausgehenden Kantengewichte Tokens in die ausgehenden Places platziert.
- - -
