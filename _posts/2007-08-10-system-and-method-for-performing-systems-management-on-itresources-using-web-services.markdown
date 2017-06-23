---

title: System and method for performing systems management on IT-resources using web services
abstract: The present invention relates to the field of systems management on IT-resources using web services. An improved method proposes a single web service implementation which dynamically and automatically generates multiple WSDLs for respective multiple resource type classes. This implementation is model-agnostic, as it doesn't require any knowledge about the underlying model, be that a resource model, or any other model in question, and uses introspection of the applied model at the time of invocation for the dynamic WSDL generation. The state of the resource is maintained within the instrumentation of the resource. No additional persistence on top needs to be implemented. A single implementation of a low number of generic web services, basically only two, reduces implementation and maintenance efforts significantly.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08082548&OS=08082548&RS=08082548
owner: International Business Machines Corporation
number: 08082548
owner_city: Armonk
owner_country: US
publication_date: 20070810
---
The present invention relates to the field of systems management. In particular it relates to a method and system for performing systems management on IT resources using web services wherein the resources are managed in a computational network within a plurality of runtime environments having different respective instrumentations and the web services are implemented according to a public web service standard and a resource configuration database is provided for storing a collection of resource specific data on such IT resources.

Web services WS standards such as WSDM Web Services Distributed Management and web service management and future converged standards describe how IT resources operating systems printers applications etc. expose their manageability capabilities using web services to client applications. These client applications typically are systems management applications provided by IBM by Internet Service Providers or other vendors. Prior art web services describe their interfaces in XML documents following the WSDL Web Service Definition Language standard. They are accompanied by implementations of the respective web services typically being deployed and executed on application servers.

With reference to representing a prior art system overview when applying prior art systems management by web services prior art system management applications target for a deployment of well defined strongly typed web services in order to be enabled to support all classes and types of resources and their relationships. Prior art clients server systems management implementations require a set of WSDL definitions to be available to use a service and access the resource using web services.

As shown in a client application implementing system management functions has to maintain a plurality 2 of WSDL documents one for each resource type provided by the service implementations. On the server side inside the broken line box the web service implementation needs to have the exact same WSDL documents as well as the service implementations based on these specific WSDL documents .

The objective of at least one embodiment of the present invention is to provide an improved method and system for web service based systems management tasks. This objective is achieved by the features stated in enclosed independent claims. Further advantageous arrangements and embodiments of the invention are set forth in the respective dependent claims.

The present invention proposes a method for performing systems management on IT resources using web services. In particular a single web service implementation is proposed which dynamically and automatically generates multiple WSDLs for respective multiple resource type classes. This implementation is model agnostic as it doesn t require any knowledge about the underlying model be that a resource model or any other model in question and uses introspection of the applied model at the time of invocation for the dynamic WSDL generation.

For example the method uses functionality in application programming interfaces APIs of instrumentations of resources e.g. a Computer Information Model CIM or functionality of APIs in case of data representations in case of the presence of configuration databases. The method may provide services that can be used unchanged in a number of different runtime environments model agnostic . The implementation of a service provided by the method is still conforming to industry standards for example adhering to the WS ResourceFramework specification.

The web service standard WSDM includes which specifications must be used to implement WSDM interfaces. The Service Group specification describes the enumeration of entries in a collection while resource property documents RPD are XML documents that describe stateful resources.

The basic methods of the present invention as sketched in box of discloses to create Service Group entries and RPDs from data stored in a configuration database such as IBM s configuration database CMDB in a very efficient manner. Further it enables for an enumeration of resource types.

The method can be applied to other domains such as CIM SNMP JMX etc. In more detail the before mentioned entries in Service Groups and RPDs are created during request time dynamically. Each time an access to the Service Group that for example enumerates the classes or types of resources in the CMDB is requested by a WSDM client the entries in the Service Group are dynamically created. The same is done for the RPD that actually describes the stateful resource. The RPD is not defined a priori as it is the case in prior art. Instead it is preferably generated at request time and passed back to the requestor. It is created from the data stored in the database CMDB for a particular class or particular type and is never persisted at any memory or storage used by the method.

So advantageously no maintenance work is necessary in order to reflect state information and to track state information other than at the resource registry or configuration database itself.

According to a preferred embodiment a method for performing systems management on IT resources using web services is disclosed wherein the resources are managed in a computational network within a plurality of runtime environments having different respective instrumentations wherein the web services are implemented according to a public web service standard e.g. WSDM wherein a resource configuration database is provided for storing a collection of resource specific data on said IT resources and wherein the method is characterized by the steps of 

From this preferred method the advantage results that descriptive information on all resource instances is obtained at runtime without the necessity of programming a special web service which is specific for the different instances of a specific resource type. In presence of hundreds or thousands of different resource types and resource type specific instances the steps can be cast into two basic generic web services which can be used instead of respective hundreds or thousands of web services as required in prior art. This descriptive information can be used for basic tasks of systems management. It can also be used for accessing a resource independently of the plurality of different prevailing sub standards.

In other words the basic procedure proposed by the present invention includes to collect resource related data by applying prior art discovery means to store the data into a suited database registries or inventories and to open these registries and data storages make the before mentioned enumerations of types and or classes of resources in order to be accessed by a generic web service provided by the invention which is used in order to support systems management functionality.

By means of this basic procedure systems management can obtain an overview over all resource types and resource instances which are present in the respective management environment also in the usual cases where different instrumentations of the resources are present. This is advantageously achieved by a small number of web services instead of a large number of web services as known from prior art.

The method can be applied for a basically unlimited number of resources including multiple different versioning of resources and including multiple different versioning of communication protocols in use for communicating with the resources or with the resource configuration databases.

Advantageously changes related to resource types or to relationships between particular resources are automatically included into the method without that any change is necessary to a web service provided by the invention. This is due to the fact that no additional persistent data storage is required for the method as it is applied just during runtime of the resource. So any state information is freshly retrieved form a resource configuration database or from a resource itself respectively and is sent via the web service to a respective administration staff member.

Another preferred embodiment of the invention comprises the stateless implementation of a web services access layer usable when a resource shall be accessed for monitoring purposes by this access specifically the capability of sending commands to the resource is of high interest as well as the retrieval of high frequently changing data for monitoring purposes.

The state of the resource is maintained within the instrumentation of the resource. No additional persistence on top is implemented according to the invention. In other words state information of said resource is generated during runtime of a request to access said resource. The stateful behavior as required by the WSDM and WS Man standards is fully available for clients despite its stateless implementation. This enables advantageously to scale in large environments and provides high availability as the clients are not bound to a single resource instance.

It should be noted that a key capability of the invention is that the method does not perform a generic abstraction of multiple underlying interfaces to one generic interface. Instead the provided web services open up a dialogue at runtime between the client occupied with systems management tasks and the resources or a resource configuration database during which dialogue multiple stages are run in a first stage a list of resource types is requested. In the second stage properties operations relationships etc of resource instances are requested. In a third optional stage driven by use cases in which an actual access to a resource is desired a Meta data description of a resource instance is requested and delivered to the client. And in a last stage instance data are requested which are required to access a particular resource.

It can be used to simulate the stateful behavior requested by WSDM WS Man standards using a stateless implementation.

It can be used to generate events or to create topology graphs or to navigate relationships between resources.

A single implementation of a low number of web services basically only two reduces implementation and maintenance efforts significantly.

Service implementers do not need to maintain WSDL libraries. Changes in the underlying models are automatically made available to clients. These changes fall basically in the category of additional or modified attributes properties operations and or modified or additional resource types. This is a significant feature because prior art needs to re deploy the changes including restart of the runtime application server.

A realistic number of resources can be processed including complex ones. The prior art implementations lack the ability to scale in real life scenarios. This is because of their stateful implementation using elements of implementations of the WS RF stack. The method just requires the WS Addressing stack as a software based prerequisite as it simulates the stateful behavior but is in turn stateless.

A WSDL provided by the invention always reflects the real world at runtime which eliminates runtime errors while prior art can have inconsistent artifacts due to it is a priori definition.

The method yields less run time resource consumption on the client and on server side due to less web service implementations.

For example WSDM on top of CIM instrumented resources is different from WSDM wrappering the data representations in the configuration management database because additional capabilities can be offered to WSDM clients due to the method.

The present invention discloses to create dynamically during request time entries in Service Groups preferably in the complete Service Group and in the RPD documents. Each time an access to the Service Group that e.g. enumerates the Classes Types in the CMDB is requested by a WSDM client the entries in the Service Group are dynamically created.

The same is done for the resource property documents RPD that actually describes the stateful resource. According to this feature the RPD is not defined a priori it is rather generated at request time and passed back to the requester. The RPD is created from the data stored in the CMDB for a particular class type and is never persisted. Thus non persistent entries of Service Groups or other enumeration implementations behave as if it would have entries persisted but they advantageously need no maintenance for holding the entries up to date.

According to a preferred aspect of the invention when using the query language of the configuration database also in Service Group specifications the query language of the source CMBD MQL CIM CQL etc is in terms of queries transparently mapped to the Service Group specification requirements.

Thus advantageously the scalability and performance of the underlying query implementations is supported with minimal overhead.

It is to be noted however that the appended drawings illustrate only example embodiments of the invention and are therefore not considered limiting of its scope for the invention may admit to other equally effective embodiments.

With general reference to the figures and with special reference now to the main components of the present invention are WSDM enabled instrumented resources a configuration database used as a registry that has WSDM interfaces a message infrastructure enabled by a notification broker to support handlings of events and a systems management application exploiting WSDM.

Step Time based discovery gathers information about network attached IT resources and stores it in a configuration database for example in a TADDM Tivoli Application Distributed Discovery Manager TADDM Configuration Management Database CMDB . Typically the discovery processes are long running scheduled activities that require a lot of compute resources. According to the invention this needs to be done only once for resources with WSDM enablement and WSDM discovery. In prior art this must be done repeatedly.

Step Multiple discovery runs performed by prior art systems management application require a correlation component ensuring that new data is inserted or already existing data is updated.

Step Systems management applications query Meta data Web Services Description Language WSDL RMD RPD enumerate CMDB classes enumerate instances of a particular class and follow the relationships of the respective entities. They access entries in database as WSDM manageable resources. They can subscribe to events issued by the database to the Notification Broker . To do this using WSDM is enabled by using a small set of generic web services referred to in here as WSDM common services WSDM CS . Prior art offers no generic web services.

Step Resources with applied instrumentation capabilities such as Computer Information Model CIM Simple Network Management Protocol SNMP or Java Management Extension JMX are WSDM enabled and thus usable for web service based system management by using a set of web services called WSDM CS for instrumented Resources. Details how these services work using a generalized proxy pattern are given further below. These resources emit life cycle events such as resource created or resource destroyed to the notification broker . This provides for the ability for short running real time discovery as well as other capabilities such as providing data to subscribers that are not stored in the configuration database . Typically this would be monitoring dynamic data like CPU load number and type of active operating system processes and the like.

Step When it is assumed that such an IT Resource advertises it s presence in the network through a life cycle event the correlation component needs to check if the data representation of the resource is already in the database because it is found earlier by for example time based discovery runs. Thus the correlation component is required in order to correlate existing entries with newly discovered ones. Further the correlation task is extended in order to cope with 

If an entry is not yet present an entry is created in the database . In both cases a relationship is established in the database that links the data entry with the Instrumented Resource. This enables clients to query the data representation and get access to the associated instrumented resources as well.

The complexity of the correlation functionality varies with the underlying models of the instrumented resources and the representation in the database . The straightforward case is if both have the same underlying model. In case they differ policies need to be defined to allow identifying if the data representation in the database is the one representing the instrumented resource.

Step Then it is possible to actually do systems management with the instrumented resource for example by issuing a command to the resource.

Included in a bottom layer typical elements used in prior art of systems management are shown. Inventories also known as registries are realized by systems management products itself e.g. IBM Director TPM or they use configuration databases such as TADDM CMDB and instrumentation technologies such as CIM SNMP JMX. These instrumentation sources or repositories keep all information of IT resources like configuration parameters and state.

Block depicts general functionality thereof the usage of a core pattern that is used to implement generic web services as described further above. The web services according to the invention use the stateless implementation of stateful interfaces of web services according to WS standards as well as an inherent model agnostic behavior.

In order to access an IT resource two additional web services depicted in box are provided according to the invention 

One additional web service is used to retrieve meta data from the available services and the available resource types. In the case of using web service standards for management this meta data is the WSDL and the RMD.

The second additional web service is a web service implementation which in turn plays the role of each web service which is virtualizing the resource using web services. In WSDM terminology this is the WSDM manageable resource.

As opposed to the prior art it is clear to a person skilled in the art that from a client perspective a significant simplification is achieved over prior art by the method as only one WSDL is required to deal with all resource types. Remark that in prior art this was a number about 1000.

On the web service implementation side the architecture is simplified also. A single service provides responses to client requests with dynamically generated payload.

With reference to more details are given outlining how a WSDM client is provided with meta data for a particular resource type using the inventional generic implementation of a meta data service. The boxes correspond to that of . In this case the meta data service plays the role of a meta data service for that particular type and retrieves the appropriate information from the configuration database . According the WSDM standard specification the WSDL and the RMD are returned to the WSDM client .

Remark that in prior art a resource property is requested on a resource ID. Then the type of the resource is looked up locally to pick the correct WSDL interface definition. Then a web service is called to request the respective resource property document. According to the invention the resource property is requested on a resource ID. Then the generic web service is called with the resource ID to get a dynamically generated WSDL. Then a web service is called to request the resource property document.

Properties and operations of WSDM Manageable Resources are then accessed or executed using the retrieved meta data and the second web service labeled Resource Instance Access Service .

In more detail according to this embodiment a first request is sent from client to the meta data service .

This is a request requesting for the WSDL or the RMD of a certain resource type or Service Group. This request is serviced by the metadata service producing a response comprising an automatically generated WSDL document or and an automatically generated resource metadata document RMD .

The component provides the generic capabilities described above with reference to to the services and .

Then in a next request client requests the properties or operations and other system attributes for a certain instance of one type of resources specified in request answer . Then the resource instance access service fulfills the request using the component and gets the meta data of the requested type by querying the configuration database of layer . With the enriched request information a new request is issued to the configuration database of layer and the Instance data is returned .

In a concrete use case according to the client application may be assumed to access a property of a specific Operating System OS namely the Vendor Name thereof. It queries two registries with WSDM compliant requests QueryResourceProperty step to finally get the EndPointReference ERP of the Operating System instance step which is then accessed using the WS common service with a WSDM compliant GetResourceProperty request.

This example is detailed in the and where the prior art access pattern is shown in for the purpose of improved clarity ready to be compared with preferred embodiments of the method depicted in 

In prior art queries the Service Group to get all resource types see step . After having received them step the client requests all Operating System OS instances from the Service Group implementation for Operating Systems see step . After having received them step with one of the OS instances the OS service is accessed see step to retrieve the property vendor name see step . Remark that disadvantageously for all types that the prior art system supports it needs respective web service implementations see all boxes in the upper part of the right column. In the resource type Computer System CS is shown as a second type see bottom part of right box column.

Next and with reference back to some details of a preferred implementation of the preferred embodiment are given in relation to WSDM CS and instrumented Resources.

The prior art WSDM Common Services CS components can be advantageously used for inventories and or registries that maintain copies of data of real IT resources as well as for IT resources with instrumentations such as the before mentioned CIM SNMP or JMX.

In order to use the WSDM CS components in a systems management environment using web services this is very important because registries inventories only store data of IT resources that are either immutable e.g. the MAC address or very infrequently changed after they have been discovered e.g. the hostname the IP Address or the Vendor Name . It should be noted that in prior art systems management frequently changing data for purposes of monitoring such as CPU load or even operations commands are not available from inventories or registries.

In details are illustrated disclosing how WSDM CS is applied to instrumented resources in general a specific implementation is selected for CIM 

Usually these capabilities are provided by an application programming interface API or by a command line interface.

In an example for a concrete implementation of the scheme in is given. The web services components are never changed. For the WBEM CIM support the plug in is implemented using the generic bridge and the appropriate JSR client. The later communicates with the CIMOM of the OpenPegasus implementation available with the Linux operating system SLES see reference . The component provides the persistence capability of CIM where a CIM Provider deals with the actual resources .

The invention can take the form of an entirely hardware embodiment an entirely software embodiment or an embodiment containing both hardware and software elements. In a preferred embodiment the invention is implemented in software which includes but is not limited to firmware resident software microcode etc.

Furthermore the invention can take the form of a computer program product accessible from a computer usable or computer readable medium providing program code for use by or in connection with a computer or any instruction execution system. For the purposes of this description a computer usable or computer readable medium can be any apparatus that can contain store communicate propagate or transport the program for use by or in connection with the instruction execution system apparatus or device.

The medium can be an electronic magnetic optical electromagnetic infrared or semiconductor system or apparatus or device or a propagation medium. Examples of a computer readable medium include a semiconductor or solid state memory magnetic tape a removable computer diskette a random access memory RAM a read only memory ROM a rigid magnetic disk and an optical disk. Current examples of optical disks include compact disk read only memory CD ROM compact disk read write CD R W and DVD.

A data processing system suitable for storing and or executing program code will include at least one processor coupled directly or indirectly to memory elements through a system bus. The memory elements can include local memory employed during actual execution of the program code bulk storage and cache memories which provide temporary storage of at least some program code in order to reduce the number of times code must be retrieved from bulk storage during execution.

Input output or I O devices including but not limited to keyboards displays pointing devices etc. can be coupled to the system either directly or through intervening I O controllers.

Network adapters may also be coupled to the system to enable the data processing system to become coupled to other data processing systems or remote printers or storage devices through intervening private or public networks. Modems cable modem and Ethernet cards are just a few of the currently available types of network adapters.

