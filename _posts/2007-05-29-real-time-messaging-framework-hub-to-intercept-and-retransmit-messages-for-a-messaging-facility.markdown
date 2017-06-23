---

title: Real time messaging framework hub to intercept and retransmit messages for a messaging facility
abstract: Methods and systems are provided for communicating an event from a server to a set of applications via a real time messaging framework hub, which communicates with the applications on individual channels and with the server on a single channel. A polling message is sent to the server and a reply is received. From the reply, it is determined whether the event has occurred. A polling message is received from a client, and a reply is sent containing either the event, if it has occurred, or a null response is sent indicating that the event has not occurred. Limitation of server communication with the hub to a single open channel substantially reduces server overhead.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08060568&OS=08060568&RS=08060568
owner: SAP Portal Israel Ltd.
number: 08060568
owner_city: Ra'Anana
owner_country: IL
publication_date: 20070529
---
This invention relates to computer network protocols. More particularly this invention relates to a real time messaging framework for use in a communications network.

Real Time Messaging Framework RTMF is an instant messaging system that is available from SAP AG Neurottstra e 16 69190 Waldorf Germany. This is an infrastructure for transferring messages between clients and servers in an application platform. Typically clients are connected to a RTMF server through a RTMF client running in a hidden frame in their portal browsers. In one aspect of RTMF every RTMF based client sends an automated request to a RTMF server every number of seconds to check if messages events requests or invitations have been sent to it. The time between each check is commonly referred to as the polling interval. The polling mechanism if not configured properly has the potential to generate load on the portal server as the number of users increases.

For security reasons data networks such as the Internet impose certain limitations on server client interactions. For example a server may not be able to initiate contact with a client unless the client first sends a request to the server. One method by which the client can be notified about a particular class of event that takes place on or is known to the server is to use a polling mechanism. At frequent intervals the client sends a message to the server asking if an event of the class has occurred. The server replies with a message indicating either that no event in the class has occurred or which contains details of the events that have occurred.

Real Time Messaging Framework RTMF provides a structure for the messages described above. It works over a HTTP HTTPS Hypertext Transfer Protocol Hypertext Transfer Protocol Secure environment. However the principles of this invention can also be applied to other similar connectivity environments.

A messaging framework such as that described above has many applications. For example it can be used for instant messaging. User messages are sent from one user to another user via a server where the user messages are stored. Each user polls the server for an event i.e. the arrival of a user message destined for that user. The polling reply contains the user message.

As the number of clients polling a server increases the load on the server increases and can become excessive. One method of reducing the load is to increase the polling interval. However as the polling interval increases the delay between the occurrence of an event and the notification to the client can become excessive to the point that the messaging system can no longer be considered real time .

According to disclosed embodiments of the invention a RTMF hub on one computing device replaces individual server notification channels of different clients on the same or different devices and combines them into one hub controlled channel. The hub services one or more clients polls the server on behalf of its clients and stores the events from the server relevant to its respective clients. The clients then transparently poll the hub in the same way that they would poll the server. This eliminates most of the polling messages that would conventionally be required. In consequence network traffic between the client and the server is greatly reduced.

In one aspect of the invention an abstraction of the notification channel is created which replaces the conventional channels used by the server to pass messages to clients and which passes messages transparently to the different clients that use the channel. In another aspect of the invention a platform controls message flow between the different clients and servers according to a particular logical schema such as business logic. For example the platform may block specific message categories when the message traffic load exceeds a predefined threshold.

An embodiment of the invention provides a computer implemented method of communication via a communications network which is carried out by executing a set of applications in a computing device wherein the applications exchange messages with a server. The server has a real time messaging facility operative for processing the messages registering the applications with a hub intercepting the messages in the hub and retransmitting the messages from the hub. The method is further carried out by communicating the messages between the hub and the registered applications via respective first channels and the messages are communicated between the hub and the real time messaging facility via only one second channel.

According to an aspect of the method the set of applications includes at least two different application types that are selected from the group consisting of instant messaging applications telephony applications and short messaging service applications.

One aspect of the method includes varying intercepting and retransmitting the messages according to a governing schema. The schema may comprise blocking predetermined categories of the messages when a traffic load exceeds a predetermined threshold.

One aspect of the method includes executing a graphical desktop interface in the computing device for coordination of the applications executing therein wherein the messages are communicated between the applications and the hub via the graphical desktop interface.

According to another aspect of the method the messages comprise polling requests from the applications to the server and polling replies from the server to the applications.

Yet another aspect of the method includes respectively associating a class of events with the registered applications wherein the polling requests comprise inquiries whether at least one event of the class has occurred.

According to a further aspect of the method the polling replies comprise a null polling reply that is sent when the at least one event has not occurred and an identification of the at least one event that is sent when the at least one event has occurred.

An embodiment of the invention provides a real time messaging framework hub including a communication interface for communicating messages with a server and a client and a processor which is configured to intercept messages that are exchanged between a set of applications that are registered with the hub and execute in the client and the server for service thereof using a real time messaging facility and to retransmit the messages. The messages are communicated between the hub and the registered applications via respective first channels and the messages are communicated between the hub and the real time messaging facility via only one second channel.

Other embodiments of the invention provide computer software product for carrying out the above described method.

One embodiment provides a computer software product for communication via a communications network including a tangible computer readable medium in which computer program instructions are stored which instructions when read by a computer cause the computer to intercept messages exchanged between a set of applications and a server for service thereof via a real time messaging facility executing in said server said applications executing in a client to register said applications with said server and to retransmit said messages wherein said messages are communicated between said computer and said registered applications via respective first channels and said messages are communicated between said computer and said real time messaging facility via only one second channel.

In the following description numerous specific details are set forth in order to provide a thorough understanding of the present invention. It will be apparent to one skilled in the art however that the present invention may be practiced without these specific details. In other instances well known circuits control logic and the details of computer program instructions for conventional algorithms and processes have not been shown in detail in order not to obscure the present invention unnecessarily.

Software programming code which embodies aspects of the present invention is typically maintained in permanent storage such as a non transitory tangible readable medium. In a client server environment such software programming code may be stored on a client or a server. The software programming code may be embodied on any of a variety of known media for use with a data processing system such as a diskette or hard drive or CD ROM. The code may be distributed on such media or may be distributed to users from the memory or storage of one computer system over a network of some type to other computer systems for use by users of such other systems.

Turning now to the drawings reference is initially made to which is a pictorial diagram of an exemplary data processing system in which the invention may be implemented. System comprises a general purpose computer which is provided with a memory for storage of executables and data. Memory is typically realized as a hard disk. Alternatively other known types of memory may be used alone or in combination with the hard disk as memory . Memory stores applications including RTMF clients for example one or more graphical desktop interfaces . Memory also stores a RTMF hub .

Computer is provided with a communication interface such as a network card which may use any known networking technique including wireless links optical networks etc. Communication interface is linked to a server via a data network and another communication interface .

Server is provided with a memory which can be of any of the forms described above for memory . Memory stores a RTMF server for example RTC Real Time Collaboration produced by SAP AG. Memory also stores a resource for example a web page.

Reference is now made to which is a pictorial diagram of a part of the data processing system of . RTMF hub provides a single point of connection for each RTMF client to server which includes RTMF server . RTMF clients shown in include in addition to one of the clients the graphical desktop interfaces and a web browser .

Reference is now made to which is a pictorial diagram of an alternative embodiment of a data processing system in which the invention may be implemented. System comprises any number of general purpose computers four are shown in similar to computers of system .

Any number of computers two are shown in are connected to computers via connection interfaces . Each computer is provided with a memory which can be of any of the forms described above for memory . Memory stores RTMF hub . Computer is sometimes referred to as a RTMF box.

Each computer is logically connected to one RTMF box . The connections between the communication devices of computers and RTMF boxes are shown in as direct connections in order to illustrate the logical connections more clearly. However the connections may actually be via network or via any other network similar to network .

Reference is now made to which is a detailed block diagram of RTMF hub in accordance with a disclosed embodiment of the invention. RTMF hub provides a RTMF connector . RTMF connector provides two Application Programming Interfaces APIs a COM API and a .NET API . COM API provides an interface for a JavaScript application . The .NET API provides an interface for .NET application . Graphical desktop interfaces may use .NET API or COM API .

In some embodiments RTMF connector interfaces to a RTMF proxy using HTTP HTTPS. In other embodiments communication between RTMF connector and RTMF proxy uses a named pipe. RTMF connector and RTMF proxy may be on the same computer as in the embodiment of or on different computers as in the embodiment of . RTMF proxy is described in further detail hereinbelow.

In some embodiments RTMF proxy communicates with a SIP module . SIP module handles Session Initiation Protocol SIP which is well known in the art.

Reference is now made to which is a detailed block diagram of RTMF proxy . A RTMF client exists in a separate thread and is in charge of a connection with RTMF server .

A data store holds a client list and an event list . Client list is a list of clients that are currently registered with the proxy. Event list is a list of events for which the clients in client list are currently registered. Data store also holds a list of new events received from RTMF server .

The data in data store is synchronized to ensure that one thread does not modify it while another thread is reading it. Methods for ensuring that data is synchronized between different threads are well known in the art and are not discussed further here.

A timer exists in a separate thread and is in charge of removing clients from client list if they stop polling RTMF proxy .

By way of example two RTMF clients referred to hereinbelow as RTMF client A and RTMF client B with the same user credentials wish to be notified about any changes to resource . RTMF client A may be on the same computer as RTMF client B as in or on a separate computer as in .

Reference is now made to which is a sequence diagram showing registration for RTMF events in accordance with a disclosed embodiment of the invention. At initial step RTMF client A sends a login request to RTMF hub . In some embodiments RTMF hub vets the login details. In other embodiments RTMF hub merely checks whether a login request for this user has already been sent. Referring again to details of RTMF client A are stored in client list .

At step RTMF client A sends a message to RTMF hub to register for a specific event i.e. changes to resource . Details of the event registered are stored in event list .

At step RTMF client passes the login request to RTMF server . In some embodiments this step takes place before step .

At step RTMF client B sends a login request to RTMF hub . RTMF hub observes that the user credentials for RTMF client B are already stored in client list . Therefore a second login request is not sent to RTMF server .

At step RTMF client B sends a message to RTMF hub to register for a specific event i.e. changes to resource . Since this event is already stored in event list RTMF client does not send a second message to register for the event to RTMF server .

Reference is now made to which is a message diagram showing polling for RTMF events in accordance with a disclosed embodiment of the invention. At initial step RTMF client A sends a polling message to RTMF hub inquiring if there have been any changes to resource since the last poll request or since RTMF client A registered for this event . RTMF client A sends polling messages periodically.

Next at step RTMF hub sends a null polling reply to RTMF client A indicating that there are no events.

At step RTMF hub sends a polling message to RTMF server inquiring if there have been any changes to resource since the last poll request or since RTMF hub registered for this event . RTMF hub sends these polling messages periodically at a rate that is typically unrelated to the rate at which RTMF clients poll RTMF hub .

At step RTMF client B sends a polling message to RTMF hub inquiring if there have been any changes to resource since the last poll request or since RTMF client B registered for this event . RTMF client B sends these polling messages periodically.

Next at step RTMF hub sends a null polling reply to RTMF client B indicating that there are no events.

At step RTMF hub sends a polling message to RTMF server inquiring if there have been any changes to resource since the last poll request. In the scenario shown in an event has occurred between steps and .

Next at step RTMF server sends a reply to RTMF hub . The reply is a RTMF message containing details of the event. The reply is received by RTMF client and stored in data store . If two or more events have occurred since the last polling request details of these requests are contained in the reply and they are all stored in data store .

At step RTMF client A sends a polling message to RTMF hub inquiring if there have been any changes to resource since the last poll request.

Next at step RTMF hub sends a reply containing the event from data store to RTMF client A. If there are two or more relevant events in data store they are sent to RTMF client A in a single reply.

At step RTMF client B sends a polling message to RTMF hub inquiring if there have been any changes to resource since the last poll request.

Reference is now made to which is a pictorial diagram illustrating the functionality of a typical graphical desktop interface which interacts with RTMF hub in accordance with a disclosed embodiment of the invention. A suitable graphical desktop interface in cooperation with RTMF hub brings together different aspects of daily work into one tool e.g. collaboration alerts work list and decision support. Graphical desktop interface enables a user to communicate with others using varied communication channels e.g. instant messaging telephony short messaging service SMS and provides a context relevant to business environment of the user.

Graphical desktop interface comprises a number of plug ins each of which performs one or more of the tasks described above.

It will be appreciated by persons skilled in the art that the present invention is not limited to what has been particularly shown and described hereinabove. Rather the scope of the present invention includes both combinations and sub combinations of the various features described hereinabove as well as variations and modifications thereof that are not in the prior art which would occur to persons skilled in the art upon reading the foregoing description.

