- **Entropie**: 
$H(X,Y) = $
$H(Y|X) = -\mathbb{E}(\;\log_{2}(\,p_{Y|X}(Y|X)\,)\;)$
$D(X||Y)=-\mathbb{E}\left(\;\log_{2}\left(\frac{p_{X}(X)}{p_{Y}(Y)}\right) \;\right)$
$I(X;Y) = \mathbb{E}\left(\log_{2}\left( \frac{p_{X,Y}(X,Y)}{p_{X}(X) p_{Y}(Y)}  \right)\right)$
$I(X;Y|Z) = \mathbb{E}\left(\log_{2}\left( \frac{p_{X,Y|Z}(X,Y|Z)}{p_{X|Z}(X|Z) p_{Y|Z}(Y|Z)} \right)\right)$


## Entropie
$$
\begin{align*}
H(X) = H(p_{X}) &= - \sum\limits_{x \in \mathcal{X}} p_{X}(x) \cdot \log_{2}[\, p_{X}(x) \,] \\
 &=? -\mathbb{E}\left(\;\log_{2}(\,p_X(X)\,)\;\right)
\end{align*}
$$
…ist der mittlere [[#Informationsgehalt]] der Zufallsgröße $X$

#### 2.2.1 Symmetrie der Entropie
$H(X,Y) = H(Y,X)$

#### Kettenregel für Entropie (2.3.1)
$$
\begin{flalign*}
H(X,Y) &= H(X) + H(Y|X) &&\\
&= H(Y) + H(X|Y) &&
\end{flalign*}
$$


## gemeinsame Entropie
$$
\begin{align*}
H(X,Y) = H(p_{X,Y}) &= \sum\limits_{(x,y) \in \mathcal{X} \times \mathcal{Y}} p_{X,Y}(x,y) \cdot \log_{2}[ \, p_{X,Y}(x,y) \,] \\
 &= -\mathbb{E}(\;\log_{2}(\,p_{X,Y}(X,Y)\,)\;)
\end{align*}
$$
…ist der mittlere [[#Informationsgehalt]] der Zufallsgrößen $X$ und $Y$??? #TODO

#### Symmetrie der gemeinsamen Entropie (2.2.2)
$H(X,Y|Z) = H(Y,X|Z)$

#### Kettenregel für bedingte Entropie (2.3.2)
$$\begin{flalign*}
H(X,Y|Z) &= H(X|Z) + H(Y|X,Z)&&\\
&= H(Y|Z) + H(X|Y,Z)&&
\end{flalign*}$$

## Informationsgehalt
$$
\begin{align*}
\log_{2}\left[\frac{1}{p_{X}(x)}\right] &=  \text{Informationsgehalt des Eregnisses } X=x
\end{align*}
$$
=> kleine 𝕎 = großer Inf.geh., große 𝕎 = kleiner Inf.geh.

## bedingte Entropie
$$H(Y|X)$$
## Transinformation
$$I(X;Y)$$
#### Symmetrie der Transinformation (2.2.3)
$I(X;Y) = I(Y;X)$

#### Kettenregel für Transinformation
$$I(X,Y|Z) = I()$$


## bedingte Transinformation
$$I(X;Y|Z)$$
#### Symmetrie der bedingten Transinformation (2.2.4)
$I(X;Y|Z) = I(Y;X|Z)$

## relative Entropie
$$D(X||Y)$$
