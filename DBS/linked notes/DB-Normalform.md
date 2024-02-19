---
aliases: Normalform
---

#### Warum Normalformen?
Redundanzen im DB-Schema erzeugen Anomalien: 
- Änderungs Anomalie – Wenn eine Änderung vergessen wird -> Inkonsistenz 
- Einfüge Anomalie – Einfügen eines partiellen Eintrags evtl. nicht möglich 
- Entfernungs Anomalie – Entfernen des letzten Eintrags löscht ungewollt Informationen

#### Ziele: 
- Vermeidung von Redundanzen und Anomalien 
- Schrittweise Beseitigung funktionaler Abhängigkeiten (außer vom gesamten Schlüssel)

Zerlegen des Schemas in ein äquivalentes Schema ohne Redundanzen und Anomalien = **Normalisierung** 

### Funktionale Abhängigkeit
[[Funktionale Abhängigkeit]]

### Attributnülle
[[Attributhülle]]

## 1. Normalform

- Alle Attribute enthalten atomare Werte (String, Integer, …) und keine Tupel, Listen, usw. 
- In relationalen DB sind nicht-atomare Werte eh nicht erlaubt/möglich 
	-> Relationale DB immer in 1. Normalform

![[Pasted image 20240219001421.png]]

## 2. Normalform

Für jedes Attribut $A$ gilt: 
- $A$ ist prim oder 
- $A$ ist [[Voll funktionale Abhängigkeit|voll funktional abhängig ]] von jedem [[Schlüssel]]kandidaten 

Beseitigung von [[Partiell funktionale Abhängigkeit |partiell funktionalen Abhängigkeiten]]  nicht-primer Attribute vom Schlüssel

- 2. NF kann nur verletzt warden wenn *Schlüssel aus mehr als einem Attribut besteht und wenn nicht-prime Attribute existieren*
##### Transformation in 2. Normalform

1. Erstelle eine neue Relation für jeden partiellen Schlüssel mit seinen Abhängigen Attributen 
2. Attribute, die voll funktional vom Schlüssel abhängig sind, bleiben in der ursprünglichen Relation

**Lieferant**(*LNr*, LName, LStadt, LLand, *Ware*, Preis) 
-> LName, LStadt und LLand hängen nur von LNr ab 
**LieferAdr**(*LNr*, LName, LStadt, Lland) 
-> Preis hängt voll funktional vom Schlüssel ab 
**Lieferung**(*LNr*, *Ware*, Preis)

## 3. Normalform

^582a55

Für alle nicht-trivialen funktionalen Abhängigkeiten $𝑋 → 𝑌$ gilt: 
- $𝑋$ enthält [[Schlüssel]]kandidaten oder 
- $𝑌$ ist prim

Nicht-prime Attribute sind nur von (ganzen) Schlüsselkandidaten funktional abhängig

Beseitigung von funktionalen Abhängigkeiten nicht-primer Attribute untereinander (= transitive Abhängigkeiten)

\3. Normalform setzt die 2. Normalform voraus
##### Transformation in 3. Normalform

1. Erstelle eine neue Relation für alle Nicht-Schlüssel-Attribute und deren funktionalen Abhängigkeiten 
2. Attribute, die voll funktional vom ursprünglichen Schlüssel abhängig und nicht abhängig von Nicht-Schlüssel-Attributen sind, bleiben in der ursprünglichen Relation 

**LieferAdr**(*LNr*, LName, LStadt, LLand) 
-> LLand ist von LStadt funktional abhängig 
**LieferAdr**(*LNr*, LName, LStadt) 
**StadtLand**(*LStadt*, LLand)

#### Synthesealgorithmus

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

## Boyce-Codd Normalform

Für alle nicht-trivialen [[Funktionale Abhängigkeit|funktionalen Abhängigkeiten]] $𝑋 → 𝑌$ gilt: 
- $𝑋$ enthält Schlüsselkandidaten 
- Beseitigt FD unter Attributen, die prim sind, aber nicht vollständig eine Schlüssel bilden 
- BCNF impliziert 3. Normalform 
- Man kann nicht immer eine BCNF-Zerlegen finden, die Abhängigkeiten bewahrt