---
aliases: Luby–Rackoff block cipher
---

In cryptography, a *Feistel cipher* (also known as Luby–Rackoff block cipher) is a symmetric structure used in the construction of block ciphers, named after the German-born physicist and cryptographer Horst Feistel, who did pioneering research while working for IBM; it is also commonly known as a *Feistel network*. A large proportion of block ciphers use the scheme, including the US Data Encryption Standard, the Soviet/Russian GOST and the more recent Blowfish and Twofish ciphers. 

In a Feistel cipher, encryption and decryption are very similar operations, and both consist of iteratively running a function called a "round function" a fixed number of times.

### VL:

Bezeichnung für bijektive symmetrische Blockverschlüsselungsverfahren mit typischen Eigenschaften: 
	- Zerlegung des Eingabeblocks in zwei Teile 
	- n Runden mit verschiedenen Rundenschlüsseln 
	- Funktion f muss nicht umkehrbar sein 
	- Alternierende Substitutionen und Permutationen setzen [[Confusion|Konfusion]] und [[Diffusion]] um ([[Avalanche Effekt]] nach Feistel).