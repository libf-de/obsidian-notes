Für das zur Nachricht $w$ gesendete Codewort $c(w)$ ist die resultierende Bitsequenz $y^{(n)}=(y_{1},y_{2},…,y_{n})$ am Empfänger aufgrund der zufälligen Übertragungsfehler eine Realisierung des Zufallsvektors $Y^{(n)}(c(w))$ und *unterscheidet sich in der Regel von* $\color{orange} c(w)$

=> Der Decodiervorgang besteht darin, die gesendete Nachricht $w$ möglichst optimal aus $y^{(n)}$ zu schätzen.

Wenn wir mit $\hat{w}$ die *decodierte Nachricht* bezeichnen, dann ist im vorliegenden Beispiel die folgende Mehrheitsentscheidung als Decodierregel plausibel. <small>(wir setzen eine ungerade Blocklänge n voraus)</small>

![[Pasted image 20230614094434.png]]
(d.h. wenn mehrheitlich eine $1$ empfangen wurde, dann ist die decodierte Nachricht gleich $2$, ansonsten gleich $1$)
-> [[Decodierfehler]] ^d79441