---

title: System and method for model-driven dashboard for business performance management
abstract: A system, method, and framework resulting therefrom, for a model-driven dashboard for business performance management, which includes capturing business dashboard model requirements at a business model level by providing at least one user-customizable model for capturing functionality of a dashboard, and after the user defines the functionality of the dashboard using the at least one user-customizable model, automatically generating code for a deployable dashboard application.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08843883&OS=08843883&RS=08843883
owner: International Business Machines Corporation
number: 08843883
owner_city: Armonk
owner_country: US
publication_date: 20070103
---
The present invention generally relates to a system and method of generating code for a model driven dashboard for business performance management and dashboard resulting therefrom and more particularly to a system and method of capturing business model requirements at a business model level including providing at least one user customizable model or a plurality thereof for capturing functionality of a dashboard and after the user defines the functionality of the dashboard using the at least one user customizable model automatically generating code for a deployable dashboard application.

Enterprises are leveraging information technology solutions in order to increase their productivity and their business value in the marketplace. As they adopt the paradigm of describing and monitoring their business operations in a systematic manner the need for visually representing such processes in a model becomes critical. Nowadays many vendors provide sophisticated tools to represent business process models and business activity monitoring models.

In modern businesses several of those processes and activities correspond to procedures that monitor and measure the performance of the business. Business Performance Management BPM generally includes a suite of components that are used to monitor the health of the business. BPM delivers significant benefits to the businesses by offering them the ability to react promptly to changes in their environment. BPM is enabled by the level of automation and systems integration that is currently in place in the majority of businesses. The integration of various systems in the business allows for continuous monitoring of business performance using carefully selected metrics also known as Key Performance Indicators KPIs .

For purposes of this disclosure Key Performance Indicators KPI generally mean indicators that help organizations achieve organizational goals through the definition and measurement of progress. The KPIs generally are displayed to the analyst through a dashboard.

For purposes of this disclosure a dashboard generally means a user interface that organizes and presents information in a way that is easy to read and interpret. Dashboards can be essential elements in the day to day operation of modern enterprises as they provide to the analysts the view of all the critical business metrics that reflect the performance of the business.

In contrast to the usefulness and ease of use that dashboards represent the amount of effort that is required for their development can sometimes be daunting. User interface development in general and dashboard development too can require a considerable investment of time and can often take as much as 65 80 of the overall development time in a model driven business transformation project.

The present inventors have recognized that business process and business performance modeling are becoming increasingly important as modern enterprises seek ways to exploit high level design and reasoning as well as some degree of automation in the code generation process.

For example the present inventors have recognized that the development of software using business and Information Technology IT models are gaining market share. Model driven Business Performance Management BPM is one such example.

The present inventors also have recognized that BPM Dashboards are a critical component of business process and business performance modeling. However conventional dashboards are custom designed with large development cycles and are not connected to Business Models.

The present inventors have recognized that a higher cost is needed to build and maintain such a dashboard if developed with conventional techniques. The present inventors have recognized a lack of business and IT dashboard models for representing business requirements. Also it is difficult to translate such conventional dashboard models if existing into actual dashboard reports due to a lack of Meta Models.

The present inventors also have recognized that the problem of defining dashboard report templates as the structure of input data is unknown and has not been addressed in the conventional systems and methods.

The inventors have recognized that while there may be a significant research effort towards these directions the conventional systems and methods to date have focused on the problem of how to effectively model a business process but have not addressed the problem of modeling the entire business performance monitoring process from the source data to the dashboard i.e. the user interface for the monitored metrics .

In view of the foregoing and other exemplary problems drawbacks and disadvantages of the conventional art methods and structures an exemplary feature of the present invention is to provide an efficient and effective model driven dashboard design system method and dashboard resulting therefrom and more particularly to capturing business dashboard model requirements at a business model level including providing a plurality of user customizable models for capturing functionality of a dashboard and after the user defines the functionality of the dashboard using at least one of the plurality of user customizable models automatically generating code for a deployable dashboard application.

The present invention extends the business performance modeling framework by providing a number of new models that enable the process of dashboard design. The model driven approach according to the present invention can render the dashboard design and deployment process less time consuming and less cumbersome. The present invention can provide automated code generation and allow fast and easy integration of the dashboard with the final solution.

The inventors of the present invention will describe the novel designing and deploying of a dashboard for a real world business as well as the results of such experiments thereby demonstrating the feasibility and effectiveness of the present invention. The present invention can provide a significant reduction in terms of required development time when compared to a conventional dashboard deployment process.

In an exemplary aspect the present invention can provide Business Dashboard Models Unified Modeling Language 2 UML2 and IT level Meta Models.

In another exemplary aspect the present invention can extend existing BPM Models UML2 Profiles to for example 

The present invention can define Meta Models Extensible Markup Language XML Schema to capture the modeling and dashboard report elements.

In another exemplary aspect the present invention can provide software components for automatic transformation of the Models to the Actual Reports.

In yet another exemplary aspect the present invention can provide Pre defined static Data Templates and Plug in components for defining Report Template.

The exemplary aspects of the present invention provide important advantages such as the capability of modeling very small set of data elements facts dimension hierarchies levels . Thus the structure of the data can be limited to few predefined sets Data Templates . The data access and filtering logic are deterministic in nature.

The exemplary aspects of the present invention can provide a mechanism to provide coarse and fine grain access to the data by roles. The context data to KPI s can be stored as dimensions. The exemplary model can allow roles to dimension level access coarse grain access . At pre runtime the present invention can provide the ability to provide user to actual content access via an administrator .

The present invention can provide a software component can transform the model into meta models and finally into deployable reports. The software component can be provided as a tag library plug in or equivalent software component for Report templates for example for auto generation of one of the predefined data sets providing filtering functionality etc.

The present invention can provide assistance to a Report template user defined for example by selecting one of the data structure sets for the template using provided tag library and Application Programming Interfaces API s to access the data etc.

The conventional systems and methods generally deal with the dashboard at the data level not at the modeling level.

One exemplary aspect of the invention is directed to a method of capturing business dashboard model requirements at a business model level which includes automatically generating code for a deployable dashboard application based on providing a plurality of user customizable models for capturing the functionality of a the deployable dashboard.

Another exemplary aspect of the invention is directed to a method of capturing business dashboard model requirements at a business model level which includes providing a plurality of user customizable models for capturing functionality of a dashboard and after the user defines the functionality of the dashboard using at least one of the plurality of user customizable models automatically generating code for a deployable dashboard application.

Yet another exemplary aspect of the invention is directed to a tool for capturing business dashboard model requirements at a business model level and automatically generating code for a deployable dashboard application wherein the tool includes a Rational Software Architect RSA Modeler.

A further exemplary aspect of the invention is directed to an Extensible Markup Language XML Schema for capturing business model requirements at a business model level and automatically generating code for a deployable dashboard application wherein the Extensible Markup Language XML Schema defines an Information Technology IT Meta Model for capturing the user customizable models.

Yet another exemplary aspect of the invention is directed a system for model driven dashboard design which includes at least one user customizable model for capturing functionality of a dashboard a dashboard code generator for automatically generating code for a deployable dashboard application after a user defines the functionality of the dashboard using at least one of the plurality of user customizable models.

Still another exemplary aspect of the invention is directed to a dashboard framework for capturing business dashboard model requirements at a business model level and automatically generating code for a deployable dashboard application which includes a dashboard model editor that edits a formal model that represents a dashboard report requirement based on artifacts of the formal model retrieved from a storage unit a dashboard meta model translator that transforms the formal model into a meta model and a dashboard code generator that automatically generates dashboard code for creating the deployable application.

Another exemplary aspect of the invention is directed to a computer readable medium tangibly embodying a program of recordable machine readable instructions executable by a digital processing apparatus to perform the exemplary method according to the present invention.

Still another exemplary aspect of the invention is directed to a method of deploying computing infrastructure in which computer readable code is integrated into a computing system and combines with the computing system to perform the method according to the present invention.

Referring now to the drawings and more particularly to there are shown exemplary aspects of the method and structures according to the present invention.

The present invention generally relates to a system and method of business performance modeling and model driven business transformation.

For example illustrates an exemplary high level architecture of model driven dashboard framework according to an exemplary non limiting aspect of the present invention. The present invention can provide business models such as business performance management BPM models as well as other models which would be known and understood by the ordinarily skilled artisan. The present invention also can provide a template store and a model store .

The model driven dashboard framework can include for example a dashboard model editor which can be used to capture a representation of the dashboard models. The dashboard meta model translator can then be used to transform the dashboard model from the dashboard model editor into a meta model representation. The meta model representation can be fed into the dashboard code generator which can automatically generate a deployable dashboard application .

Moreover the exemplary aspects of also can replace the BPM Observation Model OM with other business modeling approaches without affecting the dashboard model as exemplarily illustrated by the external modeling .

As exemplarily illustrated in the present invention provides the user with the ability to define report templates based on existing templates or newly created templates e.g. including a predetermined number type etc. of tables charts etc. . That is the user can select predefined templates or a plug in component for report templates from the template store .

Referring to the exemplary pre modeling activity diagram which is illustrated in more detail in the predefined data templates e.g. summary detail etc. can include sets of fixed data structures. The view component e.g. which can be embedded in the report templates can include a JavaServer Pages JSP tag library software component which can include for example an Application Programming Interface API to register the data template an API to register the user and user role an API to register the filter information an API to register Data warehouse related information a function to form Structured Query Language SQL for data extraction by role and filter and a function to return either the Query or Data template instance to Report etc. The predefined sample report templates can includes sets of readily available report templates incorporating framework components. The user interface UI designer modeler defined report templates can include application specific custom report templates which can be defined by an appropriate role player e.g. administrator . The user can chose the data template and embed view components to use the framework.

Turning again to the exemplary high level end to end dashboard component flow diagram as illustrated in the present invention can provide an observation model data warehouse model a dashboard model a dashboard meta model and a deployment code .

With reference to the exemplary modeling activity flow chart in the observation model data warehouse model can include for example existing models. The dashboard model UML can include stereotypes to create dashboard models such as Model User Roles to Metric Access Model User Roles to Data Access via dimension Model User Roles to Report Template Access Model Metrics to the Report Templates Model Navigation and Access etc. The dashboard models can be transformed into dashboard meta model XML e.g. an intermediate dashboard model representation XML instance .

The dashboard meta model XML can be transformed into deployable components such as dashboard databases tables Data Definition Language DDL dashboard application e.g. EAR file .ear etc.

Turning again to the exemplary high level end to end dashboard component flow diagram as illustrated in the present invention can provide deployable dashboard components users to data mapping e.g. to define access control . The deployable dashboard components can capture data from the data warehouse to generate view dashboard reports .

The inventors have recognized that while there is a significant research effort towards these directions the conventional systems and methods to date have focused on the problem of how to effectively model a business process but have not addresses the problem of modeling the entire business performance monitoring process from the source data to the dashboard i.e. the user interface for the monitored metrics .

The present invention provides an approach for dashboard development that is model driven and can be integrated with the business performance models. The present invention adopts the business performance modeling framework and extends it in order to capture the reporting aspects of the business operation. The present invention can provide models that can effectively represent all the elements necessary for the business performance reporting process and the interactions among them. The present invention can demonstrate how all these models can be combined and automatically generate the final solution.

The present invention can provide dashboard development that can be fast and easy while maintaining flexibility in the design and without sacrificing versatility or performance. The framework for dashboard design that is model driven. The framework according to the present invention can include a number of user customizable models that can effectively capture the functionality of a dashboard. The present invention can provide different models for modeling the data the users and their data access privileges and the navigation among the various data views.

Once the user has designed the dashboard with the desired functionality using the provided models the exemplary framework according to the present invention can automatically generate code for the deployment of the dashboard leaving only minor customization issues for the developer. The generated code can cover all the aspects of the dashboard such as 

The present invention can permit the developer to focus on the dashboard functionality and can relieve the developer from the burden of the user interface development experience. The benefits of such a model driven dashboard development according to the present invention can include the graphical representation and easy manipulation of the solution the error free code generation and the ability to capture the business reporting requirement quickly and cost effectively. The conventional systems and methods have not recognized such an approach for model driven dashboard design.

Thus the present invention can describe a framework for model driven dashboard design. The models employed by the present invention can cover the many facets of this process such as the data to be displayed the users of the system the roles and access privileges of each user the content of each dashboard page view and the navigation among those views.

The method according to the present invention is complementary to business process and business performance modeling and leverages from such models. The present invention describes how such a novel approach can interact with a specific business performance modeling approach namely BPM.

Nevertheless the ordinarily skilled artisan would recognize that the present invention is not customized for BPM and can operate in conjunction with any other business process model as well.

The framework according to the present invention can enable the automated generation of all the code necessary for the deployment of the dashboard. Therefore the burden of tedious programming from the dashboard development team can be reduced or eliminated and the time required for delivering the solution can be greatly reduced.

The approach of the present invention can be validated using real world scenarios. The application of the proposed method to a real problem and demonstration of the benefits of the present invention with regards to development time and flexibility of the solution will be described below.

As described above there is a growing trend in using model driven methodologies for developing large system software due to their high level abstraction and code re use or regeneration . They have been widely applied in related areas such as software reuse reverse engineering and user interface design. The benefits of adopting model driven design include reduced software development time enhanced code quality and improved code maintenance.

There are also numerous related works about business processes. Widely considered as an extension of a workflow management system business process management enables the management and analysis of operational business processes. Recent work has focused on modeling business processes consistency checking for model integration and composing Web services and business processes via the model driven approach.

Business processes can be implemented for example using a workflow or a state machine model. The workflow model is a natural representation for a business process model modeling the sequence of tasks corresponding to the business operation. There can also be control logic and data transformations between tasks. Business Process Execution Language BPEL defines a program understandable language to represent such a process for web service environments. Yet BPEL can only orchestrate the flow execution business data are still not synchronized correlated or linked together for the auditing and analysis purposes.

An approach that tries to overcome the above shortcomings is the Model Driven Business Transformation MDBT . MDBT models business operations from the point of view of a business analyst without regard to existing or planned information technology solutions. In other words an MDBT operation model is a truly Computation Independent Model as described by Object Management Group OMG . The first step in creating an operation model is to identify the primary business artifacts that an enterprise must create and process to conduct its business. The operations can then be described by the set of tasks that must be performed to process those artifacts and the roles assigned to the tasks. In our experience such operation models combine artifact lifecycles and data in a way that is more meaningful to business analysts. As described below MDBT can include a path to implementation of the operation model.

There is also much interest around the concept of dashboards with several conventional solutions. For example conventional dashboard applications have been specifically designed for doing some analytics and for visualizing data. Nevertheless these conventional approaches do not integrate with the business process and business performance models. Therefore the conventional approaches require much effort to develop and maintain.

In contrast the present invention provides a novel method for dashboard design that is model driven. The high level models defined by the present invention can be integrated seamlessly with business performance models leveraging the common parts of the design and enabling an end to end design process.

In addition to espousing a business artifact centric approach to operation modeling MDBT offers a model driven development toolkit and technique. The tools automatically transform an operation model into a platform independent solution composition model in UML2. In this stage of modeling the solution architect can fill in much of the IT detail that is outside the domain of the business analyst. These details can include integration with external services as well as role players. At each stage in the lifecycle of the business artifacts now represented as a state machine the architect specifies what portion of the data associated with the artifact will be available to the relevant role players and services. Following the completion of the solution composition model MDBT code generation tools can automatically create Java 2 Platform Enterprise Edition J2EE components that manage the process and provide a simple user interface by which users can interact with the solution. The automated transformations and code generation can enable rapid prototyping greatly accelerating the development cycle and allowing for a fast turnaround iterative development regimen.

The solution composition model also can provide a platform on which an observation model can be constructed. The elements of the observation model e.g. events can be linked to those of the solution composition model e.g. states and transitions so as to define how the performance metrics will be gathered.

Business Performance Management BPM can be an effective means of monitoring business processes. Model based BPM normally includes an observation model that conforms to a pre defined meta model such as the one provided by MDBT which we discussed above. Entities such as input events metrics outbound events situation detectors and actions can be monitored and scheduled through the observation model. Using BPM the present invention can detect bottlenecks of business operations in real time or analyze them at a pre determined schedule and identify anomalies by correlating event sequences. Based on the observation model actions triggered by the above situations can involve sending out email alerts or displaying statistics and aggregated information onto a dashboard.

The present inventors implemented a BPM solution based on the model driven development methodology. There are two exemplary approaches that were adopted for representing a BPM solution.

The first approach utilizes the Unified Modeling Language UML with UML2 profile extension. With a convenient graphic user interface GUI tool BPM entities and relationships can be defined using UML models. The second approach utilizes XML schemas for defining BPM entities and the relationships between the entities. Both approaches can be implemented as plug ins on Rational Software Architecture RSA .

Although the exemplary aspects of the present invention are described under the general framework of MDBT and BPM the ordinarily skilled artisan would know and understand that the present invention is not limited to this framework. As described in more detail below an XML interface for example can be used to allow the present invention to operate with any other business process modeling frameworks.

Referring now to the drawings and more particularly to there are shown exemplary aspects of the method and structures according to the present invention.

With reference to an exemplary high level architecture for a model driven dashboard framework will be described below. Model driven dashboards aim at automating the reporting capabilities related to business monitoring. Therefore they have the potential to bridge the gap between BPM models that specify the elements of a dashboard and dashboard development which is conventionally a manual effort i.e. manually performed .

Specifically the present invention extends the BPM Observation Model OM one of the Unified Modeling Language UML Models of MDBT Toolkit that captures the monitoring and alerting requirements of an enterprise. In order to visually represent these requirements as models the OM makes use of the UML2 profiles to extend the base UML elements. The Dashboard Model employs similar techniques to represent its modeling elements so that the solution designer can work with consistent models for the entire end to end solution design. The exemplary models can capture aspects of the BPM Dashboard. For example the model can capture a definition of metrics and related context information to be displayed on the dashboard organization of information into pages and definition of navigation paths among these pages and assignment of access control privileges to the dashboard information depending on the user roles.

The ordinarily skilled artisan would know and understand that the present invention is not limited to representing the dashboard modeling artifacts using UML 2 and that the present invention can represent the dashboard modeling artifacts using other tools and techniques other than UML 2.

The present invention can use popular modeling tools such as Rational Software Architect RSA for capturing the UML representation of the dashboard models. The ordinarily skilled artisan would know and understand that RSA can be interchanged with any other editor supporting the UML 2 notations within the spirit and scope of the present invention.

Turning again to the exemplary dashboard framework can include a dashboard model editor which can receive inputs from a report template storage unit and a model storage unit . Business models such as business performance management BPM as well as other business models can be input into the dashboard model editor .

For illustrative purposes the present invention uses UML for all the modeling requirements in the exemplary framework. However the present invention also can provide an equivalent XML representation which serves as the exemplary meta model. In fact the representation that the exemplary approach uses internally is the XML representation. illustrates an exemplary Business Performance Management BPM dashboard meta model XML schema definition according to an exemplary non limiting aspect of the present invention. The transformation between the UML and the XML representations is lossless in the sense that all the modeling elements and the relationships among them are preserved.

By providing the Dashboard XML Meta Model as an additional level of abstraction the present invention can decouple the dashboard modeling process from the modeling of the rest of the business processes. Therefore changes in the OM can be prevented from affecting the Dashboard Framework . Moreover the present invention can replace the OM with any other business modeling approach e.g. without affecting the dashboard model e.g. external modeling .

When the dashboard model e.g. has been transformed into the dashboard meta model representation e.g. the present invention can feed this representation to the dashboard code generator which subsequently can produce the deployable dashboard application . The generated application can consist of the dashboard Application which is the set of files that contain the actual code for the application and the dashboard DDL which is the set of files that generate the auxiliary structures needed by the application such as database tables. These tables can be created in the BPM data warehouse.

The dashboard application can be readily deployed on a J2EE application server. The particular choice of the application server is orthogonal to the solution of the present invention. It is noted that the exemplary code generator according to the present invention can be modified to generate deployable components for any application server.

For example the present invention can begin by defining custom reports e.g. to be used by the dashboard or by simply selecting some of the predefined reports from the template data store . The present invention can define plug in components for report templates . Atemplate store can be provided.

As will be discussed below the role of these report templates is to retrieve the appropriate data and handle the presentation of these data on the screen. Then the solution designer can model the dashboard elements using the Model Editor transform the result into the Dashboard Meta Model representation and invoke the Code Generator to generate the deployable software components e.g. . Once deployed the Dashboard can be accessed using a web browser. The aspects of exemplary Dashboard Model elements are discussed below.

The dashboard model artifacts according to the present invention can be classified for example into three categories. A first category can be related to modeling the data that are necessary for the dashboard and can include data and metric models. A second category can correspond to an abstract presentation layer including navigation and report template models. Finally a third category can be related to user roles and data access privileges and can include models that define the dashboard access control by relating user roles to data elements as well as elements in the presentation layer.

As discussed above the present invention exemplarily uses UML for the entire dashboard modeling requirements because it is widely accepted in the industry and also because it provides to the solution developer a consistent platform to work with across the various MDBT models.

The ordinarily skilled artisan would know and understand that the present invention is not limited to representing the dashboard modeling requirements using UML and that the present invention can represent the dashboard modeling requirements using other tools and techniques other than UML.

The present invention can extend the UML meta classes and relationships by introducing new stereotypes using UML 2 profiles to model the dashboard elements. These stereotypes can then be stored as part of an existing BPM model profile. When modeling an actual solution using a modeling editor these profiles can be applied in order to take advantage of the BPM Dashboard Model elements.

With reference again to in an exemplary aspect of the present invention it can be assumed that all the necessary data can be stored in a data warehouse using a star schema. Therefore the present invention can use the metric group model artifact definition as exemplary illustrated in where each data element is marked as either a dimension or a metric. Even though the data model supported by the present invention is simple its semantics are rich enough to be able to model many real life scenarios. This is because it is usual for real world data modeling problems especially the ones that are being targeted by the present invention to have a natural star like representation. An example scenario may be product sale information where the metrics can include number of units sold and revenue and the dimensions can include geographies and time.

In the present invention introduces a Metric Group modeling element which can be used for grouping of relevant metrics. Such a grouping may be useful when modeling relationships to other artifacts where all the members of the Metric Group participate. exemplarily illustrates the Metric Group UML class that connects to the Metric class in an aggregation relationship.

In the present invention illustrates exemplary GUI modeling Elements stereotypes such as a Navigation Tree Page and Menu classes. These three classes can form the Dashboard Navigation Model. In a typical scenario the analyst can start by defining some pages and then associating these pages with menus. In a last step the analyst can introduce a Navigation Tree element in order to capture the navigation paths among the pages which eventually form the Dashboard reports.

Dashboard report templates can be used to define the information content of individual pages. For example illustrates that a Report Template can be associated with a page and may refer to several Metric Groups. When the page is displayed on the dashboard the information about all the metrics corresponding to the templates can be rendered on the screen. It is noted that each page can be associated with one or more Report Templates.

The Report Templates also can define the details for the visual presentation of the data they contain. By creating a report template the user can choose to display a set of metric data as a table as a chart or using both display modes.

A dashboard access control model can define all the access control properties relevant to the dashboard. Using the various modeling elements the present invention can specify for each user role the access privileges to different parts of the data as well to different pages of the dashboard. Thus the dashboard users according to their assigned roles may only have access to a subset of the dashboard reports.

The relationships between user roles and metrics and user roles and dimensions will be exemplarily described below.

According to the present invention a UserRole MetricGroup relationship specifies the access privileges of User Role to Metric Group. When the analyst creates an aggregation link between the above two modeling elements all the users assigned to User Role gain access to all the metrics described by Metric Group. his lets the model capture the role based access to metrics. At runtime based on this model the system can determine what metrics to show on the dashboard based on the User Role i.e. only those metrics for which the user has access are displayed on the dashboard .

According to the present invention a UserRole DimensionScope relationship can define the User Role access privileges to various dimensions as well as to the dimension levels in each dimension. This lets the business analyst define fine grained access control at the metric context.

When the dashboard has been deployed and is ready for use the administrator can have the ability to further refine the data access control by the specific data values as will be described below.

An Access by Report Template can be another aspect of dashboard report access control modeling. A User Role may have access to one or more Report Templates and the business analyst may select a set of already defined templates and associate them to the User Role elements. This lets the dashboard framework filter the templates that are shown to the user of the dashboard. exemplarily illustrates a User Role to Report Template relationship.

The framework according to the present invention can permit the business analyst to define access control based on Navigation Trees as exemplarily illustrated in . It is noted that a single Dashboard Model can involve several Navigation Trees. In this exemplary case the business analyst may wish to provide different access privileges to each one of the navigation trees according to User Role.

The foregoing access control models provide a powerful and flexible toolset. Indeed not only do the foregoing access control models provide coarse and fine grain access control to data but they also allow the business analyst to design a small set of pages which at run time will display different information according to the access privileges of the user accessing the dashboard.

An exemplary dashboard model solution methodology will now be described. Even though the model driven approach brings efficiency to BPM solutions development it can be beneficial to understand and follow a specific methodology that can lead to a successful and efficient solution.

The exemplary dashboard modeling methodology according to the present invention can be divided in the following three main activities 1. Pre modeling activity 2. Modeling activity and 3. Post modeling activity each of which will be described below.

Before starting to sketch models in order to capture the dashboard requirements the business analyst is required to understand the predefined components and templates that are included in the Dashboard Framework tool. These components can aid in quickly and efficiently designing the solution.

The framework can provide another software component e.g. the view component which is responsible for connecting the data layer with the presentation layer of the dashboard. The view component can use the data structure and User Role elements to connect to the data sources and can generate an instance of the data structure which during runtime is passed to the Report Template instance discussed below that finally renders the visual widgets. In order to achieve seamless integration the view components may need to be embedded in the Report Templates. In the implementation according to an exemplary aspect of the present invention the view components can be included as JavaServer Pages JSP tag libraries.

The present invention also can provide a set of predefined Report Templates . For example a table and a chart component can be provided. As exemplarily illustrated in the framework also can support user defined Report Templates . A restriction e.g. the only restriction may be that the new template supports the data templates in its input.

After the custom Report Templates have been defined the next step can be to model the reporting requirements. During this exemplary step the user may need to perform the following tasks. First the user can identify the metrics that will become part of the dashboard views and create Metric Groups by grouping together similar metrics. Second the user can create report templates for all the different types of information that are to be displayed on the dashboard. Third the user can create page elements and associate them to one or more of the report templates defined earlier. Fourth the user can create the menu elements for the dashboard portal and link the menu items with the corresponding pages. Finally the user can introduce navigation tree elements in order to define the navigation flow of the portal.

The different user roles that need access to the dashboard portal also can be defined. Individual users can be assigned a role by the portal administrator during the portal configuration time.

Each user role can be associated with Metric Groups Dimensions Report Templates and Navigation Trees so as to specify the access control privileges.

Once the Dashboard Model is ready it can be automatically transformed into an intermediate XML meta model representation according to the present invention which can be independent of the tool used to build the Dashboard Model. Subsequently this model can be processed by the Code Generator that produces all the required deployable software components.

The Dashboard DDL can contain the definitions for all the tables that need to be created in the BPM Data Warehouse e.g. . The Dashboard DDL also can contain necessary SQL scripts for reading data from and inserting data in those tables.

The Dashboard Application can be a J2EE application that needs to be deployed on a J2EE Application Server. The Dashboard Application can contain the web module that consists of the chosen report templates along with other supporting software components provided by the framework.

As another step in the dashboard deployment procedure the user can define fine grain data access control according to specific data values of the warehouse e.g. . In describing the access control in the dashboard model above it was described that the model allows access privileges to be defined based on the data dimensions. For example the present invention can permit a particular user role to roll up and drilldown on the geography dimension.

Even though the above kind of access control can be very useful in some cases it may not be enough. For example consider the situation where two different managers are responsible for the Europe and America geographies. In this case it may be desirable to restrict the access of each manager to the geography for which she is responsible.

In order to achieve this fine level access control the present invention can augment the User Role to Dimension model with special annotations that specify the levels of each dimension that can be accessed by the User Role. Note that the present invention generally does not perform this step of access control during the modeling phase because it depends on the specific data of the application which are only available in the warehouse after the application has been deployed.

In order to assess the feasibility and effectiveness of the present invention the inventors applied exemplary aspects of the present invention to real world problems.

In an exemplary case the objective was to develop a dashboard to support the business operation of the TeleSale Representatives TSRs that are responsible for the sales of the entire range of a particular product across the globe.

The TSRs are responsible for the entire life cycle of a sale. Initially a customer expresses an interest to buy to which the TSR responds with a quote. If the customer decides to close the deal then the quote is turned into an order.

In their day to day operations the TSRs need to have a concise view of their business so as to plan their actions accordingly. The dashboard according to the present invention can be used to display information on both the quotes and the orders capturing various metrics related to these activities such as number of quotes and orders order channel revenue and others. These metrics can be organized according to several dimensions such as time geography product type customer type and others. Furthermore access restrictions can be in place which limit the views of the data offered to the TSRs and the region managers.

The steps of the exemplary solution development process using the Dashboard Framework will be described below.

The present invention can be started by presenting the models that were created for the dashboard. Note that for brevity in all the following diagrams only part of the models that form the complete solution are depicted.

As mentioned above the first step can be to identify the Report Templates that are needed. If the existing predefined templates are not suitable then custom Report Templates can be defined. For this case study pre defined summary templates e.g. OrderSummaryTemplate as well as some custom made templates e.g. OrderDetailTemplate were used.

Subsequently similar metrics were identified and grouped together as MetricGroups. As exemplarily illustrated in revenue and average revenue for orders can be grouped into OrderMetricGroup while average number of quotes and average quote value can be grouped into QuoteMetricGroup.

The relationships among metrics and dimensions can be captured by a data model as exemplarily illustrated in . This diagram can contain relationships that connect dimensions to metrics as well as metric groups. The latter case can be translated as a relationship between the dimension and each one of the metrics under the Metric Group. A link between a metric and a dimension generally means that the metric can be aggregated along this dimension.

In order to organize the information into different views or pages the present invention can use the Report Template model. exemplarily shows this model for a summary view which can display data relevant to orders and quotes. More specifically this summary page can contain data for orders revenue and average revenue represented by OrderMetricGroup and average number and value of quotes represented by QuoteMetricGroup .

Once all of the pages and menus that are going to be used in the dashboard are defined the present invention can proceed to model the Navigation Trees. The Navigation Trees can represent the paths that the dashboard user can follow when navigating from page to page. As exemplarily illustrates the present invention can define several Navigation Trees and each page can belong to more than one Navigation Tree.

Subsequently the present invention can define all the data access privileges for the dashboard. can depict the assigned privileges for the Telesales and Manager user roles with respect to metrics and dimensions. The model that is created can allow Telesales users to access quote metrics and aggregate them along the brand dimension. In addition to the above Manager users can also access order metrics and aggregate these metrics along the geography dimension.

When the modeling phase is completed the present invention can initiate the deployment of the different software components as described below.

There can be for example two deployable components generated as a result of the modeling activity. The Dashboard DDL component can be the data warehouse schema script that supports the dashboard functionality. This schema can store and manage all of the information relating to metrics and maintain the fine grained access control to this information by user role.

The Dashboard Application component can be an Enterprise Application that can be deployed on a J2EE application server and can subsequently be accessed using a web browser.

In the exemplary implementation according to the present invention the generated application can be deployed on WebSphere Portal Server and can use conventional commercial data visualization tools for rendering the reports the framework provides a tag library or equivalent software component that allows the report template to connect to various commercial data visualization tools.

In a screen capture from the deployed dashboard application according to the present invention is exemplarily illustrated. This example illustrates a page that uses tables to display two different types of data regarding quotes left side of the picture and a graph to visualize these data right side of the picture .

According to the exemplary aspects of the present invention the model driven approach for dashboard development can provide significant savings in terms of time and cost. For example a project that may normally require more than three months may be completed for example in just three weeks using the proposed framework according to the present invention.

In addition the dashboard developers do not need to have any in depth knowledge of databases and data warehouses or access control mechanisms. All these aspects of the dashboard generally can be completely hidden from the developer and managed by the proposed framework.

The CPUs are interconnected via a system bus to a random access memory RAM read only memory ROM input output I O adapter for connecting peripheral devices such as disk units and tape drives to the bus user interface adapter for connecting a keyboard mouse speaker microphone and or other user interface device to the bus a communication adapter for connecting an information handling system to a data processing network the Internet an Intranet a personal area network PAN etc. and a display adapter for connecting the bus to a display device and or printer .

In addition to the hardware software environment described above a different aspect of the invention includes a computer implemented method for performing the above method. As an example this method may be implemented in the particular environment discussed above.

Such a method may be implemented for example by operating a computer as embodied by a digital data processing apparatus to execute a sequence of machine readable instructions. These instructions may reside in various types of signal bearing media.

This computer readable media or signal bearing media may include for example a RAM contained within the CPU as represented by the fast access storage for example. Alternatively the instructions may be contained in another computer readable media or signal bearing media such as a data storage disk diskette directly or indirectly accessible by the CPU .

Whether contained in the disk diskette the computer CPU or elsewhere the instructions may be stored on a variety of machine readable data storage media such as DASD storage e.g. a conventional hard drive or a RAID array magnetic tape electronic read only memory e.g. ROM EPROM or EEPROM an optical storage device e.g. CD ROM WORM DVD digital optical tape etc. paper punch cards or other suitable computer readable media or signal bearing media including transmission media such as digital and analog and communication links and wireless. In an illustrative embodiment of the invention the machine readable instructions may comprise software object code compiled from a language such as C etc.

While the invention has been described in terms of several exemplary aspects those skilled in the art will recognize that the invention can be practiced with modification within the spirit and scope of the appended claims.

Further it is noted that Applicants intent is to encompass equivalents of all claim elements even if amended later during prosecution.

