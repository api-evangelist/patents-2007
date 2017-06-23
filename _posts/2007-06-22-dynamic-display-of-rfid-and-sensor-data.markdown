---

title: Dynamic display of RFID and sensor data
abstract: Systems, methods and computer program products, implementing techniques for automatic data acquisition and the real-time display of automatically acquired data. A system implementing the techniques includes one or more automatic data acquisition devices that emit data; and a data integration system that receives data from the automatic data acquisition devices and processes the data. The data integration system includes a display system for displaying the data to a user. The display system is operable to generate a graphical display and to update the graphical display automatically and only when new data from the automatic data acquisition devices is available. The display system is operable to update only affected parts of the graphical display but not necessarily the entire display.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=07817039&OS=07817039&RS=07817039
owner: SAP Aktiengesellschaft
number: 07817039
owner_city: Walldorf
owner_country: DE
publication_date: 20070622
---
This application is a continuation of prior U.S. patent application Ser. No. 11 020 384 filed on Dec. 22 2004 which is incorporated herein by reference.

The present disclosure relates to data processing by digital computer and more particularly to automatic data acquisition and the display of automatically acquired RFID Radio Frequency Identification data and sensor data.

Systems exist for integrating data acquisition devices such as RFID tag readers and sensor devices with enterprise software applications that make use of the data acquired by the data acquisition devices. In this specification such systems will be referred to as data integration systems.

Data integration systems typically provide an application programming interface through which the enterprise applications can access the data collected by the data integration system. However conventional data integration systems typically do not provide a user interface through which a human user can view the automatically acquired RFID and sensor data.

Systems methods and computer program products implementing techniques for displaying automatically acquired data.

In one general aspect the techniques include receiving data emitted by a plurality of automatic data acquisition devices displaying the data for viewing by a user and automatically updating the displayed data only when new data is received. The automatic data acquisition devices include both periodic devices that emit periodic data and aperiodic devices that emit aperiodic data. Periodic data is data that is emitted continuously at regular intervals. Aperiodic data is data that is emitted at irregular intervals.

The data may be received by a server. Displaying the data for viewing by a user may include sending the data to a client and displaying the data on the client for viewing by a user.

The periodic devices may include sensor devices and the aperiodic devices may include RFID Radio Frequency Identification tag readers.

In another general aspect the techniques include subscribing to a publication service that publishes data emitted by automatic data acquisition devices the publication service being provided by a web server receiving a web page from the web server the web page including the data displaying the web page for viewing by a user receiving from the web server one or more updates to the data identifying a portion of the web page that is affected by the updates and redrawing only the identified portion of the web page the identified portion being less than the entire web page. The automatic data acquisition devices include both periodic devices that emit periodic data and aperiodic devices that emit aperiodic data. Periodic data is data that is emitted continuously at regular intervals aperiodic data is data that is emitted at irregular intervals.

The web page may be displayed in a web browser without the installation of any additional programs or components to the web browser.

The web page may further include a mechanism that is operable to establish a persistent connection with the web server. The web page including the data and the one or more updates to the data may be received through the persistent connection.

The periodic devices may include sensor devices and the aperiodic devices may include RFID Radio Frequency Identification tag readers.

In another general aspect a system implementing the techniques described herein includes one or more automatic data acquisition devices that emit data and a data integration system that receives data from the automatic data acquisition devices and processes the data. The data integration system includes a display system for displaying the data to a user in real time.

The data integration system may be operable to send the data to display system and to separately send the data to one or more enterprise applications.

The display system may be operable to generate a graphical display and to update the graphical display automatically.

The display system may be operable to update the graphical display only when new data from the automatic data acquisition devices is available.

The display system may be operable to update the graphical display without redrawing the entire graphical display.

The display system may include a web server and a web browser and the graphical display may be a web page.

The web page may be displayed by the web browser without the installation of any additional programs or components.

The automatic data acquisition devices may include both periodic devices that emit periodic data and aperiodic devices that emit aperiodic data periodic data being data that is emitted continuously at regular intervals aperiodic data being data that is emitted at irregular intervals.

The periodic devices may include sensor devices and the aperiodic devices include RFID Radio Frequency Identification tag readers.

The data integration system may include a rules engine that executes a set of rules each rule specifying one or more conditions and one or more activities to be executed when the conditions are met.

The activities may include sending an event to the display system the event containing data emitted by the automatic data acquisition devices.

The display system may be operable to generate multiple graphical displays and to update the multiple graphical displays simultaneously.

Data collected by data acquisition devices can be viewed in real time by a human user. Workers in a supply chain for example dock hands truck drivers and store or warehouse clerks can view accurate real time information about the status and disposition of physical goods in the supply chain.

The data can be viewed through a graphical display. The graphical display can be viewed from a portable hand held device or from a desktop computer.

The graphical display can be viewed in a basic off the shelf web browser without requiring the installation of any additional components or programs to the web browser.

The graphical display can update automatically without user intervention. This allows for hands free use of the display.

The data can be viewed simultaneously in multiple graphical displays. The multiple graphical displays can be updated simultaneously. Graphical displays that subscribe to the same topics will receive the same updates and at the same time.

The update can be configured to only occur when new data is available thereby reducing the burden on system performance.

The update can be performed without having to redraw the entire display thereby increasing system efficiency.

The display system can be combined with a data integration system to provide an end to end solution for the automatic acquisition of RFID and sensor data and the display of such data to an end user.

Details of one or more implementations are set forth in the accompanying drawings and in the description below. Further features aspects and advantages will become apparent from the description the drawings and the claims.

The data acquisition devices can include different types of data acquisition devices. For example the data acquisition devices can include both devices that emit periodic data streams periodic devices and devices that emit aperiodic data streams aperiodic devices .

A periodic stream is a continuous stream of data occurring at regular time intervals e.g. one data value every n milliseconds as opposed to an aperiodic stream where data is emitted at irregular intervals for example only when a tagged item is detected. Examples of a periodic device are sensor devices for measuring one or more physical properties for example temperature humidity acceleration pressure light position movement or noise and servers that provide continuous data feeds for example of stock information . An example of an aperiodic device is an RFID Radio Frequency Identification tag reader or transponder.

As shown in the dynamic display system includes a server component server and one or more clients . In a web based implementation of the dynamic display system the server is a web application server the clients are web browsers or other HTTP Hypertext Transfer Protocol based web clients and the graphical displays on the clients are web pages.

The server is operable to receive events from the data acquisition devices and to publish the events to clients that have subscribed to receive events from the server . The clients are operable to visualize the events in a graphical display for viewing by a user.

The graphical display is dynamic meaning that the display can change the display is not static. The clients automatically update the graphical display to reflect new events received from the server .

The clients can be configured to update the graphical display only when new events have been received from the server . The updates do not occur regularly but only when new events containing new data to be displayed have been received.

Clients can subscribe to receive only events pertaining to a certain topic. Clients that subscribe to the same topic will receive the same events and at the same time. For example workers in a warehouse can each have their own hand held graphical display . Each of these displays can subscribe to the same topic for example a topic that provides notice about incoming pallets. When a new pallet arrives at the warehouse an incoming pallets event is sent to all of the subscribing graphical displays at the same time.

As shown in in one implementation the server includes a subscription module for processing subscriptions from the clients a publisher module for publishing events to subscribed clients and one or more subscriber instances . The subscriber instances represent the subscribed clients . Each subscriber instance includes an event queue for storing events that have been matched to the particular client represented by the subscriber instance .

The server can also include an event formatter for formatting events received from the data acquisition devices before the events are delivered to the publisher module . For example the events received from the data acquisition devices may be represented in a device specific format that is different from the format used by the dynamic display system . The event formatter can convert the events from the device specific format to the system format. The event formatter can include different types of event formatters each specific to a different type of data acquisition device.

The server can also include a client adapter for handling the data communication between the server and the clients . The client adapter can include a plurality of different types of adapters for use with different types of clients that may require different communication protocols or formats. The client adapter can include a browser adapter for web browser clients and a mobile adapter for mobile clients for example.

The server can also include an event processor for processing the events before the events are delivered to the client adapter . Examples of processing tasks include adding time stamps adding server specific headers and applying style sheets or formatting to the events.

As shown in during system operation a client subscribes to receive events from the server step . The client subscribes to the server by invoking the subscription module and passing to the subscription module one or more parameters specifying the topics that the client is subscribing to.

The subscription module creates a subscriber instance for the client and adds the subscriber instance to a subscriber list for the publisher module step . The subscription module then activates the subscriber instance step causing the subscriber instance to continuously check for and retrieve events from its event queue .

Meanwhile the server receives events generated by the data acquisition devices step . The events can be preprocessed by the event formatter . The event formatter converts the events from a device specific format to a system specific format and then forwards the events to the publisher module step .

Upon receiving the events the publisher module determines the topic of each event and identifies the subscribers subscriber instances that are interested in the event step . The event is then added to the event queue of each identified subscriber instance step .

The subscriber instance detects the event in its event queue removes the event from the queue and sends the event to the client step . The event can be sent to the client through the client adapter .

Optionally before sending the event to the client adapter the event can be processed by the event processor step .

A web based implementation of the above described functionality can be developed by extending a conventional servlet based technology known as pushlets . Pushlets is a well known technique for pushing data directly from a server to a client without requiring the client to load any additional programs or components e.g. applets or plug ins . The class diagram shown in illustrates how the conventional pushlet classes can be extended to provide the above described functionality.

The conventional pushlet classes are the ClientAdapter class the Pushlet class the Subscriber class the PushletSubscriber class the EventQueue class the Event class the Publisher class the Postlet class and the HttpServlet class .

The extension classes are the DynamicWebDisplaySubscriber class the DynWebDisplaySubscriptionRegistry class the DynWebDisplayEventGenerator class and the BrowserClientAdapter class .

The DynamicWebDisplaySubscriber class extends the conventional pushlet technology with the capability of subscribing to multiple topics.

The DynWebDisplaySubscriptionRegistry class implements the functionality of the subscriber module that is the functionality to accept subscriptions create subscriber instances and activate the subscriber instances to listen for published events.

The DynWebDisplayEventGenerator class implements the functionality of the event formatter that is the functionality to convert events from a device specific format to a system specific format.

The BrowserClientAdapter class implements the functionality of the client adapter that is the functionality to work with different types of clients that use different communication protocols and formats.

The Event Processor class implements the functionality of the event processor that is the functionality to process the events before the events are sent to the client adapter .

The previous paragraphs described a technique that allows the graphical display of a client to be updated only when new data is received. The following paragraphs describe a technique that allows the updating of the graphical display to be performed without requiring the entire graphical display to be redrawn.

In conventional web based systems the web server and the web browser communicate using a request response type of protocol typically HTTP Hypertext Transfer Protocol . With HTTP the web browser makes a request to the web server for a web page and the server responds by serving the web page which is then displayed by the web browser for viewing by a user. The user can click on links in the web page to navigate to a new web page. To obtain the new web page the web browser makes a request to the web server for the new web page.

HTTP is a stateless protocol meaning that each time the web browser client requests a new web page a connection is made to the server a new page is generated by the server and returned to the client web browser and then the connection is destroyed. This new web page is rendered and displayed by the web browser. Even if portions of the existing web page also appear on the new web page these identical portions are typically still destroyed and then redrawn again. Thus traditionally a web page can be updated only by redrawing the entire web page.

As will be described below in one implementation of the dynamic display system the client uses a technique that allows a web based graphical display web page on the client to be updated without redrawing the entire web page. In a process illustrated in a technique for selectively redrawing portions of the web page involves first establishing a persistent connection between the client and the server step . Once the persistent connection has been established the server can send events to the client through the persistent connection step . Subsequent events can also be sent through the same persistent connection.

The persistent connection can be established when the client subscribes to the server step of . The client makes a subscription request to the server . In response to the subscription request the server returns a web page illustrated in that includes two frames a visible frame and a hidden frame . The hidden frame calls a pushlet running on the server . The pushlet pushes events to the client which then displays the events or to be precise the data contained in the event in the visible frame .

Upon receiving the events the client determines which portions of the visible frame are affected by the events step and only redraws the affected portions of the frame step . Portions not affected by the events are not redrawn. The client performs the selective redraw by manipulating elements of a document object model DOM for the web page . The DOM is a hierarchical representation of the elements of the web page . The DOM elements can be manipulated using client side scripting code for example JavaScript or VisualBasicScript .

As shown in the above described dynamic display system specifically components and can be combined with a data integration system to provide an end to end system for automatically acquiring sensor and RFID data processing the acquired data and making the processed data available to enterprise applications and or displaying the processed data to a user.

As shown in the end to end system can be represented conceptually as four layers a device layer a device operation layer a business process bridging layer and an enterprise application layer .

The bottom layer the device layer represents the data acquisition devices . The topmost layer the enterprise application layer represents the enterprise applications . The two middle layers device operation layer and business process bridging layer represent the data integration system .

The device layer includes different types of data acquisition devices for example RFID tag readers environmental sensors and PLC Programmable Logic Control devices which are devices commonly used in factory automation. The device layer also includes a hardware independent low level interface for reading and writing data from and to the different types of data acquisition devices . The device layer reads data from the data acquisition devices and reports the data to the next layer the device operation layer .

The device operation layer includes one or more device controllers . Each device controller is responsible for coordinating one or more of the data acquisition devices . Each device controller receives data from a data acquisition device through the device layer and forwards the data to the next layer the business process bridging layer . Before forwarding the data the device controller can process the data for example using a chain of data processors. Device controllers and data processing chains will be described in more detail below and are also described in U.S. patent application Ser. No. 10 854 766 entitled Generic Software Mechanism for the Control of RFID Readers and other Devices .

The business process bridging layer associates incoming data with business processes performed by the enterprise applications . In one implementation these business processes involve the storage and transport of physical items for example goods in a supply chain. The business process bridging layer includes a database system that records the status and history of these physical items. The database records can include information about the item s location environment and relationship to other items. This database system and the corresponding tracking functionality will be referred to as an item tracking system .

The enterprise application layer supports business processes of enterprise applications such as Supply Chain Management SCM Customer Relationship Management CRM Asset Management or First Responder Support. The enterprise application layer receives events generated by the underlying business process bridging layer .

As shown in the above described dynamic display system can span the business process bridging layer and enterprise application layer . The server component of the display system is application independent. It can be implemented as part of the business process bridging layer . The clients are application specific and can be implemented as part of the enterprise application layer .

The dynamic display system can serve as a front end to the item tracking system . The item tracking system can generate events to send to the enterprise applications . These events can also be sent to the dynamic display system .

In one implementation the item tracking system is distributed across multiple locations which will be referred to as nodes. Each node of the item tracking system is responsible for integrating incoming data from the device controllers with the business processes of the enterprise applications . Each node is operable to interact bi directionally with the device controllers for example to receive events from the device controllers and to send commands to the device controllers . Each node is also operable to interact bi directionally to with the enterprise applications for example to receive business data from the enterprise application and to send a response . These interactions are treated as either incoming or outgoing messages.

Incoming messages to the item tracking system are routed to a rule engine which based on the message type evaluates a specified list of conditions. The result of the evaluation step is a set of qualifying rules for which one or more activities are executed in a specified order. Such an activity can for example update the system status of an object in the item tracking system communicate with an enterprise application or generate and write data to a tag.

The item tracking system provides a data repository for storing information about the current status and history of the objects being processed. This information includes data about the operations that have been applied to an object e.g move pack or unpack operations its movement and current location and its structure e.g packing information . Also the repository replicates business data from the enterprise applications about products and business partners or the physical location and type of the RFID readers. The repository provides the basis for the execution of business logic in the item tracking system in the form of customizable rules. This allows the pre processing of incoming observation data and the handling of abnormal situations within the item tracking system such as discrepancies between a received advanced shipping notification ASN and a detected pallet.

As shown in during operation of the end to end system RFID tag or sensor data is sent from an RFID reader or sensor device to a device controller step . The device controller pre processes e.g. filters aggregates enhances the incoming data and sends a corresponding observation message to a communication layer communicator of the item tracking system step .

Once the message is received the communicator then determines the message type and sends the message to a message dispatcher within the item tracking system step . The message dispatcher selects an appropriate message adapter and sends the message through the message adapter to a message parser within the item tracking system step . The message parser parses the message and generates a message object that is sent to the rule engine of the item tracking system step .

The rule engine analyzes a set of conditions step and determines a set of activities to be executed step . An example of an activity is to prepare and immediately send the incoming RFID or sensor data to the display system . Such an activity will be referred to as a display activity. An example Java class implementing a display activity is shown in Table 1 below. The execution of a display activity by the rule engine initiates the sending of an event to the server of the display system step . The event is received by the server and processed according to the data flow described above with respect to .

Ultimately the event is sent to the client step which performs the dynamic update of the affected parts of the graphical display as described above with respect to .

The various implementations of the invention and all of the functional operations described in this specification can be implemented in digital electronic circuitry or in computer software firmware or hardware including the structural means disclosed in this specification and structural equivalents thereof or in combinations of them. The invention can be implemented as one or more computer program products i.e. one or more computer programs tangibly embodied in an information carrier e.g. in a machine readable storage device or in a propagated signal for execution by or to control the operation of data processing apparatus e.g. a programmable processor a computer or multiple computers. A computer program also known as a program software software application or code can be written in any form of programming language including compiled or interpreted languages and it can be deployed in any form including as a stand alone program or as a module component subroutine or other unit suitable for use in a computing environment. A computer program does not necessarily correspond to a file. A program can be stored in a portion of a file that holds other programs or data in a single file dedicated to the program in question or in multiple coordinated files e.g. files that store one or more modules sub programs or portions of code . A computer program can be deployed to be executed on one computer or on multiple computers at one site or distributed across multiple sites and interconnected by a communication network.

The processes and logic flows described in this specification including the method steps of the invention can be performed by one or more programmable processors executing one or more computer programs to perform functions of the invention by operating on input data and generating output. The processes and logic flows can also be performed by and apparatus of the invention can be implemented as special purpose logic circuitry e.g. an FPGA field programmable gate array or an ASIC application specific integrated circuit .

Processors suitable for the execution of a computer program include by way of example both general and special purpose microprocessors and any one or more processors of any kind of digital computer. Generally a processor will receive instructions and data from a read only memory or a random access memory or both. The essential elements of a computer are a processor for executing instructions and one or more memory devices for storing instructions and data. Generally a computer will also include or be operatively coupled to receive data from or transfer data to or both one or more mass storage devices for storing data e.g. magnetic magneto optical disks or optical disks. Information carriers suitable for embodying computer program instructions and data include all forms of non volatile memory including by way of example semiconductor memory devices e.g. EPROM EEPROM and flash memory devices magnetic disks e.g. internal hard disks or removable disks magneto optical disks and CD ROM and DVD ROM disks. The processor and the memory can be supplemented by or incorporated in special purpose logic circuitry.

To provide for interaction with a user the invention can be implemented on a computer having a display device e.g. a CRT cathode ray tube or LCD liquid crystal display monitor for displaying information to the user and a keyboard and a pointing device e.g. a mouse or a trackball by which the user can provide input to the computer. Other kinds of devices can be used to provide for interaction with a user as well for example feedback provided to the user can be any form of sensory feedback e.g. visual feedback auditory feedback or tactile feedback and input from the user can be received in any form including acoustic speech or tactile input.

The invention can be implemented in a computing system that includes a back end component e.g. a data server a middleware component e.g. an application server or a front end component e.g. a client computer having a graphical user interface or a Web browser through which a user can interact with an implementation of the invention or any combination of such back end middleware and front end components. The components of the system can be interconnected by any form or medium of digital data communication e.g. a communication network. Examples of communication networks include a local area network LAN and a wide area network WAN e.g. the Internet.

The computing system can include clients and servers. A client and server are generally remote from each other and typically interact through a communication network. The relationship of client and server arises by virtue of computer programs running on the respective computers and having a client server relationship to each other.

The invention has been described in terms of particular implementations but other implementations are within the scope of the following claims. For example the operations of the invention can be performed in a different order and still achieve desirable results. In certain implementations multitasking and parallel processing may be preferable.

