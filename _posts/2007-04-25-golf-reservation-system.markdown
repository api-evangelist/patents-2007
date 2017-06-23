---

title: Golf reservation system
abstract: Embodiments of the present invention provide a golf reservation system. The golf reservation system may periodically poll tee-sheet systems to determine available inventory. The golf reservation system may use the results of these pollings for responding to a user request. Other embodiments may be described and claimed.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=07634426&OS=07634426&RS=07634426
owner: GolfNow, Inc.
number: 07634426
owner_city: Portland
owner_country: US
publication_date: 20070425
---
The present application is a non provisional application of provisional application No. 60 746 760 filed on 8 May 2006 entitled GOLF RESERVATION SYSTEM and claims priority to said provisional application. The specification of said provisional application is also hereby fully incorporated by reference in its entirety except for those sections if any that are inconsistent with this specification

Embodiments of the present invention relate to the field of online reservation systems more specifically to an online golf reservation system.

Golf reservation systems may facilitate reserving tee times for customers desiring to golf at a particular course at a particular time. Often reservation of a tee time may be made online over a wide area network WAN such as the Internet. While tee time requests and booking online may be relatively straightforward if the user knows which course is desired it may be complicated by a request to more than one course. A service processing such a request to more than one golf course may face challenges in providing the requested information to the user in a timely and efficient manner.

In the following detailed description reference is made to the accompanying drawings which form a part hereof wherein like numerals designate like parts throughout and in which is shown by way of illustration embodiments in which the invention may be practiced. It is to be understood that other embodiments may be utilized and structural or logical changes may be made without departing from the scope of the present invention. Therefore the following detailed description is not to be taken in a limiting sense and the scope of embodiments in accordance with the present invention is defined by the appended claims and their equivalents.

Various operations may be described as multiple discrete operations in turn in a manner that may be helpful in understanding embodiments of the present invention however the order of description should not be construed to imply that these operations are order dependent.

For the purposes of the present invention the phrase A B means A or B. For the purposes of the present invention the phrase A and or B means A B or A and B . For the purposes of the present invention the phrase A B means B or AB that is A is an optional element.

The description may use the phrases in an embodiment or in embodiments which may each refer to one or more of the same or different embodiments. Furthermore the terms comprising including having and the like as used with respect to embodiments of the present invention are synonymous.

Embodiments of the present invention provide an online golf reservation system OGRS that may allow a user to search and subsequently book if desired available tee times for a plurality of golf courses in an efficient timely manner.

The user portal may be coupled to the computer network via a communication interface and may include a web browser configured to render web pages of a website hosted by the NBGS on user interface . The website may allow the user to interact with the NBGS and ultimately tee sheets and of various golf courses as will be described in further detail below.

The tee sheets and may include inventory management applications relied upon by golf courses to manage their tee time inventory. In various embodiments the tee sheets may include database management systems DBSs such as but not limited to Oracle database Microsoft SQLServer a Java DBS etc. and may be implemented in any of a number of different ways.

The tee sheets may be implemented at a client golf course s device to control that golf course s inventory. The tee sheet may include a user interface a communication interface and a database . As shown all of the components of the tee sheet are embodied in the device however in other embodiments components of the tee sheet may be distributed through a computing cluster.

A user e.g. a golf course employee may interact with the managed inventory of the database through the user interface . The communication interface which may include various hardware and or software components may provide a mechanism for communications between the tee sheet and the NBGS via the computer network .

The tee sheet may be implemented through use of an application service provider ASP . The ASP may include a database to store and manage the inventory of a number of golf courses and a communication interface to provide a mechanism for communications between the tee sheet and the NBGS via the computer network .

In various embodiments the communication interfaces and may include application programming interfaces APIs configured to allow for an exchange of information between the respective tee sheets and and the NBGS .

The ASP may host an inventory management application for client golf courses which may be coupled to the ASP through devices and . The devices and may have respective communication interfaces and to facilitate coupling to the ASP via respective communication links. The ASP may provide the inventory management application to user interfaces and through e.g. web pages. In this embodiment the inventory may be stored and processed at the ASP .

Communication links are shown coupling the various components to the computer network and the components of the tee sheet in . These communication links may be any combination of wired and or wireless links. Furthermore these communication links may also include one or more computer networks. For example the communication links shown coupling devices and to the ASP may include a WAN such as the Internet.

The NBGS may include a communication interface a controller an inventory database a cache and memory generally coupled to one another as shown. The memory may include instructions loaded from a storage medium which when accessed by the controller cause the NBGS to operate in manner described in embodiments of this invention.

In various embodiments the cache may be any repository of information and in some embodiments may be organized as a database used to store golf course inventory in a manner to facilitate the execution of search queries from the user portal . The inventory database on the other hand may be used to store golf course inventory in a manner to facilitate management and or manipulation of the data from the NBGS and or tee sheets and . In some embodiments the cache and inventory database may be combined into the same database.

Operations of the various components described above may now be described in the context of certain embodiments. Other embodiments not specifically described may nonetheless be implemented within the scope of the teachings disclosed herein.

In the present embodiment assume the initial search parameters include a selection of golf courses having the devices and for a 9 00 am tee time on an upcoming Saturday. In block the NBGS may run the parameters of the received request against the inventory stored in the cache .

If the cached inventory does not include an entry that satisfies request e.g. a cache miss the NBGS may generate and transmit a response to the user indicating the absence of the requested tee time in block .

If the cached inventory does include one or more entries that satisfy the request e.g. cache hit s the NBGS may generate and transmit a response to the user including cursory information about the cache hit s in block . In various embodiments various matching levels may be set. For example in an embodiment it may be determined that tee times within fifteen minutes of the requested time may be considered cache hits.

In an example embodiment the cached inventory includes a tee time of 9 05 am for the golf course having device and a tee time of 8 57 am for the golf course having device . Therefore cursory information about these two tee times may be returned to the user. The cursory information may be a subset of the total information about the inventory asset e.g. the tee time the golf course and the number of spots available.

The user may provide a focused request by selecting one of the cache hit s for further information e.g. 8 57 am at the golf course having the device . The NBGS may then receive the focused request in block . The NBGS may load the selected cache hit into the inventory database as a tee time entry and generate and transmit further details about the tee time entry to the user in block . Further details may include e.g. the price whether a golf cart is included etc.

If a user wishes to proceed with the transaction an appropriate selection may be made and the NBGS may receive a book request in block . At that time the NBGS may transmit a booking confirmation message to the device associated with the tee time entry e.g. device in order to confirm that the tee time is still available and if so reserve it for the user in block .

Embodiments shown and described provide a way for a user to search inventory of multiple golf courses through execution of queries against the cache of the NBGS . With relevant information stored in the cache requests may be handled primarily at the NBGS with the communications to the device at the golf course being limited to the confirmation booking phase. This may in turn facilitate a reduction in processing delays that may be associated with transmissions between the NBGS and the golf course device at the time of the user request.

The reduction in processing delays experienced in embodiments of this invention may be especially noticeable when an initial request is directed to more than one golf course while the focused request is directed to one golf course as is the case of the above discussed example . The initial request may be run against the cache without having to send multiple transmissions to multiple golf course devices. Once the user s selection has been pared down to one course a direct communication with the selected course may be performed.

In order to provide relevant information in the cache embodiments of this invention may employ dynamic caching. Dynamic caching as used in embodiments of this invention may provide that the rate at which the NBGS polls the client golf courses for available inventory is adjusted based on the lead time T of the inventory. As used herein lead time T may refer to the time between the present time and a particular tee time and AI T may refer to available inventory for a given lead time T.

So for example every hour the client golf courses may be polled for AI t 12 hours e.g. What tee times are available in the next 12 hours every other hour client golf courses may be polled for AI 12 hours

The dynamic caching taught in this embodiment may allow for more up to date inventory information being cached for periods most likely to be requested by the user and or have a change of state of the inventory e.g. as lead time T decreases .

As will be understood various embodiments may employ dynamic caching schedules having polling frequencies and time periods other than those shown in TABLE 1.

In an embodiment communication between tee sheets and and the NBGS may be initiated by the tee sheets and . This may be done to avoid complications due to security configurations e.g. firewall settings of tee sheets and . This may also facilitate routing as the communication interfaces and may have their network addresses e.g. IP addresses dynamically configured at each connection. Therefore in various embodiments the communication interfaces and or may be configured to periodically query the NBGS and leave open a communication channel for a predetermined time for a response from the NBGS . The response from the NBGS may include a polling of inventory a booking confirmation message etc. If the NBGS does not respond within the predetermined time the communication interface and or may close the communication channel until the next scheduled query.

Although certain embodiments have been illustrated and described herein for purposes of description of the preferred embodiment it will be appreciated by those of ordinary skill in the art that a wide variety of alternate and or equivalent embodiments or implementations calculated to achieve the same purposes may be substituted for the embodiments shown and described without departing from the scope of the present invention. Those with skill in the art will readily appreciate that embodiments in accordance with the present invention may be implemented in a very wide variety of ways. This application is intended to cover any adaptations or variations of the embodiments discussed herein. Therefore it is manifestly intended that embodiments in accordance with the present invention be limited only by the claims and the equivalents thereof.

