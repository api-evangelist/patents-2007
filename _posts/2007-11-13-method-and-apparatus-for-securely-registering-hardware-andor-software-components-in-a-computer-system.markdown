---

title: Method and apparatus for securely registering hardware and/or software components in a computer system
abstract: A system that securely registers components in a first system is presented. During operation, the first system receives a request from an intermediary system to obtain configuration information related to the components in the first system. In response to the request, the first system: (1) encrypts configuration information for the first system using a first encryption key; (2) encrypts the first encryption key using a second encryption key; and (3) sends the encrypted configuration information and the encrypted first encryption key to the intermediary system so that the intermediary system can forward the encrypted configuration information and the encrypted first encryption key to the second system, whereby the encrypted configuration information is cryptographically opaque to the intermediary system. Next, the second system uses the configuration information to register the components in the first system.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08064606&OS=08064606&RS=08064606
owner: Oracle America, Inc.
number: 08064606
owner_city: Redwood Shores
owner_country: US
publication_date: 20071113
---
The present invention relates to techniques for obtaining configuration information from a computer system. More specifically the present invention relates to a method and apparatus for securely registering hardware and or software components in a computer system.

As the number of computer systems used by an organization increases it becomes progressively harder to perform system maintenance operations for these computer systems. One of the tasks involved in maintaining a computer system is to obtain configuration information for the computer system. For example this configuration information can include information about software and hardware components installed in the computer system. Moreover this configuration information can be used to perform maintenance tasks such as offering initialization information to the computer system registering any software firmware and hardware component with the computer system offering software and firmware patches or offering replacements for outdated hardware components.

To obtain this configuration information a system administrator typically uses a computer system belonging to the administrator to remotely request configuration information for one or more target computer systems. During this process it is desirable to require minimal interaction with a system administrator or the target systems. However at the same time there is a need to prevent unauthorized users or systems from viewing the configuration information.

Hence what is needed is a method and an apparatus for securely registering hardware and software components in a computer system.

Some embodiments of the present invention provide a system that securely registers components in a first system. During operation the first system receives a request from an intermediary system to obtain configuration information related to the components in the first system. In response to the request the first system 1 encrypts configuration information for the first system using a first encryption key 2 encrypts the first encryption key using a second encryption key and 3 sends the encrypted configuration information and the encrypted first encryption key to the intermediary system so that the intermediary system can forward the encrypted configuration information and the encrypted first encryption key to the second system whereby the encrypted configuration information is cryptographically opaque to the intermediary system. Note that the term cryptographically opaque means that a system without a security credential associated with the cryptographically opaque configuration information cannot access the configuration information. Next the second system uses the configuration information to register the components in the first system. In some embodiments the first system is an end host system the second system is a server e.g. a sever which receives configuration information for computer systems from one or more intermediary systems and the intermediary system is a service tag registration client. These systems are described in more detail below.

In some embodiments the configuration information can include one or more of a version number of one or more software packages installed on the first system a version number of one or more hardware components installed on the first system serial numbers for hardware components serial numbers for software components an operating system version number firmware version numbers for hardware components runtime instances of software components and any other configuration information for a system.

In some embodiments a new session key is generated for each request from an intermediary system to obtain configuration information.

In some embodiments prior to encrypting the configuration information for the first system the first system determines the configuration information for one or more components within the first system. The first system then stores the configuration information for the one or more components in a database within the first system.

In some embodiments the components can include one or more of hardware components and software components.

In some embodiments prior to encrypting configuration information the first system compresses the configuration information.

In some embodiments the second system receives the encrypted configuration information and the encrypted first encryption key at the second system. Next the second system uses a third encryption key for the second system to decrypt the encrypted first encryption key. The second system then uses the decrypted first encryption key to decrypt the encrypted configuration information.

In some embodiments the second encryption key is a public encryption key for the second system and third encryption key is a private encryption key associated with the second encryption key.

In some embodiments the second system stores the decrypted configuration information in a database within the second system.

In some embodiments prior to responding to the request from the intermediary system the first system receives a public encryption key for the intermediary system. The first system then determines whether a public encryption key for another intermediary system has already been received.

In some embodiments if the public encryption key for another intermediary system has already been received the first system determines whether the public encryption key for the intermediary system matches an already received public encryption key for another intermediary system. If so the first system determines that the intermediary system has already been associated with the first system.

In some embodiments if the public encryption key for the intermediary system does not match an already received public encryption key for another system and if the intermediary system is a valid intermediary system the first system determines that a rogue intermediary system was inappropriately associated with the first system. The first system then performs a remedial action.

In some embodiments if the public encryption key for another intermediary system has not been received the first system stores the public encryption key for the intermediary system. The first system then associates the intermediary system with the first system.

In some embodiments the first system receives a request for the first encryption key from the intermediary system. In response to the request the first system 1 encrypts the first encryption key using a public encryption key for the intermediary system and 2 sends the encrypted first encryption key to the intermediary system. The intermediary system receives the encrypted first encryption key and 1 uses a private encryption key for the intermediary system to decrypt the encrypted first encryption key and 2 decrypts the encrypted configuration information using the decrypted first encryption key.

In some embodiments if the configuration information is compressed the second system decompresses the decrypted compressed configuration information.

The following description is presented to enable any person skilled in the art to make and use the invention and is provided in the context of a particular application and its requirements. Various modifications to the disclosed embodiments will be readily apparent to those skilled in the art and the general principles defined herein may be applied to other embodiments and applications without departing from the spirit and scope of the present invention. Thus the present invention is not limited to the embodiments shown but is to be accorded the widest scope consistent with the principles and features disclosed herein.

The data structures and code described in this detailed description are typically stored on a computer readable storage medium which may be any device or medium that can store code and or data for use by a computer system. This includes but is not limited to volatile memory non volatile memory magnetic and optical storage devices such as disk drives magnetic tape CDs compact discs DVDs digital versatile discs or digital video discs or other media capable of storing computer readable media now known or later developed.

In some embodiments service tags enable software and hardware components installed within a host system to be registered with a central system e.g. a server or a service . In some embodiments a service tag registration application is executed on a service tag registration client ST registration client . In some embodiments the ST registration client obtains a copy of a service tag registry ST registry within one or more hosts systems. The ST registration client then sends the data contained in the received ST registries to the central system.

In some embodiments the central system includes a public private key pair wherein the public key is distributed to the end hosts. In some embodiments when the ST registration client requests that an end host send its ST registry contents to the ST registration client the end host generates a new symmetric key k encrypts the contents of the ST registry with k and k is encrypted with using the public key of the central system. Note that a symmetric key is typically a shared secret between two or more systems. Unlike a public key encryption system a symmetric key is typically not widely distributed e.g. it is not made available all computer systems . The end host then sends the encrypted data and the encrypted k to the ST registration client.

In some embodiments it is desirable for the ST registration client be able to read the configuration information prior to forwarding it to the central system. In order to do so the end host encrypts k with the public key of the ST registration client. The ST registration client can then request k from the end host and use its private key to decrypt the encrypted session key. The ST registration client can then use the decrypted session key to decrypt the encrypted configuration information.

In some embodiments the end host may not have a public key for a ST registration client. Hence it is desirable for the end host to remember if it is associated with an ST registration client or not. In some embodiments if the end host has the public key for a ST registration client the end host is associated with the ST registration client. Otherwise the end host it is not associated with the ST registration client. In some embodiments the public key for the ST registration client can be installed manually i.e. touch or supplied the first time the ST registration client contacts the end host i.e. no touch . The no touch technique has the risk that a rogue registration client can install a public key that does not belong to a valid ST registration client. In some embodiments the risk can be mitigated by reducing the time window between ST software installation and first registration client invocation. The smaller that time window the shorter the time in which this risk exists. Furthermore since an ST registration client can raise an alarm if a mismatch between a stored and presented public key is found a rogue registration can readily be detected.

Server can generally include any computational node including a mechanism for servicing requests from a client for computational and or data storage resources. Server ST registration client and end host can be located at the same physical location e.g. within the same building or can be located at different physical locations. Similarly server ST registration client and end host can be located on same network e.g. the same corporate network or can be located at different networks. Note that a network can generally include any type of wired or wireless communication channel capable of coupling together computing nodes. This includes but is not limited to a local area network a wide area network or a combination of networks. In some embodiments of the present invention the networks can include the Internet. Furthermore in some embodiments server can include one or more computer systems.

In some embodiments discovery agent listens for requests from ST registration client to send service tags for end host to ST registration client . Discovery agent then responds by informing ST registration client at which port and with which protocol e.g. TCP UDP etc. on end host to retrieve service tag information. In some embodiments when ST registration client contacts the appropriate port on end host listener agent receives the request and communicates with ST helper .

In some embodiments ST helper interacts with ST registry software component and hardware component . ST registry can store one or more service tags for one or more software components and or one or more hardware components. Note that a service tag includes configuration information for a given software or hardware component. Also note that any number of hardware and or software components can be included in end host .

In some embodiments a service tag can include a version number of one or more software packages installed on the first system a version number of one or more hardware components installed on the first system serial numbers for hardware components serial numbers for software components an operating system version number firmware version numbers for hardware components runtime instances of software components and any other configuration information for an end host.

In some embodiments ST registry is a database which can include any type of system for storing data in non volatile storage. This includes but is not limited to systems based upon magnetic optical and magneto optical storage devices as well as storage devices based on flash memory and or battery backed up memory.

In ST helper retrieves service tags step from ST registry . Similarly this process is also performed at end host and any other end hosts to which ST registration client made the request.

In ST registration client collects and forwards all service tags to server step . Note that server can collect service tags from one or more ST registration clients. For example server can collect service tags for ST registration clients located within a plurality of businesses.

The advantage of the above described process for obtaining service tags is that it is a no touch technique wherein pre installation of a trust anchor e.g. a security certificate is not necessary. If a system claiming to be a ST registration client requests service tags from an end host the end host responds by sending the service tags to the ST registration client. However this process presents a possibility that a rogue ST registration client can request and obtain service tags from end hosts. Hence the rogue system can obtain information about software and hardware components on the end host. This information can then be used by the rogue system to determine whether security holes exist in the given software and hardware components within the end host system. If so the rogue system can mount an attack on the end host. Hence it is desirable to provide a no touch technique for obtaining service tags without the above described problem.

In ST helper retrieves service tags step from ST registry . ST helper then generates a session key k step and uses k to encrypt the retrieved service tags step i.e. Z ST ST k kk . In some embodiments the service tags are compressed prior to being encrypted by the session key. In other embodiments the service tags are not compressed. Similarly this process is also performed at end host and any other end hosts to which ST registration client made the request.

Note that server can collect service tags from a number of ST registration clients. For example server can collect service tags from ST registration clients located within a plurality of businesses.

In some embodiments the service tag creation phase is executed once for each software and or hardware component being installed on a host system H. A new service tag stis created for each software and or hardware component within H and the service tag is registered it with H e.g. using an application programming interface . H then stores the new service tag in the clear into its ST Registry database

In some embodiments the service tag registry request response phase is executed once for each host system e.g. OS instance that contains a service tag registry ST Registry .

In some embodiments a registration client C creates a nonce i.e. a number which is used only once . Next C signs the nonce and its public key k. C then calculates a hash value h H nonce k k.

In some embodiments C formats and sends a message m REQUEST ST REG DB k nonce h to H where REQUEST ST REG DB is a command which instructs a host system to send service tags to the C.

H then receives m where m indicates that the message may not be a message sent from a valid registration client C the validness of the message is determined below .

In some embodiments H can be in one of two states affiliated or unaffiliated. If H is in an affiliated state then H has previously stored a public key Kfor a registration client C. If H is in an unaffiliated state then H has not previously stored a public key Kfor a registration client C.

In some embodiments if H is in an affiliated state H aborts the communication with C if the received public key k does not equal the kthat was previously stored.

In some embodiments if H is in an unaffiliated state H stores the received public key k and enters an affiliated state wherein H is affiliated with the registration client C whose public key is k .

In some embodiments H generates fresh symmetric key k for each request from a registration client. Next H encrypts k using the public key for C i.e. kk and stores it locally for C to validate the encrypted content. H then encrypts k using the public key for the server i.e. kk . Next H retrieves the service tags from the service tags ST registry database ST DB .

In some embodiments H compresses the retrieved service tags i.e. Z ST DB . H then encrypts the compressed ST DB contents with k i.e. Z ST DB k .

In some embodiments H formats and sends m REPLY ST REG DB Z ST DB k kk nonce h . Next C receives m . C aborts the transaction with H if the received value h H nonce k k. C also aborts the transaction with H if the received nonce is not fresh e.g. not within a specified time period after the message was generated .

In some embodiments C can examine the encrypted service tag data received from H. C retrieves a stored encrypted symmetric key kkfrom H out of band. Next C formats and sends m REQUEST K . H then formats and sends m REPLY K kk . In some embodiments C first authenticates itself with H before H sends C the encrypted session key kk. If C is a valid registration client then H sends kkto C.

In some embodiments after receiving the session key from H C can examine the contents of each collected Z ST DB k prior to uploading the service tags to S because C can recover the key k using C s private key kas follows 1 C recovers the session key k from kk 2 C decrypts Z ST DB k with k 3 C calculates decompression of Z ST DB and 4 C presents ST DB to an administrator who can review the contents of ST DB and uploaded ST DB to S.

In some embodiments after C receives service tags from H or a number of end hosts C uploads the service tags to S e.g. C sends m UPLOAD ST DBS Z ST DB k . S can then retrieve the contents of the received Z ST DB k because S can recover the key k by decrypting the received values k using its private key k.

In some embodiments mand mare sent are sent once for each leaf node unless there is packet loss corruption etc. .

In some embodiments mis sent once for each registration unless there is packet loss corruption etc. .

The above described exemplary implementation substantially minimizes the interaction with S making the architecture scalable. Furthermore the above described exemplary implementation protects against replay attacks by using nonces for challenge messages and challenge responses. If a message is modified by an active eavesdropper in any way it can be detected.

In some embodiments the above described exemplary implementation is stateless at all nodes except for the nonces that protect against replay attacks. However if a local clock value is used as the nonce i.e. no globally synchronized clock is used the above described exemplary implementation is completely stateless. Hence the above described exemplary implementation can protect all participants against a memory resource denial of service attack e.g. SYN flooding .

The foregoing descriptions of embodiments of the present invention have been presented only for purposes of illustration and description. They are not intended to be exhaustive or to limit the present invention to the forms disclosed. Accordingly many modifications and variations will be apparent to practitioners skilled in the art. Additionally the above disclosure is not intended to limit the present invention. The scope of the present invention is defined by the appended claims.

