---
aliases: Wired Equivalent Privacy
---

Klartext wird mit Bitstrom XOR-verknüpft 

Bitstrom wird mit RC4 als Pseudozufallszahlengenerator (WEP PRNG) erzeugt 
- Für jede Nachricht *24-bit Initialisierungsvektor* (IV) konkateniert mit 40-bit *WEP-Schlüssel als 64-bit Seed* für PRNG 
- Nachricht  konkateniert mit [[CRC]] wird mit dem Bitstrom XOR-verknüpft

![[Pasted image 20240224202754.png]]

**Entschlüsselung**
IV wird im Klartext mit jedem Chiffretext übertragen 
- Jeder, der KBSS kennt, kann Keystream erzeugen und Nachricht entschlüsseln 
- Selbstsynchronisierung von WEP 

Entschlüsselung ist inverser Vorgang zur Verschlüsselung

![[Pasted image 20240224202836.png]]

### Zugangskontrolle
Bei Open System Authentication ohne Verschlüsselung kann jeder senden 

Falls WEP aktiviert ist, kann nur senden, wer KBSS kennt 

Keine individuelle Benutzerauthentifizierung mittels WEP möglich 

Viele APs bieten zusätzlich MAC-adressbasierte Access Control Listen (ACLs) 
- Nur bekannte/freigeschaltete MAC Adressen dürfen senden, aber 
	- MAC kann einfach mitgelesen werden 
	- MAC kann einfach gefälscht werden

##### Schwächen - Überblick
WEP erfüllt **KEINE** der Sicherheitsanforderungen: 
[[Vertraulichkeit]]
- Schlüsselmanagement und Schlüssel sind ein Problem 
- WEP ist einfach zu brechen 
- Jeder der KBSS kennt, kann alle damit verschlüsselten Nachrichten mitlesen 
[[Integrität]] 
- CRC ist kein geeignetes Verfahren zur Integritätssicherung bei absichtlicher Manipulation 
[[Authentisierung]] 
- basiert auf WEP 
*Zugriffskontrolle* 
- Keine individuelle Authentifizierung, somit generell nur rudimentäre Zugriffskontrolle möglich

![[Pasted image 20240224205817.png]]
