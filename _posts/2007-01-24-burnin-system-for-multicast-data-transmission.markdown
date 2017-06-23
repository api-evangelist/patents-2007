---

title: Burn-in system for multicast data transmission
abstract: A system for improving the reliability of transmission of multibroadcast data between a source of data and a plurality of customer receivers of the data via a telecommunications network. The system includes a supervision server adapted to provide each customer receiver with a list of at least one other receiver, said customer receiver being adapted to receive missing data from said the other customer receiver via a reliable peer-to-peer connection.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08427994&OS=08427994&RS=08427994
owner: France Telecom
number: 08427994
owner_city: Paris
owner_country: FR
publication_date: 20070124
---
The present invention relates to a system for improving the reliability of transmission of multibroadcast data between a source of said data and a plurality of receivers of said data via a telecommunications network.

The invention finds one particularly advantageous application in the field of transmission of data in multibroadcast mode also known as multicast mode.

The terms multibroadcast and multicast are used interchangeably in the remainder of the description the term multicast being widely used in this field.

Close control of the efficient bulk distribution of data is crucial for Internet Service Providers ISP for Internet Service Provider . The current trend is to supply and to administer remotely network equipment installed in the home in the form of home gateways and set top boxes STB . The equipment installed in the home is referred to below as the receiver or the customer .

There are therefore potentially millions of receivers that must be administered from one or a few points controlled by the ISP. It is also increasingly obvious that viruses are continuing to spread and now affect not only personal computers but everything relating to communicating applications based on electronic data processing using equipment such as personal digital assistants PDA mobile telephones and the above mentioned home gateways and STBs. Writers of viruses and other malware are increasingly skilful and the time delays between security failings going public and viruses being developed to exploit them are continually decreasing.

It is therefore becoming vital to be able to master technologies for updating all domestic receivers administered by the operator very quickly. The reliability of the equipment and the quality of service depend on this which must be achieved by fast and efficient updating solutions in the homes of very large numbers of customers.

A first method of solving this problem is to use a raft of content servers distributed or not. That solution can be very costly however because it requires considerable resources in terms of the number of servers and considerable network resources. Also to achieve an acceptable compromise server administrators often use a policy of spreading the task in time by performing a given maximum number of daily updates. That strategy is beneficial in that it limits the growth of calls to telephone helplines hotlines software updates often leading to additional calls but it is totally unsuitable for deploying a security module urgently for example.

A second method is a multibroadcast or multicast method that constitutes simple and efficient means for a data source to reach any group of receivers from a few to several million very quickly but that solution is based on the UDP User Datagram Protocol and offers no guarantee of correct transmission of data to customers and some data can be lost at the connection or router level for example. That drawback is aggravated by the absence of a return channel which would enable recovery of missing data. Administering any such systems with very large numbers of receivers would be problematic.

However the IETF group RMT Reliable Multicast Transport has looked at this problem of improving the reliability of multicast transmission and proposes a set of solutions that can be classified into two major categories 

Conjoint use of those two techniques optimizes transfers over the network but the problem relating to DDoS type attacks persists if the application needs a list of receivers that receive the file correctly.

To summarize methods of improving the reliability of multicast data transmission have the following limitations.

With the raft of servers method it is found that if a very large number of receivers are administered by a central site that site can accept only a limited number of simultaneous requests depending on its internal resources. Such requests are based on point to point sessions in particular TCP sessions. To authorize simultaneous administration of a large number of receivers the data source is obliged to install a set of machines to distribute requests. Those solutions are generally costly and complex to administer to achieve a good load distribution.

Thus the technical problem to be solved by the subject matter of the present invention is to propose a system for improving the reliability of transmission of multibroadcast data between a source of data and a plurality of receivers of said data via a telecommunications network that would make it possible to transmit data reliably i.e. to be able to remedy any losses and guarantee the integrity of the recovered data that is economic in terms of network cost and distribution server cost that offers high performance namely fast deployment to millions of customers and that is free of any mass feedback mechanism.

The solution according to the present invention to the stated technical problem is that said system comprises a supervision server adapted to provide each customer receiver with a list consisting of at least one other customer receiver said customer receiver being able to receive missing data from said other customer receiver via a reliable peer to peer connection.

Here the peer to peer connection concept refers to the family of protocols that have recently been introduced based on Peer to Peer P2P exchanges. The novelty of a peer to peer network is that terminals behave at the same time as customers consuming resources and as servers providing resources. For example the best data file sharing P2P protocols use swarming methods whereby a file is divided into a number of portions enabling it to be downloaded from a number of source terminals which optimizes load sharing speed and robustness.

Thus the invention uses the conventional multibroadcast mechanism in which a multicast source is responsible for broadcasting data a file for example to a group of customer receivers of the network of an operator by means of ad hoc protocols. Given the non reliability of the transport layers supported by the multicast packets UDP in particular it is possible for data to be lost in the network. To solve this problem the invention proposes to use a peer to peer network approach. Each customer receiver is connected to certain of its peers by a reliable connection such as a TCP IP connection which is maintained throughout the session. If a receiver detects that a data packet has been lost it contacts a peer to recover the packet in question.

To summarize the invention combines two technologies to optimize transmission of data the multicast technology enables downloading to a very large number of customers while P2P connection avoids feeding a large number of error messages from customers back to a single source.

In a second aspect the invention provides a source of data multibroadcast to a plurality of customer receivers of said data via a telecommunications network said source of data being adapted to transmit to said customer receivers before the data the root hash HR of a Merkle hash tree of said data by reliable multibroadcasting via said telecommunications network said source of data being adapted to transmit to customer receivers hashes of lower level than said root hash HR after said root hash and before said data a customer receiver being adapted to receive missing data from another customer receiver via a reliable peer to peer connection.

In a third aspect the invention provides a supervision server for a system for improving the reliability of transmission of multicast data between a source of data and a plurality of customer receivers of said data via a telecommunications network said supervision server being adapted to provide each customer receiver with a list of at least one other customer receiver said list being intended to establish a reliable peer to peer connection between said customer receiver and said other customer receiver.

In a fourth aspect the invention provides a reference source for a system for improving the reliability of transmission of multicast data between a source of data and a plurality of customer receivers of said data via a telecommunications network said reference source having said data and being adapted to establish a reliable peer to peer connection with at least one customer receiver.

Thus if data packets for all receivers were to be lost those receivers having the reference source in the list supplied by the supervision server can then establish a peer to peer connection with said reference source and recover said lost packets such recovery being propagated to the other receivers by the mechanism of the peer to peer connection between receivers.

In a fifth aspect the invention provides a customer receiver in a system for improving the reliability of transmission of multicast data between a source of data and a plurality of customer receivers of said data via a telecommunications network said customer receiver comprising means for verifying the integrity of the data provided by said other customer receiver during a peer to peer connection.

Thus when a receiver recovers data from another receiver from its list it can be sure that the data received corresponds to the data expected.

According to preferred non limiting embodiments the fifth aspect of the invention has the following additional features separately or in combination 

The verification means comprise means for calculating hashes of fragments of data received from at least one other customer receiver and means for comparing the calculated hashes with hashes of said fragments received from said source of data.

The customer receiver includes means for verifying the integrity of hashes provided by said other customer receiver during a peer to peer connection.

Hashes received from the source are generally transmitted over a multicast connection that has not been made reliable and so can be lost and then recovered by a receiver via peers from its list in the same way as other data. Thus the hash integrity verification means are used to verify the information provided by the other customer receiver.

In a sixth aspect the invention provides a method of transmitting multicast data between a source and a plurality of customer receivers via a telecommunications network said method including transmission of missing data by a customer receiver to another customer receiver via a reliable peer to peer connection.

In a seventh aspect the invention provides a method of receiving data multicast between a source and a plurality of customer receivers . . . via a telecommunications network including reception of missing data by a customer receiver from at least one other customer receiver via a reliable peer to peer connection.

In a eighth aspect the invention provides a computer program on a data medium that can be loaded into the internal memory of a computer said program comprising code portions for executing steps of the method constituting the sixth aspect of the invention.

In a ninth aspect the invention provides a computer program on a data medium that can be loaded into the internal memory of a computer said program comprising code portions for executing steps of the method constituting the seventh aspect of the invention.

The system includes a supervision server responsible in particular for connecting the various customer receivers with a view to establishing a reliable peer to peer connection between them afterwards. For this purpose when a customer is registered the supervision server provides a list of at most N 1 other peers already registered and with which reliable TCP IP connections can be established during sessions for recovering missing data.

The first customers will not obtain N 1 peers of course which is not a problem because they will be contacted by new customers as and when their number increases.

It is important to note that the supervision server must choose carefully the peers associated with a given receiver. Choosing only peers that are nearby in the topological sense would make error recovery impossible in the event of a problem caused by the network core for example by rerouting. Conversely choosing only distant peers could burden network traffic without benefit and reduce the efficiency of the system. Furthermore a random choice of peers from all peers involved seems beneficial from the robustness point of view but of moderate efficiency in terms of traffic optimization. For the purposes of optimization it would therefore appear preferable for the server to provide a list of near and distant peers.

As shown in the system of the invention also includes a reference source that has all the data to be transmitted and appears in at least one list of peers provided by the server so as to be able to retransmit missing data to the associated peers requesting this if necessary. In fact the reference source is a customer that already has the whole file and is therefore not participating in the multicast session. In contrast it contributes to making deployment more reliable by supplying missing packets to customers to which it is connected. This can be very useful in the event of packet loss at the upstream end close to the source .

The reference source can also be located on one and the same machine as the source and the supervision server .

Before continuing the description of the reliability improvement system of the invention it is necessary to summarize the structure of a data file.

A data file consists of one or more blocks of data depending on the requirements of the application. The blocks are managed by the application itself and not by the protocol.

A block consists of a number of fragments. The integrity of the content exchanged between peers is verified relative to these fragments.

During a deployment session the file to be transferred is sent by the source in the form of segments inside UDP packets. In the event of loss the missing segment or each of the missing segments is recovered in P2P mode. It is then necessary to provide a mechanism that can guarantee the integrity of the data downloaded from a third party customer that is not necessarily trustworthy and to do this in a relatively short time.

There are a number of methods for solving this problem. Each sends securely beforehand a signature enabling customers to certify the received data.

One simple solution is to supply a hash of a file. This method has limitations because it obliges the receiver to verify the integrity of the file only when it has been completely downloaded. Moreover if the receiver has been obliged to recover data segments from a number of peers one of which was malicious the receiver finds itself unable to identify the malicious peer and the suspect data segments.

Another solution calculates hashes over fragments of the file. As a result as soon as a customer assembles a fragment from a number of segments they can verify its integrity and therefore react more promptly to a malicious attack. This is the method currently used in the BitTorrent P2P protocol http www.bittorrent.com . The weakness of this approach is that all the hashes of the fragments of a file must be supplied by the source in a secure manner. This data can become somewhat voluminous depending on the chosen size of the fragments up to a few megabytes and transporting it may represent a penalty in the event of sending to millions of customers.

The preferred solution of the invention uses a Merkle hash tree R. Merkle Secrecy Authentication and Public Key Systems PhD Dissertation Dept. of Electrical Engineering Stanford Univ. 1979 . This solution shown in calculates level hashes HS HS . . . HS over the six fragments of the file and recursively calculates level hashes HS HS HS on the previous hashes HS etc. taken two by two until a root hash HR is obtained. This solution leads to extra calculation relative to the previous solution but enables the source to transmit reliably only the root hash HR. This considerably reduces the quantity of data to be sent in advance of deployment and in an entirely reliable way to approximately one hundred bytes all inclusive for example.

This information concerning the root hash HR of the Merkle tree of the data file to be transmitted is part of information that the multicast source must group together in a metafile in order for it to be distributed in a reliable integrated and secure manner to all the receivers . . . that have to participate in the data transmission session. How this metafile is supplied to the customers is not part of the invention. This can be achieved without difficulty by sending periodically or by using the HTTP HTTPS FTP SCP protocols for example.

This produces a metafile of a few hundred bytes to be distributed before deploying the data. Note that a certificate can be associated with it to guarantee its authenticity.

The metafile and all the other data or information sent by the multicast source to the receivers are sent in packets with the format represented in .

The first four bytes Seq Num are reserved for the sequence number of the packet. By analyzing the sequence numbers received a receiver can detect the loss of one or more packets. The sequence number depends only on the order in which the data packets are sent. It is incremented each time that a multicast packet is sent.

The bytes that follow the type field correspond to the payload data whether that consists of hashes or of data from the file to be transmitted as represented in respectively.

After reliably transmitting the root hash HR of the Merkle tree of the data file to the receivers and before deployment as such the multicast source sends all the customers all the hashes necessary for verifying the integrity of data that might be recovered subsequently in the event of loss of packets. It must be remembered that the segments or data packets sent by the source are deemed to be integral by the customers.

In this way if a packet of hashes is lost it can be recovered from a peer and its integrity verified on the basis of the higher level hashes. This is valid even in the event of loss of the first packet because the verification is then effected by the root hash HR of the Merkle tree which is part of the information contained in the metafile sent reliably and integrally beforehand. It is also true for the loss of the first data packet of type 00 because the offset can be calculated a posteriori.

Note that the packets are constructed so as to send at most only one level per packet and to send only entire hashes in each packet. This is possible because the packets sent in multicast mode constitute what is known as a packet boundary i.e. the customer software can monitor the size of each packet transmitted over the network. It is therefore possible to transmit packets of hashes of varying size.

The multicast source then sends 00 type packets containing the data with the format represented in . The first packet of this type is used to calculate the offset between the sequence number Seq Num and the position of the payload data. To this end all data packets of the file to be deployed except for the last must be the same size. This information makes it possible to reconstitute the file if lost.

The sequence numbers of the packets thus enable a receiver to detect losses of data sent by the source and to effect a repair via its peers. It must be possible to detect losses during a transfer or when a transfer is interrupted for whatever reason. A number of situations are possible in which a distinction must be drawn between the source halting transfer and losses in the transmission network.

1. At the end of transmitting a file the source sends an END message that contains a field indicating the sequence number of the last segment sent. This message is sent several times to guarantee its reliable reception in the event of losses in the network. On receipt of this message a receiver can easily identify if packets have been lost and then effect a repair.

2. In the event of temporary halting of transmission by the source the source must send a PAUSE message containing the sequence number of the last packet sent. The receiver can effect a repair in a similar way to the previous situation.

3. In the event of prolonged halting of reception of data with no END or PAUSE message a time out is triggered before concluding that transmission has been broken off. The receiver can then attempt to launch a repair if it can contact its peers depending on the location of the break in the network.

4. End of transmission detection by analyzing the size of the file received is also possible. The size of the file to be transmitted is in fact a parameter of the information metafile supplied initially by the multicast source.

The mechanism of dialogue between peers during recovery of missing data by a receiver is described in detail below.

Connection to a peer is always requested by providing the Merkle root hash HR which unambiguously identifies the data file that is the subject matter of the deployment. It is nevertheless possible to envisage other identification means such as the file name or a file identifier. Supplying the identifier enables receivers to distinguish between and identify sessions.

Given that the environment of the peers concerned is not necessarily cooperative it may be preferable to institute a tit for tat policy of contact between peers.

In this context each customer peer must limit its number of simultaneous transmissions to other peers and give priority to those most generous toward them. The selection criteria are 

However in multicast mode a receiver has never tested exchanges with its peers at the time it decides to initialize a repair. It does not know a priori which are the best peers.

When a receiver has detected a loss of data it must decide to start the repair process. An important aspect of operation is optimizing requests to peers. The particular feature of multicast transmission is that in some circumstances all customers detect an end of fragment or block at the same time and are therefore led to initiate the recovery procedure quasi simultaneously if they detect loss of data. Consequently the exchange specification must avoid a profusion of messages triggered by these events in order to limit the risk of congestion of the network by bursts of traffic. A number of situations are possible 

1. The receiver waits for the end of a block a fragment or the file indicated by a PAUSE message for example to initialize a repair via its peers. The requests can contain a list of lost segments or lost ranges of segments. Each receiver triggers a pseudo random time delay in a predefined window which can be a additional field in the metafile. Thus requests are distributed over a limited time to smooth the network load. Immediately the complementary data is received each receiver verifies the integrity of the fragment by means of information from the hashes.

2. The receiver initializes a repair as soon as it has detected loss of an isolated packet or a range of packets without awaiting a PAUSE message. It triggers a time delay as above before sending a request message REQUEST defined below.

The choice of one or the other of these solutions is a function of the application the error rate and the distribution of errors.

Table 1 below defines all instructions for signaling between peers used in the missing data recovery protocol.

When a fragment is completed the customer must verify its integrity using the Merkle hash tree if some data does not come from the multicast source. It can then supply that data to its peers afterwards.

Multicast UDP IP transmission is highly sensitive to congestion in the network because there is no simple way to regulate the output bit rate of the source which is generally constant. It is therefore important that retransmission anywhere in the network is never an obstacle to the transfer of multicast packets. This behavior is natural in an IP network as the TCP traffic leaves room for UDP. If the UDP bit rate is very close to the maximum bit rate authorized on a link the only risk is the slowness of the repair.

If retransmission were to cause congestion it would then be necessary to wait for the end of transmission to initialize the repair process. The means described above remain unchanged.

The invention also provides for the root of the Merkle hash tree to be transmitted to the receivers before the data.

This root can be transmitted by any means preferably reliable means. In particular the data source is adapted to transmit the root of said Merkle hash tree to the receivers before the data by reliable multibroadcasting over said telecommunications network. Other transmission means can be envisaged of course such as a web page or electronic mail.

Similarly according to the invention said data source is adapted to transmit hashes of lower level than said root to the receivers after said root and before the data.

The invention also relates to a source of data multibroadcast to a plurality of receivers of said data via a telecommunications network noteworthy in that the data source is able to transmit the root of a Merkle hash tree of the data to the receivers before the data by reliable multibroadcasting over said telecommunications network.

Moreover said data source is able to transmit hashes of lower level than said root to the receivers after said root and before said data.

The invention further relates to a supervision server for a system for improving the reliability of transmission of multibroadcast data between a source of data and a plurality of receivers of said data via a telecommunications network noteworthy in that said supervision server is able to supply to each receiver a list comprising at least one other receiver said list being used to set up a reliable peer to peer connection between said receiver and said other receiver. The list also includes a reference source that has the data.

The invention further relates to a reference source for a system for improving the reliability of transmission of multibroadcast data between a source of data and a plurality of receivers of said data via a telecommunications network noteworthy in that said reference source has said data and is adapted to set up a reliable peer to peer connection with at least one receiver.

The invention further relates to a receiver in a system for improving the reliability of transmission of multibroadcast data between a source of data and a plurality of receivers of said data via a telecommunications network noteworthy in that said receiver comprises means for verifying the integrity of data supplied by said other receiver during a peer to peer connection.

Finally the invention relates to a system for improving the reliability of transmission of multibroadcast data between a source of data and a plurality of receivers . . . of said data via a telecommunications network said system comprising a supervision server adapted to provide each receiver with a list comprising at least one other receiver said receiver being able to receive missing data from said other receiver via a reliable peer to peer connection.

The system also includes a reference source having said data and appearing in at least one list supplied by said supervision server.

In the system each receiver comprises means for verifying the integrity of data supplied by said other receiver during a peer to peer connection.

In the system said verification means comprise means for calculating hashes of fragments of data received from at least one other receiver and means for comparing the calculated hashes with hashes of said fragments received from said data source.

In the system each receiver comprises means for verifying the integrity of hashes supplied by said other receiver during a peer to peer connection.

In the system the data source is able to transmit the root of said Merkle hash tree to said receivers before said data by reliable multibroadcasting via said telecommunications network.

In the system the data source is able to transmit hashes of lower level than said root to said receivers after said root and before said data.

