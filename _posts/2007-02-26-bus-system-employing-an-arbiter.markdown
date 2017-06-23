---

title: Bus system employing an arbiter
abstract: A method for operating a bus system, in particular in a microprocessor or microcontroller, and a semiconductor device for performing the method is disclosed. In one embodiment, for optimizing the order of accesses to the bus system, a method for operating a bus system includes at least one transmission channel, wherein the transmission channel connects at least two masters and at least one slave with one another. The masters are connected with an arbiter determining the order of accesses in which the masters access the transmission channel. The method provides that the arbiter takes into account meta information about planned accesses when determining the order of accesses. Meta information can further be stored and be referred to for subsequent determinations.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=07689746&OS=07689746&RS=07689746
owner: Infineon Technologies AG
number: 07689746
owner_city: Neubiberg
owner_country: DE
publication_date: 20070226
---
This Utility Patent Application claims priority to German Patent Application No. DE 10 2006 009 034.9 filed on Feb. 27 2006 which is incorporated herein by reference.

The invention relates to a method for operating a bus system in particular in a microprocessor or a microcontroller. Furthermore the invention relates to a semiconductor device that is suited to perform the method.

In electric or electronic systems individual system modules communicate via a transmission medium. The system modules may be different electronic devices arranged in a respective component for instance different semiconductor devices arranged in a single component. Furthermore they may be different device sub components in particular different components of a semiconductor device e.g. a memory and or computing circuit e.g. a microcontroller or microprocessor provided in one single device. The transmission medium may for instance be a bus or a switch system.

A bus or switch system may connect a plurality of devices or components that use the bus or switch system jointly.

Conventional bus or switch systems may consist of one or several partial systems for instance of a data bus for transmitting the actual payload and or a control bus for transmitting control data and or an address bus for transmitting address data. The data bus as well as the control bus and address bus may include one or several physical data lines each.

A bus or switch system may thus include several transmission channels for the transmission of data wherein a transmission channel can only be used by one of the connected devices at a time.

In the following such a transmission channel via which for instance payload or control data or address data can be transmitted and which only one connected device can access at a time will be referred to as a bus. A system that permits the simultaneous i.e. temporally parallel transmission of similar data via corresponding transmission channels will be referred to as a switch.

If a plurality of system modules are connected with each other via a bus they act either as a master or as a slave. A master is a system module that is adapted to start a communication on a bus and to actively access the bus to this end. A slave receives such communication or responds to it is however not adapted to start it independently without being requested. If for instance a processor and a memory are connected with each other via a bus the processor requests when making a read access to the memory the memory to provide data. The memory accepts this request and performs the read access and provides the desired data. The processor acts as a master starting the read access and the memory acts as a slave accepting and performing the read access.

In data processing or control systems in particular in computer as well as in microprocessor and microcontroller systems several system modules may be connected with each other via a bus wherein more than one system module acts as a master. If several masters simultaneously access the bus in an uncoordinated manner to communicate with one or several slaves they interfere with each other.

Thus there is the need to coordinate the accesses of the masters such that mutual interferences of the masters are prevented by only one master accessing the bus at a time.

The accesses to a bus are coordinated by an arbiter that is connected with every system module acting as a master and is adapted to exchange data therewith.

In accordance with a conventional method the arbiter may grant the access permission for instance in turns i.e. pursuant to a round robin method to the masters so that all masters are successively given the possibility of accessing the bus even if no necessity of access exists for them.

In accordance with a further conventional method the arbiter may use different information for determining the order of access to the bus. For evaluation of the information the arbiter includes the logic required for determining the order or access.

Before a master is capable of accessing the bus this master has to communicate the desired access to the arbiter. In the case of competing accesses to the bus the arbiter determines the order of accesses and informs a master when it is permitted to access the bus for performing the desired action.

In accordance with a further conventional method priorities may be assigned to the masters so that in the case of simultaneous and thus competing accesses it is always the master with the higher priority that is permitted to access the bus.

In complex bus or switch systems these methods do however not enable an optimum order for competing accesses to a bus so that they can be performed as quickly as possible and the bus or switch system is utilized as optimally as possible.

One embodiment of the invention provides an improved method for determining the order of access in the case of competing accesses to a bus or switch system.

One embodiment provides a method for operating a bus system. The bus system is defined to include at least one transmission channel at least two masters and at least one slave connecting at least two masters and at least one slave with one another via the transmission channel. An arbiter is coupled to the at least two masters and configured to determine the order of accesses in which the at least two masters access the transmission channel using at least one meta information about at least one access when determining the order of accesses.

In the following Detailed Description reference is made to the accompanying drawings which form a part hereof and in which is illustrated by way of illustration specific embodiments in which the invention may be practiced. In this regard directional terminology such as top bottom front back leading trailing etc. is used with reference to the orientation of the Figure s being described. Because components of embodiments of the present invention can be positioned in a number of different orientations the directional terminology is used for purposes of illustration and is in no way limiting. It is to be understood that other embodiments may be utilized and structural or logical changes may be made without departing from the scope of the present invention. The following detailed description therefore is not to be taken in a limiting sense and the scope of the present invention is defined by the appended claims.

In accordance with one embodiment of the invention there is a method for operating a bus system having at least one transmission channel wherein the transmission channel connects at least two masters and at least one slave with one another and wherein the masters are connected with an arbiter that determines the order of access according to which the masters access the transmission channel. When determining the order of access the arbiter takes into account at least one meta information about at least one access.

A meta information about an access is here information about the access. Thus a meta information describes or characterizes an access. Relevant meta information about an access is for instance the kind of access i.e. whether it is the matter of a read or write or control access or the target of the access e.g. which slave that is connected with the transmission channel is to be accessed. Further meta information may indicate the amount of data to be transmitted with the access or the presumable duration of a planned access.

The arbiter evaluates the meta information and determines whether due to the order of the accesses the accesses to be performed to the transmission channel can be performed more quickly altogether and whether the transmission channel can be better utilized by an order of access that can be determined by itself.

The meta information is given to the arbiter by each master that is connected with the transmission channel. The arbiter can store the meta information and take stored meta information into account when subsequently determining an order of access.

In accordance with a further embodiment of the invention there is suggested a semiconductor device having at least one transmission channel for transmitting data wherein the transmission channel connects at least two masters and one slave with one another and an arbiter for determining an order of access for accesses to the transmission channel. In this semiconductor device the masters are connected with the arbiter for transmitting meta information about an access.

Via the connection between the masters and the arbiter the masters communicate a planned access to the transmission channel to the master wherein meta information about a planned access is communicated to the arbiter. The arbiter thus receives information for instance about which master has to access which target i.e. a slave in which kind e.g. by a write or a read or a control access. In the case of temporally competing accesses the arbiter determines the meta information communicated so as to determine an order of accesses with which the accesses can be performed successively as quickly as possible and or wherein the transmission channel is better utilized.

In this embodiment the bus includes one transmission channel. In order to avoid mutual interferences only one master can access this transmission channel at a time. The slaves do not actively access the bus due to their property as slaves.

The first master may for instance be a CPU and the second master a memory controller e.g. a DMA controller. The first slave may for instance be a serial interface and the second slave an interface to another bus system for instance a CAN interface Controller Area Network .

All masters are further connected with an arbiter to communicate or receive information to or from it.

The directions of the arrows representing the connections of the masters and the slaves with the bus and of the masters with the arbiter indicate the direction in which a data exchange is triggered corresponding to the property as master or slave.

The open ends of the bus indicate that it is adapted to connect further masters and or further slaves.

In the instant embodiment the first master shall have a higher priority than the master so that the master is permitted to be the first to perform its access to the bus in the case of temporally competing accesses of the masters . Furthermore it is assumed that the slaves require 3 clock cycles each for performing read and write accesses.

The slaves include a write buffer for performing write accesses. In the case of a write access of a master the data to be written are initially written into the write buffer by the slave so that this action to the outside i.e. on the bus is terminated as soon as the data have been fully stored in the write buffer. The further storing of the data from the write buffer of the slaves to the final memory location takes place in a conventional manner within the slave. The bus is thus released as soon as the data have been stored in the write buffer. Since it is assumed that the data to be written can be transmitted with one bus cycle the bus is only occupied for one cycle by a master during a write access. Correspondingly a write access lasts one cycle for a master .

For a read access it is assumed in the instant embodiment that the master waits until the slave has read the desired data and is able to transmit same to the master via the bus . For a read access the bus is thus occupied for a duration of 3 cycles.

To be able to access the bus and thus a slave the two masters communicate an access request each to the arbiter via the respective communication.

In the instant embodiment the first master requires a read access to the first slave the second master requires a write access to the second slave .

In accordance with a conventional method for determining the order of accesses to the bus the masters each communicate to the arbiter that they have to access the bus without however informing the arbiter of the kind of the desired access i.e. whether it is a read or a write access nor the target of the access. Due to the access priority of the first master the arbiter will permit the first master to be the first to access the bus . As soon as the bus is free again the second master may perform its write access to the slave . If the second master requests another write access to the second slave this may be performed subsequently to the first write access of the second master to the second slave .

Table 1 illustrates the order and duration of these actions in accordance with the conventional method.

In the cycles to the first master i.e. M performs its read access entered in the Table as Read S to the first slave i.e. S . During these three cycles the bus is accessed by the first master .

The write access of the second master entered in Table 1 as Write S to the second slave starts in the fourth cycle. Since the second write access of the second master M to the second slave S may only start when the first write access within the first slave has been terminated the second write access entered in the Table 1 as Write S starts in the seventh cycle. Although the master only requires one cycle for transmitting the data to be written to the second slave the bus remains in the meantime in which the second master waits that the second slave terminates the first write access accessed by the second master . All in all the processing of this transaction thus lasts bus clocks.

Unlike the afore described conventional method the masters in accordance with the new method not only communicate to the arbiter when requesting access that they have to access the bus but they also inform it about the kind of the access and which slave will be the target of the access. The arbiter takes this information into account when determining the order of access. Since the arbiter knows that a write access only lasts one bus cycle the arbiter determines the more favorable order of accesses illustrated in Table 2.

With the order of access determined here the first write access of the second master to the second slave is preferred contrary to the priority of the first master . The bus is occupied for this write access for one cycle by the second master M . With the next bus clock i.e. cycle the first master starts its read access to the first slave . The bus is thus occupied for three cycles i.e. cycles to by the first master . The arbiter may grant the second master the access to the bus when the bus is free again and the second slave has internally processed the first write access. Thus the second master starts the second write access to the second slave in cycle . Since only one cycle is required for this write access on the bus the masters have processed the planned accesses after 5 bus cycles already.

By using the new method the bus is better utilized on the one hand and the masters all in all have to wait a shorter time on the other hand. For the processing of the planned accesses less time is thus required.

The PMI is via the connection connected with a not illustrated Data Management Unit DMU via the connection with a not illustrated Program Management Unit PMU and via the connection with a Flash Application Programming Interface FAPI .

DMU PMU and FAPI each act as masters that are adapted to actively access a Flash Access Switch . Via the Flash Access Switch code and data accesses can simultaneously be performed to a first memory module Flash Module a second memory module Flash Module and a third memory module Flash Module N wherein one memory module at a time can be accessed in reading or writing either with a code or a data access.

The memory modules and act here as slaves which the masters i.e. here the DMU and the PMU and the FAPI can access via the Flash Access Switch . To this end the FAPI is directly connected with the Flash Access Switch the accesses to the switch of the DMU and the PMU are transmitted by the PMI via the connections and to the Flash Access Switch .

The access to a memory module or is controlled via a respective busy signal that is set by a memory module as long as it performs an action i.e. is still busy performing an access.

For read accesses to a memory module there is however an acceleration for low system cycle frequencies. The arbiter may permit that a master sends a read access to a memory module when a previously started read access is still being processed by the same memory module. This however only applies for directly successive read accesses. The respective memory module or accepts the second read access. Internally however the memory module processes the read accesses sequentially so that the second read instruction is executed subsequent to the first one.

If a memory module performs an access of a different kind of access i.e. if for instance a master accesses the memory module in writing the arbiter has to observe the busy signal of the memory module and may permit an access to the respective memory module only if the busy signal of the memory module is no longer set. The sending of a second access request to a memory module is thus only admissible with directly successive read accesses.

For optimizing the accesses to the memory modules and the masters i.e. the DMU the PMU and the FAPI do not only communicate to the PMI that integrates the function of the arbiter that an access to the switch is required. Rather each master now also communicates to the PMI the information about the kind of the desired access i.e. for instance whether it is a read or a write access and or the target of the desired access i.e. which slave or the master wants to access.

The arbiter logic in the PMI evaluates this information for each of the slaves or and for the current access request and stores the information to be able to access it for the next decision about an access.

The information of the masters about the kind and the target of a desired access thus make it possible that the PMI permits two then temporally parallel read accesses to a memory module i.e. a slave at a time.

Without this information about the kind and the target of an access the PMI would not be able to examine whether the access that is currently requested for a slave and the access performed before are each read accesses so that one access to a memory module would have to be prevented at any rate until the busy signal of the memory module is no longer set.

The logic of the arbiter here integrated in the PMI is mapped as a finite state machine in the instant embodiment. Since the accesses to the slaves and i.e. the memory modules may take place independently of each other one respective finite state machine is provide for every memory module.

Such a finite state machine may assume six states that will be described for one memory module in the following.

In the first state NO ACCESS no master accesses the memory module. The memory module has not set the busy signal so that an access to the memory module can immediately be permitted independently of the kind of access. If two masters should compete for the access i.e. simultaneously request an access the order of accesses is determined in accordance with the priority rules.

The state machine assumes the second state NO ACCESS AFTER FLASH READ if the last access to the memory module was a read access i.e. a code or data read access. Although the read access is terminated the busy signal of the memory module is for internal reasons of the memory module still set. In this state an access request for a read access to the memory module may be permitted although the busy signal is still set.

In the third state FAPI DATA SFR ACCESS access to the memory module is permitted to the FAPI . In this state the FAPI accesses specific registers Special Function Registers SFR . A further access to the memory module is only admissible if the busy signal of the memory module is no longer set. In this state a simultaneous reading access to the memory module is not admissible.

In the fourth state DMU SFR ACCESS the DMU is granted an exclusive access to the memory module which also accesses Special Function Registers SFR . In analogy to the third state a further access to the memory module is only permitted if the busy signal of the memory module is no longer set.

The state machine assumes the fifth state DMU DATA ACCESS when the DMU accesses the memory module in reading i.e. with a data read access. In this state an immediate second read access to the memory module is admissible so that it need not be waited until the busy signal is reset. Access requests of other kinds i.e. requests for write accesses are accepted and permitted in the case of several requests by taking into account the priorities of the masters if the busy signal is no longer set.

Likewise an immediate reading access is permitted in the sixth state PMU CODE ACCESS . In this state the PMU accesses the memory module in reading so that a further reading access to the memory module can be permitted without the resetting of the busy signal having to be waited for. Access requests of other kinds i.e. for instance in writing are permitted in analogy to the kind of treatment in the fifth state.

Although specific embodiments have been illustrated and described herein it will be appreciated by those of ordinary skill in the art that a variety of alternate and or equivalent implementations may be substituted for the specific embodiments illustrated and described without departing from the scope of the present invention. This application is intended to cover any adaptations or variations of the specific embodiments discussed herein. Therefore it is intended that this invention be limited only by the claims and the equivalents thereof.

