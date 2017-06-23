---

title: Client apparatus for updating data
abstract: A client apparatus receives first data from a server and later receives second data from the same server in response to a refresh invocation. The client apparatus parses the received data to generate logical structures representing the data and then compares the logical structures using a tree walking algorithm. Where a difference is found between the first data and second data, the first data is updated using the second data and rendered at the client apparatus.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08312077&OS=08312077&RS=08312077
owner: International Business Machines Corporation
number: 08312077
owner_city: Armonk
owner_country: US
publication_date: 20071115
---
The World Wide Web is the Internet s multimedia information retrieval system. In the web environment a client machine communicates with a web server using the Hypertext Transfer Protocol HTTP .

With reference to there is shown a system in which a web browser an application running on a client computer renders a web page by requesting the web page from a web server . Such a web page is constructed using a markup language such as Hypertext Markup Language HTML Extensible Hypertext Markup Language XHTML etc.

In the prior art the web browser can be automatically invoked to initiate a refresh of the complete content of a web page periodically e.g. every 2 minutes . In some cases this may be acceptable to a user.

However in other cases this is not desirable. For example a web page may include share prices that are refreshed periodically and a form that a user can fill in. If a user has partially completed the form on the webpage when the complete web page refreshes the user may lose data that they have already entered into the form. This can obviously be frustrating to a user. Furthermore a full web page refresh can be very slow and cause the screen to flicker.

U.S. Pat. No. 6 377 957 discloses a system that propagates changes in hierarchically organized data to remotely cached copies of the data. The system operates by receiving an access to the data at a client. In response to this access the system determines if the client contains a copy of the data. If so the system sends a request to a server for an update to the copy. The server receives the request and determines differences between the current version of the data at the server and an older copy of the data at the client which the server has stored locally. These differences are used to construct an update for the copy of the data which may include node insertion and node deletion operations for hierarchically organized nodes in the data. Next the update is sent to the client where it is applied to the copy of the data to produce an updated copy of the data. Finally the original access is allowed to proceed on the updated copy of the data.

The invention may be embodied as a client apparatus for updating data for use with a system comprising a receiver for receiving first data and a refresh invocation means for invoking a refresh of the first data. The receiver receives second data in response to the refresh invocation means. The second data may be identical to or different from the first data. The apparatus includes a comparator for comparing the first data and the second data to determine whether there is a difference and an updater that responds to the determination of a difference by updating the first data with the second data.

The invention may also be embodied as a method for updating data for use with a system for receiving first data invoking a refresh of the first data and receiving second data. At a client computer the first and second data are compared. If there is a difference the first data is updated with the second data.

The invention may also be implemented as a computer program product for updating data in a client computer system in which first data is received and then refreshed with second data. The computer program product includes a computer usable medium embodying computer usable program code configured to compare the first data and the second data and to determine whether there is a difference between the first data and the second data. If a difference is found other computer usable program code in a computer program product updates the first data with the second data.

As will be appreciated by one skilled in the art the present invention may be embodied as a method system or computer program product. Accordingly the present invention may take the form of an entirely hardware embodiment an entirely software embodiment including firmware resident software micro code etc. or an embodiment combining software and hardware aspects that may all generally be referred to herein as a circuit module or system. Furthermore the present invention may take the form of a computer program product on a computer usable storage medium having computer usable program code embodied in the medium.

Any suitable computer usable or computer readable medium may be utilized. The computer usable or computer readable medium may be for example but not limited to an electronic magnetic optical electromagnetic infrared or semiconductor system apparatus device or propagation medium. More specific examples a non exhaustive list of the computer readable medium would include the following an electrical connection having one or more wires a portable computer diskette a hard disk a random access memory RAM a read only memory ROM an erasable programmable read only memory EPROM or Flash memory an optical fiber a portable compact disc read only memory CD ROM an optical storage device a transmission media such as those supporting the Internet or an intranet or a magnetic storage device. Note that the computer usable or computer readable medium could even be paper or another suitable medium upon which the program is printed as the program can be electronically captured via for instance optical scanning of the paper or other medium then compiled interpreted or otherwise processed in a suitable manner if necessary and then stored in a computer memory. In the context of this document a computer usable or computer readable medium may be any medium that can contain store communicate propagate or transport the program for use by or in connection with the instruction execution system apparatus or device. The computer usable medium may include a propagated data signal with the computer usable program code embodied therewith either in baseband or as part of a carrier wave. The computer usable program code may be transmitted using any appropriate medium including but not limited to the Internet wireline optical fiber cable RF etc.

Computer program code for carrying out operations of the present invention may be written in an object oriented programming language such as Java Smalltalk C or the like. However the computer program code for carrying out operations of the present invention may also be written in conventional procedural programming languages such as the C programming language or similar programming languages. The program code may execute entirely on the user s computer partly on the user s computer as a stand alone software package partly on the user s computer and partly on a remote computer or entirely on the remote computer or server. In the latter scenario the remote computer may be connected to the user s computer through a local area network LAN or a wide area network WAN or the connection may be made to an external computer for example through the Internet using an Internet Service Provider .

The present invention is described below with reference to flowchart illustrations and or block diagrams of methods apparatus systems and computer program products according to embodiments of the invention. It will be understood that each block of the flowchart illustrations and or block diagrams and combinations of blocks in the flowchart illustrations and or block diagrams can be implemented by computer program instructions. These computer program instructions may be provided to a processor of a general purpose computer special purpose computer or other programmable data processing apparatus to produce a machine such that the instructions which execute via the processor of the computer or other programmable data processing apparatus create means for implementing the functions acts specified in the flowchart and or block diagram block or blocks.

These computer program instructions may also be stored in a computer readable memory that can direct a computer or other programmable data processing apparatus to function in a particular manner such that the instructions stored in the computer readable memory produce an article of manufacture including instruction means which implement the function act specified in the flowchart and or block diagram block or blocks.

The computer program instructions may also be loaded onto a computer or other programmable data processing apparatus to cause a series of operational steps to be performed on the computer or other programmable apparatus to produce a computer implemented process such that the instructions which execute on the computer or other programmable apparatus provide steps for implementing the functions acts specified in the flowchart and or block diagram block or blocks.

With reference to there is shown a block diagram of a system in which the present invention can be implemented. The system includes a client computer and a server computer each operable to communicate with the other over a network such as the Internet. The client computer includes a web browser for rendering a web page served by the server computer .

The client computer also comprises a requester for sending a request for a web page to the server computer a receiver for receiving a response from the server computer a parser for parsing a document included in a response and storing an associated Document Object Model DOM in memory and a renderer for rendering the document. Document Object Models DOMs are described in more detail later.

The client computer also includes a comparator for comparing a plurality of DOMs and an updater for updating a DOM. It should be understood that the apparatus of the present invention can reside within a web browser at the client computer.

With reference to the requester generates and sends step a request to the server computer for a first web page. In the example the request is represented by an XMLHTTPRequest object. By using the XMLHTTPRequest object a web page can be changed with data from the server computer after the web page has loaded. Various methods can be used with the XMLHTTPRequest object. In the example described herein the requester uses an open method to specify parameters of a request e.g. a method parameter having an associated value of GET which is associated with getting data and a URL parameter associated with the URL to be obtained e.g. www.my news.com . The requester uses a send method to send the request. It should be understood that the request can be implemented in a number of ways.

In response to receiving the request the server computer sends step a response including the first web page to the receiver . In the example a first XHTML document associated with the first web page is included in an HTTP response sent by the server computer . It should be understood that any number of markup languages can be used e.g. HTML.

An example of the first XHTML document is shown in . The document includes elements represented by tags. Tags are enclosed by the characters .

The tags i.e. a root element define an XHTML document comprising a head defined by the tags and a body defined by the tags . The head comprises tags which enclose a text string specifying a title i.e. News . The head also comprises tags that are used to identify properties of a document. The tags comprise an http equiv attribute used to specify information that a server computer should convey in a HTTP response message with which the document is transmitted. In a value of the http equiv attribute is refresh and a value of an associated content attribute is 150 . The example syntax specifies that the first XHTML document which includes the tags should be refreshed following a period of 150 seconds. It should be understood that refresh invocation functionality can be implemented in a number of ways e.g. program code associated with the web browser .

In response to receiving the HTTP response the receiver passes the first XHTML document to the parser which loads the first XHTML document into memory and parses it in order to obtain a first associated DOM.

A Document Object Model DOM is an application programming interface for documents. The DOM defines a logical tree like structure of a document and the way in which a document is accessed and manipulated. A document representing a web page can be loaded into memory and parsed. Once loaded into memory and parsed the logical structure of the document can then be accessed. Elements attributes and text of a document can be represented as objects known as nodes . The World Wide Web Consortium W3C has published specifications that define a W3C DOM.

A representation of the first DOM for the first XHTML document representing the first web page is shown in . It should be understood that any number of logical structures can be used.

The exemplary first DOM comprises a first root element node a first element node a second element node a first text node a third element node a first attribute node a second attribute node a fourth element node a fifth element node a sixth element node a third attribute node a second text node a seventh element node an eighth element node a fourth attribute node and a third text node .

A first level includes the first root element node . A second level includes the first element node and the fourth element node . A third level includes the second element node the third element node the fifth element node and the seventh element node . A fourth level includes the first text node the first attribute node the second attribute node the sixth element node and the eighth element node . A fifth level includes the third attribute node the second text node the fourth attribute node and the third text node .

The first DOM is shown having a plurality of branches. A first left branch includes the second element node and the first text node . A second right branch includes the third element node the first attribute node and the second attribute node . A third left branch includes the fifth element node the sixth element node the third attribute node and the second text node . A fourth right branch includes the seventh element node the eighth element node the fourth attribute node and the third text node .

The renderer renders step the first XHTML document. A representation of the first web page is shown in comprising a first section and a second section .

As described above the tags specify that the first XHTML document should be refreshed following a period of 150 seconds. At the end of the period the requester sends step a refresh request to the server computer in the form of an XMLHTTPRequest object.

In response to receiving the refresh request the server computer sends step a refresh response comprising a second web page to the receiver . In the example a second XHTML document associated with the second web page is included in an HTTP response sent by the server computer .

In response to receiving the HTTP response the receiver passes the second XHTML document to the parser which loads the second XHTML document into memory and parses it in order to obtain an associated second DOM. The second DOM is shown in .

The second exemplary DOM comprises a second root element node a ninth element node a tenth element node a fourth text node an eleventh element node a fifth attribute node a sixth attribute node a twelfth element node a thirteenth element node a fourteenth element node a seventh attribute node a fifth text node a fifteenth element node a sixteenth element node an eighth attribute node and a sixth text node .

A first level includes the second root element node . A second level includes the ninth element node and the twelfth element node . A third level includes the tenth element node the eleventh element node the thirteenth element node and the fifteenth element node . A fourth level comprises the fourth text node the fifth attribute node the sixth attribute node the fourteenth element node and the sixteenth element node . A fifth level includes the seventh attribute node the fifth text node the eighth attribute node and the sixth text node .

The second DOM is shown having a plurality of branches. A first left branch comprises the tenth element node and the fourth text node . A second right branch comprises the eleventh element node the fifth attribute node and the sixth attribute node . A third left branch comprises the thirteenth element node the fourteenth element node the seventh attribute node and the fifth text node . A fourth right branch includes the fifteenth element node the sixteenth element node the eighth attribute node and the sixth text node .

According to the preferred embodiment the renderer does not render the second XHTML document. Rather in response to obtaining the second DOM the parser invokes the comparator .

The comparator executes step a comparison between the first and second DOMs. A process used by the comparator will now be described with reference to wherein the comparator checks for differences between the first and second DOMs.

Preferably the comparator executes a tree walking algorithm in order to compare the first and second DOMs.

Preferably the comparator uses a tree walking algorithm which visits the first level of each DOM. If no differences are found the comparator visits one or more nodes of a left subtree of each DOM in the sequence nodes and the first branch and the second branch. If no differences are found the comparator visits one or more nodes of a right subtree of each DOM in the sequence nodes and the third branch and the fourth branch. It should be understood that any number of tree walking algorithms can be implemented.

If the comparator determines that a difference is found between the DOMs the comparator invokes the updater as will be described later.

In the example described herein the updater updates the node in the first DOM for which a difference has been found in the second DOM.

With reference to the comparator visits step the first root node and the second root element node . The comparator queries the first root node and the second root element node in order to obtain associated names. With reference to in response to obtaining the names the comparator compares step the names to determine whether the names match.

If the comparator determines that the names do not match the comparator invokes step the updater as will be described later.

In response to the names matching the comparator queries the first root node and the second root element node in order to determine step whether each of the first root node and the second root element node has a child node.

If the comparator determines that neither the first root element node nor the second root element node has a child node the comparator makes a determination step as to whether there are any further nodes to visit. It should be understood that if either the first root element node nor the second root element node the comparator determines step that there are no further nodes to visit the process ends.

If the comparator determines that one or more of the first root element node and the second root element node has a child node the comparator executes a further query.

In the example herein with reference to the comparator determines that each of the first root element node and the second root element node has a child node namely nodes and respectively . In response the comparator queries each of the first root element node and the second root element node to obtain step an object representing a list of child nodes.

In response to obtaining each list a comparison is executed wherein the comparator uses a length property of each list to return a number of nodes in the list. It should be understood that if one of the first root element node and the second root element node does not have children an associated value of the length property is 0 .

For each of the first root element node and the second root element node a length of the list is shown below 

If the lengths do not match this indicates a difference. For example if the first root element node has two children and the second root element node has three children a difference has been found.

If the lengths do not match the comparator is operable to invoke step the updater as will be described later.

In the example herein the comparator determines that the lengths i.e. 2 match and in response the comparator makes a determination step as to whether there are any further nodes to visit.

In the example herein the comparator determines that there are further nodes to visit and the comparator visits step a next node in a left subtree of each DOM. In the example herein a next node is the first element node and the ninth element node . The comparator executes the process of for the first element node and the ninth element node .

The comparator visits step the first element node and the ninth element node . The comparator queries the first element node and the ninth element node in order to obtain associated names. The comparator compares step the names to determine whether the names match.

In the example herein the comparator determines that the names namely match. In response the comparator determines step whether each of the first element node and the ninth element node has a child node.

In the example herein with reference to the comparator determines that each of the first element node and the ninth element node has a child node namely nodes and respectively .

In response the comparator queries each of the first element node and the ninth element node to obtain step a list of child nodes.

In response to obtaining each list the comparator uses a length property as described above. For each of the first element node and the ninth element node a length of the list is shown below 

In response the comparator makes a determination step as to whether there are any further nodes to visit.

In the example herein the comparator determines that there are further nodes to visit and the comparator visits step a next node in each left subtree associated with each DOM.

In the example herein a next node is the third element node and the tenth element node . The comparator executes the process of for the third element node and the tenth element node .

The comparison process for further nodes in each left subtree of each DOM will not be described further as in the present example the comparator determines that the left subtree of the second DOM is not different from the left subtree of the first DOM.

The comparator compares fourth and twelfth element nodes and respectively fifth and thirteenth element nodes and respectively sixth and fourteenth element nodes and respectively and third and seventh attribute nodes and respectively . In the example described herein the comparator does not determine any differences between corresponding nodes.

The comparator visits step the second text node and the fifth text node . The comparator queries the second text node and the fifth text nodes in order to obtain associated names. The comparator compares step the names to determine whether the names match.

In the example described herein with reference to the comparator determines that the names namely Company X is due to be sold and Company X has been sold to Company Y do not match. This indicates that a difference has been found.

With reference to the updater is operable to update step the first DOM with at least one node of the second DOM that is different from a corresponding at least one node of the first DOM. The updater will now be described in more detail.

The updater queries the node i.e. the fifth text node of the second DOM that is different from a corresponding node i.e. the third text node of the first DOM to determine an associated parent node. In the example herein the parent node is the fourteenth element node .

In response to determining the parent node the updater executes a method e.g. the method removeChild to remove the fifth text node from a list of child nodes associated with the parent node .

With reference to the updater is operable to update step the first DOM with at least one node of the second DOM that is different from a corresponding node of the first DOM. The updater will now be described in more detail.

The updater queries the node i.e. the fifth text node of the second DOM that is different from a corresponding node i.e. the third text node of the first DOM to determine an associated parent node. In the example herein the parent node is the fourteenth element node .

In response to determining the parent node the updater executes a method e.g. the method removeChild to remove the fifth text node from a list of child nodes associated with the parent node .

In response to removing the fifth text node from the list of child nodes associated with the parent node the updater uses a method e.g. the method adoptNode to adopt the fifth text node from the second XHTML document to the first XHTML document.

In response to adopting the fifth text node the updater uses a method e.g. the method replaceChild to replace the second text node with the fifth text node .

The renderer renders step the first XHTML document. A representation of the second web page is shown in comprising a first section and a second section .

With reference to the comparator makes a determination step as to whether there are any more nodes to visit.

In the example herein the comparator determines that there are further nodes to visit and with reference to the comparator uses the process of to compare seventh and fifteenth element nodes and respectively eighth and sixteenth element nodes and respectively fourth and eighth attribute nodes and respectively and third and sixth text nodes and respectively . In the example described herein the comparator does not determine any differences between corresponding nodes. In response the process ends as there are no more nodes to visit.

It can be seen in that the second web page containing a different first section from the first section of the first web page has been rendered without requiring an update to the unchanged second section .

The preferred embodiment of the present invention provides a mechanism which improves handling of regular updates to a web page. As described above regular updates to a web page can be frustrating to a user. Furthermore a full web page refresh can be very slow and cause the screen to flicker.

Advantageously the preferred embodiment of the present invention allows for update of only a changed portion of a web page. Thus a user can continue to interact with unchanged portions of the web page. Furthermore the mechanism of the present invention provides for fast updating of the web page.

Furthermore the apparatus of the preferred embodiment of the present invention is provided at the client side.

Furthermore advantageously since the apparatus of the present invention is provided at the client side no change is required at the server side. This is advantageous because server side change can be complex and can affect multiple clients if errors occur. Furthermore the extra work that would be required by the server side can result in delay at the client side. Furthermore in order to compare web pages for differences a server computer is required to store an older version s of the web page which can result in a huge storage overhead at the server computer.

It should be understood that the render step can be executed following comparison of the remainder of the DOMs.

It should be understood that the comparator can be configurable to compare DOMs starting from any node in the DOMs. For example the comparator is configurable to compare a plurality of branches of each DOM e.g. the first branch the second branch the third branch and the fourth branch . This is advantageous in that it may have been determined for example in accordance with historical statistics in accordance with an instruction from a web page developer etc. that element nodes having the names and 

It should be understood that the comparator can check for any number of differences between nodes e.g. differences in values associated with attributes .

It should be understood that the updater can update a DOM in a number of ways. In the example described herein update occurs at the node in the first DOM for which a difference has been found in the second DOM. Alternatively update can occur at the node in the first DOM for which a difference has been found in the second DOM and to update one or more associated children.

In an example the updater is configurable to update a node in the first DOM for which a difference has been found in the second DOM and to update all of its associated children.

In this example the determination step as to whether each of the first root node and the second root element node has a child node is an efficient way for the comparator to determine whether there are any differences between the DOMs at a particular level without having to visit and compare nodes at a lower level. That is if the first root element node has a child node and the second root element node does not have a child node a difference has been found at the first level of the DOM. Thus visitation and comparison of nodes at one or more lower levels below the first level need not occur. Rather the comparator invokes the updater to update the first DOM at the first level wherein the first root node and all of its associated children nodes to are updated e.g. by replacement with the second root node and all of its associated children nodes to .

The flowchart and block diagrams in the Figures illustrate the architecture functionality and operation of possible implementations of systems methods and computer program products according to various embodiments of the present invention. In this regard each block in the flowchart or block diagrams may represent a module segment or portion of code which comprises one or more executable instructions for implementing the specified logical function s . It should also be noted that in some alternative implementations the functions noted in the block may occur out of the order noted in the Figures. For example two blocks shown in succession may in fact be executed substantially concurrently or the blocks may sometimes be executed in the reverse order depending upon the functionality involved. It will also be noted that each block of the block diagrams and or flowchart illustration and combinations of blocks in the block diagrams and or flowchart illustration can be implemented by special purpose hardware based systems that perform the specified functions or acts or combinations of special purpose hardware and computer instructions.

The terminology used herein is for the purpose of describing particular embodiments only and is not intended to be limiting of the invention. As used herein the singular forms a an and the are intended to include the plural forms as well unless the context clearly indicates otherwise. It will be further understood that the terms comprises and or comprising when used in this specification specify the presence of stated features integers steps operations elements and or components but do not preclude the presence or addition of one or more other features integers steps operations elements components and or groups thereof.

The corresponding structures materials acts and equivalents of all means or step plus function elements in the claims below are intended to include any structure material or act for performing the function in combination with other claimed elements as specifically claimed. The description of the present invention has been presented for purposes of illustration and description but is not intended to be exhaustive or limited to the invention in the form disclosed. Many modifications and variations will be apparent to those of ordinary skill in the art without departing from the scope and spirit of the invention. The embodiment was chosen and described in order to best explain the principles of the invention and the practical application and to enable others of ordinary skill in the art to understand the invention for various embodiments with various modifications as are suited to the particular use contemplated.

Having thus described the invention of the present application in detail and by reference to preferred embodiments thereof it will be apparent that modifications and variations are possible without departing from the scope of the invention defined in the appended claims.

