## 3.3 Eigenschaften von Huffman-Codes
### 3.3.1 Optimalität
Die mittlere Codewortlänge eines $D$-wertigen Huffman-Codes für die $\mathbb{W}$-Fkt $p$ erfüllt die Gleichung:
$$
\overline{\mathcal{l}}_{Huff}(p) = \overline{\mathcal{l}}^{*}_{pre}(p)
$$
d.h. Huffman-Codes sind optimale präfixfreie Codes.

#### Herleitung
Bezeichung:  Code $\mathcal{C} = \{c(i), i=1,…,M\}$ mit zugehörigen Codewortlängen $\mathcal{l}(i)$ und $\mathbb{W}$en $p(i)$ . (binärer Fall, $D$-wertiger Fall analog)

Vorbetrachtungen zu reduziertem Codebaum eines präfixfreien Codes:
- Angenommen $c(i)$ und $c(j)$ mit $\mathbb{W}$en $p(i)$ und $p(j)$ sind gleich lange ($\mathcal{l}(i) = \mathcal{l}(j)$) Codewörter in einem Codebaum und unterscheiden sich nur im letzten Bit.
![[Kap 3 2023-05-17 09.52.22.excalidraw]]
- Wir erhalten sogenannten *reduzierten COdebaum*, wenn wir die Codewörter $c(i)$ und $c(j)$ durch gemeinsames Codewort $c(i,j)$ ersetzen, indem wir das letzte Bit streichen, wobei $c(i,j)$ die $\mathbb{W}$ $p(i)+p(j)$ und die Länge $\mathcal{l}(i)-1$ besitzt.
- Für die mittlere Codewortlänge $\overline{\mathcal{l}}$ des ursprünglichen Codebaums und $\overline{\mathcal{l}}'$ des reduzierten Codebaums gilt:
	$\overline{\mathcal{l}}-\overline{\mathcal{l}}' = (p(i) \mathcal{l}(i) + p(j) \mathcal{l}(j)) - (p(i)+p(j)) \cdot (\mathcal{l}(i)-1)$
	$\overset{\mathcal{l(i)} = \mathcal{l(j)}}{=} p(i)+p(j)$
	$\Rightarrow \overline{\mathcal{l}} = \overline{\mathcal{l}}' + (p(i) + p(j))$ **(\*)**
- Mit _(*)_ folgt, dass Unterschied zwischen $\overline{\mathcal{l}}$ und $\overline{\mathcal{l}}'$ nur von zusammengefassten $\mathbb{W}$en $p(i)$ und $p(j)$ abhängt, aber nicht von der konkreten Struktur des reduzierten Codebaums.
*Weitere Vorbetrachtungen und Festlegungen*
- Wir nehmen an (o.b.d.A) $p(1) \geq … \geq p(M-1) \geq p(M)$
- Für optimalen Code gilt gemäß (3.3.2 i): $\mathcal{l(1)} \leq … \leq \mathcal{l}(M-1) \leq \mathcal{l}(M)$
	für die zugehörigen Codewörter $c(1) … c(M-1) c(M)$
- Nach (3.3.2 ii) existiert ein optimaler präfixfreier binärer Code, bei dem sich $c(M-1)$ und $c(M)$ nur im letzten Bit unterscheiden und für den gilt: $\mathcal{l}(M-1) = \mathcal{l}(M)$.
- WIr betrachten nachfolgend solch einen Code für die $\mathbb{W}$en $\{p(1),…,p(M-1),p(M)\}$.
**Optimalitätsnachweis**:
Es gilt folgende Äquivalenz:
$$
\begin{align*}
&\overline{\mathcal{l}} \text{ ist mittl. CWLä. für opt. präfixfreien Code zu den } \mathbb{W} \text{en } \{p(1),…,p(M-1),p(M)\}\\
&\Updownarrow\\
&\overline{\mathcal{l}}' \text{ist mittl. CWLä. für opt. präfixfreien Code zu den reduzierten } \mathbb{W} \text{en } \{p(1), …, p(M-1)+p(M)\}
\end{align*}
$$
- Das bedeutet: MIt einem optimalen Code für die reduzierten $\mathbb{W}$en lässt sich ein optimaler Code für die ursprünglichen $\mathbb{W}$en konstruieren (durch Anfügen jeweils einer $0$ und einer $1$)
- Damit ist das ursprüngliche Problem um eine $\mathbb{W}$ reduziert!
- Diesen Vorgang setzt man stufenweise fort, bis nur noch zwei $\mathbb{W}$ übrig sind. Die optimalen Codewörter dafür sind $0$ und $1$
- Stufenweise Auflösung dieser Rekursion liefert optimalen präfixfreien Code.
- Der Huffman-Algorithmus entspricht genau der betrachteten Vorgehensweise und liefert damit optimalen Code.

### 3.3.2 Eigenschaften optimaler Codes
#### Herleitung
- o.b.d.A. $p(1) \geq … \geq p(M)$ **(\*)**
	Codewort $c(i)$ mit Länge $\mathcal{l}$ ist $\mathbb{W} \; p(i)$ zugeordnet.

##### zu Teil (i)
- Sei $1 \leq i \lt j \leq M$, sodass $p(i) \gt p(j)$.
- Argumentation:
$$
\begin{align*}
(\text{"Code optimal"} \Rightarrow & \text{"}\mathcal{l}(i) \leq \mathcal{l}(j) \text{"})& \Leftrightarrow \qquad (\text{"}\mathcal{l}(i) > \mathcal{l}(j)\text{"} \Rightarrow \text{"Code nicht optiomal"})\\
\underbrace{A \qquad\qquad \Rightarrow}_{\underset{(2)}{\text{zu zeigende Aussage}}} & B &\Leftrightarrow \qquad \underbrace{\overline{B} \qquad \Rightarrow \qquad \overline{A}}_{\underset{(1)}{\text{nachf. gez. Aussage}}} \qquad \qquad \qquad \qquad \qquad 
\end{align*}
$$
- Angenommen $\mathcal{l}(i) > \mathcal{l}(j)$, d.h. kürzere Codewörter werden kleineren $\mathbb{W}$en zugeordnet
- Vertauschen wir Codewörter $c(i)$ und $c(j)$, ändert sich die mittlere Codewortlänge wie folgt:
	$[p(i)\mathcal{l}(j) + p(j) \mathcal{l}(i)] - [p(i) \mathcal{l}(i) + p(j) \mathcal{l}(j)] = \underbrace{[p(i)-p(j)]}_{>0} \cdot \underbrace{[\mathcal{l}(j) - \mathcal{l}(i)]}_{<0} < 0$
	d.h. mittlere Codewortlänge verkleinert sich.
- Unter gemachter Annahme kann Code also nicht optimal sein, d.h. wir haben (1) gezeigt und damit automatisch auch (2).

##### zu Teil (ii)
- Wir betrachten optimalen präfixfreien 2-wertigen Code.
- Nach (i) hat $c(M)$, welches kleinster $\mathbb{W} \; p(M)$ zugeordnet ist, die größte Länge.
- Codebaum:
![[Kap 3 2023-05-17 10.41.37.excalidraw]]
- $\hat{c}$ *muss* Codewort sein, ansonsten könnten wir $c(M)$ durch $\color{lightblue}\circledcirc$ ersetzen, wodurch $\mathcal{l}(M)$ um 1 kleiner würde und somit $\overline{\mathcal{l}}$ auch kleiner würde. 
	**⚡ zu Optimalitätsannahme** $\Rightarrow \hat{c}$ Codewort.
- Ist $\hat{c}$ zweitkleinster $\mathbb{W} \; p(M-1)$ zugeordnet, hat Code zu zeigende Eigenschaft.
- Falls nicht, dann ist $\hat{c}$ der $\mathbb{W} \; p(i)$ für ein $i < M-1$ zugeordnet.
- Nach _(*)_ und mit (i) gilt:
	- $\underset{c(M)}{\mathcal{l}(M)}=\underset{\hat{c}}{\mathcal{l}(i)} \underset{(i)}{\leq} \mathcal{l}(M-1) \underset{(i)}{\mathcal{l}(M)}$
	- d.h. $\mathcal{l}(M-1) = \mathcal{l}(M) = \mathcal{l}(i)$
- **=>** Codewörter, die $\mathbb{W}$en $p(i)$ und $p(M-1)$ zugeordnet sind, können vertauscht werden, ohne $\overline{\mathcal{l}}$ und Optimalität zu ändern.