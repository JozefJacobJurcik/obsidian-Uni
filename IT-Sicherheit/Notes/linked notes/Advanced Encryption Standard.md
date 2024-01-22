---
aliases: AES, Rijndael
---

## Description of the ciphers

AES is based on a design principle known as a *substitution–permutation network*, and is efficient in both software and hardware. Unlike its predecessor [[Data Encryption Standard|DES]], AES does not use a [[Feistel cipher]] network. AES is a variant of Rijndael, with a *fixed block size of 128 bits*, and a key size of *128, 192, or 256* bits. By contrast, Rijndael per se is specified with block and key sizes that may be any multiple of 32 bits, with a minimum of 128 and a maximum of 256 bits. Most AES calculations are done in a particular finite field.

AES operates on a 4 × 4 column-major order array of 16 bytes $b_0, b1, ..., b15$ termed the state:

$${\displaystyle {\begin{bmatrix}b_{0}&b_{4}&b_{8}&b_{12}\\b_{1}&b_{5}&b_{9}&b_{13}\\b_{2}&b_{6}&b_{10}&b_{14}\\b_{3}&b_{7}&b_{11}&b_{15}\end{bmatrix}}}$$

The key size used for an AES cipher specifies the number of transformation rounds that convert the input, called the [[plaintext]], into the final output, called the [[ciphertext]]. The number of rounds are as follows:

 - 10 rounds for 128-bit keys.
 - 12 rounds for 192-bit keys.
 - 14 rounds for 256-bit keys.

Each round consists of several processing steps, including one that depends on the encryption key itself. A set of reverse rounds are applied to transform ciphertext back into the original plaintext using the same encryption key.

### High-level description of the algorithm

1. `KeyExpansion` – round keys are derived from the cipher key using the [[AES key schedule]]. AES requires a separate 128-bit round key block for each round plus one more.
2. Initial round key addition:
	`AddRoundKey` – each byte of the state is combined with a byte of the round key using **bitwise** `xor`.
3. 9, 11 or 13 rounds:
	1. `SubBytes` – a non-linear substitution step where each byte is replaced with another according to a lookup table - [[Rijndael S-box]].
	2. `ShiftRows` – a transposition step where the last three rows of the state are shifted cyclically a certain number of steps.
	3. `MixColumns` – a linear mixing operation which operates on the columns of the state, combining the four bytes in each column.
	4. `AddRoundKey`
4. Final round (making 10, 12 or 14 rounds in total):
	`SubBytes`
	`ShiftRows`
	`AddRoundKey`

##### The `SubBytes` step
In the `SubBytes` step, each byte ${\displaystyle a_{i,j}}$ in the state array is replaced with a `SubByte` ${\displaystyle S(a_{i,j})}$ using an 8-bit substitution box ([[Rijndael S-box]]). Note that before round 0, the *state* array is simply the [[plaintext]]/input. This operation provides the non-linearity in the cipher. The S-box used is derived from the multiplicative inverse over $GF(2^8)$, known to have good non-linearity properties. To avoid attacks based on simple algebraic properties, the S-box is constructed by combining the inverse function with an invertible [[affine transformation]]. The S-box is also chosen to avoid any fixed points (and so is a derangement), ${\displaystyle S(a_{i,j})\neq a_{i,j}}$ , and also any opposite fixed points, i.e., ${\displaystyle S(a_{i,j})\oplus a_{i,j}\neq {\text{FF}}_{16}}$. While performing the decryption, the `InvSubBytes` step (the inverse of `SubBytes`) is used, which requires first taking the inverse of the affine transformation and then finding the multiplicative inverse.

![[Pasted image 20240122000621.png]]
##### The `ShiftRows` step
The `ShiftRows` step operates on the rows of the state; it cyclically shifts the bytes in each row by a certain offset. For *AES*, the first row is left unchanged. Each byte of the second row is shifted one to the left. Similarly, the third and fourth rows are shifted by offsets of two and three respectively. In this way, each column of the output state of the `ShiftRows` step is composed of bytes from each column of the input state. The importance of this step is to avoid the columns being encrypted independently, in which case AES would degenerate into four independent block ciphers.

![[Pasted image 20240122000848.png]]

##### The `MixColumns` step
In the `MixColumns` step, the four bytes of each column of the state are combined using an invertible linear transformation. The `MixColumns` function takes four bytes as input and outputs four bytes, where each input byte affects all four output bytes. Together with `ShiftRows`, `MixColumns` provides [[diffusion]] in the cipher.

During this operation, each column is transformed using a fixed matrix (matrix left-multiplied by column gives new value of column in the state):
$${\displaystyle {\begin{bmatrix}b_{0,j}\\b_{1,j}\\b_{2,j}\\b_{3,j}\end{bmatrix}}={\begin{bmatrix}2&3&1&1\\1&2&3&1\\1&1&2&3\\3&1&1&2\end{bmatrix}}{\begin{bmatrix}a_{0,j}\\a_{1,j}\\a_{2,j}\\a_{3,j}\end{bmatrix}}\qquad 0\leq j\leq 3}$$

Matrix multiplication is composed of multiplication and addition of the entries. Entries are bytes treated as coefficients of [[Polynome|polynomial]] of order ${\displaystyle x^{7}}$. Addition is simply `XOR`. Multiplication is [[modulo]] [[irreduzibles Polynom|irreducible polynomial]]  ${\displaystyle x^{8}+x^{4}+x^{3}+x+1}$. If processed bit by bit, then, after shifting, a conditional `XOR` with $1B_{16}$ should be performed if the shifted value is larger than $FF_{16}$ (overflow must be corrected by subtraction of generating polynomial). These are special cases of the usual multiplication in $GF(2^8)$.

In more general sense, each column is treated as a polynomial over $GF(2^8)$ and is then multiplied modulo ${\displaystyle {01}_{16}\cdot z^{4}+{01}_{16}}$ with a fixed polynomial ${\displaystyle c(z)={03}_{16}\cdot z^{3}+{01}_{16}\cdot z^{2}+{01}_{16}\cdot z+{02}_{16}}$ . The coefficients are displayed in their hexadecimal equivalent of the binary representation of bit polynomials from ${\displaystyle \operatorname {GF} (2)[x]}$ . The `MixColumns` step can also be viewed as a multiplication by the shown particular MDS matrix in the finite field $GF(2^8)$. 

![[Pasted image 20240122001808.png]]

##### The `AddRoundKey`
In the `AddRoundKey` step, the *subkey* is combined with the state. For each round, a subkey is derived from the main key using Rijndael's [[AES key schedule|key schedule]]; each subkey is the same size as the state. The subkey is added by combining of the state with the corresponding byte of the subkey using bitwise `XOR`. 

![[Pasted image 20240122002044.png]]

### Design-Kriterien
- Design-Kriterien mussten offen gelegt werden 
- Abschätzung und Stellungnahme zur Widerstandsfähigkeit gegen bekannte Angriffe 

- Schlüsselauswahl mit nichtlinearer Durchmischung wegen Verwendung der S-Box; damit widerstandsfähig gegen folgende Angriffe: 
	- Kryptanalyst kennt Teile des Schlüssels und versucht, den Rest zu berechnen. 
	- Zwei ähnliche Schlüssel haben keine große Zahl von gemeinsamen Rundenschlüsseln. 
	- Rundenkonstante verhindert Symmetrien im Verschlüsselungsprozess; jede Runde ist anders.

- Keine [[Feistel cipher]], sondern deutlich höhere Diffusion: nach 2 Runden hängen 50% Output-Bits von jedem Input-Bit ab. 
- Algebraische S-Box-Konstruktion; offengelegt; in hohem Maße nichtlinear. 
	- Damit stabil gegen *lineare und differentielle Kryptoanalyse*. 
- `ShiftRow` wurde eingefügt, um zwei neue Angriffsarten zu verhindern (truncated differentials und Square attack). 
- `MixColumn` für hohe Diffusion; Änderung in einem Input-Byte verursacht Änderung in allen Output-Bytes 
- Auswahl von 10 Runden: 
	Bei AES-128 mit bis zu 7 Runden sind Angriffe bekannt, die besser sind als Brute Force. Bei mehr als 7 Runden sind keine solchen Angriffe bekannt. D.h. 3 Runden „Reserve“, die zudem sehr leicht erweitert werden können.

### Einsatz von AES
Aufgrund von Standardisierung und Qualität sehr weit verbreitet 
Beispiele: 
- In der Vorlesung behandelte Protokolle: 
	- WLAN-Verschlüsselung mit WPA2/3 
	- Remote-Zugriff auf Rechner mit SSH
	- Verschlüsselung auf OSI-Schicht 3: IPsec 
- Weitere Protokolle und Produkte: 
	- Festplattenverschlüsselung z.B. mit Apple FileVault, Windows EFS, TrueCrypt 
	- Skype 
	- Kompressions-/Archivierungsprogramme (ZIP, RAR, ...) 
	- viele viele mehr...