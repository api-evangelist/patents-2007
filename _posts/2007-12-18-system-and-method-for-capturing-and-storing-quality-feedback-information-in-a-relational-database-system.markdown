---

title: System and method for capturing and storing quality feedback information in a relational database system
abstract: A computer implemented method of and system for capturing, storing and organizing quality feedback information associated with products sold by a retail enterprise. The quality feedback information is stored and organized within a relational database in accordance with a logical data model comprising a plurality of entities and relationships defining the manner in which quality feedback information is stored and organized within the relational database. The relational database, populated with quality feedback information, provides the retail enterprise with the means to analyze and improve retail operations, to better manage store inventory, and more efficiently manage product sales and returns.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08131577&OS=08131577&RS=08131577
owner: Teradata US, Inc.
number: 08131577
owner_city: Dayton
owner_country: US
publication_date: 20071218
---
This application claims priority under 35 U.S.C. 119 e to the following co pending and commonly assigned patent application which is incorporated herein by reference 

Provisional Application Ser. No. 61 003 191 entitled TERADATA RETAIL LOGICAL DATA MODEL 5.01 filed on Nov. 14 2007 by Pieter Lessing Dennis Jeng and Mark Crosby.

This application is related to the following co pending and commonly assigned patent applications which are incorporated by reference herein 

application Ser. No. 10 016 899 entitled SYSTEM AND METHOD FOR CAPTURING AND STORING INFORMATION CONCERNING SHOPPERS INTERACTIONS AND TRANSACTIONS WITH AN E BUSINESS RETAILER filed on Dec. 14 2001 by Kim Nguyen Hargett and Pieter Lessing 

application Ser. No. 10 017 146 entitled SYSTEM AND METHOD FOR CAPTURING AND STORING INFORMATION CONCERNING RETAIL STORE OPERATIONS filed Dec. 14 2001 by Kim Nguyen Hargett and Pieter Lessing 

application Ser. No. 10 190 099 entitled SYSTEM AND METHOD FOR CAPTURING AND STORING FINANCIAL MANAGEMENT INFORMATION filed on Jul. 3 2002 by Sreedhar Srikant William S. Black Scott Kilmo Karen Papierniak and James W. Smith and

application Ser. No. 11 444 047 entitled SYSTEM AND METHOD FOR CAPTURING AND STORING RFID SERIALIZED ITEM TRACKING INFORMATION IN A RELATIONAL DATABASE SYSTEM filed on May 31 2006 by Pieter Lessing Dennis Jeng Mark Crosby and Sreedhar Srikant.

The present invention relates generally to Data Warehouse solutions and more particularly to systems and methods for capturing storing and using detailed data on store operations for a Retail Business. Still more particularly the present invention is related to a logical data model for storing and organizing quality feedback information within a Retail Business data warehouse system.

Teradata Corporation has developed a data warehouse solution including a comprehensive suite of analytical and operational applications that captures organizes and advances the use of high value business information within a Retail Business. An objective of Teradata Corporation s retail data warehouse solution is to enable retail management to easily access and analyze information that is critical to the operation of retail outlets.

The retail data warehouse solution has been improved to enable the capturing of quality feedback information for products and services sold by the retail enterprise. Maintaining this information in a data warehouse provides the retail enterprise with the ability to analyze and improve supply chain operations to better manage store inventory and more efficiently manage product sales and returns.

A retail business customer centric warehouse is established on the Teradata Scalable Data Warehouse as defined by the Retail Logical Data Model described below. The application server supports retail analytic and operational applications such as Teradata Corporation s Teradata Solutions for Retail suite of retail business applications illustrated in .

The Teradata Solutions for Retail suite of retail business applications comprises several analytic applications built on a common data model leveraging a single source of data across all departments. The application suite includes the following application members Assortment Analysis Promotion Analysis Customer Analysis Store Analysis and E Commerce Analysis .

Assortment Analysis . The Assortment Analysis application is the foundation for basic sales and inventory reporting monitoring of sales trends by geography product and product trait. Beyond basic reporting functionality includes assortment planning and allocation analysis additional view of seasonal planning and additional detail on vendor performance measures. Also provides advanced analysis of assortment based on customer segment preferences using analysis of market basket and customer data.

Assortment Analysis integrates planning processes that occur before and during the selling season resulting in tailored merchandise assortment pricing and promotional support for unique markets and individual stores. The Assortment Management Analysis provides a diverse set of business analyses and reports views that will assist a merchant in arriving at better informed decisions regarding the management of his her product assortments to the store level.

Promotion Analysis . The Promotional Analysis application enables a retailer to analyze Lift by product brand or vendor inventory effectiveness Seasonal Regional Demand Patterns and Price Point Analysis.

The Promotion Analysis application is designed to more effectively analyze plan and target your promotions based on item store and customer data. By allowing for key sales and inventory performance measurements such as sell thru ending on hand stock and sales to be combined and presented over various dimensional perspectives one is provided with more accurate information regarding a promotion s effectiveness.

Customer Analysis . The Customer Analysis application provides critical insight into a retailer s customer base via ranking deciling RFM analysis demographic segmentation and defining purchase behavior.

The Customer Analysis application consists of a Customer Purchase Analysis application module that provides critical insight into customer base via ranking deciling RFM analysis demographic segmentation and defining purchase behavior. The Customer Purchase Analysis application module provides analysis and information concerning targeted customer promotions optimum promotional item assortment promotional effectiveness and enhanced cross merchandising strategies.

Store Analysis . The Store Analysis application provides analysis of store sales labor controllable expenses and variances.

The Store Analysis application consists of a Store Operations Analysis application module that provides analysis of store sales labor controllable expenses and variances so as to provide a deeper understanding of costs resources traffic and productivity. The Store Operations Analysis application module provides analysis and information concerning location sales labor allocation policies variable cost control and resource time allocation.

E Commerce Analysis . The E Commerce Analysis application provides analysis of customer interactions ad effectiveness preference profiling and cross channel effectiveness.

The E Commerce Analysis application provides a better understanding of the customer and their interaction with the e Storefront including customer purchase promotion and media analysis. The E Commerce Analysis application consists of three application modules 

A logical data model is a graphical representation of the way data is organized in a data warehouse environment. The logical data model specifically defines which individual data elements can be stored and how they relate to one another to provide a model of the business information. The data model ultimately defines which business questions can be answered from the data warehouse and thus determines the business value of the entire decision support system.

A properly designed LDM for a retail industry provides a foundation for more effective sales marketing and operations management and supports the customer relationship management CRM requirements related to identifying acquiring retaining and growing valuable customers. A logical data model for the retail industry reflects the operating principles and policies of the retail industry and provides the underlying structure for the data imported into the data warehouse

A logical data model provides an architecture for the information that will be included in a data warehouse. The database provides the physical realization of that architecture in a form that can be efficiently maintained and used. There may well be some differences between the logical data model and the final database design. The database may include some tables summary tables etc. or columns that have no direct correlation in the logical data model. Elements in the logical model may be grouped differently in the physical database.

A logical data model is organized by Subject Areas each comprised of numerous Entities Attributes and Relationships. The data model hierarchy includes one or more Subject Areas. Each Subject Area includes one or more Entities or Tables each having Attributes and Relationships. Each Attribute describes a fact about an Entity. Relationships between two or more Entities are further defined by Cardinality. The Relationships define which entities are connected to other entities and the cardinality of the relationships. Each of these elements will be described in greater detail below.

A subject area is a subset of objects taken from the universe of data objects for a particular line of business or industry that focus on a particular Business Process. Typically a subject area is created to help manage large data architectures that may encompass multiple business processes or business subjects. This is the highest level data concept within a conceptual entity relationship E R model. Working with subject areas is especially useful when designing and maintaining a large or complex data model. Dividing the enterprise into several distinct subject areas allows different groups within an organization to concentrate on the processes and functions pertinent to their business area.

An Entity represents a person place thing concept or event e.g. PARTY ACCOUNT INVOICE etc. . It represents something for which the business has the means and the will to collect and store data. An Entity must have distinguishable occurrences e.g. one must be able to uniquely identify each occurrence of an entity with a primary key e.g. Party Identifier Account Identifier Invoice Number etc. . An Entity is typically named with a unique singular noun or noun phrase e.g. PARTY BILLING STATEMENT etc. that describes one occurrence of the Entity and cannot be used for any other Entity. It should be exclusive of every other Entity in the database. An Entity cannot appear more than once in the conceptual entity relationship E R model. Each Entity may have relationships to other Entities residing in its own Subject Area or in other Subject Areas.

An Attribute is a data fact about an Entity or Relationship. It is a logical not physical construct. It is data in its atomic form. In other words it is the lowest level of information that still has business meaning without further decomposition. An example would be FIRST NAME or LAST NAME. An example of an invalid attribute would be PERSON NAME if it includes both the first and last names as this could be further decomposed into the separate definable first name last name data facts.

A Relationship is an association that links occurrences of one or more Entities. A Relationship must connect at least one Entity. If only one Entity is connected the Relationship is said to be Recursive. A Relationship is described by a noun or passive verb or verb phase that describes the action taken in the Relationship. A Relationship represent a static state of being between the occurrences of the Entities it connects. Relationships are not intended to represent processes or data flows. They cannot be linked to another Relationships. They may optionally represent future present and or past relatedness. The time frame must be explicitly defined in the data definition. Relationships may contain attributes. In a normalized model a Relationship containing Attributes will result in the creation of an Entity.

In order for a data model to be considered accurate it must contain both the maximum and minimum number of Entity occurrences expected. This is controlled by rules of cardinality which describes a relationship between two Entities based on how many occurrences of one Entity type may exist relative to the occurrence of the other Entity. Typically it is a ratio commonly depicted as a one to one 1 1 one to many 1 N and many to many M N relationship.

The maximum cardinality may be an infinite number or a fixed number but never zero. The minimum cardinality may be zero or some other positive number but it must be less than or equal to the maximum cardinality for the same relationship.

The logical data model for the E Business will now be described in more detail. The logical data model uses IDEF1X modeling conventions as shown in Table 1.

The Retail Logical Data Model rLDM is a large data model composed of a large number of tables. To effectively view and understand the data model the data tables have been logically organized into smaller groups called subject areas. Each subject area is comprised of a set of tables that contain information relevant to a particular entity. In addition the subject areas address particular business questions.

The Retail Logical Data Model is presented in the Conceptual View illustrated in . This view provides an overall high level understanding of the major entities and how they relate to each other. The Conceptual View was derived directly from the Retail Logical Data Model by selecting the most important entities from every subject area being sure that at least one entity from each subject area was selected and distilling the relationships among the selected entities while still maintaining the general nature of the way the entities relate to each other. During this process some intervening entities were abstracted into relationships. Many to many relationships were used where appropriate. The result is a simple easy to understand diagram that conveys the general content of the underlying logical data model.

Subject Area Views such as the QUALITY FEEDBACK subject area view illustrated in show small but highly detailed subsets of the model. Subject areas are collections of entities about business information objects or concepts that are closely related. The sum total of all subject areas equals the rLDM. For ease of use and understanding the Retail Logical Data Model has been divided into the following fifty six 56 subject areas titled 

The ADDRESS subject area represented by ADDRESS entity in the conceptual model of is used to capture all ADDRESS information that can be used for communications and physical addressing. Each unique occurrence of an ADDRESS may represent a physical MAILING ADDRESS e.g. street post office box a TELEPHONE ADDRESS e.g. voice or fax number or an ELECTRONIC ADDRESS e.g. e mail ftp or URL . Internet Protocol addresses are modeled separately in the entity IP ADDRESS within the WEB VISIT subject area.

The AGREEMENT subject area represented by AGREEMENT entity defines the specific terms and conditions between Parties. This subject area is used to track the specific agreements made relating to pricing as well as the specific terms and conditions associated with the sale payment and or delivery of products and or services between Parties in a quantitative manner so that analysis can be better performed to determine performance compliancy.

The ASSOCIATE LABOR subject area represented by ASSOCIATE LABOR entity in defines key business characteristics of an ASSOCIATE sometimes referred to as an employee who as an individual is part of the internal organization of the Enterprise. The key emphasis of the ASSOCIATE LABOR subject area is to track the critical information necessary to understand analyze and make better decisions regarding an Enterprise s labor costs and related labor expenses as they relate to each ASSOCIATE.

This section models both the forecasted or planned labor for each location stores distribution and call centers etc. in cost amounts and hours including overtime and the schedule of work for each Associate. A history of expenses related to associate labor and benefits is provided to aid in comparison analyses.

The CATALOG subject area represented by entity in is used to describe the content and usage of catalogs by an enterprise. The intent is to accommodate the typical printed catalog that is mass mailed to a targeted segmented group of potential customers. This Subject Area allows tracking of the success of a specific catalog or mailing since it is related to the SALES INTERNAL Subject Area indicating which sales were made from which catalog mailed to what target group.

Although targeted mainly at enterprises doing conventional catalog mail order business this section can be adapted for usage to also describe promotional flyers and other printed offerings if required.

The pages of a Catalog may be either printed for mailing and physical distribution or may be virtual pages placed on a web site. Additional features are available on web sites such as keyword search and automated orders. This type of customer interaction is captured in the WEB VISIT subject area.

The DEMOGRAPHICS subject area is represented in by DEMOGRAPHIC entity MARKET GROUP entity and MARKET SEGMENT entity . The DEMOGRAPHICS subject area contains information obtained purchased leased from external sources. Its primary usage is for the creation of SEGMENTs groups of PARTYs sharing common characteristics for marketing purposes.

MARKET GROUPs record third party aggregated sales data such as that purchased from Nielson or IRI for example. Information about these groups e.g. supermarket category discounter drug store etc. is typically purchased and often used by the Enterprise to measure its performance in the marketplace. Market Groups may also be associated with various DEMOGRAPHICs.

MARKET SEGMENTs are groups of PARTYs targeted by the Enterprise for marketing and or analysis and may be formed via algorithmic modeling or forecasting See MODEL SCORE FORECAST Subject Area . These segments are also related to DEMOGRAPHICs to enhance and support analysis and targeted sales campaigns See PROMOTION Subject Area .

The twenty three Financial Management FM subject areas FM.AP AR PA INVOICE FM.AP INVOICE FM.AP PAYMENT FM.AR INVOICE FM.AR PAYMENT AND COLLECTION FM.FA FIXED ASSET FM.GL.ASSET ACCOUNT FM.GL.EQUITY ACCOUNT FM.GL.EXPENSE ACCOUNT FM.GL.GENERAL LEDGER ACCOUNT FM.GL.CHART OF ACCOUNT BALANCE FM.GL.PRODUCT SEGMENT FM.GL.PROJECT SEGMENT FM.GL.SUB ACCOUNT FM.GL.JOURNAL ENTRY FM.GL.LIABILITY ACCOUNT FM.GL.REVENUE ACCOUNT FM.PA PROJECT FM.PA PROJECT RESOURCE FM.PARTY FM.PO PROCUREMENT FM.PO PROCUREMENT RECEIPT FM.PO PROCUREMENT RETURN are represented by a single entity FINANCIAL MANAGEMENT entity in .

The FM.AP AR PA INVOICE subject area contains information related to various types of billing documents or Invoices encountered by a business. Invoices are presented to a bill to party as a request for payment for goods sold or services rendered. This subject area links the Invoice detail back to the originating business transactions for verification and analytical purposes.

The FM.AP INVOICE subject area describes the details around amounts owed to a supplier for goods and services purchased. The Accounts Payable subledger holds details for these transactions including reimbursable expenses employee expense reports and recurring expenses.

The FM.AP PAYMENT subject area holds payment details for AP Invoices. Payments are the partial or complete discharge of the invoice obligation typically by its settlement in the form of a transfer of funds. Payments may be applied against obligations represented by one or more Invoices.

The FM.AR INVOICE subject area describes the details around amounts billed to customers for goods and services sold. Summary Accounts Receivable amounts as well as sales and revenue amounts from the AR subledger are recorded to the company s General Ledger.

The FM.AR PAYMENT AND COLLECTION subject area describes the details concerning the process of converting Accounts Receivable to Cash. Payments may be received for AR Invoices as well as interest earned rents receivable or periodic products and services provided. Collection activity includes any action a company takes to solicit settlement of AR obligations.

The FM.FA FIXED ASSET subject area holds information needed to track the addition and disposal of the tangible property of the business. This subject area also holds information needed to calculate and record the depreciation of an asset including term depreciation methods accounting cycle costs and residual values.

The FM.GL.ASSET ACCOUNT subject area contains information concerning enterprise assets. Assets are tangible or intangible property owned by a business having monetary value usually at cost or fair market value . These range from cash and investments to real estate such as land other tangible property such as timber or enforceable claims against others etc. For accounting purposes these are usually classified under three groups Current Assets Fixed Assets and Other Assets.

The FM.GL.CHART OF ACCOUNT BALANCE subject area contains information concerning an enterprise s Chart of Account Balances. GL Chart of Accounts Balances are actual amounts experienced through some point in time or budgeted amounts projected for a financial plan. Companies maintain only one record of actual amounts but may define multiple financial plans and maintain balances for each financial plan instance.

The FM.GL.EQUITY ACCOUNT subject area contains information concerning equity in an enterprise. Equity is the shareholders stake in any company business. From a financial accounting standpoint Equity is total assets less total liabilities also referred to as Net Worth.

The FM.GL.EXPENSE ACCOUNT subject area contains information concerning enterprise expenses. Expense is the amount spent by a company in running the business and producing goods or services. Some of the typical expense accounts are OPERATING EXPENSE ACCOUNT INTEREST EXPENSE ACCOUNT etc.

The FM.GL.GENERAL LEDGER ACCOUNT subject area contains information concerning an enterprise s General Ledger. The General Ledger is a collection of all accounts used by a business. It is the accounting transaction record maintained either manually or using computer software of all the balance sheet and income statement balances of a company or business. Previously as the name suggests the General Ledger was a collection of books that was used to physically record accounting transactions. Today these transactions are generally recorded and stored by using computer software.

There are five main types of GENERAL LEDGER GL ACCOUNTs. They are ASSET ACCOUNT LIABILITY ACCOUNT EXPENSE ACCOUNT REVENUE ACCOUNT and EQUITY ACCOUNT. Each account in turn may have sub ledgers. For example ASSET ACCOUNT consists of a group of accounts such as Fixed Asset Account Current Asset Account etc. The GL ACCOUNTs are shared by various internal organizations within a business and therefore are associated with other GL Segments in segment groups to track and report financial information.

The FM.GL.JOURNAL ENTRY subject area contains information concerning an enterprise s Journal Entries. Journal Entries record the monetary value of business transactions into GL Accounts as debits or credits. Journal Entries usually include supporting information referencing the transaction events or items affected such as a vendor invoice customer invoice or inventory receipt.

The FM.GL.LIABILITY ACCOUNT subject area contains information concerning liabilities of an enterprise. The liabilities of a company are amounts owed to other parties or organizations representing loans expenses or any other form of a legally enforceable claim on the company s assets excluding owner s equity that calls for the transfer of assets at a determined future date.

The FM.GL.PRODUCT SEGMENT subject area is associated with GL Accounts in segment groups to track and report financial product information.

The FM.GL.PROJECT SEGMENT subject area is associated with GL Accounts in segment groups to track and report financial project information. The GL PROJECT SEGMENT is used to track details of any type of business project activity.

The FM.GL.REVENUE ACCOUNT subject area contains information concerning enterprise revenue. Revenue sometimes referred to as income refers to the amount of money earned by a company.

The FM.GL.SUB ACCOUNT subject area is associated with GL Accounts in segment groups to track and report financial transactions for a company.

The FM.PA PROJECT subject area provides more granularity to project financial information than a General Ledger. Project Accounting PA focuses on maintaining control over revenues costs resources and assets directly associated with a project.

A project can be any set of related business activities for which a company wishes to track financial information. Project expenses may include associates time and expense reports vendor expenses and capital expenses. Project revenue is generated when project expenses are billable to a customer. PA generates the detailed information needed to create a customer invoice but the invoice is actually processed through the billing function of Accounts Receivable.

Within PA budgets by project resource task etc. may be maintained separately from the General Ledger budget. PA supports project reporting by task resource vendor and customer for different currencies and time periods. In some cases PA tracks projects by specific project reporting periods which may be separate from a company s accounting period.

The FM.PA PROJECT RESOURCE subject area tracks items and individuals assigned to a scheduled task in a project plan. The cost and billable rates associated with these Items and Individuals will be used in the Project Financial Plan.

The FM.PARTY subject area defines the people and organizations of interest to the enterprise as they pertain to Financial Management and its particular business requirements.

The FM.PO PROCUREMENT subject area represents information related to the process of acquiring the goods materials parts supplies equipment required to run the business. PO Procurement as an overall business function covers the process from requisition to order to tracking receipts and returns.

The FM.PO PROCUREMENT RECEIPT subject area tracks the actual receipt of items ordered for comparison to the Purchase Order and related AP Invoice. It also allows for analysis as to whether the original due dates for the receipt were actually met.

The FM.PO PROCUREMENT RETURN subject area holds information about transactions where the receiving PARTY sends back to the vendor or supplier Item s that were previously received.

The INVENTORY subject areas represented in the conceptual model of by INVENTORY ITEM entity and INVENTORY TRANSACTION entity details the movement of inventory between locations facilities as well as tracking physical and calculated stock levels and value and provides for controlling in stock and replenishment levels. Inventory is a company s merchandise raw materials and finished and unfinished products which have not yet been sold. Inventory can be individually valued by several different means including cost or current market value and collectively by FIFO First in first out LIFO Last in first out or other techniques.

The INVENTORY EXTERNAL subject area details the adjustments to Inventory where at least one EXTERNAL Location is involved. Control of Inventory is transferred to or from a Third Party and Inventory is adjusted accordingly.

The INVENTORY INTERNAL subject area details the movement of inventory between and the adjustments to inventory where only INTERNAL locations e.g. Stores DCs Warehouses are involved. Control of inventory is not transferred to or from a Third Party.

The INVOICE subject area represented by INVOICE entity holds information concerning INVOICEs which represent a request for payment by a third party vendor supplier to the enterprise or by the enterprise to a customer for goods provided or services rendered.

The ITEM DEFINITION subject area represented by ITEM entity in details all the ITEMs of interest to an enterprise. An ITEM is the lowest level for which inventory and sales records are retained within the retail store. It can be analogous to a SKU Stock Keeping Unit .

The ITEM PRICING subject area represented by ITEM PRICING entity supports Item Pricing and Costing. The inclusion of effective dates allows for historical pricing and costing information to be captured. Future pricing information can also be captured.

The LOCATION subject area represented by entities and LOCATION and CHANNEL respectively in defines a physical or virtual site or facility which is owned or leased by a retailer to support the sale of goods distribution and storage. A LOCATION may be a WEB STORE KIOSK CALL CENTER brickand mortar STORE PHARMACY DISTRIBUTION CENTER etc.

 1 CUSTOMER RELATIONSHIP MANAGEMENT CRM . By using Customer Scoring the Enterprise can tag their customers in a multitude of different ways to highlight their best customers for differentiated treatment. Example 

Customers can be scored for profitability frequency of purchases propensity to buy etc. Vendors and suppliers may similarly be scored on accuracy of orders delivery time etc.

 2 DEMAND AND SUPPLY CHAIN MANAGEMENT. The various forecasting entities can be populated by the enterprise using their own statistical methods or by using the output of 3rd party applications. Since the model contains internally generated Sales and Order Forecasts as well as Vendor generated Forecasts these forecasts can be compared for possible deltas and exception reporting. And 

 3 KNOWLEDGE MANAGEMENT DATA MINING. Supports information regarding the Analytical Models used to predict cluster or classify information that is typically used in Data Mining and Knowledge Discovery. Example A Model that describes the propensity of a customer to buy a given item etc.

The MODEL SCORE FORECAST subject area is represented in the conceptual model of by ANALYTICAL MODEL entity FORECAST entity and PARTY SCORE entity .

This MULTMEDIA subject area represented by entity in models the various multimedia elements that the enterprise uses to construct marketing collateral

The PARTY subject area defines the people and organizations of interest to an enterprise. This subject area is represented in the conceptual model by PARTY entity HOUSEHOLD entity INDIVIDUAL entity ORGANIZATION entity and PERSONA entity .

The PAYMENT ACCOUNT subject area represented by PAYMENT ACCOUNT entity and LOYALTY ACCOUNT entity in describes the mechanism by which goods are be paid for other than cash . Three main areas are described conventional typically external payment accounts such as credit cards checking accounts in house credit cards etc. loyalty accounts comprising in house programs designed to encourage customers to make purchases by offering rewards and internal accounts such as Gift Cards Gift Certificates etc.

The PHARMACY subject area represents information about the dispensing and payment for prescription drugs from the perspective of a Retail Pharmacy. This subject is represented in by PHARMACY entity and PRESCRIPTION entity .

The PLANOGRAM subject area represented by entity in models information concerning where items are located in a store as well as relationships to other items in their proximity.

The POINT OF SALE REGISTER subject area is represented by entity in . This subject are is used to capture all non sales related transactions involving P.O.S. Registers Associate sign in out or No Sale events etc. as well as specific sales transaction related keying sequence events quantity key price override . Application areas that can make use of this information could be for example cashier productivity loss prevention fraud detection or validation auditing applications that reconcile data warehouse content with actual P.O.S. logs.

Two main areas are covered Register events POS SALES taking place as part of a Sale quantity key price override etc. and those Register events POS NON SALES taking place independent of a Sales transaction settlement logging etc. .

The detail information in this Subject Area is critical in tracking and identifying exceptions suspicious or potentially fraudulent activities and for productivity and training plans and issues.

The PRIVACY subject area represents a PARTY s privacy settings for the collection and use of personal data. Privacy and the control of one s personal data is rapidly gaining attention in the media and political arena. Consumers are becoming more privacy assertive and with the rapid adoption of online privacy for the Web offline privacy expectations are rising. This subject is represented in by PRIVACY entity .

Privacy data fields are those which pertain to personal data such as age gender income marital status or purchase habits reveal identity such as name address phone number social security number bank account number or special categories of data such as racial or ethnic origin religious beliefs etc.

The PROMOTION subject area models the key information necessary to support the tracking and analysis of an enterprise s marketing efforts. It allows the determination of promotional effectiveness by tracking market segments or individuals targeted with promotional offers and the eventual response to the promotion in the form of Sales lift or Coupon redemption. This area also captures the promotion budget actual promotion expenses and expected or planned sales revenue associated with a given promotion. The PROMOTION subject are is represented by entity in .

The QUALITY FEEDBACK subject area represented by QUALITY FEEDBACK entity and QUALITY GROUP SURVEY entity provides a view of all aspects of quality feedback tracking present in the Retail Logical Data Model. The primary reason for this subject area and content is to capture feedback received by an enterprise typically regarding the quality of its products and services in an effort to analyze and improve the quality of the retailer s products and services.

The RFID SERIALIZED ITEM TRACKING subject area provides a view of all aspects of Serialized Item tracking present in the model supporting the use of RFID Radio Frequency Identification Technology in the retail industry.

The Subject Area represented by entities and in tracks the three different types of movement of Serialized Items movement to and from suppliers movement between internal locations and movement to and from customers.

The SALES EXTERNAL subject area represented by entity in details sales transactions reported by a third party possibly from a Trading Partner or Purchased leased information from a syndication organization such as VNU IRI Nielsen etc. The enterprise is neither the selling nor purchasing party in any of these transactions.

Syndicated information is available at many different aggregation levels but is typically grouped by MARKET GROUP shown as entity in externally defined grouping of organizations that are part of the same sub industry such as supermarkets convenience stores drugstores mass merchandisers warehouse clubs etc.

The SALES INTERNAL subject area represented by entity in captures information concerning the sale and fulfillment of products and services offered by an enterprise. This subject area details what was sold to whom who paid for it how paid for and when how and by whom it was provided to the customer.

Sales transactions are grouped together at a VISIT level shown as entity in defining all the sales related transactions made by a customer during a predefined time period at a given location.

The SHIPPING ORDER subject area represented by FREIGHT BILL entity in details the content of a SHIPMENT the PIECEs or Handling Units that make up a Shipment the actual Items contained therein the different PARTIES involved the TRANSPORTATION SERVICES requested and any potential CLAIMs made against selected Shipment Pieces.

The SHIPPING PLAN Subject Area supports two distinctly different Transportation and Shipping Planning options. The first Planning area allows for the advance route rate carrier service and cost planning of every single or select Shipment. The second Planning area covers a global goal setting capability.

The SHIPPING REGULATION subject area represented by CUSTOMS REQUIREMENT entity specifies the rules and regulations of transporting goods over borders. As part of the critical information that this subject area supports it specifically defines the official information required to be presented to the Controlling Authority.

The SHIPPING TRANSPORT subject area represented by ASSET entity and LEG EQUIPMENT entity details the actual transporting of a Shipment including all tracking information transport mode s used legs and routes traveled and the Equipment utilized.

The TIME PERIOD subject area not shown can be used to map country specific holidays and events climate and sales seasons. Additionally it can be used to map into an enterprise s accounting and fiscal time periods.

The VENDOR SUPPLIER subject area represented by entity VENDOR entity in captures information concerning the type of ORGANIZATION that supplies ITEMs to a retail company. This area models purchase orders made to the VENDOR and receipt of items in return.

The WEB OPERATIONS subject area models web server activity and web visit interactions. The central entity within the WEB OPERATIONS subject area is the WEB SERVER entity identified by reference numeral in . This subject area also models other areas associated with web site services. Such information as server capacity software and activity provide for monitoring and maintenance are tracked.

All key aspects of an enterprise s web site s e.g. the content intent multimedia components advertising page navigation etc. are represented in the WEB SITE subject area. The WEB SITE subject area is represented in the conceptual model of by WEB SITE entity and WEB STORE entity .

The WEB VISIT subject area is represented by REFERRAL entity and WEB PAGE VIEW entity in . This subject area stores information about web visitors visitor web activity and browsing history and referrals.

More detailed information concerning the above described subject areas is available in Provisional Application Serial Number 61 003 191 entitled TERADATA RETAIL LOGICAL DATA MODEL 5.01 filed on Nov. 14 2007.

The QUALITY FEEDBACK subject area illustrated in provides a view of all aspects of quality feedback tracking present in the Retail Logical Data Model. As stated above the primary reason for creating this subject area and content is to capture feedback received by the enterprise typically regarding the quality of it products and services in an effort to analyze and improve the quality of the retailer s products and services.

Feedback can be planned such as by contracting a third party to contact individuals and solicit feedback or the enterprise performing periodic inspections and mystery shopper activities conducted by the enterprise. Feedback can also be spontaneous such as when consumers contact the enterprise. The type of feedback can be free format such as a customer call or email or structured as in surveys.

AGREEMENT Defines the specific AGREEMENT with a specific PARTY relative to prices terms and conditions. Examples include the terms between a Third PARTY and an enterprise as it relates to the pricing of products and services.

ASSOCIATE An individual who works under the direct control of the enterprise such as Employees Contractors Temporary Workers etc.

COMPENSATORY OFFER An Offer or Offers made to a customer as compensation for feedback received. This could be to reward the customer for taking the time to provide feedback or to compensate the customer for a less than perfect experience with the enterprise.

CORPORATE FEEDBACK Feedback collected by the enterprise in a pro active manner customers or individuals contacted by the enterprise instead of the other way around . Examples include enterprise pro actively surveys customers and a mystery shopper activity associates pretending to be customers .

CUSTOMER FEEDBACK Feedback received directly from a customer where the customer or individual contacted the enterprise. Feedback can be regarding an existing order agreement shipment etc. Examples include customer informs enterprise that they can get better terms from a competitor customer called the enterprise after a visit or product order and customer completed a survey form available in an enterprise location. If needed individual subtype entities can be created for each type of business transaction feedback or contact that is collected Agreements Sales Orders Shipments etc. FEEDBACK CLASS This entity allows for a more specific classification of unstructured feedback received within a specific feedback type. Examples for products include product safety and product quality. Examples for services include service speed and service friendliness.

FEEDBACK DETAIL Specifies the particulars provided in an unstructured feedback event and also captures the Item or Associate involved if applicable .

FEEDBACK RESPONSE A brief description of the response type used to resolve a specific individual Customer Feedback. Examples of feedback types include provided a discount made available a promotional offer provided loyalty points credited customer account etc.

FEEDBACK TYPE An entity that can be used to organize or group unstructured feedback at a high level. Possible Examples product related service related staff related store related etc.

FEEDBACK A specific instance of feedback received by the enterprise typically regarding the quality of its products and services . The feedback can be planned such as contracting a third party to solicit feedback or periodic inspections and mystery shopper activities conducted by the enterprise. The feedback can also be spontaneous e.g. customers contacting the enterprise. The type of feedback can be free format or structured as in surveys .

ITEM An ITEM is the lowest level for which inventory and sales records are retained within the enterprise. A unique identifier for a grouping of one or more products or services and the corresponding price plan rate structure or unit charge that may marketed by the organization for the purpose of generating revenue. An item is what a customer purchases or subscribes to. Examples include Parker Elite fountain pen in silver Campbell s Hearty Tomato Soup 4 oz can Photo Printing Service Overnight Transportation Service Accessorial Service etc.

MARKET SEGMENT A grouping of PARTYs for marketing or analysis purposes. A MARKET SEGMENT can be re used can receive multiple offers serve as a control group or be used for customer product analysis purposes.

PARTY SEGMENT An associative entity that maps a PARTY into a MARKET SEGMENT. A PARTY can be a member of multiple MARKET SEGMENTs and vice versa.

PROMO OFFER A specific incentive made available to customers. Usually contains two parts a. condition s to be met and b. the reward for a. It is usually a narrowly defined marketing effort designed for a specific purpose. Can be part of a larger campaign. It has a specific start and end date. A promotion can contain multiple promo offers and ads. Example Buy a DELL Desk top Computer and get a free Epson printer.

QUALITY GROUP SURVEY Defines an activity that was conducted to solicit feedback from a group of customers regarding the products and services of the enterprise. Often done with a specifically targeted market segment. Example a Market Research Group is hired to obtain feedback from customers. This can be done via polling by phone in person focus groups etc. The results reported could be structured conforming to a survey format or free form unstructured .

QUALITY RESOLUTION Defines a Global Quality related action taken to resolve or address feedback received. This is a global action as opposed to the Feedback Response entity that captures the response to an individual Party s feedback instead. Examples improve associate training or improve item quality inspections.

QUALITY SURVEY A Specific pre defined formal controlled or structured set of questions where specific responses are solicited and responses typically are constrained to selecting one of several choices presented.

SALES TRANSACTION A single CUSTOMER interaction or transaction involving the potential or actual Sale or Return of one or more ITEMs. It is very open ended and can be used to describe any aggregation of ITEMS made by a potential customer. For example this entity can represent Web Shopping Cart Web Wish list Wedding Registry List Store P.O.S. Sale Store Layaway Purchase Catalog Order etc. It does not always represent an ACTUAL sale.

SURVEY FEEDBACK Feedback received in a formal controlled or structured format where specific responses are solicited and responses typically are constrained to selecting one of several choices presented.

TRAIT GROUP A cluster of related TRAITs. Examples for Item Size could be a TRAIT GROUP with each of the dimensions height width depth being a separate TRAIT for Service Quality associate rating accuracy rating expense rating etc. for RFID Trait Scan handling environmental etc.

TRAIT VALUE The actual value describing the specific TRAIT of a specific object. Examples for Item Traits color blue suitable age rating 12 years and older for Ser Item Trait expiration date 4 2009 for RFID Trait Scans ambient temperature high 40 degrees Celsius and for Quality Feedback Detail service slow associate very professional.

TRAIT Describes a trait of an object service experience etc. This structure is typically used where objects can have a wide number of dynamic descriptive attributes and or new ones are continuously encountered. In this case a generic structure as defined by the Trait structure may be more appropriate than discrete attributes. Example for Item it could be color height suitable age rating etc. For Ser Item Trait expiration date batch number quality inspector id etc. For RFID Trait Scans ambient temperature shock pressure etc. for Quality Feedback Detail service speed associate friendliness etc. In environments where objects are homogenous discrete attributes would be recommended e.g. in the case of a dedicated Bookseller.

UNSTRUCTURED FEEDBACK The Unstructured Feedback structure captures non formal feedback that is typically difficult to encode as opposed to formal interactions such as orders payments etc. . This type of feedback is typically free form phone conversations letters etc. . Attributes are provided to enable summary representative standard codes to describe the essence of the contact to make analysis possible.

A listing of all the attributes included within the entities shown in together with a brief description of each attribute is provided in Appendix A.

The Figures and description of the invention provided above reveal a flexible relational data model for a retail enterprise data warehouse solution. The data model design enables the capturing of quality feedback information for products and services sold by the retail enterprise. Maintaining this information in a data warehouse provides the retail enterprise with the ability to analyze and improve supply chain operations to better manage store inventory and more efficiently manage product sales and returns.

The foregoing description of the preferred embodiment of the invention has been presented for the purposes of illustration and description. It is not intended to be exhaustive or to limit the invention to the precise form disclosed. Many modifications and variations are possible in light of the above teaching. It is intended that the scope of the invention be limited not by this detailed description but rather by the claims appended hereto.

