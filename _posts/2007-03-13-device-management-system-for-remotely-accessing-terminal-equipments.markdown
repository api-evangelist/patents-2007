---

title: Device management system for remotely accessing terminal equipments
abstract: A device management system for remotely setting parameters to Terminal Equipments connected to a network comprises a Terminal Equipment management application (), servers connected to the network, each supporting a different remote management protocol, and means () for, upon a generic functionality-oriented request () from the Terminal Equipment management application, and for each one of the Terminal Equipments:


url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08095128&OS=08095128&RS=08095128
owner: International Business Machines Corporation
number: 08095128
owner_city: Armonk
owner_country: US
publication_date: 20070313
---
The present invention relates to device management in general and more particularly to a device management for remotely setting parameters to Terminal Equipments.

Device management is here referred to as the capability to reach out from a central location to one or a group of mobile devices to remotely manage them. It is typically implemented by a telecommunications operator but also within the enterprise or by a providers of service offerings such as configuring their clients mobile devices. Specific sub domains of device management are also implemented by mobile device vendors.

Mobile devices may be for example mobile phones Personal Digital Assistants notebook and laptop computers SIM cards vehicle embarked computers SmartHome gateways Internet appliances etc. For the purpose of this patent application they will be referred to as Terminal Equipment.

Remote management actions requiring the capability to reach out to Terminal Equipments could be without limitation involved in the following Terminal Equipment management applications Initial Provisioning Bootstrap of devices Device re configuration Continuous Provisioning Real time hardware software configuration inventory of devices Software distribution management applications Operating System any software Remote device problem determination Back up and restore of configuration data Network device application and service performance monitoring management etc.

Enablement on Terminal Equipment side of the management services accessed by the Terminal Equipment requires setting up Terminal Equipments with a complete and correct set of parameter values. If a Terminal Equipment has not been pre provisioned for the management service or whenever modifications are required the end user has to configure the Terminal Equipment manually and locally through its display menus unless a specialist e.g. Telecommunications operator support personnel can perform the operation remotely. Technologies exist today which allow to remotely perform parameters settings to a network connected Terminal Equipment. However while providing the necessary foundation for remote Terminal Equipment configuration management these technologies as a whole fall short when it comes to leveraging them in Terminal Equipment management applications that can be deployed for practical Terminal Equipment and end user remote support.

Further device management has in the last few years been affected by several significant evolution factors 

There remains to be devised a device management system that would all at the same time involve any management action against any Terminal Equipment help improve customer satisfaction be cost effective and in the case of a service provider or a telecommunications operator allow for new business processes and associated revenues.

The present invention is defined by the system set out in the appended claim . More particularly there is devised a device management system for remotely setting parameters of Terminal Equipments connected to a network. The system comprises 

an Abstraction Layer for upon a generic functionality oriented request from the Terminal Equipment management application and for each one of the Terminal Equipments 

In one embodiment the device management system also comprises a second server connected to the network supporting a second remote management protocol and means in the Abstraction Layer for determining one remote management protocol between the first and the second remote management protocols and applying the steps of querying gathering and sending in relation to the determined remote management protocol and server supporting it between the first and the second servers.

In another embodiment the first server in the device management system supports at least one other remote management protocol and the system comprises means in the Abstraction Layer for determining one remote management protocol between the first and the second remote management protocols and applying the steps of querying gathering and sending in relation to the determined remote management protocol.

A configuration service is also devised for remotely setting parameters for the installed base of Terminal Equipments for a customer using the device management system according to the invention.

The foregoing together with other objects features and advantages of this invention can be better appreciated with reference to the following specification claims and drawings.

The following description is presented to enable one of ordinary skill in the art to make and use the invention. For sake of clarity the description is first made in relation to a particular first management service and business process Multi media Messaging Service MMS is one example of a management service that is being offered by telecommunications operators. Access to the management service requires setting up the Terminal Equipment with a complete and correct set of parameter values.

Turning to there is a typical example of a network to which are connected Terminal Equipments of different brands and models but both supporting open remote management protocol OMA DM Open Mobile Alliance Device Management and a Terminal Equipment supporting another open protocol the OMA CP protocol Open Mobile Alliance Client Provisioning . The network may wireless or wired. Other Terminal Equipments not shown on could also typically support certain other including proprietary protocols.

An example of Terminal Equipment management application a Customer Care application of a telecommunications operator runs on a server for managing Terminal Equipments supporting OMA DM on top of Application Programming Interface API . Since today on the market not one single technology can address the full spectrum of Terminal Equipments providing a given functionality another Customer Care application runs on a server for managing Terminal Equipments supporting OMA CP on top of API .

The respective Customer Care applications manage the MMS service and send parameters to the managed Terminal Equipments. The actual command sent to the Terminal Equipment will differ in the Terminal Equipment and or cases because the supported protocols are different. Besides the implementation of the representation of given parameters across any one protocol varies from one Terminal Equipment brand model to another.

Looking now specifically at Terminal Equipments and and their OMA DM protocol support the actual command sent will differ between Terminal Equipment and Terminal Equipment . This is because the addresses of the objects addressing a same MMS parameter are different in the respective Terminal Equipment and implementations. The open OMA DM protocol presents the characteristic to specify the format for the addressing of individual objects addressing called Uniform Resource Identifier URI in the OMA DM protocol . However the OMA DM specifications do not prescribe the object addresses themselves except for a very limited and largely incomplete set of objects.

The OMA DM specifications do not provide the notion of a self contained group of objects needing to be addressed together coherently. Still using the MMS example OMA DM specifications do not list the set of parameters that a complete and coherent definition of the MMS function has to include. The set of MMS related objects as a consequence varies from one Terminal Equipment brand model implementation to another.

While discussed with respect to OMA DM it is to be noted that most if not all remote management protocols inherently leave open implementation options when it comes to certain object addressing or to certain objects that a management service has to include.

Our example Terminal Equipment could be sent a series of OMA DM Add commands that would target the object addresses below 

Terminal Equipment is a different brand model and could be sent a series of OMA DM Replace commands that target a different set of URI s 

Finally Terminal Equipment supporting a different open remote management protocol could be sent a WAP Push SMS built from the parameter set similar to the example below 

Each and every Terminal Equipment management application development for device management has therefore to include and maintain a representation down to the details of the protocol and of the management objects addresses for the diversity presented by the set of Terminal Equipments it targets. This significantly complexities the design of such applications increases the development costs slows down the delivery and has lead in fact to the release of multiple specialized applications where each addresses only a specific subset of the Terminal Equipment spectrum.

The invention consists of an Abstraction Layer implemented on top of the management protocol servers two in our example through APIs . Customer Care application sits on top of the Abstraction Layer. The actual set of commands to Terminal Equipments and is the same as the set mentioned above with respect to .

The Abstraction Layer transforms diverse Terminal Equipment specific device management client implementation realities into an as generic as possible set of management services. Terminal Equipment management applications such as the Customer Care Application make use of the Abstraction Layer services by submitting generic Terminal Equipment functionality oriented requests. The Abstraction Layer identifies the management protocol and server that are appropriate to fulfill the request and prepares and submits the corresponding request to each server through its API.

A comparison with highlights the benefits of the Abstraction Layer for the Terminal Equipment management application development such applications no longer need to include and maintain the knowledge of the protocol supported by the Terminal Equipments to be managed nor the knowledge of the specific object implementation under a given protocol. In the specific case of the OMA DM protocol the applications no longer need to include and maintain the knowledge of the OMA DM object representation exposed by the specific OMA DM Client implementations. Applications thereby become significantly cheaper and quicker to develop. Moreover a single application by using the Abstraction Layer services can span across multiple management protocols.

Abstraction Layer API provides to Customer Care application the set of commands and the programming interface that Abstraction Layer is capable of handling.

The Abstraction Layer makes use of a database of profiles of known Terminal Equipments types together with the various management protocols supported by each type. A Terminal Equipment type is typically characterized by its make and model. Depending on the manufacturer the Terminal Equipment may also be further characterized for remote management capability by its operating system version its device management client version or both. Creation and maintenance of the database profiles is part of administration functions . Such functions will not be described with further details as certain ways of implementing them are known to the person ordinarily skilled in the art.

As the base to achieve the object mapping administration functions add and maintain in the database profiles for each Terminal Equipment type containing all the objects supported by such Terminal Equipment. Objects within the profile are structured so that objects belonging to a same logical group are grouped together and objects can be sequenced in a particular way within a logical group. A careful design of the profile structure greatly helps the Abstraction Layer implementation to become highly generic. An example of a set of objects in a particular logical group in relation to E mail service is given further down and described in connection with .

Using Terminal Equipments characteristics make model and if applicable operating system version and or device management client version the Abstraction Layer queries the database and its profiles to determine which device management protocols are supported by the specific Terminal Equipment for which a device management request has been received. In case of more than one protocol being supported the Abstraction Layer makes a selection of one protocol to fulfill the request. Selection criteria are not described here as not being core to the invention and may be devised by the person ordinarily skilled in the art. The selected protocol in turn determines which management protocol server is to be invoked. In this case we will assume server and its API .

For the selected particular device management protocol Terminal Equipment functions are represented by sets of objects that vary in scope different set of parameters for the same function or implementation different object address for a parameter supporting the same function the Abstraction Layer further performs a mapping of the generic device management request to the actual object implementation in the specific Terminal Equipment as received through . The Abstraction Layer API s role is thus to expose abstracted services to Terminal Equipment management applications.

E mail is another example of a service that is being offered by telecommunications operators and service providers. An example of an abstract service request is here configureEmail accompanied by the list of parameters requested to be configured. The description is now continued in relation to this particular second service and business process and in connection with .

The Terminal Equipment is characterized by its make A model X its operating system version 3.6 and its device management client version 1.1 listed in the profile. The supported protocol for this profile is OMA DM .

A label column gives a set of human readable labels one per listed object. This set of labels is the same throughout all profiles in the database.

A key column gives a set of unique identifiers one per listed object. These keys or identifiers are used for communication between Abstraction Layer API and Customer Care application . This set of keys is the same throughout all profiles in the database.

A Terminal Display column gives a corresponding entry in the Terminal Equipment display menus if one exists.

An Object Address column gives an address for the one objects supported both by the Terminal Equipment and the protocol.

Other columns Max Occurrences Allowed Values Access Type provide for certain other attributes of the object.

The Terminal Equipment is characterized by its make A model X and its operating system version 3.6 listed in the profile. The supported protocol for this profile is OMA CP .

Then the next four columns Object Address Max Occurrences Allowed Values Access Type give entries specific to the combination Terminal Equipment protocol.

The Terminal Equipment is characterized by its make B model Y its operating system version 2.2.5 and its device management client version 1.1 listed in the profile. The supported protocol for this profile is OMA DM .

A Terminal Display column gives a corresponding entry in the Terminal Equipment display menus if one exists.

Then the next four columns Object Address Max Occurrences Allowed Values Access Type give entries specific to the combination Terminal Equipment protocol.

Not all columns and information as laid out in are necessary for the invention to be operational at a minimum a characterization of the Terminal Equipment is necessary make model operating system version or device management client version as well as supported remote management protocol as well as the Key information and the Object Address information.

Service providers will offer using the device management system according to the invention a service of setting parameters in the installed base of Terminal Equipment of their customers. This is made possible because the APIs of customer s servers if any are either published by servers manufacturers or communicated to the service provider by its customers. Service providers have to include and maintain database profiles for each one of the various Terminal Equipments present in the installed base of their customers this is made possible because Terminal Equipments characteristics are published or may be retrieved by polling the network with means that are not described here but are within reach of the person ordinary skilled in the art.

Although illustrative embodiments of the present invention have been described herein with reference to the accompanying drawings it is to be understood that the present invention is not limited to those precise embodiments and that various other changes and modifications may be effected therein by one skilled in the art without departing from the scope or spirit of the invention. All such changes and modifications are intended to be included within the scope of the invention as defined by the appended claims.

