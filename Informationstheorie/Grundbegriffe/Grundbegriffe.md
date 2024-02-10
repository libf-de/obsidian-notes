## Grundlegende Begriffe

### …einer Zufallsgröße
- **Zufallsgröße**: $X,Y,Z$
- **Werte** <small>einer Zufallsgröße</small>: $x,y,z$
- **Alphabet** <small>einer ZG</small>: $\mathcal{X}=\{a_{1},a_{2},…,a_{m}\}$ <span style="color: gray">… Werte, die ZG annehmen kann</span>
- **[[Träger einer Zufallsgröße|Träger]]** <small>einer ZG</small>: $\mathcal{S}_{X}=\{x \in \mathcal{X} : \mathbb{P}(X=x)>0\} \subset \mathcal{X}$ <span style="color: gray">… Annehmbare Werte <b>mit positiver 𝕎</b></span>
- **[[Wahrscheinlichkeitsfunktion|𝕎-Funktion]]**: $p_X(x)=\mathbb{P}(X=x), \;\; x \in \mathcal{X}$ <span style="color: gray">… ordnet Werten</span> $\color{gray} x$ <span style="color: gray">der ZG</span> $\color{gray} X$ <span style="color: gray">ihre 𝕎en zu</span>
- **[[Erwartungswert]]**: $\mathbb{E}(X)=\sum\limits_{x \in \mathcal{X}} x \cdot p_{X}(x)$ | *für transf. ZG:* $\mathbb{E}(Y)=\mathbb{E}(g(X))=\sum\limits_{x \in \mathcal{X}} g(x) \cdot p_{X}(x)$
- **Varianz** <small>einer ZG</small>: $var(X)=\mathbb{E}(\;(X-\mathbb{E}(X))^{2}\;)\;\; = \sum\limits_{x \in \mathcal{X}}(x-\mathbb{E}(X))^{2} \cdot p_{X}(x)\;\; = \mathbb{E}(X^{2}) - (\mathbb{E}(X))^{2}$
- **weitere Eigenschaften**: [[Transformation einer Zufallsgröße|Transformation]], [[Gleichverteilung]], [[Identisch verteilt]]

### … mehrerer Zufallsgrößen
- **[[Identisch verteilt]]**: $X \sim Y$ <span style="color: gray">… falls Träger und 𝕎-Fkt gleich sind</span>
- **Rand-**$\color{orange}\mathbb{W}$**-Funktion**: wenn gilt $p_{X}(x)=\sum\limits_{y \in \mathcal{Y}} p_{X,Y}(x,y), \quad p_{Y}(y)=\sum\limits_{x \in \mathcal{Y}} p_{X,Y}(x,y),\;\;y\in \mathcal{Y}$
- **Gemeinsame** $\color{orange}\mathbb{W}$**-Funktion**: $p_{X,Y}(x,y)=\mathbb{P}(X=x, Y=y),\quad x \in \mathcal{X},y \in \mathcal{Y}$
- **Bedingte** $\color{orange}\mathbb{W}$**-Funktion**: $p_{Y|X}(y|x)=\frac{p_{X,Y}(x,y)}{p_{X}(x)}\quad(\forall x \in \mathcal{S}_{X}, y\in \mathcal{Y})$ <span style="color: gray">… Bedingte 𝕎-Fkt. von </span>$\color {gray} Y$ <span style="color: gray">unter Bedingung</span> $\color{gray} X=x$ ^bedwfkt
- **Kombination**: $p_{(X,Y)|Z}$ <span style="color: gray">… bedingte 𝕎-Fkt von</span> $\color{gray} (X,Y)$ <span style="color: gray">unter der Bedingung</span> $\color{gray} Z$ ^711f18
- **Unabhängigkeit**: wahr, falls $\forall(x,y) \in \mathcal{X} \times \mathcal{Y}:\;\; p_{X,Y}(x,y)=p_{X}(x) \cdot p_{Y}(Y)$
- **Unkorreliertheit**: Sind $X$ und $Y$ unabhängig, sind sie auch unkorreliert. Aus Unkorrelierthiet folgt i.A. nicht Unabhängigkeit.

#### Markowkette
##### …der Länge 3
Drei diskrete ZG $X,Z$ und $Y$ bilden eine Markowkette in dieser Reihenfolge, falls $\forall (z,x) \in \mathcal{S}_{(Z,X)}$ und $y \in \mathcal{Y}$ gilt:
$$
p_{Y|(Z,X)}\left(y|(z,x)\right)=p_{Y|Z}(y|z)
$$
wobei $\mathcal{S}_{(Z,X)}$…Träger des diskreten ZV $(Z,X)$. 
**Notation:** $\color{orange}X \rightarrow Z \rightarrow Y$ $\overset{\text{äquiv.}}{\Longleftrightarrow} Y \leftarrow Z \leftarrow X \overset{\text{äquiv}}{\Longleftrightarrow}$ $X$ und $Y$ sind bedingt unabhängig gegeben $Z$



## Shannonsche Informationsmaße
![[Shannonsche Informationsmaße]]

## Grundlegende Zusammenhänge, Kettenregeln
$H(X)=H(p_{X})=\log_{2}|\mathcal{X}|-D(p_{X}||p_{U})$
$I(X;Y)=D(p_{X,Y}||p_{X}\cdot p_{Y})$
$I(X,Y;Z)=I(X;Z)+I(Y;Z|X)$
![[Pasted image 20230503101344.png]]

## Nichtnegativität, wichtige (Un-)Gleichungen:
![[Pasted image 20230503101425.png]]
