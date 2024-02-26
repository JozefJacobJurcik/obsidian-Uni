100 Punkte - 2 Stunden Bearbeitungszeit - 15 Seiten


1. 10 MC-Fragen (jeweils 1 Punkt, mehrere Auswahlmöglichkeiten können richtig sein, --> 1 Punkt wenn alles richtig, sonst 0):

z.b.:

Welche der 4 Algorithmen können bei bei der Verlüsselung in IKE eingesetzt werden?
- AES
- DES
- RSA
- MD5

Was trifft auf SSL/TLS zu:
- SSL ist von Microsoft
- TLS ist von Netscape
- garantiert Vertraulichkeit, Authentität und Integrität von Daten
- bietet ein HandshakeProtokoll (?)

Auf welchen OSI-Schichten sind keine Sicherheitsmechanismen spezifiziert?
- Bitübertragungsschicht
- Vermittlungsschicht
- Sitzungsschicht
- Anwendungsschicht

Das Folgende triff auf OSI-Sicherheitskonzept zu:
- streng sequenziell
- sehr agil zu entwickeln (?)
- Zyklen sind möglich
- ...?

Eine Paketfilterfirewall verwendet zum Erkennen, welche Entität eine Verbindung aufgebaut hat:
- TCP Sequenznummern
- TCP Ports
- IP Ziel und Quelladresse
- TCP Flags

Folgende Aussagen über SQL-Slammer treffen zu:
- besteht nur aus 376Byte
- passt in ein TCP-Paket
- verursacht hohe Netzlast
- nutzt Code-Injektion in MS-SQL-Server (?)

...?...für kryptographische Blockchiffren wird verwendet:
- ByteSubstitution
- Initialisierungsvektoren
- Bitshifts
- Integritätssicherung (?)

Bei Hybrider Verschlüsselung wird:
- der asymmetrische Schlüssel unverschlüsselt ausgetauscht
- der symmetrische Schlüssel asymmetrisch verschlüsselt und ausgetauscht
- der asymmetrische Schlüssel symmetrisch verschlüsselt und ausgetauscht
- nur asymmetrische Verschlüsselung benutzt

Das Verstecken von Information in Bildern nennt man:
- Permutation
- Aggregation
- Steganographie
- Kryptographie

Allgemeines Zeug
- eine kleine Änderung an M bewirkt eine große Änderung bei H(M)
- ...?
- 
- 

Was gibt es für Fehlerraten bei Biometrischen Systemen:
- False Acceptance Rate
- False Approval Rate
- False Refusal Rate
- False Rejection Rate


2.
Vertraulichkeit definieren + Umsetzungsmechanismus in OSI-Modell nennen
gleiches mit Verbindlichkeit


3.?


Diffi-Hellman-Lückentext
a) -(man hatte g,p,a,b und musste auf Kommunikationspfeile zwischen A und B schreiben, was geschickt wird und anschließend noch, wie der Sitzungsschlüssel für beide jeweils ausgerechnet wird)

b) - Diffi-Hellman System für 3 Parteien Alice Bob und Carol. Alice kann nur an Bob schicken, dieser nur an Carol und diese
letztlich wieder an Alice
- man kann annehmen, dass sie sich schon auf g und p geeinigt haben
- für jede Verbindung wird eigener Schlüssel eingesetzt.
1. --> man soll den Schlüsselaustausch angeben (gegeben war schon Alice --> Bob: A1=g^a und A2 = g^a' und Bob-->Carol: A2, ... )
für B-->C, C-->A und nochmals A-->B
2. --> Daraus dann die jeweiligen Sitzungsschlüssel zwischen den einzelnen Teilnehmern

c) einen Man-in-the-Middle Angriff von Bob beschreiben und dessen Auswirkung auf Kommunikatin A-->C


AES
a) Entschlüsselungablauf-Bild mit Lücken (--> beachte letzte Runde!) (6 Punkte!)
b) Erklären warum man beim Rundenschlüssel nicht das Inverse nehmen muss (im Gegensatz zu allen anderen Schritten wie z.b. inverser Spaltenmix)

WEP
a) Gegeben Diagramm für Verschlüsselung von WEP --> Entschlüsselung stichpunktartig erläutern
b) 1. Mallet weis M und C und will eine eigene Nachricht erzeugen. Wie heißt diese Art von Angriff?
2. Diesen Angriff auf WEP darlegen

WPA
- Welche Verschlüsselten Pakete schneidet man mit, wenn man einen Chopchop Angriff vorbereiten will und warum lassen sich diese trotz Verschlüsselung nutzen?
- Welche 2 Mechanismen wurden gegen Chopchop angriff eingeführt
- Wie schafften es Beck und Tews diese Mechanismen trotzdem zu umgehen?

Firewalls
Paketfilterfirewall
a) Unterschied Blacklisting - Whitelisting
b) Regeln erstellen für: von Firmenintern darf nur auf Port 80 im Internet zugegriffen werden, Internet darf nur über Port 80 auf Firmeneigenen HTTP-Server zugreifen
-basierend auf Whitlistingansatz und dynamische Filterung, Ip-Adressrange von Firmennetz
c) Warum genügt Verbot von Port 80 nicht um zu garantieren, dass Mitarbeiten nur auf HTTP zugreifen können?
d) (8 Punkte!)
Applicationlevelgateway soll zum Einsatz kommen, um Mitarbeiter vor (unseriösen) Werbeseiten zu schützen. Deshalb sollen Anfragen an URLs die ".ads." beeinhalten
nicht zugelassen werden und zusätzlich Bilder der Größe 400X100 Pixel (die wahrscheinlich Werbebanner sind) durch leere Bilder ersetzt werden.
3 Schritte zur Firewall-konfiguration erstellen und jeweils ein konkretes Beispiel angeben.
1. ausgehender HTTP-request
2. empfangenes Paket:
- html
- Bild

IPSEC
a)Paket mit AH und ESP Lücken vervollständigen (wie in der Klausurvorbereitung) und bestimmen welche Kombination aus AH/ESP
b)Ziele der 3 Phasen von IKE kurz darlegen
c)3 Inhalte einer SA angeben
d)Wie wird Authentisierung in IKE durchgeführt
e)Warum werden nicht alle HeaderFelder durch AH geschützt? Welches z.b.?

Email Verschlüsseln

a) Was muss Absender mit Email machen, damit Empfänger sicher gehen kann, dass die Nachricht von ihm ist
b) Wie kann man zusätzlich Verbindlichkeit garantieren
c) Wie kann Empfänger prüfen von wem die Email ist und ob die Integrität passt


Zertifikate
- Was ist X508.v3?
- Was ist Register Authority?

- Was für Aufgaben hat eine CA?
...?



(Auffällig: nicht oder nur in MC-Fragen dran: Kapitel 9: Netzsicherheit - Schicht 2: Data Link Layer)