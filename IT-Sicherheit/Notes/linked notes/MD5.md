
The MD5 *message-digest algorithm* is a widely used hash function producing a 128-bit hash value.

MD5-Hashwerte sind immer 128 Bits lang 
- egal, wie lange die Eingabe ist

Weil es nur $2^{128}$ verschiedene MD5-Hashwerte gibt, existieren beliebig viele Dateien mit demselben MD5-Hashwert 
- = Kollision

Zwei sehr ähnliche, aber nicht identische Eingaben sollen nicht denselben MD5-Hashwert haben 
- = Kollisionsresistenz

Angreifer versucht, die Nachricht $m$ „sinnvoll“ in $m$‘ abzuändern, so dass md5($m$) = md5($m$‘)

### Algorithm
MD5 processes a variable-length message into a fixed-length output of *128 bits*. The input message is broken up into chunks of **512-bit blocks** (sixteen 32-bit words); the message is padded so that its length is divisible by 512.

### Applications
MD5 digests have been widely used in the software world to *provide some assurance that a transferred file has arrived intact*. For example, file servers often provide a pre-computed MD5 (known as md5sum) checksum for the files, so that a user can compare the checksum of the downloaded file to it. Most unix-based operating systems include MD5 sum utilities in their distribution packages; Windows users may use the included PowerShell function "Get-FileHash", the included command line function `certutil -hashfile <filename> md5`", or use third-party applications. Android ROMs also use this type of checksum.