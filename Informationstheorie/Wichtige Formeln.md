## Grundlegende Begriffe
**Zufallsgröße**: $X$
**Alphabet** *einer ZG*: $\mathcal{X}=\{a_{1},a_{2},…,a_{m}\}$ … Werte, die ZG annehmen kann
**Träger** *einer ZG*: $\mathcal{S}_{X}=\{x \in \mathcal{X} : \mathbb{P}(X=x)>0\} \subset \mathcal{X}$ … Annehmbare Werte?
**$\color{orange}\mathbb{W}$-Funktion**: $p_X(x)=\mathbb{P}(X=x), \;\; x \in \mathcal{X}$ … ordnet Werten $x$ der ZG $X$ ihre $\mathbb{W}$s zu
**Rand-**$\color{orange}\mathbb{W}$**-Funktion**: wenn gilt $p_{X}(x)=\sum\limits_{y \in \mathcal{Y}} p_{X,Y}(x,y), \quad p_{Y}(y)=\sum\limits_{x \in \mathcal{Y}} p_{X,Y}(x,y),\;\;y\in \mathcal{Y}$
**Erwartungswert**: $\mathbb{E}(X)=\sum\limits_{x \in \mathcal{X}} x \cdot p_{X}(x)$ | *für transf. ZG:* $\mathbb{E}(Y)=\mathbb{E}(g(X))=\sum\limits_{x \in \mathcal{X}} g(x) \cdot p_{X}(x)$
**Varianz** *einer ZG*: $var(X)=\mathbb{E}(\;(X-\mathbb{E}(X))^{2}\;)\;\; = \sum\limits_{x \in \mathcal{X}}(x-\mathbb{E}(X))^{2} \cdot p_{X}(x)\;\; = \mathbb{E}(X^{2}) - (\mathbb{E}(X))^{2}$

**Gemeinsame** $\color{orange}\mathbb{W}$**-Funktion**: $p_{X,Y}(x,y)=\mathbb{P}(X=x, Y=y),\quad x \in \mathcal{X},y \in \mathcal{Y}$
**Bedingte** $\color{orange}\mathbb{W}$**-Funktion**: $p_{Y|X}(y|x)=\frac{p_{X,Y}(x,y)}{p_{X}(x)}\quad(\forall x \in \mathcal{S}_{X}, y\in \mathcal{Y})$ … Bedingte $\mathbb{W}$-Fkt. von $Y$ unter Bedingung $X=x$ ^bedwfkt
**Kombination**: $p_{(X,Y)|Z}$ … bedingte $\mathbb{W}$-Fkt von $(X,Y)$ unter der Bedingung $Z$ ^711f18

**Unabhängigkeit**: wahr, falls $\forall(x,y) \in \mathcal{X} \times \mathcal{Y}:\;\; p_{X,Y}(x,y)=p_{X}(x) \cdot p_{Y}(Y)$
Sind $X$ und $Y$ unabhängig, sind sie auch unkorreliert. 
Aus Unkorrelierthiet folgt i.A. nicht Unabhängigkeit.

#### Markowkette
##### …der Länge 3
Drei diskrete ZG $X,Z$ und $Y$ bilden eine Markowkette in dieser Reihenfolge, falls $\forall (z,x) \in \mathcal{S}_{(Z,X)}$ und $y \in \mathcal{Y}$ gilt:
$$
p_{Y|(Z,X)}\left(y|(z,x)\right)=p_{Y|Z}(y|z)
$$
wobei $\mathcal{S}_{(Z,X)}$…Träger des diskreten ZV $(Z,X)$. **Notation:** $\color{orange}X \rightarrow Z \rightarrow Y$


## Shannonsche Informationsmaße
[[Shannonsche Informationsmaße]]
$H(X)=-\mathbb{E}\left(\;\log_{2}(\,p_X(X)\,)\;\right)$ 
$H(X,Y) = -\mathbb{E}(\;\log_{2}(\,p_{X,Y}(X,Y)\,)\;)$
$H(Y|X) = -\mathbb{E}(\;\log_{2}(\,p_{Y|X}(Y|X)\,)\;)$
$D(X||Y)=-\mathbb{E}\left(\;\log_{2}\left(\frac{p_{X}(X)}{p_{Y}(Y)}\right) \;\right)$
$I(X;Y) = \mathbb{E}\left(\log_{2}\left( \frac{p_{X,Y}(X,Y)}{p_{X}(X) p_{Y}(Y)}  \right)\right)$
$I(X;Y|Z) = \mathbb{E}\left(\log_{2}\left( \frac{p_{X,Y|Z}(X,Y|Z)}{p_{X|Z}(X|Z) p_{Y|Z}(Y|Z)} \right)\right)$

## Grundlegende Zusammenhänge, Kettenregeln
$H(X)=H(p_{X})=\log_{2}|\mathcal{X}|-D(p_{X}||p_{U})$
$I(X;Y)=D(p_{X,Y}||p_{X}\cdot p_{Y})$
$I(X,Y;Z)=I(X;Z)+I(Y;Z|X)$
![[Pasted image 20230503101344.png]]

## Nichtnegativität, wichtige (Un-)Gleichungen:
![[Pasted image 20230503101425.png]]
