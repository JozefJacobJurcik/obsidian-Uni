Multiple Choice
===========
Bei der Kategorisierung von Sicherheitsmaßnahmen bedient man sich häufig welcher Schemata
- präventiv, detektierend, proaktiv
- ISO IEC 27000, ...
- technisch, organisatorisch
- …
Bei einer Blockchiffre wird welche Technik benutzt, um mathematische Funktionen, Substitution und Permutation zu realisieren?
- Keystream
- Zertifikate
- Initialisierungsvektor
- S-Box
Was hilft nicht gegen einen Internet Wurm
- Zentrales Logging
- Starke Passwörter
- Bugfixes
- 
Bei Biometrischen Verfahren gibt es zwei Typen von Fehlern
- false acceptance
- false rejection
- false …
- false …
Bei einem hybriden Verschüsselungsverfahren wird
- der asymmetrische Schlüssel symmetrisch übertragen 
- der symmetrische Schlüssel asymmetrisch übertragen
- hybride Verfahren sind grundsätzlich langsamer als rein asymmetrische Verfahren
Was stimmt hinsichtlich des Needham-Schröder-Verfahrens
- Es arbeitet mit symmetrischen Schlüsseln
- Es ist ein Schlüsselaustauschverfahren
- Es arbeitet nicht mit asymmetrischen Schlüsseln
...
Was trifft auf einen Paketfilter zu
- Er muss HTTP-Requests erkennen und modifizieren könnne
- Er muss die Ziel- und Quelladresse ermitteln können
- Er muss der [[TCP]] Destination Port ermitteln können
- Arbeiten auf Schicht 3 und 4
Was ist für kryptographische Hashfunktionen korrekt: 
- Sie bilden Nachrichten konstanter Länge auf beliebig lange Hashwerte ab
- Sie bilden Nachrichten beliebiger Länge auf beliebig lange Hashwerte ab
- Sie bilden Nachrichten beliebiger Länge auf konstant lange Hashwerte ab
- …
Welche Aussagen sind hinsichtlich SSL korrekt
- TLS ist eine von Microsoft entwickelte Variante von SSL
- SSL funktioniert nur im Zusammenhang mit UDP
- …
Was sind keine Inhalte des Risikomanagements nach ISO IEC 27000?
- Ermitteln von Risikobehandlungsoptionen
- Ignorieren von Risiken
- Schulen von MItarbeitern und Personal 
- Risikoanalyse
Woran erkennt ein Paketfilter, in welche Richtung ein Verbindungsaufbau geschieht?
- TCP Flags
- Quell-Adresse aller Pakete
- …
- …
Wie nennt man das Verstecken von Botschaften in anderen Medien
- Steganographie
- Transposition
- Substitution
- …
Was ist keine Social Engineering Technik
- Anrufe unter falschem Namen
- Papiertonnen durchsuchen
- USB-Sticks liegenlassen
- Portscans

Buffer Overflow
===========
- Was versucht ein Angreifer bei einbem stack smashing buffer overflow gezielt zu überschreiben?
- Erklären sie eine return-to-libc bufferoverflow. Geben Sie auch ein Beispiel, mit welcher Funktion ein Angreifer das Ausführen einer Shell realisieren kann
- (void) copy_user_data(char[] user_data){
     char[20] copy_data; 
     strcopy(copy_data, user_data);    
}
Beschreiben Sie, wie man diesen Code vor einem Bufferoverflow schützen kann
- Welche Methoden werden vom Betriebssystem, Compilern, etc. bereitsgestellt, um buffer overflows zu  verhindern. Nennen und erklären Sie zwei. 

WLAN
=====
- Gezeigt ist der Ablauf der WEP-Verschlüsselung. Beschreiben Sie den Ablauf der Entschlüsselung und der darauffolgenden Überprüfung der Integrität der Nachricht. 
- Welche Pakete dienen als Grundlage für den Chop-Chop-Angriff. Wie lassen sie sich trotz der Verschüsselung erkennen?
- Man könnte auch echte Zufallszahlen generieren. Begründen Sie, warum dies im Kontext der WEP-Verschüsselung nicht möglich / sinnvoll ist. 

Hashverfahren
===========
- ca bf 0b f6 96 5a 17 68 30 28 71 db 96 9d 94 47
Handelt es sich hierbei um eine SHA256, MD5 oder CRC-Prüfsumme? Begründen Sie ihre Antwort. 
- Alice schickt Bob eine Nachricht. Dieser hat sie die SHA256-Prüfsumme angefügt. Begründen Sie, warum dies nicht zur Integritätsicherung bei einem Man-in-the-Middle-Angriff ausreicht. 
- Hashed MAC
Warum wird beim HMAC Verfahren die Hashfunktoin zweimal angewandt. Was wird dadurch sichergestellt. 
- Könnte man auch einen SHA256 als Pseudozufallszahlen-Generator nutzen. Begründen Sie Ihre Antwort. 

Asymmetrische Verschlüsselung
=======================
- Was muss vor dem Senden einer eMail gemacht werden, um Authentisierung des Ursprungs und Datenintegrität zu erreichen?
- Was muss zusätzlich gemacht werden, damit auch Vertraulichkeit erreicht wird?
- Beschreiben Sie den Ablauf auf Seiten des Empfängers, welcher notwendig ist, die Nachricht zu entschlüsseln und die Integrität der Nachricht zu überprüfen. 

Kerberos
=======
- Nennen Sie einen Angriff auf Kerberos, während der Anforderung des Ticket-Granting-Tickets beim Authentication Server. 
- Wieso müssen alle Systeme die Kerberos verwenden zeitlich synchronisiert werden? 
-  Nennen Sie jeweils einen Vorteil von Kerberos im Hinblick auf Nutzerfreundlichkeit und Sicherheit des Passworts im Vergleich mit rein passwort-basierten Authetisierungsmechanismen. 
- Zwischen welchen Kerberos-Komponenten muss bei einem Multi-Domain-Kerberos eine Trust-Beziehung bestehen? 
- Unternehmensnetzwerke und u.a. auch das eduroam nutzen 802.X1 als Authentifizierungsmechanismus. Erläutern Sie, wieso Kerberos hier nicht / nicht sinnvoll eingesetzt werden kann. 

AES
===
- AES Entschlüsselungsablauf in Diagrammform gegeben. Man soll einzelne Schritte ergänzen. 
- Für die Addition des Rundenschlüssels ist keine explizite Inverse Funktion angegeben. Erklären Sie kurz warum und verdeutlichen Sie es anhand eines einfachen Bespiels.

CVSSv2
======
- Gegebener Fließtext und vermeintliche CVSSv2 Einschätzung. 5 von 14 Einschätzungen waren falsch. 
 -Es wurden Prämissen hinzugefügt (Wurm der Schwachstelle nutzt, wurde gesichtet aber Update von Hersteller wurde veröffentlicht) 
Welche Kriterien des CVSSv2 ändern sich entsprechend. 
- Normalerweise sind mehrere Schwachstellen eines IT-Systems gleichzeitig bekannt. Was für einen Zweck soll CVSSv2 in diesem Kontext erfüllen?

Sicherheitsmanagement
=================
Bei der Risikoeinschätzung wird neben der Einschätzung der Schadenshöhe was noch ermittelt?
Nennen Sie zwei Faktoren im Angreifermodell
- Studenten haben einen Algorithmus entwickelt, mit welchen man ermitteln kann, welche Facebook-Profile zusammenpassen. Daraus wird ein Geschäftsmodell gebaut. 
Es gibt drei Bereiche
- Öffentlicher Bereich der Webseite des Unternehmens
- Bereich für Kunden, zum Einsehen der Matching-Informationen
- Datenbank, in welcher die Profile und die Matches gespeichert werden. 
Welches Sicherheitsziel (Vertraulichkeit, Integrität, Verfügbarkeit) erscheint Ihnen jeweils am unwichtigsten.  Begründen Sie Ihre Antwort.

Zertifikate
========
- Erklären sie die zwei Begriffe X.509-Zertifikat und Registration Authority
- Nennen Sie drei Aufgaben einer CA

IPSec
====
Gegeben ist ein Datagram mit ESP und AH. Man muss zeigen, welcher next-Field auf welchen Header zeigt. Darüber hinaus muss man sagen, ob es Security-Gateways mit im Spiel sind, und welche Kombination von AH und ESP verwendet wurde.