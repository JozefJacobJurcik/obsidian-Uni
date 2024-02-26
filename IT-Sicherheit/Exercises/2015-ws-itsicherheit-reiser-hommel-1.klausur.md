MC-Fragen (15 Stück)
====================

## Wie nennt man das Verstecken von Nachrichten in anderen Medien?
 * Kryptographie
 * Steganographie
 * Permutation
 * Fuzzing (?)

## SQL-Slammer
 * Wird in TCP Paketen übertragen (wrong, uses udp)
 * Ist 376 Byte groß (true)
 * Verwendet einen SQL Injection Angriff (wrong, it used buffer overflow)
 * Verursacht hohe Netzlast

## Effiziente Algorithmen bei TLS zur Verschlüsselung
 * AES
 * RSA
 * 3DES
 * MD5

## Falsche Aussagen zu X.509v3
 * Der Validator pullt in regelmäßigen Abständen die CRL
 * Es kann nur die komplette CRL geladen werden, keine Deltas
 * Die CLR wird zum Validator gepusht
 * irgendwas zu OCSP

## MS-CHAPv2
 * Es löst alle Probleme von MS-CHAPv1
 * Das Protokoll ist viel einfacher geworden
 * Es ist eine Rollback Attack auf MS-CHAPv1 möglich
 * ist unabhängig von der Stärke des Passworts

## Was gibt es für Scores bei CVSSv3??? nicht "was gilt für..."?
 * Environmental Score gibt CO2 Footprint eines Angriffs an
 * Base Score, Environmental Score, Temporal Score
 * noch irgendwas zu Environmental Score, evtl. "beeinflusst das Gesamtergebnis/den Base Score" oder so ähnlich
 * ...evtl. Base Score, Ev..[was falsches, Evolutional oder so?], Temporal Score

## Was wird verwendet, damit Ciphertext möglichst zufällig ausschaut?
 * Diffusion
 * Konfusion
 * Permutation
 * Substitution

## Bei Hybrider Verschlüsselung wird
 * Ist wesentlich effizienter als eine komplette asymetrische Verschlüsselung
 * der asymmetrische Schlüssel unverschlüsselt ausgetauscht 
 * der symmetrische Schlüssel asymmetrisch verschlüsselt und ausgetauscht 
 * der asymmetrische Schlüssel symmetrisch verschlüsselt und ausgetauscht 
 * nur asymmetrische Verschlüsselung benutzt

## Was ist für kryptographische Hashfunktionen korrekt
 * Sie bilden Nachrichten konstanter Länge auf beliebig lange Hashwerte ab 
 * Sie bilden Nachrichten beliebiger Länge auf beliebig lange Hashwerte ab 
 * Sie bilden Nachrichten beliebiger Länge auf konstant lange Hashwerte ab 
 * Eine kleine Änderung der Nachricht verursacht eine große Änderung am Hash

## SYN-Flooding
 * X SYN in http-Anfragen werden kaputte Webserver angegriffen
 * Server der in einem Paket mehrere SYN-Flags gleichzeitig setzt
 * Angreifer manipuliert die SYN-Cookies
 * Angreifer verbraucht die Ressourcen des Opfers durch ganz viele halboffene TCP-Verbindungen

## Was fließt direkt oder indirekt in die Risikobewertung mit ein?
 * Schadenshöhe
 * mögliche Angriffe
 * Ergebnisse der Risikoanalyse
 * Evaluation?

## Fuzzing
 * Ein Social Engineering Methode, bei der die Leute verwirrt werden
 * Das systematische Suchen von Sicherheitslücken (oder so, die richtige antwort halt)

## DNS Amplification Attack
 * Verwendet ICMP
 * Erhöht die Netzlast
 * Man muss sich im selben Netz wie der Zielrechner befinden


Diffie-Hellman
==============
Es wird davon ausgegangen, dass die DH Parameter (g und p = Prim) noch nicht ausgetauscht wurden und Alice diese bestimmt.
Alice und Bob haben die Zufallszahlen a und b erzeugt.

Alice --- A=____,_____,_____ --> Bob
Alice <-- B=________________ --- Bob

Schlüsselberechnung von Alice: ______
Schlüsselberechnung von Bob: ______

## Füllen sie die Felder aus. Verwenden sie keine konkreten Zahlen.

## Welchen Vorteil hat DH im Gegensatz zu früheren Schlüsselaustauschverfahren?


Buffer-Overflow
===============
Beispiel C Sourcecode gegeben:

meinCopy(input) {
    char output[64];
    strcpy(output, input);
    printf("%s\n", output);
    return 42;
}

main(args...) {
    char input[0+815];
    gets(input);
    meinCopy(input);
}

a) Beschreiben, wo Buffer Overflow auftreten kann bzw. wie dieser sich auswirkt.
b) Muss die Rücksprungadresse relativ oder absolut angegeben werden?
Warum ist das Ziel bei einem Stack-Smashing-Angriff die Rücksprungadresse?
c) Wie funktioniert ASLR? Warum ist es effektiv?
d) Was sind Stack-Canaries? Wie verhindern sie im Bsp. den Buffer-Overflow?
e) Was passiert typischerweise, wenn die falsche Rücksprungadresse angegeben wurde?


AES-Aufgabe
===========
Gegeben:
 * S-Box
 * Schlüssel
 * 1. Rundenschlüssel
 * Klartext

Aufgabe:
Es soll die erste Runde bei AES berechnet werden.
Berechnen Sie die fehlenden Werte. Geben Sie die Namen der Schritte an.

## 1. Schritt: __________ (Vorrunde)
```
(42 42 42 42)     (42 42 42 42)   (42 42 42 42)
(42 42 42 42)     (42 42 42 42)   (__ __ 42 42)
(42 42 42 42) XOR (42 42 42 42) = (42 42 __ 42) 
(42 42 42 42)     (42 42 42 42)   (42 42 42 42)
```

## 2. Schritt: ________
```
(42 42 42 42)
(__ __ 42 42)
(42 42 __ 42)
(42 42 42 42)
```

## 3. Schritt: ________
```
(42 42 42 42)
(__ 42 42 __)
(__ 42 42 42)
(42 42 42 42)
```

## 4. Schritt: Mix Colums (Lösung gegeben)
```
(42  *  *  *  )
(*   *  *  *  )
(*   *  *  *  )
(*   *  *  *  )
```

## 5. Schritt: _______
```
(42 42 42 42)     (42  *  *  *  )    (__ *  *  *)
(42 42 42 42)     (*   *  *  *  )    (*  *  *  * )
(42 42 42 42) XOR (*   *  *  *  ) =  (*  *  *  * )
(42 42 42 42)     (*   *  *  *  )    (*  *  *  * )
```

IP-Sec
======

```
+--------------------------------+
| IP-Header (proto=______)       |
+--------------------------------+
| SPI | Seq.Nr                   |
+--------------------------------+
| next=_____ | SPI | Seq.Nr.     |
+--------------------------------+
| TCP Header + payload           |
+--------------------------------+
| padding | padlen | next = ____ |
+--------------------------------+
```

a) Diagramm vervollständige, die ersten beiden Lücken mit dem Protokoll, die letzte mit der Zeilennummer, auf die verwiesen wird.
b) Welche Kombination aus AH und ESP wurde angewandt? 
  Waren Endgeräte und/oder Security-Gateways im Spiel? 
  In welchem Mode waren AH und ESP jeweils?
c) Warum sind manche Headerfelder nicht von AH geschützt? Welches z.B. nicht und warum?


E-Mail Security
===============
a) Authentisierung mit digitaler Signatur. Was muss der Sender der Nachricht dafür machen?
b) Zusätzlich soll nun noch Vertraulichkeit gegeben sein. Mit welchem symmetrischen Algorithmus?
  Wie funktioniert die Ent- und Verschlüsselung? Geben Sie jeweils den Key mit an.
c) Wie wird Integrität sichergestellt und gleichzeitig die Authentizität festgestellt? Geben Sie 
  in Stichpunkten die Schritte an, die Bob machen muss.
d) Erklären Sie die Begriffe X.509v3 und Registration Authority?


Social-Engineering
==================
a) Nennen Sie zwei menschliche Eigenschaften, die Social Engineering Angreifer ausnutzen können. 
Geben Sie auch jeweils ein Beispiel an.
b) Geben Sie zwei Maßnahmen gegen Dumpster Diving an (außerhalb der normalen Awareness Maßnahmen?
c) Aus dem Modell von Fox/Kaun sind z.B. schon Poster, Anzeigen und Flyer in einer Firma umgesetzt worden.
Nennen Sie zwei weitere Maßnahmen aus diesem Modell?
d) Was unterscheidet einen Social Engineering Pentest von einem echten Social Engineering Angriff.
Geben Sie zwei Punkte an.


WEP
===
Gegeben war das Diagramm zur Verschlüsselung zu WEP.
a) Geben Sie in Stichpunkten die Entschlüsselung an und wie die Integrität überprüft wird.
b) Auf welchen Paketen basiert der Chop-Chop-Angriff auf WPA? Wie sind diese trotz Verschlüsselung erkennbar?
c) Warum hilft es der allgemeinen WLAN-Sicherheit nicht, die Broadcast-SSID auszusperren und nur authorisierte
MAC-Adressen zuzulassen?


Verschiedenes zu Kryptographie
==============================
a) Was ist ein known-plaintext-Angriff?
b) Wie wirkt sich das Geburtstagsparadox auf Angriffe auf Hashwerte aus?
c) Was ist der Unterschied zwischen Permutation und Substitution?
d) Wie viele Schlüssel braucht man bei symetrischer Verschlüsselung bei n Partnern?
e) Hashwert von "Lügenpresse" -- Unwort des Jahres 2014 -- gegeben 0d 8b 34 3b f4 ec e8 01 9b e5 5a 5b 08 18 42 0f.
   Mit welchem Algorithmus wurde dieser erstellt, MD5, SHA156 oder CRC32? Begründung angeben.


Authentisierung
===============
a) Geben Sie außer Wissen noch zwei weitere Möglichkeiten zur Authentisierung mit jeweils einem Bsp an.
b) Wie funktioniert RBAC (role based authentication)? Was ist ein Vorteil von RBAC gegenüber von DAC oder MAC?


Fragen zu Dingen
================
a) HMAC-Algorithmus gegeben: `HMAC(m) = H [(K^+ xor opad) || H[(K^+ xor ipad)||m]]`
  Was macht der Parameter K?
  Warum wird zwei Mal ein Hash berechnet?
b) Ist es bei symmetrischen Verschlüsselungsalgorithmen sinnvoller die Blocklänge oder Schlüssellänge zu vergrößern?
c) Welches Problem von ECB (Electronic Codebook Mode) löst CBC (Cipher Block Chaining)? 
   Wie funktioniert CBC generell?
   Was für ein Datum muss CBC zusätzlich haben?
d) Wozu braucht man ein Padding bei Blockchiffren?
   Wie lange muss das Padding mind. sein?
   Wie wirkt sich das Padding auf die Anzahl der Cipherblöcke aus?