## Asymptotische Größen
### Entropierate (2.8.1)
$$
\overline{H}(X)=\underset{n \rightarrow \infty}{\lim} \frac{H(X_{1},X_{2},…,X_{n})}{n}
$$
…nennen wir *Entropierate* der Folge $X=(X_{k})_{k \in \mathbb{N}}$ diskreter ZG, sofern der Grenzwert existiert.
>[!information] Bemerkung
>Die Entropierate ist u. a. eine untere Schranke für die (asymptotisch) verlustlose, "blockweise" Datenkompression, speziell bei gedächtnisbehafteten Modellen.

#### Entropierate einer stationären gedächtnislosen Quelle
$$
\begin{align*}
H(X_{1},X_{2},…,X_{n})&= \sum\limits_{k=1}^{n}H(X_{k})\\\\

\text{Wegen Stationärität sind alle } X_{k} &
 \text{ identisch verteilt, sodass gilt:}\\
H(X_{1})=H(X_{2})&=…=H(X_{n})\\\\

\text{Damit erhalten wir:}\\
H(X_{1},X_{2},…,X_{n}) &= n H(X_{1})\\\\

\text{Und für die Entropierate:}\\
\overline{H}(X) = \underset{n \rightarrow \infty}{\lim} \frac{H(X_{1},X_{2},…,X_{n})}{n} &= \underset{n \rightarrow \infty}{\lim} \frac{nH(X_{1})}{n}=H(X_{1}).
\end{align*}
$$

#### Entropierate einer stationären Markow-Quelle
$$
\begin{align*}
H(X_{1},X_{2},…,X_{n}) &\overset{2.7.1}{=} \sum\limits_{k=1}^{n} H(X_{k}|X_{k-1},\underline{X_{k-2},…,X_{1}}) \overset{*}{=}\sum\limits_{k=1}^{n}H(X_{k}|X_{k-1})\\
\\
\text{Wir erhalten }* &\text{ aufgrund der Markowketten-Eigenschaft wie folgt:}
\end{align*}
$$


### Transinformationsrate (2.8.2)
$$
\overline{I}(X;Y) = \underset{n \rightarrow \infty}{\lim} \frac{I(X_{1},X_{2},…,X_{n})}{n}
$$
…nennen wir *Transinformationsrate* der Folgen $X=(X_{k})_{k \in \mathbb{N}}$ & $Y=(Y_{k})_{k \in \mathbb{N}}$ diskr. ZG, sofern GW ex.

