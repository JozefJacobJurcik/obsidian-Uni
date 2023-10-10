Ein _Ring_ $( R , + , ⋅ )$ ist eine [[Menge]] $R$ mit zwei zweistelligen Operationen $+$ und $⋅$ , für die die folgenden Beziehungen, genannt _Ringaxiome_, gelten:

- $( R , + )$ ist eine [[abelsche Gruppe]] unter der _Addition_ $+$, deren [[neutrales Element]] als _Nullelement_ des *Rings* $R$ mit $0$ bezeichnet wird.

- $( R , ⋅ )$ ist eine [[Halbgruppe]] (in der Vorlesung [[Monoid]]) unter der _Multiplikation_ $⋅$ . In der gängigen Schreibung bindet $⋅$ stärker als + und wird sehr häufig sogar weggelassen.

- Es gelten die [[Distributivgesetz]]e
	
	$a ⋅ ( b + c ) = ( a ⋅ b ) + ( a ⋅ c ) = a b + a c$    (_linke Distributivität_)
	
	und
	
	$( a + b ) ⋅ c = ( a ⋅ c ) + ( b ⋅ c ) = a c + b c$    (_rechte Distributivität_)
	
	für alle $a , b , c ∈ R$ .

Ein Ring heißt _kommutativ_, falls er bezüglich der Multiplikation [[Kommutativgesetz|kommutativ]] ist, ansonsten spricht man von einem *nicht-kommutativen* Ring.

###### Beispiele:
$\mathbb Z,\mathbb Q,\mathbb R$ sind *kommutative Ringe*. 

[[Restklasse]]n $\mathbb Z_n$ mit Addition + und Multiplikation · [[modulo]] $n\rightarrow$ *Ring*

Die [[Menge]] $\mathbb R^{2\times2}$ der reellen $2 \times 2$-Matrizen. 
- Addition und Multiplikation von Matrizen wie üblich.
- [[neutrales Element|neutrale Elemente]] sind: 
$$\begin{matrix} \begin{pmatrix}0&0\\0&0 \end{pmatrix}\operatorname{bzgl.} + \qquad\operatorname{und}\qquad \begin{pmatrix} 1&0\\0&1\end{pmatrix}\operatorname{bzgl.} \cdot\end{matrix}$$
- $\mathbb R^{2×2}$ ist nicht [[Kommutativgesetz|kommutativ]].

Die Menge $\mathbb Q[x]$ der Polynome mit rationalen Koeffizienten. 
- Addition und Multiplikation von Polynomen wie üblich. 
- [[neutrales Element|neutrale Elemente]] sind die konstanten Polynome 0 und 1.

###### Gegenbeispiel:
$(\mathbb N, +, ·)$ ist **kein** *Ring*.