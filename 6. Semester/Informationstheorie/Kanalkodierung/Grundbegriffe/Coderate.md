- ist definiert als
$$
\begin{align*}
R = \frac{\log_{2}(|\mathcal{W}|)}{n} &\text{ bit pro Kanalbenutzung}\\\\

|\mathcal{W}|\;&…\;\text{Anz. zu übertr. Nachr.}\\
n \; &… \; \text{Blocklänge}
\end{align*}
$$
- gibt _Informationsmenge pro Bit_ an, die mit bestimmter Codierung pro Kanalbenutzung übertragen wird.
- Für [[Codierung#Variante 2|Bsp. Wiederholungscode]] gilt $R=\frac{1}{n} \frac{\text{bit}}{\text{Kanaln.}}$, d.h. Coderate konvertiert für wachsende Blöcklänge gegen 0.
- *Steigende Zuverlässigkeit* $\color{orange} (\lambda^{(n)}_\text{max} \rightarrow 0)$ *muss mit sinkender Coderate bezahlt werden* - **der** entscheidende Nachteil des Wiederholungscodes.