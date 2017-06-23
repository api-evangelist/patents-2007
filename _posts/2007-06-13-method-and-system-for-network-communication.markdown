---

title: Method and system for network communication
abstract: A method and system for network communication is provided. The method for network communication comprises setting a data size for a network connection, wherein the data size represents an amount of network data a network adapter can send to a host system for the network connection before the network adapter waits for an application to accept any data that has been sent to the host system; monitoring the amount of network data that is received by a host system driver; monitoring the amount of network data that is sent by the network adapter; and suspending transfer of network data to the host system, if the amount of network data sent by the network adapter is similar to the set data size.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08102769&OS=08102769&RS=08102769
owner: QLOGIC, Corporation
number: 08102769
owner_city: Aliso Viejo
owner_country: US
publication_date: 20070613
---
The present invention relates to network systems and more particularly to offloading host system tasks for managing network related operations.

Computer networks are commonly used in various applications. Computing systems typically use a network adapter to communicate with other networked devices. Continuous efforts are being made to efficiently improve processing of network data.

In one embodiment a method for network communication is provided. The method comprises setting a data size for a network connection wherein the data size represents an amount of network data a network adapter can send to a host system for the network connection before the network adapter waits for an application to accept any data that has been sent to the host system monitoring the amount of network data that is received by a host system driver monitoring the amount of network data that is sent by the network adapter and suspending transfer of network data to the host system if the amount of network data sent by the network adapter is similar to the set data size.

In another embodiment a method for network communication is provided. The method comprises setting a data size for a network connection wherein the data size represents an amount of network data a network adapter can send to a host system for the network connection before the network adapter waits for an application accept any data that has been sent to the host system monitoring an amount of network data that is received by a host system driver wherein a value for a first counter for a host system memory indicates the amount of network data received by the host system driver monitoring an amount of network data that is sent by the network adapter wherein a value for a second counter for a network adapter memory indicates the amount of data that is sent to the host system and suspending transfer of network data to the host system if the amount of network data sent by the network adapter is similar to the set data size.

In yet another embodiment a system for network communication is provided. The system comprises a host system executing an application for communicating with at least one networked device and a network adapter interfacing with the host system and receiving network data from the at least one network device wherein a data size is set for a network connection and the data size represents an amount of network data the network adapter can send to the host system for the network connection before the network adapter waits for the application to accept any data that has been sent to the host system and the network adapter suspends transfer of network data to the host system if the amount of network data sent by the network adapter is similar to the set data size after monitoring the amount of network data that is received by a host system driver and monitoring the amount of network data that is sent by the network adapter.

This brief summary has been provided so that the nature of the invention may be understood quickly. A more complete understanding of the invention can be obtained by reference to the following detailed description of the various embodiments thereof concerning the attached drawings.

To facilitate the understanding of the various embodiments a top level description of common network protocols standards and the general architecture operation of a host system will be described. The specific architecture and operation of the various embodiments will then be described with reference to the general architecture.

Computing systems and devices use various protocols standards for network communication. Computer networks typically use a layered protocol structure to manage network traffic. One common model that is typically used is an ISO model that includes a physical layer a data link layer that includes a MAC layer a network layer and other layers also. Upper level protocol layers ULPs for example iSCSI and RDMA described below interface with a network layer to send and receive data from the network.

Transmission Control Protocol Internet Protocol TCP IP TCP is a standard network protocol incorporated herein by reference in its entirety that provides connection oriented reliable byte stream service. This means that two nodes establish a logical connection before sending data and TCP maintains state information regarding the data transfer. Reliable means that data is delivered in the same order that it was sent. A byte stream service means that TCP views data to be sent as a continuous data stream that is sent in any way it sees fit and delivers it to a remote node as a byte stream.

IP is a standard protocol incorporated herein by reference in its entirety that provides a datagram service whose function is to enable routing of data through various network subnets. Each of these subnets could be a different physical link such as Ethernet ATM or others. IP layer is responsible for fragmentation of transmit data to match a local link s maximum transmission unit MTU . IP layer fragments data at a source node or at any intervening router between a source and a destination node.

iSCSI Protocol Internet SCSI iSCSI protocol as defined by the Internet Engineering Task Force IETF maps the standard SCSI protocol on top of the TCP IP protocol. iSCSI incorporated herein by reference in its entirety is based on the Small Computer Systems Interface SCSI standard which enables host computer systems to perform block level input output I O operations with a variety of peripheral devices including disk and tape devices optical storage devices as well as printers and scanners. The iSCSI and TCP IP protocol suite consist of four protocol layers the application layer of which iSCSI is one layer the transport layer TCP the network layer IP and the link layer i.e. Ethernet .

A traditional SCSI connection between a host system and peripheral device is through parallel cabling and is limited by distance and device support constraints. For storage applications iSCSI was developed to take advantage of network architectures based on Ethernet standards.

The iSCSI architecture is based on a client server model. Typically the client is a host system such as a file server that issues a read or write command. The server may be a disk array that responds to the client s request. Typically the client is an initiator that initiates a read or write command and a disk array is a target that accepts a read or write command and performs the requested operation.

In a typical iSCSI exchange an initiator sends a read or write command to a target. For a read operation the target sends the requested data to the initiator. For a write command the target sends a Ready to Transfer Protocol Data Unit PDU informing the initiator that the target is ready to accept the write data. The initiator then sends the write data to the target.

Once the data is transferred the exchange enters the response phase. The target then sends a response PDU to the initiator with the status of the operation. Once the initiator receives this response the exchange is complete. The use of TCP guarantees the delivery of the PDUs.

Typically logical units in a target process commands. Commands are sent by a host system in Command Descriptor Blocks CDB . A CDB is sent to a specific logical unit and may include a command to read a specific number of data blocks. The target s logical unit transfers the requested data block to the initiator terminating with a status message indicating completion of the request. iSCSI encapsulates CDB transactions between initiators and targets over TCP IP networks.

As iSCSI becomes popular various software solutions to execute the iSCSI layer in software are emerging. Host system software typically executes the iSCSI layer in software. However this process is slow and may consume host system processor time and resources especially for generating digests and checking cyclic redundancy code CRC .

Operating systems for example Microsoft Chimney support offloading of TCP IP protocol stack from a host system to a network adapter but do not solve digest and data copy problems for the iSCSI layer. For example Microsoft defines a data receive algorithm for interoperation between a TCP IP Offload Engine TOE Driver described below and the Microsoft Chimney Operating System to deliver a limited amount of data up to a Maximum Segment Size when data becomes available. The TOE Driver is blocked from delivering any more data to an Upper layer Protocol ULP until the ULP accepts or rejects the delivered data. The ULP may post additional data that may be received after the delivered data.

This process has significant latency between arrival of data and availability of a buffer memory storage to store data

A TOE Module described below holds off delivery of data to the TOE Driver while the TOE Driver is waiting for the ULP to post a buffer. The ULP only posts a buffer large enough for the delivered data and the TOE Driver notifies the TOE Module to deliver the next data. In this case the TOE Driver TOE module interaction adds to the latency of data delivery to the ULP.

In another case when the TOE Module does not hold off delivery of data while the TOE Driver is waiting for a response from the ULP the TOE Driver holds the received data in an anonymous buffer and then copies the data to the buffers posted by the ULP. This unnecessarily uses host system processor time and resources since data that is buffered by the TOE Driver has to be copied to ULP buffers consuming CPU cycles. The present adaptive aspects described below tackle the latency issue.

RDMA Remote Direct Memory Access RDMA is a standard upper layer protocol incorporated herein by reference in its entirety that assists one computer to directly place information in another computer s memory with minimal demands on memory bus bandwidth and CPU processing overhead. RDMA over TCP IP defines interoperable protocols to support RDMA operations over standard TCP IP networks.

Host memory is coupled to CPU via system bus . Host memory provides CPU access to data and program information that is stored in host memory at execution time. Typically host memory is composed of random access memory RAM circuits.

Host System includes adapter interface which couples host system to network adapter via bus connection and host interface . The structure of host interface depends on bus connection . For example if bus is a PCI bus then host interface includes logic and structure to support PCI bus based communication.

Adapter connects host system to network via network interface and network connection . The structure of network interface depends on the type of network for example Ethernet Fibre Channel and others.

Adapter includes a TCP IP accelerator module also referred to as TCP Offload Engine TOE that executes the TCP IP protocol stack in the hardware instead of a software stack at host system . Details of a TOE Module are provided in co pending patent application Ser. No. 10 620 040 filed on Jul. 15 2003 incorporated herein by reference in its entirety.

Adapter includes processor that has access to adapter memory . Processor controls overall adapter functionality by executing firmware instructions from memory .

Adapter also includes a direct memory access DMA engine which performs direct memory access functions in sending data to and receiving data from host system .

Adapter also includes iSCSI module which includes a dedicated processor or state machine to accomplish this purpose. Instead of the software layer in host system iSCSI module performs various iSCSI layer operations in adapter including processing digests performing data copy offload and large PDU transmission offload operations.

Before describing the details of buffer pools and operations the following defines certain terms that are used to explain the functionality of various embodiments described herein indicateWindowSize is a parameter used by TOE Driver and adapter specify a window size in bytes representing the amount of data which can be delivered by adapter to TOE Driver before adapter suspends data transfer to wait for an application to pass a named buffer to adapter or to acknowledge that data has been stored in anonymous buffer .

The value for indicateWindowSize may be set globally i.e. for every interaction between TOE Driver and adapter or on a per network connection basis. TOE Driver may import the indicateWindowSize value from a User Interface a driver parameter file flash read only memory NVRAM as a default value or from TOE Module . Generally TOE Driver passes the indicateWindowSize value to TOE Module during initialization of adapter . TOE Driver may also specify a unique value for indicateWindowSize for a connection when the connection is offloaded to TOE Module . The term indicatewindowSize is open means that data can be accepted from TOE module .

An indicatedBytes parameter value indicates the number of bytes that have been received by TOE Driver from adapter via TOE module at any given time. As shown in the indicatedBytes parameter is based on the value of counter that monitors the number of bytes received by TOE Driver from adapter and placed in host memory .

TOE Driver resets indicatedBytes value to zero when indicatedBytes equals indicateWindowSize and received data has been copied to a named buffer or accepted by application . When the indicatedBytes value i.e. counter is reset to zero and there are no named buffers pending TOE Driver issues an indicateAcknowledge command to TOE Module to open a new indicateWindow that allows TOE Module to resume sending data to TOE Driver . TOE Driver may optionally send an indicateAcknowledge command while data is being accepted to keep the indicate window open.

An indicatedBytesPending parameter is based on the value of counter . Counter is incremented by TOE Module when a segment is sent to TOE Driver . The value of Counter is incremented by the amount of data in the segment sent to TOE Driver . TOE Module suspends sending data to TOE Driver when counter value is equal to indicateWindowSize .

When TOE Module receives an indicateAcknowledge command from TOE Driver TOE Module decrements counter by a value specified in an AcknowledgedBytes field of the indicateAcknowledge command. When TOE Module receives a Named Buffer from TOE Driver TOE Module resets counter to the value 0.

Once TOE Module has sent a number of bytes equal to or similar to a value specified by the indicateWindowSize to TOE Driver TOE Module stops sending data received from the network. TOE Module holds pending data until TOE Driver posts a buffer for application for pending data or future received data or acknowledges that some or all of data has been received. At that time TOE Module resumes sending pending data or future data to TOE Driver .

TOE Driver receives network data sent by TOE Module in adapter . When TOE Driver receives a buffer from application TOE Driver passes the buffer to TOE Module . In one example the size of the buffer may be greater than the indicateWindowSize . In this example TOE Module DMAs data outside of indicateWindow to the buffer passed by TOE Driver . TOE Driver will first copy data in indicateWindow to the buffer. The buffers passed to TOE Module are returned when the buffer is filled or a timeout expires.

If the buffer received from application is smaller than the amount of data in indicateWindow then TOE Driver copies the amount of data based on the indicateWindow size and returns the buffer to application . TOE Driver then indicates to application that more data is available.

If TOE Driver does not receive a buffer from application and application signals that it has accepted the sent data TOE Driver then sends the next data based on the indicateWindow size to application .

As TOE Driver moves data based on the indicateWindow size it updates counter . TOE Driver may also inform TOE Module that data has moved by issuing an indicateAcknowledgement command to TOE Module .

In step S TOE Driver loads default operating parameters including a default value for indicateWindowSize .

In step S TOE Driver allocates host memory for anonymous buffer pool based on the default value for indicateWindowSize .

In step S initialization of adapter is complete and system is ready for network communication i.e. to receive and send network data.

In step S host system notifies Adapter via TOE Driver to process the connection i.e. the connection is offloaded .

In step S TOE Driver passes the indicatewindowsize to adapter in general and to TOE module in particular.

In step S TOE Driver also indicates to Adapter that no data has been received i.e. the indicatedBytes value is zero based on counter value .

In step S TOE Driver notifies host system network stack that the connection has been completed and in step S the process ends.

The process starts in step S when TOE Driver receives the IndicateData parameter from adapter for a connection.

In step S TOE Driver queues or assigns Anonymous Buffers for the connection. In one embodiment every connection has a context and data is queued for every connection.

In step S TOE Driver updates counter by an amount of data that it has received from adapter at any given time. It is assumed that adapter has previously received data from the network prior to passing it to TOE Driver in step S.

In step S TOE Driver determines if application has completed a given task at any given instance application has been notified of data availability or if a named buffer from buffer pool has been returned i.e. cleared . If yes then the process exits in step S. Otherwise in step S TOE Driver determines if a Named Buffer is available from Application for the connection. If a Named Buffer is available then in step S TOE Driver copies data from Anonymous Buffer to Named Buffer otherwise the process moves to step S described below.

In step S TOE Driver releases Anonymous Buffer and in step S the released Anonymous Buffer is returned to buffer pool that is available for TOE Module .

In step S TOE Driver determines if a Named Buffer for application is full. If yes then in step S the Named Buffer is returned to buffer pool . If Named Buffer is not full the process moves to step S as described below.

In step S TOE Driver checks if a Push Timer is running for the returned Named Buffer . If yes then in step S TOE Driver stops the Push Timer otherwise the process continues to step S.

In step S TOE Driver determines whether all the received data has been copied to a named Buffer . If TOE Driver determines that not all buffered data is copied to Named Buffer which means that there is data but there are no Named Buffers available the process moves to step S. If all the buffers are copied which means there are available buffers but there is no more data the process moves to step S described below.

In step S TOE Driver determines that Application has been notified of data availability or Named Buffer has been returned. If TOE Driver determines that Application has been notified the process exits in step S. If not then in step S TOE Driver notifies Application of data availability.

In step S if application provides a Return Code then in step S TOE Driver releases Anonymous Buffers otherwise the process continues in step S.

In step S if TOE Driver determines that Named Buffer is available then the process moves to step S otherwise the process exits in step S.

In step S if TOE Driver determines that there is more queued data then in step S TOE Driver checks if there is a Named Buffer available for the queued data. If there is no queued data in step S then the process moves to step S.

In step S if there is no Named Buffer available then the process loops back to step S. If a Named Buffer is available then the process continues to step S.

In step S TOE Driver determines if indicateWindow is full i.e. the amount of data that can be received has been received. This is inferred when indicatedBytes indicateWindowSize . If yes then in step S TOE Driver resets counter by setting indicatedBytes 0 otherwise the process exits in step S.

In step S TOE Driver determines if a Named Buffer has been posted or allocated for TOE Module if yes then in step S the process ends otherwise in step S TOE Driver issues an indicateAcknowledge parameter for TOE Module . The indicateAcknowledge parameter instructs TOE Module to open a new indicateWindow which enables TOE Module to resume sending data to TOE Driver .

In step S TOE Driver determines whether indicatedBytes indicateWindowSize . If yes then in step TOE Driver resets counter and the process ends in step S otherwise the process moves to step S.

In step S TOE Driver determines if a Named Buffer is partially full. If not then the process ends in step S otherwise TOE Driver determines if a Named Buffer is in Push Mode. If a Named Buffer is not in a Push Mode the process ends in step S.

The term Push Mode as used herein applies to Named Buffers. A Named Buffer is determined to be in a Push Mode when an Application sets a PUSH MODE flag in an application programming interface API that is used to pass the Named Buffer to the TOE Driver . When the Push Mode flag is set TOE Driver and adapter monitor received TCP segments that have been DMAed using DMA engine or copied to a Named buffer. If the TOE Driver or adapter detect that the TCP PUSH flag is set in a processed TCP Segment TOE Driver or adapter return the Named Buffer within a PUSH Timer timeout period regardless of how much data has been placed into the Named Buffer. If the Push Mode flag is not set then adapter and TOE Driver do not monitor the TCP Push flag in received TCP segments.

If the Named Buffer is in a Push Mode then in step S TOE Driver determines if a push bit is set in a copied TCP segment. If the bit is set then in step S the Named Buffer is returned. If the push bit is not set then in step S TOE Driver determines if the push timer is running. If the Push Timer is not running then the timer is started in step S and the process ends in step S. If the push timer is running then the process ends in step S.

If the push timer is running in step S then the timer is stopped in step S and the process ends in step S. If the push timer is not running in step S then the process ends in step S.

In step S TOE Driver determines if some Named Buffers have been submitted to TOE Module . If yes then the process continues to step S otherwise TOE Driver provides a Named Buffer for TOE Module starting from the head of a Named Buffer queue or pool .

In step S if TOE Driver determines that Named Buffer Size is not larger than indicateWindowSize then the process moves to step S otherwise TOE Driver in step S notifies TOE Module of Named Buffer s size and address where data can be placed.

In step S if TOE Driver determines if the push timer is running. If yes then in step S TOE Driver stops the push timer. Once the push timer expires or is stopped in step S Named Buffer is returned and the process ends in step S.

The foregoing adaptive aspects reduce latency because the indicateWindow parameter allows data to be buffered while application is determining whether to accept data or post a buffer. This reduces latency for data availability to a socket application. This results in better application performance. If the application is transaction based and operates primarily with small amounts of data the foregoing embodiments significantly increase performance by reducing latency that is incurred on every transaction.

In another embodiment the foregoing aspects also assist applications that operate primarily on large amounts of data by reducing latency and by providing simultaneous transfer of data by the TOE Driver via data copy and the TOE Device via DMA engine .

Although the present invention has been described with reference to specific embodiments these embodiments are illustrative only and not limiting. Many other applications and embodiments of the present invention will be apparent in light of this disclosure and the following claims.

