---

title: Extending an RFID reader API
abstract: The present disclosure provides a Radio Frequency Identification (RFID) reader software structure and method. A functionality of a reader engine is extended, enabling it to communicate via an extended standard Application Programming Interface (API) with an application software. The extended functionality supports a Partner Service Module that resides in the reader, thus allowing at least one of its Partner Software Functions to communicate with the application software over a single connection.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08082556&OS=08082556&RS=08082556
owner: Impinj, Inc.
number: 08082556
owner_city: Seattle
owner_country: US
publication_date: 20071219
---
This patent application claims priority from U.S. Provisional Patent Application No. 60 932 561 filed on May 30 2007 the disclosure of which is hereby incorporated by reference for all purposes.

The present description addresses the field of Radio Frequency IDentification RFID systems and more specifically the RFID reader software structure that supports a partner software module PSM that is resident of the reader for communicating with an external application software.

Radio Frequency Identification RFID systems typically include RFID tags and RFID readers. RFID readers are also known as RFID reader writers or RFID interrogators. RFID systems can be used in many ways for locating and identifying objects to which the tags are attached. RFID systems are particularly useful in product related and service related industries for tracking large numbers of objects being processed inventoried or handled. In such cases an RFID tag is usually attached to an individual item or to its package.

In principle RFID techniques entail using an RFID reader to interrogate one or more RFID tags. The reader transmitting a Radio Frequency RF wave performs the interrogation. The RF wave is typically electromagnetic at least in the far field. The RF wave can also be magnetic in the near field.

A tag that senses the interrogating RF wave responds by transmitting back another RF wave. The tag generates the transmitted back RF wave either originally or by reflecting back a portion of the interrogating RF wave in a process known as backscatter. Backscatter may take place in a number of ways.

The reflected back RF wave may further encode data stored internally in the tag such as a number. The response is demodulated and decoded by the reader which thereby identifies counts or otherwise interacts with the associated item. The decoded data can denote a serial number a price a date a destination other attribute s any combination of attributes and so on.

An RFID tag typically includes an antenna system a radio section a power management section and frequently a logical section a memory or both. In earlier RFID tags the power management section included an energy storage device such as a battery. RFID tags with an energy storage device are known as active or semi active tags. Advances in semiconductor technology have miniaturized the electronics so much that an RFID tag can be powered solely by the RF signal it receives. Such RFID tags do not include an energy storage device and are called passive tags.

RFID readers are generally controlled by software which often uses an Application Programming Interface API . Problems arise when a partner develops a new Partner Software Function PSF for a custom feature function or business process on the RFID reader. Development of such a new PSF is typically costly largely due to the need for its own API over the network.

The present disclosure provides Radio Frequency IDentification RFID reader software and methods. In some embodiments a functionality of a reader engine becomes extended enabling it to communicate via an extended standard Application Programming Interface API with an application software. The extended functionality supports a Partner Service Module that resides in the reader thus allowing at least one of its Partner Software Functions to communicate with the application software over a single connection.

The invention offers advantages over existing proprietary RFID reader API and custom API solutions by providing a unified extendable standard API solution.

These and other features and advantages of the invention will be better understood from the specification of the invention which includes the following Detailed Description and accompanying Drawings.

The present invention is now described in more detail. While it is disclosed in its preferred form the specific embodiments of the invention as disclosed herein and illustrated in the drawings are not to be considered in a limiting sense. Rather these embodiments are provided so that this disclosure will be thorough and complete and will fully convey the scope of the invention to those skilled in the art. Indeed it should be readily apparent in view of the present description that the invention might be modified in numerous ways. Among other things the present invention may be embodied as devices methods software and so on. Accordingly the present invention may take the form of an entirely hardware embodiment an entirely software embodiment an entirely firmware embodiment or an embodiment combining aspects of the above. This description is therefore not to be taken in a limiting sense.

The following definitions are provided as they are typically but not exclusively used in the RFID reader environment implementing the various adaptive aspects of the present invention.

 Application Programming Interface API is a source code interface that an operating system or library or communication port provides to facilitate communications between hosts or between processes or between software modules.

 Partner Software Module PSM is a program that implements a partner s software function which delivers one or more additional functionalities for an RFID reader. One such functionality could be called a Partner Software Function PSF .

 Private Enterprise Number PEN identifies partner service module PSM it is defined by the Internet Assigned Numbers Authority IANA .

 Reader Engine is a set of functions definitions that tracks and controls software modules and other principal objects drives I O maintains timers and conveys messages between software modules of functions. It also abstract operating system dependent commands and provides a set of standardized services to manipulate various settings of an RFID reader.

Reader and tag exchange data via wave and wave . In a session of such an exchange each encodes modulates and transmits data to the other and each receives demodulates and decodes data from the other. The data is modulated onto and decoded from RF waveforms.

Encoding the data in waveforms can be performed in a number of different ways. For example protocols are devised to communicate in terms of symbols also called RFID symbols. A symbol for communicating can be a delimiter a calibration symbol and so on. Further symbols can be implemented for ultimately exchanging binary data such as 0 and 1 if that is desired. In turn when the waveforms are processed internally by reader and tag they can be equivalently considered and treated as numbers having corresponding values and so on.

Tag can be a passive tag or an active or semi active tag i.e. having its own power source. Where tag is a passive tag it is powered from wave .

Tag is formed on a substantially planar inlay which can be made in many ways known in the art. Tag includes an electrical circuit which is preferably implemented in an integrated circuit IC . IC is arranged on inlay .

Tag also includes an antenna for exchanging wireless signals with its environment. The antenna is usually flat and attached to inlay . IC is electrically coupled to the antenna via suitable antenna ports not shown in .

The antenna may be made in a number of ways as is well known in the art. In the example of the antenna is made from two distinct antenna segments which are shown here forming a dipole. Many other embodiments are possible using any number of antenna segments.

In some embodiments an antenna can be made with even a single segment. Different points of the segment can be coupled to one or more of the antenna ports of IC . For example the antenna can form a single loop with its ends coupled to the ports. It should be remembered that when the single segment has more complex shapes even a single segment could behave like multiple segments at the frequencies of RFID wireless communication.

In operation a signal is received by the antenna and communicated to IC . IC both harvests power and responds if appropriate based on the incoming signal and its internal state. In order to respond by replying IC modulates the reflectance of the antenna which generates the backscatter from a wave transmitted by the reader. Coupling together and uncoupling the antenna ports of IC can modulate the reflectance as can a variety of other means.

In the embodiment of antenna segments are separate from IC . In other embodiments antenna segments may alternately be formed on IC and so on.

The components of the RFID system of may communicate with each other in any number of modes. One such mode is called full duplex. Another such mode is called half duplex and is described below.

Local block is responsible for communicating with the tags. Local block includes a block of an antenna and a driver of the antenna for communicating with the tags. Some readers like that shown in local block contain a single antenna and driver. Some readers contain multiple antennas and drivers and a method to switch signals among them including sometimes using different antennas for transmitting and for receiving. Moreover some readers contain multiple antennas and drivers that can operate simultaneously. A demodulator decoder block demodulates and decodes backscattered waves received from the tags via antenna block . Modulator encoder block encodes and modulates an RF wave that is to be transmitted to the tags via antenna block .

Local block additionally includes an optional local processor . Processor may be implemented in any number of ways known in the art. Such ways include by way of examples and not of limitation digital and or analog processors such as microprocessors and digital signal processors DSPs controllers such as microcontrollers software running in a machine such as a general purpose computer programmable circuits such as Field Programmable Gate Arrays FPGAs Field Programmable Analog Arrays FPAAs Programmable Logic Devices PLDs Application Specific Integrated Circuits ASIC any combination of one or more of these and so on. In some cases some or all of the decoding function in block the encoding function in block or both may be performed instead by processor .

Local block additionally includes an optional local memory . Memory may be implemented in any number of ways known in the art. Such ways include by way of examples and not of limitation nonvolatile memories NVM read only memories ROM random access memories RAM any combination of one or more of these and so on. Memory if provided can include programs for processor to run if provided. One such program may include one or more PSMs.

In some embodiments memory stores data read from tags or data to be written to tags such as Electronic Product Codes EPCs Tag Identifiers TIDs and other data. Memory can also include reference data that is to be compared to the EPC codes instructions and or rules for how to encode commands for the tags modes for controlling antenna and so on. In some of these embodiments local memory is provided as a database.

Some components of local block typically treat the data as analog such as the antenna driver block . Other components such as memory typically treat the data as digital. At some point there is a conversion between analog and digital. Based on where this conversion occurs a whole reader may be characterized as analog or digital but most readers contain a mix of analog and digital functionality.

If remote components are indeed provided they are coupled to local block via an electronic communications network . Network can be a Local Area Network LAN a Metropolitan Area Network MAN a Wide Area Network WAN a network of networks such as the internet or a mere local communication link such as a USB PCI and so on. In turn local block then includes a local network connection for communicating with network .

There can be one or more remote component s . If more than one they can be located at the same location or in different locations. They can access each other and local block via network or via other similar networks and so on. Accordingly remote component s can use respective remote network connections. Only one such remote network connection is shown which is similar to local network connection etc.

Remote component s can also include a remote processor . Processor can be made in any way known in the art such as was described with reference to local processor .

Remote component s can also include a remote memory . Memory can be made in any way known in the art such as was described with reference to local memory . Memory may include a local database and a different database of a Standards Organization such as one that can reference EPCs.

Of the above described elements it is advantageous to consider a combination of these components designated as operational processing block . Block includes those that are provided of the following local processor remote processor local network connection remote network connection and by extension an applicable portion of network that links connection with connection . The portion can be dynamically changeable etc. In addition block can receive and decode RF waves received via antenna and cause antenna to transmit RF waves according to what it has processed.

Block includes either local processor or remote processor or both. If both are provided remote processor can be made such that it operates in a way complementary with that of local processor . In fact the two can cooperate. It will be appreciated that block as defined this way is in communication with both local memory and remote memory if both are present.

Accordingly block is location agnostic in that its functions can be implemented either by local processor or by remote processor or by a combination of both. Some of these functions are preferably implemented by local processor and some by remote processor . Block accesses local memory or remote memory or both for storing and or retrieving data.

Reader system operates by block generating communications for RFID tags. These communications are ultimately transmitted by antenna block with modulator encoder block encoding and modulating the information on an RF wave. Then data is received from the tags via antenna block demodulated and decoded by demodulator decoder block and processed by processing block .

The invention additionally includes programs and methods of operation of the programs. A program is generally defined as a group of steps or operations leading to a desired result due to the nature of the elements in the steps and their sequence. A program is usually advantageously implemented as a sequence of steps or operations for a processor such as the structures described above.

Performing the steps instructions or operations of a program requires manipulation of physical quantities. Usually though not necessarily these quantities may be transferred combined compared and otherwise manipulated or processed according to the steps or instructions and they may also be stored in a computer readable medium. These quantities include for example electrical magnetic and electromagnetic charges or particles states of matter and in the more general case can include the states of any physical devices or elements. It is convenient at times principally for reasons of common usage to refer to information represented by the states of these quantities as bits data bits samples values symbols characters terms numbers or the like. It should be borne in mind however that all of these and similar terms are associated with the appropriate physical quantities and that these terms are merely convenient labels applied to these physical quantities individually or in groups.

The invention furthermore includes storage media. Such media individually or in combination with others have stored thereon instructions of a program made according to the invention. A storage medium according to the invention is a computer readable medium such as a memory and is read by a processor of the type mentioned above. If a memory it can be implemented in a number of ways such as Read Only Memory ROM Random Access Memory RAM etc. some of which are volatile and some non volatile.

Even though it is said that the program may be stored in a computer readable medium it should be clear to a person skilled in the art that it need not be a single memory or even a single machine. Various portions modules or features of it may reside in separate memories or even separate machines. The separate machines may be connected directly or through a network such as a local access network LAN or a global network such as the Internet.

Often for the sake of convenience only it is desirable to implement and describe a program as software. The software can be unitary or thought in terms of various interconnected distinct software modules.

This detailed description is presented largely in terms of flowcharts algorithms and symbolic representations of operations on data bits on and or within at least one medium that allows computational operations such as a computer with memory. Indeed such descriptions and representations are the type of convenient labels used by those skilled in programming and or the data processing arts to effectively convey the substance of their work to others skilled in the art. A person skilled in the art of programming may use these descriptions to readily generate specific instructions for implementing a program according to the present invention.

Embodiments of an RFID reader system can be implemented as hardware software firmware or any combination. It is advantageous to consider such a system as subdivided into components or modules. A person skilled in the art will recognize that some of these components or modules can be implemented as hardware some as software some as firmware and some as a combination. An example of such a subdivision is now described.

RFID reader system includes one or more antennas and an RF Front End for interfacing with antenna s . These can be made as described above. In addition Front End typically includes analog components.

System also includes a Signal Processing module . In this embodiment module exchanges waveforms with Front End such as I and Q waveform pairs. In some embodiments signal processing module is implemented by itself in an FPGA.

System also includes a Physical Driver module which is also known as Data Link. In this embodiment module exchanges bits with module . Data Link can be the stage associated with framing of data. In one embodiment module is implemented by a Digital Signal Processor.

System additionally includes a Media Access Control module which is also known as MAC layer. In this embodiment module exchanges packets of bits with module . MAC layer can be the stage for making decisions for sharing the medium of wireless communication which in this case is the air interface. Sharing can be between reader system and tags or between system with another reader or between tags or a combination. In one embodiment module is implemented by a Digital Signal Processor. Module may include a lower level functionality and a higher level functionality and so on.

System moreover includes an Application Programming Interface module which is also known as API Modem API and MAPI. In some embodiments module is itself an interface for a user.

All of these functionalities can be supported by one or more processors. One of these processors can be considered a host processor . Host processor processor exchanges signals with MAC layer via module . In some embodiments host processor is not considered as a separate module but one that includes some of the above mentioned modules of system . A user interface is typically coupled to processor .

Host processor can include other software modules for system for example Partner Service Modules PSM . In some embodiments elements of module may be distributed between processor and MAC layer .

A user interface may be coupled to API . User interface can be manual automatic or both. It can be supported by a separate processor than the above mentioned processor or implemented on it.

System and communicate with external application software hosted on PC Servers via an extended standard API.

It will be observed that the modules of system form something of a chain. Adjacent modules in the chain can be coupled by the appropriate instrumentalities for exchanging signals. These instrumentalities include conductors buses interfaces and so on. These instrumentalities can be local e.g. to connect modules that are physically close to each other or over a network for remote communication.

The chain is used in opposite directions for receiving and transmitting. In a receiving mode wireless waves are received by antenna s as signals which are in turn processed successively by the various modules in the chain. Processing can terminate in any one of the modules. In a transmitting mode initiation can be in any one of these modules. That which is to be transmitted becomes ultimately signals for antenna s to transmit as wireless waves.

The architecture of system is presented for purposes of explanation and not of limitation. Its particular subdivision into modules need not be followed for creating embodiments according to the invention. Furthermore the features of the invention can be performed either within a single one of the modules or by a combination of them.

An economy is achieved in the present document in that a single set of flowcharts is used to describe methods in and of themselves along with operations of hardware and or software and or firmware. This is regardless of how each element is implemented.

Reader engine communicates via a standard API with application software . By standard API it is meant native or non extended API.

Reader communicates via two different channels with application software . Reader engine communicates via standard API while PSM communicates via custom reader API .

Reader engine is operationally coupled to PSMs namely to PSM and also to optional PSM and PSM N if provided. Reader engine communicates with external application software via initial standard reader AP and with other reader components via modem API . External application software may be hosted in PC Server or in RFID reader itself.

One of the executable files is generally developed by a partner. It can be used for extending the RFID reader embedded features and functions.

At least one of the PSFs not shown can communicate with external application via only extended standard API and not directly. In some embodiments all the PSFs of one or all the PSMs can communicate with external application via only extended standard API .

At least one of the PSFs can obtain RFID reader information from other reader components . All messages are routed through extended reader engine . Extended reader engine may duplicate messages if multiple PSMs have been hosted or of the messages are also to be provided to an external application.

A routing schema for messages can include upstream communication functionality and downstream communication functionality. Upstream communication functionality includes for example routing for standard messages from other reader components to application software routing for pass through messages from PSM and PSM to application software and routing for PSM initiated messages from PSM N to application software . Downstream communication functionality includes the inverse of the above in some embodiments.

Routing for PSM consumed messages is unidirectional from other reader components to PSM PSM and PSM .

It should be noted that in the absence of a PSM only standard routing is utilized. Furthermore routing messages for individual PSMs are controlled according to their own specific configuration files.

Method optionally starts at action when a partner develops a desired Partner Software Function PSF to operate on the reader. The implementing software module of a PSF which is called a PSM is then installed on the RFID reader.

After system boot in optional action attempting to discover a new PSM the reader engine checks a well known directory for the presence of a PSM in configuration files of PSMs.

In action a standard API definition is extended. Extending may be performed in any number of ways. Preferably extending is made so as to reflect PSM requirements. One such way is described in more detail below.

In action a PSM process is hosted. In action the reader is operationally ready to handle standard i.e. native and custom API message types with the extended standard API over a single connection.

Method optionally starts at action when a partner develops a desired Partner Software Function PSF to operate on the reader. In further optional action a PSM is installed by a partner which is the implementing software module of a PSF.

After system boot in optional action PSM starts up i.e. is spawned independently of the reader engine. In optional action the PSM is registered. In action a standard API definition is extended to reflect PSM requirements. In action the reader is operationally ready to handle standard i.e. native and custom API message types with the extended standard API over a single connection.

Numerous details have been set forth in this description which is to be taken as a whole to provide a more thorough understanding of the invention. In other instances well known features have not been described in detail so as not to obscure unnecessarily the invention.

The invention includes combinations and subcombinations of the various elements features functions and or properties disclosed herein. The following claims define certain combinations and subcombinations which are regarded as novel and non obvious. Additional claims for other combinations and subcombinations of features functions elements and or properties may be presented in this or a related document.

