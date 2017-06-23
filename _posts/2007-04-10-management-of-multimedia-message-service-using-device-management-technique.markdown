---

title: Management of multimedia message service using device management technique
abstract: A technique for remotely managing a message service of a terminal (device) is disclosed. Resources or parameters, especially for parameters related to a message service, of the terminal are provided in the form of a tree to a device management server, so that the device management server can remotely manage the message service of the terminal.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=07912970&OS=07912970&RS=07912970
owner: LG Electronics Inc.
number: 07912970
owner_city: Seoul
owner_country: KR
publication_date: 20070410
---
The present invention relates to a message service and more particularly to a technique for remotely managing a message service in a terminal device .

A message service is a technology allowing a user to transmit or receive a message to or from another party through a fixed line terminal or a mobile terminal. The message service includes a short message service SMS an enhanced message service EMS and a multimedia message service MMS etc. Recently the MMS which allows users to attach diverse multimedia such as text photos video or audio into a message and transmit and receive it is commonly used.

In order to execute the message service in the terminal the terminal should have a message client and various set parameters. First in order to allow the terminal to be connected with a network information or set values for connectivity should be set in the terminal. In addition various parameters that can be adjusted e.g. a parameter for reporting whether a recipient has received a message after the message is transmitted can be set in the terminal.

Therefore in order to address the above matters the various features described herein have been conceived. An aspect of the exemplary embodiments is to manage a message service of a terminal through device management DM techniques. Here the DM is a technique by which a particular device or client e.g. a terminal for which DM is to be performed provides its resources or parameters set values in the form of a tree or other hierarchical logical structure to a DM server and the DM server accesses and manages the desired resource s or parameter s of the tree.

This specification provides a method for managing a message service of a terminal that may include configuring a management object related to a message service in the form of a tree receiving a request for providing the management object related to the message service from a DM server and providing the tree of the management object to the DM server.

This specification also provides a method for managing a message service that may include providing a management object related to a message service to a DM server receiving a request for updating a parameter of the management object from the DM server and updating the parameter of the management object according to the request.

This specification also provides a terminal that may include a management object that comprises at least one among a first node that allows an application of the terminal to refer to a connectivity parameter for a message service and a second node that designates a URL Uniform Resource Location of an MMS Proxy Relay and an enabler that allows a device management DM server to access the management object.

This specification also provides a device management DM server that may include a transmitting receiving unit that receives from a terminal a management object related to a message service in the form of a tree structure and a processor that checks the received management object and selectively requests the terminal to update a parameter of the management object through the transmitting receiving unit.

This specification also provides a server that may include an enabler that receives a management object in the form of a tree from a terminal that includes at least one among a first node that allows an application of a terminal to refer to a connectivity parameter for a message service and a second node that designates a URL Uniform Resource Location of an MMS Proxy Relay and accesses the management object.

The foregoing and other objects features aspects and advantages of the present invention will become more apparent from the following detailed description of the present invention when taken in conjunction with the accompanying drawings.

The exemplary embodiment of the present invention will now be described in detail with reference to the accompanying drawings.

In the attached drawings although a terminal is shown as an example such depicted terminal may also be referred to in terms of other expressions such as user equipment UE mobile equipment ME etc. In addition the terminal can be a portable device such as a notebook computer a mobile phone a PDA Personal Digital Assistant a smart phone a multimedia device etc. or can be a non portable device such as a PC or a vehicle mounted device.

As shown in a terminal is wirelessly connected with an MMS Multimedia Message Service Proxy Relay for transmission and reception of a multimedia message MM and also wirelessly connected with a DM server for management.

The terminal may include a DM enabler client an MMS client a task execution module and a management object .

The DM enabler client is connected with the MMS client the task execution module and the management object to provide interface with the DM server for DM. For example the DM enable client may report a state of the MMS client to the DM server or may receive a request for updating software of the MMS client from the DM server . In addition the DM enabler client may provide the management object in the form of a tree to the DM server or receive a request for updating the management object from the DM server .

The MMS client may be an element for an MMS and may be implemented as software. The MMS client transfers a multimedia message MM created by a user to the MMS Proxy Relay such that the message can be transmitted to another party.

The MMS client receives a message from an arbitrary originator sender through the MMS Proxy Relay . The MMS client may be connected with the DM enabler client and report its state to the DM server as mentioned above. In addition the MMS client may be connected with the management object to read a parameter of the management object and drive a multimedia message service according to the parameter.

The task execution module is connected with the DM enabler client and the management object . The task execution module may perform several operations for device management according to a request of the DM server . For example the task execution module may update several software of the terminal or firmware according to a request of the DM server . Namely as mentioned above the task execution module may update software of the MMS client according to a request of the DM server .

The management object may include resources of the terminal or a parameter set value . Namely the management object includes several parameters for allowing the MMS client to drive the multimedia message service. Resource or parameters existing in the management object is provided in the form of a tree by the DM enabler client to the DM server and the DM server accesses the terminal through the tree. In this case the DM server may access only a desired resource or parameter in the management object rather than every parameter stored in the management object . The DM server may modify delete and update only a desired parameter. The management object will now be described in detail with reference to .

The DM server includes a DM enabler server . The DM enabler server receives the management object in the form of a tree from the terminal and accesses the management object. In addition the DM enabler server may request the terminal to update a parameter of the management object.

The DM enabler server may receive a report on a state from the MMS client of the terminal . In addition the DM enabler server may request updating of an application of the terminal e.g. software of the MMS client .

Thus far the terminal of the present disclosure has been described to include the DM enabler client the MMS client the task execution module and the management object . However but without being limited thereto these elements may also be implemented as a combination of a processor a communication module also called a transmitting receiving unit or a network interface and a storage unit.

Likewise the DM server according to the present invention may also include a combination of a processor not shown a communication module also called a transmitting receiving unit or a network interface and a storage unit not shown .

As shown in a management object including several parameters for a multimedia message service may have the form of a tree. The management object will now be described in detail.

a A node serves as a place holder for the multimedia message service in the management object . There may exist one or more nodes.

b A NAME node includes the name of the MMS Proxy Relay that can be read by a user. Thus the format of the Name node comprises letters text . One or more NAME nodes may exist in the management object.

c A MMS Release node indicates a version of a multimedia message service supported by the MMS client . The format of the MMS Release node comprises letters text .

d A Provider ID node indicates an identifier of a provider of the multimedia message service. The format of this node comprises letters text .

e A ToConRef node allows an application of the terminal e.g. the MMS client to refer to a connectivity parameter for the multimedia message service. The ToConRef node includes a node. The node serves as a place holder for the connectivity parameter. One or more nodes may be included in the ToConfRef node. A ConRef node may be included at a lower position of the node. The ConRef node specifies a specific linkage to the connectivity parameter. The ConfRef node points to the right connectivity identity NAP ID and a WAP gateway.

g A CM node also called CreMode specifies a creation mode supported by the MMS client . Namely the CM node designates a mode used for creating and transmitting a new multimedia message MM . In other words this leaf node specifies the creation mode used for creation and submission of a new multimedia message. This mode includes three types of modes R RESTRICTED W WARNING and F FREE modes. In the RESTRICTED mode R the terminal may only create multimedia messages MMs belonging to a Core MM Content Domain. In WARNING mode W a terminal may guide the user to create and submit only multimedia messages MMs belonging to the Core MM Content Domain. In other words in the WARNING mode a user is informed that the terminal may generate or transmit only multimedia messages belonging to a particular domain e.g. belonging to the Core MM Content Domain .

h A RM node designates a re submission mode supported by the MMS client . Namely this leaf node specifies the re submission mode used for submission of an earlier retrieved multimedia message . In other words the RM node designates the re submission mode used for submission of an earlier restricted multimedia message. The RM node may specify three types of modes R RESTRICTED mode W WARNING mode and F FREE mode. Here the re submission follows the creation mode when the creation mode is set to WARNING or FREE. In other words the re submission mode follows the transmission mode when the transmission mode is set to the WARNING mode or the FREE mode. In the RESTRICTED mode R the terminal may only re submit multimedia messages belonging to the Core MM Content Domain. In other words the terminal may only re transmit multimedia messages belonging to the core MM content domain. In the WARNING mode W the terminal may guide the user to re submit only multimedia messages belonging to the core MM Content Domain . In other words the terminal informs the user that only the multimedia messages belonging to the core MM content domain can be re transmitted. In the FREE mode the terminal may allow the user to re transmit any earlier retrieved MM.

i A Retrieval Mode node specifies a method that the MMS client receives retrieves the multimedia message. The Retrieval Mode node may specify one of the Retrieval Mode Automatic mode or Manual mode. In the Manual mode a user confirmation is first made before receiving a message.

j A MMSA node indicates an interface state between the MMS client and a different application of the terminal .

k An Expiry Time node indicates expiry time information related to transmission of a message. The Expiry Time node includes a Time Value node and a Time Formation node. The Expiry Time Time Value node designates specifies a time value indicating until when a message transmitted by the MMS client can be stored in the MMS Proxy Relay or when it should be deleted. The Expiry Time Time Format node designates the format of a time value designated in the Time Value node. Namely The Expiry Time Time Format node has an absolute or relative value.

l A Sender Visibility node allows an identity of a sender to be provided to a recipient or to be hidden. This node has a value of hide or show.

m A Delivery Report node designates whether to report the sender whether or not the recipient has received a message. The value of the Delivery Report node can be designated by Yes or No.

n A Read Report node designates whether to report to the sender whether or not the recipient has read the message. The value of the Read Report node can be designated by yes or no .

o A Store node indicates information related to storing the message in a multimedia message box. The Store node includes a Store Value node and a MM State node. The Store Value node of the Store node designates whether or not a message which has been transmitted is stored in the multimedia message box. The MM State node of the Store node indicates a state of the stored message. The MM State node may indicate a state of being drafted a sent state a new state a received state retrieved state or forwarded state .

p An Adaptation Authorization node indicates whether the multimedia message can be converted i.e. the Adaptation Authorization node specifies the X Mms Adaptation Allowed field of the send request e.g. it indicates whether the MMS client authorizes an MM to be adapted or not .

4 A PCAddr node or an address of Postcard service node designates an address of a postcard i.e. the PCaddr node defines an address for postcard service to be used as the recipient of multimedia message that includes a postcard . Here the postcard service refers to allowing the user to add a previously defined phrase or image at a lower end portion of the message when sending the message. The postcard service is also called vCard service.

In the above description the management object with respect to the multimedia message is shown in the form of a tree. The above described nodes may not be all necessarily included but can be reduced extended or changed by a person in the art. In addition the names of the above described nodes can be changed by the person in the art.

As shown in in the DM method according to the present invention the DM server may search and modify a parameter related to the multimedia service of the terminal .

2 The DM enabler client accesses the management object to search the parameter requested by the server .

As so far described the method according to the present invention can be implemented by software hardware and their combination. For example the method according to the present invention can be stored in a storage medium e.g. an internal memory of a mobile terminal a flash memory a hard disk etc. and can be implemented as codes and command languages in a software program that can be executed by a processor e.g. an internal microprocessor of the mobile terminal .

Because the resources or parameters of the terminal in particularly the parameters related to the message service can be provided in the form of a tree to the DM server the DM server can remotely manage the message service of the terminal. In addition because only resources or parameters desired by the DM server among all the resources and parameters of the terminal is provided to the DM server and the DM server can adjust them the network load and communication costs can be reduced.

In the above description the multimedia message is taken as an example but without being limited thereto the present invention can be also applicable to a short message service SMS an enhanced message service EMS etc.

As the present invention may be embodied in several forms without departing from the spirit or essential characteristics thereof it should also be understood that the above described embodiments are not limited by any of the details of the foregoing description unless otherwise specified but rather should be construed broadly within its spirit and scope as defined in the appended claims and therefore all changes and modifications that fall within the metes and bounds of the claims or equivalents of such metes and bounds are therefore intended to be embraced by the appended claims.

