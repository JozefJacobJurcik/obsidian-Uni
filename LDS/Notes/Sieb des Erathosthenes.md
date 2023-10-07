---
tags: algorithm, math
---
Algorithmus zur Berechnung der Primzahlen bis $n$ 

```Pseudocode
Liste := [2, 3, 4, . . . , n]
repeat 
	p := erstes unmarkiertes Element der Liste 
	markiere p 
	streiche alle Vielfachen von p 
until p > sqrt(n)
```

**Beispiel:** *2* *3* ~~4~~ *5* ~~6~~ *7* ~~8 9 10~~ *11* ~~12~~ *13* ~~14 15 16~~ *17* ~~18~~ *19* ~~20 21 22~~ *23* ~~24 25 26 27 28~~ *29* ~~30~~
