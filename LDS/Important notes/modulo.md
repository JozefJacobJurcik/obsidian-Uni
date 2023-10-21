---
aliases: mod, Ganzzahlige Division mit Rest
klausur: 2
---

Für alle  $a, b ∈ \mathbb Z$ mit $b \ne 0$ gibt es eindeutig bestimmte $q,r ∈ \mathbb Z$ mit $0 ≤ r < |b|$ und $a = q · b + r$ 

*Notation:*  $q = \lfloor\frac{a}{b}\rfloor$ und $r = a \operatorname{mod} b$ 

Für  $a, b ∈ \mathbb Z$ ist *definiert*: 
$b \:|\: a$    gdw.    $a \operatorname{mod} b = 0$    gdw.    $a = q \cdot b$   für ein  $q ∈ \mathbb Z$ 

Jedes $a ∈ \mathbb Z$  mit  $a \:|\: b$ ist ein *Teiler* von $b$. 

Für alle  $a ∈ \mathbb Z$ gilt:
$1 \:|\: a$    und    $a \:|\: a$ 

Auf $\mathbb N$ ist die [[Relation]] | eine [[partielle Ordnung]].

**See also:** [[Restklasse]]

![[Kongruenz]] 

### Modulares Rechnen

>[!tip] Lemma 
>Für alle $a, b, m ∈ \mathbb Z$ und $m ≥ 2$ gilt: 
>- $(a + b)$ mod $m$ = ($a$ mod $m + b$ mod $m$) mod $m$ 
>- $(a · b)$ mod $m$ = ($a$ mod $m · b$ mod $m$) mod $m$

$$-4 \:\operatorname{mod}\: 5 = {\color{Orchid}1}+(-1)5 = {\color{Orchid}1}$$
##### Schnelle Exponentiation:
Berechne $a^b\: mod\: m$ wie folgt:
- First, it is required that the exponent $e$ be converted to binary notation. That is, $e$ can be written as:
$$e=\sum _{i=0}^{n-1}a_{i}2^{i}$$
In such notation, the _length_ of $e$ is $n$ bits. $a_i$ can take the value 0 or 1 for any $i$ such that $0 ≤ i < n$. By definition, $a_{n − 1} = 1$.

The value $b_e$ can then be written as:
$${\displaystyle b^{e}=b^{\left(\sum _{i=0}^{n-1}a_{i}2^{i}\right)}=\prod _{i=0}^{n-1}b^{a_{i}2^{i}}}$$
The solution $c$ is therefore:
$${\displaystyle c\equiv \prod _{i=0}^{n-1}b^{a_{i}2^{i}}{\pmod {m}}}$$

```pseudocode
function modular_pow(base, exponent, modulus) is
    if modulus = 1 then
        return 0
    Assert :: (modulus-1)*(modulus-1) does not overflow
    result := 1
    base := base mod modulus
    while exponent > 0 do
        if (exponent mod 2 == 1) then
            result := (result * base) mod modulus
        exponent := exponent >> 1
        base := (base * base) mod modulus
    return result
```
$\hookrightarrow$ ">>" is *bit shift right* 


$b^e \:\: mod\:\: m$
```lua
function modPow(b, e, m)
  if m == 1 then
    return 0
  else
    local r = 1
    b = b % m
    while e > 0 do
      if e % 2 == 1 then
        r = (r*b) % m
      end
      b = (b*b) % m
      e = e >> 1     --use 'e = math.floor(e / 2)' on Lua 5.2 or older
    end
    return r
  end
end
```

###### Beispiel:
$b=4$ , $e=13$ (1101 in binary), $m = 497$ 

There are four binary digits, so the loop executes four times, with values $a_0 = 1$, $a_1 = 0$, $a_2 = 1$, and $a_3 = 1$ 

- First, initialize the result $R$ to 1. (Lua line 5)

- If $b\geq m$ we use the identity (Lua line 6) $b^e \:\: mod\:\: m =(b \:\: mod\:\:m)^e\:\:mod\:\:m$ 

1.  The first bit is 1 ($a_0 = 1$) , so first set ${\color{red}R} \leftarrow R \cdot \: b \equiv {\color{red}4}$ (mod 479)
	- set $b\leftarrow b^2 \equiv 4^2=16$ (mod 497)

2.  $a_1 = 0$ so do not reset ${\color{red}R}$
	- set ${\color{green}b} \leftarrow b^2 \equiv {\color{green}b^4} =16^2=256$ (mod 497)

3. $a_2 = 1$ so set ${\color{magenta}R} \leftarrow {\color{red}R} \cdot \: {\color{green}b} \equiv {\color{red}4} \cdot {\color{green}b^4} = {\color{magenta}b^5} = 1024\equiv {\color{magenta}30}$ (mod 479)
	- set ${\color{YellowGreen}b} \leftarrow b^2 \equiv {\color{YellowGreen}b^8} =256^2=65,536 \equiv {\color{YellowGreen}429}$ (mod 497)

4. $a_3 = 1$ so set ${\color{cyan}R} \leftarrow {\color{magenta}R} \cdot \: {\color{YellowGreen}b} \equiv {\color{magenta}b^5} \cdot {\color{YellowGreen}b^8}= {\color{cyan}b^{13}} \equiv {\color{magenta}30}\cdot{\color{YellowGreen}429} \equiv {\color{cyan}445}$ (mod 479)

We are done: $R$ is now $4^{13}\equiv 445$ (mod 497)

|$a_i$|R| |b |
|---|---|---|---|
||1||4|
||$\downarrow$|$\swarrow$|$\Downarrow$|
|1|4||16|
||$\downarrow$||$\Downarrow$|
|0|$\downarrow$||256|
||$\downarrow$|$\swarrow$|$\Downarrow$|
|1|30||429|
||$\downarrow$|$\swarrow$||
|1|*445*|||

 