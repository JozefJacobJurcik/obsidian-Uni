---

---

- Kommunikationspartner teilen *gemeinsamen, geheimen Schlüssel* (Shared Secret; deshalb: Symmetrie) 
- Ver- und Entschlüsselungsschlüssel sind identisch oder jeweils trivial aus dem Shared Secret abzuleiten. 
- Setzt vorherige Verständigung (*Schlüsselaustausch*) voraus. 

**Protokoll:**
1. Alice und Bob vereinbaren („out of band“) den gemeinsamen Schlüssel: $k_e = k_d = k_{A,B}$
2. Alice verschlüsselt $m$ : $c = e(m,k_{A,B})$ und sendet $c$ an Bob 
3. Bob entschlüsselt $c$ : $m = d(c, k_{A,B}) = d(e(m, k_{A,B}), k_{A,B})$

**Beispiele:** DES, AES, IDEA, RC4, Blowfish, Serpent, Twofish, ...

###### Beispiele:

[[Data Encryption Standard]] (DES)
[[Block- und Stromchiffren]]
[[Advanced Encryption Standard]] 