---

title: Open platform architecture for integrating multiple heterogeneous network functions
abstract: A platform for seamlessly hosts a plurality of disparate types of packet processing applications. One or more applications are loaded onto a service card on the platform. A programmable path structure is included that maps a logical path for processing of the packets through one or more of the plurality of service cards according to characteristics of the packets. Multiple path structures may be programmed into the platform to offer different service paths for different types of packets.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08000329&OS=08000329&RS=08000329
owner: Alcatel Lucent
number: 08000329
owner_city: Paris
owner_country: FR
publication_date: 20070629
---
The present patent application is related to the following U.S. Patent Applications filed concurrently herewith and commonly assigned herewith U.S. patent application Ser. No. 11 824 555 entitled NETWORK SYSTEM HAVING AN EXTENSIBLE CONTROL PLANE and and U.S. patent application Ser. No. 11 824 565 entitled NETWORK SYSTEM HAVING AN EXTENSIBLE FORWARDING PLANE . The contents of the aforementioned applications are fully incorporated herein by reference.

The present invention relates generally to networking and more specifically to integrating different networking applications on a single platform.

Edge devices provide packet connectivity entry points into a core network. They typically control and analyze the flow of traffic entering the core network provide security to the core network by preventing harmful traffic from entering it or provide enhancements to applications.

Examples of edge devices that monitor and analyze traffic include traffic monitoring systems traffic analysis systems flow replication systems and various other systems that monitor and control the type of traffic entering the core network.

Examples of edge devices that analyze the content of data entering the network to provide security to the core network include firewalls and detection prevention equipment.

Briefly a firewall refers to a device which limits access to a network by only allowing authorized flows users access to a private network.

Whereas detection prevention equipment refers to systems that identify and block malicious code from entering a network such as but not limited to computer viruses worms trojan horses spam malware spyware adware and other malicious and unwanted software. Intrusion detection equipment may also include systems that detect when an attack is being perpetrated on a core network such as a denial of service attack.

Examples of edge devices that provide enhancement of applications include applications that enhance the flow of packets content adaptation applications and acceleration application functions.

In many instances companies and organizations will purchase the best in class edge device solutions for use at the edge of a network. For example an organization may purchase Vendor A s virus detection product Vendor s B firewall Vendor s C flow replication product and Vendor s D router because each is the best in class or for some other reason.

As a result most devices found at the edge of a core network are a hodgepodge of dissimilar interconnected devices each performing a different task. The total cost for setting up and operating these disparate edge solutions is soaring out of control. Besides purchasing all these different solutions there are costs associated with keeping the equipment running and managing software on all of the disparate pieces of equipment. Moreover adding equipment to the edge of the network to handle growing network demands is often complicated and inflexible.

Furthermore with multiple types of equipment needed to examine packets for different purposes such as malware DDoS firewalls routing and so forth there may be multiple examinations of packets between the time a packet is received at the edge of a network and the time it is routed to a destination. Unfortunately each time a packet is examined and analyzed there is a delay incurred which is undesirable especially for packets that require quality of service such as packets containing real time data such as voice or video.

Presently there is no flexible way to service different types of packets or traffic flows. When a packet enters the edge it is routed through a fixed series of vendor s solutions. There is little choice on selecting which services are performed on each packet entering a network regardless of the type of packet. For example it is difficult for certain packet types having a higher priority level or trusted source to bypass certain packet analysis equipment to increase efficiency. It is also difficult to thread e.g. route packet flows through different combinations of vendor s devices and services.

Furthermore much of the functionality provided by different vendors equipment has fixed functionality limited in scope to particular application. Accordingly while it may be possible to reprogram upgrade the particular application for its intended use it is not presently possible to dynamically reprogram a device to change its intended purpose entirely. For example it is not presently possible to convert a device for running spyware into a device for performing transcoding.

Thus there is presently a desire to more efficiently service packets entering a network to reduce the quantity of examinations to a minimum desired level per packet type. There is also a desire to ensure Quality of Service is not sacrificed with the ability to route certain packets classified at the highest priority level through a more efficient examination process at the edge of a network. Further there is also a present desire to simplify and more flexibly integrate the various disparate types of functionalities performed at the edge of a network or elsewhere often provided by different vendors.

To address the above discussed deficiencies of the prior art the present invention provides a single network platform that seamlessly hosts a plurality of disparate types of packet processing applications where each application may be provided by different vendors. As used herein a platform may include a single physical device or may include multiple devices linked together at one or more sites but administered logically as a single network entity.

In one embodiment the platform includes a plurality of service cards forming a forwarding plane each service card configured to execute one or more particular packet processing applications applications associated with performing network security transcoding traffic analysis or other packet processing functionalities. The platform may also include one or more input output I O cards each card configured to route the packets from ingress to egress of the platform. A programmable service path structure is included that maps a logical path for processing of the packets through one or more of the plurality of service cards and one or more of the I O cards according to characteristics of the packets. Multiple path structures may be programmed into the network platform to offer different service paths for different types of packets.

In one embodiment decisions as to how a packet enters or exits the platform i.e. forwarding of a packet from the platform are segregated from decisions as to which applications are traversed e.g. executed for processing a packet.

In another embodiment a fabric is included on the platform having a plurality of input and output ports configured to physically route the packets from and to one or more plurality of service cards and one or more I O cards according to the programmable service path structure.

In another embodiment each service card may be reprogrammed dynamically during runtime such as upgrading an application or completely deleting an application and replacing it with a new application having a completely new purpose and functionality. For example it is possible to dynamically reconfigure a service card from executing an application associated with performing virus protection to executing an application associated with transcoding.

A feature and advantage of the innovative platform is the ability to incorporate traditional functionality of a router coupled with the ability to flexibly integrate multiple network packet service applications usually found in separate devices.

Additional exemplary implementations and features advantages are described in the Detailed Description in conjunction with the accompanying drawings below.

Reference herein to one embodiment an embodiment an implementation or one implementation or similar formulations herein means that a particular feature structure operation or characteristic described in connection with the embodiment is included in at least one embodiment of the present invention. Thus the appearances of such phrases or formulations herein are not necessarily all referring to the same embodiment. Furthermore various particular features structures operations or characteristics may be combined in any suitable manner in one or more embodiments.

In the following description for purposes of explanation specific numbers materials and configurations are set forth in order to provide a thorough understanding of the present invention. However it will be apparent to one skilled in the art that the present invention may be practiced without each specific example. In other instances well known features are omitted or simplified to clarify the description of the exemplary embodiments of the present invention and thereby to better explain the present invention.

Whereas second network is a computer or telecommunication network that may be connected to a service provider network and may have different administrative authorities. For instance in one embodiment second network is an access network which forms a portion of a communications network which connects users and other networks to first network and vice versa. In other embodiments second network may represent another core network or a customer network such as that of a private organization or government entity.

Interposed between first network and second network is a packet services platform platform for routing packets from access network to core network and vice versa.

In one embodiment platform resides at the edge of a network but can be located at points within a network other than the edge of a network. Platform is used to facilitate communications between networks and . For example in the illustration of platform provides connectivity access between first network and second network . Platform may also provide connectivity between other core networks or access points.

Platform hosts a plurality of disparate network functionalities in a single integrated platform. Each of the disparate network functionalities may be selected from different vendors. Examples of the different types of functionality that may be incorporated in platform include but are not necessarily limited to packet routing security services such as firewall s Denial of Services detection malware detection packet analysis such as traffic accounting and flow monitoring and other present or future packet service technologies.

Thus platform according to one aspect of the invention includes all the traditional functionality of a router coupled with the ability to flexibly integrate multiple network packet service applications usually found in separate devices.

The interface between first network and second network is provided by input output I O cards for receiving packets from second network and sending the packets to a destination via first network and vice versa.

Packets may be in the form of data or control packets. As used herein a packet refers to any formatted block of information carried by a network. In certain examples herein the term packet may refer to a single packet packet flows a collection of packets or some other delineation of one or more packets such as frames.

Platform generally includes a forwarding plane and a control plane . In general forwarding plane transports packets and performs packet processing services associated with the flow of packets. Control plane processes control information for managing and administering platform .

Incoming packets enter ports of I O cards and are sent to either forwarding plane or control plane of platform . That is incoming packets enter I O cards and are forwarded to one or more service cards control elements or feature servers via fabric . Incoming packets may also be forwarded directly to another I O card if no additional services are needed such as for egress. I O cards generally determine whether packets are sent to either forwarding plane or control plane when received by the cards. However in other implementations other elements may determine whether packets are sent to forwarding plane or control plane . For example a service card may perform the function of an I O card.

Service cards comprise a portion of a forwarding plane for platform for processing packets. Each service card includes at least one packet processing application for performing a packet processing service. Examples packet processing services include performing policy enforcement such as implementing firewall s and traffic conditioners performing intrusion detection and prevention such as Denial of Services detection malware detection performing packet analysis such as accounting metering and traffic monitoring performing Network Address Translation transcoding or other suitable packet services that may be deployed in a network. Other packet processing services may be performed as would be readily appreciated by those skilled in the art having the benefit of this disclosure.

In one implementation at least one service card is physically implemented as a slot card also commonly referred to as a blade or circuit pack that is processor based with the ability to execute code associated with one or more network applications.

It should be appreciated by those skilled in the art after having the benefit of this disclosure that a service card may take other forms. For example in one implementation a service card may be implemented in firmware such as using configurable Field Programmable Gate Arrays FPGAs and may be reprogrammable.

In still another implementation a service card may be hardware based such as implemented using Application Specific Integrated Circuits ASIC .

Although shown as residing on platform it is appreciated by those skilled in the art after having the benefit of this disclosure that one or more service cards may be remote from platform . For instance service cards may be multiple hops away from platform and not co located therein.

I O cards . . . N form a portion of the forwarding plane for platform . One or more I O cards are configured to route a packet from ingress to egress of platform . That is each I O card may process an incoming packet received from I O ports or fabric and may send it to an appropriate I O port for forwarding.

I O cards may also process an incoming packet previously processed by one or more service cards or other I O cards via fabric . I O cards process packets and may make routing decisions including such as determining a next hop or destination for packets based on forwarded rules loaded onto I O cards via fabric by control elements .

Alternatively in another embodiment one or more service cards may form part of the forwarding for platform . That is one or more service cards may process packets and make routing decisions including determining a next hop or destination for packets based on routing rules loaded onto service cards via fabric by control elements . Packets may be forwarded to a next hop destination via a fabric and a port of an I O card .

Although shown as residing on platform it is appreciated by those skilled in the art after having the benefit of this disclosure that one or more I O cards may be remote from platform . For instance I O cards may be multiple hops away from platform and not co located therein.

Control elements form a portion of control plane for platform . Control elements may transmit configuration information for configuring service cards and I O cards . Also feature server to be described in more detail may transmit configuration information to configure service cards . Additionally control elements may also configure feature servers to install new feature server applications. Control elements may interact with logic not shown for controlling fabric to effectively establish connections between service cards and the I O cards . Control elements may also provide information to service cards for routing packets within platform referred to as a programmable service path structure see to be described . The programmable service path structure may be conveyed to each service card via fabric connection .

Control elements may also communicate with fabric connection to establish connections between service cards and I O cards . Control elements maintain knowledge of links status between network elements not shown in network route changes and update information when changes are made in routing configurations. Control elements may also provide control for the overall general operation of platform .

Although shown as residing on platform it is appreciated by those skilled in the art after having the benefit of those disclosure that one or more control elements may be remote from platform . For instance control elements may be multiple hops away from platform and not co located therein. Accordingly when platform boots up powers on platform discovers control elements which become associated with platform . In such an implementation some logic or control unit provides initial direct contact between the data plane and control plane. Further details of how control elements may be bound to forwarding plane such as during boot up are described in commonly owned U.S. Patent Application Publication No. 20060092974 entitled Softrouter which is fully incorporated in its entirety herein by reference.

It should also be appreciated by those skilled in the art after having the benefit of this disclosure that illustrates only one embodiment for implementing control plane for platform . Although several control elements are shown in it is appreciated that control plane may only include a single control element. Additionally some portions of control plane may be implemented remotely as described above while some portions of control plane may reside on the same physical platform as forwarding plane . It should also be appreciated that forwarding plane and control plane are illustrated as being logically distinct from each other but may physically reside and or operate in an integrated fashion.

Fabric is illustrated as a single block and serves a communication hub for all elements comprising in platform . Fabric may be implemented as a cross bar switch interconnected switches other suitable cross point technology and a combination of such connectivity technology as would be appreciated by those skilled in the art having the benefit of this disclosure.

For instance in one implementation fabric may include an internally contained switched network such as a Gigabit Ethernet network using several Ethernet switches acting in concert.

Fabric also facilitates multiple parallel communication sessions of traffic as well as permits multiple entities such as control elements and service cards to communicate with each other in a simultaneous fashion. It is noted that while fabric is generally shown to reside within a single platform or chassis it is possible that one or more portions of fabric may be distributed across a network at different sites and linked together forming a single mass fabric.

As shall be explained the intra routing of packets i.e. the path structure within platform is programmable. That is the exact order of servicing packets by service cards is completely configurable. Thus platform facilitates the integration of functions provided by each service card into programmable combinations of one or more different services each such combination of services performed on incoming packets based on characteristics of the packets.

In the illustrated example a packet is received at an ingress port by I O card and forwarded to service card via fabric according to logical service path structure . The packet is processed by at least one application associated with a service card and forwarded to a next service card . Next the packet is serviced by at another application on service card and forwarded to I O card in accordance with logical service path structure . Finally the packet is forwarded to first network or second network via an egress port of I O card .

As shown in when transporting a packet from ingress to egress of a platform programmable service path structure is configured to select and link one or more applications and together. Programmable service path structure is also configured to bypass one or more applications such as application when a packet traverses service card .

Thus a service card may contain multiple applications and each of these particular applications may be selected or bypassed in accordance with programmable service path structure .

It is noted that while the above example only shows three network service applications it should be appreciated by those skilled in the art after having benefit of this disclosures that a service card may include more or less applications.

Thus based on the examples of and it should be apparent to those skilled in the art that the logical path i.e. a programmable service path structure that each packet flow takes when traversing through platform may be programmed into platform . Thus and show logical paths for processing a packet flow from ingress to egress platform .

In order to link the completion of an application performed in a service card to the start of another in the same card or on a different card a message system may be utilized to transport packets facilitating a packet flow through platform .

In one implementation the message system uses a service path flow ID a pointer to the next module I O card or port which is looked up by a service card indicating a next hop for a packet flow. A next hop ID is then encoded into a header of a packet flow indicating its next destination. Accordingly each sub path e.g. segment of a programmable service path structure provides the information necessary to link the next service card or a series of service cards for servicing a packet.

In another implementation an entire sequence of service cards and applications forming a programmable service path structure may be determined upon ingress of packets to platform . In such a scenario a flow ID may be embedded in the header s of a packet indicating which service flow path sub paths to take. In such an implementation I O cards may determine appropriate service cards which traffic should be directed when the packets are first received. Multiple sequential applications to perform a sequence of services and functions may be performed using service cards which may be daisy chained together through connections established via fabric .

In another implementation characteristics of the packets may be used to determine which sequence of service cards comprising a logical service path structure is chosen for routing a packet flow through platform .

For instance suppose packets of a characteristic type A have a classifier X encoded therein which determines which one of a plurality of programmable service path structures i.e. Service Path Service Path Service Path . . . or Service Path N a packet flow is to follow. Each programmable service path structure contains a sequence of applications which may include one or more service cards as well as applications per module. Suppose the programmable service path structure corresponding to classifier X is Service Path . Further suppose that the programmable service path structure for Service Path includes service application a firewall service application virus detection and then an I O card routing . This logical path could be programmed into I O cards and service cards such that any packet received with classifier X causes the I O cards and service cards to forward each packet according a programmable service path structure corresponding to Service Path .

Characteristics that may be utilized to determine how a packet is routed through platform include the source of the packets whether the source is trusted or not the type of packets i.e. data control video etc. the quality of service associated with the packets and so forth. Any characteristic associated within a packet such as a field within its header or data associated with a payload may be used to determine which service path is selected Service Path Service Path . . . or Service Path N .

Thus in a path routing implementation an entire sequence of applications embedded on one or more service cards and I O cards is selected upon entry to platform using a flow classifier.

In another implementation the programmable service path structure may be dynamically determined on the fly. That is a next hop within platform is determined anew after each I O card or service card using packet classifications. For example a service card may select one of two different service cards to distribute traffic if either such cards were included as part of a next hop.

In another embodiment a service card may also determine which programmable service path a packet flow is to follow based on characteristics of the packets.

A programmable service path structure may be linear such as shown in which a first service application is executed followed by a second subsequent service application followed by a next service application and so forth until all service applications are executed within a service path structure. Furthermore each one of the applications . . . through N forming the programmable service path structure is configurable and reconfigurable. Different applications can be added or removed from the service path simply by re programming re configuring one or more of the I O cards the service cards through the control plane.

A programmable service path structure may also be non linear such as shown in . AND and OR operators are primitives that may be used by programmers users to construct a logical service path structure and link different applications. In particular the AND operator replicates packet flows. For instance with use of an AND operator in packet flows would be duplicated for applications AND . In other words if a packet flow is to be replicated meaning creating two or more copies one copy of the packet flow will follow the upper path to application and one duplicate copy of the packet flow will follow the lower path to application .

Whereas the OR operator selects a particular one of at least two subpaths. In particular with use of an OR operator in packet flows would either be sent to application R application such as for load balancing.

Thus using the basic flow operators AND and OR it is also possible to logically link a next application with a prior application by inserting either operator between applications to provide a link.

It is noted that when there is only one branch the AND or OR operators may be used as links between applications in a linear fashion. Thus referring back to each application application . . . application N may be linked together using the AND or OR operators. Thus AND or OR operators may link multiple branches.

In one embodiment it is also possible to include external devices or functions within the service path structure that my not be integrated into platform . It is possible to define a service path structure that flows through one or more I O cards and service cards then flows out of platform to an external device which processes the packets. After the external device processes the packets they are sent back to platform and the packets continue to be processed by the service path structure until they exit platform . Thus a service path structure may include external elements which may be connected to I O ports of an I O card or service cards with external ports to handoff packets to an external device.

In one embodiment service card includes at least one processor and memory . Memory may include volatile memory e.g. RAM and or non volatile memory e.g. ROM . In some implementations volatile memory is used as part of the computing device s cache permitting application code and or data to be accessed quickly and executed by processor . Memory may also include non volatile memory in the form of flash memory content addressable memory and so forth. It is also possible for other memory mediums having various physical properties to be included as part of service card .

A service card can also contain other specialized other hardware assist devices not shown . For example it may include a special purpose processor not shown that can perform security functions such as encryption decryption or payload search engines in conjunction with a general purpose processor.

Operating system may reside as a component in the form of computer executable instructions and or logic within memory and may include a file system that when executed serves as a logical interface between code stored in memory. In one implementation operating system is the Linux Operating System permitting a completely open platform. Other operating systems may be incorporated into a module as would be appreciated by those skilled in the art having benefit of this disclosure.

Service card may also include one or more Input Output ports to transmit and or receive data. I O ports are typically connected in some fashion to controller processor and memory . I O ports are usually at least partially implemented in hardware for connecting computing device to a communication link and may include wired as well as wireless capabilities. Communication link may include any suitable connection means for handling the transportation of data to and from service card such as but not limited to cable fiber optics and wireless technology. Communication link may also include connectors to from a backplane or faceplate not shown of platform .

Stored within one or more portions of memory is a service engine . That is service engine includes one or more sets of computer executable code resident on a computer readable medium such as memory . Service engine performs functions associated with one or more service applications as mentioned above. Each one of the service applications may be programmed and reprogrammed to perform various packet services.

Service engine may also include application and configuration data such as flow look up tables used for purposes of choosing a next hop or next point to route packets.

In one implementation service engine may also include a communications module which is a set of code associated with the communicating between control elements. In one implementation communications module may include a standard protocol such as ForCES for communicating with control elements. Other communication protocols could be incorporated in module as would be appreciate by those skilled in the art after having the benefit of this disclosure.

Although described in terms of code the exemplary service engine may be implemented in hardware software or combinations of hardware and software. Additionally all components of service engine may be communicatively coupled to each other. As would be appreciated by those skilled in the art many of the components of service engine may be stored and identified as files under control of operating system .

In other embodiments service cards may be implemented as Field Programmable Gate Array FPGA ASIC network processors or any combination of the above.

Referring back to much functionality associated with platform is implemented in software which further facilitates reconfiguration and scalability. For example the quantity of service cards and I O cards per platform may vary. Additionally service cards or I O cards may be added or removed as necessary and fabric is reconfigurable to accommodate the necessary connections. As described above it is possible to configure and reconfigure service cards I O cards and fabric to establish the appropriate connections in a dynamic fashion. All such configurations can be loaded in their respective devices via control elements .

In terms of control a plurality of control elements can be implemented remotely for platform and or internally within platform . Forwarding plane may logically communicate with control elements as single virtualized unit as it may not be aware of each individual control element . This makes it possible to scale up and increase the capacity of control plane with more control elements as forwarding plane logically treats control elements as a single virtualized control plane.

Thus in addition to providing scalability for the forwarding plane platform provides scalability for the control plane . In particular the number of control elements may vary and additional control elements can be added without platform knowing there is any change as control elements as a cluster can be virtualized.

The available processing of control elements may cooperate with each other to share the processing burden of the control plane as necessary. As such the processing capability afforded by the control plane of platform may be scaled throughout the life of platform by adding control elements which increases control processing resources for the forwarding elements.

Based on the foregoing platform provides scalability in an independent fashion from the control plane and the forwarding plane including scalability for I O. Depending on the control plane and forwarding plane resources as well as the number of I O cards and associated ports fabric can be configured dynamically to accommodate additional service cards or I O cards .

As fabric is implemented using a switched network gigabit Ethernet it supports simultaneous communications without requiring the respective communicating entities to wait for network availability prior to communicating with each other. Thus the connections between modules are not fixed and are effectively under software control thereby avoiding physically static connections. Platform as implemented will include an appropriate backplane for facilitating the connection of each of the elements described above as would be readily appreciated by those skilled in the art having the benefit of this disclosure.

As control elements may be implemented in a virtual fashion it is possible to deploy new service functionalities executed by feature servers in a sandbox.

In one implementation feature server includes a sandbox which is a partitioned area of memory in which code created by an end user is installed. Sandbox is an area of memory in the control plane that is segregated from other areas of memory in which trusted application code or operating system code resides. Sandbox creates an environment in which there are strict limitations on what system resources the code created by a user can request or access. A security manager implemented in software guarantees that no run time environment is replaced by the code in sandbox which has access through a well defined Application Programming Interface API . Security manager also blocks any operations in which it is possible to perform a dangerous operation which could cause harm to the system. Security manager has the option to veto the operation by generating a security exception.

In another embodiment a sandbox can be defined for each application. That is there may be different sandboxes for each service application.

More specifically a feature server implemented with customer implemented application may directly access an existing control state of platform in a safe and efficient manner. The safety offered by a feature server is guaranteed through use of a restricted functional API and the use of logical or physical sandboxes .

In block a data packet is received by platform . For example a packet is received at ingress port of platform .

In a decisional block a determination is made whether the packet is a control or data packet. If in block the incoming packet is determined to be a control packet process proceeds to block . In block the packet is routed to one or more feature servers or control elements.

On the other hand if in block the incoming packet is determined to be a data packet process proceeds to block . In block a characteristic of the packet is determined based on header or payload information.

Additionally it is possible for platform to originate packets such as packets originating from control elements or feature server based on packets received in block . Accordingly in block A a packet may originate from control elements or feature servers.

In block a flow ID is inserted in the header of a packet relaying information indicating which service path or next hop i.e. sub path of a logical service path full path the packet is to follow. This logical path may be selected from one out of a plurality of different service paths which are configurable and reconfigurable. Each flow ID is configured to link a completion of processing of one specific segment of processing associated with one of the service cards service applications to a start of processing of another specific segment of another of the service cards such that each portion of processing of the packets can be performed in a specific order and by any of the plurality of service cards specified by the plurality of service paths. The packet is routed to service cards in accordance with the logical path selected and each service application is executed.

In block the packet is routed from a service card to an I O card which is configured to route the packet to a port for egress of the packet out of the platform. The flow ID or some other pointer or message may be used to link the service path with the data card for routing of the packet to the data card.

It is should be appreciate by those skilled in the art having the benefit of this disclosure that certain operational acts of method may be performed differently. For example it may not be necessary to insert flow ID into the packets to select a service path. Instead each service card may be configured to selected a next hop or service chain based on characteristics of the payload or header associated with a packet. Additionally one or more service cards may have dedicated tables for determining a next hop of a packet. Still further information inserted in field headers without adding additional bits that may be relied on to select a service path.

Additionally any exemplary functionality provided by a service card logical path or functional block may be described in the general context of computer executable code being executed by a processor of a computer. Generally computer executable code include modules routines programs objects components data structures logic and other executable code that perform particular tasks or implement particular abstract data types when executed by a computing device. Computer executable code may be located in a computer readable medium such as but not limited to local remote and or distributed computer storage media including memory storage devices.

Custom routing standard shortest path routing as commonly used in IP routing may not be suitable for certain applications. For example VoIP should be routed along a least delay path rather than a shortest path. In general a carrier or its customers may have its special routing requirements that do not mesh well with traditional protocols. Force fitting of such routing requirements on a shortest path routing framework can be unwieldy. The ability to host custom routing protocol can solve this problem. With this a customer can deploy its own version delay based routing and even inter domain QoS routing with its peers.

Custom protocol processing The emergence of IPTV has brought renewed attention to IP multicast. A key challenge to IPTV is the ability to perform fast channel change. This is typically implemented as multicast group join and leave which in turns relates to IGMP processing. Specialized IGMP processing can provide a customer unique differentiation to its IPTV network.

Custom network measurement Basic network measurements provide statistics only at the transport level e.g. queue length link utilization etc. A carrier can indirectly infer the performance of an application using these measures. A way to understand application performance is to directly measure it at the application level. For example with an extended control plane it is relatively easy to inject VoIP signaling or bearer traffic to directly measure SIP signaling and VoIP quality.

Custom data management A router collects a lot of internal statistics. The existing way of getting at this statistics is clumsy and inefficient. For example SNMP is very inefficient if you try to obtain the data at a different granularity. Through feature servers data can be preprocessed e.g. aggregated within platform and exported in a customize format.

It is to be understood that the present invention is not limited to the embodiments described above but encompasses any and all embodiments within the scope of the subjoined Claims including their equivalents.

