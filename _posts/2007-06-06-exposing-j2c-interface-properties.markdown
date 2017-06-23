---

title: Exposing J2C interface properties
abstract: The invention relates to Web Services Invocation Framework (WSIF) operations. “interactionSpec” and “connectionSpec” are Java 2 Enterprise Edition Java Connector Architecture interfaces. Their properties are exposed as data in WSIF operations. Thus WSIF support for the Java 2 Enterprise Edition Java Connector Architecture is made functionally more complete.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=07966619&OS=07966619&RS=07966619
owner: International Business Machines Corporation
number: 07966619
owner_city: Armonk
owner_country: US
publication_date: 20070606
---
The present application is a continuation application of U.S. patent application Ser. No. 10 696 063 entitled Exposing J2C Interface Properties filed on Oct. 29 2003 now U.S. Pat. No. 7 290 265.

A portion of the disclosure of this patent document contains material which is subject to copyright protection. The copyright owner has no objection to the facsimile reproduction by any one of the patent document or the patent disclosure as it appears in the Patent and Trademark Office patent file or records but otherwise reserves all copyright whatsoever.

The present invention relates to Web Services Invocation Framework WSIF operations and in particular to exposing J2C interface properties in such operations.

Historically Enterprise Information integration Systems EIS such as legacy mainframe systems and more recently commercial applications have been at the center of modern information technology environments providing critical data for enterprise operations. Companies have big investments in their Enterprise Information Systems. While many applications may be old some may be new. The EIS provides the company with the quality of service required by the company. An example application known as a transactional application allows updates to be made to a bank account. Although these systems continue to be critically important to many businesses these businesses may further rely on other applications. As these other applications are often web or wireless applications there appears to be an increasing need to integrate web and wireless applications with legacy mainframe systems and existing commercial applications. Such integration requires the real time exchange of information and services by a range of interested parties. The new applications for which this integration is required are increasingly being developed in the Java programming language.

As a required element of the Java 2 Enterprise Edition J2EE the Java ConnectorArchitecture J2C provides a standardized means to integrate Java applications with EISs Java is a Trademark of Sun Microsystems Inc. J2C defines a Common Client Interface CCI . The CCI defines a standard client Application Programming Interface API for application components. The CCI enables application components and Enterprise Application Integration EAI frameworks to drive interactions across heterogeneous EISs using a common client API. Interfaces that are part of the CCI include interactionSpec and connectionSpec these interfaces are further described hereinafter.

As mentioned hereinbefore companies may have business requirements to enable web access to these services. To extend the previous example of a banking application there may be a requirement to enable access to bank accounts over the Internet. The J2EE Connector architecture J2C provides an environment so that an EIS can provide a resource adapter that can plug in to any application server so that the application server can generically provide qualities of service to all resource adapters and optionally through the CCI the resource adapter can implement the common client programming model for the enterprise application. Such J2C services may further be extended to be web services.

Integration of Java applications with EIS may be accomplished through the use of J2C. The Web Services Description Language WSDL with its extensions allows the description of many different kinds of services Web services Java services Enterprise Java Bean EJB services Java Message Service JMS services J2C services etc. The Web Services Invocation Framework provides a common way of invoking each of these services. The WSIF supports a simple Java API for invoking Web services. Use of the WSIF API allows clients to invoke services focusing on an abstract service description that is the portion of WSDL that covers port types operations and message exchanges without referring to real protocols.

As mentioned hereinbefore WSDL is extensible to allow the description of many types of services other than web services. With WSIF any of these types of services may be invoked in a common fashion. However WSIF does not expose certain J2C properties thus constraining certain applications.

interactionSpec and connectionSpec properties are exposed as data in WSIF operations thus WSIF support for J2C is made functionally more complete. Advantageously exposing J2C interactionSpec and connectionSpec properties as data in a WSIF operation allows the connectionSpec and interactionSpec properties to be set dynamically on input and the interactionSpec properties to be retrieved dynamically on output.

In accordance with an aspect of the present invention there is provided a method of improving Web Services Invocation Framework support for Java 2 Enterprise Edition Java Connector Architecture comprising exposing properties of a given interface as data.

In accordance with another aspect of the present invention there is provided a method of a performing Web Services Invocation Framework operation. The method includes receiving an input message that includes a plurality of parts determining whether any of the plurality of parts are instances of a property of a given interface and if a given part of the plurality of parts is determined to be an instance of the property of the given interface setting a value from the given part into the given interface thereby exposing a property of the given interface as data. In other aspects of the present invention a resource adapter is provided in an application sever the resource adapter for performing this method and a computer readable medium is provided to allow a general purpose computer to perform this method.

Other aspects and features of the present invention will become apparent to those of ordinary skill in the art upon review of the following description of specific embodiments of the invention in conjunction with the accompanying figures.

As mentioned hereinbefore J2C provides an environment so that the EIS can provide a resource adapter that can plug in to the application server so that the application server can generically provide the qualities of services available from the resource adapter illustrated and other EIS specific resource adapters not shown .

The resource adapter may be loaded with methods exemplary of this invention from a software medium which could be a disk a tape a chip or a random access memory containing a file downloaded from a remote source.

Much of the following description of interactionSpec and connectionSpec and respective properties is drawn from the Java 2 Platform Enterprise Edition v 1.3 API Specification hereby incorporated herein by reference .

The interactionSpec property holds properties for driving an interaction with an EIS instance. The CCI specification defines a set of standard properties for an interactionSpec. An interactionSpec implementation is not required to support a standard property if that property does not apply to its underlying EIS. The interactionSpec implementation class must provide getter and setter methods for each of its supported properties. The getter and setter methods convention should be based on the Java Beans design pattern. The standard properties are as follows 

ExecutionTimeout the number of milliseconds an Interaction will wait for an EIS to execute the specified function

The last five standard properties are used to give hints to an Interaction instance about the ResultSet requirements.

A CCI implementation can provide additional properties beyond that described in the interactionSpec interface. Note that the format and type of the additional properties is specific to an EIS and is outside the scope of the CCI specification.

ConnectionSpec is used by an application component to pass connection request specific properties to an interface for getting connection to an EIS instance. The CCI specification defines a set of standard properties for a ConnectionSpec. The properties are defined either on a derived interface or an implementation class of an empty ConnectionSpec interface. In addition a resource adapter may define additional properties specific to its underlying EIS. A resource adapter is a system level software driver that is used by a Java application to connect to an EIS. The resource adapter plugs into an application server and provides connectivity between the EIS the application server and the enterprise application. In simpler terms a resource adapter is the software that allows an application to access functions in an EIS.

Among others the following standard properties are defined by the CCI specification for ConnectionSpec 

Password password for the user establishing a connection interactionSpec and ConnectionSpec Properties generally need to be exposed to allow an application to set the values of the properties at execution time. Otherwise the values of the properties would have to be set when the application is built.

Often the interactionSpec values may be preset. However some scenarios require the ability to set a value or to obtain a value on output. For example in component managed signon there is a requirement of the ability to set the user name and password on the connectionSpec on input. In contrast for container managed signon a connectionSpec is not used.

ConnectionSpec properties are part of the port section of the WSDL. ConnectionSpec exposes any security information and connection parameters that are specific to the resource adapter. In the component managed signon case an application component passes security information example username password through a ConnectionSpec instance. interactionSpec properties are part of the binding section of the WSDL.

It is known that J2C has a managed and a non managed scenario. In the non managed scenario the connectionSpec and interactionSpec properties are taken from an associated WSDL file. An interactionSpec object can also be exposed as a property on a proxy that is used to execute an EIS interaction.

In the managed scenario some connectionSpec properties UserName and Password are exposed as an administered Java Authentication and Authorization Service JAAS Subject or as custom properties on an interface for getting connection to an EIS instance. interactionSpec properties are not exposed in the managed scenario.

Exposing connectionSpec properties is important for enabling component managed signon. Exposing interactionSpec properties is important because some EIS interactionSpec properties are important for the application to set or retrieve at runtime. Unfortunately when working with WSIF J2C operations the interactionSpec properties are part of the binding and are not exposed. A binding is a WSDL concept. A binding defines the concrete implementation of an abstract operation. The binding specifies the message format and protocol details of the abstract operation. In the context of a WSIF J2C operation the binding is communicated to the resource adapter in one or more messages.

To implement the exposure of the interactionSpec properties and the connectionSpec properties as data the method typically implemented by the resource adapter is altered as illustrated in .

An input message is received by the resource adapter from the application server causing the resource adapter to perform the steps of the method illustrated in . The updateInteractionSpec method provided by the EIS is initially called step to update the interactionSpec using data from the input message. The method called updateInteractionSpec determines whether any of the parts in the input message are instances of the interactionSpecProperty. If a part is determined to be such an instance updateInteractionSpec takes the value from the part and sets the value into the interactionSpec. It is then determined whether a connection is currently available step . Where a connection is not available the connection is considered to be null . If a connection is not currently available it is determined whether any of the parts in the input message are instances of the connectionSpecProperty step . If so while creating a connection to the EIS step values from each of such parts are set into the connectionSpec which is then used when creating the connection. If no parts are instances of the connectionSpecProperty a connection to the EIS is created with no connectionSpec specified step . In each of steps and the connection to the EIS is created by calling a createConnection method. If a connection is determined step to be currently available or once a connection has been created step or an interaction i.e. a javax.resource.cci.Interaction is created from the connection step . An interaction execute method is then invoked step with the EIS . The interaction is then closed step . If the interaction execute method is an input only method the method is complete. However where the interaction execute method is a request response operation determined in step the interactionSpec is set into an output message step and the output message is updated step with specified interactionSpec properties.

Note that in the port type section of the WSDL the developer adds a part to the input message for each interactionSpec or connectionSpec property that is to be exposed as data. Parts are also added to the output message for each interactionSpec property that is to be exposed as data. In the binding section of the WSDL for the input and output sections of the operation the developer then specifies how these added parts map to connectionSpec or interactionSpec properties. This mapping is then used at runtime.

As will be apparent to a person skilled in the art the portion of the method illustrated in that is typically implemented by the resource adapter is represented by step step and step .

The method called updateInteractionSpec that is used in WSIFOperation JCA.java see and called at step of is provided as part of exemplary code illustrated in called WSIFProvider ECI.java in particular see . The ECI acronym relates to the External Call Interface of the resource adapter . The method called updateinteractionSpec determines whether any of the parts in the input message are instances of the interactionSpecProperty. If a part is determined to be such an instance updateInteractionSpec takes the value from the part and sets the value into the interactionSpec. The method called updateInteractionSpec calls ECIInteractionSpecProperty which is illustrated in .

The method called createConnection that is used in WSIFOperation JCA.java see and called at step of is also provided as part of WSIFProvider ECI.java see . The method called createConnection determines whether any of the parts in the input message are instances of the connectionSpecProperty. If a part is determined to be such an instance createConnection takes the value from the part sets the value into the connectionSpec and uses the connectionSpec when creating the connection. If no parts are instances of the connectionSpecProperty a connection is created with no connectionSpec specified. The method called createConnection calls ECIConnectionSpecProperty which is illustrated in .

Additionally a method called updateOutputMessage that is used in WSIFOperation JCA.java see and called at step of is provided as part of WSIFProvider ECI.java see .

A known interface called WSIFProviderJCAExtensions has been updated as shown in . to include the updateInteractionSpec updateOutputMessage and createConnection methods.

WSIFMessage JCAStreamable which is illustrated in keeps the input interactionSpec and connectionSpec properties which were provided as parts in the input message from being sent as data to the EIS . WSIFMessage JCAStreamable also populates the parts of the output message as appropriate from the interactionSpec.

WSIFBindingOperation JCAProperty which is illustrated in is an interface of the methods used to get set part Name and either connectionSpec property name or interactionSpec property name.

Consider the use of an embodiment of the present invention in the following example. A message called getCustomerRequest is defined in Customer.wsdl see in particular . The message definition includes identification of particular parts including userid password and functionName . An operation called getCustomer is also defined in Customer.wsdl. The getcustomer message receives the specific getCustomerRequest message as input and issues a getCustomerResponse message as output.

The getcustomer operation is further defined in CustomerCICSECIBinding.wsdl see . By this further definition the user name part and the password part are each defined as a ConnectionSpecProperty and the functionName part is defined as an InteractionSpecProperty. Thus the user name part and the password part may be exposed on the ConnectionSpec as data and the functionName part may be exposed on the interactionSpec as data.

The definitions of exemplary definition files Customer.wsdl and CustomerCICSECIBinding.wsdl are imported into the exemplary definition file called CustomerCICSECIService.wsdl . The acronym CICS refers to the Customer Information Control System which is a family of application servers and connectors that provides online transaction management and connectivity for applications.

Exemplary program code CustomerProxy.java is illustrated in . Notably CustomerProxy.java references the exemplary definition file called CustomerCICSECIService.wsdl see and by doing so thus references exemplary definition files Customer.wsdl and CustomerCICSECIBinding.wsdl. The reference to these exemplary definition files allows the exemplary program code to make reference to the getCustomer operation and the getCustomerRequest and getCustomerResponse messages see .

As will be apparent to a person skilled in the art exposing interactionSpec and ConnectionSpec properties as data allows the size of the commarea of a CICS external call interface to be specified providing a performance enhancement where a commarea is a communications area which defines the input and output for a program . Additionally the exposing allows a user name and a password to be passed by a resource adapter when establishing a connection thus supporting component managed signon.

Other modifications will be apparent to those skilled in the art and therefore the invention is defined in the claims.

