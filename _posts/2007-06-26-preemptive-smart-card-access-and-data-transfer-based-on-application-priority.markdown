---

title: Preemptive smart card access and data transfer based on application priority
abstract: The invention relates to a personal token running a series of applications, wherein said personal token includes a thread controller which transmits data from the applications to an external device in a cyclic way, a cycle being constituted of a series of data transfers from the applications and to the external device, a cycle comprising a respective number of data transfers dedicated to each respective application which is different according to the respective application, the number of data transfers for a respective application in a cycle corresponding to a priority level of the application as taken into account by the thread controller.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08863135&OS=08863135&RS=08863135
owner: Gemalto SA
number: 08863135
owner_city: Meudon
owner_country: FR
publication_date: 20070626
---
The invention relates to personal tokens used for authenticating a user when such user accesses to a limited or a private resources equipment such as a mobile telecommunication network a remote server storing secret data or even a protected area with limited physical access thereto.

The mostly known device of this type is the IC card such as for example a SIM card Subscriber Identification Module or a credit card but it can also be a USB key a mass memory card or any kind of token carrying some necessary credentials.

Because of the resource limitation in SIM card previous generation of SIM card usually can only work in single thread model where only one SIM application can run at one time.

Later generation of SIM cards can work with multi thread model by using a Logical Channel concept using a different APDU parameter so as to indicate to use different threads . But this method has little acceptance because it raises compatibility issues between terminals and SIM cards.

Multi thread model of SIM applications is more and more required. Particularly in recent transition of SIM application role from STK SIM application toolkit only which requires only single thread model to SCWS Smart Card Web Server which requires to handle several requests from web clients in parallel.

In such respect one purpose of the invention to provide an enhanced method to control several simultaneous processes threads of data transfer sessions between a terminal and a personal token in general e.g. SIM card in particular.

An embodiment will now be described in the context of a SIM Subscriber Identification Module and in relation to a mobile phone terminal as depicted schematically on .

Such SIM stores and runs a set of applications for example Java applications referenced A B C on . In addition to applications A B and C the exemplified SIM includes a logic entity typically a software program which is a thread controller TC as described hereafter. Thread Controller TC is here a program which controls several threads that share one APDU Application Protocol Data Unit exchange channel between the SIM card and the terminal. Thread controller TC will perform a time sharing of the channel based on an APDU switching between several threads so they can run in parallel.

The terminal as for itself includes a software equipment for example a set of terminal applications which is represented under general reference TS on .

In the present embodiment the SIM applications have to run in compliance with a multi thread model i.e. they have to exchange APDU commands with the terminal in a seemingly simultaneous manner i.e. more precisely some of the applications of the SIM may send and receive APDUs in an alternate manner. For example a first application may send and receive a first set of APDUs and then another application may send and receive its own set of APDUs before the first application then goes on with a following set of further APDUs.

A data transfer is considered here as an APDU transfer between terminal and SIM card. Here the SIM card can act as both server and client. In this embodiment one session of data transfer is considered as one thread.

Simultaneous process of data transfer sessions here is management of several data transfer sessions which are running in parallel.

There will now be described how the thread controller TC interfaces with the SIM applications A B and C.

All SIM applications A B and C have registered by the thread controller. This preliminary step occurs preferably at power on of the mobile phone. During such registration every SIM application shall provide its priority parameter to the thread controller which priority parameter may range from 0 lowest priority to N highest priority . However each application may change its priority in the middle by registering again to the thread controller. Such priority changing may be triggered for example by a particular routine of the application being reached which requires a higher amount of exchanges with the terminal.

One channel APDU which is available will be shared between several SIM applications. The mechanism to share this channel is using of a time sharing approach instead of logical channel approach . Before any APDU exchange thread controller will decide which application needs to be invoked and send its APDU to the terminal.

The thread controller TC manages a queue buffer to manage all the application which register to it. Queue buffer stores the reference of all SIM applications which have been registered. For the purpose of managing the applications a higher priority application has more entries in the buffer. For example an application with priority 2 will have 2 entries in the queue and an application with priority 5 will have 5 entries in the queue.

To manage the time sharing mechanism and select the application to use the APDU channel the thread controller TC scans the queue buffer in a cyclic way. In this way the application which has higher priority will automatically has more chance to use APDU channel.

Priority 1 means for every cycle Thread Controller will activate the particular SIM application one time. Priority 5 still 

A data transfer session is a session of data transfers between client and server. One session can consist of several APDU exchanges. During a data transfer session both server and client must maintain several session variables i.e. the above mentioned context which is specific to the current session and can only be cleared after the session is finished. The thread controller TC will also manage buffers which store each active thread s context. This context to be buffered can be 2 kinds The first kind is the APDU which is about to be sent by the SIM application. The second kind is the APDU which is a response from the terminal and which is supposed to be sent to the application.

A more precise example will now be given in reference to in which five SIM applications A B C D E are implied.

Those five SIM applications have been registered to the thread controller TC. Application A is registered with priority A 1 application B is registered with priority 3 application C is registered with priority 5 application D is registered with priority 0 and application E is registered with priority 6 where 6 is the highest priority i.e. the above mentioned N priority.

Suppose that these five applications are running in parallel content of queue buffer in thread controller will be like A B B B C C C C C . . . .

The respective threads D and E of applications D and E will not be stored in the queue buffer. Thread E will be executed first until it is finished. Then threads A B C will be executed in parallel with APDU switch mechanism.

The cycle of execution will be A B B C C C C C A B B . . . until finish. After A B C are finished thread D will be executed.

In step the terminal software TS receives the APDU from application A. Because the next step is the turn of application B thread controller TC creates the context buffer for application A which has just received the response APDU from terminal software TS so that the stored context includes the returned APDU.

In step application B is enabled to send an APDU to terminal software TS because now it is the turn of application B.

In step terminal software TS receives an APDU command from application B and terminal software TS returns an APDU command for application B. The context buffer which relates to application A is still preserved.

In step application B can still send an APDU command to terminal software TS. In step terminal software TS receives such APDU command from application B.

Because the next step is the turn of application C thread controller TC creates the context buffer which relates to application B. In step application C is enabled to send an APDU command to terminal software TS because now it is the turn of application C.

The next step i.e. the step at the end of the illustrated doted arrow is a step where the turn of application A comes back. Thread controller TC switches from context buffer of application C to context buffer of application A. Context buffer of application A contains the return APDU from terminal software TS to application A as occurred in Step

On similar basic steps are illustrated. represents a situation where threads A and B are running. In addition to the example explained above after some time application E starts running triggered by a specific event. At step E thread E interrupts threads A and B because it has priority 6 i.e. above explained priority N . Thread controller TC will allocate all of time for thread E until it is finished before resuming at step E to execute threads A and B.

The present embodiment of the invention has been described wherein the thread controller is implemented in the SIM. In an alternate embodiment of the invention the thread controller may be implemented in the mobile terminal and may control the priorities of applications which may reside in the associated SIM.

