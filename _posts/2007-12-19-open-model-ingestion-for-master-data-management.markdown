---

title: Open model ingestion for master data management
abstract: A method, apparatus, and article of manufacture provide the ability to import a first data model into a meta-data representation in one or more computers. An import wizard or graphical user interface is invoked and guides a user through a process of importing the first data model into the meta-data representation. A source is selected that specifies database connectivity information of a source database containing the first data model. A schema is selected from the selected source, from which tables will be imported into the meta-data representation. A list of all table names within the selected schema is retrieved and displayed. Tables are selected from the list of all table names to import into the meta-data representation. Table information, for all of the selected tables, is populated into the meta-data representation.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08010905&OS=08010905&RS=08010905
owner: Teradata US, Inc.
number: 08010905
owner_city: Dayton
owner_country: US
publication_date: 20071219
---
This invention relates in general to managing business critical data in a computer and in particular to importing a data model from any source and expressing the data model in a standard format.

Master Data Management available from the assignee of the present invention is an application that allows users to manage their business critical data. This critical data can originate from a myriad of sources and external feeds but ultimately the goal is that all of this data be consolidated into a central business data warehouse. Master Data Management is the process and framework for maintaining a series of business rules and process workflows that will manage this data as it feeds in from multiple sources. Master Data Management then applies these business rules and process workflows to produce master data which is then fed to all consuming business processes.

Core to the management of master data is the definition of a data model. The data model serves as the foundation for all business rules and workflow processes within the Master Data Management framework. The data model represents the form the master data must ultimately take in the customer s data warehouse to be used by the consuming business applications.

Today many customers have existing data models. These may be represented created through a data modeling tool such as ERWIN or EMBARCADERO . These models may exist as a physical database on a Relational Database Management System RDBMS . Or these models may exist in some other undetermined format. Further such a model may represent significant investment on the part of the customer and the model needs to be recreated within the Master Data Management framework. Often times these data models contain several hundred tables thousands of attributes or columns and a large number of primary key foreign key index constraint and other table linkage information.

Prior to this invention users would have to manually recreate their data model in the Master Data Management framework this is necessary so that business rules and workflow processes will understand the data. This process can take several weeks or months to define manually.

Accordingly what is needed is a method apparatus and article of manufacture that allows a user to easily and efficiently import data from a variety of data models into a standard format.

Open model ingestion provides the ability to ingest a pre existing data model into master data on a Master Data Management framework from any existing model source e.g. a Relational Database Management System an ERWIN data model created using an ERWIN data modeling tool XML files etc. . This represents a significant optimization to the process of implementing Master Data Management at a customer site.

In the following description of the preferred embodiment reference is made to the accompanying drawings which form a part hereof and in which is shown by way of illustration a specific embodiment in which the invention may be practiced. It is to be understood that other embodiments may be utilized and structural changes may be made without departing from the scope of the present invention.

Master data sometimes referred to as reference data are facts that define a business entity facts that may be used to model one or more definitions or view of an entity. Entity definitions based on master data provide business consistency and data integrity when multiple systems across an organization or beyond identify the same entity differently e.g. in differing data models .

Business entities modeled via master data are usually customer product or finance. However master data can define any entity like employee supplier location asset claim policy patient citizen chart of accounts etc.

A system of record is often created or selected also referred to as a trusted source as a central authenticated master copy from which entity definitions and physical data are propagated among all systems integrated via a Master Data Management framework .

The system of record can take many forms. Many users build a central database e.g. a data warehouse or operational data store as a hub through which master data metadata and physical data are synchronized. Some hubs are simply master files or tables that collect and collate records.

Regardless of the technology approach the goal of the system of record is to provide a central mechanism for collecting and sharing consistent definitions usually across otherwise unrelated systems. The improved Master Data Management framework of the invention provides a practice of defining and maintaining consistent definitions of business entities and sharing such definitions across multiple systems.

In the preferred embodiment the RDBMS includes at least one parsing engine PE and one or more access module processors AMPs A E storing the relational database in one or more data storage devices A E. The parsing engine and access module processors may be implemented in separate machines or may be implemented as separate or related processes in a single machine. The RDBMS used in the preferred embodiment comprises the Teradata RDBMS sold by Teradata US Inc the assignee of the present invention although other DBMS s could be used.

Generally clients include a graphical user interface GUI for operators or users of the system wherein requests are transmitted to the interface to access data stored in the RDBMS and responses are received therefrom. In response to the requests the interface performs the functions described below including formulating queries for the RDBMS and processing data retrieved from the RDBMS . Moreover the results from the functions performed by the interface may be provided directly to clients or may be provided to the RDBMS for storing into the relational database. Once stored in the relational database the results from the functions performed by the interface may be retrieved more expeditiously from the RDBMS via the interface . Further each client may have other data models .

Note that clients interface and RDBMS may be implemented in separate machines or may be implemented as separate or related processes in a single machine. Moreover in the preferred embodiment the system may use any number of different parallelism mechanisms to take advantage of the parallelism offered by the multiple tier architecture the client server structure of the client interface and RDBMS and the multiple access module processors of the RDBMS . Further data within the relational database may be partitioned across multiple data storage devices to provide additional parallelism.

Generally the clients interface RDBMS parsing engine and or access module processors A E comprise logic and or data tangibly embodied in and or accessible from a device media carrier or signal such as RAM ROM one or more of the data storage devices A E and or a remote system or device communicating with the computer system via one or more data communications devices.

However those skilled in the art will recognize that the exemplary environment illustrated in is not intended to limit the present invention. Indeed those skilled in the art will recognize that other alternative environments may be used without departing from the scope of the present invention. In addition it should be understood that the present invention may also apply to components other than those disclosed herein.

As described above the data model represents the form the data must take in a customer s data warehouse to be used by a particular client e.g. a consuming business application . However data models may contain several hundred tables thousands of attributes or columns and a large number of primary key foreign key index constraint and other table linkage information. Further multiple different RDBMSs may be used by different clients for data stored in different models.

The improved Master Data Management framework of the invention assures data definition structure and consistency for all data across all clients . Prior to this invention users would have to manually recreate their data model in the Master Data Management framework e.g. manually recreate the data from one data model into the master data model . Such a recreation can take several weeks or months to define manually.

One or more embodiments of the invention utilize the interface to provide for open model ingestion. A pre existing data model is ingested into the improved Master Data Management framework from any existing model source e.g. a RDBMS an ERWIN model or XML extensible markup language files . Such an interface represents a significant optimization to the process of implementing an improved Master Data Management at a client site.

Interface may include an open model ingestion OMI application also referred to herein as OMI application that imports a data model from any source e.g. from client or other RDBMS and expresses this model in a standard format e.g. metadata format that is specific to a particular entity e.g. a Teradata master data management solution available from the assignee of the present invention .

 1 An Import Wizard. This wizard guides the user step by step through the process of identifying a model source identifying the model components to import and any reconciliation or standardization steps that need to occur.

 2 A generic model ingestion framework. This framework includes abstract interface definitions the basis for an object oriented design that specify the process for retrieving data model information.

 3 Source specific code. This code implements the generic interfaces identified in the previous step for a specific data source. One source specific code set exists per data source e.g. RDBMS or modeling tools such as ERWIN .

 4 Final representation of the data model. The data model is converted from its original source into the Teradata Master Data Management model definition which includes one or more folders with each folder containing one or more document or table definitions. The model definition also contains a data dictionary that defines all data types used by the model. Finally the format of the document and dictionary files are an XML format.

Open model ingestion provides a significant competitive advantage when compared to the prior art. Embodiments of the invention allow customers or implementers to import a pre existing data model into a defined improved Master Data Management framework of the invention e.g. into the format of a meta data representation i.e. of a master data model within an hour. This represents a significant time savings when compared to other similar solutions which require that the pre existing model be redefined recreated manually a process which can consume weeks or months.

The OMI feature of the invention provides the ability to import a model from any source i.e. ERWIN EMBARCADERO physical DDL document definition language statements etc. . As described above the ingestion framework is not specific to the source from which a model is imported. The ingestion framework includes steps for creating new import wizards model wizard steps and the overall ingestion process which are not specific to a particular data model e.g. ERWIN or DDL specific .

This section documents the requirements for Open Model Ingestion OMI in accordance with the invention.

 1 The ability to import a data model generated by any tool. Embodiments of the invention import from multiple sources and promote as much reuse as possible. However some level of tool specific coding may be utilized for each new import source.

 2 Users clients ability to select a single database model source then select a subset of tables entities from the specified source to import.

 3 Users clients ability to import the source database objects directly into a meta data representation that may include a data dictionary .

Some embodiments may provide the ability to import a particular data model. The present invention provides the ability to extend such import capabilities to different types of models. To extend import capabilities an import strategy is utilized steps may be added to an import wizard existing import wizard steps are connected to the new steps and a model manager may be modified.

The import ingestion framework is governed by the import strategy . The import strategy is an abstract interface class specific implementations A C are provided as necessary to import from new data sources A C. Some embodiments provide models to be imported from a database e.g. RDBMS A . Accordingly the various implementations A C of the import strategy directly support the OMI process using a relational database as the source. For OMI ERWIN support e.g. B and B or to support other sources of models C another import strategy C is implemented. Note that a given import strategy implementation A C for a specific modeling tool may require updates as new versions of the tools are released.

The import strategy interface is an abstract class that consists of the following methods that are implemented A C for specific data models A C 

Accordingly meeting the requirements of OMI may require the implementation of multiple import strategies A C to support multiple data models A C. However there is a significant amount of reuse in the overall import process. Embodiments may include an import wizard and steps that are leveraged in any new import process. In fact leveraging such steps provides critical capabilities to properly merge new tables datatypes e.g. from data models A C into a meta data representation and to resolve any all differences.

Currently the process of importing a data model e.g. from an RDBMS model is invoked by right clicking on a graphical representation of the RDBMS model and selecting an Import Relational Database menu option. Such an action brings up an import wizard screen needed to import a model from a relational database model. A similar invocation of the import wizard may be used to initiate the importation of any first data model i.e. other data models B or C into the meta data representation A that is different from the first data model . The invocation of the import wizard provides a graphical user interface that guides the user through the process of importing a first data model B C into the meta data representation upon which master data model constructs e.g. workflows processes rules etc. can be built.

Overall there are a number of wizard steps performed when importing from a data model e.g. relational database model . Such wizard steps are illustrated in further detail in the flow chart of .

At step the source is selected by specifying the connectivity information of the source. Such connectivity information may be database connectivity information if a database model is being imported or an Erwin file name if importing from an Erwin file. Also note that a model wizard may be specified here. Such a step identifies the location of the source to be imported.

At step in a relational database importation process a schema is selected by selecting a single database from the selected source from which tables will be imported into the existing model.

At step one or more tables are selected from the schema to import into the meta data representation. Such a selection first retrieves and displays a list of all table names within a selected schema followed by the selection of one or more tables from the list.

At step tables are prepared by configuring e.g. adding renaming removing fields from a table as it is imported populated and also to create synonyms.

At step a nomenclature is setup by applying naming conventions upper lower cases add prefix suffix etc.

At step field types are categorized by moving data type definitions into a data dictionary that is stored with the meta data representation.

At step the model set is reconciled by specifying how the imported tables should be reconciled to the meta data representation. Such a process may also include populating table information for all of the selected tables into the meta data representation.

Note that of these steps only the first two steps select source and select schema are specific for a particular type of data model e.g. importing from a relational database . The remaining steps are generic regardless of the source or model type from which a model is being imported. More importantly the wizard itself is designed simply as a series of steps e.g. wizard steps and new model wizards can be created that still point to and reuse existing wizard steps .

Every import operation must have a model wizard file . A model wizard file is an XML file maintained by a model manager containing or consisting of a series of steps . The various steps select a source e.g. database connectivity information select a target holds target model and data dictionary i.e. the importation location select a schema selected schema to import from and select documents a list of selected tables documents while applying rules preparing tables lists any rules that are included as part of the import step resolving field types lists how data types are resolved and applying converters steps lists any data field converters that must be applied during the import .

Each step has a corresponding class that is referenced by the model manager. The model manager has overall responsibility for loading and saving the model wizard file while the individual classes have responsibility for loading their respective elements.

Each individual step class may implement an interface as well as two additional methods that return the contents of the step object as an XML element referred to as a get element method and that takes an element and sets it with the values currently held in the object referred to as an initialize element method .

Adding a new step to the import wizard may require adding additional step s to the model wizard . Model wizard steps can be added by 

While open model ingestion is described above a particular component implementation of the OMI provides the ability to import from an ERWIN data model B. The import strategy implemented in A C is the key component in creating an import method C for any other model C. An import strategy A C will need to be created implemented from abstract import strategy for each import source A C. ERWIN files B will require an import strategy B as well.

The particular import strategy A C is derived from an interface . All new importers A C must be derived from this interface and must implement the methods described above.

With respect to the getSchemaName method i.e. step of the ERWIN implementation B retrieves a list of schemas for display. The most common usage of ERWIN is probably that an ERWIN model B contains only a single schema database. However users may still be presented with a schema selection page in the import wizard .

The getTableNames method i.e. step of returns a sorted list of all table names within the specified schema from the ERWIN file B.

The getNecessaryTablesFor method also part of step of is called when the user selects tables from the available tables list and moves them to the selected tables list. This is part of the select tables step of the Import Wizard .

The populateDbSchema method i.e. steps of populates the table information for all selected tables. Like the previous method it is a mix of application logic and user interface UI code as it contains an action listener class to update the status display to show each table as it is being processed. This method is invoked when users press next on the table selection step of the import wizard .

The output of this method is a database document representing the table with all of the above information located within the database document data members.

Much of the actual ERWIN specific work the code that interfaces with the ERWIN model B directly is contained in a helper class called ERWINPlus.

The ERWIN import strategy B directly accesses the ERWIN data model B through the ERWINPlus class. The ERWINPlus class is a wrapper class that accesses the ERWIN data model B and aggregates results into the format required by the ERWIN ImportStrategy B. The ERWINPlus class accesses ERWIN model data B through an application programming interface API e.g. a COM component that is installed with the ERWIN product . This API provides the ability to directly access ERWIN model B components and to access sub components of each component.

An XML based approach to represent the meta data may also be used wherein a series of JAVA classes are generated that can be used to import marshal an XML document. ERWIN models B can be exported into an XML format i.e. of the meta data representation .

The following information can be retrieved if available from ERWIN data models B and imported into the appropriate master data manager structure 

The following table lists the various data types that can be found in ERWIN data models B and the data type this will ultimately map to in a master data management framework . Note that the data type may initially be mapped to an existing JAVA type code and then to a valid master data management type.

Of all of the import wizard steps described above i.e. in only three may be required for implementation of an ERWIN data model B i.e. in ERWIN import strategy B 

In view of the above the wizard presents a series of steps designated as steps in and steps of in a graphical user interface e.g. a simple window that allows the users to navigate and define the import ingestion operation.

The above described open model ingestion feature may be tied to an import process in which individual model objects had to be individually reconciled back to the current meta data representation. Put another way while users may quickly import a model from a source such as an ERWIN data model B the final step in the import process require the user to manually reconcile each data type and each table back to the meta data representation i.e. at step . Such manual reconciliation may be performed so that if the user is re importing an existing meta data representation changes to individual items can be reconciled rather than simply adding them to the existing meta data representation.

In a primary use case for the open model ingestion feature the user has an empty model i.e. meta data representation and the goal is to import all model objects from a source into the current meta data representation. Without the automatic reconciliation feature described below users would have to select the Add to Target reconciliation option for each data type and for each table. In a large model this could result in well over ten thousand 10000 mouse clicks and could take several hours simply to complete this final step in the import process when really the user just wants to automatically import all data types and table definitions into the current meta data representation e.g. the master data model .

Accordingly automatic reconciliation represents a significant optimization of the model ingestion process by allowing users with a single click to import all new data types and table definitions. This optimization allows a large model to be imported in less than 30 minutes rather than the several hours that could be consumed by a manual reconciliation operation.

With automatic reconciliation the final step of the master data management import wizard i.e. step of is optimized. A method of the invention without such automatic reconciliation is illustrated in wherein users are required to select a reconcile action of Add to Target for each data type and table definition. As illustrated the user is manually specifying a reconcile action in the resolution column then selecting the global action Apply Reconcile Intent which applies the specified reconcile intent specified in column to all data types and table definitions.

One or more embodiments of the invention simply add a global action called Add All To Target e.g. to the menu button on the bottom left enabling the activation of a down arrow adjacent to the apply reconcile intent text . When the user selects the Add All To Target action and presses the Go button all data types and documents tables that do not exist in the current meta data representation will automatically be added to the current meta data representation. Accordingly the user will not have to specify a reconcile action for each individual data type and table definition. Instead once utilized the resolution for every data type and table will automatically be set to Add to Target .

Thereafter the intent for each data type and table also known as documents internally is set to Add to Target and applied accordingly. The net result of such a process is that simply by selecting the proper global action and pressing the Go button every data type and table that does not already exist in the model will be automatically added.

In view of the above automatic reconciliation allows users to select a single global action of Add All To Target and press a Go button . All data type and table definitions are then automatically added i.e. without additional user input into the current meta data representation with a single mouse click saving the user several hours of tedious work. Accordingly the user may select an option to add all data types and tables from a first data model to a meta data representation wherein the selected option enables an automatic addition of all data types and tables without the user having to specify a reconcile action for each data type and table individually and manually .

This concludes the description of the preferred embodiment of the invention. The following paragraphs describe some alternative embodiments for accomplishing the same invention.

In one alternative embodiment any type of computer or configuration of computers could be used to implement the present invention. In addition any database management system decision support system on line analytic processing system or other computer program that performs similar functions could be used with the present invention.

The foregoing description of the preferred embodiment of the invention has been presented for the purposes of illustration and description. It is not intended to be exhaustive or to limit the invention to the precise form disclosed. Many modifications and variations are possible in light of the above teaching. It is intended that the scope of the invention be limited not by this detailed description but rather by the claims appended hereto.

