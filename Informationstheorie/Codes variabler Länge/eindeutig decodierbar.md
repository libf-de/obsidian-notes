falls jede endliche Aneinanderreihung von Codewörtern ohne Trennzeichen rekonstruiert werden kann.

=> sind stets [[nicht-singulär]]

## Minimale mittlere Codewortlänge
…für $\mathbb{W}$-Funktion $p$ bezeichnen wir mit:
$\overline{\mathcal{l}}^{*}_{ud} = \overline{\mathcal{l}}^{*}_{ud}(p) = \min \left\{ \overline{\mathcal{l}}(\mathcal{C},p):\;\mathcal{C} \text{ eindeutig decodierbar}\right\}$ 

## Optimale Codes
…ist optimal für $\mathbb{W}$-Funktion $p$ falls gilt:
$\overline{\mathcal{l}}(\mathcal{C},p)=\overline{\mathcal{l}}^{*}_{ud}(p)$

## Kriterium
$\mathcal{C}$ ist ein eindeutig decodierbarer Code $\Longleftrightarrow$ Kein Suffix ist Codewort in $\mathcal{C}$

##### Suffix
Sei $\mathcal{C}$ ein [[D-wertiger Code]]. Eine endliche Folge $s$ von Symbolen des $D$-wertigen Codealphabets heißt _Suffix in $\color{orange}\mathcal{C}$_, falls:
$$
\begin{align*}
\text{(I)} & \;\exists c(i),c(j) \in \mathcal{C} \;:\;c(i)=c(j)s &\text{oder}\\
\text{(II)} & \; \exists c(i) \in \mathcal{C} \text{ und  ein Suffix } \hat{s} \text{ in } \mathcal{C}: \hat{s}=c(i)s & \text{oder}\\
\text{(III)} & \; \exists c(i) \in \mathcal{C} \text{ und ein Suffix } \hat{s} \text{ in } \mathcal{C}: c(i) = \hat{s} s
\end{align*}
$$

> [!example] Beispiele 2-wertiger Codierungen:
> Code $\mathcal{C}_{1} = \{0,01,0{\color{red}10},1{\color{red}0}\}$
> -> nicht eindeutig dec., da Suffixe $10$ und $0$ Codewörter sind
> 
> Code $\mathcal{C}_{2} = \{10,00,11,110\}$
> -> Eindeutig dec., da einziger Suffix $0$ kein Codewort ist.
> 
> Code $\mathcal{C}_{3} = \{0,10,110,111\}$
> -> Eindeutig dec., da ohnehin [[präfixfrei]]







