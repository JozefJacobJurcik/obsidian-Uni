---
aliases: Wireless Local Area Network
---
Wireless Local Area Network

![[Pasted image 20240224202009.png]]

- Alle Geräte teilen sich die Bandbreite 
- Maximaler Durchsatz praktisch nicht erreichbar (netto wird i.d.R. weniger als die Hälfte erreicht, z.B. 200-300 Mbit/s bei 802.11n)

### Infrastruktur-Modus
Access Point (AP): Zugangsknoten zum WLAN
Station (STA) 
- Gerät mit WLAN-Ausstattung 
- (Intelligenter) Client 
Basic Service Set (BSS) 
- Gruppe von STAs, die selbe Frequenz nutzen 
Extended Service Set (ESS) 
- logisches Netz aus mehreren BSS 
- wird gebildet durch Verbindungsnetz (Distribution System (DSS)) 
- ESS wird durch SSID identifiziert 
Portal: Verbindung zu anderen Netzen

![[Pasted image 20240224202331.png]]

### Ad-Hoc Modus
- Kein Access Point (AP) erforderlich 
- Alle Stationen sind gleichberechtigt 
- Basic Service Set (BSS) 
	- Gruppe von STAs, die dieselbe Frequenz nutzen 
	- Keine Kommunikation zwischen BSS möglich

![[Pasted image 20240224202506.png]]

## Sicherheitsmechanismen
Mallet und Eve haben es im WLAN (wg. Funk) noch einfacher als in kabelgebundenen Netzen.

**Sicherheitsanforderungen** 
- Authentisierung der Teilnehmer 
- Zugangskontrolle zum Netz (Autorisierung) 
- Vertraulichkeit der Daten 
- Integrität der Daten 

**Sicherheitsmechanismen** 
- Wired Equivalent Privacy ([[WEP]]) 
- WiFi Protected Access ([[WPA]]) 
- WiFi Protected Access 2 (WPA2) 
- IEEE 802.11i 
- WiFi Protected Access 3 (WPA3) (2018)