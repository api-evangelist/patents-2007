---

title: Ontology system providing enhanced search capability with ranking of results
abstract: Ontology system providing enhanced search capability receives a search request specifying nodes and edges of interest and determines a set of matching ontologies stored in a knowledge store. The ontology system also generates a ranking for each of the matching ontologies based on the extent of matching. Data indicating the matching ontologies and corresponding rank is sent as a search result.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08468163&OS=08468163&RS=08468163
owner: Oracle International Corporation
number: 08468163
owner_city: Redwood Shores
owner_country: US
publication_date: 20070930
---
The present application is related to and claims priority from the co pending India Patent Application entitled Ontology System Providing Enhanced Search Capability Serial Number 1797 CHE 2007 attorney docket number ORCL 058 India Filing Date Aug. 13 2007 Applicant Oracle International Corporation naming the same inventors Aditya Gupta Abhishek Maheshwari and Ajay Singh as in the subject patent application and is incorporated in its entirety herewith.

The present disclosure relates to ontology management systems and more specifically to an ontology system providing enhanced search capability.

Information refers to knowledge presented in the form of data text images sounds codes and computer programs individually or in combination. One challenge in the management of information is the organization of the information to enable inference of conclusions or in general reason about the information based on the knowledge represented in the organized form. Different approaches can be used for organizing information and for inferring conclusions.

In one approach information is organized in the form of a database wherein the information is provided in the form of tables columns constraints specifying primary foreign keys restriction on each type of data etc. etc. The manner in which the information is modeled in the database is referred to as a schema. Thus a schema provides a conceptual and or physical view of the information in the database enabling inference of conclusions from the information.

In another approach information is organized in the form of an ontology system. An ontology system organizes information in the form of objects concepts or classes and relations existing among the objects concepts portions of which are referred to as a ontology . In general an ontology may be viewed as a graph containing nodes representing concepts objects etc. and edges representing links relations between the nodes. For further details of ontology systems the reader is referred to the book entitled Ontological Engineering with examples from the areas of Knowledge Management e Commerce and the Semantic Web by Asuncion Gomez Perez et al with ISBN number 1 8523 3551 3.

An ontology system generally provides such conceptualization of information while hiding the details of implementation which can be based on flat files such as XML or based on data stored in databases . As such for inference of conclusions or reasoning about information an ontology system is often considered to be more desirable compared to a database.

It is often required that a user be provided a facility to search for information of interest in ontology systems. In one prior approach the search was conducted based on keywords or text provided by a user. Such a search capability may not be adequate in several scenarios.

In the drawings like reference numbers generally indicate identical functionally similar and or structurally similar elements. The drawing in which an element first appears is indicated by the leftmost digit s in the corresponding reference number.

An aspect of the present invention enables an ontology system to provide enhanced search capability. In an embodiment the ontology system receives a search request specifying nodes and edges existing between nodes of interest and determines a set of matching ontologies stored in a knowledge store. Data indicating the matching ontologies is sent as a response to the search request.

Another aspect of the present invention generates a ranking for each of the matching ontologies. The ranking is generated based on the extent of matching of the nodes and edges of interest specified in the search request. Data indicating rank of the matching ontologies is also included in the response to the search request.

Thus by accepting edges of interest in a search request and generating a ranking based on the extent of matching of the edges of interest an ontology system provides enhanced search capability enabling a user to find desired ontologies more accurately.

Several aspects of the invention are described below with reference to examples for illustration. It should be understood that numerous specific details relationships and methods are set forth to provide a full understanding of the invention. One skilled in the relevant art however will readily recognize that the invention can be practiced without one or more of the specific details or with other methods etc. In other instances well known structures or operations are not shown in detail to avoid obscuring the features of the invention.

Merely for illustration only representative number type of systems is shown in the Figure. Many environments often contain many more systems both in number and type depending on the purpose for which the environment is designed. Each system device of is described below in further detail.

Network provides connectivity between various client systems A C and ontology server . Network may be implemented using protocols such as Internet Protocol IP well known in the relevant arts.

Each of client systems A C represents a system such as a personal computer workstation mobile station etc. and is used by a user to generate requests to ontology server . The requests may be generated according to a suitable interface.

Knowledge store facilitates storage and retrieval of information and may be implemented as a file server or as database server. In one embodiment knowledge store represents a file server storing each of the ontologies in a corresponding separate file encoded as XML data. However alternative approaches such as using database technologies permitting structured queries can also be used in implementing knowledge store .

Ontology server represents a server system such as an ontology management server which is capable of performing searches requested by client systems A C. The results of the search are sent as corresponding responses to the requesting client systems. The ontology server and knowledge store together constitute an ontology system. The manner in which ontology server performs searches requested by client systems is described below with examples.

In addition some of the steps may be performed in a different sequence than that depicted below as suited in the specific environment as will be apparent to one skilled in the relevant arts. Many of such implementations are contemplated to be covered by several aspects of the present invention. The flow chart begins in step in which control immediately passes to step .

In step ontology server maintains information in the form of ontologies with each of the ontologies containing nodes and edges linking the nodes. The information may be maintained in knowledge store . The nodes may represent concepts classes objects instances attributes properties and or events and or the like based on the manner in which the information is organized. Edges may represent links relations that exist between the nodes.

In step ontology server receives a search request specifying a set of one or more nodes and a set of edges of interest. The search request may be received from one of client systems A C. It may be appreciated that the nodes in the search request may represent concepts instances properties and or events and or the like contained in the maintained information. The edges on the other hand define links relations existing between the nodes.

In step ontology server determines ontologies matching the search request. The determination may be performed based on both the nodes and edges of interest specified in the search request. Thus an ontology in knowledge store containing the nodes and edges of interest either completely or partially may be determined to be a matching ontology.

In step ontology server generates a ranking for each of the matching ontologies. The ranking of each of the matching ontologies may be generated based on the extent to which the matching ontology matches the nodes and edges of interest specified in the search request. The ranking may be specified as an absolute value indicating the extent of match or may be a relative value indicating the extent of matching in comparison to the other ontologies.

In step ontology server sends data indicating the matching ontologies and corresponding ranking as a search result. The search result may be sent to the requesting client system. The flow chart ends in step .

It may be appreciated that ontology server provides an enhanced search capability by enabling a user to search for ontologies using concepts relations instances properties and or events existing in the information. The manner in which an ontology system enables a user to perform a search is illustrated below with examples.

Node represents a concept BLevel of interest that is to be searched in a knowledge store. The label BLevel indicates a name that uniquely identifies each node representing a concept instance property in the knowledge store. Similarly node labeled DevMgr represents another concept of interest. Node labeled Monty represents an instance and thereby shown in a dotted line in the Figure of interest.

Edge between nodes and represents a link that exists between the concepts BLevel and DevMgr . Edge between nodes and represents another link that exists between concepts DevMgr and Monty . Edge is shown in a dotted line indicating that a relation instance exists between the concepts that is Monty is an instance of DevMgr .

Thus the above search request specifies that the search be performed for a concept BLevel which is related to another concept DevMgr having an instance Monty . It may be observed that the search request may also be viewed as an ontology or as an ontology fragment .

On receiving such a search request ontology server determines ontologies matching the search request and generates a ranking for each of the matching ontologies. Data indicating the matching ontologies and corresponding rankings are then sent as the search result to the user.

In one embodiment the search result contains the identifier of each of the matching ontologies a numerical value indicating a corresponding rank and another numerical value indicating the extent of match with the search request. The manner in which the search results are sent to a user is described with examples below.

Table depicts a portion of a search result sent in response to a search request received from a user. The search result contains data indicating the ontologies matching the search request and also indicating a ranking of each of the matching ontologies. Though the search result is depicted as being presented in a tabular format it may be appreciated that in alternative embodiments the search result may be provided in any convenient desired format.

Column labeled Rank indicates a ranking of each of the matching ontologies. Column contains a numerical value 1 2 3 etc. with a lower value indicating a higher rank. Thus a matching ontology with rank 1 is determined to have a better match than another matching ontology with rank 2 .

Column labeled Search Result specifies an identifier identifying each of the matching ontologies. Column labeled Match specifies a numerical value hereafter referred to as match score indicating the extent of matching of each of the ontologies with the search request. A higher numerical value in column indicates a better match with the search request as such will have a higher rank .

Each of rows specifies an ontology determined to be matching the search request. In particular row specifies an ontology identified by the identifier ontology13 as specified in row having a rank of 1 as specified in row and having a match score of 4.0 as specified in row . Similarly row specifies an ontology identified by the identifier ontology03 having a rank of 2 and a match score of 3.5 . It may be observed that ontology13 is ranked higher than ontology03 since the corresponding match score 4.0 is greater than the match score 3.5 corresponding to ontology03 .

It may be appreciated that multiple ontologies may have the same match score and may therefore be given the same rank. The other rankings may then be appropriately changed according a pre defined convention for example by starting the next ranking with a numerical value more than the number of ontologies tied for a current rank . It may further be appreciated that in a scenario when no matching ontologies are determined the data in the search result may be modified to indicate the failure of the search.

Thus a user may send a search request as depicted in specifying nodes and edges of interest to ontology server and receive in response a search result as depicted in . The description is continued describing the manner in which ontology server determines ontologies matching a search request in an embodiment.

Ontology server on receiving a search request inspects the ontologies stored in knowledge store to determine the ontologies that match the search request. In an embodiment an ontology is considered to be matching the search request only if the ontology contains at least one node representing a concept instance or property specified in the search request. In the scenario that an ontology does not match any of the nodes specified in the search request the ontology is considered to be not matching the search request.

In one embodiment each node is associated with a corresponding name URI uniform resource identifier and matching is performed based on the name URI of the nodes in an ontology and the search request. As such a node in the ontology is determined to be matching a node in the search request if the name URI and the type concept instance property of the nodes in the ontology and the search request are the same.

Each of ontologies labeled ontology03 labeled ontology06 labeled ontology13 and labeled ontology16 represents an ontology matching the nodes and edges of interest specified in the search request depicted in . The labels associated with the ontologies may be used to identify each of the ontologies stored in knowledge store .

It may be observed that in ontology node matches node of the search request depicted in since both the nodes have the same name BLevel and are of the same type concept . As such ontology is included in the set of ontologies matching the search request.

Similarly ontologies and are also included in the set of matching ontologies since node in ontology node in ontology and node in ontology matches node in the search request. It may be observed that ontology also contains node and edge matching node and edge specified in the search request.

It may be appreciated that labels of the ontologies matching the search request may be used as identifiers in the search result as depicted in sent as a response to a search request as depicted in . As such the ontologies and correspond to the ontologies specified in respective rows and in .

Ontology server after determining the set of matching ontologies generates a ranking for each of the matching ontologies. The manner in which ontology server generates a ranking for ontologies matching a search request is described in detail below.

In one embodiment the ranking of the matching ontologies is generated based on the match score calculated for each of the matching ontologies. To facilitate calculation of the match scores ontology server first determines a numerical value indicating the importance for each node specified in the search request.

Thus the weight of a node is related to the various concepts instances and properties associated with the node and also the importance of the concepts related to the node.

Referring to the search request depicted in node is associated with a importance of 1 since node is an instance and does not have subclasses or instances or properties associated to it that is the sets D I and P are empty. As such the cardinality of each of the sets is 0 and the importance of subclasses is also 0. Substituting in the above equation 1 0 0 0 the importance of node is determined to be 1.

Node is associated with a weight of 2 since node has one instance node associated with it that is I 330. As such the cardinality of set I is 1 while for the other sets the cardinality is 0 since they are empty . Substituting in the above equation 1 0 1 0 the importance of node is determined to be 2.

For node the set D contains node since node is a subclass of node . The sets P and I are empty as node does not have any instances or properties associated with it. Further the subclass node is associated with a importance of 2. Substituting in the above equation 1 2 0 0 the importance of node is determined to be 3.

From the above it may be readily observed that the input ontology of is received as a set of nodes in a hierarchy with node Blevel being at the highest level and instance Monty being at the lowest level. The nodes at the higher level are assigned higher importance compared to nodes at the lower level. As described below ontologies of matching nodes of higher importance are computed to have a higher match score and thus ranked higher e.g. 1 .

After determining the importance of each node in the search request ontology server generates for each of the matching ontologies a match score indicating the structural similarity of the matching ontology to the search request based on the importance. The manner in which match scores of ontologies matching a search request are calculated is described in detail below.

In one embodiment the calculation of a match score is divided into calculation of two scores a node score and an edge score. The match score may then be calculated as Match Score Node Score Edge Score

Node score of a matching ontology indicates the extent to which the nodes of the matching ontology matches the nodes of a search request and is calculated using the formula given below 

Nis the weight of a matching concept set to be equal to the importance of the matching concept in the search request 

Iis the weight of a matching instance set to be equal to the importance of the matching instance in the search request 

Pis the weight of a matching property set to be equal to the importance of the matching property in the search request .

Edge score of a matching ontology indicates the extent to which the edges of the matching ontology matches the edges of a search request and is calculated using the formula given below 

A half edge represents a partial matching of an edge contained in the search request to an edge relationship existing in the matching ontology. A partial matching occurs when the type of edge relationship and only one of the nodes related by that relationship matches to corresponding node and relationship in the search request. In the above equation the weight of a half edge is assumed to be half the weight of an edge which is completely matched that is the type of edge and both the nodes linked by the edge are matched .

Referring to the node score of ontology would be 3.0 since only node matches node in the search request and node has an importance of 3.0 as calculated above . Further the edge score of ontology is calculated as 0.5 since there exists a half edge that is an edge corresponding to edge in the search request and one of the nodes linked by the edge that is the node . As such the match score of ontology is determined to be 3.5 as depicted in row in .

Similarly the match score of ontology is determined to be 2.0 node score of 2.0 edge score of 0.0 since only node matches node having importance of 2.0 in the search request and there are no matching edges. The match score of ontology is determined to be 4.0 node score of 3.0 edge score of 1.0 since nodes and match nodes and having importance of 2.0 and 1.0 respectively in the search request and edge matches edge in the search request completely. Further the match score of ontology is determined to be 2.5 node score of 2.0 and edge score of 0.5 . The match scores corresponding to ontologies and are depicted in respective rows and in .

It may be appreciated that the match score is calculated assuming that the matching nodes and edges have unit weight factors which is then multiplied by the importance of the nodes in the search request as depicted in above equations. Alternatively the weights of the matching nodes and edges may be adjusted according to the type of node edge. For example a matching instance may be given more weight compared to a matching concept. Thus the ranking may be adapted based on the types of nodes and edges matched.

Further a user may associate a weight factor for each of the nodes and edges of interest received in the search request. For example the nodes edges which occur rarely among the ontologies may be given higher weight factors than which occurs frequently. The weight factors in combination with the importance of the nodes may be used to generate the ranking of the matching ontologies thereby enabling a user to find desired ontologies more accurately.

It may be further appreciated that though the ontologies in knowledge store and the search request are depicted as graphs in the Figures for illustration implementations may employ various conventions to represent the same information.

In one embodiment as noted above knowledge store represents a file server with each of the ontologies being maintained in a corresponding file in the file server. In such an embodiment the search request depicted in is received in the form of a file containing the nodes and edges of interest. The manner in which ontologies are represented as files is described in detail below.

Line tag indicates that the data in the received search request is encoded as XML. Lines tag specify a definition of the XML to be used for validating the data contained in the search request. Lines in between tags and specify the nodes and edges of interest in the search request. Lines tag specify information about the ontology. In the example no information is specified since an empty tag is specified in line .

Lines specify the various classes concepts that is nodes in the search request. In particular line tag specifies a class with name BLevel as indicated by the attribute rdf about . It may be appreciated that the node specified in line corresponds to node in .

Similarly lines in between tags and specifies another class with name DevMgr . In line tag the class DevMgr is specified as a subclass of the class BLevel as indicated by the attribute rdf resource . As such the information in lines corresponds to node class DevMgr and link the relation subclass in .

Lines specify the various instances in the search request. In particular line tag specifies an instance of the class DevMgr having a name Monty as indicated by the attribute rdf about . The information in line corresponds to node instance Monty and link the relation instance in .

Thus nodes and edges may be specified by a user in a search request. The search request may then be sent to an ontology system providing enhanced search capability specifically having the capability of search based on both nodes and edges . The result of the search may then be received in a tabular format as depicted in .

It should be appreciated that ontology server may be implemented in a combination of one or more of hardware software and firmware. The description is continued with respect to an embodiment in which various features are operative by execution of corresponding software instructions.

Digital processing system may contain one or more processors such as a central processing unit CPU random access memory RAM secondary memory graphics controller display unit network interface and input interface . All the components except display unit may communicate with each other over communication path which may contain several buses as is well known in the relevant arts. The components of are described below in further detail.

CPU may execute instructions stored in RAM to provide several features of the present invention. CPU may contain multiple processing units with each processing unit potentially being designed for a specific task. Alternatively CPU may contain only a single general purpose processing unit. RAM may receive instructions from secondary memory using communication path .

Graphics controller generates display signals e.g. in RGB format to display unit based on data instructions received from CPU . Display unit contains a display screen to display the images defined by the display signals. Input interface may correspond to a keyboard and a pointing device e.g. touch pad mouse . Network interface provides connectivity to a network e.g. using Internet Protocol and may be used to communicate with others connected systems such as client systems A C of .

Secondary memory may contain hard drive flash memory and removable storage drive . Secondary memory may store the data e.g. portions of and software instructions which enable digital processing system to provide several features in accordance with the present invention.

Some or all of the data and instructions may be provided on removable storage unit and the data and instructions may be read and provided by removable storage drive to CPU . Floppy drive magnetic tape drive CD ROM drive DVD Drive Flash memory removable memory chip PCMCIA Card EPROM are examples of such removable storage drive .

Removable storage unit may be implemented using medium and storage format compatible with removable storage drive such that removable storage drive can read the data and instructions. Thus removable storage unit includes a computer readable storage medium having stored therein computer software and or data. However the computer or machine in general readable storage medium can be in other forms e.g. non removable random access etc. .

In this document the term computer program product is used to generally refer to removable storage unit or hard disk installed in hard drive . These computer program products are means for providing software to digital processing system . CPU may retrieve the software instructions and execute the instructions to provide various features of the present invention described above.

While various embodiments of the present invention have been described above it should be understood that they have been presented by way of example only and not limitation. Thus the breadth and scope of the present invention should not be limited by any of the above described exemplary embodiments but should be defined only in accordance with the following claims and their equivalents.

