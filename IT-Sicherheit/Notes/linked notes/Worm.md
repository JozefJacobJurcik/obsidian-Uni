---

---
A computer **worm** is a standalone malware computer program that replicates itself in order to spread to other computers. It often uses a computer network to spread itself, relying on security failures on the target computer to access it. It will use this machine as a host to scan and infect other computers. When these new worm-invaded computers are controlled, the worm will continue to scan and infect other computers using these computers as hosts, and this behaviour will continue. *Computer worms use recursive methods to copy themselves without host programs and distribute themselves based on exploiting the advantages of exponential growth*, thus controlling and infecting more and more computers in a short time. Worms almost always cause at least some harm to the network, even if only by consuming bandwidth, whereas viruses almost always corrupt or modify files on a targeted computer.

*Many worms are designed only to spread, and do not attempt to change the systems they pass through*. However, as the Morris worm and Mydoom showed, even these "payload-free" worms can cause major disruption by increasing network traffic and other unintended effects. 

https://www.icir.org/vern/papers/cdc-usenix-sec02/cdc.pdf
#### Hit-list Scanning
One of the biggest problems a worm faces in achieving
a very rapid rate of infection is “getting off the ground.”
Although a worm spreads exponentially during the early 
stages of infection, the time needed to infect say the first
10,000 hosts dominates the infection time, as can be seen
in Figure 3.

There is a simple way for an active worm to overcome
this obstacle, which we term hit-list scanning. Before
the worm is released, the worm author collects a list of
say 10,000 to 50,000 potentially vulnerable machines,
ideally ones with good network connections. The worm,
when released onto an initial machine on this hit-list, be-
gins scanning down the list. When it infects a machine,
it divides the hit-list in half, communicating half to the
recipient worm, keeping the other half.

This quick division ensures that even if only 10–20% of
the machines on the hit-list are actually vulnerable, an
active worm will quickly go through the hit-list and es-
tablish itself on all vulnerable machines in only a few
seconds. Although the hit-list may start at 200 kilo-
bytes, it quickly shrinks to nothing during the partition-
ing. This provides a great benefit in constructing a fast
worm by speeding the initial infection.

The hit-list needn’t be perfect: a simple list of machines
running a particular server type may suffice, although
greater accuracy will improve the spread. The hit-list
itself can be generated using one or several of the fol-
lowing techniques, prepared well in advance, generally
with little fear of detection.

*Stealthy scans.* Portscans are so common and so
widely ignored that even a fast scan of the entire
Internet would be unlikely to attract law enforce-
ment attention or more than mild comment in the
incident response community. However, for attack-
ers wishing to be especially careful, a randomized
stealthy scan taking several months would be very
unlikely to attract much attention, as most intrusion
detection systems are not currently capable of de-
tecting such low-profile scans. Some portion of the
scan would be out of date by the time it was used,
but much of it would not.

*Distributed scanning.* An attacker could scan the
Internet using a few dozen to a few thousand
already-compromised “zombies,” similar to what
DDOS attackers assemble in a fairly routine fash-
ion. Such distributed scanning has already been
seen in the wild—Lawrence Berkeley National
Laboratory received 10 during the past year.

*DNS searches.* Assemble a list of domains (for ex-
ample, by using widely available spam mail lists, or
trolling the address registries). The DNS can then
be searched for the IP addresses of mail-servers
(via MX records) or Web servers (by looking for
www.domain.com).

*Spiders.* For Web server worms (like Code Red),
use Web-crawling techniques similar to search en-
gines in order to produce a list of most Internet-
connected Web sites. This would be unlikely to at-
tract serious attention.

*Public surveys.* For many potential targets there
may be surveys available listing them, such as the
Netcraft survey [Ne02].

*Just listen.* Some applications, such as peer-to-
peer networks, wind up advertising many of their
servers. Similarly, many previous worms effec-
tively broadcast that the infected machine is vul-
nerable to further attack. For example, because of
its widespread scanning, during the Code Red I in-
fection it was easy to pick up the addresses of up-
wards of 300,000 vulnerable IIS servers—because
each one came knocking on everyone’s door!

Indeed, some individuals produced active counter-
measures to Code Red II by exploiting this obser-
vation, when combined with the backdoor which
Code Red II installs [DA01]. However, it is not a
given that future worms will broadcast their pres-
ence, and we also note that worms could readily fix
the very security holes they exploit (such as is often
already observed for attackers performing break-
ins manually), which undermines the superficially
appealing countermeasure of using the worm’s vec-
tor as a means by which to disable it.


#### Permutation Scanning

Another limitation to very fast infection is the general
inefficiency of random scanning: many addresses are
probed multiple times. Similarly there is no means for a
randomly scanning worm to effectively determine when
all vulnerable machines are infected. Permutation scan-
ning solves these problems by assuming that a worm can
detect that a particular target is already infected.

In a permutation scan, all worms share a common
pseudo random permutation of the IP address space.
Such a permutation can be efficiently generated using
a 32-bit block cipher and a preselected key: simply en-
crypt an index to get the corresponding address in the
permutation, and decrypt an address to get its index.

Any machines infected during the hit-list phase (or lo-
cal subnet scanning) start scanning just after their point
in the permutation, working their way through the per-
mutation, looking for vulnerable machines. Whenever
the worm sees an already infected machine, it chooses a
new, random start point and proceeds from there. Worms
infected by permutation scanning would start at a ran-
dom point.

This has the effect of providing a self-coordinated, com-
prehensive scan while maintaining the benefits of ran-
dom probing. Each worm looks like it is conducting a
random scan, but it attempts to minimize duplication of
effort. Any time an instance of the worm, W , encounters
an already-infected host, it knows that W ′, the original
infector of the host, is already working along the cur-
rent sequence in the permutation, and is further ahead.
Hence, there’s no need for W to continue working on
the current sequence in addition to W ′.

Self-coordination keeps the infection rate high and guar-
antees an eventual comprehensive scan. Furthermore, it
allows the worm to make a local decision that further
scanning is of little benefit. After any particular copy
of the worm sees several infected machines without dis-
covering new vulnerable targets, the worm assumes that
effectively complete infection has occurred and stops the
scanning process.

A timer could then induce the worms to wake up, change
the permutation key to the next one in a prespecified se-
quence, and begin scanning through the new permuta-
tion, starting at its own index and halting when another
instance is discovered. This process insures that every
address would be efficiently rescanned at regular inter-
vals, detecting any machines which came onto the net
or were reinstalled but not patched, greatly increasing a
worm’s staying power. Otherwise, the worms are silent
and difficult to detect, until they receive attack orders
(see Section 6).

A further optimization is a partitioned permutation scan.
In this scheme, the worm has a range of the permutation
that it is initially responsible for. When it infects another
machine, it reduces its range in half, with the newly in-
fected worm taking the other section. When the range
gets below a certain level, it switches to simple permu-
tation scanning and otherwise behaves like a permuta-
tion scan. This scheme offers a slight but noticeable
increase in scanning efficiency, by dividing up the ini-
tial workload using an approximate divide-and-conquer
technique.

Permutation scanning interacts particularly well with a
worm which attacks multiple security holes: after de-
ciding that the initial exploit is exhausted, the worm re-
sets the permutation to its current address, changes the
permutation key, and exploits the second security hole.
Thus, even relatively rare secondary holes can be effi-
ciently and quickly scanned once the worm has estab-
lished itself on the network.

It may seem that the permutation scanning algorithm is
spoofable, but only to a very limited degree. If an unin-
fected machine responds to the scan in the same way as
a worm, by falsely claiming to be infected, it will tem-
porarily protect those machines which exist later in the
current permutation from being scanned by the worm.
However, since the permutation itself changes on ev-
ery rescan, the set of machines protected is constantly
changing. The result is that unless a very large number
of uninfected machines respond to probes like an actual
worm, the protection is almost nonexistent.
#### Simulation of a Warhol Worm
A combination of hit-list and permutation scanning can
create what we term a Warhol worm, capable of attack-
ing most vulnerable targets in well under an hour, possi-
bly less than 15 minutes. Hit-list scanning greatly im-
proves the initial spread, while permutation scanning
keeps the worm’s infection rate high for much longer
when compared with random scanning.

In order to evaluate the effects of hit-list and permuta-
tion scanning, we wrote a small, abstract simulator of a
Warhol worm’s spread. The simulator assumes complete
connectivity within a $2^{32}$ entry address space using a
pseudo-random permutation to map addresses to a sub-
set of vulnerable machines. We used a 32-bit, 6-round
variant of RC5 to generate all permutations and random
numbers.

We can parameterize the simulation in terms of: the
number of vulnerable machines in the address space;
scans per second; the time to infect a machine; num-
ber infected during the hit-list phase; and the type of
secondary scan (permutation, partitioned permutation,
or random). The simulator assumes multithreaded scan-
ning.

To ensure that the simulator produces reasonable re-
sults, Figure 6 shows a comparison between the simu-
lator’s output and the model developed in Section 2, for
a worm capable of 10 scans/second in a population of
300,000 vulnerable machines. The simulation results fit
the model for K = 2.6 and T = 5.52. This represents a
worm which is slightly faster (less than 50%) than Code
Red I.

Figure 7 then shows how both faster scanning and the
Warhol strategies affect the propagation time. The faster
scanning worm (capable of 100 scans/second) reduces
the infection time down to under an hour, while the com-
bination of hit-list scanning, permutation scanning, and
fast scanning, further reduces infection time to roughly
15 minutes.

Figure 8 shows in more detail the behavior of the Warhol
strategies. It gets a huge boost from the hit-list during the
first few seconds of propagation, quickly establishing it-
self on the network and then spreading exponentially. As
the infection exceeds the 50% point, some of the worms
begin recognizing that saturation is occurring and stop
scanning. By the time the graph ends (at 99.99% of
the simulated population), most of the worms have gone
silent, leaving a few remaining worms to finish scanning
the last of the address space.


![[Pasted image 20231212211554.png]]

#### Topological Scanning

An alternative to hit-list scanning is topologically aware
scanning, which uses information contained on the vic-
tim machine in order to select new targets. Email worms
have used this tactic since their inception, as they harvest
addresses from their victim in order to find new poten-
tial targets, as did the Morris worm (necessary because
of the very sparse address space when it was released)
[Sp89, ER89].

Many future active worms could easily apply these tech-
niques during the initial spread, before switching to
a permutation scan once the known neighbors are ex-
hausted. An active worm that attacked a flaw in a peer-
to-peer application could easily get a list of peers from
a victim and use those peers as the basis of its attack,
which makes such applications highly attractive targets
for worm authors. Although we have yet to see such a
worm in the wild, these applications must be scrutinized
for security. These applications are also vulnerable to
contagion worms, as discussed in Section 5.

Similarly, a worm attacking web servers could look for
URLs on disk and use these URLs as seed targets as well
as simply scanning for random targets. Since these are
known to be valid web servers, this would tend to greatly
increase the initial spread by preferentially probing for
likely targets.

#### Flash Worms
We further observe that there is a variant of the hit-list
strategy that could plausibly result in most of the vul-
nerable servers on the Internet being infected in tens of
seconds. We term this a *flash worm*.

The nub of our observation is that an attacker could plau-
sibly obtain a hit-list of most servers with the relevant
service open to the Internet in advance of the release of
the worm.

In addition to the methods already discussed for con-
structing a hit-list in Section 4.1, a complete scan of the
Internet through an OC-12 connection would complete
quickly. Given a rate of 750,000 TCP SYN packets per
second (the OC-12 provides 622 Mbps, the TCP seg-
ment takes 40 bytes, and we allow for link-layer fram-
ing), and that the return traffic is smaller in volume
than the outbound (it is comprised of either same-sized
SYN ACKs or RSTs, smaller ICMPs, or, most often, no
response at all), it would take roughly 2 hours to scan
the entire address space. Faster links could of course
scan even faster. Such a brute-force scan would be easily
within the resources of a nation-state bent on cyberwar-
fare.

Given that an attacker has the determination and fore-
sight to assemble a list of all or most Internet connected
addresses with the relevant service(s) open, a worm can
spread most efficiently by simply attacking addresses on
that list. For example, there are about 12.6 million Web
servers on the Internet (according to Netcraft [Ne02]), so
the size of that particular address list would be 48 MB,
uncompressed. The initial copy of the worm can be pro-
grammed to divide the list into n blocks, and then to find
and infect the first address in each block (or an especially
chosen high-bandwidth address in that block), and then
hand the child worm the list of addresses for that block.
That copy of the worm can then re-iterate the process to
infect everything in its block. A threaded worm could
begin infecting hosts before it had received the full host
list from its parent to work on, to maximize the paral-
lelization process, and it could start work on looking for
multiple children in parallel.

This design is somewhat fragile if an early copy of the
worm is neutralized very quickly, or infects a site from
which it cannot scan out. To mitigate this, the worm
copies could overlap in their scanning so that all ad-
dresses were scanned a small number of times, with
every target address being scanned by different paths
through the infection tree. This has the additional side-
effect of removing the need for further parent-to-child
communication after initial infection occurs.

A related design would call for most of the address list
to be located in pre-assigned chunks on one or a num-
ber of high-bandwidth servers that were well-known to
the worm. Each copy of the worm would receive an as-
signment from its parent, and then fetch the address list
from there. The server would only have to send out por-
tions of the list, not the entire list; in principle, it should
only have to transmit each address in the list once. In ad-
dition, after the worm has propagated sufficiently that a
large number of copies are attempting to fetch their (now
quite small) lists, at that point the worm collective could
switch to sending around the address list with each new
infection, rather than having the infectees each contact
the server.

This process will result in relatively little wasted effort.
For example, if the worm had a list of Web servers, and
a zero-day IIS vulnerability, about 26% of the list would
be vulnerable. No server would be probed twice. If
n = 10, then the infection tree for the 3 million vulner-
able servers would be just 7 layers deep.

The spread rate of such a worm would likely be con-
strained by one of two things. The worm itself is likely
to be small (Code Red I was about 4 KB, and a highly
malicious worm could easily be less than 100 KB, even
allowing for a complex payload). Thus, at the start, the
address list is much larger than the worm itself, and the
propagation of the worm could be limited by the time re-
quired to transmit the host list out of the initial infection
site or servers where it was stored. Since all the children
of the infection will have much smaller lists to transmit,
these later lists are less likely to limit the worm spread
(unless a first generation child has less than 1/n of the
initial copy’s bandwidth available to it). The exact time
required to transmit the list will depend on the available
bandwidth of the storage sites. As an example, however,
we point out that a 48 MB address list could be pushed
down an OC-12 link in less than a second.

Thus, starting the worm on a high-bandwidth link is
desirable for the attacker, and bandwidth is probably a
concern at the next layer or two. Compression of the
list could make the list delivery much faster. Indeed,
we took a sorted list of the 9 million server addresses
discussed in Section 5 and found that gzip compression
shrinks the list from 36 MB to 13 MB, and differencing
the addresses prior to compression reduced it to 7.5 MB.

Another possible limitation is simply the latency re-
quired to infect each new layer in the tree. Given that
probes can be issued in parallel, and substantially more
threads can be spawned than n (the number of children),
we do not have to add up the time required for a given
copy to cycle through its list, but simply take the maxi-
mum infection latency. A single second is a reasonable
latency, but with n = 10 and a large hit-list to trans-
fer, it might take a little longer to get 10 copies of the
worm through a given site’s link. However, not much
longer—if a 5 KB worm can get 50% utilization through
a 256 Kbps DSL uplink, it can transmit ten copies of it-
self in three seconds. That leads to a sub-thirty-second
limit on the total infection time, given an infection tree
seven layers deep and a design where the new worm chil-
dren go to a server for their addresses. (An additional
concern here is the possibility of elements of the worm
interfering with one another, either directly, by induc-
ing congestion, or indirectly, for example by overflowing
ARP tables, as happened during the Code Red I outbreak
[SA01]. These possibilities are difficult to analyze.)

In conclusion, we argue that a compact worm that be-
gins with a list including all likely vulnerable addresses,
and that has initial knowledge of some vulnerable sites
with high-bandwidth links, appears able to infect almost
all vulnerable servers on the Internet in less than thirty
seconds.
#### Stealth worms—contagion
The great speed with which the worms described in the
previous sections can propagate presents a grave threat
to the Internet’s security, because there is so little time
available to react to their onset. Still, there might be
a possibility of devising mechanisms that automatically
detect the spread of such worms and shut them down
in some fashion [MSVS02]. Such mechanisms would
likely be triggered by the singular communication pat-
terns the worms evince—hosts generating much more
diverse and rapid Internet traffic than they usually do.

We now turn to a different paradigm of worm prop-
agation, contagion, which, while likely spreading sig-
nificantly slower than the rapidly-propagating worms,
evinces almost no peculiar communication patterns. As
such these worms could prove much more difficult to de-
tect and counter, allowing a patient attacker to slowly but
surreptitiously compromise a vast number of systems.

The core idea of the contagion model can be expressed
with the following example. Suppose an attacker has
attained a pair of exploits: Es, which subverts a popular
type of Web server; and Ec, which subverts a popular
type of Web client (browser). The attacker begins the
worm on a convenient server or client (it doesn’t matter
which, and they could start with many, if available by
some other means), and then they simply wait. If the
starting point is a server, then they wait for clients to visit
(perhaps baiting them by putting up porn content and
taking care that the large search engines index it). As
each client visits, the subverted server detects whether
the client is vulnerable to Ec. If so, the server infects it,
sending along both Ec and Es. As the client’s user now
surfs other sites, the infected client inspects whether the
servers on those sites are vulnerable to Es, and, if so,
again infects them, sending along Ec and Es.

In this fashion, the infection spreads from clients to
servers and along to other clients, much as a contagious
disease spreads based on the incidental traffic patterns of
its hosts.

Clearly, with the contagion model there are no unusual
communication patterns to observe, other than the larger
volume of the connections due to the worm sending
along a copy of itself as well as the normal contents of
the connection—in the example, the URL request or the
corresponding page contents. Depending on the type of
data being transferred, this addition might be essentially
negligible (for example, for MP3s). Thus, without an
analyzer specific to the protocol(s) being exploited, and
which knows how to detect abnormal requests and re-
sponses, the worm could spread very widely without de-
tection (though perhaps other detection means such as
Tripwire file integrity checkers [Tw02] might discover
it).

In addition to exploiting the natural communication pat-
terns to spread the worm, these might also be used by the
attacker to then control it and retrieve information from
the infected hosts, providing that the endemic traffic pat-
terns prove of sufficient frequency and volume for the
attacker’s purposes. (Or, of course, the attacker might
more directly command the infected hosts when the time
is ripe, “blowing their cover” in the course of a rapid
strike for which keeping the hosts hidden can now be
sacrificed.)

As described above, one might find contagion worms a
clear theoretical threat, but not necessarily such a grave
threat in practice. The example requires a pair of ex-
ploits, and will be limited by the size of the populations
vulnerable to those attacks and the speed with which
Web surfing would serve to interconnect the populations.
While some argue the Web exhibits the “small world”
phenomenon [Br+00], in which the distance between
different Web items in the hypertext topology is quite
low, this doesn’t necessarily mean that the dynamic pat-
terns by which users visit that content exhibit a similar
degree of locality.

We now present a more compelling example of the la-
tent threat posed by the contagion model, namely lever-
aging peer-to-peer (P2P) systems. P2P systems gener-
ally entail a large set of computers all running the same
software. Strictly speaking, the computers need only all
run the same protocol, but in practice the number of
independent implementations is quite limited, and it is
plausible that generally a single implementation heavily
dominates the population.

Each node in the P2P network is both a client and a
server.7 Accordingly, the problem of finding a pair of
exploits to infect both client and server might likely be
reduced to the problem of finding a single exploit, signif-
icantly less work for the attacker. P2P systems have sev-
eral other advantages that make them well suited to con-
tagion worms: (i) they tend to interconnect with many
different peers, (ii) they are often used to transfer large
files, (iii) the protocols are generally not viewed as main-
stream and hence receive less attention in terms of moni-
toring by intrusion detection systems and analysis of im-
plementation vulnerabilities, (iv) the programs often ex-
ecute on user’s desktops rather than servers, and hence
are more likely to have access to sensitive files such
as passwords, credit card numbers, address books, and
(v) the use of the P2P network often entails the transfer
of “grey” content (e.g., pornography, pirated music and
videos), arguably making the P2P users less inclined to
draw attention to any unusual behavior of the system that
they perceive.

The final, sobering quality of P2P networks for form-
ing contagion worms is their potentially immense size.
We obtained a trace of TCP port 1214 traffic recorded
in November, 2001, at the border of a large university.
Port 1214 is used by the KaZaA [Ka01] and Morpheus
[Mu01] P2P sharing systems (both8 built on the Fast-
Track P2P framework [Fa01]). As of January, 2002,
the KaZaA distributors claim that more than 30,000,000
copies have been downloaded [Ka01]. Since our data
does not allow us to readily distinguish between KaZaA
and Morpheus traffic, for ease of exposition we will sim-
ply refer to all of the traffic as KaZaA.

Our KaZaA trace consists of summaries of TCP con-
nections recorded by a passive network monitor. We
have restricted the data to only those connections for
which successful SYN and FIN handshakes were both
seen (corresponding to connections reliably established
and terminated, and eliminating unsuccessful connec-
tions such as those due to scanning).

The volume of KaZaA traffic at the university is im-
mense: it comprises 5–10 million established connec-
tions per day. What is particularly striking, however, is
the diversity of the remote hosts with which hosts at the
university participated in KaZaA connections. During
the month of November, 9 million distinct remote IP ad-
dresses engaged in successful KaZaA connections with
university hosts. (There were 5,800 distinct university
KaZaA hosts during this time.)

Distinct addresses do not directly equate to distinct com-
puters. A single address can represent multiple comput-
ers due to the use of NAT, DHCP, or modem dialups ac-
cessed by different users. On the other hand, the same
computer can also show up as different addresses due
to these mechanisms. Thus, we do not have a precise
sense of the number of distinct computers involved in the
November trace, but it appears reasonable to estimate it
as around 9 million.

KaZaA uses a variant of HTTP for framing its applica-
tion protocol. Given HTTP’s support for variable-sized
headers, it would not be surprising to find that a buffer
overflow exploit of KaZaA exists. Given such an ex-
ploit, it is apparent that if an attacker started out having
infected all of the university’s KaZaA hosts, then after a
month they would have control of about 9 million hosts,
assuming that the KaZaA clients are sufficiently homo-
geneous that a single exploit could infect them all.

How plausible is it that the attacker could begin with
control over all of the university’s KaZaA hosts? Quite:
while the goal of the contagion worm is to evade detec-
tion, the attacker can likely risk a more blatant attack on
a single university. If they can find a university lacking
in diligent security monitoring (surely there must be a
few of these!), they can then compromise a single host
at the university, engage in “noisy” brute-force scanning
of the internal hosts to find all of the KaZaA clients, and
infect them. They then switch into contagion spread-
ing.

While the above argues that the attacker could gain the
9 million hosts within a month, the actual spread is likely
much faster, because once a remote host is infected, it
too contributes to spreading the contagion. Not only
does this accelerate the epidemic, but it also likely turns
it into a pandemic, because the remote hosts can connect
with other remote hosts that wouldn’t happen to visit the
university. Furthermore, depending on the protocol, a
single infected node could pretend to have information it
doesn’t have, in order to appear highly attractive and in-
crease the number of connections received, although that
would somewhat disrupt the normal patterns of commu-
nication.

We would like therefore to better understand the rate at
which a KaZaA contagion worm could spread, and to
what breadth. To estimate this from just the university
trace is difficult, because we don’t know the total size
of the KaZaA population. Doubtless it is larger than
9,000,000—but is it as high as 30,000,000, as indicated
in [Ka01]? How many of those copies were redundant
(same user fetching the software multiple times), or are
no longer in use? On the other hand, could the popula-
tion be higher, due to users getting copies of the clients
from other sources than [Ka01]?

Another problem is that we do not know the degree to
which the university’s hosts are “typical.” We also lack
any traces of their internal peer-to-peer traffic, which, if
frequent, would have major implications for the rate at
which the worm could infect an entire remote site.

We are pursuing further work in this area. First, we are
attempting with colleagues to develop graph-based mod-
els with which we can then extrapolate properties of the
spread of the contagion based on different sets of as-
sumptions about the hosts in our trace. Second, we have
obtained traces of KaZaA traffic from another university
(in another country), and will be analyzing these to de-
termine the degree of overlap and cross-talk between the
two universities, with which to then better estimate the
total KaZaA population and its communication patterns.
Finally, we are building a simulator for both active and
contagion worms within various peer-to-peer topologies.

As a last comment, we have evidence that the KaZaA
network may behave like a “scale-free” topology in
terms of its interconnection. Figure 9 shows the dis-
tribution of the degree of the remote hosts in the trace,
i.e., the number of distinct local hosts to which each re-
mote host connected during November, 2001. The plot is
shown as a log-log complementary distribution function:
the x-axis shows log10 of the remote host’s degree, and
the y-axis shows log10 of the probability of observing a
remote host with that outdegree or higher. (Due to the
immense size of the dataset, we plot a subset rather than
the entire dataset, randomly sampled with p = 0.01.)

A straight line on such a plot corresponds to a Pareto
distribution. While the majority of the remote hosts con-
nected to only one or two local hosts, for those con-
necting to three or more hosts, the fit to a Pareto dis-
tribution (with shape parameter α = 2.1) is compelling.
That the degree has such a distribution is then strongly
suggestive that the underlying KaZaA network may ex-
hibit a scale-free (or Zipf-like) topology. The propaga-
tion of contagion through such networks has recently
been studied [PV01]. While the discussion in that ar-
ticle is flawed—it confounds the Internet’s underlying
IP topology with email and Web application topology—
the general framework the authors develop gives hope
that we can leverage it to better understand the behav-
ior of a KaZaA contagion worm. That said, we add that
the degree of the local hosts is clearly not Pareto, so the
analysis might not in fact apply.
