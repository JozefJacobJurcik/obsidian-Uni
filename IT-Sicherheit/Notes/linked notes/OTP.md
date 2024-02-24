---
aliases: One Time Password System
---

A *one-time password* (**OTP**), also known as a *one-time PIN*, one-time authorization code (*OTAC*) or *dynamic password*, is a password that is *valid for only one login session or transaction*, on a computer system or other digital device. OTPs avoid several shortcomings that are associated with traditional (static) password-based authentication; a number of implementations also incorporate *two-factor authentication* by ensuring that the one-time password requires access to something a person has (such as a small keyring fob device with the OTP calculator built into it, or a smartcard or specific cellphone) as well as something a person knows (such as a PIN). 

# VL:

*Schutz vor Race Angriff*: 
- [[S - Key|S/Key]] Implementierungen erlauben i.d.R. mehrere gleichzeitige Sessions mit einem Passwort 
- Angreifer kann abgehörtes Passwort für kurzen Zeitraum nutzen (Replay Angriff) 

Jede Anmeldung mit OTP braucht eigenes One-Time Passwort 
Sonst nur marginale Änderungen zu [[S - Key|S/Key]]

### Angriffe

**Sicherheit hängt essentiell von der Sicherheit des gewählten Passwortes ab**
##### Dictionary Attack: 
Alle Nachrichten werden im Klartext übertragen, z.B. 
- Angreifer kann mit diesen Informationen versuchen, das Passwort des Benutzers zu brechen
Daher empfiehlt OTP die Verschlüsselung über [[IPSec]] 

##### Spoofing-Angriff:
Angreifer gibt sich als Authentisierungs-Server aus 
- Damit Man-in-the-Middle Angriff möglich 
- Auch hier: OTP empfiehlt die Verwendung von [[IPSec]] zur Authentisierung des Servers
