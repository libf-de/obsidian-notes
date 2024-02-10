## 2.3.1) Kettenregel für Entropie
[[Shannonsche Informationsmaße#Entropie]]
![[Pasted image 20230420101117.png]]

##### Herleitung 2.3.1
> [!inf]- Spoiler
> $$\begin{align*}
H(X,Y)&\overset{\overset{\text{Darst. als }\mathbb{E}\text{-Wert}}{\downarrow}}{=}-\mathbb{E}(\log_{2}(p_{X,Y}(X,Y)))\\
&\overset{\overset{p_{X,Y}(X,Y)=p_{X}(X)\cdot p_{Y|X}(Y|X)}{\downarrow}}{=} -\mathbb{E}(\log_{2}(p_{X}(X) \cdot p_{Y|X}(Y|X)))\\
&\overset{\overset{\log_{2}(a\cdot b)=\log_{2}a+\log_{2}b}{\downarrow}}{=} -\mathbb{E}(\log_{2}(p_{X}(X)))-\mathbb{E}(\log_{2}(p_{Y|X} (Y|X) ))\\
&\overset{\overset{\mathbb{E}(U+V)=\mathbb{E}(U)+\mathbb{E}(V)}{\downarrow}}{=} H(X) + H(Y|X)\\
\end{align*}$$
> Analog erhält man $H(X,Y)=H(X|Y)$ durch Vertauschen von $X$ und $Y$ in vorhergehender Herleitung.


## 2.3.2) Kettenregel für bedingte Entropie
[[Shannonsche Informationsmaße#bedingte Entropie]]
![[Pasted image 20230420101149.png]]

##### Herleitung 2.3.2
>[!inf]- Herleitung
>Analog zu [[#Herleitung 2.3.1]], mit Ersetzung:
$p_{X,Y} \Rightarrow p_{X,Y|Z}$
$p_{X} \Rightarrow p_{X|Z}$
$p_{Y|X} \Rightarrow p_{Y|X,Z}$
(also überall $|z$ hinzufügen?)

## 2.3.3) Transinformation und (bedingte) Entropie
![[Pasted image 20230420101615.png]]
($V…$ weitere diskrete ZG mit endlichem Alphabat)
##### Herleitung 2.3.3
> [!inf]- Spoiler
> $$\begin{align*}
I(X;Y) &\overset{\overset{(2.1.5)}{\downarrow}}{=} \mathbb{E}\left(\log_{2}\frac{p_{X,Y}(X,Y)}{p_{X}(X)\cdot p_{Y}(Y)}\right)\\
&\overset{\overset{\text{Log-Gesetze}}{\downarrow}}{=} \underbrace{\mathbb{E}(\log_{2}(p_{X,Y}(X,Y)))}_{-H(X,Y)} \underbrace{-\mathbb{E}(\log_{2}(p_{X}(X)))}_{H(X)} \underbrace{-\mathbb{E}(\log_{2}(p_{Y}(Y)))}_{H(Y)}\\
&\overset{\overset{(2.1.5)}{\downarrow}}{=}-H(X,Y)+H(X)+H(Y)\\
\\
H(X;Y)&= H(X,Y)+H(X)+H(Y)\\
&\overset{\overset{(2.1.3)}{\downarrow}}{=}-(H(X)+H(Y|X))+H(X)+H(Y)\\
&= H(Y) - H(Y|X)\\
\\
H(X;Y) &= -(H(Y)+H(X|Y))+H(X)+H(Y)\\
&\overset{\overset{(2.1.3)}{\downarrow}}{=} H(X)-H(X|Y)
\end{align*}$$

## 2.3.4) Bedingte Transinformation und bedingte Entropie
![[Pasted image 20230420103128.png]]

##### Herleitung 2.3.4
> [!inf]- Spoiler
> Analog zu [[#Herleitung 2.3.3]] mit Ersetzungen
> $p_{X,Y} \Rightarrow p_{X,Y|Z}$
> $p_{X} \Rightarrow p_{X|Z}$
> $p_{Y} \Rightarrow p_{Y|Z}$
> und Verwendung von [[#2.3.2) Kettenregel für bedingte Entropie|2.3.2]] statt 2.3.1.


## Grafische Merkregel
für Zusammenhänge in [[#2.3.1) Kettenregel für Entropie]] und [[#2.3.3) Transinformation und (bedingte) Entropie]]
![[Pasted image 20230420103317.png]]

## 2.3.5) Kettenregel für Transinformation
![[Pasted image 20230420103348.png]]

##### Herleitung 2.3.5
> [!inf]- Spoiler
> $$\begin{align*}
I(X,Y;Z)&\overset{\overset{(2.3.3)}{\downarrow}}{=} H(X,Y) &-H(X,Y|Z)\\
&\overset{\overset{(2.3.1,2.3.2)}{\downarrow}}{=} [H(X)+{\color{red}H(Y|X)}] &-[{\color{green}H(X|Z)}+H(Y|X,Z)]\\
&\overset{\;\;\qquad}{=} [H(X)-{\color{green}H(X|Z)}] &+[{\color{red}H(Y|Z)}-H(Y|X,Z)]\\
&\overset{\overset{\overset{(2.3.3)}{(2.3.4)}}{\downarrow}}{=} I(X;Z) &+I(Y;Z|X)\qquad\qquad\quad\;\;
\end{align*}$$
> Analog erhält man durch Vertauschen von $X$ und $Y$:
> $I(X,Y;Z)=I(Y;Z)+I(X;Z|Y)$

## 2.3.6) Kettenregel für bedingte Transformation
![[Pasted image 20230420104325.png]]

##### Herleitung 2.3.6
> [!inf]- Spoiler
> Analog zu [[#Herleitung 2.3.5]], durchgehende Ergänzung von $…|V$ in allen Termen, und Verwendung von [[#2.3.4) Bedingte Transinformation und bedingte Entropie|2.3.4]] / [[#2.3.2) Kettenregel für bedingte Entropie|2.3.2]]

