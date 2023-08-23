Eine [[Relation]] *R* ⊆ A × B heißt **Funktion** von A nach B, wenn für alle a ∈ A gilt :
$$|\,\{\, b\in B \, ;\, a R b\,\}\,| = 1$$
### Notation

- f (a) ist das eindeutige b ∈ B mit (a, b) ∈ f 
- f : A → B 
- $f^{−1}$ (b) = { a ∈ A ; f (a) = b }      **Urbild** von b 
- f (A′) = { f (a) ; a ∈ A′ } für A′ ⊆ A 
- $f^{−1}$ (B′) = $\bigcup_{b\in B'}$ $f^{−1}$ (b) = { a ∈ A ; f (a) ∈ B′ } für  B′ ⊆ B

### Eigenschaften von Funktionen
Eine Funktion f : A → B heißt:

- [injektiv](Injektivität.md)
	wenn f ($a_1$) = f ($a_2$) nur gilt, wenn $a_1 = a_2$, 
	also für alle  b ∈ B gilt |$f^{ −1}$ (b)| ≤ 1
- [surjektiv](Surjektivität.md) 
	wenn es für jedes b ∈ B ein a ∈ A gibt mit f (a) = b, also für alle b ∈ B gilt |$f^{−1}$ (b)| ≥ 1 also wenn f (A) = B
- [bijektiv](Bijektivität.md)
	wenn f injektiv und surjektiv ist, 
	also für alle b ∈ B gilt |$f^{−1}$ (b)| = 1
	
Ist |A| = |B| endlich, und f : A → B, so gilt: f ist [injektiv](Injektivität.md) gdw. f ist [surjektiv](Surjektivität.md) gdw. f ist bijektiv
### Funktionskomposition

Seien f : B → C und g : A → B Funktionen. 
Die Komposition f ◦ g : A → C ist definiert durch 
**(f ◦ g)(x) = f (g(x))** für x ∈ A

### Eigenschaften:

- Sind f und g beide [[Injektivität |injektiv]], so ist f ◦ g injektiv.
- Sind f und g beide [[Surjektivität |surjektiv]] , so ist f ◦ g surjektiv.
- Sind f und g beide [[Bijektivität|bijektiv]], so ist f ◦ g bijektiv.

### [[Identitätsfunktion]]
### [[Umkehrfunktion]]
### [[Permutation]]
