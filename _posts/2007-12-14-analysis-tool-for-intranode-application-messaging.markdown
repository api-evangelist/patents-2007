---

title: Analysis tool for intra-node application messaging
abstract: A method and apparatus for transforming message events between applications running on a computing device into a form that appears as network events between multiple virtual network access devices. These “network events” may then be processed by known network software protocol analyzers.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08725901&OS=08725901&RS=08725901
owner: AT&T Intellectual Property II, L.P.
number: 08725901
owner_city: Atlanta
owner_country: US
publication_date: 20071214
---
The present invention relates generally to computer networking and more particularly to a methodology and apparatus for transforming messages communicated between software applications running on a computing device into network events that can be processed by known network software protocol analyzers.

Message based software applications are widely found in domains such as telecommunications. Such applications exchange data through messages to fulfill their desired functions. The applications enable a variety of capabilities including real time communications and data transfer. In this connection a stream of messages between network components can be commonly analyzed by Software Protocol Analyzers SPA such as Wireshark formerly known as Ethereal and the like which are well known in the art. SPAs enable monitoring of network operations ensure proper network performance and assist with debugging issues by capturing and analyzing such messages between applications.

Currently deployed SPAs are disposed between hosts communicating through a network as shown in . Thus they are restricted to analyzing messages between applications that are located on separate hosts. It would therefore be desirable to utilize such standard inter host tools to analyze message events which are defined as those events that occur between applications that are running on a single host.

In accordance with aspects of the present invention there is disclosed a methodology and apparatus for transforming message events that are created by applications executing on a single computing device into a form that appears analogous to network events . In a general sense the method comprises creating a virtual network access device corresponding to each application logging message events which are communicating between applications running on the computing device correlating the message events logged by sending and receiving applications with each other correlating some message events with true network events and transforming the message events into network events such that the message i.e. network events may be processed by SPAs.

In accordance with another aspect of the invention a computing device comprising a memory medium embodying machine readable instructions which when executed by a processor enable the computing device to create a virtual network access device corresponding to each application log message events which are communicating between applications running on the computing device correlate the message events into network events and transform the message events into network events such that the message i.e. network events may be processed by SPAs.

In accordance with still another aspect of the invention there is provided a memory medium containing machine readable instructions which when executed by a processor enable a computing device to create a virtual network access device corresponding to each application log message events which are communicating between applications running on the computing device correlate the message events into network events and transform the message events into network events such that the message i.e. network events may be processed by SPAs. These and further advantages will become apparent to those skilled in the art as the present invention is described with particular reference to the accompanying drawings.

Embodiments of the invention will be described with reference to the accompanying drawing figures wherein like numbers represent like elements throughout. Before embodiments of the invention are explained in detail it is to be understood that the invention is not limited in its application to the details of the examples set forth in the following description or illustrated in the figures. The invention is capable of other embodiments and of being practiced or carried out in a variety of applications and in various ways. Also it is to be understood that the phraseology and terminology used herein is for the purpose of description and should not be regarded as limiting. The use of including comprising or having and variations thereof herein is meant to encompass the items listed thereafter and equivalents thereof as well as additional items.

In accordance with a first aspect of the invention there is disclosed herein a method for transforming message events that occur between applications running on a computing device such that they appear as network events between virtual hosts on a communication network for analysis by standard network messaging software i.e. Software Protocol Analyzers SPA .

With reference now to an illustrative network architecture is shown which generally comprises a plurality of network access devices NADs . . . which communicate therebetween through a communications network simply characterized by the reference numeral . Such networks are well known in the art and as example an exemplary Voice over IP VoIP application for enabling telephone calls between a plurality of users connected to the network is shown. Examples of NADs include but are not limited to a telephone coupled to an access backbone network providing VoIP services a personal computer PC laptop and or a personal digital assistant PDA such as a Blackberry Palm or like apparatus.

Typically a SPA is deployed somewhere in the network as shown or in a NAD . . . . The SPA processes and analyzes inter host messages as described in the foregoing.

Layer 1 Physical This layer implements the transfer of data over the physical link specifically the mechanical electrical and procedural characteristics to establish maintain and deactivate the physical link.

Layer 2 Data Link This layer enables the reliable transfer of data across the physical link of Layer 1. It provides the functional and procedural method to transfer data between CDs and to detect and possibly correct errors that may occur in the Physical layer.

Layer 3 Network This layer provides the functional and procedural means of transferring data from a source to a destination through a plurality of networks while maintaining data integrity quality specified by Layer 4 Transport layer .

Layer 4 Transport This layer enables the transfer of data between end users and provides reliable data transfer services to Layer 5 Session layer .

Layer 5 Session This layer establishes a control structure for communication between applications specifically to establish manage and deactivate connections sessions between applications.

Layer 6 Presentation This provides a standardized Application Programming Interface API and to provide common communications services.

Layer 7 Application This layer provides services to the end users of the OSI environment. It can provide services such as File Transfer Protocol FTP transaction server network management etc.

The OSI provides a framework for computer networking from the application layer running programs at the top level for the user to an input output I O interface coupled to a communications network . In this regards each layer messages the adjacent layer of the model. The CD includes conventional memory and a processor as is commonly known in the art. The CD here is depicted as bidirectionally communicating with another CD over a communications network .

In accordance with the present invention current state of the art methods for handling messages created in known message based applications are restricted to events that occur at layers of the OSI stack below the Application Layer e.g. at layers 3 and 4 . Aspects of this invention provide a methodology for correlating messages generated by independent applications running on a single host and allow for the generation of a consolidated log of events that may be transformed into a format that can be readily processed by SPAs either on the host itself or somewhere else on a network. These intra host messages may never reach the lower layers of the OSI stack required by current state of the art methods. This invention therefore allows standard inter host software tools to be used for processing of such intra host messages.

With reference to an exemplary flow diagram is depicted for practicing a method in accordance with an aspect of the invention. This method employs three components an Application Logger AL a Log Correlator LC and a Log Formatter LF .

The Application Logger AL is a software library or module that is used by each application AL AL AL running on the CD as described above and intercepts i.e. logs messages that are communicating between applications running on the CD. In a preferred embodiment the logging function is executed automatically as network events occur such that the author of the application need not provide such code within new software instructions of each individual application. This arrangement simplifies software development testing debugging deployment operation maintenance and computer networking upgrades.

The Log Correlator LC in is a software component that bidirectionally interfaces with each AL and correlates the logs generated by the AL . It analyzes the log files to determine which output events from an application correspond to input events from another application as well as which message events may correspond to true network events and then creates consolidated network events to represent such linkages.

The Log Formatter LF in is a software component that bidirectionally interfaces with the LC and operates on the consolidated logs to format the network events into a standard format that can be easily processed by a variety of SPAs. A consolidated log representing all of the network events is shown at which log is thereafter output to a SPA .

The foregoing detailed description is to be understood as being in every respect illustrative and exemplary but not restrictive and the scope of the invention disclosed herein is not to be determined from the description of the invention but rather from the claims as interpreted according to the full breadth permitted by the patent laws. It is to be understood that various modifications will be implemented by those skilled in the art without departing from the scope and spirit of the invention.

