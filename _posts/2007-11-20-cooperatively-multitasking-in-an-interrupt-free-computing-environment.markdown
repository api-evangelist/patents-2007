---

title: Cooperatively multitasking in an interrupt free computing environment
abstract: Multitasking in a hardware interrupt free environment. Event indicators are employed to multitask between processes of the environment. Processes to be multitasked register with one another, and then during processing, one of the processes toggles an event indicator to allow another process to execute. The toggling allows the processes to share resources in an interrupt free environment.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08056078&OS=08056078&RS=08056078
owner: International Business Machines Corporation
number: 08056078
owner_city: Armonk
owner_country: US
publication_date: 20071120
---
This application is a continuation of U.S. patent application Ser. No. 10 421 978 filed on Apr. 22 2003 entitled Cooperatively Multitasking in an Interrupt Free Computing Environment by Fred A. Bower III published on Oct. 28 2004 as U.S. Patent Publication No. US 2004 0216100 A1 and issued on Mar. 4 2008 as U.S. Pat. No. 7 340 740 B2 the entirety of which is hereby incorporated herein by reference.

This invention relates in general to multitasking within a computing environment and in particular to multitasking in a hardware interrupt free computing environment.

At times it is desirable to operate within a computing environment with limited functionality enabled. This reduces complexity and facilitates debugging. However in order to provide limited functionality certain features are disabled or not provided. One such feature is system or hardware interrupts. The disabling of system interrupts reduces the complexity of the environment but at a cost. The cost is that certain functions are not provided such as for instance multitasking.

Multitasking enables an individual process to share resources e.g. CPU memory etc. with one or more other individual processes without requiring the process to completely exit before allowing another process to execute. Instead the multitasking processes remain resident in memory.

With the disabling of system interrupts however multitasking is not performed. Instead a process runs for a period of time saves its state in persistent storage and then exits completely before another process that is to share the resource commences execution. This increases complexity and degrades system performance. Thus a need exists for a capability that enables multitasking in the absence of hardware interrupts.

The shortcomings of the prior art are overcome and additional advantages are provided through the provision of a method of multitasking in a computing environment. The method includes for instance executing a first process in a hardware interrupt free computing environment and multitasking the first process with a second process of the hardware interrupt free computing environment wherein the multitasking includes employing one or more event indicators.

In one example the employing includes toggling at least one event indicator of the one or more event indicators to indicate which process of the first process and the second process is to execute.

In another embodiment a method of multitasking in a single processor environment is provided. The method includes for instance executing a first process in a hardware interrupt free single processor environment and multitasking the first process with a second process of the hardware interrupt free single processor environment.

System and computer program products corresponding to the above summarized methods are also described and claimed herein.

Additional features and advantages are realized through the techniques of the present invention. Other embodiments and aspects of the invention are described in detail herein and are considered a part of the claimed invention.

In accordance with an aspect of the present invention a multitasking capability is provided that enables processes to cooperatively multitask in a hardware interrupt free computing environment. The processes employ event indicators to perform the multitasking as one example. The toggling of the event indicators indicates that a process is to sleep while another is to execute.

One embodiment of a computing environment to incorporate and use one or more aspects of the present invention is described with reference to . A computing environment includes for instance a central processing unit a memory e.g. main memory and one or more input output I O devices coupled to one another via for example one or more buses .

As one example computing environment includes an Itanium processor i.e. a single threaded single processor executing the Extensible Firmware Interface EFI available from Intel Corporation Santa Clara Calif. EFI is a firmware operating environment that supports utility applications such as diagnostics or operating system loaders. EFI is built to particular specifications. EFI allows a machine to operate without an extensive amount of configuration or functionality by instituting certain rules. As an example processes are limited to particular priority levels. That is a given process may temporarily increase its priority level of operation if it is operating at a low or medium priority level but is not allowed to decrease its priority level of operation according to the specifications. Further a higher priority process is not allowed to launch lower priority processes.

Although EFI has instituted these rules to reduce complexity there are times when greater functionality is beneficial even within the EFI environment. Thus steps have been taken to overcome some of the limitations of EFI. For example a capability is now provided in which a higher priority task is able to launch lower priority tasks. This is described in U.S. patent application Ser. No. 09 898 978 entitled Method of Launching Low Priority Tasks filed on Jul. 2 2001 and published on Jan. 2 2003 as U.S. Patent Publication No. US 2003 0005026 A1 which is hereby incorporated herein by reference in its entirety.

As a further example within an EFI environment system or hardware interrupts are disabled in order to reduce complexity within the environment. The disabling of the interrupts however effects the providing of certain functions that may be beneficial. This includes for instance multitasking in which separate and distinct processes share resources e.g. hardware resources such as CPU memory etc. of the computing environment to execute. Thus in accordance with an aspect of the present invention a capability is provided that enables multitasking to be performed in a hardware interrupt free environment.

One embodiment of the logic associated with an initialization procedure to enable multitasking in a hardware interrupt free environment is described with reference to . Initially an executive process is initialized STEP . The executive process is typically but not necessarily a process that runs at a higher priority than other processes. It may be for instance a diagnostic executive that is responsible for launching monitoring and interpreting results from diagnostic tests. The diagnostic executive resides in memory and runs at a privileged level that allows it to have at least some control over the diagnostic tests. The initialization includes for instance initializing a memory location for an event indicator e.g. a flag which is of a predefined size e.g. one or more bits .

In addition to initializing the executive process a polling event e.g. in EFI an EVT Notify signal event is created STEP . This polling event indicates for example that when a process goes to sleep on the event a corresponding event indicator is reset e.g. cleared and one or more other processes are allowed to execute. As is known the polling event is a software construct that supports the waiting upon the toggling of the flag. In some environments such as EFI one or more application programming interfaces APIs are provided to create the polling event.

Moreover one or more other processes are initialized STEP . In the diagnostic example these processes may be tests. However the processes need not be diagnostic tests other types of processes may be initialized. Similar to the executive each of these processes creates an event indicator and places it in a selected memory location. Likewise each process creates its own event which is similar to the executive s event STEP .

The processes then register with the executive STEP . This includes for instance a registration handshake in which the memory locations of event indicators for the processes are exchanged. For example a process provides to the executive an indication of where its indicator is located and in turn the executive provides to the process a location of its indicator. Thus in this example the executive and other processes are cooperative in that they at least implicitly work together to enable multitasking. The registration process completes the initialization technique and allows multitasking to commence.

One embodiment of the logic associated with multitasking in a hardware interrupt free environment is described with reference to . Initially the executive sets the flag corresponding to a cooperative process event indicating that the cooperative process can run STEP . The executive s flag is in the cleared state and the executive goes to sleep waiting on its event STEP . A scheduling process such as the EFI scheduling process determines that the cooperative process event has been triggered and it awakens the cooperative process for execution STEP . In one example the EFI scheduler places the process in a ready to execute queue.

The process executes STEP and at a desired time e.g. at end of execution or other selected time the process triggers the executive s event STEP . For example the process sets the executive flag. Further the process goes to sleep waiting on its event flag STEP and its event flag is reset.

The scheduling process then determines that the executive process event has been triggered and awakens the executive process for execution STEP . The executive process executes for an amount of time e.g. until a particular task is completed or some other selected time STEP and processing continues at STEP .

Described in detail above is a multitasking capability that enables processes to be multitasked in a hardware interrupt free environment. In one example the environment is a single processor environment. Any number of processes can be supported.

Advantageously multitasking is enabled in a hardware interrupt free environment. Multitasking allows processes to share resources e.g. hardware resources such as CPU memory etc. without having to terminate execution. Instead each process remains active in memory in order to preserve the process state. The processes simply go to sleep to enable one or more other processes to execute and then in turn are awakened. The sharing of the resources is transparent in that a user is not aware that multiple processes are operating in the same physical hardware.

The multitasking capability advantageously allows multiple processes to run simultaneously passing active execution back and forth to one another through a set of events which are controlled by flags.

This multitasking capability is beneficial for many functions including diagnostic testing. Advantageously the diagnostic executive executes for a certain amount of time and then allows one or more other testing processes to run. In accordance with an aspect of the present invention the diagnostic executive is a mid priority dispatcher of one priority e.g. either medium or high priority that enables a lower priority process to be spawned when the process event is triggered. The lower priority process executes for a period of time and then allows the executive to run again.

Thus in accordance with one or more aspects of the present invention multitasking is provided in environments that do not allow and or do not use hardware interrupts. Additionally a programmer is able to span privilege domains in directions not allowed for within EFI and similar environments.

Although an example of a computing environment is described above this is only an example. A computing environment having different components may incorporate and or use one or more aspects of the present invention. For instance a processor may be other than an Itanium processor and or other than an Intel processor. Further the computing environment need not include the EFI environment. Other variations are also possible and are considered a part of the claimed invention. Moreover other computing and or operating environments may incorporate and use one or more aspects of the present invention without departing from the spirit of the present invention.

Further in another embodiment the executive process may be other than a diagnostic executive. In yet another example there need not be an executive process just processes that are to be multitasked. Further the processes need not be diagnostic tests. Moreover although in this example one process is actively running at a time in other examples more than one process can be actively running.

The present invention can be included in an article of manufacture e.g. one or more computer program products having for instance computer usable media. The media has embodied therein for instance computer readable program code means for providing and facilitating the capabilities of the present invention. The article of manufacture can be included as a part of a computer system or sold separately.

Additionally at least one program storage device readable by a machine embodying at least one program of instructions executable by the machine to perform the capabilities of the present invention can be provided.

The flow diagrams depicted herein are just examples. There may be many variations to these diagrams or the steps or operations described therein without departing from the spirit of the invention. For instance the steps may be performed in a differing order or steps may be added deleted or modified. All of these variations are considered a part of the claimed invention.

Although preferred embodiments have been depicted and described in detail herein it will be apparent to those skilled in the relevant art that various modifications additions substitutions and the like can be made without departing from the spirit of the invention and these are therefore considered to be within the scope of the invention as defined in the following claims.

