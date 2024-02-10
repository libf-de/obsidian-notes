-Wahrscheinlichkeit

Für die Nachricht $w$ ist die decodierte Nachricht eine Funktion des Zufalls-  
vektors $Y^{(n)}(c(w))$ und damit selbst eine Zufallsgröße, die wir mit $\color{red}\hat{W}$ bezeichnen wollen.

Die Decodierfehler-$\mathbb{W}$ $\lambda^{(n)}(w)$ für Nachricht $w$ ist die $\mathbb{W}$ dafür, dass Nachricht $w$ mittels Codewort $c(w)$ gesendet wurde und nicht als Nachricht $w$ decodiert wurde:
$$
\lambda^{(n)}(w) = \mathbb{P}\Bigl(\hat{W} \neq w \; | \; X^{(n)}=c(w)\Bigr)
$$

Die maximale und die mittlere Decodierfehler-$\mathbb{W}$ eines Codier-Decodier-Schemas sind dann definiert durch
$$
\begin{align*}
\lambda^{(n)}_{\text{max}} = \underset{w \in \mathcal{W}}{\text{max}} \lambda^{(n)}(w)\\
\lambda^{(n)}_{\text{av}}=\frac{1}{|\mathcal{W}|} \sum\limits_{w \in \mathcal{W}} \lambda^{(n)}(w)
\end{align*}
$$

### Beispiel
In diesem Beispiel erhält man für das in [[Codierung#^2a8e06|Cod2]] und [[Decodierung#^d79441|Dec1]] verwendete Codier-Decodier-Schema für die Decodierfehler-$\mathbb{W}$en der Nachrichten $w=1$ und $w=2$:
![[Pasted image 20230614095415.png]]

- Wegen $Y_{k}(1)=1-Y_{k}(0)$ folgt in diesem Beispiel $\lambda^{(n)}(1)=\lambda^{(n)}(2)$ und daher auch $\lambda^{(n)}_\text{max} = \lambda^{(n)}_{\text{av}} = \lambda^{(n)}(1) = \lambda^{(n)}(2)$.

- Die Zufallsgrößen $Y_{1}(0),Y_{2}(0),…,Y_{n}(0)$ sind wegen [[Übertragungseinrichtung]] und [[Übertragungseinrichtung]] unabhängig und identisch Bernoulli-verteilt mit dem Parameter $\epsilon$. Daher ist die Summe $\sum^{n}_{k=1} Y_{k}(0)$ binomialverteilt mit den Parametern $(n,\epsilon)$.
- Für beliebige Blocklänge $n$ können wir die Decodierfehler-$\mathbb{W}$en wie folgt berechnen / nach oben abschätzen:
![[Pasted image 20230614095945.png]]
wobei $\gamma=(1-2 \epsilon)/(2 \epsilon)$. (Abschätzung mit [[Chernoff-Ungleichung]])
 ^6312bb
- Für $n=1$ erhalten wir ${\color{orange} \lambda^{(1)}(1)} = \mathbb{P}\left(Y_{1}(0) > \frac{1}{2}\right) = \mathbb{P}\bigl(Y_{1}(0)=1\bigr) \color{orange}= \epsilon$
- Bei der Codierung nach [[Codierung#Variante 1|Variante 1]] ist die Decodierfehler-$\mathbb{W}$ gleich der Bitfehler-$\mathbb{W}\; \epsilon$. Eine vollständig zuverlässige Nachrichtenübertragung ist damit also nicht möglich.

- Für $0 < \epsilon < \frac{1}{2}$ gilt in [[#^6312bb|oben]]: $\left(\frac{e^{\gamma}}{(1+\gamma)^{(1+\gamma)}}\right)^{\epsilon}< 1$
- Daraus folgt für den Wiederholungscode in [[Codierung#Variante 2|Variante 2]], dass für jedes $\delta > 0$ eine Blocklänge $n$ existiert, sodass gilt:
$$
\lambda^{(n)}_\text{max} < \left[\left(\frac{e^{\gamma}}{(1+\gamma)^{(1+\gamma)}}\right)^{\epsilon}\right]^{n} < \delta
$$
=> Die Decodierfehler-$\mathbb{W}$ kann durch Erhöhung der Blocklänge $n$ also beliebig verkleinert werden, trotz Störungen bei der Übertragung.