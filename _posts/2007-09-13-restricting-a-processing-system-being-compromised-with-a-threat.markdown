---

title: Restricting a processing system being compromised with a threat
abstract: A method, system, computer readable medium of instructions and/or computer program product. The method comprises receiving, in a proxy server, response data from a remote processing system, according to a request from the client processing system to download data from the remote processing system; using, in one or more emulated operating systems of the proxy server, the downloaded data; monitoring behavior of the use of the data in the one or more emulated operating systems; and in response to detecting malicious behavior indicative of a threat, restricting the client processing system being compromised with the threat of the response data.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08887278&OS=08887278&RS=08887278
owner: Symantec Corporation
number: 08887278
owner_city: Mountain View
owner_country: US
publication_date: 20070913
---
This application claims the benefit of priority from U.S. Provisional Patent Application No. 60 844 773 filed Sep. 15 2006 and is incorporated by referenced.

The present invention generally relates to the field of computing and more particularly to a method system computer readable medium of instructions and or computer program product for restricting a processing system being compromised with a threat.

A portion of the disclosure of this patent document contains material that is subject to copyright protection. The copyright owner has no objection to the facsimile reproduction by anyone of the patent disclosure as it appears in a Patent Office patent files or records but otherwise reserves all copyrights whatsoever.

As used herein a threat comprises malicious software also known as malware or pestware which comprises software that is included or inserted in a part of a processing system for a harmful purpose. The term threat should be read to comprise possible potential and actual threats. Types of malware can comprise but are not limited to malicious libraries viruses worms Trojans adware malicious active content and denial of service attacks. In the case of invasion of privacy for the purposes of fraud or theft of identity malicious software that passively observes the use of a computer is known as spyware .

There are currently a number of techniques to restrict threats such as malware compromising a processing system.

One technique comprises using database driven malware techniques which detect known malware. In this technique a database is used which generally comprises a signature indicative of a particular type of malware. The signatures are then compared to the downloaded entity such as an executable file to determine if the entity is malicious.

However this technique suffers from a number of disadvantages. This technique can only detect known malware. If there is no signature in the database for a new variant of malware the malicious entity could go undetected and thus compromise the processing system.

Another technique used is code signing. Code signing attempts to assure users that downloaded software such as an executable file downloaded from a web site has been supplied by a trusted software vendor that is participating in an infrastructure of trusted entities. Such a trusted infrastructure is available using Microsoft Authenticode. This mechanism generally involves the use of digital signatures and certificates in order to verify the software vendor.

However code signing also suffers from disadvantages. Firstly code signing does not analyse whether the downloaded software is malicious. It only guarantees that the software vendor is part of the trusted infrastructure. Additionally it is still possible that an author of malware may join the infrastructure of trusted entities if they meet particular criteria such as an acceptable Dun Bradstreet Rating prior to publishing malicious software for download by the public.

Therefore there is a need for a method system computer program product and or computer readable medium of instructions which addresses or at least ameliorates one or more problems inherent in the prior art.

An emulator is a module which emulates the functionality of another. Generally emulation software is software designed to enable a processing system to emulate a specified software system that is not its own.

An Application Programming Interface API is an interface which an application accesses services comprising operating system services.

A proxy server is a server which is intermediate a client processing system and the network such as the Internet. A proxy server may be a processing system or a software application which executes on a processing system.

Hyper Text Transfer Protocol HTTP is a protocol used to request and transfer files especially web pages and web page components over the Internet or other computer networks.

File Transfer Protocol FTP is a communications protocol for the transfer of files over a computer network.

A system registry is a database used by modern operating systems for example Windows platforms. The system registry comprises information needed to configure the operating system. The operating system refers to the registry for information ranging from user profiles to which applications are installed on the machine to what hardware is installed and which ports are registered.

A hash function i.e. Message Digest eg. MD5 can be used for many purposes for example to establish whether a file transmitted over a network has been tampered with or contains transmission errors. A hash function uses a mathematical rule which when applied to a file generates a hash value i.e. a number usually between 128 and 512 bits in length. This number is then transmitted with the file to a recipient who can reapply the mathematical rule to the file and compare the resulting number with the original number.

In a networked information or data communications system a user has access to one or more terminals which are capable of requesting and or receiving information or data from local or remote information sources. In such a communications system a terminal may be a type of processing system computer or computerised device personal computer PC mobile cellular or satellite telephone mobile data terminal portable computer Personal Digital Assistant PDA pager thin client or any other similar type of digital electronic device. The capability of such a terminal to request and or receive information or data can be provided by software hardware and or firmware. A terminal may comprise or be associated with other devices for example a local data storage device such as a hard disk drive or solid state drive.

An information source can comprise a server or any type of terminal that may be associated with one or more storage devices that are able to store information or data for example in one or more databases residing on a storage device. The exchange of information ie. the request and or receipt of information or data between a terminal and an information source or other terminal s is facilitated by a communication means. The communication means can be realised by physical cables for example a metallic cable such as a telephone line semi conducting cables electromagnetic signals for example radio frequency signals or infra red signals optical fibre cables satellite links or any other such medium or combination thereof connected to a network infrastructure.

The reference in this specification to any prior publication or information derived from the prior publication or to any matter which is known is not and should not be taken as an acknowledgment or admission or any form of suggestion that the prior publication or information derived from the prior publication or known matter forms part of the common general knowledge in the field of endeavour to which this specification relates.

In one broad form there is provided a method of restricting a client processing system being compromised by a threat wherein the method comprises 

receiving in a proxy server response data from a remote processing system according to a request from the client processing system to download data from the remote processing system 

in response to detecting malicious behaviour indicative of a threat restricting the client processing system being compromised with the threat of the response data.

determining using a cache module if the request has previously been serviced wherein the cache module stores analysed response data and

in the event that the request has previously been serviced retrieving using the cache module analysed response data.

storing using the cache module analysed response data using a hash value generated based upon the response data and

retrieving using the cache module analysed response data using a hash value generated using received response data.

In another form the method comprises removing a portion of the response data which is associated with malicious activity.

In one embodiment the method comprises replacing the portion removed from the response data with a non malicious portion.

In another embodiment upon determining that the response data requires modification the method comprises 

performing a search of stored analysed response data using the cache module to determine if a substantially similar request has previously been serviced and

receiving from the cache module analysed response data which at least substantially corresponds to the requested data.

In optional forms the method comprises generating a wrapper of the analysed data wherein the wrapper is indicative of scan data.

In additional or alternate forms the wrapper is indicative scan data the scan data being indicative of at least one of 

In one aspect the step of generating the wrapper comprises configuring the wrapper to intercept use or execution of the data by the client processing system wherein the wrapper upon interception of the use or execution of the data presents the scan data.

In one form the method comprises generating the wrapper to present a prompt requesting input regarding whether the data is to be executed or used by the client processing system quarantined or deleted.

In one aspect in the event that the data downloaded is executable the step of using the data comprises executing the data.

recording one or more events that occur during use of the data by the one or more emulated operating systems and

analysing the one or more events to determine whether the use of the data exhibits behaviour which is indicative of a threat.

selecting in the proxy server and in accordance with the data downloaded the one or more emulated operating systems from a plurality of emulated operating systems and

using the one or more emulated operating systems with the data to monitor the use of the behaviour of the data.

In another broad form there is provided a system to restrict a client processing system being compromised with a threat wherein the system is configured to 

receive in a proxy server response data from a remote processing system according to a request from the client processing system to download data from the remote processing system 

in response to detecting malicious behaviour indicative of a threat restrict the client processing system being compromised with the threat of the response data.

In an additional or alternate form the proxy server is configured to be executed at a second processing system in data communication with the client processing system.

In one form the system comprises an analysis module configured to analyse the response data wherein the analysis module comprises at least one of 

In another form there is provided a computer program product comprising a computer readable medium having a computer program recorded therein or thereon the computer program enabling restriction of a client processing system being compromised by data downloaded from a remote processing system wherein the computer program product configures the client processing system or a second processing system in data communication with the client processing system to 

receive in a proxy server response data from a remote processing system according to a request from the client processing system to download data from the remote processing system 

in response to detecting malicious behaviour indicative of a threat restrict the client processing system being compromised with the threat of the response data.

According to another broad form there is provided a computer readable medium of instructions for giving effect to any of the aforementioned methods or systems. In one particular but non limiting form the computer readable medium of instructions are embodied as a software program.

The following modes given by way of example only are described in order to provide a more precise understanding of the subject matter of a preferred embodiment or embodiments.

In the figures incorporated to illustrate features of an example embodiment like reference numerals are used to identify like parts throughout the figures.

A particular embodiment of the present invention can be realised using a processing system an example of which is shown in . In particular the processing system generally comprises at least one processor or processing unit or plurality of processors memory at least one input device and at least one output device coupled together via a bus or group of buses . In certain embodiments input device and output device could be the same device. An interface can also be provided for coupling the processing system to one or more peripheral devices for example interface could be a PCI card or PC card. At least one storage device which houses at least one database can also be provided. The memory can be any form of memory device for example volatile or non volatile memory solid state storage devices magnetic devices etc. The processor could comprise more than one distinct processing device for example to handle different functions within the processing system .

Input device receives input data and can comprise for example a keyboard a pointer device such as a pen like device or a mouse audio receiving device for voice controlled activation such as a microphone data receiver or antenna such as a modem or wireless data adaptor data acquisition card etc. Input data could come from different sources for example keyboard instructions in conjunction with data received via a network. Output device produces or generates output data and can comprise for example a display device or monitor in which case output data is visual a printer in which case output data is printed a port for example a USB port a peripheral component adaptor a data transmitter or antenna such as a modem or wireless network adaptor etc. Output data could be distinct and derived from different output devices for example a visual display on a monitor in conjunction with data transmitted to a network. A user could view data output or an interpretation of the data output on for example a monitor or using a printer. The storage device can be any form of data or information storage means for example volatile or non volatile memory solid state storage devices magnetic devices etc.

In use the processing system is adapted to allow data or information to be stored in and or retrieved from via wired or wireless communication means the at least one database . The interface may allow wired and or wireless communication between the processing unit and peripheral components that may serve a specialised purpose. More than one input device and or output device can be provided. It should be appreciated that the processing system may be any form of terminal server specialised hardware or the like.

The processing system may be a part of a networked communications system. Processing system could connect to a network for example the Internet or a WAN. Input data and output data could be received from or communicated to other devices such as a server via the network. The network may form part of or be connected to the Internet and may be or form part of other communication networks such as LAN WAN ethernet token ring FDDI ring star etc. networks or mobile telephone networks such as GSM CDMA or 3G etc. networks and may be wholly or partially wired comprising for example optical fibre or wireless networks depending on a particular implementation.

Referring now to there is shown an example system to restrict a client processing system being compromised with a threat. In particular the system comprises a remote processing system a proxy server and a client processing system which are in data communication. The proxy server may be a stand alone processing system however it will be appreciated that the proxy server may be a software application at either the remote processing system or the client processing system . It will also be appreciated that client processing system and remote processing system may be forms of processing system .

When a user at the client processing system attempts to download data such as software from the remote processing system request data is generated by the client processing system and transferred to the proxy server . Generally the proxy server then transfers the request data to the remote processing system . In accordance with the request data the remote processing system generates response data which is transferred to the proxy server . The proxy server uses the data such as executing the software in one or more emulated operating systems to analyse if the data is malicious. If the use of the data is malicious at least a portion of the data is restricted by the proxy server from compromising the client processing system . Analysed response data can then transferred to the client processing system from the proxy server .

Referring now to there is shown a flow diagram illustrating an example method of restricting the client processing system being compromised with a threat.

In particular at step the method comprises the proxy server receiving response data to the request to download data from the remote processing system . At step the method comprises using the data in one or more emulated operating systems. This may comprise executing downloaded software in the one or more emulated operating systems. At step the method comprises monitoring the behaviour of the use of the data in the one or more emulated operating systems. At step the method comprises determining if the behaviour of the use of the data is indicative of a threat. If the behaviour is malicious the method proceeds to step wherein the proxy server restricts the client processing system being compromised with the threat of the response data .

Referring now to there is shown another example system to restrict a client processing system being compromised with a threat. Although the example system is to be discussed in relation to restricting the client processing system being compromised with software it will be appreciated that other forms of data may also be restricted from compromising the client processing system using the system .

In particular the proxy server comprises a number of sub modules to analyse the response data and restrict malicious software compromising the client processing system . The proxy server comprises an executable identifier module an emulation module an execution module a monitor module an analysis module a modification module and a cache module .

When the client processing system transfers request data to the proxy server the cache module analyses the request to determine if the request has previously been serviced. The cache module is configured to store analysed response data that has been previously transferred to client processing systems . In one form the cache module may store a hash value of each serviced request and the associated analysed response . The cache module may be configured to determine a hash value for the received request wherein records of previously serviced requests are searched using the determined hash value to determine if the request has been responded to previously. In the event that the received request data has been previously serviced the cache module retrieves the relevant analysed response data which is transferred to the client processing system .

In the event that the cache module does not comprise a recorded response to the particular request the request data is transferred to the server processing system . When the server processing system transfers the response data to the proxy server the executable identifier analyses the software of the response data to determine if the software is an executable file. In the event that the executable identifier module determines that the software is not executable the response data is transferred to the analysis module . However in the event that the executable identifier module determines that the software is executable the response data is transferred to the emulation module .

The software of the response data is executed in one or more emulated operating systems by the execution module . Events that occur in relation to the executed software in the one or more emulated operating systems are monitored by the monitor module . The monitor module may be configured to monitor particular events which are indicative of malicious behaviour associated with a threat. The monitor module can record the events of the executed software in a log file . The log file is then transferred to the analysis module . A detailed explanation of monitoring behaviour of malicious software is described in the Applicant s following co pending applications the content of which is herein by incorporated by cross reference co pending U.S. patent application Ser. No. 11 829 592 and co pending Australian Patent application AU2007203543 entitled Threat Identification co pending U.S. patent application Ser. No. 11 829 608 and co pending Australian Patent application AU2007203534 entitled Real Time Malicious Software Detection and co pending U.S. patent application Ser. No. 11 780 113 and co pending Australian Patent application AU2007203373 entitled Detecting Malicious Activity .

The analysis module analyses the log file to determine if the software exhibits malicious behaviour indicative of a threat. In particular the analysis module comprises a malicious behaviour module which applies a number of rules to the log file to determine if the software is exhibiting malicious behaviour. Such rules may comprise 

As will be appreciated from above example a number of different combinations of rules can be applied to determine whether the behaviour of the executed software in the one or more emulated operating system is malicious. The malicious behaviour module may be provided in the form of a database. The analysis module may also comprise other sub modules which may be applied to executable and non executable software to determine if the software or a portion thereof is malicious as will be discussed in more detail below.

Results of the analysis performed by the analysis module are then transferred to the modification module . The response data is also transferred to the modification module . The modification module can modify if appropriate the software in accordance with the results of the analysis. For example the results may indicate that a portion of the software is malicious. Therefore the modification module may remove the malicious portion of the software from the response data . The modification module may optionally replace the malicious portion of the software with a non malicious portion of software as will be explained in more detail below. In some instances the entire downloaded software may be considered malicious and as such may be either removed or replaced with a non malicious version of the software as will also be explained in more detail below. If the analysis results indicate that the software is non malicious then the software does not require modification.

A wrapper component can be added to the analysed response data to indicate scanning data and or emulation data. The scanning data may be indicative of a version of a signature database which was used by the analysis module to analyse the response data . The emulation data may be indicative of at least one of the time and or date which the emulation was performed the one or more emulated operating systems used to analyse the software a version number indicative of the malicious behaviour rule module a size of the software one or more locations in the one or more emulated operating systems which the software was executed and whether the software is code signed.

When the user receives the analysed response data and attempts to execute the downloaded software the wrapper component may be executed by the client processing system displaying to the user the scanning data and or emulation data. The wrapper component can provide a prompt to the user requesting confirmation that based on the emulation data and or scanning data the user still wishes to execute the software. The user may indicate using the input device of the client processing system that the software is to be executed or that the software is to be deleted or quarantined for further analysis.

Optionally the modification module may accept the code signed prompt such that the user at the client processing system is not prompted to perform the acceptance.

In the event that the software or a portion thereof is to be replaced the modification module may generate and transfer a replacement request to the cache module . The replacement request can indicate the software of the response data . For example information such as name of the software the version of the software may be comprised in the replacement request and the network address of the server processing system which transferred the response data .

In response to the replacement request the cache module performs a search of recorded analysed response data to determine if a similar request had been previously serviced for the requested software. In the event that the cache module determines a previous non malicious version of the software had been provided to a client processing system in the past the cache module may transfer the closest matching software or portion thereof back to the modification module . The modification module may then use the closest matching software or portion thereof to modify the response data so as to restrict the client processing system being compromised with a threat. For example the modification module may remove a particular malicious file from the software and replace it with an earlier non malicious version of the file which had previously been transferred to the client processing system . Alternatively the entire malicious software may be removed from the response data and the non malicious version of the software may be comprised.

The analysed response data is then transferred from the modification module to the cache module for caching. Once the cache module has cached the analysed response data the analysed response data is then transferred from the cache module to the client processing system .

Referring now to B C and D there is shown a more detailed flow diagram illustrating a method of restricting the client processing system being compromised with a threat. Again although the example method is to be discussed in relation to restricting the client processing system being compromised with software it will be appreciated that other forms of data may also be restricted from compromising the client processing system using the method .

In particular at step the method comprises the client processing system generating request data to download software from the remote processing system . This may be performed by the user selecting using input device a hyperlink in a web page available on the Internet wherein the hyperlink allows software to be downloaded from the remote processing system . At step the method comprises the client processing system transferring the request data to the proxy server .

At step the method comprises the proxy server initiating the cache module to determine whether an analysed response has previously been transferred to a client processing system for the requested software. At step if the software has previously been requested and suitable analysed response data is available in the cache module the method proceeds to step where the cache module transfers to the client processing system previously transferred analysed response data . In the event that the cache module does not comprise suitable analysed response data for the software requested the method proceeds to step where the cache module transfers the request data to the remote processing system .

At step the method comprises the remote processing system transferring response data to the proxy server wherein the response data is indicative of the requested software. At step the method comprises the proxy server initiating the executable identifier module to determine if the software of the response data is an executable entity. In the event that the executable identifier module determines that the software is not executable the method proceeds to step . In the event that the executable identifier module determines that the software is executable the method continues to step .

At step the method comprises the proxy server initialising the emulation module . This step could comprise initialising the one or more emulated operating systems such that the execution of the software can be emulated. This step could optionally comprise determining the one or more operating systems which are relevant for emulating the execution of the software. For example the software may be designed for Microsoft Windows 2000 and Microsoft Windows XP but not for Microsoft Windows 95. As such only the first two operating systems are initialised for emulation in the emulation module .

At step the method comprises the emulation modules executing the software of the response data in the one or more emulated operating systems. Optionally the one or more emulated operating systems can emulate execution of the software in succession or simultaneously. The one or more emulated operating systems can comprise at least one of system registry APIs file access creation and interaction APIs networking APIs such as Winsock and process control APIs. The one or more emulated operating systems can be configured to return to the executing software a success value or an error value.

At step the method comprises the monitor module monitoring one or more events associated with the executed software in the one or more emulated operating systems. The monitor module can be configured to monitor each event that occurs in relation to the executed software. However in more preferable forms only particular events which are associated with a loadpoint in the emulated operating system are monitored by the monitor module .

At step the method comprises the monitor module recording the one or more events. In one form the recordings are recorded in a log file . Optionally one or more entities associated with the one or more events are also recorded. For example an executable file of the software may attempt to connect to the Internet. In this instance the event is the action of connecting to the Internet and the one or more associated entities are the executable file and the Internet. Therefore the event and the entities associated with the event can be recorded in the log file .

At step the method comprises the analysis module analysing the software to determine if the software is malicious. In one form the analysis module analyses the software by analysing the results of the monitor module to determine if the software exhibited behaviour generally associated with a threat. The analysis module can comprise an malicious behaviour module which comprises one or more rules which when applied to the recorded events and entities determine whether the emulated execution of the software exhibited malicious behaviour generally associated with a threat.

In an additional or alternative form other modules of the analysis module can be applied to the software to determine if the software is malicious. These other modules of the analysis module will be discussed in more detail later.

A footprint of the one or more emulated operating systems may also be analysed by the analysis module to determine whether the software performed maliciously. At step in the event that the software or a portion thereof is determined to be malicious the method proceeds to step . In the event that the software was non malicious the method proceeds to step .

At step the method comprises the modification module modifying at least a portion of the response data to restrict the client processing system being compromised with a threat. This step can comprise removing the software from the response data and modifying the response data to indicate that the software was malicious. In another form a malicious portion of the software can be removed. In another form the software or a portion thereof can be replaced with non malicious software or portion thereof retrieved from the cache module as has previously been discussed.

At step the wrapper component is added to the analysed response data wherein the wrapper component is indicative of emulation data and or scan data. In other optional forms any code signing provided with the response data can be accepted.

At step the method comprises the cache module storing the analysed response data. The cache module records in a store such as a database the analysed response data in association with the request data . The cache module may calculate a hash value for the analysed response data and or the request data and store this in the database such that the cache can be easily searched. Other information may also be stored in the cache module such as the date and or time which the software was requested such that unsuitable recordings in the cache module can be removed when appropriate.

At step the cache module transfers the analysed response data to the client processing system . The analysed response data may comprise the requested software. However if the software transferred from the remote processing system was determined to be malicious then it may be possible that the software or a portion thereof may have been removed. It is also possible that a replacement version of the software may be comprised in the analysed response data wherein the different version of the software or portion thereof is considered to not be malicious. In another form the analysed response data may comprise modified software wherein one of the software s components may have been modified or replaced.

The analysed response data may indicate to the user what modification if any occurred by the proxy server and the reasons for any modification.

In particular the analysis module can comprise the modules of the malicious behaviour module as discussed above a cryptographic hash module a checksum module a disassembly module a black list white list module and a pattern matching module .

The cryptographic hash module of the analysis module is configured to generate a cryptographic hash value of at least a portion of the software. As the cryptographic hash value can be used as an identity the cryptographic hash value can be used in comparisons with the blacklist whitelist module to determine whether the at least a portion of the software is malicious.

The checksum module of the analysis module is configured to determine a checksum of the software. The checksum can be compared to a database blacklist whitelist module to determine whether the software is malicious.

The pattern matching module of the analysis module is configured to search the software or the log file for particular patterns of strings instructions or events which are indicative of malicious activity. The pattern matching module may operate in combination with the disassembly module of the analysis module .

The disassembly module is configured to disassemble binary code of the software such that the disassembly module determines processing system instructions. The processing system instructions of the software can then be used by the pattern matching module to determine whether the software is malicious. Although strings of instructions can be compared by the pattern matching module the pattern matching module may be configured to perform functional comparisons of groups of instructions to determine whether the functionality of software is indicative of a threat.

The blacklist whitelist module of the analysis module comprises a list of malicious and or non malicious software. The blacklist whitelist module may be provided in the form of a table or database which comprises data indicative of malicious and non malicious software. The table may comprise checksums and cryptographic hash values for malicious and non malicious software. The data stored in the blacklist whitelist module can be used to determine whether the software is malicious or non malicious.

In another optional form the executable identifier module may also be configured to identify an archive file which comprises one or more executable entities. The archived entities of the archive file may be extracted by the execution module . If one or more of the extracted entities or portions thereof are determined to be malicious the modification module modifies the one or more extracted entities or portions thereof accordingly and re archives the archive file to be transferred in the analysed response data to the client processing system .

The embodiments illustrated may be implemented as a software package or component. Such software can then be used to pro actively seek to determine one or more malicious entities. Various embodiments can be implemented for use with the Microsoft Windows operating system or any other modern operating system. The embodiments described throughout can also be implemented via hardware or a combination of hardware and software.

The embodiments described can be used to detect and remove a threat from a network request such as a HTTP request or FTP download. While the current implementation is Linux eg Squid with ICAP enabled WINE QEMU and Windows specific the disclosed methods and systems may be applied to modern operating systems on any device comprising embedded gateway appliances such as routers and firewalls.

In some forms the malicious assessment server may transfer restricting instructions to the relevant proxy server for restricting the software of the response data compromising the client processing system . For example the malicious assessment server may transfer restricting instructions which instruct the modification module to quarantine particular portions of the software. In some forms the restricting instructions may be executable by the modification module .

The cache module may apply one or more algorithms to remove unsuitable cached analysed response data . Such algorithms may comprise Least Recently Used LRU and Least Frequently Used LFU .

An example piece of pseudocode for implementing a method of restricting a threat compromising the client processing system is provided below 

Optional embodiments of the present invention may also be said to broadly consist in the parts elements and features referred to or indicated herein individually or collectively in any or all combinations of two or more of the parts elements or features and wherein specific integers are mentioned herein which have known equivalents in the art to which the invention relates such known equivalents are deemed to be incorporated herein as if individually set forth.

Although a preferred embodiment has been described in detail it should be understood that various changes substitutions and alterations can be made by one of ordinary skill in the art without departing from the scope of the present invention.

