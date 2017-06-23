---

title: Method and apparatus for storing and restoring state information of remote user interface
abstract: An apparatus and method are provided for restoring a remote user interface (RUI) in a Universal Plug and Play (UPnP) environment. In the method, a client receiving an RUI from a server, requests that the state information of the RUI be saved. The method includes obtaining state information generated when the RUI is used, and requesting that the obtained state information be saved. Accordingly, it is possible to apply a method of storing and restoring state information of a remote user interface, in a UPnP environment, to an HTTP-based remote protocol model having stateless characteristics which do not allow state information of a remote user interface to be stored.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08219692&OS=08219692&RS=08219692
owner: Samsung Electronics Co., Ltd.
number: 08219692
owner_city: Suwon-si
owner_country: KR
publication_date: 20070118
---
This application claims priority from Korean Patent Application No. 10 2006 0005575 filed on Jan. 18 2006 in the Korean Intellectual Property Office the disclosure of which is incorporated herein in its entirety by reference.

Apparatuses and methods consistent with the present invention relate to restoring state information of a remote user interface RUI and more particularly to restoring an RUI in a Universal Plug and Play UPnP environment.

According to UPnP the RUI CP discovers and controls the RUI client and the RUI server . The RUI client and the RUI server that are connected under the control of the RUI CP process a request and a response received via an RUI according to out of band remote protocol such as remote desktop protocol RDP and extended remote technology XRT protocol.

In operation the RUI CP searches for RUI connections that are currently in progress by calling GetCurrentConnection to the first RUI client and learns a connection to the RUI server from the searched RUI connections.

In operation the RUI CP calls SetUILifetime to the RUI server in order to instruct the RUI server to maintain the RUI connections that are currently in progress for a predetermined time.

In operation the RUI CP calls Disconnect to the first RUI client in order to terminate the RUI connections that are in progress.

In operation the RUI CP calls Connect to the second RUI client in order to start the RUI connections maintained according to the instructions given in operation .

However as described above the conventional method of is applicable only to a remote protocol model which allows all state information of RUIs to be stored in an RUI server. However in the case of a HyperText Transfer Protocol HTTP based remote protocol model when a transaction that processes a request and a response is completed the state information of a remote interface is lost and is not stored due to the stateless characteristics of the HTTP and therefore the RUI client manages most of the state information.

Accordingly the conventional process of storing and restoring state information of an RUI according to UPnP is applicable to remote protocol models such as RDP and XRT in which all state information of RUIs is stored in an RUI server. However the conventional process has a problem in that it cannot be applied to remote protocol models such as HTTP in which most of the state information is managed by an RUI client. In particular binary protocol based RDP and XRT need a wider network bandwidth than HTTP. Therefore since an HTTP based RUI is widely used the above problem has emerged as a very important issue.

The present invention provides a method and an apparatus for allowing a process of storing and restoring state information of an RUI in a UPnP environment to be applied to an HTTP based remote protocol model having stateless characteristics that does not allow state information of an RUI to be stored.

The present invention also provides a computer readable recording medium having recorded thereon a program for executing the method.

According to an aspect of the present invention there is provided a method of allowing a client which receives the remote user interface from a server to request that state information of a remote user interface be saved the method comprising obtaining state information generated when the remote user interface is used and requesting that the obtained state information be saved.

According to another aspect of the present invention there is provided a computer readable medium having recorded thereon a program for executing the method of requesting that state information regarding a remote user interface be saved.

According to another aspect of the present invention there is provided an apparatus for allowing a client which uses the remote user interface received from a server to request that state information of a remote user interface be saved the apparatus comprising a remote user interface control point module obtaining information of a storage server providing storage for saving the state information and a web browser requesting the storage server to save the state information based on the information about the storage server obtained by the remote user interface control point module.

According to another aspect of the present invention there is provided a method of restoring state information of a remote user interface by using a client which receives the remote user interface from a server the method comprising obtaining state information generated when the remote user interface is used and reflecting the obtained state information in the remote user interface.

According to another aspect of the present invention there is provided a computer readable medium having recorded thereon a program for executing the method of restoring state information of a remote user interface.

According to another aspect of the present invention there is provided an apparatus for allowing a client which receives the remote user interface from a server to restore state information of a remote user interface the apparatus comprising a remote user interface control point module obtaining information of a storage server providing storage which stores the state information and a web browser obtaining the state information from the storage server based on the information about the storage server which is obtained by the remote user interface control point module and reflecting the obtained state information in the remote user interface.

Hereinafter exemplary embodiments of the present invention will be described in detail with reference to the accompanying drawings. In this disclosure an RUI based on an HTTP which is a stateless protocol that does not store state information will be described with respect to a web page containing an HTTP object which is a Java script object that processes an HTTP request without reloading the web page. However it would be apparent to those of ordinary skill in the technical field to which the present invention pertains that the present invention and the exemplary embodiments are applicable to other types of remote user interfaces and not just the web page.

The RUI CP module acts as a UPnP CP that discovers and controls UPnP CDs. In particular according to an exemplary embodiment of the present invention the RUI CP module acquires information based on UPnP regarding an SS server during discovery of an RUI server and an SS server which are CDs based on UPnP. Also the RUI CP module provides the information regarding the SS server to an SS handler in order to request that state information of a remote interface i.e. a web page be stored.

The RUI CD module advertises that it is a UPnP CD and acts as a UPnP CD to be controlled by a UPnP CP that discovers the RUI CD module in response to the advertisement.

The web browser module acts as an HTTP based general web browser. That is the web browser module is a client module that receives a request for a web page from a user transmits the request to the RUI server having a web server performs rendering of the web page acquired in response to the request and displays the rendering result.

In particular the web browser module may include the SS handler therein or in the form of a plug in. The SS handler is an optional module needed only when the RUI CP module is present. The RUI CP module and the SS handler are capable of establishing internal communications via interprocess communication IPC or a UNIX domain socket. When receiving the HTTP header and realizing that the RUI client includes the RUI CP module the RUI server may provide a savable page illustrated in which is represented by a Java script using the SS handler to obtain the information regarding the SS server . That is when the Java script is executed the SS handler obtains the information regarding the SS server from the RUI CP module and provides the obtained information to a states saving page illustrated in when there is a request for the states saving page .

The web browser module receives the savable page illustrated in from the RUI server . Also when receiving from the user a command to save state information regarding an RUI that is when the user clicks a SAVE button not shown on the main page of the savable page the web browser module requests the state information regarding the RUI server which is generated when the user uses the web page in the case that a Java script included in the web page is executed in order to generate the state information of the RUI server . That is the web browser module transmits a GETSTATES request message as illustrated in to the RUI server .

Also the web browser module obtains the state information of the RUI server in response to the request. That is the web browser module receives from the RUI server a GETSTATES response message illustrated in in response to the GETSTATES request message and obtains the state information of the RUI server by executing the Java script included in the web page. If the user uses a web page regarding product sales information regarding a product that the user selects remains in the RUI server . Also if the user uses a web page regarding user authentication information regarding a result of user authentication remains in the RUI server . Such items of information are examples of the state information of the RUI server .

Also the web browser module executes the Java script included in the web page in order to read from the web page the state information of the RUI client which is generated when the user uses the web page. While the user is using the web page form input information cookie information state information of an audio visual AV object corresponding to an input value of the user are generated. Such items of information are examples of the state information of the RUI client .

In order to request the SS server to save the above generated information and the obtained state information of the web page that is the state information of the RUI client and the RUI server the web browser module receives information regarding the SS server from the RUI CP module or an RUI CP module depicted in and described below of the RUI server . More specifically the web browser module may display a presentation page received from the RUI server by executing the Java script in the web page in order to display the information of the SS server to the user so that the user can select the SS server as a storage server for storing the state information of the web page. Otherwise the web browser module may request the SS handler to provide the information of the SS server and display the obtained information to the user so that the user can select the SS server as a storage server for storing the state information of the web page.

Also the web browser module executes the Java script in the web page in order to request the SS server to save the state information of the web page by using the information of the SS server selected by the user i.e. a uniform resource locator URL of the SS server . That is the web browser module transmits a SAVE request message illustrated in to the SS server . Also the web browser module receives a SAVE response message illustrated in which indicates that saving of the state information of the web page is completed from the SS server .

Also when receiving from the user a command to display a list of restoring pages for web pages the web browser module receives the information of the SS server from the RUI CP module or the RUI CP module shown in of the RUI server . Also the web browser module requests the SS server to provide the list of restoring pages by using the information of the SS server i.e. the URL of the SS server . That is the web browser module transmits a restoring page request message illustrated in to the SS server .

Also the web browser module obtains the list of restoring pages in response to the request. That is the web browser module receives from the SS server a restoring page response message illustrated in in response to the restoring page request message and obtains the list of restoring pages for web pages from the restoring page response message. Also the web browser module displays the list of restoring pages to the user so as to allow the user to select one from the list of restoring pages.

Also the web browser module requests the SS server to provide the selected restoring page and receives the selected restoring page as a response to the request. That is the web browser module transmits the restoring request message illustrated in to the SS server and receives a restoring response message illustrated in as a response to the restoring request message.

Also the web browser module requests the SS server to provide state information for the selected restoring page and obtains the state information from a response to the request. The obtained state information includes the state information of the RUI server obtained via the URL of an originalpage frame as shown in and the state information of the RUI client in the form of a saved states page as shown in . Also the web browser module requests the RUI server to provide an original page as shown in and at the same time provides the RUI server with the state information of the RUI server of the obtained state information so that the RUI server can restore the state of the RUI server . That is the web browser module provides the RUI server with a ValueFor ServerStates  field of the restoring page the syntax of which is shown in . In this case the web browser module also transmits information for access to the state information of the RUI client shown in to the RUI server via a statesAccessPrefix field shown in .

Also the web browser module obtains as a response to the request the original page containing a Java script for restoring the state of the RUI client . Also the web browser module executes the Java script in the original page in order to reflect the executing result in the original page thereby restoring the web page.

The RUI CP module acts as a UPnP CP that discovers and controls UPnP CDs. In particular according to an exemplary embodiment of the present embodiment when the RUI client does not include the RUI CP module the RUI CP module obtains information of the SS server during discovery of the SS server according to the UPnP standard and provides it to the SS server selector .

The RUI CD module advertises that it is a UPnP CD and acts as a UPnP CD controlled by a UPnP CP that discovers the RUI CD module according to the advertisement.

The web server module acts as an HTTP based general web server. That is the web server module is an HTTP server module that receives a request for an application from the RUI client processes the application and provides the result of processing in response to the request. In particular when receiving a request for a general web page from the RUI client the web server module creates and provides a web page in response to the request.

The state manager which manages the state information of the RUI server is an optional module needed only when the state information of the RUI server is generated when a user of the RUI client uses an RUI application i.e. a web page which is provided by the RUI server . More specifically when receiving from the RUI client a request for the state information of the RUI server generated when the user of the RUI client uses a web page provided from the RUI server the state manager provides the state information of the RUI server to the RUI client . That is upon receiving the GETSTATES request message illustrated in via the web server module the state manager transmits a GETSTATES response message illustrated in in response to the GETSTATES request message.

Also when receiving the state information of the RUI server from the RUI client the state manager restores the state of the RUI server based on the received information. That is when receiving ValueForServerStates  in a restoring message illustrated in from the RUI client the state manager restores the state of the RUI server based on the ValueForServerStates  .

The RUI application module performs an application for a web page corresponding to an RUI remote user interface. More specifically when receiving a request for a web page from the RUI client via the web server module the RUI application module creates a savable page providing a unit e.g. a SAVE button via which the user can instruct that the state information of the web page is to be saved and provides the savable page to the RUI client .

Also when receiving from the RUI client information for accessing the state information of the RUI client i.e.  StatesAccessPrefix  in the restoring page the syntax of which is shown in the RUI application module creates an original page containing a Java script for accessing the state information of the RUI client in order to restore the state of the RUI client and provides the original page to the RUI client .

The SS server selector is an optional module needed only when the RUI CP module is present. The SS server selector creates a representation page displaying to a user information about the SS server obtained by the RUI CP module and provides the information to the RUI client . Also as described above when the user who recognizes the representation page selects the SS server the SS server selector provides a call window not shown with the information about the SS server by using an opener object of the Java script.

The main page is visible to a user and the user can input desired information thereto via a user interface and view the result. In particular according to an exemplary embodiment of the present invention the main page contains a SAVE button not shown the use of which allows state information of RUIs to be saved.

The states saving page is invisible to the user and contains a Java script for storing the main page in the SS server . When the user clicks the SAVE button the information regarding the SS server is obtained from the SS handler of the RUI client and the information of the RUIs is stored in the SS server based on the obtained information by using the states saving page .

If the RUI client does not have the RUI CP module and the SS handler and if the RUI server includes the RUI CP module and the SS server selector the RUI server provides a savable page the syntax of which is shown in for example which is different from the savable page whose representative syntax is illustrated in and .

The RUI CD module advertises that it is a UPnP CD and acts as a UPnP CD controlled by either the UPnP CP module of the RUI client or the UPnP CP module of the RUI server which discovers the RUI CD module according to the advertisement. That is the RUI CD module may include information such as true in a description of the RUI CD module in order to advertise that the SS server has the state storage unit capable of storing state information of a remote interface i.e. a web page.

The web server module acts as an HTTP based general web server. That is the web server module is an HTTP server module that receives a request for an application from the RUI client and processes the application and provides the processing result in response to the request. In particular the web server module receives and processes commands to save and restore the state information of a web page which is received from the RUI client .

When receiving a SAVE request message such as the one illustrated in via the web server module the save handler stores all state information of the web page which is contained in the SAVE request message i.e. the state of the RUI client and the state information of the RUI server in the state storage unit . In particular when the value of URLFortheOriginalPageToBeSaved in the SAVE request message of is the same as state information stored in the state storage unit the save handler changes the value and then stores the state information of the web page.

The RUI restoring unit allows the RUI client to select and restore state information of the web page desired by a user. More specifically when receiving a request for a list of restoring pages for web pages from the RUI client the RUI restoring unit provides a list of restoring pages stored in the state storage unit to the RUI client . That is when receiving the restoring page request message illustrated in from the RUI client via the web server module the RUI restoring unit transmits a restoring page response message illustrated in in response to the message. Also if the user selects one of the restoring pages upon receiving a request for the selected restoring page the RUI restoring unit provides the selected restoring page. That is when receiving a restoring request message as illustrated in via the web server module the RUI restoring unit transmits a restoring response message illustrated in to the RUI client in response to the received request message.

Also when receiving a request for state information for the restoring page provided to the RUI client the RUI restoring unit reads the requested state information from the state storage unit and provides it to the RUI client .

The state storage unit stores all the state information of the web page which is received from the RUI client e.g. information regarding cookies generated when the user used RUIs information regarding forms AV object information and the state information of the RUI server .

The original page is visible to a user and is provided from the RUI application module of the RUI server .

The saved states page is invisible to the user and is an HTML document containing cookie information form information and AV object information stored in the state storage unit . The RUI client reflects the state information of the saved states page in the original page thereby completely restoring the original state of the original page when the RUI client used the original page .

Also ValueFor serverStates  has the same value as the argument value of  serverStates  in the SAVE request message illustrated in . Thus the web browser module of the RUI client receiving the restoring page of can load the original page received from the RUI server into the originalpage frame and at the same time provide the RUI server with the state information of the RUI server so that the original page can be restored to its original state when the RUI server used the original page .

Also  statesAccessPrefix indicates a Java script access path for allowing a Java script in the original page provided from the RUI server to read the state information of a web page from the saved states page which is loaded into the savedstates frame. That is since it is impossible to recognize the data structure of an HTML document of the saved states page from the SS server by using the Java script in the original page from the RUI server the SS server indirectly provides the saved states page by using a  statesAccessPrefix  argument.

NameForToBeSavedStates field indicates the name of a web page to be stored in the SS server and must be set to have a unique value. For example the unique name may be tag saved time . If a web page having the same name as the indicated name has already been stored in the state storage unit of the SS server receiving this message indicating the name of the web page the indicated name is renamed and stored.

A Content Type application x www form urlencoded field represents a multipurpose Internet mail extensions MIME type of body content of the SAVE request message the format of which should be fixed so that the SS server can understand it. Also an  url  URLForTheOriginalPageToBeSaved  serverStates  opaque server states string  hiddenFrameURL  URLForStatesSavingPage field which is a part of the body content of the SAVE request message indicates the URL of the original page as shown in generated by the RUI application module of the RUI server and the state information of the RUI server . In particular the value of  serverStates  is interpreted by the SS server and thus may be set as the RUI server desires. However keys of the  url  URLForTheOriginalPageToBeSaved  serverStates  opaque server states string  hiddenFrameURL  URLForStatesSavingPage field i.e.  url   serverStates  and hiddenFrameURL  must be predetermined between the RUI server and the SS server so that the SS server can understand the keys.

An Opaque strings for any RUIC states field represents the state information of RUI client e.g. cookie information form input information AV object state information. Since these strings are also the state information of the RUI client key values of these strings need not be set to be understood by the SS server unlike in the case of  url   serverStates  and  hiddenFrameURL  . That is the key values of these strings may be set so that only the RUI server can understand them.

However since a method of storing an RUI according to an exemplary embodiment of the present invention is applied to two RUI clients the RUI client illustrated in will be divided into the first RUI client and the second RUI client for convenience. The first RUI client and the second RUI client are generally separate RUI clients but they may be regarded as a single RUI client. For example in the former case a user uses a web page in a plurality of RUI clients and in the latter case the user sequentially uses a first web page a second web page and the first web page in only a single RUI client.

In operation the first RUI client receives a request from a user for a web page corresponding to an RUI.

In operation the first RUI client requests the RUI server to provide the web page requested in operation .

In operation the RUI server provides the web page requested in operation to the first RUI client . Here the web page provided from the RUI server is a savable page containing a unit i.e. a SAVE button whereby the user can save the state information of the web page.

In operation the first RUI client receives a command to save the state information of the web page when the user clicks the save button.

In operation the first RUI client transmits a GETSTATES request message to the RUI server in order to request the RUI server to provide the state information. Next the RUI server receives the GETSTATES request message and transmits a GETSTATES response message in response to the GETSTATES request message. Next the first RUI client receives the GETSTATES response message and obtains the state information of the RUI server contained in the GETSTATES response message. Operation is optional and is needed when the RUI server manages the state information of RUIs.

In operation the first RUI client reads from the web page the state information of the first RUI client which is generated when the user uses the web page.

In operation the first RUI client transmits a SAVE request message to the SS server in order to request the SS server to save the state information of the web page.

In operation the SS server receives the SAVE request message and stores the state information of the web page which is included in the received message in the state storage unit .

In operation the second RUI client receives from a user a command to display a list of restoring pages.

In operation the second RUI client transmits a restoring page request message to the SS server in order to request the list of restoring pages. Next the SS server receives the restoring page request message and transmits a restoring page response message in response to the restoring page request message. Next the second RUI client receives the restoring page response message and obtains the list of restoring pages from the received message. Next the second RUI client displays the list of restoring pages to the user.

In operation the second RUI client receives the user s input indicating that one of the restoring pages from the list of restoring pages has been selected by the user.

In operation the second RUI transmits a restoring request message to the SS server in order to request the SS server to provide the restoring page selected in operation . Next the SS server receives the restoring request message and transmits a restoring response message in response to the restoring request message. Next the second RUI client receives the restoring response message and obtains the restoring page from the restoring response message.

In operation the second RUI client requests the SS server to provide state information for the restoring page. Next the SS server transmits the requested state information to the second RUI client in response to the request. Next the second RUI client obtains the requested state information.

In operation the second RUI client requests the RUI server to provide the original page . In this case the second RUI client provides the RUI server with the state information of the RUI server and information for accessing the state information of the RUI client so that the RUI server can restore the state information of a web page. Next the RUI server restores its state accesses the state information of the second RUI client by using the information for accessing the state information of the second RUI client in order to create an original page containing a Java script for restoring the state of the second RUI client and transmits the original page to the second RUI client . Then the second RUI client obtains the original page as a response to the request.

In operation the second RUI client restores the state of the web page by reflecting the state information obtained in operation in the original page by using the Java script in the original page .

In operation the web server module provides the web browser module with a savable page containing a SAVE button.

In operation when a user clicks the SAVE button in the main page the web browser module executes the states saving page . However the main page may be executed according to a Java script provided from the RUI server .

In operation the web server module receives the state information of the RUI server from the state manager .

In operation the web server module provides the state information of the RUI server to the states saving page .

In operation the states saving page sets the state information of the RUI server as the value of an tag illustrated in the states saving page shown in in order to use the state information for transmitting a SAVE request message.

In operation in the states saving page or the main page the SS handler is requested to provide information about the SS server i.e. the URL of the SS server . Whether the states saving page or the main page is used to request the information of the SS server is determined according to the type of savable page provided from the RUI server . Hereinafter the method of will be described according to the case where the states saving page is used. It would be apparent to those of ordinary skill in the art that the method of is applied similarly in the case where the main page is used.

In operation the RUI CP module obtains the description of the SS server discovered in operation . In particular if the description of the SS server reveals that the state storage unit is provided in order to store state information the SS server is regarded as a storage server providing the state storage unit capable of storing state information. If the RUI CP module has already stored the description of the SS server operations and are skipped.

In operation the states saving page reads the state information of the main page from the main page in order to obtain the state information of the RUI client and also obtains the state information of the RUI server .

In operation the web server module stores the state information obtained in operation in the state storage unit .

In operation the web server module transmits a SAVE response message to the states saving page in response to the SAVE request message.

The above exemplary embodiments of the present invention can be embodied as a program that can be executed by a computer system and executed by a general digital computer via a computer readable medium or via carrier waves such as in transmission over the Internet . Also data constructions used in the above embodiments can be recorded in a computer readable medium or in carrier waves via various devices.

Examples of the computer readable medium include a magnetic recording medium a ROM a floppy disk a hard disc etc. an optical recording medium a CD ROM a DVD etc. .

According to exemplary embodiments of the present invention an RUI client requests an external storage server to store the state information of an RUI and restores the original state of the RUI by using the stored state information. Accordingly a method of storing and restoring the state information of an RUI in a UPnP environment according to exemplary embodiments of the present invention is applicable to an HTTP based remote protocol model having stateless characteristics that do not allow the state information of an RUI to be saved.

Furthermore the exemplary embodiments of the present invention allow a user to select a desired storage server for storing the state information of a RUI. Also according to the exemplary embodiments of the present invention a user can select a web page to be restored from a list of restoring pages the state information of which is stored in a storage server.

While this invention has been particularly shown and described with reference to exemplary embodiments thereof it will be understood by those skilled in the art that various changes in form and details may be made therein without departing from the spirit and scope of the invention as defined by the appended claims and their equivalents.

