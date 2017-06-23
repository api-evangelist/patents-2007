---

title: Processor and interface
abstract: A data processing apparatus comprises a processor constructed to operate under control of a sequence of program instructions selected from a predetermined instruction set; master circuitry to request access to storage locations of the processor; an interface circuit to provide an interface for an external apparatus to signal a request for access to the storage locations and an interface for the master circuitry to signal a request for access to the storage locations; and control to provide access between the storage locations and the interface circuit in response to the request only at predetermined points in execution of the stored program, the control being operable to fix periods of time for providing such access relative to the sequence of program instructions such that execution timing of the stored instructions is independent of whether a request is supplied to the interface.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08683163&OS=08683163&RS=08683163
owner: Cambridge Consultants Ltd.
number: 08683163
owner_city: 
owner_country: GB
publication_date: 20071108
---
This is a continuation under 35 U.S.C 111 a of PCT GB2006 01756 filed May 12 2006 and published in English as WO 2006 120470 A2 on Nov. 16 2006 which claimed priority to United Kingdom application no. 0524772.1 filed on Dec. 5 2005 and United Kingdom application no. 0509738.1 filed on May 12 2005 which applications and publications are incorporated in their entirety herein by reference and made a part hereof.

The present invention relates to a processor to an interface in particular a serial interface associated with the processor and to methods of operation of the processor and the interface. The invention also relates to an instruction set and to methods of programming operation of the processors and the interface. The invention also relates to a data processing apparatus. The invention also relates to a family of processors.

Broadly according to an aspect of the invention there is provided a family of processors which share a number of common characteristics and in which substantially the only differences between the processors are as a result of the different sizes thereof.

According to another aspect of the invention there is provided a processor forming part of a family of similar processors each having a number of common characteristics and in which the only differences between the processors and the other processors in the family are as a result of the different sizes of the processors.

Preferably the processors are similar in that that they share one or more of the characteristics listed in Table 1 below. More preferably each of the processors is unique in accordance with one or more of the parameters listed in Table 1 below.

Broadly according to another aspect of the invention there is provided a data processing apparatus including one or more processors each processor having associated memory registers and debug instructions and an interface capable of communicating with the or each processor wherein the interface provides non invasive access to the or each processor memory registers or debug instructions.

Preferably the data processing apparatus is implemented in a single semiconductor device or chip which contains one interface and one or more processors. The processors are preferably slaves to the interface. More preferably the processors form part of the family of processors as hereinbefore described.

The term semiconductor device as used herein is preferably intended to connote an ASIC or FPGA implemented in silicon or germanium or gallium arsenide or some other semiconductor material. The semiconductor device is also referred to as a chip.

The term high code density as used herein refers to the size of the compiled program. Thus for the same original high level program code a smaller sized compiled program will have a higher code density than a larger sized complied program.

Preferably the processors are optimised for embedded use in ASICs and FPGAs. More preferably the processors may be of different sizes.

Preferably the interface which is also referred to as a SIF interface can support an off chip master and an on chip master. Preferably the off chip master uses an external xSIF interface. Preferably the on chip master uses an internal iSIF interface. In this way the interface may be controlled and hence provide access to the processor s memory registers and debug instructions provided either via an external source using an off chip master or via an on chip device such as a further processor. Further details in this regard can be found in and .

Preferably the masters can read and write the registers and memory of one or more on chip processors. More preferably the masters can also issue debug instructions to one or more on chip processors. Preferably the external interface is a serial interface. Preferably the internal interface is a parallel interface.

Preferably the interface comprises arbitration hardware for ensuring that communication bandwidth is shared between the internal and external masters.

Furthermore each of the processors in the family also share the following common features the processors may all be Load Store RISC processors the processors may all support unaligned byte addressing the processors may all have a Von Neumann architecture having a single memory and or memory bus for code and data the processors may all be implemented in a synthesisable Verilog RTL Register Transfer Level language the processors may all be optimised for code density so that a given program written in for example C will compile to be as small as possible giving lower cost and power consumption while running at a faster speed the processors may all have a mixture of 16 and 32 bit instructions. Preferably these instructions can be freely mixed and are evaluated on an instruction by instruction basis. More preferably a user does not have to specify whether to use a 16 or 32 bit instruction at the time of coding the processors may all use the same style of instruction mnemonics the processors may all have the same 4 processor modes User Supervisor Interrupt Non Maskable Interrupt NMI the processors may all use a SIF interface for software debugging and data acquisition. The SIF interface supports an internal parallel iSIF interface and an external serial xSIF interface the processors may all use the same developer environment for software development In preferred embodiments the developer environment comprises the xIDE Toolkits the processors may all have GCC GNU Compiler Collection compilers the compilers and instruction sets for use with the processors may all be developed together for compatibility and optimal code density the processors may have good hardware support for embedded operating systems.

Preferably all code for these processors will be in C or another high level language. Preferably the code will normally use 8 16 and 32 bit fixed point data. The code will not normally use floating point data. Some of this code will be custom developed for the application but much will be off the shelf standard product software. Advantageously the family of processors XAP3 XAP4 and XAP5 all have good features for porting 3 party software.

As can be seen from Table 1 the processors XAP3 XAP4 and XAP5 all have many aspects in common. This family approach makes it possible for programmers easily to migrate code from one processor to another. It also makes it easy for programmers acquainted with one processor to learn how to use another processor in the family. These advantages are achieved because of the consistent philosophy applied across all the processors in the family.

The programmer will typically choose a particular processor based upon required software size speed requirements cost size of processor and memory requirements and power consumption requirements.

The XAP4 processor is the smallest in size. The XAP3 processor is the largest and the XAP5 processor is medium sized.

A key feature of all the processors is good code density for compiled C code. In all cases this is achieved by instruction sets that are a mixture of 16 and 32 bit some instructions are only available as 16 bit some instructions are only available as 32 bit and some instructions are available in 16 bit and in 32 bit form.

Preferably the instruction mnemonics do not indicate whether an instruction is 16 or 32 bit. Thus the programmer and compiler do not need to be aware of whether instructions are 16 or 32 bit Only the assembler has to choose between 16 or 32 bit encodings for a particular instruction. This is much more convenient for the programmer as he always has access to all of the processor and all of the instructions some processors have modes which only allow the programmer to access a subset of the processor s hardware and instructions . The 16 and 32 bit instructions can be freely mixed and are evaluated by the hardware at run time. This may provide good code density while retaining a friendly programming interface.

It should also be noted that the above two aspects of the invention XAP3 and XAP4 are closely related since they cover a family of closely related processors and an associated interface. Therefore any some and or all features in one aspect may be applied to any some and or all features in the other aspect in any appropriate combination.

In SIF communications in the preferred embodiment a SIF Computer transfers data to and from one or more SIF Slaves via one or more SIF Pods. The SIF Slave is normally an integrated circuit.

Aspects of the SIF and associated processor are described in WO 96 09583 WO 03 048978 GB 2382889 United Kingdom Patent Application Nos. 9419246.5 and 0129144.2 each in the name of Cambridge Consultants Limited and each of which is hereby incorporated by reference.

SIF technology includes elements of the SIF inside the integrated circuit and external SIF elements found in the SIF Computer and SIF Pods.

The XAP3 and SIF Slave module are normally implemented together in the same integrated circuit. The integrated circuit may also contain other circuit elements. The integrated circuit may contain more than one processor but normally contains just one SIF Slave module.

The XAP3 is a 32 bit processor that may be implemented in an integrated circuit. The integrated circuit may be a standard component or an Application Specific Integrated Circuit ASIC or a Field Programmable Gate Array FPGA .

In embodiments of the XAP3 processor the same width is used for data registers and address and instruction in accordance with good processor design and preferably the same memory can be used to store data and store programs and store pointers.

The preferred embodiment of a SIF system comprises three main components a SIF Slave module which may also be referred to herein simply as the SIF module or SIF in various contexts usually located in an integrated circuit a SIF Pod located external to the integrated circuit and preferably located external to the circuit board upon which the integrated circuit is located and a SIF computer also referred to as a computer or control computer which includes a SIF driver preferably implemented in software. The SIF Pod and the SIF computer together may be referred to as a SIF master. Alternatively the SIF Pod alone is sometimes referred to as the SIF master. The SIF computer may be a laptop or desktop computer and may be for instance a PC or Mac.

An overview of the architecture of preferred embodiments of the SIF processor interface system can be seen in .

The integrated circuit is referred to at various places herein as the SIF Slave ASIC even though it may be an FPGA or standard component .

In the preferred embodiment the SIF Slave ASIC contains a SIF Slave module one or more processors application specific digital circuitry and application specific analogue circuitry. In the preferred embodiment the processor is a XAP3 processor. In other embodiments the processor may be for instance a XAP1 or XAP2 processor.

A plurality of SIF Slave ASICs or FPGAs may be connected to a single SIF Pod and a plurality of SIF Pods may be connected to a single SIF Computer as can be seen for instance in .

The SIF Slave module in the preferred embodiment comprises a shift register with three interface signals SIF CLK SIF MOSI SIF MISO and handshake circuitry with one interface signal SIF LOADB . The shift register has two inputs SIF CLK to which a clock signal is applied to effect the movement of binary data between subsequent stages of the shift register and SIF MOSI Master Out Slave In for receiving binary information in a serial manner from an external source thereby allowing the information to be entered into the shift register and debug system . The shift register has a single output SIF MISO Master In Slave Cut for allowing binary data to be output in a serial manner from the shift register to an external source. In preferred examples the shift register is a 64 bit shift register XAP2 or an 88 bit shift register XAP3 . Typically the SIF CLK SIF MOSI SIF MISO and SIF LOADB signals connect the SIF Slave module to the SIF Pod.

The SIF Pod may comprise a hardware based interface between the SIF Slave ASIC and a personal computer. The SIF Pod may be connected to the SIF Slave ASIC by a 16 wire interface and may be connected to the PC via a standard communications interface such as Ethernet RS232 or USB Universal Serial Bus .

The SIF Driver in the SIF Computer may comprise a computer program that translates information between the standard communications interface such as Ethernet RS232 or USB and the xSIF API Application Programmer s Interface . The enables application programs on the PC to simply control and transfer information with the SIF Slave ASICs. Further computer programs may also be executed on the PC which programs may utilise the xSIF API to allow data to be written to and read from the SIF Slave devices. This data may then be analysed to determine the operation of the processor such as for allowing debugging of programs being executed by the processor or processors in the SIF Slave ASIC. Alternatively or additionally data read from the SIF Slave ASIC may be data relating to the operation of a sensor or other device and the SIF Slave ASIC may then operate as a data logging device.

The SIF interface system can be operated on the SIF Slave ASIC concurrently with other software being executed by the ASIC processor such as an operating system and user mode programs. Concurrent operation may be achieved by time slicing which provides time windows during which the ASIC processor performs NOP No Operation leaving the SIF Slave module free to execute debug control of the processor or to access the processor s memory and registers.

Typically each processor comprises a Core an MMU Memory Management Unit an IVC Interrupt Vector Controller and a SIF Slave Module. The Core communicates with memory external to the processor via the Memory Management Unit. In a preferred example the Memory Management Unit can communicate with external memory including Flash memory typically used for the storage of programs RAM Random Access Memory typically used for the temporary storage of data variables to be manipulated by programs and one or more registers.

The memory management unit typically has address and read write lines and data lines. These signals are typically unidirectional when on chip. The data lines are typically bi directional when off chip.

The SIF Slave Module in the preferred embodiment is connected to the Memory Management Unit such that the SIF Slave module is able to control the memory control and address signals thereby enabling it to read and write data from to the processor s memory.

In the preferred embodiment a number of further lines are provided to enable interaction of the processor Core with the SIF Slave module.

In the preferred embodiment a number of lines are provided between the SIF Slave module and the SIF Pod including the SIF CLK SIF MOSI SIF MISO and SIF LOADB lines referred to above. A further input to the SIF Slave ASIC is the chip select line SIF CS. The 16 wire interface from the SIF Pod contains 4 lines that may be used as separate SIF CS lines to up to 4 SIF Slave ASICs.

In one aspect there is provided a processor interface apparatus comprising at least one processor an interface connected to the processor and comprising means for writing data to and or reading data from the processor control means for controlling operation of the interface the control means comprising master and slave modules and wherein the master controlling module is located on the same chip as the or each processor.

The provision of a master on the same chip as the or each processor i.e. an on chip master provides increased flexibility. In particular it enables the interface to be used after the design of the chip has been finalised i.e. in the final application and not only during the design and debugging of the chip.

Preferably the apparatus further comprises a master controlling module which is not located on the same chip as the or each processor i.e. an off chip master. The off chip master may be in the form of or implemented in a separate piece of hardware for example a PC.

In this context the term chip and hence the terms on chip and off chip preferably refers to any single semiconductor device such as an ASIC or FPGA including various processors and or memory manufactured from silicon germanium gallium arsenide or any other semiconductor material.

The interface is also referred to herein as a SIF interface which comprises at least one SIF master and at least one SIF slave.

Preferably the SIF master controls the SIF slave. More preferably the SIF slave is connected to the or each of the on chip processors.

Preferably read and or write access to the processors via the SIF interface is non invasive. Thus the processor s functionality and timing remain unchanged.

Preferably the on chip processors can be of different types. Preferably the processors are XAP processors.

The SIF interface provides a mechanism for masters to access the registers memory and debug instructions of one or more on chip processors. In the case where the master is an off chip device the SIF interface is accessed via an external xSIF interface. In the case where the master is on chip the SIF interface is accessed via an internal iSIF interface. Preferably the external xSIF interface comprises a serial interface. Preferably the internal iSIF interface comprises a parallel interface.

In xSIF communications there is preferably one SIF slave per chip. In a preferred embodiment a SIF Computer xSIF master transfers data to and from one or more on chip processors via one or more SIF Pods and via one or more SIF slaves. Communications between the SIF pod and the SIF slave use the xSIF interface.

In iSIF communications in a preferred embodiment an iSIF master transfers data to and from one or more processors via the SIF slave using the on chip iSIF parallel interface. The iSIF master SIF slave and processors are normally on the same chip.

The XAP4 and SIF Slave module are normally implemented together in the same integrated circuit. The integrated circuit may also contain other circuit elements. The integrated circuit may contain more than one processor but normally contains just one SIF Slave module.

The XAP4 is a 16 bit processor that may be implemented in an integrated circuit. The integrated circuit may be a standard component or an Application Specific Integrated Circuit ASIC or a Field Programmable Gate Array FPGA .

In embodiments of the XAP4 processor the same width is used for data registers and address and instruction in accordance with good processor design and preferably the same memory can be used to store data and store programs and store pointers.

A preferred embodiment of a SIF system as shown in and comprises three main components one or more ASICs a SIF Pod and a SIF computer. Each ASIC comprises a SIF slave module one or more processors and optionally an iSIF master. The SIF pod and SIF computer are located external to the ASIC. The SIF computer includes a SIF driver preferably implemented in software. The SIF Pod and the SIF computer together may be referred to as an xSIF master. Alternatively the SIF Pod alone is sometimes referred to as the xSIF master. The SIF computer may be a laptop or desktop computer and may be for instance a PC or Mac. All three components are required for xSIF communication. The SIF Pod and SIF Computer are not required for iSIF communication.

In the preferred embodiment the SIF Slave ASIC contains a SIF Slave module one or more processors application specific digital circuitry and application specific analogue circuitry. In the preferred embodiment the processor is a XAP4 processor. In other embodiments the processor may be for instance a XAP1 XAP2 XAP3 or XAP5 processor.

The SIF Slave module in the preferred embodiment comprises the external xSIF interface the internal iSIF interface and control logic.

The xSIF interface comprises a shift register with three interface signals SIF CLK SIF MOSI SIF MISO and handshake circuitry with one interface signal SIF LOADB . The shift register has two inputs SIF CLK to which a clock signal is applied to effect the movement of binary data between subsequent stages of the shift register and SIF MOSI Master Out Slave In for receiving binary information in a serial manner from an external source thereby allowing the information to be entered into the shift register and debug system . The shift register has a single output SIF MISO Master In Slave Out for allowing binary data to be output in a serial manner from the shift register to an external source. In preferred examples the shift register is a 64 bit shift register XAP2 an 88 bit shift register XAP3 a 52 bit shift register XAP4 or a 84 bit shift register XAP5 . Typically the SIF CLK SIF MOSI SIF MISO and SIF LOADB signals connect the SIF Slave module to the SIF Pod.

The iSIF interface comprises iSIF fields and iSIF control signals. The input fields to iSIF are address control and data write. The output fields from iSIF are data read and status. The input control signals to iSIF are isif load and isif cancel. The output control signal from iSIF is isif done. There are multiplexers for the three iSIF input fields.

The SIF Pod may comprise a hardware based interface between the SIF Slave ASIC and a personal computer. The SIF Pod may be connected to the SIF Slave ASIC by a 16 wire interface and may be connected to the PC via a standard communications interface such as Ethernet RS232 LPT or USB Universal Serial Bus . The 16 wire interface includes the xSIF interface.

The SIF Driver in the SIF Computer which is an xSIF master may comprise a computer program that translates information between the standard communications interface such as Ethernet RS232 LPT or USB and the xSIF API Application Programmer s Interface . This enables application programs on the PC to simply control and transfer information with the SIF Slave ASICs. Further computer programs may also be executed on the PC which programs may utilise the xSIF API to allow data to be written to and read from the SIF Slave devices. This data may then be analysed to determine the operation of the processor such as for allowing debugging of programs being executed by the processor or processors in the SIF Slave ASIC. Alternatively or additionally data read from the SIF Slave ASIC may be data relating to the operation of a sensor or other device and the SIF Slave ASIC may then operate as a data logging device.

The SIF interface can be operated on the SIF Slave ASIC concurrently with other software being executed by the processors such as operating systems and user mode programs. Concurrent operation may be achieved by time slicing which provides time windows during which the ASIC processor performs NOP No Operation leaving the SIF Slave module free to execute debug control of the processor or to access the processor s memory and registers. This mechanism is used both for iSIF and xSIF accesses.

Preferably xSIF and iSIF use substantially the same instruction set Thus the inclusion of iSIF functionality adds very little hardware to the existing xSIF system.

Typically each processor comprises a Core an MMU Memory Management Unit an IVC Interrupt Vector Controller and a SIF Slave Module see and . The Core communicates with memory external to the processor via the Memory Management Unit. In a preferred example the Memory Management Unit can communicate with external memory including Flash memory RAM and one or more registers.

The memory management unit typically has address and read write lines and data lines. These signals are typically uni directional when on chip. The data lines are typically bi directional when off chip.

The SIF Slave Module in the preferred embodiment is connected via each processor to each respective processor s Memory Management Unit such that the SIF Slave module is able to control the memory control and address signals thereby enabling it to read and write data from to the processor s memory. This is used identically for xSIF and iSIF accesses.

In the preferred embodiment a number of further control lines are provided to enable interaction of the processor Core with the SIF Slave module.

In the preferred embodiment for an xSIF interface a number of lines are provided between the SIF Slave module and the SIF Pod including the SIF CLK SIF MOSI SIF MISO and SIF LOADB lines referred to above. A further input to the SIF Slave ASIC is the chip select line SIF CS. The 16 wire interface from the SIF Pod contains 4 lines that may be used as separate SIF CS lines to up to 4 SIF Slave ASICs.

Preferably the apparatus further comprises at least one control line and wherein operation of the interface controller is dependent upon a signal applied to the control line.

Preferably the apparatus processes instructions passed via the internal iSIF and external interfaces xSIF in alternate fashion.

Preferably the apparatus further comprises means for arbitrating the processing of instructions passed via the internal iSIF and external xSIF interfaces.

Preferably in particular for cancel purposes the instructions passed via the external xSIF interface take precedence over instructions passed via the internal iSIF interface.

According to an aspect of the invention there is provided a data processing apparatus including a processor and an interface capable of communicating with the processor each processor having associated memory registers and debug instructions and wherein the interface provides access to the memory registers and debug instructions of the or each processor.

Preferably the SIF interface comprises at least one SIF master module and at least one SIF slave module.

Preferably the SIF master is provided on chip. More preferably the SIF master communicates via an internal iSIF interface.

Preferably the SIF master further comprises an off chip device. More preferably the off chip device communicates via an external xSIF interface.

Preferably access via the SIF interface to the processors is non invasive. Thus the processor s functionality and timing remain unchanged by a SIF access.

Preferably the data processing apparatus is in the form of a single semiconductor device or chip containing one interface and one or more processors.

Preferably the term semiconductor device is intended to connote an ASIC or FPGA implemented in silicon or germanium or gallium arsenide or some other semiconductor material. The semiconductor device is also referred to as a chip.

Preferably communications between the master and slave s may be from within the semiconductor device internal or from outside the semiconductor device external .

Preferably the internal interface master is implemented in hardware in the form of another processor or dedicated state machine.

Preferably the internal master can read and write registers and memory of one or more processors. This can be used to download software after system reset to capture and store processor state before turning processor power off to restore processor state after turning processor power back on to read memory mapped IO registers in real time in a non invasive manner. The IO register could be an ADC analogue to digital converter .

Preferably the internal master can also issue debug instructions to one or more processors. This can be used to start stop single step set breakpoint run to breakpoint and reset one or more processors.

The provision of an internal master enables all of the abovementioned functionality to be used in the final application and not only during product debug.

Preferably the slave is adapted to support both an internal and external interface. The internal interface is to an internal master. The external interface is to an external master. More preferably the internal interface is parallel and the external interface is serial.

It is also possible for internal and external masters to simultaneously read and write registers and memory of one or more processors.

Furthermore it is possible for internal and external masters to issue debug instructions to one or more processors.

According to another aspect of the present invention there is provided a network which comprises a computer one or more pods one or more chips each containing one or more processors and communications protocols wherein the communications protocols allow the computer to interact with any of the processors.

According to another aspect of the present invention there is provided a network according to claim wherein the communications between computer and processors may be non invasive to the processor s functional behaviour so does not affect that processor s functionality or timing.

References made herein to UK patent numbers GB2382889 and GB2294137 which relate to a non invasive debug It is now proposed to perform a non invasive debug over a network.

Many new electronic devices are for communications networks they might be wireless WiFi Bluetooth Zigbee GSM GPRS etc. or wireline Ethernet USB FireWire Power Line Comms etc. . These devices are normally Integrated Circuits IC or chip . They are designed to be configurable platforms. This is done by incorporating one or more microprocessors and using software to configure the chip to perform different functions. This creates a very difficult debug problem.

At a certain stage in the development there may be several chips running software and trying to communicate with each other. The software will contain bugs. It is difficult enough trying to debug a single processor with new software. The difficulty increases significantly when there is more than one processor in the chip. The difficulty increases hugely when there are several chips trying to communicate with each other via incomplete bug ridden interfaces. This is why it is very important for each chip to contain a debug interface that allows them all to be connected in a debug network. It is also important that the debug interface is non invasive. This allows each chip to continue functioning in its normal manner without having its function or timing affected when the debug interface is in operation.

The original SIF interface XAP patent 1994 provided non invasive debug to a single processor in a single chip. The new SIF interface xSIF iSIF provides non invasive debug to many chips each potentially containing many processors.

For example there might be a single computer connected to 10 chips via the SIF debug interface locally via USB interface or remotely via ethernet interface . One of the functions of the chips is to communicate with each other e.g. via a radio link or power line communications . This functional interface may still many bugs. The debug computer may be able to monitor the packets of information travelling between the chips. It may also be able to download and debug software to all the processors in all the chips. This allows it to single step or set break points for all or any of the processors and creates a very complete debug environment that allows the computer to find and fix software bugs within a complex network system.

The network debug system may also be used to find hardware bugs in the chip designs before they have been made into silicon. In this early stage a hardware emulator based on an FPGA Field Programmable Gate Array may be created for each chip. The debug computer may be connected to the emulators via the SIF network in the same way as it would be to the final chips. This debug environment can be used to find hardware and software bugs. When a hardware bug is found it may be fixed and the FPGA re programmed. When a software bug is found it can be fixed from the debug computer and downloaded to the relevant processor in the relevant chip.

The Network SIF Debug system may include many features to support the above functionality. In addition these features may operate within the constraints of modem high speed low power software configurable devices. These are described in the following sections.

The iSIF and or xSIF may contain one or more willing hardware slaves they may be easy to turn off low power and or easy to read write program download data acquisition .

The debug features should generally be available from off chip and on chip devices. Off chip devices are served by xSIF which is a serial interface of 4 or optionally 5 pins. On chip devices are served by iSIF which is a parallel interface. In both cases this may allow the Master to read and write to memory mapped devices RAM ROM Flash IO Register read and write to Processor Registers and issue debug commands e.g. Start Stop Single Step Run to Breakpoint Reset .

The addition of iSIF to the existing xSIF has added very few gates which keeps the system cost low. This has been possible because the instruction codes used xSIF and iSIF are similar.

In practice SIF networks consisting of SIF Computer SIF Pods SIF Slaves are likely to use xSIF for the following purposes downloading software to target memory in selected processor in selected chip executing debug instruction in selected processor in selected chip and reading back data from memory of selected processor in selected chip static data or continuous data for real time data acquisition .

iSIF makes these features available to an on chip SIF Master. This is becoming more common as chip sizes increase and complete networks may exist in a single chip. The SIF Master might be another processor or might be a small hardware state machine. Either way the on chip Master may access the SIF instructions via the iSIF. Because it is all on chip it is acceptable to have a parallel interface with many signals. By using a parallel interface iSIF may enable much faster execution of SIF instructions than xSIF. iSIF is likely to be used for control of software download from non volatile memory e.g. Flash or EEPROM to RAM at bootup time data acquisition from a Slave processor memory to the Master without affecting the Slave s timing or functionality and full processor debug to all the Slave processors e.g. if the Master processor already has its own debug interface e.g. JTAG it can enable full debug of all the processors from the original debug interface via iSIF to all the SIF Slaves. This avoids the need to add any extra external pins to the chip. It also means that it may be possible to create a single debug tool on the computer that can be aware of all the processors on the chip thus creating a fully integrated debug environment.

As the xSIF and iSIF are accessing the same SIF Slaves it could be possible for one interface to hog the SIF module and block accesses from the other. This would be unacceptable to the SIF Masters. Consequently the SIF module has been designed to have a ping pong system that alternates between xSIF and iSIF requests. On completing an xSIF request the SIF module may process an iSIF request if there is one before processing the next xSIF request. Similarly on completing an iSIF request the SIF module may process an xSIF request if there is one before processing the next iSIF request. This means that the xSIF and iSIF channels will generally appear to be open to the SIF Masters. If both channels are being used simultaneously they may simply appear to have lower speeds to the respective SIF Master. XAP3 In a further aspect there is provided the ability to simultaneously monitor and debug a plurality of SIF Slaves. Multiprocessor debugging is provided. Multi processor support in xIDE a particular Integrated Development Environment may be used. Data packets flowing between SIF Slaves e.g. radio or power line communications devices may be monitored.

In a further aspect there is provided a device interface apparatus comprising a plurality of interfaces each comprising respective means for writing data to and or reading data from a respective device and control means for controlling operation of the plurality of interfaces. Each device may be a slave and or may comprise a processor.

Preferably the apparatus further comprises a plurality of control means each adapted to control a respective plurality of interfaces.

Preferably the apparatus further comprises a computer adapted to communicate with and preferably control the or each control means. Preferably the SIF computer is adapted to receive data from and or send data to one or more devices via the or each control means.

Preferably the or each computer is adapted to communicate with a respective plurality of control means using a packet based protocol for instance TCP IP or ethernet.

Preferably the apparatus comprises means for detecting errors in packets sent between the or each computer and at least one of the control means.

Preferably the or each interface comprises a register preferably a shift register and preferably the or each interface comprises a SIF slave module. Preferably the control means comprises a SIF Pod and or a control computer.

Preferably the processor and the interface are on the same circuit board and or form part of an ASIC or FPGA.

Preferably the interface and or the control means and or the computer comprises means for debugging the or each device and or comprises means for capturing data from the or each device and or comprises means for analysing data from the or each device.

Networking of SIF slaves allows a single computer to access many SIF Slaves simultaneously which enables for instance de bugging and or data acquisition on a wide scale.

Referring to the software running on each of the SIF slaves for instance ASICs or FPGAs shown can be debugged because packets can be observed from the computer going to each of them.

This aspect may have particular application to meshing of networked radio devices particularly when used for communication of non voice data which a plurality of separate radio devices are able to identify and communicate with each other. By way of example meshing may be used to control lights in a warehouse. A particular light may be controllable using a radio transmitter. In the case where the radio transmitter is out of range of the light the radio signal from the transmitter may be passed via a plurality of radio devices for instance located on other lights located between the light and the transmitter. The radio devices work out usually upon power up how to communicate with each other and pass messages on to the intended recipient device.

Each radio device has a unique number. Each device may be used as stand alone often battery powered device passing data to and via other devices via radio links.

Each device may be connected via Ethernet in order to enable multi processor debugging. Thus the devices slaves may communicate by radio links between themselves but may also each have an Ethernet connection to the SIF Computer to enable debugging and other data transfer.

The SIF enables the reading of and writing to various specified addresses or registers inside a chip in real time without changing its functionality or timing. It is non invasive. In general the timing of the chip is not changed.

This is particularly advantageous in for instance DSP systems having a fixed frequency plan and enables communications to take place between a SIF Computer and a SIF Slave without changing the SIF Slave s timing.

A chip may be connected up in its real mode to for instance a sensor to a radio to a USB link to a RS232 link or to a CAN link and at the same time may have another wire e.g. SIF going in which may not be part of the application allowing monitoring of operation without changing operation or timing.

XAP4 In a further aspect there is provided the ability to simultaneously monitor and debug a plurality of processors and associated memories. Multiprocessor debugging is provided. Multi processor support in xIDE a particular Integrated Development Environment may be used. Data packets flowing between SIF Slaves e.g. radio or power line communications devices may be monitored.

There can be a single xSIF master accessing multiple ASICs each having one xSIF interface. Furthermore the xSIF master may also access multiple processors within each ASIC. Alternatively there can be a single iSIF master accessing multiple processors via an iSIF within the same ASIC. In this way the xSIF and iSIF masters may access each processor s associated memory registers and debug instructions.

A chip may be connected up in its real mode to for instance a sensor to a radio to a USB link to a RS232 link to a LPT link or to a CAN link and at the same time may have another wire e.g. SIF going in which may not be pan of the application allowing monitoring of operation without changing operation or timing 

There are more potential fault conditions in a network than in a simple point to point communications system. If the SIF Master encounters a fault condition it is important that it is able to recognise that there has been a fault and where it is occurring. If it is a permanent fault it may alert the user to the problem. If it is an occasional fault then the faulty data packets may be exposed so that they can be rejected.

SIF Slaves may contain a simple parity checking scheme. This may have separate parity bits for. PARITY AC for Address Control fields 1 parity bit for both fields together PARITY D for Data field and PARITY S for Status field.

The SIF configurations for XAP3 and XAP4 can mean that if the SIF MOSI or SIF MISO pins are stuck high or low parity errors may be reported in PARITY AC and PARITY S respectively. This is because in both cases the parity bits may be set for odd parity over an even number of bits. This configuration can generally expose both stuck high low faults. If even parity is used or there are an odd number of bits being parity protected then some stuck at faults may not be exposed.

The Parity bits may expose any odd number of bit errors in each of the 3 protected fields. They do not generally expose an even number of errors. In practice this means that they can only be relied upon for up to 1 bit error in each field.

The extra benefit of being able to expose stuck faults on the SIF MOSI and SIF MISO lines is novel. Furthermore this is an added benefit which comes for free no extra hardware needed . Normally parity bits are used to protect parallel words so the concept of exposing stuck faults on a single serial wire is not relevant. In this case the data is serial and synchronous so such a scheme is possible. RS232 is a serial interface that uses parity bits but it is an asynchronous system with start and stop bits is it is not capable of implementing the SIF parity protection scheme described herein.

In a further aspect there is provided an apparatus comprising an interface adapted to communicate with a processor and a control means adapted to communicate with and or control operation of the interface the apparatus further comprising monitoring means for monitoring communication of data preferably between the control means and the interface.

Preferably the monitoring means is adapted to perform an error checking procedure to determine whether there has been an error in communicating data between the interface and the control means.

Preferably the data comprises at least one parity bit and the monitoring means is adapted to carry out a parity checking procedure with respect to the or each parity bit.

Preferably the data comprises a plurality of fields and at least one parity bit is included in or associated with at least one of the plurality of fields. Preferably the plurality of fields comprise at least one of an address field a data field a control field and a status field.

Preferably the control field contains a parity bit preferably a PARITY AC bit. Preferably that parity bit is odd parity including the parity bit itself for the combined address and control fields. Preferably the whole field is an even number of bits.

Preferably the status field contains a parity bit preferably a PARITY D bit. Preferably that parity bit is odd parity odd number of 1s for the combined data field and the parity bit itself.

Preferably the status field contains a further parity bit preferably a PARITY S bit. Preferably that parity bit is odd parity odd number of 1s for the status field including the further parity bit itself .

Preferably the apparatus is adapted to carry out a further operation on the data or on a field included in the data in dependence on the outcome of the parity checking procedure.

Preferably the monitoring means is adapted to monitor communication of data between the interface and the processor and preferably the monitoring means is adapted to perform an error checking procedure to determine whether there has been an error in communicating data between the interface and the processor.

Preferably the monitoring means is adapted to monitor data received by the interface from the control means and or is adapted to monitor data received by the control means from the interface.

Preferably the interface comprises a SIF preferably the processor comprises an 8 bit 16 bit 32 bit or 64 bit processor. Preferably the processor comprises a XAP1 XAP2 or XAP3 processor. Preferably the control means comprises a SIF master and or a control computer. Preferably the apparatus comprises means for debugging or for acquiring data from the interface and or the processor. The processor may form part of an ASIC or FPGA and preferably the interface also forms part of the ASIC or FPGA. Preferably the processor and the interface are on the same circuit board.

XAP4 Parity bit checking in and or out of the SIF may be provided. Parity bit checking is provided for both xSIF and iSIF accesses.

Preferably the interface comprises a SIF preferably the processor comprises an 8 bit 16 bit 32 bit or 64 bit processor.

Preferably the processor comprises a XAP1 XAP2 XAP3 XAP4 or XAP5 processor. Preferably the control means comprises a SIF master and or a control computer. Preferably the apparatus comprises means for debugging or for acquiring data from the interface and or the processor. The processor may form part of an ASIC or FPGA and preferably the interface also forms part of the ASIC or FPGA. Preferably the processor and the interface are on the same circuit board.

To be able to debug many processors on the debug network the SIF Computer needs to run debug software that gives it control of substantially every processor on substantially every chip in the network.

This may be done by the xIDE software running on the SIF Computer. It may download software read and write memory and run debug functions for substantially every processor in the debug network by using the SIF debug network. In addition it may support multiple processors sharing the same memory which is a complicated debug problem.

XAP3 In a further aspect there is provided a processor apparatus comprising a first processor a second processor and interface means adapted to enable communication between the first processor and the second processor.

Preferably the first processor and the second processor are adapted to co operate together via the interface means and preferably the first processor is adapted to perform first aspects of a process and the second processor is adapted to perform second aspects of a process.

Preferably the second processor is programmable so that the second aspects of the process may be varied. Preferably the second aspects comprise aspects relating to a user interface and or pricing aspects and or language aspects i.e. functions that may need to be modified during product lifetime . Preferably the first aspects comprise critical functionality of the process. Preferably the first aspects comprise aspects of the process which require regulatory approval. Preferably the first aspects comprise functionality that is likely to remain fixed throughout the product lifetime.

Preferably the first processor is adapted to carry out the first aspects of the process in dependence upon instructions that may be stored in ROM because they are likely to remain fixed . Preferably the second processor is adapted to carry out the second aspects in dependence upon instructions stored in RAM or Flash memory or in some other rewritable memory because they are unlikely to remain fixed .

Preferably the interface further comprises means for instructing operation of the first processor and or the second processor.

Preferably the first processor is part of an ASIC or FPGA. Preferably the interface comprises a SIF interference.

SIF enables silicon partitioning. Two chip solutions to separate fixed operational features from short term marketing driven features. This reduces the risk of affecting operation of operational features when altering marketing driven features.

There are provided two chips and preferably alteration of functionality of one chip does not affect functionality of the other chip.

As SIF can be used in real applications it is easier to do partitioning of functionality between chips. Typically critical functionality may be provided by one chip and less critical functionality which may vary for particular products and or for regulatory or marketing reasons .

A SIF may be used for monitoring and data logging and analysis in for instance production monitoring and analysis systems.

In one embodiment a SIF is used in a gas meter system. An ASIC is used for front end applications. The ASIC in effect implements all of the critical functionality of the system but different products are made for the German French British and American markets due to the different regulatory requirements.

A separate ASIC is not produced for each market. Instead an external microprocessor is provided which talks to the ASIC over the SIF. The microprocessor can access the ASIC in a way which is not invasive. The design is partitioned so that the critical science functionality cannot be tampered with as it is locked in the ASIC. Whereas the external microprocessor may vary from one market to another.

In another embodiment there is separation between features of Bluetooth functionality which have obtained regulatory approval and features which do not require regulatory approval. A chip is provided which includes features of Bluetooth functionality which require or have obtained regulatory approval. A separate software development environment is provided which can be used for instance by a customer to customise features of the product for instance buttons and LED s. It is ensured that in customising features the Bluetooth functionality cannot be broken or changed in such a way that it would be needed to reapply for radio approvals.

XAP4 Preferably the first processor is part of an ASIC or FPGA. Preferably the interface comprises a SIF interface. This may be an xSIF or iSIF interface.

In a two chip solution the second processor is an xSIF master and on a separate chip from the first processor.

In a one chip solution the two processors are both on the same chip. In this case the second processor is an iSIF master.

Previous SIFs only supported 2 fields address and data. The computer software drivers constrained these field sizes to be 1 to 32 bits. The address field was used for address and control read write prog data side word size etc functions. This meant that in practice the address and data buses could not be a full 32 bits. The data field was used for data and status e.g. time stamp functions. This meant that in practice the data bus could not be a full 32 bits.

The SIFs described herein may use 4 fields address control data and status. All 4 fields may be parameterised to be any size from 1 to 32 bits. This means that it is able to support 32 bit processors with full 32 bit address bus 32 bit data bus. Aspects of this new SIF system from SIF Computer through the SIF Pods and onto SIF Slaves containing several processors reflect these 4 fields. e.g. the xSIF API in the SIF Computer as used by xIDE and Matlab tools reflects these 4 SIF fields. The field sizes are configured differently for XAP3 XAP4 or other processors.

An important point is that these 4 fields enable a SIF computer to perform substantially all SIF instructions to substantially all processors in substantially all SIF chips on the SIF network. The SIF Computer is generally a Master it generally initiates SIF instructions. The processors in the chip SIF Slave are generally slaves and generally respond to the request initiated by the Master. The SIF instructions may be executed in a non invasive manner. Even with network debug they do not generally affect the timing or functionality of the selected processor. This is essential for any system that needs to maintain a frequency plan. This is a requirement for many applications for example the DSP functions for a radio system.

The 4 SIF fields help to identify a particular processor on the selected chip. The xSIF API helps to identify which chip the SIF Master wants to communicate with. This all helps full non invasive network debug to be supported.

By having a long instruction word built of the 4 fields the SIF Master can specify exactly what it wants the SIF Slave to do in every SIF Instruction. It doesn t need to assume any state such as SIF Instructions to this chip are currently going to Processor . This kind of assumption is necessary for many short word protocols. This makes it very difficult for the SIF Master because it is frequently impossible for it to make any assumptions about processor state. Consequently it has to send multiple instructions every time even they are not atomic might be split by a request from a different Master which makes the whole network much slower sometimes cannot work at all.

XAP3 In a further aspect there is provided a processor interface apparatus comprising a register adapted to be connected to a processor and to read data from and or write data to the processor. Preferably the register comprises a plurality of fields preferably at least three fields each field comprising at least one bit.

Preferably the plurality of fields comprises at least one of and preferably all of an address field a control field a data field and a status field.

Preferably the address field comprises an address in the processor from which data is to be read or to which data is to be written and or the address field comprises information which identifies an operation for instance a debug operation to be performed by the processor.

Preferably the data field comprises data to be written to or data which has been read from the processor. Preferably the apparatus is adapted to write the data to the address specified in the address field. Preferably the apparatus is adapted to read the data from the address specified in the address field.

Preferably the control field comprises data relating to control of the processor and or the register and or a further component of the processor interface apparatus and or relating to control of communication between the register and the processor and or a further component of the processor interface apparatus.

Preferably the control field comprises data relating to at least one of error checking parity checking processor identification type of operation to be carried out for instance read or write mode information for instance debug mode SIF mode and data size information.

Preferably the status field comprises data relating to the status of at least one of the processor the register and a further component of the processor interface apparatus and or relating to communication between at least one of the processor the register and a further component of the processor interface apparatus. Preferably the status field comprises data relating to the status of a process carried out by at least one of the processor the register and a further component of the processor interface apparatus. Preferably the status field comprises at least one of an error code a parity code and a timestamp. Preferably the contents of the status field are independent of the address.

An error code may comprise a SIF error code or a processor error code. An error code may be included in the status field.

Preferably the register comprises 88 bits. Preferably the address field comprises 32 bits. Preferably the control field comprises 8 bits. Preferably the data field comprises 32 bits. Preferably the status field comprises 16 bits. Such a configuration of the fields is typically used in the XAP3 processor.

Alternatively the register may comprise 52 bits. In that case preferably the address field comprises 16 bits. Preferably the control field comprises 8 bits. Preferably the data field comprises 16 bits. Preferably the status field comprises 12 bits.

Preferably the further component of the apparatus comprises at least one of a SIF Pod or SIF Master communicating with a SIF Computer running SIF Driver software.

Preferably the register comprises a shift register and preferably the register forms part of a SIF Slave module. Preferably the SIF Slave module is adapted to communicate with a SIF Pod or SIF Master. Preferably the processor is a XAP3 processor.

Four SIF fields may be provided. Each of the four fields may be up to 32 bits long. The four fields may be address control data and status fields.

Transfer of data to and from the address control data and status fields in the preferred embodiment is illustrated diagrammatically in .

The API enables a programmer to program an application which talk to SIF Slaves via SIF Pods. The application may for instance be written in xIDE or SIF Toolkit or Matlab. The API may be an xSIF API or a SIF API.

The SIF API has the concept of two fields address data each of which can be up to 32 bits the lengths being parameterisable. This can be used for instance with XAP1 and XAP2 processors. XAP1 may have a 36 bit shift register. XAP2 may have a 64 bit shift register.

The XAP3 processor requires an 88 bit shift register. This cannot be supported by the SIF API which can only support shift registers up to 64 bits in length.

The xSIF API has the concept of four fields address control data status each of which can be up to 32 bits the lengths being parameterisable. The xSIF API is capable of supporting the 88 bit shift register used by the XAP3 processor.

It is preferable for the SIF and xSIF APIs to be portable across several different computer platforms and programming languages.

In alternative embodiments two fields are provided address data each of 64 bits. This can also support the 88 bit shift register used by the XAP3 processor.

In the preferred embodiment address and data fields have to be 32 bits and address is interpreted the same way in the SIF as in the processor.

There is provided multi processor de bug within a single chip whilst still only having a single SIF. The SIF may have for instance four or five pins.

Preferably in the control field there is a write bit which identifies whether a SIF instruction is a read or a write.

Preferably in the control field there is a debug bit which identifies whether a SIF instruction is a normal instruction or a debug instruction.

Preferably in the control field there are two size bits which say whether a read or write is to use 8 16 or 32 bit d

XAP4 The sizes of each the respective four SIF fields must be the same for the xSIF and iSIF interfaces.

Preferably the register comprises 52 bits. Preferably the address field comprises 16 bits. Preferably the control field comprises 8 bits. Preferably the data field comprises 16 bits. Preferably the status field comprises 12 bits. Such a configuration of the fields is typically used in the XAP4 processor. Thus the SIF address field is the same width as the processor address bus and the SIF data field is the same width as the processor data bus. However the SIF control and status fields are independent of any processor bus widths. Advantageously the SIF control field is identical in all preferred embodiments of the invention. Thus a single SIF device may be used to debug a variety of processors on the same chip.

Preferably the register comprises a shift register and preferably the register forms part of a SIF Slave module. Preferably the SIF Slave module is adapted to communicate with a SIF Pod or SIF Master. Preferably the processor is a XAP4 processor.

Transfer of data to and from the address control data and status fields in the preferred embodiment is illustrated diagrammatically in .

The XAP4 processor requires a 52 bit shift register. The SIF API can support a shift register having two fields each up to 32 bit in length i.e. a total of 64 bits in length However the XAP4 processor requires a shift register having four fields.

The xSIF API has the concept of four fields address control data status each of which can be up to 32 bits the lengths being parameterisable. The xSIF API is thus capable of supporting the 52 bit shift register used by the XAP4 processor.

In alternative embodiments two fields are provided address data each of 64 bits. This can also support the 52 bit shift register used by the XAP4 processor.

Preferably in the control field there is a write bit which identifies whether a SIF instruction is a read or a write.

XAP3 Multiple processors per SIF multi processor support direct SIF instruction talking direct to the SIF .

In a further aspect there is provided apparatus comprising an interface adapted to be connected to a plurality of processors and adapted to communicate with each processor individually. Preferably the interface is also adapted to communicate with the plurality of processors together.

Preferably the interface is responsive to a processor identifier. Preferably each of the processors is responsive to at least one respective processor identifier. Preferably the apparatus is arranged to establish communication between the interface and one or more of the processors in dependence on a processor identifier. Preferably the processor identifier is included in a portion of data and the interface is adapted to process the portion of data and in particular to send the portion of data to or receive the portion of data from a particular processor or processors in dependence upon the processor identifier. Preferably the interface is adapted to read data from or write data to a particular processor or processors in dependence upon the device identifier.

Preferably the apparatus is adapted to read the portion of data into and or out of a register preferably a shift register.

Preferably the interface is adapted to send a reset instruction to a particular processor or processors identified by the processor identifier. The reset instruction may be one of a plurality of reset instructions. One of the reset instructions may be such as to reset the particular processor or processors to a normal mode of operation preferably running in the normal mode of operation. Another one of the reset instructions may be such as to reset the particular processor or processors to a debug mode of operation preferably stopped in the debug mode of operation.

Preferably the interface comprises a SIF or SIF module preferably each processor comprises an 8 bit 16 bit 32 bit or 64 bit processor. Preferably each processor comprises a XAP1 XAP2 or XAP3 processor. Preferably each interface forms part of an interface apparatus which preferably includes means for debugging or for acquiring data from the interface and or the or each processor. The processors may form part of an ASIC or FPGA and preferably the interface also forms part of the ASIC or FPGA. Preferably the processors and the interface are on the same circuit board.

In the preferred embodiment particular bits may be allocated in every SIF instruction which identify a processor if any with which the instruction is concerned.

Typically one SIF per chip is provided and multiple processors per SIF. Multiple processors per chip may be provided. The chip may comprise an ASIC or FPGA. Each SIF instruction may be directed to any one or ones of the multiple processors.

In the preferred embodiment there are various ways which allow a master to talk just to the SIF. There are various ways in which the master can find out about the SIF as well as or instead of about a plurality of processors associated with the SIF. For instance command mode enables information concerning the SIF to be obtained. Direct de bug SIF instructions in normal mode also enable information concerning the SIF to be obtained.

Processor debug SIF instructions may specify one or more of the plurality of processors to which those instructions are to be sent.

By way of example a particular chip may be connected to a computer. The computer using a SIF master installed on or connected to the computer may go into command mode.

In command mode the SIF master may talk to the SIF to find out how many processors there are on the chip and what types they are. It may read various addresses and subsequently when having left normal mode communicate with any of the processors. It may also find out from the SIF what the lengths are of the various SIF fields. It may also obtain an ASIC identifier if one exists which would tell it more about the chip it is connected to. Subsequently the computer may put the system into normal mode and could then for instance debug processor while leaving processor and running. Processor and may be say XAP3 whereas processor may be say XAP2. Individual processors can be reset or the whole chip can be reset Single step or run to break point operation may be set on one processor whilst another is set to run normally. All of these functions are provided in the preferred embodiment without adding any extra pins.

In a further aspect there is provided a processor interface apparatus comprising an interface for writing data to and or reading data from a plurality of processors and control means for controlling operation of the interface. Using a single interface to access several processors uses fewer chip pins than having a separate interface for each processor. For example a single SIF interface with 4 chip pins may be used to access 8 on chip processors.

Preferably the interface further comprises means for instructing operation of each of the plurality of processors.

Preferably the plurality of processors form part of a single chip. Preferably the plurality of processors form part of an ASIC or FPGA.

Preferably the interface comprises a SIF Slave module. Preferably the control means comprises a SIF Pod and or a control computer.

Preferably each of the plurality of processors comprises one of a XAP1 processor a XAP2 processor and a XAP3 processor.

XAP4 Multiple processors per SIF multi processor support direct SIF instruction talking direct to the SIF . Multiprocessor support is provided for xSIF and iSIF accesses.

Preferably the interface comprises a SIF or SIF module preferably each processor comprises an 8 bit 16 bit 32 bit or 64 bit processor. Preferably each processor comprises a XAP1 XAP2 XAP3 XAP4 or XAP5 processor. Preferably each interface forms part of an interface apparatus which preferably includes means for debugging or for acquiring data from the interface and or the or each processor. The processors may form part of an ASIC or FPGA and preferably the interface also forms part of the ASIC or FPGA. Preferably the processors and the interface are on the same circuit board.

In command mode the SIF master may talk to the SIF to find out how many processors there are on the chip and what types they are. It may read various addresses and subsequently when having left normal mode communicate with any of the processors. It may also find out from the SIF what the lengths are of the various SIF fields. It may also obtain an ASIC identifier if one exists which would tell it more about the chip it is connected to. Subsequently the computer may put the system into normal mode and could then for instance debug processor while leaving processor and running. Processor and may be say XAP4 whereas processor may be say XAP2. Individual processors can be reset or the whole chip can be reset Single step or run to break point operation may be set on one processor whilst another is set to run normally. All of these functions are provided in the preferred embodiment without adding any extra pins.

Preferably each of the plurality of processors comprises one of a XAP1 processor a XAP2 processor and a XAP4 processor.

The XAP3 and XAP4 hardware may have 2 asynchronous reset inputs resetb xap resetb sif . The XAP3 and XAP4 hardware may also have 4 synchronous reset outputs. These may be controlled by direct SIF instructions. If connected up correctly they can individually cause resets to occur in separate regions of the chip reset a selected XAP or other processor reset the SIF or other chip debug section reset User Gates on chip . The hardware designer can decide what circuitry should be reset by this signal and reset off chip devices. This signal is an external pin if used.

This means that the central SIF Computer can accurately send specific reset signals to the desired region of every processor in substantially every chip on the debug network. This may be necessary because it is often necessary to put substantially all the SIF Slave devices into a known state and then start them together or in a known sequence in order to debug a complex network system.

The Reset SIF instruction may be a direct SIF instruction that can be executed at any time. It does not generally require the SIF to be put into debug mode. Generally there is only one SIF module per chip so it is not necessary to specify a processor. The instruction may be accompanied by a required data value to reduce the risk of a SIF reset being caused by accident.

The Reset XAP instruction may also be a direct SIF instruction. It may require the selected XAP processor to already be in Debug mode. This is to reduce the risk of a XAP reset being caused by accident.

Also note that it may be possible to reset the XAP into a running or stopped state both are needed for different types of system . This is achieved with the force stop input signal and the self force stop output signal.

XAP3 In a further aspect there is provided a processor interface apparatus comprising a processor an interface and means for a resetting operation of at least part of the apparatus.

Preferably the resetting means is adapted to reset at least part of the processor at least part of the interface at least part of at least one further processor and or at least part of an associated device. Each of these reset operations can be selected individually or together as a simultaneous group.

Preferably the resetting means is adapted to reset operation of the at least part of the apparatus preferably the processor or the at least one further processor independent of the state of operation of the processor or of the at least one further processor.

Alternatively the resetting means is adapted to reset operation of the at least part of the apparatus preferably the processor or the at least one further processor only if the processor or the at least one further processor is in a specified mode preferably in a debug mode.

Preferably the interface comprises a SIF interface comprising at least one of a SIF Slave module and a SIF Pod. Preferably the processor comprises at least one of a XAP1 XAP2 or XAP3 processor. Preferably the processor forms part of an ASIC or FPGA.

In a further aspect there is provided the following features alone or in any appropriate combination direct SIF debug instruction for reset RST normal running RST debug mode debug stopped options everything off chip ASIC SIF selected processor and selected user gates.

SIF instructions are either normal SIF instructions or debug SIF instructions. Debug SIF instructions may be direct debug SIF instructions which are executed in the SIF and do not access any processor or may be processor debug SIF instructions which refer to a selected processor.

Two different styles of reset may be provided which can differentiate between going into the normal reset mode and going into the reset debug mode. Resets may be to everything or to a chip or to specific processors or to the SIF.

XAP4 In a further aspect there is provided a processor interface apparatus comprising a processor an interface and means for a resetting operation of at least part of the apparatus.

The SIF instruction set is identical for xSIF and iSIF accesses. As such the SIF reset instructions are identically available to xSIF and iSIF.

Preferably the interface comprises a SIF interface comprising at least one of a SIF Slave module and a SIF Pod. Preferably the processor comprises at least one of a XAP1 XAP2 XAP3 XAP4 or XAP5 processor. Preferably the processor forms part of an ASIC or FPGA.

Normal SIF instructions are shown first in the table followed by direct debug instructions followed by other debug instructions.

SIF instructions are either normal SIF instructions or debug SIF instructions. Debug SIF instructions may be direct debug SIF instructions which are executed in the SIF and do not access any processor or may be processor debug SIF instructions which refer to a selected processor.

Direct SIF Instructions to Read Preferably to Read Four Counters SIF Status Counters and Direct SIF Instructions to Read Them

There may be Direct SIF instructions to read the values on 4 debug counters. These may monitor the number of reads writes errors and cancels that have occurred in the SIF since it was last cancelled. This can allow the SIF Computer to verify that the number of SIF Instructions seen by the SIF Slave is the same as the SIF Computer thinks has happened. This can allow the SIF Computer to monitor data integrity on the debug network and alert the user if errors are found.

XAP3 In a further aspect there is provided a processor interface apparatus comprising a processor and an interface the interface comprising means for reading data from and or writing data to the processor and the apparatus further comprising means for monitoring operation of the interface and or operation of the processor and or communication between the processor and the interface.

Preferably the monitoring means is adapted to monitor at least one of the number and or type and or timing of data read or write operations between the interface and the processor the number and or type and or timing of errors occurring in the interface the processor or in communication between the processor and the interface the number and or type and or timing of reset operations and or cancellation operations occurring in the interface the processor or in communication between the interface and the processor the quantity of data read write or transferred and the timing of data readings by the processor.

Preferably the interface comprises a SIF interface comprising at least one of a SIF Slave module and a SIF Pod. Preferably the processor comprises at least one of a XAP1 XAP2 or XAP3 processor. Preferably the processor forms part of an ASIC or FPGA.

In a further aspect there is provided at least one self monitoring SIP counter. The SIF itself may monitor the number of reads writes errors and number of cancellations preferably using direct SIF instructions.

The SIF itself has at least one counter and preferably four counters which monitor SIF activity. Preferably the SIF counters monitor at least one of the number of SIF reads since reset the number of writes the number of errors which have occurred and the numbers of times SIF operation has been cancelled.

This aspect is particularly useful in connection with the running of say a data acquisition system particularly an overnight data acquisition system gathering large quantities of data. It enables a user to identify if there had been any problems during the data acquisition process.

In the preferred embodiment there are Direct SIF Instructions in the SIF Slave module to enable a SIF Computer to read the value of these 4 counters via a SIF Pod.

XAP4 Preferably the interface comprises a SIF interface comprising at least one of a SIF Slave module and a SIF Pod. Preferably the processor comprises at least one of a XAP1 XAP2 XAP3 XAP4 or XAP5 processor. Preferably the processor forms part of an ASIC or FPGA.

In the preferred embodiment there are Direct SIF Instructions in the SIF Slave module to enable a SIF Computer to read the value of these 4 counters via a SIF Pod.

When a SIF Master issues a SIF instruction to a SIF Slave it may be that the SIF Slave is running code in normal mode that does not contain any sif or sleeps if instructions. This would mean that the SIF Slave could not generally respond to the SIF Instruction and may cause the xSIF or iSIF bus the one used for the request to hang. This may crash a part of the debug network. So it is necessary to detect and fix such a problem when it occurs. This is particularly important in a large network that may contain hundreds of SIF Slave devices. The SIF Computer may be able to detect any part of the network that has crashed and be able to repair it automatically.

This may be done by the SIF Master monitoring the time from the SIF request and causing a time out if it has to wait too long. This is equally the case for an on hip SIF Master using iSIF or an off chip SIF Master using xSIF. Having detected the problem the SIF Master may have a Cancel method to fix it.

For iSIF this may be achieved with the isif cancel input signal. When the iSIF Master pulls this signal high it may cancel the pending SIF instruction which the iSIF Master can see because the isif done output signal will go high. For xSIF this may be done by one of several methods including pulling SIF CS low SIF CS is an optional pin so this will not always be possible and toggling SIF CLK 32 times and sampling SIF MOSI for for example the last 8 clocks. This may indicate what type of Cancel to occur. Such a Cancel can specify whether to cancel an xSIF instruction or an iSIF instruction or both.

Note that generally iSIF cannot cancel an xSIF instruction but xSIF can cancel an iSIF instruction. i.e. xSIF has priority. This means that an external debug system xSIF Master can generally guarantee to put the chip into a known state despite what lockup condition it has got into. It would not be good to let the iSIF Master cancel an xSIF request. If the iSIF Master software had bugs it could crash the system and prevent the external debug system from recovering the situation and putting the chip back into a known state. That is why generally the iSIF Master cannot cancel an xSIF instruction.

XAP3 In a further aspect there is provided a processor interface apparatus comprising an interface and a processor the interface being adapted to communicate with the processor when the processor is in a communication mode.

Preferably the processor is adapted to enter the communication mode in response to a signal from the interface. Preferably the processor is adapted to exit the communication mode in response to an indication that a communication process has been completed successfully.

Preferably the interface is adapted to communicate with the processor only when the processor is in a communication mode and the interface is in a communication mode. Preferably the interface is adapted to enter the communication mode in response to a signal from the processor that the processor is in the communication mode.

Preferably there is provided means for making the processor and or the interface exit the communication mode after a specified time delay preferably a specified time delay from entry into the communication mode. Preferably the means for making the processor and or the interface exit the communication mode is included in a control means.

Preferably the processor is adapted to exit the communication mode in response to a signal preferably a signal from the interface regardless of whether the communication process has been completed successfully or not.

Preferably the processor is adapted to exit the communication mode in response to the interface stopping requesting communication. Preferably the interface is adapted to stop requesting communication in response to a cancel signal from a or the control means.

Preferably the interface comprises a SIF interface comprising at least one of a SIF Slave module and a SIF Pod. Preferably the processor comprises a XAP3 processor. Preferably the processor forms part of an ASIC or FPGA. Preferably the control means comprises a SIF pod and or a SIF computer.

In known handshake procedures a master may queue up a request and a slave may be waiting to process the request but may never get an answer and thus may stay stuck low. In that case a SIF may not be usable thereafter and may produce an error message such as SIF error even though the error would not have been with the SIF .

Furthermore if a number of devices are on the same pod then if one of them pulls SIF LOADB low then not only is that device stuck but the pod cannot contact any of the devices because the SIF is being shared by the devices.

Examples of when SIF LOADB may get stuck low in known handshake procedures occur when an invalid request is made for instance when an undefined SIF instruction is given if it is requested to write to a register which is read only a request is made which requires being in debug mode but the SIF is not in debug mode or a request is made whilst a processor is running which requires the processor to be stopped or to execute a processor sif or processor sleeps if instruction.

The SIF Cancel Method features provide solutions to the problems outlined in the preceding three paragraphs.

In the first method the master pulls the slave chip select pin SIF CS low causing the slave to no longer be selected and clearing any pending SIF cycles which are stuck.

In the second method the slave automatically stops pulling the relevant pin low regardless of actions that have taken place after a certain number of clock cycles for instance 32 cycles on SIF CLK. Thus the SIF is cleared simultaneously for all the slaves.

The first method typically requires that each slave be cleared in turn. However usually no more than one slave should be selected at any one time so no more than one slave should be stuck at any one time in any event. The second method typically clears all slaves simultaneously.

Typically if a pod makes a request that can t be completed by the slave because it has not received the relevant processor sif or processor sleepsif instructions it leaves SIF LOADB stuck low. That tells the pod that it has requested something that it shouldn t have done. Typically the SIF Computer detects a timeout and then issues a SIF CANCEL procedure which will clear the stuck SIF and allow SIF LOADB to go high again.

If an iSIF master has to wait too long for an iSIF access it performs a time out and cancels the iSIF access with the isif cancel signal.

If an xSIF master has to wait to long for an xSIF access it performs a time out and cancels the xSIF access using one of the xSIF cancel methods.

The following paragraphs in this section refer in particular to methods an xSIF master may use to issue a SIF cancel.

Preferably the interface comprises a SIF interface comprising at least one of a SIF Slave module and a SIF Pod. Preferably the processor comprises a XAP4 processor. Preferably the processor forms part of an ASIC or FPGA. Preferably the control means comprises a SIF pod and or a SIF computer.

In the second method the slave automatically stops pulling the relevant pin low regardless of actions that have taken place after a certain number of clock cycles for instance 32 cycles on SIF CLK. Thus the SIF is cleared simultaneously for all the slaves. This method can cannel an xSIF an iSIF or both accesses. These different types of cancels are distinguished by the SIF slave sampling SIF MOSI for the last 8 cycles of SIF CLK.

A common SIF instruction is for the SIF Master to read a memory location of a specified address on a specified processor on a specified SIF Slave device. In a debug network it may be that the response data values arrive in a different order from that in which the requests were issued. It is very useful to know whether the SIF instruction executed cleanly or with an error. If there was an error it is useful to know what type of error it was. For all responses it is useful to know the exact time at which the SIF Slave formed its response Data and Status fields .

The Status field may be used for error reporting and for capturing the value of any user selected hardware register in the ASIC at the time the SIF instruction is completed for SIF read or write . It is often useful to make this register a hardware timestamp i.e. a counter that is clocked at some known rate. This means that when the SIF Master receives the response from the SIF instruction that it will generally know the time at which the SIF instruction was completed in the SIF Slave.

This is very useful for data acquisition systems. It means that the SIF Computer may reconstruct a series of data samples with the connect time interval between them. It also may expose whether there are any missing data samples which is important when trying to characterise an analogue cell such as an ADC .

Having the Status field for the timestamp means that the Data field is left free for a full 32 bit data bus.

XAP3 In a further aspect there is provided a processor interface apparatus comprising a register preferably a shift register adapted to be connected to a processor and to read data from and or write data to the processor.

Preferably the register comprises a plurality of fields preferably at least three fields and more preferably four fields each field comprising at least one bit and preferably the time stamp data is included in at least one of the fields.

Preferably the time stamp data corresponds to a portion of data preferably to a portion of data written to or read from the register. Preferably the time stamp data indicates when the portion of data was written to or read from the register and or written to or read from the processor. Preferably the portion of data is data from a device preferably a sensing device associated with the processor and the timestamp indicates when the portion of data was recorded by the device.

Preferably the plurality of fields comprises at least one of and preferably all of an address field a control field a data field and a status field.

Preferably the time stamp data is included in the status field. The corresponding portion of data may be included in the data field.

Preferably the register comprises 88 bits. Preferably the address field comprises 32 bits. Preferably the control field comprises 8 bits. Preferably the data field comprises 32 bits. Preferably the status field comprises 16 bits.

Preferably the further component of the apparatus comprises at least one of a SIF Pod or SIF Master together with a SIF Computer running SIF Driver software.

Preferably the register comprises a shift register and preferably the register forms part of a SIF Slave module. Preferably the SIF Slave module is adapted to communicate with a SIF Pod or SIF Master. Preferably the processor is a XAP3 processor.

The status field is 16 bits in the preferred embodiment and the top two bits used are as parity bits PARITY S PARITY D . STAT is a time stamp this is discussed in more detail below.

Processors according to the invention and in particular XAP processors may be used for instance in software debug production tests or data acquisition. In preferred embodiments the SIF is used to acquire data from a processor relating to each of those activities.

In the preferred embodiments for data acquisition the master continuously requests data from the slave. The slave attaches a time stamp to each piece of data that it sends to the master. The master can analyse the timestamps to see if it has missed any piece of data or whether it has received two or more pieces of data from the same sampling period at the master or whether it has received two or more pieces of data with the same timestamp.

Preferably in performing software de bug a pod controls transfer of data and the pod does not have to respond to transactions initiated by the slave.

Preferably the same SIF interface with the same pins is used for debug and for data acquisition. In the preferred embodiment the data transfers are always initiated by the SIF Pod and Computer never by the SIF Slave. This means that in the preferred embodiment the SIF Slave never throws data even during data acquisition. The SIF Slave in the preferred embodiment always responds to requests from the SIF Pod whether it is being used for control or data acquisition. This makes it much easier to create a deterministic data transfer system. The problem is that during data acquisition some data samples may be acquired more than once and other samples may be missed. The SIF timestamp is a system solution to this problem.

One example of the use of a data acquisition process is the use of an ADC analogue to digital converter . Preferably the signal being sampled is over sampled to ensure that no samples are missed. In characterising an ADC it is important not to miss any samples. It is also important to know whether two copies of the same data have been obtained.

A typical software loop for an ASIC processor comprises obtaining new data then executing the software then issuing a processor sleepsif instruction to enable the external SIF Pod to obtain data from the ASIC. In the processor sleepsif window the SIF can get many reads of the same data. The SIF does not know at that time whether it is in cycle n or cycle n 1.

Preferably there is provided a hardware counter which is incremented at some known rate normally correlated to the data acquisition rate within the chip for instance about 24 kHz .

Preferably the status field is arranged to give extra data which is independent of the address. In the case where a lot of reads are being carried out the data is from the address requested. The status field is independent of the address requested and can be used for any ASIC register or memory at any address.

Preferably the status field is used to provide a time stamp. In the example given above the time stamp is an indication of sample number. Accordingly it is possible to determine whether duplicate copies of the same data have been obtained or whether samples have been missed.

In certain embodiments over sampling takes place and the data obtained may be post processed for instance in Matlab. Duplicate copies of data may then be discarded. Accordingly one and only one copy of the relevant data is obtained by the post processing.

This feature is particularly useful when using PCs in a data acquisition process as PCs can occasionally miss data acquisition for periods of time typically 2 to 3 millisecond in length. The use of a time stamp enables identification of periods where data is missing.

Considering the time stamp in more detail shift register bit definitions for the preferred embodiment are provided.

It can be seen that the shift register bits are divided between address control data and status fields in the preferred embodiment and that there are 32 address bits 8 control bits 32 data bits and 16 status bits.

Transfer of data to and from the address control data and status fields in the preferred embodiment is illustrated diagrammatically in .

It can be seen that in the preferred embodiment the 8 bits of the control field are made up of three processor bits control bits one debug bit control bit two size bits control bits one parity bit control bit and one write bit control bit .

It can be seen from the description of shift register bits to which make up the 32 bit data field that in the preferred embodiment the data field may be used for 8 16 or 32 bit read and write operations.

In the preferred embodiment the status field can be used for a variety of purposes. It can be seen that two of the status bits are used as parity bits six of the status bits are used as error bits and eight of the status bits are used for other status purposes which may include being used as a time stamp.

In other embodiments bits in particular status bits may be used for other purposes or in different combinations. For instance thirteen of the sixteen status bits could be used as a time stamp or for other status purposes.

Preferably status and control fields are broken down into individual bits each bit having its own function either alone or in combination with other bits.

The time stamp frequency may be chosen to suit a particular purpose and may be chosen on command of a user.

Preferably the time stamp is dependent on operation of the SIF and or of the processor. It may be synchronised with a data acquisition update rate or a software loop rate.

Data written to the status field may comprise a software register written to by the processor as well as or instead of time stamp data.

XAP4 Preferably the register comprises 52 bits. Preferably the address field comprises 16 bits. Preferably the control field comprises 8 bits. Preferably the data field comprises 16 bits. Preferably the status field comprises 12 bits.

Preferably the register comprises a shift register and preferably the register forms part of a SIF Slave module. Preferably the SIF Slave module is adapted to communicate with a SIF Pod or SIF Master. Preferably the processor is a XAP4 processor.

It can be seen that the status field is 12 bits in the preferred embodiment and that the top two bits used are as parity bits PARITY S PARITY D . STAT is a time stamp discussed in more detail below.

Considering the time stamp in more detail shift register bit definitions for the preferred embodiment are provided.

It can be seen that the shift register bits are divided between address control data and status fields in the preferred embodiment and that there are 16 address bits 8 control bits 16 data bits and 12 status bits.

Transfer of data to and from the address control data and status fields in the preferred embodiment is illustrated diagrammatically in .

It can be seen from the description of shift register bits to which make up the 32 bit data field that in the preferred embodiment the data field may be used for 8 16 or 32 bit read and write operations.

In other embodiments bits in particular status bits may be used for other purposes or in different combinations. For instance nine of the twelve status bits could be used as a time stamp or for other status purposes.

The SIF Computer may be connected to many SIF Slave chips via the SIF debug network. It is important that the SIF Computer is able to recognise what kind of device each SIF Slave is for the network may be connected to many different types of SIF Slave device. Different SIF Slave devices may have different SIF shift register lengths and be connected to different numbers of internal processors each of which needs to be identified.

SIF command mode may allow a SIF Master to automatically interrogate a SIF Slave device via xSIF. Generally it is not necessary for iSIF as the on chip processor types will be known at chip design time.

SIF command mode may be a standard protocol which uses substantially all the xSIF pins except SIF LOADB. This means that the SIF commands do not generally cause a SIF instruction to be executed which is a desirable feature. Generally identifying what kind of device the SIF Slave is should not affect its behaviour or operation.

SIF command mode reveals to the SIF Master the size of the 4 SIF fields address control data status what kind of processor if any there is at each of the 8 on chip processor locations from 0 to 7 the ASIC identifier.

This is enough information to allow the SIF Master to communicate with on chip processors on substantially every SIF Slave device. The SIF Master may perform this automatically and there is not generally any need for manual configuration by the user. This is an essential feature for a debug network which may contain hundreds of SIF Slave devices.

XAP3 The SIF command mode enables plug and play. Different SIFs may be of different length the SIF command mode may be used mainly for query functions. Use of the SIF command mode enables query functions without the need to add extra pins without affecting normal operation and without having any ambiguity of command.

In a further aspect there is provided an interface apparatus comprising an interface adapted to communicate with a device for instance a processor and a control means adapted to communicate with and or control the interface the interface being adapted to send data concerning itself to the control means and the control means being adapted to configure itself or the interface dependent upon the data.

Preferably the interface is adapted to send the data concerning itself to the control means when in a specified mode preferably a Command mode. Preferably there is provide a command set for use in the Command mode the command set comprising a plurality of commands. Preferably the interface is one of a plurality of interfaces and preferably each interface is adapted to recognise a respective sub set of the command set or all of the command set. Preferably all of the interfaces recognise a common sub set of the command set.

By providing such features interface interrogation functionality is provided without the need to add additional hardware for instance additional pins and without affecting existing modes of operation. Existing modes of operation may comprise for instance Normal SIF instructions Debug SIF instructions and SIF Cancel operations.

Preferably the data comprises at least one of a specific processor or chip identifier or a generic interface identifier identifying the type of interface preferably the type of SIF interface or data representing at least one individual characteristic of at least one component of the interface preferably a SIF interface. The at least one individual characteristic may comprise a field length for instance an address control data or status field length. Also the at least one individual characteristic may comprise information concerning the bits within a field in particular within the control and or status fields.

Preferably the interface may be one of a plurality of interfaces. Preferably each interface comprises a respective shift register. Preferably each shift register comprises a plurality of fields.

Preferably the interface is adapted to send data concerning itself in response to a request signal from the control means. Preferably the request signal comprises a specified sequence of signals. Preferably the apparatus is arranged so that the request signal may be sent from the control means to the interface over a channel which is normally used to send other signals between the control means and the interface and the interface is adapted to recognise and respond to the request signal when sent over the channel.

Preferably the request signal comprises a specified sequence of 8 16 32 64 128 or 256 bits or other data units. Preferably the interface is adapted to enter a command mode in response to the request signal. Preferably the interface is adapted to exit the command mode in response to a further request signal which may be the same as or different to the request signal.

Preferably the interface comprises a SIF. Preferably the control means comprises a SIF Pod and or a control computer. Preferably the processor comprises an 8 bit 16 bit 32 bit or 64 bit processor. The processor may be a XAP1 processor a XAP2 processor or a XAP3 processor. The processor may form part of an ASIC or FPGA and preferably the interface also forms part of the ASIC or FPGA. Preferably the processor and the interface are on the same circuit board. Preferably the request signal represents a command in Command mode.

SIF normally operates in Normal mode. In the preferred embodiment a Command mode is provided for interrogation purposes in particular to ascertain characteristics of a particular SIF.

In preferred embodiments all SIFs recognise certain common commands in Command mode and all SIFs enter the Command mode in the same way. However particular SIFs may not be adapted to recognise all commands in Command mode.

In preferred embodiments all SIFs recognise request commands requesting a chip identifier or SIF type or number or type of processors associated with the SIF or SIF field length or information concerning bits within a SIF field.

In preferred embodiments in Command mode if the SIF does not recognise a command it generates a response of 0xFF. The range of responses to any valid command in Command mode is 0x00 to 0xFE.

SIF characteristics may vary and in particular characteristics of the SIF shift register or SIF shift register fields in particular SIF shift register length or SIF shift register field length may vary for different SIFs and or for different processors with which a SIF may be associated.

For instance for XAP1 XAP2 and XAP3 processors the SIF shift register length is typically 32 bits 64 bits and 88 bits respectively.

In the preferred embodiment a command mode is provided. When the SIF is in the command mode the master can interrogate the SIF typically using query functions. When in the command mode in the preferred embodiment the SIF does not access the associated processor the SIF is returned to normal mode when access to the associated processor by the SIF is required.

In the preferred embodiment the command mode is entered in response to a series of 256 clocks bits representing successive Hex 33333 . . . signals on the SIF MOSI line.

When the SIF is in command mode the master can ask various questions for instance what is the address field length what is the control field length What is the data field length How many processors do you have what types of processors are they at the various places . There is provided an instruction set which the SIF can recognise in command mode.

Then when you either shift in an instruction of zeros or you pull chip select low or you pull SIF LOADB low it immediately reverts to normal mode.

Thus the ability to interrogate an interface or part of an interface and to set up control means so as to communicate with and or control the interface is provided without adding any extra pins to the SIF and in a way which does not affect normal operation. In the preferred embodiment command mode can be entered without having to pull SIF LOADB low.

Typically in the preferred embodiment when a device is first plugged in command mode is entered the device is interrogated the apparatus is tailored to the device if necessary and then normal mode is entered.

Preferably the interface is adapted to send the data concerning itself to the control means when in a specified mode preferably a Command mode. Preferably there is provided a command set for use in the Command mode the command set comprising a plurality of commands. Preferably the interface is one of a plurality of interfaces and preferably each interface is adapted to recognise a respective sub set of the command set or all of the command set. Preferably all of the interfaces recognise a common sub set of the command set.

Preferably the interface comprises a SIF. Preferably the control means comprises a SIF Pod and or a control computer. Preferably the processor comprises an 8 bit 16 bit 32 bit or 64 bit processor. The processor may be a XAP1 processor a XAP2 processor a XAP3 processor or a XAP4 processor. The processor may form part of an ASIC or FPGA and preferably the interface also forms part of the ASIC or FPGA. Preferably the processor and the interface are on the same circuit board. Preferably the request signal represents a command in Command mode.

For instance for XAP1 XAP2 XAP3 XAP4 or XAP5 processors the SIF shift register length is typically 32 bits 64 bits 88 bits and 52 bits respectively.

In the preferred embodiment a command mode is provided. When the SIF is in the command mode the master can interrogate the SIF typically using query functions. When in the command mode in the preferred embodiment the SIF does not access the associated processor the SIF is returned to normal mode when access to the associated processor by the SIF is required.

According to a further aspect of the present invention there are provided multiple processors per chip and or multiple chips.

Many modem chips contain more than one processor. It is common to have a control processor and a data processor e.g. a DSP . Sometimes there will be more than 2 processors on a given chip. These processors may each have their own memories or may share memory. Either way it is important that the network debug system is still able to access all the processors and their associated memories in every chip on the network. Furthermore these features should be provided in a non invasive manner and with fast access times.

Some debug systems e.g. JTAG only allow a 1 dimensional daisy chain access to all the on chip devices. This can result in very long shift registers and slow access times if there are many on chip processors.

By contrast SIF may provide a random access 2 dimensional access to substantially every processor and substantially every memory on the chip. This means that the network debug is provided in a fast manner via xSIF and iSIF to substantially all the on chip devices. This is vastly superior to a 1 dimensional solution.

The default SIF module in XAP3 and XAP4 systems may support up to 8 on chip processors in this 2 dimensional parallel manner.

Another useful feature is that the SIF Master may issue a direct SIF instruction which will cause substantially every processor in a single chip to stop when any of those processors hit a breakpoint. This is a very valuable feature when debugging multiple processor systems. There is also the more conventional simple direct SIF instruction which causes a single processor to stop when it hits a breakpoint. Both features are needed in a network debug system.

XAP3 Multiple processors per SIF multi processor support direct SIF instruction talking direct to the SIF .

In a further aspect there is provided apparatus comprising an interface adapted to be connected to a plurality of processors and adapted to communicate with each processor individually. Preferably the interface is also adapted to communicate with the plurality of processors together.

Preferably the interface is responsive to a processor identifier. Preferably each of the processors is responsive to at least one respective processor identifier. Preferably the apparatus is arranged to establish communication between the interface and one or more of the processors in dependence on a processor identifier. Preferably the processor identifier is included in a portion of data and the interface is adapted to process the portion of data and in particular to send the portion of data to or receive the portion of data from a particular processor or processors in dependence upon the processor identifier. Preferably the interface is adapted to read data from or write data to a particular processor or processors in dependence upon the device identifier.

Preferably the apparatus is adapted to read the portion of data into and or out of a register preferably a shift register.

Preferably the interface is adapted to send a reset instruction to a particular processor or processors identified by the processor identifier. The reset instruction may be one of a plurality of reset instructions. One of the reset instructions may be such as to reset the particular processor or processors to a normal mode of operation preferably running in the normal mode of operation. Another one of the reset instructions may be such as to reset the particular processor or processors to a debug mode of operation preferably stopped in the debug mode of operation.

Preferably the interface comprises a SIF or SIF module preferably each processor comprises an 8 bit 16 bit 32 bit or 64 bit processor. Preferably each processor comprises a XAP1 XAP2 or XAP3 processor. Preferably each interface forms part of an interface apparatus which preferably includes means for debugging or for acquiring data from the interface and or the or each processor. The processors may form part of an ASIC or FPGA and preferably the interface also forms part of the ASIC or FPGA. Preferably the processors and the interface are on the same circuit board.

In the preferred embodiment particular bits may be allocated in every SIF instruction which identify a processor if any with which the instruction is concerned.

Typically one SIF per chip is provided and multiple processors per SIF. Multiple processors per chip may be provided. The chip may comprise an ASIC or FPGA. Each SIF instruction may be directed to any one or ones of the multiple processors.

In the preferred embodiment there are various ways which allow a master to talk just to the SIF. There are various ways in which the master can find out about the SIF as well as or instead of about a plurality of processors associated with the SIF. For instance command mode enables information concerning the SIF to be obtained. Direct de bug SIF instructions in normal mode also enable information concerning the SIF to be obtained.

Processor debug SIF instructions may specify one or more of the plurality of processors to which those instructions are to be sent.

By way of example a particular chip may be connected to a computer. The computer using a SIF master installed on or connected to the computer may go into command mode.

In command mode the SIF master may talk to the SIF to find out how many processors there are on the chip and what types they are. It may read various addresses and subsequently when having left normal mode communicate with any of the processors. It may also find out from the SIF what the lengths are of the various SIF fields. It may also obtain an ASIC identifier if one exists which would tell it more about the chip it is connected to. Subsequently the computer may put the system into normal mode and could then for instance debug processor while leaving processor and running. Processor and may be say XAP3 whereas processor may be say XAP2. Individual processors can be reset or the whole chip can be reset Single step or run to break point operation may be set on one processor whilst another is set to run normally. All of these functions are provided in the preferred embodiment without adding any extra pins.

In a further aspect there is provided a processor interface apparatus comprising an interface for writing data to and or reading data from a plurality of processors and control means for controlling operation of the interface. Using a single interface to access several processors uses fewer chip pins than having a separate interface for each processor. For example a single SIF interface with 4 chip pins may be used to access 8 on chip processors.

Preferably the interface further comprises means for instructing operation of each of the plurality of processors.

Preferably the plurality of processors form part of a single chip. Preferably the plurality of processors form part of an ASIC or FPGA.

Preferably the interface comprises a SIF Slave module. Preferably the control means comprises a SIF Pod and or a control computer.

Preferably each of the plurality of processors comprises one of a XAP1 processor a XAP2 processor and a XAP3 processor.

XAP4 Multiple processors per SIF multi processor support direct SIF instruction talking direct to the SIF . Multiprocessor support is provided for xSIF and iSIF accesses.

Preferably the interface comprises a SIF or SIF module preferably each processor comprises an 8 bit 16 bit 32 bit or 64 bit processor. Preferably each processor comprises a XAP1 XAP2 XAP3 XAP4 or XAP5 processor. Preferably each interface forms part of an interface apparatus which preferably includes means for debugging or for acquiring data from the interface and or the or each processor. The processors may form part of an ASIC or FPGA and preferably the interface also forms part of the ASIC or FPGA. Preferably the processors and the interface are on the same circuit board.

In command mode the SIF master may talk to the SIF to find out how many processors there are on the chip and what types they are. It may read various addresses and subsequently when having left normal mode communicate with any of the processors. It may also find out from the SIF what the lengths are of the various SIF fields. It may also obtain an ASIC identifier if one exists which would tell it more about the chip it is connected to. Subsequently the computer may put the system into normal mode and could then for instance debug processor while leaving processor and running. Processor and may be say XAP4 whereas processor may be say XAP2. Individual processors can be reset or the whole chip can be reset Single step or run to break point operation may be set on one processor whilst another is set to run normally. All of these functions are provided in the preferred embodiment without adding any extra pins.

Preferably each of the plurality of processors comprises one of a XAP1 processor a XAP2 processor and a XAP4 processor.

When a SIF Master is doing data acquisition from a SIF Slave it may be possible for the SIF Slave to control the rate of data requests. The SW Master may sit in a loop continually requesting SIF reads from the SIF Slave. The SIF Slave may only let the SIF read instruction complete when it is ready by holding isif done of SIF LOADB low . This allows the SIF Slave to reduce noise and interference caused by xSIF transactions while it is making sensitive ADC readings from its analogue circuitry. This is valuable as it can increase the accuracy of the analogue readings.

One way the SIF Slave can achieve this is in software by not executing a sif or sleepsif instruction until the ADC readings are complete.

Another way is in hardware. The SIF Slave can contain FIFO First In First Out hardware for capturing the data samples. The FIFO can be hardware coupled to the SIF so that the SIF instruction is only completed when a new piece of data has arrived in the FIFO. Generally only at this point is isif done for iSIF or SIF LOADB for xSIF allowed to go high. It is generally only when the xSIF MAster sees that SIF LOADB has gone high that it will shift the SIF results out on xSIF thus causing potential noise and interference . But at this point it doesn t matter as the analogue data sample has already been captured cleanly. This hardware method may leave the processor free to get on with other processing while the FIFO is waiting for the next data sample.

In a further aspect there is provided an interface apparatus comprising an interface and a processor the processor comprising a register for temporary storage of data and the interface being adapted to read data stored in the register.

Preferably the apparatus further comprises means for sending a signal to the interface indicating that the register has been updated the interface being adapted to read updated data stored in the register in response to the update signal.

Preferably the apparatus further comprises control means adapted to communicate with the interface. Preferably the apparatus comprises means for sending to the control means data read from the register by the interface.

Preferably the control means is adapted to establish a communication session with the interface. Preferably the sending means is adapted to send the data from the interface to the control means during a communication session. Preferably the sending means is adapted to maintain a communication session between the control means and the interface pending updated data becoming available to be sent from the interface to the control means.

Preferably the interface comprises an interface register arranged so that data read from the register is read to the interface register. Preferably the register comprises a FIFO first in first out .

Preferably the interface comprises a SIF preferably the processor comprises an 8 bit 16 bit 32 bit or 64 bit processor. Preferably the processor comprises a XAP1 XAP2 or XAP3 processor. Preferably the control means comprises a SIF master and or a control computer. Preferably the apparatus comprises means for debugging or for acquiring data from the interface and or the processor. The processor may form part of an ASIC or FPGA and preferably the interface also forms part of the ASIC or FPGA. Preferably the processor and the interface are on the same circuit board.

Preferably when a master issues a SIF instruction to read the FIFO address the SIF LOADB handshake will not be completed until the FIFO has been updated with new data and then the processor executes a processor sif instruction or a processor sleepsif instruction.

A handshake procedure may be provided between the SIF and a master. The master may make a request and the SIF LOADB may stay low until the new data obtained from the FIFO. The SIF would then release the new data to the master.

Preferably the interface comprises a SIF preferably the processor comprises an 8 bit 16 bit 32 bit or 64 bit processor. Preferably the processor comprises a XAP1 XAP2 XAP3 XAP4 or XAP5 processor. Preferably the control means comprises a SIF master and or a control computer. Preferably the apparatus comprises means for debugging or for acquiring data from the interface and or the processor. The processor may form part of an ASIC or FPGA and preferably the interface also forms part of the ASIC or FPGA. Preferably the processor and the interface are on the same circuit board.

A handshake procedure may be provided between the SIF and an xSIF master. The xSIF master may make a request and the SIF LOADB may stay low until the new data is obtained from the FIFO. The SIF would then release the new data to the xSIF master.

A handshake procedure may be provided between the SIF and an iSIF master. The iSIF master may make a request with isif load and the isif done signal may stay low until the new data is obtained from the FIFO. The SIF would then release the new data to the iSIF master.

Plays to modem interface packet protocols high bits s and low packets s i.e. favours high granularity data.

Modem communication protocols are based on packets of data. They have high bit rate but low packet rate. i.e. the data packets are large. Wireline protocols such as Ethernet and USB both display this characteristic. The same also applies to wireless protocols such as WiFi IEEE 802.11 and Bluetooth.

To take advantage of such communications channels the SIF should also be capable of high granularity data transactions. The xSIF API contains simple low granularity instructions such as xsif read xsif write .

However the xSIF API also contains high granularity instructions that can achieve high data throughput such as xsif read array xsif read block xsif write block .

XAP3 In a further aspect there is provided apparatus comprising a control means preferably a SIF pod adapted to be connected to a control computer preferably a SIF computer and to send data to and or receive data from the control computer and means for performing an error checking and connection procedure on the data. Preferably the error checking procedure is based upon checking CRC codes included in the data.

Preferably the SIF pod is adapted to be connected to the control computer via an ethernet or USB or RS232 or LPT link.

XAP4 Preferably the SIF pod is adapted to be connected to the control computer via an Ethernet or USB or RS232 or LPT link.

This is a software method to solve the problem described herein of keeping interference and noise low while acquiring sensitive analogue signals.

Many software loops consist of process new data samples go to sleep wakeup and re start execution when there is a hardware wakeup indicating that a new set of data samples is ready .

If the software is happy for xSIF or iSIF transactions to occur during the sleep period it should use a sleepsif instruction. If it is not happy for xSIF or iSIF instructions to occur during the sleep period it should use the sleepnop instruction.

In a further aspect the XAP can individually enable just iSIF or just xSIF instructions by using the instructions isif xsif sleepisif and sleepxsif.

XAP3 In a further aspect there is provided an instruction for a processor adapted to communicate via an interface the instruction when processed by the processor causing communication from the interface to the processor and or from the processor to the interface to be stopped or not allowed preferably for a fixed period and or until a further instruction is processed.

In a further aspect them is provided an interface for communication with a processor the interface being responsive to an instruction from the processor to stop communication with the processor and or to not allow communication with the processor and or to not allow transmission of data from the interface to the processor preferably for a fixed period and or until receipt of a further instruction.

A sleepsif instruction may allow external debugger access to processor registers and memory while the processor is in the low power sleep state. A sleepnop instruction may prevent SIF accesses. These two instructions allow an application programmer to control precisely when a SIF has access to the system s resources.

Distinct sleepnop and sleepsif instructions may be provided. Control from the slave end is thus provided enabling it to ensure that the SIF is quiet for instance allowing the slave to take readings.

Preferably the processor has two states a sleeping state and an awake state. In the sleeping state at least part of the operation of the processor may be suspended for example by suspending the execution of any further instructions which may reduce the power consumed by the processor. In the awake state the processor may be capable of a greater degree of operation than is possible in the sleeping state for example the processor may execute instructions that are not available in the sleeping state. Thus the greater degree of activity permitted in the awake state results in the processor consuming more power whilst in the awake state than whilst in the sleeping state.

The sleeping state may comprise two sub states a sleepsif state and a sleepnop state. In the sleepsif state the processor may be capable of performing functions related to debugging and in particular a SIF Module may be fully operable. However in the sleepsif state other functionality of the processor may not operable and in particular the processor may not operable to execute instructions unrelated to debugging such as those of User Mode programs.

In the sleepnop state the processor may not be operable to execute any instructions more particularly neither instructions related to debugging nor instructions unrelated to debugging may be executed in the sleepnop state. Thus in the sleepnop state the SIF Module may be inoperable. The provision of the sleepnop state can further reduce the power consumption of the processor relative to that of the sleepsif state and the processor awake state. Additionally by deactivating the SIF Module in the sleepnop state electrical noise that may be produced by the SIF Module may be reduced which may allow more accurate measurements to be made by an analogue to digital converter that is incorporated in an electrical circuit comprising the microprocessor.

Sometimes a chip is powered up with the processor running and the memory has not been initialised. This is not a healthy design but during hardware development it may well occur.

It is useful if the SIF Computer can execute SIF instructions even in this state to read and write memory. Generally some Direct SIF Instructions are enabled even when there is no sif or sleepsif instruction in the processor code. However other SIF instructions may require a sif or sleepsif instruction to be executed.

In such a situation it is quite likely that the memory will start up in an all high or all low state. For this reason the XAP3 sif instruction has been defined to be all 1s 32 bit version and all 0s 16 bit version . This means that the processor is likely to execute sif instructions which is a useful state even from uninitialised memory.

XAP3 The processor sif background debug interface instruction may be all 1 s in 32 bit form and or all 0 s in 16 bit form. This allows for example external SIF control from the SIF Pod when the internal ASIC processor data bus is stuck at all 1s or all 0s.

In a further aspect there is provided a processor adapted to execute a debug instruction automatically upon the occurrence of a fault. Preferably the fault is an unintended or unforeseen mode of operation of a computer program being executed by the processor. Preferably the debug instruction is encoded by a binary word corresponding to logic levels that are likely to be found on a bus of the processor following a fault. Preferably the bus is a program memory data bus. Preferably the debug instruction is encoded by a binary word in which all bits are 1 or as a binary word in which all bits are 0.

Preferably the processor is capable of executing one or more instructions encoded as a binary word having a first length and one or more instructions encoded as a binary word having a second length wherein the first length is greater than the second length. Preferably the processor is adapted to execute a long debug instruction encoded as a word of the first length and a short debug instruction encoded as a word of the second length. Preferably the short debug instruction is encoded by a word equal to the one s complement of the least significant bits of the long debug instruction.

In the preferred embodiment operation of the SIF Slave module may be initiated when a dedicated processor sif instruction is executed by the processor Core. The processor sif instruction may be stored in program memory typically on a flash memory device and read into the Core via the Memory Management Unit.

In certain embodiments when a processor sif instruction is read by the Core the Core completes execution of its current instruction and sends a signal to the SIF Slave module by setting the Core s SIF output signal to a defined logic level. The execution of further instructions by the Core is suspended until a CONTINUE signal is received by the Core from the SIF Slave module the Core CONTINUE input signal typically using the sane logic level as the CONTINUE output from the SIF Slave module . By suspending the execution of further instructions by the Core in this manner the SIF Slave module and debugger can be permitted to have uninhibited access to registers in the Core and to the rest of the apparatus. This can also allow debug access via the SIF Slave module to be easily synchronised with software being executed on the processor.

In a preferred example of a processor which executes 32 bit instructions the SIF instruction is encoded as 0x00000000. In another preferred example of a processor which executes. 32 bit instructions the SIF instruction is encoded as 0xFFFFFFFF. In other words the SIF instruction is denoted by an instruction in which all bits are zero and or in which all bits are 1. Thus when a SIF instruction is read from program memory into the Core all of the 32 lines of the program memory data bus are high or all of the 32 lines of the program memory data bus are low. Such an arrangement of logic levels on the program memory data bus is also likely to occur following a fault such as may be caused by incorrect operation of a program being executed by the Core for example or when no software has yet been loaded. Therefore by encoding the SIF instruction with a binary word that is likely to be found on the program memory data bus following a fault the processor can be caused automatically to execute a SIF instruction immediately following such a fault. This can allow operation of the SIF module to be initiated in response to the fault thereby allowing software to be debugged.

In a preferred example in which the processor is capable of executing both 16 bit an 32 bit instructions in 16 bit instruction mode the SIF instruction is encoded as 0x0000 and in 32 bit mode as 0xFFFFFFFF.

Performance of an operation may require a processor sif instruction. In certain circumstances errors may result in the data bus being stuck at all 1s or all 0s.

By making the processor sif debug instruction all 1s or all 0s external SIF control and debugging is enabled when such errors occur.

SIF instructions are either normal SIF instructions or debug SIF instructions. Debug SIF instructions may be direct debug SIF instructions which are executed in the SIF and do not access any processor or may be processor debug SIF instructions which refer to a selected processor.

The first three instructions in table 50 by way of example are SIF normal instructions for reading from and writing to memory. The size of the data field whether 8 bit 16 bit or 32 bit is specified. In order to carry out the read or write process a processor sif or a processor sleepsif instruction is first required from the processor.

In the preferred embodiment instructions for for instance going into debug mode coming out of debug mode reading status reading version number and reading license number may be carried out without being in debug mode.

Once in debug mode a wide range of actions may be performed for instance Stop Run Single Step Run to Break

In the normal mode of the preferred embodiment a SIF operation comprises three stages shift in stage handshake stage and shift out stage.

In certain circumstances there may be some ambiguity as an operation may be validly waiting for something to happen may be operating with a time delay or may be stuck an error having occurred . In each case there may a significant amount of time after the shift in stage before a handshake occurs during which time it may not be clear whether the processor is operating normally and the handshake will occur in due course or whether the processor has locked up.

XAP4 The processor sif background debug interface instruction may be all 1 s in 32 bit form and or all 0 s in 16 bit form. This allows for example external SIF control from the SIF Pod when the internal ASIC processor data bus is stuck at all 1s or all 0s. This may be exploited by xSIF and iSIF accesses.

As mentioned above it can be seen that in preferred embodiments SIF instructions are either normal SIF instructions or debug SIF instructions. Debug SIF instructions may be direct debug SIF instructions which are executed in the SIF and do not access any processor or may be processor debug SIF instructions which refer to a selected processor.

The first two instructions in table 71 by way of example are SIF normal instructions for reading from and writing to memory. The size of the data field whether 8 bit or 6 bit is specified. In order to carry out the read or write process a processor sif or a processor sleepsif instruction is first required from the processor.

In the normal mode of the preferred embodiment a SIF operation comprises three stages shift in stage handshake stage and shift out stage.

XAP3 In a further aspect there is provided a processor instruction set which is not regular but which is tailored to compiler behaviour and or calling convention.

Preferably registers are not all treated symmetrically by instructions. The instructions may play to the coding conventions used by the compiler. In particular instruction set support for the compiler s conventions for function entry and exit can achieve significant improvement in code density.

In the preferred embodiment certain registers are used for certain functions by the C compiler. For instance there may be certain things that may require to be done by register R which are not required to be done with register R. Accordingly there may be particular instructions for say R and not for R.

In the preferred embodiment the first five function arguments are passed in registers R to R and subsequent function arguments are passed on the stack ie in memory . Therefore in the preferred embodiment there are also provided instructions which have preferential support for registers R to R.

Examples of instructions which have preferential support for R to R in the preferred embodiment include the 16 and 32 bit forms of movm and movm.x the 16 and 32 bit forms of pop.ret the 16 bit forms of ldm and stm.

In the preferred embodiment the function return value is passed in register R Therefore in the preferred embodiment there are also provided instructions which have preferential support for register R.

Some instructions may in practice be used often and other instructions may be used less often. In the preferred embodiments 16 bit codings are given to those instructions which are used often and only 32 bit codings are given to those instructions which are used less often.

Preferably there are provided compound instructions each compound instruction being adapted to carry out a plurality of actions. Thus fewer instruction fetches are required Examples of such compound instructions in the preferred embodiment include movm. ldm. stm. push push.r pop pop.ret blkst.r blkst.8.r and blkcps.r where is a wildcard character .

Preferably the processor comprises an 8 bit 16 bit 32 bit or 64 bit processor. Preferably the processor comprises a XAP1 XAP2 or XAP3 processor. The processor may form part of an ASIC or FPGA and preferably the interface also forms part of the ASIC or FPGA. Preferably the processor and the interface are on the same circuit board or chip.

In a further aspect there is provided a processor having a variety of instruction sizes determined on an instruction by instruction basis.

That enables higher code density than would be achieved with a single fixed instruction size whilst still being simple for the programmer to use.

Preferably an immediate value of 0 is interpreted to represent 1. This is possible in the case where a register in the preferred embodiment R represents zero. Thus code density may be further improved.

Efficient function entry and exit is essential for good code density. In the preferred embodiment efficient function entry is provided by the push and push.r instructions.

Efficient function entry and exit is essential for good code density. In the preferred embodiment efficient function exit is provided by the pop and pop.ret instructions.

In a further aspect uneven register visibility in instructions for instance in 16 bit instructions is provided to optimise for code density.

XAP4 In the preferred embodiment certain registers are used for certain functions by the C compiler. For instance there may be certain things that may require to be done by register R which are not required to be done with register R. Accordingly there may be particular instructions for say R and not for R.

In the preferred embodiment the first three function arguments are passed in registers R to R and subsequent function arguments are passed on the stack ie in memory . Therefore in the preferred embodiment there are also provided instructions which have preferential support for registers R to R.

Examples of instructions which have preferential support for R to R in the preferred embodiment include pop pop.ret and push.

In the preferred embodiment the function return value is passed in register R Therefore in the preferred embodiment there are also provided instructions which have preferential support for register R.

Examples of such instructions which have preferential support for RD in the preferred embodiment include pop.ret.

Preferably there are provided compound instructions each compound instruction being adapted to carry out a plurality of actions. Thus fewer instruction fetches are required. Examples of such compound instructions in the preferred embodiment include push pop and pop.ret. Preferably the processor comprises an 8 bit 16 bit 32 bit or 64 bit processor. Preferably the processor comprises a XAP1 XAP2 XAP3 XAP4 or XAP5 processor. The processor may form part of an ASIC or FPGA and preferably the interface also forms part of the ASIC or FPGA. Preferably the processor and the interface are on the same circuit board or chip.

Preferably a 3 bit field identifies whether the instruction is 16 or 32 bit. Preferably 7 of the 3 bit values represent 16 bit instructions and the remaining 8value represents 32 bit instructions. This ratio may result in close to optimum code density for a 16 bit processor. This leads to 56 k 16 bit instructions and 512M 32 bit instructions.

Efficient function entry and exit is essential for good code density. In the preferred embodiment efficient function entry is provided by the push instruction.

In another aspect there is provided a processor which is provided without a constant zero register. In this way compiled code density may be improved.

Preferably the instruction includes both a read and a write form in which case the instruction either reads data from or writes data to a memory location specified in part by the register. In a preferred embodiment XAP4 the read instruction is in the form of a load instruction ld.p and the write instruction is in the form of a store instruction st.p . In this way code density may be improved.

These instructions are used for global data which can be variables and constants. Such instructions improve code density.

XAP3 Examples of instructions which have preferential support for R to R in the preferred embodiment include the 16 and 32 bit forms of movm and movm.x the 16 and 32 bit forms of pop the 16 and 32 bit forms of pop.ret the 16 bit forms of ldm and stm the 16 bit forms of push and push.r.

Preferably there are provided compound instructions each compound instruction being adapted to carry out a plurality of actions. Thus fewer instruction fetches are required. Examples of such compound instructions in the preferred embodiment include movm. ldm. stm. push push.r pop and pop.ret where is a wildcard character .

In a further aspect there is provided an instruction for a processor for writing each of a plurality of portions of data to a respective register. Preferably at least one of the portions of data comprises an immediate.

Preferably the instruction comprises a plurality of arguments each argument comprising a respective one of the portions of data or a respective address preferably a register selector .

Preferably there is associated with each portion of data a respective flag which indicates whether that portion of data should be interpreted as an address for instance a register selector or as an immediate.

Preferably an immediate value of 0 is interpreted to represent 1. This is possible in the case where a register in the preferred embodiment R represents zero. Thus code density may be further improved.

Preferably the or each address comprises the address preferably a register selector where a respective portion of data is stored and preferably the instruction when performed is such as to cause the portion of data stored at the or each address preferably a register selector to be written to a respective one of the registers. Preferably the or each address is a register address or identifier such as a register selector. Preferably the instruction comprises a series of arguments and the instruction when performed is such as to cause each of the series of arguments or a respective portion of data obtained by processing of each of the series of arguments to be written in order to a respective one of a series of registers.

Preferably the processor comprises an 8 bit 16 bit 32 bit or 64 bit processor. Preferably the processor comprises a XAP1 XAP2 or XAP3 processor. The processor may form part of an ASIC or FPGA.

In the preferred embodiment the movm instruction can move up to five registers or small immediate values into R R thus replacing up to five mov instructions with a single movm instruction.

In the preferred embodiment the order of writing to registers for movm is from R to R. In contrast the order of writing to registers for movm.x is from R to R. By providing both movm and movm.x chained copies of registers is possible from low to high registers and from high to low registers.

In a further aspect there is provided an instruction for a processor which moves each of a plurality of data elements into a respective one of a plurality of registers the instruction comprising at least one identifier and a plurality of arguments each argument being representative of a respective one of the plurality of data elements the at least one identifier identifying for each argument the type of data of which that argument is representative. Preferably each argument when processed is processed in dependence upon the type of data of which it is representative. Preferably the types of data comprise register data and immediates and each argument comprises one of a register address and an immediate value.

In the preferred embodiment both movm source and pop.ret return value fields can be registers or immediates encoded as a 5 bit field one bit specifies register immediate the remaining four bits specifying either one of R R or an immediate value of 1 1 . . . 15.

In the preferred embodiment memory is only accessed through a load from memory to register or a store from register to memory or multiples of such operations or through push and pop instructions which are other multi cycle instructions associated with the stack or with the swap instruction.

In a further aspect there is provided an instruction for instance push and push.r in the preferred embodiment which writes multiple registers to a stack allocates space for local automatic variables and updates a stack pointer register accordingly.

In the preferred embodiment the push instruction pushes all selected registers from R to R onto the stack. This saves many instructions at the beginning of a function for saving call save registers on the stack. This reduces power consumption.

In the preferred embodiment the push.r instruction pushes registers from R upwards and then copies any of registers R R to matching registers from R onwards. This saves many instructions at the beginning of a function for saving call save registers on the stack and copying argument registers into the upper registers. This uses even fewer memory accesses than the push instruction thereby further reducing power consumption.

In the preferred embodiment both the push and push.r instructions assume that R is the stack pointer.

Efficient function entry and exit is essential for good code density. In the preferred embodiment efficient function entry is provided by the push and push.r instructions.

In a further aspect there is provided an instruction for a processor for instance a pop or pop.ret instruction in the preferred embodiment which loads at least one register from memory via a stack pointer removes zero or more words of automatic storage for instance as allocated by an instruction such as a push or push.r instruction in the preferred embodiment and updates the stack pointer.

Examples of instructions which have preferential support for R to R in the preferred embodiment include the 16 and 32 bit forms of movm and movm.x the 16 and 32 bit forms of pop the 16 and 32 bit forms of pop.ret the 16 bit forms of ldm and stm the 16 bit forms of push and push.r.

Examples of such instructions which have preferential support for R in the preferred embodiment include the 16 and 32 bit forms of pop.ret.

Preferably there are provided compound instructions each compound instruction being adapted to carry out a plurality of actions. Thus fewer instruction fetches are required Examples of such compound instructions in the preferred embodiment include movm. ldm. stm. push push.r pop and pop.ret where is a wildcard character .

In the preferred embodiment memory is only accessed through a load from memory to register or a store from register to memory or multiples of such operations or through push and pop instructions which are other multi cycle instructions associated with the stack or with the swap instruction.

Preferably the instruction takes an additional argument preferably a register or small immediate and stores that argument in a register for instance in R in the preferred embodiment and updates condition flags as if that value was compared with 0. Preferably the instruction for instance the pop.ret instruction in the preferred embodiment then executes a return via another register for instance the Link Register in the preferred embodiment . This reduces the number of instructions thus reducing memory size and power consumption.

Efficient function entry and exit is essential for good code density. In the preferred embodiment efficient function exit is provided by the pop and pop.ret instructions.

In the preferred embodiment both movm source and pop.ret return value fields can be registers or immediates encoded as a 5 bit field one bit specifies register immediate the remaining four bits specifying either one of R R or an immediate value of 1 1 . . . 15.

In a further aspect there is provided a processor adapted to process portions of data of variable length the processor comprising means for determining the length of a portion of data and being adapted to process the portion of data in dependence upon that determination.

In a further aspect uneven register visibility in instructions for instance in 16 bit instructions is provided to optimise for code density.

In a further aspect there is provided a processor and associated instructions in which registers of the processor are not all treated symmetrically by the processor instructions. Preferably the use of registers is tailored to the coding conventions used by the compiler. Certain registers are used for certain functions by the compiler.

In the preferred embodiment the design of the 16 bit instruction set has been further optimised to be even closer to the output of the compiler for example some 16 bit instructions allow access to R R and R R skipping R due to register usage behaviour of the compiler.

There are certain things that it may be desired to do with say register R which it is not desired to do with say register R. Accordingly in the preferred embodiment there are certain instructions for R and not for R.

In a further aspect there is provided a processor instruction set which is not regular but which is tailored to compiler behaviour and or calling convention.

Preferably registers are not all treated symmetrically by instructions. The instructions may play to the coding conventions used by the compiler. In particular instruction set support for the compiler s conventions for function entry and exit can achieve significant improvement in code density.

In the preferred embodiment certain registers are used for certain functions by the C compiler. For instance there may be certain things that may require to be done by register R which are not required to be done with register R. Accordingly there may be particular instructions for say R and not for R.

In the preferred embodiment the first five function arguments are passed in registers R to R and subsequent function arguments are passed on the stack ie in memory . Therefore in the preferred embodiment there are also provided instructions which have preferential support for registers R to R.

Examples of instructions which have preferential support for R to R in the preferred embodiment include the 16 and 32 bit forms of movm and movm.x the 16 and 32 bit forms of pop the 16 and 32 bit forms of pop.ret the 16 bit forms of ldm and stm the 16 bit forms of push and push.r.

In the preferred embodiment the function return value is passed in register R Therefore in the preferred embodiment there are also provided instructions which have preferential support for register R.

Examples of such instructions which have preferential support for R in the preferred embodiment include the 16 and 32 bit forms of pop.ret.

Some instructions may in practice be used often and other instructions may be used less often. In the preferred embodiments 16 bit codings are given to those instructions which are used often and only 32 bit codings are given to those instructions which are used less often.

Preferably there are provided compound instructions each compound instruction being adapted to carry out a plurality of actions. Thus fewer instruction fetches are required. Examples of such compound instructions in the preferred embodiment include movm. ldm. stm. push push.r pop and pop.ret where is a wildcard character .

Preferably the processor comprises an 8 bit 16 bit 32 bit or 64 bit processor. Preferably the processor comprises a XAP1 XAP2 or XAP3 processor. The processor may form part of an ASIC or FPGA and preferably the interface also forms part of the ASIC or FPGA. Preferably the processor and the interface are on the same circuit board or chip.

XAP3 These features are implemented in certain embodiments of the invention such as XAP3 and not implemented in other embodiments XAP4 or XAP5 .

Preferably there are provided compound instructions each compound instruction being adapted to carry out a plurality of actions. Thus fewer instruction fetches are required. Examples of such compound instructions in the preferred embodiment include push pop and pop.ret.

XAP4 In a further aspect there is provided an instruction for instance push in the preferred embodiment which writes multiple registers to a stack allocates space for local automatic variables and updates a stack pointer register accordingly.

In the preferred embodiment the push instruction pushes all selected registers from R to R onto the stack. This saves many instructions at the beginning of a function for saving call save registers on the stack. This reduces power consumption.

Efficient function entry and exit is essential for good code density. In the preferred embodiment efficient function entry is provided by the push instruction.

Preferably the processor comprises an 8 bit 16 bit 32 bit or 64 bit processor. Preferably the processor comprises a XAP1 XAP2 XAP3 XAP4 or XAP5 processor. The processor may form part of an ASIC or FPGA.

Examples of instructions which have preferential support for R to R in the preferred embodiment include pop pop.ret and push.

Examples of such instructions which have preferential support for R in the preferred embodiment include pop.ret.

Preferably there are provided compound instructions each compound instruction being adapted to carry out a plurality of actions. Thus fewer instruction fetches are required. Examples of such compound instructions in the preferred embodiment include push pop and pop.ret.

Preferably the instruction takes an additional argument preferably a register or small immediate and stores that argument in a register for instance in R in the preferred embodiment and updates condition flags as if that value was compared with 0. Preferably the instruction for instance the pop.ret instruction in the preferred embodiment then executes a return via another register for instance the Link Register R in the preferred embodiment . This reduces the number of instructions thus reducing memory size and power consumption.

In the preferred embodiment the design of the 16 bit instruction set has been further optimised to be even closer to the output of the compiler for example some 16 bit instructions allow access to R R but not to R due to register usage behaviour of the compiler.

There are certain things that it may be desired to do with say register R which it is not desired to do with say register R. Accordingly in the preferred embodiment there are certain instructions for R and not for R.

In the preferred embodiment certain registers are used for certain functions by the C compiler. For instance there may be certain things that may require to be done by register R which are not required to be done with register R. Accordingly there may be particular instructions for say R and not for R.

In the preferred embodiment the first three function arguments are passed in registers R to R and subsequent function arguments are passed on the stack ie in memory . Therefore in the preferred embodiment there are also provided instructions which have preferential support for registers R to R.

Examples of instructions which have preferential support for R to R in the preferred embodiment include pop pop.ret and push.

In the preferred embodiment the function return value is passed in register R Therefore in the preferred embodiment there are also provided instructions which have preferential support for register R.

Examples of such instructions which have preferential support for R in the preferred embodiment include pop.ret.

Preferably there are provided compound instructions each compound instruction being adapted to carry out a plurality of actions. Thus fewer instruction fetches are required Examples of such compound instructions in the preferred embodiment include push pop and pop.ret.

Preferably the processor comprises an 8 bit 16 bit 32 bit or 64 bit processor. Preferably the processor comprises a XAP1 XAP2 XAP3 XAP4 or XAP5 processor. The processor may form part of an ASIC or FPGA and preferably the interface also forms part of the ASIC or FPGA. Preferably the processor and the interface are on the same circuit board or chip.

In a further aspect there is provided a processor adapted to process portions of data of variable length the processor comprising means for determining the length of a portion of data and being adapted to process the portion of data in dependence upon that determination.

In a further aspect uneven register visibility in instructions for instance in 16 bit instructions is provided to optimise for code density.

In a further aspect there is provided a processor and associated instructions in which registers of the processor are not all treated symmetrically by the pro r instructions. Preferably the use of registers is tailored to the coding conventions used by the compiler. Certain registers are used for certain functions by the compiler.

In the preferred embodiment the design of the 16 bit instruction set has been further optimised to be even closer to the output of the compiler for example some 16 bit instructions allow access to R R but not to R due to register usage behaviour of the compiler.

There are certain things that it may be desired to do with say register R which it is not desired to do with say register R. Accordingly in the preferred embodiment there are certain instructions for R and not for R.

XAP3 Preferably each instruction can be 16 bit or 32 bit freely mixed on an instruction by instruction basis.

16 bit instruction decode may be done serially 16 32 as a decompression stage prior to full 32 bit decode.

In a further aspect there is provided a 16 bit instruction set which is a true subset of a 32 bit instruction set each 16 bit instruction may be mapped onto a corresponding 32 bit instruction.

In a further aspect there is provided an instruction set having equivalent instructions in short and long forms. Preferably all instructions in the instruction set are available in long form and a sub set of the instructions is available in short form. Preferably instructions which are used frequently and which can be coded in a short form are provided in a short form.

Being able to mix instructions freely on a long and short form basis means that the processor does not need to have distinct instruction length modes which thus provides a simple programming model for the programmer.

In a further aspect there is provided a processor adapted to process portions of data of variable length the processor comprising means for determining the length of a portion of data and being adapted to process the portion of data in dependence upon that determination.

Preferably the determining means is adapted to determine the length of a portion of data in dependence upon a length identifier the length identifier preferably being included in or associated with the portion of data.

Preferably the processor is adapted to process a series of portions of data in turn the determining means being adapted to determine the respective length of each portion of data in turn and the processor being adapted to process each portion of data in dependence on the respective determined length.

Preferably the or each portion of data may comprise at least one operator and may also comprise at least one argument.

Preferably there is provided an instruction set preferably for a processor as described herein comprising an instruction provided in a first portion of data having a first length and an instruction provided in a second portion of data having a second length the first length being greater than the second length. Preferably the first portion of data comprises an argument and the second portion of data comprises a further argument the length of the argument of the first portion of data being longer than the argument of the second portion of data. Preferably the first portion of data comprises an operator and the second portion of data comprises the same operator. Preferably each of the first portion of data and the second portion of data comprises a respective length identifier identifying the length of that portion of data. Preferably the first portion of data has a length of 32 bits and the second portion has a length of 16 bits.

In a further aspect there is provided an instruction set comprising a first sub set of instructions which are provided in both a first form and a second form and a second sub set of instructions which are provided in a first form. Preferably each instruction in its first form comprises a portion of data of a first length and each instruction in its second form comprises a portion of data of a second length the first length being greater than the second length. Preferably each instruction comprises an operator and or an argument. Preferably an or each instruction is provided in the second form or not in dependence on the length of a respective operator and or in dependence on the length of a respective argument and or in dependence on the likelihood that the instruction will occur in use of the instruction set. Preferably the instruction set is arranged so that commonly used instructions may be coded with arguments and or operators that are sufficiently short that such commonly used instructions may be provided in both or either the first form and the second form. Preferably each instruction in its first form is a 32 bit instruction and each instruction in its second form is a 16 bit instruction.

Preferably the processor comprises an 8 bit 16 bit 32 bit or 64 bit processor. Preferably the processor comprises a XAP1 XAP2 or XAP3 processor. The processor may form part of an ASIC or FPGA and preferably the interface also forms part of the ASIC or FPGA. Preferably the processor and the interface are on the same circuit board.

As can be seen in the preferred embodiment there are provided both 16 bit instructions and 32 bit instructions. At least some instructions are provided in both 16 bit form and 32 bit form depending on the length of the argument included with the instruction such instructions generally providing identical functionality in both their 16 and 32 bit forms.

Commonly used instructions in the preferred embodiment are provided both in 16 bit and 32 bit forms depending on the length of the argument included in the instruction .

In the preferred embodiment processor memory includes both 32 bit instruction space and 16 bit instruction space. Typically far more 32 bit instruction space is provided than 16 bit instruction space. For instance there may by say 64 000 times more 32 bit instruction space than 16 bit instruction space.

In the preferred embodiment the processor is defined by a 32 bit instruction set and a subset of that which is used frequently is coded in 16 bits. In the preferred embodiment there are around 32 000 different 16 bit instructions and around 2 000 000 000 different 32 bit instructions.

In the preferred embodiment the 32 bit instruction space overlaps the 16 bit instruction space. Instructions may be identical in their 16 bit form and 32 bit forms but they may they have different i.e. smaller in the case of the 16 bit form argument ranges.

Preferably the instruction set is arranged so that roughly 60 to 70 of operations carried out are from 16 bit instructions with regard to this statement at least an operation could be considered to be say adding 13 to register R whilst say adding 14 to register R would be considered to be a different operation .

In the preferred embodiment the compiler produces assembler code which does not indicate whether an instruction is 16 bit or 32 bit. For each piece of assembler code the assembler then determines whether there is underlying 16 bit code or only underlying 32 bit code available.

Preferably there is provided a 16 32 bit converter adapted to convert 16 bit instructions to 32 bit instructions prior to execution.

As discussed instructions have a minimum size of either 16 bits or 32 bits in the preferred embodiment. Preferably 16 bit instructions also have a 32 bit form.

In the preferred embodiment there are 6 bits in the primary op field and there are 64 primary op codes. In the preferred embodiment each primary op code can take a 25 bit argument. The 25 bit argument may be split into different fields.

In one embodiment op codes to are left free. Op code is an extended op code. All extended op code instructions have arguments which are less than 25 bits arguments of 21 bits or less in the preferred embodiment.

Preferably some instructions are provided which have a separate prime opcode for each register eg mov.p . This allows coding long immediates in single instructions.

XAP4 Preferably each instruction can be 16 bit or 32 bit freely mixed on an instruction by instruction basis. 16 bit instructions require a single memory fetch. 32 bit instructions require a double memory fetch.

Some instructions are only available in 16 bit form. Some instructions are only available in 32 bit form. Some instructions are available in 16 and 32 bit forms.

Instruction decode is performed as soon as the full instruction is available. This will be after the first fetch for 16 bit instructions and after the second fetch for 32 bit instructions.

Preferably a 3 bit field identifies whether the instruction is 16 or 32 bit. Preferably 7 of the 3 bit values represent 16 bit instructions and the remaining 8value represents 32 bit instructions. This ratio may result in close to optimum code density for a 16 bit processor. This leads to 56 k 16 bit instructions and 512 k 32 bit instructions.

In a further aspect there is provided an instruction set having equivalent instructions in short and long forms. Preferably instructions which are used frequently and which can be coded in a short form are provided in a short form.

Preferably the processor comprises an 8 bit 16 bit 32 bit or 64 bit processor. Preferably the processor comprises a XAP1 XAP2 XAP3 XAP4 or XAP5 processor. The processor may form part of an ASIC or FPGA and preferably the interface also forms part of the ASIC or FPGA. Preferably the processor and the interface are on the same circuit board.

As can be seen in the preferred embodiment there are provided both 16 bit instructions and 32 bit instructions. At least some instructions are provided in both 16 bit form and 32 bit form depending on the length of the argument included with the instruction such instructions generally providing identical functionality in both their 16 and 32 bit forms.

In the preferred embodiment processor memory includes both 32 bit instruction space and 16 bit instruction space. Typically far more 32 bit instruction space is provided than 16 bit instruction space. For instance there may by say 8 000 times more 32 bit instruction space than 16 bit instruction space.

In the preferred embodiment the processor is defined by a 32 bit instruction set and a subset of that which is used frequently is coded in 16 bits. In the preferred embodiment there are around 56 000 different 16 bit instructions and around 500 000 000 different 32 bit instructions.

In the preferred embodiment the 32 bit instruction space overlaps the 16 bit instruction space. Instructions may be identical in their 16 bit form and 32 bit forms but they may they have different i.e. smaller in the case of the 16 bit form argument ranges.

Preferably the instruction set is arranged so that roughly 80 to 90 of operations carried out are from 16 bit instructions with regard to this statement at least an operation could be considered to be say adding 13 to register R whilst say adding 14 to register R would be considered to be a different operation .

In the preferred embodiment there are 3 bits in the primary op field and there are 8 primary op codes. In the preferred embodiment each primary op code can take a 13 bit argument. The 13 bit argument may be split into different fields.

XAP3 In known systems byte addresses are generally used to address memory for a range of processor sizes for instance 8 bit 16 bit and 32 bit processors .

In known systems processors include branch instructions to branch to the location of the next instruction to be executed. The address used in the branch instruction is normally the low address of the instruction being branched to which is significant if the instruction contains more than one byte . That low address is commonly referred to as the low byte. In little endian systems the low byte represents the bottom 8 bits of the instruction or data word . In big endian systems the low byte represents the top 8 bits of the instruction or data word .

In a further aspect there is provided a processor having a variety of instruction sizes determined on an instruction by instruction basis.

That enables higher code density than would be achieved with a single fixed instruction size whilst still being simple for the programmer to use.

Preferably each instruction comprises at least one instruction size bit to indicate the instruction size.

Preferably the at least one instruction size bit is provided in the lowest byte preferably in the lowest bit position in a little endian architecture processor.

Alternatively the at least one instruction size bit is provided in the highest byte preferably in the highest bit position in a big endian architecture processor.

Thus it is ensured that the at least one location size bit is always in the byte address branched to. Preferably this is the lowest byte address of the instruction.

In a further aspect 32 bit instructions and or 16 bit instructions are provided and there is also provided a bit included in an instruction which indicates whether the instruction is a 16 bit instruction or a 32 bit instruction.

In a further aspect there is provided a method of processing data comprising a plurality of bits arranged in a series the plurality of bits comprising at least one bit representing data of a first type and at least one bit representing data of a second type the at least one bit representing data of a first type being provided in a selected position or range of positions in the series.

Preferably the first type data comprises argument data preferably at least one immediate. Preferably the second type data comprises operating code. Preferably the data comprises 32 bit or 16 bit data. Preferably the first type data is provided from a particular bit upwards in series of bits. Preferably the first type data is provided from the 8bit bit when counting from zero upwards in a series of bits. Alternatively the first type data may be provided from a particular bit downwards in a series of bits for instance if using a big endian architecture .

Preferably the processor comprises an 8 bit 16 bit 32 bit or 64 bit processor. Preferably the processor comprises a XAP1 XAP2 or XAP3 processor. The processor may form part of an ASIC or FPGA and preferably the interface also forms part of the ASIC or FPGA. Preferably the processor and the interface are on the same circuit board.

In a further aspect there is provided a XAP3 processor adapted to run of the shelf software for instance Gnu software such as the Gnu C or C compiler and or adapted to communicate using TCP IP protocol and or ethernet protocol and or Bluetooth.

XAP4 In a further aspect there is provided a processor having an instruction set in which the ratio of 16 to 32 bit instructions is greater than 2 1 and less than 32 1 and preferably 7 1.

Preferably the processor comprises an 8 bit 16 bit 32 bit or 64 bit processor. Preferably the processor comprises a XAP1 XAP2 XAP3 XAP4 or XAP5 processor. The processor may form part of an ASIC or FPGA and preferably the interface also forms part of the ASIC or FPGA. Preferably the processor and the interface are on the same circuit board.

In a further aspect there is provided a XAP4 processor adapted to run off the shelf software for instance GNU software such as the GNU C or C compiler and or adapted to communicate using TCP IP protocol and or ethernet protocol and or Bluetooth

XAP3 In a further aspect there is provided an instruction for instance push and push.r in the preferred embodiment which writes multiple registers to a stack allocates space for local automatic variables and updates a stack pointer register accordingly.

In the preferred embodiment the push instruction pushes all selected registers from R to R onto the stack. This saves many instructions at the beginning of a function for saving call save registers on the stack. This reduces power consumption.

In the preferred embodiment the push.r instruction pushes registers from R upwards and then copies any of registers R R to matching registers from R onwards. This saves many instructions at the beginning of a function for saving call save registers on the stack and copying argument registers into the upper registers. This uses even fewer memory accesses than the push instruction thereby further reducing power consumption.

In the preferred embodiment both the push and push.r instructions assume that R is the stack pointer.

Efficient function entry and exit is essential for good code density. In the preferred embodiment efficient function entry is provided by the push and push.r instructions.

Preferably the processor comprises an 8 bit 16 bit 32 bit or 64 bit processor. Preferably the processor comprises a XAP1 XAP2 or XAP3 processor. The processor may form part of an ASIC or FPGA.

XAP4 In a further aspect there is provided an instruction for instance push in the preferred embodiment which writes multiple registers to a stack allocates space for local automatic variables and updates a stack pointer register accordingly.

In the preferred embodiment the push instruction pushes all selected registers from R to R onto the stack. This saves many instructions at the beginning of a function for saving call save registers on the stack. This reduces power consumption.

Efficient function entry and exit is essential for good code density. In the preferred embodiment efficient function entry is provided by the push instruction.

Preferably the processor comprises an 8 bit 16 bit 32 bit or 64 bit processor. Preferably the processor comprises a XAP1 XAP2 XAP3 XAP4 or XAP5 processor. The processor may form part of an ASIC or FPGA.

XAP3 In a further aspect there is provided an instruction for a processor for instance a pop or pop.ret instruction in the preferred embodiment which loads at least one register from memory via a stack pointer removes zero or more words of automatic storage for instance as allocated by an instruction such as a push or push.r instruction in the preferred embodiment and updates the stack pointer.

Preferably the instruction takes an additional argument preferably a register or small immediate and stores that argument in a register for instance in R in the preferred embodiment and updates condition flags as if that value was compared with 0. Preferably the instruction for instance the pop.ret instruction in the preferred embodiment then executes a return via another register for instance the Link Register in the preferred embodiment . This reduces the number of instructions thus reducing memory size and power consumption.

Efficient function entry and exit is essential for good code density. In the preferred embodiment efficient function exit is provided by the pop and pop.ret instructions.

Preferably the instruction takes an additional argument preferably a register or small immediate and stores that argument in a register for instance in R in the preferred embodiment and updates condition flags as if that value was compared with 0. Preferably the instruction for instance the pop.ret instruction in the preferred embodiment then executes a return via another register for instance the Link Register R in the preferred embodiment . This reduces the number of instructions thus reducing memory size and power consumption.

It is important that a 16 bit processor provides good support for 32 bit data variables. By contrast it is not so important that a 32 bit processor provides good support for 64 bit data variables because they are seldom needed or used .

This means that it is more important for a 16 bit processor to have good support for register pairs than it is for a 32 bit processor. It is also important that a 16 bit processor contains instructions that directly use 32 bit values stored in register pairs e.g mov.32.r mult.32s.i div.32u.r . It is more efficient if the register pair can be identified with one register selector field 3 bits for an 8 register processor like the XAP4 than with 2 register selector fields which would be 6 bits in the XAP4 . This means that it is necessary to have a convention as to how the 2 registers in a register pair are related.

A suggestion is to say that a register pair is formed from 2 consecutive registers. e.g. R R or R R. The XAP3 4 5 processors generally use little endian memory organisation low bits of a multi byte word are located at the low byte address . So it is clearest if the registers are organised in the same way. The XAP3 4 5 processors generally organise registers in a little endian manner for storing words that are too big to fit in a single register. e.g. for the 16 bit XAP4 which contains 8 registers R R R R R word 31 16 R word 15 0 and R R R word 31 16 R word 15 0 .

The difference of XAP4 and XAP5 processors over conventional processors is that they allow the register pair to be unaligned as well as aligned.

If the register pairs are aligned then the even registers are generally used for one part of the word low bits in little endian or high bits in big endian and the odd registers are generally used for the other part of the word high bits in little endian or low bits in big endian .

If the registers can be unaligned then substantially any contiguous register pair may be used to stare a 32 bit word. The XAP4 and XAP5 support unaligned and aligned registers in a little endian manner. The register pair is referred to by the lower register of the pair unaligned register pair R R R R word 31 16 R word 15 0 and aligned register pair R R R R word 31 16 R word 15 0 .

In practice we found that this was essential to get the GCC compiler to work for the XAP4 at all. GCC is really aimed at 32 bit processors with at least 16 registers. The XAP4 is a 16 bit processor with only 8 registers so it has much harder to port GCC to it We have succeeded in this and achieved good code density because of the hardware features that we have incorporated. Support for unaligned register pairs was essential for this.

Furthermore the support for unaligned register pairs means that the register allocator in the compiler has an easier job resulting in smaller code size faster execution because register spills to the stack are not needed so often. For example suppose the compiler is already using R and R but R and R are free. If it now needs to load a 32 bit variable into registers it can do so into R R if the processor supports unaligned registers but otherwise it can t. If the processor only supported aligned registers it would have to push R onto the stack and then store the 32 bit variable in R R. Later on it will have to pop the new stack variable back into a free register. This clearly takes more instructions so increases code size reduces execution speed and increases power consumption.

In addition the XAP4 and XAP5 may have 32 bit buses between the register file and the ALU. This means that the processor can access register pair 32 bit variables in a single clock cycle. e.g. in mov.32.r you can move data from substantially any Rs source register pair to substantially any Rd destination register pair in a single clock cycle. So the hardware has been implemented to support the above register scheme unaligned and aligned source and destination register pairs and to do so quickly in a single clock cycle .

This philosophy of supporting unaligned registers can be extended further for longer words. e.g. for 64 bit words stored in 4 16 bit registers aligned register quad R R R R R R word 63 48 R word 47 32 R word 31 16 R word 15 0 unaligned register quad R R R R R R word 63 48 R word 47 32 R word 31 16 R word 15 0 .

Generally there is no hardware or instruction support for 64 bit data variables in XAP4 or XAP5 but the compiler does use the above convention when storing 64 bit words in registers. The fact that the 64 bit word can be stored in registers in an unaligned manner makes it much easier to port GCC and means that it is more efficient at run time because the register allocator has more freedom and therefore register spills to the stack are required less frequently. This reduces code size execution time and power consumption.

XAP3 Preferably some instructions are provided which have a separate prime opcode for each register eg mov.p . This allows coding long immediates in single instructions.

Preferably 17 bit immediates are provided which allow both 17 bit signed for instance 65536 . . . 65535 and unsigned for instance 0 . . . 131069 value ranges to be encoded in a single immediate. This enables an implementation with smaller hardware and lower power consumption.

A 4n 1 where n is an integer format for the immediates may be provided. Preferably the arguments available in different instructions in the instruction set are of length 4n 1 where n is an integer for example of length 25 bits 21 bits 17 bits or 13 bits.

Preferably processor instructions sign extend or zero extend immediates to represent full word length. In the preferred embodiment full word length is 32 bits.

Preferably reserved word features used in assembler would not be valid in C. Preferably any reference to a register or registers is prefixed by a percentage. Preferably immediates are prefixed with a hash. Preferably the assembler instructions are case sensitive. Preferably reserved words in assembler are lower case.

In a further aspect there is provided an instruction which allows a programmer to explicitly specify the value of the high bits in an immediate and which provides that all unspecified low bits take the value of the least significant specified bit. This is effectively down extending the least significant specified bit of the immediate.

In a further aspect there is provided an instruction for a processor for performing an operation dependent on a first portion of data the operation comprising setting the value or sign of a second portion of data dependent on the value of at least part of the first portion of data or generating the second portion of data to have a value or sign dependent on the value of sign of at least part of the first portion of data.

Preferably the first portion of data is included in the instruction. Preferably the first portion of data comprise an immediate.

Preferably the operation comprises setting each bit of the second portion of data to be 0 or to be 1 or to be the same as a selected bit in the first portion of data. Preferably the selected bit is the lowest bit in the first portion of data.

Preferably the instruction may be referenced by an instruction reference which is recognised by a processor the instruction including a base instruction reference and an additional reference. Preferably the processor recognises the base instruction reference as being to a further instruction. Preferably the additional reference comprises a suffix to the base reference and preferably comprises a type mnemonic and preferably comprises .h .i or .r.

Preferably the processor comprises an 8 bit 16 bit 32 bit or 64 bit processor. Preferably the processor comprises a XAP1 XAP2 or XAP3 processor. The processor may form part of an ASIC or FPGA.

In the preferred embodiment the high immediate .h instructions combined with the 17 bit immediate feature support the setting of the upper half of a 32 bit value to a 16 bit value together with setting the lower sixteen bits to 0 or 1. This is particularly useful in creating bit masks where the remaining bits of a 32 bit mask must be 0 or 1. .h instructions combine two instructions setting the upper and lower halves of a 32 bit value into a single instruction.

In the preferred embodiment a single immediate instruction can be used to assign a full 32 bit immediate to a SIF where either all the top bits are all zeros or all ones or all the bottom bits are all zeros or all ones.

Thus for example in the case where it is only desired to do work in the top or bottom 16 bits only one instruction rather than two is needed to set the other bits to an appropriate value. In the preferred embodiment values are extended downwards.

It can be seen for example that instructions to are all .h instructions and that instructions to are all .i instructions which all have the low immediate registry. In the preferred embodiment the nomenclature used after an index is u for unsigned s for signed and h for high extending downwards .

In a further aspect there is provided an instruction for a processor which moves each of a plurality of data elements into a respective one of a plurality of registers the instruction comprising at least one identifier and a plurality of arguments each argument being representative of a respective one of the plurality of data elements the at least one identifier identifying for each argument the type of data of which that argument is representative. Preferably each argument when processed is processed in dependence upon the type of data of which it is representative. Preferably the types of data comprise register data and immediates and each argument comprises one of a register address and an immediate value.

In the preferred embodiment both movm source and pop.ret return value fields can be registers or immediates encoded as a 5 bit field one bit specifies register immediate the remaining four bits specifying either one of R R or an immediate value of 1 1 . . . 15.

XAP4 Preferably 16 bit immediates are provided which allow both 16 bit signed for instance 32768 . . . 32767 and unsigned for instance 0 . . . 65535 value ranges to be encoded in a single immediate. This enables an implementation with smaller hardware and lower power consumption.

Preferably processor instructions sign extend or zero extend immediates to represent full word length. In the preferred embodiment full word length is 16 bits.

Preferably reserved word features used in assembler would not be valid in C. Preferably any reference to a register or registers is prefixed by a percentage. Preferably immediates are prefixed with a hash. Preferably the assembler instructions are case sensitive. Preferably reserved words in assembler are lower case.

These features are implemented in certain embodiments of the invention such as XAP3 and not implemented in other embodiments XAP4 or XAP5 .

Preferably the encoding style for 16 bit instructions follows a 3 3 3 4 3 bit patter with each group of bits representing a register address and or an immediate. Similarly the encoding style for a 32 bit instruction will follow a 16 3 3 3 4 3 pattern. Thus it is apparent that in this preferred embodiment the encoding of 16 and 32 bit instructions is largely the same the only difference being that a 32 bit instruction has the ability to address more memory and or to handle larger immediates.

In a further aspect there is provided an instruction for a processor which executes a single and or multiple similar sub instructions repeatedly.

Preferably the repeatedly executed sub instructions are in the form of copy and or store instructions.

Preferably the instruction is interruptible. More preferably on interrupt a current sub instruction is completed before processing the interrupt routine. The benefits of making such instructions interruptible is that interrupt latency ins reduced. Some instructions are not interruptible so that behaviour is always atomic and deterministic.

XAP3 Preferably some instructions are provided which have a separate prime opcode for each register eg mov.p . This allows coding long immediates in single instructions.

In the preferred embodiment the PC relative instruction is mov.p. Other PC relative instructions include bra.p and bsr.p and all conditional branch instructions.

XAP4 In the preferred embodiment the instruction mnemonics are of the form base.parameters.type.size. All mnemonics include base. Parameters type and size are optional but where they exist they are in the order base.parameters.type.size. Examples of such instruction mnemonics include add.i add.r add.c.r cmp.c.r cmp.8c.r cmp.16xc.r or.i or.h or.r bra.a bra.a.4 bra.a.2 bra.p mov.i mov.r mov.32.r mov.p ld.i ld.8zp ld.r st.8.i stz.r.

In the preferred embodiment the PC relative instructions include mov.p. Other PC relative instructions include ld.p st.p and stz.p bra.p and bsr.p and all conditional branch instructions.

Allows multiply result to be normalised as required for known data range. This allows the input output registers to be the same size 16 bit in XAP4 32 bit in XAP3 .

Normally a register multiply results in a register pair result. This is unwieldy as there are fewer instructions that operate on a register pair than on a single register. For example XAP4 16 16 multiply produces a 32 bit result register pair or XAP3 32 32 multiply produces a 64 bit result register pair .

Frequently the user needs to perform more arithmetic on the multiply result e.g. DSP systems but doesn t need so much resolution Consequently he uses a register pair shift right to normalise the result before performing further arithmetic on it. This is slow and means that 2 registers have been used for Rd when one would have done.

The mult.sh.r instruction solves this problem. The single instruction performs the multiply and shifts right by the specified amount instruction parameter with 1 bit resolution so that the result can be directly stored in a single register. This is fast reduces the number of registers corrupted and increases code density.

It is a very valuable instruction for DSP systems. It means that normalisation can be done with integer arithmetic avoiding the need to move to fractional arithmetic.

XAP3 Processor code may have debug registers with a count conditional to trigger a breakpoint after some numbers of executions of the target instructions. This simplifies debugging of say loops. This is in addition to being able to trigger on address data or a mask value.

As this is part of the core and not an external module it facilitates common debug environment both for development and in field debugging. Especially for debugging user mode code by an operating system.

There may be provided hardware breakpoint registers in the processor core which support software implemented multi stage breakpoint. The breakpoint registers may use in core debug registers and or a debug module within OS and or a textual or graphical interface to specify the breakpoint state.

There is provided a SIF Ethernet pod that allows for remote debugging of applications over the internet.

Preferably the debugging means is integral with the core. Preferably the debugging means is fully contained within the core.

A further aspect provides a debugging means. A yet further aspect provides a debugging means for a processor core.

Preferably the core is adapted to execute a computer program. Preferably the debugging means is adapted to facilitate the debugging of a computer program. For example the debugging means may trigger a predetermined instruction or sequence of instructions upon the occurrence of one or more specified events in the program to be debugged thereby enabling the operation of the computer program to be monitored by a programmer or engineer.

Preferably the debugging means is adapted to enable the execution of a debug processing step. For example execution of the debug processing step may include the execution of one or more instructions subroutines and or computer programs.

Preferably the debugging means includes a breakpoint address register. Preferably the breakpoint register is adapted to reference or to store information relating to the address of a memory location. Preferably the breakpoint register is adapted to reference a memory location external to the processor core.

Preferably the debugging means is adapted to enable the execution of the debug processing step when predetermined processing is performed in relation to the address referenced by the breakpoint address register.

Preferably the predetermined processing includes one or more of the address referenced by the breakpoint address register being accessed a predetermined number of times a predetermined data value or a range of predetermined data values being read from and or written to the address referenced by the breakpoint address register.

Preferably the debugging means is adapted to enable the execution of the debug processing step when the address referenced by the breakpoint address register has been accessed a predetermined number of times.

Preferably the debugging means is adapted to enable the execution of the debug processing step when the address referenced by the breakpoint address register has been accessed a predetermined number of times by a selected access mode. Preferably the access mode is selectable from the following write relating to the writing of data to memory read relating to the reading of data from memory or fetch relating to the reading of an instruction from memory .

Preferably the debugging means comprises a breakpoint control register for storing information relating to the selected access mode.

Preferably the debugging means comprises a count register for storing information relating to the number of times that the address referenced by the breakpoint address register has been accessed.

Preferably the debugging means is adapted to enable the execution of the debug processing step when a predetermined data value or a range of predetermined data values is read from and or written to the address referenced by the breakpoint address register.

Preferably the debug processing steps include one or more of the following generating an exception halting the processor.

Preferably the processor comprises a break enable flag for storing information relating to the selected debug processing step.

Preferably the core comprises a plurality of operating modes. Preferably the operating modes are selectable.

Preferably each of the operating modes has a respective privilege level. For example the core may have one or more of the following operating modes a privileged Supervisor Mode a privileged Interrupt Mode a privileged NMI non maskable interrupt mode and an unprivileged User Mode.

Preferably the debugging means comprises a register that is not accessible by a program operating in an unprivileged operating mode. Preferably the debugging means comprises a register to which data cannot be written by a program operating in an unprivileged operating mode. Preferably the debugging means comprises a register from which data cannot be read by a program operating in an unprivileged operating mode.

A software debugger may be used to debug a program being executed on a processor that does not comprise a hardware debugger or that comprises a hardware debugger without this functionality. In the case of a software debugger the registers and or flags described herein may be implemented in software as variables.

Certain features of the preferred embodiment and of possible alternative embodiments are now described in more detail purely by way of example.

In the preferred embodiment the processor executes a sequence of instructions comprising one or more programs. Such programs require testing inspection and verification during development and testing and correction when the product is in use

The use of multiple processing units in a single system or even a single integrated circuit requires the support of an integrated and uniform debug and verification system to make it feasible to develop reliable and robust software within acceptable timescales.

In many applications of the processor the program is held in memory which is difficult or impossible to change once the product has been assembled.

A means is described in which the processor core itself can stop and examine the state of one or more programs currently executing on the processor. The invention is part of the core of the processor and as such is present in all variations of the processor core. This facilitates a debug infrastructure debug software external debug interface remote debug software communication protocols etc common to all instances of the processor. This reduces development costs through design re use and easily supports the debugging of multi processor designs through a common debug interface shared among the processor cores.

A processor includes a set of registers the processor interface and supporting hardware gates the implementation .

Certain registers known as breakpoint registers can contain information relating to breakpoints. A breakpoint is a point of execution of a program that is characterised by either the address of an instruction in the program or one program of several or the address of a location in memory at which the program may access. Upon encountering a breakpoint execution may stop and control of the processor be taken by other software e.g. operating system debug executive external debugger etc .

These breakpoints may additionally be qualified by either or both of two predicates conditions a count of the number of times the instruction may execute or memory be accessed before causing a break a predetermined data value or one or more ranges of predetermined data values transferred to or from memory external to the processor core.

In the preferred embodiment the processor comprises a debug system supporting eight breakpoints four of which are further qualified with a count predicate and in which two of these count qualified breakpoints are yet further qualified by data predicates.

In the preferred embodiment sixteen breakpoint registers and a breakpoint control register to describe the behaviour of eight breakpoint are provided. The sixteen breakpoint registers are named BRK through BRK BRKCOUNT through BRKCOUNT BRKDATA BRKMASK BRKDATA and BRKMASK. The breakpoint control register is named BRKE. A single bit in the processor s FLAGS register specifies if breakpoints should occur or be ignored.

The breakpoint address registers BRK through BRK respectively describe a 32 bit wide address for each of the eight breakpoints. These addresses can either be the address of an instruction or the address of a unique memory element external to the processor core.

The count registers BRKCOUNT through BRKCOUNT respectively describe a 32 bit wide count predicate corresponding to breakpoints through as specified in the registers BRK through BRK . A break occurs if an address match happens that is the address specified in a breakpoint address register matches the address to from which an instruction or data is to be read written or stored and if the value of the count register corresponding to that breakpoint address register is zero. If an address match occurs but the value of the corresponding count register is not zero the value of the count register is decremented by one and no break occurs. The count register preferably cannot be decremented below zero once it reaches zero it remains at zero until a new value is written to it.

The default value of the count registers is zero such that normal behaviour is the sane as for the first four breakpoints. That is when the value in a count register is zero the corresponding breakpoint behaves like a simple breakpoint.

The BRKDATA and BRKMASK registers further specify a data qualifier on the corresponding breakpoint as specified in register BRK. These registers operate such that a break occurs when a data value read from or written to memory at the location specified in register BRK satisfies the data qualifier. It will be appreciated that the data value can preferably be either an instruction or data. The data qualifier is specified for each of the 32 bits in the data value. For each bit the qualifier is satisfied if either the corresponding bit in the mask register BRKMASK is a 1 and the corresponding bit in the data register BRKDATA matches that is is equal to the corresponding bit in the data value or the corresponding bit in the mask register is 0 .

Thus by setting a bit in the mask register to 1 the occurrence of a break is conditional upon the bit of the data value that corresponds to that bit of the mask register being equal to the corresponding bit of the data register. Alternatively by setting a bit in the mask register to 0 a don t care condition is selected and the occurrence of a break is not conditional upon the value of the corresponding bit of the data value.

The BRKDATA and BRKMASK registers operate similarly to the BRKDATA and BRKMASK registers but in respect of the breakpoint specified in register BRK.

Thus a break can be caused when a predetermined data value is read from and or written to a predetermined location in memory. By setting a plurality of bits of the mask register to 0 a break can be caused when a data value belonging to a set of predetermined data values is read from and or written to memory. For particular values of the mask register the set of predetermined data values can include one or more ranges of consecutive values.

The default value of the mask and data registers is zero such that normal behaviour is the same as for the first six breakpoints. That is when a mask register is set to zero the corresponding breakpoint behaves like a simple breakpoint since all bits of the mask register treated as don t cares and the breakpoint will occur irrespective of the data value being read from and or written to memory.

The breakpoint control register BRKE is a 32 bit wide register. It is split into eight 4 bit wide fields where each field corresponds to one of the eight breakpoints.

Each field has three control bits and one unused bit the fourth bit is left for future debug facilities for example. The three control bits specify whether a breakpoint should occur if an instruction writes to the address matching the corresponding breakpoint address if an instruction reads from the address matching the corresponding breakpoint address if an instruction has been fetched for execution from the address matching the corresponding breakpoint address.

Finally there is a breakpoint enable bit in the FLAGS register. If this bit is set and the processor is in the lowest privileged execution mode then breakpoints will cause an exception to occur to allow the debug software to take control of the processor and monitor and or modify the state of the program or programs. Thus by setting the breakpoint enable bit an exception is generated rather than halting the processor.

XAP4 Preferably the predetermined processing includes one or more of the address referenced by the breakpoint address register being accessed a predetermined number of times a predetermined data value or a range of predetermined data values being read from and or written to the address referenced by the breakpoint address register enable bits for breaks to occur when the specified address is the instruction and or a data read and or a data write.

These breakpoints may additionally be qualified by either or both of two predicates conditions a count of the number of times the instruction may execute or memory be accessed before causing a break a predetermined data value or one or more ranges of predetermined data values transferred to or from memory external to the processor core.

In the preferred embodiment eight breakpoint registers and a breakpoint control register to describe the behaviour of four breakpoints are provided. The eight breakpoint registers are named BRK through BRK BRKCOUNT through BRKCOUNT BRKDATA and BRKMASK. The breakpoint control register is named BRKE. A single bit in the processor s FLAGS register specifies if breakpoints should occur or be ignored.

The breakpoint address registers BRK through BRK respectively describe a 16 bit wide address for each of the four breakpoints. These addresses can either be the address of an instruction or the address of a unique memory element external to the processor core.

The count registers BRKCOUNT through BRKCOUNT respectively describe a 16 bit wide count predicate corresponding to breakpoints through as specified in the registers BRK through BRK . A break occurs if an address match happens that is the address specified in a breakpoint address register matches the address to from which an instruction or data is to be read written or stored and if the value of the count register corresponding to that breakpoint address register is zero. If an address match occurs but the value of the corresponding count register is not zero the value of the count register is decremented by one and no break occurs. The count register preferably cannot be decremented below zero once it reaches zero it remains at zero until a new value is written to it.

The BRKDATA and BRKMASK registers further specify a data qualifier on the corresponding breakpoint as specified in register BRK. These registers operate such that a break occurs when a data value read from or written to memory at the location specified in register BRK satisfies the data qualifier. It will be appreciated that the data value can preferably be either an instruction or data. The data qualifier is specified for each of the 16 bits in the data value. For each bit the qualifier is satisfied if either the corresponding bit in the mask register BRKMASK is a 1 and the corresponding bit in the data register BRKDATA matches that is is equal to the corresponding bit in the data value or the corresponding bit in the mask register is 0 .

The BRKDATA and BRKMASK registers operate similarly to the BRKDATA and BRKMASK registers but in respect of the breakpoint specified in register BRK.

The breakpoint control register BRKE is a 16 bit wide register. It is split into four 4 bit wide fields where each field corresponds to one of the four breakpoints.

Each field has three control bits and one unused bit the fourth bit is left for future debug facilities for example. The three control bits specify whether a breakpoint should occur if an instruction writes to the address matching the corresponding breakpoint address if an instruction reads from the address matching the corresponding breakpoint address if an instruction has been fetched for execution from the address matching the corresponding breakpoint address.

In summary the invention relates to at least some of the following aspects which may be combined with one another in any appropriate combination Processor Features for High Code Density in particular features for efficient function entry and exit variable length instructions unaligned registers immediates block store instructions mov.p and mov.g instructions as well as the mult.sh.r instruction and breakpoint features.

Generally herein the invention extends to methods and or apparatus substantially as herein described with reference to the accompanying drawings.

Any feature in one aspect of the invention may be applied to other aspects of the invention in any appropriate combination. In particular method aspects may be applied to apparatus aspects and vice versa.

The invention also provides a computer program and a computer program product for carrying out any of the methods described herein and or for embodying any of the apparatus features described herein and a computer readable medium having stored thereon a program for carrying out any of the methods described herein and or for embodying any of the apparatus features described herein.

The invention also provides a signal embodying a computer program for carrying out any of the methods described herein and or for embodying any of the apparatus features described herein a method of transmitting such a signal and a computer product having an operating system which supports a computer program for carrying out any of the methods described herein and or for embodying any of the apparatus features described herein.

Furthermore features implemented in hardware may generally be implemented in software and vice versa Any reference to software and hardware features herein should be construed accordingly.

It will be understood that the present invention is described below purely by way of example and modification of detail can be made within the scope of the invention.

Each feature disclosed in the description and where appropriate the drawings may be provided independently or in any appropriate combination.

There are three main embodiments to the present invention each will be described separately herein. The three embodiments will be known respectively as 

The first section provides a generic description of the first embodiment the SIF network debug interface. This is independent of any particular implementation of SIF. It describes the way SIF is used for a whole network and the details of how it is used in a SIF Computer a SIF Pod and in a SIF Chip and the interfaces between them. Inside the chip it describes the xSIF external serial interface and the iSIF internal parallel interface . It describes how a single SIF module in a chip supports multiple processors in that chip.

The second section provides a description of the second embodiment the XAP3 32 bit processor. It contains sections on the XAP3 Programmer s Model and the specific implementation of SIF used in a chip containing XAP3. The programmer s model instruction set and compile chain for the XAP3 have been developed together to give very high code density. The XAP3 has 16 32 bit registers. The XAP3 processor supports up to 4 GB of memory. The XAP3 compile chain is GCC or NCC compilers and binutils assembler and linker .

The final section of the description provides a description of the third embodiment the XAP4 16 bit processor. It contains sections on the XAP4 Programmer s Model and the specific implementation of SIF used in a chip containing XAP4. The programmer s model instruction set and compile chain for the XAP4 have been developed together to give very high code density. The XAP4 has 8 16 bit registers. The XAP4 processor supports up to 64 kB of memory. The XAP4 compile chain is GCC compiler and binutils assembler and linker . Various aspects of XAP4 have been designed to ease the port of GCC to this small processor.

In addition reference is made to UK Patent Application Numbers 2382889 and 2294137 B whose content is herein incorporated by reference.

SIF is a non invasive real time synchronous interface. SIF is used to debug and test ASICs ASSP SoC or FPGA.

The SIF Slave is typically an ASIC or FPGA or Integrated Circuit IC or chip. Each chip contains one SIF module which can communicate to one or more processors on the chip. The SIF module contains an xSIF interface external serial and an iSIF interface internal parallel . The following sections sometimes refer simply to the SIF interface in the Slave. This normally refers to the xSIF serial interlace. However the functions supported by the xSIF and iSIF interfaces are identical memory read write register read write debug control instructions . . . .

xSIF was developed first iSIF was added later. The addition of iSIF functionality to xSIF has added very little hardware silicon gates because all the instruction decodes are identical for xSIF and iSIF. The difference is that xSIF instructions are loaded serially whereas iSIF instructions are loaded in parallel as described in further detail herein.

The SIF Master is typically a PC Silicon Tester or Microprocessor. The SIF Master can read or write any memory mapped address inside the SIF Slave in real time without affecting the timing or functionality of the SIF Slave. This enables the SIF Master to setup and configure the SIF Slave and to do data acquisition from it. The SIF Master can also develop and debug embedded software for the SIF Slave debug functions include start stop run to breakpoint etc .

The standard SIF Slave interface has 4 pins SIF CLK SIF MOSI SIF MISO SIF LOADB. The first 3 pins are unidirectional signals to a shift register which can be of different lengths for different circuits . SIF LOADB is a bi directional pin for hand shaking. This interface will support a single master single slave network. The addition of a 5pin SIF CS to the SIF Slave enables single master multi slave networks. The addition of the SIF REQ SIF ACK pins to the SIF Master enables multi master multi slave networks.

The following sections describe typical ways in which the SIF is used throughout the life of an ASIC or FPGA. The FPGA could be the final product or an emulator for an ASIC before tape out

SIF Slave ASICs normally contain one or more microprocessors e.g. XAP1 XAP2 XAP3 or other . The SIF provides a debug interface for code development on these microprocessors and is used for functions such as 

The hardware in an ASIC can often be configured by software to have alternative functional behaviours. The configuration is set by writing the required values to specific addresses. This can be done by the on chip processor or by an external SIF Master using the SIF interface.

It is often useful to transfer data generated in an ASIC to a computer for detailed analysis. For example it is useful to analyse an ADC output stream in Matlab. The SIF enables such data acquisition to be done at high speed 600 k 32 bit words s with USB SIF Pod .

SIF is often used by an ASIC tester e.g. Teradyne Catalyst in production test. This is especially useful for the analogue sections of an ASIC. The SIF can be used to configure the ASIC as required for a particular test and then to read back the results. SIF can co exist and share 3 pins with JTAG and ScanPath test interfaces.

Support costs for a manufacturing company can be high when a product is out in the field large volumes spread all over the world . If users have a problem with their product the support costs are reduced if they can run software that provides good diagnostic information. Such computer software can access large regions of the ASIC while it is running in normal functional mode via the SIF. The acquired data can then be sent back to the product manufacturer to help them solve the problem.

The purpose of the SIF is to let a SIF Master read or write data to one or more SIF Slaves. The reads and writes are always initiated by the SIF Master. The SIF Slave never initiates any reads or writes it is only responsive. The data rates are determined by the SIF Master and can be faster or slower than the system clock used inside the SIF Slave.

The clever circuitry is in the SIF Slave. It is always implemented in hardware. It allows a SIF Master to read or write any address mapped variable normally a register or memory . The SIF Master is normally a computer which accesses the SIF Slave via a SIF Pod. The SIF Master functionality can be implemented in hardware or software.

Old SIF Pods ISA LPT do not have any intelligence. The pods are like combinational circuitry. There is no checking for data integrity between the computer and pod.

New SIF Pods Universal Ethernet USB2 RS232 do have intelligence contain a processor and FPGA . They support the new SIF Pod Protocol. This maintains data integrity between the computer and pod by sending packets with CRC codes.

The 16 IDC SIF interface used between a SIF Pod and a PCB or PCBs containing 1 to 4 SIF Slaves. The interface contains 3 power 4 SIF and 9 IO pins. This enables the pod master to read and write up to 4 slaves in Normal or Command mode. See .

Pin is SIF VDD. This allows the Pod to either supply power to the Slave PCB or to sense the voltage being used on it.

Computer drivers have been developed for the SIF. These support a number of operating systems and pods. The API Application Programmer s Interface for these drivers are 

It is possible to manufacture a number of SIF hardware pods. These are used to connect computers normally PCs to SIF slaves. The connection from the pod to the PCB containing 1 to 4 SIF slaves is always a 16 IDC ribbon and connectors . There are a variety of standard interfaces from the computer to the pod. SIF Toolkits contain drivers to support all these pods under a variety of computer operating systems.

They implement the connection firm xSIF API to the relevant communications socket Ethernet USB RS232 LPT .

SIF Toolkit 4. integrates the above functionality into a single tool called SIF Explorer. It also adds the following extra functionality 

xIDE is an Integrated Development Environment developed by Cambridge Consultants. It is implemented in C and Qt. It consists of a standard kernel and custom plugins for particular processors or complete ASICs.

xIDE is used as the IDE for the XAP1 XAP2 and XAP3 ASIC processors. They all include software simulators. They also include SIF interfaces via pods to hardware emulators normally based on xEMU . These xIDE toolkits are major applications that use the SIF and xSIF APIs to the SIF drivers in Windows x86 Linux and MacOSX computers.

Matlab is a powerful tool for controlling hardware tests in the lab. It is very popular with physicists. It is very useful for data acquisition and analysis. As such xSIF provides a full Matlab API to SIF pods and slaves.

The termination strategy is to have 100 ohm series source termination at each driver output as shown in the diagram above. This is to match the standard impedance of the ribbon cable which is 100 ohm .

This works well for point to point connections i.e. a single Slave as shown in . Any wave reflections from the destination should be perfectly absorbed in the 100 ohm series resistor at the source thereby preventing multiple reflections .

However it does not work so well when there are multiple Slaves in the Slave PCB i.e. 2 to 4 . The reflections will be seen by the intermediate Slaves which could cause errors. One way to deal with this is to use slower edge speeds and shift frequencies. Another is to add buffers to the Slave PCB so that the cable does only see point to point loads. This second method is recommended and shown in section 8 on SIF Slave PCBs.

In practice the SIF Pod has ESD High voltage protection on every signal anyway see description on SIF Master . This includes a 100 series resistor. So in fact this resistor can double up as protection and source series termination for the Pod outputs. Actually the Pod contains protection circuitry for the Inputs SIF MISO SIF ACK Bidirectionals SIF LOADB STOPB as well. This is not ideal but does not do much harm as the gate inputs are such high impedance anyway .

It is necessary for the Slave PCB to have 100 ohm source series termination close to the SIF MISO and SIF ACK pins on each SIF Slave. It is best if the Slaves are positioned as close as possible to the 16 IDC SIF connector on the Slave PCB.

The SIF Slave protocol describes the way a SIF Master e.g. a Pod must control the SIF signals SIF CS SIF CLK SIF MOSI SIF MISO SIF LOADB in order to read from and write to a SIF Slave ASIC or FPGA .

A SIF Slave is either in Normal or Command mode. At reset it is in Normal mode. Most of the time the SIF Slave is used in Normal mode.

If the SIF Slave will never be used in multi slave networks then it only needs to have 4 external SIF pins. In such cases SIF CS should be tied high 1 inside the slave.

To access a SIF Slave SIF CS should be 1 for Normal and Command Modes . However SIF CS only affects the SIF LOADB and SIF MISO pins in a SIF Slave.

SIF CS does not affect the 2 input pins to the shift register SIF CLK SIF MOSI . Data is always fed into the shift register even if SIF CS 0.

When SIF CS 0 the internal copy of SIF LOADB is forced to 1 meaning that it is not possible to do a SIF Read or Write .

Normal mode uses all 5 SIF pins and supports variable length shift registers from one ASIC design to another .

In effect Command mode only uses 4 SIF Pins SIF LOADB not used . When in Command mode the shift register is treated as fixed length across all designs . 8 bit Commands are fed into SIF MOSI and 8 bit Responses are generated from SIF MISO.

The limits on these times vary from one SIF Pod to another. SIF Pods must obey these limits when performing the various SIF Operations described in the rest of this section.

Pipelined SIF Read performs n SIF Reads by iterating the following cycle n times this may be seen in 

Pipelined SIF Write performs n SIF Writes by iterating the following cycle n times this may also be seen in 

SIF Instructions are always initiated by the SIF Master. The SIF Slave only ever responds. This can still be used for data acquisition tasks by using the Status field as a timestamp e.g a counter where the LSB toggles at 1 to 100 kHz . The SIF Master can then reconstruct the acquired data discarding duplicate samples and spotting if there are any missing samples.

For very fast data acquisition it can be simpler if the SIF Slave initiates the SIF transaction. The way to do this is as follows 

This feature is application specific. Not all SIF Slaves will contain such a FIFO. SIF Slaves which do contain such a FIFO can hold SIF LOADB for longer when the SIF Master makes a SIF Read to the FIFO. However SIF reads to any other address will behave as normal without any stretching of SIF LOADB .

If the SIF Master issues a SIF Instruction to a selected SIF Processor inside the Slave that cannot be completed then the SIF Slave will continue to hold SIF LOADB low for ever. This can happen for a variety of reasons including 

The SIF Master must be able to detect that SIF LOADB is stuck low and timeout after a specified period. The SIF is then locked and needs to be cleared by issuing a SIF Cancel instruction. This can be done using one of the following 2 methods.

When the SIF Master issues a SIF Cancel to the SIF Slave it cannot be certain whether the previous SIF Instruction read or write will be executed or not. The Slave might execute the SIF Instruction in the period between the Master transmitting the start of the SIF Cancel and the Slave receiving the end of the SIF Cancel. However the Master can assume that if the SIF Instruction is executed that it will be exactly as requested. The Master doesn t know whether the read or write has occurred but it does know that if it did occur then it was executed correctly. The Slave will never execute any unrequested SIF Instructions reads or writes during SIF Cancel or any other period .

If the SIF Master pulls SIF CS low sampled by Slave system clock the SIF Slave will no longer be selected. The SIF Slave will stop pulling SIF LOADB low allowing the signal to go high again. It does not matter what the values are on SIF CLK SIF MOSI or SIF LOADB. A SIF Slave cannot hold SIF LOADB low if its SIF CS pin is low. Some SIF Slaves do not use the SIF CS pin i.e. can only be used in Single Slave networks . In such devices the SIF CS signal is permanently tied high inside the chip. Therefore the method for clearing a locked SIF cannot be used in all SIF Slaves.

This feature is only implemented in SIF Slaves from 2005 onwards. It is implemented in the CVS Verilog repository for sif and xsif. It is implemented in XAP2 and XAP3. It is not implemented in XAP1.

If the SIF Master issues 32 cycles high then low on SIF CLK then on the 32negedge the SIF Slave will stop pulling SIF LOADB low allowing the signal to go high again.

It does not matter what the values are on SIF CS SIF MOSI or SIF LOADB during this sequence. All SIF Slaves on the network will release SIF LOADB after the 32negedge on SIF CLK Of course this does not cause any change of state in SIF Slaves that were not holding SIF LOADB low.

The reason this protocol works is because there should not be any cycles on SIF CLK when SIF LOADB is low. In fact SIF CLK should always be low when SIF LOADB is low.

This feature is implemented in SIF devices from 1999 onwards. It is implemented in the CVS Verilog repository for sif and xsif. It is implemented in XAP2 and XAP3. It is not implemented in XAP1.

The maximum frequency for SIF CLK in Command mode is 1 MHz. This includes the 256 clock sequence to transfer from Normal to SIF Mode.

At reset the SIF Slave is in Normal mode. To use SIF Commands the SIF Slave must first be put into Command mode. This is done by raising the SIF Command Mode Counter value to 256 which is done as follows and may be seen in FIG. 

Note that the SIF Slave only has Tclklow 2half of SIF CLK cycle from entering Command mode negedge SIF CLK to putting Response 7 on SIF MISO posedge SIF CLK . With a 1 MHz SIF CLK this is 500 ns and could be as low as 400 ns with a 40 60 duty cycle on SIF CLK. This is the why the fastest frequency for Command mode is only 1 MHz.

The SIF Command Mode Counter goes back to 0 thus putting the SIF back into Normal Mode when any of the following occur 

SIF Commands and Responses are always 8 bit. The Command is fed into the SIF Slave on SIF MOSI while the Response from the previous Command is simultaneously fed out on SIF MISO. While the first Command is fed into SIF MOSI 0x5A is output on SIF MISO. This confirms to the Master that the Slave has successfully entered Command mode.

All of the SIF Commands defined so far are Get functions. They all query the SIF configuration and in effect read a fixed ROM inside the SIF. They do not update the SIF Slave in any way. In future there may be some simple Set functions for general IO lines inside the SIF. SIF Commands cannot be used to read or write any processor or memory address space in the SIF Slave. That can only be done by Normal mode SIF Instructions.

There will not be any data corruption between Computer and Pod because the SIF Pod Protocol includes a CRC check on each packet. This is used for all SIF Pods apart from the LPT Pod. In addition Ethernet and USB protocols contain their own error correction protocols by error checking and re send to guarantee data transfer without corruption.

There could be data corruption between Computer and the LPT Pod because it does not implement the SIF Pod Protocol and therefore does not contain any error correction protocol.

Older devices such as XAP2 and XAP1 do not provide any error checking. In such devices there could be data corruption on the serial link between the SIF Pod Master and Slave using SIF CLK SIF MOSI SIF MISO over the 16 IDC ribbon interface .

It is safe to assume that the parallel loads inside the Slave between the SIF shift register and the memory bus will function correctly. This part of the Slave circuit will be correct by design. t will not change from one installation or Pod to another.

This means that if data integrity is maintained over the 16 IDC ribbon serial link then there will not be any read or write errors between the Pod and Slave. This data integrity may vary through time. For example interference from switching motors or relays could cause data errors.

SIF does not include any error reaction between the Pod and Slave. However the parity checking does mean that single bit corrupted SIF Instructions do not get executed. Such events are reported back to the Master by the error bits in the Status field

A variety of error detection methods are used by SIF. Some are automatically implemented in the xSIF drivers parity checking and diagnostics . Others must be implemented at the software application level e.g. CRC or checksum across large packets .

XAP3 SIF devices include parity checking between the Master and Slave. This will expose single bit stuck at 0 and stuck at 1 faults on 

The Slave will not execute a SIF Instruction if it finds a parity error in PARITY AC on the Address and Control fields . It will report this and other errors in the Status field returned to the Master. This means that single bit corrupted SIF Reads will not be executed. Corrupted SIF Writes will be executed if the error is in the Data field which is parity protected as an output but not as an input . However the Master will check the PARITY D bit in the Status field which will indicate that the data was corrupted. This tells the Master about the corrupt SIF Write after the event has taken place. The Master must then take corrective action.

The Master will always check the PARITY D on Data field and PARITY S on Status field bits in the Status field. This will tell the Master if the data transferred from the Slave has been corrupted exposing all single bit errors .

SIF computer applications can and should run diagnostics checks on the integrity of the serial links from Pod to Slave and back to Pod. This is possible because the SIF Slave shift register is continuous from the SIF MOSI input to the SIF MISO output like JTAG but unlike SPI and IC . This means it is possible to check that the data sent from Computer to Slave via Pod is the same as that received back from Slave to Computer. This is best if SIF LOADB remains high i.e. no read or write is performed . The SIF CLK frequency can be increased until this test fails. This reveals the maximum frequency that the serial link can safely be run at.

Such checks can be done by the application software. They are also done automatically by the xSIF drivers when the appropriate diagnostics level is selected.

The Computer can run data integrity checks on some or all affects speed of the data during SIF reads and writes. These checks are in addition to the parity checks that always operate in the XAP3 SIF. The data integrity checks are performed by the driver when diagnostics is turned on level 1 default case for all software applications . Thus the application software can continuously monitor the quality of the serial link between Pod and Slave during SIF operation. This is helpful in exposing hardware problems between the Pod and Slave. SIF Diagnostics can be set to different levels 

The SIF system as seen from the controlling computer will tell the user when anything is broken and make suggestions as to what it might be.

The SIF Slave does not perform any error correction as this is too big an overhead. However the SIF Pod and drivers do run automatic parity checks in XAP3 SIF and diagnostic checks in all SIF devices when the Diagnostics level is set appropriately .

The SIF Pod does perform error correction on the link to the computer by using the CRC in each packet of the SIF Pod Protocol.

The following sections show the 3 kinds of network you can have from a single SIF Pod. Even bigger networks can be built by using multiple SIF Pods. This is particularly powerful with Ethernet SIF Pods which can be physically located a long distance from the controlling computer. By using an Internet link the computer can even control SIF Slaves in remote countries.

After the 3 network types there are descriptions of the control and timing that must exist between the Master and its Slaves.

Without SIF CS one can only have 1 SIF Master and 1 SIF Slave. This means that it is only possible to have one SIF Slave per SIF Pod see .

If the SIF Slave ASICs have a SIF CS input you can have a network with 1 SIF Master e.g. SIF Pod and multiple SIF Slaves see . The Master controls the SIF CS inputs to each SIF Slave. SIF MISO from each Slave is tristated when the associated SIF CS input is low. SIF MISO is enabled when SIF CS is high. Thus the Master should never pull more than one SIF CS line high at a time or there will be contention on the SIF MISO line .

It does not affect SIF CLK or SIF MOSI in any way. It is still possible to clock new data into the SIF Shift Register even if SIF CS is low. However SIF MISO will be tristated so this output will be high impedance even if the SIF Shift Register is clocked.

If SIF CS is low the Slave will ignore SIF LOADB when it is pulled low by the Master. The Slave will not latch SIF LOADB low and will not queue up a SIF Transfer for the next SIF cycle.

This configuration is not often used. It is useful when the end product contains a microprocessor and a SIF Slave ASIC see . In this situation the SIF Master can be the microprocessor or the SIF Pod. It allows the SIF Pod to negotiate with the microprocessor to decide who should have control of the SIF thus enabling communication with the SIF Slaves . This is done with 2 signals 

If there is more than one SIF Master on the SIF Slave PCB then they should be daisy chained using extra SIF REQ and SIF ACK signals as shown in the diagram above.

The delay times are estimated and will vary from system to system. This shows the best time for the Master to sample SIF MISO in red.

The Master and Slave can be thought of as one continuous shift register. However it is not symmetrical as SIF CLK is generated in the Master. Shift registers go wrong if the clock to a downstream bit is late. They do not go wrong if the clock to a downstream bit is early. This is why it is safe to sample SIF MISO in the Master almost on posedge SIF CLK. It would not be safe to sample SIF MOSI in the Slave on posedge SIF CLK which is why it is actually sampled on negedge SIF CLK. So the summary operation of the Master and Slave shift Registers are 

SIF LOADB is the bidirectional handshaking signal between the SIF Master and the SIF Slaves see . The SIF LOADB pins in Master and Slaves are open drain bidirectionals with pullup resistors. In addition there is a pullup resistor normally 10 k ohm on the wire between the Master and Slaves. SIF LOADB can be pulled low by the SIF Master or any SIF Slave.

SIF LOADB is active low. It is high when the SIF is not being used or when the SIF Master is shifting data to and from the SIF Slave. When SIF LOADB is high the Master can shift data through the Slave s shift register as much as it likes taking care not to invoke Command mode . Nothing will happen in the SIF Slave until the SIF Master pulls SIF LOADB low.

If the SIF Master continues to pull SIF LOADB low after the SIF Slave has let go the SIF Slave will not perform any further SIF Instructions. The SIF Slave cannot perform another SIF Instruction until it sees SIF LOADB go high and then low again.

It was mentioned earlier that the circuitry required in the Pod is a compromise between the ESD high voltage requirements and the termination requirements. The above scheme shows how the 13 signal pins are protected by a 100 ohm resistor diodes to SIF VDD and GND and a polyswitch fuse. Component numbers and values are given in section 9 on the SIF Master.

The Slave PCB is shown with buffers for all signals. These are recommended for FTB Functional Test Board and ATB Analogue Test Board . They are not mandatory for production boards. The benefit of the buffers is 

The preferred buffers are NC7NZ17 in the US8 package. This is Fairchild TinyLogic. Each Spin pack contains 3 non inverting buffers. They can deliver 24 mA and have a propagation time of 3.6 ns typical into a 50 pF load. They are rated for operation over 40 to 85 deg C. There may be some cases where an ATB needs to use a different buffer if the environmental test chamber needs to go above 85 deg C. sometimes we need 125 deg C. . These devices are very fast and therefore must have good decoupling capacitors between SIF VDD and GND e.g 100 nF 0603 X7R . Without this there will be interference on SIF VDD when the buffers switch.

A 4k7 pulldown resistor is shown at the input to the SIF MISO buffer. This is needed if the SIF Slave ASIC has a SIF CS input pin which tri states the SIF MISO ASIC output. The resistor prevents the buffer input from floating to mid rail.

SIF slaves can operate in Normal or Command mode. All SIFs support Normal mode. The only design to support Command mode as of January 2005 is the XAP3.

The shift register length for Command mode is always 8 bits. Command mode operates identically across all SIF slaves. It enables the SIF Master to discover the SIF configuration details of the SIF slaves in Normal mode e.g shift register field lengths .

A SIF Slave should only ever contain 1 SIF interface. However this can support several processors as shown in . These processors can be of different types. The default SIF supplied with the XAP3 supports up to 8 on chip SIF Processors.

Most ASIC packages have pins identified by a single number QFP QFN PLCC TSOP SOIC DIL etc . The SIF signals should be allocated to package pins in the following order 

Similarly the SIF pads should all be contiguous and in this order on the silicon die. The pin and pad numbers are expected to increase in an anti clockwise direction when looking down on the package or silicon die.

BGA packages have pins in a 2D grid of rows and columns. Consequently they use pin names of the form B. The SIF Pads should be allocated to the BGA pins in a sensible manner given the above constraint on pad positions on the silicon die.

Separate JTAG controller logic should be included inside the ASIC. This will use the clock edges as defined above which is the opposite from normal SIF operation 

Most JTAG interfaces use a 14 IDC or 20 IDC connector. This often contains TCK RET. This is a returned clock from the Slave to the Master. TCK is synchronised with the Slave system clock. The Master operates a hand shaking system called Adaptive Clocking where it won t generate posedge TCK until it receives negedge TCK RET. Similarly the Master won t generate negedge TCK until it receives posedge TCK RET. This enables the Slave to slow down the Master which is sometimes necessary if the Slave is in a slow low power mode. However it does reduce the maximum shift rate for the JTAG interface.

None of this is necessary in SIF because the SIF shift register is completely asynchronous from the Slave s system clock. The handshaking between Master and Slave is handled by the SIF LOADB signal. This means that even when the Slave is in a slow low power mode the Master can still use the fastest shift rates to communicate with the Slave.

The SIF shift register consists of 4 fields. The length of these fields can each be from 0 to 32 bits. This is a property of the slave design remains fixed. The Computer and SIF Master must know the lengths of these 4 fields in order to communicate with the SIF Slave. This is either known by manual configuration or on newer designs by auto discovery using SIF Commands.

For all 4 fields data is shifted in and out MSB first. The order of the 4 shift register fields in the SIF Slave from input to output must always be 

The Address field is an output from the SIF Master and an input to the SIF Slave. Address steps are in the same units as those used by the selected SIF Processor in the SIF slave. e.g. 

The Control field is an output from the SIF Master and an input to the SIF Slave. It can include several different signals which from LSB to MSB must be in the following order 

The length of the Control field is defined to include the PARITY AC and WRITE bits. Many functions in the xSIF API pass a Control argument. Such Control arguments should 

The memory or register that the data is written to or read from depends on the Address and Control fields used for the SIF Instruction.

The Shift Register Data field should only be updated for valid SIF Reads. It should not be updated for SIF Writes or any SIF Error.

The Status field is always an output from the SIF Slave and an input to the SIF Master regardless of whether it is a SIF read or a write . The Shift Register Status field is updated after all completed i.e complete SIF LOADB handshake SIF Instructions valid or error .

The value of the Status field is independent of the Address and Control fields. It is normally updated with an internal hardware register STAT and error information on the success of the SIF Instruction.

The SIF Slave hardware module Verilog has an input bus for STAT that feeds into the Status field. The hardware designer can decide what information should be connected to this bus. Examples include 

The Status field is an output from the SIF Slave and an input to the SIF Master. It can include several different signals which from LSB to MSB must be in the following order 

PARITY D and PARITY S are set by the SIF Slave and checked by the SIF Master. PARITY D should be set first. PARITY S is set afterwards and covers the whole Status field i.e includes PARITY D .

The XAP1 XAP2 and XAP3 processors all include a SIF interface. The APE1 and APE2 processing engines normally contain a SIF interface. The standard lengths for these SIF implementations are 

The SIF Slave implementation below is for a XAP3. Of course it can be scaled to have different field lengths Address Control Data Status for other SIF Slave devices.

The handshake SIF LOADB pulse phase is only clocked by CLK. Negedge SIF LOADB is detected synchronously with CLK. Thus SIF LOADB SLAVE is clocked by CLK.

After negedge SIF LOADB has been detected the Address Control and Data shift registers are copied to the Address Control and Data Write capture registers which are clocked by CLK . This means that the shift register can be clocked by SIF CLK afterwards e.g for a SIF Cancel without corrupting the Address Control and Data Write fields used for the SIF Instruction in case it is executed before the SIF Cancel has completed .

The Address and Control fields are clocked on negedge SIF CLK. They always operate as a shift register.

The Data and Status fields and MISO REG flipflop are clocked on posedge SIF CLK. They normally operate as a shift register. However they sometimes do a parallel load from the Data Read and Status Capture registers. These occur on the first posedge SIF CLK after posedge SIF LOADB see FIG. 

When a parallel load happens the Capture register bits are shifted up by one bit when fed into the Data and Status fields. This means that there is never a parallel load into DATA 0 . DATA 0 always acts as a shift register taking its input from CONTROL MSB .

This section contains several diagrams that show the extra components that should be placed on the SIF Slave PCB for the most common configurations of SIF Slave ASICs. These use the 4 main SIF signals SIF LOADB SIF CLK SIF MOSI SIF MISO and one or more SIF CS signals. The components are for buffering and termination. shows the components needed in a Slave PCB if all 13 SIF signals are used which is unusual .

All of these extra components should be placed right next to the 16 IDC connector on the SIF Slave PCB. The SIF Slave ASICs should also be placed as close as possible to the connector. All of the buffers should be powered by the SIF VDD and GND signals in the 16 IDC interface and should have 100 nF de coupling capacitors.

The general strategy is that production boards should minimise the number of components fitted. This can be restricted to a few 0603 resistors. This minimises cost but does not provide as much drive strength or protection as a board that contains buffers. It therefore may have to be used at lower shift speeds and because there is less protection should be used with short cables.

Functional Test boards FTB and Analogue Test Boards ATB are made in lower volumes and can afford to have more components in order to provide 

The preferred buffers are NC7NZ17 in the US8 package. This is Fairchild TinyLogic. Each 8 pin pack contains 3 non inverting buffers. They can deliver 24 mA and have a propagation time of 3.6 ns typical into a 50 pF load. They are rated for operation over 40 to 85 deg C. There may be some cases where an ATB needs to use a different buffer if the environmental test chamber needs to go above 85 deg C. sometimes we need 125 deg C. . These devices are very fast and therefore must have good de coupling capacitors between SIF VDD and GND e.g. 100 nF 0603 X7R . Without this there will be interference on SIF VDD when the buffers switch.

In multi slave systems the buffers are connected in parallel to maintain simple point to point links. This reduces reflections and enables faster shift speeds to be used.

The most important signal is SIF CLK. It is important that there are no oscillations which might cause multiple clock edges at the SIF Slave inputs.

The SIF CS pin is not essential for a single slave system and may not be included in the SIF Slave ASIC see .

This board should be used with a short ribbon cable. If you need the board to work with a long cable it would be sensible to add a buffer and pulldown resistor to the SIF MISO signal as shown in of a single slave board .

The addition of buffers makes this board faster and more immune to interference than the previous low cost Production board for a Single Slave SIF system.

The SIF CS pin is not essential for a single slave system and may not be included in the SIF Slave ASIC. If it is not included then the above components can be omitted 

This board should be used with a short ribbon cable. If you need the board to work with a long cable it would be sensible to add a buffer and pulldown resistor to the SIF MISO signal as shown in a multi slave board .

It may need to be used with a modified SIF Pod that generates signals with slow edges so as to avoid reflections. This is especially important on SIF CLK.

The above scheme can be used for Functional FTB or Analogue ATB Test Boards. Of course a similar scheme can be used for a board containing 2 or 3 SIF Slave ASICs.

The addition of buffers makes this board faster and more immune to interface than the previous low cost Production board for a Multi Slave SIF system.

The scheme shown in can be used for Functional FTB or Analogue ATB Test Boards. It can be used with high speeds and a long ribbon cable to the SIF Pod. Of course a similar scheme can be used for a board containing 2 or 3 SIF Slave ASICs.

The buffers come in packs of 3. Multiple buffers are needed for the SIF CLK and SIF MOSI signals. Where possible all 3 buffers in a pack should be used for the same signal.

The most commonly used SIF Master is a SIF Pod. Separate microprocessors or ASIC test machines can also be SIF Masters. The implementation example given here is for a SIF Pod.

A SIF Pod can be implemented in many different ways. The most common way in modern pods is to use see FIG. 

A trade off can be made between the microprocessor and FPGA as to which should implement the various parts of the SIF Slave Protocol 

All the flipflops in this design are clocked on posedge of the same system clock called CLK. This is likely to be a fast continuous clock e.g. 50 MHz . The logic is controlled with enable signals. SIF CLK is not used as a clock inside the Pod FPGA. It is a generated signal from posedge CLK see .

The above FPGA design is a simple one which relies on the external microprocessor to do the control for multi cycle functions such as xsif read array or xsif contread star . It contains 

The MOSI and MISO shift registers could be 64 bit. This would be a bit faster enabling longer shifts before having to do a parallel load.

STOPB and RUN STEP are debug control signals used for the XAP1 Processor. They are not used for any other processors see . These signals control 

In the XAP2 and XAP3 ASICs these functions are implemented as SIF Instructions which is why they do not have STOPB or RUN STEP pins.

The LPT SIF Pod does not implement any circuitry for STOPB or RUN STEP. Pins and in the 16 IDC Interface are left unconnected.

The modern Pods USB Ethernet Universal all implement the STOPB and RUN STEP functionality in the FPGA. This is implemented as hardware circuitry the same as in the ISA SIF Pod 98. This is interfaced to the memory bus with the following control signals 

The recommended circuitry for ESD and high voltage protection to the 16 IDC interface in a SIF Pod is as follows 

The 100 ohm series resistors in this protection scheme are also useful for source series termination 9 of the 13 ins are outputs from the Pod see . Termination and the SIF Slave PCB are further described herein.

The power supply voltage SIF VDD on Pin used for the 16 IDC interface signals should be the same in the SIF Pod and in the SIF Slave PCB. This voltage can be 

In the latter case the Pod voltage is controlled from the Computer. The most common output voltages used in SIF Pods and available in Xilinx Virtex2 FPGAs are 

Previous SIF systems have only provided an external serial physical interface to the SIF Slave. This interface was called SIF but will now be called xSIF external SIF . A new development to SIF technology is to provide a second physical interface to the SIF Slave called iSIF. iSIF is an internal parallel interface 

XAP systems should offer the iSIF and xSIF hardware interfaces as shown in . The new signals for iSIF are as follows. All control signals are active high All iSIF circuitry and interface signals arm clocked on posedge clk and are reset normally to 0 by the asynchronous reset signal resetb sif All outputs are reset to 0.

In addition the following signals should be available for each XAP. These signals are all active high. They are all sampled and change on posedge clk. The 4 outputs are all reset by resetb sif. They are all reset to 0 except self force stop which is reset to 1 

If the SIF is currently unused and xSIF and iSIF load requests happen on the same clk cycle then the xSIF should be served first. Similarly in all equal cases of contention where xSIF and iSIF request the same service simultaneously then xSIF should be served first.

The SIF Control circuitry implements a ping pong system to prevent iSIF from blocking xSIF and to prevent xSIF from blocking iSIF 

This means that the SIF channel bandwidth whether due to the XAP being stopped or executing sif or sleepsif instructions is shared by time multiplexing between xSIF and iSIF.

The bit format of the main SIF fields is identical for xSIF and iSIF. The Control and Status fields contain parity bits. Their usage by xSIF is described in section 0 of this TM. In iSIF the parity bits are treated as follows 

The SIF fields contain parity bits to expose communication errors. This is a valuable feature for xSIF as the off chip serial interface is exposed to electrical interference.

Parity bits are not that useful for iSIF as the on chip parallel interface is not exposed to any more electrical interference than the rest of the chip. This is why iSIF ignores PARITY AC and the iSIF Master can safely ignore PARITY D and PARITY S.

isif cancel cancels an iSIF instruction. If there is no iSIF instruction being executed then isif cancel is ignored.

When the SIF CS pin is pulled low any running xSIF instruction is cancelled. It does not affect any running iSIF instruction.

When SIF LOADB 0 and SIF CLK is toggled 32 times it can cause a SIF Cancel. The last 8 bits on SIF MOSI are sampled on negedge SIF CLK to specify the type of SIF Cancel. The decode is only performed after the 32negedge SIF CLK. These bits 7 0 are interpreted as follows 

The iSIF requires the following new bits to be added to each XAP Status Register. These will be present in all XAP processors even if the iSIF is not being used.

If the application designer does not want to use iSIF he should tie all iSIF inputs to 0. At synthesis most iSIF hardware will be optimised away.

The control scheme whether done as software or as hardware state machine from iSIF Master to SIF should be as follows 

The iSIF Master does not need to write to all the write fields isif address isif data write isif control if it knows they already contain the correct values

User mode allows unknown software to be run safely without affecting the operation of the supervisor interrupt and NMI mode code. The MODE 1 0 signal from xap3 core to xap3 mmu indicates whether the xap3 core is in User Supervisor Interrupt or NMI Mode. The xap3 core has a memory exception input that allows the xap3 mmu to indicate when a memory access is attempted that is illegal in the current operating mode.

It is expected that the majority of code will execute in User Mode and operating system functions will be implemented in Supervisor Mode. User mode code can call Supervisor Mode code by using the trap instruction.

The processor resets to Supervisor mode. The initialisation code is then responsible for initialising the stack and starting User Mode. The mode switch is implemented using the movr2s instruction to write to the FLAGS register.

User mode can only access User registers. The Interrupt NMI and Supervisor modes are known as privileged modes. They can access their own and the User Mode registers. Supervisor Mode cannot access Interrupt or NMI Mode registers and vice versa. In order to initialise Interrupt and NMI Mode registers programmers must disable interrupts and manually switch to Interrupt or NMI Mode by writing to the FLAGS register.

When the processor is awake SIF accesses can only take place when the CPU is executing a sif instruction.

The state of the program refers to whether the core is executing instructions or not. The program can be in three states 

Registers R R R and R are shadowed such that there is one of each of these registers per processor mode. For these registers the actual register accessed by an instruction depends on the mode in which the processor is operating.

The C compiler will use R as a Stack Pointer. R R R and R are shadowed in Supervisor and Interrupt modes. Only R and R are shadowed in NMI mode. NMI shares the Interrupt mode R and R shadow registers. At any one time a register is only used for a single variable whether it is 8 16 or 32 bit . All arithmetic compare and logical operations operate on full 32 bit words. Load and Store instructions have 16 bit and 8 bit forms sign and zero extended however allowing programs to operate on 16 bit and 8 bit variables.

The XAP3 contains eight breakpoint registers BRK that can be configured to stop the processor when an address is read written or executed.

In addition to this BRK have matching count registers such that the breakpoint is triggered if the address condition described above matches and the value of the corresponding count register is zero. At reset the count registers contain zero which means the breakpoint registers behave like simple breakpoints. When an address match happens and the count register is not zero the count register is decremented by one. Note that the count value never cycles once it reaches zero it stays there until changed by a write with the movr2b instruction.

In addition to this BRK and BRK have associated data and mask registers that allow the breakpoints to be conditional on the data read written by an instruction. These will only trigger when the address matches the count is zero and the data and mask conditions are satisfied. The data registers specify 1 s and 0 s to match against the mask registers specify don t cares where 1 match 0 don t care. For example suppose we want to break on a data value where bit is one bit is zero and we don t care about the rest of the bits. We specify 

When a mask register is set to zero the data matching is effectively disabled because all data values will trigger a match. So the break will occur when the address matches and the count is zero.

The count and data match features can be used to implement sophisticated conditional breakpoints in the debugger.

Providing privileged modes access to the breakpoint registers allows Supervisor Mode debuggers to be implemented that allow User Mode tasks to be debugged without needing to stop the processor. This allows for example the main operating system to remain running when debugging User Mode applications.

In User mode the above break conditions will also halt the processor if the B flag is 0. If the B flag is 1 the processor will not halt but will generate a Break exception instead.

The breakpoint registers can be written and read by privileged modes using the movr2b and movb2r instructions see below. The movs2r and movr2s instructions allow access to the BRKE register.

The movs2r and movr2s instructions allow Interrupt Supervisor and NMI mode access to the Special Registers. These are shown in die table below.

When in the Supervisor NMI or Interrupt Modes the entire FLAGS register can be modified by executing the movr2s instruction. The movs2r instruction allows the FLAGS register to be read. The irqe and irqd instructions can be executed in Supervisor NMI and Interrupt Modes. They are used to enable and disable interrupts.

The mode bits of the FLAGS register are automatically changed when interrupts or exceptions happen. The other bits remain unchanged. At reset the processor will start executing code in supervisor mode.

The condition flags Z. N C and V will be modified as instructions are executed. See the instructions description for details of the instructions that modify flags.

The memory model has a 32 bit address space 4G Bytes containing both code and data. The address space is byte addressed. All pointers are kept as full 32 bit byte addresses and will thus fit in a 32 bit register.

All instructions are aligned to a 16 bit boundary i.e. bit of the address is 0 but it is not necessary for 32 bit instructions to be aligned to a 32 bit boundary. This means that all 16 bit instructions are aligned whereas 32 bit instructions can be unaligned.

All data objects are unaligned. This means that 8 16 and 32 bit data can have any byte address. only shows aligned data objects.

All words use Little Endian byte ordering i.e. the low bits of 16 bit or 32 bit or 64 bit words are at the low byte address.

All registers and flip flops in XAP3 are asynchronously set or reset when the RESETB input pin goes low. Wherever possible the registers and flip flops should be reset and not set.

The bsr.p or bsr.a instruction is used to make function calls. The effect of bsr.p or bsr.a is to transfer the address of the next instruction to the link register R and to transfer the destination address to the PC. Control is returned to the calling function when the contents of R is transferred to PC. In practice the compiler generates the bsr.p instruction. The calling convention for the XAP3 is 

This is the basic application model where the locations of all functions and data are known at link time.

The XAP3 supports systems where applications can be loaded to memory locations that are not known at link time. Statically allocated variables are accessed relative to the GP register.

The relative positions of code and data can be varied at load time. PC relative addressing for code and constants probably stored in Flash means only minimal load time fixups are needed. GP relative addressing for global variables probably stored in RAM means only minimal load time fixups for data too.

If the same program is being run in more than one instance then the code constants only need to be loaded once. Each instance will have its own GP value pointing to its own area of RAM.

Absolute addressing can be used to access code and data at fixed addresses. This means that no load time fixups are required to access absolute code and data locations within the system.

Fixups will be necessary when static initialisers contain an address of a static variable. The location of the static variable is not known until link time hence the loader will need to fixup the initialisation constant. This code would require a load time fixup when used as part of a dynamically loaded application.

Many instructions take an immediate value. The width of the immediate bitfield in the instruction varies but is always less than 32 bits. The assembler encodes each immediate operand to generate the correct bitfield for the XAP3 instruction. The rules for performing the encoding vary according to the instruction type. If the encoding is not possible the assembler generates an error.

The assembler syntax for immediates in instructions is not affected by these rules. Immediate operands can be 32 bit numbers. However the encoding rules result in only a subset of the 2possible immediates being valid for each rule. The five immediate encoding rules are 

The cmp.8 .i instruction specifies an immediate operand and the ALU performs an 8 bit compare against bits 7 0 of Rs. The immediate operand can be signed or unsigned. Valid operands are therefore in the range 0 to 255 or 128 to 127.

The cmp.16 .i instruction specifies an immediate operand and the ALU performs an 16 bit compare against bits 15 0 of Rs. The immediate operand can be signed or unsigned. Valid operands are therefore in the range 0 to 65535 or 32768 to 32767.

The left most bit in the instruction bitfield is treated as a sign bit. This significance of this bit defines the valid range of the immediate operand. As an example if the significance of the left most bit is 28 the range of valid immediates operands is 256 to 255.

Some instructions do not encode the low order bits of the immediate operand. These must be zero in the operand.

This is used on the 16 bit encoding for the add.i Rd r15 instruction. The instruction encodes bits 8 2 s of the immediate. Bits and are not specified in the instruction and must be zero in the immediate operand see .

This is indicated by a u in the instruction bitfield. u encoding also applies to offsets in the push and pop instructions.

The immediate operand is treated as unsigned. The significance of the left most bit in the instruction bitfield defines the valid range of the immediate operand. As an example if the significance of the left most bit is 2 the range of valid immediates operands is 0 to 131071 see .

As with the s encoding rule some instructions do not encode the lowest bits of the operand. These must be zero. Examples of valid instructions are 

The cmp.16 .h instruction specifies an immediate operand and the ALU performs an 16 bit compare against bits 31 16 of Rs. Valid operands are in the range 0xFFFF0000 to 0xFFFFFFFF. The least significant 16 bits in the immediate operand are not encoded in the instruction and must be zero.

The instruction bitfield encodes bits 31 15 of the immediate operand. Bits 14 0 of the immediate operand must be the same as bit see .

bra.p bsr.p and mov.p take a 25 bit PC relative offset. The offset is signed and is sign extended to 32 bits before use. As all instructions start on a 16 bit boundary bit of the offset must be zero and is not encoded in the instruction.

The valid range for operands is 32 MByte to 32 MByte. The operand represents an offset relative to the current PC.

bra.a and bsr.a take a 25 bit unsigned absolute address. As all instructions start on a 16 bit boundary bit of the offset must be zero and is not encoded in the instruction see .

mov.g takes a 23 bit signed unsigned offset. The offset is the start address of a data object relative to GP. As all data objects start on a 32 bit boundary bits 1 0 of the offset must be zero and are not encoded in the instruction see .

Some of the instructions specify either a small immediate or a register e.g. movm as an operand. The instruction encoding of each operand uses five bits one bit selects between register and immediate four bits specify the register or the immediate.

To specify an immediate value of zero use register R. An immediate operand of 1 is encoded in the instruction bitfield as zero. Thus a four bit immediate bitfield can represent numbers 1 1 2 . . . 15.

A XAP3 ASIC is a single SIF Slave. The ASIC only contains one SIF interface with 4 or 5 external pins . The default SIF provided with XAP3 can support up to 8 on chip SIF Processors. These can all be XAP3 or can be a variety of different processors. Each can have its own or shared address space.

The SIF allows the user to debug software and to read or write the registers memory and IO registers of all the on chip SIF Processors. The SIF is also used for data acquisition and analogue production test of the ASIC. All memory and IO register reads and writes are performed in a non invasive manner. The processors continue to operate in functional mode without having their timing affected.

There are 2 SIF Modes Normal and Command. These modes are properties of the SIF and are independent of the processor types or states. For the purpose of readability the 3 statements in each row are defined to be equivalent 

The SIF Master can issue a special sequence of 256 bits on SIF MOSI to put the SIF into Command mode. The properties of Command SIF Mode are 

Most processors have 2 SIF Processor Modes Normal and Debug. At any time each processor has its own SIF Processor Mode. Each processor s mode can only be changed by the SIF interface.

The SIF Processor can be a variety of different processors. This specification describes the behaviour of the XAP3 in Normal and Debug SIF Processor Modes. For the purpose of readability the 3 statements in each row are defined to be equivalent 

The ASIC resets with all XAP3 processors in Normal mode. This allows the SIF Master to read and write address mapped variables normally IO registers or memory of the selected XAP3. These can be 8 16 or 32 bit.

The selected XAP3 is put into Debug mode by executing the Debug Enable SIF Instruction. It will then remain in Debug mode until it executes the Debug Disable SIF Instruction when it will return to Normal mode .

Some SIF Instructions can only be executed if the XAP3 is already in Debug mode. In practise Debug mode is only used during software development and ASIC test Debug mode allows the user to perform functions such as start stop set breakpoint run to breakpoint read and write XAP3 internal registers and flags etc.

It is important to distinguish between Normal Debug SIF Instructions and Normal Debug XAP3 SIF Processor Modes 

When the SIF is in Command Mode SIF Operations SIF Commands are executed immediately. As soon as the 8 bit Command has been shifted in to SIF MOSI the 8 bit Response will shift out on SIF MISO. There is never a wait period. SIF LOADB is not used. This is why SIF Commands cannot access processors or memory space. They are normally only used to query the SIF configuration i.e. to read a small ROM inside the SIF .

In the second stage Handshake the SIF Slave holds SIF LOADB low for varying amounts of time. This depends upon the type of SIF Instruction and whether the selected XAP3 is stopped or running. As soon as the selected XAP3 executes the SIF Instruction it tells the SIF Slave . The SIF can then let go of SIF LOADB allowing it to return high again. The same handshake process is used for Direct SIF Instructions which do not access any processor .

The following SIF Instructions are error conditions which are recognised by the hardware selected processor or SIF itself . The hardware will respond immediately returning the appropriate Processor or SIF error code 

In most cases the selected XAP3 waits for a sif or sleepsif XAP3 instruction before executing the SIF Instruction 

The following SIF Instructions are error conditions which cannot be recognised by the hardware selected processor or SIF itself . In such cases the SIF Slave will permanently hold SIF LOADB low 

In such cases the selected XAP3 will never tell the SIF that it has completed the SIF Instruction so the SIF Slave will never release SIF LOADB which the SIF Master will see and will know that this is being done by the selected SIF Slave . This has the effect of locking up the SIF Interface. The SIF Master must clear this with a SIF Cancel before it can proceed with any further SIF Instructions.

The SIF has locked up because the SIF Master issued an invalid SIF Instruction to the selected SIF Processor in the selected SIF Slave. The SIF Master must be able to detect and recover from such a situation by 

In both cases the SIF Slave will release SIF LOADB allowing it to go high again. At this point the SIF lockup has been cleared. This allows the SIF Master to issue further SIF Instructions.

It is possible for the requested SIF Instruction debug or normal mode read or write to be completed even after the Master has started a SIF Cancel. This means that when a Master issues a SIF Cancel it cannot know whether the previously requested SIF Instruction will happen or not. The Master can assume that if the previous SIF instruction was executed by the Slave then it will be the correct one requested.

The WRITE bit is 1 for SIF Write Instructions and 0 for SIF Read Instructions. For all modes the only way that the SIF can update any part of the ASIC is with a SIF Write. SIF Reads cannot update any part of the ASIC.

The PARITY AC bit is set by the SIF Master and checked by the SIF Slave. If the Slave finds a parity error it should set ERROR ERROR TYPE and ERROR CODE 3 0 in the Status field.

The 2 SIZE bits indicate whether the data is 8 16 or 32 bit The SIZE bits are interpreted for all Normal SIF Instructions i.e. reads and writes to memory and IO registers whether the selected XAP3 is in Normal or Debug mode. Debug SIF Instructions which have a Data parameter must set the SIZE bits correctly. Debug SIF Instructions which do not have a Data parameter must set the SIZE bits to 0.

The 3 PROCESSOR bits select which of the 8 SIF Processors the SIF Instruction should be passed to. All SIF Instructions must select a SIF Processor. Only One SIF Processor can be accessed at a time. There is no state. Successive SIF Instructions can access any SIF Processors in any order. SIF Processor Addresses should be allocated from 0 upwards. If the ASIC only contains one XAP3 it should be at SIF Processor Address 0.

The 32 bit Data field is used for SIF Reads and Writes from or to the specified Memory Address or Register .

For security reasons some Debug SIF Instructions require the Data field to be set to a specific value.

The Slave should only update the Data field after valid SIF Reads. If there has been any kind of error i.e. ERROR 1 the Data field should not be updated.

The 16 Bit Status field STATUS 15 0 format depends upon whether there has been an error in the SIF Instruction or not The Slave SIF has a 13 bit input from the main part of the ASIC called STAT 12 0 .

The format of the Status field is independent of the specified Address and Control fields. Its format depends upon STAT 12 0 and on whether there was a SIF Error.

The Slave should update the Status field after all completed SIF LOADB handshake SIF Instructions. This should happen whether there is an error or not

A particular kind of Debug SIF Instruction is the Direct SIF Instruction. These are executed in the SIF itself and do not access any processor. Direct SIF Instructions all format the shift register bits as follows 

All other Debug Instructions refer to the selected processor. Such Debug SIF Instructions can be split into 3 categories 

Like the XAP3 itself SIF reads and writes can use any byte address for all word sizes. The words do not need to be memory aligned. i.e. 

The following XAP3 SIF Instructions Normal then Direct then other Debug cover a subset of possible values for the Control and Address fields. The table does not include the PARITY AC or WRITE bits in the Control field. The table assumes that PROCESSOR 2 0 0. All unspecified values are reserved for future use.

One of the SIF Debug Instructions reads the selected XAP3 Status Register. Note that this is not the same as the SIF shift register Status field STATUS 15 0 .

Normally parity bits can only expose single bit errors. However the XAP3 SIF has a parity checking configuration which also detects stuck high and stuck low faults on SIF MOSI and SIF MISO.

PARITY AC Address Control field parity is set by the SIF Master and checked by the SIF Slave. It has odd parity so there are an odd number of 1s in the 40 bits 

If SIF MOSI is stuck at 1 or stuck at 0 there will be a parity error in PARITY AC. This is because there is an even number of protected bits including PARITY AC and odd parity checking. This means that the bits cannot all be the same value.

PARITY D Data field parity is set by the SIF Slave and checked by the SIF Computer. It has odd parity so there are an odd number of Is in the 33 bits 

PARITY S Status field parity is set by the SIF Slave and checked by the SIF Computer. PARITY S should be calculated after PARITY D. It has odd parity so there are an odd number of 1s in the 16 bits 

If SIF MISO is stuck at 1 or stuck at 0 there will be a parity error in PARITY S. This is because there is an even number of protected bits including PARITY S and odd parity checking. This means that the bits cannot all be the same value.

PARITY S is based on the values in the Status Capture Register which will always be parallel loaded into the Status Shift Register when a SIF Instruction is completed .

The counters reset to 0 by hardware ASIC or SIF Reset . The counters wrap and do not have any overflow detection.

It is possible for a SIF Read or Write to be completed after a SIF Cancel. In this case the Cancel Counter and one of the other counters will be incremented.

The SIF and XAP3 Verilog modules do not contain any test mode circuitry. They do not impose or assume any test strategy for the ASIC. They are scannable designs that the designer can configure for a variety of test strategies.

All conditioning of clock and reset signals as required for Scan and other test modes should be done in the CLOCKS RESETS module. This module generates the RESETB resets that are fed to the various modules in the ASIC. These signals will often need to be controlled by external pins in TEST mode to make the ASIC fully scannable. The CLOCKS RESETS module is application specific and should be designed by the user to conform to the test strategy being used for the ASIC.

The SIF Instructions include several resets for different parts of the ASIC and Off Chip devices. SIF resets are done by 2 mechanisms 

RESETB DEBUG is needed so that the whole ASIC or selected processors can be put into reset state and stopped before single stepping for software debug 

User mode allows unknown software to be run safely without affecting the operation of the interrupt mode code. The other 3 modes are privileged modes.

The processor resets to Supervisor mode. The initialisation code is then responsible for initialising the stack and starting User Mode. The mode switch is implemented using the movr2s instruction to write to the FLAGS register.

User mode can only access User registers. The Supervisor Interrupt and NMI modes are known as privileged modes. They can access their own and the User Mode registers. Supervisor Mode cannot access the Interrupt or NMI Mode registers and vice versa. In order to initialise Interrupt and NMI mode registers programmers must disable interrupts and manually switch to Interrupt mode by writing to the FLAGS register.

When the processor is awake SIF accesses can only take place when the CPU is executing a sif instruction.

The state of the program refers to whether the core is executing instructions or not. This is determined by RUN STATE 1 0 in the XAP4 Status Register see 0 . This is decoded as the following 4 states 

RunContinuous is the normal state used for program execution. The other 3 states will only be encountered during interactive debugging.

Registers R R and R are shadowed such that there is one of each of these registers per processor mode. For these registers the actual register accessed by an instruction depends on the mode in which the processor is operating.

Any pair of adjacent registers can be joined to form a 32 bit accumulator. These are used by the mult div rem divrem shift and rotate instructions. Such accumulators are referred to by the lower register of the pair. e.g 

The C compiler uses R as Stack Pointer and R as Link Register. R R and R are shadowed in Supervisor Interrupt and NMI modes.

At any one time a register is only used for a single variable whether it is 8 or 16 bit . All arithmetic and logical operations operate on full 16 bit words. Load Store and Compare instructions have 16 bit and 8 bit forms zero extended allowing programs to operate on 8 bit variables.

The XAP4 contains one breakpoint register BRK that can be configured to stop the processor when an address is read written or executed.

Providing privileged modes access to the breakpoint register allows Interrupt Mode debuggers to be implemented that allow User Mode tasks to be debugged without needing to stop the processor. This allows for example the main operating system to remain running when debugging User Mode applications.

If the B flag is 1 and the processor is in User mode it will not halt but will generate a Break exception instead.

The breakpoint registers can be written and read by privileged modes using the movr2b and movb2r instructions see below. The movs2r and movr2s instructions allow access to the BRKE register.

The movs2r and movr2s instructions allow Interrupt Supervisor and NMI mode access to the Special Registers. These are shown in the table below.

When in Supervisor Interrupt or NMI modes the entire FLAGS register can be modified by executing the movr2s instruction. The movs2r instruction allows the FLAGS register to be read. The irqe and irqd instructions can be executed in Supervisor Interrupt or NMI Mode. They are used to enable and disable interrupts.

The mode bits of the FLAGS register are automatically changed when interrupts or exceptions happen. The other bits remain unchanged. At reset the processor will start executing code in Supervisor mode.

The condition flags Z N C and V will be modified as instructions are executed. See the instructions description for details of the instructions that modify flags.

The memory model has a 16 bit address space 64 kBytes containing both code and data. The address space is byte addressed. All pointers are kept as full 16 bit byte addresses and will thus fit in a 16 bit register see .

All instructions are aligned to a 16 bit boundary i.e. bit of the address is 0 but it is not necessary for 32 bit instructions to be aligned to a 32 bit boundary.

All data objects are unaligned. This means that 8 16 and 32 bit data can have any byte address. The diagram above only shows aligned data objects.

All words use Little Endian byte ordering i.e. the low bits of a 16 bit or 32 bit word are at the low byte address.

All registers and flip flops in XAP4 are asynchronously set or reset when the RESETB input pin goes low. Wherever possible the registers and flip flops should be reset and not set.

The bsr.p or bsr.a instruction is used to make function calls. The effect of bsr.p or bsr.a is to transfer the address of the next instruction to the link register R and to transfer the destination address to the PC. Control is returned to the calling function when the contents of R is transferred to PC. In practice the compiler generates the bsr.p instruction.

This is the basic application model where the locations of all functions and data are known at link time.

The XAP4 supports systems where applications can be loaded to memory locations that are not known at link time. Statically allocated variables are accessed relative to the PC register.

The relative positions of code and data can be varied at load time. PC relative addressing for code and constants probably stored in Flash means only minimal load time fixups are needed.

If the same program is being run in more than one instance then the code constants only need to be loaded once.

Absolute addressing can be used to access code and data at fixed addresses. This means that no load time fixups are required to access absolute code and data locations within the system.

Fixups will be necessary when static initialisers contain an address of a static variable. The location of the static variable is not known until link time hence the loader will need to fixup the initialisation constant. This code would require a load time fixup when used as part of a dynamically loaded application.

The XAP4 16 bit processor is able to write to and or read from any two contiguous register pairs aligned or unaligned in a single clock cycle. Any of the 0.32 instructions are able to make use of this feature. Two particular examples follow 

A XAP4 ASIC is a single SIF Slave. The ASIC only contains one SIF interface with 4 or 5 external pins . The default SIF provided with XAP4 can support up to 8 on chip SIF Processors. These can all be XAP4 or can be a variety of different processors. Each can have its own or shared address space. The SIF can be accessed by the external serial xSIF interface or by the internal parallel iSIF interface.

The SIF allows the user to debug software and to read or write the registers memory and IO registers of all the on chip SIF Processors. The SIF is also used for data acquisition and analogue production test of the ASIC. All memory and IO register reads and writes are performed in a non invasive manner. The processors continue to operate in functional mode without having their timing affected.

Either xSIF or iSIF may be used for Debug SIF instructions but not both. The most common modes will be 1 or 2.

Parity checking is performed on xSIF but not on iSIF. iSIF does not check PARITY AC. It does generate PARITY D and PARITY S but the iSIF Master may ignore them if it wishes.

xSIF may cancel stuck xSIF or iSIF instructions. iSIF may cancel stuck iSIF instructions but not stuck xSIF instructions.

In all other respects xSIF and iSIF behave identically. They access equivalent SIF fields Address Control Data Status and use the same SIF instruction codes.

There are 2 SIF Modes Normal and Command. These modes are properties of the SIF and are independent of the processor types or states see . For the purpose of readability the 3 statements in each row are defined to be equivalent 

Command mode is available to xSIF but not to iSIF. The xSIF Master can issue a special sequence of 256 bits on SIF MOSI to put the SIF into Command mode. The properties of Command SIF Mode are 

Most processors have 2 SIF Processor Modes Normal and Debug. At any time each processor has its own SIF Processor Mode. Each processor s mode can only be changed by the SIF interface xSIF or iSIF .

The SIF Processor can be a variety of different processors. This specification describes the behaviour of the XAP4 in Normal and Debug SIF Processor Modes. For the purpose of readability the 3 statements in each row are defined to be equivalent 

The ASIC resets with all XAP4 processors in Normal mode. This allows the SIF Masters xSIF and iSIF to read and write address mapped variables normally IO registers or memory of the selected XAP4. These can be 8 or 16 bit If the XAP4 is in Normal mode then it will be running. It can only be stopped when in Debug mode.

The selected XAP4 is put into Debug mode by executing the Debug Enable SIF Instruction issued by xSIF or iSIF Master . It will then remain in Debug mode until it executes the Debug Disable SIF Instruction when it will return to Normal mode .

Some SIF Instructions can only be executed if the XAP4 is already in Debug mode. In practise Debug mode is only used during software development and ASIC test. Debug mode allows the user to perform functions such as start stop set breakpoint run to breakpoint read and write XAP4 internal registers and flags etc.

It is important to distinguish between Normal Debug SIF Instructions and Normal Debug XAP4 SIF Processor Modes 

Command mode is available to xSIF but not to iSIF. When the SIF is in Command Mode SIF Operations SIF Commands are executed immediately. As soon as the 8 bit Command has been shifted in to SIF MOSI the 8 bit Response will shift out on SIF MISO. There is never a wait period. SIF LOADB is not used. This is why SIF Commands cannot access processors or memory space. They are normally only used to query the SIF configuration i.e to read a small ROM inside the SIF .

In the second stage Handshake the xSIF Slave holds SIF LOADB low for varying amounts of time. This depends upon the type of SIF Instruction and whether the selected XAP4 is stopped or running. As soon as the selected XAP4 executes the SIF Instruction it tells the xSIF Slave . The xSIF can then let go of SIF LOADB allowing it to return high again. The same handshake process is used for Direct SIF Instructions which do not access any processor .

The following SIF Instructions are error conditions which are recognised by the hardware selected processor or SIF itself . The hardware will respond immediately returning the appropriate Processor or SIF error code 

In most cases the selected XAP4 waits for a sif or sleepsif XAP4 instruction before executing the SIF Instruction 

The following SIF Instructions are error conditions which cannot be recognised by the hardware selected processor or SIF itself . In such cases the SIF Slave will permanently hold SIF LOADB low 

In such cases the selected XAP4 will never tell the SIF that it has completed the SIF Instruction so the SIF Slave will never release SIF LOADB which the SIF Master will see and will know that this is being done by the selected SIF Slave . This has the effect of locking up the SIF Interface. The SIF Master must clear this with a SIF Cancel before it can proceed with any further SIF Instructions.

The SIF has locked up because the SIF Master issued an invalid SIF Instruction to the selected SIF Processor in the selected SIF Slave.

In both cases the SIF Slave will release SIF LOADB allowing it to go high again. At this point the SIF lockup has been cleared. This allows the SIF Master to issue further SIF Instructions.

It is possible for the requested SIF Instruction debug or normal mode read or write to be completed even after the Master has started a SIF Cancel. This means that when a Master issues a SIF Cancel it cannot know whether the previously requested SIF Instruction will happen or not. The Master can assume that if the previous SIF instruction was executed by the Slave then it will be the connect one requested.

iSIF has the equivalent fields. The field sizes and bit allocations are the same as for the xSIF shift register. However iSIF splits the Data field into 2 separate fields for DataWrite and DataRead.

The WRITE bit is 1 for SIF Write Instructions and 0 for SIF Read Instructions. For all modes the only way that the SIF can update any part of the ASIC is with a SIF Write. SIF Reads cannot update any part of the ASIC.

The PARITY AC bit is set by the xSIF Master and checked by the xSIF Slave. If the Slave finds a parity error it should set ERROR ERROR TYPE and ERROR CODE 3 0 in the Status field. iSIF ignores PARITY AC so the iSIF Master does not need to set it.

The 2 SIZE bits indicate whether the data is 8 or 16 bit The SIZE bits are interpreted for all Normal SIF Instructions i.e reads and writes to memory and IO registers whether the selected XAP4 is in Normal or Debug mode. Debug SIF Instructions which have a Data parameter must set the SIZE bits correctly. Debug SIF Instructions which do not have a Data parameter must set the SIZE bits to 0.

The 3 PROCESSOR bits select which of the 8 SIF Processors the SIF Instruction should be passed to. All SIF Instructions must select a SIF Processor. Only One SIF Processor can be accessed at a time. There is no state. Successive SIF Instructions can access any SIF Processor in any order. SIF Processor Addresses should be allocated from 0 upwards. If the ASIC only contains one XAP4 it should be at SIF Processor Address 0.

The 16 bit Data field is used for SIF Reads and Writes from or to the specified Memory Address or Register .

For security reasons some Debug SIF Instructions require the Data field to be set to a specific value.

The Slave should only update the Data field after valid SIF Reads. If there has been any kind of error i.e ERROR 1 the Data field should not be updated.

The 12 Bit Status field STATUS 11 0 format depends upon whether there has been an error in the SIF Instruction or not. The Slave SIF has a 9 bit input from the main part of the ASIC called STAT 8 0 .

The format of the Status field is independent of the specified Address and Control fields. Its format depends upon STAT 8 0 and on whether there was a SIF Error.

The Slave should update the Status field after all completed SIF LOADB handshake SIF Instructions. This should happen whether there is an error or not.

A particular kind of Debug SIF Instruction is the Direct SIF Instruction. These are executed in the SIF itself and do not access any processor. Direct SIF Instructions all format the shift register bits as follows 

All other Debug Instructions refer to the selected processor. Such Debug SIF Instructions can be split into 3 categories 

Like the XAP4 itself SIF reads and writes can use any byte address for all word sizes. The words do not need to be memory aligned. i.e. 

The following XAP4 SIF Instructions Normal then Direct then other Debug cover a subset of possible values for the Control and Address fields. The table does not include the PARITY AC or WRITE bits in the Control field. The table assumes that PROCESSOR 2 0 0. All unspecified values are reserved for future use. Instructions marked are only implemented when the SIF is connected to more than one processor.

One of the SIF Debug Instructions read the selected XAP4 Status Register. Note that this is not the same as the SIF shift register Status field STATUS 11 0 .

Normally parity bits can only expose single bit errors. However the XAP4 SIF has a parity checking configuration which also detects stuck high and stuck low faults on SIF MOSI and SIF MISO.

PARITY AC Address Control field parity is set by the SIF Master and checked by the SIF Slave. It has odd parity so there are an odd number of 1s in the 24 bits 

If SIF MOSI is stuck at 1 or stuck at 0 there will be a parity error in PARITY AC. This is because there is an even number of protected bits including PARITY AC and odd parity checking. This means that the bits cannot all be the same value.

PARITY D Data field parity is set by the SIF Slave and checked by the SIF Computer. It has odd parity so there are an odd number of 1s in the 17 bits 

PARITY S Status field parity is set by the SIF Slave and checked by the SIF Computer. PARITY S should be calculated after PARITY D. It has odd parity so there are an odd number of Is in the 12 bits 

If SIF MISO is stuck at 1 or stuck at 0 there will be a parity error in PARITY S. This is because there is an even number of protected bits including PARITY S and odd parity checking. This means that the bits cannot all be the same value.

PARITY S is based on the values in the Status Capture Register which will always be parallel loaded into the Status Shift Register when a SIF Instruction is completed .

The SIF and XAP4 Verilog modules do not contain any test mode circuitry. They do not impose or assume any test strategy for the ASIC. They are scannable designs that the designer can configure for a variety of test strategies.

All conditioning of clock and reset signals as required for Scan and other test modes should be done in the CLOCKS RESETS module. This module generates the resetb resets that are fed to the various modules in the ASIC. These signals will often need to be controlled by external pins in TEST mode to make the ASIC fully scannable. The CLOCKS RESETS module is application specific and should be designed by the user to conform to the test strategy being used for the ASIC.

The SIF Instructions include several resets for different parts of the ASIC and Off Chip devices. SIF resets are done by 2 mechanisms 

resetb xap is often pulled low by xIDE executing the relevant Debug SIF Instruction. When resetb xap is pulled low the XAP will be reset to 

resetb sif is normally only pulled low at power on reset. When resetb sif is pulled low the XAP will be reset to 

If the designer wants the XAP to be stopped after resetb sif is pulled low he should connect the self force stop output to the force stop input. In the diagram on the previous page Processor is stopped and Processor is running after resetb sif is pulled low.

The XAP4 is a powerful 16 bit processor optimised for low gate count and low power. It has a von Neumann architecture and can address 64 kByte of linear byte addressable memory.

The XAP4 architecture instruction set compiler toolchain and application binary interface are all designed for efficient execution of programs written in C.

The XAP4 implements the features necessary to support complex software systems where high reliability or high integrity is a requirement. The XAP4 provides hardware support for common real time operating system primitives including a clear definition of user and supervisor modes atomic instructions for synchronisation constructs and position independent code to allow dynamic linkage.

The XAP4 MMU interface enables memory protection systems for instruction and data throwing exceptions if processes access code or data memory illegally.

The XAP4 supports a total of 16 interrupts and 16 exceptions. Each has its own handler defined in a vector table.

A rich set of instructions is provided including a complete set of branches arithmetic operations on 8 16 and 32 bit data. Several instructions map closely onto C language constructs thereby providing very high code density and fast execution.

The XAP4 instruction set contains 145 unique instructions. Most common instructions are 16 bits long with less common instructions using 32 bits. Some instructions have 16 bit and 32 bit forms with the toolchain using the 16 bit form whenever possible.

This approach gives high code density. Programs can mix 16 bit and 32 bit instructions at will. No switching between modes is necessary and the processor executes all instructions at full speed. The 16 bit instructions can access all of the processor resources available to the 32 bit instructions.

The XAP4 processor includes a hardware multiplier divider and barrel shifter. Instruction execution is pipelined resulting in operating speeds of over 100 MHz on a 0.18 m ASIC process. The processor can be implemented in any ASIC process between 2.0 m and 0.065 m and in any FPGA.

The XAP4 instruction set architecture is available in different hardware implementations. The XAP4a implementation is targeted for low cost low power applications and requires approximately 12 k gates for the processor core.

The GNU Compiler Collection gcc provides an industry standard ANSI C compiler plus GCC extensions. xap4 gcc and binutils assembler and linker are provided in the XAP4 software toolkit

The xIDE integrated development environment provides a cross platform development and debugging tool for XAP4 programmers using an industry standard look and feel.

The XAP4 is the smallest embodiment of the invention within the Von Neumann architecture XAP processor family

These processors have all been designed for embedded use in ASICs and FPGAs. They all use Cambridge Consultants patented SIF interface for debugging and the xIDE development environment for software development. They all have excellent code density when used with their GCC binutils compile chains. XAP3 also has an ANSI C compiler that provides even higher code density. They all have 4 processor modes with excellent support for RTOS and low latency interrupts. They all have the same style of instruction set and programmer s model. The family offers an easy upgrade path between systems of different sizes offering the programmer a consistent interface.

The new XAP family builds on the success of Cambridge Consultants legacy 16 bit Harvard architecture XAP processor family 

XAP1 has been used in many ASIC projects since its development in 1994 resulting in over 10 million silicon devices.

The XAP2 is an evolutionary development from XAP1. XAP2 has been used in over 100 million silicon devices since its development in 1999. This includes all of CSR s Bluetooth and 802.11 devices.

The XAP4a hardware implementation exists as a soft IP core written entirely in synthesisable Verilog RTL. This can be targeted at either System on Chip ASIC or FPGA implementations.

The xIDE toolset includes an instruction set simulator for XAP4a. This can be extended to include models of other parts of the system including memories and interrupts.

The XAP4a system itself does not contain any I O registers neither does it have specific instruction to perform I O operations. All I O must be memory mapped and are accessed using the normal XAP4 instructions. As with the memories the I O register should be synchronous. The XAP4a system comes with examples of synchronous memory mapped I O registers.

A typical ASIC containing a XAP4a system is shown in the . This illustrates the xap4 system module connected to application specific circuitry to provide 

All Verilog names modules ports signals are lower case. Words are separated with an underscore character. Buses are always of the form high low . Module names all start with xap4  . Control signals are normally active high. If active low the signal name or intermediate word ends in b . e.g. 

The high level modules have been created as Fletcher charts that automatically generate the Verilog RTL to be used. This methodology uses a flat naming convention. This means that a signal has the same name at all levels of the hierarchy. This means that signals and ports have the same names.

The low level modules are hand written in Verilog RTL. In general this maintains the flat naming strategy but it may not always be the case.

There are no special features in XAP4a for test. It has been designed for simple scan path testing. It provides the designer with clean access to the clock and reset signals. It is recommended that any special test mode behaviour is implemented in the xap4 clocks resets module. This may modify clock and reset behaviour in the various test modes.

We expect the ASIC designer to create a single module called xap4 clocks resets for the whole ASIC. All clock reset and test signals should either pass through or be generated from within the xap4 clocks resets module. This allows the designer to have a single block to analyse for the correct operation of clocks and resets for the ASIC in functional and in all test modes including scan path .

There are no latches or memories inside xap4 system. The only sequential components used am clocked flip flops. There are only two clocks used in xap4 system. Inside xap4 system the two clocks are only used to clock flip flops.

The XAP4 input sif mosi is sampled on negedge sif clk. All other XAP4 inputs are sampled on posedge clk. Some of these inputs go directly into the flip flop D pin. Other inputs have combinational logic between the module input and the flip flop D pin.

The XAP4 output sif miso out changes on posedge sif clk. All other XAP4 outputs change on posedge clk. Some of these outputs come directly from the flip flop Q pin. Other outputs have combinational logic between the flip flop Q pin and the module output. Such signals may bounce for a short period after posedge clk before assuming their new stable value.

Clocks are not gated at all within xap4 system. If the ASIC designer wishes to gate clocks when for example the XAP4 is in a sleep state this should be done outside xap4 system. An example of how to do this in the xap4 clocks resets module is described herein

We expect the xap4 clocks resets module to generate four active low resetb signals these signals should be generated from the associated four rst outputs from xap4 system. They may also be generated by other reset sources such as power on reset or watchdog 

The xap4 clocks resets module which generates the resetb signals should synchronise the end of each reset i.e. posedge resetb with negedge clk. A possible circuit is shown in . This shows each resetb signal generated from a flip flop that is asynchronously cleared either by emu reset the external reset signal into the ASIC or by the associated rst signal. The trailing rising edge of each resetb signal is synchronised to the next falling edge of clk when the rst signal or emu reset is removed.

The four rst signals are all outputs from flip flops in xap4 system clocked on posedge clk. These signals are all active high and are one clk cycle wide. All four can be generated in various combinations by SIF commands from the debug computer. These can be connected in hardware via xap4 clocks resets module to reset different sections of the ASIC. The ASIC designer is free to connect up some or all of these rst outputs as best supports his system reset strategy. It is only mandatory to connect the rst xap and rst sif signals. See the example RTL in xap4 clocks resets for guidance.

The unknown instruction output is also clocked on posedge clk. It is generated by the xap4 when it encounters an unrecognised opcode and it is not in User mode. An unknown instruction in User mode generates an exception that can be processed by an exception handler. An unknown instruction in any privileged mode Supervisor Interrupt NMI is typically considered a fatal error. We expect this signal to be used as input to the xap4 clocks resets module so that it can be used to set the various resetb signals low.

XAP4 has a number of inputs and outputs for overall system control. It is recommended that these signals all be connected to the xap4 clocks resets module.

These are all synchronous signals generated or synchronously sampled by XAP4 on posedge of clk. Further description for these signals is provided below and in section 0.

The asleep output signal is set high if the XAP4 is in a sleep state i.e. if it is executing a sleepnop or sleepsif instruction. The XAP4 remains in this state with asleep set until the XAP4 samples the wake up signal high at posedge of clk which then terminates the sleepnop sleepsif instruction. It is only necessary to set wake up high for at least one clock cycle. The wake up signal is ignored by XAP4 if it is not in a sleep state.

It is also possible to wake up the XAP with a SIF wake up instruction. This causes the XAP4 to exit sleep state exactly as if wakeup had been pulsed high for one clock cycle.

One common use of the asleep and wake up signals is for an external clock gating scheme to reduce power consumption. An example of this is provided in the xap4 clocks resets module. This operates according to the timing shown in .

The xap4 clocks resets module gates the main system clock to the XAP4 clk from its internal continuous version of the clock clk contin . When the XAP4 executes a sleepnop or sleepsif instruction it goes into a sleep state and sets the asleep signal high shown at time t in . The xap4 clocks resets module detects this on the following clock edge t and turns off clk to XAP4. Internally clk contin continues to run and is used to synchronise and edge detect external interrupts.

Normally the user will want to re awake the XAP4 when some external event occurs. The xap4 clocks resets module uses a posedge on interrupt 9 as the trigger to re awake XAP4 but it could of course be some other signal not necessarily an interrupt or a combination of several signals. When the wake up condition occurs at clock edge t the xap4 clocks resets module re enables the clocks and pulses interrupt 9 and wake up high for one clk period. On the first posedge of the re enabled clock at t the XAP4 sees wake up set high and resumes program execution which sets asleep low. Also at t the IVC captures the pulse on interrupt 9 which sets ivc status 9 high. This can then be used to generate an interrupt to XAP4 software.

If an interrupt is used both to re awake the XAP4 and generate an interrupt to the XAP4 software the XAP4 will wake up and immediately branch to the interrupt vector provided that interrupts are enabled in the flags register and in the IVC.

Another possible scenario is the need to support xSIF access when the XAP4 is asleep with clk disabled. For example the XAP4 may have executed a sleepnop instruction which puts the processor in sleep mode but allows SIF access. If the xap4 clocks resets module disables clk while the XAP is asleep then the XAP4 cannot complete the SIF access.

The recommended solution is to use the posedge of sif clk to enable clk to XAP4 at the start of an xSIF access and then disable clk again when the XAP4 portion of the access is complete signified by a posedge on sif loadb out. Note that there is no need to pulse wake up or an interrupt for this xSIF access the only requirement is to turn clk on to XAP4 to allow the xSIF access to complete.

The debug output signal is set high if the XAP4 is in debug mode. This occurs when the SIF xSIF or iSIF executes a particular SIF instruction to put the XAP in debug mode. It remains in debug mode until a corresponding SIF instruction is executed to exit debug mode. The XAP must be in debug mode in order to execute certain SIF instructions of an invasive nature writing processor registers processor control rum stop wake up run to break etc.

The force stop signal provides a way to externally stop the XAP4 this is in addition to mechanisms provided by the SIF interface. The stopped output signal is set high if the XAP4 is stopped either because the force stop input is high or because Run State Stopped. The XAP4 enters Run State Stopped when any of the following conditions occur.

A SIF instruction sets Run State Run To Break and the processor subsequently hits a breakpoint condition.

A SIF instruction sets Run State Single Step and the processor subsequently executes a single instruction.

The XAP4 starts running and sets the stopped output low only when the force stop input is low and Run State Stopped.

Note that setting or clearing force stop does not have any effect on Run State. Run State is controlled solely by SIF instructions or by the processor terminating a Run To Break or Single Step as described above.

When the xap4 SIF logic receives a reset on resetb sif the Run State is reset to Run Continuous. This allows a system with ROM resident code to begin execution immediately following a power on reset. For a XAP4 system with RAM resident code the XAP4 must be held stopped until the code is loaded into RAM. The force stop signal provides this ability using one of two methods 

The XAP4 tests for a stop request from force stop or from a SIF instruction at the posedge of clk at the end of each XAP4 instruction and at the end of each transfer in a blkcp block copy or blkst block store instruction. The maximum delay in stopping is therefore equal to the length of the longest atomic instruction which is the divide instruction .

The XAP4 leaves the stopped state and sets the stopped output low only when the force stop input is low and Run State Stopped. So if force stop is set from high to low the stopped output may still remain high if Run State Stopped.

The two timing diagrams below illustrate typical timing relationships between force stop stopped and Run State.

The XAP4 system includes an xSIF interface this is a serial interface consisting of 4 or 5 pins. This interface is for debug use only and is not intended to be used for functional purposes.

The ASIC block diagram in shows an optional isif master module. This uses the iSIF internal SIF interface to provide powerful debugging and control capabilities from another processor or control logic within the ASIC. The iSIF is an internal parallel version of the xSIF interface and differs significantly from xSIF in that it can be used for functional purposes by the ASIC designer. The iSIF is expected to be used in one of the ways 

The xap4 single module provides the functionality necessary to implement the XAP4 instruction set. It decodes the instruction fetched from memory and then executes the necessary ALU operation s and or memory load operations writing the appropriate results back to the internal registers flags and memory as necessary. The core contains the following features 

Register file for the r0 r7 processor registers with one write port and three read ports. The registers are split into even and odd groups allowing a pair of contiguous registers to be read or written in one cycle for 32 bit data .

The MMU module forms the interface between xap4 single and external memories and peripherals. The XAP4a is provided with an example MMU xap4 mmu but should be adapted to the user s specific requirements. The MMU provides the following functions 

The xap4 single module initiates a memory access by setting high either read for a read access or write for a write access . It also drives address 15 0 and size to indicate the target address and the width of the access 1 or 2 bytes . If this is a write access it also drives data write 15 0 .

The MMU decodes the address and determines first if the access is to be permitted or whether it should cause an exception. If the access is not permitted the MMU flags an exception see section 0 . Otherwise the MMU sets high the appropriate chip select signal e.g. ram cs for a write to RAM and sets we high for a write access or low for a read access. It also and sets byte 1 0 according to address 0 and size 

The MMU decodes the incoming address from the XAP to create one or more chip select signals to the various memory devices. show the recommended memory maps for the four most common configurations. shows Recommended Memory Maps.

The MMU is responsible for informing the xap4 processor if wait states are required. The MMU drives mem wait high unless this is the selected memory can accept a new address on the next clock cycle. The xap4 single module holds its memory interface outputs stable until mem wait goes low.

When xap4 single samples mem wait low at a clock edge it is free to begin a new memory access. Note that for a read access the read data is returned on the clock after the one in which mem wait goes low see the memory read timing described herein.

For best performance the xap4 should be connected to memory data and program that operates with zero wait states i.e. single cycle memory. This means that the memory should be ready to accept a new address for a read or write access on every clock cycle. Since most xap4 instructions make full use of the memory bandwidth the use of memory with one or more wait states will degrade xap4 performance almost linearly.

The user can modify the xap4 mmu module to suit the memory and peripherals connected to the MMU. If memory with one or wait states is to be used then the user should refer to section 0 that discusses how this impacts the use of the XAP4 sif instruction.

The MMU has two memory exception flags that it drives to the xap4 data exception and prog exception. These can be used to notify the xap4 of illegal data or program accesses respectively. In addition the MMU outputs an error flag sif mmu error that it can set or clear during SIF accesses to memory. This signal can be used by the MMU to notify the SIF interface of an illegal memory access

The MMU receives various qualifiers from the xap4 single module to assist it in qualifying memory access exceptions 

It is a straightforward task for the user to modify the MMU to extend exception detection as required. For example it may be desired to prevent program access to certain areas of RAM in User mode or to prevent data access to portions of RAM or to flag byte writes to memory without byte enables or to differentiate between SIF access and xap4 access to memory. These and other combinations can be achieved with the signals provided to the MMU.

In normal operation accesses to memory will be sequential. The xap4 system design provides pipelined operation for maximum throughput. Total throughput is one clock per access for zero wait state memory two clocks per access for one wait state etc. illustrates a sequence comprising 

This section has discussed various capabilities provided by the MMU including address decoding exception detection and wait state control. For most users these capabilities will be fixed and can be coded directly into the RTL. However some users may require that some or all of these capabilities be software configurable. This can be achieved by modifying the MMU to include I O mapped registers within the MMU to specify these parameters. For example a pair of registers could be added to specify the base address and size for RAM or a set of registers to specify the address range for which data access is permitted. Alternatively some users may wish to add registers that capture certain signals when memory exceptions are detected.

These registers are not included in the example MMU since the need for them and their precise format will be highly application dependent. In addition their inclusion would unnecessarily increase chip area and power for those users that do not need this capability. However it is relatively straightforward to add these registers if needed and the example MMU does provide address decoding to access these registers.

The IVC module forms the interface between xap4 single and all external interrupts. The XAP4a is provided with an example IVC xap4 ivc but should be adapted to the user s specific requirements.

The Interrupt Vector Controller IVC accepts up to 16 interrupts named interrupt 15 0 . The IVC captures incoming interrupt pulses and then generates an interrupt and interrupt number to xap4 single. The interrupt priority scheme can be customised to meet the user s requirements.

The IVC accepts 16 external interrupts interrupt 15 0 . It assumes that these inputs have already been synchronised and converted to high going pulses one clock wide.

The example IVC sets the corresponding bit in the ivc status register if a pulse is detected on interrupt 7 0 . If more than 8 interrupts are required it is a simple matter to modify the IVC to use the remaining 8. If more than 16 interrupts are required this can be achieved by grouping several interrupts to share a single interrupt number. The interrupt handler software would then need to read additional registers in the IVC to determine and clear the precise source of the interrupt.

Software can read the ivc status register at any time to determine which interrupts have been detected since the last time any have been cleared. Software can clear one or more bits in the ivc status register by setting the corresponding bit s in the ivc clear register. For each bit set high during a write to the ivc clear register the IVC will reset to zero the corresponding bit in the ivc status register. For each bit set low during a write to the ivc clear register the corresponding bit in the ivc status register will be unaffected.

Note that if a new interrupt arrives on the same clock cycle as it is being cleared by software the arriving interrupt takes precedence and will set the corresponding bit in the ivc status register. This ensures that an incoming interrupt cannot be inadvertently lost .

Each captured interrupt is then individually AND ed with its corresponding bit in the ivc enable register. The ivc enable register allows software to control which interrupt sources are allowed to generate an interrupt to the xap4. If a bit in the ivc enable register is set high the corresponding interrupt is enabled otherwise it is disabled.

All enabled interrupts are then passed to a priority encoder. This sets the irq signal to the xap4 if any of the enabled interrupts are active and also sets irq num 3 0 to indicate the number of the highest priority active interrupt. The example IVC implements a straightforward fixed priority scheme with interrupt 7 being the highest priority and interrupt 0 being the lowest. This can of course be modified if a more complex priority scheme is required such as a round robin or a hybrid scheme.

When xap4 single detects irq set high and it is in the appropriate mode any mode except NMI Mode it will vector to the interrupt at the end of the next instruction. It uses the value provided by irq num to create a branch address into the Interrupt Vector Table IVT . This branch address is simply 0x40 irq num 4 .

In the example IVC nmi is connected to ivc status 8 . Since this is derived from interrupt 8 which is not used by the example IVC nmi is always inactive. If the NMI function is required by the ASIC designer it should be connected to the desired signals ensure that the sources are properly synchronised to clk .

The xap4 single module samples irq and irq num on the posedge of clk. It expects these to remain valid until it has branched to the IVT and interrupt handler software has written to the IVC to clear the respective bit in the ivc status register. It is not necessary that irq num remain stable throughout this period the IVC may change irq num to reflect the arrival of another interrupt with higher priority an example of this is shown later in sections 0 and 0 . However any change on irq num must settle in time for xap4 single to sample it reliably on each posedge of clk.

The XAP4 tests for exceptions and interrupts at the posedge of clk at the end of each instruction and at the end of each transfer in a blkcp block copy or blkst block store instruction. If the XAP4 detects irq set interrupts are enabled in the FLAGS register the E bit is set and the XAP4 is in User Supervisor or Interrupt Mode it will take 4 clks to change to Interrupt Mode and branch to the appropriate entry in the IVT.

The XAP4 gives highest priority to exceptions if in User Mode then to interrupts if in User Supervisor or Interrupt Mode and finally lowest priority to nmi in any mode . This means that if an interrupt arrives in User Mode just as an exception occurs the XAP4 will process the exception first. It does this by switching to Supervisor Mode and clearing the E bit in the FLAGS register which disables interrupts. The exception handling code must be designed to re enable interrupts as soon as it can safely be interrupted. When it does so the exception handler will be interrupted by the pending interrupt which will then cause XAP4 to go from Supervisor Mode to Interrupt Mode and begin servicing the interrupt.

The minimum interrupt latency is therefore 4 clk cycles assuming that irq is asserted just as an instruction is completing that the instruction does not generate a User Mode exception and that the system is using zero wait state memory. The maximum interrupt response time is 4 N M where N is the number of memory wait states and M is the length of the longest atomic instruction. This assumes that 

At clock edge t interrupt 4 arrives at the IVC and sets ivc status 4 high. Some time later xap4 single recognises the interrupt disables further interrupts and branches to the IVT for interrupt 4 . Some time later at clock edge t interrupt 7 arrives at the IVC and sets ivc status 7 high which changes irq num to reference this higher priority interrupt. Some time later at clock edge t the interrupt handler software sets ivc clear 4 high which clears ivc status 4 . However this does not remove irq which is still set due to interrupt 7 . When the interrupt handler software executes an irqe instruction to re enable interrupts it will now recognise this second interrupt and branch to its interrupt handler code.

In this second case a higher priority interrupt arrives before the XAP4 recognises the first interrupt and therefore gets serviced first. As for case 1 the first lower priority interrupt is interrupt 4 and the second higher priority interrupt is interrupt 7 and we will assume that both are already enabled in the IVC see .

At clock edge t interrupt 4 arrives at the IVC and sets ivc status 4 high. Some time later at clock edge t interrupt 7 arrives at the IVC and sets ivc status 7 high which changes irq num to reference this higher priority interrupt. Some time later xap4 single recognises the interrupt disables further interrupts and branches to the IVT for interrupt 7 . Some time later at clock edge t the interrupt handler software sets ivc clear 7 high which clears ivc status 7 . However this does not remove irq which is still set due to interrupt 4 . When the interrupt handler software executes an irqe instruction to re enable interrupts it will now recognise the original first interrupt and branch to its interrupt handler code.

The xap4 single module samples nmi on the posedge of clk. Similarly to the interrupt clearing method described herein it is expected that the NMI handler will write to the IVC when it wishes to clear the captured nmi state in the IVC.

In some implementations an NMI may be considered a fatal error or a shutdown request recoverable only through a reset. In this case it would not be necessary for the IVC module to support a write to clear mechanism for nmi. Instead nmi could be left set high until cleared by a system reset.

The XAP4 tests for NMI at the posedge of clk at die end of each instruction and at the end of each transfer in a blkcp or blkst instruction. If the XAP4 detects nmi set and it is in User Supervisor or Interrupt Mode it will take 4 clks to change to NMI Mode and branch to the NMI entry in the IVT.

The XAP4 gives lowest priority to nmi behind exceptions and interrupts. This means that if an NMI arrives just as an interrupt or User Mode exception occurs the XAP4 will start to process the interrupt or exception first. It does this by switching to Interrupt or Supervisor Mode and clearing the E bit in the FLAGS register which disables interrupts. The XAP4 will then recognise the pending NMI switch to NMI Mode and begin servicing the NMI.

The minimum NMI latency is therefore 4 clk cycles assuming that nmi is asserted just as an instruction is completing that the system is using zero wait state memory and that there are no valid exceptions or interrupts to be acted upon. The maximum NMI response time is 7 N M where N is the number of memory wait states and M is the length of the longest atomic instruction. The initial 7 clks accounts for an exception or interrupt branch occurring first followed by the branch to the NMI. 

When the IVC detects a pulse on interrupt 8 at clock edge t it sets ivc status 8 high. This immediately sets nmi high this happens immediately because NMI is by definition always enabled . At the end of the next XAP4 instruction xap4 single recognises the NMI disables further interrupts and branches to the IVT. The branch address for an NMI 0x04. Some time later at clock edge t the nmi handler software writes to the ivc clear register and sets bit . This clears ivc status 8 which removes nmi.

Software breakpoints can be inserted by swapping normal instruction with the brk instruction in memory. The xIDE for XAP4 debugger uses this method whenever possible i.e. if programs are stored in RAM as there is no limit as to how many breakpoints can be used. However this method cannot be used with memory that does not support individual word writes nor does it support conditional breaks.

XAP4 also provides a hardware breakpoint capability. This can be used with any kind of memory because the memory itself is not modified. It can also support real time conditional breaks. However XAP4 only supports a single hardware breakpoint address. The xIDE for XAP4 debugger only uses this method when it is unable to use software breakpoints.

The XAP4 contains one breakpoint register BRK that holds the breakpoint address. This can be configured using the breakpoint enable register BRKE to stop the processor or cause an exception when an address is read written or executed. The BRK and BRKE registers can be accessed by privileged modes using the movr2b movb2r movs2r and movr2s instructions.

When a software or hardware breakpoint is detected by the XAP4 it can respond by taking an exception or by halting or by doing neither. The XAP4 will generate a break exception only if the XAP4 is in User Mode and the B flag in the FLAGS register is set. If these conditions are not met then the XAP4 will halt if the Run State set by the SIF interface is Run To Break. If this condition is also not met then the breakpoint will be ignored.

The XAP4 supports software controlled single stepping. If the T bit in the FLAGS register is set a single step exception will be triggered after every User Mode instruction. If there is another exception pending this will take precedence over the single step exception. This ensures that an exception caused by the instruction itself such as a DivideByZero exception is not lost when stepping The Link Register R will point to the next instruction to be executed and R will point to the instruction that caused the exception. This capability supports remote debugging and single stepping of User Mode applications.

In addition XAP4 supports hardware based single stepping when used with a SIF based debugger such as xIDE for XAP4 . When the Run State is set by the SIF interface to Single Step the XAP4 will execute one instruction and then stop. Similarly to software controlled single step the XAP4 will not stop immediately if there is an interrupt or exception pending instead it will process the interrupt or exception to the point where it is about to branch into the IVT. The next step will therefore execute the appropriate instruction in the IVT.

Block copy and block store instructions blkcp and blkst are non atomic instructions meaning that they can take an interrupt or exception after each transfer of the copy or store operation. This includes the ability to step through a block copy or store instruction one transfer at a time.

Single stepping on a brk instruction or a hardware execution breakpoint will cause the PC to remain unchanged until the break condition is removed or disabled.

The XAP4 provides a sif instruction that can be used to provide predictable time slots for non invasive debugger monitoring. In a typical application the user would insert one or more sif instructions in the code contiguous or dispersed to provide the desired debug bandwidth. When the XAP4 encounters a sif instruction and is not in User Mode it sends a signal to the SIF interface that a fixed length time slot is available for a single SIF access. If there is a SIF access waiting it will use this time slot to read or write memory space or read a XAP4 register. At the end of the time slot the XAP4 continues with the next instruction.

The length of the sif instruction is configured according to the maximum number of wait states that may be encountered by the sif access. This ensures that if a sif access does occur it will have completed by the end of its time slot Consequently the XAP4 program timing is unaffected by whether or not a sif access actually occurs during a sif instruction.

The sif instruction length can be tailored to the number of memory wait states by including a file called xap4 user constants.h This should include a statement to indicate the maximum number of memory wait states 

where N is a hexadecimal number in the range 0 to F 0 to 15 decimal . The actual number of clock cycles taken by the sif instruction is 

where MAX WAIT STATES is as defined above and PROG WAIT STATES is the number of wait states seen when accessing program memory. If the xap4 user constants.h file is not present then the XAP4 assumes that the default sif instruction length need only support zero wait state memory.

The processors and or interfaces as herein described preferably possess the ability to enable them to perform all of the functionality described in the appended set of claims and possess the structure necessary to achieve that functionality.

It will be understood that the present invention has been described above purely by way of example and modifications of detail can be made within the scope of the invention.

Each feature disclosed in the description and where appropriate the claims and drawings may be provided independently or in any appropriate combination.

