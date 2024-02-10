#5-3-1
## Annahmen
- Die Übertragung von Symbolen über den Kanal erfolgt mit einem festen Takt, d. h. sie ist zeitdiskret.  
- Die Menge der Sende- und Empfangssymbole ist endlich, d. h. die Übertragung ist wertdiskret.  
- Der Kanal modelliert zufällige Störungen bei der Übertragung, d. h. der Zusammenhang zwischen Kanaleingang und -ausgang ist stochastisch.

## Diskreter Kanal
- Die endlichen Mengen
$$
\mathcal{X}=\{a_{1}, a_{2},…,a_{l}\} \quad \text{und} \quad \mathcal{Y}=\{b_{1},b_{2},…,b_{m}\}
$$
   möglicher Sende- und Empfangssymbole bezeichnen wir als *Eingangs- und Ausgangsalphabet*.
- Für Symbolsequenzen der Länge $n$
$$
x^{(n)} = (x_{1},x_{2},…,x_{n})\quad \text{und} \quad y^{(n)} = (y_{1},y_{2},…,y_{n})
$$
   am Kanaleingang und -ausgang gilt entsprechend $x^{(n)} \in \mathcal{X}^{n}$ und $y^{(n)} \in \mathcal{Y}^{n}$
- Wie bereits in [[Informationstheorie/Kanalkodierung/Grundbegriffe/Grundbegriffe|Grundbegriffe]] eingeführt, modellieren die Zufallsvektoren
$$
X^{(n)} = (X_{1}, X_{2}, …, X_{n}) \quad \text{und} \quad Y^{(n)} = (Y_{1}, Y_{2}, …, Y_{n})
$$
   mit den Alphabeten $\mathcal{X}^{n}$ und $\mathcal{Y}^{n}$ sowie den $\mathbb{W}$-Funktionen $p_{X}^{(n)}$ und $p_{Y}^{(n)}$ das _zufällige Auftreten von Symbolsequenzen_ der Länge $n$ am Kanaleingang und -ausgang und für jedes $x^{(n)} \in \mathcal{X}^{n}$ beschreibt der Zufallsvektor
$$Y^{(n)}\Bigl(x^{(n)}\Bigr)$$
   die _zufällige Kanalausgabe bei fester Kanaleingabe_.
- Die Menge der $\mathbb{W}$-Funktionen des Zufallsvektors $Y^{(n)}\bigl(x^{(n)}\bigr)$ für alle $x^{(n)} \in \mathcal{X}^{n}$ bzw. äquivalent dazu die _bedingte W-Funktion von_  $\color{orange} Y^{(n)}$ _gegeben_ $\color{orange}X^{(n)}$
$$p^{(n)}_{Y|X} = \Bigl\{ p^{(n)}_{Y|X} (\cdot|x^{(n)}),x^{(n)}\in \mathcal{X}^{n} \Bigr\}$$
   bezeichnen wir als _diskreten Kanal für Sequenzen der Länge_ $\color{orange} n$
 ^6f4d94
- Die Menge $\mathcal{K} = \Bigl\{p_{Y|X}^{(n)}, n \in \mathbb{N} \Bigr\}$ _aller_ diskreten Kanäle mit fester Blocklänge $n$ bezeichnen wir als _diskreten Kanal_
	- Der definierte diskrete Kanal modelliert ganz allgemein die zeidiskrete und wertdiskrete Übertragung von Symbolen mit zufälligen Störungen.
	- Dieses allgemeine Modell schließt sowohl zeitvariante als auch   gedächtnisbehaftete Kanäle mit ein.
	- Im Folgenden wollen wir uns auf den zeitinvarianten, gedächtnislosen   Spezialfall beschränken.
