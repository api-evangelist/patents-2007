---

title: Enforcing security groups in network of data processors
abstract: A technique for securing message traffic in a data network using various methods for distributing security policies and keys, where policy definition is determined in a Management and Policy (MAP) functional layer that is responsible for policy distribution; a separate Key Authority Point (KAP) that is responsible for key generation, key distribution, and policy distribution; and a separate Policy Enforcement Point (PEP) which is responsible for enforcing the policies and applying the keys.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08082574&OS=08082574&RS=08082574
owner: Certes Networks, Inc.
number: 08082574
owner_city: Pittsburgh
owner_country: US
publication_date: 20070723
---
This application claims the benefit of U.S. Provisional Application No. 60 837 410 filed on Aug. 11 2006 and is related to co pending U.S. patent application Ser. No. 11 649 336 filed on Jan. 3 2007 entitled Securing Network Traffic Using Distributed Key Generation and Dissemination Over Secure Tunnels. The entire teachings of the above referenced applications are incorporated herein by reference.

The present invention relates to securing message traffic in a data network and more particularly to a service layer approach to implementing group security functions.

 Securing implies both encryption of data in transit as well as authenticating that the data has not been manipulated in transit.

A security policy or policy defines data or traffic to be secured by a source IP address a destination IP address a port number and or a protocol. They also define the type of security to be performed.

A key for a secure tunnel is the secret information used to encrypt and decrypt or to authenticate and to verify data in one direction of traffic in the secure tunnel.

A Management and Policy Server MAP is a device that is used to define high level security policies which it then distributes to one or more Key Authority Points KAPs .

A Key Authority Point KAP is a device that generates detailed policies from high level policies which it then distributes to one or more Policy Enforcement Points PEPs .

Data traffic in most computer networks is normally sent unsecured without encryption or strong authentication of the sender and receiver. This allows the traffic to be intercepted inspected modified or redirected. Either the sender or receiver can falsify their identity. In order to allow private traffic to be sent in a secure manner a number of security schemes have been proposed and are in use. Some are application dependent as with a specific program performing password authentication while others such as TLS are designed to provide comprehensive security to whole classes of traffic such as HTTP Hyper Text Transfer Protocol and FTP File Transfer Protocol .

IPsec is a protocol that was developed to address a broader security need. As the majority of network traffic today is over Internet Protocol IP IPsec was designed to provide encryption and authentication services to this traffic regardless of the application or transport protocol. This is done in IPsec transport or tunnel modes. In either mode the process involves encrypting a data packet if encryption is required performing a secure hash authentication on the packet and wrapping the resulting packet in a new IP packet indicating it has been secured using IPsec.

Encryption keys secrets and other required configuration information must be exchanged by the parties involved in order for IPsec to work. This is accomplished using Internet Key Exchange IKE which is done in two phases.

In a first phase IKE Phase 1 a connection between two parties is started in the clear. Using public key cryptographic mechanisms where two parties may agree on a secret key by exchanging public data without a third party being able to determine the key each party may determine a secret for use in the negotiation. Public key cryptography requires that each party either share secret information pre shared key or exchange public keys for which they retain a private matching key. This is normally done with certificates e.g. Public Key Infrastructure PKI . Either of these methods authenticates the identity of the peer to some degree.

Once a secret has been agreed upon in IKE Phase 1 a second phase IKE Phase 2 may begin and the specific secret and cryptographic parameters of a specific tunnel are developed. All traffic in IKE Phase 2 negotiations is encrypted by the secret from IKE Phase 1. When these negotiations are complete a set of secrets and parameters for security have been agreed upon by the two parties and IPsec secured traffic may commence.

Security Gateways SGWs may be implemented at routers and other internetworking devices to implement IPsec in a tunnel mode alleviating some of the responsibility for security from end nodes. When a packet is detected at a SGW with a source destination pair that requires IPsec protection the secret and other security association SA information are determined based on the Security Policy Database SPD and IPsec encryption and authentication is performed. The packet is then directed to a SGW that can perform decryption. At the receiving SGW the IPsec packet is detected and its security parameters are determined by a Security Packet Index SPI in the outer header. This is associated with the SA and the secrets are found for decryption and authentication. If the resulting packet matches the policy it is forwarded to the original recipient.

Although IPsec tunnel mode has been used effectively in securing direct data links and small collections of gateways in networks a number of practical limitations have acted as a barrier to more complete acceptance of IPsec as a primary security solution throughout the industry.

Configuration of Policies Using the above approach each SGW must be configured with each pair of source and destination IP addresses or subnets that must be secured or allowed in the clear or dropped . For example 11 SGW units fully meshed each protecting 10 subnets would require 1000 policies in the SPD. This is a challenge in terms of the user setting up the policies the time required to load the policies the memory and speed difficulties in implementing the policies and the increase in network time spent performing negotiations and rekey. The time required for initial IKE negotiations in this example may exceed ten minutes.

In addition even smaller networks would require the user to have a complete knowledge of all protected subnets and their security requirements and any additions or modifications would need to be implemented at each gateway.

Installation of an IPsec IKE Stack on Individual PCs With the variety of available operating systems Windows XP XP Service Pack 1 and 2 Linux and all of its kernel releases etc. and hardware platforms a software implementation of the IPsec stack which is dependent on both of these must be designed compiled tested and supported for each implementation. Hardware solutions such as IPsec on a NIC provide some separation from these issues but preclude automated remote installation of the IPsec stack.

In addition the computer with the installation must be configured with the user certificate and the policy configuration. Ideally the user would be identified in some way other than a machine based certificate but unfortunately all existing implementations require the computer to be configured directly normally by a network security manager. IKE also offers methods for remote access using certificate based authentication combined with RADIUS and XAUTH for the user ID as well as mode configuration to supply the user with a local network identification.

The present invention is an approach that separates network security functions in into three functional layers. In general the three layers are respectively responsible for 1 management of security groups and encryption policies 2 key and policy distribution to security group members and 3 policy enforcement. In one embodiment the layers include 

 1 Management And Policy Server MAP responsible for coordinating the definition and coordination of encryption policies and communication entitlements across an enterprise e.g. which data processors are assigned to which groups which users are allowed to access which applications etc. 

 2 Key Authority Point KAP responsible for generation of keys and secure distribution of keys and policies in the enterprise such as through Policy Enforcement Points PEPs .

 3 Policy Enforcement Points PEPs responsible for enforcement of security in the network. The PEPs may be distributed somewhere along the data path including at network end points embedded in personal computers PDAs storage servers VPN clients internetworking devices routers gateways and the like that perform traffic inspection or other network enabled devices and or locations. The PEPs perform packet encryption and decryption as well as IPsec header generation on outgoing and incoming packets according to security policies.

By dividing policy management key generation and exchange and policy enforcement into these three separate layers one may solve some of the limitations of existing IPsec IKE and other network security approaches.

The architecture permits enforcement of data protection across enterprise environments as a security overlay that operates independently of the network. It provides a number of advantages over standard IKE IPsec security including but not limited to 

Simplified Configuration of Policies The definition of policies local and remote combined with policy linkage provides simplified secure network definition. This is enhanced by the ability to load individual policies to the PEP s .

Multicast Broadcast Traffic Separating Key Distribution from Policy Enforcement allows for support of these traffic types independent of network protocols.

Firewalls Intrusion Detection Systems IDS These may be surrounded with a decrypt encrypt barrier to provide a clear packet to a firewall or IDS. This is supported with a configuration that performs key distribution from a central authority to multiple PEPs.

Resiliency The invention improves secure network resiliency by providing multiple identically keyed paths and by providing low state controllers for easy failover. Approaches with complex states in units other than the PEP s will offer greater resiliency challenges.

Installation of an IPsec IKE Stack on Individual PCs By separating Policy Definition and Key Generation and Distribution from the PEP the requirements of each PC installation are greatly reduced.

In one method for securing message traffic in a data network using a security protocol a security policy definition to be applied to traffic in the network is determined at a Management and Policy Server MAP within a network. The policy definition includes at least a definition of traffic to be secured and parameters to be applied to the secured traffic. At least one security policy definition from the MAP is received at a Key Authority Point KAP within the network. The KAP generates one or more keys to be used in securing the traffic according to the policy definition and distributes the security policy definition and the keys to two or more peer Policy Enforcement Points PEPs . The security policy definition and the keys from the KAP are received at a PEP within the network. The PEP receives a network traffic packet determines if the network traffic packet falls within the definition of traffic to be secured and applies security processing to the network traffic packet according to the keys and the parameters of the security policy definition.

The MAP may authenticate each KAP and PEP and provide a visualization of security groups. The security policy definition may include a definition of groups communities of interest and may include a definition of membership and permissions of groups.

The KAP may use IPsec to distribute the security policy definition and the keys to two or more peer PEPs and may communicate with the peer PEPs via an Application Programming Interface API . The KAP may also monitor the operation of the peer PEPs. It should be noted that in one system the MAP and KAP may be centralized on a single physical machine.

The PEP may be embedded in a network connected device or may be implemented as a process running on a network appliance. Additionally the PEP may encrypt outbound packets may decrypt inbound packets and may store and process security packet index SPI data associated with the packets.

The MAP is a data processing device typically a PC or workstation through which an administrative user may input and configure security policies. The MAP may be thought of as a network management layer device that acts as a secure server storing and providing access to security policies by other elements of the system. The MAP thus provides a single unified interface for definition and enforcement of policies in a network of data processors such as may be spread across an enterprise. In addition to the functions listed in a high level visualization of these and other functions provided by the MAP is illustrated in .

The functions provided by the MAP include authentication of other functional layers i.e. authentication of each Key Authority Point and Policy Enforcement Point through existing authentication services such as an Authentication Authorization and Accounting AAA protocol per RFC 2903 e.g. Diameter RADIUS TACAS etc. pushing and enforcing policies out to the Key Authority Points and providing support for definition of groups or communities of interest of various elements of the enterprise.

As is key to the present invention the MAP provides for aggregation and unification of security group definitions across an enterprise. The security groups define permitted or prohibited user to user communications network to network communication user to application level communication user to data and so forth.

The MAP thus has an interface to allow for the definition of security group policies that describe how and when members of groups may communicate. These may include management of privileges in defining user roles and group roles memberships and permissions of particular groups i.e. as defined to specific machines applications or users assignments of privileged users and applications or data centers which in turn may be rule and policy based.

Security group identity and creation that is determining who belongs to which security groups may be provided in a number of ways. This can be created from user data filled into templates or imported from business applications i.e. from human resources or information technology operations in an enterprise. The data may be provided by such other applications as CRM ARP SEM software or LDAP Microsoft Active Directory applications.

Additionally the MAP provides coordination of provided security group functions such as network traffic data protection network validation change control and the like.

The MAP may also be used to configure the KAP and PEP appliances e.g. one function is to configure IPsec tunnel policies to be used for communication between the KAPs and the PEPs . 

The MAP user interface may also provide visualization of security groups i.e. a visualization of what is protected. Security infrastructure information may also be provided to administrative users to show a snapshot of the present status of the MAP KAPs and PEPs in particular.

The Key Authority Points KAPs provide for generation and distribution of keys and security policies to the Policy Enforcement Points PEPs . The KAPs serve as the authorities for providing encryption keys to the PEPs and may be thought of as a distribution layer. The KAPs may use certain standard types of security policies such as Security Association SA and keys that may be distributed by IPsec to the PEPs .

KAPs may also monitor the operation of PEPs . Such monitoring may occur through tunnel transport as a secure communication mechanism with the PEPs . The KAPs may support tunnel transport and network modes and may support multi vendor PEPs.

The KAPs are typically located in a different physical machine than the PEPs i.e. PEPs as will be described may be distributed throughout a network and even to end nodes themselves. Thus some mechanism is necessary to provide for the secure transport of keys and other information between the KAPs and PEPs . The preferred communication may be through an open Application Programming Interface API .

The KAP and MAP may be centralized on a single physical machine or may be implemented in a distributed fashion. However in a typical enterprise having a network that spans more than one physical location as shown in the MAP is based in a central location such as a headquarters location and the KAPs are typically distributed at individual locations. In the illustrated example there are five KAPs and each responsible for providing the KAP functionality at a given physical network site. It should be understood that a given KAP may actually be responsible for providing KAP functions to more than one physical local area network and or location and that is merely intended for illustration. Thus the physical local area networks and are each within the authority of KAP . Multiple KAPs may also allow for distributed redundant deployment of the KAP distribution functional layer.

PEPs may be hardware or software based and are typically embedded in network connected devices end nodes such as PCs or within internetworking devices such as routers . illustrates where PEPs may reside in a network including at end nodes that may be typical client computers such as personal computers PCs workstations Personal Digital Assistants PDAs digital mobile telephones wireless network enabled devices and the like. The nodes may also be file servers video set top boxes data processing machines or other networkable devices from which messages originate and to which message are sent. The policies and keys of the PEPs are enforced by a KAP and each PEP authenticates its corresponding KAP . PEPs may support tunnel transport and network modes and may provide multi vendor support though the API .

The message traffic in the network layer typically takes the form of data packets in the well known Internet Protocol IP packet format. As is well known in the art an IP packet may typically be encapsulated by other networking protocols such as Transmission Control Protocol TCP User Datagram Protocol UDP or other lower level and higher level networking protocols. It should be understood that other functions and devices may be present in the network and the above configuration is only one example. Since the PEPs are located on the data path they may also be instantiated as a process running on a hardened network appliance such as a Secure Gateway SGW .

Referring to the PEPs are responsible for a number of tasks principally for encryption of outbound packets and decryption of inbound packets received on the fast path interface. The PEPs may thus identify packets that need to be secured according to policies as configured by the KAPs . The PEPs may also simply pass through or drop such packets according to such policies.

The PEPs are configured to perform IPsec tasks such as handling Security Association SA information to store and process necessary policies such as Security Packet Index SPI data associated with the IPsec packets and the like as instructed by the KAPs . A PEP may support standard encryption such as AES and three DES as well as other encryption algorithms.

A typical PEP will support a well defined command line interface CLI via SSH or other security measures. They also leverage NIC and others and AAA authentication techniques involving RADIUS LDAP TACAS and others.

As mentioned above the Key Authority Points KAP are primarily responsible for distributing keys and policies to the PEPs . They are preferably deployed on hardened appliances or on other target elements in the network such as devices utilizing Cisco Application Oriented Network AON . In addition to the functions mentioned above the KAPs perform functions including at least the following 

Key Generation. This module creates keys to secure a given tunnel. In prior art IKE approaches this is done in coordination with a single peer node as each side agrees on outbound and inbound keys. However in an embodiment of the present invention this is performed at the KAP that generates keys for traffic between a number of nodes.

Key Distribution. This module ensures that all connections to the tunnel have the keys necessary to decrypt and encrypt data between the end points. As mentioned previously this is done in standard IKE as part of the IKE Phase 2 key exchange between two peers. However in the present invention this is performed by the KAPs and PEPs exchanging keys over a secure tunnel. With these techniques key distribution is still securely protected to prevent eavesdropping and tampering and to ensure that the exchange occurs with an authorized party.

Policy Distribution. Policies must be installed and or made available to the Policy Enforcement Points . This may be done at configuration or as part of the discovery process. This may also be done on a per packet basis as outgoing packets are detected and have a policy check performed.

While this invention has been particularly shown and described with references to preferred embodiments thereof it will be understood by those skilled in the art that various changes in form and details may be made therein without departing from the scope of the invention encompassed by the appended claims.

