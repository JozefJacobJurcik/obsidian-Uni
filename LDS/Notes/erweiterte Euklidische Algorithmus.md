---
tags: algorithm, math
---

Der Algorithmus berechnet für $m, n ∈ \mathbb N$ mit $m ≤ n$ Zahlen $s,t ∈ \mathbb Z$ mit [[ggT]]$(m, n) = sm + tn$.

```Pseudocode
Eingabe: m,n ∈ N mit m ≤ n
Ausgabe: s,t ∈ Z mit ggT(m,n) = sm + tn

ErwEuklid(m,n)
	if m | n then
		return (1 , 0)
	else 
		(s′ , t′) := ErwEuklid(n mod m,m)
		s = t′ − s′ ⌊n/m⌋ 
		t = s′ 
		return (s,t)
```

```Python
# Python - extended Euclidean algorithm

def extended_gcd(a, b):
    if a == 0:
        return b, 0, 1
    else:
        gcd, x, y = extended_gcd(b % a, a)
        return gcd, y - (b // a) * x, x
        
if __name__ == '__main__':
    gcd, x, y = extended_gcd(30, 50)
    print('The GCD is', gcd)
    print(f'x = {x}, y = {y}')
```
