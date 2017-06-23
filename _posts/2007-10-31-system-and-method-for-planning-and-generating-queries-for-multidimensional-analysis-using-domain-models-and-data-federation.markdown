---

title: System and method for planning and generating queries for multi-dimensional analysis using domain models and data federation
abstract: Data integration and data analysis using computing equipment, software as well as hardware, includes a system and method for integrating data from various data sources, structured and unstructured, without physically creating a data warehouse and automatically generating queries for analysis of the integrated data from a multitude of different views.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=07716174&OS=07716174&RS=07716174
owner: International Business Machines Corporation
number: 07716174
owner_city: Armonk
owner_country: US
publication_date: 20071031
---
This patent application is a continuation of U.S. patent application Ser. No. 11 037 909 now U.S. Pat. No. 7 337 170 filed on Jan. 18 2005.

The present invention relates to data integration and data analysis using computing equipment software as well as hardware and more particularly to a system and method for integrating data from various data sources structured and unstructured without physically creating a data warehouse and automatically generating queries for analysis of the integrated data from a multitude of different views.

In recent years industry trends toward mergers and acquisitions has forced most OEMs to re think their processes to account for the multitude of data sources used by the various corporate divisions within the enterprise for storing and manipulating product data including the product bill of materials parts catalog diagnostic procedures and warranty claims as a partial list of the kinds of product data that exists.

Government regulations rising production cost shorter time to market are yet other reasons why companies are looking for a more adaptive and dynamic information technology IT infrastructure that would scale to the on demand era for product life cycle management.

The complexity of the IT environment in the industrial manufacturing sector has grown exponentially over the years creating problems. Some attributes of these problems include 

The increasingly complex nature of the product itself as measured by the number of components that goes into the making of a product and the umber of configurations for each product. This translates into increased storage and processing capacities for managing the information associated with the product design that could be in the order of a terabyte for just one product model.

The lack of visibility across the product life cycle due to the disparity of data management systems used in the different stages of the design development manufacturing process and services after sales. A large number of heterogeneous systems that are in use throughout the extended enterprise create an artificial barrier for information sharing.

The product design is often organized in silos around specific product assemblies in the case of automobiles e.g. wing design engine design body structure design interior design etc making it difficult to integrate data across multiple divisions. While the project team is often composed of a multi disciplinary group of engineers the IT tools remain too fragmented and specifically tailored to the organization or division that uses them the most.

In this environment traditional approaches for data integration using data warehousing does not always scale well. A data warehouse is a copy of transaction data specifically structured for querying analyzing and reporting. A data warehouse can be normalized or denormalized. It can be a relational database flat file hierarchical database object database etc. Data warehouse data often gets changed. Data warehouses often focus on a specific activity or entity. Data warehouses are usually designed to meet the requirements of one specific application and are not easily extensible without tearing down and rebuilding the table schema. They provide a fixed view on the data and are not easily adapted to changing business needs such as when new suppliers are integrated into the value chain.

Furthermore product data tends to be deeply hierarchical in nature and has associated semantics and access control procedures that are encapsulated within the data management system that hosts the information and cannot be easily exposed to external applications. In order to safeguard the integrity of the data that is owned by any given partner the industry had traditionally resorted to product data exchange where each partner exports a subset of the data that is stored within its domain and shares the data with other partners by mean of data replication. This approach tends to be slow and costly as multiple iterations may be required to provide the information that is needed. The approach leads to data redundancy where multiple replicas of the same work product could exist within the extended enterprise and requires additional complexity for managing the life cycle of the exchanged information.

As industry transforms its processes to better leverage the resources and know how of the extended enterprise a new approach based on data federation emerges as it promises to deliver on speed and accuracy both of which are needed to quickly predict and pinpoint weaknesses in a product design and performance. Delivering on such a promise requires a better understanding of the semantic and data models that are prominently used in the industry.

In the following description the automotive industry will be used as an illustrative example of an application of the present invention. However the invention is not to be construed as being limited solely to the automotive industry. A generic product structure is a hierarchical structure of generic concepts or functions such as the vehicle body structure or the vehicle hydraulic system. The generic product structure describes a logical aggregation of the vehicle assemblies and serves as a template for creating the detailed product structure. As such the generic product structure can be used to define the common concepts e.g. seats that are shared among similar product classes e.g. SUV and passenger cars .

An ontology is a specification of a conceptionalization. That is an ontology is a description like a formal specification of a program of the concepts and relationships that can exist for an agent or a community of agents. A common ontology defines a vocabulary with which queries and assertions are exchanged among agents. A commitment to a common ontology is a guarantee of consistency but not completeness with respect to queries and assertions using the vocabulary defined in the ontology. An automotive vehicle ontology is an annotated meta model of the generic product structure and processes that can execute against such structure. It augments the generic product structure with various relationships and dependencies that may exist between the different components but cannot otherwise be expressed in the generic product structure or the detailed product structure. For example the generic product structure for a vehicle may contain a placeholder for the wheel assembly. The vehicle ontology augments this assertion by defining a similar to relationship between the wheel assembly of a sports same product class. One derived benefit of such ontological relation is to broaden the scope of the search to a wider set of data sources that otherwise would not have been considered.

The vehicle ontology provides the foundation for defining a common semantic model of the product structure with all the associated engineering processes that execute against the product structure as shareable business objects. is a block diagram of one possible vehicle ontology.

Reducing warranty costs by conducting a deep failure analysis and improved claim processes have been identified as a strategic initiative by many in the automotive industry. While OEMs continues to strive to manage warranty payout while improving supplier recovery for failed parts they recognize the value of proactive failure. identification. The objectives of these efforts are to reduce the cost of warranty through identification of warranty issues more quickly than has been previously achieved and thereby reducing costs and enhancement of brand loyalty by demonstrating a commitment to the reliability and quality of products carrying the brand name.

Earl warning and failure analysis solutions focus on applying data mining and analytics against a wider set of data sources including warranty claims call center contacts vehicle bills of materials supplier parts catalog suppliers bulletins and other attributes for how and where the vehicle is used. The analytics aims at identifying trends patterns and abnormalities at an early stage and creating a knowledge model that can be used by the quality engineers to anticipate any major recall.

The present invention provides a system and method for planning and generating queries for multi dimensional analysis across divisions in an entity using domain models and data integration.

A principal object of the present invention is therefore the provision of a system and method for integrating federating data from various data sources structured and unstructured.

An object of the present invention is the provision of a system and method for executing human friendly queries over integrated data sources.

Another object of the present invention is the provision of a system and method for automatically planning and generating physical queries to integrated data sources from human friendly queries.

A further object of the present invention is the provision of a system and method for analyzing integrated data sources from a multitude of views and dimensions without physically building a data warehouse and or OLAP data warehouse for analysis processing data remodel e.g. a star or snow flake schema which are traditional approaches to multi dimensional analysis.

A still further object of the present invention is the provision of a system and method for creating semantic models for a domain for data integration and analysis.

A yet further object of the present invention is the provision of a system and method for generating and recording mappings between the semantic model and data sources.

A still another object of the present invention is the provision of a system and method for using a data federation system for structuring the access of data from unstructured data sources.

A yet another object of the present invention is the provision of a system and method for using a report system for generating reports for multi dimensional analysis.

Further and still other objects of the present invention will become more clearly apparent when the following description is read in conjunction with the accompanying drawing.

Referring now to the figures and specifically to there are shown a semantic model for automotive diagnostics and an expanded semantic model respectively. A semantic model ontology is a formal explicit description of classes i.e. concepts in a domain of discourse e.g. automotive properties of each class describing its attributes relations with other classes being a special kind of properties e.g. subclass equivalentClass etc. properties of relations e.g. transitive symmetric inverse etc. and constraints on properties e.g. cardinality etc. . Knowledge base often indicates a semantic model together with a set of individual instances of classes. The theoretical foundation of semantic models and technologies include logic First Order Logic and Description Logic knowledge representation of artificial intelligence AI and symbolic computation. The advantages of using semantic models include 1 the models provide a means to express rich semantics of concepts and relations of domains and 2 the models provide a means to query knowledge base with automated reasoning inferencing .

The first step in realizing all these benefits is to create a mapping between the semantic model and the underlying data sources. Unfortunately this task is not straightforward because often the structures of data sources vary drastically. It is also necessary to handle a multitude of data sources in an enterprise environment. Moreover some sources do not have much structure e.g. semi structured or unstructured data . The mapping creation step is described below in conjunction with .

Once the initial mapping is bootstrapped by utilizing naming similarities then the system can make further mapping suggestions regarding neighboring concepts in neighbor mapping manager . For example once the phone number concept in the domain model is mapped to the pnum column in a table in the IT model the system can suggest that the address concept neighboring with the phone number concept be mapped to the addr column in the table. Again the system would suggest the mapping and a human makes the final mapping decision. In this way the system can incrementally build mapping information by using prior mapping and human interaction. Also after the mapping process the user can add more semantics if necessary to the classes and properties in the model such as symmetry transitivity inverse etc. by means of an annotation manager . The final mapping yields a new domain model and IT model .

The database sources are located on one or more servers or alternatively are located on the World Wide Web.

As explained above one of the advantages of using semantic models is the ability to express rich semantics of concepts and relations and use the semantics in answering queries providing automated reasoning and inferencing based on logic . show some examples of such reasoning with semantic queries. The ontology query server supports the automated reasoning capability.

The query result returned by the data sources is federated by the data federation system and then passed to the report generator which can generate reports regarding various useful multidimensional analyses.

The mapping server is a build time tool described in conjunction with which is used to create semi automatically the mapping information between semantic models and IT models. The mapping server identifies tables views and columns defined in them in the IT model that present relations in the domain model. It is possible to semi automate the process by using some heuristics machine learning and or statistical approaches. The semantic model may be defined in terms of a domain tree. Also if is possible to define some simple rules for creating joins when necessary.

The user analyst submits the query through Query GUI . The Ontology Query Generator translates the submitted query to an ontology query in server in N3 format. An example of a user query is as follows 

The Result Set is used by the SQL Query Plan Generator to compose a SQL query. The Result Set can be shown to the user for selecting dimensions of interest for the composition.

The SQL Query Plan Generator composes a SQL query by using the Result Set from Ontology Query Server and Mapping information from Mapping Server . An example of a SQL query is as follows 

The GROUP BY dimension can be any dimension from the list. The query basically creates a cube view over aggregated counts of the given Failure Code. The query is submitted to data sources and via the Data Federation System which retrieves data instances from the data sources. The retrieved data instances are displayed as a report by the Report Generator e.g. Alpha Blocks . The analyst reviews this report and decides on the next query repeating the above steps.

Drill down and roll up is an important query type of OLAP along with aggregation. Ontology query can help compose drill down and roll up queries.

The SQL Query Plan Generator composes a SQL query by using the Result Set and Mapping information. The SQL query is 

The query is submitted to data sources and via the Data Federation System DB2II which retrieves the data on the fly. Note that in traditional OLAP systems all the aggregation values are pre computed.

The user continues the analysis by finding classes and data directly related to the given Failure Code. A user query example is 

The secondary dimensions can be used by the SQL Query Plan Generator to compose a SQL query. The secondary dimensions along with direct dimensions can be shown to the user for selecting dimensions of interest for the composition. The SQL Query Plan Generator composes a SQL query by using the Result Set and Mapping information. A SQL query is 

The SQL Query Generator composes a SQL query by using the Result Set and mapping information. A SQL query is 

It will be understood by those skilled in the art that while the above description refers to the automotive industry in examples in describing the invention the invention is not so limited and is applicable to any situation where there is a use for planning and generating queries for multi dimensional analysis of data.

While there has been described and illustrated a system and method for planning and generating queries for multi dimensional analysis using domain models and data federation it will be apparent to those skilled in the art that modifications and variations are possible without deviating from the broad teachings and spirit of the present invention which shall be limited solely by the scope of the claims appended hereto.

