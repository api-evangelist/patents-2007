---

title: Virtual machine location system, virtual machine location method, program, virtual machine manager, and server
abstract: A virtual machine location system includes a resource conflict detection unit for detecting a resource conflict using measurement data regarding a resource usage state of the entirety of a single server and a resource usage state of virtual machines running on the server, and a virtual machine relocation determination unit for transferring the virtual machine on the server for which a resource conflict has been detected to another server having a lower resource usage rate are included.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08346933&OS=08346933&RS=08346933
owner: NEC Corporation
number: 08346933
owner_city: Tokyo
owner_country: JP
publication_date: 20071122
---
The present invention relates to a virtual machine location system and a virtual machine location method and in particular to a virtual machine location system a virtual machine location method a virtual machine manager a program and a server for changing the location of a virtual machine based on a resource conflict situation during operation.

A virtual machine VM technique which causes a plurality of operating systems OS to run on a single server a computer such as a workstation a personal computer and a server only machine so that one computer may be virtually used as a plurality of servers has been known. As products using this type of technique VMWare Registered Trademark ESX Server from VMWare Inc Virtual Server from Microsoft Registered Trademark Corporation and Xen from XenSource Inc. US have been known. By issuing a command to create a virtual machine these products can create new virtual machines on a server.

In addition a technique of transferring a virtual machine created on a server to another server in a distributed processor environment where a plurality of servers are connected through a network has been known. The technique of transferring a virtual machine has been described in Japanese Patent Application Laid Open Patent Publication No. Hei 10 283210 Patent Document 1 for example. Such a technique provides a function for transferring a virtual machine referred to as vMotion for VMware Registered Trademark and as migration for Xen.

In such an environment where a plurality of servers are distributed since each virtual machine has a different performance requirement which virtual machine is located on which server hereinafter referred to as location of virtual machine affects the effective performance of the virtual machine.

As a method of determining the location of a virtual machine a method has been known in which based on measurement data indicating the performance of existing virtual machines the sum of the performance values is calculated for each of the possible combinations of respective virtual machines and respective servers and each virtual machine is relocated in order to maximize the sum which has been described in Japanese Patent Application Laid Open Patent Publication No. 2005 115653 Patent Document 2 .

As described above the techniques described in the patent documents determine the location of a virtual machine based on past performance data concerning a virtual machine to be located.

A first problem of the method is that the quick relocation of a virtual machine in response to a change in load on the virtual machine cannot be achieved.

The reason is that a sudden increase in load cannot be detected because the performance data has to be collected over a fixed period of time typically several minutes to several hours .

A second problem is that a situation occurs in which a system constructed on a virtual machine cannot be temporarily used.

The reason is that the system is temporarily stopped in the course of relocation because all the existing virtual machines become targets of the relocation.

An exemplary object of the present invention is to provide a virtual machine location system capable of maintaining the location of an optimal virtual machine by relocating the virtual machine immediately when performance degradation occurred because of a sudden increase in load.

Another exemplary object of the present invention is to provide a virtual machine location system capable of relocating a virtual machine with a system on the virtual machine being run by imposing a limitation on virtual machines which become targets of the relocation.

According to an exemplary aspect of the invention a virtual machine location system includes a resource conflict detection unit for detecting a resource conflict using measurement data regarding a resource usage state of the entirety of a single server and a resource usage state of a virtual machine running on said server and a virtual machine relocation determination unit for transferring said virtual machine on said server for which said resource conflict has been detected to another server having a lower resource usage rate.

A first effect is that a virtual machine can be relocated immediately in response to a sudden change in load.

A second effect is that a virtual machine can be relocated without stopping a system running on the virtual machine.

A virtual machine location system according to a first exemplary embodiment of the present invention will now be described in detail with reference to the drawings.

Referring to the virtual machine location system according to the present exemplary embodiment comprises a virtual machine manager a management terminal and a plurality of servers .

The virtual machine manager is a computer controlled by a program and includes a resource usage state collection unit a resource conflict detection unit a virtual machine VM relocation determination unit and a resource usage state storage unit .

The management terminal is connected to the virtual machine manager and is a terminal device console operated by a system administrator. The management terminal usually comprises a display unit display monitor a key board and a mouse. Referring to the management terminal is connected directly to the virtual machine manager but may be connected through a network .

The server is a computer having the ability to activate one or more virtual machines and includes a resource usage state collection unit a virtual machine control unit and a plurality of virtual machines .

The virtual machine manager and the servers and in some cases the management terminal are interconnected through the network . The network may be a local area network LAN such as Ethernet Registered Trademark a wide area network WAN such as the internet or may be a combination of them.

The resource usage state collection unit has a function for acquiring resource usage state data not shown indicating the latest resource usage state from a plurality of resource usage state acquisition units through the network and a function for storing the acquired resource usage state data in the resource usage state storage unit .

A typical example of the resource usage state data is data including a CPU processor central processing unit usage rate regarding the entire server a CPU usage rate used by each of the virtual machines running on the server memory main memory usage and an input output I O bandwidth.

The resource conflict detection unit has a function for determining whether or not there is a resource conflict condition based on the resource usage state data collected from the resource usage state acquisition unit by the resource usage state collection unit .

A resource conflict condition means that two or more virtual machines running on a single server are in a highly loaded states with respect to the same type of resource. As a specific example of a decision criterion of the resource conflict condition a condition in which the CPU usage rate regarding the entirety of the single server has reached a predetermined threshold e.g. 80 and the CPU usage rates of at least two of the virtual machines running on the single server have reached another predetermined threshold e.g. 10 is determined to be a resource conflict condition.

The virtual machine relocation determination unit has a function for determining a transfer destination server for the virtual machine running on the server which was determined to be in the resource conflict condition by the resource conflict detection unit and controlling the transfer of the virtual machine according to the determination. In this case an example of a method of determining the transfer destination server includes selecting a server having the lowest CPU usage rate regarding the entire server .

The resource usage state acquisition unit has a function for regularly acquiring the resource usage state data regarding the server and the virtual machines running on the server including a CPU usage rate memory main memory usage and an input output I O bandwidth and sending the result to the resource information collection unit .

The virtual machine control unit has a function for controlling the transfer of the existing virtual machine according to the command from the virtual machine relocation determination unit . This function typically performs processing such as storage of the running state of the virtual machine and halting of the virtual machine on the transfer source server and restoration of the running state of the virtual machine and activation of the virtual machine on the transfer destination server .

The above described resource usage state acquisition unit and the virtual machine control unit use functions provided by the above described virtual machine products e.g. VMware Registered Trademark Microsoft Registered Trademark Virtual Server and Xen .

The CPU usage rate regarding the entire server and the CPU usage rate of the virtual machine will now be described in detail.

First the resource usage state data stored in the resource usage state storage unit will be described. Items contained in the resource usage state data include 1 the CPU usage rate regarding the entirety of the single server hereinafter referred to as the total CPU usage rate and 2 the CPU usage rate of each virtual machine running on the server for example.

Next the concept of the total CPU usage rate and the CPU usage rate of the virtual machine will be described.

The total CPU usage rate means the CPU usage rate for a fixed period of time until data acquisition time e.g. one minute when the resource usage state acquisition unit has acquired the resource usage state data among the CPU usage rates of the CPUs mounted on a single server . The maximum value is 100 . When more than one CPU or CPU core is mounted on the single server the total CPU usage rate is calculated by averaging the usage rates regarding the CPUs or CPU cores and performing normalization so that the maximum value may be 100 .

Each of a virtual machine monitor VMM and a plurality of virtual machines running on a single server uses part of the total CPU usage rate. In the example of a virtual machine monitor and two virtual machines VM and VM are running on the server and VM and VM use CPU time of 30 and 40 respectively. Namely the CPU usage rates of the VM and VM are 30 and 40 respectively.

Generally the value of the total CPU usage rate of a single server is slightly smaller than the sum of the CPU usage rate of the virtual machine monitor VMM running on the server and the CPU usage rate of all the virtual machines VM 30 VM 40 .

Next the structure of the resource usage state data will now be described. The resource usage state data is not necessarily limited to the CPU usage rate. For example the resource usage state data may include the amount of memory transfer per time unit the amount of disk transfer per time unit amount of I O transfer and the amount of network traffic per time unit. Further several types of resource usage state data may be used at the same time.

Referring to the resource usage state storage unit according to the present exemplary embodiment stores the resource usage state data regarding the five servers from host to host in this example. Commonly to all the servers these resource usage state data include the measurement values regarding the total CPU usage rate. Further the resource usage state data according to the present exemplary embodiment includes the CPU usage rate of each of the virtual machines running on each server .

Note that the number of the virtual machines run by the server may be different thus the number of data the number of CPU usage rates from VM to VMn related to the CPU usage rate of the virtual machines may be different for each server . In the number of data related to the CPU usage rate of the virtual machines is two VM and VM for each of host and host three VM VM and VM for each of host and host and four VM VM VM and VM for host.

Note that if the resource usage state data to be collected by the resource usage state acquisition unit is other than the CPU usage rate the structure of the resource usage state data stored in the resource usage state storage unit is changed accordingly.

Referring to the virtual machine manager according to the present invention may be achieved with the similar hardware structure to that of a general computer and comprises a central processing unit CPU a main storage unit which is a main memory such as a random access memory RAM and used as a work area for data and a temporary save area for data a communication control unit for sending receiving the data through the network a presentation unit such as a liquid crystal display a printer and a speaker an input output unit such as a keyboard and a mouse an interface unit which is connected to peripheral devices to send receive data an auxiliary storage unit which is a hard disk device formed of a nonvolatile memory such as a read only memory ROM a magnetic disk and a semiconductor memory and a system bus for interconnecting each of the above described components of the information processing unit.

The virtual machine manager according to the present invention can achieve its operation obviously in hardware by implementing in the virtual machine manager a circuit component comprising a hardware component such as a large scale integration LSI in which a program for achieving such a function is incorporated as well as in software by executing a program for providing each function of each component described above with the CPU on the computer processing device.

Namely the CPU loads into the main storage unit and executes the program stored in the auxiliary storage unit and controls the operation of the virtual machine manager to achieve each function described above in software.

Note that the server according to the present exemplary embodiment or each of other exemplary embodiments described later may have a structure as described above to achieve each function described above in hardware or in software.

The operation of the virtual machine location system according to the present exemplary embodiment will now be described in detail.

The resource usage state collection unit repeatedly performs the operations of acquiring the resource usage state data from a server under management at preset regular intervals and storing the acquired resource usage state data in the resource usage state storage unit .

The operating procedure of the resource usage state collection unit will be described below in connection with the flowchart of .

First the resource usage state collection unit acquires from a plurality of servers connected through the network the resource usage state data regarding the servers Step S .

Next the resource usage state collection unit stores the resource usage state data acquired in the previous step in the resource usage state storage unit Step S .

Finally the resource usage state collection unit notifies the resource conflict detection unit of the arrival of the latest resource usage state data Step S . Note that upon reception of this notification the resource conflict detection unit starts operating.

The resource usage state data acquired from the servers by the resource usage state collection unit is acquired by the resource usage state acquisition unit on the server under management. The resource usage state acquisition unit is a program running on any of a host OS a virtual machine monitor or a privileged virtual machine special virtual machine for controlling other virtual machines and acquires the resource usage state data through a command or an application programming interface API provided by existing OSs or virtual machine products e.g. a vmstat command for UNIX Registered Trademark type OS and an xenmon command for Xen .

Next the operation of the resource conflict detection unit will be described in detail. Upon receipt of the notification of the arrival of the resource usage state data from the resource usage state collection unit the resource conflict detection unit sequentially takes out the resource usage state data stored in the resource usage state storage unit and checks whether or not there is a resource conflict on the server under management. If a resource conflict has been detected the resource conflict detection unit notifies the virtual machine relocation determination unit of occurrence of a resource conflict and starts virtual machine relocation processing for resolving the conflict.

The operating procedure of the resource conflict detection unit will be described below in connection with the flowchart of .

First upon receipt of the notification of the arrival of the resource usage state data from the resource usage state collection unit the resource conflict detection unit acquires the resource usage state data regarding a single server from the resource usage state storage unit Step S .

At that time if processing of Steps S to S has already been performed on the latest resource usage state data of all the servers stored in the resource usage state storage unit resource conflict detection has already been performed on the latest resource usage state data of all the servers the processing of the resource conflict detection unit is ended Step S . Otherwise this process goes to Step S.

In Step S the resource conflict detection unit checks if the total CPU usage rate has reached a predetermined value specified in advance regarding the acquired resource usage state data . If so the process goes to Step S. Otherwise the process returns to Step S where the resource usage state data regarding the next single server is checked. A threshold a predetermined value specified in advance used here is specified by a system administrator for example and the same value e.g. 80 may be specified for all the servers or a different value may be specified for each server .

In Step S the resource conflict detection unit checks if the CPU usage rates of two or more virtual machines have reached a predetermined value specified in advance regarding the acquired resource usage state data . If so the process goes to Step S. Otherwise the process returns to Step S where the resource usage state data regarding the next single server is checked. The ways of determining a threshold a predetermined value specified in advance here will be described later.

Finally in Step S the resource conflict detection unit notifies the virtual machine relocation determination unit of start of the virtual machine relocation processing. The notification includes the contents of the resource usage state data acquired in Step S. Note that after this step the virtual machine relocation determination unit starts operating.

An example of the way of determining a threshold regarding the CPU usage rates of the virtual machines used in Step S specifies the same threshold for all the virtual machines .

For example when the same threshold is specified as 20 if each of the CPU usage rates of two or more of the virtual machines running on a single server is equal to or higher than 20 the resource conflict detection unit determines that there is a resource conflict on the server and the process goes to Step S.

Another example of the way of determining a threshold regarding the CPU usage rates of the virtual machines determines the threshold dynamically based on the number of virtual machines running on a single server and the value of the total CPU usage rate.

Namely assuming that the total CPU usage rate of a server of interest is Up and the number of virtual machines running on the server is N Up N is used as the threshold.

A specific example of the way of determining the threshold will be provided in connection with the resource usage state data shown in .

Since the total CPU usage rate of the server host is 24 and two virtual machines are running on the server the threshold is 24 2 12 .

In the resource usage state data of one virtual machine VM of two virtual machines on server host is less than the threshold therefore the resource conflict detection unit determines that there is no resource conflict on the host.

Since the total CPU usage rate of the server host is 84 and four virtual machines are running on the server the threshold is 84 4 21 .

In the resource usage state data of three virtual machines on the server host are equal to or higher than the threshold therefore the resource conflict detection unit determines that there is a resource conflict on the three virtual machines VM VM and VM on the host.

Further as a variation of this way of determining a threshold instead of the threshold being set to Up N Up N k may be used as a threshold using a constant k specified in advance. In this case the condition for detecting that a conflict occurred is looser compared to the case in which Up N is used as the threshold. For example regarding the server host of the threshold for conflict occurrence detection when k 5 is 84 4 5 16 .

In above described Steps S and S the resource usage state data measurement data used as a decision criterion for detecting a resource conflict is not limited to CPU usage rates and the amount of memory transfer per time unit the amount of disk transfer per time unit or the amount of network traffic per time unit may be used. In a conflict detection method using these measurement data the CPU usage rate is replaced with these measurement data.

Note that when detecting a resource conflict using without limited to the CPU usage rate measurement data related to two different types of data by resource type among data such as the amount of memory transfer the amount of disk transfer or the amount of network traffic per time unit the conflict detection method needs to be replaced with either of the following two types of detection methods 

 1 The above described Steps S to S are performed on each resource type used as a decision criterion and when the occurrence of a conflict is detected regarding any of resource types the process goes to Step S.

 2 The procedure of the above described Steps S to S is performed as is. However only when the measurement values regarding all the resource types which are the decision criteria are equal to or higher than a given value in Step S the process goes to Step S. Further in S when the decision criteria are fulfilled for all the resource types serving as decision criteria the process goes to Step S.

Next the operating procedure of the virtual machine relocation determination unit will be described. If a resource conflict is detected by the resource conflict detection unit the virtual machine relocation determination unit determines the following three pieces of information and controls the relocation of a virtual machine based on the information.

 1 A virtual machine to be transferred is determined. A virtual machine to be transferred means a virtual machine transferred from a server to which the virtual machine itself belongs to another server during the relocation of the virtual machine.

 2 A transfer source server is determined. A transfer source server means a server to which a virtual machine to be transferred belongs before the transfer of the virtual machine.

 3 A transfer destination server is determined. A transfer destination server means a server to which a virtual machine to be transferred belongs after the transfer of the virtual machine.

The operating procedure of the virtual machine relocation determination unit will be described below in connection with the flowchart of .

First upon receipt of the notification of the start of the virtual machine relocation processing from the resource conflict detection unit the virtual machine relocation determination unit selects as a transfer source server the server on which a resource conflict occurred Step S . The virtual machine relocation determination unit can acquire the name of the server on which a resource conflict occurred from the resource usage state data contained in the notification issued in Step S.

Next the virtual machine relocation determination unit selects as a virtual machine to be transferred the virtual machine having the highest CPU usage rate among virtual machines running on the transfer source server Step S . The CPU usage rate of each virtual machine running on the transfer source server is contained in the resource usage state data contained in the notification issued in Step S described above.

Next the virtual machine relocation determination unit selects as a transfer destination server the server having the largest free CPU usage rate among the servers under management. A free CPU usage rate means a numeric value obtained from the following expression free CPU usage rate 100 total CPU usage rate.

Next the virtual machine relocation determination unit checks if the free CPU usage rate of the transfer destination server selected in Step S exceeds the CPU usage rate of the virtual machine to be transferred selected in Step S Step S . If so the process goes to Step S otherwise the process is ended. In the latter case the relocation of the virtual machine is not performed.

Finally in Step S the virtual machine relocation determination unit requests either or both of the transfer source server and the transfer destination server to transfer the virtual machine to be transferred. Upon receipt of the notification the virtual machine control unit on these servers issues a command for transferring the existing virtual machine e.g. xm migrate command for xen to relocate the virtual machine .

In Step S described above the way that the virtual machine relocation determination unit selects the virtual machine to be transferred is not limited to one based on the CPU usage rate of the virtual machine .

One of other ways of selecting a virtual machine to be transferred is based on resource usage state data measurement data other than the CPU usage rate. For example among virtual machines running on the transfer source server the one having the highest I O usage may be selected as measurement data. This case is based on the premise that the resource usage state collection unit collects the data concerning the I O usage of all the virtual machine as the measurement data.

Another way of selecting a virtual machine to be transferred is based on predetermined priorities specified in advance. For example when the two virtual machines VM and VM are running on the transfer source server and the priorities and are set on these virtual machines respectively where priority 2 1 the virtual machine relocation determination unit selects the virtual machine VM having a higher priority as a transfer target.

Further a virtual machine to be transferred may be selected by combining measurement data regarding several types of resources such as a CPU a memory a disk or a network and additionally combining priorities therewith. In this case after an expression including these measurement data and priorities is specified the virtual machine having the highest calculated value obtained by the expression is selected as a virtual machine to be transferred.

In Step S described above the way that the virtual machine relocation determination unit selects the transfer destination server is not limited to one based on the free CPU usage rate of the server .

One of other ways of selecting a transfer destination server is based on resource usage state data measurement data other than the CPU usage rate.

For example the server having the smallest I O usage regarding the entirety of the single server hereinafter referred to as total I O usage may be selected as the transfer destination. This case is based on the premise that the resource usage state collection unit collects the data regarding the total I O usage of respective server . Further as a criterion for selecting a transfer destination server a certain expression may be used to combine measurement data regarding several types of resources such as a CPU a memory a disk or a network.

Note that if among the servers under management one having a different hardware structure is included it is not necessarily appropriate that the free CPU usage rates or other measurement data are simply compared to determine a transfer destination server . For example a situation in which a server has one CPU another server has the same type of two CPUs and both servers have the free CPU usage rate of 80 is considered. In this case since the server can be assumed to have more space in the CPU resource it is appropriate that the server is selected. In order to address such a situation a coefficient may be specified for each server and the coefficient is multiplied to the free CPU usage rate or other measurement data which may be used as a selection criterion.

Another way of selecting a transfer destination server may determine priorities based on the conditions of respective servers . More specifically the server on which no virtual machine is running may be selected as the transfer destination with a lower priority than the other servers namely the server on which no virtual machine is running is selected only when among the servers on which a virtual machine is running there is not even one server having sufficient free resources . According to this method by causing the virtual machines to run on as few as possible number of servers and turning off the power sources of the remaining servers the electricity consumption by the servers can be saved. This type of prioritization can be used in combination with other ways of selection described above.

A first effect is that a virtual machine can be relocated immediately in response to a sudden change in load.

The reason is that the virtual machine manager relocates the virtual machine based on the latest resource usage state data of the virtual machine without the past data regarding the performance of the virtual machine when the relocation of the virtual machine .

A second effect is that a virtual machine can be relocated without stopping a system running on the virtual machine .

The reason is that only the virtual machine that has caused the resource conflict is the target of a relocation at one time thus the operation of the other virtual machines is not affected.

A third effect is that CPU performance required for a server is lower than those of second and third exemplary embodiments which are described later.

The reason is that most processing including the detection of a resource conflict and the determination of relocation of a virtual machine is performed by the virtual machine manager separated from the server . However the virtual machine manager needs a relatively high performance hardware resource.

Next a virtual machine location system according to a second exemplary embodiment of the present invention will now be described in detail with reference to the drawings.

Referring to as in the first exemplary embodiment the virtual machine location system according to the present exemplary embodiment comprises a virtual machine manager a management terminal and a plurality of servers . The virtual machine manager and the plurality of servers are interconnected through the network .

The difference from the first exemplary embodiment is that the virtual machine manager does not have the resource conflict detection unit and the server has an intra server resource conflict detection unit .

Namely in the present exemplary embodiment instead of using the collected resource usage state data for the virtual machine manager to detect a resource conflict the intra server resource conflict detection unit provided on each server detects a resource conflict.

The intra server resource conflict detection unit has a function for detecting a resource conflict which is similar to that of the resource conflict detection unit according to the first exemplary embodiment and a function for notifying the virtual machine relocation determination unit provided on the virtual machine manager that a conflict occurred through the server when detecting a resource conflict on the server on which the intra server resource conflict detection unit itself is provided. Further the intra server resource conflict detection unit may have a function for storing the resource usage state data which is similar to that of the resource usage state storage unit according to the first exemplary embodiment. Note that the intra server resource conflict detection unit may make a notification including the contents of the resource usage state data acquired from the resource usage state acquisition unit .

The virtual machine relocation determination unit has a function for initiating virtual machine relocation determination processing at the time of receiving the notification.

Next the operation of the virtual machine location system according to the present exemplary embodiment will be described in detail focusing on the difference from the first exemplary embodiment.

Steps S and S are the same as Steps S and S of illustrating the operating procedure of the resource usage state collection unit according to the first exemplary embodiment. The difference is that Step S is eliminated. Namely the difference is that this processing is ended at the time when the resource usage state data collected by the resource usage state collection unit according to the present exemplary embodiment is stored in the resource usage state storage unit .

In principle as in the first exemplary embodiment the resource usage state collection unit is executed at regular intervals. Alternatively the resource usage state collection unit may be executed at the time when the virtual machine relocation determination unit receives the notification indicating that a resource conflict occurred from the intra server resource conflict detection unit . In the former case the virtual machine relocation determination unit can initiate virtual machine relocation processing as soon as a resource conflict is detected. On the other hand in the latter case although time is needed for collecting the resource usage state data when a resource conflict occurred consumption of the CPU and the network bandwidth generated due to collecting the resource usage state data during a normal situation namely when no resource conflict occurs can be held in check.

The operation of the virtual machine relocation determination unit according to the present exemplary embodiment is basically similar to that of the virtual machine relocation determination unit according to the first exemplary embodiment . Note that there is a difference in that according to the second exemplary embodiment the virtual machine relocation determination unit starts operating upon receipt of a notification from the intra server resource conflict determination unit compared to the first exemplary embodiment in which the virtual machine relocation determination unit starts operating upon receipt of a notification from the resource conflict detection unit .

Further if the resource usage state collection unit is not executed at regular intervals namely if the processing of the resource usage state collection unit is started at the time when the virtual machine relocation determination unit receives the notification indicating that a resource conflict occurred the processing of the resource usage state collection unit Steps S and S of has to be finished before Step S of .

The operating procedure of the intra server resource conflict detection unit will be described in connection with the flowchart of . The basic flow of the operation is the same as that of the resource conflict detection unit according to the first exemplary embodiment . Note that the difference is that the intra server resource conflict detection unit does not sequentially acquire all data stored in the resource usage state storage unit but handles only the resource usage state data regarding a single server . According to the present exemplary embodiment the intra server resource conflict detection unit is executed at regular intervals specified in advance.

First the intra server resource conflict detection unit acquires the latest resource usage state data from the resource usage state acquisition unit in a server Step S . The resource usage state data acquired at that time is limited to data regarding a single server . For example the resource usage state collection unit in a server acquires only the resource usage state data regarding the same server .

Next the intra server resource conflict detection unit checks if the total CPU usage rate has reached a predetermined value specified in advance regarding the acquired resource usage state data Step S . If so the process goes to Step S. Otherwise the processing of the intra server resource conflict detection unit is ended and after idling for a given period of time the processing from Step S onward is performed again. The processing in this step is the same as that of Step S in the resource conflict detection unit .

In Step S the intra server resource conflict detection unit checks if the CPU usage rates of two or more virtual machines have reached a predetermined value specified in advance regarding the acquired resource usage state data . If so the process goes to Step S. Otherwise the processing of the intra server resource conflict detection unit is ended and after idling for a given period of time the processing from Step S onward is performed again. The processing in this step is the same as that of Step S in the resource conflict detection unit .

Finally in Step S the intra server resource conflict detection unit notifies the virtual machine relocation determination unit in the virtual machine manager of start of the virtual machine relocation processing. The notification includes the contents of the resource usage state data acquired in Step S. After this step the processing of the virtual machine relocation determination unit starts.

A first effect is that the time required between the occurrence of a conflict and the detection thereof is short because the intra server resource conflict detection unit is located on each server .

A second effect is that the performance required for the virtual machine manager is lower than that of the first exemplary embodiment because resource conflict detection is not performed in the virtual machine manager . However the server needs the performance higher than that of the first exemplary embodiment.

A virtual machine location system according to a third exemplary embodiment of the present invention will now be described in detail with reference to the drawings.

Referring to the virtual machine location system according to the present exemplary embodiment has a plurality of servers which are interconnected by the network .

Differing from the first and second exemplary embodiments the virtual machine location system according to the present exemplary embodiment has no virtual machine manager . Instead in the virtual machine location system according to the present exemplary embodiment each server has a function of the virtual machine manager according to the first and second exemplary embodiments. Namely each server according to the present exemplary embodiment includes the resource usage state collection unit a virtual machine VM relocation determination unit and a resource usage state storage unit DB .

In addition the virtual machine control unit in each server according to the present exemplary embodiment has a lock mechanism .

The lock mechanism has a function when the virtual machine relocation determination unit in a server determines the transfer of the virtual machine to the server having the lock mechanism and has accessed the server for causing the first virtual machine relocation determination unit to have accessed the server to acquire exclusively the access right lock . Therefore when the virtual machine relocation determination unit in a server has already acquired the lock on a predetermined server access to the server from the virtual machine relocation determination unit in another server is not permitted.

As in the second exemplary embodiment the virtual machine location system according to the present exemplary embodiment uses the intra server conflict detection unit provided on each server to detect a resource conflict on each server . When the intra server conflict detection unit is used to detect a resource conflict the server relocation determination unit provided on the server on which the resource conflict occurred is used to relocate the virtual machine .

Next the operation of the virtual machine location system according to the present exemplary embodiment will be described in detail focusing on the difference from the first and second exemplary embodiments.

The operating procedure of the intra server resource conflict detection unit according to the present exemplary embodiment is the same as that of the intra server resource conflict detection unit according to the second exemplary embodiment . Note that there is a difference in that in Step S the intra server resource conflict detection unit according to the present exemplary embodiment does not notify the virtual machine manager of start of the virtual machine relocation but notifies the virtual machine relocation determination unit in the server on which the intra server resource conflict detection unit itself is provided. Namely the intra server resource conflict detection unit according to the present exemplary embodiment notifies the virtual machine relocation determination unit in a server of the start of the virtual machine relocation when the intra server resource conflict detection unit in the same server detects a resource conflict.

The operating procedure of the resource usage state collection unit according to the present exemplary embodiment is the same as that of the resource usage state collection unit according to the second exemplary embodiment . Note that according to the present exemplary embodiment the resource usage state collection unit is executed every time the execution of the virtual machine relocation determination unit which will be described later is started not at regular intervals.

The operation of the virtual machine relocation determination unit according to the present exemplary embodiment is basically similar to that of the virtual machine relocation determination unit according to the first exemplary embodiment . However there are two differences as follows 

 1 In Step S the virtual machine relocation determination unit according to the present exemplary embodiment starts operating upon receipt of the notification from a server on which the virtual machine relocation determination unit itself is provided or the intra server resource conflict detection unit in another server not from the resource conflict detection unit .

 2 The virtual machine relocation determination unit according to the present exemplary embodiment finishes the processing of the resource usage state collection unit Steps S and S of before Step S is performed. At that time in Step S the virtual machine relocation determination unit according to the present exemplary embodiment acquires the resource usage state data from a server on which the virtual machine relocation determination unit itself is provided not from each server .

According to the present exemplary embodiment since each server has the virtual machine relocation determination unit the virtual machine relocation determination units of two or more servers may operate simultaneously thus there is the possibility that transfers of virtual machines are attempted simultaneously with respect to a single server .

In order to avoid this situation the virtual machine control unit in a server has the above described lock mechanism .

When the virtual machine relocation determination unit selects a server as a transfer destination server in Step S the virtual machine relocation determination unit has to acquire the lock on the server . If the virtual machine relocation determination unit could not acquire the lock namely if the virtual machine relocation determination unit in another server has already acquired the lock a different server is selected as a transfer destination server.

The operating procedure of the virtual machine relocation determination unit according to the present exemplary embodiment utilizing the lock mechanism will be described below in connection with the flowchart of .

Steps S to S and Step S are the same as those of a case in which a lock mechanism is not utilized Steps S to S and Step S of . In Step S the virtual machine relocation determination unit according to the present exemplary embodiment goes to Step S not to Step S if the free CPU usage rate of a transfer destination server exceeds the CPU usage rate of a virtual machine to be transferred.

In Step S the virtual machine relocation determination unit according to the present exemplary embodiment tries to acquire the lock on a transfer destination server. If the lock can be acquired successfully in Step S the process goes to Step S. If the lock cannot be acquired in Step S the process returns to Step S where the virtual machine relocation determination unit selects a transfer destination server again. In this case the virtual machine relocation determination unit excludes from the target to be selected as transfer destination servers the servers that failed in lock acquisition until the previous time.

After the transfer of the virtual machine is finished in Step S the process goes to Step S. In Step S the virtual machine relocation determination unit releases the lock acquired in Step S.

An effect of the third exemplary embodiment is that a dedicated virtual machine manager or a server into which a program serving as a virtual machine manager is integrated does not have to be provided. According to the first and second exemplary embodiments the virtual machine manager is needed for the relocation of the virtual machine therefore in the event of failure of the virtual machine manager the present invention does not function. On the other hand according to the third exemplary embodiment even in the event of failure of any servers the relocation of the virtual machine can be performed.

A first effect is that a virtual machine can be relocated immediately in response to a sudden change in load.

The reason is that a resource conflict determination unit is provided for detecting a resource conflict using the resource usage state regarding the entirety of a single server and the measurement result of the resource usage state of a virtual machine running on the server therefore the relocation of the virtual machine is performed only based on the latest information regarding the resource usage state of the virtual machine without the past data regarding the performance of the virtual machine.

A second effect is that a virtual machine can be relocated without stopping a system running on the virtual machine.

The reason is that the virtual machine relocation determination unit is provided for transferring the virtual machine on a server for which a resource conflict has been detected to another server having a lower resource usage rate therefore only the virtual machine that has caused the resource conflict is the target of a relocation at one time thus the operation of other virtual machines is not affected.

Although the preferred exemplary embodiments of the present invention have been described the present invention is not necessarily limited thereto and various modifications may be made without departing from the technical idea.

The present application claims the benefit of the priority of Japanese Patent Application No. 2006 317175 filed on Nov. 24 2006 and the disclosure is incorporated herein.

The present invention can be applied to operation management middleware for centrally managing server resources forming an enterprise information system or a data center or a self managing server in the enterprise information system or the data center.

