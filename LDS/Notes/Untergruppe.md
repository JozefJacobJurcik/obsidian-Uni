Eine nichtleere Teil[[menge]] $U$ von $G$ bildet genau dann eine *Untergruppe* $( U , ∘ )$ von $( G , ∘ )$ , wenn eine (und damit alle) der folgenden äquivalenten Bedingungen gilt:

- Zu zwei beliebigen Elementen in $U$ ist auch deren Verknüpfung in $U$, und mit jedem Element in $U$ auch dessen [[inverses Element|Inverses]].

- Für alle $a , b ∈ U$ gilt $a ∘ b^{− 1} ∈ U$.

- ${\displaystyle a\sim b:\Longleftrightarrow a\circ b^{-1}\in U}$ ist eine [[Äquivalenzrelation]] auf $G$.

-  Für alle ${\displaystyle a\in U,b\in G\!\setminus \!U}$    gilt    ${\displaystyle a\circ b\notin U}$ .

#### Untergruppenkriterium

Sei $U$ eine Teil[[menge]] der [[Gruppe]] $G$.

$U$ ist genau dann eine Untergruppe von $G$, wenn für alle $a,b \in U$ gilt
$$\displaystyle a \cdot b^{-1} \in U \,. $$
Ist $G$ eine endliche [[Gruppe]], dann ist $U$ genau dann eine Untergruppe von $G$, wenn für alle $a,b \in U$ gilt
$$\displaystyle a \cdot b \in U \,. $$
###### Beweis
Ist $U$ eine Untergruppe von $G$, dann ist für $a,b \in U$ trivialerweise $a\cdot b^{-1} \in U$.

Es ist also umgekehrt zu zeigen, dass $U$ eine Gruppe ist, wenn für alle $a,b \in U$ gilt $a\cdot b^{-1} \in U$.

Die [[Assoziativgesetz|Assoziativität]] von $U$ folgt aus der Assoziativität von $G$. Für beliebiges $a \in U$ wählt man $b$ als $b=a$. Dann ist $a \cdot b^{-1}=a \cdot a^{-1}=1_G \in U$. Somit ist das [[neutrales Element]] von $G$ in $U$ enthalten, und es gilt $1_G=1_U$. Es bleibt noch zu zeigen das für jedes Element $u \in U$ auch $u^{-1} \in U$ ist. Dazu wählt man $a=1$ und $b=u$. Dann ist nach Voraussetzung $a \cdot b^{-1}=1 \cdot u^{-1}=u^{-1} \in U$.

Ist $G$ eine endliche [[Gruppe]], dann besitzt jedes Element endliche [[Ordnung]]. Für ein Element $u \in U$ ist dann auch $u \cdot u=u^2 \in U$ (mit der Wahl $a=b=u$). Durch iterieren erhält man für alle $n \in \mathbb{N}$, dass $u^n \in u$ ist. Sei nun $m \in \mathbb{N}$ die Ordnung von von $u$, d.h. $u^m=1$. Dann ist $1=u^m=u \cdot u^{m-1}$ und damit $u^{-1}=u^{m-1} \in U$. 


### Vorlesung
Eine [[Unterstruktur]] $H$ einer [[Gruppe]] $G$ heißt *Untergruppe*, wenn sie eine [[Gruppe]] ist, also wenn $e ∈ H$ ist, und für jedes $h ∈ H$ auch $h^{−1} ∈ H$ ist.

>[!tip] Lemma 
> Jede [[Unterstruktur]] einer endlichen [[Gruppe]] ist auch *Untergruppe*.

>[!tip] Lemma 
>Sind $H_1$ und $H_2$ *Untergruppen* von $G$, dann auch $H_1 ∩ H_2$.
