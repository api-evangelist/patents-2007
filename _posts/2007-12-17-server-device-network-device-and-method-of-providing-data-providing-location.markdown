---

title: Server device, network device, and method of providing data providing location
abstract: A server device that provides a client device with one or more data storage locations of one or more sets of information about one or more datasets. The one or more sets of information about the one or more datasets are to be provided by one or more network devices. Each of the sets of information about the datasets is described in a structured format. The server device includes a data storage location acquiring unit that acquires the data storage locations of the sets of information about the datasets from the corresponding network devices, a data storage location management unit that manages the acquired data storage locations of the sets of information about the datasets; and a data storage location providing unit that provides the client device with the acquired data storage locations of the sets of information about the datasets.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09124501&OS=09124501&RS=09124501
owner: RICOH COMPANY, LTD.
number: 09124501
owner_city: Tokyo
owner_country: JP
publication_date: 20071217
---
This disclosure generally relates to a server device a network device a method of providing a data providing location a program for providing a data providing location and a recording medium and particularly relates to a server device a network device a method of providing a data providing location a program for providing a data providing location and a recording medium for use in a system in which a client device acquires a set of information about a dataset from a data storage location.

In recent years RSS Rich Site Summary has been used for publishing updated information of Web sites. RSS is an XML Extensible Markup Language based format for describing metadata such as title and summary of a Web site in a structured manner.

Updated information written in RSS can contain titles addresses headings summaries updated time etc. of Web site pages. RSS makes it possible for RSS subscribers to efficiently handle the updated information on many Web sites in a uniform format.

Some conventional multifunction machines have functions for providing device management information such as communication histories in RSS see Japanese Patent Laid Open Publication No. 2006 54732 Patent Document 1 also published as U.S. Application Publication No. 2006 0033950 A1 . Patent Document 1 discloses an RSS reader that runs on a computer serving as a client device. The RSS reader periodically polls RSS feeds in plural multifunction machines and thus collectively manages plural sets of device management information of the plural multifunction machines.

The term RSS feed as used herein may indicate the URL of the RSS source. The RSS source is information described in RSS format.

However according to Patent Document 1 a user of the RSS reader needs to register RSS feeds of the multifunction machines into the RSS reader. That is the user needs to find out each of the URLs of the RSS feeds of the multifunction machines. This might be very troublesome if the user needs to register a number of RSS URLs.

Similarly in the case where an administrator such as an IT manager manages a number of network devices and multifunction machines the administrator needs to find out and register all the RSS feed URLs of the managed network devices and multifunction machines which might be very troublesome.

In an aspect of this disclosure there is provided view a server device capable of correctly and easily registering a data storage location indicating the location of a set of information about a dataset provided by a network device the network device and a method of providing a data providing location.

In another aspect there is provided a server device that provides a client device with one or more data storage locations of one or more sets of information about one or more datasets. The one or more sets of information about the one or more datasets are provided by one or more network devices. Each of the sets of information about the datasets is described in a structured format. The server device comprises a data storage location acquiring unit that acquires the data storage locations of the sets of information about the datasets from the corresponding network devices a data storage location management unit that manages the data storage locations of the sets of information about the datasets acquired from the network devices and a data storage location providing unit that provides the client device with the acquired data storage locations of the sets of information about the datasets.

According to another aspect there is provided a network device that provides a set of information about a dataset described in a structured format. The network device comprises a specifying unit that specifies a server device that provides a client device with a data storage location of the set of information about the dataset and a providing unit that provides the server device specified by the specifying unit with the data storage location of the set of information about the dataset.

Embodiments of the present invention include a method a device a system a computer program a recording medium and a data structure to which an element or an arbitrary combination of elements of the present invention is applied.

Embodiments of the present invention can provide a server device capable of correctly and easily registering a data storage location of a set of information about a dataset provided from a network device the network device and a method of providing a data providing location.

Preferred embodiments of the present invention are described below with reference to the accompanying drawings. In the examples illustrated in the following embodiments an IT manager as an administrator of plural network devices such as multifunction devices which are capable of providing device management information as RSS feeds registers URLs of the RSS feeds of the network devices. The following embodiments provide a technique for facilitating registration of the URLs of the RSS feeds provided by the plural network devices into an RSS reader of a client device.

The processor controls the network device . More specifically the processor executes functions that are specific to the network device in combination with the device specific hardware . The processor is also used for executing Web server functions in the network device .

The work memory is used for executing software and also used as a temporary storage area for associated operations. The storage unit is an electrically rewritable storage medium such as a flash ROM. The storage unit stores software such as a control program for realizing the functions of the network device and a program of an embodiment of the present invention. The device specific hardware is specific to the network device . The input output circuit is used for connecting to the LAN .

The software includes a user interface layer an application layer and a service layer. The user interface layer provides users with user interfaces. The application layer provides application functions. The service layer controls the hardware to provide each of the applications with their specific functions.

The user interface layer includes device user interface UI and a Web UI . The device UI provides an operations panel of the network device with user interfaces. The Web UI provides a user of the network device with user interfaces for operating the network device from a Web browser of e.g. the PC .

The application layer includes a copier application a fax application a printer application and a scanner application . The copier application provides copier functions. The fax application provides fax functions. The printer application provides printer functions. The scanner application provides scanner functions.

The service layer includes a printing service a scanning service a network service and a memory service . The printing service controls a plotter unit included in the hardware . The scanning service controls a scanning unit included in the hardware . The network service controls the input output circuit . The memory service manages the work memory .

For example if a user gives an instruction to make a photocopy of an original document using the operations panel of the network device the device UI first receives the instruction from the user. Then the device UI provides an instruction of a copy operation to the copier application . According to the copy operation instruction from the device UI the copier application instructs the scanning service to scan the original document and the printing service to perform a printing operation. Thus the user can obtain a copy of the original document.

The Web screen providing unit receives through the network service a request from the Web browser of the PC being used by a user. The Web screen providing unit is configured to send based on the received request a Web page containing device management information to the PC thereby providing the Web page to the user.

The device management information may include various types of information items such as device status energy saving status error status toner level paper feed tray status and job history. Although these device management information items may be provided on a single Web page they are usually provided on different Web pages according to the types of the information items. For example the Web pages may include a Web page as a top page indicating general device status such as device status energy saving status and error generating status and another Web page indicating job history information.

The RSS feed providing unit receives through the network service a request from the RSS reader running on the PC being used by a user. The RSS feed providing unit is configured to based on the received request send an RSS feed containing the device management information to the PC thereby providing the RSS feed to the user.

More specifically the information contained in the RSS feed includes summaries of the device management information items and links to Web pages that provide details of the device management information items. Generally the information displayed by the RSS reader used by the user includes the summaries of the device management information items. To see the details of one of the device management information item the user follows the corresponding link which is displayed on the RSS reader to the Web page containing the details of the information item and displays the Web page provided by the Web screen providing unit by using the Web browser or a Web browser function of the RSS reader.

As in the case of the Web pages described above the information items to be provided in the form of RSS feed may be provided in a single RSS feed. However an RSS feed containing different types of information items is not convenient for users. Moreover RSS readers usually have a function for remixing contents of plural RSS feeds and displaying the remixed contents. It is therefore preferable that the information items be provided in different RSS feeds according to the types of the information items thereby allowing the user to use his her desired utilization method.

The OPML file providing unit is configured to provide through the network service an OPML file containing a list of all the RSS feeds of the RSS feed providing unit . The URL of the OPML file may be hereinafter referred to as the OPML feed. The contents of the OPML file may be hereinafter referred to as the OPML source.

The processor controls the server device . More specifically the processor executes functions that are specific to the server device in combination with the device specific hardware . The processor is also used for executing Web server functions in the server device .

The work memory is used for executing software read from the storage unit and also used as a temporary storage area for associated operations. The storage unit is a rewritable storage medium such as an HDD. The storage unit stores software such as a control program for realizing the functions of the server device and a program of an embodiment of the present invention. The device specific hardware is specific to the server device . The input output circuit is used for connecting to the LAN .

The software includes an application layer and a service layer. The application layer provides application functions. The service layer controls the hardware to provide each of the applications with their specific functions.

The application layer includes a DHCP application an RSS application and an SMTP application . The DHCP application provides DHCP functions. The RSS application provides RSS functions. The SMTP application provides mail receiving functions.

The service layer includes a network service and a memory service . The network service controls the input output circuit . The memory service manages the work memory .

The RSS feed providing unit receives through the network service a request from the RSS reader running on the PC being used by a user. The RSS feed providing unit is configured to send based on the received request an RSS feed containing device management information to the PC thereby providing the RSS feed to the user.

More specifically the RSS feed contains summaries of the device management information items and links to Web pages that provide details of the device management information items. Generally the information displayed by the RSS reader used by the user includes the summaries of the device management information items. To see the details of one of the device management information items the user follows the corresponding link which is displayed on the RSS reader to the Web page containing the details of the information item and displays the Web page provided by the Web screen providing unit of the network device by using the Web browser or a Web browser function of the RSS reader.

As in the case of the Web pages described above the information items to be provided in the form of RSS feed may be provided in a single RSS feed. However an RSS feed containing different types of information items is not convenient for users. Moreover RSS readers usually have a function for remixing contents of plural RSS feeds and displaying the remixed contents. It is therefore preferable that the information items be provided in different RSS feeds according to the types of the information items thereby allowing the user to use his her desired utilization method.

The OPML file providing unit is configured to provide through the network service an OPML file containing a list of all the RSS feeds to be provided by the RSS feed providing unit . The URL of the OPML file may be hereinafter referred to as the OPML feed. The contents of the OPML file may be hereinafter referred to as the OPML source.

The external RSS feed acquiring unit is configured to acquire an RSS feed containing device management information from the network device on the LAN through the network service .

The external RSS feed management unit is configured to hold the RSS feed acquired by the external RSS feed acquiring unit and provide the RSS feed to the RSS feed providing unit .

The external OPML file acquiring unit is configured to acquire through the network service an OPML file containing a list of all the RSS feeds of the network device on the LAN . The external OPML acquiring unit is also configured to provide information of the RSS feeds contained in the OPML file to the external RSS feed acquiring unit .

In an embodiment of the present invention the network devices which are connected to the LAN and are to be managed by the IT managers automatically register their RSS feeds into the server device . That is the RSS feeds of the network devices are collected into the server device . The IT manager can register the RSS feeds of the plural network devices by accessing the server device .

By providing the server device with a protocol server function necessary for the usual network device the network device to be managed can without having any special functions specify the server device as the destination to which the network device reports its RSS URL as described below.

In Step S the network service of the network device reads out the registered server address from the storage unit . In Step S the network service reports the RSS URL of the network device to the server device corresponding to the registered server address from the input output circuit through the LAN . In this way based on the registered server address the network device specifies the server device .

In Step S the network service of the network device requests a DHCP server i.e. the server device to assign an IP address to the network device from the input output circuit through the LAN . In Step S the network service receives a response indicating an IP address assignment result from the server device through the LAN and detects an IP address of the server device from the response. In Step S the network service stores as a registered server address the detected IF address of the server device in the storage unit .

In Step S the network service of the network device reads out the registered server address from the storage unit . In Step S the network service reports the RSS URL of the network device to the server device corresponding to the registered server address from the input output circuit through the LAN . In this way the network device specifies the DHCP server that assigns an IF address to the network device i.e. the server device .

In Step S the network service reads out the name of a registered server device the registered server name in this case the name of the server device from the storage unit .

In Step S the network service receives a name resolution result from the DNS server through the LAN and thus acquires an IP address of the server device .

In Step S the network service of the network device reports the RSS URL of the network device to the server device corresponding to the acquired IP address from the input output circuit through the LAN . In this way based on the registered server name the network device resolves the name by querying the DNS server and specifies the server device .

The server device executes the operation shown in the sequence diagram of when detecting the network device when receiving an ARP request or a request of IP address assignment according to DHCP protocol .

In Step S the server device sends a method getRSSUrl for acquiring the RSS URL of the network device as a SOAP request. In Step S the network device returns a SOAP response as a response to the SOAP request. The SOAP response contains the RSS URL of the network device .

The server device executes the procedure shown in the sequence diagram of when detecting the network device when receiving an ARP request or a request of IP address assignment according to DHCP protocol . The procedure shown in is based on HTTP which is a representative example of a REST I F architecture implementation. In this example HTTP GET is used for acquiring the RSS URL.

In Step S the server device sends HTTP GET. In Step S the network device returns an RSS URL of the network device as a response to HTTP GET. is a diagram showing exemplary configurations of REST information items exchanged between the network device and the server device . The REST information item of sent by the network device contains an RSS URL http 169.96.228.88 rssurl.html .

In Step S the network device sends the RSS URL to the server device based on SMTP. is a diagram showing an example of a configuration of mail information sent from the network device to the server device . The mail information shown in contains an RSS URL http 169.96.228.88 rssurl.html in the body of the mail.

In this way the RSS URL can be sent from the network device to the server device in the body of mail based on SMTP.

In Step S the network device sends the RSS URL to the server device based on SMTP. is a diagram showing an example of a configuration of mail information sent from the network device to the server device . The mail information shown in contains an RSS URL http 169.96.228.88 rssurl.html in the subject of mail.

In this way the RSS URL can be sent from the network device to the server device as the subject of mail based on SMTP.

The network device executes the operation shown in the sequence diagram of when connected to the LAN for example. In Step S the network device broadcasts an Address Resolution Protocol ARP request. In Step S the server device that has detected the ARP request sends an ARP response to the network device which originated the ARP request.

In Step S the server device queries the network device the source of the ARP request for an RSS URL. The above described SOAP I F REST I F or the like may be used in querying for the RSS URL. In Step S the network device returns an RSS URL as a response to the query.

According to the sequence diagram of after sending the ARP response to the network device which originated the ARP request the server device queries the source of the ARP request for an RSS URL and thus automatically acquires the RSS URL of the network device connected to the LAN .

The server device includes a management table managing the network devices to be managed. The server device updates the management table as described below. is a flowchart showing an example of processing by the server device using a timer.

The processing shown in the flowchart of is executed after the IT manager selects a timer entry screen for example. In Step S the server device displays the timer entry screen. The device specific hardware of is used for timer entry.

In Step S the server device determines whether a timer value has been entered. The operation in Step S is repeated until a timer value is entered. If a timer has been activated then in Step S the server device sets the timer value. In Step S the server device starts the timer.

When the timer reaches the set timer value the server device executes an operation shown in the flowchart of . is a flowchart showing an example of a management table update operation.

In Step S the server device sets N a network device identifier to 0. In Step S the server device queries the network device corresponding to N whether the network device corresponding to N supports RSS.

If the network device corresponding to N does not support RSS the process proceeds to Step S wherein the server device deletes the network device corresponding to N from the management table. Then the process proceeds to Step S. On the other hand if the network device corresponding to N supports RSS the process proceeds to Step S.

In Step S the server device determines whether another network device is present. If another network device is present then in Step S N is incremented by 1. Then the process returns to Step S. On the other hand if another network device is not present then in Step S the server device restarts the timer.

In Step S the network device determines whether the report timer has timed out. The operation in Step S is repeated until the network device determines that the report timer has timed out. If the network device determines that the report timer has timed out then in Step S the network device provides an RSS feed to the server device . In Step S the network device restarts the report timer. Then the process returns to Step S. With the processing using the report timer shown in the network device can provide the RSS feed to the server device every time the report timer times out.

On the other hand if an RSS feed has not been provided from the network device then in Step S the server device sets N a network device identifier to 0. In Step S the server device determines whether an expiration checking timer for the network device corresponding to N has timed out.

If the server device determines that the expiration checking timer for the network device corresponding to N has timed out the process proceeds to Step S wherein the server device deletes the network device corresponding to N from the management table. Then the process proceeds to Step S. On the other hand if the server device determines that the expiration checking timer for the network device corresponding to N has not yet timed out the process proceeds to Step S.

In Step S the server device determines whether another network device is present. If another network device is present then in Step S N is incremented by 1. Then the process returns to Step S. On the other hand if another network device is not present the process returns to Step S.

For example in the case where the report timer is set to 10 minutes and the expiration checking timer is set to 60 minutes the expiration timer does not time out in Step S as long as the network device is activated. Accordingly the network device continues to be managed.

The server device can store the RSS feeds of the network devices to be managed in an OPML format. is a flowchart showing an example of processing for storing the RSS feeds in an OPML format.

In Step S the server device sets N a network device identifier to 0. In Step S the server device acquires the RSS feed of the network device corresponding to N. In Step S the server device adds the acquired RSS feed of the network device in an OPML format.

In Step S the server device determines whether another network device is present. If another network device is present then in Step S N is incremented by 1. Then the process returns to Step S. On the other hand if another network device is not present the processing shown in the flowchart of ends.

The server device can acquire the RSS sources from corresponding RSS feeds of the network devices to be managed and store the RSS sources in an RSS format. is a flowchart showing an example of processing for storing the RSS sources.

In Step S the server device sets N a network device identifier to 0. In Step S the server device acquires the RSS source of the network device corresponding to N. In Step S the server device adds the acquired RSS source of the network device in an RSS format.

In Step S the server device determines whether another network device is present. If another network device is present then in Step S N is incremented by 1. Then the process returns to Step S. On the other hand if another network device is not present the processing shown in the flowchart of ends. is an example of the acquired RSS sources of plural network devices stored in an RSS format.

The server device can provide not only the device management information but also other information e.g. company news as an RSS feed. The server device can import information of the RSS sources of external general servers and provide the imported RSS source information.

The present invention is not limited to the above described embodiments and variations and modifications may be made without departing from the scope of the invention.

The present application is based on Japanese Priority Application No. 2006 350481 filed on Dec. 26 2006 with the Japanese Patent Office the entire contents of which are hereby incorporated by reference.

