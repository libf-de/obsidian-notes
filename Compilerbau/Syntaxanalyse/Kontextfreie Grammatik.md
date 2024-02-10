(CFG)

>[!inf] Definition
> Viertupel: $(\underbrace{N}_{\text{Nichtterminale}}, \underbrace{T}_{\text{Terminale}}, \underbrace{P}_{\text{Prod.regeln}}, \underbrace{S}_{\text{Startsymbol}})$
> $\quad P \subseteq N \times (N \cup T)^{*}, S \in N$

Notation:
- $A,B,C… \rightarrow$ Nichtterminale
- $a,b,c… \rightarrow$ Terminale
- $\alpha,\beta,\gamma… \rightarrow$ Zeichenketten aus $(N \cup T)^{*}$
- $A \Rightarrow \alpha \;\rightarrow$ Produktionen


## Ableitung
Für beliebige $\alpha,\beta \in (N \cup T)^{*}$ kann $\beta$ direkt aus $\alpha$ abgeleitet werden ($\alpha \Rightarrow \beta$), wenn es $\gamma_{1}, \gamma_{2} \in (N \cup T)^{*}$ und $(A, \gamma_{3}) \in P$ gibt, sodass $\alpha=\gamma_{1} \, A \, \gamma_{2}$ und $\beta=\gamma_{1}\,\gamma_{3}\,\gamma_{2}$

Eine Ableitungskette $\alpha_{1} \Rightarrow \alpha_{2} \Rightarrow … \Rightarrow \alpha_{n}$ wird als $\alpha_{1} \Rightarrow^{*} \alpha_{n}$ geschrieben

## Umwandlung aus regex
$$
\begin{align*}
(a|b) && \mapsto && A\Rightarrow a,\;\; A\Rightarrow b\\
a^{*} && \mapsto && A\Rightarrow aA,\;\; A\Rightarrow \epsilon
\end{align*}
$$