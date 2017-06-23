---

title: Virtual regulator for multi-database systems
abstract: A system for managing a plurality of systems, includes a domain comprised of a plurality of systems, wherein the systems are managed by one or more closed-loop system management (CLSM) regulators. A virtual regulator manages operational characteristics of the domain and the plurality of systems, by communicating with the CLSM regulators to monitor the systems' states, events and conditions within the domain and to adjust the systems' operational characteristics in response to the systems' states, events and conditions.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08359333&OS=08359333&RS=08359333
owner: Teradata US, Inc.
number: 08359333
owner_city: Dayton
owner_country: US
publication_date: 20070312
---
This application claims the benefit under 35 U.S.C. 119 e to the following co pending and commonly assigned applications 

U.S. Provisional Patent Application Ser. No. 60 877 767 filed on Dec. 29 2006 by Douglas P. Brown Anita Richards John Mark Morris and Todd A. Walter and entitled Virtual Regulator for Multi Database Systems 

U.S. Provisional Patent Application Ser. No. 60 877 766 filed on Dec. 29 2006 by Douglas P. Brown Scott Gnau and John Mark Morris and entitled Parallel Virtual Optimization 

U.S. Provisional Patent Application Ser. No. 60 877 768 filed on Dec. 29 2006 by John Mark Morris Anita Richards and Douglas P. Brown and entitled Workload Priority Influenced Data Temperature and

U.S. Provisional Patent Application Ser. No. 60 877 823 filed on Dec. 29 2006 by John Mark Morris Anita Richards and Douglas P. Brown and entitled Automated Block Size Management for Database Objections 

U.S. Utility patent application Ser. No. 10 730 348 filed Dec. 8 2003 by Douglas P. Brown Anita Richards Bhashyam Ramesh Caroline M. Ballinger and Richard D. Glick and entitled Administering the Workload of a Database System Using Feedback 

U.S. Utility patent application Ser. No. 10 786 448 filed Feb. 25 2004 by Douglas P. Brown Bhashyam Ramesh and Anita Richards and entitled Guiding the Development of Workload Group Definition Classifications 

U.S. Utility patent application Ser. No. 10 889 796 filed Jul. 13 2004 by Douglas P. Brown Anita Richards and Bhashyam Ramesh and entitled Administering Workload Groups 

U.S. Utility patent application Ser. No. 10 915 609 filed Aug. 10 2004 by Douglas P. Brown Anita Richards and Bhashyam Ramesh and entitled Regulating the Workload of a Database System 

U.S. Utility patent application Ser. No. 11 468 107 filed Aug. 29 2006 by Douglas P. Brown and Anita Richards and entitled A System and Method for Managing a Plurality of Database Systems which applications claims the benefit of U.S. Provisional Patent Application Ser. No. 60 715 815 filed Sep. 9 2005 by Douglas P. Brown and Anita Richards and entitled A System and Method for Managing a Plurality of Database Systems 

U.S. Utility patent application Ser. No. 11 716 890 filed on same date herewith by Douglas P. Brown Scott Gnau and John Mark Morris and entitled Parallel Virtual Optimization 

U.S. Utility patent application Ser. No. 11 716 880 filed on same date herewith by John Mark Morris Anita Richards and Douglas P. Brown and entitled Workload Priority Influenced Data Temperature and

U.S. Utility patent application Ser. No. 11 716 890 filed on same date herewith by John Mark Morris Anita Richards and Douglas P. Brown and entitled Automated Block Size Management for Database Objections 

As database management systems DBMS continue to increase in function and expand into new application areas the diversity of database workloads is increasing as well. In addition to the classic relational DBMS workload consisting of short transactions running concurrently with long decision support queries workloads comprising of an even wider range of system demands are emerging. New complex data types such as image files audio files video files and other large objects and new active data warehouse requirements such as capacity on demand data replication fault tolerance dual active query processing recursion user defined types UDFs external UDFs and so on result in widely varying memory processor disk and network demands on database systems.

In general a DBMS has a number of operational characteristics. These include physical statistics such as CPU usage query response times and performance statistics. In some DBMS the operational characteristics include rule sets under which the database operates relating to the likes of resource consumption and request prioritization. Varying these rule sets often has an effect on other physical characteristics for example altering performance statistics. Ideally a DBMS should be able to accept performance goals for a workload and dynamically adjust its own performance based on whether or not these goals are being met.

Closed loop system management CLSM is a technology directed towards this ideal. Under some known CLSM type systems incoming queries are split into workload groups each workload group having respective service level goals SLGs . The DBMS is responsive to whether or not these goals are met for selectively switching between predetermined rule sets or adjusting performance controls.

It is also known to operate multi system environments wherein a plurality of databases database systems or DBMS operate in parallel. For example DBMS that use a Massively Parallel Processing MPP architecture across multiple systems or a Symmetric Multiprocessing SMP architecture. In particular it is known to operate a dual active system wherein a plurality of databases operate in parallel and intercommunicate. It will be appreciated that managing complex workloads and performance objectives across the board in a multi system environment is difficult.

Consequently there is still a need in the art for additional management techniques for use in multi system environments. The present invention satisfies this need.

To overcome the limitations in the prior art described above and to overcome other limitations that will become apparent upon reading and understanding the present specification the present invention discloses a system for managing a plurality of systems includes a domain comprised of a plurality of systems wherein the systems are managed by one or more CLSM regulators. A virtual regulator manages operational characteristics of the domain and the plurality of systems by communicating with the CLSM regulators to monitor the systems states events and conditions within the domain and to adjust the systems operational characteristics in response to the systems states events and conditions.

In the following description of the preferred embodiment reference is made to the accompanying drawings which form a part hereof and in which is shown by way of illustration a specific embodiment in which the invention may be practiced. It is to be understood that other embodiments may be utilized and structural changes may be made without departing from the scope of the present invention.

The present invention discloses a Virtual Regulator that uses DBMS and CLSM technologies to manage workloads in a multi system environment. Specifically the Virtual Regulator has the capability to manage workloads across a domain comprised of multiple systems managed by one or more CLSM regulators in order to achieve a set of SLGs.

Referring initially to there is provided a CLSM Regulator for managing a plurality of database systems and . The CLSM Regulator includes an interface for obtaining data indicative of one or more operational characteristics of each of database system and . A monitor analyzes the data and provides a signal indicative of an instruction to adjust one or more of the operational characteristics of a selected one of database systems and .

In the present disclosure the term database systems is used in a general sense and is meant to include the wider range of components used in conjunction with a database in a database system. In some embodiments database systems and are simple tables of data whereas in other embodiments they include complex relational database management systems RDBMS . An example of such a database system or is the Teradata RDBMS sold by NCR Corporation the assignee of the present invention.

At a high level the CLSM Regulator operates as a controller including a feedback response mechanism for a domain defined by a plurality of database systems and . It is responsive to the performance of the domain insofar as database requests are performed within predefined threshold requirements. The CLSM Regulator is responsive to data indicative of this performance for adjusting settings such as resource consumption rules and query prioritization settings in the database systems and . In many embodiments this is used to better ensure that the available resources are utilized in a manner conducive to efficiently processing a variable workload.

It will be appreciated that the terms workload class WC workload group WG and workload definition WD are substantially synonymous. That is the terms each relate to the same general identification structure used to separate requests for prioritization processing and performance monitoring in a database system or including a CLSM Regulator .

In the present example the CLSM Regulator analyzes the performance of each of the database systems and and adjusts their respective operational characteristics in response to the analysis. The analysis includes determining whether a particular class of queries are processed in accordance with one or more SLGs assigned to that class of queries.

In brief the CLSM Regulator separates incoming queries into workload groups for each database system and in accordance with predefined principles. Each workload group has assigned to it one or more respective SLGs. Each database system and maintains logs and obtains data to determine whether or not SLGs are being met for particular workload groups and makes adjustments to operational characteristics in response. The typical objective is to adjust available settings such that the SLGs are met.

The precise nature of how workload groups are defined and settings adjusted is generally beyond the scope of the present disclosure and various aspects are dealt with in detail in the cross referenced applications set forth above. Other embodiments are used with database systems that use alternate architectures to analyze their performance and inherently adjust their respective operational characteristics in response to the analysis.

As noted above in some CLSM type systems incoming queries are split into workload groups wherein each workload group has its respective SLGs. The DBMS may be responsive to whether or not these goals are met for selectively switching between predetermined working values defined within a rule set or adjusting performance controls.

In this regard the full set of workload definitions as well as filters throttles and priority scheduler settings are considered a rule set for the system.

For normal operating procedures one set of behaviors defined for a rule set can generally manage workloads and system performance well. For example when arrival rates per workload are in anticipated ranges and all system components are up and functioning a workload manager s the management of CPU concurrency and workload exceptions can effectively manage workload performance. However external or system wide events can cause workload performance to stray beyond reasonable levels.

In addition the business environment can impose restrictions on the system s performance. In the present invention a database administrator DBA has the ability to specify different behaviors depending on the current situation. This is done through the definition of a two dimensional state matrix of system conditions SysCons and operating environments OpEnvs .

A System Condition SysCon represents the condition or health of the system e.g. degraded to the red system condition because a node is down.

An Operational Environment OpEnv represents the kind of work that the system is being expected to perform e.g. within the batch operational environment because a load job is executing.

The elements of the State Matrix are pairs. Each State Matrix element references a State. Multiple matrix elements may reference a common State. Only one State is in effect at any given time based on the matrix element referenced by the highest severity SysCon and the highest precedence OpEnv in effect. Many pairs correlate to fewer States. Each State has a Working Value Set. A or the State can change as directed by event directives defined by the DBA.

In the present example operational characteristics include performance statistics rule sets e.g. working values under which a database system or is operating physical attributes and so on.

The CLSM Regulator includes an input for receiving a request from a user . Although user is illustrated as a person it will be appreciated that various hardware and software devices also provide requests .

Request is typically a database query such as a tactical query. In the present embodiment database systems and define a dual active system where either database system or is capable of handling a request . Despite this it will be appreciated that one of the database systems or is often able to handle a request more efficiently given its operational characteristics. As such a processor is responsive to interface for selecting one of database systems or or both database systems and to process a received request .

An output provides the request the selected database system or for processing. In output is shown to be providing requests to both database systems and . This is meant to illustrate the provision of at least two discrete requests as well as a single request being provided to both database systems and .

In the present embodiment output provides request to database systems and in accordance with a predetermined query prioritization protocol such as that administered by an implementation of a Priority Scheduler Facility PSF or a similar component. Monitor adjusts this predetermined query prioritization protocol in response to data . For example in an embodiment where PSF is used monitor adjusts the PSF settings such a class weights.

Processor categorizes the request into one of a plurality of predetermined workload groups. As previously mentioned each workload group has its respective SLGs. These SLGs relate to response times and the like and generally comprise levels of service that are expected from database systems or in the processing of a request . In determining which database system or should be selected to process a request processor is responsive to operational characteristics that indicate the ability of a particular database system or to process a request belonging to a particular workload group in accordance with the SLGs of that workload group. For example each database system and is operated under one of a group of predetermined system resource consumption rules sets. Processor is initiated to recognize a particular rule set as being particularly suited to handling a certain workload mix.

As a simple example consider two generic exemplary workload groups tactical queries and background queries. Assume that rule set A is most suitable for handling tactical queries and rule set B is most suitable for handling background queries. For the sake of the example interface has obtained data indicative of database system operating under rule set A and database system operating under rule set B. A tactical query is received by interface and recognized as a tactical query by processor . Processor is then responsive to interface for selecting database system to process that tactical query.

The above example is over simplistic to a degree. In some circumstances interface obtains other operational characteristics of database system that suggest it is not meeting SLGs for tactical queries. In such a case processor selects database system for the tactical query. In practical terms tactical queries are directed to database system until interface obtains data to which processor is responsive for altering the procedure.

Monitor is responsive to processor for providing a signal identifying these decisions. Using the above example when processor begins to send a stream of tactical queries to database system the workload mix of database system changes. As such rule set B is not necessarily the optimal choice in the present example assume that rule set C is more suitable. In such a case monitor takes the pro active step of sending a signal to database system and in response database system adapts for operation under rules set C.

Processor is responsive to whether SLGs for requests are being met across the domain defined collectively by database systems and . To this end monitor adjusts operational characteristics such as OpEnvs SysCons system states and or rule sets for either or both of database systems and . It will be appreciated that this assists in the provision of a domain wide approach to workload administration.

It will also be appreciated that at a high level the CLSM Regulator monitors on a short term basis the execution of requests to detect a deviation from the SLGs and where a sufficient deviation is detected the assignment of system resources to particular workload groups across the plurality of database systems and are adjusted to reduce the deviation.

Referring to and embodiments will now be described with reference to a domain comprised of a plurality of multiple dual active database systems wherein each of the dual active database systems is managed by one or more CLSM Regulators and the domain is managed by one or more multi system Virtual Regulators .

Managing system resources on the basis of individual systems and requests does not in general satisfactorily manage complex workloads and SLGs across a domain of database systems in a multi system environment. To automatically achieve workload goals in a multi system environment performance goals must first be defined administered then managed regulated and finally monitored across the entire domain set of systems participating in an n system environment .

CLSM Regulators are used to manage workloads on an individual system basis. Under the present embodiment the Virtual Regulator comprises a modified CLSM Regulator implemented to enhance the CLSM architecture. That is by extending the functionality of the CLSM Regulator components complex workloads are manageable across a domain .

The function of the Virtual Regulator is to control and manage existing CLSM Regulators across all systems in a domain . The new functionality of the Virtual Regulator extends the existing CLSM goal oriented workload management infrastructure which is capable of managing various types of workloads encountered during processing .

In one embodiment the Virtual Regulator includes a thin version of a database system where the thin database system means a database system executing in an emulation mode such as described in U.S. Pat. Nos. 6 738 756 7 155 428 6 801 903 and 7 089 258. The query optimizer function of the thin database system allows the Virtual Regulator to classify received queries into who what where classification criteria and allows the query director function of the thin database system to perform the actual routing of the queries among multiple systems in the domain . In addition the use of the thin database system in the Virtual Regulator provides a scalable architecture open application programming interfaces APIs external stored procedures XSPs user defined functions UDFs message queuing logging capabilities rules engines etc.

The Virtual Regulator also includes a set of open APIs known as Traffic Cop APIs that provide the Virtual Regulator with the ability to monitor system states to obtain system status and conditions to activate inactive systems to deactivate active systems to set workload groups to delay queries i.e. to control or throttle throughput to reject queries i.e. to filter queries to summarize data and statistics and to create dynamic operating rules. The Traffic Cop APIs are also made available to the CLSM Regulators thereby allowing the CLSM Regulators and Virtual Regulator to communicate this information between themselves in a multi system domain .

 a Regulate adjust system conditions resources settings PSF weights etc. against workload expectations SLGs across the domain and to direct query traffic to any of the systems via a set of predefined rules.

 b Monitor and manage system conditions across the domain including adjusting or regulating response time requirements by system as well as using the Traffic Cop APIs to handle filter throttle and or dynamic allocation of resource weights within systems and partitions so as to meet SLGs across the domain .

 c Raise an alert to a database administrator for manual handling e.g. defer or execute query recommendation etc. 

 d Cross compare workload response time histories via a query log with workload SLGs across the domain to determine if query gating i.e. flow control through altered Traffic Cop API settings presents feasible opportunities for the workload.

 e Manage and monitor the sub system CLSM Regulators across the domain using the Traffic Cop APIs so as to avoid missing SLGs on currently executing workloads or to allow workloads to execute the queries while missing SLGs by some predefined or proportional percentage based on shortage of resources i.e. based on predefined rules .

Although depicts an implementation using a single Virtual Regulator for the entire domain in some exemplary environments one or more backup Virtual Regulators are also provided for circumstances where the primary Virtual Regulator malfunctions or is otherwise unavailable. Such backup Virtual Regulators may be active or may remain dormant until needed.

Referring to both the CLSM Regulator and Virtual Regulator include an exception monitor for detecting workload exceptions which are recorded in a log . A system condition monitor is provided to detect system conditions such as node failures. These collectively define an exception attribute monitor .

In practice both the CLSM Regulator and Virtual Regulator receive requests and assign these requests into their respective workload groups and priority classes at . The assigned requests are then passed through a workload query manager also known as a delay manager. The workload query manager is responsive to workload rules and exception monitor for either passing a request on or placing it in a queue until predetermined conditions are met.

If passed the requests are split into their priority classes for handling by PSF . PSF is responsive to the priority classes for providing the requests in accordance with predefined principles for processing at . These principles are updated over time in response to system monitor and exception monitor . PSF reports observed system conditions to monitor and throughput information to monitor which are responsive to such information for updating the principles under which the PSF operates.

Both the CLSM Regulator and Virtual Regulator use a set of user defined rules or heuristics to guide a feedback mechanism that manages the throughput of a workload for each workload group defined in the system. In general Virtual Regulator provides a single view of managing workloads and the associated rules across the domain . Meanwhile CLSM Regulators continue to support workloads in a CLSM environment running on each system defined in domain .

The Virtual Regulator manages PSF settings and workload groups by controlling CLSM Regulators and or adjusting workload rules in order to achieve SLGs. It also monitors operational characteristics such as system conditions exceptions system failures workload exceptions and the like. Further it controls the amount of work allowed into each system to meet SLGs across domain .

The Virtual Regulator gathers system information by broadcasting to all CLSM Regulators in domain a request that they report their current status. This will be recognized as the functionality of interface in .

In some embodiments each system may have superordinate and subordinate systems and so on. An example of this is shown in which illustrates a tree structure. In such embodiments each CLSM Regulator gathers information related to its own systems as well as that of its children CLSM Regulators and reports the aggregated information to its parent CLSM Regulator or the Virtual Regulator at the highest level of the tree. In some cases each CLSM Regulator waits until it has received information from its children CLSM Regulators before forwarding the aggregated information to its parent CLSM Regulator or the Virtual Regulator . In that way the system information is compiled from the bottom of the tree to the top. When the Virtual Regulator compiles its information with that which is reported by all of the CLSM Regulators it will have complete information for domain . The Virtual Regulator analyzes the aggregated information to apply rules and make adjustments.

In the example shown in the tree is a binary tree. It will be understood that other types of trees will fall within the scope of this broad invention. Further while the tree in is symmetrical symmetry is not a limitation.

In another example system each CLSM Regulator communicates its system information directly to the Virtual Regulator . The Virtual Regulator compiles the information adds domain or additional system level information to the extent there is any and makes its adjustments based on the resulting set of information.

Each CLSM Regulator monitors and controls in a closed loop fashion workload group performance information for a single system or dual active system . For example this may require performance information received from a dispatcher processor wherein the performance information is compared to SLGs . In the example of throughput information the level of desired throughput defined in SLGs is compared to the actual level of throughput occurring for a particular workload. The Virtual Regulator then adjusts resource allocation weights to better meet the workload rules.

Referring to the Virtual Regulator receives information concerning the states events and conditions of the systems from the CLSM Regulators and compares these states events and conditions to the SLGs . In response the Virtual Regulator adjusts the operational characteristics of the various systems through a set of Traffic Cop Open APIs to better address the states events and conditions of the systems throughout the domain .

To manage workloads among dynamic domain wide situations the Virtual Regulator classifies the various states events and conditions into at least three general detection categories and specifies what automated actions should occur in response thereto as set forth below 

3. Detection category system device or application condition. These conditions are detected by an individual request or workload group being impacted e.g. average response time greater than the SLG for some qualifying interval by a condition and can be implemented through existing exception monitoring rather than more difficult domain wide detection. Preferably there are symptom and cause conditions 

4. Automated actions. Upon detection of any of the above states events or conditions one or more automated actions can be triggered by the Virtual Regulator or CLSM Regulator . Automated actions may include but are not limited to the following 

Alternatively there may be some other action taken in order to automatically resolve the detected category. Moreover many other categories of detections and automated actions can be implemented.

Generally speaking CLSM Regulators provide real time closed loop system management over resources within the systems with the loop having a fairly narrow bandwidth typically on the order of milliseconds seconds or minutes. The Virtual Regulator provides real time closed loop system management over resources within the domain with the loop having a much larger bandwidth typically on the order of minutes hours or days.

Further while CLSM Regulators controls resources within the systems and the Virtual Regulator controls resources across the domain in many cases system resources and domain resources are the same. The Virtual Regulator has a higher level view of resources within the domain because it is aware of the state of resources of all systems while each CLSM Regulator is generally only aware of the state of resources within its own systems .

There are a number of techniques by which Virtual Regulator implements its adjustments to the allocation of system resources. For example and as illustrated in the Virtual Regulator communicates adjustments directly to CLSM Regulators and the CLSM Regulators then apply the relevant rule adjustments. Alternatively the Virtual Regulator communicates adjustments to the CLSM Regulators by passing them down a tree such as that in . In either case the CLSM Regulators incorporate adjustments ordered by the Virtual Regulator in the various systems .

Given that the Virtual Regulator has access to the state event and condition information from all CLSM Regulators it can make adjustments that are mindful of meeting SLGs for various workload groups. It is capable of for example adjusting the resources allocated to a particular workload group on a domain basis to make sure that the SLGs for that workload group are met. It is further able to identify bottlenecks in performance and allocate resources to alleviate the bottleneck. Also it selectively deprives resources from a workload group that is idling resources. In general the Virtual Regulator provides a domain view of workload administration while the CLSM Regulators provide a system view of workload administration.

Thus it will be appreciated that the illustrated Virtual Regulator is capable of monitoring the performance and operational characteristics of a plurality of systems across a domain . From this it provides a domain based approach to resource and performance management.

This concludes the description of the preferred embodiment of the invention. The following describe some alternative embodiments for accomplishing the same invention.

The invention has been primarily developed for monitoring and adjusting the operational characteristics of a plurality of systems within a domain. However it will be appreciated that the invention is in no sense limited to that application. For example the invention is generally applicable to a wide variety of environments where such functionality has value.

The foregoing description of the preferred embodiment of the invention has been presented for the purposes of illustration and description. It is not intended to be exhaustive or to limit the invention to the precise form disclosed. Many modifications and variations are possible in light of the above teaching. It is intended that the scope of the invention be limited not by this detailed description but rather by the claims appended hereto.

