---
aliases: Normalform
klausur: 2
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
- $A$ ist [[Prime Attribute|prim]] oder 
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

![[Pasted image 20240221190225.png]]
## 3. Normalform

^582a55

Für alle nicht-trivialen funktionalen Abhängigkeiten $𝑋 → 𝑌$ gilt: 
- $𝑋$ enthält [[Schlüssel]]kandidaten oder 
- $𝑌$ ist [[Prime Attribute|prim]]

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

![[Pasted image 20240221190303.png]]
![[Synthesealgorithmus 3. Normalform]]

## Boyce-Codd Normalform

Ein Schema $R$ ist in *Boyce-Codd-Normalform*, wenn für alle nicht-trivialen [[Funktionale Abhängigkeit|funktionalen Abhängigkeiten]] $𝑋 → 𝑌$ gilt: 
	 $𝑋$ enthält [[Schlüssel]]kandidaten von $R$

- Beseitigt FD unter Attributen, die [[Prime Attribute|prim]] sind, aber nicht vollständig eine Schlüssel bilden 
- BCNF impliziert 3. Normalform 
- Man kann nicht immer eine BCNF-Zerlegen finden, die Abhängigkeiten bewahrt

