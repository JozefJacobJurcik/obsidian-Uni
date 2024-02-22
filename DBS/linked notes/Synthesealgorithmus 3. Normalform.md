---
aliases: Synthesealgorithmus
---

[[DBS Skript.pdf#page=298|DBS Skript, page 298]]

## WIKI:

Es müssen alle [[Funktionale Abhängigkeit|funktionalen Abhängigkeiten]] ${\displaystyle {\mathcal {F}}}$ der zu zerlegenden Relation $R$ unter den Attributen bekannt sein.

Beispiel:
	${\displaystyle R=\operatorname {Relation} (A,B,C,D,E,F)}$
	${\displaystyle {\mathcal {F}}=\left\{\left\{A\right\}\to \left\{B,E\right\},\left\{A,E\right\}\to \left\{B,D\right\},\left\{F\right\}\to \left\{C,D\right\},\left\{C,D\right\}\to \left\{B,E,F\right\},\left\{C,F\right\}\to \left\{B\right\}\right\}}$

Der Synthesealgorithmus besteht dann aus vier Schritten:

1. Reduktion von ${\displaystyle {\mathcal {F}}}$, d. h. die *Bestimmung der kanonischen Überdeckung*.
2. Erzeugen der neuen Relationenschemata aus der kanonischen Überdeckung.
3. Ggf. die Hinzunahme einer Relation, die nur den Ursprungsschlüssel enthält.
4. Elimination der Schemata, die in einem anderen Schema enthalten sind.

### Reduktion

Dies wird auch die Berechnung der **kanonischen Überdeckung** genannt.

#### 1. Schritt: Linksreduktion 

Für alle $\psi  \in \Psi$ ersetze $\Psi \rightarrow \Gamma$ durch $\Psi  \setminus \{\psi\} \rightarrow \Gamma$ , falls $\Gamma$ schon durch $\Psi \setminus \{\psi\} \rightarrow \Gamma$ determiniert ist.

Die obige Bedingung lässt sich testen, indem man überprüft, ob $\Gamma \subseteq \mathop{\mathrm{AttributH\ddot ulle}}(F, \Psi \setminus \{\psi\})$ ist, wobei F die Menge der funktionalen Abhängigkeiten bezeichnet. Falls dies zutrifft, kann $\psi$ aus $\Psi$ entfernt werden.

Beispiel: $\mathop{\mathrm{Relation}}\left(A,B,C,D,E,F\right)$

-   $A \rightarrow B,E$
-   $A\underline{E} \rightarrow B,D$
-   $F \rightarrow C,D$
-   $CD \rightarrow B,E,F$
-   $\underline{C}F \rightarrow B$

In der zweiten Relation fällt E weg, da sich B und D in der Attributhülle von A ($A^+ = \{A,\underline{B,D},E\}$) befinden. In der letzten Relation fällt C weg, wegen $F^+ = \{\underline{B},C,D,E,F\}$. 
Man kann es auch so formulieren: E wird in $AE \rightarrow B,D$ nicht benötigt, um $B,D$ zu erreichen.

Lösung:

-   $A \rightarrow B,E$
-   $A \rightarrow B,D$
-   $F \rightarrow C,D$
-   $CD \rightarrow B,E,F$
-   $F \rightarrow B$

#### 2. Schritt: Rechtsreduktion 

Für alle $\gamma \in \Gamma$ ersetze $\Psi \rightarrow \Gamma$ durch $\Psi \rightarrow \Gamma \setminus\{\gamma\}$, falls $\gamma$ schon transitiv durch $\Psi$ bestimmt ist.

Die obige Bedingung lässt sich überprüfen, indem man für jedes $\gamma \in \Gamma$ testet, ob $\gamma \in\text{AttributHuelle}((F \setminus (\Psi \rightarrow \Gamma)) \cup (\Psi \rightarrow (\Gamma \setminus \{\gamma\})),\Psi)$ ist. Falls dies zutrifft, kann $\gamma$ aus $\Gamma$ entfernt werden.

An obigem Beispiel:

-   $A \rightarrow \underline{B},E$
-   $A \rightarrow B,D$
-   $F \rightarrow C,D$
-   $CD \rightarrow \underline{B},E,F$
-   $F \rightarrow B$

In der ersten Relation fällt B weg, da $A^+_{F'}$ = $\{A,\underline{B},D,E\}$. In der vierten Relation fällt ebenfalls das B weg, wegen $CD^+_{F'}$ = $\{\underline{B},C,D,E,F\}$.

-   $A \rightarrow E$
-   $A \rightarrow B,D$
-   $F \rightarrow C,D$
-   $CD \rightarrow E,F$
-   $F \rightarrow B$

#### 3. Schritt: Leere Klauseln 

Eliminiere Klauseln der Form $\Psi \rightarrow \varnothing$

Im Beispiel aus Schritt 2 gibt es keine Abhängigkeiten mit leerer rechter Seite. Also gibt es in diesem Fall hier nichts zu tun.

#### 4. Schritt: Zusammenfassen 

Fasse Formeln $a \rightarrow b_0 , a \rightarrow b_1 \dots$ zu $a \rightarrow b_0 \cup b_1 \dots$ zusammen.

Im Beispiel fassen wir nun Ausdrücke mit gleicher linker Seite zusammen:

-   $A \rightarrow E,B,D$
-   $F \rightarrow C,D,B$
*  $CD \rightarrow E,F$

### Neues Relationenschema 

Aus allen $Ψ \to Γ$ wird $R(Ψ, Γ)$ .

Zusätzlich muss ein neuer [[Schlüssel]] gefunden werden. Gegebenenfalls muss eine neue Relation erzeugt werden. Überflüssige Relationen können gestrichen werden, wenn diese in anderen enthalten sind.

Am Beispiel:

-   $R_1(\underline{A},B,D,E)$  \# $A$ ist Primär[[schlüssel]]
-   $R_2(B,C,D,\underline{F})$ \# $F$ ist Primärschlüssel
-   $R_3(\underline{C,D},E,F)$ \# $CD$ ist Primärschlüssel (Die Elemente dieser [[Relation]]sind zwar schon durch $R_1$ und $R_2$ gegeben, jedoch muss zur Abhängigkeitserhaltung diese weiterhin aufgeführt werden, es dürfte nur entfernt werden, wenn eine Relation vollends in einer anderen enthalten wäre. Dies ist jedoch nicht möglich, da diese Fälle vorher durch die Links- und Rechtsreduktion entfernt wurden.)

### Hinzufügen einer Relation 

Nun muss durch Hinzunahme einer Relation eine Beziehung zwischen $R_1$, $R_2$ und $R_3$ hergestellt werden. Das wird durch eine Relation $R_4$ ermöglicht, die nur den Ursprungsschlüssel $AF$ enthält (beachte, dass $AF^+=\{A,B,C,D,E,F\}$ ist). Wir erhalten ein Schema in der 3. Normalform wie folgt:

-   $R_1(\underline{A},B,D,E)$
-   $R_2(B,C,D,\underline{F})$
-   $R_3(\underline{C},\underline{D},E,F)$
-   $R_4(\underline{A},\underline{F})$, wobei $A$ und $F$ jeweils Fremd[[schlüssel]] darstellen und zusammengenommen den Primärschlüssel von $R_4$ erzeugen.


## VL

*Synthesealgorithmus* wird verwendet um beliebiges Relationenschema $R$ mit [[Funktionale Abhängigkeit]]en $F$ in Relationen $𝑅_1, … , 𝑅_𝑛$ zu zerlegen für die gilt: 
- $𝑅_1, … , 𝑅_𝑛$ ist eine verlustlose Zerlegung von $R$ 
- $𝑅_1, … , 𝑅_𝑛$ ist abhängigkeitserhaltend 
- $𝑅_1, … , 𝑅_𝑛$ sind alle in [[DB-Normalform#^582a55|3. Normalform]]

##### Schritt 1 – kanonische Überdeckung $𝑭_𝒄$ zu $𝑭$ 

a) **Linksreduktion**: 
	Prüfe für jede $𝑋 → 𝑌 ∈ 𝐹$: 
		Prüfe für jedes $𝐴 ∈ 𝑋:$
			$𝑌 ⊆ \operatorname{AttrHuelle} (𝐹, 𝑋 − 𝐴)$ 

Wenn obiges gilt, ist $A$ in $X$ überflüssig und kann aus $X$ entfernt werden

 $\Rightarrow$ Aus $𝑋 → 𝑌$ wird $(𝑋 − 𝐴) → 𝑌$

b) **Rechtsreduktion**: 
	Prüfe für jede (*linksreduzierte*) $𝑋 → 𝑌 ∈ 𝐹$ : 
		Prüfe für jedes $B ∈ Y$ : 
			$B ⊆ \operatorname{AttrHuelle} ((𝐹 − (𝑋 → 𝑌) ∪ (𝑋 → (𝑌 − 𝐵 )), 𝑋)$ 

$(𝐹 − (𝑋 → 𝑌)) ∪ (𝑋 → (𝑌 − 𝐵))$ bedeutet: $𝑋 → 𝑌$ wird ersetzt durch $𝑋 → (𝑌 − 𝐵)$ 

Wenn obiges gilt, ist $B$ auf der rechten Seite überflüssig 

$\Rightarrow$ Aus $𝑋 → 𝑌$ wird $X → (𝑌 − 𝐵)$

c) **Entferne** alle funktionalen Abhängigkeiten (FD) mit leere rechten Seite also: 
	$𝑋 → \{\}$

d) **Fasse** alle FDs mit gleicher linken Seite zusammen 
	Aus $𝑋 → 𝑌_1, … , 𝑋 → 𝑌_𝑛$ wird $𝑋 → (𝑌_1 ∪ ⋯ ∪ 𝑌_𝑛)$

##### Schritt 2 – Erzeuge Relationenschemas aus $𝑭_c$

Für jede FD $𝑋 → 𝑌 ∈ 𝐹_𝑐$ : 
- Erzeuge Relationenschema $𝑅_𝑋 ≔ 𝑋 ∪ 𝑌$ 
- Ordne $𝑅_𝑋$ die FDs $𝐹_𝑋 ≔ \{X^′ → Y^′ ∈ 𝐹𝑐 \:|\: 𝑋^′ ∪ 𝑌^′ ∈ 𝑅_𝑋 \}$ 
- Schlüssel sind alle Attribute aus $𝑋$ 

##### Schritt 3 – Rekonstruiere einen Schlüsselkandidaten

Falls eines der in Schritt 2 erzeugten Schemata eine Schlüsselkandidaten von $R$ bezüglich $𝐹_𝑐$ enthält, ist nichts zu tun 

Wenn nicht: 
	Wähle einen [[Schlüssel]]kandidaten $𝑆 ⊆ 𝑅$ aus und definiere folgendes Schema: 
		$𝑅_𝑆 ≔ 𝑆 mit 𝐹_𝑆 ≔ \{\}$

##### Schritt 4 – Eliminiere überflüssige Relationen

Eliminiere diejenigen Schemata $𝑅_𝑋$, die in einem anderen Relationenschema $𝑅_{𝑋^′}$ enthalten sind, d.h. 
	$𝑅_𝑋 ⊆ 𝑅_{𝑋^′}$ 

###### Beispiel: 

![[DBS Skript.pdf#page=298|DBS Skript, page 298]]

