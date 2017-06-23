---

title: Information management method and information processing device
abstract: An information management method and an information processing device functioning as a node are provided to enable an effective use of information distributed to, and shared with, a plurality of nodes on a network and to enable maintenance of security against leakage of information by controlling information retention. This management method of information gathers information distributed to, and shared with, a plurality of the nodes on a network and holds the information in a state accessible from other nodes to a temporary information memory unit when generating restored information. The information management method is also characterized in setting a flag for showing a history of the information and immediately discarding the information in the case that the retention of restored information becomes improper from a view point of contents of the flag.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08958435&OS=08958435&RS=08958435
owner: Konica Minolta Holdings, Inc.
number: 08958435
owner_city: Tokyo
owner_country: JP
publication_date: 20071005
---
This application is a National Stage of International Application No. PCT JP2007 069576 filed with the Japanese Patent Office on Oct. 5 2007 which is based on Japanese Patent Application No. 2006 303834.

The present invention relates to information management methods in the network in which divided information is distributed to and shared with a plurality of nodes and relates to information processing devices functioning as a node constituting the network.

In recent years a network which has a communication form in which data are freely transmitted and received among arbitrary nodes that constitute the network has come to be used actively.

Conventionally a centralized processing type network that includes a server which functions as a host and is positioned in the center and terminals each of which acts as a client individually accessing the host server was mainly used. Therefore in the case where the terminals needed to communicate with each other the communication is performed via the host server.

Meanwhile a so called distributed processing type network is gradually appearing. In order to realize a mechanism that distributes stored information or distributes process of the information the communication function must also be distributed. Namely data communications must be freely performed between each node that constitutes the network.

As a typical form there is a form of a communication network called P2P Peer to Peer . P2P is a form of use of the network in which the information is directly exchanged among a large unspecified number of nodes. There are two kinds of P2P. They are P2P that technically requires mediation of a central server and P2P that carries data in a bucket brigade type.

Also in the case where a central server is required the central server only provides a file search database and performs connection management of the nodes. The exchange of data itself is performed by the direct connection between the concerned nodes.

A technology to efficiently realize a distributed processing network form mentioned above has been studied refer to patent documents 1 and 2 . In both patent documents 1 and 2 the P2P system is used. Further in Patent documents 1 and 2 there is formed a system in which the data are distributed to and shared with arbitrary nodes and the transmission and reception of data is performed.

Thereby the flexibility as a usage form of the network system has improved and users have gained a large convenience. However on the other hand since processing capability has to be distributed among the nodes there may be a case where the distribution of the processing capability can be seen as a burden from the viewpoint of efficiency.

For example in the case where data are distributed a user is able to share a larger amount of data as the network scale becomes larger. However in the conventional way the user cannot acquire data only by accessing a specific server. It is also necessary to collect the required data distributed from a large network and restore the data in a required form.

In the system in which data can be distributed to and shared with a plurality of nodes just as the above mentioned P2P network system it was needed for a node to collect the necessary data distributed to a large network every time and restore the data into a suitable form. This restoration processing also requires a great cost time CPU power and network traffic .

An object of the present invention is to solve the above mentioned problem and provide an information management method that is able to effectively use information divided and distributed to and shared with a plurality of nodes on a network and to provide an information processing device functioning as a node.

1. An information management method in a network system in which divided information is distributed to and shared with a plurality of nodes the method comprising 

an information restoration step for causing a first node to collect the divided information and generating information which was before divided as restored information and

a temporary storage step for storing the restored information generated in the information restoration step in a temporary information storage section with a flag indicating a history of the restored information in a state that the restored information is accessible by a second node different from the first node.

an information discard step for causing the first node to reference the flag and discarding based on a content of the flag the restored information which is stored in the temporary storage section in the temporary storage step.

a restored information obtaining step for causing the second node to access the first node and obtain the restored information.

a restored information modifying step for when the restored information is modified causing the first node to modify the flag and store the modified restored information in the temporary storage section with the modified flag.

a divided information transmission step for causing the first node to divide the restored information modified in the restored information modifying step to be corresponding to the divided information and transmit corresponding newly divided information to each node storing the divided information which was divided before restored.

an information discard step for causing the first node to reference the flag and discarding based on a content of the flag the restored information which was stored in the temporary storage section in the temporary storage step 

wherein when the restored information has been modified in the restored information modifying step the divided information transmission step is executed before the information discord step is executed.

7. The information management method of Item 2 wherein the content of the flag includes about information stored in the temporary storage section one or more of the followings time at which the information was generated time at which the information was referenced a number of times the information was read out a number of times the information was written an occurrence of error when the information was referenced an occurrence of a system failure and an interruption of a system power and the information discard step is executed when the content of the flag satisfies a predetermined condition.

8. An information processing device as a node in a network system in which divided information is distributed to and shared with a plurality of nodes the information processing device comprising 

an information restoration section for collecting the divided information and generating information which was before divided as restored information 

a temporary storage section for storing the restored information generated by the information restoration section with a flag indicating a history of the restored information in a state that the restored information is accessible by the other nodes.

an information discard section for referencing the flag and discarding the restored information stored in the temporary storage section based on a content of the flag.

a restored information obtaining section for searching the other nodes for restored information stored in the other node 

wherein if the node storing the restored information is found the restored information processing section accesses the found node and obtains the restored information from the found node.

a restored information modifying section for modifying the restored information and the flag stored in the temporary storage section and storing the modified restored information and the modified flag instead of the restored information.

a divided information transmitting section for dividing the restored information modified by the restored information modifying section to be corresponding to the divided information and transmitting each of the newly divided restored information to each node so that the divided information is replaced by each of the corresponding newly divided information.

an information discard section for referencing the flag and discarding the restored information stored in the temporary storage section based on the content of the flag 

wherein when the restored information has been modified by the restored information modifying section the divided information transmission section transmits the divided information before the information discard section discards the restored information.

14. The information processing device of Item 9 wherein the content of the flag includes about information stored in the temporary storage section one or more of the followings time at which the information was generated time at which the information was referenced a number of times the information was read out a number of times the information was written an occurrence of error when the information was referenced an occurrence of a system failure and an interruption of a system power and the information discard section discards the information stored in the temporary storage section when the content of the flag satisfies a predetermined condition.

In an information management method and an information processing device functioning as a node according to the present invention when the divided information distributed to and shared with a plurality of nodes on a network is collected and restored into restored information the restored information is stored in a temporary information storage section in such a manner that the other nodes can access the information whereby each node can efficiently use the restored information.

An embodiment according to the present invention will be described below with reference to the drawings.

The network according to an embodiment of the present invention is LAN Local Area Network configured with nodes such as a plurality of terminal devices a switching hub a router and an authentication server as illustrated in . These terminal devices are connected to the switching hub in a star shape through a twisted pair cable.

The terminal device functioning as a node that constitutes the network is an information process apparatus. Further the terminal device is an apparatus that executes a process of input and output of data from and to another apparatus such as a personal computer a workstation or a printer. Hereafter a node is only referred to a terminal device of this type. Further the embodiment will be described on a premise that a personal computer is used as the information process apparatus.

In this embodiment of the present invention a configuration of a communication network called P2P Peer to Peer is used. P2P is a usage form of the network in which a large unspecified number of nodes directly exchanges information each other. There are two types of P2P. The two types are P2P that technically requires mediation of a central server and P2P that carries data in a bucket brigade manner.

Also in the case where a central server is required the central server only provides a file search database and performs management of the connection between the nodes. The exchange of data itself is performed through direct connection between the nodes.

In this embodiment of the present invention the nodes terminal devices associated with each other in advance are directly connected and communicate with each other without using a central server. The connection topology of will be described later. The node is indirectly connected to the other nodes via a node directly connected with it. The authentication server only performs a management of a certificate for authentication. The authentication server does not directly participate in the connection for communication. The router also does not directly participate in the communication between the nodes terminal devices .

In P2P in order for the nodes to directly communicate with each other the security of how to authenticate mutual validity or how to control the chance for illegal access is important. Therefore a digital certificate issued by the authentication server is used. In an SSL communication which will be mentioned later the digital certificate of X.509 specification is used.

When the digital certificate is expired or the validity of the digital certificate is lost by loss or theft of the secret key the certificate authority adds to a certificate revocation list CRL Certificate Revocation List to disclose the fact.

Hereafter description will be made from the above mentioned viewpoint in the case where these nodes perform mutual data communication and restore and use the information distributed to and shared with the nodes in the network according to this embodiment of the present invention.

As illustrated in the terminal device is configured with a CPU a RAM a ROM C a hard disk a communication interface an image interface an input and output interface and other various circuits or apparatuses.

For example the communication interface is an NIC Network Interface Card . The communication interface is connected to one port of switching hub via a twisted pair cable. The image interface is connected to a monitor and sends out an image signal for displaying it on a monitor.

The input and output interface is connected to an external storage device such as a CD ROM drive or an input apparatus such as a keyboard or a mouse. The interface inputs through the input apparatus the signals indicating how the user operated the input apparatus. Further the input interface causes an external storage device to read the data recorded on a recording medium such as CD ROM and input the data. In addition the interface outputs the data to be written into a recording medium to the external storage device.

The hard disk will be described later using a functional block diagram and . The hard disk stores programs and data for realizing the functions of the following sections a connection table holding section a connection table management section a data holding section a data operating section an authentication section a network application section a data receiving section a data analyzing section of a data generating section and a data transmitting section . These programs and data are read out into the RAM as needed and the program is executed by the CPU

Each node is given with a host name machine name an IP address and a MAC address to be distinguished from the other nodes . The host name can freely be given by an administrator of the network . The IP address is given in accordance with the rule of the network . The MAC Address is an address fixedly given to the communication interface of the node .

In this embodiment of the present invention host names such as PC and PC are given to the nodes terminal device and respectively. Hereafter these nodes may be indicated by their host name.

As illustrated in the nodes are considered to be arranged in a virtual space. As indicated by a dotted line a node is associated to at least one other neighboring node in the virtual space. In addition all the nodes are directly or indirectly associated to each other by this association.

 Directly associated refers to the state in which a node is connected to another node with a dotted line in for example a relationship between PC and PC or PC and PC of . Indirectly associated refers to a state in which a node is connected to another node through one node or more with more than one dotted line for example a relationship of PC and PC of . The node transmits data to other directly associated nodes itself.

For example PC PC PC PC PC and PC in hold connection tables TL TL TL TL TL and TL as illustrated in respectively.

The connection table holding section stores a connection table TL that indicates a list of attributes such as a host name IP address and MAC address of other nodes that is directly associated to the concerned node itself. For example an example of the connection table held in the connection table holding section of each node was mentioned already with reference to . The contents of these connection tables TL are created by the administrator in advance based on the association the nodes .

The connection table management section manages the connection table TL held at the above mentioned connection table holding section .

The data holding section stores as a file these data the attribute data indicating the attribute of the node or a user the data used for a digital certificate of the node itself a certificate revocation list CRL data used by an operating system OS or application software data created by a user with an application software or other various data.

The authentication server issues a digital certificate in response to a request from the node and the concerned node holds the issued digital certificate. The digital certificate is used for authenticating each other at the time of the communication between the nodes . The certificate revocation list CRL registers and indicates the invalidity of the digital certificate caused by withdrawal of a node. The authentication server manages the certificate revocation list CRL and in this embodiment of the present invention in which P2P communication is used each node holds the certificate revocation list CRL and performs management such as update.

The data operating section stores data in the data holding section . The data operating section performs process of updating the data stored in the data holding section . For example the attribute data are updated every time the environment or the setting contents of the node change. Further the data operating section performs process of updating the certificate revocation list CRL .

The data operating section also performs temporary storage and process of data information acquired from other nodes.

The authentication section performs process of authenticating the other nodes based on the digital certificate transmitted from the other nodes . The authentication section verifies whether the transmitted digital certificate is valid or not by referencing the certificate revocation list CRL stored in the data holding section .

The network application section performs a process for the node attempting to newly participate in the network or withdrawing from the network.

The data operating section the authentication section and the network application section perform data communication with the other nodes in the network via the data receiving section and the data transmitting section as needed. Further the data operating section the authentication section and the network application section reference or update the data of the connection table holding section and of the data holding section as needed.

The data operating section includes a temporary information storage section that temporarily stores restored data restored information and a flag that indicates the history of the restored data. The data operating section also includes an operation section that collects data information from the nodes to restore the collected data. When the data is changed in order to write back the stored data in each node the operation section performs the process of re dividing the changed data a distribution process and a flag update. Then the operation section performs the process of discarding the restored data in response to the updating of the flag. These processes are controlled so as to perform the following processing operation.

For example when the operation section collects data information from each node and generates restored data restored information the temporary information storage section temporarily stores the restored data. In addition to that the temporary information storage section temporarily stores a flag that indicates the history of the restored data. The contents of the flag will be described later in detail and examples of the contents of the flag include when the restored data was generated or referenced.

The operation section performs a search to collect the data information from the other nodes and when it found out the node that is temporarily storing the restored data restored information the operation section acquires the restored data from the node and uses it. Which means that the operation section functions as a restored information acquisition device.

Alternatively when there is no restored data in the other nodes the operation section collects the divided data from the other nodes generates the restored data and temporarily stores the restored data along with the flag in the temporary information storage section which means that the operation section functions as an information restoring device.

The operation section performs a process of changing the restored data temporarily stored in the temporary information storage section . Then the operation section replaces the original restored data with the changed restored data and temporarily stores the changed restored data in the temporary information storage section . The operation section also updates the flag. That is the operation section functions as a restored information changing device.

The operation section re divides the restored data corresponding to the divided data before the restoration stored in each node and writes back the data into newly divided data based on the comparison of the flag for the restored data and the flag for every data divided before the restoration and stored in each node. The operation section updates the flag for every divided data. That is the operation section functions as a divided information transmission section.

The operation section similarly references the flag that indicates the history of the restored data temporarily stored in the temporary information storage section . When the flag satisfies a predetermined condition the operation section performs a process of discarding the restored data temporarily stored in the temporary information storage section . This is to avoid the risk of information leak caused by holding the restored data too long in the temporary information storage section . That is the operation section also functions as an information discarding section.

The operation section arbitrarily updates the flag in response to occurrence of a state affecting the history of the restored data for example such a case where the other node references the restored data temporarily stored in the temporary information storage section

The data receiving section performs a controlling a process for performing data communication with the other nodes . The data receiving section receives only the packet that is needed by the node in the packets that are flowing through the network .

The data analyzing section distinguishes the type of the received data by extracting the necessary information from the data received by the data receiving section and by analyzing the contents of the extracted information.

The data generating section creates the transmission data to be transmitted to the other nodes based on instructions of the data operating section the authentication section or the network application section .

The data transmitting section transmits the transmission data generated and packetized by the transmission data generating section to the other nodes .

The node in this embodiment of the present invention can perform SSL Secure Sockets Layer communication between the nodes directly or indirectly associated to each other. SSL is a protocol for safely transmitting and receiving data on a network by encrypting using a digital certificate. The flow of the process that establishes a connection of the SSL communication in this embodiment of the present invention will be described below.

The standard specifications of a common digital certificate and a certificate revocation list CRL are defined as X.509 by ITU International Telecommunication Union . In the following description of the SSL communication the digital certificate is called X.509 certificate.

As a STEP preceding the establishment of the connection with SSL communication the connection itself is established. Assuming that a command for requesting a communication with PC is inputted by a user operating a keyboard on PC for example the data generating section creates a connection request data. The data transmitting section transmits the connection request data to the other node PC.

Then in PC the data receiving section receives the connection request data from PC and the data analyzing section analyzes the data type of the received data. In this case the data will be obviously analyzed to be the connection request data. The data generating section of PC generates connection permission data that indicates the permission for connection. Then the data transmitting section of PC transmits the connection permission data to PC.

When the connection permission data is received by the data receiving section of PC and a predetermined process is performed after that then PC and PC are connected. However at this time the connection of the SSL communication is not established yet and the process then enters into a flow of establishment of the SSL connection.

First in either PC or PC the data generating section generates the SSL version data indicating the available SSL version and the data transmitting section transmits the SSL version data to the other node STEP S . In PC transmits the SSL version data to PC.

Then in PC the data receiving section receives the SSL version data the data analyzing section analyzes the type of the data and the data generating section selects from the versions indicated by the SSL version data one version that can be handled by PC and generates the SSL version selection data indicating the selected version. The data transmitting section of PC transmits this SSL version selection data to PC STEP S .

In PC when the SSL version selection data from PC is received by the data receiving section the indicated SSL version is adopted as a protocol for the intended communication. The SSL version is adopted the same way in PC.

Subsequently in PC a X.509 digital certificate is transmitted to PC. In case where this X.509 certificate is not signed by the known authentication server a chain of the old certificates up until this point is also transmitted. PC has in advance a root certificate verifying the authentication server and PC checks whether a certificate that signed X.509 certificate received from PC exists in them. Further PC checks whether the certificate is included in the certificate revocation list CRL issued by the authentication server that signed the concerned certificate. When the certificate is included in the certificate revocation list CRL the communication is interrupted at this time STEP S .

When the certificate passes the above mentioned authentication process PC notifies PC that PC has finished responding STEP S .

In response to receiving the notice of the end of the response from PC PC generates a premaster key with a random value of 384 bits in order to generate a common key to be used in the SSL communication. The data generating section of PC encrypts the premaster key with a public key of PC contained in X.509 certificate received from PC and transmits the premaster key to PC STEP S .

Based on this premaster key PC generates the common key actually used for encrypting data. Then PC begins to use the common key as the encryption key for communication. PC also transmits to PC a notice of change of encryption informing of change of encryption STEP S .

When PC receives the notice of end of change of encryption from PC STEP S the notice of change of encryption is also transmitted to PC in order to perform the change of the encryption key in PC STEP S . The data receiving section of PC decodes the premaster key which is encrypted with its public key and received from PC with the corresponding secret key. When the data analyzing section verifies that the type of data is a premaster key by analyzing the data the data operating section generates a common key based on the received premaster key. Henceforth between PC and PC an encrypted communication using the common key is performed. That is an encryption key has been changed.

After the change of the encryption key is finished as above mentioned PC transmits the notice of the end of a change of encryption to PC STEP S .

By the above mentioned process the SSL connection is established between PC and PC. Whereby intended communication can safely be performed.

In the above mentioned establishment of the connection the case in which PC verifies the X.509 certificate of PC was illustrated. However PC may simultaneously verify the X.509 certificate of PC. This is called a SSL client authentication communication.

In order to perform this SSL client authentication communication between PCs and between authentication servers each node needs to hold an X.509 certificate. Further in order to verify the certificate the node also needs to hold the root certificate.

Thus each node of the network can achieve the operation for safely communicating with each other as the authenticated nodes.

In the network according to this embodiment of the present invention as mentioned above a mutual authentication establishment of the SSL communication and transmission and reception of data are performed between the associated nodes terminal device which are prescribed in the connection table TL.

Data information that are divided distributed to and shared with the nodes can be used in any node through searching and collecting based on such communication. In the following descriptions all of the information which is distributed to and shared with each node and is to be acquired and restored will be referred to as data.

The data to be distributed and shared is passed onto the data operating section . The operation section of the data operating section divides data by a known method. As a data dividing method for example a striping method may be used in which method a document is divided into pieces by a unit of line. The publicly known methods may be used such as a two dimensional parity method a multiplex parity method and a reed solomon method.

The data operating section determines where to distribute this divided data in accordance with the connection table TL held in the connection table holding section . The distribution may be determined arbitrarily. Alternatively a certain weighting may be set to the nodes and the data may be distributed based on the weighting.

The divided data are sent to the data generating section to be formed into a network packet form and are transmitted to the assigned node through the data transmitting section .

In the node that received the divided data the received divided data is finally stored in the data holding section via the data receiving section the data analyzing section and the data operating section . When there is an access from the other nodes the operation section of the data operating section references the data holding section and performs process of providing data and other processes.

In the information management method in the above mentioned network according to this embodiment of the present invention in order to improve the efficiency of the use and restoration of data distributed to and shared with each node the restored data is temporarily stored in the temporary information storage section in the node in which the data restoration was performed. Further the node keeps the restored data in the state that the other nodes can access the restored data and discard the restored data after a certain period by using the flag.

In the flow from the generation to discard of the restored data processes may be executed such as changing writing back of data and access from the other nodes. Example of such typical flows will be described below.

First a node A that is to use the distributed and shared data transmits a search command to each node and receives a response STEP S . The search command may be multicast or broadcast using UDP User Datagram Protocol . The search command may also be transmitted by unicast in accordance with the connection table TL held in the connection table holding section .

Thereby the node A recognizes each node B that is storing the divided data. Further the node A also recognizes whether there is a node C that already restored the divided data and temporarily stores the restored data.

In STEP S it is determined whether there already is restored data temporarily stored. When the restored data already exists STEP S YES the process proceeds to STEP S and a process of acquiring the restored data is performed. The restored data acquisition process of STEP S will be mentioned later. When the restored data does not exist STEP S NO the process proceeds to STEP S and a process of data restoration is performed. The data restoration process of STEP S will be mentioned later.

In STEP S a temporary storage of the restored data is performed. Setting up a flag is also performed. The process of temporary storage of data will be mentioned later. From here to the point of time when the flag is referenced in STEP S every time there is a change in the history regarding the restored data such as access from the other node the flag is updated.

In STEP S it is checked whether there is a search command searching for the restored data from the other nodes. When there is the search command STEP S YES the process proceeds to STEP S. Then the node replies that there is the restored data and provides the restored data. In addition the restored data may have already been changed before this time. The restored data acquisition process in such a case will also be mentioned later. When there is no search command STEP S NO the process proceeds to STEP S.

In STEP S it is determined whether to change the stored restored data or not. When performing the change STEP S YES the process proceeds to STEP S and the restored data changing process is performed. There is the case in which the node that holds the restored data requests the change or the case in which the other node requests the change. Both cases will be described later. When not performing the change STEP S NO the process proceeds to STEP S.

In STEP S the flag of the stored restored data is referenced and whether it is time to discard the data or not is determined. The data discarding determining process will be described later.

When it is time to discard the data STEP S YES the process proceeds to the following STEP S. When it is not time to discard the data STEP S NO the process returns to STEP S. STEP S through STEP S are repeated until it is time for discarding the data.

In STEP S before discarding the restored data whether the restored data has been changed or not is determined. When the data has been changed STEP S YES the process proceeds to the following STEP S. Then the process of writing back the restored data is performed. The process of writing back will be described later in detail. When the data has not been changed STEP S NO the process proceeds to STEP S. Then the discarding process of the restored data is performed.

The above is a flow of typical process from generating the restored data to discarding the restored data. The more detailed example of the process of each step will be described below.

First in the node A when a request to use data D distributed and shared is generated STEP S a search command is transmitted to each node B from the node A STEP S . In response to the search command each node B which the data D is distributed to and shared with transmits a response to the node A STEP S . Then the node A acquires the response. Thereby the node A recognizes each node B that store the divided data. Further the node A also recognizes that none of the node C temporarily stores the restored divided data.

The above is the same as that of STEP S of . However note that in this case there is no node C that temporarily stores the restored data D.

However in this case not all of the nodes that received the search command may reply a respond. Some nodes may not return a response for the reason of occurrence of failure or some other thing. If PC for example does not respond in the data D cannot be acquired.

In such a case the node A selects one of the options acquiring all the divided data to generate the restored data D and generating a partial restored data D with the attainable data D to D . Since data are divided generally with redundancy there may be a case that the entire data is restored from partial data.

Data does not necessarily need to be restored entirely. If not in the above case intentionally partially restored data may be enough. illustrates an example of acquiring divided data and performing the restoration process for just the first 20 pages. In this case which part is restored is indicated in the flag to inform a node attempting to acquire the restored data. In the case of partial restoration the restored part needs to include enough information to read out and to use.

When all of each node B have retuned the response the data operating section of the node A requests the data transmission from each node B storing the divided data D through D in the following STEP S. In response to these requests each node B returns in STEP S the divided data D to D stored each in nodes B.

Subsequently in STEP S the data operating section of the node A generates original pre divided data as the restored data D using the acquired divided data D to D . That is from the above mentioned STEP S to STEP S function as the information restoration process.

Next in STEP S the data operating section of the node A sets up a flag corresponding to the restored data D. First a content of the flag is restoration time. However other than the restoration time the information regarding its history such as when referenced read out and writing in is included in the flag. After the following temporary storage change of the history will be updated every time there is a change.

Next in STEP S the data operating section of the node A stores the restored data D and its flag to the temporary information storage section in the node A in a state that is accessible from other nodes. That is the above mentioned STEP to STEP S function as the temporary storage process.

After the temporary storage process of this restored data D the node A becomes a temporary storage node C of the restored data.

The following STEP S to STEP S are the same as STEP S to STEP S regarding the information restoration process of . However there is a premise that the temporary storage node C of the restored data D exists in this case.

First when a request to use the distributed and shared data D is generated in the node A STEP S the node A transmits the search command to each node including node C STEP S . In response to the search command each node which the data D is distributed to and shared with transmits a response. Then the node C replies that the node C is temporarily storing the restored data D STEP S . Thereby the node A recognizes the existence of the node C here PC that temporarily stores the restored data D and recognizes each node B that stores the divided data.

Next in STEP S the data operating section of the node A requests the restored data transmission to the node C that temporarily stores the restored data D. In response to this in STEP S the node C returns to the node A the restored data D that is temporarily stored in the node C.

Subsequently in STEP S the data operating section of the node A acquires the restored data. In STEP S the node C that provided the restored data updates the history of the flag. That is the above mentioned STEP S to STEP S function as the restored information acquisition process.

Similarly illustrates a sequence diagram showing an example of the flow of the restored data acquisition process corresponding to STEP S of and a change is added to the restored data itself change of restored data will be mentioned later .

The example of the restored data acquisition process between the node A hereafter referred to as PC in this page that requests the data and the node C hereafter referred to as PC in this page that temporarily stores the changed restored data D will be described with reference to .

The following STEP S to STEP S are the same as STEP S to STEP S regarding the restored information acquisition process of . However in this case there is a premise that the restored data held by the temporary storage node C has been already changed to the restored data D.

First when a request to use the distributed and shared data D is generated in the node A STEP S the node A transmits the search command to each node B including node C STEP S . In response to the search command each node which the data D is distributed to and shared with transmits a response STEP S and the node C responds to the node A that the node C is temporarily storing the restored data D STEP S . Thereby the node A recognizes the existence of the node C here PC that temporarily stores the changed restored data D and recognizes each node B that stores the divided data.

The restored data D has been already changed. The contents of change can be recognized from the history indicated in the flag. Therefore PC is able to collect the divided data D to D . Also PC is able to acquire the changed restored data D. Further PC is able to acquire the original restored data D and the difference of change D D based on the restored data D.

Next in STEP S for example the data operating section of the node A requests from the node C the transmission of the restored data D and the changed data D D. In response to this in STEP the node C transmits the temporarily stored restored data D and the changed data D D which is the difference of the original restored data D and the restored data D. In some cases the restored data D can be generated by collecting the divided data from the node B as in STEP S. The changed data D D and the restored data D are acquired as needed. There may be a case in which only the restored data D is acquired.

Subsequently in STEP S the data operating section of the node A acquires the restored data D and the difference data D D. In STEP S the node C that provided the restored data updates the history of the flag. That is the above mentioned STEP S to STEP S function as the restored information acquisition process.

When a request for change of the restored data D is generated first in STEP S the data operating section performs the process of changing the restored data D temporarily stored in the temporary information storage section . Subsequently in STEP S the data operating section replaces the restored data D with the changed restored data D in the temporary information storage section to be newly stored.

Next in STEP S the data operating section updates the flag. The time when the data was changed last time and the contents of the change for example are indicated in the flag. That is the above mentioned STEP S to STEP S function as the restored information change process.

The following STEP S to STEP S are an example of the process in the case where the change of restored data D is requested from the other nodes A. There is a premise that the node A recognizes that the node C temporarily stores the restored data. The contents of change are instructed by the node A and the process of changing is executed in the node C.

First in STEP S the node A transmits the change request of the restored data D to the node C. In response to the change request the node C transmits the response of whether to approve the request or not to the node A in STEP S. When the node C approves the change the node A transmits the restored data D and its changed section or the changed restored data D itself to the node C in STEP S. In STEP S the node C transmits the acknowledgment of receipt of the contents of change to the node A. Then the node C begins the change process of the temporarily stored restored data D.

The following STEP S to STEP S are the same as STEP S to STEP S which are the restored information change process of . Therefore the description will be omitted. That is STEP S to STEP S function as the restored information change process.

Next in STEP S the data operating section of the node C notifies the completion of the restored data change process to the node A.

Further in STEP S the node A acquires the changed restored data from the node C and verifies the changed restored data. The procedure of acquiring the changed restored data is not described in detail. However the procedure may follow the already mentioned procedure of the restored data acquisition process or .

The example of the restored data assigning process between the node C that issues assignment of the temporary storage of the restored data and the node A that accepts the temporary storage of the restored data will be described with reference to . When the process ends the node A becomes the node C and the node C becomes the node A.

The change of roles assigner and accepter can be requested by either node. illustrates a case in which the node C being the temporary storage node requests the assignment.

First in STEP S the node C transmits the request for undertaking of the temporary storage of the restored data to the other suitable node A. In STEP S in response to the assignment request the node A for example transmits the response of approval.

In STEP S the node C receives the response of approval from the node A and transmits the information such as the restored data D and the attached flag to the node A. In STEP S the node A that received the information such as the restored data D and the attached flag transmits acknowledgment of receipt to the node C. Then the processes of assignment and acceptance end.

Subsequently in STEP S the node C that finished the assignment discards the information regarding the stored restored data D. That is STEP S functions as an information discarding process. Thereby the node C is no longer the temporary storage node. That is the node C is not the node C any longer.

Next in the node A that accepted the assignment the temporary storage process is performed. In STEP S the history of the flag accompanying the acceptance of the restored data is updated. In STEP S the restored data D and its flag are temporarily stored in the temporary information storage section in a state where the information is accessible from the other node. That is STEP S to STEP S function as the temporary storage process.

Thereby the node A that accepted the assignment becomes the temporary storage node. That is the node A becomes the node C. This situation is kept until the information discarding process for discarding the restored data accepted by this node is executed.

The writing back process is executed when the restored data is changed as already mentioned in reference to . Further the writing back process is executed from the time when that was determined to be the time for discarding the information STEP S until before executing the discarding process STEP S . Therefore with a premise that the temporarily stored restored data will be discarded the following writing back process is executed in order to reflect the changed content to the originally stored divided data.

First in STEP S the temporarily stored restored data D is divided again to be written back in the temporary information storage section in the data operating section of the node C. The restored data D is divided in such a manner that each divided D corresponds to the originally stored data divided to be distributed to and shared with.

Next in STEP S the node A transmits the writing back request to each node B. In STEP S each node B receives the writing back request and replies whether to deny or accept. Here for example in the case where the flag of the restored data D is newer than the flag that indicates the creation time of the divided data stored in the node B the node B responds to accept the request. When the flag of the restored data D is not newer the node B replies to deny the request.

Upon receiving the reply of acceptance from each node B in the following STEP S the node A transmits the divided and changed restored data D to D to each node B that stores corresponding divided data D to D respectively.

In STEP S each node B receives the divided and changed restored data that corresponds to each node and write back each divided data to be stored. Further in STEP S an update process is also performed to the flag regarding the storage data.

The node A transmits the completion notice that notifies the end of the update process of the stored data to the node C and then the writing back process of the changed restored data D ends. That is the above mentioned STEP S to STEP S function as a divided information transmission process.

As a special case illustrates the state in which the change of the restored data cannot be reflected to the divided storage data. Here a state in which PC functioning as node C is transmitting a writing back request to PC to PC and acquiring the responses is illustrated. In an ordinary case PC replaces the divided data D to D stored in PC PC PC and PC with the new divided data D to D prepared from the restored data D respectively.

However in this case the reply of refusal is coming from PC PC PC and PC. The time of the divided data stored in each PC last changed is newer than that of restored data D changed by PC. That is the divided data stored is already reflected to D to D .

New data cannot be replaced by old data. In the information management method of this embodiment of the present invention such incident does not usually occur. However for example such incident may occur in case where the power supply of PC briefly stops for a certain reason and the restored data of PC disappears from the network.

Even when PC is in such situation in which the writing back is not possible PC performs the already mentioned restored data assigning process and ends the role of the temporary storage node. Alternatively PC can take measures such as to search for new restored data and attempt to perform the restored data changing process again.

In the case where the security is prioritized when there is a trouble such as stop of the power supply the information discarding process mentioned below is unconditionally executed and PC ends its role as the temporary storage node.

When it was determined from reference to the flag in STEP S of to be the time for discarding the information the information such as the restored data and the flag is discarded in STEP after a necessary process such as the restored data writing back process. Then the temporary storage node ends its role as the temporary storage node. That is STEP S and STEP S of function as the information discarding process.

The timing for discarding the information is controlled by the contents of the flag but basically the information is discarded after a certain laps of time to avoid the risk of information leakage to a third party because of a long time of storage of the data.

For example it is the restoration time. The time when the restored data is generated is recorded and when a fixed period time lapses after the restoration the information is discarded.

For example it is the reference time. The time when the restored data is last referenced is recorded and when the restored data is not referenced for a certain period after that time the information is discarded.

The flag is thus updated every time the date is accessed. When the data is frequently accessed the data is not discarded and when a certain period of time has passed without access the data is discarded.

Other than the above mentioned as an example of the contents of the flag the timing for discarding the information can be set by estimating the frequency of use from the number of times of read out and the number of times of write in.

Further from the security point of view apart from the degree of use it is effective to discard information based on data reference error system error and other error occurred. It is preferable to discard the restored data every time the power supply stops.

Of course apart from the contents of the flag it is possible to arbitrary discard the information held in the temporary information storage section depending on an instruction of the administrator.

Thus according to the information management method and the information processing device functioning as a node according to the embodiment of the present invention the divided information which is distributed to and shared with a plurality of nodes on the network is collected the restored information is generated and the restored data is stored in the temporary information storage section in a state that the restored data is accessible from the other nodes. Thus each node is able to efficiently use the restored information. In addition a flag that indicates the history of the information is provided. When the holding of the restored information is determined to be inappropriate based on the contents of the flag the security against the information leakage is secured by immediately discarding the information.

The scope of the present invention is not limited to the above mentioned embodiment. As far as it does not depart from the scope of the present invention a modification of the embodiment is also included in the present invention.

