---
klausur: 1
---

### Ziehen von Elementen aus einer Menge

**Frage:** Wie viele Möglichkeiten gibt es, k Elemente aus einer n-elementigen Menge auszuwählen?

**Zwei Unterscheidungen:**

- mit oder ohne **Zurücklegen**, d.h. sind *Wiederholungen* möglich
- **geordnet** oder **ungeordnet**, d.h. spielt die *Reihenfolge* eine Rolle?

$\Longrightarrow$ 4 verschiedene Zählprobleme.

###### Beispiel
Beispiel: Ziehen von k = 2 Elementen aus {1, 2, 3}, also n = 3. 

- Geordnet, mit Zurücklegen: 9 Möglichkeiten: (1, 1), (1, 2), (1, 3), (2, 1), (2, 2), (2, 3), (3, 1), (3, 2), (3, 3) 

- Geordnet, ohne Zurücklegen: 6 Möglichkeiten: (1, 2), (1, 3), (2, 1), (2, 3), (3, 1), (3, 2) 

- Ungeordnet, mit Zurücklegen: 6 Möglichkeiten: {1, 1}, {1, 2}, {1, 3}, {2, 2}, {2, 3}, {3, 3} 

- Ungeordnet, ohne Zurücklegen: 3 Möglichkeiten: {1, 2}, {1, 3}, {2, 3}

### Anzahlformeln
**Frage:** Wie viele Möglichkeiten gibt es, k Elemente aus einer n-elementigen Menge auszuwählen?

*Geordnet, mit Zurücklegen*:  
- k-mal Ziehen, jedes mal n Möglichkeiten 
		$\rightarrow$ insgesamt $n^k$

*Geordnet, ohne Zurücklegen*:  
- k-mal Ziehen, Anzahl Möglichkeiten nimmt jedes mal um 1 ab
		$\rightarrow$  $n · (n − 1) · . . . · (n − k + 1) = \frac {n!}{(n − k)!}$

*Ungeordnet, ohne Zurücklegen*:
- wie oben, aber jede Auswahl wird dort k! mal gezählt 
		$\rightarrow$  $\frac{n · (n − 1) · . . . · (n − k + 1)}{k!} = \frac {n!}{(n − k)!\:k!} = {n\choose k} \rightarrow$ [[Binomialkoeffizient]]

*Ungeordnet, mit Zurücklegen*:
- [[Kombination mit Wiederholung]]
		$\rightarrow \: {\displaystyle {\frac {(n+k-1)!}{(n-1)!\cdot k!}}={\binom {n+k-1}{k}}={\binom {n+k-1}{n-1}}=\left(\!\!{\binom {n}{k}}\!\!\right)}$

### [[Binomialkoeffizient]]

### Das [[Schubfachprinzip]] 
