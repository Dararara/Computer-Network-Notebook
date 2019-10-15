

# Chapter 1

## 1.1 Introduction
End system access the Internet through Internet Service Providers(ISPs), including residential ISPs such as local cable or telephone companies; corporate ISPs; university ISPs...

* Internet standards are developed by the Internet Engineering Task Force(IETF). The IETF standards documents are called requests for comments(RFCs).
* End system attached to the Internet provide a socket interface that specifies how a program running on one end system asks the Internet infrastructure to deliver data to a specific destination program running on another end system.

## 1.2 The network edge
Today, the two most prevalent types of broadband residential access are digital subscriber line(DSL) and cable.
* DSL: A residence typically obtains DSL Internet access from the same local telephone company that provides its wired local phone access. Thus, when DSL is used, a customer's telco is also its ISP.
* Cable Internet access makes use of the cable television company's existing cable television infrastructure.
* fiber to the home(FTTH) provide an optical fiber path from the CO(center office) to directly to the home

Access in the Enterprise and the Home: Ethernet and WIFI

* Ethernet: Ethernet users use twisted-pair copper wire to connect to an Ethernet switch, or a network of such interconnected switches, is then in turn connected into the larger Internet.(With Ethernet access, users typically have 100Mbps or 1Gbps access to the Ethernet switch whereas servers may have 1Gbps or even 10Gbps access.)
* WIFI, wireless.

### Physical Media
For each transmitter-receiver pair, the bit is sent by propagating electromagnetic waves or optical pulses across a physical medium.
Physical media fall into two categories: guided media and unguided media.
* With guided media: the waves are guided along a solid medium, such as fiber-optic cable, twisted-pair copper wire, or a coaxial cable.
* With unguided media, the waves propagate in the atmosphere and in outer space, such as in a wireless LAN or a digital satellite channel.


Wire type
* Twisted-pair Copper Wire. This is the least expensive and most commonly used guided transmission medium. Unshielded twisted pair(UTP) is commonly used for computer network within a building. 
* Coaxial Cable: Like twisted pair, coaxial cable consists of two copper conductors, but the two conductors are concentric rather than parallel. With this construction and special insulation and shielding, coaxial cable can achieve high data transmission rates. Coaxial cable is quite common in cable television systems. Coaxial cable can be used as a guided shared medium.
* Fiber Optics: An optical fiber is a thin, flexible medium that conducts pulses of light, with each pulse representing a bit. A single optical fiber can support tremendous bit rates, up to tens or even hundreds  of gigabits per second. They are immune to electromagnetic interferene, have very low signal attenuation up to 100 kilometers, and are very hard to tap. These characteristics have made fiber optics the preferred long-haul guided transmission media, particularly for overseas links.
* Terrestrial Radio Channels
* Satellite Radio Channels

## 1.3 The Network Core
### 1.3.1 Packet Switching
In a network application, end systems exchanges messages with each other. To send a message from a source end system to a destination end system, the source breaks long messages into smaller chunks of data known as packets. Between source and destination, each packet travels through communication links and packet switches(two predominant types: routers and link-layer switches).

* Most packet switches use store-and-forward transmission at the inputs to the links. Store-and-forward transmission means that the packet switch must receive the entire packet before it can begin to transmit the first bit of the packet onto the outbound link.
Consider the general case of sending one packet of size L from source to destination over a path consisting of N links each of rate R. The end-to-end delay is:
$$
d_{end-to-end} = N\frac{L}{R}
$$

#### Queuing Delays and Packet Loss
Each packet switch has multiple links attached to it. For each attached link, the packet switch has an output buffer(also called output queue)  which stores packets that the router is about to send to that link. 

* If an arriving packet needs to be transmitted onto a link but finds the link busy with the transmission of another packet, the arriving packet must wait in the output buffer. This is queuing delays.

* Since the amount of buffer space is finite, an arriving packet may find that the buffer is completely full with other packets waiting for transmission. In this case, packet loss will occur--either the arriving packet or one of the already-queued packets will be dropped.

#### Forwarding Tables and Routing Protocols
Each router has a forwading table that maps destination addresses(or portions of destination addresses) to that router's outbound links.
The Internet has a number of special routing protocols that are used to automatically set the forwarding tables.

### 1.3.2 Circuit Switching
There are two fundamental approaches to moving data through a network of links and switches: circuit switching and packet switching.
In circuit switching, the network establishes a dedicated end-to-end connection between the two hosts.
Once the circuit established, it reserves a constant transmission rate in the network's links. The sendercan transfer data to the receiver  at the guaranteed constant rate.

#### Multiplexing in Circuit-Switched Networks
A circuit in a link is implemented with either frequency-division multiplexing(FDM) or time-division multiplexing(TDM).

Circuit switching is wasteful because the dedicated circuits are idle during silent periods.

### 1.3.3 A Network of Network

![Screenshot from 2019-10-16 00-48-11](Screenshot from 2019-10-16 00-48-11.png)


## 1.4 Delay, Loss, and Throughput in Packet-Switched Network
total delay = nodal processing delay + queuing delay + transmission delay + propagation delay![Screenshot from 2019-10-16 00-48-21](Screenshot from 2019-10-16 00-48-21.png)



queuing delay depends on traffic intensity: La/R, say a file is L bits, one second comes a files, and the transmit rate of the router is R. If La/R < 1, no delay, if La/R > 1, the delay can be huge.(especially the average La/R > 1)

Suppose there are N-1 routers between the source host and the destination host.
$$
d_{end-end} = N(d_{proc} + d_{transmit} + d_{propagation})
$$



### 1.4.4 Throughput in Computer Networks
instantaneous throughput at any instant of time is the rate at which host is receiving the file.
average throughput
Bottleneck link