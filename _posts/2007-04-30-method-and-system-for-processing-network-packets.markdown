---

title: Method and system for processing network packets
abstract: Method and system for transferring information from a host system is provided. The method includes sending a SCSI read command and a scatter/gather (“S/G”) list from an application executed by a processor for the host system to a iSCSI software layer executed by the processor for the host system; generating an iSCSI protocol data unit (“PDU”) header for a iSCSI PDU for the SCSI read command; sending the iSCSI PDU to a data mover layer executed by the processor for the host system; and sending the iSCSI PDU to an iSCSI offload module in a network adapter operationally coupled to the host system; wherein the iSCSI offload module appends a PDU header digest to the iSCSI PDU header; and transmits the PDU to a PDU destination.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08387073&OS=08387073&RS=08387073
owner: QLOGIC, Corporation
number: 08387073
owner_city: Aliso Viejo
owner_country: US
publication_date: 20070430
---
This application claims priority to U.S. provisional patent application Ser. No. 60 896 784 filed on Mar. 23 2007 the disclosure of which is incorporated herein by reference in its entirety.

The present invention relates to network systems and more particularly to offloading host system tasks for managing network related operations.

Computer networks are commonly used today in various applications. Computer networks typically use a layered protocol structure to manage network traffic. One common model that is typically used is the ISO model that includes a physical layer a data link layer that includes a MAC layer a network layer and others. Upper level protocol layers ULPs for example iSCSi and RDMA interface with a network layer to send and receive data from the network.

As iSCSI an upper layer protocol becomes popular various software solutions to execute the iSCSI layer in software are emerging. Host system software typically executes the iSCSI layer in software. However this process is slow and can consume host processor time and resources especially for generating digests and checking cyclic redundancy code CRC .

Operating systems for example Microsoft Chimney support offloading of TCP IP protocol stack but do not address digest and data copy problems. Typical iSCSI host bus adapters HBAs that offload iSCSI layer functionality from a host system to the HBA do not interface very well with host system software based iSCSI solutions. Therefore there is a need for an efficient method and system for offloading iSCSI functionality in general and more specifically offloading digest processing data copy operations and large PDU transmission.

In one embodiment a method for transferring information from a host system is provided. The method includes sending a SCSI read command and a scatter gather S G list from an application executed by a processor for the host system to a iSCSI software layer executed by the processor for the host system generating an iSCSI protocol data unit PDU header for a iSCSI PDU for the SCSI read command sending the iSCSI PDU to a data mover layer executed by the processor for the host system and sending the iSCSI PDU to an iSCSI offload module in a network adapter operationally coupled to the host system wherein the iSCSI offload module appends a PDU header digest to the iSCSI PDU header and transmits the PDU to a PDU destination.

In another embodiment a method for a network adapter operationally coupled to a host system and a network is provided. The method includes receiving network data from a networked device forwarding the network data to an iSCSI offload module for the network adapter validating a digest for the network data wherein the iSCSI offload module validates the digest sending the network data and a PDU header to a iSCSI layer executed by a processor for the host system and sending network data to a storage layer wherein the iSCSI layer sends the network data to the storage layer executed by the processor for the host system.

In yet another embodiment a method for a network adapter operationally coupled to a host system and a network is provided. The method includes receiving a marker protocol data unit aligned MPA frame at a remote direct memory access RDMA offload module of the network adapter verifying cyclic redundancy code CRC for the MPA frame wherein the RDMA offload module verifies the CRC copying data to a scatter gather S G list sending data and status to a iSCSI layer via an application programming interface and a data mover layer and forwarding the data to an application layer executed by a processor for the host system.

In another embodiment a system for processing network data is provided. The system includes a processor for a host system executing an application layer for sending a SCSI read command and executing an iSCSI layer for generating an iSCSI protocol data unit PDU header for the SCSI read command and a network adapter with an iSCSI offloading module that receives the iSCSI PDU and appends a PDU header digest before transmitting the iSCSI PDU to a PDU destination.

This brief summary has been provided so that the nature of the invention may be understood quickly. A more complete understanding of the invention can be obtained by reference to the following detailed description of the various embodiments thereof concerning the attached drawings.

To facilitate an understanding of the various embodiments a top level description of common network protocols standards and the general architecture operation of a host system will be described. The specific architecture and operation of the various embodiments will then be described with reference to the general architecture.

Computing systems and devices use various protocols standards for network communication. shows an example of various protocol layers that are used in networking systems. Data link layer which includes the MAC layer interfaces with an IP Internet Protocol layer . TCP Transmission Control Protocol layer typically sits on top of the IP layer. Upper Layer Protocols ULPs may include plural layers for example the iSCSI layer the RDMA layer and others. The following provides a brief introduction to some of the standards protocols 

Transmission Control Protocol Internet Protocol TCP IP TCP is a standard network protocol incorporated herein by reference in its entirety that provides connection oriented reliable byte stream service. This means that two nodes establish a logical connection before sending data and TCP maintains state information regarding the data transfer. Reliable means that data is delivered in the same order that it was sent. A byte stream service means that TCP views data to be sent as a continuous data stream that is sent in any way it sees fit and delivers it to the remote node as a byte stream.

The IP standard protocol incorporated herein by reference in its entirety provides a datagram service whose function is to enable routing of data through various network subnets. Each of these subnets could be a different physical link such as Ethernet ATM or others. IP is also responsible for fragmentation of the transmit data to match a local link s maximum transmission unit MTU . IP can fragment data at the source node or at any intervening router between the source and destination node.

A complete description of the TCP IP protocol suite is provided in TCP IP Illustrated Vol. 1 by W. Richard Stevens and Volume 2 by Gary R. Wright and W. Richard Stevens published by Addison Wesley Professional Computing Series that is incorporated herein by reference in its entirety.

iSCSI Protocol Internet SCSI iSCSI as defined by the Internet Engineering Task Force IETF maps the standard SCSI protocol on top of the TCP IP protocol. iSCSI incorporated herein by reference in its entirety is based on the Small Computer Systems Interface SCSI standard which enables host computer systems to perform block data input output I O operations with a variety of peripheral devices including disk and tape devices optical storage devices as well as printers and scanners. The iSCSI and TCP IP protocol suite consist of 4 protocol layers the application layer of which iSCSI is one application the transport layer TCP the network layer IP and the link layer i.e. Ethernet .

A traditional SCSI connection between a host system and peripheral device is through parallel cabling and is limited by distance and device support constraints. For storage applications iSCSI was developed to take advantage of network architectures based on Ethernet standards. iSCSI leverages the SCSI protocol over established networked infrastructures and defines the means for enabling block storage applications over TCP.

The iSCSI architecture is based on a client server model. Typically the client is a host system such as a file server that issues a read or write command. The server may be a disk array that responds to the client request. Typically the client is an initiator that initiates a read or write command and a disk array is a target that accepts a read or write command and performs the requested operation.

In a typical iSCSI exchange an initiator sends a read or write command to a target. For a read operation the target sends the requested data to the initiator. For a write command the target sends a Ready to Transfer Protocol Data Unit PDU informing the initiator that the target is ready to accept the write data. The initiator then sends the write data to the target.

Once the data is transferred the exchange enters the response phase. The target then sends a response PDU to the initiator with the status of the operation. Once the initiator receives this response the exchange is complete. The use of TCP guarantees the delivery of the PDUs.

Typically logical units in the target process commands. Commands are sent by the host system in Command Descriptor Blocks CDR . A CDB is sent to a specific logical unit for example the CDB may include a command to read a specific number of data blocks. The target s logical unit transfers the requested data block to the initiator terminating with a status message indicating completion of the request. iSCSI encapsulates CDB transactions between initiators and targets over TCP IP networks.

RDMA Remote Direct Memory Access RDMA is a standard upper layer protocol incorporated herein by reference in its entirety that assists one computer to directly place information in another computer s memory with minimal demands on memory bus bandwidth and CPU processing overhead. RDMA over TCP IP defines the interoperable protocols to support RDMA operations over standard TCP IP networks. A network interface card or adapter that can offload TCP IP protocol processing and support RDMA over TCP IP may be referred to as an RNIC.

Embedded in a stream of iSCSI or RDMA data there are three fields which may need to be located for processing by a receiving network node. These fields are referred to as Markers DIFs and Digests. Each of these fields may or may not be present in a data stream regardless of the presence of the other fields. The location of each field in a data stream is unrelated but can have an affect on locating other fields.

Markers are inserted into a data stream periodically at a predetermined interval starting at a given TCP sequence number. Markers are a fixed length and indicate the offset to the start of the next protocol data unit PDU . iSCSI markers are 8 bytes long while RDMA markers are 4 bytes long. Insertion of iSCSI markers into the data stream is performed logically after insertion of digests and or DIFs. Thus iSCSI markers are not included in the Cyclic Redundancy Check CRC calculation for either of those fields.

RDMA markers are inserted into a data stream logically after the insertion of DIFs but prior to insertion of Digests. Thus RDMA markers are not included in the calculation of the DIF CRC but are included in the Digest CRC calculation.

DIFs are 8 byte fields appended to each block of data stored on a mass storage device. A DIF contains a Reference Tag Application Tag and a CRC value. As a direct memory access DMA occurs the CRC is determined for each DIF on each data block during a transfer. Depending on the application in a system an incoming data stream may need to insert DIFs periodically into the data stream validate and remove them from the data stream or validate them and keep them in the data stream.

DIFs are included in the Digest calculation for both iSCSI and RDMA. Markers are not included in the iSCSI Digest calculation but are included in the RDMA Digest calculation.

iSCSI Data Digests are 4 byte fields appended to the end of an iSCSI PDU which are a CRC calculation over the data portion of the PDU. iSCSI Header Digests are 4 byte fields appended to the end of a 48 byte iSCSI PDH Header which are a CRC calculation over the header portion of the PDU.

Host memory is coupled to CPU via a system bus or a local memory bus not shown . Host memory is used to provide CPU access to data and program information that is stored in host memory at execution time. Typically host memory is composed of random access memory RAM circuits. A computing system with the CPU and main memory is often referred to as a host system.

System includes an adapter which can be used for both initiator and target applications i.e. can be used on a host bus adapter or with a redundant array of inexpensive disks RAID controller . Adapter may be on a PCI development board with a Field Programmable gate Array FPGA . The chip may also be integrated into an Application Specific Integrated Circuit ASIC with an embedded serialize de serializer SERDES not shown and internal programmable random access memory RAM .

Adapter includes plural modules including a network interface module a RDMA offload module and an iSCSI offload module . Network interface module operates as a network adapter to connect host system to another networked device for example storage system via a network connection and network . Network Interface module includes a TCP IP accelerator module or chip or system or engine TOE A that executes the TCP IP protocol stack in hardware instead of software at host . TOE A includes an embedded Ethernet MAC to connect a PCI based host to a LAN not shown . Details of a TOE device are provided in U.S. Pat. No. 7 403 542 assigned to QLogic Coporation incorporated herein by reference in its entirety.

RDMA offload module executes the RDMA protocol functionality and is coupled to network via link . iSCSI offload module coupled to network via link executes the specific functions of the iSCSI layer in adapter and specifically performs digest processing data copy offload and large PDU transmission offload instead of the software layer in host system .

Adapter includes iSCSI hardware for processing digests performing data copy offload and large PDU transmission offload operations. Hardware may include a dedicated processor or state machine to accomplish this purpose.

Adapter may include processor that has access to adapter memory . Processor controls overall adapter functionality by executing firmware instructions from memory .

DMA engine is used to perform direct memory access functions in sending data to and receiving data from the host.

An industry standard organization RDMA consortium developed data mover layer that allows an iSCSI layer to utilize the RDMA transport commonly known as iSER to send iSCSI commands. In one embodiment iSCSI offload module interfaces with data mover layer via an iSCSI application programming interface API . A standard data mover layer does not typically interface with an iSCSI API .

iSCSI offload module or engine performs various functions to offload execution of iSCSI layer in host software. For example iSCSI offload module performs Digest calculations and also assists in sending large data packets. For example if there is a request to send 4 megabytes of data and adapter has negotiated a PDU size of 8K then 512 PDUs are needed to send 4 MB of data. The host system sends a header for the first PDU and iSCSI offload module replicates the headers for the other 511 PDUs. This will save CPU processing time.

iSCSI offload module also assists in processing Immediate Data as defined by the iSCSI standard and with solicited and unsolicited data. Some SCSI commands require additional parameter data to accompany the SCSI command. Immediate Data may be placed beyond the boundary of the iSCSI header in a data segment. Alternatively user data e.g. from a WRITE operation can be placed in the data segment both cases are referred to as Immediate Data .

Outgoing SCSI data initiator to target user data or command parameters is sent as either solicited data or unsolicited data. Solicited data are sent in response to a response to target R2T PDUs. Unsolicited data can be sent as part of an iSCSI command PDU Immediate Data or in separate iSCSI data PDUs.

Immediate data are assumed to originate at an offset 0 in an initiator SCSI write buffer outgoing data buffer not shown . All other Data PDUs have a buffer offset set explicitly in the PDU header.

Sockets API interfaces with TOE A and a TCP IP stack . Sockets API assists in establishing a network connection.

It is noteworthy that for clarity sake various components for example TOE A RDMA offload module and iSCSI module have been shown as separate components. These modules can be all integrated into a single module to implement the functionality of the various embodiments disclosed herein.

In step S iSCSI layer builds an iSCSI PDU header for the read command. The PDU is then sent to data mover layer which can process the PDU in three different paths steps S to S via sockets API steps S to S via iSER RDMA API and steps S to S via iSCSI API that are described below.

In step S the PDU header is sent to sockets API which appends the header digest in step S. In step S the read data S G list is saved. In step S the PDU is copied in a socket buffer located in a memory managed by a sockets layer before being sent to adapter . Thereafter the PDU is sent in step S via adapter .

In step S iSCSI layer sends the PDU header and S G list to data mover layer . In step S this information is passed to iSER RDMA layer .

In step S RDMA offload module appends MPA Marker PDU Aligned frame for TCP CRC. In step S tagged information is stored and the PDU header is transmitted in step S.

In step S iSCSI offload module appends PDU header digests and in step S saves the S G list. The PDU is transmitted in step S by iSCSI Module .

In step S a network packet for the socket segment is received. TOE A validates the digest in step S and data in the payload is copied in step S. In step S data and SCSI status PDU headers are passed to iSCSI layer . In step S the header is parsed and data and status is passed on to application layer for example a SCSI layer .

In step S MPA frames are received by RDMA offload module and the CRC is verified by RDMA offload module . In step S tagged data are copied to a S G list by RDMA offload module . Tagged data is data received in an RDMA PDU which has a direct data placement DDP tagged flag set. The DDP header includes a steering tag which identifies a memory buffer where data is to be placed directly for a particular buffer i.e. a named buffer . Untagged data typically do not have any particular data buffer and are saved in an unnamed buffer i.e. a memory buffer from among a plurality of buffers.

In step S data and status with PDU headers are passed to iSCSI layer via iSER RDMA API and Data mover layer . Thereafter in step S the header is parsed and data is sent to application .

In step S iSCSI offload module receives data and status. iSCSI module validates the digest in step S. In step S data is copied to S G list. In step S data and the SCSI PDU is passed to iSCSI layer via iSCSI API . Thereafter in step S iSCSI layer parses the PDU header and data and status is sent to storage layer .

Although the present invention has been described with reference to specific embodiments these embodiments are illustrative only and not limiting. Many other applications and embodiments of the present invention will be apparent in light of this disclosure and the following claims.

