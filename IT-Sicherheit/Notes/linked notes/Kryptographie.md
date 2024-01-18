---
aliases: cryptography
---

Lehre von den Methoden zur Ver- und Entschlüsselung von Nachrichten

### Begriffe und Definitionen
- *Klartext* ([[Plaintext]]): Zu verschlüsselnde Nachricht 
- *Geheimtext* ([[Ciphertext]]): Verschlüsselte Nachricht 
- *Verschlüsselung*, Chiffrierung ([[Encryption]]): Vorgang, der Klar- in Geheimtext (Chiffretext) überführt 
- *Entschlüsselung*, Dechiffrierung ([[Decryption]]): Überführung von Geheim- in Klartext 
- *Chiffriersystem* (Cryptographic Algorithm, Cipher): Algorithmisches Verfahren zur Ver- bzw. Entschlüsselung 
- Algorithmen werden parametrisiert über Schlüssel (*Key*)

![[Pasted image 20240114210354.png]]

### Angriffsszenarien

- Eve kann die Nachrichtenübertragung (**passiv**) mithören
- Mallet kann die Nachrichtenübertragung **aktiv** manipulieren
	- Alice schickt sich selbst Nachrichten!?

![[Kryptographisches System]]