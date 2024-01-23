---
aliases: eulersche Funktion, Eulersche φ-Funktion, 
---

Die eulersche Phi-Funktion  ist eine zahlentheoretische [[Funktion]]. Sie gibt für jede positive natürliche Zahl $n$ an, wie viele zu $n$ [[Teilerfremdheit|Teilerfremd]]e positive natürliche Zahlen es gibt, die nicht größer als $n$ sind.

Ihr Funktionswert $\varphi(n)$ ist gleich der Anzahl der zu $n$ teilerfremden Reste modulo $n$. Für $n > 1$ liegt er im Bereich ${\displaystyle 1\leq \varphi (n)<n}$ . 

### Definition

Die Phi-Funktion ist definiert durch ${\displaystyle \varphi \colon \mathbb {N} ^{+}\to \mathbb {N} ^{+}}$ und
$${\displaystyle \varphi (n)\;:=\;{\Big |}\{a\in \mathbb {N} \,\mid \,1\leq a\leq n\land \operatorname {ggT} (a,n)=1\}{\Big |}}$$
Dabei bezeichnet $\operatorname {ggT}(a,n)$ den [[ggT|größte gemeinsame Teiler]] von $a$ und $n$ .

Eine andere, trivialerweise äquivalente, Schreibweise ist die Darstellung als Summe:
$${\displaystyle \varphi (n)\;=\;\sum \limits _{\overset {1\leq a\leq n}{\operatorname {ggT} (a,n)=1}}1}$$

### Berechnung

##### Primzahlen
Da eine Primzahl $p$ nur durch 1 und sich selbst teilbar ist, ist sie zu den Zahlen 1 bis $p-1$ [[Teilerfremdheit|Teilerfremd]]. Weil sie größer als 1 ist, ist sie außerdem nicht zu sich selbst teilerfremd. Es gilt daher
$${\displaystyle \varphi (p)=p-1.}$$
