---

title: Document management apparatus and document management method
abstract: An apparatus stores one or more document information of which access right is managed by an access right management apparatus, and generates an index of stored document information. The apparatus receives user identification information, and sends the user identification information, and information for identifying document information of which index has not been generated to the access right management apparatus. The apparatus receives access right information associated with the user from the access right management apparatus, and generates index of the identified document information based on the received access right information.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08046365&OS=08046365&RS=08046365
owner: Canon Kabushiki Kaisha
number: 08046365
owner_city: Tokyo
owner_country: JP
publication_date: 20070312
---
The present invention relates to document management processing of a document management apparatus which communicates with a server device controlling access right and controls a document processing request requested from a client device.

Document management systems which include storage devices storing document information and perform document search and document registration processing from a client device via a network have been realized.

With a document management system access right as to each of documents is set for each user and when accessing a document the access right of a user as to the document is determined whereby operations of the user are allowed or denied based on the determination result. Examples of the access right mentioned here include a reference right a reading right a writing right and a deletion right.

Also a set of one or more combinations of a user and an access right is referred to as a policy and there is a technique for reducing complications associated with setting an access right by applying a policy to a document.

Also there is a technique for listing the documents of multiple document servers as well as the access rights thereof e.g. Japanese Patent Laid Open No. 2005 085113 .

Japanese Patent Laid Open No. 2005 085113 discloses listing the search results crossing multiple document servers as well as the access rights thereof. Additionally Japanese Patent Laid Open No. 2005 085113 refers to a search program for confirming the access right of a document included in the search results by inquiring of a document server managing the document thereof.

The access right management using a document management system is only valid as to the documents within the document management system and a technique such as the following is employed regarding the documents outside the document management system.

That is to say this is a technique wherein a document is encrypted authentication is performed when accessing the document to confirm the access right thereof following which the document is decoded.

Such authentication or authorization access right management is frequently performed as to a dedicated server outside of the document management system. The access right management at this dedicated server is frequently performed employing the above described policy so such a dedicated server is referred to as a policy management server below.

The system realizing the access right management employing such a policy management server is referred to as a Rights Management System RMS . A document of which the access right is managed with RMS can be stored in the document management system.

However with existing document management systems including a document management system made up of multiple servers described in Japanese Patent Laid Open No. 2005 085113 the documents of which access rights are managed with the RMS are encrypted. Therefore full text search information has not been able to be obtained.

Also regardless of full text search or attribute search the search results are presented to a user without determining the access right as to a document included in the search results.

Therefore it is difficult for the user to readily confirm the documents that he she can access so it is necessary for the user to confirm his her access right by accessing each of documents and inquiring of a policy management server whether or not the user can access the document which is poor in convenience.

Also in the event of presenting the result of full text search to the user though only the key words employed for search a user is informed about the contents of a document which should be kept in secret by access restriction to begin with which causes a problem even from the perspective of security.

Embodiments of the present invention are provided to solve or at least mitigate the above mentioned problems. An embodiment of the present invention provides an arrangement wherein even if document information of which access right is set is encrypted and stored decoding can be performed in accordance with user authority and also full text search can be performed with sufficient convenience.

According to an aspect of the present invention an embodiment is directed to a document management apparatus including a document information storing unit configured to store one or more document information of which access right is managed by an access right management apparatus an index generating unit configured to perform processing for generating an index of document information stored in the document information storing unit a sending unit configured to accept user identification information for identifying a user and send to the access right management apparatus the user identification information and information for determining document information of which index generating processing has not been performed by the index generating unit of the document information stored in the document information storing unit a receiving unit configured to receive the access right information of the user regarding the document information to be sent from the access right management apparatus which responds to the user identification information and the document information sent by the sending unit and a control unit configured to control the index generating processing of the document information by the index generating unit based on access right information received by the receiving unit.

According to another aspect of the present invention an embodiment is directed to a method for a document management apparatus having a document information storing unit capable of storing one or more document information of which access right is managed by an access right management apparatus. The method includes performing processing for generating an index of document information stored in the document information storing unit receiving user identification information for identifying a user and sending to the access right management apparatus the user identification information and information for identifying document information of which index generating processing has not been performed of the document information stored in the document information storing unit receiving the access right information of the user regarding the document information to be sent from the access right management apparatus which responds to the user identification information and the information identifying the document information and controlling the index generating processing of the document information based on the received access right information.

Further features of the present invention will become apparent from the following description of exemplary embodiments with reference to the attached drawings.

Next description will be made regarding the preferred embodiments for implementing the present invention with reference to the drawings.

Now the policy management server separately from the document management system performs processing for controlling and issuing control data called policy for performing access control as to a document also referred to herein as document information . In one context the term policy is used to describe a set of one or more combinations of a user and an access right.

The document management system according to an embodiment includes the client which runs on the operating system OS of a personal computer and the document server . The document management system executes processing wherein a document is obtained from an image input device such as a scanner or a file on the OS and the document is managed by multiple users.

First description will be made regarding a processing unit for performing input output or operations of a document disposed within the client .

The client includes a control unit including CPU ROM and RAM as the base a keyboard a pointing device and a display device as an input output device and further an external device such as a hard disk or the like.

The CPU loads the OS stored in the external device into the RAM and performs device processing and processing such as activation and termination of software. Note that the document server also has similar hardware resources.

Also the client and the document server each include a network controller for communicating via a network which is configured so as to communicate with multiple protocols.

In reference numeral denotes a user interface unit. A user performs operations via the user interface unit such as registration of a document to the document server obtaining of a document from the document server or search of a document.

The information e.g. command entered via the user interface unit is analyzed at a command control unit where appropriate processing is performed. Also commands for communicating with the document server are generated by the command control unit .

A device control unit performs control of a device such as a scanner or the like. Here processing such as uploading document data from the device side or receiving data transmitted from the device side is performed.

A document file saved on the OS such as a file server or the like is configured so as to perform input processing at a file control unit in a form of importing document data. The file control unit also performs processing for exporting a file managed upon the document server to the OS.

Reference numeral denotes an external module communication unit which performs communication with an external application and performs processing such as transmitting a document within the document server to an external application receiving a document from an external application and so forth. An external application is another application installed into the client . The external module communication unit performs processing such as transmitting a document managed at the document server to an electric mail application corresponding to MAPI Messaging Application Programming Interface for example.

Reference numeral denotes a document management control unit which is a functional processing unit for controlling the document management processing at the client . Here processing corresponding to a file or command transmitted from the input output processing unit is performed.

Reference numeral denotes an internal data saving unit which saves temporary data. The internal data saving unit temporarily saves data created at a process for performing image processing data created at a process for communication with the server and so forth. The internal data saving unit substantively comprises memory devices such as a hard disk RAM and so forth and access to the memory devices is controlled by the CPU via the OS.

Reference numeral denotes a communication control unit which performs control for communicating with the document server or the policy management server using a predetermined protocol.

The communication control unit shown in the present embodiment performs control with the processing of the document server or the policy management server and with regard to control of communication such as TCP IP or the like serving as a protocol the control prepared by the OS is employed.

Next description will be made regarding various types of processing units disposed within the document server .

Reference numeral denotes a communication control unit which performs control for communicating with the communication control unit of the client .

However the communication control unit of the document server is configured so as to communicate with the communication control units of a great number of clients simultaneously. With the present embodiment in an example is illustrated wherein the one client can communicate with the document server but the system can be configured so as to communicate with multiple clients.

Reference numeral denotes a document management control unit which integrally controls the processing at the document server side in accordance with an instruction from the client .

The document management control unit as a result of authentication as to the policy management server encrypts the document information obtained from the client registers this in a later described volume database and manages this.

Also in the event that an access right is determined at later described processing the document management control unit subjects the document information encrypted and registered in the volume database to decoding processing based on the stored authentication information. Alternatively the document management control unit subjects the encrypted document to decoding processing based on the information obtained from the policy management server .

Reference numeral denotes an internal data saving unit which saves temporary data. The internal data saving unit temporarily saves data created at a process of communication with the client .

Reference numeral denotes a search control unit which performs processing for searching the document requested from the client or performs the search information registration processing of the registered document.

Reference numeral denotes a policy data processing unit. The policy data processing unit performs processing for determining whether or not policy data appended to a document exists or transmitting policy data to the policy management server to confirm the contents of the policy.

With the policy data processing unit user authentication information is requested to the client and is obtained from the client the authentication of the relevant user is performed and the authority information including an authority list regarding the document information of the authenticated user is obtained from the policy management server .

Also the policy data processing unit processes an available authority list received from the policy management server and returns the confirmation result of the policy and so forth to the document control unit . Note that the authority list and so forth are stored in the internal data saving unit and the user authentication information and so forth stored by the document control unit are removed based on the authentication result or the authority determining processing.

The policy data processing unit is configured depending on the specifications of the policy management server .

Next description will be made regarding a database processing unit disposed within the document server .

Reference numeral denotes a database control unit which performs processing wherein data to be saved in a database is created and the corresponding document is saved in a volume database an attribute database and a full text search database .

Also the database control unit performs processing wherein data is extracted from each of the above databases depending on a request from the client and a document to be transmitted to the client is created.

Reference numeral denotes a volume database which is a database to which the entity of a document is saved. The volume database is a conceptual database so there is no problem even if the entity is the file system of the OS.

Reference numeral denotes an attribute database which is a database where information relating to attributes such as a document name created date remarks and so forth is saved. Also an access right administrator for each document an access right ID policy management server information policy ID and the cache of the access right information of the RMS are also saved in the attribute database .

Reference numeral denotes a full text search database which extracts text data from a document registered in the volume database and the data converted into index information is registered therein.

Upon receiving a full text search request from the client the document management control unit searches the full text search database based on the search conditions received from the client . Here as for the search conditions various types of data such as a keyword date and time a title an image name and so forth can be specified as search conditions.

Next description will be made regarding a policy management processing unit disposed within the policy management server .

Reference numeral denotes a communication control unit which performs control for communicating with the communication control unit of the server system. The communication control unit of the policy management server is configured so as to communicate with multiple information processing devices connected to the network simultaneously.

Reference numeral denotes a policy management control unit which performs the integral processing of the policy management server . The policy management control unit performs processing depending on a command obtained from the communication control unit .

Reference numeral denotes a policy issuing unit which creates a policy. Here the term policy is a set of one or more combinations of a user and an access right.

Reference numeral denotes a database control unit which creates data to be saved in the policy management data base and performs processing for saving the data in the policy management database . The policy management database stores information correlating between the ID for determining a document equivalent to the policy ID in and a policy and a key for decoding the document in a correlated manner.

Also the database control unit performs processing wherein the corresponding data from the policy management database is extracted according to an external request and the data is transmitted to the client or the document server .

Reference numeral denotes a policy management database which is a database where policies and the user information managed by the policy management server are saved.

With the document management system thus configured the document management apparatus document server includes a document database volume database . The document management apparatus communicates with one of the server devices managing the access right of a user regarding the document information encrypted and registered in the volume database and controls a document processing request requested from the client . The term server devices include the policy management server and other policy management servers in which access right obtaining destinations are registered.

The document server includes the attribute database capable of storing attribute information for determining user authentication information access right and so forth to create an index for subjecting document information to full text search. In an embodiment the attribute information includes determination destination information for determining an access right management destination such as policy management server information shown in .

Also the document server includes an obtaining function for obtaining access right information from the policy management server . Specifically such as shown in the steps of a later described flowchart upon receiving a full text search request from the client the following processing is performed. That is to say the document server includes an obtaining function for obtaining access right information from the policy management server in accordance with the policy management information determined from the attribute database based on the user authentication information obtained from the client .

The document server also includes a setting function for setting the access right information for each user regarding a document which is obtained from the policy management server to the attribute database .

The document server further includes a document decoding function for decoding a document of which access is permitted of the documents encrypted and registered based on the user authentication information stored in the attribute database . Note that for the encryption algorithm of a document various types of algorithms can be employed.

Also the document server includes an obtaining function for obtaining full text search information index from the decoded document information and a registration function for registering the obtained full text search information in the full text search database .

Also the document server includes a determination function for determining the validity of the access right for each user who performs full text search based on the policy obtained from the policy management server . Additionally the document server includes a restriction function for restricting an access request regarding the document information on which the user has no access right stored in the attribute database based on the determination result thereof. Thus the document server can execute full text search as to the encrypted document in accordance with an access right while performing access right management based on a policy.

Also the document server includes a notification function for notifying the client of the search result display information for displaying on a display unit a list of document information on which a user serving as a search request origin has access rights stored in the attribute database .

In an embodiment access rights are made up of multiple hierarchical structures and are arranged so as to set various rights such as a deletion right a writing right a reading right and a reference right for example.

Also the attribute information stored in the attribute database is arranged so as to set status information for managing the registration status of the full text search information see the full text search information registration status shown in as to the full text search database .

Further with regard to the attribute information an arrangement is made wherein the registration of full text search information as to the full text search database and obtaining of the registered full text search information are performed asynchronously.

Reference numeral is folder data which is the data of a folder for a user storing data in the document server . The folder includes a folder ID folder attribute information and a parent folder ID.

Note that with the present embodiment multiple folders can be provided so folders existing in the most significant class which are equivalent to the number thereof are registered as child data connected to immediately following the root such as the folder . Therefore the parent folder of the folders and is the root . Also the parent folder of the folder is the folder .

Reference numeral denotes document data which exists as the child data to be stored in the folder . The document data includes a document ID document attribute information a search index ID a volume data ID and a parent folder ID and saves data as document attribute information such as a document name update date and time remark data and so forth.

A document ID is an ID appended to a document and is a value unique to the entire document management system. A search index ID is an ID employed for the full text database distinguishing documents and upon causing the database control unit to search a search index ID by specifying a keyword the search index ID of the relevant document is returned.

A volume data ID is an ID registered in the volume database and the information relating to a document can be extracted from each of the databases using this ID. A plurality of document data can exist under a folder so the number of document data equivalent to the number thereof can be registered such as the document data . A parent folder ID is information indicating the ID of the folder in which the relevant document is stored. For example the parent folder of the document data is the folder ID of the folder .

In reference numeral denotes a document ID. Reference numeral denotes a parent folder where an upper class folder ID is set. A document name is the document name of a document. An access right administrator is information serving as the main body for controlling the access right as to a document and here takes one of a value of document management system and a value of policy management server .

An access right ID is information for determining an access right which is managed and set within the document management system in the event that the access right as to a document is controlled by the document management system.

Policy management server information is an IP address as to the network of the policy management server in the event that the access right as to a document is controlled by using the external policy management server .

A policy ID is a unique ID for determining a document within the relevant policy management server in the event that the access right as to the document is determined with the policy management server information i.e. the policy management server.

A full text information registration status is information regarding whether or not the full text search information generated regarding the document information decoded by the document management control unit is registered in the full text search database and for example either registered or unregistered is set. Here the term full text search information is index information for search and is encrypted and registered in the volume database by the document management control unit . The full text search information is decoded in accordance with a user authentication and the access right of an authenticated user following which is generated as to the decoded document information.

In an embodiment the access right is made up of four types of a deletion right a writing right a reading right and a reference right and the access right of each type is strong in this order. A strong access right includes a weak access right. For example including a deletion right means including a writing right a reading right and a reference right. Also including a writing right means including a reading right and a reference right.

Note that with the present embodiment in the event that there is no combination of the access right ID and the user ID in the access right information management is performed assuming that this user has no access right regarding the document appended with the access right ID.

The present cache is a partial copy of the policy stored in the policy management server or another policy management server and is added and managed by the database control unit each time the policy data processing unit obtains a policy from the policy management server. Also in the event that modification of a policy is informed from the policy management server the policy data processing unit deletes the cache of the corresponding policy stored on the attribute database . In the event that the contents of the modified policy are informed from the policy management server as well the policy following modification may be cached.

In a user ID is as with the user ID in an ID for uniquely identifying a user within the document management system. Policy management server information is information for determining the policy management server or another policy management server . There are a case wherein authentication information is stored as a credential and a case wherein it is stored as a pair of a user name and a password . Also in the event that a user has not performed user authentication using the policy management server or the like information such as unauthenticated is input to the authentication information .

With the example shown in the document management control unit manages the password as another item different from the credential but the document management control unit may manage the password as one of the credential .

In the event of storing the authentication information as the credential the expiration date of the authentication information is controlled by the policy management control unit of the policy management server .

On the other hand in the event of storing the authentication information as a pair of the user name and the password the expiration date of the authentication information is controlled by the document management control unit of the document management system.

With the present embodiment the credential is some kind of information employed in the case of a user performing authentication as to the policy management server .

Examples of a credential include information for certificating the relevant user and an encryption key or signature information employed in the case of performing a session for authentication as to the policy management server .

Note that the document management control unit adds information to the present information saved in the internal data saving unit at the point of authentication as to the policy management server succeeding. Also the document management control unit deletes the relevant information at the point of the authentication becoming invalid.

In a user ID is as with the user ID in an ID for uniquely identifying a user within the document management system. A full text search information obtaining range can be set for each user of the document management system and is saved and managed in a correlation with the user ID .

In an embodiment the full text search information obtaining range is any one of all permitted partially permitted and all denied .

Here all permitted is set in the case of permitting acquisition and registration of full text search information regarding all of the documents that the user has the access rights shown in .

Also partially permitted is set in a case wherein the user specifies a permission range for each document or each folder and the document management system records the specified range in the permission range as a document ID group or folder ID group.

Further all denied is set in the case of not permitting acquisition and registration of full text search information regarding all of the documents that the user has the access rights.

Also the present processing is performed in the case of confirming the access right of a document of which access right is managed using the RMS stored on the document management system. Following the present processing processing such as obtaining access right information or the like is performed. Note that reference numerals through represent the respective steps. Also the respective steps in describe the processing performed by the client and the document server but the processing performed by other than the document management system will be described later.

First in step the document management control unit determines whether or not the authentication information at the policy management server relating to the operating user is stored in the internal data saving unit . Now if the document management control unit determines that the authentication information is stored on the internal data saving unit the flow proceeds to step .

On the other hand if the document management control unit determines in step that the authentication information is not stored on the internal data saving unit the flow proceeds to step .

Note that the present step and later described steps and are steps for reducing the number of times authentication information requests are issued to the user and improving convenience of the user.

In step the document management control unit requests authentication information as to the policy management server from the user via the communication control unit . This request is ultimately propagated to the user interface unit of the client to seek authentication information from the user.

On the other hand the user operates an input device on the client and from a displayed UI screen inputs authentication information as to the policy management server .

Subsequently in step the user interface unit of the client obtains the authentication information as to the policy management server from the user and propagates the authentication information to the policy data processing unit via the communication control units and .

Next in step the policy data processing unit inquires of the policy management server the access right as to the operating user regarding the document. This is performed by inquiring of the policy management server via the communication control unit .

At this time an inquiry is made with the authentication information input from the client in step or with the authentication information obtained from the internal data saving unit in step .

The policy management server receives the above authentication information performs authentication processing with reference to the policy management database and replies the result thereof to the document server .

Subsequently in step the document management control unit determines whether or not the authentication has succeeded with respect to the inquiry in step . Subsequently in the event that the document management control unit determines that the authentication has succeeded the flow proceeds to step but in the event of determining that the authentication has not succeeded the flow proceeds to step .

In step in the event that the authentication information of the policy management server of the operating user is registered on the internal data saving unit the document management control unit deletes the authentication information and the flow returns to step .

Thus with regard to the existing authentication information authentication processing is prevented by the authentication information being determined to be wrong in step thereby improving processing efficiency.

On the other hand in the event that the document management control unit determines in step that the authentication has succeeded in step the document management control unit newly records the authentication information of the policy management server on the internal data saving unit and the present processing ends.

Note that in the event that the authentication information has been already recorded this processing may be omitted.

The document information of which access right is managed by the policy management server is encrypted so in the event of a period wherein the user is authenticated by the document server the decoding key of such encrypted document information can be obtained from the policy management server using the credential information of the relevant user it is needless to say that the policy that can access to the relevant document is assumed to have been applied . Thus it is not necessary for the user to instruct to generate an index and the document server can automatically perform index generation of the document information of which access right is managed by the policy management server .

First in step the document management system obtains the authentication information as to the policy management server of the user temporarily stored in the internal data saving unit . Subsequently the following processing from step to step is repeated for each of authentication information as to the policy management server .

In step the document management control unit of the document server obtains the full text information obtaining permission range based on the user ID of the user saved in the attribute database illustrated in . Subsequently the document management control unit determines whether the full text information obtaining permission range is all permitted or partially permitted .

In the event that the document management control unit determines that the full text search information obtaining permission range is all permitted or partially permitted the flow proceeds to step and in the event of determining that the full text search information obtaining permission range is all denied the flow proceeds to step .

Subsequently in step the document management control unit obtains a document ID group of the documents included in the user permission range and repeats the processing from step to step regarding each of the documents.

Next in step the document management control unit obtains the full text search information registration status of one of the documents to which the obtained ID is set here obtains the full text search information registration status stored in the attribute database illustrated in . Subsequently the document control unit determines whether or not the full text search information registration status thereof is registered .

Now in the event that registered is determined by the document management control unit the flow proceeds to step where processing regarding the next document is performed but in the event of unregistered being determined the flow proceeds to step .

Next in step the document management control unit transmits the authentication information as to the policy management server obtained in step and the policy ID of the document determined as unregistered to the policy management server and receives the decoding key for decoding the document from the policy management server . An arrangement may be made wherein in step the access right information as to the document to be decoded with the decoding key thereof is further received from the policy management server .

Subsequently in step the document management control unit determines whether or not decoding of the document information using the decoding key received from the policy management server has succeeded. However if the relevant user has no access right higher than a reference authority regarding the document information determined by the policy ID transmitted to the policy management server or if the policy management server includes no policy of the relevant document information the decoding key is not transmitted from the policy server. In such a case the document information cannot be decoded and accordingly in step determination is made that decoding has failed. On the other hand if the policy wherein the relevant user has the access right of reference authority transfer is applied to the document information specified by the relevant policy ID determination can be made that decoding of the relevant document information can be performed and the subsequent index generating processing can be performed. In other words in the event that the decoding key is transmitted from the policy management server it can be also considered that the information indicating that there is the access right as to the relevant document is received. Now if the document management control unit determines that decoding has succeeded the flow proceeds to step but in the event of determining that decoding has been failed the flow proceeds to step where processing regarding the next document is performed.

Next in step the document management control unit of the document management system obtains full text search information index from the decoded document and registers the full text search information in the full text search database . The full text search information is the keyword employed for full text search which is extracted from the text portion of a document. Subsequently the document management control unit changes the full text search information registration status managed by the attribute database as to the relevant policy ID to registered .

The document management control unit repeats the above processing from step to step regarding the documents included in the full text search information obtaining permission range of the user .

Subsequently the document management control unit repeats the processing from step to step regarding the authentication information as to the policy management server of the user temporarily stored in the internal data saving unit of the document management system and the present processing ends.

The processing in enables the full text search information of the encrypted document to be obtained using the authentication information as to the policy server temporarily stored. Thus it becomes unnecessary for the user to perform operations for authentication as to the policy server to obtain full text search information whereby convenience in the case of obtaining full text search information from a document improves.

In step the document management system inquires search conditions of the user. The user inputs search conditions from the client via the user interface unit . The document management control unit of the document management system receives the response thereof via the user interface unit and stores the search conditions in the memory or the temporary data .

Next in step the document management control unit of the document management system inquires of the document server the document that matches the search conditions stored on the above memory. This can be realized by performing the following processing.

For example the database control unit searches the document matching the above search conditions from the full text search database and returns a search index ID group. Here the document management control unit converts a search index ID into the corresponding document ID and stores this information in the internal data saving unit . Hereafter the document ID group stored in the internal data saving unit is referred to as search results.

The document management system performs the processing of step through regarding each of the documents included in the search results. Specifically in step the document management control unit determines whether the access right administrator of a document is the policy management server or the document management system.

Now if the document management control unit determines that the access right administrator is the policy management server the flow proceeds to step . On the other hand if the document management control unit determines that the access right administrator is the document management system the flow proceeds to step .

Subsequently in step the document management control unit of the document management system searches the attribute database and obtains the access right of the operating user as to the document.

Note that step through step are the processing in a case wherein the access right as to the document is managed by the policy management server .

First in step the document management control unit of the document management system obtains the policy management server information and policy ID that manage the document access right shown in .

Subsequently in step the document management control unit of the document management system determines whether or not the access right information of the operating user as to the policy ID is cached on the internal data saving unit . Now in the event that the document management control unit determines that the cache of the access right information exists the document management control unit obtains the access right information thereof and the flow proceeds to step but in the event of determining that there is no cache the flow proceeds to step .

Subsequently in step with the document management system the document management control unit determines whether or not the authentication information as to the policy management server of the operating user temporarily stored on the internal data saving unit is valid.

Now in the event that the document management control unit determines that the authentication information is valid the flow proceeds to step .

On the other hand in the event that invalidity is determined by the document management control unit in step the document management control unit obtains the authentication information as to the policy management server to perform the authentication processing as to the policy management server illustrated in .

The policy data processing unit of the document management system inquires of the policy management server the access right appended with the authentication information and policy ID. The policy management server returns the access right information correlated with the relevant user of the policies managed with a policy ID. The policy data processing unit of the document management system receives the access right information from the policy management server . Subsequently the document management control unit of the document management system additionally registers the access right received from the policy management server on the cache on the internal data saving unit .

Next in step with the document management system the document management control unit determines whether or not the access right as to the document that obtained in step or or is equal to or greater than the reading right shown in .

Now if the document management control unit determines that the access right as to the document is less than the reading right the document management control unit removes the ID of the relevant document from the search results . The document management control unit repeats the above processing regarding each of the documents included in the search results . Subsequently in step the document management control unit of the document management system informs the client about the search results. Thus the device control unit included in the client displays the search results on the display device via the user interface unit of the client to have the user confirm the search results and the present processing ends.

Thus with the document management apparatus access rights are managed at the external policy management server and full text search can be performed even regarding a document stored in an encrypted state.

Also only the documents that a user who searched documents can access are displayed as search results whereby security and user convenience can be improved.

With the above embodiment in the event that the policy regarding a document is managed at the policy management server the authority thereof and so forth may be modified in some cases.

Now in the event that the document management control unit receives a policy modification notice from the policy management server the policy data processing unit performs the following processing.

The policy data processing unit deletes the access right information of the policy corresponding to the received policy modification notice. Specifically the policy data processing unit deletes the access right and so forth within the attribute database with reference to the user ID and so forth.

Also in the event that the contents of the policy after modification are also informed from the policy management server the access right information may be overwritten by the access right information stipulated by the policy after modification.

Description will be made below regarding the structure of a data processing program that can be read by the document management apparatus according to the present invention with reference to the memory map illustrated in .

Note that though not particularly shown in the drawing information managing a program group stored in the storing medium for example such as version information a creator and so forth is stored and also information depending on the OS or the like at the program readout side for example such as icons for displaying programs in a distinguishable manner and so forth is stored in some cases.

Further data belonging to various types of programs is also managed in the above directory. Also in the event that a program for installing various types of programs in a computer and programs to be installed are compressed a decompression program or the like is also stored in some cases.

The functions illustrated in according to the present embodiment may be executed by a host computer using a program to be externally installed. In this case even in the event that an information group including programs is supplied to an output device from a storing medium such as CD ROM flash memory FD or the like or from an external storing medium via a network the present invention can be applied.

As described above a storing medium in which the program code of software for realizing the functions of the above embodiments is recorded is supplied to a system or device. Subsequently it is needless to say that the functions of the present invention can be provided by the computer or CPU or MPU of the system or device thereof reading out and executing the program code stored in the storing medium.

In this case consequently the program code itself read out from the storing medium realizes the new functions of the present invention and accordingly the storing medium storing the program code thereof makes up the present invention.

Accordingly as long as the functions of the program are included any form of a program such as an object code a program executed by an interpreter script data supplied to the OS and so forth can be employed.

As for a storing medium for supplying the program for example a flexible disk a hard disk an optical disc a magneto optical disk MO CD ROM CD R CD RW magnetic tape nonvolatile memory ROM DVD and so forth can be employed.

In this case the program code itself read out from a storing medium realizes the functions of the above embodiments and accordingly the storing medium storing the program code thereof makes up the present invention.

In addition as for a method for supplying the program the program can be supplied by an arrangement wherein the client computer is connected to a home page of the Internet using a browser of the client computer and subsequently the computer program itself of the present invention or a compressed file including an automatic install function is downloaded in a storing medium such as a hard disk or the like from the home page. Also the program code making up the program of the present invention is divided into multiple files and each of the files is downloaded from a different home page whereby the program can be supplied. In other words a WWW server or a ftp server or the like for downloading the program file for realizing the functional processing of the present invention at a computer to multiple users are also encompassed in the claims of the present invention.

Also an arrangement may be made wherein the program of the present invention is encrypted and stored in a storing medium such as CD ROM or the like to distribute this to users and only the user satisfying predetermined conditions can download the key information for decoding the encryption from a home page via the Internet and subsequently execute the encrypted program using the key information thereof to be installed in a computer whereby the functional processing of the present invention can be realized.

Also the functions of the above embodiments may be realized not only by executing the program code that the computer reads out but also by the OS or the like running on the computer performing a part or all of the actual processing based on the instruction of the program code thereof for example and it is needless to say that the case of the functions of the above embodiments being realized by the processing thereof is also encompassed in the present invention.

Further the program code read out from a storing medium may be written in the memory included in a function expansion board inserted in the computer or a function expansion unit connected to the computer following which the CPU or the like included in the function expansion board or function expansion unit thereof performs a part or all of the actual processing and it is needless to say that the case of the functions of the above embodiments being realized by the processing thereof is also encompassed in the present invention.

According to the present invention encrypted and stored document information is disposed in a document management apparatus which can manage user rights at a management server and the documents of which access rights are managed can be decoded whereby full text search can be performed.

Also only the documents that the user who searched can access are displayed as search results whereby security and user convenience can be improved.

The present invention is not restricted to the above embodiments so various types of modification including an organic combination of the respective embodiments based on the meaning of the present invention can be made which are not eliminated from the scope of the present invention.

While the present invention has been described with reference to exemplary embodiments it is to be understood that the invention is not limited to the disclosed exemplary embodiments. The scope of the following claims is to be accorded the broadest interpretation so as to encompass all modifications equivalent structures and functions.

This application claims the benefit of Japanese Application No. 2006 082138 filed Mar. 24 2006 which is hereby incorporated by reference herein in its entirety.

