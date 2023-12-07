---

---

A Smurf attack is a [[Denial of Service (DoS) und DDoS|DDoS]] in which large numbers of Internet Control Message Protocol (ICMP) packets with the intended victim's spoofed source IP are broadcast to a computer network using an IP broadcast address. Most devices on a network will, by default, respond to this by sending a reply to the source IP address. If the number of machines on the network that receive and respond to these packets is very large, the victim's computer will be flooded with traffic. This can slow down the victim's computer to the point where it becomes impossible to work on. 

A **Smurf amplifier** is a computer network that lends itself to being used in a Smurf attack. Smurf amplifiers act to worsen the severity of a Smurf attack because they are configured in such a way that they generate a large number of ICMP replies to the victim at the spoofed source IP address.

In DDoS, amplification is the degree of bandwidth enhancement that an original attack traffic undergoes (with the help of Smurf amplifiers) during its transmission towards the victim computer. An amplification factor of 100, for example, means that an attacker could manage to create 100 Mb/s of traffic using just 1 Mb/s of its own bandwidth.

**The fix** is two-fold:

1. Configure hosts and routers to ignore packets where the source address is a broadcast address; and
2. Configure routers to not forward packets directed to broadcast addresses. Until 1999, standards required routers to forward such packets by default. Since then, the default standard was changed to not forward such packets.