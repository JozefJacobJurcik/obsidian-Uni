---

---

DNS amplification attacks involves an attacker sending a DNS name lookup request to one or more public DNS servers, spoofing the source IP address of the targeted victim. The attacker tries to request as much information as possible, thus amplifying the DNS response that is sent to the targeted victim. Since the size of the request is significantly smaller than the response, the attacker is easily able to increase the amount of traffic directed at the target.

Gegenmaßnahme: 
* Keine rekursiven Anfragen von extern beantworten 
- Schwellenwerte für identische Anfragen desselben vermeintlichen Clients