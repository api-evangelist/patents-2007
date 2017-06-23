---

title: Integrated retailer process
abstract: In accordance with one embodiment of the invention, a set of API's for integrated retailers to perform standard order fulfillment operations to fulfill and return products on behalf of their clients is described. A common catalog on a software platform is intended be a flexible common hub around which many different commerce models can be implemented. Integrated retailer is one such model on which e-commerce occurs. Integrated retailers are permitted to sell product from the common catalog with another company providing back-end fulfillment. The common catalog infrastructure's pre-existing XML catalog export facility provides product information to the retailer. The Retail Web Service (RWS) provides the fulfillment functions as a REST-style web service.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08200537&OS=08200537&RS=08200537
owner: Digital River, Inc.
number: 08200537
owner_city: Minnetonka
owner_country: US
publication_date: 20070402
---
This application claims the benefit of U.S. Provisional Application No. 60 788 413 filed 31 Mar. 2006 entitled Integrated Retailer Process which is incorporated herein by reference

The present invention relates to order fulfillment operations to fulfill and return products on behalf of clients on the internet. More particularly the present invention relates to a system and related tools for providing an integrated retailer process.

The Internet is a set of computer networks possibly dissimilar joined together by means of gateways that handle data transfer and the conversion of messages from the sending network to the protocols used by the receiving network with packets if necessary . When capitalized the term Internet refers to the collection of networks and gateways that use the TCP IP suite of protocols.

The Internet has become a cultural fixture as a source of both information and entertainment. Many businesses are creating Internet sites as an integral part of their marketing efforts informing consumers of the products or services offered by the business or providing other information seeking to engender brand loyalty. Many federal state and local government agencies are also employing Internet sites for informational purposes particularly agencies which must interact with virtually all segments of society such as the Internal Revenue Service and secretaries of state. Providing informational guides and or searchable databases of online public records may reduce operating costs. Further the Internet is becoming increasingly popular as a medium for commercial transactions.

Currently the most commonly employed method of transferring data over the Internet is to employ the World Wide Web environment also called simply the web . Other Internet resources exist for transferring information such as File Transfer Protocol FTP and Gopher but have not achieved the popularity of the Web. In the Web environment servers and clients effect data transactions using the Hypertext Transfer Protocol HTTP a known protocol for handling the transfer of various data files e.g. text still graphic images audio motion video etc. . The information in various data files is formatted for presentation to a user by a standard page description language the Hypertext Markup Language HTML . In addition to basic presentation formatting HTML allows developers to specify links to other Web resources identified by a Uniform Resource Locator URL . A URL is a special syntax identifier defining a communications path to specific information. Each logical block of information accessible to a client called a page or a Web page is identified by a URL. The URL provides a universal consistent method for finding and accessing this information not necessarily for the user but mostly for the user s Web browser . A browser is a program capable of submitting a request for information identified by an identifier such as for example a URL. A user may enter a domain name through a graphical user interface GUI for the browser to access a source of content. The domain name is automatically converted to the Internet Protocol IP address by a domain name system DNS which is a service that translates the symbolic name entered by the user into an IP address by looking up the domain name in a database.

The Internet also is widely used to transfer applications to users using browsers. With respect to commerce on the Web individual consumers and businesses use the Web to purchase various goods and services. In offering goods and services some companies offer goods and services solely on the Web while others use the Web to extend their reach.

With respect to these commercial activities and others businesses and other content providers go through a highly manual process to set up mechanisms to facilitate business to business commerce. For example in setting up customized catalogs for use between businesses the items in the catalog are currently set up through telephonic communications. A customized catalog is also referred to as a catalog . Manual configuration of the catalog as well as various terms and operating conditions also are discussed telephonically. After agreement is reached then the catalog is configured and placed on a Web site. Other times the catalog may be set up through face to face meetings between representatives of the different businesses. Such a mechanism takes time and manpower.

Therefore it would be advantageous to have an improved method and apparatus for setting up a business to business commerce relationship. The present invention provides a solution to these needs and other problems and offers other advantages over the prior art.

The present invention is related to a software system that solves the above mentioned problems. In accordance with one embodiment of the invention a set of application programming interfaces APIs for integrated retailers to perform standard order fulfillment operations to fulfill and return products on behalf of their clients is described. A common catalog on a software platform is intended to be a flexible common hub around which many different commerce models can be implemented. Integrated retailer is one such model on which e commerce occurs. Integrated retailers are permitted to sell product from the common catalog with another company providing back end fulfillment. The common catalog infrastructure s pre existing XML catalog export facility provides product information to the retailer. The Retail Web Service RWS provides the fulfillment functions as a representational state transfer REST style web service. The RWS implementation is a relatively thin layer on top a set of core functionality shared with other common catalog models. This gives RWS access to the evolving set of tools for common catalog such as catalog filtering. The REST architecture implements all services as HTTP GET and POST operations on URLs that represent business resources Orders Fulfillment Units and Returns etc. As such this architecture enables use of standard HTTP protocol features such as cache control and redirection to achieve great scalability and flexibility.

Additional advantages and features of the invention will be set forth in part in the description which follows and in part will become apparent to those skilled in the art upon examination of the following or may be learned by practice of the invention.

Before moving into the detailed description a few commonly used terms need to be defined as shown in Table 1 below.

In accordance with one embodiment of the invention a set of API s for integrated retailers to perform standard order fulfillment operations to fulfill and return products on behalf of their clients is described. A common catalog on a software platform is intended be a flexible common hub around which many different commerce models can be implemented. Integrated retailer is one such model on which e commerce occurs. Integrated retailers are permitted to sell product from the common catalog with another company providing back end fulfillment. The common catalog infrastructure s pre existing XML catalog export facility provides product information to the retailer. The Retail Web Service RWS provides the fulfillment functions as a REST style web service. Representational State Transfer REST is an architectural style for distributed hypermedia systems like the web. The RWS implementation is a relatively thin layer on top a set of core functionality shared with other common catalog models. This gives RWS access to the evolving set of tools for common catalog such as catalog filtering. The REST architecture implements all services as HTTP GET and POST operations on URLs that represent business resources Orders Fulfillment Units and Returns etc. As such this architecture enables use of standard HTTP protocol features such as cache control and redirection to achieve great scalability and flexibility.

A set of API s for integrated retailers perform standard order fulfillment operations to fulfill and return products on behalf of their clients. Integrated retailers will integrate with an ecommerce platform so that fulfillment requests and transactions are processed on the platform. The platform delegates the fulfillment request for download URL and digital right to the originating platform. A Dealer order may contain fulfillment requests to be delegated to more than one platform. Products will have a grace period for which they may still be ordered after being removed from an integrated retailers catalog. Integrated retailers will have access to products with double byte characters. Local taxation requirements are also fulfilled as are return processing. Reissue of product keys and security of each dealer catalog is also performed. Integration retailer process also supports external contract between an integrated retailer and a publisher where the integrated retailer pays the publisher.

A REST full web service involves defining the service in terms of resources referenced by URIs operated on by standard HTTP operations GET and POST. In addition all GET operations will be safe and will be used whenever the operation is safe. POST will be used for all operations that change server state. As an example the following would be a REST compliant operation.

Reliable execution of fulfillment requests is guaranteed as follows. Standard HTTP security will be used SSL Basic Auth to authenticate client.

Several elements in the XML documents have the uniform resource identifier URI attribute. This attribute s value is a URI which identifies the resource represented by that element. Other XML documents will refer to that resource using that URI referring attribute will have a name like resource typeUri.

The format of the value is completely up to the creator of the resource. The dealer might send URIs consisting only of its internal order id. The only requirement is that it uniquely identifies the order and it is a maximum of 64 characters in length. A nested element s URI can be relative to an outer element s URI. The dealer created root element URIs may be valid non relative HTTP URIs. This is so that a user may for example send the dealer order status change notifications by posting to the order s URI.

Operations will follow the HTTP protocol s status code and message conventions. The status code and message will also be duplicated in the response XML for the benefit of client implementations that choose to not access the response headers.

All API s will return a TransactionID uniquely identifying the request for tracking purposes. XPATH notation is used to describe the contents of the XML messages.

The purpose of this operation is to allow a dealer to validate product metadata price and availability upon insert of a ecommerce business product to the dealer shopping cart. The dealer should not allow a product to be added to the customers shopping cart if the product is no longer available for sale. Implementation of this API by the dealer is not required but encouraged.

Referring now to an overview of a product catalog business process is shown. The product catalog service provides a catalog feed of available products for sale by the IR. This feed is available in xml format and can be transferred via FTP to an FTP server location for the IR to consume. It will be understood that a client ecommerce system contains catalog browsing and shopping and a catalog repository. It will also be understood by one of ordinary skill in the art that a hosted ecommerce system contains a maintenance interface and catalog repository. A file processing application and an ICPP business process set aid the catalog feed to FTP server locations .

Failover may cause duplicate orders which must be resolved at some point after the requisition data is merged on operational data source ODS . Initially it may need to run on ODS like DigitalLocker.

There are two types of errors Transient and Permanent. Transient errors are a result of requests that cannot be fulfilled but should be resubmitted at a later time. Line Item pending digital rights or unable to communicate with third party system are examples of transient errors. Permanent errors are a result of requests that will never be fulfilled no matter how many times the request is submitted. An example of a permanent error would be a FulfillOrder request containing a retired product.

RWS uses a job management services provided by an integration services for example com.digitlariver.integration . The webservices exposed by RWS will be deployed on the servlet framework provided by integration services com.digitalriver.integration.servlet . Within this framework a single process will specify the single Job subclass that dispatches all RWS requests. A ProcessConfiguration will need to be created for each integrated dealer site.

A logging infrastructure will be created to log events occurring within the network channel API calls. A logging interface com.digitalriver.netchan.arch. NetworkChannelLogger has two implementations 

Security concerns itself with two fundamental questions are you who you say you are authentication are you allowed to do what you are trying to do authorization . RWS supports both authentication and authorization.

Also there is an additional security requirement which RWS supports namely each platform s Integrated Retailer will be represented in on the platform as a Site . This requirement will partially dictate the implementation of authentication and authorization within RWS.

Security also addresses the issue of confidentiality that is how can two parties exchange messages without being eavesdropped by a third party. RWS also support secure transport of messages.

RWS exposes a set of webservices. These webservices will be deployed within the Integration Services servlet framework. As of this writing the framework does not support an adequate authentication mechanism. With that said the framework is being enhanced to provide authentication services which RWS will then be able to leverage.

The Integration Services servlet framework will be providing authentication at a ProcessConfiguration level. Three types of authentication will be available UserBasedAuthenticator ProcessConfigurationBasedAuthenticator CustomAuthenticator. RWS uses a UserBasedAuthenticator method.

The UserBasedAuthenticator method makes use of the industry standard Basic Auth over HTTP. Basic Auth provides a username and password combination that can be used to authenticate a user.

RWS needs to scope a user to a specific site. In order to accommodate this requirement RWS will format the Basic Auth username as userlogin siteID where userlogin and siteID are the platform s notion of siteID and a user s userlogin .

Upon successful authentication the servlet framework will construct a user Principal . If authentication is not successful the framework will construct the appropriate error.

Once authenticated the Principal will be passed to the RWS Job . The RWS Job will be responsible for dispatching the incoming webservices request to the appropriate business logic. Before dispatching to the business logic authorization will be preformed. The RWS Job will be responsible for performing authorization of the provided Principal . Authorization will occur at the application level against a pre defined access control list ACL .

The ACL associates a role with a set of allowed operations. Each Principal will have an associated role. The following code fragment illustrates how to obtain the role from a Principal 

RWS also uses authorization to perform data scoping. A Principal must belong to a Platform Integrated Retailer site in order to issue requests on behalf of that dealer. Again this is enforced at the application layer.

RWS requires and supports that all communication occur over a secure transport layer. Secure Sockets Layer SSL is an industry standard mechanism for establishing a secure channel of communication between two systems. All communication between RWS and interested parties will take place over a SSL connection.

Establishing communication over SSL can be taxing on systems. One popular solution to this problem is to use specialized hardware when establishing a SSL connection. Integration retailer process deployment infrastructure utilizes this solution.

By agreeing to use hardware accelerated SSL the current infrastructure makes some requirements of RWS. For example in order to enforce that all communication is over a secure transport layer RWS will need to check a special HTTP header attribute SSL for a value of true .

The initial Metro implementation used Sun s Java web services developers toolkit JWSDP libraries to provide SOAP transport. The MetroDeliveryPartnerService dispatched all Metro requests to various command objects. Both the dispatcher and the command object interfaces were derived from Microsoft s web services description language WSDL and used data types defined therein e.g. ESD RESULT.

The RWS FulfillOrder operation requirements are met by a Metro DP ChargeCustomer operation followed by DP GetDownloadURL with the following differences.

Dealer specific information site etc. which Metro stores in the application attribute MetroConfig must be moved to a request attribute and populated based on the authenticated principal.

The ChargeCustomer command is refactored so that all of its payment information and behavior is encapsulated in a PaymentStrategy object which is passed as a parameter. There are two implementations MetroPaymentStrategy and RwsPaymentStrategy. MetroAdapter will create the MetroPaymentStrategy and pass the credit card info inside it. The RwsPaymentStrategy will encapsulate the RWS payment strategy where the purchase order payment method will be used.

The RequisitionFacade delegates requisition lineItem pricing calculations to the pricing module where prices are retrieved from a price list. The RequisitionFacade enhances to optionally populate line item prices from values retrieved from the integrated retailer. This configuration is retrieved from the ChanClientConfig class.

The ChargeCustomer command is refactored so that all of its session and transaction behavior is encapsulated in a Session Strategy object.

The CommonCatalog is a collection of all the products that can be sold by Integrated Retailers. By being implemented in a platform this model forbids products from being removed from the CommonCatalog they may only be retired. CommonProductInfo currently maps easily to a Platform Product Variation that has no child variations. The defaultCost is the cost of goods stored in the common catalogs COGS pricelist.

DealerFeedProductInfo is the information needed for a particular product that is included in a particular DealerFeed.

A new product filtering class is created verify and filter products that do not have a cost associated with them. This filtering class is associated with integrated retailer export feeds.

Logging functionality is added to the export feed for purposes of reporting errors as well as reporting what products have been filtered during the filtering process. The framework will use the same pattern as the bulk loader product import process.

A new pricing export handler is created to calculate integrated retailer product cost and populate pricing beans accordingly. This CostExportHandler is added as an extended attribute to the process configuration version as an additional export handler.

The following sections are intended to provide information on how to implement the service offerings of the Integrated Retailer. This system as designed strives to use the best and most standardized technologies in the industry in order to make the offering more universal in nature so that most clients will not have any major issues understanding the workings of the system and also so that there are no proprietary aspects that would make the implementations more difficult.

XML HTTPS and FTP are the main technical vehicles of standardization. Most IT departments will be familiar and comfortable with these technologies and would have implemented internal systems or subsystems in support of these universal web based technologies that have had a huge affect in the integration of the Internet and its services. XML is the primary data formatting protocol for all the APIs and acts as the mechanism that describes the data offered in each business process. HTTPS and FTP are the communication protocols real time and batch respectively that are employed by the APIs. HTTPS is used for the real time business processes used to create orders described in this integration document. FTP is used for the batched product catalog business process described in a separate document.

Once the product catalog has been imported into the client s eCommerce system the order create business process can be enabled. For this process the client will process the transaction performing payment authorization fraud check and other client specific transaction processing functions implemented via their eCommerce solution.

After these processes have run so that the client knows the customer and order are acceptable they will use the Order Create API to submit the order to ecommerce provider for fulfillment. For a digital product this fulfillment information consists of a ecommerce business hosted download URL that the client delivers to the customer who placed the order so they can download the product they purchased. Sometimes products may require a serial number or unlock code to be given to the customer in addition to the download URL in order to install the product properly. In these cases the Order Create business process returns this information for the client to display on the site to the customer at the time of purchase in the customer service interface that the customer has access to and also in the email notification that is sent out to the customer.

The business process uses XML and HTTPS since the APIs are real time in nature. Clients should consider coding in a timing feature so that in the very rare case where the call to the ecommerce business server takes over ten seconds or so they return a page to the customer indicating that they shall follow up with the information later to the customer that they need in order to get the product that they purchased.

If the Client inadvertently submits the same order twice i.e. the same external order id and line items an ecommerce business web host will accept the request and pass back the same information via the OrderCreate Response that it did in previous order submission s . If one or more of the line items was pending digital rights the ecommerce business web host will attempt to obtain the digital rights before sending the response.

Occasionally products on the ecommerce business web host side can be deactivated as part of the normal course of business activities with respect to product catalog maintenance. If a product that a Client has as part of their catalog is deactivated on the ecommerce business web host side the return response will contain an error code.

The following table is intended to list out all of the data that is included in the order create business process.

A schema is provided in Table 21 that describes how the XML is formed to construct the product catalog information. The following is an example of an XML OrderCreate submission from a Client.

Once a fulfillment request has been received ecommerce business web host will provide an immediate response to this call. This response s XML format follows a specific XML schema provided in Table 21. The following table lists the fields that are included in the order create response business process.

The following table shows the values for status return codes. There are two types of return codes one for the order itself and one for each line item in the order. For orders with multiple products that are not successful the line item order status will allow the client to pinpoint which product in the order caused the failure.

Here is an example of a return response to the example order request earlier in the document. The earlier request was for two copies of the same product. This fulfillment response shows a license and unlock code for one of the products and a pending digital rights response for the 2product.

The order return business process is used when a client needs to reverse a particular order for a customer based on a customer service issue that the customer is experiencing. In this case in order to reverse the transaction on the ecommerce business web host side the Order Return API should be called which will notify Digital River to disable the customer s download URL. The Order Return business process works in a similar fashion as the Order Create business process in that it leverages XML and HTTPS and has a request and response message passing sequence.

The schema for the Order Return XML is located in Table 21 here is an example of a return request from a Client.

The schema for the Order Return Response XML is located in Table 21 here is an example of an order return response sent to a Client.

The following sections are intended to provide the people in IT roles with the clients of the ICPP information on how to implement the service offerings ecommerce business web host strives to use the best and most standardized technologies in the industry in order to make the offering more universal in nature so that most clients will not have any major issues understanding the workings of the system and also so that there are no proprietary aspects that would make the implementations more difficult.

XML HTTPS and FTP are the main technical vehicles of standardization. Most IT departments will be familiar and comfortable with these technologies and would have implemented internal systems or subsystems in support of these universal web based technologies that have had a huge affect in the integration of the Internet and its services. XML is the primary data formatting protocol for all the APIs and acts as the mechanism that describes the data offered in each business process. HTTPS and FTP are the communication protocols real time and batch respectively that are employed by the APIs. HTTPS is used for the real time business processes used to create and return orders which will be described in a separate integration document. FTP is used for the batched product catalog business process described in the following sections.

The business process implementation of the product catalog consists of client filling out the product profile form which is included in the business users guide ecommerce business web host sets up the business process according to this form and then the client goes through the implementation and testing on their side to make the business process work. This business process is available in batch mode only because of the substantial amount of data that is being shared.

The business process architecture diagram is shown below in and is a combination of several views. It combines a data flow view an implementation view and a process flow view into a common condensed view intended to provide the developers less architectural views to deal with and make it simpler to understand and implement the ICPP. shows a business process architectural diagram for a product catalog business process.

The client will have one file created each time the product catalog extract is run. Files will be placed on the ecommerce business FTP server in the client s home directory under the PRODUCTCATALOG directory or alternatively onto the client s FTP servers. Since ecommerce business archives files for 30 days it is recommended that the client maintain an archive as well.

The export file will contain all the products that are currently available for purchase by a customer. When importing the file a client will want to scan for products they have in their database but are no longer in their feed as those products have been retired and should no longer be available for sale on their site. After the retired products are flagged in the client s database the entire catalog feed should be re imported so all updates and changed data elements are available in addition to new products.

Ecommerce business will export the full catalog once per day. It is recommended that the client import this full catalog every day to keep in sync with changes receive new products and retire products that are no longer available.

It is to be understood that even though numerous characteristics and advantages of various embodiments of the present invention have been set forth in the foregoing description together with details of the structure and function of various embodiments of the invention this disclosure is illustrative only and changes may be made in detail especially in matters of structure and arrangement of parts within the principles of the present invention to the full extent indicated by the broad general meaning of the terms in which the appended claims are expressed. For example the particular elements may vary depending on the particular application for the web interface such that different dialog boxes are presented to a user that are organized or designed differently while maintaining substantially the same functionality without departing from the scope and spirit of the present invention.

