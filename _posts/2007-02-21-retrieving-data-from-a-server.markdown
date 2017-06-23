---

title: Retrieving data from a server
abstract: A system includes a server and a controller embedded in a device. Both the server and the embedded controller are capable of communicating over a computer network. The embedded controller sends a command to the server over the computer network that identifies an instance of the device. In response, the server identifies the instance of the device based on the command, retrieves data that is specific to the instance of the device, and send the data to the embedded controller over the computer network.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=07937370&OS=07937370&RS=07937370
owner: Axeda Corporation
number: 07937370
owner_city: Foxboro
owner_country: US
publication_date: 20070221
---
This patent application is a continuation and claims the benefit of priorty under 35 U.S.C. 120 of U.S. patent application Ser. No. 09 667 737 filed on Sep. 22 2000. The disclosure of U.S. patent application Ser. No. 09 667 737 is considered part of and is incorporated by reference into the disclosure of this application as if set forth herein in full.

This invention relates to a controller embedded in a device an embedded controller that retrieves data from a remote server for a specific instance of the device.

A device may contain an embedded controller such as a microprocessor to monitor and control its operation. Any type of device may have an embedded controller including but not limited to home appliances such as washing machines dishwashers and televisions and manufacturing equipment such as robotics conveyors and motors.

Embedded controllers also referred to as embedded devices are often connected to an internal network such as a local area network LAN with an interface to the Internet. Other devices on the internal network may communicate with the embedded controllers over the internal network. However the embedded controllers are not generally addressable from the Internet.

In general in one aspect the invention is directed to a controller embedded in a device for retrieving data from a server. The controller sends a command to the server that identifies an instance of the device and receives from the server and in response to command data that is specific to the instance of the device.

This aspect of the invention may include one or more of the following. The command may include an operational parameter for the device and the data may include an updated value for the operational parameter. The command may include plural operational parameters for the device and the data may include updated values that differ from current values of the operational parameters.

The data may include a list of operational parameters. In this case the embedded controller sends an second command to the server which includes operational parameters from the list and receives from the server and in response to second command updated values of one or more of the operational parameters included in the second command. The data may include a list of operations to be performed by the controller. In this case the embedded controller parses the operations from the list and performs the operations from the list.

The data may include a configuration file for the device. The command may identify the instance of the device by a device type and or one or more of a serial number and a universal unique identifier. The embedded controller may send the command to the server periodically. The server may run the Hypertext Transfer Protocol and the command may contain Extensible Markup Language code.

In general in another aspect the invention is directed to a server for sending data over a network to a controller embedded in a device. The server receives a command from the embedded controller identifies an instance of the device from information in the command retrieves data that is specific to the instance of the device and sends the data to the embedded controller.

This aspect of the invention may include one or more of the following features. The command may include a device type and or one or more of a serial number and a universal unique identifier. The instance of the device may be identified based on the device type and or one or more of the serial number and the universal unique identifier. The server may parse the device type and one or more of the serial number and universal unique identifier from the command prior to identifying the instance of the device.

The command may include an operational parameter for the device. The data may include an updated value of the operational parameter. The data may include a list of operational parameters for the device. The server receives a second command from the embedded controller which includes an operational parameter from the list of operational parameters obtains an updated value of the operational parameter and sends the updated value of the operational parameter to the embedded controller.

The data may include a list of operations to be performed by the embedded controller. The data may include a configuration file for the device. The server may receive the data specific to the instance of the device and store the data in memory from which it is retrieved. The data specific to the instance of the device may be received via a web page generated by the server. The server may run the Hypertext Transfer Protocol and the command may contain Extensible Markup Language code.

In general in another aspect the invention is directed t a system that includes a controller embedded in a device that is capable of communicating over a computer network and a server that is capable of communicating over the computer network. The embedded controller sends a command to the server over the computer network that identifies an instance of the device and in response the server i identifies the instance of the device based on the command ii retrieves data that is specific to the instance of the device and iii sends the data to the embedded controller over the computer network.

This aspect of the invention may include one or more of the following features. The embedded controller is not remotely addressable from the computer network. The computer network is the Internet. The server runs the Hypertext Transfer Protocol and the command may contain Extensible Markup Language code.

Other features and advantages of the invention will become apparent from the following description including the claims and drawings.

Device is connected to an internal network such as a LAN. A router or modem couples internal network to an external network such as the Internet World Wide Web Web . External network runs TCP IP Transmission Control Protocol Internet Protocol or some other suitable protocol. Network connections are via Ethernet telephone line wireless or other transmission media.

External network contains a server which is a computer or any other processing device. Server communicates with embedded controller over external network and internal network . Embedded controller has a local IP Internet Protocol address that can be resolved within internal network . However this local IP address may not be recognizable by devices on external network such as server . As such server may not be able to directly address device .

Embedded controller runs software which includes web client application and operating software . Web client application includes a TCP IP protocol stack that allows embedded controller to communicate over external network . Device operating software provides an interface between Web client application and a database . Through device operating software embedded controller retrieves data stored in database and stores data in database .

Database is stored in a memory on device or internal to embedded controller . Database stores data including operational parameters configuration files and identification information for device .

The operational parameters constitute settings and or control instructions for the device which are implemented by embedded controller . The types of operational parameters that are stored in database depends on the nature of device . For example if device is a heating cooling system the operational parameters may include temperature levels humidity levels airflow controls vent duct open close controls and fan motor speed settings. A configuration file is a file that contains a set of one or more operational parameters for an instance of device .

What is meant by instance is the specific identity of device as distinguished from other identical devices. The identification information stored in database identifies the instance of device . This identification information includes but is not limited to data identifying the type of the device a common or friendly name for the device the manufacturer of the device the model name of the device the model number of the device the serial number of the device and a universal unique identifier UUID for the device.

The device type specifies a uniform resource locator URL for the device which includes the name of the device. This information identifies a Web site that is associated with and generated by server for the device. For example a device type might be 

Server is a computer that runs HTTP Hypertext Transfer Protocol . Server includes a controller such as a microprocessor for executing software to perform the functions described below. To avoid confusion in terminology the following reads as though software in controller of server performs the functions.

Server executes Web server software to communicate over external network . Web server software also hosts a Web page associated with device . The Web page not shown is displayed on the computer of a user such as the owner of device who may input updated operational parameters for the device. These input updated operational parameters are transmitted to Web server software over external network . Web server software stores the updated parameters in database .

Web server software stores and retrieves data in database using application logic . Application logic is software for accessing database using the CGI Common Gateway Interface protocol. CGI is a well known protocol for accessing a database. The operational parameters can be stored in database individually or as part of a configuration file for an instance of device .

Database is stored in a memory which is inside of or external to server . Database stores data associated with device including the operational parameters noted above. Other data that may be stored for device is described below.

Embedded controller executes software to retrieve data such as operational parameters from remote server . Server executes software to send the data to embedded controller . shows these processes in detail. The left half of titled Embedded Controller shows process performed by embedded controller and the right half of titled Server shows process performed by server .

Process generates and sends a command to server . the command or a modified version thereof is sent by embedded controller to server periodically. It is through this command that embedded controller polls server to determine if they are any new updated operational parameters for device .

The command includes data identifying device . The data identifies the specific instance of device and includes a device type field and one or both of a device serial number field and a device UUID. The command may also include the common name field the manufacturer name field the model name field and the model number field as set forth above.

The command may be either an HTTP GET command or an HTTP post command. The data included in those commands is similar with the difference being that the HTTP GET command retrieves a document such as a configuration file that contains operational parameters and the HTTP POST command retrieves individual operational parameters. An example of an HTTP GET command is shown in Appendix A and an example of an HTTP POST command is shown in Appendix B.

The HTTP POST and GET commands shown in appendices A and B contain XML eXtensible Markup Language commands. XML is a self describing computer language in the sense that fields in the XML code identify variables and their values in the XML code. For example as shown in the Appendices the manufacturer field identifies a manufacturer e.g. Sony and is delineated by to indicate the start of the field and to indicate the end of the field. XML is used because it can be generated parsed and read relatively easily by server and embedded controller .

As noted the GET command is used to retrieve a document from server . The document to be retrieved corresponds to the fields in the GET command in particular to the device type serial number and or UUID fields. By contrast the POST command is used to retrieve individual operational parameters. The operational parameters that are to be retrieved are listed in the POST command itself. For example as shown in Appendix B the operational parameters include airflow humidity motor and vent values for the fictitious widget device. the current values of these parameters are specified in the POST command shown in appendix B as follows 

As shown both the POST and GET commands include the URL of the device in the device type field. As described below this directs server to a Web site associated with device and thereafter in the case of a GET Command to retrieve a specific Web page that is generated by server for the device. It is noted that since the POST command retrieves parameters not a document like the GET command the POST command need not include a URL of the device.

Referring back to process in server receives the command from embedded controller . Process identifies the command as either a POST or GET command based on a header such as POST CONTROL HTTP 1.1 see the headers in Appendices A and B in the command. Process uses an XML parser to parse the various identifying fields such as device type serial number and UUID from the command.

Process identifies the instance of device based on the information parsed from the command. That is process uses the device type serial number and UUID field information to identify the instance.

The remaining identification information from the command is used to narrow the search through database down to data for the specific instance of device . The device serial number and or UUID are used to retrieve operational parameters specific to device .

Once the appropriate data has been identified process retrieves that data using application logic . Process compares the values of the operational parameters to those included in the POST command. If the values are the same process returns an indication that there are no new updated values for device . If the values of the operational parameters are different process adds the appropriate updated value fields to the POST command and sends the POST command with the updated operational parameters back to embedded controller . Thus only those operational parameters that differ from their original values are returned to embedded controller in the POST command.

As was the case above with the POST command the remaining identification information from the command is used to narrow the search through database down to data for the specific instance of device . In particular the device serial number and or UUID are used to retrieve a configuration file that is specific to device . Process then sends the configuration file to embedded controller . The configuration file may be a Web page identified by the URL in the device type field. This Web page is generated by server using parameters stored in database and then sent to device . It is noted that the complete Web page itself need not be stored. Alternatively the GET command may retrieve separate configuration files and Web pages.

Process in embedded controller receives the data operational parameters or configuration file from server in response to sending the command. Process then uses the data to update reset device . For example if device is a heating system a new operational parameter may be a new temperature setting for its thermostat. In this example embedded controller sets the new temperature accordingly. If the device is a television a new operational parameter may indicate that certain pay television stations are now available. In this case embedded controller performs any appropriate decoding descrambling functions on the television signal.

Referring to process in embedded controller begins by sending a command to server . The command in this case is an HTTP GET command since it is requesting a document not individual operational parameters. The document is an XML document that contains a list of operational parameters to be updated. Using this document embedded controller can change the operational parameters that it periodically updates.

Process in server receives the command from embedded controller parses the command using an XML parser to obtain the information specific to the instance of device and identifies the appropriate document based on this information. As before the information that identifies the instance of device includes among other things the device type its serial number and its UUID. Process retrieves the document containing the list of operational parameters to be updated and sends the document back to embedded controller .

Process in embedded controller receives the document from server parses the operational parameter to be updated from the document and formulates a POST command to send to server . The command is formulated using a command template not shown into which process inserts the operational parameters parsed from the document. Process sends this second command to the server. At this point processes and operate in the same manner as processes and respectively when used with a POST command. Accordingly the details of processes are not repeated here.

This alternative embodiment may be generalized further. For example rather than simply retrieving a list of operational parameters embedded controller may retrieve from server a list of operations that it is to perform. For example that list may contain operational parameters to be updated times at which the updates are to occur a schedule of diagnostic tests and the like. Any operation that may e performed by embedded controller may be included on the list.

The process for retrieving the list of operations is identical to processes and save for the contents of the list itself. The actions that embedded controller takes once it has the list i.e. depend on the contents of the list. For example the list might specify that parameters are to be updated every hour and may also contain a list of parameters to be updated. The list may contain XML commands which can be parsed by embedded controller . Thus embedded controller reads the commands in the list and performs the appropriate operations with respect to device .

Processes and are not limited to use with the hardware software configuration of they may find applicability in any computing or processing environment. Processes and may be implemented in hardware e.g. an ASIC Application Specific Integrated Circuit and or an FPGA Field Programmable Gage Array software or a combination of hardware and software.

Processes and may be implemented using one or more computer programs executing on programmable computers that each includes a processor a storage medium readable by the processor including volatile and non volatile memory and or storage elements at least one input device and one or more output devices.

Each such program may be implemented in a high level procedural or object oriented programming language to communicate with a computer system. Also the programs can be implemented in assembly or machine language. The language may be compiled or an interpreted language.

Each computer program may be stored on a storage medium or device e.g. CD ROM hard disk or magnetic diskette that is readable by a general or special purpose programmable computer for configuring and operating the computer when the storage medium or device is read by the computer to perform processes and .

Processes and may also be implemented as a computer readable storage medium configured with a computer program where upon execution instructions in the computer program cause the computer to operate in accordance with processes and .

The invention is not limited to use with the protocols and standards described above. For example Web server may use Java Servlets ASP Active Server Pages and or ISAPI Internet Server Application Programming Interface to communicate with application logic instead of or in addition to CGI. The commands sent by embedded controller and or server e.g. in are not limited to HTTP GET and POST commands. Any commands and or requests for requesting and receiving data may be used.

The data transferred to embedded controller by server is not limited to operational parameters or configuration files. The data may include for example a schedule of actions to be performed by device that is based on information pertaining the owner of the device. For example owner preferences may be stored in database . The instance specific data may be used by server to correlate the owner of the device to the appropriate preferences. These preferences then may be transmitted back to device to control the operation thereof.

The original parameters sent by embedded controller to server may be used by server to calculate new updated parameters based on data stored in database . Thus the invention is not limited to simply retrieving updated data but may also include calculating new data based on currently available data.

The documents and commands described above are not limited to XML format. any computer language may be used for the commands. The documents may be in any format for example HTML Hypertext Markup Language documents may be used. In addition the invention is not limited to use with the Web Web servers and the like. The servers and embedded controllers described herein may be the same type of general purpose computers appropriately programmed or different devices.

