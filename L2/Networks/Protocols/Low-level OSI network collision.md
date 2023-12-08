A network only exists, when multiple machines communicate with each other, therefore, conflicts exists: just like people talking at the same time.
At a second OSI model communication layer, there are protocols to prevent, avoid and resolve communication conflicts in a same carrier.

#### CSMA
Carrier-sense multiple access, which states: multiple access sensing for same carriers, and is one of the founding protocols of networks collision. It defines some sub-protocols, providing solutions for this issue.

The most straightforward children protocols are: 
- _CA_: meaning "collision avoidance" method, requires a client, to check for an idle channel, before acting. 
- _CD_: meaning "collision detection" method complements the _CA_ technique, and checks for bit per bit early collisions. A JAM signal is sent to notify other clients of it (a 32-bit value), and if the collision limit is not reached, we wait before restarting the process.

> [!NOTE]
> An _early collision_ is defined by the protocol, as the first **512-bits** of data. After that, the collision is considered not to be a communication conflict-wise problem, as other parties should have had the time to detect a busy channel. In a nutshell: **a late collision probably occurred due to external factors**.
> 
> The responsibility is given to the upper protocol levels, as they decide, if data must be resent.

###### Drawbacks
As always: each solution has its own drawback: CSMA, along with its CA and CD complements, can introduce _large latencies_ on a client's neighbors, due to it sending _large packets_. 
It is also often related to wireless exchanges and therefore called the hidden node problem, as a neighbor can't keep track of other parties band and therefore doesn't know about conflicts or a busy endpoint.

The _IEEE 802.11 tries to solve_ this, by introducing a new contraint, where each party performs a RTS/CRS (Request to Send/Clear to Send). This means: the origin party requests for a permission to send data and the endpoint must allow them, before any data is sent.
Its drawback, is also latency being introduced, in smaller amounts, but at each request.







