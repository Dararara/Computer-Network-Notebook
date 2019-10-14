# Transport Layer
## 3.1
A transport-layer protocol provides for logical communication between application processes running on different hosts.
There are two  distinct transport-layer protocols available to the application layer.

* UDP(User Datagram Protocol) provides an unreliable, connectionless service. The packet is called datagram(for network-layer packet, it is also called  datagram)
* TCP(Transmission Control Protocol), provides a reliable, connection-oriented service to the invoking application. The packet is called segment.
* To simplify terminology, in this book, we refer to the transport-layer packet as a segment.

Internet's network-layer protocol is called  IP(Internet Protocol)
IP provides logical communication between hosts. The IP service model is a best-effort delivery service. This means that IP makes its "best effort" to deliver segments between communicatin hosts, but it makes no guarantees. In particular, it does not guarantee segment delivery, it does not guarantee orderly delivery of segments, and it does not guarantee the integrity of the data in the segments.
For this reason, IP is said to be an unreliable service.

Service provided by UDP and TCP
* The most fundamental responsibillity of UDP and TCP is to extend IP's delivery service between two end systems to a delivery service between two processes running on the end systems. Extending host-to-hos delivery to process-to-process delivery is called tranport-layer multiplexing and demultiplexing.
* UDP and TCP also provide integrity checking by including error-detection fields in their segments' headers. UDP is an unreliable service, but TCP provides reliable data transfer.
* TCP provides congestion control while UDP don't.

