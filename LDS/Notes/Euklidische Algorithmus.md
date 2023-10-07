---
tags: algorithm, math
---

Der *Euklidische Algorithmus* bestimmt zu zwei beliebigen natürlichen Zahlen den größten gemeinsamen Teiler ([[ggT]]).

```Pseudocode
Eingabe: m, n ∈ N mit m ≤ n 
Ausgabe: ggT(m, n)

Euklid(m,n) 
	if m | n then
		return m 
	else 
		return Euklid(n mod m,m)
```

```python
a = int(input("What's the first number? "))
b = int(input("What's the second number? ")) 
while 1:
    r=a%b
    if not r:
        break
    a=b
    b=r
print('GCD is:', b)
```

**Die Korrektheit folgt aus dem Folgenden:**
- Sind $m, n ∈ \mathbb N$ mit $m ≤ n$ und $m \nmid n$, so gilt: $ggT(m, n) = ggT(n \: mod \:m, m)$.


![[erweiterte Euklidische Algorithmus]]

