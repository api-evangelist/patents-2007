---

title: Virus detection in mobile devices having insufficient resources to execute virus detection software
abstract: A virus scanning system which scans a mobile device/mobile device for files containing viruses even if the files are not executable on the mobile device. Corrective actions such as removing the files can be performed once the viruses are detected. As a result, viruses which are not executable (as being designed for other mobile device types) can also be detected and removed from mobile devices. According to another aspect, a common interface is provided when a virus scanning program requests data from mobile devices, and the computer is provided with different remote application programming interfaces suited to retrieve the specified data from the corresponding mobile devices. As a result, the computer can be extended to integrate scanning of new device types easily. According to one more aspect, a scanning program retrieves only data portions required for continuing the scan operation. According to yet another aspect, the program modules and virus definitions for scanning are received from a server on a network.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=07945955&OS=07945955&RS=07945955
owner: Quick Heal Technologies Private Limited
number: 07945955
owner_city: Pune, Maharastra
owner_country: IN
publication_date: 20070911
---
The present application claims priority from the following pending Indian patent application which is incorporated in their entirety into the present application application Ser. No. 2073 MUM 2006 filed on Dec. 18 2006 naming as inventor Sanjay Sahebrao Katkar entitled VIRUS DETECTION IN MOBILE PHONE TYPE DEVICES IN WHICH VIRUS DETECTION SOFTWARE IS EXECUTED EXTERNALLY 

The present invention relates generally to virus detection systems and more specifically to a method and apparatus for detecting viruses in mobile phones type devices in which virus detection software is executed externally.

Virus detection software refers to program s which scan examine data on a target device for existence of any viruses on the target device. A virus generally refers to a software code data which gets installed on target devices often without the knowledge of the user of the target device and is often in the form of part of a a file present on the non volatile memory. The file can be executable in which case processing resources can be wasted or features otherwise available on the target device may be impacted or mere data wasting storage resources on the target device.

There are several scenarios in which virus detection software is executed external to the target device being scanned. For example virus detection software is often executed on a computer system to scan mobile phone type devices such as mobile phones PDAs etc. example target devices often since such types of devices have insufficient resources storage and or processing capacity to execute virus detection software.

Such target devices are increasingly vulnerable to virus attacks. For example mobile phones are increasingly being provided with features such as ability to access electronic mail and world wide web multi media messaging services MMS games short message services SMS desktop applications etc. Due to such connectivity applications mobile phones or mobile devices in general are increasingly more vulnerable to virus attacks. Furthermore the virus can spread from one mobile phone to another thereby infecting additional mobile phones. Accordingly it is generally desirable to at least detect the presence of the viruses on mobile phones.

According to one prior approach detection of viruses in a mobile device is performed by connecting the mobile device to a computer having relatively larger memory and processing power and running a virus scan software in the computer. In one embodiment different virus scanning software programs are implemented for corresponding operating environments e.g. operating system or model of the mobile phone on the computer. Such a fragmented approach leads to several inefficiencies such as increased cost of development potentially not detecting files of viruses which are designed for other operating environments etc.

A virus scanning program provided according to an aspect of the present invention scans a mobile device e.g. mobile phone for files containing viruses even if the files are not executable on the device. Corrective actions such as removing the files can be performed once the viruses are detected. As a result viruses which are not executable as being designed for other device types can also be detected and removed from the devices. Further cost effort of procuring and loading copy of virus scan program into each mobile device is avoided.

According to another aspect a common interface is provided when a virus scanning program requests data from mobile devices and the computer is provided with different remote application programming interfaces suited to retrieve the specified data from the corresponding devices. As a result the computer can be extended to integrate scanning of new device types easily.

According to one more aspect a scanning program retrieves only data portions required for continuing the scan operation. Thus the scan operation can be completed without copying the entire file locally to the computer on which the scanning program is executed.

According to yet another aspect the program modules and virus definitions for scanning are received from a server on a network.

Several aspects of the invention are described below with reference to examples for illustration. It should be understood that numerous specific details relationships and methods are set forth to provide a full understanding of the invention. One skilled in the relevant art however will readily recognize that the invention can be practiced without one or more of the specific details or with other methods etc. In other instances well known structures or operations are not shown in detail to avoid obscuring the features of the invention.

Wireless network provides connectivity between mobile phones A Z using various standards such as GSM CDMA etc. Each mobile phone A Z transfers voice signal and or data according to the protocol defined by the corresponding standards. Each mobile phone may also be provided with ability to communicate using technologies such as USB connection Infra Red Bluetooth and WiFi or wired LAN connection to communicate with other devices systems.

Personal computer PC provides a platform on which virus scan software implemented according to an aspect of the present invention can be executed and mobile phones  Z can be scanned for viruses. In addition PC may facilitate operations such as configuring mobile phones uploading a new application providing a new feature configuring the present settings uploading a phonebook data and operation of the mobile phones through graphical user interface provided in the PC using an appropriate physical protocol interface provided to the corresponding mobile phone as is well known in the relevant arts .

Mobile phones A Z enable telephone calls to be made received using wireless network . Each mobile phone may have a corresponding different operating environment operating system such as Symbian OS from Symbian Ltd. WIN Ce from Microsoft Corporation and modifications to such operating systems as suited for different model of the mobile devices etc . Each mobile phones A Z runs a desired application providing features such as multimedia accessing web application file transfer massaging services etc. Mobile phones communicate and exchange data using wireless network . The data exchange may be in the form of messages SMS MMS and other data exchange features provided by the corresponding network standard noted above.

Mobile phones A Z receives viruses through MMS SMS Blue Tooth connection etc. The viruses while propagating may land up or infects a mobile phone that is having different operating environment. Such viruses may not be able to spread further from the corresponding mobile since it is designed to be executed on a particular type of operating environment for a virus to spread further it needs to execute itself in the mobile to spread to other mobile phones . Thus the virus file may remain saved on the mobile phone as it is.

The manner in which the virus detection is performed including detection of such unwanted files using PC is described below in further detail.

In step computer establishes communication with a mobile device mobile phone sought to be scanned. Communication may be established by connecting the mobile phone to the PC on a physical port such as USB RS232 and proprietary physical protocol interfaces etc. Various software modules e.g. drivers may be run in the mobile phone to facilitate access to the content in the mobile phone based on or inherent to the provided communication.

In step computer retrieves a portion of a file needed to continue scanning for detecting a set of viruses. In general a designer of the scan program chooses the set of viruses to scan can be a single virus or more and the nature format of the data representing the viruses determines the amount of data and the location of the data in the files that is required to continue scanning. Thus a designer of the scanning program needs to understand the content of the virus files to determine the specific location in the file and the amount of data required.

As described in sections below the file portion may be retrieved using API functions provided for each mobile phones for accessing the data. The API function may retrieve the data from a specified location. In one embodiment header portion of the file is retrieved first. The retrieved portion may be stored in a buffer.

In step computer scans the portion for the set of viruses. Scanning may be performed consistent with the understanding of the nature format of data representing the set of viruses and can be performed in a known way. Computer may compare the content of the buffer with a already available strings sequence of binary bytes in one embodiment to determine some conditionally the presence of a corresponding virus. For example a file header may be compared with known file header formats and each corresponding field in the file header may be checked for file type size etc. Based on file type determined by the contents of the header the set of viruses to scan the corresponding file may be determined. Also based on the file type and certain header bytes the portion of the file and the amount of bytes data to be scanned for viruses may be determined.

In step computer determines if more data is needed in the file to detect any of the set of viruses. For example based on the content of the header or the portion of the file thus far examined computer may determine if additional portion is needed to detect the set of viruses. As an illustration one type of virus may attach itself towards the end of the content in an executable file and accordingly the end portion may be determined to be such additional portion. If additional portion is needed control transfers to step else to step .

In step computer retrieves the additional portion of the file containing the required data and control passes to step . The additional portion from the specified location may be retrieved again using API calls as described in the examples scenarios in sections below. With reference to above example computer may retrieve the end portion of an executable file as additional portion.

In step computer determines whether any virus was found based on the data scanned thus far for a file. Again the content of the retrieved data may be compared with pre specified data in making such a determination. If the determination indicates the presence of a virus control passes to step or else to step .

In step computer performs a desired action for the detected virus. For example computer may delete the portion determined to be containing the virus or the entire file. The flow chart ends in step .

Due to the above described approach viruses can be detected while retrieving limited data instead of entire file from mobile phones. In addition the flow chart of can be repeated for different sets of viruses potentially designed only for execution on other i.e. not the one implemented in the present phone being scanned operating environments as described in further detail in sections below.

The description is continued with respect to the details of an example embodiment of mobile device A which supports the above described features of computer .

Driver provides electrical physical and protocol interfaces using which bits of data can be transmitted and received to from computer . The interfaces may specify various aspects such as signal levels bit rates command interchange requirements etc. consistent with the specific interface implementations employed in computer . Path may be of type USB Serial port Ethernet etc. The extracted data during reception is provided to file access interface using any of the data transfer technique. Similarly driver transmits data received from file access interface .

Operating system may control access to and allocate various resources available within mobile phone A to various entities user applications file access interface etc. executing in mobile phone A. Different mobile phones can be implemented with different operating systems potentially provided by same different vendors and the noted entities are generally designed consistent with the interface provided by operating system to access the desired resources.

Data access interface represents set of program interfaces for accessing data from memory . Data access interface receives a request or command from driver and performs requested operation such as opening a file retrieving desired portion of the data either of a file or previously stored MMS SMS from memory write data into memory etc. and performs the corresponding action by interfacing with operating system . Data access interface may be interfaced to driver using various service routines interrupt service routines pipes etc. supported in operating system though not shown as is well known in the relevant arts.

Memory may store data in various formats and provide access for writing and reading the data in the corresponding format. For example memory may store some data representing pre specified images program files representing operating system portions or user applications etc. in a file system format structure as individual files and facilitate data access through various file access program interface.

The data representing SMS MMS etc. may also be stored as files. For example all SMS may be stored in one file or each SMS may be stored in an individual file. APIs are often provided to access an individual or group of messages from such file formats and may thus be used for scanning.

Memory may also contain viruses written designed for operating system and also viruses designed for operating system other than . The manner in which all such viruses in memory may be detected in PC is described below with reference to .

User interface may provide an interface to a user for monitoring the status of scan operation as well as provide any necessary inputs. For example virus scan program may prompt the user to input data for confirming operations such as delete modify scan etc.

Driver operates similar to and cooperatively with driver described above. Driver transmits on path the requests for desired data portions received from RAPI and receives the requested data in response. The received data is provided to remote application program interface RAPI .

Remote application program RAPI represents a set of program logic code corresponding to functions or procedures to generate command strings to access memory . The program logics are implemented compliant with the requirements of program logic in data access interface . Often RAPI for each mobile phone is provided by the mobile phone vendor for accessing mobile phones through PC .

Example set of program logics functions are listed in . The set of program logics are provided for mobile phone with Window CE based operating environment. Each row contains a function call in first column and description of the action performed by the corresponding function call in second column . For example details in row indicates a function call CeReadFile and the corresponding action indicate that the function reads the data from a file starting at the position indicated by the file pointer. The remaining rows are not described in the interest of conciseness.

Continuing with respect to data access modules invokes the program logics e.g. corresponding to the functions of in RAPI to retrieve a desired portion of data requested by virus scan module . The data received in response is stored in memory buffer by interfacing with operating system services . In addition to data retrieval data access module may also enable virus scan module to perform actions such as delete file write to a file etc. by interfacing with RAPI .

Virus definitions may contain data strings or other suitable logic which identify each virus type. The set may contain strings representing viruses executable on all possible operating environments. Though not shown in the Figure the definitions can be updated periodically as more viruses are discovered.

Virus scan program detects viruses in mobile phone A according to an aspect present invention. Virus scan program interfaces with data access module for retrieving file data in mobile phone . Virus scan program may operate in accordance with described above in retrieving only portions of data as required for detecting a set of viruses chosen for each iteration. However alternative approaches e.g. copying the entire file to local storage may be employed without departing from the scope and spirit of several aspects of the present invention.

According to an aspect of the present invention virus definitions contains the definitions of all viruses whether executable in specific operating environment mobile device type or not. Accordingly virus scan program can scan each mobile device for all known viruses irrespective of whether the data file corresponding to the virus is executable or not on the specific mobile device. Once virus data files are detected a suitable action such as deleting the data file can be performed to free up storage space on the target mobile device scanned .

According to another aspect of the present invention an approach is chosen which facilitates the virus scan program to easily scan mobile devices of different operating environments as described below in further detail.

In step computer determines a type of the mobile device sought to be scanned. The mobile device may be configured to communicate the ID upon establishment of the connection with the PC and the type may be determined based on the received ID. Alternately a user may provide the corresponding information through appropriate user interface graphical display key board etc. as represented by user interface .

In step computer selects a device interface providing connectivity with the determined type. The set of interface programs providing connectivity with the corresponding device types may be stored in a local memory. In one embodiment a set of program modules are provided by the mobile device vendor in the form of SDK software development kit . The SDK contains a set of application program interface APIs and the appropriate API can be selected based on the determined device type.

New set of library APIs and drivers may be added with the help of SDK to support a new model of mobile devices. Such new set of API are often provided by the corresponding mobile device vendors along with the mobile device. The user using the mobile device connected to PC may install appropriate drivers provided by the device vendor.

In step computer retrieves the content of a file of the device using the selected device interface. Corresponding API may be used to retrieve desired content portion of the file. The retrieved portion may be stored in a local buffer for scanning. The approach of can be used to retrieve only portion of the file. Alternatively the file data can be copied locally before scanning the data for virus.

In step computer scans the file for the viruses of all device types consistent with the definitions in virus definitions . Scanning of the retrieved content may be performed using any of the scanning technique. In step computer performs desired actions e.g. deleting repairing or cleaning of the file if infected with virus based on the results of the scan. The flow chart ends in step .

Thus by integrating different SDKs into computer multiple mobile device types can be easily scanned using a single virus scan program. In addition since the virus definitions can contain information of all types of the viruses any type of virus even if its designed for different mobile operating environment can be reliably detected and removed from mobile devices.

Another aspect of the present invention facilitates easier integration of additional mobile device types by having the scan program use a common interface to interface with the various SDKs as described below in further detail.

Multi data access module provides to virus scan module universal common library functions facilitating access of desired data in mobile phones A Z irrespective of phone type. Universal library functions is designed facilitate data access required for virus scan. For example multi data access module may contain function calls to enable file access SMS access MMS access and data source containing information such as mobile phone type make model and other properties of mobile phone access.

In one embodiment the provided library functions include but not limited to OpenFile ReadFile WriteFile CloseFile GetFileSize GetFileAttributes DeleteFile RenameFile FindFirstFile FindNextFile etc. each with self explanatory label. Similarly for SMS access and MMS access the library may contain functions such as GetMessageProperties like time stamp number sent or received from etc. DeleteMessage to delete message from storage GetSMSMessage GetMMSFile etc.

Universal library functions in turn invoke the program logics in one of RAPIs A J depending on the mobile phone type sought to be scanned to retrieve data from the corresponding mobile. The type of mobile device that is being scanned may be obtained from user interface based on appropriate user inputs or through device ID sent through the physical interface .

Virus scan module scans the content of memory buffer as described in . Physical interface provide physical connectivity to mobile phones A Z. The physical interface may represent a USB port serial Port ethernet port wireless bluetooth port etc. through which mobile phones are connected to PC .

Download module and network interface enable mobile device to dynamically retrieve various program logics and virus definitions from the web as described in further detail in sections below. Broadly download module represents a program logic for retrieving the applicable program logics and virus definitions and storing replacing the same in virus scan module and virus definitions .

On the other hand network interface provides the physical electrical and protocol interfaces necessary for a computer to exchange data with a server over a network. In one embodiment network interface may be implemented as an ethernet interface exchanging data using Internet Protocol IP well known in the relevant arts.

Each driver A K provides data connectivity based on a type of driver implemented in the corresponding mobile phone A Z. For example a mobile phone with a USB connectivity may be connected through one of drivers A K implemented with USB protocol.

Each RAPIs A K represents the set of function calls program logics to access the corresponding mobile phone. Each RAPIs A J perform an operation similar to the RAPI described in . Accordingly RAPIs A J retrieve the data portion of file which is eventually stored by multi data access modules to memory buffer . Often each mobile phone manufacturer provides a software package containing RAPI along with the mobile phone. The software package enables the access to mobile phone having the corresponding operating environment. Each software package is installed in the PC as the corresponding one of RAPI A J.

In addition for each operating environment vendors may provide a software development kit SDK . Software application integrating the corresponding RAPI may be developed using the SDK. SDK may be used to develop functions in the multi data access module .

It must be appreciated that the number and variety of viruses that affect mobile devices are increasing and evolving at a rapid rate. It may be difficult for a mobile device user to keep current the program modules and virus definitions if they were to be made available through conventional media such as computer readable media.

However if the user was to obtain the program modules and virus definitions from a server on which the updated versions are maintained the user may always have access to the updated program modules and virus definitions. The manner in which a user may obtain the program modules and virus definitions from a server is described below with examples.

Internet represents a network providing connectivity between server and computers A Z. Internet may be implemented using protocols such as Internet Protocol well known in the relevant arts. Computers A Z and server may exchange data for example program modules virus definition model of mobile devices etc. over internet .

Server represents a server containing software applications capable of performing operations for example retrieval of program modules virus definitions etc. requested by computers A Z. The data representing the program modules and virus definitions may be stored either internally within server or stored on an external server e.g. a database server . The data may be retrieved and processed as needed and sent as a response to various operations requested by computers A Z.

Mobile phones A Z operate similarly to mobile phones A Z described with reference to . As noted there mobile phones A Z may become infected malevolent program modules being present in a mobile phone without user consent by viruses through SMS MMS other application programs etc. It may also happen that malevolent program modules not capable of executing in a mobile phone because they are designed for other mobile phone environments may also be present.

Mobile phones A Z may be connected to respective computers A Z e.g. by USB interface well known in the relevant arts and scanned for both the kinds of malevolent program modules according to various aspects of the present invention as described below with examples.

In addition some of the steps may be performed in a different sequence than that depicted below as suited in the specific environment as will be apparent to one skilled in the relevant arts. Such implementations are contemplated to be covered by several aspects of the present invention. The flow chart begins in step in which control immediately passes to step . The description is provided assuming that Mobile phone A connected to computer A is to be scanned for viruses.

In step computer A receives a request for scanning an externally connected mobile device for viruses. Mobile device A may be connected to computer A by a user using a communication port such as USB Wired or Wireless Ethernet Bluetooth etc. as described in sections above. After connecting mobile device A to computer A a user may make a request to computer A to scan mobile device A for viruses for example using a graphical user interface or a keyboard etc. implemented based on user interface .

In step computer A determines the type of the mobile device sought to be scanned. The determination may be performed either using manual i.e. based on user inputs or automatically e.g. based on various plug and play techniques well known in the relevant arts . The type may be specified by identifiers of manufacturer and or model number e.g. Nokia N60 . However alternative information such as the operating environment operating system internal processor used memory size SIM card details may be provided which facilitates identification of the appropriate software modules and virus definitions as described below.

In step computer A obtains from server the program modules and virus definitions which are together designed to scan the type of mobile device. Download module may send the type of mobile device determined in step and a request for respective program modules and virus definitions to server over internet . Server may retrieve the program modules and virus definitions applicable to the mobile device type specified and send upload the files over internet to computer system A.

Download module may receive from server the program modules and virus definitions corresponding to the mobile device type sent and stores them in a storage. For example the virus definitions may be stored in virus definitions either to replace previously stored portions or as additive components. The program modules may consist of various modules such as virus scan module driver modules for example drivers A to K etc. required to access files from the mobile device etc. The received data may be stored in appropriate locations to respectively form virus scan module driver modules A to K etc.

It should be appreciated that only those definitions and program modules as applicable to the model of the mobile phone are received.

In step computer A executes the program modules using the virus definitions to identify any viruses present on the mobile device. In an embodiment the virus definitions and the program modules are received in the form of ActiveX components in technologies provided by Microsoft Corporation . Accordingly computer A may be designed to support such ActiveX technology. The reception of the components and execution of the same when required can be performed in a known way.

Thus if there are any driver modules in the downloaded program modules operating system services may perform appropriate actions to form the required ones of drivers A K from the received data. Virus scan module for example virus scan module may then be executed to scan mobile device A for viruses as described in sections above. A file or a portion of a file in mobile device A may be retrieved stored in memory for example memory buffer and scanned for viruses using virus definitions as described above. The scan may be continued for all the files on mobile device A. If a file is found to be infected with a virus the file may be cleaned repaired or deleted as noted above.

The flowchart ends in step . Computer systems A Z obtain the program modules and virus definitions from server as described above. The manner in which a server may provide the program modules and virus definitions to a computer in response to a request from the computer is described below with examples.

In addition some of the steps may be performed in a different sequence than that depicted below as suited in the specific environment as will be apparent to one skilled in the relevant arts. Such implementations are contemplated to be covered by several aspects of the present invention. The description is provided assuming that Mobile phone A connected to computer A is to be scanned for viruses. The flow chart begins in step in which control immediately passes to step .

In step server receives from a computer system data indicating a type of mobile device to be scanned for viruses. For example computer A may send the type of mobile device A connected to computer A for scanning for viruses determined in step to server over Internet .

In step server selects the program modules and virus definitions which are designed to scan the type of mobile device. Server maintains a library of program modules and virus definitions in a data storage which may be internal to server or external for example in a database server . The library contains a number of program modules and virus definitions which may be used to scan different types of mobile devices. Server selects the program modules and virus definitions pertaining to the type of mobile device received from computer A .

In step server sends the selected program modules and virus definitions to the computer system. Server sends the selected pertaining to the received type of mobile device program modules and virus definitions to computer A over internet . Computer A may receive and execute the program modules and virus definitions to scan mobile device A as described above. As noted above the program modules and virus definitions may be packaged as ActiveX components and sent in one embodiment. The flowchart ends in step .

The description is continued with respect to the details of an example server in an embodiment of the present invention.

Program module library contains program modules such as a virus scan module driver modules for example drivers A to K etc. required to access files from a mobile device etc. corresponding to each of the mobile device types it is designed to scan for viruses. Thus assuming there are 4 makes provided by each of 5 manufacturers the program modules and virus definitions for all the 20 types may be stored in the library.

Virus definition library contains virus definitions for example virus definitions corresponding to each of the mobile device types it is designed for.

Server receives a type of mobile device and a request for program modules and virus definitions corresponding to that type of mobile device from a computer such as computer A. Server selects the corresponding program modules from program module library and virus definitions from virus definition library and provides them over a network for example internet to the computer such as computer A making the request.

Network interface provides the physical electrical and protocol interfaces necessary for server to exchange data with computers such as computers A Z over a network such as internet

Upload module represents a set of program logic for receiving a mobile device type from a computer such as computer A select program modules and virus definitions corresponding to the received mobile device type from a respective program module library such as program module library and a virus definition library such as virus definition library and upload send the selected program modules and virus definitions to computer A over internet .

It should be appreciated that the features described above can be implemented in a combination of one or more of hardware software and firmware. The description is continued with respect to an embodiment in which the features are operative by execution of software instructions as described below in further detail.

Digital processing system may contain one or more processors such as a central processing unit CPU random access memory RAM secondary memory graphics controller display unit phone interface input interface and network interface . All the components except display unit may communicate with each other over communication path which may contain several buses as is well known in the relevant arts. The components of are described below in further detail.

CPU may execute instructions stored in RAM to provide several features of the present invention. CPU may contain multiple processing units with each processing unit potentially being designed for a specific task. Alternatively CPU may contain only a single general purpose processing unit. RAM may receive instructions from secondary memory using communication path .

Graphics Processor Unit GPU generates display signals e.g. in RGB format to display unit based on data instructions received from CPU . Display unit contains a display screen to display the images defined by the display signals.

Input interface may correspond to a keyboard and a pointing device e.g. touch pad mouse which may be used to specify various user actions start scanning enter mobile device type confirmation of deleting a virus infected file etc. described above.

The images displayed on the display screen together with input interface forms the basis for various user interface features provided according to various aspects of the present invention described above.

Phone interface may enable system to send receive data to the phones and may be viewed as containing physical interface and described above. Phone interface may be present only computer systems but not in the server and can be implemented in a known way.

Network interface provides connectivity to a network such as internet and may be used to communicate with other connected systems such as other computers A Z mobile phones devices server etc. .

Packet memory stores queues packets representing voice or data waiting to be forwarded or otherwise processed .

Secondary memory may contain hard drive flash memory and removable storage drive . Secondary memory may store the data for example virus definitions and software instructions such as program modules for scanning for viruses which enable digital processing system to provide several features in accordance with the present invention.

Some or all of the data and instructions may be provided on removable storage unit and the data and instructions may be read and provided by removable storage drive to RAM . Floppy drive magnetic tape drive CD ROM drive DVD Drive Flash memory removable memory chip PCMCIA Card EPROM are examples of such removable storage drive .

Removable storage unit may be implemented using medium and storage format compatible with removable storage drive such that removable storage drive can read the data and instructions. Thus removable storage unit includes a computer readable storage medium having stored therein computer software and or data. However the computer or machine in general readable storage medium can be in other forms e.g. non removable random access etc. .

In this document the term computer program product is used to generally refer to removable storage unit or hard disk installed in hard drive . These computer program products are means for providing software to digital processing system . CPU may retrieve the software instructions and execute the instructions to provide various features of the present invention described above.

While various embodiments of the present invention have been described above it should be understood that they have been presented by way of example only and not limitation. Thus the breadth and scope of the present invention should not be limited by any of the above described embodiments but should be defined only in accordance with the following claims and their equivalents.

