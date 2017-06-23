---

title: RFID reader Q-parameter aided by RF power measurement
abstract: RFID tag responses are detected by an RFID reader system. The tag response may be detected based on a reference measurement during a tag silent period and another one during the tag response. This helps determine whether a slot is empty or occupied, in a slotted aloha algorithm. The result is reported to the Q-algorithm for a better decision.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08077013&OS=08077013&RS=08077013
owner: Impinj, Inc.
number: 08077013
owner_city: Seattle
owner_country: US
publication_date: 20070112
---
This utility patent application claims the benefit of U.S. Provisional Application Ser. No. 60 758 349 filed on Jan. 12 2006 which is hereby claimed under 35 U.S.C. 119 e . The provisional application is incorporated herein by reference.

This application may be found to be related to the following application which is incorporated herein by reference Application titled RFID READER SYSTEMS AIDED BY POWER MEASUREMENT by inventors Scott A. Cooper and Christopher J. Diorio Ser. No. 11 622 066 filed with the USPTO on Jan. 11 2007 and due to be assigned to the same assignee.

Radio Frequency IDentification RFID systems typically include RFID tags and RFID readers the latter are also known as RFID reader writers or RFID interrogators . RFID systems can be used in many ways for locating and identifying objects to which the tags are attached. RFID systems are particularly useful in product related and service related industries for tracking large numbers of objects being processed inventoried or handled. In such cases an RFID tag is usually attached to an individual item or to its package.

In principle RFID techniques entail using an RFID reader to interrogate one or more RFID tags. The reader transmitting a Radio Frequency RF wave performs the interrogation. A tag that senses the interrogating RF wave responds by transmitting back another RF wave. The tag generates the transmitted back RF wave either originally or by reflecting back a portion of the interrogating RF wave in a process known as backscatter. Backscatter may take place in a number of ways.

The reflected back RF wave may further encode data stored internally in the tag such as a number. The response is demodulated and decoded by the reader which thereby identifies counts or otherwise interacts with the associated item. The decoded data can denote a serial number a price a date a destination other attribute s any combination of attributes and so on.

An RFID tag typically includes an antenna system a power management section a radio section and frequently a logical section a memory or both. In earlier RFID tags the power management section included an energy storage device such as a battery. RFID tags with an energy storage device are known as active tags. Advances in semiconductor technology have miniaturized the electronics so much that an RFID tag can be powered solely by the RF signal it receives. Such RFID tags do not include an energy storage device and are called passive tags.

A typical application for an RFID reader is to read the codes of tags brought in its field of view which is also called inventorying the tags. Since many tags could be brought in front of the reader at the same time there is a process for inventorying that forces the tags to be addressed individually called singulation.

Stingulation often uses a technique called the slotted aloha technique. The slotted aloha technique distributes the RFID tag population in sequential slots which will be described later in more detail. The reader determines a value for a Q parameter and transmits it to the tags. The tags occupy the slots according to random numbers. When a tag occupies a single slot it can be read out individually without interference from the others.

When first encountering a population of RFID tags the reader does not know how many they are. Yet it chooses as a guess a value for the Q parameter that creates slots. There is an optimum number of slots to create for a population of a given size and if the reader makes a poor guess it will not inventory the tags quickly.

Improvements to the slotted aloha technique have been made when the reader further runs an algorithm that can change the value of the Q parameter depending on what is being encountered in the field. Such an algorithm is called a Q algorithm. If a better value of Q is reached then inventorying can be accelerated. Such improvements are described for example in copending U.S. patent application Ser. Nos. 11 210 573 11 210 575 and 11 210 422 all filed on Aug. 24 2005 all due to be assigned to the same assignee and all incorporated herein by reference.

A requirement for a Q algorithm is that it learns how tags are distributed in the slots it has created as it is examining the slots. A problem with this is interference from noise sources in the environment. These may mask tag responses or be mistaken by the reader as a true tag response. In addition to giving false readings from tags they can also mislead the Q algorithm.

This Summary is provided to introduce a selection of concepts in a simplified form that are further described below in the Detailed Description. This Summary is not intended to identify key features or essential features of the claimed subject matter nor is it intended to be used as an aid in determining the scope of the claimed subject matter.

Embodiments are directed to detecting RFID tag responses in an RFID reader. The tag response may be detected based on a reference measurement during a tag silent period and another one during the tag response. This helps determine whether a slot is empty or occupied which is reported to the Q algorithm for a better decision. Results are improved because the reference measurement is made at a time when the tags are known to be silent.

Various embodiments will be described in detail with reference to the drawings where like reference numerals represent like parts and assemblies throughout the several views. Reference to various embodiments does not limit the scope of the invention which is limited only by the scope of the claims attached hereto. Additionally any examples set forth in this specification are not intended to be limiting and merely set forth some of the many possible embodiments for the claimed subject matter.

Throughout the specification and claims the following terms take at least the meanings explicitly associated herein unless the context clearly dictates otherwise. The meanings identified below are not intended to limit the terms but merely provide illustrative examples for the terms. The meanings of a an and the includes plural reference the meanings of in includes in and on. The term connected means a direct electrical connection between the items connected without any intermediate devices. The term coupled means either a direct electrical connection between the items connected or an indirect connection through one or more passive or active intermediary devices. The term circuit means either a single component or a multiplicity of components either active and or passive that are coupled together to provide a desired function. The term signal means at least one current voltage charge temperature data or other measurable quantity. The terms RFID reader and RFID tag are used interchangeably with the terms reader and tag respectively throughout the text and claims.

Reader and tag exchange data via wave and wave . In a session of such an exchange each encodes modulates and transmits data to the other and each receives demodulates and decodes data from the other. The data is modulated onto and decoded from RF waveforms.

Encoding the data in waveforms can be performed in a number of different ways. For example protocols are devised to communicate in terms of symbols also called RFID symbols. A symbol for communicating can be a delimiter a calibration symbol and so on. Further symbols can be implemented for ultimately exchanging binary data such as 0 and 1 if that is desired. In turn when the waveforms are processed internally by reader and tag they can be equivalently considered and treated as numbers having corresponding values and so on.

Tag can be a passive tag or an active tag i.e. having its own power source. Where tag is a passive tag it is powered from wave .

RFID reader and RFID tag talk and listen to each other by taking turns. As seen on axis TIME when reader talks to tag the communication session is designated as R T and when tag talks to reader the communication session is designated as T R . Along the TIME axis a sample R T communication session occurs during a time interval and a following sample T R communication session occurs during a time interval . Of course interval is typically of a different duration than interval here the durations are shown approximately equal only for purposes of illustration.

According to blocks and RFID reader talks during interval and listens during interval . According to blocks and RFID tag listens while reader talks during interval and talks while reader listens during interval .

In terms of actual technical behavior during interval reader talks to tag as follows. According to block reader transmits wave which was first described in . At the same time according to block tag receives wave and processes it to extract data and so on. Meanwhile according to block tag does not backscatter with its antenna and according to block reader has no wave to receive from tag .

During interval tag talks to reader as follows. According to block reader transmits a Continuous Wave CW which can be thought of as a carrier signal that ideally encodes no information. As discussed before this carrier signal serves both to be harvested by tag for its own internal power needs and also as a wave that tag can backscatter. Indeed during interval according to block tag does not receive a signal for processing. Instead according to block tag modulates the CW emitted according to block so as to generate backscatter wave . Concurrently according to block reader receives backscatter wave and processes it.

In the above an RFID reader interrogator may communicate with one or more RFID tags in any number of ways. Some such ways are called protocols. A protocol is a specification that calls for specific manners of signaling between the reader and the tags.

One such protocol is called the Specification for RFID Air Interface EPC TM Radio Frequency Identity Protocols Class 1 Generation 2 UHF RFID Protocol for Communications at 860 Mhz 960 Mhz which is also colloquially known as the Gen2 Spec . The Gen2 Spec has been ratified by EPCglobal which is an organization that maintains a website at at the time this document is initially filed with the USPTO.

It was described above how reader and tag communicate in terms of time. In addition communications between reader and tag may be restricted according to frequency. One such restriction is that the available frequency spectrum may be partitioned into divisions that are called channels. Different partitioning manners may be specified by different regulatory jurisdictions and authorities e.g. FCC in North America CEPT in Europe etc. .

The reader typically transmits with a transmission spectrum that lies within one channel. In some regulatory jurisdictions the authorities permit aggregating multiple channels into one or more larger channels but for all practical purposes an aggregate channel can again be considered a single albeit larger individual channel.

Tag can respond with a backscatter that is modulated directly onto the frequency of the reader s emitted CW also called baseband backscatter. Alternatively Tag can respond with a backscatter that is modulated onto a frequency developed by Tag that is different from the reader s emitted CW and this modulated tag frequency is then impressed upon the reader s emitted CW. This second type of backscatter is called subcarrier backscatter. The subcarrier frequency can be within the reader s channel can straddle the boundaries with the adjacent channel or can be wholly outside the reader s channel.

A number of jurisdictions require a reader to hop to a new channel on a regular basis. When a reader hops to a new channel it may encounter RF energy there that could interfere with communications.

Embodiments of the present disclosure can be useful in different RFID environments for example in the deployment of RFID readers in sparse or dense reader environments in environments with networked and disconnected readers such as where a hand held reader may enter the field of networked readers in environments with mobile readers or in environments with other interference sources. It will be understood that the present embodiments are not limited to operation in the above environments but may provide improved operation in such environments.

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

The invention additionally includes programs and methods of operation of the programs. A program is generally defined as a group of steps or operations leading to a desired result due to the nature of the elements in the steps and their sequence. A program is usually advantageously implemented as a sequence of steps or operations for a processor such as the structures described above.

Performing the steps instructions or operations of a program requires manipulation of physical quantities. Usually though not necessarily these quantities may be transferred combined compared and otherwise manipulated or processed according to the steps or instructions and they may also be stored in a computer readable medium. These quantities include for example electrical magnetic and electromagnetic charges or particles states of matter and in the more general case can include the states of any physical devices or elements. It is convenient at times principally for reasons of common usage to refer to information represented by the states of these quantities as bits data bits samples values symbols characters terms numbers or the like. It should be borne in mind however that all of these and similar terms are associated with the appropriate physical quantities and that these terms are merely convenient labels applied to these physical quantities individually or in groups.

The invention furthermore includes storage media. Such media individually or in combination with others have stored thereon instructions of a program made according to the invention. A storage medium according to the invention is a computer readable medium such as a memory and is read by a processor of the type mentioned above. If a memory it can be implemented in a number of ways such as Read Only Memory ROM Random Access Memory RAM etc. some of which are volatile and some non volatile.

Even though it is said that the program may be stored in a computer readable medium it should be clear to a person skilled in the art that it need not be a single memory or even a single machine. Various portions modules or features of it may reside in separate memories or even separate machines. The separate machines may be connected directly or through a network such as a local access network LAN or a global network such as the Internet.

Often for the sake of convenience only it is desirable to implement and describe a program as software. The software can be unitary or thought in terms of various interconnected distinct software modules.

This detailed description is presented largely in terms of flowcharts algorithms and symbolic representations of operations on data bits on and or within at least one medium that allows computational operations such as a computer with memory. Indeed such descriptions and representations are the type of convenient labels used by those skilled in programming and or the data processing arts to effectively convey the substance of their work to others skilled in the art. A person skilled in the art of programming may use these descriptions to readily generate specific instructions for implementing a program according to the present invention.

Embodiments of an RFID reader system can be implemented as a combination of hardware and software. It is advantageous to consider such a system as subdivided into components or modules. A person skilled in the art will recognize that some of these components or modules can be implemented as hardware some as software some as firmware and some as a combination. An example of such a subdivision is now described.

RFID reader system includes one or more antennas and an RF Front End for interfacing with antenna s . These can be made as described above. In addition Front End typically includes analog components.

System also includes a Signal Processing module . In this embodiment module exchanges waveforms with Front End such as I and Q waveform pairs. In some embodiments signal processing module is implemented by itself in an FPGA.

System also includes a Physical Driver module which is also known as Data Link. In this embodiment module exchanges bits with module . Data Link can be the stage associated with framing of data. In one embodiment module is implemented by a Digital Signal Processor.

System additionally includes a Media Access Control module which is also known as MAC layer. In this embodiment module exchanges packets of bits with module . MAC layer can be the stage for making decisions for sharing the medium of wireless communication which in this case is the air interface. Sharing can be between reader system and tags or between system with another reader or between tags or a combination. In one embodiment module is implemented by a Digital Signal Processor.

In a number of embodiments it is preferred to host the Q algorithm in MAC layer . Indeed in the shown embodiment there is a module that implements the Q algorithm. It should be remembered however that this is only a design choice and that the Q algorithm may be hosted by other modules or a combination of modules.

System moreover includes an Application Programming Interface module which is also known as API Modem API and MAPI. In some embodiments module is itself an interface for a user.

System further includes a host processor . Processor exchanges signals with MAC layer via module . In some embodiments host processor is not considered as a separate module but one that includes some of the above mentioned modules of system . A user interface is coupled to processor and it can be manual automatic or both.

Host processor can include applications for system . In some embodiments elements of module may be distributed between processor and MAC layer .

It will be observed that the modules of system form something of a chain. Adjacent modules in the chain can be coupled by the appropriate instrumentalities for exchanging signals. These instrumentalities include conductors buses interfaces and so on. These instrumentalities can be local e.g. to connect modules that are physically close to each other or over a network for remote communication.

The chain is used in opposite directions for receiving and transmitting. In a receiving mode wireless waves are received by antenna s as signals which are in turn processed successively by the various modules in the chain. Processing can terminate in any one of the modules. In a transmitting mode initiation can be in any one of these modules. That which is to be transmitted becomes ultimately signals for antenna s to transmit as wireless waves.

The architecture of system is presented for purposes of explanation and not of limitation. Its particular subdivision into modules need not be followed for creating embodiments according to the invention. Furthermore the features of the invention can be performed either within a single one of the modules or by a combination of them.

An economy is achieved in the present document in that a single set of flowcharts is used to describe methods in and of themselves along with operations of hardware and or software. This is regardless of how each element is implemented.

The invention also includes methods. Some are methods of operation of an RFID reader or RFID reader system. Others are methods for controlling an RFID reader or RFID reader system.

These methods can be implemented in any number of ways including the structures described in this document. One such way is by machine operations of devices of the type described in this document.

Another optional way is for one or more of the individual operations of the methods to be performed in conjunction with one or more human operators performing some. These human operators need not be collocated with each other but each can be only with a machine that performs a portion of the program.

Flowchart can be performed during inventorying. According to an operation a decision is made whether a new value should be used for the Q parameter or the same one should be retained. The first time operation is performed the first value for the Q parameter will be a new one anyway and execution proceeds to an operation .

According to operation a new value is decided for the Q parameter. Another time that operation is executed this new value will be a next value. The new value is decided as described in the copending and incorporated U.S. patent application Ser. Nos. 11 210 573 11 210 575 and 11 210 422.

According to an operation a first reader command is caused to be transmitted to the RFID tags for inventorying them. The first reader command may be encoded in a modulated carrier wave which is transmitted as caused by the appropriate component.

The first reader command communicates the value for the Q parameter decided in operation . In some embodiments the first reader command is one of a Query command and in others a QueryAdj command.

As such the first reader command causes each of the RFID tags to occupy one of a number of first slots that are defined by the first value. An example is now described in more detail.

As mentioned previously the reader does not know the size of the population and guesses in an inventorying round as to how many tags there are. In this case it guesses Q 5. Each of tags chooses a Q bit random number and stores it in their slot counter as shown.

As shown in diagram two of the tags have generated the same binary random number 10010 which equals 18 so they occupy the 18th slot. In addition tag occupies slot which tag occupies slot .

Returning now to the slots will now be examined individually. In some embodiments the above command permits examining the contents of slot .

According to an operation a QueryRep command is transmitted to the tags. In fact one such QueryRep command is transmitted for examining each slot in an inventory round. Two examples of inventory rounds are now described.

Action table has rows with commands by the reader the prevailing Q value and what the tags do. Only the Query command communicates a Q while a series of QueryRep commands examines all the slots that have been defined for a complete inventorying round. Here two such complete inventorying rounds are shown one with Q and one with Q.

Action table has rows with commands by the reader the prevailing Q value and what the tags do. The Q value is changed a number of times by the QueryAdj command before a round is completed.

Each QueryRep command is for examining one more of the slot. With each QueryRep command the tags decrement the numbers in their slot counters by one. The tags reaching the number zero in their slot counter respond to the reader. As a result of the decrementing and responding process each time three outcomes are possible 

Diagram shows an example of the first case. As a result of continuing decrementing arrow none of the tags reach zero. Accordingly content is an empty content and the reader knows that no tag occupied the slot at least in theory.

Diagram shows an example of the second case. As a result of continuing decrementing arrow one of the tags reaches zero value in its slot counter and thus sends a reply to the reader. Accordingly content is a single reply content and the reader knows that a single tag occupied the slot at least in theory.

Diagram shows an example of the third case. As a result of continuing decrementing arrow two of the tags reach zero value in their slot counters and send replies which collide. Accordingly content is a content with a collision. The collided responses can be from more than two tags. Accordingly the reader knows that two or more tags occupied the slot at least in theory.

Attention is now drawn to detection within a single slot. The QueryRep command causes a tag occupying the slot to backscatter a response within a tag response time window. In addition the tag must be silent at a tag silent period of the first slot that is outside the tag response time window. The tag response time window and the tag silent periods can be known from the Air Interface communication protocol in use and which is known in advance to the reader system. An example is now described.

In the Gen2 Spec it is specified that after time TR there shall be a minimum tag silent period TMIN during which no tag may respond. For inventorying commands responses may start either at TMIN or at a little later time point TMAX.

Three possible tag responses are shown namely and . They each start between TMIN and TMAX and have different durations. For the purposes of this example tag response starts at the latest possible time TMAX and is of the longest possible duration. As such it ends at a delay time TDEL.

The delay time TDEL depends on which commands are used. For example if another reader command is transmitted between the QueryRep commands it could ask for more or different information of the type that takes longer. As such the delay time TDEL can be increased.

One or more of these tag responses can be perceived and detected by the reader as a signal. The challenge is for the reader to discern which signals are from the tags and which from the environment.

It will be appreciated that the tag response time window is between TMIN and TDEL. In addition two tag silent times are defined. The first is between TR and TMIN before the tag response time window. The second is after TDEL perhaps limited by other design factors such as desire to inventory quickly and so on.

In diagram three possible measurements are illustrated. The first measurement P is made during the silent period between time points TR and TMIN following the transmission of reader command . As per the above measurement P is done with the confidence that no tag responses are included.

The second power measurement P may be performed at any time during the tags responses. The preferred time is between TMAX and the possible end of tag response so as to allow for all possibilities.

Finally a third power measurement P may be made in the silent period after TE when all tag responses are expected to be completed. Again measurement P is done with the confidence that no tag responses are included.

Returning now to according to an operation an initial reference signal is received during one of the tag silent periods. According to some embodiments the reference signal maybe a background noise detected by the reader while the tags are silent.

According to an operation an aspect of the initial reference signal is measured. This can be measurement P or P shown in . Any aspect can be measured such as a power a voltage a current and so on. The aspect is measured from a single measurement or many or a continuing one integrating over some time.

While operations and can be performed only once it is advantageous that they be performed more frequently. For example they can be performed ever time a command is transmitted as per operation .

An advantage therefore is that the measured reference signal reflects the ambient noise free from any backscatter of the RFID tags of interest. In some embodiments the ambient noise can be too high and other measures can be implemented. For example if the measured aspect exceeds a threshold a data rate of a transmit circuit of the RFID system can be adjusted down. Or the RFID tags can be commanded to not respond on the baseband frequency of the first signal but on its subcarrier. Inverse measures can be implemented if the ambient noise is lower than expected.

According to a next operation a detection threshold is set or updated from the measured aspect. The detection threshold can be set in any number of ways such as by adjusting a filter in a receive circuit of the RFID reader system. As such the detection threshold can be determined as a quantity expressed in one of dB Watts Volts Amps a number and so on.

An advantage therefore is that the detection threshold is set at a time that it is known that the tags are not backscattering because they have been forced to be silent from the reader. This will enable more reliable measurements later on.

Operations may happen only once and thus the other times execution can proceed from operation to operation . Or they can be repeated for more robustness. For example an updated reference signal can be received during another one of the tag silent periods an aspect of it can be measured and the detection threshold can be updated. This is advantageous in the event that the ambient noise is changing.

According to an operation a second signal is detected by the reader within the known tag response time window when the tag response is expected. The second signal can be received before or after the initial reference signal. And such signals can be received at these windows for multiple examined slots.

A power of the second signal is measured e.g. by one or many measurements such as the above. Instead of the power another aspect of the second signal can be equivalently measured. And the measured aspect can be expressed or converted to the same units as the detection threshold for the impending comparison with the detection threshold to make sense. Of all possible aspects power is mentioned more predominantly in this document because it is the preferred signal aspect to measure.

According to an operation it is determined from the second signals whether the occupancy of the examined first slots is none or at least one of the RFID tags. This can be performed in any number of ways. Plus it can be performed the same way or different ways for each slot.

For at least one of the slots operation is performed by comparing the detection threshold to a power of a second signal corresponding to the certain slot. In that case the occupancy of that slot is determined to be none if the second signal power is less than the detection threshold and at least one if the second signal power is greater than the detection threshold.

According to an optional operation the determined occupancy of the slot is reported to the host of the Q algorithm. Then execution reverts to operation . This time however the decision of operation is performed according to the determined occupancy of the slots.

In some instances there will be no new value for the Q parameter and execution will proceed to operation for examining one more slot.

In other instances execution will proceed to operation and a new value for the Q parameter will be decided upon in view of the determined occupancy of the slots. Then execution proceeds again to operation and a new reader command is transmitted to the RFID tags which communicates the new value for the Q parameter. The new value can be communicated explicitly or indirectly as an increment or a decrement.

Methods of the invention can also be for only a component of the reader system which is considered separately and intended to work with other such components. Such separate components were first discussed with reference to .

For such a component an operation can be that a first inventory instruction is received which includes a first value for a Q parameter. Then the component can cause to be transmitted to the RFID tags a first reader command that communicates the first value for the Q parameter. As per the above this causes the tags to occupy slots such as those of .

Then the component an cause to be transmitted to the RFID tags sequentially a number of QueryRep commands for examining respective slots for their occupancy as per the above.

Again a reference signal can be received during a tag silent period and an aspect of it measured. Then a detection threshold can be set or updated from the measured aspect. Then a second signal can be detected and the slot occupancy can be determined all again as per the above. Then a report can be transmitted informing of the determined occupancy. Then a second inventory instruction can be received that includes a new value for the Q parameter which has been determined responsive to the report.

Then the component can cause to be transmitted to the RFID tags another reader command which communicates the next value for the Q parameter. As per the above this causes the tags to occupy a new number of slots and so on.

In the above what was determined was only whether the occupancy is zero or higher than zero. This can be enough information for running advantageously the Q algorithm.

In some embodiments additional measures are taken to determine the occupancy with further certainty. For example the second signal can be demodulated and tested according to a demodulation score. If the slot occupancy is higher than zero and demodulation produced a good score then the occupancy was exactly 1 and so on.

In this description numerous details have been set forth in order to provide a thorough understanding. In other instances well known features have not been described in detail in order to not obscure unnecessarily the description.

A person skilled in the art will be able to practice the embodiments in view of this description which is to be taken as a whole. The specific embodiments as disclosed and illustrated herein are not to be considered in a limiting sense. Indeed it should be readily apparent to those skilled in the art that what is described herein may be modified in numerous ways. Such ways can include equivalents to what is described herein.

The following claims define certain combinations and sub combinations of elements features steps and or functions which are regarded as novel and non obvious. Additional claims for other combinations and sub combinations may be presented in this or a related document.

