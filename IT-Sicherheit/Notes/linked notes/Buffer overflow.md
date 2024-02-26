---

---

 A **buffer overflow** or buffer overrun is an anomaly whereby a program writes data to a buffer beyond the buffer's allocated memory, overwriting adjacent memory locations.

### Stack smashing

A *stack buffer overflow can be caused deliberately as part of an attack* known as **stack smashing**. If the affected program is running with special privileges, or accepts data from untrusted network hosts (e.g. a webserver) then the bug is a potential security vulnerability. If the stack buffer is filled with data supplied from an untrusted user then that user can *corrupt the stack in such a way as to inject executable code into the running program* and take control of the process. This is one of the oldest and more reliable methods for attackers to gain unauthorized access to a computer.

#todo

![[Skript.pdf#page=106|Skript, page 106]]