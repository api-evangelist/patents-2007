---

title: Guaranteeing hypertext link integrity
abstract: There is described a method, system and computer program product for processing a link embedded in a link document in a client computer, said link comprises a URL reference for a URL document in the client computer or another computer, there being stored a record containing a link reference and an intended fingerprint, said intended fingerprint representing the content of the URL document associated with the URL of the link at the time of or after the link was created, said method comprising the steps of: fetching the intended fingerprint for the link; fetching the URL document; creating a current fingerprint of the fetched URL document; comparing the intended fingerprint and the current fingerprint; and identifying that the intended fingerprint and the current fingerprint are different in a material way. There is further described, on identifying that the intended fingerprint and current fingerprint are different in a material way and there being provided a database of current fingerprints and corresponding URLs, searching the current fingerprint database and locating current fingerprints that are similar to the intended fingerprint; choosing a current fingerprint that matches the intended fingerprint; and changing the URL of the link in link document to match the URL of the matched current fingerprint.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08135705&OS=08135705&RS=08135705
owner: International Business Machines Corporation
number: 08135705
owner_city: Armonk
owner_country: US
publication_date: 20070709
---
This application is a continuation application of U.S. patent application Ser. No. 10 682 391 entitled GUARANTEEING HYPERTEXT LINK INTEGRITY filed Oct. 9 2003 now U.S. Pat. No. 7 290 131 the disclosure of which is incorporated herein in its entirety for all purposes.

This invention relates to a method and apparatus for guaranteeing hypertext integrity. More specifically it relates to a method of guaranteeing hypertext integrity via a centralised resource.

One of the most prolific hypertext systems in recent years has been the World Wide Web which allows inter linked HTML Hypertext Markup Language documents to be transmitted between computers on the Internet using HTTP Hypertext Transfer Protocol . Each document exists as a separate entity which can be identified by a unique address on the network called a URL Uniform Resource Locator . This naming scheme allows for one party to reference to another s work by including a URL which points to the referenced work such that a web site belonging to a first party links to a second party document.

A web site value is measured by the availability accuracy relevance and reliability of the page being linked to. When a document on the web site is removed replaced altered or moved such value measurements can changed for the worse. Therefore making any change to a web site could have a detrimental effect on the value of the web site and the value of other web sites that link to it.

The problem relates to web site maintenance specifically of pages which link to documents which subsequently move change disappear or get replaced. These interconnecting links form the backbone of the World Wide Web and are often a valuable business tool in forming alliances and cross promotion.

There is a requirement for web site owners to be able to guarantee that their site is as up to date as possible with invalid links and inappropriate content discovered and repaired quickly.

This is also a more general problem affecting any system which contains links or pointers between items of information for example entries in a relational database.

Tools do exist that crawl through HTML documents either locally or over HTTP reporting broken links. Such a tool indicates to the web site owner that URL document of a particular link is no longer there. These tools do not indicate if the link still points to the same page and cannot give any guidance on whether the information has changed. The tools also do not attempt to resolve broken links or identify new locations for moved content. In the particular case of HTTP if a web site owner is aware that a document that was linked to has moved and they know where it has moved to they can set up their site so that when the resource is accessed a 302 Moved response is sent. However the onus is on the web site owner to find the new location of the page and to manually set up the redirection facility. Also the web site administrator must allow this facility to be set up. A problem for a web site administrator is that the content of the site is owned by someone other than the web site administrator but that complaints about broken links are more likely to come to the web site administrator especially on an intranet.

The problem of broken links is so severe that Google Google is a trademark of Google Technology Inc. has taken to caching whole pages that people can view if the search result is a broken link. Another solution from Google is to find similar documents for documents located in a search. Although this is not specifically limited to broken links it can be useful when a document is not available due a broken link. Similar documents in a Google search means other documents in the same category as the located document and Google specifically excludes very close matches to the located document.

One solution US Patent Publication US2002 0169865 discloses a software agent called Revbot to detect a changed page and then trigger a central resource which reindexes the changed page. Such central resources are typically search engine network nodes. This publication discloses how software agents are installed on the web site s computer platform and are aware of search engines and other qualifying databases and lists located at other nodes. The RevBot can be used to filter block and enhance web site content. By working in a manner that is the reverse of a search engine a RevBot is installed on a web site s computing platform and is aware of a search engine located remotely on a network. It transmits data relating to the web site such as the synopsis of the recently changed content to the search engine. When a web server changes a document Revbot will request that the search engine updates its index. This helps the search provider and users of this search engine.

Although the above description relates to a completely broken link the problem also extends to a link which does not return the internal document.

An object of at least one of the embodiments is to assist an administrator of a web site and content owner in maintaining the integrity of the hyperlinks.

An object of at least one of the embodiments is to locate the information and URL document that the content owner originally intended to link to.

Another object of at least one of the embodiments is to make each fingerprint unique to the content of a URL document not to URLs.

Another object of at least one of the embodiments is to locate the original of moved and altered content automatically whereby such an embodiment can be trusted to maintain a set of documents without manual intervention.

Another object of at least one of the embodiments is to update stored information as frequently as it is configured to do so and to provide information on demand.

Another object of at least one of the embodiments is to verify the state of a web site and guarantee that it is fully functional accurate and up to date.

Another object of at least one of the embodiments is to protect confidential information with a secure system.

According to a first aspect of the present invention there is provided a method as described in claim .

A URL uniform resource location defines the location in the Internet of a document such a document is referred to as a URL document. A link is a URL reference it is physical code or mark up language in a document called a link document henceforth that includes a URL refers to a URL document and may refer to a position within the URL document. Although a link document can be a URL document and vice versa the two documents are normally distinct in this specification and it is not envisaged that they would refer to the same document at the same time. A link reference is physical code or mark up language in a data structure distinct from a link document and a URL document that includes the link refers to the link document and may refer to the position of the link in the link document. Generating a fingerprint of a document comprises calculating a potentially unique numerical value in multidimensional content space for that document which is distinct from categorising the document in a defined index structure. A material difference in simplest terms is a percentage change in the content of the document and depends on the embodiment. A difference of more than 5 of the content of a document can be taken as more than a material difference in the document whereas a difference of 50 can be consider a completed changed document and essentially a broken link.

The first aspect of the invention thereby identifies a link which no longer points to the intended URL document the intended URL document having been removed completely or changed completely or changed in a small way.

According to a second aspect of the present invention there is provided a system for processing a link embedded in a link document in a client computer as described in claim .

According to a third aspect of the present invention there is provided a computer program product as described in claim .

Although the preferred embodiment is described in terms of Internet technology the invention is also suited for application in other forms of document and links to document. For instance the invention could be implemented for database records having pointers in links embedded in a link document.

The method advantageously further comprises on identifying that the intended fingerprint and current fingerprint are different in a material way and there being provided a database of current fingerprints and corresponding URLs searching the current fingerprint database and locating current fingerprints that are similar to the intended fingerprint choosing a current fingerprint that matches the intended fingerprint and changing the URL of the link in link document to match the URL of the matched current fingerprint.

More suitably the method further comprises checking all links in a group of link documents in a systematic order.

Preferably the method further comprises if a intended fingerprint does not exists for a link creating a link fingerprint from a URL document and storing the intended fingerprint and associated link reference.

More preferably the method further comprises if a intended fingerprint does not exist for a link and a URL document does not exist for a link creating a broken link report.

Even more preferably the method further comprises if the located similar current fingerprints are not within a permitted level of similarity creating a broken link report.

Advantageously the method further comprising spidering from a seed URL creating current fingerprints from the seed URL document and descendent URL documents and storing the current fingerprints and associated URLs.

The matched current fingerprint may correspond to a copy of the original URL document a previous or future version of the originally requested document or another URL document closely related to the original URL document by virtue of its content. If the original URL document has been changed significantly then another URL document may match the intended fingerprint better.

In the preferred embodiment the current fingerprints are stored in a Resource Location Broker RLB which at its simplest is a database residing on a client web server or third party broker. The intended fingerprints are stored as part of a link controller residing on a client web server or third party broker. The RLB may be part of a search engine and the current fingerprint database existing along with the URL index of the search engine. The steps of fetching and identifying the intended fingerprint are performed in the link controller. This aspect of separating the RLB current fingerprint database and the link controller intended fingerprint database components allows for flexibility of the solution to several configurations of client web server and third part broker. Four example configurations are described in embodiments 1 through 4. In all embodiments 1 to 4 the link controller and the link documents are included on a client computer or within a client network however in an alternate embodiment the link document and link controller are separated and the link controller provides a service for link documents on a customer computer.

In the second embodiment a client includes a link controller and a link document a web server includes both the URL documents and an RLB.

In a third embodiment the client includes a link controller and the link document the web server includes a URL document and a third party broker includes a RLB.

In a fourth embodiment the client is part of an intranet and includes a link controller a link document a URL document and an internal RLB for constructing fingerprints of the client URL documents. A web server includes a URL document linked to from within the intranet and a broker includes a global RLB.

One advantage of at least one embodiments is to reduce the problem of hacked links on a web site. Often a link on a site can be changed by a malicious party to point to an unrelated document such as advertising or a pornography site. By storing an intended fingerprint it is possible to detect and fix such maliciously changed links.

Referring to there is shown an overview of the preferred embodiment which is the third embodiment in the description of the embodiments at the end of this specification. The preferred embodiment is implemented for a system comprising a client broker and web server . The preferred embodiment comprises a link controller residing on the client and a resource location broker RLB residing on the broker .

The link controller comprises a intended fingerprint database an initialiser a document loader a link checker a fingerprint processor and a link fix component . The methods of the link controller are described further on with respect to . The RLB comprises an initialiser a document loader a spider a fingerprint processor current fingerprint database and fingerprint matcher . Web server comprises a document database accessible to the client and broker via a network.

In the preferred embodiment the fingerprint processor in the link controller and fingerprint processor in the RLB are able to parse a document completely to locate the contents and then generate a unique identification for the document from the contents. The fingerprint processors scan a document as is shown in and ignore parts of the document which are not content. In an HTML document the fingerprint processors can ignore table cells which are solely used for navigation within a site and pass the remainder as content to the fingerprint generator stage. shows a fairly common layout of navigation down the left hand side navigation window a standard header navigation window and a large content area indicated by the dotted lines. The parser isolates the content area to the exclusion of the navigation areas in the preferred embodiment and provides such content area for fingerprint generating. Metadata from the document is included in fingerprint generation because it can help to source and locate different versions of the same document when it is difficult to tell from small changes in the content.

In another embodiment of the invention the navigation area is used in the creation of the fingerprint as it can help set the position of the document within the web site.

The fingerprint is a numerical representation of the content of the document and may be considered a multidimensional vector in content space. It is stored in a matrix format using normal array structures. Note however that checksum algorithms such as MD5 would not be appropriate as the result of an MD5 sum on a document varies wildly with small changes.

The fingerprint is defined by certain properties Property 1 unique identifier for content rather than URL Property 2 guaranteed same identifier generated for same content Property 3 comparable with another identifier to find degree of difference Property 4 small change in content results in small change in identifier Property 5 large change in content results in small change in identifier Property 6 degree of difference between identifiers represents degree of difference in content Property 7 content cannot be derived from the identifier Property 8 generated from main content and not static headers and footers and Property 9 storage requirements less than average content. For the system to correctly identify moved content it needs to store a unique identifier which can be used to locate the same content at a different URL or the closest approximation to it.

In the preferred embodiment and referring to link controller sits in the client and provides the functionality on the client side. The actual changing of the link is performed by a link fix . The link controller is executed whenever the client wants to fix links in link containing documents on the client or on a server that it has publish access to.

Web server contains documents having URLs in the links of documents on the client. Therefore documents on the web are referred to as URL documents and documents containing links are called link documents. The web server can be located within the client s enterprise or is an external web server belonging to a third party perhaps including a customer.

The intended fingerprint database stores a fingerprint for each occurrence of a link in the link documents. So for the same URL there may be several links and therefore several fingerprint entries in the link database. Such fingerprints maybe referred to as intended fingerprints.

Initialiser generates a starting link list by uploading links from the intended fingerprint database . Typically this will be all the documents on the client s database.

Link checker tests the status of the returned document for the URL of the link and determines if the URL document is non existent. If there is no intended fingerprint then link checker will forward the link on to the fingerprint processor so that a new fingerprint can be generated and stored for future use. A newly generated fingerprint can be referred to as a current fingerprint but once it is stored with respect to a particular link it becomes an intended fingerprint.

Link fix has two inputs for a first condition when a link URL returns a URL document and a second condition when a link URL does not return a URL document. In the first case if the URL document is considered the same as intended by the link nothing is done and the component passes control. However in the first case if the URL document is considered different enough to that intended a new URL is located that matches better the original intention of the link. The intention is assumed to be as indicated by the intended fingerprint. A query containing the intended fingerprint is passed to the RLB and a new URL is returned. If the new URL returns a URL document that is considered similar enough then the link in the link document is edited to that returned URL if not then the link is marked as broken. In the second case a query containing the intended fingerprint is passed straight to the RLB and a new URL is returned. Again if the new URL returns a URL document that is considered similar enough then the link is edited to such a URL if not then the link is marked as broken.

Other functionality such as controlling the components in relation to a list of links is performed by the Link controller .

The Resource Location Broker RLB is a centralised resource which has two functions firstly to spider a defined set of hypertext URL documents and store current fingerprints for all the content found and secondly to accept queries from link controllers to match a intended fingerprint in the current fingerprint database.

The first function is performed by the initialiser document loader spider and fingerprint processor and described with respect to the components of the RLB in . A description of the method steps are described later with respect to . The initialiser supplies a first URL to start the spidering such a URL is a search engine index root for maximum coverage so that queue A starts with a seed URL and traverses each link for subsequent links until there are no more links. The document loader loads a URL document at the first link URL in the queue. The spider proceeds to create a new list queue B of all the URLs in the downloaded document and to add them to queue A if they are not already there. Fingerprint processor creates and stores a fingerprint for the document. The RLB manages the next URL in queue A and passes it step on to the document loader or exits if there is no more URLs.

The second function is performed by the fingerprint matcher . Fingerprint matcher accepts queries in the form of a first fingerprint and searches the current fingerprint database for matching fingerprints and corresponding fingerprints and URLs. The nearest matching fingerprint and URL is sent back to the requester. In a variation of this several matching fingerprints with corresponding URLs are returned so that the requester can choose between them.

In the case of a web site on the web server a link controller may find that the web server e.g. at www.xyz.com is returning an error code such as 404 not found with a protocol such as HTTP for the URL being queried or that a document is returned but the fingerprint is so wildly different it can be assumed that the page has been replaced or dramatically altered.

Once a new URL is determined for a link link controller rewrites the link in the local document using the newly determined URL. The rewriting of the link is possible by using the application programming interfaces of a content management system which may be in use such as Lotus Domino or of any operating system which handles files.

The RLB spider process will now be described in relation to . Steps to are performed by the link controller initialiser . Step load settings such as the seed link links to include exclude from spidering for example limiting spidering to within company and blocking inappropriate content. Step start of the spidering process. A queue of links A is initialised with a seed link.

Steps to are performed by the RLB document load . Step a URL document pointed to by the top link in the queue A is fetched referred to as the document in progress and the top link is removed from queue A step .

Steps to are performed by the RLB spider . Step start of the sub process for inserting all links in the URL document into queue A. A new queue B is created from all the links in the URL document. For example by parsing the HTML and extracting all the href attributes from a tags. Step the next link in the queue B is taken from it. Step if the link is not already present in queue A it is inserted step . Step are there more links in queue B If so go back to step . Otherwise end of the sub process for inserting all links in the URL document into queue A and move onto step .

Steps and are performed by the Fingerprint processor . Step the fingerprint a current fingerprint for the URL document in progress is calculated. Step the current fingerprint is stored in a current fingerprint database using an index against the URL of the link which allows rapid searching by querying for fingerprints within a specified difference.

Step queries whether there are more links in queue A . If so skip to . Otherwise end of the spidering process step .

The link controller process will now be described with respect to . Step is the start of the process in the link controller .

Steps performed in initialiser . Step user settings are loaded which for example will define the threshold for automatic changing of links and the administrator email address. Step a list of all hypertext files under the document root is created.

Steps are performed by the document loader . Step the next file in the list is taken from the head of the list and loaded step into memory.

Step start of checking individual links. A list of links within the client document is retrieved or created. For example by parsing the client s HTML link documents and extracting all the href attributes from a tags.

Step the link is checked to see if a intended fingerprint is associated with it such a intended fingerprint may have been created at installation or from an earlier run of the software. The intended fingerprint is loaded into a working memory.

Step start of sub process where a intended fingerprint is not available. The linked URL document is fetched into a working memory.

If step an error code is not returned the current fingerprint of the fetched URL document in the working memory is calculated step and stored step in working memory. Skip to .

Step in the link checker is the start of sub process where the intended fingerprint is available. Step the linked URL document is fetched.

Step checks to see if an error code is returned to signify that there is no URL document at this URL. If no URL document at the URL then skip to step in link fix . If there is a URL document then go to step in the link fix .

Steps are performed by the link fix . Step start of sub process where error code is not returned. The current fingerprint of the URL document in working memory is calculated and placed into working memory step and compared step with the intended fingerprint. If the difference is above a set threshold then skip to step otherwise if the difference is below the set threshold then skip to . End of sub process where error code is not returned.

Step finds identical current fingerprints for the intended fingerprint by making a request to the RLB . The RLB performs a search see for current fingerprints which are within a specified difference and returns the set of URL links associated current fingerprints and associated differences. In an adapted embodiment two fingerprints are sent to the RLB in a current fingerprint lookup the intended fingerprint and also the fingerprint of the link document so that the RLB search can take account of the types of documents linking to the linked document when determining the best match.

In step the results are checked at the client and a URL is chosen from the results. Some results will not be acceptable to the client for various reasons and the client can choose which URL to link to. It may be that none of the results are suitable and the difference between the fingerprints is above a second threshold which in this embodiment is the same as or similar to the first threshold. In this case step is next otherwise step .

In step if the difference between the closest result and the intended fingerprint is above the second threshold then the link is marked as broken. A routine for notifying the web master of the broken link is called typically writing the list of broken links and closest URLs returned by the RLB to a system file. This is the end of sub process where intended fingerprint is available and the process moves to step .

Step the difference between the current fingerprint and the intended fingerprint is below the set threshold. The URL of the link in the link document is substituted for the URL of the chosen current fingerprint. The process moves to step .

Step are there more links to check in this link document If so the process goes back to step . Otherwise this is the end of on link document and the process moves to step .

Step are there more link documents in the list If so go to step if not this is the end of the process.

The general solution presented here provides a secure centralised resource location broker RLB and an application which can be installed on a web server to auto correct invalid links by plugging into a Content Management System CMS or as a stand alone application on a workstation. Although the solution below uses terms appropriate to web site maintenance the same concepts can be directly applied to the more general case of systems containing linked information.

A global RLB is a central resource which is aware of all URL documents which may be linked to for each document it stores the document URL and a current fingerprint which uniquely identifies the content presented in the document.

Two documents at different URLs may contain the same content. When this occurs the same fingerprint will be stored for the separate documents which allows for dynamic rewriting of the link if one of the documents becomes inaccessible. The mapping of URLs to fingerprints in a current fingerprint table is similar to table 1 below 

The client application link controller maintains a intended fingerprint table similar to the table 2 below 

The intended fingerprint table contains fingerprints for each link it follows within the web site for which it is responsible. In table 2 there are two similar documents example.html and example2.html having links to the same URLs but stored as separate links in the table. On an automated schedule the link controller will work through its configured document tree such as the root of a company s web server and verify that the link returns a valid URL document. It will then calculate the current fingerprint for the returned content and check that it is either the same as the intended fingerprint or that is within a specified allowable degree of similarity. If it is the same it shows the document has not changed at all but if within the allowable difference allowing for minor changes to document content such as the fixing of spelling mistakes then the document has changed. There will also be cases where the fingerprint is wildly different and in such cases the link is deemed to be broken.

For example consider a link document example.html which resides in the directory home web htdocs on the client server www.abc.com which sits within the company s fire wall. This document is accessible at the URL www.abc.com example.html and contains the following fragment of HTML indicating a link to a page on a remote web server 

This arrangement can be seen below but is only one possible encoding hypertext systems other than HTML may define links differently.

ABC LTD s web master configures link fix to run at 1 am on a Sunday morning. The process is the same whether or not the link controller has been run before 

The link controller works through the document root on www.abc.com and at some point finds home web htdocs example.html.

The URL document is fetched from the web server and its fingerprint GCA TCG ATA CAT acquired from the intended fingerprint database . In this first example a valid document is received and a further fingerprint is generated GCA TCG ATA DOG . The newly generated fingerprint GCA TCG ATA DOG is compared with the retrieved information GCA TCG ATA CAT . In this first example the fingerprint is not identical to the fingerprint stored and the RLB is queried with the GCA TCG ATA CAT fingerprint. The RLB returns URL www.xyz.com product cat.html which is associated with GCA TCG ATA CAT . The link controller then updates the link document with this new URL.

In this example the similarity is exact but one of the considerations the user will have to make when deciding whether or not to enable this option is that a document could have changed within the specified degree of similarity each time the application runs. However over a longer period of time this could result in a totally different document which would be outside the specified allowed degree of similarity. At this stage only documents which have a fingerprint outside the allowable degree of similarity which returned an invalid status code remain.

Several embodiments are now described referring to . In the first second third and fourth embodiment the link controller resides in the client . In the first and second embodiment the RLB resides on the client and the document server respectively but in the third and fourth embodiment an RLB resides on the broker .

In a first embodiment see the client comprises link controller and RLB . Link document in client is shown linking to URL document on web server . The client based RLB stores current fingerprints so if the client resources are limited the pool of current fingerprints will not be sufficient to provide the best matches.

In a second embodiment see the client contains the link controller and the web server stores the current fingerprint records in RLB the web server receives the request locates the URL of a version of the first document using the current fingerprint records and returns the located URL to the requester server. Link document is shown linking to URL document . The client fixes the link with the located URL. In this embodiment the web server based RLB has fingerprints for all the documents on web server . Therefore when the client discovers that a link pointing to the web server needs to be fixed it can query the web server RLB directly.

In the third embodiment and preferred embodiment see the client comprises the link controller and link document . A link in link document points to URL document . The broker comprises the RLB and receives the request for a matching fingerprint record. If the RLB can not find an exact match for the intended fingerprint it locates a current fingerprint e.g. fingerprint of URL document that is as close as possible to that in the request. The client then fixes the link in the link document with the located URL of URL document .

The third and preferred embodiment of the invention uses a single RLB to determine the current fingerprints of documents on the Internet. A single RLB uses less resource then if multiple local RLB s spidered the same web sites. Therefore it would be more efficient if link controller on other clients queried a single global RLB for any other documents which many have similar fingerprints. A dedicated third party server in theory has more resources available to store and analysis fingerprints and therefore return better matches.

A variation of the third and preferred embodiment is a service provided on a global scale over the Internet using web services SOAP for the communication and UDDI for RLB discovery. The business model could typically be to sell subscriptions to the RLB and give the application away free.

A problem that the third embodiment does not solve is when a client e.g. ABC Ltd wants to use the link controller within its intranet the global RLB would be unable to spider their internal documents. Therefore the client talks to a local RLB within a fire wall. The local RLB is configured to only spider the documents within the intranet and so its database will only contain fingerprints for documents internal to ABC Ltd. If the link controller is configured to only talk to the local RLB then it cannot link to web server . Chaining of RLBs is used to overcome this problem.

In a fourth embodiment see the client A includes RLB A as well as link controller . An example link link resides on client B within client intranet . Link is a hypertext link in a document on client B and points to document on the web server .

Client RLB A stores for documents on intranet servers for reasons of web security and does not allow external indexing or spiders. Therefore broker RLB B does not spider the intranet but instead receives current fingerprint data directly from RLB A so that it has effectively fingerprinted the documents on the intranet. In an adapted embodiment RLB A will receive requests from RLB B to perform searches. RLB A receives a request to fix a link A or B and if it cannot locate a close matching fingerprint it will forward the request to RLB B. Conversely for RLB B requests from clients not part of the intranet can be forwarded to RLB A. If the RLB A recognises the a link URL as outside of its scope for example it may be outside of the intranet it will pass the query to RLB B and then return the response to link controller . Link controller is not aware of this extra request except for a potentially longer response time. In addition to allowing spidering of internal documents the above arrangement also prevents exposing the structure of the internal web pages to an external body and can also be used to provide scalability by cascading and distributing queries.

Although the preferred embodiment is described in terms of its main components it is assumed that these component boundaries need not be limited to the methods described since the invention maybe implemented in many ways including object oriented program techniques procedural techniques and a mixture of both.

Although the embodiments are described in terms of a client which fixes links on local documents on the client or intranet the documents can be anywhere on a network where the client has publisher access. In a further embodiment the client is a web service and charges its user for fixing links.

