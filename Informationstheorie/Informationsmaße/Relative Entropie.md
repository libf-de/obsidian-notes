Gilt $\mathcal{X} \subset \mathcal{Y}$, dann heißt die Größe
$$
D(X||Y) = \left\{\begin{matrix}  
\sum\limits_{x \in \mathcal{X}} p_{X}(x) \log_{2} \frac{p_{X}(x)}{p_{Y}(x)} &&\text{falls } \mathcal{S}_{X} \subseteq \mathcal{S}_{Y} \\ 
\infty && \text{sonst}
\end{matrix}  
\right.
$$
_relative Entropie zwischen (den ZG) $\color{orange} X$ und $\color{orange}Y$._
- ist ein quantitatives Maß für den Unterschied der $\mathbb{W}$-Verteilungen der Zufallsgrößen $X$ und $Y$.
- quantifiziert u.a. zusätzlich erforderlichen Speicherbedarf bei suboptimaler Quellencodierung.

### 2.1.6) Darstellung anderer Maße mit relativer Entropie
#### II) Entropie
$p_{U}$: $\mathbb{W}$-Funktion einer _Gleichverteilung_ auf $\mathcal{X}$ #imp
$$
H(X)=H(p_{X})=\log_{2}|X|-D(p_{X}||p_{U})
$$

#### III) Bedingte Entropie
$p_{\widetilde{U}}$: $\mathbb{W}$-Funktion einer _Gleichverteilung_ auf $\mathcal{Y}$
![[Pasted image 20230420095352.png]]

#### IV) Transinformation
$$
I(X;Y)=D(p_{X,Y}||p_{X}*p_{Y})
$$ #imp 

#### V) Bedingte Transinformation
$$
\begin{align*}
I(X;Y|Z)&= \sum\limits_{z \in \mathcal{Z}} p_{Z}(z) I(X;Y|Z=z)\\
&= \sum\limits_{z \in \mathcal{Z}}p_{Z}(z) D(p_{X,Y|Z}(\cdot,\cdot|z) || p_{X|Z}(\cdot|z) p_{Y|Z}(\cdot|z))  

\end{align*}
$$

##### Herleitung zu 2.1.6:
$$
\begin{align*}
(II) && D(p_{X}||p_{U})&= \sum\limits_{x \in \\
\mathcal{X}} p_{X}(x) \log_{2} \frac{p_{X}(x)}{\frac{1}{|\mathcal{X}|}} &\\
(IIa)&& &= \underbrace{\sum\limits_{x \in \mathcal{X}}p_{X}(x)\log_{2}(p_{X}(x))}_{-H(X)} + \underbrace{\sum\limits_{x \in X} p_{X}(x) \log_{2} |\mathcal{X}|}_{\log_{2}|\mathcal{X}|}\\
&& &= -H(p_{X})+\log_{2}|\mathcal{X}|\\
(III) && &\text{mit Def. (2.1.2) und (II)}\\
(IV) && &\text{direkt mit Def. (2.1.3) und (2.16.I)}\\
(V) && &\text{mit Def. (2.1.4) und (IV)}
\end{align*}
$$

$$
\begin{align*}
IIa) && \log_{2}\left(\frac{a}{b}\right)=\log_{2}a-\log_{2}b \quad \log_{2}\left(\frac{1}{c}\right)=-\log_{2}c\\

\end{align*}
$$