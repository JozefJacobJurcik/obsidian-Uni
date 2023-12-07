---

---
A SYN flood is a form of [[Denial of Service (DoS) und DDoS|DoS]] attack on data communications in which an attacker rapidly initiates a connection to a server without finalizing the connection. The server has to spend resources waiting for half-opened connections, which can consume enough resources to make the system unresponsive to legitimate traffic.

The packet that the attacker sends is the SYN packet, a part of TCP's three-way handshake used to establish a connection.

### Technical details
When a client attempts to start a [[TCP]] connection to a server, the client and server exchange a series of messages which normally runs like this:

1. The client requests a connection by sending a `SYN` (synchronize) message to the server.
2. The server acknowledges this request by sending `SYN-ACK` back to the client.
3. The client responds with an `ACK`, and the connection is established.

This is called the *TCP three-way handshake*, and is the foundation for every connection established using the TCP protocol.

A SYN flood attack works by not responding to the server with the expected `ACK` code. The malicious client can either simply not send the expected `ACK`, or by spoofing the source IP address in the `SYN`, cause the server to send the `SYN-ACK` to a falsified IP address – which will not send an `ACK` because it "knows" that it never sent a `SYN`.

The server will wait for the acknowledgement for some time, as simple network congestion could also be the cause of the missing `ACK`. However, in an attack, the *half-open connections* created by the malicious client bind resources on the server and may eventually exceed the resources available on the server. At that point, the server cannot connect to any clients, whether legitimate or otherwise. This effectively denies service to legitimate clients. Some systems may also malfunction or crash when other operating system functions are starved of resources in this way. 

### Countermeasures

There are a number of well-known countermeasures listed in RFC 4987 including:

1. Filtering
2. Increasing backlog
3. Reducing SYN-RECEIVED timer
4. Recycling the oldest [half-open TCP](https://en.wikipedia.org/wiki/TCP_half-open "TCP half-open")
5. SYN cache
6. [SYN cookies](https://en.wikipedia.org/wiki/SYN_cookies "SYN cookies")
7. Hybrid approaches
8. Firewalls and proxies