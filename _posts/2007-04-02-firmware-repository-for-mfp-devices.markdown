---

title: Firmware repository for MFP devices
abstract: A firmware repository includes an Extensible Markup Language (XML) description file. A system and method for managing the repository is described.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08019794&OS=08019794&RS=08019794
owner: Sharp Laboratories of America, Inc.
number: 08019794
owner_city: Camas
owner_country: US
publication_date: 20070402
---
Many electronic devices today include firmware. Firmware may be a software program or set of instructions programmed on a hardware device. The firmware may provide instructions which are executed to determine how the device operates. The firmware may be stored in memory of a hardware device. As updated firmware is developed the firmware stored in a device may be replaced or updated.

Existing solutions to manage the firmware FW of electronic devices such for example multifunction printing MFP devices have many limitations. MFP devices may perform imaging scanning printing copying and facsimile machine functions or some subset of these functions. FW updates may typically be distributed either on a CD or through a web site. Both the mechanisms have drawbacks. FW distribution through CD is a slow process. It takes time to create and ship the CDs for new firmware updates to individual customers. On the other hand FW distribution through a web site may be difficult for users to navigate.

In the following detailed description and in the several figures of the drawing like elements are identified with like reference numerals. The figures are not to scale and relative feature sizes may be exaggerated for illustrative purposes.

A firmware repository may provide a mechanism to distribute firmware releases and make them available to machine dealers and customers in a secure orderly and error free manner. A firmware repository may be located on a local resource such as a CD ROM network drive or a remote resource accessed through the Internet. diagrammatically depicts an exemplary operating environment in which a firmware repository may be utilized.

In one exemplary embodiment the new or updated firmware may be made available through a firmware repository hosted on a web server . Users with proper privileges may access e.g. to manage or browse this web repository through an HTTP or HTTPS connection via a web browser which may be running by way of example on a terminal or via the Internet which may be connected through a firewall to web server . Authorized persons may publish new firmware and remove or update existing firmware. The firmware may be obtained from a CD using a CD drive or from a network storage drive or from another firmware repository.

Customers users and dealers with required access privileges may access this web repository through a web browser to obtain firmware for a machine. In some applications access privileges may not be required so that the firmware update access is freely available to customers users.

Customer and dealers who are running a management gateway or printer administration utility PAU software application running on a console terminal or server located on a customer s intranet for example may have a local firmware repository . The terminal is connected on the intranet behind a firewall through which a connection to the Internet is made. A management gateway application and techniques for remote firmware management are described in pending application Ser. No. 11 670 875 entitled Remote Firmware Management for Electronic Devices filed Feb. 2 2007 the entire contents of which are incorporated herein by this reference. A PAU from Sharp Electronics for example is a networked printer management tool using standard Simple Network Management Protocol SNMP to monitor status and enable remote configuration of networked digital printer and copier devices. This exemplary PAU may be utilized by network administrators for monitoring all Sharp network connected printers and copiers. The utility keeps a constant status check on the devices warning when some action is necessary by the administrator for example if paper supply is low or toner supply is low or if a periodical service is due and alerting when a problem has occurred for example paper jam or toner exhausted. By utilizing the PAU network administrators can manage all digital printers and copiers remotely via the network from a single console. PAU users can access this local repository to add new firmware and update existing firmware. In the example illustrated in users of a PAU can obtain new firmware from a local CD a network drive and from the web firmware repository in order to update or install firmware on devices . The devices may be multifunction printer MFP devices for example. Thus PAU users will be able to add new firmware to the local repository from a web firmware repository by using a web browser e.g. a web browser running on a local terminal . In an exemplary embodiment the terminal may be connected to the console through an HTTPS or HTTP connection.

The firmware repository local to the PAU and the web firmware repository are independent of each other though they use the same technology to store locate and retrieve the firmware.

A manufacturer may release the new firmware also on CDs. A CD may have the firmware in a local repository . In an exemplary embodiment the PAU will be able to understand the structure of the CD repository. There may also be situations in which a CD may contain the firmware without any also being on a local firmware repository.

Authorized personnel e.g. those of a device manufacturer can create the CD with a local repository e.g. by using a software utility as described below.

In an exemplary embodiment of a firmware repository many or all the processes related to the firmware repository may be automated. Automation of the processes in this case may reduce human errors. Most of the processes related to the firmware repository may involve interaction with a computer or computer networks. In an exemplary embodiment one or more of the following exemplary processes may be carried out programmatically rather than manually. For example a user may accomplish these functions using a software program or utility in which the user initiates a given function and the software carries out the function using inputs provided by the user through a user interface.

5. modification of the existing properties of the firmware in the repository for example to change the release notes 

In an exemplary embodiment activities related to a firmware repository may be automated by a software utility developed using an API Application Programming Interface . For example an automation API may be called by to access the firmware repository and make changes to the repository. Those who intend to use the firmware repository in a manual way may do so by using the web browser or client application provided by a device manufacturer or dealer. The firmware repository may be accessed programmatically e.g. using an API called by a utility program to access and update the firmware repository. This will provide for automation so that the firmware repository may be managed programmatically e.g. using software utility programs which call an API.

The software utility and API called by the software utility may reside on a console or terminal such as laptop running utility API and or on console running utility program .

In an exemplary embodiment of a firmware repository repository automation is XML Extensible Markup Language based the firmware repository may be based on an XML schema which contains the following information 

In an exemplary embodiment the XML description file includes an information field specifying for each device model the location of the corresponding firmware file. This location may be on the same computer readable media as the XML description file or may be a different location. The firmware repository thus could be constructed without any firmware files A B N as the files may be located on another server or computer readable medium such as medium depicted in . As an example repository may be installed on server in and the firmware files may be located on CD or another remote web server.

An XML parser utility program such as parser may be running on a console used to access the firmware repository read the XML description file and manage or download firmware files for a given device such as device . The parser utility program is illustrated in as installed on server but may also be installed on consoles and for example.

An exemplary embodiment of a firmware repository is stored using an XML schema. An exemplary firmware repository may be accessed using one of the following methods in an exemplary embodiment 

1. Firmware Repository Web Service A firmware repository located on web may be implemented using web services. A repository web service can be accessed via a specialized web service API for programmatic access or through a web browser for manual access.

2. Traditional directory structure browsing User can access an URL and browse the directory structure to locate the firmware of interest and download it.

3. Software Application If firmware is distributed through CD then a software application may be used to create and view the repository on CD.

If the firmware repository is located on the network or on a local server then it can be accessed through any of the above mentioned methods.

In order to ensure that only authorized entities access the repository in an exemplary embodiment the firmware repository provides one or more of the following security options 

In an exemplary embodiment a firmware repository may support two types of users. General users or end users may have access to only browse the repository and download the firmware including a version matrix. Advanced or administrative users may have access to all the features including creation modification and update of the repository and user profile management.

An exemplary embodiment of a firmware repository may include techniques for notifying the registered users when new firmware updates become available. Users can be notified using email or other messaging methods like instant messaging SMS Simple Messaging Service MMS Multi media Messaging Service and paging.

As described above an XML description file in the firmware repository may include a version matrix for each model or model of devices. An exemplary embodiment of a version matrix is a matrix of version numbers of all the firmware for different components of the whole system. It also contains the interdependencies among the various components. A representation of an exemplary version matrix is depicted in the following table and in .

The first part of the table provides the version numbers of the firmware for different components. For example the version of the released MFP firmware package is 7.0. In this example the MFP firmware is made up five components Print Engine firmware Copier firmware Scanner firmware Fax firmware and Job Accounting Firmware. Components of the MFP may have different versions. In this case even though the MFP firmware version is 7.0 the Fax firmware version is 5.0.

The bottom half of the table in this example of a version matrix provides the compatibility matrix of the version of components. The columns represent the versions of new firmware components. The rows show the versions of old firmware that are compatible with the new firmware versions shown in the columns. For example Job Accounting version 4.0 in the new firmware is compatible with copier firmware version 6.5 or greater in the old releases.

This dependency relationship is represented as the XML schema and forms the version matrix. The version matrix is used in making decisions whether to update a particular component on not. For example if a MFP has Job Accounting firmware with version 3.2 and printer firmware with version 6.7 and someone decides to update the firmware of Job Accounting to 4.0 then he also has to update the print engine firmware to 7.0 otherwise Job Accounting firmware will not work properly.

The following is an exemplary sample XML schema for a firmware repository for example an XML schema for an XML description file as described above regarding .

The following is an exemplary sample XML description file for a firmware repository. This example relates to two particular device models identified as MX 3501N and AR M700U.

As illustrated in the foregoing example the XML description file may include information for each subcomponent of the system may include an identification of the firmware for that component as well as information such as the location of the subcomponent firmware file.

An exemplary embodiment of a repository for firmware updates may provide one or more of the following capabilities 

Well defined location and storage structure to archive the firmware updates for electronic devices e.g. MFP devices.

Automation of repository creation and the process for populating the repository with firmware updates.

For the devices with multiple sub components where each component requires a separate firmware there may be a need to update more than one firmware at the same time. Firmware for different components may have interdependencies. They may have dependency on the order in which the firmware for components is upgraded. Additionally they might have dependency across versions. A particular version of one component may only work with a particular version of firmware for another component. An exemplary embodiment of a firmware repository provides a structure which captures a matrix of firmware versions for different components and their interdependencies.

Algorithms to manage the repository e.g. removing elements purging the repository periodically and deleting the repository if needed.

Exemplary embodiments of a firmware repository and management system may include one or more of the following features 

Although the foregoing has been a description and illustration of specific embodiments of the invention various modifications and changes thereto can be made by persons skilled in the art without departing from the scope and spirit of the invention as defined by the following claims.

