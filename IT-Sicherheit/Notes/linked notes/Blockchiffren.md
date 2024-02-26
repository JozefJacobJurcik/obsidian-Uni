---
aliases: Block cipher
---

In cryptography, a *block cipher* is a [[deterministic algorithm]] that operates on fixed-length groups of bits, called **blocks**. Block ciphers are the elementary building blocks of many cryptographic protocols. They are ubiquitous in the storage and exchange of data, where such data is secured and authenticated via encryption.

A block cipher uses blocks as an unvarying transformation. Even a secure block cipher is suitable for the encryption of only a single block of data at a time, using a fixed key. A multitude of modes of operation have been designed to allow their repeated use in a secure way to achieve the security goals of [[Vertraulichkeit|Confidentiality]] and [[Authentizität|Authenticity]]. However, block ciphers may also feature as building blocks in other cryptographic protocols, such as universal hash functions and pseudorandom number generators. 
### Blockchiffren (Beispiel: [[Data Encryption Standard|DES]])

- Erwartet Eingabe fester Blocklänge n (meist 64 oder 128 Bit) 
- Nachricht m der Länge $|m|$ wird in $r$ Blöcke der Blocklänge $n$ zerlegt
- Letzter Block hat Länge
- Falls $k < n$ : Auffüllen mit sog. Padding 
- Länge des Padding muss geeignet hinterlegt werden 
- Ciphertext ergibt sich durch Konkatenation der Output-Blöcke

#### Betriebsmodi von Blockchiffren

***Electronic Codebook Mode*** (**ECB**) 
- Jeder Klartext-Block wird einzeln mit demselben Schlüssel verschlüsselt. 
- *Identische Klartext-Blöcke liefern somit identische Ciphertext-Blöcke.* 
- Erleichtert Angriffe, z.B. 
	- Vertauschen/Löschen/Wiedereinspielen von Ciphertext-Nachrichten fällt nicht sofort beim Entschlüsseln auf. 
	- Rückschlüsse auf den Klartext aufgrund statistischer Eigenschaften.
- Einfach zu implementieren, aber nur für kurze Nachrichten geeignet (vgl. Kritik an „Staatstrojaner“).  

***Cipher Block Chaining*** (**CBC**) 
- Jeder Klartext-Block wird vor der Verschlüsselung mit dem vorhergehenden Ciphertext-Block XOR-verknüpft. 
- Benötigt einen *Initialisierungsvektor (IV)* für die XOR-Verknüpfung des ersten Klartext-Blocks. 
- Beseitigt die Defizite des ECB-Modes; aber: Kein wahlfreier Zugriff.

![[Pasted image 20240121163847.png]]
