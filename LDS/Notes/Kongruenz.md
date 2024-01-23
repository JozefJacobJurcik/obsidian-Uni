---
aliases: congruent
klausur: 1
---

Die Kongruenz ist eine Beziehung zwischen ganzen Zahlen. Man nennt zwei ganze Zahlen $a$ und $b$ *kongruent* [[modulo]] $m$  (= eine weitere Zahl), wenn sie bei der Division durch $m$ beide denselben Rest haben. Das ist genau dann der Fall, wenn sie sich um ein ganzzahliges Vielfaches von $m$ unterscheiden. Stimmen die Reste hingegen nicht überein, so nennt man die Zahlen *inkongruent* [[modulo]] $m$. Jede Kongruenz modulo einer ganzen Zahl ist eine Kongruenzrelation auf dem Ring der ganzen Zahlen

>[!tip] Lemma 
>Für alle $a, b, c, d, m ∈ \mathbb Z$ und $m ≥ 2$ gilt:
> 
>Sind $a ≡ b \quad(mod \:\:m)$ und $c ≡ d \quad(mod\:\: m)$ 
>Dann sind auch:
>
>$a + c ≡ b + d \quad(mod\:\: m)$ und $a · c ≡ b · d \quad (mod\:\: m)$

Ist  $a + c ≡ b + c \:\:\:\:(mod\:\: m)$    dann auch    $a ≡ b \:\:\:\:(mod\:\: m)$

>[!tip]  Lemma 
>Für alle  $a, b, c, m ∈ \mathbb Z$ mit $m ≥ 2$ und [[ggT]]$(c, m) = 1$ gilt: 
>Ist $a · c ≡ b · c\quad (mod\:\: m)$   , dann auch   $a ≡ b \quad(mod\:\: m)$.

### Lösen von Kongruenzen

>[!tip] Lemma 
>Für $a, b, m ∈ \mathbb Z$ mit $m ≥ 2$ hat die *Kongruenz* $a · x ≡ b \quad (mod \:\:m)$ genau dann eine Lösung $x ∈ \mathbb Z_m\:$, wenn [[ggT]]$(a, m) = 1$ ist.

Speziell für  $b = 1$: Lösung von   $ax ≡ 1 \quad(mod \:\:m$)   ist Inverses von $a$ [[modulo]] $m$.

>[!info] Theorem (Chinesischer Restessatz) 
>Seien $b_1, . . . , b_k ∈ \mathbb N$ und $m_1, . . . , m_k ∈ \mathbb N$ mit 
>[[ggT]]$(m_i , m_j) = 1$ für  $i \ne j$ und sei $m = m_1 · . . . · m_k$ . 
>Dann existiert genau ein $x ∈ \mathbb Z_m\:$ mit $x ≡ b_i \quad (mod \:\:m_i)$ für $i = 1, . . . , k$.

>[!info] Für Polynome gilt: 
>$a(x) ≡ b(x)\quad (\operatorname{mod}\: m(x))\quad$   wenn   $\quad m(x)$   teilt   $a(x) − b(x)$
>also für multiplikative inverse in endlichen Körpern gilt:
>$a(x) \cdot a^{-1}(x) - 1 ≡ 0  \quad \operatorname{mod}\: m(x)$



##### Finden einer Lösung
Eine Lösung $x$ kann wie folgt ermittelt werden: 
Für jedes $i$ sind die Zahlen $m_i$ und $M_{i}:=M/m_{i}$ teilerfremd, also kann man z. B. mit dem [[erweiterte Euklidische Algorithmus]] zwei ganze Zahlen $r_i$ und $s_i$ finden, so dass

$r_{i}\cdot m_{i}+s_{i}\cdot M_{i}=1$
Setze $e_{i}:=s_{i}\cdot M_{i}$ dann gilt:

${\displaystyle {\begin{aligned}e_{i}&\equiv 1{\pmod {m_{i}}}\\e_{i}&\equiv 0{\pmod {m_{j}}},\ j\neq i\end{aligned}}}$

Die Zahl

$x:=\sum _{{i=1}}^{n}a_{i}e_{i}$ 

ist dann eine Lösung der simultanen Kongruenz.

![[Kleiner Satz von Fermat]]
