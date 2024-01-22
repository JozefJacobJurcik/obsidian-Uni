---
aliases: stream cipher, Stromchiffren
---
### Stromchiffren

A *stream cipher* is a symmetric key cipher where [[plaintext]] digits are combined with a pseudorandom cipher digit stream (**keystream**). In a stream cipher, each plaintext digit is encrypted one at a time with the corresponding digit of the keystream, to give a digit of the ciphertext stream. Since encryption of each digit is dependent on the current state of the cipher, it is also known as state cipher. In practice, a digit is typically a bit and the combining operation is an exclusive-or (XOR).

The pseudorandom keystream is typically generated serially from a random seed value using digital shift registers. The seed value serves as the cryptographic key for decrypting the ciphertext stream. Stream ciphers represent a different approach to symmetric encryption from [[Blockchiffren|Block cipher]]s. Block ciphers operate on large blocks of digits with a fixed, unvarying transformation. This distinction is not always clear-cut: in some modes of operation, a block cipher primitive is used in such a way that it acts effectively as a stream cipher. *Stream ciphers typically execute at a higher speed than block ciphers and have lower hardware complexity.* However, stream ciphers can be **susceptible** to security breaches (see stream cipher attacks); for example, *when the same starting state (seed) is used twice*. 

![[Pasted image 20240121154157.png|400]]
###### Beispiel: 
RC4 bei WEP-WLAN-Verschlüsselung) 

- Verschlüsseln kleine Klartext-Einheiten, z.B. 1 Bit oder 1 Byte 
- Klartext-Einheit wird mit einem frischen Zeichen aus dem sog. Keystream XOR-verknüpft 
- Keystream wird von Pseudo-Zufallszahlen-Generator (PRNG) erzeugt 
- PRNG wird von Absender und Empfänger mit Shared Secret initialisiert