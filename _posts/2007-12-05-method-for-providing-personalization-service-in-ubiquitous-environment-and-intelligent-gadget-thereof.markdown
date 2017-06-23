---

title: Method for providing personalization service in ubiquitous environment and intelligent gadget thereof
abstract: Provided is a method for providing a personalization service in a ubiquitous environment and an intelligent gadget thereof. The intelligent gadget includes: a gadget service block for collecting and processing data to provide a personalization service; and a gadget interface block for forming a gadget network between gadgets and providing a cooperating service based on the collected and processed data.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=07822804&OS=07822804&RS=07822804
owner: Electronics and Telecommunications Research Institute
number: 07822804
owner_city: Daejon
owner_country: KR
publication_date: 20071205
---
The present invention claims priority of Korean Patent Application No. 10 2006 0124029 filed on Dec. 7 2006 which is incorporated herein by reference.

The present invention relates to a method for providing a personalization service in a ubiquitous environment and an intelligent gadget thereof and more particularly to a method for providing a personalization service in a ubiquitous environment which forms a gadget network actively changed by a gadget and provides the personalization service through interaction between gadgets and an intelligent gadget thereof.

This work was supported by the IT R D program for MIC IITA 2006 S 032 01 Development of an Intelligent Service Technology based on the Personal Life Log .

Recently an information processing technology and an information processing device have been remarkably developed. An information process based service is diversely applied to a daily life based on the information processing technology and the information processing device. The information process based service has a target of realizing a ubiquitous environment for providing a seamless service. Also many researches for providing a customized service have been progressed.

In the conventional researches described above each device on a network is expressed as a descriptor and a research on a service recreation required by a user by applying the descriptor has been progressed. The research is limited to rebuild a service applying a device descriptor by interruption of the user in a static network environment.

Also conventional researches include a research related to a procedure that a device in a personal network region determines handoff with an enterprise network. In the conventional researches the device in the enterprise network personal network region becomes a part of the enterprise network in handoff. Since the device in the enterprise network personal network region becomes the part of the enterprise network the conventional researches have a difficulty in maintaining a security.

The conventional researches also include a research on a set up procedure between two devices for data exchange between mobile devices in a personal network region and a research on a procedure that a device network is included in a personal region network or disconnected.

The many conventional researches related to cooperation with the personal region network and an external network and creation and performance of services according to active network change need to be continuously progressed.

An embodiment of the present invention is directed to providing a method for providing a personalization service in a ubiquitous environment which forms a gadget network actively changed by a gadget and provides the personalization service through interaction between gadgets and an intelligent gadget thereof.

Other objects and advantages of the present invention can be understood by the following description and become apparent with reference to the embodiments of the present invention. Also it is obvious to those skilled in the art to which the present invention pertains that the objects and advantages of the present invention can be realized by the means as claimed and combinations thereof.

In accordance with an aspect of the present invention there is provided an intelligent gadget for providing a personalization service in a ubiquitous environment including a gadget service block for collecting and processing data to provide a personalization service and a gadget interface block for forming a gadget network between gadgets and providing a cooperating service based on the collected and processed data.

In accordance with another aspect of the present invention there is provided a method for providing a personalization service by a gadget in a ubiquitous environment including the steps of a when a gadget network is formed based on gadget identification ID and network ID of neighboring gadgets starting own gadget service exchanging gadget service control information with the neighboring gadgets and loading a gadget network based service b creating a new gadget network based service based on the gadget service control information exchanged with the neighboring gadgets c forming a logical gadget network including only gadgets attending performance of the gadget network based service when the created gadget network based service is created and d performing a gadget network based service through interaction of gadgets based on the logical gadget network.

The advantages features and aspects of the invention will become apparent from the following description of the embodiments with reference to the accompanying drawings which is set forth hereinafter. Therefore those skilled in the field of this art of the present invention can embody the technological concept and scope of the invention easily. In addition if it is considered that detailed description on a related art may obscure the points of the present invention the detailed description will not be provided herein. The preferred embodiments of the present invention will be described in detail hereinafter with reference to the attached drawings.

Referring to the intelligent gadget network which is called a gadget network hereinafter is divided into a private gadget network only including private gadgets and and a public gadget network including a public gadget which is not included in the private gadget network. In particular a specific private gadget may be simultaneously overlaid in the private gadget network and the public gadget network.

Since a gadget network is designated to the private gadgets and in advance but is not designated to the public gadget the public gadget may be included in any gadget network.

The gadget network cooperates with an external network. Since the gadget network is not exposed to the external network it is easy to maintain a security in the gadget network.

When the specific private gadget in a private gadget network has communication media capable of cooperating with a communication access point in the external network the specific private gadget becomes a gateway gadget providing a function for cooperating with the external network in other private gadgets within the private gadget network. Accordingly the private gadget network can cooperate with the external network. When the specific private gadget within the private gadget network does not have the communication media capable of cooperating with the external network the specific private gadget cooperates with the external network through the public gadget providing a gateway function.

As described above the gadget network is divided into the private gadget network and the public gadget network and managed. Since the private gadget network cooperates with the external network through a gadget functioning as a gateway inside or cooperates with the outside through the public gadget it is easy to extend a network.

In addition a person owes and moves the private gadget and the public gadget is fixed in a near place. The private gadget and the public gadget have a logic providing a communication interface and a communication protocol and are included in an active gadget network according to configuration information of a perimeter gadget which is a situation of recognizing each other and actively changing. Accordingly the private gadget and the public gadget cooperate based on the exchanged gadget service control information and provides a personalization service to the user. Also the private gadget and the public gadget can widely provide a proper service to the user according to own situation.

According to the above procedure the private gadget and the public gadget may be a subject providing a specific service or an object inactively receiving the specific service.

Referring to the intelligent gadget for providing the personalization service in the ubiquitous environment which is called a gadget hereinafter builds a ubiquitous environment and easily provides a ceaseless personalization service through the built ubiquitous environment.

The gadget includes a gadget service block and a gadget interface block . The gadget service block provides a unique personalization service function which is called a gadget service hereinafter. The gadget interface block provides a service provided by forming of a gadget network between gadgets and cooperating of the gadgets. In particular the gadget interface block includes a communication protocol logic for a communication function between gadgets a service management function based on a gadget network and a service performance function.

The gadget service block includes a data collecting unit and a data processing unit . To be specific the data collecting unit may be more than one in the gadget service block and collects specific data by using a sensor an actuator a camera and Global Positioning System GPS . The data processing unit cooperates with the data collecting unit and manufactures and processes data in a predetermined format. That is the gadget service block can provide more than one gadget service to the user.

Also the gadget interface block includes a gadget network interface a gadget network determining unit and a gadget control unit . To be specific the gadget network interface provides a communication function for forming a gadget network. For example the gadget network interface mutually recognizes a neighboring gadget member according to a wireless personal area network WPAN . The gadget network interface executes a general function which determines an optimal communication environment with the gadget network members.

The gadget network determining unit determines and controls a gadget network configuration according to an actively changing gadget member. That is the gadget network determining unit manages own gadget identification ID and a network ID of a gadget network e.g. WPAN ID.

The gadget network determining unit determines whether a gadget is a private gadget or a public gadget based on the network ID of the neighboring gadget member. When the gadget network to be included in the network ID is designated the gadget is determined as the private gadget. When the gadget network to be included in the network ID is not designated the gadget is determined as the public gadget. Also the gadget network determining unit is included in a private gadget network having a private gadget authenticated according to a pre determined authentication procedure as a member based on the gadget ID of the neighboring gadget member. Since the gadget network determining unit is included in a public gadget network according to the same method as described above detailed description will not be provided herein.

The gadget control unit exchanges and processes gadget service information and gadget service control information i.e. Application Programming Interface information between members of the gadget network determined by the gadget network determining unit . That is when the gadget network is completely formed the gadget control unit performs publishing inquiring and responding on the gadget service control information such that other gadget network members can control the gadget service information and gadget service provided by the gadget control unit between the gadget network members. In order wards the gadget control unit can provide a gadget network based service created by controlling the gadget service provided by another gadget network member to the user.

The gadget control unit can control the gadget service provided by the neighboring gadget network member based on the gadget service information and the gadget service control information of the gadget member. That is the gadget control unit provides the gadget network based service created by interacting with the gadget network member to the user based on the gadget service control information of more than one gadget network member.

According to user request the gadget control unit provides the gadget network based service created by interacting with the gadget network member to the user based on the gadget service control information of pre formed gadget network members. Also when the gadget control unit has an awareness function of specific contexts such as currently provided gadget service control information a performing service requested gadget service control information and user s taste the gadget control unit creates and performs the gadget network based service according to the specific context based on the gadget service control information exchanged between the gadget network members. Also the gadget control unit attends the pre formed gadget network. However when the gadget network member does not request the gadget service control information the gadget control unit performs the gadget service which is a unique function of the gadget control unit .

While the gadget interface block exchanges the gadget service control information with the gadget network members and performs the gadget network based service the gadget interface block is included in a logical gadget network to be described below with the gadgets attending the specific gadget network based service determined based on the gadget service control information.

Referring to the intelligent gadget network includes a private gadget network and a public gadget network. The private gadget network includes private gadgets such as a cardiac sensor gadget a user interface gadget and a GPS gadget and performs the gadget network based service. The public gadget network actively cooperates with the public gadgets such as an external cooperation gadget and a movie service gadget and performs the gadget network based service.

For example silver care service which is the private service is provided to the user through the private gadget network formed by the private gadgets and . The silver care service includes a medical management service based on old age cardiac information a road guide service based on GPS information and a life log based on user information.

The user owes and moves the private gadgets and . The private gadgets and form a private gadget network according to a general communication protocol. The private gadgets and cooperate according to a silver care service application loaded in the private gadgets and and perform the gadget network based service. The private gadgets and manufacture information collected from the user into context awareness information and performs a specific gadget network based service by own determination or by cooperation with the public gadgets and related to a corresponding service.

To be specific the cardiac sensor gadget forms a public gadget network with the external cooperation gadget and cooperates with an external network such that medical management service based on the cardiac information provided by a corresponding gadget service server not shown in can be provided to the user. Also the GPS gadget forms a public gadget network with the external cooperation gadget and cooperates with an external network such that a road guidance service based on the GPS information provided from a corresponding gadget service server not shown in is provided to the user. Also the user interface gadget forms the private gadget network but performs a personal life log through cooperation between more than one gadgets. Accordingly the user interface gadget can provide a memory improving service for providing the personal life log to the user.

The private gadget including the cardiac sensor gadget the user interface gadget and the GPS gadget maintains or reforms the formed gadget network. The user interface gadget provides a theater service i.e. a movie watching service provided by the movie service gadget to the user by cooperating with the movie service gadget .

Referring to the gadget network includes a first private gadget network a second private gadget network a first public gadget network and a second public gadget network.

The first and second private gadget networks include only private gadgets to and to where a network ID included in the gadget network is pre set up. The first and second public gadget networks include a public gadget where a network ID included in the gadget network is not set up.

When the private gadget starts in an initial operation state the private gadget determines that the network ID designated to the searched two neighboring private gadget networks i.e. the first and second private gadget networks is the same as own network ID.

The private gadget determines a communication state and tries to join the gadget network showing an optimal communication environment. The private gadget uses a signal strength a link quality and a Packet Error Rate PER to determine a communication state with the first and second private gadget networks. When the private gadget determines that the second private gadget network is a gadget network showing an optimal communication environment the private gadget tries to join the second private gadget network.

The private gadget performs a user authentication procedure with the second private gadget network. When the private gadget determines through the user authentication procedure that a user is different from the user of the second private gadget network the private gadget fails to join the second private gadget network.

When the private gadget fails to join the second private gadget network the private gadget joins the first private gadget network having the same network ID. That is the private gadget joins the first private gadget network according to the network joining procedure described above.

When there is the neighboring public gadget after formation of the first and second private gadget networks the first and second public gadget networks includes the public gadget and formed doubly with the first and second private gadget networks.

The gadgets within the first and second public gadget networks i.e. the private and public gadgets exchange the gadget service control information among gadgets in a procedure of performing the gadget network based service. In the private and public gadgets only gadgets attending the specific gadget network based service based on the exchanged gadget service control information. The gadget network based service is performed based on the logical gadget network formed described above.

Referring to the first logical gadget network in the first public gadget network including the first private gadget network includes the private gadgets and . Also the second logical gadget network in the second public gadget network including the second private gadget network includes private gadgets and and a public gadget .

Referring to a user A includes a private gadget A a private gadget A and a private gadget A . Also a user B includes a private gadget B a private gadget B and a private gadget B . A public gadget is not included in a specific user in providing a service.

The gadget network based service provided to the user A including a gadget network based service A and a gadget network based service A is performed through interaction of more than one gadget. To be specific the gadget network based service A is performed through interaction of the private gadget A and the private gadget A . The gadget network based service A is performed through interaction of the private gadget A the private gadget A and the public gadget .

The gadget network based service provided to a user B including a gadget network based service B and a gadget network based service B is performed through interaction of more than one gadget. To be specific the gadget network based service B is performed through interaction of the public gadget and the private gadget B . The gadget network based service B is performed through interaction of the private gadget B the private gadget A and the private gadget A .

In particular specific gadgets including the private gadget A the public gadget and the private gadget B may be simultaneously operated to provide more than one gadget network based service. Also the specific services including the gadget network based service A and the gadget network based service B are performed by cooperation of the private gadgets and and the public gadget .

Referring to the first private gadget checks information such as a gadget type of neighboring gadgets including a public gadget and a second private gadget and a network ID and authenticates the user at steps S and S.

The first private gadget and the second private gadget form a private gadget network at step S. When the first private gadget and the second private gadget form the private gadget network a public gadget network which includes the public gadget and is overlapped with the private gadget network is formed at step S.

The first private gadget starts the gadget service which is a unique function of the first private gadget and performs loading on the pre set up gadget network based service at step S. The first private gadget performs publishing inquiring and responding on the gadget service control information for exchanging gadget service control information among gadgets in the gadget network at step S.

The first private gadget creates and loads a new gadget network based service based on the gadget service control information exchanged between the gadgets at step S or forms a logical gadget network including only gadgets attending the performance of the gadget network based service at step S. When a new gadget network based service is created based on the gadget service control information exchanged between gadgets the first private gadget creates a service based on the context awareness information or creates the service upon request of the user at step S.

For example the user interface function is not provided to the first private gadget . When the public gadget for providing a display function is detected it will be performed as follows.

A gadget network based service for helping that the first private gadget uses the display function provided from the public gadget is actively created. The gadget network based service is performed through interaction of gadgets based on a logical gadget network.

The present invention can build a ubiquitous environment and ceaselessly provide a personalization service in a built ubiquitous environment.

Since the present invention is managed by being divided into a private gadget network and a public gadget network a network can be easily extended.

Also since the gadget is not exposed to an external network in the private gadget network the present invention can easily maintain security.

The present invention can easily apply own gadget service between gadget network members in another gadget.

As described above the technology of the present invention can be realized as a program and stored in a computer readable recording medium such as CD ROM RAM ROM floppy disk hard disk and magneto optical disk. Since the process can be easily implemented by those skilled in the art of the present invention further description will not be provided herein.

While the present invention has been described with respect to the specific embodiments it will be apparent to those skilled in the art that various changes and modifications may be made without departing from the spirit and scope of the invention as defined in the following claims.

