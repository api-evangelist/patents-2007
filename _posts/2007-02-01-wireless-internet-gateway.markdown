---

title: Wireless internet gateway
abstract: A wireless Internet gateway which bridges the gap between the Internet and wireless devices, e.g., via a short message service center (SMSC). The disclosed wireless Internet gateway provides a portal to SMPP, HTTP, TNPP, or other protocol messages using Java Remote Method Invocation (RMI) techniques. Application servers (e.g., in communication with the Internet or an Intranet) insert RMI objects containing messages in a message queue handler of the wireless Internet gateway. The RMI objects are queued and passed either directly to a destination delivery handler (e.g., SMPP, SMTP, HTTP or TNPP protocol handler), or passed through a generic destination interface to provide an additional layer of abstraction to simplify development of the support of other destination protocols. An SMTP handler may be integrated into the wireless Internet gateway to provide direct communication of SMTP protocol messages (i.e., e-mail) to the message queue.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=07949773&OS=07949773&RS=07949773
owner: TeleCommunication Systems, Inc.
number: 07949773
owner_city: Annapolis
owner_country: US
publication_date: 20070201
---
This application is continuation of U.S. application Ser. No. 09 630 762 to SMITH entitled Wireless Internet Gateway filed on Aug. 2 2000 now U.S. Pat. No. 7 228 333 which in turn claims priority from U.S. Provisional Appl. No. 60 196 367 to SMITH entitled Wireless Internet Gateway filed on Apr. 12 2000 the entirety of both of which are expressly incorporated herein by reference.

This invention relates generally to wireless carriers Internet service providers ISPs and information content delivery services providers. More particularly it relates to wireless telecommunications and wireless portals for routing messages from mobile devices to Internet destinations.

Short Message Service Centers SMSCs deliver short messages through a wireless network. Typically they operate on highly valuable server platforms that are protected deep within a wireless carrier s network and communicate via specialized protocols.

In particular as shown in a gateway translates between HTTP protocol messages from the Internet and SMPP protocol messages to wireless devices in a wireless network via an SMSC .

The gateway provides a portal between wireless networks and the Internet . However conventional portals between wireless networks and the Internet generally utilize either a proprietary operating system or are developed to operate on a single operating system e.g. WINDOWS NT or SOLARIS . Moreover conventional gateway architecture provides a communication path between fixed protocol types e.g. between HTTP protocol messages and SMPP protocol messages. Separate gateway application programming interfaces APIs are developed to communicate with other protocol types.

For instance to allow communications between an application server on the Internet using HTTP protocol messages and a paging terminal using TNPP protocol messages a new gateway API must be developed from point to point from the HTTP interface to the TNPP interface. This presents a tremendous amount of development work necessary to support new network elements particularly wireless network elements.

There is thus a need for a more flexible gateway architecture and method which provides interface capability without the need for the total redevelopment of separate gateways to support different types of message protocols.

The present invention provides a wireless Internet gateway which bridges the gap between the Internet and wireless devices e.g. via a short message service center SMSC . The disclosed architecture is modular and provides a generic destination interface to any of a plurality of destination devices of any of a variety of protocols. This reduces redevelopment efforts to those required only between the generic destination interface and the particular destination device eliminating the need for redevelopment of the application programming interface API up to the generic destination interface.

In a particular disclosed embodiment the wireless Internet gateway provides a portal to SMPP protocol messages using RMI techniques. However the present invention has applicability to portals or gateways providing a communication path between RMI objects and any other type of wireless network messaging protocol.

The disclosed embodiment of a wireless Internet gateway in accordance with the principles of the present invention receives SMPP messages on a wireless network side translates those SMPP messages to RMI message objects and re transmits those RMI message objects to an application server having access to the Internet or Intranet e.g. to an E mail server a chat server voice messaging system paging system etc. . The wireless Internet gateway utilizes common protocols e.g. SMPP to allow operation with existing standard conforming wireless networks.

In particular the disclosed wireless Internet gateway is provided between the Internet using e.g. HTTP protocols and a Short Message Service Center SMSC which communicates with wireless handsets over a wireless network using e.g. SMPP protocols.

Importantly the wireless Internet gateway uses Java Remote Method Invocation RMI techniques to communicate with relevant application servers using other transmission protocols of the Internet or Intranet e.g. HTTP SMTP relating to e mail messages etc. . The RMI techniques insert RMI message objects in the wireless Internet gateway which are communicated to a generic destination interface. From the generic destination interface the messages are packaged into relevant messages of the particular destination protocol e.g. SMPP and transmitted to the relevant network element e.g. to an SMSC .

A wireless Internet gateway in accordance with the principles of the present invention effectively provides a shield for a wireless provider s short message service center SMSC from direct interaction with Internet clients. This provides a more secure environment from the perspective of the wireless provider and allows the wireless provider the freedom to implement Internet access for wireless subscribers using existing otherwise non Internet ready SMSCs.

The disclosed wireless Internet gateway is flexible in that it is easily developed to support any input protocol using RMI techniques with a relevant application server providing the particular input protocol and any output protocol developed to package messages from RMI message objects passed to a generic destination interface into the particular output protocol.

The standard protocol commands utilized by the disclosed wireless Internet gateway can be extended or added to software already existing in an SMSC or other appropriate element of a wireless system through the addition of an appropriate Application Programming Interface API . Moreover the wireless Internet gateway can serve as a messaging middleware layer for other applications.

The wireless Internet gateway preferably is implemented so as to be capable of operating on a number of different platforms. One way of accomplishing this is by using software written in the Java programming language. In this way any operating system or hardware platform that supports the Java run time environment can be used to support a wireless Internet gateway application. For instance a wireless Internet gateway application written in Java may be implemented on most operating systems including Linux HP UX Netware Solaris Intel and Sparc and NT.

An important feature of the present invention is the use of Java Remote Method Invocation RMI technology to provide an interface to other application servers which in turn communicate over the Internet. In this way application servers on the Internet are responsible for communicating over the Internet using other protocols e.g. HTTP SNMP SMTP etc. or directly with a user. These application servers on the Internet each then communicate with a wireless Internet gateway utilizing RMI techniques implemented in an appropriate gateway Application Programming Interface API . The disclosed gateway API is a collection of Java classes and their methods which use Java Remote Method Invocation RMI technology to pass data between an application server in communication with the Internet and the wireless Internet gateway.

Thus in accordance with the principles of the present invention as long as an application server in communication with the Internet communicates with the wireless Internet gateway using RMI techniques the application server is free to utilize any other protocol on its front end to communicate over the Internet.

In particular as shown in a wireless Internet gateway together with appropriate application servers bridge the gap between an off the shelf OTS short message service center SMSC and the Internet .

The SMSC communicates with network elements of a wireless network . The SMSC communicates with the wireless Internet gateway using standard SMPP protocol commands.

The wireless Internet gateway in turn communicates with the Internet via one or more appropriate application servers preferably using a Java Remote Method Invocation RMI technique.

The application servers may utilize any appropriate front end to communicate with other servers via the Internet . For instance one application server may be configured to communicate over the Internet using HTTP protocols. HTTP protocols may be appropriate e.g. when a wireless device in the wireless network desires to participate in a chat group hosted by a chat server in communication with the Internet . In such a case the wireless Internet gateway will pass SMPP protocol messages with the SMSC with utilize RMI techniques with the appropriate application server and the application server will translate the chat group postings into HTTP protocol messages for transmission via the Internet to the chat server .

Similarly another application server may be configured with an appropriate application program to provide an SMTP front end presence on the Internet to the wireless Internet gateway . In this way wireless devices in the wireless network may send and receive E mail using SMPP protocol messages from the wireless network to the SMSC and to the wireless Internet gateway which are passed to the appropriate application server using RMI techniques and translated by the application server to the requisite SMTP protocol messages for transmission over the Internet .

Other application servers may provide other types of front ends in communication with the Internet e.g. SNMP.

The Internet front end protocol interfaces shown in as being provided by application servers may alternatively be integrated into the wireless Internet gateway . For instance the wireless Internet gateway may include appropriate application programs and interfaces to provide an SMTP interface directly to the Internet avoiding the need for a separate application server for that purpose.

Similarly the wireless Internet gateway may include integrated front ends for HTTP and or SNMP protocol communication links with the Internet . Moreover the wireless Internet gateway may interface directly with a local chat server .

The wireless Internet gateway may have multiple provisions in its API for relaying data to and from the wireless devices in the wireless network to the application servers . For instance the wireless Internet gateway may implement a queuing technique that attempts guaranteed delivery to a relevant wireless device through multiple transmissions if necessary. An example of a suitable application for the queuing technique is E mail.

In particular as shown in the wireless Internet gateway provides an RMI handler for handling receipt of RMI objects from RMI clients i.e. application servers . The RMI objects are inserted into a queue handler by the relevant application servers . Using RMI techniques the particular front end protocol is abstracted away from the wireless Internet gateway API.

In addition to RMI objects e mail messages are processed by an SMTP handler as they are received and sent to Email application servers

The queuing technique shown in captures incoming messages into a message queue . The messages come from either RMI objects from the front end application servers or as E mail into a built in mail server front end function of the wireless Internet gateway . Thus E mail messages from appropriate E mail clients on the Internet are received and processed by an appropriate SMTP handler and passed on to a queue handler .

In the embodiment shown in the wireless Internet gateway also includes a direct SMTP connection from a local application server provided by an SMPP link proxy module . The SMPP link proxy module allows direct insertion and removal of SMPP formatted messages into a SMPP delivery module .

The integrated SMPP link proxy module may communicate with the external application server using any particular protocol. For instance the SMPP link proxy module may communicate with the external application server using RMI techniques. Alternatively the SMPP link proxy module may communicate with the application server using e.g. SMPP objects etc. The application server may be e.g. another wireless Internet gateway .

The SMPP link proxy module is particularly useful for listening to a particular port. A selected port can be monitored and any all messages sent to that port can be captured by the SMPP link proxy module and passed to the local application server for e.g. printing display transmission via the Internet etc.

The SMPP link proxy module is optional. As shown the SMPP link proxy module provides a mechanism for messages from the wireless network to be passed to a particular application server while the queue handler is most efficient in passing messages from application servers or e mail application servers to a wireless device. However the queue handler can be implemented to handle messages in both directions to and from mobile devices.

RMI objects inserted into the queue handler by the RMI handler allows for a generic approach to the Internet side of the wireless Internet gateway separate from the particular protocol used e.g. HTTP whereas the use of a direct link such as the SMPP link proxy module requires particular development and dedication to a particular protocol e.g. to SMPP as shown in . While RMI techniques can be utilized for multiple application servers utilizing any of a number of different types of protocols on its front end the direct technique dictates a protocol specific implementation.

The queue handler has access to a message cache directory and to a messages database . When a message arrives its contents are stored in the message cache directory and details about the message are stored in the messages database .

Received messages are stored in the a message queue . The message queue orders the messages in an appropriate fashion e.g. by their time of arrival.

A queue monitor in communication with the queue handler and the message queue is responsible for removing a message from the message queue and sending the same on to the SMSC via an appropriate SMPP delivery application module .

If the SMSC acknowledges receipt of the message the message is then removed from the message cache directory and marked as sent in the messages database . If on the other hand the SMSC fails to acknowledge the message the message is copied from the message cache directory and placed back onto the message queue for a subsequent retransmission at the appropriate time. In this fashion messages are retransmitted until they are received.

A second exemplary provision of an API in a wireless Internet gateway is the establishment and integration of a direct connection from a wireless Internet gateway to applications such as chat sessions. In particular the wireless Internet gateway may communicate directly with a chat server using e.g. RMI techniques.

The wireless Internet gateway is capable of supporting features to give messages certain characteristics and or to include particular information with a message. For instance message priority callback numbers and or validity times may be included with messages handled by the wireless Internet gateway .

In particular messages can be given a priority. When a message has a particular priority the priority is signaled to the SMSC which in turn will expedite its delivery.

Callback numbers may be inserted with a message by the wireless Internet gateway . Callback numbers provide a service which generally makes it easier for a recipient to respond to a particular received message.

The wireless Internet gateway may also mark messages with validity times. A validity time in a message allows a recipient to respond accordingly.

When a response is received from the wireless device the wireless Internet gateway passes the message directly to the application server . This session occurs through RMI to provide for the addition of new direct communication servers such as chat servers and web page interfaces.

When a short message of any type arrives at the wireless Internet gateway the short message is examined for its type and destination. The type and destination of the short message dictate how it is handled.

For instance if the received short message is an acknowledgement of a short message sent from the wireless Internet gateway then a receipt acknowledgement of the short message is sent to the source of the short message. As another example if the received short message is an E mail destined for transmission over the Internet then the E mail message is passed to the relevant mobile E mail application server e.g. to the integrated SMPT mail server or to an external SMTP application server which in turn sends the E mail message to a mail relayer for ultimate transmission over the Internet .

In a like fashion each short message received by the wireless Internet gateway from a mobile device is sent to an appropriate internally integrated or external application server for processing e.g. to an HTTP server for transmission over the Internet to an SMTP E mail server for transmission over the Internet etc.

The queue monitor may communicate directly to the SMPP delivery module utilizing appropriate SMPP protocol messages. However to further abstract the particular protocol requirements away from the wireless Internet gateway a generic destination interface may be inserted between the queue monitor or other message source and the destination handler.

The generic destination interface provides an interface between the particular protocol on the destination side of the wireless Internet gateway e.g. SMPP as shown using the SMPP delivery module and the messages in the message queue . In this way adaptation to other protocols need change only the support of the generic destination interface with respect to the destination handler .

For instance the SMPP delivery module may be replaced in the wireless Internet gateway with e.g. another wireless Internet gateway an Internet gateway or a paging terminal . While the SMPP delivery module the wireless Internet gateway the Internet gateway and the paging terminal are all shown together in this is for convenience of explanation only. The disclosed embodiment relates to the implementation of only one of the destination handlers in any one wireless Internet gateway .

In particular as shown in SNMP acces to the wireless Internet gateway may occur through Management Information Base MIB objects. The SNMP access can be considered to occur in three levels of abstraction the top level is the SNMP management console the middle layer of abstraction includes the SNMP agent and the bottom layer of abstraction includes the wireless Internet gateway and inserted RMI objects.

When allowing direct communications between wireless devices and application servers the relevant application server binds to the wireless Internet gateway and receives messages to and from the wireless device s . These messages aren t queued but may be directly relayed from the wireless Internet gateway to the SMSC and the wireless device when they are received.

The status of the wireless Internet gateway can be controlled and monitored by the Simple Network Management Protocol SNMP manager . For instance the SNMP management console may initiate a status inquiry. The SNMP agent inserts a query status RMI object into the wireless Internet gateway and the relevant status in the wireless Internet gateway is obtained.

The wireless Internet gateway may communicate with the SNMP agent of an appropriate application server via an RMI interface. The SNMP agent of the application server b in turn communicates to the SNMP Management Console . Using this facility the wireless Internet gateway may essentially become an SNMP device and thus can be remotely monitored and managed e.g. from the SNMP management console or remote scripts and programs.

Using SNMP management the number of active SMPP links can be seen the last error examined and other configuration changes made. In this way the wireless Internet gateway can be remotely reset if necessary or desired.

SNMP access to the wireless Internet gateway may occur using Management Information Base MIB objects. Each MIB object defines an item to monitor or control. The MIB s may in turn be translated into Java code using a conventional SNMP development package. The generated Java code gathers an internal value of the wireless Internet gateway and makes it visible to the SNMP agent . The code generated from an MIB object can also perform actions within the wireless Internet gateway and in so doing affect the state of the wireless Internet gateway as desired.

The SNMP agent communicates using RMI protocol. Services requiring SNMP access preferably use methods defined by the SNMP agent which in turn communicates with the SNMP management console using SNMP protocol.

SNMP traps which reflect error or alert conditions in the wireless Internet gateway go through the SNMP agent for display on the SNMP management console . Remote processes and scripts may also monitor these traps.

Scripts and separate processes can talk SNMP remotely with the wireless Internet gateway . The code generated from the MIB s provides the interface to do this. This allows other monitoring processes to watch the wireless Internet gateway and for example send notifications to an administrator if any problems occur. They send commands and configuration information as necessary also.

In particular as shown in the wireless Internet gateway may maintain message logs of its activity for local or remote monitoring. For instance plain text files may be made available to be accessed and viewed. As an example of a plain text file a message log may be accessed with a text viewer e.g. a web page server using a LogView Java servlet running on the host machine implementing the API of the wireless Internet gateway .

There are several files to which the text viewer may provide access e.g. read only access . As shown in they may comprise a systems log an accounting log a STDOUT log and a STDERR log .

The text viewer can also show a configuration file for the wireless Internet gateway . The systems log file may contain messages describing the operation of the wireless Internet gateway .

Messages typically have a severity level associated with them e.g. a severity level indicating a serious error and severity levels through being of decreasing severity. The text viewer preferably filters and or presents the messages based on their severity level.

The accounting log file may contain a list of the messages sent through the wireless Internet gateway .

The STDERR log and STDOUT log files may contain messages from the API software of the wireless Internet gateway and may be used by the administrator of the wireless Internet gateway to determine if any program errors have occurred.

The wireless Internet gateway can be statically configured at initialization time via the gateway configuration file .

Table 1 shows an exemplary sample gateway configuration file for a wireless Internet gateway in accordance with the principles of the present invention.

The gateway configuration file may set such parameters as e.g. the maximum message length message transmission timeout host names and or wireless device access number ranges. The gateway configuration file may be a plain text file which is created modified with a standard text editor. The gateway configuration file may contain configuration parameters in a tagged data format. Tagged data format is a descriptive term describing the configuration item and the item s value.

One parameter that may be configured in the gateway configuration file is a spam filter. Spam is unsolicited and unwelcome E mail. By reading the spam configuration values as defined by appropriate spam parameters the wireless Internet gateway can prevent too many messages from the same sender going to a particular recipient. Also the wireless Internet gateway can prevent one sender from sending an excessive number of messages via the wireless Internet gateway .

The wireless Internet gateway may keep track of the number of messages a sender has sent and or how many messages a particular recipient has received.

If the configuration values are exceeded a message may be sent to the systems log . This provides among other things the ability for a wireless carrier to base a subscriber rate based on their own specifically monitored use of the Internet e.g. on a number of messages sent and or received via a wireless Internet gateway .

Support for internationalization may be included in the wireless Internet gateway . For instance responses to users can be configured to reflect the language in the local region where the wireless Internet gateway has been deployed. Internationalization may be implemented using Java property files and its internationalization APIs.

As an example to provide internationalization the gateway configuration file might contain the following two lines 

This demonstrates how an administrator may specify which language and or in which country the wireless Internet gateway will operate. If the locale parameters are not present in the gateway configuration file the language and country may default e.g. to English en and the United States US respectively.

The property files may include a corresponding es AR string in the file name. For example the SMPP.properties file which implies en US may contain a number of possible error messages e.g. 

User parameters may be restricted. For instance to control which parameters a customer can configure the wireless Internet gateway may work with an encrypted license. The license may encapsulate a variety of parameters associated with a customer s license agreement.

In particular a third party license generator may create a customer license in the form of an encrypted file containing all pertinent license information. This may be accomplished by running the license generator and providing it with the allowed configuration. An encrypted license file e.g. smscgw.lic may be deployed with the wireless Internet gateway . Thus when the wireless Internet gateway is started it reads the license file and as it performs its functions it may query the license properties and behave accordingly.

In particular as shown in SMPP Provisioning Protocol also known as the SMPP P protocol allows for the creation modification and deletion of subscribers paging subscribers and distribution lists within the SMSC . The wireless Internet gateway may have provisioning capabilities provided via a web page on an appropriate PC or other computer device operating a web browser . The web browser utilizes HTTP protocol messages to an appropriate HTTP server which in turn communicates with the SMPP P application server e.g. via the Internet or an Intranet.

Alternatively provisioning for the wireless Internet gateway may be provided from a remote wireless device such as a Wireless Access Protocol WAP phone .

SMPP may be implemented as another application server using the RMI protocol as shown in or internally as shown in . In any case the wireless Internet gateway handles transmission and receipt of SMPP P messages with the SMSC .

The wireless Internet gateway may include one or more integrated communication interfaces e.g. simple mail transfer protocol SMTP .

In particular as shown in a wireless Internet gateway including SMTP support includes an integrated SMTP mail server connected to the Internet . E mail is passed between the integrated SMTP mail server and the SMPP application programming interface of the wireless Internet gateway .

The SMTP mail server shown in may insert messages into the message queue shown in directly without the need to utilize RMI techniques. However the wireless Internet gateway may alternatively or additionally communicate using RMI techniques with a particular application server which provides e mail services.

The integration of the SMTP mail server into a wireless Internet gateway allows mail from standard E mail clients to be sent to the wireless Internet gateway and ultimately on to wireless devices serviced by the SMSC in communication with the wireless Internet gateway . The SMTP mail server translates messages between SMTP protocol messages between the wireless Internet gateway and the Internet and SMPP protocol messages between the wireless Internet gateway and the SMSC .

The SMTP mail server may be part of the software constituting the application programming interface API of the wireless Internet gateway and preferably otherwise operates as a standard mail server.

In operation the disclosed SMTP mail server of the wireless Internet gateway monitors a mail port defined by a configuration file for the wireless Internet gateway and answers mail requests sent from E mail clients . When an E mail client sends an E mail message to a wireless device serviced by the SMSC the wireless Internet gateway receives and queues the E mail messagefl. Then the wireless Internet gateway sends the E mail message to the relevant SMSC using SMPP protocol for transmission to the relevant wireless handset in the wireless network .

The API of the wireless Internet gateway may also ensure that an E mail message is truncated if necessary e.g. if the E mail message is longer than the currently configured maximum message length. In addition or alternatively the API of the wireless Internet gateway may be configured to break long E mail messages up into several separate transmissions for transmission to the SMSC and on to the relevant wireless handset in the wireless network .

A user of a mobile device in a wireless network including a wireless Internet gateway in accordance with the principles of the present invention may initiate an E mail message from their mobile device and may receive a receipt therefore indicating that the destination has received and or reviewed the E mail message. In such a case the wireless Internet gateway will send the mobile originated E mail message to an appropriate E mail server using RMI if external to the wireless Internet gateway and that E mail server will accomplish delivery of the E mail message.

In the disclosed embodiment communications between wireless devices and the SMSC of a wireless network and the wireless Internet gateway utilize messages conforming to standard SMPP v3.3 protocols for mobile terminated MT communications with the following exceptions in the case of mobile originated MO communications 

Alpha numeric E mail may be embedded in the source addr field for a short message. In particular E mail addresses can be embedded in source addr field for submit sm messages and in the destination addr for deliver sm messages. Such embedding provides an indication as to where the particular E mail comes from and where it should go. The conventional character or other length limitation may be extended as necessary or desired for these particular fields.

Certain aspects of communications between mobile devices and the wireless Internet gateway are shown and described in co owned U.S. Appl. No. 60 198 108 filed Apr. 18 2000 by Richard A. Smith and Johanna Wilson entitled Short Messaging Service Center SMPP to HTTP Internet Communications the entirety of which is expressly incorporated herein by reference.

In particular as shown in a wireless Internet gateway sends a message to a mobile wireless handset device and requests two types of delivery feedback 1 acknowledgement of when the user reads the message and 2 a response code from the user.

The message is derived from an E mail message received from the Internet to an address e.g. MIN gateway . The wireless Internet gateway supplies the sender s E mail address so that it may be processed by the mobile wireless handset device.

Note that in the preferred embodiment the wireless Internet gateway will not request delivery feedback of any kind when submitting short messages for incoming E mail.

In step of the wireless Internet gateway generates a SUBMIT SM message with key elements populated in the following way 

In step of the SMSC sends a standard submit sm response message. The response is matched to the submit sm by sequence number. The body contains the SMSC generated tracking number.

In step of the user of the mobile device reads the message. A Delivery Ack is sent by the mobile device through the network to the SMSC.

In step of the SMSC generates a Deliver SM message to the wireless Internet gateway using a Delivery Receipt template. The stat portion of the delivery receipt may use identical values as the normal SMSC Delivery Receipt. In the given example the value for the esm class is 8 bit enabled .

The text portion of the delivery receipt will also include the R trigger prior to any text thus indicating the MO tracking number. This tracking number will be the same that was assigned by the original submit sm in step . A M trigger following the R value contains the first 20 characters of the original short message.

In step of the user of the mobile device responds to the received short message with a keypress or other action which results in the generation of e.g. a value of 3 .

In step of the SMSC generates a Deliver SM message to the wireless Internet gateway again using the Delivery Receipt template. In the given example the stat portion of the message contains the response code. e.g. 3 . The esm class value is 16 bit enabled .

The delivery feedback may be dependent on the registered delivery flag value. For example a value of 8 bit enabled may cause only the User Response code to have been returned.

In particular as shown in a mobile device originates a message to the wireless Internet gateway requesting both delivery receipt and a response code from the recipient. The short message could be submitted to an E mail address and the mobile device can request a delivery receipt to ensure that the short message was delivered successfully.

In step of the mobile device generates a mobile originated short message addressed to a particular E mail address.

In step of the SMSC parses the destination address determines that it is formatted like an E mail address and forwards it to the wireless Internet gateway over the SMPP rx connection.

The new ref id may be generated by the mobile device and forwarded by the SMSC through the R trigger.

In step of the wireless Internet gateway generates a deliver sm resp code. This contains the internal tracking number of the wireless Internet gateway within the message body. The sequence number matches that of the Deliver SM.

In step of the wireless Internet gateway has read the short message and generates a delivery receipt to the SMSC. For example it would generate a delivery receipt showing the result of an attempt to forward the E mail message.

The delivery receipt may be formatted as shown and described with respect to step in . In particular the stat field contains the status code and the text field contains the R ref id M message content. The Reference ID value is the same as received from the deliver sm in step of . The esm  class is .

In step of if the wireless Internet gateway were to provide a response code it would generate a delivery receipt with the response code within the stat element and the esm class 16. This would be passed through a submit sm message to the SMSC. Of course delivery receipt need not be implemented in any particular application.

In particular as shown in a wireless Internet gateway in accordance with the principles of the present invention can be configured to run redundantly on separate hardware platforms. In this environment separate wireless Internet gateway servers can be configured to share the workload of client processing and or serve as hot standby servers.

A first wireless Internet gateway provides communication between an SMSC and the Internet . Similarly a second wireless Internet gateway provides communication between the SMSC and the Internet . A network redirector device evenly distributes incoming traffic between the first wireless Internet gateway and the second wireless Internet gateway .

Each of the first and second wireless Internet gateways are given access to separate databases in which they each maintain information about their respective messages. The first wireless Internet gateway can be designated as the primary device with the corresponding database designated as the primary database. The second wireless Internet gateway and corresponding database can be designated as secondary devices.

As messages are processed on one wireless Internet gateway appropriate database software may synchronize information with the other database s .

Upon failure of a primary wireless Internet gateway the network redirector transparently routes the failed wireless Internet gateway s traffic to the remaining wireless Internet gateway s . In this way any pending messages from the failed wireless Internet gateway will not be lost because they will have been sent not only to the database corresponding to the failed wireless Internet gateway but also to the other database s corresponding to the secondary backup wireless Internet gateway s .

Redundant architecture such as that shown in includes primary wireless Internet gateway databases and secondary wireless Internet gateway databases maintaining information about short messages.

The first and second wireless Internet gateways may ordinarily share the load imposed upon them. However if one wireless Internet gateway should fail its messages may be automatically redirected by the network redirector and then handled by one of the redundant wireless Internet gateways .

The wireless Internet gateway provides an abstracted mechanism for sending mobile terminated MT messages where the MT delivery protocol is encapsulated from other GW software components. Using the generic destination interface two way messaging may be implemented to support any relevant protocol e.g. SMPP Reflex SNPP SMTP and other protocols.

Two way messaging may be enabled and disabled in the same way that the RemoteSMPP and other pieces are controlled. The configuration file may define whether or not two way messaging is enabled and or an encrypted license file may also include permission to enable two way messaging.

In particular the exemplary two way messaging software package hierarchy may be implemented e.g. with a number of key components 

A Config class may be configured to interact with the Registrar at runtime in order to dynamically assign sender receiver relationships. A sender can have any number of receivers.

Sub packages define particular aspects of the 2 way capabilities. For example an smtp sub package defines a Sender and Receiver that know how to send and receive SMTP 2Way Messages. The TwoWayMessage class is abstract subclasses provide details specific to particular protocols being used. This allows the handlers to set and retrieve protocol specific parameters while still allowing the messages to be treated in a generic manner.

A remote package provides a mechanism for remote RMI objects to register as 2 way message receivers and senders. This approach is akin to the RemoteSMPP module where external apps can register as SMPP listeners as well as originate SMPP messages into the wireless Internet gateway. However this approach is preferable because it is not tied to a particular protocol.

Protocol handlers within the wireless Internet gateway such as the SMTP handler and the SMPP Delivery module will interact with the two way software modules. Thus if a generic two way feature is enabled in the config file then the SMTP and SMPP listeners will also forward select traffic through the two way module to be delivered to potential listeners.

The API software of the wireless Internet gateway preferably allows objects both within and external to the wireless Internet gateway to receive and send messages in a protocol independent manner.

Integrating listeners and senders can be simplified and configurable at runtime through the use of the configuration file . This is especially true of external applications that wish to register a listeners for particular message senders.

The wireless Internet gateway preferably gracefully handles disconnected Remote applications. If an external application is stopped or re started the wireless Internet gateway preferably logs an error and cleans up all internal references occupied by the remote application.

Using two way messaging a Mobile Terminated Receiver object may be made available in the wireless Internet gateway by which messages can be delivered into the message queue .

In particular as shown in a 2WaySMTPListenerAgent implements an IMessageSender interface . It is therefore able to send messages to whatever ImessageReceivers might want to register with it. The 2WaySMTPListenerAgent would be optionally created by a tcs.ain.smsgw.SMTPSession class. Whenever SMTP messages are sent to a particular address they are sent to the 2WaySMTPListenerAgent rather than delivered into the message queue .

The 2WaySMTPListenerAgent then forwards the message step . to each IMessageReceiver object that had registered with it through the addReceiver function in step .. When the 2WaySMTPListenerAgent tells the receiver to process the message it includes three parameters itself the Sender a Return Path IMessageReceiver object through which responses can be made and finally the message itself.

In this example the message is sent to App which implements both the sender and receiver interfaces. After App receives and processes the message it will want to send a response back. Reponses must be returned to the return path IMessageReceiver object that was provided when the message was received. Since App is also a sender it can directly send the response message to the return path receiver.

In this case the SMTPDeliveryAgent is the receiver that had been specified. The message is received by the SMTPDeliverAgent step and then forwarded back to the user.

In particular RMI is a bit more complicated but similar in nature. As shown in a Remote2Way object brokers the inside and outside worlds. It ensures that references are cleaned up if the remote client should disconnect or fail. It also helps ensure that the core classes do not worry about RMI details at all. For every remote object that binds through the Remote2Way a local proxy object is created which actually binds to the specified senders and relays messages back and forth through the Remote2Way .

As indicated previously the Registrar is used to facilitate connecting receivers to senders. This can be done by explicitly passing in sender and receiver objects to the registrar . However one can also assign unique identifies to senders and receivers and then reference either by their ID rather then by the actual object. This latter approach is useful for objects that need to be connected at runtime as defined by a configuration file .

In the above scenario the Config object assigns an ID to a sender object. A remote app then binds to the wireless Internet gateway s Remote2Way interface and requests to be a listener for the sender with the same given ID. Remote2Way creates a ProxyReceiver for the remote object and then uses the Registrar to register the proxyReceiver as a listener to the Sender with the specified ID.

When the Sender sends a message it will be delivered to the proxyReceiver which forwards it to Remote2Way which then goes to the remote object . The remote object can then reply with a message which will be sent via Remote2Way to the ProxyReceiver which will ensure that it gets delivered to the ReturnPath Receiver that was originally specified when the Sender sent the message.

Remote2Way also provides methods for originating new messages directly to senders. So the remote app can do more than just reply.

A wireless Internet gateway in accordance with the principles of the present invention is particularly useful for wireless carriers and or Internet service providers ISPs . For instance a wireless Internet gateway can also be used within the Enterprise and ISP markets to provide a single point of entry for short message system SMS delivery to multiple wireless carriers.

While the invention has been described with reference to the exemplary embodiments thereof those skilled in the art will be able to make various modifications to the described embodiments of the invention without departing from the true spirit and scope of the invention.

