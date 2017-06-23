---

title: Root-cause approach to problem diagnosis in data networks
abstract: An improved root-cause approach to problem diagnosis in data networks in the form of a method comprising the steps of: associating each metric in a at least one set of metrics with at least one component and/or network device; obtaining values for each such metric from a monitoring system; determining whether each such metric is indicative of a problem within the data network; and ranking and correlating indicative problems to determine whether a problem may be symptomatic of another problem based on an interconnection and/or interdependency between a physical machine and a virtual machine, between components or between components and network devices.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08208381&OS=08208381&RS=08208381
owner: EG Innovations PTE. Ltd.
number: 08208381
owner_city: Singapore
owner_country: SG
publication_date: 20070727
---
This application claims benefit of priority to U.S. application Ser. No. 11 781 156 and its corresponding PCT International Application entitled Monitoring System for Virtual Application Environments both filed on Jul. 20 2007 which are hereby incorporated by reference.

The invention relates to an improved root cause approach to problem diagnosis in data networks. The invention is particularly suited to diagnosing problems in a data network including at least one virtual machine.

The following discussion of the background to the invention is intended to facilitate an understanding of the present invention. However it should be appreciated that the discussion is not an acknowledgment or admission that any of the material referred to was published known or part of the common general knowledge in any jurisdiction as at the priority date of the application.

In U.S. Pat. No. 6 701 459 the applicants disclosed a root cause approach to problem diagnosis in data networks. However the recent increased utilisation of virtual machines as part of data networks has resulted in the diagnostic approach recited therein no longer providing a proper assessment of potential root cause problems.

To elaborate it is to be remembered that virtual machines are inter related with the physical computer systems on which they operate since they share a common pool of central processing unit CPU memory disk space and storage resources. Accordingly a malfunctioning application running on one virtual machine may result in other virtual machines hosted on the same physical computer system being starved of resources which should otherwise be available to them. Similarly abnormal processes on the physical computer system may result in poor performance of applications running on each virtual machine hosted thereon.

The root cause diagnosis problem is further complicated because the virtual machines may themselves be dynamically moved between physical computer systems during operation. At the same time their identity eg. IP address hostname etc. remains the same and the applications executing on the re located virtual machine continue to operate in the same manner i.e. independent of the new physical machine s on which the virtual machine is running. This dramatically increases the difficulties in diagnosing potential root cause problems as the relationship or where the virtual machine is hosted across multiple machines relationships between physical computer systems and virtual machines need to be constantly updated.

Accordingly it is an object of the present invention to provide an improved root cause diagnosis process that takes into account at least some of the problems associated with analysing data networks that include virtual machines.

Throughout this document unless otherwise indicated to the contrary the terms comprising consisting of and the like are to be construed as non exhaustive or in other words as meaning including but not limited to .

In accordance with a first aspect of the invention there is an improved root cause approach to problem diagnosis in data networks in the form of a method comprising the steps of 

The method may include the step of obtaining and storing information on the interconnection and interdependencies between each physical machine and virtual machine in the data network and where the step of ranking and correlating indicative problems includes the sub step of ranking and correlating indicative problems to determine whether a problem may be symptomatic of another problem based on the stored physical virtual machine interconnection and interdependency information. The method may also include the step of obtaining and storing information on the interconnection and interdependencies between components and between components and network devices and where the step of ranking and correlating indicative problems includes the sub step of performing end to end correlation of the indicative problems based on the stored component network interconnection and interdependency information.

In this form the step of ranking and correlating indicative problems includes the sub step of performing top to bottom correlation of the indicative problems based at least in part on the hierarchical layer model.

Preferably the step of obtaining information on the interconnection and interdependencies between each physical machine and virtual machine in the data network is repeatedly obtained and compared to the prior stored information on the interconnection and interdependencies between each physical machine and virtual machine in the data network and if the information so obtained differs from the prior stored information storing the obtained information in place of the prior stored information.

Additionally the step of obtaining information on the interconnection and interdependencies between components and between components and network devices is repeatedly obtained and compared to the prior stored information on the interconnection and independencies between components and between components and network devices and if the information so obtained differs from the prior stored information storing the obtained information in place of the stored information.

The method can also include the step of defining a set of priority queues and the step of ranking the indicative problems is made with reference to the priority queues. Where the method allows the step of performing end to end correlation may be performed on each priority queue in turn. Similarly the step of performing top to bottom correlation may be performed between each priority queue and the next lowest priority queue if any.

Ideally the method includes the step of demoting any indicative problem determined to be symptomatic of another indicative problem to the next lowest priority queue where possible to do so.

The method may further operate so that those indicative problems relating to the layer upon which all other layers are dependent are processed first. This is valuable as the root cause of any problems in the data network is likely to arise here.

Preferably each indicative problem is associated with a component name which includes a port number and each metric is associated with a port number the method including the step of comparing the port number of the component name with the port number of the associated metric and if the comparison shows that the indicative problem is independent of the port number the component name is modified to delete the associated port number.

In accordance with additional aspects of the invention there is a system for implementing an improved root cause approach to problem diagnosis in data networks and a computer readable medium having computer software stored thereon for executing the method as described in the first aspect of the invention.

In accordance with a first embodiment of the present invention there is an improved root cause diagnostic process . The root cause diagnostic process operates to diagnose problems in a data network . The data network includes at least one physical machine and at least one virtual machine . The virtual machines may be hosted by one or more of the at least one physical machines .

The invention will be described with reference to a monitoring system operable to provide certain metrics relating to the physical machines and virtual machines . With respect to this particular embodiment the monitoring system concerned is the monitoring system as described in the first embodiment of the applicant s co pending application entitled Monitoring System for Virtual Application Environments having the same priority date as the present application.

The monitoring system as described in the co pending application is slightly modified in processing but retains the structural elements of agent programs and a single manager program . This modification is described with reference to .

Step sees each agent program and the manager program analyse their respective physical machines . This analysis is aimed at determining a predetermined set of information in respect of the physical machine and each virtual machine hosted by the physical machine if any .

In this embodiment the predetermined set of information includes the IP addresses and host names of each such physical machine and virtual machine . To provide an example of how this can be obtained where the physical machine is executing the Linux operating system the ifconfig command is used to obtain the IP address of the physical machine . Domain Name Server DNS lookups of the IP addresses can then provide the host name of the physical machine .

In order to determine the number of and IP addresses for each virtual machine the application programming interface API of the virtualisation technology running on the physical machine is used Again for example purposes the physical machine uses VMware technology from VMWare Inc. of Palo Alto Calif. to support the hosting of the virtual machines. This software is then used as follows.

A connection is established with the VMware server using the server connect method call. Once the connection is established the server registered vm names method call can be used to obtain a list of all registered virtual machines on that server. For each virtual machine so discovered a connection to the virtual machine using the vm connect connect params config method call. The vm get guest info ip call can then be used to obtain the IP addresses of each virtual machine . The vm get execution state method call can then be used to determine if the virtual machine is set to an on state or not. This is important as there is no need to include virtual machines set to an off state in the root cause analysis process. Finally a further round of DNS lookups using the IP address of each virtual machine allows the hostnames of such virtual machines to be collected.

At the same time the agent program also obtains as part of the predetermined set of information information relating to what applications are running on each system physical machine or virtual machine the relationships between such applications and the relationship between applications and network devices. The applications running on a system can be discovered using TCP port checks eg.

Network devices can similarly be discovered using Simple Network Management Protocols SNMPs by polling specific Management Information Bases MIBs for different devices. For example the traceroute UniX command and the tracert Microsoft Windows command can be used to find the general network topology.

The relationships between applications can be discovered by using network sniffers to look at TCP packet transmissions between ports. The netstat command on a UniX server can also provide this information.

The predetermined set of information is then transmitted by each agent program to the manager program so that the manager program can establish a physical virtual relational map of the data network as well as a dataflow graph of the data network step . The data flow graph defines the interconnections and interdependencies between applications components and network devices.

Step sees the manager program determine whether any of the agent programs are transmitting their respective predetermined set of information to it. If so processing continues to step where the predetermined set of information is used by the manager program to create a relational map of the physical machines and virtual machines in the data network as well as a dataflow graph of the data network . The new relational map and dataflow graph are then compared with the existing relational map dataflow graph at step to determine whether the relational map or dataflow graph has changed.

If the relational map or dataflow graph has changed the new relational map or dataflow graph as created at step is stored by the manager program in a configuration file for later reference step .

The actual root cause diagnostic process is able to operate once the discovery process referred to above with reference to has executed at least once and a layer model has been defined. In this embodiment the layer model is as shown in . The HOST layer monitors the CPU memory and disk utilisation of the physical machine as well as the status of physical server hardware i.e. temperature voltage etc. . The NETWORK layer monitors the network connectivity to the physical machine and the traffic to network interfaces of the physical machines . The TCP layer monitors the TCP protocol traffic to the physical machine . The VIRTUAL GUESTS layer represents the view of the virtual machine as taken from the perspective of the physical machine . The VIRTUAL SERVERS layer represents the view of the virtual machines as taken from the perspective of the operating system executing on the virtual machine . As shown in the Figure each layer depends on its lower layers to function properly.

Each layer in the layer model is also correlated at the time of definition to a set of metrics. The importance of this correlation will be described in more detail below.

At step a report table is initialised. The report table represents a list of components that have been identified as being in an abnormal state. Once each report table is initialised the manager program waits for values for preset metrics to be transmitted to it from agent programs step . Step sees the manager program receive such values from an agent program .

Each metric value is assessed to determine the layer to which it is related. This relationship between layer and component is made with reference to the set of metrics associated with each layer as defined in the layer model. At the same time the component from which the metric value has been obtained as communicated by the agent program is related to the metric value step .

Thereafter each metric value is again assessed to determine whether the metric value is normal for example by comparing the metric value to a specific normal value or range of values step . If the metric value assessed is normal processing continues to step . If not processing continues to step .

Step sees the manager program check whether each component layer combination associated with the normal metric value has a corresponding entry in the report table. If so the corresponding entry in the report table is deleted step . The system administrators are thereafter informed that a previously identified abnormal component layer combination has now become normal step . Processing then continues at step .

However if the component layer combinations associated with the normal metric value do not have a corresponding entry in the report table a check is made as to whether the metric value being processed is the last metric value to be processed step . If so processing moves to step . If not processing returns to step where the next metric value is processed.

In a similar manner step sees the manager program check whether each component layer combination associated with the abnormal metric value has a corresponding entry in the report table. If such component layer combinations do have corresponding entries a check is made as to whether the metric value being processed is the last metric value to be processed step . If so processing moves to step . If not processing returns to step where the next metric value is processed.

If a component layer combination associated with an abnormal metric does not have a corresponding entry in the report table an entry is made in the report table for each such component layer combination step . Again a check is thereafter made to determine whether the metric value being process is the last metric value to be processed step . If so processing moves to step . If not processing returns to step where the next metric value is processed.

Step sees the report table being re formatted to form an alert table. As part of the reformatting the following variables are attributed to each entry in the alert table 

For the sake of ease of reference the above variables will be suffixed by a number representative of the position of the entry in the appropriate queue see below to which the variable relates so as to evidence differences between entries.

The manager program begins to categorise the entries in the alert table into a high priority queue a medium priority queue and a low priority queue step . The categorisation is based on a predetermined assessment of the severity of any problem associated with the component layer combination at the time of configuration.

The alert table is subsequently assessed to determine whether there are multiple entries in the high priority queue step . If so the manager program performs an end to end correlation of the entries in the high priority queue.

This end to end correlation process commences with each alert being compared to each other alert in the high priority queue step . To elaborate with reference to the comparison of the first and second entries in the high priority queue the manager program checks whether components are related as indicated by the dataflow graph. ie. Ct1 Ct2 and Cn1 Cn2 . If there is a dependency the manager program considers the two alerts as being duplicates and moves the first entry ie. Ct1 Cn1 to the medium priority queue step while retaining the second entry ie. Ct2 Cn2 in the high priority queue. If there is no dependency as indicated by the dataflow graph both entries are retained in the high priority queue. This comparative process continues until all entries in the high priority queue have been compared with each other entry in the high priority queue.

An identical end to end correlation process is then performed in respect of the medium priority queue with duplicated entries being moved to the low priority queue and in turn the low priority queue with duplicated entries being eliminated from the low priority queue .

On completion of the end to end correlation of each priority queue each priority queue is subjected to a top to bottom correlation process. This top to bottom correlation process will be explained with reference to the high priority queue only step . In this context each entry in the high priority queue is compared with each other entry in the high priority queue. As part of this comparison 

As with the end to end correlation process in relation to entries moved when performing the top to bottom correlation on the medium priority queue such entries are moved to the low priority queue. Similarly entries moved when performing the top to bottom correlation on the low priority queue such entries are deleted from the low priority queue rather than being moved.

At step each entry in the high priority queue is compared with each entry in the medium priority queue and then each entry in the low priority queue. If this comparison identifies an identical entry in the medium priority queue the medium priority entry is moved to the low priority queue. In the case of a comparison identifying identical entries in the low priority queue however the low priority queue entries are merged to form a single alarm.

The virtual environment is then dealt with at step which sees each entry in the top and medium priority queues assessed to determine whether the entry relates to a virtual machine as evidenced by the physical virtual relational map . Typically this assessment is done based on a check of the IP address and or host name of the machine associated with those IP address values and machine names that form part of the physical virtual relational map. This check commences by processing the entries in the high priority queue first followed by the medium priority queue. Checks are not performed on the low priority queue as these entries cannot be demoted further.

If this check indicates that the entry in the priority queue relates to a virtual machine processing continues to step . If not processing returns to step where the next entry in the priority queue is being processed. Of course if the entry just processed is the last entry in the priority queue being processed processing commences on the next lowest priority queue until the last entry in the low priority queue has been processed.

At step a check is made of each other entry in the priority queue being processed to determine whether any such entry relates to a physical machine . If no such entries relate to a physical machine processing returns to step where the next entry in the priority queue being processed is assessed.

Alternatively if any entry in the priority queue being processed does relate to a physical machine an assessment is made to determine whether the virtual machine the subject of the entry being processed is hosted in whole or in part by the physical machine the subject of the other entry step . If so processing continues to step . If not processing returns to step where further comparisons of entries relating to physical machines continues.

Upon identifying that a virtual machine entry correlates to a physical machine entry the manager program moves the virtual machine entry to the next lowest priority queue step . Processing then returns to step where the next entry in the priority queue being processed is assessed.

On completion of assessment of all entries in the priority queues in accordance with the above steps the process finishes with step before repeating. At step the administrator is informed of any changes in significance of any of the entries in any of the priority queues so that corrective action can be taken or verify that any corrective action taken has been effective as appropriate.

It should be appreciated by the person skilled in the art that the above invention is not limited to the embodiment described. In particular the following modifications and improvements may be made without departing from the scope of the present invention 

It should be further appreciated by the person skilled in the art that feature disclosed above and in the embodiment described where not mutually exclusive may be combined to form yet further embodiments that fall within the scope of the present invention.

