
The MD5 *message-digest algorithm* is a widely used hash function producing a 128-bit hash value.

MD5-Hashwerte sind immer 128 Bits lang 
- egal, wie lange die Eingabe ist

Weil es nur $2^{128}$ verschiedene MD5-Hashwerte gibt, existieren beliebig viele Dateien mit demselben MD5-Hashwert 
- = Kollision

Zwei sehr ähnliche, aber nicht identische Eingaben sollen nicht denselben MD5-Hashwert haben 
- = Kollisionsresistenz

Angreifer versucht, die Nachricht $m$ „sinnvoll“ in $m$‘ abzuändern, so dass md5($m$) = md5($m$‘)