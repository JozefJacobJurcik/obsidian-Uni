---
aliases: Polynomial division
klausur: 1
---

#math #algorithm

Das Verfahren funktioniert für Polynome mit ganzzahligen Koeffizienten genau so wie die *schriftliche Division* ganzer Zahlen mit Rest und kann mit dem gleichen Schema (Verfahren, Vorgehensweise) gelöst werden. Hier werden die einzelnen Schritte am Beispiel
$$\frac{p(x)}{q(x)} ={\frac {4\cdot x^{5}-x^{4}+2\cdot x^{3}+x^{2}-1}{x^{2}+1}}$$
erläutert:

Wie bei der Division ganzer Zahlen wird zuerst der *Summand höchsten Grades* des Polynoms $p$ eliminiert. 

Dazu wird zunächst der *Summand höchsten Grades von* $p$ durch den *Summanden höchsten Grades von* $q$ dividiert. Das Ergebnis ist  $\frac {4x^{5}}{x^{2}}=4x^{3}$  . *Danach wird $q$  mit $4x^3$ multipliziert und von $p$ subtrahiert.
$$\displaystyle {\begin{matrix}(4x^{5}&-x^{4}&+2x^{3}&+x^{2}&-1)&:&(x^{2}&+1)&=&4x^{3}+{\frac {-x^{4}-2x^{3}+x^{2}-1}{x^{2}+1}}\\{\underline {-4x^{5}}}&&{\underline {-4x^{3}}}\\&-x^{4}&-2x^{3}\end{matrix}}$$ 

Es bleibt der Rest  $-x^{4}-2x^{3}+x^{2}-1$ . Sein *Grad* ist nicht kleiner als der des *Divisors*.

Im nächsten Schritt wird von diesem Rest der *Summand höchsten Grades* eliminiert, bis in mehreren solchen Schritten ein Rest entsteht (hier: $2 x − 3$ ), der nicht mehr eliminiert werden kann, weil sein Grad kleiner als der Grad des Divisors $q$ ist.

$$\displaystyle {\begin{array}{rrrrl}(-x^{4}&-2x^{3}&+x^{2}&&-1)&:&(x^{2}&&+1)=-x^{2}&-2x&+2&+{\frac {2x-3}{x^{2}+1}}\\{\underline {+x^{4}}}&&{\underline {+x^{2}}}\\&-2x^{3}&+2x^{2}\\&{\underline {+2x^{3}}}&&{\underline {+2x}}\\&&+2x^{2}&+2x\\&&{\underline {-2x^{2}}}&&{\underline {-2}}\\&&&+2x&-3\end{array}}$$

### Algorithmus

```BASIC
For i = GradZ - GradN To 0 Step -1
    Quotient(i) = Zähler(i + GradN) / Nenner(GradN)
    For j = GradN To 0 Step -1
        Zähler(i + j) = Zähler(i + j) - Nenner(j) * Quotient(i)
    Next j
Next i
For j = GradN - 1 To 0 Step -1
    Rest(j) = Zähler(j)
Next j
```

Die Variable `Zähler()` ist ein Feld (Array), welches die Koeffizienten des Zählerpolynoms enthält, so dass `Zähler(i)` den Koeffizienten der Potenz $x^i$ enthält. Entsprechend ist `Nenner()` ein weiteres Feld, welches in gleicher Art die Koeffizienten des Nennerpolynoms enthält. Das Ergebnis sind zwei Polynome, welche in `Quotient()` und `Rest()` ausgegeben werden. Die Variablen `GradN` und `GradZ` enthalten den jeweiligen Polynomgrad von Zähler und Nenner.

In einem optimierten Programm könnte man die innere Schleife von `0` bis `GradN-1` laufen lassen und die Ergebnisse in `Zähler()` zurückschreiben, so dass die Variablen `Quotient()` und `Rest()` entfallen würden. Der Einfachheit halber wurde hier darauf verzichtet.