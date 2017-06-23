---

title: Taxonomy editor
abstract: A repository  stores metadata, including at least one taxonomy definition  and records , which may be classified using the defined taxonomies. An editor  may be used to edit taxonomy definitions, using a local copy . To check the edit, a taxonomy search service in repository  may be called to check for consistency, whether or not the data in the repository  exposed on repository interface 
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=07765188&OS=07765188&RS=07765188
owner: Hewlett-Packard Develoment Company, L.P.
number: 07765188
owner_city: Houston
owner_country: US
publication_date: 20070608
---
There has been considerable interest in recent times in the provision of web services i.e. the provision of services on the internet that do not simply provide web pages for display to human users.

One approach that has been adopted is a registry for defining aspects of web available services. For example the universal description discovery and integration UDDI standard defines an extended markup language XML based registry that allows services to be published with details about the service provided. Such registries can be interrogated for further information which may for example include web service description language WDSL documents defining web services including protocol bindings and message formats. The registry will normally be interrogated by messages in a standard format such as the SOAP format or other suitable formats.

In order to classify the information various classification schemes known as taxonomies can be adopted. For example Dun and Bradsheet have defined numbers in the data universal numbering system D U N S . Each business that has applied for such a number has a single unique number assigned to it. Another taxonomy is the ISO 3166 Geographic taxonomy which assigns a number representing a geographic location. Further examples include taxonomies that assign numbers to different types of business service so one number indicates a supplier of courier services and another number indicates a supplier of photocopying services.

In general a single entry may include a number of such codes in a number of taxonomies. For example an entry may include the D U N S number to identify the service provider an ISO 3166 code to indicate the geographic location and other numbers indicating the service provided. The provision of multiple codes allows the search for a number of different aspects of the data entry provided for example it allows a user to search for a particular geographic location.

The definitions of a taxonomy may change over time. New codes may be introduced for new categories former codes merged or deleted and the definitions of specific codes may change.

The metadata repository is in communication with a taxonomy editor which in the example is an application running on a separate client workstation. The taxonomy editor retrieves one or more taxonomies from the repository creating a local copy of the one or more taxonomies edits the local copy and returns the edited local copy to the repository to update the taxonomies there.

The resources are in this example resources having a categoryBag definition which includes entries based on the taxonomies . In the particular example these entries are keyValue entries.

For example the UDDI specification defines categoryBag elements which may include one or more keyedReference elements. Each keyedReference element includes three items keyvalue keyName and tModelKey. The first is the value of the code i.e. the value that is searched. The keyName is a convenient human readable label. The tModelKey defines the classification scheme generally by using a universally unique identifier uuid . Thus a categoryBag element including both the D U N S number and the ISO 3166 geographic code will have a first keyedReference element including the D U N S number as the keyValue and the tModelKey as a uuid for the D U N S taxonomy and a second keyedReference element including the ISO 3166 geographic code as the keyvalue a human readable element such as US CA for the keyName and a uuid for the ISO 3166 geographic code as the tModelKey.

Consider as an example the taxonomy failure impact a very simple taxonomy that includes values such as low medium and high reflecting the impact of a particular failure on a business.

Another abstract taxonomy Business service may include a property failure impact that is defined to have values from the Failure impact taxonomy. Thus a taxonomy is effectively used as a data type. Any change to the definition of the Failure impact taxonomy can thus affect the business service taxonomy. The abstract taxonomy Business type is in the example not intended for use itself but as the basis for further taxonomies that are defined by inheritance based on Business type .

The properties of the artifact are represented in XML in the example. As an example consider a business service artifact defined as follows 

The artifact is defined to have a number of properties which are specified by XML statements in the form or data where the property name is name of property. Thus in the example the revision property has the numeric data 2 . This indicates the second revision of the artifact.

A further example is the property criticality name which in the example takes the value Low . This value is taken from a taxonomy defined at a uri uddi systinet.com soa model taxonomies impactLevel and having a value defined at the url uddi systinet.com soa model taxonomies impactLevel low. Thus it will be seen in this example that the property is effectively typed that is to say it can have only predetermined values defined in the taxonomy definition file explicitly referenced in the instance of the artifact.

The example also has a categoryBag property that may be used to store a number of different types of taxonomy information i.e. untyped or free format data. In he example the artifact has a defined category value of Agriculture Forestry and Fishing from the taxonomy defined at uddi 70a80f61 77bc 4821 a5e2 2a406acc35dd which defines a particular business service area and a further category value of change management from the taxonomy defined at uddi systinet.com. In particular the artifact may have properties defined to store data.

Thus when creating an instance of the business services artifact any property from any taxonomy may be used to classify the instance even if this was not foreseen when designing the artifact.

When a taxonomy is updated this can create a number of difficulties. Firstly there may be resources stored in the repository that are classified using either a complete taxonomy that no longer exists or codes defined in an earlier version of the taxonomy that no longer exist in the updated version.

Accordingly the metadata repository exposes a number of routines on the UDDI interface which are called by the taxonomy editor to carry out a check. The check is accordingly carried out through cooperation between the repository and editor.

In more detail the check carries out the following steps as illustrated in . Note that the steps in the taxonomy editor are on the left side of and the steps carried out in the repository are on the right side.

For each taxonomy indicated in the editor as being required to be checked including deleted taxonomies the taxonomy editor calls the repository to execute a specific routine check on that taxonomy. The taxonomy editor then calls three further check routines in turn to check different aspects.

The first check is simply to find any other taxonomy with the same ID as the checked taxonomy that is to check for duplicate taxonomies.

The second check is to find inconsistencies between the model definition of the checked taxonomy and other taxonomies that is to say to find and return any data type that refers to a taxonomy that has been deleted or values of a taxonomy that has been deleted.

The third check is to find records using a checked taxonomy or an entry in the checked taxonomy that is no longer present. In the example of a deleted Failure impact taxonomy the third check will return any records using this as a data type when called using the Failure impact taxonomy as the checked taxonomy such as the Business Method artifact defined above.

The fourth check is to check the values in categoryBag records against the checked taxonomy and returning the records including any values that do not appear in the current version of the checked taxonomy. Thus if the Failure Impact taxonomy is edited so that it no longer includes the value low the instance of the Business Method artifact defined above that uses this value low will be returned.

The third and fourth checks together thus return all records that are no longer compatible with the checked taxonomy. In alternative implementations these two checks could be run with a single query.

Each of the checks in turn are then repeated for each taxonomy to be checked until all taxonomies have been checked. Inconsistencies are then displayed .

In this way the taxonomy check an be carried out even if the repository is a stateless repository such as a REST repository and in particular in spite of the lack of a record kept in the repository of the state of the taxonomy editor.

Conveniently the check can be carried out for all taxonomies amended in the editor or for all taxonomies.

The check then returns a screen with a tree structure indicating any difficulties on the client which may be used to correct any problems. The screen displays any taxonomies that have been returned in the first and second checks and artifacts in taxonomies that have been returned in the third and fourth checks.

Although in the simple example given it would be relatively straightforward to carry out the checks manually taxonomy systems and resources can get very complicated and where there is a lot of inheritance it can be essentially impossible to check manually all possibilities. The example illustrates a convenient and reliable way of carrying out the check.

Of course those skilled in the art will realise that many changes may be made to the example above as required. For example the repository and editor can be provided on a single computer system or a networked system and the various data storage devices can again be local or networked as required.

