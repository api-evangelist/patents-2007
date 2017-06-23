---

title: RFID readers and systems with antenna switching upon detecting too few tags and methods
abstract: RFID readers, reader systems, and methods are provided that utilize smart antenna switching. A first signal is transmitted from a first antenna estimating presence of tags within the antennas field of view. If fewer than a predefined number of tags are estimated, the system switches to a second antenna. Otherwise, the tags found in the field of view of the first antenna are inventoried before switching to the second antenna.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08120494&OS=08120494&RS=08120494
owner: Impinj, Inc.
number: 08120494
owner_city: Seattle
owner_country: US
publication_date: 20070516
---
This utility patent application claims the benefit of U.S. Provisional Application Ser. No. 60 832 667 filed on Jul. 21 2006 which is hereby claimed under 35 U.S.C. 119 e . The provisional application is incorporated herein by reference.

This utility patent application claims the benefit of U.S. Provisional Application Ser. No. 60 839 746 filed on Aug. 24 2006 which is hereby claimed under 35 U.S.C. 119 e . The provisional application is incorporated herein by reference.

This application may be found to be related to the following applications all of which are incorporated herein by reference 

Application titled RFID READERS AND SYSTEMS WITH ANTENNA SWITCHING UPON TAG SENSING AND METHODS by the same inventors filed with the USPTO on the same day as the present application and due to be assigned to the same assignee Ser. No. 11 749 235 and

Application titled CHANGING MANNER OF DETERMINING A QUERY PARAMETER Q USED FOR INVENTORYING RFID TAGS by Scott A. Cooper Christopher J. Diorio Todd E. Humes and Vadim P. Lobanov application Ser. No. 11 210 575 filed with the USPTO on Aug. 24 2005 and assigned to the same assignee.

Radio Frequency IDentification RFID systems typically include RFID tags and RFID readers the latter are also known as RFID reader writers or RFID interrogators . RFID systems can be used in many ways for locating and identifying objects to which the tags are attached. RFID systems are particularly useful in product related and service related industries for tracking large numbers of objects being processed inventoried or handled. In such cases an RFID tag is usually attached to an individual item or to its package.

In principle RFID techniques entail using an RFID reader to interrogate one or more RFID tags. The reader transmitting a Radio Frequency RF wave performs the interrogation. A tag that senses the interrogating RF wave responds by transmitting back another RF wave. The tag generates the transmitted back RF wave either originally or by reflecting back a portion of the interrogating RF wave in a process known as backscatter. Backscatter may take place in a number of ways.

The reflected back RF wave may further encode data stored internally in the tag such as a number. The response is demodulated and decoded by the reader which thereby identifies counts or otherwise interacts with the associated item. The decoded data can denote a serial number a price a date a destination other attribute s any combination of attributes and so on.

An RFID tag typically includes an antenna system a power management section a radio section and frequently a logical section a memory or both. In earlier RFID tags the power management section included an energy storage device such as a battery. RFID tags with an energy storage device are known as active tags. Advances in semiconductor technology have miniaturized the electronics so much that an RFID tag can be powered solely by the RF signal it receives. Such RFID tags do not include an energy storage device and are called passive tags.

A single RFID reader system may have several antennas. Due to the Tx Rx chain the RFID reader system selects drives and listens from only one of its antennas at any given time. A further complication arises when a combination of RFID systems is typically deployed and they need to coordinate antennas between themselves to limit interference.

Commonly used static antenna driving techniques may result in wasted time on antennas where no tags are in the field of view not enough time on antennas where many tags are in their respective fields of view and increased interference in multiple reader systems where transmission is caused through antennas even when no tags are in the field of view.

This Summary is provided to introduce a selection of concepts in a simplified form that are further described below in the Detailed Description. This Summary is not intended to identify key features or essential features of the claimed subject matter nor is it intended to be used as an aid in determining the scope of the claimed subject matter.

Embodiments are directed to switching antennas in an RFID reader system while performing tag population checks instead of inventorying of all tags within one antennas field of view. Presence of tags is first detected through one antenna. If the number of tags is smaller than a predefined threshold the system switches to another antenna without inventorying the tags detected in the field of view of the first antenna.

This and other features and advantages of the invention will be better understood in view of the Detailed Description and the Drawings in which 

Various embodiments will be described in detail with reference to the drawings where like reference numerals represent like parts and assemblies throughout the several views. Reference to various embodiments does not limit the scope of the invention which is limited only by the scope of the claims attached hereto. Additionally any examples set forth in this specification are not intended to be limiting and merely set forth some of the many possible embodiments for the claimed subject matter.

Throughout the specification and claims the following terms take at least the meanings explicitly associated herein unless the context clearly dictates otherwise. The meanings identified below are not intended to limit the terms but merely provide illustrative examples for the terms. The meaning of a an and the includes plural reference the meaning of in includes in and on. The term connected means a direct electrical connection between the items connected without any intermediate devices. The term coupled means either a direct electrical connection between the items connected or an indirect connection through one or more passive or active intermediary devices. The term circuit means either a single component or a multiplicity of components either active and or passive that are coupled together to provide a desired function. The term signal means at least one current voltage charge temperature data or other measurable quantity. The terms RFID reader and RFID tag are used interchangeably with the terms reader and tag respectively throughout the text and claims.

All of the circuits described in this document may be implemented as circuits in the traditional sense such as with integrated circuits etc. All or some of them can also be implemented equivalently by other ways known in the art such as by using one or more processors Digital Signal Processing DSP a Floating Point Gate Array FPGA a general purpose micro processor etc.

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

One such protocol is called the Specification for RFID Air Interface EPC Radio Frequency Identity Protocols Class 1 Generation 2 UHF RFID Protocol for Communications at 860 MHz 960 MHz which is also colloquially known as the Gen2 Spec . The Gen2 Spec has been ratified by EPCglobal which is an organization that maintains a website at at the time this document is initially filed with the USPTO.

It was described above how reader and tag communicate in terms of time. In addition communications between reader and tag may be restricted according to frequency. One such restriction is that the available frequency spectrum may be partitioned into divisions that are called channels. Different partitioning manners may be specified by different regulatory jurisdictions and authorities e.g. FCC in North America CEPT in Europe etc. .

The reader typically transmits with a transmission spectrum that lies within one channel. In some regulatory jurisdictions the authorities permit aggregating multiple channels into one or more larger channels but for all practical purposes an aggregate channel can again be considered a single albeit larger individual channel. Tag can respond with a backscatter that is modulated directly onto the frequency of the reader s emitted CW also called baseband backscatter. Alternatively Tag can respond with a backscatter that is modulated onto a frequency developed by Tag that is different from the reader s emitted CW and this modulated tag frequency is then impressed upon the reader s emitted CW. This second type of backscatter is called subcarrier backscatter. The subcarrier frequency can be within the reader s channel can straddle the boundaries with the adjacent channel or can be wholly outside the reader s channel.

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

As mentioned previously a single RFID reader system may have several antennas. Due to the Tx Rx chain the RFID reader system selects drives and listens from only one of its antennas at any given time. Furthermore a combination of RFID systems is typically deployed and they need to coordinate antennas between themselves to limit interference.

To complicate the design of multiple antenna reader systems antennas may be facing different directions. Time spent on an antenna that views no tags while the other antenna has tags in view represents missed performance missed opportunity to identify tags . Even though the antennas could all be facing at the same location different ones view different groups of tags and may have differential effectiveness. For example a dock door with two antennas at different heights on same side of the door connected to the same reader. In such a scenario tag placement in the pallet would define which antenna is more likely to find which tags. Some tags may only be read by one of the antennas.

Moreover synchronizing antennas between readers requires precision to limit system downtime. Synchronizing clocks accurately on separate processors is a complex problem. In addition readers that view no tags and still transmit using their antennas increase the noise floor in a system deployment unnecessarily. This may cause degradation in the performance of other readers in the deployment which do view tags. Finally antenna switching may need to be controlled at the speed of the air protocol. With the increased speed of new generation air protocols increased demands are put on antenna switching.

Some of the solutions to challenges of static antenna switching mechanisms include user specifying time spent per antenna user specifying order in which to cycle through antennas or user specifying external triggers to start antenna operation. These approaches have their own limitations such as users or installers having to configure the reader s at time of deployment for a specific scenario which may be costly and require tuning if scenario changes e.g. conveyor belt speed changes use of humans or forklifts for pushing pallets through the field of view of readers etc. .

Additionally tags may not be rapidly detected in a particular antenna read zone causing delay in seeing tags for the first time. Antennas may be grouped into sources e.g. in a symmetrical deployment like a dock door each of the 2 sources may be given same amount of time to see tags . This effectively gives a 50 duty cycle per door even if no tags are in that door. External triggers are also challenging to deploy and may break easily.

Diagram A illustrates one of the problems with conventional antenna switching methods where commonly a predetermined time is allocated to each antenna associated with the RFID reader system.

It should be noted while the term antenna is used throughout this document the principles described herein are applicable to reader systems where multiple antennas are used in connection with RF ports. For example a reader may employ four RF ports with two antennas attached to each RF port. In that scenario and similar ones the same principles described for the embodiments below apply to the RF ports as they would to the antennas.

Referring back to diagram A a conventional RFID reader system allocates equal periods of time to four antennas for antenna for antenna for antenna for antenna and so on . Thus period is dedicated to inventorying of tags in the field of view of antenna . The reader switches to antenna from antenna regardless of whether any tags are found or whether the inventorying of found tags is completed.

As discussed previously tags are not always stationary. In applications such as dock doors tags may be moving in and out of the field of view of one of the antennas constantly. Hence a problem of latency is encountered. As shown by reference numeral in a worst case latency scenario a tag may arrive in the field of view of antenna shortly after the reader switches from antenna to antenna . The arriving tag may be inventoried only after the reader completes checking all other antennas and switches back to antenna . Thus the inventorying of the tag is delayed by almost the period it takes the reader to check three antennas.

Diagram B illustrates another aspect of the problem s with conventional antenna switching mechanisms at antenna level. Upon turning on the RF signal a first fixed period is dedicated to inventorying tags within the field of view of antenna . However a few tags may be found at the beginning of the fixed period as shown by reference numeral and the inventory process completed before period ends. If no additional tags are found the remainder of period is wasted time on antenna as illustrated by reference numeral .

Furthermore a number of tags may be found in the field of view of antenna during period . If the number of tags is such that their inventory cannot be completed within period the inventory process is cut off at the end of and the reader switches to another antenna forcing the inventory process to begin either from the start. Some readers may implement complicated algorithms to remember the tags during the first attempt to inventory through antenna but that approach is not only expensive in terms of processing resources but may not be reliable when tags are constantly moving in and out of the field of view.

The invention also includes methods. Some are methods of operation of an RFID reader or RFID reader system. Others are methods for controlling an RFID reader or RFID reader system.

These methods can be implemented in any number of ways including the structures described in this document. One such way is by machine operations of devices of the type described in this document.

Another optional way is for one or more of the individual operations of the methods to be performed in conjunction with one or more human operators performing some. These human operators need not be collocated with each other but each can be only with a machine that performs a portion of the program.

The invention additionally includes programs and methods of operation of the programs. A program is generally defined as a group of steps or operations leading to a desired result due to the nature of the elements in the steps and their sequence. A program is usually advantageously implemented as a sequence of steps or operations for a processor such as the structures described above.

Performing the steps instructions or operations of a program requires manipulation of physical quantities. Usually though not necessarily these quantities may be transferred combined compared and otherwise manipulated or processed according to the steps or instructions and they may also be stored in a computer readable medium. These quantities include for example electrical magnetic and electromagnetic charges or particles states of matter and in the more general case can include the states of any physical devices or elements. It is convenient at times principally for reasons of common usage to refer to information represented by the states of these quantities as bits data bits samples values symbols characters terms numbers or the like. It should be borne in mind however that all of these and similar terms are associated with the appropriate physical quantities and that these terms are merely convenient labels applied to these physical quantities individually or in groups.

The invention furthermore includes storage media. Such media individually or in combination with others have stored thereon instructions of a program made according to the invention. A storage medium according to the invention is a computer readable medium such as a memory and is read by a processor of the type mentioned above. If a memory it can be implemented in a number of ways such as Read Only Memory ROM Random Access Memory RAM etc. some of which are volatile and some non volatile.

Even though it is said that the program may be stored in a computer readable medium it should be clear to a person skilled in the art that it need not be a single memory or even a single machine. Various portions modules or features of it may reside in separate memories or even separate machines. The separate machines may be connected directly or through a network such as a local access network LAN or a global network such as the Internet.

Often for the sake of convenience only it is desirable to implement and describe a program as software. The software can be unitary or thought in terms of various interconnected distinct software modules.

This detailed description is presented largely in terms of flowcharts algorithms and symbolic representations of operations on data bits on and or within at least one medium that allows computational operations such as a computer with memory. Indeed such descriptions and representations are the type of convenient labels used by those skilled in programming and or the data processing arts to effectively convey the substance of their work to others skilled in the art. A person skilled in the art of programming may use these descriptions to readily generate specific instructions for implementing a program according to the present invention.

Embodiments of an RFID reader system can be implemented as a combination of hardware and software. It is advantageous to consider such a system as subdivided into components or modules. A person skilled in the art will recognize that some of these components or modules can be implemented as hardware some as software some as firmware and some as a combination.

Process begins at operation where an estimate of how many tags there are in an antenna s field of view is performed by the reader. This may be performed by tag population check which includes transmitting a signal and listening to determine if any tags are responding to the signal or not.

The number of present tags may also be estimated by determining a power of the tag response signals and comparing that to an expected power of a single tag response.

According to a next decision operation a determination is made whether fewer than a predefined number of expected tag replies are detected. If more than the expected number of tags are detected processing advances to operation where tags in the field of view of the antenna are inventoried.

According to a next operation following fewer than the expected number of tags having been detected at decision operation or operation another antenna is selected for further operations.

After completing operation the process may return to operation for performing another tag population estimate through the selected other antenna. As discussed below a reader system may include a plurality of antennas and the antenna selection may be based on an order of antennas a pseudo random algorithm user specification and the like.

Some of the operations of process A are similar to likewise numbered operations of process . Process A begins with two operations grouped together as representing the tag population check employing a non persistent session.

According to a next decision operation a determination is made whether fewer than an expected number of tags are detected.

If more than the expected number of tag responses are detected those tags are inventoried at operation .

According to a next operation following fewer than expected number of tag detection at decision operation or operation another antenna is selected for further operations. After completing operation the process may return to operation for performing another tag population estimate through the selected other antenna.

Some of the operations of process B are similar to likewise numbered operations of processes and A. Process B begins with four operations grouped together as representing the tag population check employing a persistent session. The persistent session is the same session as the inventory process.

According to a first operation a query command with a Q parameter of 0 value is transmitted for detecting tags. In a persistent session tag responses may be directed to target session flag state A or B. Therefore the first query command is directed at target session flag state A.

According to a next decision operation a determination is made whether fewer than an expected number of tag replies are detected for target session flag state A. If more tag replies than the expected number are detected the tags may be inventoried at next operation . Otherwise processing advances to operation .

According to a next operation another query command with a Q parameter of 0 value is transmitted for target session flag state B.

According to a next decision operation a determination is made whether less than the expected number of tag replies were detected for target session flag state B. If more tag replies than the expected number were detected the tags may be inventoried at next operation . Otherwise processing advances to operation .

According to a next operation following detection of fewer than expected tags at decision operation or operation another antenna is selected for further operations. After completing operation the process may return to operation for performing another tag population estimate through the selected other antenna.

The operations included in processes A and B are for illustration purposes. Antenna switching upon detecting fewer than an expected number of tags may be implemented by similar processes with fewer or additional steps as well as in different order of operations using the principles described herein.

According to some embodiments a method for an RFID reader system coupled to at least a first antenna and a second antenna includes causing the first antenna to radiate a first signal for estimating whether any tags are present in the first antenna s field of view and causing the second antenna to radiate a second signal for estimating whether any tags are present in the second antenna s field of view if fewer than a preset number of tags are estimated in the first antenna s field of view. Otherwise the method includes inventorying tags estimated in the first antenna s field of view.

The preset number may be learned by the reader based on tag responses. If fewer than the preset number of tags are estimated in the second antenna s field of view the reader system may cause a third antenna coupled to the RFID reader system to radiate a third signal for estimating whether any tags are present in the third antenna s field of view. Otherwise the reader system may inventory tags estimated in the second antenna s field of view.

The second signal may be radiated regardless of whether any tags are estimated as present in the first antenna s field of view or responsive to estimating that no tags are present in the first antenna s field of view. The first tags may also be estimated as present in the first antenna s field of view and the second signal radiated without addressing individually the first tags.

The second antenna may be selected before completing causing the first antenna to radiate such that no signal is radiated from the first antenna beyond the first signal. Also selecting the second antenna may be delayed until an operation for a specific tag is completed.

According to another embodiment the tag operation may be completed when a predefined criterion is satisfied. The predefined criterion may include one or more of a decision based on completion of an inventory operation a decision based on an expiration of a time out period or a decision based on a predefined Q parameter value. The Q parameter value may be learned by the RFID reader system based on tag responses or dictated by the first signal and have a value of at least 2.

According to further embodiments the first signal may be for performing a partial query operation to detect the presence of the tags such that if one of a valid preamble and a collision is detected a tag is estimated else no tag is estimated. The second signal may be radiated regardless of whether any tags are estimated as present in the first antenna s field of view. The second signal may also be radiated responsive to estimating that no tags are present in the first antenna s field of view.

According to yet other embodiments first tags fewer than the preset number may be estimated as present in the first antenna s field of view and the second signal may be radiated without addressing individually the first tags.

The second antenna may be selected among a plurality of antennas associated with the RFID reader system based on a first predefined algorithm an order of available antennas or by random selection in which the selection is different depending on whether any tags are sensed through the first antenna. If no tags are estimated a third antenna may be selected according to the first algorithm or a second algorithm.

When tag population check is performed for each antenna instead of statically assigned time for inventorying tags regardless of whether any tags are estimated time spent on each antenna is significantly reduced in the absence of tags in each antenna s field of view.

In diagram the reduction in time spent on each antenna is illustrated by the TPC periods through . In periods through the TPC may determine to tags have replied or fewer than an expected number have replied. Thus the reader system switches to another antenna.

Following the worst case latency scenario discussed in a tag may arrive in antenna s field of view shortly after the reader has switched to antenna . The arriving tag is detected when the reader completes checks through the other antennas per its antenna selection algorithm and returns to antenna as shown by reference numeral . The tag is then inventoried through antenna when the reader switches from tag population check mode to inventory mode on antenna . The worst case latency as illustrated by reference numeral is significantly reduced compared to the scenario shown in .

According to the example scenario shown in diagram during a TPC process through a first antenna too few tags are found . So the reader switches to another antenna reducing time wasted on the first antenna significantly . Following a TPC or query process sufficient tags are found in the field of view of the second antenna.

The tags found in the field of view of the second antenna may then be inventoried. According to some embodiments the time allocated to the second antenna may be adjusted to allow completion of the inventorying of all tags found in the field of view of the second antenna.

In this description numerous details have been set forth in order to provide a thorough understanding. In other instances well known features have not been described in detail in order to not obscure unnecessarily the description.

A person skilled in the art will be able to practice the embodiments in view of this description which is to be taken as a whole. The specific embodiments as disclosed and illustrated herein are not to be considered in a limiting sense. Indeed it should be readily apparent to those skilled in the art that what is described herein may be modified in numerous ways. Such ways can include equivalents to what is described herein.

The following claims define certain combinations and sub combinations of elements features steps and or functions which are regarded as novel and non obvious. Additional claims for other combinations and sub combinations may be presented in this or a related document.

