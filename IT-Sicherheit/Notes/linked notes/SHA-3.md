---
Aliases: Keccak
---

*SHA-3* (Secure Hash Algorithm 3) is the latest member of the Secure Hash Algorithm family of standards, released by [[NIST]] on August 5, 2015. Although part of the same series of standards, SHA-3 is internally different from the [[MD5]]-like structure of SHA-1 and SHA-2.

SHA-3 is a subset of the broader cryptographic primitive family **Keccak**. Keccak's authors have proposed additional uses for the function, not (yet) standardized by NIST, including a stream cipher, an authenticated encryption system, a "tree" hashing scheme for faster hashing on certain architectures, and AEAD ciphers Keyak and Ketje.

Keccak is based on a novel approach called **sponge construction**. Sponge construction is based on a wide random function or random permutation, and allows inputting ("*absorbing*" in sponge terminology) any amount of data, and outputting ("*squeezing*") any amount of data, while acting as a pseudorandom function with regard to all previous inputs. This leads to great flexibility.


## Design

![[Pasted image 20240223203242.png]]

SHA-3 uses the sponge construction, in which data is "absorbed" into the sponge, then the result is "squeezed" out. In the absorbing phase, message blocks are *XORed* into a subset of the state, which is then transformed as a whole using a permutation function $f$. (Calling $f$ a [[permutation]] may be confusing. It is technically a permutation of the state space, thus a permutation of a set with $2^{1600} \approx 4.4 \cdot 10^{481}$ elements, but it does more than merely permute the bits of the state vector.) In the "**squeeze**" phase, output blocks are read from the same subset of the state, alternated with the state transformation function $f$. The size of the part of the state that is written and read is called the "*rate*" (denoted $r$), and the size of the part that is untouched by input/output is called the "*capacity*" (denoted $c$). The capacity determines the security of the scheme. The maximum security level is half the capacity.

Given an input bit string $N$, a padding function $pad$, a permutation function $f$ that operates on bit blocks of width $b$, a rate $r$ and an output length $d$, we have capacity $c = b - r$ and the sponge construction $Z = \text{sponge}[f,pad,r](N,d)$, yielding a bit string $Z$ of length $d$, works as follows:

-   pad the input *N* using the pad function, yielding a padded bit string *P* with a length divisible by $r$ (such that $n = \text{len}(P)/r$ is an integer)
-   break *P* into *n* consecutive *r*-bit pieces *P*$_0$, ..., *P*$_{n−1}$
-   initialize the state *S* to a string of *b* zero bits
-   absorb the input into the state: for each block *P*$_i$ :
    -   extend *P*$_i$ at the end by a string of *c* zero bits, yielding one of length *b*
    -   XOR that with *S*
    -   apply the block permutation *f* to the result, yielding a new state *S*
-   initialize *Z* to be the empty string
-   while the length of *Z* is less than *d*:
    -   append the first *r* bits of *S* to *Z*
    -   if *Z* is still less than *d* bits long, apply *f* to *S*, yielding a new state *S*
-   truncate *Z* to *d* bits

The fact that the internal state *S* contains *c* additional bits of information in addition to what is output to *Z* prevents the [[length extension attacks]] that SHA-2, SHA-1, MD5 are susceptible to.

In SHA-3, the state *S* consists of a array of *w*-bit words (with *w* = 64), *b* = 5 × 5 × *w* = 5 × 5 × 64 = 1600 bits total. Keccak is also defined for smaller power-of-2 word sizes *w* down to 1 bit (total state of 25 bits). Small state sizes can be used to test cryptanalytic attacks, and intermediate state sizes (from 200 bits, to 800 bits) can be used in practical, lightweight applications.

For SHA3-224, SHA3-256, SHA3-384, and SHA3-512 instances, *r* is greater than *d*, so there is no need for additional block permutations in the squeezing phase; the leading *d* bits of the state are the desired hash. However, SHAKE128 and SHAKE256 allow an arbitrary output length, which is useful in applications such as optimal asymmetric encryption padding.

Here is how it works in practice ¯\\\_(ツ)\_/¯ : https://youtu.be/orIgy2MjqrA?si=QAnZo8uoFUEvGxpP

## Keccak: Bewertung 

Innovativer Ansatz: 
- Vermeidet Probleme klassischer Merkle-Damgard-Konstrukte wie [[MD5]]; 
- ist entsprechend aber noch weniger von Kryptanalytikern untersucht. 
- Komplementär zu SHA-2 verwendbar.

Variable Output-Länge 
- ermöglicht flexible Anpassung an jeweiligen Bedarf 
- Gute Eignung als PRNG für Stream Ciphers 

- Effiziente Implementierung in Hard- und Software möglich 

- Konservative Sicherheitsreserve durch große Rundenzahl