---

title: Thin client discovery
abstract: A method of assigning a resource to provide services to a thin client is disclosed. The thin client is discovered by receiving a response to a discovery request wherein the response is directed to a broker. The resource to allocate for the thin client is determined. The thin client to the resource is mapped. A connection to the thin client is requested to be established between the resource and the thin client.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08583831&OS=08583831&RS=08583831
owner: Samsung Electronics Co., Ltd.
number: 08583831
owner_city: Suwon-si
owner_country: KR
publication_date: 20071005
---
Thin clients can provide efficient use of compute resources across multiple users and multiple locations. Generally a thin client will connect to a broker and request a compute resource such as a virtual machine that can provide services to the client. Typically this is done by the thin client opening a browser initiating a connection with the broker and then interacting with the broker. However the ability to do this represents a certain level of complexity and cost for the thin client. It would be useful to further simplify the thin client to reduce the cost of the thin client system. With such a simplified thin client it would be useful to have a consistent method to connect the thin client and the compute resource.

The invention can be implemented in numerous ways including as a process an apparatus a system a composition of matter a computer readable medium such as a computer readable storage medium or a computer network wherein program instructions are sent over optical or communication links. In this specification these implementations or any other form that the invention may take may be referred to as techniques. A component such as a processor or a memory described as being configured to perform a task includes both a general component that is temporarily configured to perform the task at a given time or a specific component that is manufactured to perform the task. In general the order of the steps of disclosed processes may be altered within the scope of the invention.

A detailed description of one or more embodiments of the invention is provided below along with accompanying figures that illustrate the principles of the invention. The invention is described in connection with such embodiments but the invention is not limited to any embodiment. The scope of the invention is limited only by the claims and the invention encompasses numerous alternatives modifications and equivalents. Numerous specific details are set forth in the following description in order to provide a thorough understanding of the invention. These details are provided for the purpose of example and the invention may be practiced according to the claims without some or all of these specific details. For the purpose of clarity technical material that is known in the technical fields related to the invention has not been described in detail so that the invention is not unnecessarily obscured.

Thin client is a client device available to users of the system. In some embodiments these can be soft clients running on a personal computer PC instead of physical client device. Compute resource is a virtual machine or other types of compute resources that users log into. Compute resource may be a virtual machine remote universal serial bus USB device or other computing device for access by thin client . A thin client may be of low complexity and cost and without a local operating system OS software firmware or central processing unit CPU of any kind. Hence each thin client needs assistance to find any compute resource .

Broker is the device that assists thin client to find a compute resource . Thin client may be so limited in complexity that it needs assistance to find any broker . The broker is thus responsible for discovering thin client . In some embodiments the broker is responsible for further rendering a user interface to collect the information necessary to determine which compute resource the thin client ultimately gets connected to.

In step a device in the thin client system of is discovered. To allow a thin client of low complexity and cost the thin client may not have the capability to originate any network connections or discover the network autonomously. There are at least five methods for discovering thin clients in such a system 

1. Broadcast Discovery on local LAN segment The broker periodically sends out a broadcast packet on a local LAN segment probing for thin clients . All thin clients respond to that probe announcing their presence. The broker then keeps track of all thin clients in a local database. Once a thin client has been discovered the broker sends it a command driver level message telling it to no longer respond to discovery probes. By telling already discovered thin clients to not respond network bandwidth load on the broker can be reduced. The thin client uses a watchdog mechanism such that responding to discovery probes is re enabled if contact is lost with the broker or a connected compute resource .

2. Broadcast Discovery on remote LAN segment. This is identical to the Broadcast Discovery on local LAN segment method except that the broadcast request is expected to be routed by a router to a remote LAN segment. In many situations routers are configured to not forward broadcasts to remote segments in which case broadcast discovery may not be an appropriate discovery method.

3. Unicast Discovery This is similar to the Broadcast Discovery methods except that discovery probes are sent iteratively to a sequence or range of IP addresses. No response will be received from IP addresses that are either not valid or are not thin clients . The process is optimized such that addresses are no longer probed once they are discovered and addresses that were most recently discovered are probed with a higher priority and or rate as it is more likely a thin client will appear there because of the nature of Dynamic Host Configuration Protocol DHCP leases.

4. DHCP with Client Announce When a thin client powers up on a DHCP network it will get assigned an IP address by a DHCP server. Some DHCP servers will allow the DHCP response to include additional vendor or option codes. In such a case the DHCP server would supply an IP address for the broker . In these cases the thin client can then contact the broker and announce itself.

5. Thin Client Remote Assist For cases where the thin client is on a remote LAN segment where the broker cannot direct a broadcast and the broker has discovered a thin client on that remote LAN segment using any of these Discovery methods the broker can then ask that thin client to do a local broadcast probe searching for other thin clients . The responses from those thin clients are forwarded to the broker .

To allow a thin client of low complexity and cost discovery probes are nothing more than TNP configuration read requests except they are directed as a broadcast. Thin clients receiving this request process it normally and response with a standard configuration read response. Likewise the announcement used in the DHCP with Client Announce method are nothing more than a configuration read response to a configuration read request CRRQ that was generated virtually and locally at the thin client instead of being generated remotely over the network.

In step the discovered thin client is mapped to a possible compute resource that the thin client is entitled to or that the thin client and its user is entitled to. To allow a thin client of low complexity and cost the thin client may require the broker to perform all rendering of a user interface to determine a compute resource a user is allocated.

In step the broker then hands off the thin client s connection to the mapped compute resource . To allow a thin client of low complexity and cost the thin client may only permit one connection at a time so that the broker first tears down its connection to thin client and persuades the compute resource to connect to the thin client once the broker connection is torn down.

In step the operational connection between thin client and compute resource is maintained by broker . The thin client has a virtual or physical Help button that allows the thin client to request help outside of the operational connection. By asserting the Help button the user of thin client can 

1. Rollback Request a temporal rollback of the state of compute resource . In some embodiments this includes taking periodic snapshots of the state of compute resource every for example twenty four hours and allows the user to reload a previous state to compute resource .

2. Trouble Ticket File a trouble ticket with the thin client system administrator for assistance. In some embodiments this trouble ticket will be sent over email web phone pager or cell phone messaging service.

3. Broker Assistance Sending an escalating request to the currently connected compute resource the compute resource agent and the broker to regain control over an operational connection or rediscover the thin client . In some embodiments the thin client will be augmented to allow direct notification of the broker when the Help button is asserted.

4. Quarantine Quarantine the existing compute resource marking it as in need of repair and provide the user with a new compute resource.

5. Other Functions as customized by the system administrator using application programming interfaces APIs and or scripts.

After the connection is broken down the device remains discovered and returns to step for the next client or user entitlements.

TNP allows two or more devices to communicate with one another over a network while minimizing the size complexity and cost of the required implementation. In some embodiments TNP is implemented in hardware using digital logic. In some embodiments TNP is implemented in software. Any communication between devices can be considered to be the combination of a plurality of host to client interactions. In a given interaction the host is the initiator of the communication and the client is the target. On a network each device may simultaneously assume of the role of host and client and multiple hosts and clients may coexist on the network. Furthermore each device may simultaneously assume the role of multiple hosts and or multiple clients.

TNP allows for communication across any computer or telecommunications network. TNP transfers datagrams across the underlying network. In some embodiments TNP datagrams are transferred over UDP IP making it possible to use TNP over any IP capable network such as Ethernet wireless Ethernet or general packet radio service GPRS. 

TNP allows for two forms of host to client interactions. The first form is referred to as connection less transport and the second is referred to as connection oriented transport.

All interactions serve to transfer units of data referred to as messages between the host and client or the client and host. These messages are carried over the network using TNP datagrams . A message may be as short as 1 byte or as long as is supported by the particular embodiment. In some embodiments the size of the message is limited based on various factors including the amount of available buffering and the maximum transmit unit MTU on the underlying network. A message fits within a single TNP datagram to be transferred on the underlying network. A message may be considered a small portion of a larger data transfer. Messages may be used to transfer commands in addition to data. Commands are specially encoded data bytes requesting the host or client to perform a certain action.

Oob 1 bit Boolean to indicate if the TNP datagram is part of connection less transport or connection oriented transport. If the Oob bit is set the TNP datagram should be processed under the rules set forth for connection less transport. If the Oob bit is cleared the TNP datagram should be processed under the rules set forth for connection oriented transport 

Syn 1 bit Boolean to indicate when sequence numbers need to be synchronized as part of a connection oriented transport s connection setup sequence or when order ID need to be synchronized as part of a connection less transport interaction 

Nack 1 bit Boolean indicating if the TNP datagram is indicating that a lost TNP datagram was detected 

Rst 1 bit Boolean used for connection oriented transport indicating when a connection is being torn down 

AckSeqNo Sequence number of TNP datagram being acknowledged when the Ack bit is set or the sequence number of the next expected datagram when the Nack bit is set 

OrderId OrderId used to determine the order of TNP datagrams for connection less transport. Sequence numbers such as SeqNo and OrderId are compared using a circular comparison function 

Messages A TNP datagram with a payload may contain one or more messages. Each message may be 1 or more bytes in length. The special case of zero byte messages may also be optionally supported and

Connection oriented transport allows a series of messages to be reliably transferred in order between a host and a client. Before messages may be transferred the host initiates a connection setup sequence in order to establish a connection. Once the connection has been established messages may flow in either direction until either the host or client tears down the connection.

A host or client may have several established connections simultaneously. In some embodiments to reduce complexity and cost a client may be restricted to a small number of connections or one connection. When a TNP datagram is received by a host or client it determines if the TNP datagram is associated with connection oriented or connection less transport. Further it determines if the TNP datagram is associated with a currently established connection. The former is determine by examining the Oob bit in the TNP datagram and the latter is determine by examining various fields in the packet containing the TNP datagram and comparing those fields against a table of peers to which a connection is currently established in order to identify the peer and its associated connection.

The exact structure of the peers table is dependent on the type of network carrying the TNP datagrams . In some embodiments TNP datagrams are transported using UDP IP. In such an embodiment the peer would be identified by its IP address and UDP port number.

For each established connection the host and client maintains a set of resources such as a state variable associated with a state machine various sequence numbers and various timers. The description below of connection oriented transport makes references to these resources under the assumption that a unique resource is allocated for each connection.

A host may initiate a connection setup sequence to a client by sending a TNP datagram containing a connection request to the client. The client may either accept or refuse the connection by responding with a TNP datagram containing either a positive or negative acknowledgement. The connection is completed by the host sending the client a TNP datagram acknowledging that the connection setup is complete. This process is described in more detail below.

The host and client each maintain a state machine to assist with the process. The host state machine has the following states IDLE SYN ACK and CONNECTED. The client state machine has the following states IDLE SYN ACK and CONNECTED. Initially both the host and client are in the IDLE state. The following procedure is used 

Step 1. SYN First the host creates an entry in the peer table to help identify future TNP datagrams received as part of this connection. The host sends the client a TNP datagram with the Syn bit set and the SeqNo field set to the sequence number of the first TNP datagram of the connection for TNP datagrams traveling from the host to the client. This sequence number may be selected arbitrarily by the host. Once the TNP datagram is sent the host enters the SYN state 

Step 2. SYN ACK Once the client receives TNP datagram sent in step 1 adds an entry to its peer table enters the SYN ACK state and responds to the host with a TNP datagram with both the Syn and Ack bits set the SeqNo field indicating the sequence number of the first TNP datagram of the connection for TNP datagrams traveling from the client to the host and the AckSeqNo field set to the sequence number of the TNP datagram received in Step 1. The SeqNo selected by the client is also arbitrary and

Step 3. ACK Once the host receives the TNP datagram sent in step 2 it enters the ACK state and responds to the client with a TNP datagram with the Ack bit set the SeqNo field having been incremented and the AckSeqNo indicating the sequence number of the TNP datagram received in Step 2. Upon reception of this TNP datagram the client enters the CONNECTED state. After transmitting this ACK TNP datagram the host may begin transmitting TNP datagrams containing messages. Optionally the host may include a message in the TNP datagram sent in this step.

The TNP protocol is designed to be carried over unreliable networks. Hence datagrams may have been lost during any of these steps. The following rules are followed to ensure successful connection setup 

Rule 1 If the host transmits a SYN TNP datagram and does not receive a response within a reasonable amount of time SYN TIMEOUT it may re transmit the SYN request with the same sequence number. This may be repeated a reasonable number of times SYN MAX RETRY at which point the host should give up and enter the IDLE state 

Rule 2 If the client receives a SYN request from the same peer while in the SYN ACK state it re transmits the SYN ACK TNP datagram previously transmitted with the same sequence numbers previously used 

Rule 3 If after transmitting a SYN ACK the client does not receive an ACK within a reasonable amount of time SYNACK TIMEOUT it re transmits the SYN ACK TNP datagram previously transmitted with the same sequence numbers previously used. This may be repeated a reasonable number of times SYNACK MAX RETRY at which point the client should give up and enter the IDLE state 

Rule 4 If the host receives a SYN ACK TNP datagram while in the ACK state it re transmits the ACK TNP datagram previously sent with the same sequence numbers. Any packets sent after the ACK packet is also be re transmitted 

Rule 5 If the host is in the ACK state and receives a TNP datagram acknowledging a TNP datagram with a payload sent after the ACK packet in Step 3 then the host will enter the CONNECTED state 

Rule 6 If the client receives a SYN from its peer while in the CONNECT state it responds with a TNP datagram with the Ack bit set and AckSeqNo set to the sequence number of the most recently received valid TNP datagram and

Rule 7 If while in the SYN state the host receives a packet with the Ack bit set and the Syn bit is not set it responds with a packet with only the Rst bit set.

If the client receives a connection request but does not have the resources to accept the connection or does not wish to accept the connection for any other reason it refuses the connection by responding with a packet with both the Syn and Nack bits set and the AckSeqNo field set to the sequence number of the SYN packet requesting the connection.

Optionally the client need not implement the SYNACK TIMEOUT and SYNACK MAX RETRY mechanisms. Instead the burden of detecting a lost Step 3 ACK may be placed on the host. This is accomplished by always including a message in the ACK TNP datagram sent in Step 3. When the client receives the TNP datagram containing the ACK and message it will respond with an acknowledgement. The host may use the acknowledgement to determine when the Step 3 ACK has been received by the client and the connection setup sequence is complete. If after sending the Step 3 ACK to the client the host does not receive an acknowledgement within a reasonable amount of time it should retransmit the Step 3 ACK. This may be repeated a reasonable number of times if necessary at which point the host may give up and return to the IDLE state.

Once the connection between the host and client has been setup TNP datagrams continue to flow between the host and client to maintain connection state transfer messages and ensure reliable reception of messages. Once connected a TNP datagram may contain an acknowledgement or payload or both. The SeqNo field contains a valid sequence number. The SeqNo field of TNP datagrams without a payload contains the sequence number of the next TNP datagram with a payload that will be transmitted. For TNP datagrams with the Ack bit set the AckSeqNo field contains the sequence number of the last TNP datagram with a payload received For TNP datagrams with the Nack bit set the AckSeqNo field contains the next expected sequence number of a TNP datagram with a payload.

Rule 1 The host maintains a TXSEQNO sequence number to keep track the sequence number of transmitted TNP datagrams 

Rule 2 The TXSEQNO may be initialized to any value. The initial value is transmitted in the SYN packet initiating the connection. The TXSEQNO is incremented when the host receives the SYN ACK TNP datagram that pushes it into the ACK state 

Rule 4 If a TNP datagram is transmitted with a payload then TXSEQNO is incremented after the packet is transmitted 

Rule 6 If the host receives a TNP datagram with the Ack bit set then all previously transmitted packets with a sequence number SeqNo less then or equal to the AckSeqNo field of the received TNP datagram are considered to be acknowledged 

Rule 7 If the host does not receive an acknowledgement for a previously transmitted TNP datagram within a reasonable amount of time PACKET TIMEOUT it retransmits that TNP datagram and all subsequent TNP datagrams with their respective sequence numbers. When re transmitting a TNP datagram the Ack Nack and AckSeqNo fields are updated to reflect the current state 

Rule 8 The host maintains an RXSEQNO sequence number to keep track of the sequence number of received TNP packets 

Rule 9 The RXSEQNO is initialized to the value of the SeqNo field 1 in the SYN ACK TNP datagram that pushed the host into the ACK state 

Rule 10 If a TNP datagram with a payload is received with SeqNo equal to RXSEQNO then the payload may be accepted and RXSEQNO incremented. If the host does not have enough buffering to accept the payload it may discard the payload but still processes the other fields in the header. The host should transmit a TNP datagram to the client with the Ack bit set and AckSeqNo set to the SeqNo of the received packet. The host may choose to delay transmission of the Ack until payload is available to be sent with it or until multiple Acks can be combined together. However the host should not delay transmission of the Ack so long that the client retransmits the original packet. If the payload of the datagram was discarded then RXSEQNO should not be incremented and a TNP datagram containing an Ack should not be sent. The client may optionally transmit a TNP datagram containing a Nack to the host indicating that the payload was lost and it needs to be retransmitted 

Rule 11 If a TNP datagram with or without a payload is received with SeqNo greater than RXSEQNO then the host transmits a TNP datagram to the host with the Nack bit set and AckSeqNo set to RXSEQNO. The payload of any such packet is discarded and

Rule 12 The host should retransmit the most recently transmitted Ack with each TNP payload packet transmitted.

Rule 1 The client maintains a TXSEQNO sequence number to keep track the sequence number of transmitted TNP datagrams 

Rule 2 The TXSEQNO may be initialized to any value. The initial value is transmitted in the SYN ACK TNP datagram initiating the connection. The TXSEQNO is incremented when the client receives the ACK TNP datagram that pushes it into the CONNECTED state 

Rule 4 If a TNP datagram is transmitted with a payload then TXSEQNO is incremented after the packet is transmitted 

Rule 7 If the client receives a TNP datagram with the Ack bit set then all previously transmitted TNP datagrams with a sequence number SeqNo less then or equal to the AckSeqNo field of the received packet are considered to be acknowledged 

Rule 8 If the client does not receive an acknowledgement for a previously transmitted TNP datagram within a reasonable amount of time PACKET TIMEOUT it retransmits that TNP datagram and all subsequent packets with their respective sequence numbers. When retransmitting TNP datagrams the Ack Nack and AckSeqNo fields are updated to reflect the current state 

Rule 9 The client maintains an RXSEQNO sequence number to keep track of the sequence number of received TNP packets 

Rule 10 The RXSEQNO is initialized to the value of the SeqNo field 1 in the SYN packet that pushed the client into the SYNACK state 

Rule 11 If a packet with a payload is received with SeqNo equal to RXSEQNO then the payload may be accepted and RXSEQNO incremented. If the client does not have enough buffering to accept the payload it may discard the payload but still processes the other fields in the header. The client should transmit a TNP packet to the host with the Ack bit set and AckSeqNo set to the SeqNo of the received packet. The client may choose to delay transmission of the Ack until payload is available to be sent with it or until multiple Acks can be combined together. However the client should not delay transmission of the Ack so long that the host retransmits the original packet 

Rule 12 If a packet with or without a payload is received with SeqNo greater than RXSEQNO then the client transmits a packet with the Nack bit set and AckSeqNo set to RXSEQNO. The payload of any such packet is discarded and

Rule 13 The client should retransmit the most recently transmitted Ack with each TNP datagram transmitted containing a payload.

Both the host and client each maintain a PACKET TIMEOUT timer that determines how long the host or client should wait before assuming that a TNP datagram was lost and retransmitting it. For example if the PACKET TIMEOUT timer is set to 5 ms on the client then the client would wait for 5 ms after transmitting a TNP datagram to the host and if at that time the TNP datagram has not been acknowledged then it would retransmit the TNP datagram .

The host and client may use different values for the PACKET TIMEOUT. The value of the PACKET TIMEOUT timer is determined based on the round trip TNP datagram to acknowledgement delay. It is up to the host or client to measure this round trip delay and determine the appropriate value of PACKET TIMEOUT. The client may optionally not implement the functionality to measure round trip delay and program PACKET TIMEOUT appropriately. In such a case the host would be responsible for measuring round trip delay and instructing the client as to the appropriate value to be used for PACKET TIMEOUT.

An existing connection can be disconnected by sending a TNP datagram with the Rst bit set. A host wishing to teardown a connection should use the following procedure 

Step 1. Wait until all out standing TNP datagrams have been acknowledged including retransmitting TNP datagrams as necessary. If this does not occur within a reasonable amount of time proceed to step 2 

Step 3. RSTACK Wait until the client responds with a TNP datagram with the Rst and Ack bits. If this TNP datagram is not received within a reasonable amount of time return to step 2. If this procedure is repeated a reasonable number of times without success the host may consider the connection tear down complete.

Step 1. Wait until all out standing TNP datagrams have been acknowledged including retransmitting TNP datagrams as necessary. If this does not occur within a reasonable amount of time proceed to step 2 

Step 3. RSTACK Wait until the host responds with a TNP datagram with the Rst and Ack bits. If this TNP datagram is not received within a reasonable amount of time return to step 2. If this procedure is repeated a reasonable number of times without success the client may consider the connection tear down complete.

Rule 2 If after sending a RST TNP datagram the host does not receive a response containing an RSTACK within a reasonable amount of time PACKET TIMEOUT it retransmits the RST. This may be repeated a reasonable number of times RST MAX RETRY 

Rule 3 If the host receives an RST TNP datagram from its peer while in the CONNECTED state it responds with an RSTACK and

Rule 2 If the client receives an RST TNP datagram from its peer while in the CONNECTED state it responds with an RSTACK 

Rule 4 If after sending a RST TNP datagram the client does not receive a response containing an RSTACK within a reasonable amount of time PACKET TIMEOUT it retransmits the RST. This may be repeated a reasonable number of times RST MAX RETRY and

The client may optionally implement a timeout known as a activity timeout that results in the connection being torn down if no TNP datagrams are received for a reasonable amount of time. In such a case the host may implement a keep alive mechanism that periodically ensures that a TNP datagram is transmitted to the client to keep the connection established and prevent the client for initiating a connection tear down. This keep alive packet need not contain anything other than the required fields but may optionally contain an Ack.

If an atypically high rate of TNP datagrams loss is experienced it may be an indication of congestion on the network. The host and or client may implement mechanisms to detect TNP datagram loss and respond by reducing the amount of data being sent onto the network.

To reduce complexity and cost of the client the client may optionally not implement its own congestion control mechanisms. Instead the host can detect when TNP datagrams transmitted from the client to the host are being lost and respond by sending a command to the client instructing it to reduce its bandwidth utilization.

For connection oriented transport a copy of each TNP datagram sent is stored in a buffer until it is acknowledged. This buffer is referred to as the replay buffer. If the size of the replay buffer is smaller than the round trip TNP datagram to acknowledgement delay then transfer rate may be limited. In general the maximum data rate of a connection can be characterized by the following equation MaxRate ReplayBufferSize RoundTripDelay

For example a replay buffer of 15 KB with a round trip delay of 20 ms would limit the data rate to 6.1 Mbps. The replay buffer should be sized by the client and host keeping in mind typical data rates and round trip delays. ReplayBufferSize MaxRate RoundTripDelay

Hence if 10 Mbps of bandwidth is required on a network with a 50 ms round trip delay the minimum recommended replay buffer size is 64 KB.

The client or host may optionally choose to use a smaller replay buffer to save on resources with the understanding that the maximum transfer rate will be limited. This may be acceptable for certain applications.

There is no need for the replay buffer sizes in the client and host to be matched. In a scenario where high data rates and required in one direction and not the other it may make sense to size the buffers such that one is large and the other is small.

Because TNP datagrams are buffered before they are transmitted resources may be saved by reducing the maximum allowable size of a TNP datagram that the client or host will transmit. There is no need for the maximum allowable size of be the same on the client and host. One may choose to transmit large packets while the other chooses to transmit only small packets.

Depending on the particular embodiment complexity and or resource requirements may be shifted from the client to the host using one or more of the following methods 

Method 1 Congestion control mechanisms may be implemented only on the host side. The host would detect TNP datagram loss and instruct the client as to its maximum bandwidth utilization 

Method 2 The SYNACK TIMEOUT and SYNACK MAX RETRY timers may be removed from the client side. The host would implement additional recover mechanisms to detect these error conditions. The three way handshake would be replaced with a four way handshake as described above 

Method 3 The client may limit the number of connections it is capable of simultaneously accepting to a small number such as one 

Method 4 The client may limit the size of the retry buffer to reduce the amount of required resources 

Method 5 The client may limit the maximum size of a TNP datagram that it will transmit to reduce required resources 

Method 7 The client may choose to not support connection oriented transport and to only support connection less transport 

Method 9 Many of the timeouts and retry counters described above are programmable in value. The client may choose to allow the host to control these values instead of trying to control them itself. For example the PACKET TIMEOUT timer that determines the amount of time before the client will retransmit a TNP datagram may be programmable by the host. The host will program the client with the appropriate PACKET TIMEOUT value based on the round trip delay as measured by the host.

Further methods may exist to shift complexity from the client to the host. There are additional mechanisms that reduce the required complexity and or resources on the client. For example the client does not need to implement the mechanisms necessary to initiate a new connection because connections are always initiated by the host. Furthermore the client need not implement a keep alive mechanism as this is the responsibility of the host.

A connection less transport interaction may consist of one two or three stages depending on the requirements of the interaction. These three stages are 

Stage 2. Optionally the client may respond with a TNP datagram containing no messages and an acknowledgement of the reception of the TNP datagram received in stage 1 and

Stage 3. Optionally the client may respond with one or more datagrams containing one or more messages in response to the message s received in stage 1.

Legal interactions include stage 1 only stages 1 and 2 only stages 1 and 3 only all three stages or stage 1 with stages 2 and 3 being combined into the same TNP datagram or datagrams .

During this interaction it is possible that one or more TNP datagrams will be lost. In such a case recovery mechanisms may be used to retransmit the lost messages.

Message transfer between the host and client is asymmetric in that a heavier burden is placed on the host to correct for TNP datagram loss if desired. TNP datagrams transmitted from the host to the client are acknowledged. If after transmitting a TNP datagram the host does not receive an acknowledgement then either the original TNP datagram was lost or its acknowledgement was lost. Because it is not possible to determine which of the two was lost recovery is left to higher levels in the network stack. The TNP host will notify higher levels which packets were acknowledged and which were not.

Rule 1 If the host or client receives a TNP datagram with the Oob bit set and no payload it is discarded 

Rule 2 If the client receives a TNP datagram with the Oob bit set the NoAck bit cleared and a payload it responds with an Acknowledgement TNP datagram . The acknowledgement TNP datagram has the Oob and Ack bits sets SeqNo is undefined AckSeqNo set to the value of the SeqNo of the TNP datagram being acknowledged and no payload. Exactly one Acknowledgement TNP datagram is sent for each packet received 

Rule 3 The value of the SeqNo field of all Oob packets transmitted from the client is always undefined 

Rule 4 After processing the messages the client may choose to send TNP datagrams including response messages to the host and

Rule 5 In order to distinguish acknowledgements from one another the host should not recycle sequence numbers until all numbers in the sequence number space have been exhausted.

TNP datagrams sent from the client to the host are not acknowledged. The client has no way of knowing if a transmitted TNP datagram was lost. If the host was expecting a TNP datagram that was not received recovery may be attempted by higher levels in the network stack.

It is possible for the host to have several host client interactions as described above in flight simultaneously. In other words the host does not need to wait until a TNP datagram has been acknowledged before sending additional TNP datagrams associated with subsequent interactions.

Because TNP datagrams my be delivered out of order it is useful to provide a mechanism such that the client can distinguish when TNP datagrams from the host have been received out of order in the case of multiple outstanding host client interactions.

For any series of interaction between a host and client the client should maintain an ORDERID state variable. If a TNP datagram arrives with both the Ordered and Syn bits set the ORDERID state variable should be set to value of the OrderId field in the TNP datagram . If a TNP datagram arrives with Ordered bit set the Syn bit cleared and the OrderId field in the TNP datagram less than the ORDERID state variable then the TNP datagram should be discarded and a NACK TNP datagram sent to the host with the AckSeqNo field set to the SeqNo of the TNP datagram being discarded. Otherwise if a TNP datagram arrives with the Ordered bit set then the ORDERID state variable should be set to the value of OrderId in the TNP datagram . TNP datagrams with the Ordered bit cleared should be treated normally according to the rules described above.

A host communicating with a client through a series of interactions should increment the OrderId field in the TNP datagram only when order is important. It may be possible that several TNP datagrams sent in sequence are not sequence dependent. In such a case they may be sent all with the same OrderId.

The first time a host sends a TNP datagram to a client with the Ordered bit set it should also set the Syn bit to indicate to the client that it should initialize its ORDERID state variable. The host should continue to set the Syn bit until a TNP datagram with the Syn bit is acknowledged.

A host that wishes to maintain order for TNP datagrams need not set the Ordered bit for all TNP datagrams . The host may choose to set the bit only for TNP datagrams for which sequence is important.

To reduce implementation complexity or required resources the client may choose to not support ORDERID. In such a case the Ordered bit in the TNP datagram should be ignored.

To reduce implementation complexity or required resources the client may choose to limit the number of hosts for which it maintains an ORDERID state variable. Furthermore this may be limited only to hosts for which a connection oriented transport connection has been established.

TNP allows messages to be transferred in either direction between the host and client. Because there may be one or more producers or consumers of messages it may be useful to allow each message to be associated with a particular producer or consumer. In some embodiments a field in each message is included called EndPoint. The EndPoint field indicates which message consumer the message is destined to. Each message consumer is referred to as an end point.

A network may have many hosts and clients on it and further there may be one or more types of hosts or clients on the network. For example a network may simultaneously have a terminal server and a voice over internet protocol gateway each acting as hosts and a thin client and voice over internet protocol handset each acting as a client. Hence it is useful to provide standard mechanisms that clients may implement to aid with detection of a client determination of the type of client and configuration of the client.

In some embodiments an End Point with ID 0 is implemented that is common across all types of devices. Any message received in a TNP datagram with an EndPoint field of 0 is processed by End Point Zero.

Messages sent to End Point Zero of a client contain commands also referred to as operations. The client may respond to a command by sending a message to End Point Zero of the host that the command arrived from. When End Point Zero of a client processes a message it stores the source of the TNP datagram that the message arrived in so that it can send a response back to the same host if necessary.

Furthermore a client may choose to send messages to End Point Zero of a host to notify the host of certain events such as interrupts or error conditions. These messages are initiated by the client and are not necessarily in response to a command sent by the host.

OpCode This field indicates the type of operation carried by the message. Valid OpCodes include No Operation Configuration Read Configuration Read Return Configuration Write CSR Write CSR Read CSR Read Return Interrupt and Error 

End Point Zero on the client allows the host to detect and configure clients on the network. Access to the client is performed through Read and Write operations to resources on the client. The host indicates which resource is being operated on through an address field which is used to address the resources. End Point Zero has two address spaces referred to as Configuration address space and CSR address space.

Rule 2 Whenever End Point Zero on the client receives a message requesting that an operation be performed and the operation requires that a response be sent back to the host then the response message is sent to End Point Zero of the peer that the operation request arrived from using the same type of transport connection less or connection oriented that the request arrived on 

Rule 3 If the operation is a Configuration Read Request then the resources located at the address in the Address field of the request through address Address Length 1 inclusive of the configuration address space should be read and the data returned in an End Point Zero Message with OpCode Configuration Read Return the read data in the Data field and all other field being preserved from the original request 

Rule 4 If the operation is a CSR Read Request then the resources located at the address in the Address field of the request through address Address Length 1 inclusive of the CSR address space should be read and the data returned in an End Point Zero Message with OpCode CSR Read Return the read data in the Data field and all other field being preserved from the original request 

Rule 5 If the operation is a Configuration Write Request then the resources located at the address in the Address field of the request through address Address Length 1 inclusive of the configuration address space should be written with the data in the Data field of the request 

Rule 6 If the operation is a CSR Write Request then the resources located at the address in the Address field of the request through address Address Length 1 inclusive of the CSR address space should be written with the data in the Data field of the request 

Rule 7 An interrupt controller connected to End Point Zero may request than an interrupt be sent to the host. In such a case a End Point Zero Message with OpCode Interrupt should be sent to the host. The Address Data and Transaction ID fields can be used to carry further information identifying the source type and characteristics of the interrupt. The interrupt controller would have to inform End Point Zero of which hosts to transmit an interrupt to although by default the interrupt would be sent to all hosts with an established connection to the client and

Rule 8 If an error occurs while completing a read or write request either because of an invalid address a timeout or some other error condition the client may wish to send an error response to the host. In such a case an End Point Zero Message with OpCode Error and all other fields being preserved should be sent back in place of the response.

In some embodiments the resources in configuration address space are intended to be the same across all types of devices. These resources are used to determine the type of device and to configure common aspects of these devices. Those resources unique to a device are intended to be in the CSR address space. Likewise the properties of End Point Zero are intended to be common across all devices and all other end points are intended to be used for purposes unique to each type of device.

When a client is initially powered on or attached to a network it may wish to establish a connection with a host. Because a host initiates a connection requests there are multiple mechanisms in place to help a client to be found and connected to by a host as described in step .

In some embodiments Broadcast Discovery of step involves a host periodically sending out a broadcast onto the network searching for clients. A TNP datagram broadcast onto the network will contain a message to End Point Zero containing a Configuration Read Request operation to address 0x0000. Each client on the network that receives this request will send a Configuration Read Return message back to the host. Hence by periodically repeating this process the host will eventually collect a list of all clients on the network.

When processing broadcast requests clients may choose to wait a random amount of time before transmitting the response. This will ensure that a response storm does not hit the network at once from a large number of clients.

Once a client has been discovered by a host the Broadcast Enable bit in the TNP Capability Structure should be disabled to prevent it from responding to future broadcasts. This bit is periodically re disabled to prevent it from being re enabled by the BCASTEN TIMEOUT timer. The purpose of the timer is to allow the device to be rediscovered if the host that disabled the Broadcast Enable bit disappears from the network unexpectedly.

In some embodiments Broadcast Discovery of step involves the client periodically sending out a broadcast onto the network to announce its presence. The broadcast is a TNP datagram with a message to End Point Zero with an OpCode of Announce and the remainder of the message being identical to a Configuration Read Return to address 0x0000 and a length of 4 words.

In some embodiments Unicast Discovery of step involves the client periodically sending an announcement message to a particular host. The identity of the host already is known to the client through some other means such as a smart card or other form of non volatile storage.

Some network devices are required to implement the Address Resolution Protocol ARP to translate IP addresses to Ethernet or other L2 addresses. A typical ARP implementation has two components Response and Request. The response component will listen to the network for ARP requests and send a response back. The request component will send requests onto the network and listen on the network for a response.

The client may be simplified by only implementing the response component of ARP and not the request component. In such a case the client will be limited in that it will not be able to send packets to IP addresses from which a packet was net recently received. Because the host will normally initiate a connection to the client the client will know the Ethernet address of the host before sending it a response.

In step the DHCP server responds to the DHCP request of thin client by sending the IP addresses of both the network gateway and the broker . If it is determined at step that the IP address of broker is on the same subnet as the thin client then control is transferred to step . If it is determined at step that the IP address of broker is not on the same subnet as the thin client then control is transferred to step .

In step the thin client may use ARP to request the medium access control MAC address of broker . In step the thin client uses ARP to request the MAC address of the network gateway. In step the thin client uses the MAC address from step or step to generate a virtual CRRQ. In step the thin client responds to the virtual CRRQ of step in a manner similar to that used in the Broadcast Discovery or Unicast Discovery methods.

In step the broker receives the type of thin client . Throughout this specification a thin client type refers to the actual genre of device used as a thin client . Three examples of a thin client type are a keyboard video mouse terminal a voice over IP VoIP phone or a network printer. The broker also receives the IP address of thin client . The broker then consults a local or remote database based on the type and IP address of thin client .

If it is determined in step that the database query result requires user credentials of the current user on thin client then control is passed to step . If it is determined in step that the database query result does not require user credentials of the current user on thin client then control is passed to step .

In step the broker then determines the user and client entitlements based on user credentials gathered at the thin client . To allow a thin client of low complexity and cost the broker may render the remote access user interface RAUI for gathering user credentials at thin client . In some embodiments the broker may use the thin client information gathered and consult a local or remote database to map a physical location to thin client . In some embodiments the broker may use the user information gathered and consult a local or remote database to determine a list of active sessions for the user. A list of the compute resources is determined for selection and throughout this specification this is called the resource allocation policy. In some embodiments the user may be presented with the full or partial list for selection. In some embodiments a compute resource may be autoselected without the user s assistance.

In step the broker determines client entitlements based on credentials gathered at the thin client in step . In some embodiments the broker may use the thin client information gathered and consult a local or remote database to map a physical location to thin client . A list of the compute resources or resource allocation policy is determined for selection. In some embodiments the user may be presented with the full or partial list for selection by the broker rendering a screen with the list and then monitoring thin client for keyboard mouse or input events. In some embodiments a compute resource may be autoselected without the user s assistance. In step the compute resource is selected and assigned for mapping to the thin client .

In step the broker renders the RAUI as a bitmap to include a window for requesting user credentials including a username and a password. This rendered bitmap is sent over TNP to the thin client . The thin client then sends the keyboard mouse or other input device events that contain the user credentials back to broker .

In step the broker then consults a special database called a directory server local or remote with the user credentials. In some embodiments a Microsoft Active Directory Server is used for the directory server. If it is determined in step that the user credentials are valid then control is transferred to step . If it is determined in step that the user credentials are invalid or not known then control is transferred back to step to repeat the request.

In step the directory server is consulted with the valid user credential to look up all groups associated with the user. In step a local or remote database is used to provision resources available to those groups for example cross referencing the groups associated with the user with a list of compute resources available to those groups. In step the resource allocation policy is assembled from the database query from step for either the user or broker to select from.

a thin client system administrator brand bitmap to identify the thin client system or its administrator 

a thin client system architecture or service provider bitmap to identify the thin client service provider 

an input frame for user credentials including username password and any other applicable credentials such as workgroup or user domain 

a confirmation frame that would allow the user to logon with the credentials input in or alternately cancel and clear the input frame and

an advanced button to allow for more advanced or customizable options such as the ability to allow a user to self help including one or more of requesting a temporal rollback of the state of compute resource filing a trouble ticket with the thin client system administrator for assistance sending an escalating request to the currently connected compute resource and quarantining the existing compute resource.

The remote access user interface screen may be customizable by the system administrator using skins application program interfaces APIs and scripts.

In step after discovery in step the broker tells the thin client to turn off the discovery mechanism to prevent a rediscovery process. In step the broker determines the compute resource for thin client . In some embodiments the process of is included in this step .

In step the broker communicates to a compute resource agent running on compute resource to indicate the thin client is ready to connect to compute resource . The compute resource agent on compute resource acknowledges it will attempt a connection.

In step the broker may tear down its connection to thin client . To allow a thin client of low complexity and cost the thin client may not have the capability to originate any network connections and may only permit one connection at a time. Thus the broker and compute resource may not be able to both connect to the thin client at the same time. In step the compute resource agent on compute resource establishes its connection to thin client and hand off is complete.

In state the thin client is considered Undiscovered with No current connection. To allow a thin client of low complexity and cost the thin client may not have the capability to originate any network connections or discover the network autonomously. In this state the thin client will respond to any discovery requests or connection requests.

State transition from state to state occurs if the user of thin client activates the thin client asserting that a session should begin and commences thin client discovery. In some embodiments this state transition between state and is included in step of .

In state the thin client is considered Discovered with its current connection to broker . To allow a thin client of low complexity and cost the thin client may only permit one connection at a time. In this state thin client does not respond to any further discovery requests and does not process any further connection requests because of its connection to broker .

State transition from state to state occurs if the broker determines the resource allocation policy for thin client and determines a possible mapped compute resource for the operational connection. In some embodiments this state transition between state and is included in step of .

In state the thin client is considered Discovered with no current connection. In this state thin client does not respond to any further discovery requests but will process any connection requests the most likely being a connection request from mapped compute resource .

State transition from state to state occurs if a connection timer reaches zero. This may happen if the mapped compute resource cannot or will not commence the operational connection to thin client in time. State transition from state to state also occurs if the Help button is asserted indicating that the user of thin client has an issue with the discovery process.

State transition from state to state occurs if the handoff to compute resource is completed successfully. In some embodiments this state transition between state to state is included in step of .

State transition from state to state occurs if a special watchdog timer reaches zero. This may happen if the mapped compute resource is not functioning properly and the broker is also not functioning properly.

In state the thin client is considered Discovered with a current connection to mapped compute resource . In this state thin client does not respond to any further discovery requests and does not process any further connection requests because of its connection to mapped compute resource .

State transition from state to state occurs if the user of thin client logs off the current operational connection to allow the thin client to return to a Discovered state for the next user. State transition from state to state also occurs if the Help button is asserted indicating that the user of thin client has an issue with the discovery process.

State transition from state to state occurs if a special watchdog timer reaches zero. This may happen if the mapped compute resource is not functioning properly and the broker is also not functioning properly.

an option to rollback the current session with a variable or fixed time to rollback for example twenty four hours 

an option to save the current session s state so that the user can take the state with them via a nonvolatile memory card for example a USB pen drive.

Although the foregoing embodiments have been described in some detail for purposes of clarity of understanding the invention is not limited to the details provided. There are many alternative ways of implementing the invention. The disclosed embodiments are illustrative and not restrictive.

