## Erreichbarkeit von Markings
- Wenn $t$ in $M$ **aktiviert** ist: $M[t)$
- Ein Marking $M_n$ ist **erreichbar** von $M_0$ falls eine Firing-Sequenz $s$ existiert die $M_0$ zu $M_n$ transformiert: $M_0\; [s)\; M_n$
- Eine Firing-Sequenz ist Sequenz an Transitionen: 
	$s = M_0 \;[t1)\; M_1 \;[t2)\; M_2 ... [tn) M_n$   oder   $s=t1\; t2\; t3\; … \;tn$
- Menge aller von $M_0$ erreichbaren Markings: $R(M_0)$ 
	-> Spannt Reachability Graph/State-Automat auf
- Menge aller möglichen Firing-Sequenzen in einem Netz $(N,M_0)$: $L(M_0)$
	-> Sprache des Automaten $R(M_0)$
![[reachability-robots.png]]

## Boundedness und Sicherheit
- Ein Petrinetz $(N, M_0)$ ist ($k$-)**bounded**, wenn jeder Place auf $k$ Tokens größenbeschränkt ist:
	$M(p) \leq k$ für jeden Place $p$ und jedes Marking $M$ in $R(M_0)$
- Ein Petrinetz ist **sicher** wenn es 1-bounded ist.
(Bounded-Netze haben nur endlich viele States -> korrespondiert zu endlichem Automat)

- Markings eines States kann die Menge der verfügbaren Ressourcen darstellen (RAM, ...)
	-> Boundedness kann verwendet werden um zu beweisen dass ein System nur $k$ Resourcen verbraucht

## Liveness
### Petrinetz
Ein **Petrinetz** $(N,M_0)$ ist **live** wenn, egal welche Marking von $M_0$ erreicht wurde, wenn alle Transitionen live sind (=es möglich ist, jegliche weitere Transition des Netzes zu feuern mittels einer gewissen weiteren Firing-Sequenz).
### Transition
Liveness drückt aus, ob eine Transition aktiv bleibt oder nicht.
Eine Transition $t$ ist...
- **Tot (L0-live)**, falls $t$ niemals in irgendeiner Firing-Sequenz in $R(M_0)$ feuern kann
- **L1-live** (potentiell feuerbar), falls $t$ in mind. 1 Firing-Seq. in $R(M_0)$ feuern kann (=1x von SK)
- **L2-live** ($k$-feuerbar), falls $t$ mind. $k$-Mal von Startkonfiguration aus feuerbar ist.
- **L3-live** ($\infty$-feuerbar), falls $t$ unendlich oft von Startkonf. aus feuerbar ist.
- **L4-live** falls $t$ L1-live von jeder (auch unerreichbare) Marking $M$ in $R(M_0)$ ist
### Markings
- Ein Marking ist **tot** wenn keine der Transitionen aktiviert ist.
- Eine Marking ist **live** wenn keine erreichbare Marking tot ist (=alle Transitionen live)
- Ein *Netz* ist **live** falls $M_0$ live ist.
![[Pasted image 20231209120025.png]]
![[Pasted image 20231209120048.png]]

### …mittels Inzidenzmatrix
- Bounded Petrinetze lassen sich direkt auf Matrizen abbilden -> **Inzidenzmatrix**:
- PN mit $n$ Transitionen und $m$ Places --> $n \times m$-Integer-Matrix $A=[a_{ij}]$
	- **Zeilen = Transitionen, Spalten = Places**
- Kantengewichte: Eintrag in Matrix zeigt Effekt $a_{ij}$ auf Place $i$ durch *Addition* der *eingehenden* Tokens und *Subtraktion* der *ausgehenden* Token von Transition $j$:
	$a_{ij} = w(t_j, s_i) - w(s_i, t_j)$, wobei $w(t_j, s_i)$=eingeh. Gewicht, $w(s_i, t_j)$=ausgeh. Gewicht
- Transition $j$ ist aktiviert falls bei Marking $M$ gilt: $-a_{ij} \leq M(i),\; i = 1…m$
- Markings --> Vektoren
- Firing-Sequenzen --> (Firing-)Vektoren
- Matrix-Vektor-Multiplikation zeigt Einfluss des PN auf ein Marking
- Multiplizieren von Inzidenzmatrix mit Firing-Vektor ergibt neues Marking
![[Pasted image 20231209121145.png]]
$p_1$ verliert 2 an $t_1$, bekommt 1 von $t_2$ sowie $t_3$; $p_2$ verliert 1 an $t_2$, bekommt 1 von $t_1$, …

#### Firing Vectors
- Markierung $M_k$ wird als $m \times 1$-Spaltenvektor geschrieben; $j$-ter Eintrag von $M_k$ = Anzahl an Tokens im $j$-ten Place nach dem $k$-ten feuern
- Der Firing-Vektor $u_k$ ist ein $n \times 1$-Spaltenvektor aus $n-1$ Nullen und einem Nicht-0-Eintrag
	- 1 in der $i$-ten Position = Transition $i$ feuert beim $k$-ten feuern
- Die _recurrence_ der Inzidenzmatrix $A$ ist eine Matrixgleichung über Firing-Vektoren:
	$M_k=M_{k-1} + A^{T} u_k,\; k = 1,2,…$ -> Fasst alle erreichbaren States zusammen

### State-Gleichung
Sei $M_d$ erreichbar von $M_0$ mittels Firing-Sequenz $\{u_1,…,u_d\}$:
Die State-Gleichung um $M_d$ von $M_0$ zu bestimmen ist: $M_d = M_0 + A^T \sum\limits^{d}_{k=1} u_k$
Alternativ: $A^T x = \Delta M$,  $\Delta M = M_d - M_0$ und $x…n \times 1$-Spaltenvektor (Firing Count Vektor):
	$x = \sum\limits_{k=1}^d u_k$
-  $i$-ter Eintrag von $x$ kennzeichnet wie oft Transition $i$ feuern muss um $M_0$ zu $M_d$ zu transf.
- charakterisiert eine Firing Sequence
![[Pasted image 20231209135904.png]]

### Invarianten
>[!information] Transitions-Invariant
>Ist die transponierte Inzidenzmatrix gleich 0 ($A^T x = 0$) -> T(ransitions)-Invariant
> - Firing-Vektor transformiert eine Marking zu sich selbst.
> - Firing-Reihenfolge nicht spezifiziert, aber Anzahl an Firings.

> [!example] State-Invariant
> Ist die Inzidenzmatrix gleich 0 ($A y = 0$) nennt man dies S(tate)-Invariant
> 

- Ein invarianter Vektor $y$ ist *minimal*, falls es keine andere Invariante $y_1$ gibt für die gilt:
	$y_1(p) \leq y(p) \; \forall p$
- **Theorem:** ein $n$-Vektor $x > 0$ ist eine T-Invariante gdw. es eine Marking $M_0$ gibt, sodass ihre Firing-Sequence $\sigma$ von $M_0$ zurück zu $M_0$ führt.

=> Überprüfungs-Prozedur um Liveness eines Petrinetzes zu prüfen:
- **Switch-Vektor**: Summe alle minimalen T-Invarianten
- Berechne minimale T-Invarianten durch elementares Null-Setzen
- Überprüfe dass der Switch-Vektor keine Null-Einträge hat
- Baue den Erreichbarkeits-Graphen und überprüfe ob die Start-Markierung $M_0$ von allen erreichbaren Konfigurationen erreichbar ist.

**Sinn**: Überprüfen ob zwei Komponenten zusammenpassen ([[Grundlagen Petrinetze]] -> Anwendung)
