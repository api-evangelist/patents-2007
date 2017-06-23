---

title: Web gateway multi-carrier support
abstract: Wireless Internet gateway (WIG) providing multicarrier support that allows the gateway to send message to other peer gateways including a Message Distribution Center (MDS) trough which short messages are routed to other carriers based on carrier formats stored in a lookup table. Carrier format tables may be updated rather than employing an Internet gateway program thereby reducing downtime for updating, reducing the complexity of updates, and improving reliability during changes in a subscriber carrier. The WIG communicates with other carrier gateways utilizing different or varying protocols. Information regarding other carriers may be added, changed, and/or removed by modifying a configuration property file relating to the message format for other carriers, rather than by providing each carrier with its own class thereby avoiding a need to reprogram sending gateways.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09002951&OS=09002951&RS=09002951
owner: TeleCommunication Systems, Inc.
number: 09002951
owner_city: Annapolis
owner_country: US
publication_date: 20070925
---
This application is a continuation of U.S. application Ser. No. 09 716 944 to SMITH et al. entitled Web Gateway Multi Carrier Support filed on Nov. 22 2000 which is incorporated herein by reference.

This invention relates generally to wireless carriers Internet service providers ISPs and information content delivery services providers. More particularly it relates to gateways between a wireless network and the Internet for routing messages to wireless devices.

Short Message Service Centers SMSCs deliver short messages through wireless networks. Typically they operate on highly valuable server platforms that are protected deep within a wireless carrier s network and communicate via specialized protocols.

In particular as shown in a gateway implemented in a wireless network translates between HTTP protocol messages SMPP protocol messages and or email messages from wireless devices serviced by one Carrier s wireless network via an SMSC and devices serviced by another Carrier s wireless network through another gateway on the Internet .

Conventional gateway architecture provides a communication path between fixed protocol types e.g. between HTTP protocol messages and SMPP protocol messages based on known formats of destination Carriers. Separate gateway application programming interfaces APIs are developed to communicate with other protocol types and those separate API s are conventionally hard coded into the gateway .

For instance to pass communications from devices in the wireless network serviced by a first carrier to devices in another wireless network serviced by another carrier the gateway formats the messages in a way which is known to conform to the needs of the other carrier using the other gateway .

Unfortunately as any particular wireless carrier s resources change software updates may be required in a transmitting gateway to conform to the format of the newly changed receiving carrier s gateway. This requires the sending gateways to undergo a tremendous amount of development work as a result of the addition of new network elements particularly wireless network elements.

In conventional systems every carrier to which a short message may be transmitted to has its own class file. Thus if there are e.g. one hundred 100 carriers accessible from a particular wireless network then the gateway application code will necessarily include e.g. one hundred 100 class files one for each carrier.

Of course as time goes on some new carriers may enter a wireless network some existing carriers may change configurations and still other carriers may leave a wireless network. Each of these events relating to any of the carriers requires new or updated source code e.g. new java code in the sending gateway relating to a change in the relevant class file. This results in additional effort and or down time in the gateways of one or all gateways between wireless networks and the Internet to accommodate the changes and or additions to adjust the relevant application program class files.

There is a need for a technique and architecture to provide a unified means for routing message destinations to the gateways of other wireless carriers.

In accordance with the principles of the present invention a short message distribution center comprises an incoming message queue a carrier format table and a destination link. The carrier format table comprises information relating to a plurality of different carrier formats each relating to a destination gateway of a relevant destination carrier.

A method of abstracting destination carrier format from a wireless Internet gateway in accordance with yet another aspect of the present invention comprises receiving an incoming short message. Destination carrier information is retrieved from the incoming short message. Destination carrier format information is retrieved from a carrier format table based on a match to the retrieved destination carrier information.

Multi Carrier support is a feature of a wireless Internet gateway WIG that allows the WIG to send messages to any number of peer gateways on the Internet in a conveniently reconfigurable manner. In accordance with the principles of the present invention the WIG includes a Message Distribution Center MDC through which short messages can be routed to the gateways of other wireless carriers based on carrier formats stored in an abstracted carrier format table. The conventional technique of separate classes written for each carrier is replaced by entries in a look up table format to provide a more easily adaptable wireless gateway.

Thus in accordance with the principles of the present invention occasional updates of the carrier format table need only be updated rather than the wireless Internet gateway program reducing down time for updates reducing the complexity of updates and improving the reliability of a wireless Internet gateway in the face of changes for one or more carriers in a wireless network.

A suitable wireless Internet gateway is disclosed in co owned U.S. application Ser. No. 09 630 762 filed Aug. 2 2000 entitled Wireless Internet Gateway to Richard Smith the entirety of which is expressly incorporated herein by reference.

The present invention enables a WIG to communicate with the gateways of other carriers particularly other wireless carriers having different and occasionally changing kinds of message destinations using different and occasionally changing protocols.

In accordance with the principles of the present invention information regarding other carriers i.e. destinations may be added changed and or removed from a wireless short messaging system network by simply modifying a configuration property file relating to message formats for each other carrier rather than the conventional technique of providing each carrier with its own class avoiding the conventional need to reprogram relevant sending gateways.

In particular as shown in short messages of various protocols are received by respective protocol receivers and fed into a message queue . The various protocol receivers may relate e.g. to email HTTP get etc. A message distribution center portion of a wireless Internet gateway receives the queued short messages from the message queue e.g. on a first come first served basis.

The queued messages are interrogated by the message distribution center to determine their destination carrier. One appropriate interrogation method is e.g. in the case of a page or voice message to map the area code and exchange number of the destination telephone number to a particular carrier. This is performed in the area code exchange mapper in communication with the message distribution center .

The WIG may determine the destination gateway by the area code and exchange of the destination device NPA NXX . For example short messages to numbers beginning with 443994 are automatically routed to AT T Wireless Services . For devices with non 10 digit destination numbers e.g. some pagers standard numbers are prefixed to the actual destination in order to make it 10 digits.

In accordance with the principles of the present invention once a carrier is determined from the short message the preferred format and other carrier specific information is determined from a carrier format table . Then given the carrier specific information obtained from the carrier format table the messages are sent to a destination link for transmission via the appropriate protocol to the appropriate destination via the Internet .

In the disclosed embodiments the carrier format table includes a carrier property configuration file or carrier format file e.g. GWDEST.properties . The GWDEST.properties file is used to define carriers in a wireless short messaging system together with the particular properties that go along with each carrier.

While the present embodiment describes a carrier property file named GWDEST.properties the carrier format table may have any name within the scope of the present invention. The GWDEST.properties file specifies the various settings that are necessary to support a particular carrier.

The internal queue simply sends messages to a generic Interface which can be implemented in any number of ways. The interface defines basic messaging requirements such as sendTextMessage and makeConnection .

A WIG in accordance with the principles of the present invention is able to support multiple destinations carriers in an easily updatable fashion because the potential carrier destinations are internally abstracted away from their associated protocols. For the multi carrier support feature in accordance with the principles of the present invention the destination link interface transparently routes short messages to other destination objects representing each possible peer gateway. Peer gateway objects are created from classes that capture the underlying protocol to use. For example SMTP HTTP Post and HTTP Get.

The carrier format table configuration file preferably includes the universal resource locator URL and form field names together with information regarding whether the carrier is communicated with e.g. using HTTP GET HTTP POST or Email.

In the disclosed embodiment carrier specific properties of all carriers in a network are entered into the carrier format table e.g. into the GWDEST.properties file. The GWDEST.properties file may be updated on a periodic basis as necessary without the need to affect other operations of the gateway.

The following is an example configuration file called GWDEST.properties including destination information for seven 7 carriers. Of course the principles of the present invention relate to a configuration file containing fewer or many many more carrier entries e.g. hundreds. Note that the number of entries for each carrier may change depending upon the particular carrier.

To show the flexibility of the GWDEST.properties file and the carrier format table in general the following is an alternative entry for carrier No. 6 

Each carrier entry in the exemplary configuration file may start with the carrier s ID number as set in an appropriate database.

The ClassName currently takes one of three forms although additional forms may be possible. The ClassName relates to the method of communication to the relevant carrier.

In the disclosed embodiment a ClassName of GWDestHttpGet indicates that the carrier communicates with an HTTP GET command and handles carriers that use HTTP GET. A ClassName of GWDestHttpPost indicates that the carrier communicates with an HTTP POST command and handled carriers that use HTTP POST. A ClassName of GWDestEmail indicates that the carrier communicates via Email and handles carriers that use email.

The MaxLen parameter may be used to indicate the maximum length of the short message which may be supported by the relevant carrier.

X fieldNumY ourVariableName theirVariableName where ourVariableName can be any of the following types min callback subject message priority areaCode exchange extension phoneNumber and miscVar.

As disclosed the carrier s variables are mapped into the variables of the sending carrier. The sub parameter miscVar may be used for any variable that does not have a dynamically assigned value. When the URL is generated it is spit out as is.

In particular as shown in a message is sent by the sender to one of the protocol receivers as shown in message .

The message distribution center interrogates the message to determine the intended destination and looks up the particular destination from an appropriate database e.g. the area code exchange mapper as depicted in message .

In message the message distribution center delivers the message to the abstracted destination link for delivery to the relevant destination.

The present invention focuses on the use of a carrier format table by the destination link to obtain the appropriate format for the destination carrier. In particular multi carrier support relates to the definition and use of special classes in the Abstract Destination IGWSNLink that know how to deliver messages to various Peer wireless internet gateways using e.g. SMTP HTTP or other even future protocols.

The destination link includes a destination link cluster module a Gateway destination link module called GWDestLink IGWSNLink a GWDestResource and a Routing Database . The destination link also includes peer modules including a PeerDestination IGWSNLink which utilizes an appropriate format module e.g. Email Dest PeerGWDestination module which communicates via email Post Dest PeerGWDestination module which communicates via POST commands and Get Dest PeerGWDestination module which communicates via GET commands.

As shown in a message may be sent to the destination link GWDestLink . The message is sent using e.g. a sendTextMessage to the GWDestLink .

The GWDestLink aggregates many peer destinations. For instance the GWDestLink gets information from a GWDestResource to create a peer destination as shown in message . The GWDestResource may be used to dynamically create peer destinations and to assign attributes such as which servers to communicate with the format to use to communicate etc.

As shown in message the GWDestLink forwards the message to the appropriate peer destination which is to handle transmission of the message to another gateway over the Internet using the appropriate protocol e.g. Email HPPT post etc. which in turn provide an appropriate message to the PeerDestination IGWSNLink module .

The enabling WIG technology disclosed here allows short messages e.g. email voice mail HTTP post etc. to be transparently routed to the appropriate destination gateway using a configurable carrier format table. It also allows the message length to be formulated to reflect the destination e.g. a 400 character message can be sent in whole to a Bell South IPS pager whereas the same message would be split into 4 separate 100 characters messages when sent to a Sprint Phone.

While the invention has been described with reference to the exemplary embodiments thereof those skilled in the art will be able to make various modifications to the described embodiments of the invention without departing from the true spirit and scope of the invention.

