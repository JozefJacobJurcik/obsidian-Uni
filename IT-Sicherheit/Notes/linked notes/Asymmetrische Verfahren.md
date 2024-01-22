### Asymmetrische Verfahren

Jeder Partner besitzt *Schlüsselpaar* aus 
- persönlichem, geheim zu haltenden Schlüssel (*private key*) (wird NIE übertragen) 
- und öffentlich bekannt zu gebenden Schlüssel (*public key*) (kann über unsichere und öffentliche Kanäle übertragen werden) 

**Protokoll:** 
1. Alice und Bob erzeugen sich Schlüsselpaare: $(k^A_e,k^A_d)(k^B_e,k^B_d)$
2. Öffentliche Schlüssel $(k^A_e,k^B_e)$ werden geeignet öffentlich gemacht 
3. Alice will $m$ an Bob senden; dazu benutzt sie Bobs öffentlichen Schlüssel $c = e(m, k^B_e)$
4. Bob entschlüsselt die Nachricht mit seinem privaten Schlüssel: $m = d(c,k^B_d)=d(e(m, k^B_e), k^B_d)$

##### Zielsetzung
Effizienz / Performanz: 
- Schlüsselpaare sollen „einfach“ zu erzeugen sein. 
- Ver- und Entschlüsselung soll „schnell“ ablaufen. 

Veröffentlichung von $k_e$ darf keine Risiken mit sich bringen 

Privater Schlüssel $k_d$ darf nicht „einfach“ aus $k_e$ ableitbar sein 
- D.h. Funktion $f$ mit $f(k_d) = k_e$ soll nicht umkehrbar sein („Einwegfunktion“) 

Einsatz zur *Verschlüsselung*: 
- Alice schickt Nachricht $m$ mit Bobs Public Key verschlüsselt an Bob 
- Bob entschlüsselt den empfangenen Chiffretext mit seinem privaten Schlüssel 

Einsatz zur *elektronischen Signatur:* 
- Alice verschlüsselt ein Dokument mit ihrem privaten Schlüssel 
- Bob entschlüsselt das Dokument mit Alices öffentlichem Schlüssel

###### Beispiele: 
RSA, DSA, ElGamal, ...

![[One Time Pad]]

![[RSA]]