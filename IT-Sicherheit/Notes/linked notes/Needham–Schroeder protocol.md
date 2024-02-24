---

---

- Verwendet vertrauenswürdigen Dritten Trent neben Alice und Bob (Trusted Third Party, TTP) 
- Optimiert zur Verhinderung von Replay-Angriffen 
- Verwendet symmetrische Verschlüsselung 
- Trent teilt mit jedem Kommunikationspartner eigenen Schlüssel

![[Pasted image 20240224012117.png]]

**Problem**
- Alte Sitzungsschlüssel $K$ bleiben gültig 
- Falls Mallet an alten Schlüssel gelangen und die 1. Nachricht von Alice an Bob wiedereinspielen konnte, wird Maskerade möglich 
- Mallet braucht keine geheimen Schlüssel von Trent $(K_A,T, K_B,T)$ 

![[Pasted image 20240224012238.png]]

**Lösungsidee**
- Sequenznummer oder Timestamps einführen 
- Gültigkeitsdauer von Sitzungsschlüsseln festlegen