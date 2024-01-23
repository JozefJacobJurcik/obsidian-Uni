---
aliases: modulo multiplikativ Inverse
---

A modular multiplicative inverse of an integer $a$ is an integer $x$ such that the product $ax$ is [[Kongruenz|congruent]] to 1 with respect to the modulus $m$. In the standard notation of modular arithmetic this congruence is written as
$$ax \equiv 1 \pmod{m}$$
which is the shorthand way of writing the statement that $m$ divides (evenly) the quantity $ax − 1$, or, put another way, the remainder after dividing $ax$ by the integer $m$ is $1$. If $a$ does have an inverse [[modulo]] $m$, then there are an infinite number of solutions of this congruence, which form a congruence class with respect to this modulus. Furthermore, any integer that is congruent to a (i.e., in a's congruence class) has any element of $x$'s congruence class as a modular multiplicative inverse. Using the notation of ${\displaystyle {\overline {w}}}$ to indicate the congruence class containing $w$, this can be expressed by saying that the modulo multiplicative inverse of the congruence class ${\overline {a}}$ is the congruence class  ${\overline {x}}$ such that:
$${\displaystyle {\overline {a}}\cdot _{m}{\overline {x}}={\overline {1}},}$$
where the symbol ${\displaystyle \cdot _{m}}$ denotes the multiplication of equivalence classes [[modulo]] $m$. Written in this way, the analogy with the usual concept of a multiplicative inverse in the set of rational or real numbers is clearly represented, replacing the numbers by congruence classes and altering the binary operation appropriately.

As with the analogous operation on the real numbers, a fundamental use of this operation is in solving, when possible, linear congruences of the form
$${\displaystyle ax\equiv b{\pmod {m}}}$$
Finding modular multiplicative inverses also has practical applications in the field of cryptography, e.g. public-key cryptography and the [[RSA]] algorithm. A benefit for the computer implementation of these applications is that there exists a very fast algorithm (the [[erweiterte Euklidische Algorithmus|extended Euclidean algorithm]]) that can be used for the calculation of modular multiplicative inverses. 