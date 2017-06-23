---

title: Repository system and method
abstract: A repository has a database containing a number of artifacts storing data and a system device model defining various entities, including the artifacts and properties used in the artifacts. To update a system device model in database an extension package is passed to the repository. Update software identifies differences introduced by the extension package that are only permitted if the data in the artifacts is compatible and updates the database if and only if the data and extension package are compatible.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=07925636&OS=07925636&RS=07925636
owner: Hewlett-Packard Development Company, L.P.
number: 07925636
owner_city: Houston
owner_country: US
publication_date: 20070608
---
The invention relates to a method apparatus and computer program product that acts as a repository particularly but not exclusively a stateless repository.

There has been considerable interest in recent times in the provision of web services i.e. the provision of services on the internet that do not simply provide web pages for display to human users.

One approach that has been adopted to deal with this situation is a registry or repository for defining aspects of web available services. For example the universal description discovery and integration UDDI standard defines an extended markup language XML based registry that allows services to be published with details about the service provided. Such registries can be interrogated for further information which may for example include web service description language WSDL documents defining web services including protocol bindings and message formats. The registry will normally be interrogated by messages in a standard format such as the SOAP format formally an abbreviation of Simple Object Access Protocol or other suitable formats.

There are a number of models for exchanging data from a server with the data to a client to which the data is provided. In a traditional client server approach all of the information about the data format is hidden from the client that is to say encapsulated.

A development of this approach is known as the Representational State Transfer REST approach in which an artifact is transferred from a server to a client using one of a number of standard data types. The data type used for the transfer may be selected dynamically for example based on the capability or desire of the client and the nature of the artifact. The representation may include instructions in a standard format for example Java instructions where the client is known to support Java.

The interface does not reveal whether the data type used for the transfer is the format stored by the server to store the data or merely a derivation of that format so in this sense there is encapsulation.

The REST approach is a stateless approach that is to say the server does not store the state of the session with the client. The session state is therefore kept only on the client.

The unit of stored data is an artifact which may be thought of as a general object or resource in general containing data code or some defined mixture. The artifact is the access unit for the contents of the database and each request received from a client returns only one artifact .

The definitions of the artifacts are stored in a special file in the repository namely a SOA definition model SDM or object model which is in the form of a document which stores format details of a number of different types of artifacts. The SDM will also be referred to simply as the definition model. In the embodiment the SDM is an XML document defining a number of artifacts and attributes of the artifacts which will be referred to as properties. The abstract definition of a property of an artifact will be referred to as a property descriptor.

Each artifact is defined in the SDM to have one or more properties which may be either required or optional. Required properties for example may include a name of the artifact and a unique numeric ID.

Optional properties may include for example a geographic location property defining the geographic location that created a particular instance of the artifact may be defined as optional.

The database stores in addition to the SDM model instances of artifacts compliant with the definitions in the SDM model . Relations between instances of the artifacts are indicated schematically using arrows. The relations are from a source artifact to a target artifact and are considered to be properties of both the source artifact and the target artifact.

As will be appreciated it is normally necessary to update the data model from time to time in order to cope with changes in business process or the data that is collected. However such updates may cause incompatibility issues with data already in the database. Referring to an embodiment illustrating updating the SDM will now be described which takes account of these issues.

Firstly a copy of the SDM file is sent from the repository to the client . The client includes the software for editing the SDM. The embodiment uses XML so the client software may be as simple as text editor but a bespoke SDM model editor may also be used.

The user updates the SDM model on a client . During this process initial checks on the validity of the updates to the SDM are performed.

When the user has made the desired amendments the user can the upload the changes to the database by creating an extension package and sending it to update software located in the repository . The creating step also includes a number of validity checks on the extension package which is not created if it is internally inconsistent or inconsistent with the remaining unchanged portions of the SDM . In the embodiment the extension package is a Java Archive JAR file.

The update software then carries out a number of checks based on information provided to it via communication lines and that provide bidirectional communications between the update software and the SDM .

Firstly the update software identifies the changes in the extension package and classifies each change as a compatible change a non compatible change or a non allowed change.

Compatible changes are those changes that are allowed regardless of the contents of the artifacts stored in the database . The set of compatible changes include changes of addition that is to say 

modifying an SDM entry in a way that does not have an effect on data. In particular instead of deleting an SDM entry it is possible to deprecate it.

Non compatible changes are changes that may or may not be allowed depending on the content of the database.

Some changes may simply be non allowed regardless of the state of the database. These include changes to any definition in the SDM file that conflicts with other parts of the SDM file. For example changing the categorization of an object in an object taxonomy is non allowed once the object has been categorised it will have this value and cannot be changed.

The update software identifies non compatible changes and then gets data from the database to check whether there are any instances of artifacts not compatible with the changes.

The check is performed if there are no incompatibilities the update software updates the SDM file in the repository . If there is any incompatibility the update software returns a message to the client indicating failure and also indicating the reasons for that failure.

Thus by providing a limited but still useful number of changes to the model that may be made using the update file the possibility exists for users or programmers to update the SDM model in a controlled and reliable way without risking data incompatibility with the contents of the database. This allows for changes to the model to be introduced even after the database is in use i.e. populated with data.

In the above example a predetermined set of non compatible changes to the SDM is permitted if and only if the content of the database is appropriate.

In other examples the predetermined set of changes may vary slightly with suitable adjustments to the checks.

A particular example will now be described in more detail. In the particular example the SDM model is an XML file which contains a number of the following entities as appropriate.

Firstly the SDM model includes taxonomy descriptors which describe taxonomies used for categorizing property descriptors see below .

Secondly the SDM model includes predetermined property types i.e. base types such as string integer and other types that may be used for properties.

Thirdly the SDM model includes property descriptors i.e. descriptors specifying for each property the type of values stored by the property whether a taxonomy or a property type as well as further information such as XML serialisation and value range if required.

Fourthly the SDM model includes artifact descriptors declaring XML serialisation and a list of properties for artifacts. Some artifacts can be abstract i.e. instances of the artifact are used as base classes for other artifacts. The properties are defined as being required where a single instance of the property must be defined for the artifact optional if the property is optional or multiple if plural instances of the property are possible.

Fifthly the SDM model can include artifact taxonomies relating the artifact to other artifacts possibly using inheritance.

The client software in the embodiment is a user interface tool that takes the existing SDM from the repository . As well as changing the model the embodiment of the user interface tool also allows changing taxonomies configuration files and Java code contained in artifacts in the database.

The tool permits only certain changes to the SDM namely the changes discussed above as being compatible or non compatible not changes that are not allowed regardless of the content of the database.

Note that the list of non compatible changes includes changing a property from optional or required to multiple from multiple to optional or required or from optional to required.

Once the changes have been created on the tool they are returned to the repository for updating the SDM file in the repository.

A particular feature of the invention is that the extension packages can be used to update multiple instances of the repository. In particular there may be multiple users of repository software in different organisations all of which will wish to update their software and in particular the SDM as improvements are made. The extension package allows changes to be disseminated to a number of users in the form of the extension package but only implemented by the user if their data is compatible with the extension package.

Further the update software in the repository may be configured to install multiple extension packages simultaneously.

Conveniently the existing SDM is also configured as an existing package in the same format as extension package and the update software merges these two packages as illustrated in .

In this approach a core file has both model information SDM and user interface information. The extension package is represented by extension file which contains updates to the model information as well as updates to the user interface.

These are merged together by update software in merge step to produce a merged model file subject to satisfactory testing as explained above.

The user interface is updated by its bindings to the SDM. So if a new property is added a user interface configuration is added to allow it to be changed. Similarly if an artifact or property is removed from the SDM corresponding configuration options are removed from the user interface.

Then the other features contained in the update file in addition to the model are also merged. In particular in an aspect generation step the update software creates a merged i.e. updated user interface . The update software also creates client packages including code necessary for running on the client . In general these other features will not directly use the database although they may be dependent on changes to data in artifact properties so in general the changes implemented in aspect generation step are not tested against the data stored in the database in the same way as changes to the SDM.

In alternative embodiments however some permitted changes to the other features may potentially have conflicts with data in the database and accordingly checks may be introduced for these changes also.

The server is configured in this example as a REST repository which stores a plurality of artifacts . The repository is accessed through a web service interface which in the example is a UDDI interface. In the example the repository is accessed by http GET and POST instructions.

An application programming interface API acts as an interface between the repository and the database .

A number of instances of the artifact s defined in the SDM are created and stored in the database . As will be appreciated there may be one many or indeed no instances of any particular defined artifact stored in the database.

In the embodiment the relations are stored in a separate table in the database storing all relations and this table is separate from the remainder of the features of each artifact.

The client and repository and links between them may be implemented using standard computers and networks of computers using one or more data storage devices and one or more processors as is known to those skilled in the art.

Those skilled in the art will realise that any alternative way of storing the data for example in database tables may be used instead. For example the specific way in which data is stored in the repository can match exactly the format of the messages described. Indeed the REST framework allows data to be stored in the repository in any convenient way as long as the artifact can be formatted correctly when returned to the client.

