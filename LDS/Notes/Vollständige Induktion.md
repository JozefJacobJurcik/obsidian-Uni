---
modul: "LDS"
---
#math #beweis #def

Um zu zeigen, dass $A(n)$ für alle $n$ ∈ $\mathbb N$ gilt, zeige:

- **Induktionsanfang**  $A(1)$ gilt

- **Induktionsschritt** 
	- $\forall\: n \in \mathbb N$ gilt $\rightarrow$ wenn $A(n)$ gilt, dann auch $A(n + 1)$
		- *d.h.* zeige: für beliebiges  $n ∈ \mathbb N$ gilt $A(n + 1)$ unter Verwendung der **Induktionshypothese** $A(n)$ 

	- $\forall\: n \in \mathbb N$ gilt $\rightarrow$ wenn $A(k)$ für alle  $k ≤ n$ gilt, dann auch $A(n + 1)$
		- *d.h.* zeige für beliebiges  $n ∈ N$ gilt $A(n + 1)$ unter Verwendung der **Induktionshypothese** $A(k)$ für alle  $k ≤ n$


### Beispiel 1
$$\sum_{i=1}^n (2i -1) = n^2 $$
**Induktionsanfang**: Für $n = 1$ beträgt die linke Seite $2 · 1 − 1 = 1$ ebenso wie die rechte Seite. Damit stimmt die Aussage für $n = 1$ und der *Induktionsanfang ist erledigt*.

**Induktionsschritt:** Es gelte die Aussage für ein $n ∈ \mathbb N$, d.h. es gelte $\sum_{i=1}^n (2i-1) = n^2$. Zu zeigen ist die Aussage für $n + 1$, also
$$\sum_{i=1}^{n+1} (2i -1) = (n+1)^2 $$
Wir verifzieren:
$$\sum_{i=1}^{n+1} (2i -1) = \sum_{i=1}^{n} (2i -1) + (2(n+1)-1) = n^2 +2n +1 =(n+1)^2$$
Folglich stimmt die Aussage für $n + 1$. Der Induktionsbeweis ist damit durchgeführt, d.h. wir haben bewiesen, dass die Behauptung für alle $n ∈ \mathbb N$ gilt.

### Beispiel 2

$3^{2n+4}-2^{n-1}$ ist durch 7 teilbar

**Induktionsanfang:** Es gilt $3^{2·1+4} − 2^{1−1} = 728 = 7 · 104$, d.h. die Behauptung für $n = 1$ stimmt.

**Induktionsschritt:** Wir nehmen an, die Aussage gelte für ein $n ∈ \mathbb N$, also $3^{2n+4}-2^{n-1} = 7m$ für ein $m ∈ \mathbb N$. Dann folgt:

$3^{2(n+1)+4}-2^{(n+1)-1} = 3^{2n+4} \cdot 9 -2^{n}$
		$= (7m+2^{n-1}) \cdot 9 -2^n$
		= $7 \cdot 9m + 9\cdot 2^{n-1}-2^n$
		$= 7\cdot 9 m + (9-2)\cdot2^{n-1}$
		$= 7 \cdot (9m+2^{n-1})$

Da $9m+2^{n-1}$ eine natürliche Zahl ist, ist $3^{2(n+1)+4}-2^{(n+1)-1}$ durch 7 teilbar und der **Induktionsschritt** ist *vollzogen*.

### Beispiel 3

$$\sum_{i=1}^n \frac{1}{(3i-2)(3i+1)}= \frac{n}{3n+1}$$
**Induktionsanfang:** Für $n = 1$ beträgt die linke Seite $\frac{1}{(3-2)(3+1)}=\frac{1}{4}$ ebenso wie die rechte Seite, d.h. die Behauptung stimmt für $n = 1$.

**Induktionsschritt:** Wir nehmen an, die Aussage gelte für ein $n ∈ \mathbb N$. Dann folgt:

$$\displaystyle {\begin{matrix} \sum_{i=1}^{n+1} \frac{1}{(3(i-1)+1)(3i+1)} & =\sum_{i=1}^n \frac{1}{(3(i-1)+1)(3i+1)} + \frac{1}{(3n+1)(3n+4)}\\ \\ IH \rightarrow & =\frac{n}{3n+1}+\frac{1}{(3n+1)(3n+4)} \\ \\ & = \frac{n(3n+4)+1}{(3n+1)(3n+4)} = \frac{3n^2+4n+1}{(3n+1)(3n+4)} \\ \\ PD \rightarrow & = \frac{(3n+1)(n+1)}{(3n+1)(3n+4)} \\ \\& =\frac{n+1}{3n+4} =\frac{n+1}{3(n+1)+1} \end{matrix}}$$

IH: Induktionshypothese
PD: [[Polynomdivision]]


