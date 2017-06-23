---

title: Method and systems for bandwidth scheduling and path computation for connection-oriented networks
abstract: A connection-oriented network includes a control server. The control server receives requests to establish and utilize dedicated channels in the network. The control server utilizes various scheduling methods and algorithms to determine channels based on the request's requirements and resources of the network. For example, the control server may determine a channel based on: (i) a specified bandwidth in a specified time slot, (ii) highest available bandwidth in a specified time slot, (iii) earliest available time with a specified bandwidth and duration, and (iv) all available time slots with a specified bandwidth and duration.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08144686&OS=08144686&RS=08144686
owner: UT-Battelle, LLC
number: 08144686
owner_city: Oak Ridge
owner_country: US
publication_date: 20070420
---
This invention was made with government support under NSF Grant No. CCR9912395. The United States Government has certain rights in the invention.

A number of large scale science and commercial applications produce large amounts of data on the order of terabytes to petabytes that must be transported across wide area networks. For example large simulation data sets produced by science application such as eScience application on supercomputers may be archived at a remote storage site or bank transaction records or inventories of large department stores may be synchronized with remote storage during off peak hours.

When data providers and consumers are geographically distributed dedicated connections are needed to effectively support a variety of remote tasks including data mining data consolidation and alignment storage visualization and analysis. The dedicated bandwidth channels offer large capacity for massive data transfer operations and dynamically stable bandwidth for monitoring and steering operations. It is important that these channels be available when the data is or will be ready to be transferred at a particular time. Thus the ability to reserve such dedicated bandwidth channels either on demand or in advance is critical to both data transfer operations.

An embodiment of the present disclosure is directed to a system for controlling access to a network. The system comprises an input for receiving a request to establish a dedicated channel in a network. The request comprises at least one of a bandwidth for the channel and duration of the channel. The system further comprises a bandwidth scheduler coupled to the input for determining a path of the channel across the network based request and resources of the network and a signaling daemon for generating a control signals based the determined path.

Another embodiment of the present disclosure is directed a method for transferring data. The method comprises receiving a request to establish a dedicated channel in a network. The request comprises at least one of a bandwidth for the channel a start time for the channel and a duration of the channel. The method further comprises determining a path of the channel across the network based on the request and resources of the network and scheduling the channel based on the determination.

Another embodiment of the present disclosure is directed to a computer. The computer comprises a processor and an input coupled to the processor. The input receives a request to establish a dedicated channel in a network. The request comprises at least one of a bandwidth for the channel a start time for the channel and a duration of the channel. The computer further comprises a memory coupled to the processor and input. The memory contains instructions for causing the processor to determine a path of the channel across the network based on the request and resources of the network and schedule the channel based on the determination.

Additional embodiments of the disclosure will be set forth in part in the description which follows and in part will be obvious from the description or may be learned by practice of the present disclosure. The embodiments of the disclosure will be realized and attained by means of the elements and combinations particularly pointed out in the appended claims.

It is to be understood that both the foregoing general description and the following detailed description are exemplary and explanatory only and are not restrictive of the invention as claimed.

According to embodiments of the present disclosure systems and methods are directed to determining and scheduling dedicated channels in a connection oriented network. The connection oriented network includes a control server. The control server receives requests to establish and utilize dedicated channels in the network. The control server utilizes various scheduling methods and algorithms to determine channels based on the request s requirements and resources of the network. For example the control server may determine a channel based on i a specified bandwidth in a specified time slot ii highest available bandwidth in a specified time slot iii earliest available time with a specified bandwidth and duration and iv all available time slots with a specified bandwidth and duration.

Reference will now be made in detail to the exemplary embodiments of the present disclosure an example of which is illustrated in the accompanying drawings. Wherever possible the same reference numbers will be used throughout the drawings to refer to the same or like parts.

In the following description reference is made to the accompanying drawings that form a part thereof and in which is shown by way of illustration specific exemplary embodiments which may be practiced. These embodiments are described in sufficient detail to enable those skilled in the art to practice the embodiments and it is to be understood that other embodiments may be utilized and that changes may be made without departing from the scope of the invention. The following description is therefore merely exemplary.

Network backbone provides high speed and large bandwidth for data transfers over geographical distances. Network backbone may provide dedicated channels for data transfer to systems and users located in sub networks and coupled to network backbone .

Network backbone includes core switches and data lines . Core switches allow dedicated channels to be established through network backbone . Core switches may be geographically distributed with data lines connecting core switches over the geographic distances. Core switches may be any type of well known hardware software and combination thereof to interconnect data lines and to control the flow of data at layer or physical layer in an OSI network hierarchy of data lines . For example core switches may be a multiplexing switch add drop cross connect switch and the like.

Data lines may be any type of physical connection such as electrical wires optical fiber and the like wireless connection and combinations thereof to transfer data over geographic distances. For example data lines may be optical fibers with core switches utilizing synchronous optical networking SONET to control data in network backbone .

Sub networks and may be connected to network backbone in any suitable manner to allow a requester in the sub networks to request access and utilize a dedicated channel of network backbone . One skilled in the art will realize that any number of sub networks or devices may be connected to network backbone .

Sub network may include a server and clients . Server may be coupled to one of core switches . Server may include a network interface card that directly communicates with core switch . Server may provide further network resolution to clients . For example server may provide layer and layer network services in an open system interconnection OSI network hierarchy to clients to allow clients to request access and utilize dedicated channels in network backbone .

Sub network may include a network switch a server and clients . Network switch may be coupled to one of core switches . Network switch may be any type of hardware software or combination thereof to support network protocols at layer and layer to allow a connection to network backbone . For example network switch may be an Ethernet switch and the like. Network switch may be coupled to one of core switches .

Server may be coupled to network switch . Server may provide further network resolution to clients . For example server may provide additional layer and layer network services to clients to allow clients to request access and utilize dedicated channels in network backbone .

Sub network may include a provisioning platform and a server . Provisioning platform may be coupled to one of core switches . Provisioning platform may be any type of hardware software or combination thereof to support network protocols at layer to allow connection to network backbone .

Sub network may include a router a server and one or more clients . Router may be coupled to one of core switches . Router may be any type of network hardware software or combination thereof to receive and forward data from server and clients onto network backbone .

In the above sub network servers and and clients and may be implemented using a variety of devices software and combinations thereof. For example the clients and servers may be implemented on a personal computer workstation terminal and the like. In addition the clients and servers may run under an operating system such as the LINUX operating system the MICROSOFT WINDOWS operating system and the like. The clients and servers may also operate network applications for supporting communicating with networks and transferring data such as web browsers and servers file clients and hosts ftp client and hosts and the like.

One skilled in the art will also recognize that servers and and clients and may be implemented with various peripheral devices such as a display one or more speakers and other suitable devices. Servers and and clients clients client and client may also be implemented with various peripherals for accepting input from a user such as a keyboard a mouse and the like.

Although shows several sub networks one skilled in the art will realize that network may include any number of sub networks. Further one skilled in the art will realize that the sub networks may also be additional or fewer network hardware such as switches and routers servers and clients.

Network backbone provides high speed and large bandwidth for data transfers over geographical distances. Network backbone provides dedicated channels for data transfer to requesters located in sub networks and coupled to network backbone . Any of the clients and servers may become a requester to request access and utilize the dedicated channels. In order to utilize the dedicated channels any requester can request a dedicated channel from control server .

Control server may be a separate and stand alone computer system capable of determining and allocating dedicated channels in network backbone . Control server may be coupled to any one of core switches . Control server may receive requests for dedicated channels in network backbone from sub networks and . Alternatively the functions of control server may be performed by any one of servers and . Further any of control server and servers and may function cooperatively to determine dedicated channels.

Control server may include any necessary hardware software and combination thereof to receive requests for use of dedicated channels from sub networks and . Control server may include any necessary hardware software and combination thereof to determine the channel allocations on network backbone . Control server may include any necessary hardware software and combinations thereof to generate configuration signals for core switches to establish and destroy the dedicated channels.

Since control server controls all access to network backbone control server may only process requests from authorized requesters such as servers and clients. Control server may employ any type of well known secure authorization system such as secure login digital signatures cryptographic verification and the like to establish the authenticity of a requestor.

Additionally the data connection from requesters to control server may also be secure to prevent interception and tampering with dedicated channel requests. For example the data connection from requestors to control server may be a secure connection such as virtual private network VPN virtual local area network VLAN and the like. In the secure connection the data transmitted to and received from control server may be secured by any well known cryptographic techniques such as symmetric cryptography asymmetric cryptography digital signature and the like.

Server front end provides an interface for requesters for example clients and servers to request and reserve a dedicated channel on network backbone . Server front end may be implemented in hardware software and combinations thereof. For example server front end may be a web server for providing web services to the requesters such as clients and servers. The web services provide a web based interface for the requester to request and reserve a channel on network backbone .

The request received by control server may include identity information of the requestor and different information about the requirements for the channel. The identity information may include a login name and password. The requirements information may include the location of the client or host the destination of the data the bandwidth requested and the time period for the channel.

Returning to server front end may also provide an interface for administrators of control server to add and modify information about the structure of network . For example server front end may be a web server for providing web services to the administrators. The interface provides a web based interface for the requestor to add and remove devices of network . Additionally the interface may allow administrator to add information about network such as bandwidth of the links. Server front end may be coupled to database . As such server front end may store information about the structure of network in database .

Requestor management unit provides an interface for registering requestors such as clients and servers allowed to request and reserve a channel on network backbone . Requestor management unit may register clients and servers as requestors by receiving identity information from the clients and servers. Requestor management unit verifies the information provided by the clients and servers.

Requestor management unit may be coupled to database . Once the requestor is verified the identity information may be stored in database . Server front end may retrieve the identity information from database in order to authenticate the requestors requesting and reserving channels on network backbone .

Token management unit may provide further authentication and access control if control server requires a secure connection in order to request a channel. For example token management unit may control the authentication and access control if control server utilizes a secure connection such as VPN or VLAN.

Bandwidth scheduler receives the authenticated request from server front end . Bandwidth scheduler determines and schedules an available channel based on the requirements of the request. Bandwidth scheduler may allocate the available bandwidth to the dedicated channels in time and space. Bandwidth scheduler may determine the dedicated channel based on two types of requests and based on the current availability of bandwidth 

 a On demand request a connection request for an immediate dedicated channel. Bandwidth scheduler may accept or deny the request depending on the current bandwidth availability and

 b In advance request a connection request for future dedicated channels. Bandwidth scheduler may determine and allocate the dedicated channel based on bandwidth allocation schedules.

Bandwidth scheduler may be coupled to database . Bandwidth scheduler may retrieve data from database about network and the requestor. For example bandwidth scheduler may retrieve information such as the structure and devices in network and the sub networks current channels and bandwidth usage on network future scheduled dedicated channels location and identity of the requester and the like.

According to embodiments of the present disclosure in order to determine a channel s availability bandwidth scheduler may utilize various scheduling methods and algorithms depending on the request. Bandwidth scheduler determines a channel by receiving the source and destination of the channel. The source may be location in the network of the requestor. The destination may be the ending point in the network of the channel i.e. the location in the network were the requester may transmit data . Bandwidth scheduler may determine a channel by determining a path or slot across network based on the request requirements and the resources of network . The path may be the different devices such as switches routers computers and the like and data links through which the channel would be established.

For example a dedicated channel from a given source to a given destination based on the request requirements and one or more of i a specified bandwidth in a specified time slot ii highest available bandwidth in a specified time slot iii earliest available time with a specified bandwidth and duration and iv all available time slots with a specified bandwidth and duration.

Once a dedicated channel is determined bandwidth scheduler may generate the appropriate scripts to implement the dedicated channel over network . Bandwidth scheduler may store the scripts in database .

Once a dedicated channel has been determined signaling daemon may invokes appropriate scripts to set up or tear down the channels in the network for the determined channel. Signaling daemon may be coupled to database . Signaling daemon may retrieve the scripts from database . Signaling daemon may transmit the scripts to the components of network such as core switches .

Database may maintain information regarding the structure of network the identity of clients and servers in network the determined channels in network the available bandwidth and the like.

Control server may be implemented using a variety of devices software and combinations thereof. For example control server may be implemented one or more computing platforms such as personal computer workstation terminal and the like. Control server may include the standard components of a computing platform such as a processor memories busses input output ports network interface cards and the like.

In addition control server may run under an operating system such as the LINUX operating system the MICROSOFT WINDOWS operating system and the like. The various components such as server front end requester management unit token management unit bandwidth scheduler and signaling daemon of control server may be implemented as software applications stored in memory in control server and executed by the processor of control server . The software applications may be written in a variety of programming languages such as C C Java etc. Database may be implemented using well known database technology such as relational databases or object oriented databases.

Control server also may be implemented with various peripheral devices such as a display one or more speakers and other suitable devices. Control server may also be implemented with various peripherals for accepting input from a user such as a keyboard a mouse and the like.

While illustrates a single system performing the functions of control one skilled in the art will realize that multiple control servers may cooperatively operate together to perform the functions of control server . Further one skilled in the art will realize that the component of may be embodied one than one computing platform.

Control server controls the scheduling determination creation and management of dedicated channels in network . is a flow diagram illustrating a method for receiving requests for dedicated channels and determining a dedicated channel based on the requests.

Method begins with control server receiving a request for a dedicated channel stage . For example a requester such as a client or server in the sub networks may access an interface hosted by server front end . In the interface the requestor may enter the information regarding the requested dedicated channel.

The request may include all necessary information in order to determine and establish the channel. For example the request may include the identity of the requester and the requirements of the dedicated channel. The identity information may include a login name and password. The requirements of the dedicated channel may include requested bandwidth the source and destination of the channel the start and end time of the dedicated channel and the duration of the dedicated channel.

Then control server authenticates the requester based on the identity information in the request supplied by the requestor stage . For example control server may authenticate the requester by retrieving stored identity information for the requestor and comparing the information with the supplied identity information. If the information does not match the request may be denied by control server .

Next control server determines a dedicated channel based on the requirement information supplied by the requester stage . According to embodiments of the present disclosure in order to determine a channel bandwidth scheduler may utilize various scheduling methods to determine a path across the network. For example a dedicated channel from a given source the location of the requestor to a given destination the destination of the data may be based on i a specified bandwidth in a specified time slot ii highest available bandwidth in a specified time slot iii earliest available time with a specified bandwidth and duration and iv all available time slots with a specified bandwidth and duration.

The particular method utilized may depend on the type of dedicated channel requested whether on demand or in advance and the requirements of the channel. Below are described several methods for determining the dedicated channel fixed slot largest bandwidth in a slot first slot first slot and all available slots and all available slot for all pairs. According to embodiments bandwidth scheduler may utilize one or more of the methods depending on the type of request.

In the scheduling methods network may be represented as a graph G V E where each node or vertex represents a device in network such as a switch for layers and router for layer and each edge represents a link such as in network . For each edge e E there exists a list of bandwidth reservations specified as a piecewise constant function of time. In terms of data structure G is represented using the cost array adjacency list representation and each edge has a list the TB list of time bandwidth pairs associated with it. Let t b . . . t b be the TB list associated with edge u v . The time bandwidth pairs t b are in ascending order of t. The pair t b is interpreted to mean that edge u v has bandwidth bavailable from time tto time t 1 t .

If the requester requests a dedicated channel for a fixed bandwidth for a fixed duration for a specified period of time bandwidth scheduler may utilize a fixed slot scheduling method to determine and allocate a path. In fixed slot bandwidth scheduler defines a path from a source vertex s to a destination vertex d. The path can have an available bandwidth of at least b from a pre specified start time t to the time t. Such a path may be called a feasible path.

According to embodiments of the present disclosure the fixed slot method is accomplished utilizing an extend breadth first search because a breadth first search finds a path from s to d with the fewest number of hops. is a flow diagram illustrating the fixed slot method consistent with embodiments of the present disclosure. Method begins with bandwidth scheduler receiving source s and destination d and bandwidth b start time t and end time t stage .

Next bandwidth scheduler computes a path utilizing an extended breadth first search stage . The extended breadth first search begins at vertex s and terminates either when vertex d is reached via a feasible path or when it is determined that there is no feasible path to d. In case a feasible path exists the reverse of the sequence d prev d prev prev d . . . s is one such path.

If a computed path exists bandwidth scheduler determines the path to be a feasible path stage . If no path is found bandwidth scheduler determines that no feasible path exists.

In accordance with embodiments of the present disclosure below is an example of pseudocode for the extended breadth first algorithm 

The extended breadth first search begins at vertex s and terminates either when vertex d is reached via a feasible path or when it is determined that there is no feasible path to d. In case a feasible path exists the reverse of the sequence d prev d prev prev d . . . s is one such path. The complexity of the extended breadth first search algorithm is O n L where n is the number of vertices in the network and L is the sum of the lengths of the TB lists.

If the requester requests a dedicated channel with the maximum available bandwidth for a given duration and given period of time bandwidth scheduler may utilize a largest bandwidth in a slot method to determine a path.

Next bandwidth scheduler determines bandwidth between s and all vertices and bandwidth between all vertices stage . Additionally bandwidth scheduler compares the determined bandwidths stage . Bandwidth scheduler may utilize a modified Dijkstra s shortest path algorithm to determine and compare the bandwidths. Based on the comparison bandwidth scheduler selects the path with the largest bandwidth stage .

Here b u v is the minimum bandwidth available on the edge u v during the specified interval slot and bw u is the maximum bandwidth along paths from the source s to vertex u under the constraint that these paths go through only those vertices to which a maximum bandwidth path has already been found. The complexity of the algorithm is O n for a general n vertex graph. However practical network graphs have O n edges and the complexity becomes O n log n when a max heap for example is used to maintain the bw values.

If the requester requests the first available path with a particular bandwidth for a particular bandwidth bandwidth scheduler may utilize a first slot method. is a flow chart illustrating the first slot method consistent with embodiments of the present disclosure. Method begins with bandwidth scheduler receiving source s and destination d and bandwidth b and duration T stage .

Then bandwidth scheduler generates a start time list stage . For each edge u v of the graph an ST start time list ST u v comprises pairs of the form a b a b. The pair a b has the interpretation for every start time x a b edge u v has an available bandwidth of at least b from time x to time x T. Bandwidth scheduler may generate the ST list such that pairs on an ST list are disjoint and in ascending order. Bandwidth scheduler may generate the ST lists may be constructed from the network resource information e.g. TB lists stored in database . Let a

In such a case the start time for the first slot with bandwidth b and duration T if such a slot exists must be one of these as. The first slot may be found by determining the smallest afor which there is an s to d path such that ais in an a b interval of every edge on the path.

Then bandwidth scheduler performs a breadth first search on the ST list stage . Bandwidth scheduler may perform a search such as the extended breadth first search described for the Fixed Slot method. The search uses only those edges that include ain one of their a b intervals. From the search bandwidth scheduler determines a feasible path with a start time or determines no path exists stage .

According to embodiments of the present disclosure exemplary pseudo code for the first slot algorithm may be 

In this algorithm for each edge u v of the graph an ST start time list ST u v comprises pairs of the form a b a b. The pair a b has the interpretation for every start time x a b edge u v has an available bandwidth of at least b from time x to time x T. The pairs on an ST list are assumed to be disjoint and in ascending order. The ST lists may be constructed from the TB lists in O L time. Let a

In such a case the start time for the first slot with bandwidth b and duration t if such a slot exists must be one of these as. The first slot may be found by determining the smallest afor which there is an s to d path such that as is in an a b interval of every edge on the path.

In the exemplary algorithm NewBFS does a breadth first search beginning at s. The search uses only those edges that include ain one of their a b intervals. The search returns true if a path from s to d is found. The array prev has the same significance as in the extended breadth first search algorithm for the fixed slot method.

Since the as are tried in ascending order and the a b pairs in the ST lists are also in ascending order it is possible to implement NewBFS so that the total running time of FirstSlot is O eq where e is the number of edges in the graph. Since e O n for real world networks the complexity is O nq . The actual s to d path for the first slot may be constructed in O n additional time using the prev values as described for the fixed slot algorithm.

In addition to the first path available at a particular bandwidth a requestor may desire to view all paths with the available bandwidth for a particular duration. Bandwidth scheduler may utilize a First Slot and All available Slots scheduling method.

Then bandwidth scheduler generates a start time list ST list stage . Next bandwidth scheduler generates a start time list for all paths stage . The concept of an ST list for an edge may be extended to that of an ST list for a path. Let st k u be the union of the ST lists for all paths from vertex s to vertex u that have at most k edges on them. As such st 0 u for u s and st 0 s 0 . Also st 1 u ST s u for u s and st 1 s st 0 s . For k 1 actually also for k 1 the following recurrence appears

where U and are list union and intersection operations. For an n vertex graph st n 1 d gives the start times of all feasible paths from s to d. Bandwidth scheduler may determine the extended ST list by employing an extension of the Bellman Ford algorithm to compute st n 1 d . This extension allows a determination of all available slots from s to d and provides an alternative algorithm for the first slot method as the earliest start time for a bandwidth b and duration t path from s to d is the a value of the first a b pair in st n 1 d .

The computation of the st s may be done in place i.e. st k u overwriting st k 1 u and the computation of the sts terminated when st k 1 u st k u for all u. As such bandwidth scheduler may utilize an extended Bellman Ford algorithm to compute st n 1 .

From the computation bandwidth scheduler determines several feasible paths meeting the requirements of the request or determines no path exists stage .

Each iteration of the for loop takes O l time where l is the length of the longest st list. Since this for loop is iterated a total of O ne times the complexity of the extended Bellman Ford algorithm is O nel . For real world networks with e O n this complexity is O nl . The described extended Bellman Ford algorithm is an early terminating variant of the Bellman Ford algorithm.

When using the extended Bellman Ford algorithm to solve the first slot problem first find the earliest start time t for a feasible path using Extended Bellman Ford. Then the actual path may be computed using the function for fixed slot with t t and t t T. In practice the first slot method of may be expected to be faster by expecting q

When a requestor desires to view all paths with the available bandwidth the requestor may also desire to see all available paths including different vertices that meet the bandwidth and duration requirements. Bandwidth scheduler may utilize an All available Slots for all Pairs method to achieve this.

Then bandwidth scheduler generates a start time list ST list stage . Next bandwidth scheduler generates a start time list for all paths between all vertices stage . The extended Bellman Ford algorithm of the fixed slot and all available slots computes st u st n 1 u for a given source vertex s and all u in O nel time. st u gives the start time of all available slots of duration d and bandwidth b. So in O nel using extended Bellman Ford algorithm all available slots from s to every other vertex u including vertex d can be determined.

To determine all available paths between all pairs of vertices bandwidth scheduler may run the extended Bellman Ford algorithm n times once with each vertex as the source vertex s. So the time needed to determine all slots between all pairs of vertices is O nel . As alternative strategy to determine all available slots between all pairs of vertices bandwidth scheduler may utilize an extension of Floyd s all pairs shortest path algorithm.

From the computation bandwidth scheduler determines several feasible paths for all vertices meeting the requirements of the request or determines no path exists stage . As such the requester may choose to utilize a different source to establish the channel.

Here st u v is the ST list for paths from u to v. Initially st u v ST u v . On termination st u v gives all possible start times for paths from u to v.

The complexity of the extended Floyd algorithm is O nZ where Z is the length of the longest st list. Since the number of edges in a general graph is O n the worst case complexity of using the extended Bellman Ford algorithm to find all available slots between all pairs of vertices is more by a factor of n where n is the number of vertices than using the extended Floyd algorithm. However for network the number of edges in a network is O n and both algorithms have the same asymptotic complexity. Since the extended Bellman Ford algorithm has an early terminating feature it is expected to perform better than the extended Floyd algorithm when there are short paths i.e. a small number of edges relative to n 1 between pairs of vertices.

After the appropriate method is performed bandwidth scheduler determines if the computed path for establishing a channel meets the requirements of the request stage . Bandwidth scheduler may determine this by checking the results of one or more of the methods described above to determine if a path was found that meets the requirements of the request.

If the channel does not meet the requirements bandwidth scheduler denies the request and the requestor is notified stage . If a channel does meet the requirements bandwidth scheduler notifies the requestor that a path for the channel has been found stage . In the case that bandwidth scheduler determines multiple channels all slots methods the bandwidth scheduler may notify the requestor of the multiple channels and allow the requester to select a channel stage .

Then bandwidth scheduler generates the scripts to create the dedicated channel stage . Bandwidth scheduler then stores the scripts in database stage .

After the scripts have been stored in database signaling daemon may retrieve the scripts at the appropriate time and forward the scripts to the network components stage . If the request is on demand signaling daemon may immediately retrieve and forward the scripts. If the request is in advance signaling daemon may retrieve the scripts at the appropriate time and forward the scripts to the network components.

After the duration of the channel has passed signaling daemon may destroy or tear down the channel stage . Signaling daemon may destroy the channel by retrieving and forwarding the scripts to remove the channel from network .

Network including control server and method may be utilized in any setting in which large amounts of data need to be transmitted between dispersed geographic locations. For example network may be a network which interconnects various universities and scientific laboratories.

In such a setting sub network may be located on the campus of a university. Researchers may be conducting experiments using clients with server providing the network support for the sub network. During the course of experiments the researches may wish to share data with other institutions or utilize the computing resources of another institution.

For example sub network may be located at a national or international laboratory. Researchers may share data with the laboratory by requesting a dedicated channel in network for control server . Since the channel will be guaranteed a large bandwidth for fixed durations the researchers may efficiently share data with the laboratory or utilize the computing resources of the laboratory.

One skilled in the art will realize that network and control server are exemplary. The methods for establishing and controlling dedicated channels such as method and may be performed on any network structure by any suitable control system. For example the methods may be performed by any network structure and at any level of an OSI network architecture.

Other embodiments of the present disclosure will be apparent to those skilled in the art from consideration of the specification and practice of the invention disclosed herein. It is intended that the specification and examples be considered as exemplary only with a true scope and spirit of the invention being indicated by the following claims.

