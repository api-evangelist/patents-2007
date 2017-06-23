---

title: Method, apparatus and computer program for registering a respective target network system state from each one of a plurality of programs
abstract: It is disclosed a method comprising registering a respective target network system state from each one of a plurality of programs, each of the plurality of programs comprising a first program state, detecting a current network system state, selecting one or more of the plurality of programs based on a result matching the detected current network system state against the registered target network system states, and commanding transition of the selected one or more programs from the first program state to a second program state different from the first program state.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=07792777&OS=07792777&RS=07792777
owner: Nokia Corporation
number: 07792777
owner_city: Espoo
owner_country: FI
publication_date: 20070405
---
The present invention relates to a method apparatus and computer program for registering a respective target network system state from each one of a plurality of programs. In particular the present invention is advantageously applicable in mobile stations e.g. under consideration of the issues multi radio memory consumption reduction and power saving.

Communication technology has made considerable progress in recent time. With the ever advancing minimization of the physical size of mobile stations memory space within such mobile stations remains limited since ever more advanced memory technologies are proposed to offer substantially the same memory space on ever smaller physical space.

Considering e.g. a podcasting application i.e. an application for consuming media data e.g. visual and or audio data on a personal computer or a mobile device the application may be configured to detect the occurrence of connection of the device with e.g. a WLAN Wireless Local Area network network and to start downloading a data content. However in order to detect the connection to WLAN the application must be running and in resident memory. Mobile devices tend to have so little memory that loading multiple programs to memory in background is not possible. For example background applications may be closed when memory space becomes congested. If the application is forced to remain resident in memory it might prevent some other application from running e.g. web browser from displaying a large page .

Approaches have been suggested in which an application running e.g. on a mobile station that wishes to use a specific access technology e.g. WLAN remains resident in memory and checks for available access technologies e.g. regularly.

In consideration of the above it is an object of the present invention to overcome one or more of the above drawbacks. In particular the present invention provides method apparatus and computer program for registering respective a target network system state.

According to the present invention in a first aspect this object is for example achieved by a method comprising 

registering a respective target network system state from each one of a plurality of programs each of the plurality of programs comprising a first program state 

selecting one or more of the plurality of programs based on a result of matching the detected current network system state against the registered target network system states and

commanding transition of the selected one or more programs from the first program state to a second program state different from the first program state.

According to advantageous further refinements of the invention as defined under the above first aspect 

According to the present invention in a second aspect this object is for example achieved by an apparatus comprising 

a registrator configured to register a respective target network system state from each one of a plurality of programs each of the plurality of programs comprising a first program state 

a selector operably connected to both the registrator and the detector and configured to select one or more of the plurality of programs based on a result of matching the detected current network system state against the registered target network system states and

a commander operably connected to the selector and configured to command transition of the selected one or more programs from the first program state to a second program state different from the first program state.

According to advantageous further refinements of the invention as defined under the above second aspect 

According to the present invention in a third aspect this object is for example achieved by an apparatus comprising 

means for registering a respective target network system state from each one of a plurality of programs each of the plurality of programs comprising a first program state 

means operably connected to both the means for registering and the means for detecting and for selecting one or more of the plurality of programs based on a result of matching the detected current network system state against the registered target network system states and

means operably connected to the means for selecting and for commanding transition of the selected one or more programs from the first program state to a second program state different from the first program state.

According to the present invention in a fourth aspect this object is for example achieved by a computer program embodied on a computer readable medium configured to control a method comprising 

registering a respective target network system state from each one of a plurality of programs each of the plurality of programs comprising a first program state 

selecting one or more of the plurality of programs based on a result matching the detected current network system state against the registered target network system states and

commanding transition of the selected one or more programs from the first program state to a second program state different from the first program state.

According to advantageous further refinements of the invention as defined under the above fourth aspect 

In this connection it has to be pointed out that advantageously the present invention enables one or more of the following 

Hence many applications in mobile stations work faster or cheaper or consume less power when using a specific access technology. In addition memory in mobile stations is a scarce resource and must therefore be conserved. Due to this reason it is not practical to have such applications running in the mobile station permanently waiting for the suitable access to appear.

The present invention advantageously enables applications to register to a dispatching entity to wait for suitable radio access to appear. Once a suitable connection is available e.g. WLAN the dispatching entity may launch the application.

Embodiments of the present invention are described herein below by way of example with reference to the accompanying drawings.

As shown in a communication network comprises an access network . The access network serves e.g. for providing access to various services and is defined e.g. by a current network system state CP. The current network system CP state may be expressed by a set of one or more current network system state parameters CP . . . CP. These current network system state parameters may among others e.g. be network data rate connection cost an application type an inactivity time interval and or an identification of the at least one network technology.

The communication network further comprises a mobile station entity comprising a dispatching entity and one or more applications to n to stored e.g. on a ROM see . Each of the applications to may comprise a target network system state TP . . . TPbeing e.g. a set of one or more target network system state parameters TP. . . TP TP. . . TP. These target network system state parameters may among others e.g. be network data rate connection cost an application type an inactivity time interval and or an identification of the at least one network technology. The dispatching entity is described in detail herein below with reference to .

In step S each particular one of the applications to may register the respective target network system state TP . . . TPat the dispatching entity . The dispatching entity may be configured to store or hold the respective target network system states TP . . . TP as further described herein below with reference to . This registering may be performed e.g. upon installing the applications to or upon the applications to attempting to poll the access network . In this context registering a target network state at the dispatching entity e.g. means associating by and or at the dispatching entity the target network system state with the application.

Furthermore in step S e.g. the dispatching entity or the applications to themselves may be configured to perform transition of the applications to e.g. into a non resident state i.e. the applications to remain stored in the ROM but not resident in a RAM see . As an example this non resident state is indicated in by the applications to being hatched in their functional blocks from bottom left to top right.

In step S the current network system state CP of the access network is detected by the mobile station entity and is supplied e.g. to the dispatching entity .

In step S one or more of the applications to are selected based on a result of matching the detected current network system state CP against the registered target network system states TP . . . TP. This selecting may exhibit e.g. one of the following forms or combinations thereof 

 i best match the parameters of target network system state s TP . . . TPof the application s having e.g. the smallest mean distance to the parameters of the current network system state may be selected 

 ii weighted match the parameters of the current target network system state may be multiplied by specific gain coefficients prior to conducting the best match . As an example the parameter network data rate may be prioritized by a higher gain coefficient than that of the parameter connection cost 

 iii ordered match the parameters of the current target network system state may be matched in the order of parameters and only in case of ambiguities or too many hits occurring in e.g. the first parameter the second parameter is considered for matching etc 

 iv technology ID a parameter identifies the access technology that has been registered for the application s to use and such applications may be launched sequentially for instance based solely on this or in combination with other parameters 

 v Examples of such rules can further comprise for example that all applications whose target network system states match or sufficiently match the current network system state are launched simultaneously or that they are launched sequentially one after another such that a subsequent one is only launched after the previous one becomes non resident in a RAM.

In step S the dispatching entity may command the activation of the one or more of the selected applications to i.e. the transition from e.g. the non resident state into a resident state i.e. the executable objects are produced from the applications to stored in the ROM and are launched in a RAM see .

In step S the commanded one or more of the applications to may perform their scheduled tasks since being e.g. in the resident state indicated by the functional blocks of step S hatched from bottom right to top left .

In step S the commanded one or more of the applications to may be terminated e.g. by performing transition from the resident state to the non resident state indicated by the functional blocks of step S hatched again from bottom left to top right . Alternatively the dispatching entity may be configured to stop or pause the commanded one or more application to . In this case stopping or pausing the commanded one or more application to may be effected in co operation with the application e.g. based on interrupting execution of the application or pausing the transmission effected by the application. The application to in question may be configured to perform transition from the resident state to the non resident state and when performing transition from the non resident state to the resident state subsequently the application to in question may be configured to resume execution e.g. based on information on a preceding execution.

As shown in the mobile station entity comprises the dispatching entity a CPU for processing various signals a ROM a random access memory RAM and a transceiver Tx Rx and network measurement device or tool Tx Rx measurement entity hereinafter . It is to be noted that the functionalities of the Tx Rx measurement entity i.e. sending and or receiving e.g. via an access technology and measurement of the current network system state may be comprised in one entity as shown in or in entities distributed e.g. in the mobile station entity .

Furthermore the dispatching entity may comprise or have access to a selector and a registrator . The selector and the registrator may also be implemented as software code portions e.g. of the dispatching entity and or the CPU or as an operating system running e.g. on the CPU and may exhibit one or more of the following functionality functionalities 

It is to be noted that the dispatching entity may be implemented among others e.g. in the following forms or any combinations thereof 

 i on chip hardware implementation e.g. integrally with the CPU ROM and or RAM indicated by a broken line extension of the functional block of the CPU 

 ii hardware implementation e.g. as a chipset insertable device on an own chip to be inserted into the mobile station entity 

 iv software implementation e.g. as source code in the ROM and as a related executable object in the RAM .

Referring back to the applications to n to may be stored or held e.g. in the ROM in a non resident state indicated by being hatched from bottom left to top right . Alternatively the applications to may also be stored or hold in another ROM e.g. in the access network to which ROM the mobile station entity may have access. In this case the mobile station entity may not require comprising the ROM .

As described in conjunction with step S of the applications to may be configured to register their respective target network system states TP . . . TPin the dispatching entity e.g. by the registrator . Depending on the above described implementation form the dispatching entity may be configured to store or hold the registered target network system states TP . . . TPin a one to one correspondence with the respective applications to e.g. in the ROM the RAM a cache not shown of the CPU or the registrator itself.

As described in conjunction with step S of the current network system state CP CP . . . CP in the access network may be detected e.g. via the Tx Rx measurement entity . Alternatively the access network may also be configured to transmit or broadcast the current network system state CP in which case the Tx Rx measurement entity may not require comprising the measurement functionality and it may be sufficient to receive the current network system state from the network.

As described in conjunction with step S of the current network system state CP in the access network may be matched against the registered target network system states TP . . . TP. Furthermore as mentioned above the dispatching entity may be configured to store or hold pre determined rules e.g. in the selector on how to select one or more of the applications to based on the result of matching the current network system state CP against the target network system states TP . . . TP.

As described in conjunction with step S of the dispatching entity may be configured to command transition of the selected one or more of the applications to e.g. from the non resident state being stored in the ROM to the resident state being held in the RAM indicated by being hatched from bottom right to top left .

In a particular example to which the present invention is not to be restricted to the target network system states of two exemplary applications 1 and 2 may have the following form 

As described in conjunction with steps S and S of the commanded application as an example application 1 is chosen may have access to the access network e.g. via the Tx Rx measurement entity and e.g. the WLAN access technology and may terminate processing i.e. transition from the resident state to the non resident state upon completion of the task of the commanded application or upon interrupt e.g. from the dispatching entity .

Herein below a second embodiment of the present invention is described with reference to . For brevity of description only the differences to the first embodiment in conjunction with are described.

Referring back to the same reference signs designate the same or similar components in . For the sake of description brevity description of the components being unchanged as compared to i.e. communication network access network mobile station entity and applications 1 to n to as well as access technology is omitted.

As for the differences the dispatching entity according to the first embodiment may be distributed according to the second embodiment so that each of the applications to comprises an individual application portion constituting an individual dispatching entity DE to DE n . These individual dispatching entities to may e.g. be application portions or independent programs in a wait state indicated by being hatched from left to right i.e. the portion or independent program is in a non active resident state while the remainder of each of the applications to remain e.g. in the non resident state.

Therefore in step S of each particular one of the applications to may be configured to register the respective target network system state TP . . . TPat the individual dispatching entity to e.g. by the registrator . The dispatching entities to may be configured to store or hold the respective target network system state TP . . . TP as further described herein below with reference to . This registering may be performed e.g. upon installing the applications to or upon the applications to attempting to poll the access network .

Step S of may be substantially identical with step S of wherein the current network system state CP is supplied e.g. to all individual dispatching entities to

Steps S and S of may be substantially identical with steps S and S of . However the individual dispatching entities to may additionally be configured e.g. to be prioritized with respect to each other.

Referring back to the same reference signs designate the same or similar components in . For the sake of description brevity description of the components being unchanged as compared to i.e. access network mobile station entity CPU ROM RAM Tx Rx measurement entity selector registrator and applications 1 to n to as well as access technology is omitted.

As for the differences as described with reference to the dispatching entity according to the first embodiment may be distributed in the second embodiment so that each of the applications to comprises an individual application portion constituting an individual dispatching entity DE to DE n . Alternatively the individual dispatching entities DE to DE n may be constituted by independent programs respectively associated with the applications to . These individual dispatching entities to may e.g. be the application portions or the independent programs in a wait state indicated by being hatched from left to right i.e. the portion or the independent program is in a non active resident state while the remainder of each of the applications to remains e.g. in the non resident state.

It is to be noted that the dispatching entities to may be implemented among others e.g. in the following forms or a combination thereof 

 i software implementation e.g. as portions of the source code of the associated application in the ROM and as related executable objects in the RAM 

 ii software implementation e.g. as independent source codes not shown being associated respectively with the applications in the ROM and as related executable objects in the RAM .

Referring back to the remainder of the applications to n to may be stored or held e.g. in the ROM in a non resident state indicated by being hatched from bottom left to top right .

As described in conjunction with step S of the applications to may be configured to register the respective target network system state TP . . . TPin the respective individual dispatching entity to e.g. by the respective registrator .

As described in conjunction with step S of each of the individual dispatching entities to may be configured to have access to pre determined rules e.g. in a common or respective selector on how to select the associated remainder of the application to

As described in conjunction with step S of the dispatching entities to may be configured to command transition of the associated selected remainder of application to e.g. from the non resident state being stored in the ROM to the resident state being held in the RAM indicated by being hatched from bottom right to top left . In addition as mentioned above according to the second embodiment the dispatching entities to may e.g. be prioritized with respect to each other.

Due to the above the particular example given in the first embodiment may function in substantially the same way when effected in the second embodiment.

The second embodiment may be summarized as follows without being restricted to the implementation details a similar kind of effect as obtained in the first embodiment may be accomplished by launching first a smaller monitor portion of each application that assumes a non active resident state and performs transition to the active resident state e.g. periodically. If a connectivity e.g. in WLAN becomes available then the remainder of the actual application is launched e.g. as additional thread i.e. performs transition the resident state. So instead of a centralized dispatcher this can be done using an application specific dispatcher monitor. The application specific monitor may take the form of a portion of an application or the form of a standalone program and it may enter a wait state and emerge therefrom periodically or it may receive e.g. interrupts from the multi access transceiver when attachment to an access is completed. The dispatcher s may be triggered by an interrupt when the current network state parameters change.

Without being restricted to the following implementation details the present invention may be summarized according to the following It is proposed that a so called registrator is configured to register applications with specific kinds of accesses and these associations between applications and specific kinds of accesses may be stored in a dispatching entity . As soon as the access becomes available the dispatching entity may launch the application in question. When the application is installed or set to periodically poll the network the application in question may register itself to the dispatching entity. The parameters that are specified in the associations can e.g. be like the following 

The present invention is e.g. applicable to mobile devices which are resource constrained. The invention is also applicable if implemented e.g. as a public API Application Programming Interface for 3party developers or if implemented e.g. as closed function within a system.

generally the present invention is also applicable in those network terminal environments relying on a data packet based transmission scheme according to which data are transmitted in data packets and which are for example based on the Internet Protocol IP. The present invention is however not limited thereto and any other present or future IP or mobile IP MIP version or more generally a protocol following similar principles as M IPv4 6 is also applicable 

