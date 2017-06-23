---

title: Apparatus and method of customizable model import and export to and from XML schema formats
abstract: In one embodiment the present invention includes a computer-implemented method of converting first metadata to second metadata using a mapping and custom exits. The metadata is at the M1 level and the mapping is generated based on information at the M2 level. The custom exits provide programmable mapping rules in addition to the mapping. In this manner, metadata created in one modeling environment may be used in another modeling environment.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08112738&OS=08112738&RS=08112738
owner: SAP AG
number: 08112738
owner_city: Walldorf
owner_country: DE
publication_date: 20070926
---
The present invention relates to model transformation and in particular to customizable model import and export to and from extensible markup language XML schema formats.

Unless otherwise indicated herein the approaches described in this section are not prior art to the claims in this application and are not admitted to be prior art by inclusion in this section.

A model is a representation of the structure and or behavior of an application or system. A representation is based on a language that has a well defined form syntax meaning semantics and possibly rules of analysis inference or proof for its constructs. The syntax may be graphical or textual. For building a concrete model some infrastructure is needed for example how should the semantics look etc. A metamodel may be used to make a language for model. Metamodeling is the process of designing languages through meta and meta meta notations. These notations help to ensure syntactically correct specifications as well as in the construction of customizable modeling. The idea behind metamodeling is to provide Tool and Data interchange between many different tools.

The state of the art in metamodeling is using a fixed metamodel for a specific area. With the rapid changes in business logic the need for freely created metamodels is growing up with the rapid changes in business logic. In answer to this demand for modeling the Object Management Group OMG has introduced the concept of a Meta Object Facility MOF in the framework of a model driven architecture MDA .

The MOF is the OMG s adopted technology for defining metadata and representing it as common object request broker architecture CORBA objects. An MOF metamodel defines the abstract syntax of the metadata in the MOF representation of a model. The MOF model itself describes the abstract syntax for representing. MOF metamodels can be represented using a subset of unified modeling language UML syntax. The MOF Model is made of two main packages in MOF 2.0 essential MOF EMOF and complete MOF CMOF .

The M0 level contains the run time instances of the user. The instances have data that is used by the instances. The instances can be in different forms for example as databases. The elements of the M0 level may be generally referred to as data . Specific examples of M0 instances include a customized order management process and a specific purchase order.

The M1 level contains models for example a UML model of a software system. Each element in the M0 level is an instance of an element of the M1 level . M1 elements directly specify what instances in the M0 world look like. The M1 level is the traditional understanding of a model . The elements of the M1 level may also be generally referred to as metadata since they are meta to the data of the M0 level . Specific examples of M1 elements include the web service description language WSDL an order management process component and a purchase order business object.

The elements that exist at the M1 level for example class attributes and other model elements are themselves instances of classes at the M2 level . An element at the M2 level specifies the elements at the M1 level . The same relationship that is present between elements of levels M0 and M1 exists between elements of M1 and M2. Every element at M1 is an instance of an M2 element and every element at M2 categorizes M1 elements. The model that resides at the M2 level is called a metamodel since it is meta to the model of the M1 level . UML extensible markup language XML schema definition XSD and common warehouse metamodel CWM are examples of such languages. Specific examples of M2 metamodels include process components business objects and integration scenarios.

Every element at M2 is an instance of an M3 element and every element at M3 categorizes M2 elements. The M3 level defines the concepts needed to reason about concepts from the M2 level . Within the OMG the MOF is the standard M3 language. All modeling languages like UML XSD CWM and so on are instances of the MOF. The elements of the M3 level may be generally referred to as meta metamodels since they are meta to the metamodels of the M2 level .

Another example of a MOF is SAP s Modeling Infrastructure MOIN . MOIN is a development project within SAP s NetWeaver organization. One aspect of the MOIN project is to implement the platform for SAP s next generation of modeling tools.

Eclipse is an open source community whose projects are focused on building an extensible development platform runtimes and application frameworks for building deploying and managing software across the entire software lifecycle. Eclipse project categories include enterprise development embedded and device development rich client platform rich internet applications application frameworks application lifecycle management ALM and service oriented architecture SOA .

The Eclipse modeling framework EMF is a modeling framework and code generation facility for building tools and other applications based on a structured data model. From a model specification described in extensible markup language XML metadata interchange XMI EMF provides tools and runtime support to produce a set of Java classes for the model a set of adapter classes that enable viewing and command based editing of the model and a basic editor. Models can be specified using annotated Java XML documents or modeling tools like Rational Rose then imported into EMF. EMF is another example of an M3 level model.

Given two types of M3 level models for example MOIN and EMF it is desirable that metadata created with one type of M3 model be accessible by the other type of M3 model. Current implementations of integration tools are lacking in ease of use and it is cumbersome to implement new integration tools for additional metamodels. EMF provides a default mapping for importing XSD to EMF metamodels but does not allow the developer to influence the generated models manually for each M2 metamodel a model importer has to be written manually to import M1 instances and make them compliant with the M2 metamodel.

As another example EMF currently only generates a trace mapping that is used only for informational purposes and is not used any further. Given the EMF trace mapping a developer must program a complete importer function to import a M2 metamodel into MOIN without having any reuse option.

Thus there is a need to reduce efforts for writing import and export tools for model component integration purposes. More specifically there is a need for processing instances of metamodels at the M2 level to create corresponding M1 instances.

Thus there is a need for improved model integration tools. The present invention solves these and other problems by providing an apparatus and method of customizable model import and export to and from XML schema formats.

Embodiments of the present invention improve model integration tools. In one embodiment the present invention includes a computer implemented method of converting first metadata to second metadata. The first metadata is related to a first model and the second metadata is related to a second model. The method includes providing a declarative mapping between a first metamodel and a second metamodel. The first metamodel relates to the first model and the second metamodel relates to the second model. The method further includes providing custom exits. The custom exits provide programmable mapping rules in addition to the declarative mapping. The method further includes applying the declarative mapping and the custom exits to the first metadata to result in the second metadata.

A computer system according to an embodiment of the present invention may include software components that implement the above described method.

A computer readable medium according to an embodiment of the present invention may include software components that implement the above described method.

In accordance with embodiments of the present invention metadata developed in one modeling environment for example Eclipse may be used in a different modeling environment for example MOIN and vice versa.

The following detailed description and accompanying drawings provide a better understanding of the nature and advantages of the present invention.

Described herein are techniques for customizable model import and export to and from XML schema formats. In the following description for purposes of explanation numerous examples and specific details are set forth in order to provide a thorough understanding of the present invention. It will be evident however to one skilled in the art that the present invention as defined by the claims may include some or all of the features in these examples alone or in combination with other features described below and may further include modifications and equivalents of the features and concepts described herein.

The following description makes specific references to Eclipse EMF and MOIN. However the principles of embodiments of the present invention may be applied to other types of metadata technologies and modeling technologies.

As new MOIN based tools are developed metadata produced with other tools based on other technologies is desired to be accessible from MOIN and vice versa . According to one embodiment of the present invention read only import of external XSD based content and read only export of MOIN models to XSD based standard formats are performed. As an import example an embodiment of the present invention allows MOIN to reference WSDL XSD created by WTP Eclipse Web Tools Project . As another import example an embodiment of the present invention allows MOIN to reference WebDynpro content. As an export example an embodiment of the present invention allows MOIN to export Core Component Technical Specification CCTS data types as XSD.

On the left are data and models related to a first format for example XML and XSD information. This XML and XSD information includes WSDL information at the M1 level XSD information at the M2 level and XSD schema information at the M3 level . The WSDL information is an instance of the XSD information which is itself an instance of the XSD schema . Referring back to the WSDL information at the M1 level may also be referred to generally as model data or metadata. The metadata may be in a format determined by the model. 

On the right are data and models related to a second format for example MOIN information. This MOIN information includes MOIN metadata at the M1 level a MOIN metamodel at the M2 level and a MOIN meta metamodel at the M3 level . The MOIN metadata is an instance of the MOIN metamodel which is itself an instance of the MOIN meta metamodel .

In the center are software components and files related to the import and export of the metadata and related model data. A default metamodel import component at the M2 level uses a default metamodel mapping at the M3 level to relate the XSD information and the MOIN metamodel . The default metamodel import component generates a mapping component . In addition custom exits may be generated. A model import component uses the mapping component and the custom exits to transform the WSDL information to the MOIN metadata at the M1 level .

At the M1 level the idea is to use the model importer that can be configured with mapping information between the XSD schema of the source artifact e.g. wsdl.xsd and the target MOIN metamodel of the target artifact e.g. WSDL metamodel . Using this mapping the model importer finds the correct output meta model element to instantiate for a given XML DOM document object model element on the input side. The corresponding export works in a similar fashion in the opposite direction.

Even though this mapping approach may suffice for most cases where only simple mappings are used some complex mappings may be hard to express by direct one to one mappings. For such cases and also for processing different referencing mechanisms of XSD the custom exits may be provided for specific XSD and or metamodel elements.

According to one embodiment the MOIN metamodel as well as the mapping table used for a given XML schema like WSDL may be provided manually. According to another embodiment the MOIN metamodel may be generated from a given XML schema and at the same time the matching mapping may be generated. Afterwards any modification of the MOIN metamodel may be reflected either in updates to the corresponding mapping or in additional custom exits and vice versa .

The process converts first metadata to second metadata. These metadata reside at the M1 level see . The first metadata is related to a first model at the M1 level and the second metadata is related to a second model at the M1 level . The first metadata and the first model at the M1 level are instances of a first metamodel at the M2 level see . The second metadata and the second model at the M1 level are instances of a second metamodel at the M2 level see .

As an example with reference to the first metadata may be the WSDL information and the second metadata may be the MOIN metadata . As another example the first metadata may be persisted in an XML based format for example EMF and the second metadata may be persisted in MOIN. As another example the first metamodel may be the XML schema and the second metamodel may be the MOIN metamodel .

In step a declarative mapping is provided between the first metamodel and the second metamodel. Declarative means a one to one association of source and target elements without the need for programming. As an example with reference to the mapping may be the mapping component .

In step custom exits are provided. The custom exits provide programmable mapping rules in addition to those of the mapping. As an example with reference to the custom exits may be the custom exits .

In step the mapping and the custom exits are applied to the first metadata to result in the second metadata. As an example with reference to the model import component may apply the mapping and the custom exits to the WSDL information to generate the MOIN metadata .

At the core the mapping from XSD based input elements to MOF based output elements may be done on the M2 level by a list of properties i.e. String typed key value pairs as they are common in Java for storing configurations etc. Input keys may be XML element names as defined in XSD element or type definitions e.g. interface in . Output values may be either MOF ModelElements or names of Java Classes.

The MOF ModelElements may point to the corresponding metamodel element to instantiate e.g. Interface Classifier in . Alternatively a MOF Id may be used to uniquely identify an element. The alternate solution is less prefereable due to maintenance effort without proper tool support due to the bad readability for humans. 

The names of Java Classes may be used where custom exits describe how to proceed with the input element for certain special cases where a simple one to one mapping does not suffice. The application programming interface API and programming model of these custom exits are described below see heading API and Programming Model for Custom Exits .

According to one embodiment developers can define the mapping manually according to a given also hand crafted target metamodel on the MOIN side. According to another embodiment a Default metamodel Import feature similar to Eclipse s EMF XSD import generates the target metamodel and the corresponding mapping definitions. Experiments with EMF have shown that such default import mechanisms yield low quality results especially for more complex XML schemata like WSDL . Consequentially developers may then refine both the imported metamodel as well as the mapping definitions potentially in a synchronized fashion.

As a vehicle for accessing XML elements by name the DOM API part of J2SE as package org.w3c.dom may be used. The relevant subset of DOM for this purpose is outlined in .

The Node is the central superinterface of all relevant DOM constructs. An ordered composition relationship is spanned between parent and child Nodes. This is the primary vehicle to navigate through the DOM tree complemented by the name mapped ownerElement attributes relationship between Elements and Attributes which is interestingly enough not a refinement of the recursive parent child composition. The root of the DOM tree is represented by the Document Node which features exactly one documentElement.

Relevant in the context of MOIN interoperability IMOIN is the capability of finding all Elements within a Document by a given TagName. In the example of this allows the Model Import component to locate all instances of interface in a WSDL document for instantiating corresponding Interfaces on MOIN side for example as part of .

On the MOIN side a MOIN tool interfaces with a MOIN MOF based repository to access the NU metamodel information and the M1 model information .

A metamodel import component interfaces with the filesystem and with the MOIN MOF based repository . The metamodel import component may generate the mapping table . The metamodel import component may interface with the default metamodel mapping to generate the mapping table . The model import component interfaces with the DOM model and with the MOIN MOF based repository . The model import component uses the mapping table and the custom exits to generate the M1 model information . The label Impl in the custom exits component denotes the multitude of implementations of CustomExits that the ModelImport may use in addition to the declarative mapping table. The translation backlog component is described in the section API and Programming Model for Custom Exits below.

The embodiment of elaborates the embodiment of with respect to data and control flow. The data and control flow shows importing a certain XSD based format for instance WSDL files based on an XSD definition of the WSDL format which are to be imported as models of a MOF compliant WSDL model on MOIN side.

The Model Import may be triggered in one of three following ways. The first way is via push when the producing external tool triggers import upon save or rebuild. The second way is via pull when the consuming MOIN tool triggers import upon some event. Third the Developer may explicitly import certain models.

Once triggered the Model Importer uses the XML DOM parser to create an in memory representation of the input document which it then traverses recursively depth first starting at the root node. It reads the Mapping Table to determine a corresponding model element on MOF side for the current DOM node according to its name. If the entry in the Mapping Table refers to a Java class this class is instantiated reflectively and invoked via the Custom Exit API described in the section API and Programming Model for Custom Exits below. A Translation Backlog keeps track of already processed elements as well as elements whose processing has been postponed because required references need to be resolved first. This issue is also described below in the context of the Custom Exit API. The import terminates as soon as the DOM tree is completely traversed.

Regarding the evaluation of entries in the Mapping Table there are two alternative strategies a minimalistic implicit strategy and a verbose explicit strategy.

In the minimalistic implicit strategy if no entry is found for the currently processed input Node the Model Importer implicitly assumes the same containment structure for the output model and tries to instantiate model elements with equal names as the input Nodes. For instance XML Attributes may be mapped to MOF Attributes.

In the verbose explicit strategy if no entry is found for the currently processed input Node the Model importer does nothing and proceeds immediately with to the next sibling Node. This strategy is preferred in one embodiment for the following reason There is often more than one valid mapping. For instance XML Attributes could just as well be modeled in MOF as associated Classes. If the default mapping changes this would not only affect the Metamodel Import but also the Model Import implementations. Hence an explicit mapping for all importable nodes fosters separation of concerns.

The set of relevant metamodels and XSD based formats are rather limited at the moment. However referenced related work may be used and adapted to address this level. In principle the Metamodel Import eases the developer s task of providing the Mapping Table by exporting this as a trace of its applied default mapping from XSD schema elements to MOF model elements. The developer may then adapt those parts of the metamodel and the mapping where the default mapping did not yield the wanted results.

Custom Exits enable both the import and export of XML nodes to and from MOF models. Custom exits are useful in cases where a simple 1 1 mapping of elements does not suffice anymore and complex semantics need to be resolved or instance for mapping IDREF strings from XML to association instances in MOF. Custom Exits perform this in principle by traversing up and down the input object tree while simultaneously constructing the output object tree accordingly.

As mentioned above Custom Exits will often be used to correctly transform references from input to output. It is possible in this context that referenced target is not yet present in the output model at the time the input reference is processed by the Model Importer. Consequentially it must be handled later as soon as its target is transformed. There are three ways to handle this issue as follows.

The first way is to use a double pass Model Importer that picks up and transforms deferred element on the second run. This way may not suffice for more complex scenarios when the second pass yields more deferred elements.

The second way is to immediately transform the required reference target and continue with the depending reference element. Recursion could create quite deep call stacks if the reference target also needs to transform other elements first. Special attention needs to be paid to cycle detection if elements are to be transformed which already appeared further up the stack. Resolving such cycles may deteriorate this solution to a multi pass approach similar to the previous one.

The third way favored according to one embodiment is to enlist deferred transformations in a Translation Backlog such as element in containing transformations waiting for some element to become available on the output side. This represents sort of the opposite solution to the previous approach. If a Custom Exit realizes that some element is missing it registers its context input output as waiting for that element. The Model Importer checks with the Translation Backlog after each transformation if there are other transformations waiting for its result and invokes them accordingly.

In this section are discussed assumptions constraints and limitations of certain of the embodiments detailed above.

A valid solution especially in combination with the verbose explicit mapping strategy recommended above according to one embodiment is the use of simple XPath expressions as keys for uniquely identifying DOM nodes e.g. library name vs. library writers name .

The second set of embodiments provide more details such as being an extension of the first set of embodiments.

One feature is explicitly introducing type information to the simple DOM based in memory representation of XML input files by instances of an XSD based schema model . This may be done indirectly via the Post Schema Validation Infoset PSVI which gives access to the XML Schema API that corresponds to the XSD metamodel. Hence the Mapping Table may reference instances of the MOF based XSD metamodel instead of DOM Node names. This way the Model Import represents a model transformation from XSD based schema model instances to some other metamodel instance.

First there is no concept for technically representing M0 objects as model instances in MOIN. Hence DOM Level 3 API may be used to access the PSVI of DOM Elements. The PSVI in turn exposes the XML Schema API which parallels the XSD metamodel . This way both Model Import and Metamodel Import may use the in memory representation of XML Schema API to instantiate corresponding M1 XSD models in MOIN such as .

Second the Mapping table now maps M1 instances of the XSD metamodel to M2 elements of the target metamodel . Although XPath like String expressions may be used to specify keys this may cause two problems 

A first problem is if no implicit ID attributes are present XSD metamodel instances can only be identified by index numbers which are subject to change depending on storage implementations etc. for instance library.xsd Writer XSDComplexTypeDefinition 1 XSDParticle XSDModelGroup XSDParticle to identify a writer s name in the example of .

A second problem is without proper tool support using MOF Ids instead results in mappings illegible for human users.

As a solution to the above problems an embodiment of the present invention uses a MOF based Mapping Model that relates actual model elements instead of String based java.util.Properties.

Third the crossing of metalevels from M0 to M1 and M1 to M2 respectively is a conceptual challenge. If MTI is to be used for model transformation it may be desirable to shift metalevel up on the input side.

The MOIN MOF based repository stores M2 XSD metamodel and a M1 XSD model as well as the M2 metamodel and the M1 model .

The DOM model component uses the DOM Level 3 API to access the PSVI component . The PSVI component exposes the XML Schema API which parallels the XSD metamodel. This is as discussed above regarding .

The mapping table references instances of a MOF based XSD metamodel instead of DOM Node names. This is as discussed above regarding .

The model import represents a model transformation from XSD based schema model instances such as the XSD model to some other metamodel instance such as the M1 model . This is as discussed above regarding .

In contrast to other persistence formats MOIN uses Globally Unique Ids GUIDs to create references between model elements both in memory and in the persistence. Stable references between externally created elements EMF XSD and MOIN native elements thus may involve a mapping. This can be accomplished in at least to ways. The first way is to explicitly manage the mapping information XPath EGUID . The second way is to define a function to calculate MOF Ids GUID F XPath .

The first way may involve modifications to the external tool in order to re calculate mappings during refactoring i.e. to map Resource URIs to MOIN partition resource identifiers PRIs and XPaths to GUIDs. Semantic keys paths or subsets of key attributes uniquely identifying an element would avoid this caveat. For instance an MQL query may be used to select the requested MOF element.

If the semantic key is also independent from the Resource URI no fixed Resource Partition is necessary. For instance if an element was already imported finding it will also allow the importer to determine its DC and Partition.

To minimize write access to MOIN updates may be triggered by providers e.g. WTP . On the MOIN side querying by semantic keys allows to prevent redundant imports even for redundant Resources. When possible mapped MOIN Partitions may be in the same project as their source. Resources in non MOIN projects may be managed by a MOIN project that either duplicates or references the original Resources.

The user interacts with the system via the Eclipse core user interface UI framework . The iMOIN specific parts include the iMOIN user interface the iMOIN XSD import component the example import component and the example MOIN metamodel component . In various implementations the example metamodels may be replaced by actual metamodels such as WSDL XSD etc. 

The MOIN components include the MOIN in Eclipse framework UI the MOIN runtime component the MOIN IDE facade and the MOIN facility component .

At the lowest layer example can be replaced by the name of any other metamodel. The IMOIN UI can use any Eclipse plug in extending the extension point schemaimport defined by the generic IMOIN import plug in. Every extender plug in may provide a properties list mapping XSD elements to metamodel elements and or custom exits. The accompanying importer specific custom exit implementation may be capable of handling any special mapping that cannot be accommodated by the simple 1 1 mapping declared in the properties.

Computer system may be coupled via bus to a display such as a cathode ray tube CRT or liquid crystal display LCD for displaying information to a computer user. An input device such as a keyboard and or mouse is coupled to bus for communicating information and command selections from the user to processor . The combination of these components allows the user to communicate with the system. In some systems bus may be divided into multiple specialized buses.

Computer system also includes a network interface coupled with bus . Network interface may provide two way data communication between computer system and the local network . The network interface may be a digital subscriber line DSL or a modem to provide data communication connection over a telephone line for example. Another example of the network interface is a local area network LAN card to provide a data communication connection to a compatible LAN. Wireless links is also another example. In any such implementation network interface sends and receives electrical electromagnetic or optical signals that carry digital data streams representing various types of information.

Computer system can send and receive information including messages or other interface actions through the network interface to an Intranet or the Internet . In the Internet example software components or services may reside on multiple different computer systems or servers and across the network. Metadata conversion processors described above may be implemented on one or more servers for example. A server may transmit actions or messages from one component through Internet local network and network interface to a component on computer system . Metadata conversion processing may be implemented on any computer system and receive data metadata model information etc. across a network for example. In one embodiment translation processing may be implemented as a software service by one or more servers for example.

According to one embodiment of the present invention a mapping that was automatically generated can be edited manually and used automatically by an importer function. If the structure still deviates significantly that is the original mapping is of low quality a custom exit allows programming to adapt to specific elements of the M2 metamodel.

According to another embodiment of the present invention a combination of framework technology for adaptation exits and simple flexible mappings allow using a generic importer that can be customized.

One feature of an embodiment of the present invention is to enable migration between modeling tools for example from EMF to MOIN.

Another feature of an embodiment of the present invention is the integration of modeling tools for example between EMF and MOIN. For example tools such as Eclipse tools may be outside of direct control of a business entity such as SAP. An embodiment of the present invention allows MOIN to access EMF metadata.

According to an embodiment of the present invention a customizable XSD based tool uses an XSD schema and mapping information to de serialize an XML file into a custom MOIN model. According to another embodiment of the present invention a customizable XSD based tool uses an XSD schema and mapping information to serialize an XML file from a custom MOIN model.

According to an embodiment of the present invention in order to be able to interoperate with different metadata repository technologies interoperability support is integrated at the persistence format level providing a framework that implements the repeatable import export connection strategy using a customizable XSD based model conversion for integrating external metadata persisted in an XML based format into MOIN. Given an external XML format for example an XSD schema a Model Import component creates MOIN models based on the conceptual metamodel implied by the XSD.

The above description illustrates various embodiments of the present invention along with examples of how aspects of the present invention may be implemented. The above examples and embodiments should not be deemed to be the only embodiments and are presented to illustrate the flexibility and advantages of the present invention as defined by the following claims. Based on the above disclosure and the following claims other arrangements embodiments implementations and equivalents will be evident to those skilled in the art and may be employed without departing from the spirit and scope of the invention as defined by the claims.

