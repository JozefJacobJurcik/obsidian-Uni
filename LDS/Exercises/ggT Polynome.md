---
klausur: 1
---


If we want to find the [[ggT]] of 2 polynomials $f(x)$ and $g(x)$ we need to first use the [[Polynomdivision|Polynomial division]], dividend being the polynomial with a higher deg() (here arbitrarily $f(x)$). If there is no remainder the [[ggT]]  is simply $g(x)$. After the [[Polynomdivision|Polynomial division]] it should look like this:
$$f(x) : g(x) = p_1(x) + \frac{r_1(x)}{g(x)}$$
$p(x)$ is a polynomial that would be the result of a floor division and $r_1(x)$ is the *remainder* of this division. Now repeat the [[Polynomdivision|Polynomial division]] with the dividend being $g(x)$ and the divisor $r_1(x)$.
$$g(x) : r_1(x) = p_2(x) + \frac{r_2(x)}{r_1(x)}$$
Repeat this process until there is no remainder and the polynomial $p_n(x)$ will be the [[ggT]].
$$r_{n-1}(x) : r_n(x) = p_n(x)$$

###### Beispiel:

$\operatorname{ggT}(x^2 + 3x + 2,\:\: x^5 + x^3 + x^2 + 3x + 2)$ in $\mathbb Z_5[x]$

$x^5 + x^3 + x^2 + 3x + 2 \quad \operatorname{mod} \quad x^2 + 3x + 2$

| |$x^5$|$x^4$|$x^3$|$x^2$|$x^1$|$x^0$| |
|---|---|---|---|---|---|----|----|
||1|0|1|1|3|2||
|-|1|3|2||||$= x^3 \cdot (x^2+3x+2)$|
|||||||||
|||2|4|1|3|2||
|-||2|1|4|||$=2x^2 \cdot (x^2+3x+2)$|
|||||||||
||||3|2|3|2||
|-|||3|4|1||$=3x \cdot (x^2+3x+2)$|
|||||||||
|||||3|2|2||
|-||||3|4|1|$= 3 \cdot (x^2+3x+2)$|
|||||||||
||||||3|1||

$x^2 + 3x + 2 \quad \operatorname{mod} \quad 3x+1$

| |$x^2$|$x^1$|$x^0$| |
|---|---|---|---|---|
||1|3|2||
|-|1|2||$=2x \cdot (3x+1)$|
||||||
|||1|2||
|-||1|2| $=2 \cdot (3x+1)$|
||||||
||||0||

$\hookrightarrow$ $\operatorname{ggT}(x^2 + 3x + 2,\:\: x^5 + x^3 + x^2 + 3x + 2) = 3x+1$ in $\mathbb Z_5[x]$

**btw:** alle zulässigen Lösungen sind: $x + 2,\: 2x + 4,\: 3x + 1,\: 4x + 3$ 