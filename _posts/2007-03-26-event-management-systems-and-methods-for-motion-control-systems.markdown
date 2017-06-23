---

title: Event management systems and methods for motion control systems
abstract: A motion control system comprising a machine platform, at least one event destination, and an event handler. The machine platform carries out automated tasks and generates events. The event handler is configurable to receive at least one event from the machine platform and send the at least one event to the at least one event destination.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=07904194&OS=07904194&RS=07904194
owner: Roy-G-Biv Corporation
number: 07904194
owner_city: Bingen
owner_country: US
publication_date: 20070326
---
This application is a continuation of U.S. patent application Ser. No. 11 368 231 filed on Mar. 3 2006 now abandoned which claims priority of U.S. Provisional Application Ser. No. 60 658 746 filed on Mar. 3 2005 and the 231 application is a continuation in part of U.S. patent application Ser. No. 10 074 577 filed on Feb. 11 2002 now U.S. Pat. No. 7 031 798 and which claims priority of U.S. Provisional Application Ser. No. 60 267 645 filed on Feb. 9 2001. The contents of all related applications listed above are incorporated herein by reference.

The present invention relates to motion control systems and more specifically to an event management system optimized for the processing and distribution of events associated with a motion control device.

Electromechanical systems are used in numerous environments to translate electrical signals into mechanical movement. As examples factory automation systems toys appliances and the like all may use one or more electromechanical transducers that move in response to electrical control signals.

Typically an application programmer familiar with a specific environment creates an application program defining a desired sequence of movements. U.S. Pat. Nos. 5 691 897 5 867 385 and 6 209 037 to Brown et al. disclose systems and methods for generating processing and or distributing control commands to one or more motion control devices based on such an application program.

The present invention may be embodied as a part of an overall motion control system as described in the Brown et al. patents and will be described herein in that context. However as described below the principles of the present invention may have broader application to other motion control systems and methods and the scope of the present invention should be determined by the claims appended hereto and not the following detailed description.

The present invention may be embodied as a motion control system comprising a machine platform at least one event destination and an event handler. The machine platform carries out automated tasks and generates events. The event handler is configurable to receive at least one event from the machine platform and send the at least one event to the at least one event destination.

Referring initially to depicted therein is a motion control system constructed in accordance with and embodying the principles of the present invention. The motion control system is an event based system used to control configure and query one or more motion based devices or machines such as indicated by reference character in the drawing. The motion based devices or machines will be referred to herein as the target device.

In the context of the motion control systems described herein data is often associated with events. The term data or data items includes any numeric or string data values collected from a target machine or device in an analog or digital format that is made compatible for computer systems. For example BIT BYTE WORD DWORD LONG REAL DOUBLE FLOAT STRING ASCII STRING are a few data types that represent data items. Data may be collected from data sources by reading register values on the data source reading shared memory provided by the data source sending commands to the data source for which a data response is given containing the data requested reading variables provided by the data source reading and writing to variables in a sequence necessary to produce data values querying data using a proprietary or standard data protocol calling a function provided by the target data source etc. The term variable as used herein refers to a data item that has both a name and optionally associated data. A data item may be a function call a named data variable a tag within a database or the like. The terms variable and data item are used interchangeably to refer to a data point that includes one or more atomic data elements.

In the following discussion the components or objects that form the motion control system and the basic operation of the system will first be described. After that will follow a discussion of the interaction between those objects and several detailed scenarios of typical actions of this system .

Referring initially to of the drawing it can be seen that the motion control system comprises the motion based machine or device a motion event manager one or more motion event provider objects a motion event interface a motion web site and a media creation tool .

The system is adapted to be run on a general purpose computer platform comprising computer hardware and an operating system . The exemplary operating system is a Windows variant and comprises a registry .

The web site and media creation tool provide access to one or more motion media files . The motion media files contain what will be referred to herein as motion media.

The term motion media includes motion scripts motion application programs and or individual motion instructions capable of causing the target device to perform a desired motion operation comprising a discrete movement or sequence of movements.

The motion media comprises what will be referred to as motion commands. The term motion commands will be used herein to refer to both control commands and media commands associated with a desired motion operation. The term control commands as used herein refers to device specific commands that may be directly run by a target device to obtain a desired motion operation.

The term media commands used herein refers to machine independent instructions that generically define a desired motion operation. Normally media commands are converted into control commands before the target device executes the desired motion operation corresponding to a particular media command or set of media commands.

The term application program will be used to refer to a set of control and or media commands associated with a sequence of discrete movements. In general the term application refers to client software that uses the functionality of the example motion control systems described herein. An application is typically an executable but may also be a DLL component or other module that takes advantage of the functionality of the motion control systems described herein.

The term module as used herein refers to a binary block of computer logic that contains functions objects components ActiveX components .NET source HTML XML and or other computer code that can be executed in real time or in script form. Several examples of a module include an executable EXE a dynamic link library DLL an OLE component or set of components housed within a DLL or EXE an ActiveX Control an HTML or XML based Control a VB script source file a Java Serverlet Java Control Java Object .NET Package etc.

The motion event manager comprises a motion control component and an event handling component . The motion event interface further comprises a event provider configuration control and a media view control . As used herein the term component refers to a logical organization of computer logic designed to perform a set of operations. Several examples of a component are an OLE Component an ActiveX Control an HTML or XML based Control an HTML or XML based object a NET object a Visual Basic based object etc.

The motion control system operates basically as follows. The motion event providers generate what will be referred to as event tokens based on the occurrence of a predetermined event. The event token is associated with the predetermined event in advance and thus identifies the predetermined event. The event token may also contain additional information such as the source of the predetermined event parameters associated with the predetermined event and the like.

The event tokens are sent to the motion event manager . The motion event providers and motion event manager run in separate processes and could perhaps run on separate physical machines connected over a network. As used herein the term network refers to a link between two or more computer systems and may be in the form of a packet based network a streaming based network broadcast based network or peer to peer based network. Several network examples include a TCP IP network the Internet an Intranet a wireless network using WiFi a wireless network using radio waves and or other light based signals etc.

The motion event providers and motion event manager thus use the system for the inter process communication provided by the operating system to transmit the event tokens from the event providers to the motion event manager .

The motion event manager notifies the motion control component when the event token is received and the identity of the event token. The action taken by the motion control component upon receipt of an event token depends upon the nature of the event token. The received event token may contain or identify a particular control command and the motion control component can simply pass that control command to the target device . The received event token may contain or identify a particular media command in which case the motion control component may be required to convert the media command into a control command capable of being run by the target device . Another event token may start stop or otherwise control a separate application program run by the motion control component .

In the exemplary system the association of motion media with event tokens is preferably made by the motion event manager . This association is typically represented by a table spreadsheet or other data storage means capable of defining relationships between event tokens and motion media. Upon receipt of each event token the motion event manager will identify the motion media previously associated with the received token and send the identified motion media to the motion control component for control of the target device .

With the foregoing understanding of the basic operation of the system the details of this exemplary motion control system will now be described.

The motion event manager handles the creation of each event provider installed on the system by creating in proc providers or injecting other providers into their target processes. The event manager also catches events fired from each provider and initiates the appropriate motion request for each event. In the exemplary system the event manager is the only object that communicates directly with the motion control component as will be described in further detail below. The exemplary event manager is accessible by double clicking its icon in the Windows System Tray in a conventional manner.

The purpose of the event handling component is to handle the inter process communications between the motion event manager and the motion event providers . The exemplary event handling component is or may be a conventional software object referred to as a message pump.

The motion event provider objects are individually designed to monitor user configurable events from a given source. The exemplary system employs two types of motion event providers simple in proc servers hosted by the motion event manager and specialty DLLs that are injected into a target process to monitor event cases. Each motion event provider object also contains an event configuration control that as will be described below allows a user to configure all events supported by the motion event provider objects . The motion event provider objects notify the motion event manager of each event caught by the objects .

The motion event manager and motion control component operate together to allow interaction between the motion event providers and the target device .

The motion control component may be or incorporate parts of a software system as disclosed for example in U.S. Pat. Nos. 5 691 897 and 5 867 385. The systems disclosed in the 897 and 385 patents are capable of generating device specific control commands based on hardware independent media commands written to a predetermined application programming interface.

As an alternative the motion control component may act as a conduit that passes device specific control commands and query responses between the motion event providers and the target device . A motion control component implemented in this manner would not convert between hardware independent media commands and device specific control commands.

A preferred implementation of the motion control component would be to be for the component to function in both a translation mode and in a pass through mode. In the translation mode the component converts media commands into control commands. In the pass through mode the component simply passes control commands from the motion event providers to the target devices . In either mode query responses are returned from the target devices to the event provider in an appropriate format.

The motion event configuration interface is preferably a visual interface displayed on a screen to allow a user to configure all motion event providers installed on the system . The exemplary interface also provides access to the motion web site where new motion media and motion event providers may be downloaded and installed.

As will be described in more detail below the configuration options allowed by the interface include the ability to enable disable event providers and map motion media to particular events supported by each provider . The interface also provides access to the motion web site allowing for new motion media and motion event providers to be downloaded and installed onto the current system.

Each motion event provider contains a visual configuration control that allows the user to configure the events supported by each provider . The exemplary configuration controls use the media view control object to gain access to the available motion media in the motion media file that can be mapped to each available event.

These controls may also be configured to allow the user to add new customized events to the motion event providers . The dynamic events can be defined using parameters such as text usernames messages email etc. date time or any other parameter particular to an event provider s event source.

The media view control object provides access to all installed motion media scripts as represented by the motion media file . Preferably the media view control object displays a conventional browse select dialog to allow identification and selection of the available motion media. This object is used by the event provider configuration controls and allows the configuration controls to remain independent of the motion media format.

The media creation tool application allows the user to customize and or create motion media. This application preferably implements a graphical easier to use front end user interface design.

The motion web site provides a location for the user to download new motion media as well as new and or updated motion event providers . The motion media is preferably stored in a single meta file. New motion media downloaded from the motion web site will be added to this meta file.

The present invention is preferably embodied using the Windows registry typically a component category is created for each of the motion event providers allowing the motion event manager to enumerate all providers installed on the system. Primary event sources are user actions in any active application supported via a motion event provider and operating system tasks.

With the foregoing understanding of the modules that form the exemplary system various scenarios in which these modules typically interact will now be described.

Referring now to depicted therein is the scenario describing the startup process of the motion event manager of the system . Each of the steps of this startup process will now be described with reference to .

The motion event manager process begins on system startup. The motion event manager process next queries the MOTION EVENT PROVIDER component category in the Windows Registry to enumerate all motion event providers installed on the system.

Third the registry entry of each of the event providers contains startup information indicating if the particular event provider is either a standard in proc provider or a specialty provider that is injected into a target process to monitor event conditions.

Fourth the motion event manger creates a new instance of each provider . If the event provider is a specialty provider that is injected into a target application process the event manger will read the target process information from the provider s registry entry find the target process and perform the DLL injection. If the target process is not active the motion event manager will continually monitor the creation of new applications and perform the injection when if the requested application is launched.

Fifth once the event providers are created the motion event manager will send the appropriate initialization information to each provider including callback information to allow the event providers to post event messages back to the event manager .

Finally the event provider reads initialize message data and establish the necessary event syncs to monitor the events. The initialize message data includes a registry key identifying the location of the event configurations and preferences as last set by the motion event configuration interface or the default installed set.

Referring now to depicted therein is the DLL injection scenario map. This scenario describes the process of injecting a motion event provider DLL into the address space of a target application.

As shown in the first step of this process is for the motion event manager to determine which process into which the motion event provider must be injected based on the registry entry of the provider .

Once the target process has been identified the next step is for the event manager to install a Windows message hook in the target process. This causes the event provider DLL to be loaded into the target address space of the target process. The event provider DLL has now been loaded into the required process and will now wait for the initialize message from the motion event provider .

Referring now to depicted therein is the motion event configuration scenario map. This scenario map describes the process of configuring motion events of each of the motion event providers .

First the user launches the motion event configuration interface from system tray interface of the motion event manager .

Each event provider object supports a custom visual control that can be used to edit the object s supported events. The event configuration interface creates and hosts these visual controls for the user.

Next when the event provider configuration control is created and initialized it will receive the location in the Windows Registry of its persisted event data which will be loaded into the control .

Next the user will select an event provider to configure. Individual events may be mapped to motion actions and particular events as well as the entire event provider itself may be deactivated if desired. As noted above these event configuration controls may also provide the means to add additional customized events based on input user parameters custom text strings buddy chat names email messages etc .

When the user selects an event to configure the event provider configuration control will defer to the media view control object . The media view control object displays all available motion media via a dialog box allowing the user to make a selection.

Finally once the user makes a motion media selection the media view control object returns data back to the event provider configuration control object including human readable description text of the event for display as well as a data token which can later be used to identify media selection . The configuration control object then persists this information to the Windows Registry .

Referring now to depicted therein is a motion event scenario map. This scenario describes the process of handling a motion event.

The scenario depicted in begins whenever an event occurs. The occurrence of an event may be caused from a user action operating system event or an event situation monitored in a third party application.

The event provider then fires a event token associated with this event to the event manager . The event token has previously been stored in the registry during the event configuration process. If the provider requires queried data to be returned the provider will also pass the necessary callback data to the event manager .

The event manager next receives the event and passes the requested media information to the motion control component . The motion control component then executes the specified motion media on the target motion device .

Finally if a query action was requested the motion control component will return the appropriate data. The motion event manger will send the data through the specified event provider callback mechanism.

Depicted in is a motion web site scenario map. The scenario of describes how a user may obtain new motion media and motion event providers from the motion web site .

This process may be started when users visit the motion web site to browse currently available motion event providers and new motion media. In the reference character is used to represent a motion media file stored locally by the system while the reference character represents a motion media file stored at a remote location.

Next the user selects the desired provider media download option and the new software is installed into the motion event manager including the motion control component .

The next time the motion event configuration interface is launched the user will be able to configure the new event provider or motion media in the local motion media file

Alternatively users may download new event providers and motion media directly from within the motion event Configuration dialog interface. This configuration dialog will provide the following options to the user Download new Motion Media and or Download install new motion event providers . The user or the motion event manager may also check for new versions of currently installed motion media and or event providers .

Next the user selects the desired provide media download or update option and the configuration dialog interface object automatically downloads and installs the new software from the media web site .

Finally once the new software is installed the configuration dialog will automatically update to provide access to the new components and or media.

Referring now to depicted therein is the system shutdown scenario map. This scenario describes the process of shutting down the exemplary event manager module associated with the motion control component .

The event manager next posts a shutdown message to each event provider currently being managed by the manager . Specialty event providers that have been injected into external processes may have already finished if the target process has been shutdown. In this case those event providers would have already notified the event manager that they are no longer available.

Upon finishing any shutdown tasks each provider will notify the event manager that the provider is now finished.

Once the event manager receives notifications that each of the event providers managed thereby have been shutdown the event manager itself is now finished.

Referring now to depicted therein is a scenario map illustrating the mapping of text to motion events. This scenario generally describes the mapping of text based event situations to motion.

The first step of this process is for a text based event situation to occur. This text could be one or more of the following a a particular sub string in an Instant Message or the entire message string itself b an Instant Message sent from a target screen or buddy name c a text string converted from a speech to text engine installed on the user s machine and or d an email message meeting previously configured criteria Sent From Subject message content etc . In the case of an event created using a peer to peer networked application such as Instant Messenger type process text is entered at a remote source application and sent as a text message to a receiving application.

The motion event provider monitoring the specific text based event catches the event and performs any pre processing of the text required to identify the particular event. In the peer to peer application described above a DLL functioning as the event provider is injected into the receiving application the DLL event provider intercepts the message received by the receiving application and treats the received message as an event.

Once an event has been identified the event provider will lookup the corresponding motion event token as previously configured. As generally described above the motion event tokens are pre loaded upon initialization. In the peer to peer example described above the DLL functioning as the event provider sends the text message as part of the event token to the event manager using a process to process communication system as generally described above.

After the event token containing the text message is sent to the motion event manager the event manager determines the type of event represented by the received token.

If the event manager determines that the received event token corresponds to a text event the event manager next parses the text parameter from the event token. The motion event manager looks up the motion media associated with the event type and event text parameter. The appropriate motion media is then sent to the motion control component for execution on the target motion device as described above with reference to .

The process described above with reference to can also occur in the reverse. In particular the event manager uses the motion control component to continually query the target device for state information. When the state information meets certain parameters the control component causes the event manager to create a new event such as a text event and send it to an event provider .

The event provider in turn then causes the receiving application to sent a message to a remote peer to peer application again the receiving and remote peer to peer applications may be Instant Messenger compatible applications.

An example of the use of the present system to verify motion status would be for the event manager to continually or periodically query the target device through the motion control component for status parameters that indicate a fault condition. Once a fault condition occurs the event manager builds a text message that describes the fault and then sends the text message to a remote application such as an Instant Messenger user using process to process communication system and the peer to peer networked application.

The following Table A describes the interface specifications for components of the exemplary motion control system described above using the exemplary motion control component .

In the following discussion the details of a number of the exemplary components of the system will now be described.

Data associated with the motion event providers is persisted to the Windows Registry primarily to accommodate event provider DLLs that need to be injected into a target process an environment where those DLLs may not be able to rely on standard COM storage alternatives.

At runtime when the motion event manager initializes an event provider the provider will receive a location in the registry where it should read its previously configured event data.

At design time when hosted within the motion event configuration interface the event configuration controls of the event providers receive the registry location and will persist configuration changes to that location.

Event providers will persist both standard hard coded and custom events to their registry storage location. Associated with each event will be the configured motion event token data which the provider will use when firing event notifications back to the motion event manager .

The event manager provides a mechanism to support different event schemes. This allows configurations unique for several different users situations or motion devices. When a new scheme is selected via the motion event configuration interface the event manager will pass the new scheme registry location to each event provider object allowing access to the new scheme data. Each scheme will be located in a unique sub key under the primary event manager registry location.

The user interface components and of the system may be implemented in many different forms. The motion event configuration control is used to configure all motion event providers installed on the system as well as to provide access to the motion web site where new motion media and motion providers may be downloaded and installed. The interface of the media creation tool is a preferably graphical representation of the motion device or system where simple drag drop click and record operations will facilitate the creating and modification of motion media.

The system is designed to be easily extendible via new motion event provider and motion media components. The system is also capable of supporting any number of additional event sources with the addition of new motion event providers by registering these new providers with the system . These event providers can link to virtually any event source to a target system .

The motion media formats can be modified and extended without requiring changes to any event provider objects. For example a XMCMediaCtrl object proxies the raw motion media format to the event providers. Accordingly once the XMCMediaCtrl component is updated to handle any new media formats the event providers may by design make use of the changes.

Instead of triggering entire motion programs as described above with reference to a motion program or media set may be streamed to the device through the system . Whether or not and how the media plays may be controlled by captured events. For example a media player may fire events based on different musical notes or tones. When such events are received one media stream may be selected over another thus causing the motion device to perform different actions. This may also occur with the standard motion programs described above.

Very large motion programs may be downloaded in partial form and then either downloaded in full over time or as certain specified events occur in the system.

Similar to streaming media support single motion operations may also be supported in which a specified event causes a single motion operation to take place immediately. One example of this would be an event that causes movement of one axis in the clockwise direction.

Referring now to depicted therein is a second example of a motion control system constructed in accordance with and embodying the principles of the present invention. The motion control system comprises a machine platform and an event notification system .

The machine platform may be implemented using a controller neutral platform technology as described for example in U.S. Pat. Nos. 5 691 897 5 867 385 6 209 037 6 480 896 6 513 058 6 516 236 6 542 925 and or 6 571 141 which are incorporated herein by reference. However the machine platform is or may be any motion control system whether controller dependent or controller neutral that comprises a machine converts motion commands into movement of an object.

In the context of the present application the term controller refers to the hardware or software that contains the logic used to run the machine. Typically the controller one or more of a PLC CNC Controller or Motion Controller. The controller contains the main control loop used to position monitor or otherwise direct a machine to carry out useful automated tasks.

The term machine is used herein to refer to a physical machine or device asset used to perform a specified task. For example a machine may be a CNC Mill used to shape metal a pick n place machine used to position parts on a circuit board a robotic machine used to perform surgery a medical data input device used to collect the vitals from a human being i.e. blood glucose meter asthma meter etc a gaming device used when playing a game a robotic toy an animatronics figure a robotic machine used to deliver goods to a warehouse or to people an automobile truck or farm vehicle a boat or ship that maneuvers in water a airplane jet helicopter and or spacecraft. Any self powered machine or device mobile or not that is either directly controlled by humans or automatically controlled via a computer based system falls within the definition of machine as used herein. The term device as used herein is essentially synonymous with the term machine but may be used in reference to a machine with a relatively small footprint.

The example event notification system comprises a main event handler one or more event handler applications and one or more event handler property pages . The example main event handler comprises a data queue .

The main event handler is a component that is in communication with the machine platform such that the main event handler receives one or more events from the machine platform . The example data queue within the main event handler is a standard data queue that employs first in last out technology. Optionally the data queue may be implemented as a priority queue that allows the items in the queue to be organized based on given priorities associated with the data contents of each item in the queue. The data queue may optionally use a timing scheme that ensures that all items within the queue are processed within a given time frame such that no items within the queue are starved out when a high frequency of higher priority items are received.

The event handler application is used to configure and run the main event handler . The example event handler application is a Windows System Tray application. The event handler application is optional and the main event handler may be run and configured using other systems and methods. The event handler property page is used to configure the settings of the main event handler by presenting a user interface that allows the user to see the settings of the main event handler and or to change these settings.

The main event handler is also in communication with one or more possible event destinations such as an upstream event handler and or a downstream event handler .

The example upstream event handler is a module similar to the main event handler that serves data to the main event handler . The example downstream event handler is also a module similar to the main event handler but one that receives data from the main event handler . From the perspective of the upstream event handler the main event handler is a downstream event client. From the perspective of the downstream event handler the main event handler is an upstream event client.

The main event handler may also be in communication with one or more event destinations through an intermediate destination such as a shared memory system a memory queue and or a network protocol . The shared memory system is a block of memory that is accessible to different modules and or applications. The example memory queue uses Microsoft Message Queue MSMQ technology or a similar technology. MSMQ allows for communication with other modules and or applications using a delayed messaging technology called Message Queuing. The example network protocol is formed using TCP IP or UDP broadcast protocols as a mechanism of sending output data to another target. The TCP IP protocol specifies specific data target s and the UDP protocol broadcasts data to all nodes on a given network.

The main event handler delegates one or more events received from the machine platform to one or more event destinations such as the upstream event handler and or the downstream event handler . In addition or instead the main event handler may delegate one or more events received from the machine platform to additional event destinations using one or more of the intermediate destinations such as the shared memory system the memory queue and or the network protocol .

The main event handler may further be in communication with an alternate event source such as a data transport system . The data transport system may be implemented using the data router technology described in co pending U.S. patent application Ser. No. 10 844 025 which is incorporated herein by reference. The data transport system routes data outputs to various output sources one of which may be the main event handler .

If the motion control system employs the data transport system the main event handler may also be configured to delegate events from the data transport system to the event destinations such as the upstream client and or the downstream event handler and or to intermediate destinations such as the shared memory system the memory queue and or the network protocol .

The event notification system may use an event handler such as the main event handler which is internally configured to handle communications with the event destinations and or intermediate destinations as shown in . Alternatively the motion control system may use an event notification system having a modular main event handler as depicted in . The modular event handler is a more modular design where each output is modularized thus giving the event handler the capability to select from a list of destination modules either programmatically or through a user interface.

In particular the example modular main event handler further comprises at least one event communication component configured to handle the details of communicating with one or more of the event destinations and intermediate destinations. shows that the modular main event handler is in communication with the following event communication components a component configured to communicate using e mail or SMTP protocols a component configured to access shared memory such as the shared memory system a component configured to communicate with a network protocol such as the network protocol a component configured to communicate with a memory queue such as the memory queue a component configured to communicate with a peer to peer communication system such as Instant Messenger a component configured to communicate using XML messaging a component configured to communicate using envelope based communication services such as SOAP and or other communications components

More than one event communication component of the same type may be used simultaneously. For example the event handler may use two event client components configured to communicate with a network protocol where each component is capable of sending data to a different destination network address.

Once configured the event handler must be initialized to prepare it for use. depicts the steps that take place when initializing the event handler . First a component such as the data transport and or the event handler application directs the event handler to initialize itself. Next the event handler uses its internal properties which were previously configured during the configuration stage to connect to a machine platform or an upstream event client and subscribe to the data items specified in the configuration data.

In practice the data items specified in the configuration data must be data that are published by the machine platform or failures may occur. As used herein the term publish or publish subscribe refers to a method of receiving data updates where the client subscribes to data published by the server. For example a server may have three data items available for subscriptions A B C. The client may then subscribe to any of these data items upon which the client may receive data updates based upon certain criteria such as the data value of the subscribed data item changing a time period passing or some other event occurring in the system such as a trigger variable firing etc. The term trigger variable refers to variable or data item that causes the registered actions to be carried out when the variable or data item s event conditions are met.

Once configured and initialized the event handler is ready to receive events for each of the subscribed data items. depicts the steps that take place when processing events. First the event is received from an upstream component such as the machine platform and or an upstream event handler that is daisy chained to the main event handler .

Upon receiving the event the data is optionally placed at the back of the internal data queue . If a queue is not used the data is immediately sent to all event destinations such as shared memory system or the network protocol that are in an enabled state for that event. If the internal data queue is used data items are pulled off the data queue according to the rules for that queue and sent to all outputs that are in an enabled state for that event. As described above the data queue may be a first in last out queue a priority queue and or a queue implementing a timing scheme.

In addition to processing events the event handler may also process commands via API calls to one of its interfaces. For example the data transport may direct the event handler to send data to an event destination by calling an API of the event handler . depicts the steps that occur when processing a command using API calls. First the remote component such as the data transport may call an event handler API through which the data is passed. When called the API may optionally place the data into an internal data queue . If a data queue is not used the data is passed directly to all outputs such as the shared memory system or the network protocol that are in an enabled state for a given event.

Optionally the main event handler may be daisy chained with one or more upstream event handlers and or one or more downstream event handlers . In this case data is received from upstream event handlers and or sent to downstream event handlers . depicts the steps that occur when processing events or commands in a daisy chained configuration.

First if an event handler is connected upstream to the main event handler the data is received from that upstream event handler as an event and or as an API call. If an upstream event handler is not used data may be received in the normal manner either via an event or API call. Next upon receiving the data as an event and or as an API call the data may be placed at the back of an internal data queue if used. If a data queue is not used the data is sent directly to all outputs such as shared memory system or network protocol that are in an enabled state.

Third when using the internal data queue the data is pulled from the data queue and sent to all enabled outputs. Again the data queue may be a first in last out queue a priority queue and or a queue implementing a timing scheme.

Fifth if a network protocol is used and is enabled the data is sent to zero one or more event destinations previously configured for this output in the case of a TCP IP network. As described above the data may be sent as a UDP broadcast to all nodes on a network or group of networks. TCP IP may also be used to send the data via a tunneling mechanism such as is used within a Virtual Private Network like those implemented with Microsoft RRAS from the current event handler to another event handler or even to a group of event handlers where the receiving component receives the TCP IP or UDP data and then translates it into an event or API input.

Sixth if a message queue such as a MSMQ event destination is used and enabled the data is sent via the message queue to another application or component or even to another event handler or group of components .

Seventh if one or more upstream event handlers and or one or more downstream event handlers are used and enabled the main event handler sends data directly to any such event handlers and or .

As an optional eighth step a downstream event handler may be configured to communicate with the upstream event handler via the shared memory and or other standard synchronization events such as the event object supported within Win32.

When daisy chaining event handlers it may also be important to pass configuration data and other data between the event handler components. When configuring any such event handler components as depicted in the downstream event handler may pass configuration information on to the main event handler . For example when subscribing to data any downstream event handler will notify any upstream event handler of all data items that are to be subscribed. The subscribing data may be continually passed along the daisy chain to modify any upstream event handlers and or directly notify the machine platform if it is connected directly to the machine platform .

The event handler is preferably a modular system made up of a set of components i.e. each component is based on a component technology such as OLE COM from Microsoft Corporation . Optionally each component may use a separate parallel ActiveX component and or a property page component to implement all user interface aspects of the main component. Each ActiveX and or property page component may be implemented either within the main component module or separately in its own module. Bundling each object within one module is not required as they may be located at any location i.e. across a network and so forth but doing so may optimize all communication between modules. How and where components are implemented is a logistical decision. Once components are built and deployed to the field it is difficult to update a single component if all components are implemented within a single DLL or EXE module.

OLE Categories are used to determine how many components fall into a certain group of components. Currently components used to form the event handler components use what will be referred to herein as the XMC Data Router components. The XMC Data Router components are general data router components support the general read write and configure API.

The IXMCDirect interface is used for most communications between all components making up the event handler . The following methods make up this interface as specified in the standard OLE COM IDL format .

The IXMCDirect GetProperty method is used to query the property corresponding to the property name pszPropName . Each component defines the properties that it supports.

This IXMCDirect SetProperty method is used to set a property in the component corresponding to the pszPropName property. For the set of properties supported by the component see the specific component description.

The IXMCDirect InvokeMethod method is used to call a specific method implemented by the component. For more information on the methods supported see the description of the specific component.

The IXMCDirectSink interface is an event reception point on which one component can send event data to another. The component implementing this interface is the event receiver and the event source calls the interface passing to it event data.

The IXMCDirectSink OnEvent method is called by the event source and passed the event data in a SAFEARRAY form for easy marshalling across process boundaries.

The IXMCDirectSink OnError method is called by the event source when an error occurs and passed the event error data in a SAFEARRAY form for easy marshalling across process boundaries.

In order to receive events directly from the machine platform the event handler also supports the IXMCaCNCEventDataSink interface as specified in the machine platform product sold by ROY G BIV Corporation.

Referring now to of the drawing depicted there in is an example of the IXMCaCNCEventDataSink OLE Interface.

The OnData event is called each time the event condition for an enabled subscription is met for a subscription configured by a client application. Deadlock can occur when running in multi application mode and calls to other XMC API are made from within this event hander or another event raised by this event handler. To avoid this situation applications that implement this method should copy all data from this method into a temporary buffer and immediately return without calling other XMC API.

The OnError event is called each time an error occurs for a subscription configured by a client application. Applications that implement this method should immediately copy the data received in a temporary buffer and or array and immediately return so as to not cause deadlock within their application. Deadlock can occur when running in multi application mode and calls to other XMC API are made from within this event handler or another event raised by this event handler.

The Methods and properties exposed by the XMC Event Client component will now be described in further detail.

This section describes the general component properties of each property supported by the event handler component.

This section describes the general component methods supported by the majority of the components. For the specific list of methods supported by any given component see the section describing that given component.

The XMC DE BROWSE GET COUNT method returns the number of data items in the browse set supported by the component.

The XMC DE BROWSE GET ITEMS method returns the number of data items in the browse set supported by the component.

The XMC DE SYSTEM CONNECT CMPNT method is used to connect one server to another so that they may interact with one another.

The XMC DE SYSTEM DISCONNECT CMPNT method is used to disconnect one server to another so that they stop interacting with one another.

The XMC DE DATA PROCESS method is called by a client to process data where a data set is input processed in some way by the server and then the resulting data is returned as output.

The XMC DE DATA PROCESS CONFIGURE method is used to configure what type of data is returned when processing a given data item. For example in the server may be configured to return the minimal amount of data on each read i.e. just the data item value or the server may be requested to return more substantial data.

The XMC DE DATA READ method is called by a client application to poll for data from the server. As used herein the term poll refers to the process of continually reading a data item so that the most recent value of the data is always on hand.

The XMC DE DATA READ CONFIGURE method is used to configure what type of data is returned when reading a given data item. For example in the server may be configured to return the minimal amount of data on each read i.e. just the data item value or the server may be requested to return more substantial data.

The XMC DE EVENT ENABLE method enables disables a previously subscribed data item in the subscription list maintained by the server. Only enabled subscriptions actually fire.

The XMC DE EVENT RECEIVE DATA method is called by the server and implemented by the client when each subscribed event fires.

The XMC DE EVENT RECEIVE DATA CONFIGURE method is used to configure what type of data is returned on each event that is fired. For example in the server may be configured to send the minimal amount of data on each event i.e. subscription cookie and data item value or the server may be requested to return more substantial data.

The XMC DE EVENT SUBSCRIBE method subscribes to a given data item activating the event interface when the subscription criteria are met for the data item. All subscribing components must use the IXMCDirect interface to receive events received from the server for which they are subscribed.

The XMC DE EVENT UNSUBSCRIBE method removes a previously subscribed data item from the subscription list maintained by the server.

The XMC DE SYSTEM INITIALIZEHW method is used to initialize any hardware systems associated with the component.

The XMC DE SYSTEM SHUTDOWNHW method is used to shutdown any hardware systems associated with the component.

The event handler component implements the following general methods listed in the General Component Methods section above.

The following methods have special notes for this component. The XMC DE EVENT SUBSCRIBE method is only needed when daisy chaining components together. The XMC DE EVENT UNSUBSCRIBE method is only needed when daisy chaining components together.

The visual elements presented by the event handler component namely the event handler property pages will now be described in further detail.

The example property page depicted in allows the user to set up the connection settings used to connect to the target machine from which data will be received. In addition this property page allows the user to configure how the component is connected and starts up when it is first run.

As shown in the following user interface elements form the connection and start up property page . A target machine field identifies the target machine from which data is to be received using the TARGETMACHINE method. A connect button tests the connection with the target machine using a CONNECT method. A disconnect button disconnects the system from the target machine using the DISCONNECT method.

A map variables check box specifies whether or not to load mapped variables from a file when connecting using OPTIONS OF MAPVARIABLES ENABLED and VARMAPFILE properties. When checked a dialog appears allowing the user to select the file to load mapped variables from.

An enable auto load check box specifies whether or not the auto load feature should be enabled and when enabled from which file to load the settings from as identified in a file field using OPTIONS OF AUTOLOAD ENABLED CONFIGFILE properties.

An enable auto start check box specifies whether or not to enable auto start using OPTIONS OF AUTOSTART ENABLED properties.

An event monitoring property page depicted in allows the user to configure which variables are to be monitored. The event monitoring property page comprises the following interface elements.

A variables box contains a list of all variables that are available for monitoring. A test button directs the application to test a selected highlighted variable by reading it using a READ method. An attributes button retrieves the attributes of the selected highlighted variable using the READ attrib method.

A variables to monitor box contains a list of all variables that have been selected for monitoring using VAR MONITOR COUNT and VAR MONITOR properties.

A first add . . . button directs the event handler to add a variable from the variable list in the box to the variables to monitor list in the box . A first remove button directs the event handler to remove the selected variable from the variables to monitor list in the box . When a first all check box is checked pressing the first remove button directs the event handler to remove all variables from the variables to monitor list box .

A variables to read box contains a list of all variables that have been selected for reading using VAR READ COUNT and VAR READ properties. A second add . . . button directs the event handler to add a variable from the variable list in the box to the variables to read list in the box . A second remove button directs the event handler to remove the selected variable from the variables to read list in the box . When a second all check box is checked pressing the second remove button directs the event handler to remove all variables from the variables to read list box .

Referring now to depicted therein is an example of a data collection property page that allows the user to specify how the variable data is collected. The data collection property page comprises the following user interface elements.

A queue event results up to check box and associated edit field specify the maximum number of items to be placed in the optional data queue using the following properties OPTIONS OF QUEUE API CALLS ENABLED OPTIONS OF QUEUE EVENTS ENABLED and QUEUEMAXSIZE.

A wait for data received event check box and associated edit field specify the amount of time to wait for the recipient of the data to respond by signaling the data ready event using the following properties 

A delete old items after check box and associated edit field specify the amount of time that data items may remain in the queue after which they are purged using the following properties OPTIONS OF DELETE OLD QUEUE ITEMS and DATAOLDTIMEOUT method.

The collect data always check box specifies whether or not data should always be collected even when the data does not change using the following properties OPTIONS OP COLLECT DATA ALWAYS .

The present invention may be embodied in forms other than those described above. The scope of the present invention should thus be determined with reference to the following claims and not the foregoing exemplary detailed description.

This Appendix A contains the definitions of all special types used by the methods and properties of each component making up the example XMC Program Engine system that may form a part of the present invention.

All methods exposed by each component in the XMC Program Engine system use the standard XMC parameters set to describe data used to set and query properties as well as invoke methods. The standard parameters are in the following format 

Each element in the rgData array corresponds to a parameter with the first element in the array corresponding to the first parameter. The XMC PARAM DATA structure can contain either a numerical or a string value and is defined as follows 

The adt member of the XMC PARAM DATA structure describes the data contained within the XMC PARAM DATA structure. The values are described below 

When querying and setting boolean TRUE FALSE values any non zero value is considered TRUE whereas a zero value is considered FALSE.

