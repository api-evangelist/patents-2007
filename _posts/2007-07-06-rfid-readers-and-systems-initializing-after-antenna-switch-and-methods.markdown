---

title: RFID readers and systems initializing after antenna switch and methods
abstract: RFID readers, reader systems, and methods are provided for processing RFID tags through interruptions for antenna change or other reasons. If the reason for the interruption is an antenna change, the reader restarts processing the tags initializing any operational parameters. If the reason is other than an antenna change, the reader determines whether the operation is to be continued or to be restarted upon power up and proceeds accordingly.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=07920046&OS=07920046&RS=07920046
owner: Impinj, Inc.
number: 07920046
owner_city: Seattle
owner_country: US
publication_date: 20070706
---
This utility patent application is a Continuation In Part CIP of U.S. application Ser. No. 11 749 235 filed on May 16 2007. The benefit of the earlier filing date of the parent application is hereby claimed under 35 U.S.C. 120.

This utility patent application claims the benefit of U.S. Provisional Application Ser. No. 60 832 667 filed on Jul. 21 2006 which is hereby claimed under 35 U.S.C. 119 e . The provisional application is incorporated herein by reference.

Application titled RFID READERS AND SYSTEMS WITH ANTENNA SWITCHING UPON TAG SENSING AND METHODS by the same inventors application Ser. No. 11 749 235 filed with the USPTO on May 16 2007 and assigned to the same assignee 

Application titled RFID READERS AND SYSTEMS WITH ANTENNA SWITCHING UPON DETECTING TOO FEW TAGS AND METHOD by the same inventors application Ser. No. 11 749 281 filed with the USPTO on May 16 2007 and assigned to the same assignee 

Application titled RFID READER SYSTEMS AND METHODS FOR ANTENNAS WITH ADJUSTABLE DUTY CYCLE TO REDUCE CONTRIBUTED INTERFERENCE by the same inventors application Ser. No. 11 749 235 filed with the USPTO on Jun. 28 2007 and assigned to the same assignee 

Application titled RFID READERS AND SYSTEMS PERFORMING PARTIAL OPERATION PER ANTENNA AND METHODS by the same inventors application Ser. No. 11 769 444 filed with the USPTO on Jun. 27 2007 and assigned to the same assignee and

Application titled CHANGING MANNER OF DETERMINING A QUERY PARAMETER Q USED FOR INVENTORYING RFID TAGS by Scott A. Cooper Christopher J. Diorio Todd E. Humes and Vadim P. Lobanov application Ser. No. 11 210 575 filed with the USPTO on Aug. 24 2005 and assigned to the same assignee.

Radio Frequency IDentification RFID systems typically include RFID tags and RFID readers the latter are also known as RFID reader writers or RFID interrogators . RFID systems can be used in many ways for locating and identifying objects to which the tags are attached. RFID systems are particularly useful in product related and service related industries for tracking large numbers of objects being processed inventoried or handled. In such cases an RFID tag is usually attached to an individual item or to its package.

In principle RFID techniques entail using an RFID reader to interrogate one or more RFID tags. The reader transmitting a Radio Frequency RF wave performs the interrogation. A tag that senses the interrogating RF wave responds by transmitting back another RF wave. The tag generates the transmitted back RF wave either originally or by reflecting back a portion of the interrogating RF wave in a process known as backscatter. Backscatter may take place in a number of ways.

The reflected back RF wave may further encode data stored internally in the tag such as a number. The response is demodulated and decoded by the reader which thereby identifies counts or otherwise interacts with the associated item. The decoded data can denote a serial number a price a date a destination other attribute s any combination of attributes and so on.

An RFID tag typically includes an antenna system a power management section a radio section and frequently a logical section a memory or both. In earlier RFID tags the power management section included an energy storage device such as a battery. RFID tags with an energy storage device are known as active tags. Advances in semiconductor technology have miniaturized the electronics so much that an RFID tag can be powered solely by the RF signal it receives. Such RFID tags do not include an energy storage device and are called passive tags.

An RFID reader may utilize antenna switching to cover multiple areas or enhanced coverage of tag populations especially in locations where tags may be moving such as dock doors. In addition to antenna switching some readers may employ Frequency Hopping Spread Spectrum FHSS operation that includes switching of transmit frequencies at predetermined intervals for regulatory and or performance reasons. A complication in processing tags may arise when an antenna switch occurs in the middle of a tag operation such as inventory of tags.

A reader may stop transmitting briefly for a number of additional reasons as well. During the non transmit period tags in the reader s field of view may lose their power new tags may enter the field of view and other changes may occur in the tag population depending on a length of the non transmit period.

This Summary is provided to introduce a selection of concepts in a simplified form that are further described below in the Detailed Description. This Summary is not intended to identify key features or essential features of the claimed subject matter nor is it intended to be used as an aid in determining the scope of the claimed subject matter.

Embodiments are directed to processing RFID tags by an RFID reader system employing antenna switching. When RF transmission is interrupted during a tag processing operation a reason for the interruption may be determined. If the reason is an antenna change the likelihood of a change in tag population is large. Therefore the reader may restart processing the tags by initializing any operational parameters. If the reason is other than an antenna change such as an FHSS frequency switch the reader may determine whether the operation is to be continued or restarted upon power up and proceed accordingly.

This and other features and advantages of the invention will be better understood in view of the Detailed Description and the Drawings in which 

Various embodiments will be described in detail with reference to the drawings where like reference numerals represent like parts and assemblies throughout the several views. Reference to various embodiments does not limit the scope of the invention which is limited only by the scope of the claims attached hereto. Additionally any examples set forth in this specification are not intended to be limiting and merely set forth some of the many possible embodiments for the claimed subject matter.

Throughout the specification and claims the following terms take at least the meanings explicitly associated herein unless the context clearly dictates otherwise. The meanings identified below are not intended to limit the terms but merely provide illustrative examples for the terms. The meaning of a an and the includes plural reference the meaning of in includes in and on. The term connected means a direct electrical connection between the items connected without any intermediate devices. The term coupled means either a direct electrical connection between the items connected or an indirect connection through one or more passive or active intermediary devices. The term circuit means either a single component or a multiplicity of components either active and or passive that are coupled together to provide a desired function. The term signal means at least one current voltage charge temperature data or other measurable quantity. The terms RFID reader and RFID tag are used interchangeably with the terms reader and tag respectively throughout the text and claims.

All of the circuits described in this document may be implemented as circuits in the traditional sense such as with integrated circuits etc. All or some of them can also be implemented equivalently by other ways known in the art such as by using one or more processors Digital Signal Processing DSP a Field Programmable Gate Array FPGA a general purpose micro processor etc.

Reader and tag exchange data via wave and wave . In a session of such an exchange each encodes modulates and transmits data to the other and each receives demodulates and decodes data from the other. The data is modulated onto and decoded from RF waveforms.

Encoding the data in waveforms can be performed in a number of different ways. For example protocols are devised to communicate in terms of symbols also called RFID symbols. A symbol for communicating can be a delimiter a calibration symbol and so on. Further symbols can be implemented for ultimately exchanging binary data such as 0 and 1 if that is desired. In turn when the waveforms are processed internally by reader and tag they can be equivalently considered and treated as numbers having corresponding values and so on.

Tag can be a passive tag or an active tag i.e. having its own power source. Where tag is a passive tag it is powered from wave .

Tag is formed on a substantially planar inlay which can be made in many ways known in the art. Tag includes an electrical circuit which is preferably implemented in an integrated circuit IC . IC is arranged on inlay .

Tag also includes an antenna for exchanging wireless signals with its environment. The antenna is usually flat and attached to inlay . IC is electrically coupled to the antenna via suitable antenna ports not shown in .

The antenna may be made in a number of ways as is well known in the art. In the example of the antenna is made from two distinct antenna segments which are shown here forming a dipole. Many other embodiments are possible using any number of antenna segments.

In some embodiments an antenna can be made with even a single segment. Different places of the segment can be coupled to one or more of the antenna ports of IC . For example the antenna can form a single loop with its ends coupled to the ports. When the single segment has more complex shapes it should be remembered that at the frequencies of RFID wireless communication even a single segment could behave like multiple segments.

In operation a signal is received by the antenna and communicated to IC . IC both harvests power and responds if appropriate based on the incoming signal and its internal state. In order to respond by replying IC modulates the reflectance of the antenna which generates the backscatter from a wave transmitted by the reader. Coupling together and uncoupling the antenna ports of IC can modulate the reflectance as can a variety of other means.

In the embodiment of antenna segments are separate from IC . In other embodiments antenna segments may alternately be formed on IC and so on.

The components of the RFID system of may communicate with each other in any number of modes. One such mode is called full duplex. Another such mode is called half duplex and is described below.

RFID reader and RFID tag talk and listen to each other by taking turns. As seen on axis TIME when reader talks to tag the communication session is designated as R T and when tag talks to reader the communication session is designated as T R . Along the TIME axis a sample R T communication session occurs during a time interval and a following sample T R communication session occurs during a time interval . Of course interval is typically of a different duration than interval here the durations are shown approximately equal only for purposes of illustration.

According to blocks and RFID reader talks during interval and listens during interval . According to blocks and RFID tag listens while reader talks during interval and talks while reader listens during interval .

In terms of actual technical behavior during interval reader talks to tag as follows. According to block reader transmits wave which was first described in . At the same time according to block tag receives wave and processes it to extract data and so on. Meanwhile according to block tag does not backscatter with its antenna and according to block reader has no wave to receive from tag .

During interval tag talks to reader as follows. According to block reader transmits a Continuous Wave CW which can be thought of as a carrier signal that ideally encodes no information. As discussed before this carrier signal serves both to be harvested by tag for its own internal power needs and also as a wave that tag can backscatter. Indeed during interval according to block tag does not receive a signal for processing. Instead according to block tag modulates the CW emitted according to block so as to generate backscatter wave . Concurrently according to block reader receives backscatter wave and processes it.

In the above an RFID reader interrogator may communicate with one or more RFID tags in any number of ways. Some such ways are called protocols. A protocol is a specification that calls for specific manners of signaling between the reader and the tags.

One such protocol is called the Specification for RFID Air Interface EPC TM Radio Frequency Identity Protocols Class 1 Generation 2 UHF RFID Protocol for Communications at 860 MHz 960 MHz which is also colloquially known as the Gen2 Spec . The Gen2 Spec has been ratified by EPCglobal which is an organization that maintains a website at at the time this document is initially filed with the USPTO.

It was described above how reader and tag communicate in terms of time. In addition communications between reader and tag may be restricted according to frequency. One such restriction is that the available frequency spectrum may be partitioned into divisions that are called channels. Different partitioning manners may be specified by different regulatory jurisdictions and authorities e.g. FCC in North America CEPT in Europe etc. .

The reader typically transmits with a transmission spectrum that lies within one channel. In some regulatory jurisdictions the authorities permit aggregating multiple channels into one or more larger channels but for all practical purposes an aggregate channel can again be considered a single albeit larger individual channel.

Tag can respond with a backscatter that is modulated directly onto the frequency of the reader s emitted CW also called baseband backscatter. Alternatively Tag can respond with a backscatter that is modulated onto a frequency developed by Tag that is different from the reader s emitted CW and this modulated tag frequency is then impressed upon the reader s emitted CW. This second type of backscatter is called subcarrier backscatter. The subcarrier frequency can be within the reader s channel can straddle the boundaries with the adjacent channel or can be wholly outside the reader s channel.

A number of jurisdictions require a reader to hop to a new channel on a regular basis. When a reader hops to a new channel it may encounter RF energy there that could interfere with communications.

Embodiments of the present disclosure can be useful in different RFID environments for example in the deployment of RFID readers in sparse or dense reader environments in environments with networked and disconnected readers such as where a hand held reader may enter the field of networked readers in environments with mobile readers or in environments with other interference sources. It will be understood that the present embodiments are not limited to operation in the above environments but may provide improved operation in such environments.

A driver can send a driving signal to cause its respective antennas to transmit an RF wave which is analogous to RF wave of . In addition RF wave can be backscattered from the RFID tags analogous to RF wave of . Backscattered RF wave becomes a signal sensed by driver .

Unit also has other components such as hardware and software which may be described in more detail later in this document. Components control drivers and as such cause RF wave to be sent and interpret the sensed backscattered RF wave . Optionally and preferably there is a communication link to other equipment such as computers and the like for remote operation of system .

Local block is responsible for communicating with the tags. Local block includes a block of an antenna and a driver of the antenna for communicating with the tags. Some readers like that shown in local block contain a single antenna and driver. Some readers contain multiple antennas and drivers and a method to switch signals among them including sometimes using different antennas for transmitting and for receiving. And some readers contain multiple antennas and drivers that can operate simultaneously. A demodulator decoder block demodulates and decodes backscattered waves received from the tags via antenna block . Modulator encoder block encodes and modulates an RF wave that is to be transmitted to the tags via antenna block .

Local block additionally includes an optional local processor . Processor may be implemented in any number of ways known in the art. Such ways include by way of examples and not of limitation digital and or analog processors such as microprocessors and digital signal processors DSPs controllers such as microcontrollers software running in a machine such as a general purpose computer programmable circuits such as Field Programmable Gate Arrays FPGAs Field Programmable Analog Arrays FPAAs Programmable Logic Devices PLDs Application Specific Integrated Circuits ASIC any combination of one or more of these and so on. In some cases some or all of the decoding function in block the encoding function in block or both may be performed instead by processor .

Local block additionally includes an optional local memory . Memory may be implemented in any number of ways known in the art. Such ways include by way of examples and not of limitation nonvolatile memories NVM read only memories ROM random access memories RAM any combination of one or more of these and so on. Memory if provided can include programs for processor to run if provided.

In some embodiments memory stores data read from tags or data to be written to tags such as Electronic Product Codes EPCs Tag Identifiers TIDs and other data. Memory can also include reference data that is to be compared to the EPC codes instructions and or rules for how to encode commands for the tags modes for controlling antenna and so on. In some of these embodiments local memory is provided as a database.

Some components of local block typically treat the data as analog such as the antenna driver block . Other components such as memory typically treat the data as digital. At some point there is a conversion between analog and digital. Based on where this conversion occurs a whole reader may be characterized as analog or digital but most readers contain a mix of analog and digital functionality.

If remote components are indeed provided they are coupled to local block via an electronic communications network . Network can be a Local Area Network LAN a Metropolitan Area Network MAN a Wide Area Network WAN a network of networks such as the internet and so on. In turn local block then includes a local network connection for communicating with network .

There can be one or more remote component s . If more than one they can be located at the same place with each other or in different places. They can access each other and local block via network or via other similar networks and so on. Accordingly remote component s can use respective remote network connections. Only one such remote network connection is shown which is similar to local network connection etc.

Remote component s can also include a remote processor . Processor can be made in any way known in the art such as was described with reference to local processor .

Remote component s can also include a remote memory . Memory can be made in any way known in the art such as was described with reference to local memory . Memory may include a local database and a different database of a Standards Organization such as one that can reference EPCs.

Of the above described elements it is advantageous to consider a combination of these components designated as operational processing block . Block includes those that are provided of the following local processor remote processor local network connection remote network connection and by extension an applicable portion of network that links connection with connection . The portion can be dynamically changeable etc. In addition block can receive and decode RF waves received via antenna and cause antenna to transmit RF waves according to what it has processed.

Block includes either local processor or remote processor or both. If both are provided remote processor can be made such that it operates in a way complementary with that of local processor . In fact the two can cooperate. It will be appreciated that block as defined this way is in communication with both local memory and remote memory if both are present.

Accordingly block is location agnostic in that its functions can be implemented either by local processor or by remote processor or by a combination of both. Some of these functions are preferably implemented by local processor and some by remote processor . Block accesses local memory or remote memory or both for storing and or retrieving data.

Reader system operates by block generating communications for RFID tags. These communications are ultimately transmitted by antenna block with modulator encoder block encoding and modulating the information on an RF wave. Then data is received from the tags via antenna block demodulated and decoded by demodulator decoder block and processed by processing block .

RFID reader system includes one or more antennas and an RF Front End for interfacing with antenna s . These can be made as described above. In addition Front End typically includes analog components.

System also includes a Signal Processing module . In this embodiment module exchanges waveforms with Front End such as I and Q waveform pairs. In some embodiments signal processing module is implemented by itself in an FPGA.

System also includes a Physical Driver module which is also known as Data Link. In this embodiment module exchanges bits with module . Data Link can be the stage associated with framing of data. In one embodiment module is implemented by a Digital Signal Processor.

System additionally includes a Media Access Control module which is also known as MAC layer. In this embodiment module exchanges packets of bits with module . MAC layer can be the stage for making decisions for sharing the medium of wireless communication which in this case is the air interface. Sharing can be between reader system and tags or between system with another reader or between tags or a combination. In one embodiment module is implemented by a Digital Signal Processor.

System moreover includes an Application Programming Interface module which is also known as API Modem API and MAPI. In some embodiments module is itself an interface for a user.

System further includes a host processor . Processor exchanges signals with MAC layer via module . In some embodiments host processor is not considered as a separate module but one that includes some of the above mentioned modules of system . A user interface is coupled to processor and it can be manual automatic or both.

Host processor can include applications for system . In some embodiments elements of module may be distributed between processor and MAC layer .

It will be observed that the modules of system form something of a chain. Adjacent modules in the chain can be coupled by the appropriate instrumentalities for exchanging signals. These instrumentalities include conductors buses interfaces and so on. These instrumentalities can be local e.g. to connect modules that are physically close to each other or over a network for remote communication.

The chain is used in opposite directions for receiving and transmitting. In a receiving mode wireless waves are received by antenna s as signals which are in turn processed successively by the various modules in the chain. Processing can terminate in any one of the modules. In a transmitting mode initiation can be in any one of these modules. That which is to be transmitted becomes ultimately signals for antenna s to transmit as wireless waves.

The architecture of system is presented for purposes of explanation and not of limitation. Its particular subdivision into modules need not be followed for creating embodiments according to the invention. Furthermore the features of the invention can be performed either within a single one of the modules or by a combination of them.

As mentioned previously a single RFID reader system may have several antennas. Due to the Tx Rx chain the RFID reader system selects drives and listens from only one of its antennas at any given time. Furthermore a combination of RFID systems is typically deployed and they could coordinate antenna transmission between themselves to limit interference.

To complicate the design of multiple antenna reader systems antennas may be facing different directions. Time spent on an antenna that views no tags while the other antenna has tags in view represents missed performance missed opportunity to identify tags . Even though the antennas could all be facing at the same location different ones view different groups of tags and may have differential effectiveness. For example a dock door with two antennas at different height on same side of the door connected to the same reader. In such a scenario tag placement in the pallet would define which antenna is more likely to find which tags. Some tags may only be read by one of the antennas.

Moreover synchronizing antennas between readers requires precision to limit system downtime. Synchronizing clocks accurately on separate processors is a complex problem. In addition readers that view no tags and still transmit using their antennas increase the noise floor in a system deployment unnecessarily. This may cause degradation in the performance of other readers in the deployment which do view tags. Finally antenna switching may need to be controlled at the speed of the air protocol. With the increased speed of new generation air protocols increased demands are put on antenna switching.

Some of the solutions to challenges of static antenna switching mechanisms include user specifying time spent per antenna user specifying order in which to cycle through antennas or user specifying external triggers to start antenna operation. These approaches have their own limitations such as users or installers having to configure the reader s at time of deployment for a specific scenario which may be costly and require tuning if scenario changes e.g. conveyor belt speed changes use of humans or forklifts for pushing pallets through the field of view of readers etc. .

Additionally tags may not be rapidly detected in a particular antenna read zone causing delay in seeing tags for the first time. Antennas may be grouped into sources e.g. in a symmetrical deployment like a dock door each of the 2 sources may be given same amount of time to see tags . This effectively gives a 50 duty cycle per door even if no tags are in that door. External triggers are also challenging to deploy and may break easily.

Inventorying of tags is one of the most common tag operations. During an inventory operation a reader may communicate with tags in its field of view multiple times cause tags to change their state and so on. Thus the interruption of an inventory operation may result in missed tags double processing of tags wasted time and reader resources.

Diagram illustrates a reader beginning a first inventory operation A while transmitting on frequency . The inventory process is however interrupted by the reader switching to frequency due to an FHSS operation. During the frequency switch the transmitter is disabled thus interrupting the RF communication .

Depending on its configuration the reader may continue or restart the inventory operation when the transmission begins on frequency completing the inventory process later during the transmission on frequency . A restart may unnecessarily prolong the operation and waste reader resources because the tag population is unlikely to change substantially when only the frequency changes. Therefore the reader may simply continue the inventory operation after the frequency switch. A second inventory process B may then be started on frequency .

The second inventory process B is first interrupted by the frequency switch from frequency to frequency through which the operation continues. The inventory operation is interrupted for the second time by an antenna change from antenna to antenna . The reader also continues the operation through the antenna switch completing on frequency .

The problem with this approach is that the tag population in the field of view of antenna may be substantially different from the tag population in the field of view of antenna . Thus the inventory may be completed on two disjointed tag populations with erroneous results or prolonged operation time and wasted resources.

The invention also includes methods. Some are methods of operation of an RFID reader or RFID reader system. Others are methods for controlling an RFID reader or RFID reader system.

These methods can be implemented in any number of ways including the structures described in this document. One such way is by machine operations of devices of the type described in this document.

Another optional way is for one or more of the individual operations of the methods to be performed in conjunction with one or more human operators performing some. These human operators need not be collocated with each other but each can be only with a machine that performs a portion of the program.

The invention additionally includes programs and methods of operation of the programs. A program is generally defined as a group of steps or operations leading to a desired result due to the nature of the elements in the steps and their sequence. A program is usually advantageously implemented as a sequence of steps or operations for a processor such as the structures described above.

Performing the steps instructions or operations of a program requires manipulation of physical quantities. Usually though not necessarily these quantities may be transferred combined compared and otherwise manipulated or processed according to the steps or instructions and they may also be stored in a computer readable medium. These quantities include for example electrical magnetic and electromagnetic charges or particles states of matter and in the more general case can include the states of any physical devices or elements. It is convenient at times principally for reasons of common usage to refer to information represented by the states of these quantities as bits data bits samples values symbols characters terms numbers or the like. It should be borne in mind however that all of these and similar terms are associated with the appropriate physical quantities and that these terms are merely convenient labels applied to these physical quantities individually or in groups.

Even though it is said that the program may be stored in a computer readable medium it should be clear to a person skilled in the art that it need not be a single memory or even a single machine. Various portions modules or features of it may reside in separate memories or even separate machines. The separate machines may be connected directly or through a network such as a local access network LAN or a global network such as the Internet.

The invention furthermore includes storage media. Such media individually or in combination with others have stored thereon instructions of a program made according to the invention. A storage medium according to the invention is a computer readable medium such as a memory and is read by a processor of the type mentioned above. If a memory it can be implemented in a number of ways such as Read Only Memory ROM Random Access Memory RAM etc. some of which are volatile and some non volatile.

Often for the sake of convenience only it is desirable to implement and describe a program as software. The software can be unitary or thought in terms of various interconnected distinct software modules.

This detailed description is presented largely in terms of flowcharts algorithms and symbolic representations of operations on data bits on and or within at least one medium that allows computational operations such as a computer with memory. Indeed such descriptions and representations are the type of convenient labels used by those skilled in programming and or the data processing arts to effectively convey the substance of their work to others skilled in the art. A person skilled in the art of programming may use these descriptions to readily generate specific instructions for implementing a program according to the present invention.

Embodiments of an RFID reader system can be implemented as a combination of hardware and software. It is advantageous to consider such a system as subdivided into components or modules. A person skilled in the art will recognize that some of these components or modules can be implemented as hardware some as software some as firmware and some as a combination.

Process begins with operation where a reader transmits an RF signal for a tag operation through a first antenna.

According to a next operation the RF signal is turned off by the reader. The signal may be turned off for a variety of reasons such as a frequency change due to an FHSS operation an antenna change a power interrupt completion of an operation and the like.

According to a next optional operation the reason for turning off the RF signal is determined by the reader.

According to a next decision operation a determination is made whether the reason for turning off the RF signal is an antenna change. If the reason is antenna change the reader switches to a next antenna at subsequent operation .

According to operation following operation the reader transmits the RF signal for a restarted tag operation through the next antenna and may initialize any operational parameters.

If the determination at decision operation is that the reason for turning off the RF signal is not an antenna change process continues to operation where the reader determines whether the tag operation needs to be restarted.

If the signal turn off is for a brief duration and the tag population within the reader s field of view may remain substantially same the operation may not need to be restarted.

According to a next decision operation a determination is made whether a restart is necessary. If a restart is necessary process may continue to operation . If a restart is not necessary a signal may be transmitted for continued tag operation at subsequent operation .

After operation process may optionally return to operation . Process also returns to operation after operation .

Process begins with optional decision operation where a determination is made whether the RF signal turn off is for an antenna switch or a frequency hop.

If the reason is frequency hop another determination is made at the next decision operation whether an antenna change is close. If the antenna change is not close the tag operation is continued using the next frequency at next operation .

If the antenna change is close the reader may start a new inventory round with initialized parameters using a next frequency through the next antenna at operation .

If the determination at optional decision operation is that the reason for the signal turn off is an antenna switch another determination is made at next decision operation whether a frequency switch is close.

If the frequency switch is close the reader starts a new inventory round with initialized parameters using a next frequency through the next antenna at operation . Otherwise the reader starts a new operation through the next antenna using the same frequency at next operation .

The operations included in processes and are for illustration purposes. The described methods may be implemented by similar processes with fewer or additional steps as well as in different order of operations using the principles described herein.

According to one embodiment a method for an RFID reader system employing antenna switching may include causing a first signal for a first tag operation to be radiated through a first antenna turning off the first signal for a first reason determining whether the first reason is an antenna change from the first antenna to a second antenna and if the first reason is the antenna change causing a second signal to be radiated through the second antenna for a second tag operation that does not continue the first tag operation. The first tag operation may include a tag inventory operation.

According to another embodiment the first tag operation may further include a Tag Population Check TPC before starting the tag inventory operation. A tag population check according to embodiments may include transmitting a signal and listening to determine if any tags are responding to the signal or not. If the first reason is an antenna change the second tag operation may include restarting a tag inventory operation through the second antenna. The second tag operation may further include another TPC before restarting the tag inventory operation through the second antenna. Moreover the second signal may be radiated responsive to detecting that tags are present in the reader s field of view.

According to a further embodiment the first signal may dictate an initial Q parameter for performing the inventory operation according to a Q algorithm and the second signal may dictate the initial Q parameter or a different Q parameter for restarting the inventory according to the Q algorithm.

The antenna change from the first antenna to the second antenna may include selecting the second antenna to radiate the second signal from among a plurality of antennas associated with the RFID reader system based on one of a predefined algorithm an order of available antennas and by random selection in which the selection is different depending on whether any tags are sensed through the first antenna. Furthermore selecting the second antenna may be delayed until an operation for a specific tag is completed.

According to yet another embodiment the method may further include turning off the first signal for a second reason that is other than for an antenna change from the first antenna to the second antenna determining whether the first tag operation is to be continued due to the second reason and if the first tag operation is not to be continued causing a third signal to be radiated through the first antenna for a third tag operation.

The second reason may be a change from a first frequency to a second frequency for a Frequency Hopping Spread Spectrum FHSS operation of the reader system. The second reason may be a completion of the first tag operation where the method further includes restarting another tag operation when the third signal is radiated through the first antenna without repeating a portion of the first tag operation performed when the first signal is radiated.

According to a yet further embodiment the first tag operation may be a tag inventory operation and the method may further include continuing to inventory the tags when the third signal is radiated without repeating a portion of the inventory performed when the first signal is radiated performing a TPC before beginning the inventory when the first signal is radiated where the TPC is not repeated when the second signal is radiated.

The first signal may dictate an initial Q parameter for performing the inventory operation according to a Q algorithm and the second signal may use a Q parameter value determined by the reader when the first operation is interrupted. If the inventory is completed about an expiration of a dwell period on a first frequency the frequency change due to the FHSS operation and an antenna change from the first antenna to the second antenna may be combined. Combining the frequency change and the antenna change may include performing the antenna change earlier than a predefined time or performing the frequency change before the expiration of the dwell period.

An antenna change may result in the reader facing a substantially different tag population. In consequence the tag operation e.g. an inventory operation using a Q algorithm may have to be restarted with initialized parameters.

As illustrated by diagram the reader uses frequencies and through during the FHSS operation with RF interruptions between different frequencies and RF interruption for changing antennas from antenna to antenna . A first tag operation begins during the transmission of the RF signal using frequency .

When the first RF interruption occurs the first tag operation is continued upon the reader beginning to transmit on frequency resulting in uninterrupted tag operation by frequency hopping. Similarly the second operation is started on the second frequency.

When the antenna change occurs interrupting the second operation however the reader restarts the second operation on frequency . Another frequency switch interruption does not cause a restart and the second operation is completed on frequency .

Because the tag population is likely to change between the two antennas the reader does not risk performing a tag operation over distinct tag populations and wasting time to recover errors.

As shown in diagram the reader begins its operations by performing a TPC on a tag population while transmitting on frequency through the first antenna . The TPC is followed by inventory operation A . When the frequency dwell time expires the reader switches to frequency after a brief RF interruption still through the first antenna. Because the reason for the RF interruption is frequency switch the inventory operation is continued without a restart after the reader begins transmitting on frequency .

After completion of the inventory operation a second inventory operation B is started while the reader is still transmitting on frequency through the first antenna without a renewed TPC. The second inventory operation B is also continued without a restart when the reader switches from frequency to frequency through the first antenna.

When the operation s are interrupted due to an antenna change from the first antenna to a second antenna however a new TPC is performed because the tag population may have changed. After the TPC operation a first inventory operation is restarted through the second antenna with initialized parameters Q parameter value .

Another RF interruption due to frequency switch through the second antenna does not cause the new inventory operation to be restarted. Similar to the previous operations through the first antenna the inventory operation A is continued when the reader switches to frequency still transmitting through the second antenna.

In this description numerous details have been set forth in order to provide a thorough understanding. In other instances well known features have not been described in detail in order to not obscure unnecessarily the description.

A person skilled in the art will be able to practice the embodiments in view of this description which is to be taken as a whole. The specific embodiments as disclosed and illustrated herein are not to be considered in a limiting sense. Indeed it should be readily apparent to those skilled in the art that what is described herein may be modified in numerous ways. Such ways can include equivalents to what is described herein.

The following claims define certain combinations and sub combinations of elements features steps and or functions which are regarded as novel and non obvious. Additional claims for other combinations and sub combinations may be presented in this or a related document.

