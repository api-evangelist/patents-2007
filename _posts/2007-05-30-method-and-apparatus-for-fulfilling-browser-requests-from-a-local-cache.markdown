---

title: Method and apparatus for fulfilling browser requests from a local cache
abstract: One embodiment of the present invention provides a system that facilitates intercepting browser communication protocol requests at a client. In addition, the system optionally fulfills the requests with content which is locally cached on the client rather than with content from a web server, which is located externally from the client. During operation, the system receives a communication protocol request at a browser's communication protocol stack. In response to the request, the system identifies a Uniform Resource Locator (URL) for the request. The system also determines if an item of content identified by the URL can be retrieved from a local cache. If so, the system fulfills the request from the local cache.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08429247&OS=08429247&RS=08429247
owner: Google Inc.
number: 08429247
owner_city: Mountain View
owner_country: US
publication_date: 20070530
---
The present invention relates to web browsers. More specifically the present invention relates to a method and an apparatus for fulfilling browser requests from a local cache.

In recent years computer users have begun to use web based applications to perform various computational tasks. These web based applications provide a number of advantages. For example web based applications allow a user to access his or her data from any computer or device that has a web browser and network access. Web based applications also have minimal impact on client resources which is a significant advantage for resource constrained computing devices. However web based applications have one major drawback they do not operate efficiently or in many cases at all without the presence of a network connection.

In order to facilitate offline browsing browsers typically provide a caching mechanism which enables web pages that are delivered to the browser to be stored in a browser s local cache. At some subsequent time if the user attempts to view a previously viewed page and the client does not have a connection to the web server that hosted the web page the browser can retrieve a copy of the web page from its local cache and can display the copy of the web page to the user.

However the browser s local cache is not sufficient to reliably run the client side of a web based application without network connectivity. Additionally such caching does not facilitate handling query arguments or conditionally serving local cached resources based on browser cookies.

Hence what is needed is a method and an apparatus for executing the client side of a web based application without the problems listed above.

One embodiment of the present invention provides a system that facilitates intercepting browser communication protocol requests at a client. In addition the system optionally fulfills the requests with content which is locally cached on the client rather than with content from a web server which is located externally from the client. During operation the system receives a communication protocol request at a browser s communication protocol stack. In response to the request the system identifies a Uniform Resource Locator URL for the request. The system also determines if an item of content identified by the URL can be retrieved from a local cache. If so the system fulfills the request from the local cache.

In some embodiments of the present invention the system receives a list of URLs associated with the URL for the request. Next the system determines if content specified by each URL in the list of URLs is currently in the local cache. Finally for content that is not currently in the local cache the system downloads the content specified by each URL in the list of URLs and stores the content in the local cache.

In some embodiments of the present invention determining if the item of content identified by the URL can be retrieved from the local cache involves determining if all of the content specified by each URL in the list of URLs can be retrieved from the local cache. If all of the items of content specified by each URL in the list of URLs cannot be retrieved from the local cache then the system determines that the item of content cannot be retrieved from the local cache.

In some embodiments of the present invention the system periodically receives an updated list of URLs associated with the URL for the request.

In some embodiments of the present invention the system downloads the content specified by each URL in the list of URLs in the background while a user is using the browser.

In some embodiments of the present invention the system determines whether a cookie associated with a user is present on the client. Next the system fulfills the request from the local cache only if the cookie is present on the client. Note that fulfilling the request may include serving the content based on a value in the cookie while the content is served from the local cache.

In some embodiments of the present invention the URL includes query arguments. In some embodiments determining if the item of content identified by the URL can be retrieved from the local cache involves processing a query with the query arguments.

In some embodiments of the present invention fulfilling the request from the local cache involves processing a server side script in the item of content.

In some embodiments of the present invention the system inserts a second item of content into the local cache and subsequently sends the item of content to the web server.

In some embodiments of the present invention the communication protocol is HyperText Transfer Protocol HTTP .

The following description is presented to enable any person skilled in the art to make and use the invention and is provided in the context of a parti cular application and its requirements. Various modifications to the disclosed embodiments will be readily apparent to those skilled in the art and the general principles defined herein may be applied to other embodiments and applications without departing from the spirit and scope of the present invention. Thus the present invention is not limited to the embodiments shown but is to be accorded the widest scope consistent with the claims.

The data structures and code described in this detailed description are typically stored on a computer readable storage medium which may be any device or medium that can store code and or data for use by a computer system. This includes but is not limited to volatile memory non volatile memory magnetic and optical storage devices such as disk drives magnetic tape CDs compact discs DVDs digital versatile discs or digital video discs or other media capable of storing computer readable media now known or later developed.

One embodiment of the present invention provides a system that facilitates intercepting browser communication protocol requests at a client. In addition the system optionally fulfills the requests with content which is locally cached on the client rather than with content from a web server which is located externally from the client. During operation the system receives a communication protocol request at a browser s communication protocol stack. In response to the request the system identifies a Uniform Resource Locator URL for the request. The system also determines if an item of content identified by the URL can be retrieved from a local cache. If so the system fulfills the request from the local cache.

In some embodiments of the present invention the system receives a list of URLs associated with the URL for the request. For example the system may receive a list of URLs that are associated with images video audio files cascading style sheets and scripts for a web page which is associated with a URL. Next the system determines if content specified by each URL in the list of URLs is currently in the local cache. Finally for content that is not currently in the local cache the system downloads the content specified by each URL in the list of URLs. The system also stores the content in the local cache.

In some embodiments of the present invention determining if the item of content identified by the URL can be retrieved from the local cache involves determining if the content specified by each URL in the list of URLs can be retrieved from the local cache.

In some embodiments of the present invention the system periodically receives an updated list of URLs associated with the URL for the request. This can happen at a predetermined time or at a specified interval. In some embodiments the system receives an updated list the first time the user navigates to the website in a given session. In other embodiments the user may request to receive an updated list.

In some embodiments of the present invention the system downloads the content specified by each URL in the list of URLs in the background while a user is using the browser.

In some embodiments of the present invention the system determines whether a cookie associated with a user is present on the client. The system then fulfills the request from the local cache only if the cookie is present on the client. In some embodiments of the present invention this cookie includes user preferences such as language settings. By including such user settings in the cookie or cookies the system allows different users to use a different set of offline resources for the same web based application. For example the browser local cache may return content in English for one user and may return content in German for another user.

Note that this use of cookies can include serving different content such as a web page for a location referenced by an existing URL based on values stored in the cookie. In some embodiments of the preset invention different versions of the URL are store in the local cache. In some embodiments of the present invention the content is retrieved from the server one time stored in the local cache and modified as it is served for multiple users based on the values stored in cookies.

In some embodiments of the present invention the URL includes query arguments. In some embodiments determining if the item of content identified by the URL can be retrieved from the local cache involves processing a query with the query arguments.

In some embodiments of the present invention fulfilling the request from the local cache involves processing a server side script in the item of content.

In some embodiments of the present invention the system inserts a second item of content into the local cache and subsequently sends the second item of content to the web server. For example while interacting with the web based application while offline a user may upload a file to the web based application. Because the user is offline the file cannot be uploaded immediately to the web server that serves the web based application. In this example the system places the file into the local cache and then uploads the file to the web server the next time or a subsequent time the client has a connection to the web server. To the user it appears as if the file was uploaded while the user was offline. Note that in some embodiments of the present invention the web based application may include an indicator that indicates to the user that the client should be synchronized with the web server.

In some embodiments of the present invention the communication protocol is HyperText Transfer Protocol HTTP . However note that any protocol for delivering web based resources may be used.

Clients can include any node on a network including computational capability and including a mechanism for communicating across the network.

Similarly servers can generally include any node on a network including a mechanism for servicing requests from a client for computational and or data storage resources.

Users and can include an individual a group of individuals an organization a group of organizations a computing system a group of computing systems or any other entity that can interact with computing environment .

Network can include any type of wired or wireless communication channel capable of coupling together computing nodes. This includes but is not limited to a local area network a wide area network or a combination of networks. In one embodiment of the present invention network includes the Internet. In some embodiments of the present invention network includes phone and cellular phone networks.

Database can include any type of system for storing data in non volatile storage. This includes but is not limited to systems based upon magnetic optical or magneto optical storage devices as well as storage devices based on flash memory and or battery backed up memory. Note that database can be coupled to a server such as server to a client or directly through a network.

Devices can include any type of electronic device that can be coupled to a client such as client . This includes but is not limited to cell phones Personal Digital Assistants PDAs smart phones personal music players such as MP3 players gaming systems digital cameras portable storage media or any other device that can be coupled to the client. Note that in some embodiments of the present invention devices can be coupled directly to network and can function in the same manner as clients .

Browser is loaded on client . In one embodiment of the present invention browser can include any program that is capable of displaying web pages that include scripts. Note that browser can be loaded on any computational device such as clients servers and devices .

Next the system determines the Uniform Resource Locator URL of the request operation . The system also determines if the content identified by the URL can be retrieved from the local cache operation . If so the system fulfills the request from the local cache operation . Otherwise the system fulfills the request by retrieving the content from the server operation .

In some embodiments of the present invention the system always retrieves the content from the local cache if the content is available in the local cache. In other embodiments of the present invention the system always retrieves the content from the server if the server is reachable. In some embodiments of the present invention the content is always retrieved from the local cache unless a specified period of time has elapsed since the content was last retrieved from the server .

Note that from the user s point of view the system operates as if user is always communicating with server . In other words the process of determining if content can be retrieved from the local cache and the process of retrieving content from the local cache occurs in a manner that is invisible to the user . For example even if the client is offline and has no connection to a network or server user enters the URL of the web application into browser . User is then presented with the web based application that is being served from the local cache but it appears to user as if the web based application is being served from server .

In some embodiments of the present invention when retrieving content from the local cache the system executes any server side scripts or logic present in the content. This can include processing any queries including queries arguments that are included in the URL string as well as handling any cookies or other processing that is normally handled by server .

Note that in one embodiment of the present invention server returns a list of URLs associated with the entire web based application. In some embodiments of the present invention no items of content are served to browser from the local cache until all of the content associated with all of the URLs for the web based application are retrieved and stored in the local cache. This facilitates upgrades to the web based application where the client will not receive any content from the local cache for a new version of the web based application until all of the components of the new version of the web based application have been retrieved and stored in the local cache. Thus the new components are downloaded and stored and the decision to server the new version or the old version of the web based application from the local cache is atomic based on retrieving the entire set of the content.

Next for each URL in the list of URLs the system determines if the content specified by the URL is present in the local cache operation . If not the system downloads the content from the server and stores the content in the local cache operation . The system also downloads any server logic associated with the content and stores the server logic in the local cache operation .

Once all of the content associated with each URL in the list of URLs is downloaded and stored in the cache the system indicates that the content stored at the associated URL is available from the local cache operation .

Embodiments of the present invention provide a system that facilitates intercepting browser communication protocol requests at a client and serving these requests from a local cache. Intercepting the communication requests and serving the communication requests from the local cache happens in a manner that is transparent to the user . User interacts with the web based application via browser as if client is online and coupled to network and server .

In some embodiments of the present invention the system downloads server side logic associated with the URLs from server and stores the server side logic in the local cache. This can include scripts executable code etc. The system then processes any server side logic as the content is delivered from the local cache. In this way the content being served from the local cache is dynamic and may appear different than the last time the content was delivered directly from server . This is an advantage over existing browser caches where static versions of dynamic pages are cached locally and the same static version is subsequently served from the local cache without the server side logic being executed.

The foregoing descriptions of embodiments of the present invention have been presented only for purposes of illustration and description. They are not intended to be exhaustive or to limit the present invention to the forms disclosed. Accordingly many modifications and variations will be apparent to practitioners skilled in the art. Additionally the above disclosure is not intended to limit the present invention. The scope of the present invention is defined by the appended claims.

