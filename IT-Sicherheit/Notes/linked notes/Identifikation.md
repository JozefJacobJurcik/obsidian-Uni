---

---

Zweifelsfreie Verbindung (Verknüpfung) von digitaler ID und Real-World Entity (Person, System, Prozess,....) 

Ohne sichere Identifikation kann es keine zuverlässige [[Authentisierung]] geben 

Mindestens zweistufiger Prozess:
- Personalisierung: 
	Zweifelsfreie Ermittlung der Real-World Identität (bei Personen z.B. durch Personalausweis) und Vergabe einer digitalen ID (z.B. Benutzername) 
-  Identifikation: Verbindung von digitaler ID mit Informationen, die nur die Entität nutzen / kennen kann (z.B. Passwort, Schlüsselpaar, bzw. öffentlicher Schlüssel) 

**Problem**
	Falls der Angreifer in der Lage ist, seine Informationen mit fremder ID zu verbinden, kann er Maskerade-Angriffe durchführen

### Identifikation durch digitale Signatur / Zertifikat

**Grundidee**
	*Trusted Third Party* (TTP) bürgt durch Unterschrift (digitale Signatur) für die Identität einer Entität (vergleichbar mit einem Notar) 

 **Begriffe** 
  - Zertifikat: 
	  Datenstruktur zur Verbindung von Identitätsinformation und öffentlichem Schlüssel der Entität; digital signiert von einer 
-  Certification Authority (CA) / Trust Center: 
	Trusted Third Party 
- Realm: Benutzerkreis der CA 
	- Alle Benutzer in einer Realm „vertrauen“ der CA, d.h. 
	- „Aussagen“ der CA werden von allen Benutzern als gültig, richtig und wahr angenommen 
- (Local) Registration Authority (LRA): Nimmt Anträge auf ein Zertifikat (Certification Request) entgegen; führt Personalisierung durch

##### Aufgabenspektrum einer CA

- Generierung von Zertifikaten (*Certificate Issuance*): Erzeugung der Datenstrukturen und Signatur 
- Speicherung (*Certification Repository*): Allgemein zugängliches Repository für Zertifikate 
- Widerruf und Sperrung (*Certificate Revocation*): Z.B. falls geheimer Schlüssel des Zertifizierten kompromittiert wurde 
- Aktualisierung (*Certification Update*): Erneuerung des Zertifikates nach Ablauf der Gültigkeit 
- Schlüsselerzeugung (*Key Generation*)  
- Historienverwaltung (*Certification History*): Speicherung nicht mehr gültiger Zertifikate (zur Beweissicherung) 
- Beglaubigung (*Notarization*): CA signiert Vorgänge zwischen Benutzern (z.B. Verträge) 
- Zeitstempeldienst (*Time Stamping*): CA bindet Info an Zeit 
- Realm-übergreifende Zertifizierung (*Cross-Certification*): Eigene CA zertifiziert fremde CAs
- Attribut-Zertifikate (*Attribute Certificate*): Binden von Attributen an eine Identität (z.B. Berechtigungen, Vollmachten, ....)

#### Ablauf der Benutzerzertifizierung

1. Schlüsselgenerierung: 
	- Zentral durch CA oder dezentral durch Benutzer 
	- „Ausreichend sichere“ Schlüssel müssen erzeugt werden 
	- Nur der Zertifizierte darf geheimen Schlüssel kennen 
2. Personalisierung, Certification Request: 
	- Benutzer beantragt ein Zertifikat (Certification Request) 
	- Feststellung der Identität des Benutzers (z.B. durch pers. Erscheinen) 
	- Benutzer muss belegen, dass er im Besitz des passenden privaten Schlüssels ist (z.B. durch Challenge-Response-Protokoll)
3. Generierung der Datenstruktur für das Zertifikat: 
	- Entsprechende Attribute werden aus dem Certification Request des Benutzers entnommen 
	- Im Folgenden X.509v3-Zertifikate als Beispiel 
4.  Digitale Signatur durch die CA

X.509v3 Zertifikat: Attribute
![[Pasted image 20240224170532.png]]

#### Kopplung von Realms; Zertifizierungspfade
Bisher wurde nur eine CA betrachtet, nun 
CA Hierarchie:

![[Pasted image 20240224170736.png]]

Legende: 
	X{A} = Zertifikat ausgestellt von X für A (X zertifiziert A)

A kommuniziert mit B und möchte dessen Zertifikat verifizieren

Dazu Aufbau eines Zertifizierungs-pfades erforderlich: 
- A braucht folgende Zertifikate X{W},W{V},V{Y},Y{Z},Z{B} 
- Alle Zertifikate längs dieses Pfades müssen verifiziert werden 
- D.h. A braucht öffentliche Schlüssel von: X, W, V, Y und Z 

Im Bsp. eine streng hierarchische CA Infrastruktur

-> Optimierung des Pfades?
![[Pasted image 20240224170917.png]]

Cross-Zertifizierung nicht entlang der Hierarchieebenen 
- Damit Aufgeben des hierarchischen Ansatzes 
- Vermaschte bzw. vernetzte CA-Infrastruktur 
- Es entsteht ein „Web of Trust“ (vergleichbar mit PGP) 
- Pfade deutlich kürzer 
- Pfadermittlung und Pfadverwaltung damit aber u.U. deutlich aufwendiger

#### Widerruf von Zertifikaten
Falls Schlüssel kompromittiert wurde, muss Zertifikat widerrufen werden 

Dazu Certificate Revocation Lists (CRLs): 
	Liste jeder Zertifikats-ID mit Datum der Ungültigkeit; digital signiert von CA 

 Problem der Informationsverteilung: 
 -  Zeitnah, d.h. möglichst aktuell 
 - Vollständig 
 - Effiziente Verteilung 
 
 **Grundsätzliche Ansätze**: 
 -  Push-Modell (regelmäßige Übersendung der CRL) 
 - Pull Modell (Verifikator fragt bei Überprüfung aktuell nach, ob Zertifikat noch gültig, oder lädt sich CRL) 
 - Vollständige CRL oder Delta-Listen

### Online Certificate Status Protocol ([[OCSP]])