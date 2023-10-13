https://en.wikipedia.org/wiki/Sequent_calculus


![[Sequenz]]

![[Schlussregeln]]


![[Axiom]]


Definition: *Eine Herleitung* einer [[Sequenz]] $Γ ⇒ ∆$ aus einer [[Menge]] $S$ von Sequenzen (Prämissen) ist: 

- eine Folge $S_1, . . . , S_k$ von Sequenzen mit 
	- $S_k = Γ ⇒ ∆$ 
	- Für jedes $i ≤ k$ gilt eines der Folgenden: 
		- $S_i$ ist ein Axiom 
		- $S_i ∈ S$ 
		- es gibt $j < i$ so dass $S_i$ Konklusion einer Regel mit Prämisse $S_j$ ist 
		- es gibt $j_1, j_2 < i$ so dass $S_i$ Konklusion einer Regel mit Prämissen $S_{j1}$ und $S_{j2}$ ist 

Ein **Beweis** für $Γ ⇒ ∆$ ist eine *Herleitung* von $Γ ⇒ ∆$ aus $∅$ 

>[!tip] Lemma 
>Für jede Schlussregel und jede Bewertung α gilt: 
>erfüllt α die Prämissen der Regel, dann auch die Konklusion.

>[!info] Theorem 
>Sei eine Herleitung von $S$ mit aus den Prämissen $S$ gegeben.
>Dann gilt für jede Bewertung α: 
>Wenn $α |\!\!\!= S^′$ für $S^′ ∈ S$, dann auch $α |\!\!\!= S$

>[!tip] Korollar 
>Gibt es einen Beweis für  $⇒ F$, dann ist $F$ eine [[Tautologie]]

>[!info] Theorem 
>Ist $F$ eine [[Tautologie]], dann gibt es einen **Beweis** für $⇒ F$.

>[!tip] Lemma 
>Für jede Schlussregel und jede Bewertung $α$ gilt: [[erfüllbar|erfüllt]] $α$ die Konklusion der Regel, dann auch alle Prämissen.

