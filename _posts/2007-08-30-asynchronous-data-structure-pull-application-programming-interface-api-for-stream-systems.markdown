---

title: Asynchronous data structure pull application programming interface (API) for stream systems
abstract: Provided are techniques for processing data items. A limit on the number of dequeue operations allowed in a current step of processing for a queue-like data structure is set, wherein the number of allowed dequeue operations limit at least one of an amount of CPU resources and an amount of memory resources to be used by an operator. The operator to perform processing is selected and the operator is activated by passing control to the operator, which then dequeues data constrained by the limits set. In response to receiving control back from the operator, the data structure size is examined to determine whether the operator made forward progress in that the operator enqueued or dequeued at least one data item.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08141080&OS=08141080&RS=08141080
owner: International Business Machines Corporation
number: 08141080
owner_city: Armonk
owner_country: US
publication_date: 20070830
---
Embodiments of the invention relate to an asynchronous data structure pull Application Programming Interface API for stream systems.

A process may be described as a data flow diagram. A process may be constructed from the following components a data flow diagram operators and arcs. A data flow diagram may be described as a directed graph where the vertices boxes of the graph are called operators and the arcs describe directional flow of data. The data flow diagram describes the data as the data flows from various data sources through the different operators to various data targets. Operators are able to read data from an external resource write data to an external resource and or apply data transformations while doing so. In general operators are able to consume data from every incoming arc and can produce data on every outgoing arc. Many operators are provided as built in operators to provide common data access and transformations while other operators may be created by the user and easily integrated into the system. Arcs represent flow of data between two connected operators.

A continuous process may be described as a process that reads from continuous data sources i.e. data sources that provide data continually and generates result data corresponding to input data as the input data becomes available. A system that runs as a continuous process is a stream system . A stream system may be represented by a data flow diagram.

A scheduler may be described as a runtime component that activates the operators of the process. The scheduler s job is to allow the process to produce data while minimizing consumed resources such as memory and CPU and while maximizing Quality of Service QoS measurements such as latency and throughput.

While the data is streaming into and out of the operators the scheduler needs to decide in every step which operator or operators to activate. In particular the execution time of a process is composed from a finite number of scheduler steps. In the beginning of each step the scheduler decides which operators will be activated during that step.

In event based methods a routine or method is invoked for each data item received or possibly for each available output location made available. However some such event based methods do not provide a desired coarse granularity. A drawback of the event based approach is overhead due to lack of granularity control. A method invocation is required for each data item delivered to the operator and the operator code restores and then saves back any state needed between the receipt of every data item received.

With multi threading use of multiple threads incurs the overhead of stack allocation and switching which is more costly than ordinary procedure calling. Moreover multi threading is disallowed in some execution frameworks e.g. Java 2 Platform Enterprise Edition J2EE application servers Java and J2EE are trademarks of Sun Microsystems Inc. in the United States other countries or both .

In general use of threads may be considered problematic because such use destroys most composition properties of programs. For example in order to use a library of software the developer needs to know whether or not the library uses threads and how the threads are used in order to know whether the library can be used from another context that uses threads.

Finally some third party code that needs to be included in operators may simply not be thread safe. Hosting this code requires either an entirely separate operating system level process or requires a single threaded operator framework implementation.

One of the desirable properties of a dataflow system i.e. a system that processes data flow diagrams is the ability to avoid use of thread based concurrency. For example J2EE application server based deployments disallow use of threads by applications. Hence it is the nature of single threaded systems that once the scheduler activates an operator and passes control to the operator it is up to the operator to decide when to return control to the scheduler. That is the scheduler cannot interrupt the operator or cancel activation of the operator or even initiate communication with the operator until the operator decides to end the current activation cycle. Furthermore the scheduler has no knowledge of the nature of the logic implemented by the operators. Thus a kind of cooperative multitasking is needed.

Provided are a method computer program product and system for processing data items. A number of allowed dequeue operations allowed in a current step of processing for a data structure is set wherein the number of allowed dequeue operations limit at least one of an amount of CPU resources and an amount of memory resources to be used by an operator. The operator to perform processing is selected. The operator is activated by passing control to the operator wherein the operator is capable of consuming data from one or more input arcs and producing data on one or more output arcs. In response to receiving control back from the operator the data structure size is examined to determine whether the operator enqueued or dequeued at least one data item.

In the following description reference is made to the accompanying drawings which form a part hereof and which illustrate several embodiments of the invention. It is understood that other embodiments may be utilized and structural and operational changes may be made without departing from the scope of the invention.

Given a single threaded scheduler embodiments provide an operator API to be used by the scheduler that supports the following 

3. In a single activation an operator can consume data from each input arc and produce data arbitrarily on each output arc.

4. One activation uses limited CPU resources defined by the scheduler. That is the operator s activation duration is determined by scheduler and not by the operator.

5. An operator does not wait for data that has not arrived. That is the operator code does not block the activating thread either for data to arrive or for output acknowledgments nor can the operator poll the inputs repeatedly until data arrives.

6. The scheduler is able to enforce forward progress. That is the scheduler enforces that data was consumed or data was produced or both by the operator during an activation.

7. An activation uses limited memory resources defined by the scheduler for incoming and outgoing data.

8. Granularity of activations may be larger than one data item In any single activation an operator may produce and consume multiple items within scheduler defined resource limitations.

9. The scheduler may multiplex multiple operators sequentially on a single thread of control using a single stack. In certain embodiments operators do not have their own threads or stack space. In certain other embodiments operators may have their own threads or stack space i.e. such embodiments use multiple threads stacks .

The pretender data structures do not behave as conventional queues. For example if the scheduling requirements are such that an active operator that consumes a pretender data structure needs to be deactivated the pretender data structure pretends to be empty. This means an operator cannot keep running on more data independently of the scheduler i.e. the operator cannot continue processing without returning control to the scheduler which may then activate that operator again later in a subsequent step. . In conventional solutions the operator could spin forever in an infinite loop e.g. either because of a flaw in the operator logic that is not detected or because of a lack of the level of cooperation required from the operator . However within embodiments the operator is not able to get more data to continue work on unless the operator cooperates with the framework by returning control to the scheduler after the operator has been activated and done some processing. By way of the pretender data structure s behavior the scheduler is able to enforce the required level of cooperation on the operator.

Table 1 provides the definitions of terms used in the flow charts described in B A B and where the scheduler may be said to perform processing in steps 

In block the pretender data structure sets the scheduler step in which the operator had a last successful Dequeue operation to be the current step i.e. LastDeqStep CurrentStep . Processing continues to block and the pretender data structure sets the number of successful Dequeue operations done in the current step to zero i.e. CurrentDequeues 0 . Processing continues to block and the pretender data structure sets the number of unsuccessful Dequeue operations done in the current step to zero i.e. numFailedAttempts 0 . From block processing continues to block .

In block the pretender data structure determines whether a data structure is empty. If so processing continues to block otherwise processing continues to block .

In block the pretender data structure increments the number of unsuccessful Dequeue operations done in the current step by one i.e. numFailedAttempts . Processing continues to block the pretender data structure returns NULL in response to the operator request for the new data item because the data structure is empty .

In block the pretender data structure determines whether the number of successful Dequeue operations done in the current step are less than the number of allowed Dequeue operations for the current step i.e. CurrentDequeues

In block the pretender data structure increments the number of successful Dequeue operations done in the current step i.e. CurrentDequeues . Processing continues to block and the pretender data structure returns a data item i.e. dequeues a data item from the data structure and returns that data item return q.Dequeue .

Returning to in block the pretender data structure determines whether the number of unsuccessful Dequeue operations done in the current step is one. If so processing continues to block otherwise processing continues to block . In block the pretender data structure raises an error e.g. by throwing an exception . That is to ensure that the operator does not wait for data that has not arrived i.e. the operator code cannot block either for data to arrive or for output acknowledgments if the operator tries to perform a Dequeue operation after an unsuccessful Dequeue operation in the same step without returning to the scheduler an error is raised.

In block the pretender data structure sets the scheduler step in which the operator had a last successful Dequeue operation to be the current step i.e. LastDeqStep CurrentStep . Processing continues to block and the pretender data structure sets the number of successful Dequeue operations done in the current step to zero i.e. CurrentDequeues 0 . Processing continues to block and the pretender data structure sets the number of unsuccessful Dequeue operations done in the current step to zero i.e. numFailedAttempts 0 . From block processing continues to block .

In block the pretender data structure determines whether a data structure is empty. If so processing continues to block otherwise processing continues to block .

In block the pretender data structure returns TRUE to the operator in response to the request asking whether the data structure is empty.

In block the pretender data structure determines whether the number of successful Dequeue operations done in the current step are greater than or equal to the number of allowed Dequeue operations for the current step i.e. CurrentDequeues AllowedDequeues . If so processing continues to block otherwise processing continues to block . In block the pretender data structure returns FALSE to the operator in response to the request asking whether the data structure is empty. That is if the number of actual Dequeue operations performed by the operator in a step equal or exceed the number of allowed Dequeue operations for that operator in the step then the pretender data structure returns an indication that the data structure is empty even when the data structure is not actually empty. Hence the operator cannot obtain data and so must return control to the scheduler.

In block the pretender data structure sets the scheduler step in which the operator had a last successful Dequeue operation to be the current step i.e. LastDeqStep CurrentStep . Processing continues to block and the pretender data structure sets the number of successful Dequeue operations done in the current step to zero i.e. CurrentDequeues 0 . Processing continues to block and the pretender data structure sets the number of unsuccessful Dequeue operations done in the current step to zero i.e. numFailedAttempts 0 . From block processing continues to block .

In block the pretender data structure returns a value in response to the request asking the size of the data structure to the operator . In particular rather than providing the actual size of the data structure the pretender data structure returns a value of the maximum of the number of allowed Dequeue operations minus the number of successful Dequeue operations done in the current step i.e. Max AllowedDequeues CurrentDequeues q.size .

In block the scheduler selects any operator . In certain embodiments the scheduler is able to multiplex multiple operators on a single thread of control using a single stack and there is no need for operators to have their own threads or stack space although embodiments which use multiple threads stacks are not precluded . Since the operators return control to the scheduler after every step in each step the scheduler can select a particular operator to activate i.e. the particular operator can be the same or different operator than the operator that returned control most recently . Thus the scheduler uses a single thread of control with a single stack for any number of operators .

Next the operator is activated thereby allowing the operator to consume or produce data. In particular the scheduler calls the operator activates method block . To activate the operator by allowing the operator to produce data the scheduler calls the operator activate method.

Block is entered when the operator activate call returns. In block the scheduler examines the data structure size to determine whether the operator enqueued or dequeued at least one data item. That is to enable the scheduler to enforce forward progress data was consumed data was produced the scheduler is able to examine the data structure sizes and decide whether the operator has made progress or not. In block the scheduler ensures forward progress by checking on return from an operator activation whether the operator did in fact dequeue or enqueue at least one data item. In certain embodiments if there is no forward progress an exception is thrown by the error block . If there is forward progress then at block CurrentStep is incremented e.g. currentStep and processing loops back to block .

With reference to the operator in any single activation to enable an operator to produce and consume multiple items while not exceeding resource limitations the scheduler sets the AllowedDequeues value to a number greater than one and the operator is able to consume multiple items and produce multiple items before returning control to the scheduler .

To ensure that the operator does not wait for data that has not arrived i.e. the operator code cannot block either for data to arrive or for output acknowledgments if the operator tries to perform a Dequeue operation after an unsuccessful Dequeue operation in the same step without returning to the scheduler an error is raised by the pretender data structure . This prevents the operator from implementing a poll algorithm. A poll algorithm may be described as a looping and repeating of a method question until the desired result is obtained. This results in poor performance behavior since the CPU cycles are wasted on the repeats. Also the operator code cannot block since the operator has to return control to the scheduler to enable the scheduler to change the current step count which allows the Dequeue operation to deliver data again during the next activate call of this operator.

As to pretender data structures embodiments overload a Dequeue operation i.e. Dequeue result so that the scheduler is able to control the granularity of action of the operator for input data and overload an Enqueue operation i.e. Enqueue result so that the scheduler is able to suggest or control granularity of action of the operator for output data. For example the AllowedDequeues variable may be used for input granularity while an AllowedEnqueues variable may be used for output granularity.

Within embodiments a scheduler decides what the granularity of action of the operators are by controlling the pretender data structures.

The scheduler prevents busy waiting inside operators by controlling pretender queues so that their return status does not return to data available once it has become data unavailable during any single activation. For example an operator asks whether a data structure is empty more than once in a single activation step it is determined that the operator is attempting to implement polling and an exception is thrown.

Embodiments provide a separate technique for determining whether the end of data has been actually reached to distinguish this from the case in which the scheduler has decided not to make data available or data is actually not available. In certain embodiments if a Dequeue operation returns null it is determined that either the operator cannot consume any more data or data has ended. To distinguish between the two an API method of the pretender data structure the wasLast method returns true if this is the real final end of data and not just a temporary end for purposes of control by the scheduler or temporary unavailability of data.

As to output direction for finite size vectors embodiments provide a method to close the queue and end the data stream.

Embodiments combine with co routines to allow use of a blocking style API where a co routine with a separate stack i.e. not the scheduler thread s stack is used when running the operator logic.

Embodiments use large values for AllowedDequeues to enable the activated operator to enter a loop and handle data for a substantial period of time keeping intermediate data in local state thereby reducing the scheduling overhead to a small percentage of overall data processing overhead. This allows amortizing the cost of scheduling by allowing the operator to have an autonomic run over a quota determined by the scheduler. This results in a higher performance of the overall system.

Embodiments enable hosting third party library code in a single threaded environment thereby avoiding the overhead of separate operating system level processes.

Embodiments allow operators to use regular function calls when processing the data rather than the event driven procedures that are used in some of the conventional approaches. This means operators can specify the way their logic traverses the data rather than having to traverse the data however it arrives which is characteristic of the event driven style.

For any data flow system e.g. an IBM WebSphere DataStage system an IBM WebSphere Message Broker system or an IBM DB2 Query processor that desires the ability to schedule operators adaptively to achieve high performance embodiments simplify the construction of those systems.

The described operations may be implemented as a method computer program product or apparatus using standard programming and or engineering techniques to produce software firmware hardware or any combination thereof.

Each of the embodiments may take the form of an entirely hardware embodiment an entirely software embodiment or an embodiment containing both hardware and software elements. The embodiments may be implemented in software which includes but is not limited to firmware resident software microcode etc.

Furthermore the embodiments may take the form of a computer program product accessible from a computer usable or computer readable medium providing program code for use by or in connection with a computer or any instruction execution system. For the purposes of this description a computer usable or computer readable medium may be any apparatus that may contain store communicate propagate or transport the program for use by or in connection with the instruction execution system apparatus or device.

The described operations may be implemented as code maintained in a computer usable or computer readable medium where a processor may read and execute the code from the computer readable medium. The medium may be an electronic magnetic optical electromagnetic infrared or semiconductor system or apparatus or device or a propagation medium. Examples of a computer readable medium include a semiconductor or solid state memory magnetic tape a removable computer diskette a rigid magnetic disk an optical disk magnetic storage medium e.g. hard disk drives floppy disks tape etc. volatile and non volatile memory devices e.g. a random access memory RAM DRAMs SRAMs a read only memory ROM PROMs EEPROMs Flash Memory firmware programmable logic etc. . Current examples of optical disks include compact disk read only memory CD ROM compact disk read write CD R W and DVD.

The code implementing the described operations may further be implemented in hardware logic e.g. an integrated circuit chip Programmable Gate Array PGA Application Specific Integrated Circuit ASIC etc. . Still further the code implementing the described operations may be implemented in transmission signals where transmission signals may propagate through space or through a transmission media such as an optical fiber copper wire etc. The transmission signals in which the code or logic is encoded may further comprise a wireless signal satellite transmission radio waves infrared signals Bluetooth etc. The transmission signals in which the code or logic is encoded is capable of being transmitted by a transmitting station and received by a receiving station where the code or logic encoded in the transmission signal may be decoded and stored in hardware or a computer readable medium at the receiving and transmitting stations or devices.

A computer program product may comprise computer useable or computer readable media hardware logic and or transmission signals in which code may be implemented. Of course those skilled in the art will recognize that many modifications may be made to this configuration without departing from the scope of the embodiments and that the computer program product may comprise any suitable information bearing medium known in the art.

The term logic may include by way of example software hardware firmware and or combinations of software and hardware.

Certain implementations may be directed to a method for deploying computing infrastructure by a person or automated processing integrating computer readable code into a computing system wherein the code in combination with the computing system is enabled to perform the operations of the described implementations.

The logic of B A B and describes specific operations occurring in a particular order. In alternative embodiments certain of the logic operations may be performed in a different order modified or removed. Moreover operations may be added to the above described logic and still conform to the described embodiments. Further operations described herein may occur sequentially or certain operations may be processed in parallel or operations described as performed by a single process may be performed by distributed processes.

The illustrated logic of B A B and may be implemented in software hardware programmable and non programmable gate array logic or in some combination of hardware software or gate array logic.

Input Output I O devices including but not limited to keyboards displays pointing devices etc. may be coupled to the system either directly or through intervening I O controllers .

Network adapters may also be coupled to the system to enable the data processing system to become coupled to other data processing systems or remote printers or storage devices through intervening private or public networks. Modems cable modem and Ethernet cards are just a few of the currently available types of network adapters .

The system architecture may be coupled to storage e.g. a non volatile storage area such as magnetic disk drives optical disk drives a tape drive etc. . The storage may comprise an internal storage device or an attached or network accessible storage. Computer programs in storage may be loaded into the memory elements and executed by a processor in a manner known in the art.

The system architecture may include fewer components than illustrated additional components not illustrated herein or some combination of the components illustrated and additional components. The system architecture may comprise any computing device known in the art such as a mainframe server personal computer workstation laptop handheld computer telephony device network appliance virtualization device storage controller etc.

The foregoing description of embodiments of the invention has been presented for the purposes of illustration and description. It is not intended to be exhaustive or to limit the embodiments to the precise form disclosed. Many modifications and variations are possible in light of the above teaching. It is intended that the scope of the embodiments be limited not by this detailed description but rather by the claims appended hereto. The above specification examples and data provide a complete description of the manufacture and use of the composition of the embodiments. Since many embodiments may be made without departing from the spirit and scope of the embodiments the embodiments reside in the claims hereinafter appended or any subsequently filed claims and their equivalents.

