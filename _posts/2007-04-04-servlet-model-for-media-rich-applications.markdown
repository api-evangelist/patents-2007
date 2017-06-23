---

title: Servlet model for media rich applications
abstract: A media rich SIP servlet is enabled using a media control layer and a conventional SIP Servlet container. The media rich SIP servlet provides a media control API that can be used by SIP-based application developers to incorporate media rich functions into SIP-based applications. The media rich SIP servlet includes an advanced call control API, which enhances the basic call control functions provided by a SIP servlet. The media rich SIP servlet provides call and media control primitives for use by SIP servlet based applications, thereby enabling media rich SIP servlet based applications.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=07865607&OS=07865607&RS=07865607
owner: Movius Interactive Corporation
number: 07865607
owner_city: Duluth
owner_country: US
publication_date: 20070404
---
The present application claims the benefit of U.S. Provisional Patent Application No. 60 788 701 filed on Apr. 4 2006 which is herein incorporated by reference in its entirety.

The present invention relates generally to Session Initiation Protocol SIP based applications. More particularly the invention relates to a method system and computer program product for enabling media rich SIP based applications.

The Java 2 Enterprise Edition J2EE platform is an end to end architecture that provides a programming model that uses Servlets Java Server Pages JSPs and Enterprise JavaBeans EJBs to implement and deploy business logic.

An aspect of the J2EE platform is the use of containers to simplify the development of business logic with each container providing reusable components for use by application developers. For example the EJB container handles distributed communication threading and transaction management. Similarly Java Servlets simplify web development by providing infrastructure for component communication and session management in a web container integrated within a web server.

Session Initiation Protocol SIP is a signaling protocol for multimedia applications such as IP telephony applications instant messaging and online games for example. Based on simple signaling SIP enables rapid establishment of sessions over IP Internet Protocol .

To support SIP in a J2EE platform Java Specification Request JSR 116 a Sun JCP Java Community Process standard defines a Session Initiation Protocol SIP Servlet Application Programming Interface API to simplify the task of building SIP based applications. The SIP Servlet API together with a SIP protocol stack provides a SIP Servlet container based on which SIP based applications can be developed in a J2EE platform.

A SIP Servlet container is integrated onto a J2EE platform in a similar way to an EJB container or a Web container and provides basic functions enabling the development of user agents proxies and registrars for SIP based applications. These basic functions allow a SIP based application developer for example to create SIP sessions in a J2EE architecture. However they are limited to SIP based call control.

Many SIP based applications such as telephony for example require SIP based call control and media control functionality. Other SIP based applications require advanced call control functions that cannot be afforded by the basic functions available through the basic SIP Servlet container. Thus an improved SIP Servlet model is needed.

An improved SIP servlet model enabling fast and easy development of complex media rich SIP based applications is needed.

A media rich servlet for enabling media rich SIP based applications is disclosed herein. The media rich SIP servlet is enabled using a media control layer and a conventional SIP Servlet container. The media rich SIP servlet provides a media control API that can be used by SIP based application developers to easily incorporate media rich functions into SIP based applications. In addition the media rich SIP servlet includes an advanced call control API which enhances the basic call control functions provided by a SIP Servlet. Accordingly the media rich SIP servlet provides call and media control primitives for use by SIP servlet based applications thereby enabling media rich SIP servlet based applications.

Further embodiments features and advantages of the present invention as well as the structure and operation of the various embodiments of the present invention are described in detail below with reference to the accompanying drawings.

Embodiments of the present invention will be described with reference to the accompanying drawings. The drawing in which an element first appears is typically indicated by the leftmost digit s in the corresponding reference number.

The Java 2 Enterprise Edition J2EE platform is an end to end architecture that provides a programming model that uses Servlets Java Server Pages JSPs and Enterprise JavaBeans EJBs to implement and deploy business logic. One aspect of the J2EE platform is the use of containers to simplify the development of business logic with each container providing reusable components for use by application developers.

Database is responsible for the actual storage of data used by J2EE Server containers. In practice database may include a database logic layer and a database manager layer with the database manager layer generating physical storage facilities of the data on the basis of a database logic typically written in SQL stored in the database logic layer.

Due in part to its simplicity the Session Initiation Protocol SIP is a popular protocol currently proposed for establishing multimedia sessions. SIP is a signaling protocol that provides functionality for handling the setup modification and teardown of multimedia sessions. is a diagram that illustrates a typical SIP call process between two SIP users and . Call process begins with SIP user the calling party sending a SIP INVITE message to SIP user the called party. The SIP INVITE message invites SIP user to participate in a session with SIP user . A number of interim responses to the INVITE message might take place prior to the called party accepting the call. For example the caller might be informed that the call is queued and or that the called party is being alerted to the INVITE request Ringing tone . Subsequently SIP user accepts the call which generates an OK response back to the caller SIP user . The calling party SIP user acknowledges that the called party SIP user has answered by issuing an ACK message. At this point a conversation including media e.g voice video etc. can be exchanged between the two SIP users. Finally when one of the parties hangs up SIP user in a BYE message is sent to the other party. The other party SIP user in confirms its receipt of the BYE message by issuing an OK message thereby ending the session.

To incorporate SIP in a J2EE architecture Java Specification Request JSR 116 a Sun JCP standard defines a Session Initiation Protocol SIP Servlet API to simplify the task of building SIP based applications. In an exemplary embodiment the SIP Servlet API together with a SIP protocol stack provides a SIP Servlet container which can be integrated in a J2EE platform similar to a Web container or an EJB container for example.

Conventionally functions provided by a SIP Servlet container for use by SIP based application developers remain limited to basic call control functions related to session establishment modification and teardown. JSR 116 for example is silent on integrating media control as well as advanced call control using a SIP Servlet container functions required by a multitude of SIP based applications.

Embodiments of the present invention extend the current SIP Servlet container to provide media control and advanced call control functionality to SIP based application developers thereby enabling fast and easy development of media rich SIP based applications. The following description presents exemplary embodiments of a media rich servlet model for achieving this objective.

Media control layer includes a media resource stack an Automatic Speech Recognition ASR and Text to Speech TTS resource stack and a conference resource stack . Media resource stack is configured to control Interactive Voice Response IVR functions. ASR TTS resource stack is configured to control Automatic Speech Recognition and Text to Speech functions and conference resource stack is configured to control conference functions. In an embodiment media control layer communicates with media server using a MGCP Media Gateway Control Protocol interface.

Using functionality provided by its resource stacks media control layer provides media control functions that together with a conventional SIP Servlet container enable a media rich SIP servlet . Media rich SIP servlet not only includes a basic call control API as provided by a conventional SIP Servlet but also provides a media control API that can be used by SIP based application developers to easily incorporate media rich functions into SIP based applications. In addition media rich SIP servlet may include an advanced call control API which enhances the basic call control functions provided by a SIP Servlet. Accordingly media rich SIP servlet provides call and media control primitives for use by a SIP servlet based application thereby enabling media rich SIP servlet based application . In an embodiment the media control API and the advanced call control API may be integrated in a single API which is used by SIP servlet based applications. In another embodiment the media control API and the advanced call control API may be separate.

The media control API and the advanced call control API provided by media rich SIP servlet are protocol and device independent. In other words media and advanced call control functionality provided by the APIs are independent of the type of signaling protocol employed to establish the multimedia session. For example referring to SIP servlet container may be replaced by a different signaling protocol container e.g. H323 container to generate a media rich servlet for that signaling protocol e.g media rich H323 Servlet .

The media control API and the advanced call control API further are independent of the type of device running the SIP based application that employs the APIs. For example SIP based applications may be web based or telephony based and yet access the same media control and advanced call control APIs.

Architecture may be used by Value added System Integrators Developers Resellers and Independent Software Vendors ISVs .

In an exemplary embodiment architecture allows the integration of media rich application packages and services enabled by Service Enablers SEs to support the above described applications. For example architecture allows the integration of media rich application packages with Presence and Availability Management services Contact Management services External Database and Directories services third party content services and other web services.

In the exemplary embodiment illustrated in the media rich application packages may be developed using a Software Creation Environment SCE and or an Integrated Development Environment IDE that make use of the media rich SIP servlet and a J2EE server.

Exemplary embodiments for implementing the media rich servlet model described above will now be provided. These examples are provided for illustration purposes only and are not limiting.

Media control servlet is derived from a SIP servlet . Accordingly media control servlet intercepts all of SIP Servlet lower level call backs processes the SIP Servlet lower level calls backs and provides higher level call backs to application media control servlet which is derived from media control servlet . In an embodiment media control servlet provides a set of call back functions to application media control servlet to hide the details of SIP and IVR related call control including processPlayCollectEvent processPlayAnnouncementEvent and processCallOffering . Note that application media control servlet does not implement any SIP Servlet call backs such as doInvite or doAck for example because Media Control Servlet intercepts these methods as will be shown in the sequence diagram of .

Calls to application media control servlet include a Media Control Request object . For example to play announcements or other IVR functionalities application media control servlet sets appropriate parameters into Media Control Request object through proper API. In an embodiment the API includes several functions to set IVR parameters including setPlayCollect setAnnouncement and send . The send function sends the media request to IVR Resource Control which negotiates the media request with the media server. IVR Resource Control can be implemented over MGCP or SIP stack.

In step SIP stack relays the SIP INVITE to media control servlet using call function doInvite . In response media control servlet in step creates a media control request object and in step passes the created media request object as an argument in call function processCallOffering to application media control servlet .

In step application media control servlet sets the requested media resource in media control request . For example the media resource may be an IVR resource or a conference resource. An IVR resource provides IVR functionalities. A conference resource provides stream mixing functionalities along with IVR functionalities. In example process the requested resource is an IVR resource. As such in step media control servlet requests that IVR resource control creates a media control session.

IVR resource control uses either MGCP BAU Base Audio Server or MSML Media Server Markup Language SIP or any other suitable IVR protocol package to negotiate with media server to reserve an IVR resource. In the case of MGCP as illustrated in example process in steps and IVR resource control sends a CRCX message to media server to reserve the IVR resource to which media server responds with a 200 OK message to confirm the reservation. IVR resource control subsequently in step returns the created media control session object to media control servlet . In an embodiment IVR resource control passes the media control session object as an argument in the call function processResourceAcquired .

In step media control servlet stores the media control session object in SIP application session using the setAttribute function provided by the SIP application session. Subsequently in steps and media control servlet sends a SIP 200 OK message to call agent in response to the received SIP INVITE and receives an ACK message back through SIP stack . In an embodiment step is performed using the doAck function called by SIP stack which invokes in step the processCallConnected call back application media control servlet .

In subsequent steps and application media control servlet starts the IVR call by invoking the setPlayCollect function of media control request object and the send function to execute it. This triggers IVR resource control to send in step a notification request RQNT to media server which responds with a notify NTFY in step . This sets up media server to notify IVR Resource Control of certain events.

Once IVR resource control receives the NTFY from media server it updates the media control session in step and passes it in step to media control servlet as an argument in call back function processPlayCollectEvent . Media control servlet in step invokes the processPlayCollectEvent call back function of application media control servlet which plays a prompt and collects DTMF digits entered by a user.

In step SIP servlet invokes a createMediaResource function call at media control servlet factory which in turn in step invokes a createMediaSession function call at IVR resource control . IVR resource control creates a media control session and then as in process negotiates with media server to reserve the requested resource. Once that is achieved in step IVR resource control directly stores created media control session in SIP application session as opposed to performing that through media control servlet in process .

Subsequently IVR resource control creates a media control request and in step passes it to media control servlet using a processResourceAcquiredEvent function call. Media control servlet in steps and directly sets and executes IVR parameters in media control request object . Note that in process media control servlet performs similar steps through application media control servlet . In the example of media control servlet invokes a setAnnouncement function which is used to play announcements in situations where there is no need for interaction with the user. IVR resource control processes this function in step by invoking a processPlayAnnouncementEvent function at media control servlet .

In an embodiment of the present invention the system and components of the present invention described herein may be implemented using well known computers as computer schematically illustrated in .

Computer can be any commercially available or later developed computer capable of performing the functions described herein well known examples of such computers are available from International Business Machines Apple Sun HP Dell Compaq Digital Cray etc.

Computer may include one or more processors also called central processing units or CPUs for performing the functions. For simplicity illustrates only a single processor those skilled in the art readily will appreciate that plural processors may be utilized to perform the functions described herein. Processor may be connected to a communication bus .

Computer also may include a main or primary memory such as random access memory RAM . Primary memory may have stored therein control logic A computer software and data.

Computer also may include one or more secondary storage devices . Secondary storage devices may include for example a hard disk drive and or a removable storage device or drive as well as other types of storage devices such as memory cards and memory sticks. Removable storage drive may represent a floppy disk drive a magnetic tape drive a compact disk drive an optical storage device tape backup etc.

Removable storage drive may interact with a removable storage unit . Removable storage unit may include a computer useable or readable storage medium A having stored therein computer software B control logic and or data. Removable storage unit may represent a floppy disk magnetic tape compact disk DVD optical storage disk or any other computer data storage device. Removable storage drive may read from and or writes to removable storage unit in a well known manner.

Computer also may include input output display devices such as monitors keyboards pointing devices etc.

Computer further may include a communication or network interface . Network interface may enable computer to communicate with remote devices. For example network interface may allow computer to communicate over communication networks or mediums B representing a form of a computer useable or readable medium such as LANs WANs the Internet etc. Network interface may interface with remote sites or networks via wired or wireless connections.

Control logic C may be transmitted to and from computer via communication medium B. More particularly computer may receive and transmit carrier waves electromagnetic signals modulated with control logic via communication medium B.

As used herein computer program product or program storage device refers to any apparatus or manufacture comprising a computer useable or readable medium having control logic software stored therein. In the exemplary embodiment illustrated in this includes but is not limited to computer main memory secondary storage devices removable storage unit and carrier waves modulated with control logic . Such computer program products having control logic stored therein that when executed by one or more data processing devices cause such data processing devices to operate as described herein and represent embodiments of the invention.

The invention can work with software hardware and or operating system implementations other than those described herein. Any software hardware and operating system implementations suitable for performing the functions described herein can be used.

While various embodiments of the present invention have been described above it should be understood that they have been presented by way of example only and not limitation. It will be apparent to persons skilled in the relevant art that various changes in form and detail can be made therein without departing from the spirit and scope of the invention. Thus the breadth and scope of the present invention should not be limited by any of the above described exemplary embodiments but should be defined only in accordance with the following claims and their equivalents.

