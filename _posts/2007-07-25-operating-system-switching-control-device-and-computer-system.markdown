---

title: Operating system switching control device and computer system
abstract: In a computer system according to the present invention, a switch-source OS controller unit includes: a OS switch request receiver unit configured to receive an OS switch request for requesting that the switch-destination OS in a suspend status becomes the OS in the active status; a switch event notifying unit configured to notify event information to the switch-destination OS or an application on the switch-destination OS, the event information being included in the received OS switch request, and requesting the switch-destination OS or the application on the switch-destination OS to perform a process; and a switch controller unit configured to call the OS switching function, by using the event information as an argument, so that the switch-destination OS becomes the OS in the active status.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08042117&OS=08042117&RS=08042117
owner: NTT DoCoMo, Inc.
number: 08042117
owner_city: Tokyo
owner_country: JP
publication_date: 20070725
---
This application is based upon and claims the benefit of priority from the prior Japanese Patent Applications No. 2006 202603 filed on Jul. 25 2006 and P2007 171099 filed on Jun. 28 2007 the entire contents of which are incorporated herein by reference.

And the entire contents of the US laid open disclosure public patent bulletin No. 20010018717A1 which are incorporated herein by reference.

The present invention relates to an operating system switching control device provided in a computer system comprising an operating system switching function of exclusively switching an operating system in an active status from one operating system called a switch source operating system to another operating system called a switch destination operating system .

In addition the present invention further relates to a computer system which includes a plurality of operating systems each exclusively becoming an operating system in an active status or a plurality of virtual operating systems provided by a single operating system with a plurality of setting modes and in which an operating system switching function exclusively switches an operating system in the active status from a switch source operating system to a switch destination operating system

2. Description of the Related Art Conventionally there has been known a configuration in which a plurality of operating systems hereinafter referred to as OSs is installed on a computer system terminal so that an OS in an active status can be switched between the OSs.

In the above mentioned configuration a suspend resume function of OS is utilized and a first OS in the active status becomes in a suspend status a paused status and thereafter a second OS in the suspend status is resumed so that the OS in the active status is exclusively switched.

In other words if one OS a first OS is in the active status the other OS a second OS is in the suspend status an inactive status .

With the application of the above mentioned configuration it is possible to built a computer system with two or more execution environments also referred to as domains having different usages or OS types.

For example it is possible to build a computer system in which executable public and private domains coexist by switching an OS in the active status between a first OS used for process on private information and a second OS used for process on business information.

In addition it is possible to build a computer system by using Linux OS registered trademark for the first OS and Windows Mobile registered trademark for the second OS.

In the above mentioned configuration each of the plurality of OSs exclusively becomes in the active status and therefore an OS in the suspend status an inactive OS needs to be switched to become in the active status in order to perform a process.

Here a possible trigger for switching the inactive OS to become in the active status is an event a switch event such as an push of a switch button by a user a reception of a telephone call or data call whose destination is the inactive OS a request for executing a function on the inactive OS or an expiration of a timer registered by the inactive OS .

Accordingly in the above mentioned configuration there is a challenge that when an OS in the active status is switched from a switch source OS to a switch destination OS in response to an occurrence of the above mentioned switch event it is necessary to notify such switch event to the switch destination OS and to perform a suitable process for the switch event in the switch destination OS.

In particular a switch destination OS is required to promptly perform a process for an urgent event a switch event such as reception of an incoming telephone call. For this reason there is a need to reduce a time required for switching from a switch source OS to a switch destination OS.

Furthermore a first challenge in the above mentioned technique is to prevent a critical process from being interrupted by switching an OS in the active status.

More specifically there is a problem that since it is desired to reject or suspend the switching of the OS in the active status during executing the critical process such as process for a telephone call which is not desirable to be interrupted even if a switch event occurs it is necessary to lock the switching of the OS in the active status during executing the critical process.

Specifically when means for locking the switching of the OS in the active status is used in order to achieve the first challenge there is a possibility that the lock is not properly unlocked due to a failure and that the switching of the OS in the active status becomes impossible. For this reason it is necessary to achieve the second challenge to maintain the function of switching an OS in the active status even if a failure occurs.

The present invention has been made in view of the forgoing challenges. Accordingly an object of the present invention is to provide an operating system switching control device and a computer system which are capable of executing the switch processes of the switch source OS and the switch destination OS which are selected in accordance with to event information while reducing a time required for switching from a switch source OS to a switch destination OS and a time required for performing a process for a switch event addressed to is an inactive OS. In order to reduce these times the operating system switching control device and the computer system are capable of changing the switch process very flexibly in response to an occurring switch event by allowing the switch processes corresponding to the event information to be optimized.

In addition an object of the present invention is to provide an operating system switching control device and a computer system which are capable of executing safely the switching of an OS in the active status by checking whether or not a process to prohibit the switching of the OS in the active status is being executed.

A first aspect of the present invention is summarized as an operating system switching control device provided in a computer system comprising an operating system switching function of exclusively switching an operating system in an active status from a switch source operating system to a switch destination operating system including a switch source operating system controller unit configured to operate when the switch source operating system is in the active status wherein the switch source operating system controller unit includes an operating system switch request receiver unit configured to receive an operating system switch request for requesting that the switch destination operating system in a suspend status becomes the operating system in the active status a switch event notifying unit configured to notify event information to the switch destination operating system or an application on the switch destination operating system the event information being included in the received operating system switch request and requesting the switch destination operating system or the application on the switch destination operating system to perform a process and a switch controller unit configured to call the operating system switching function by using the event information as an argument so that the switch destination operating system becomes the operating system in the active status.

In the first aspect the switch controller unit can be configured to further perform a switch process of a switch source operating system selected in accordance with the event information.

In the first aspect the operating system switching control device can further include a switch destination operating system controller unit configured to operate when the switch destination operating system is in the active status wherein the switch destination operating system controller unit can include a switch event acquiring unit configured to acquire the event information after the switch destination operating system becomes the operating system in the active status and an event processor unit configured to execute an event process corresponding to the acquired event information.

In the first aspect the switch controller unit can be configured to further perform a switch process on a switch destination operating system selected in accordance with the acquired event information.

In the first aspect the switch source operating system controller unit can include a switch judgment unit configured to determine whether or not the switch source operating system can become the operating system in a suspend status and when it is determined that the switch source operating system can become the operating system in the suspend status the switch controller unit can be configured to instruct the operating system switching function that the switch destination operating system becomes the operating system in the active status.

In the first aspect the switch source operating system controller unit can include a switch lock request receiver unit configured to receive a switch lock request for requesting to prohibit or stop prohibiting that the switch source operating system becomes the operating system in the suspend status and the switch judgment unit is configured to determine whether or not the switch source operating system can become the operating system in the suspend status in accordance with the received switch lock request.

In the first aspect the switch lock request receiver unit can be configured to receive the switch lock request including a priority the operating system switch request receiver unit can be configured to receive the operating system switch request including a priority and the switch judgment unit can be configured to determine whether or not the switch source operating system can become the operating system in the suspend status in accordance with the priority of the received switch lock request and the priority of the received operating system switch request.

In the first aspect the switch source operating system controller unit can include an activity notifying unit configured to periodically notify to the operating system switching function that the operating system switching control device operates normally.

In the first aspect the switch source operating system control unit can include an operation inspector unit configured to monitor an executing process which is being executed in the switch source operating system and the switch judgment unit can be configured to determine whether or not the switch source operating system can become the operating system in the suspend status in accordance with the executing process.

In the first aspect the switch source operating system control unit can include an switching permission information manager unit configured to manage information on whether or not the switch source operating system can become the operating system in the suspend status for a combination of the event information and a process type for specifying the executing process the operation inspector unit is configured to monitor whether or not a process specified by the process type is being executed in the switch source operating system and the switch judgment unit is configured to determine whether or not the switch source operating system can become the operating system in the suspend status in accordance with the combination of the process type for specifying the executing process and the notified event information by referring to the switching permission information manager unit.

In the first aspect the switch source operating system controller unit can include an switching permission information manager unit configured to manage information on whether or not the switch source operating system can become the operating system in the suspend status for a combination of the event information and a process type for specifying the executing process and the switch lock request receiver unit is configured to receive the switch lock request for every process type the switch judgment unit can be configured to determine whether or not the switch source operating system can become the operating system in the suspend status in accordance with the combination of the process type corresponding to the switch lock request and the notified event information by referring to the switching permission information manager unit.

In the first aspect the switch source operating system controller unit can include a user inquiring unit configured to make an inquiry to a user about whether or not the switch source operating system can become the operating system in the suspend status the switching permission information manager unit can be configured to manage for the combination of the event information and the process type whether or not an inquiry needs to be made to a user about whether or not the switch source operating system can become the operating system in the suspend status and the switch judgment unit can be configured to determine whether or not the switch source operating system can become the operating system in the suspend status in accordance with a result of making the inquiry to the user.

A second aspect of the present invention is summarized as a computer system which includes a plurality of operating systems each exclusively becoming an operating system in an active status or a plurality of virtual operating systems provided by a single operating system with a plurality of setting modes and in which an operating system switching function exclusively switches an operating system in the active status from a switch source operating system to a switch destination operating system the computer system including an operating system switching control device configured to operate when the switch destination operating system is in the active status wherein the operating system switching control device includes an operating system switch request receiver unit configured to receive an operating system switch request for requesting that a switch destination operating system in a suspend status becomes an operating system in the active status a switch event notifying unit configured to notify event information to the switch destination operating system or an application on the switch destination operating system the event information being included in the received operating system switch request and requesting the switch destination operating system or the application on the switch destination operating system to perform a process and a switch controller unit configured to call the operating system switching function by using the event information as an argument so that the switch destination operating system becomes the operating system in the active status.

In the second aspect the switch controller unit can be configured to further perform a switch process of the switch source operating system selected in accordance with the event information.

By referring to description will be given of a configuration of a computer system according to a first embodiment of the present invention.

A computer system according to this embodiment has a configuration on which a plurality of OS and OS that each operate exclusively and in which an OS in the active status an active OS is switched by an OS switching function .

The OS switching function is configured to switch among a plurality of physically different OSs and to switch among a plurality of virtual OSs.

Here at the time of switching among the plurality of physically different OSs the OS and OS are executed by different programs.

As for switching among the plurality of OSs a status of hardware an OS or an application when a switch source OS is in the active status is suspended saved and a status of hardware an OS or an application when a switch destination OS is in the active status is resumed restarted .

As shown in the computer system according to this embodiment is provided with an OS switching control device A for the OS and an OS switching control device B for the OS.

Since the above mentioned OS switching control devices A and B basically have a same configuration the description will be given of the configuration of the OS switching control device A.

As shown in the OS switching control device A is provided with an OS switch request receiver unit a switch event notifying unit a switch controller unit a switch event acquiring unit an event processor unit a switch prohibition data notifying unit an activity notifying unit an operation inspector unit a switch lock request receiver unit a lock status manager unit a switching permission information manager unit a user inquiring unit and a switch judgment unit .

It is to be noted that functions to composing the OS switching control device A can be classified into two kinds a switch source OS controller unit which operates if the OS switching control device A is provided in the switch source OS and a switch destination OS controller unit which operates it the OS switching control device A is provided in the switch destination OS.

Here the switch source OS controller unit is provided with the OS switch request receiver unit the switch event notifying unit the switch controller unit the switch prohibition data notifying unit the activity notifying unit the operation inspector unit the switch lock request receiver unit the lock status manager unit the switching permission information manager unit the user inquiring unit and the switch judgment unit .

On the other hand the switch destination OS controller unit includes the switch event acquiring unit and the event processor unit .

Here the OS switching control device A is provided in the computer system including an OS switching function which exclusively switches an OS in the active status an active OS from the switch source OS to the switch destination OS.

Specifically all of the functions to composing the above mentioned OS switching control device A may be provided inside the OS or may be provided outside the OS.

In addition it is also possible that a part of the functions to composing the above mentioned OS switching control device A may be provided inside the OS and the rest of the functions to may be provided outside the OS.

Furthermore the functions to composing the OS switching control device A may be implemented by software or hardware.

The OS switch request receiver unit is configured to receive an OS switch request for requesting that the switch destination OS in the suspend status becomes an OS in the active status.

Specifically the OS switch request receiver unit is configured to show a cause a switch event of switching the OS in the active status and to receive and hold the OS switch request including event information requesting the process by an application on the switch destination OS or by the switch destination OS.

For example the OS switch request receiver unit may be configured to receive an OS switch request in any receiving mode such as a function call in accordance with the Application Programming Interface API disclosed by the OS switching control device A a message passing or the like 

For example as a specific example of the function based on the API a design such as OS Switch Event Receive event param is possible in which event indicating event information and an additional parameter param are used as arguments.

In addition the OS switch request receiver unit may receive an OS switch request including event information requesting the switch source OS to make notification.

For example as the above mentioned event information it is possible that a time in the future is set and that notification is requested when the time comes.

Furthermore the OS switch request receiver unit may be configured to receive an OS switch request including a priority.

The switch event notifying unit is configured to notify event information to the OS which is the switch destination OS the OS switching control device B for the OS or the application on the OS .

The event information is included in the received OS switch request and requests a process by the application on the switch destination OS or by the switch destination OS.

For example the switch event notifying unit may be configured to notify the OS of event information by using asynchronous message passing means for performing asynchronous message passing which writes a message on a region shared with the OS or to notify the OS of the event information by using another communication means.

Note that each of the OS and OS is configured to operate exclusively. In other words if the OS is in the active status the OS is in the inactive status the suspend status .

Accordingly the switch event notifying unit notifies the OS of the event information not by synchronous type communication means such as a TCP IP socket or the like but by asynchronous communication means.

For example the switch event notifying unit can notify the OS of the event information by calling the function such as OS Switch Event osid event parm .

Here the osid denotes an identifier of the source destination OS the event denotes event information indicating a cause a switch event of switching an active OS for example reception of an incoming telephone call reception of a incoming mail a switching button input an application activating request from another OS or the like and the param denotes an additional parameter dependent on the event information.

If an OS switch prohibition flag is not set by the determination unit that is when it is determined that the switch source OS can become an OS in the suspend status when it is determined that OS in the active status can be switched the switch controller unit is configured to execute the switch process of the switch source OS selected in accordance with the event information to delete all of the OS switch requests held by the OS switch request receiver unit to call the OS switching function by using the event information as an argument and thereby to instruct the OS being an inactive OS to become an OS in the active status.

For example if a switch event of receiving an incoming telephone call occurs as the switch process of the switch source OS as described above in order to reduce a call receiving process time it is assumed that a status of communication device relating to the telephone call is saved in a region shared with the switch destination OS or that one part of an encryption process or a deleting process for protecting data or the like on a memory or storage of the switch source OS is omitted.

In addition as an example of utilizing the event information that the OS switching function receives as the argument it can be considered that storing suspending a status of one part of hardware an OS or an application is omitted.

If a user inquiring flag is set by the switch judgment unit the switch controller unit may call a user inquiring unit and determine whether or not the OS switching function is called in response to a result of inquiry on the user by the user inquiring unit .

The switch event acquiring unit is configured to acquire the event information notified by the OS switching control device B for the OS after the OS becomes in the active status.

In other words the switch event acquiring unit is configured to acquire the event information notified by the switch source OS after the OS in the active status is switched.

It is to be noted that similar to the switch event notifying unit the switch event acquiring unit for example may acquire the event information by using means for performing asynchronous message passing which writes a message on a region shared between the OS and OS or may acquire the event information by using another means of communications.

The event processor unit is configured to perform the switch process of the switch destination OS selected corresponding to the event information acquired by the switch event acquiring unit and the event process.

For example as switch process of the above mentioned switch destination OS it is assumed that a status of the communication device saved in the region shared with the switch source OS in order to promptly process an urgent switch event such as receiving an incoming telephone call is recovered or that decoding of the data on the memory or storage is put off to reduce the amount of process .

For example the event processor unit is configured to prepare a table of managing combinations of event information and event process as shown in to select suitable process event process by using a key of the event information acquired by the switch event acquiring unit so that the above mentioned process can be called.

In the example of if event information of receiving an incoming telephone call is acquired the event processor unit determines that the event process of activating a telephone application is requested and executes such event process.

If event information of an application activating request for requesting to activate an application is acquired the event processor unit determines that the event process of activating an application designated by the application activating request is requested and executes such event process.

In addition in the example of if event information of a switching button input is acquired the event processor unit determines that special event process is not requested and does not execute the special event process.

Incidentally it may be possible to embed event process corresponding to the event information themselves in a program that implements the event processor unit instead of preparing a table shown in in the event processor unit .

Furthermore in a case where the execution of the event process is failed because the application cannot be activated even if the event process corresponding to the event invention is tried to be executed or in a case where the event process can be normally executed the event processor unit may notify the OS switching control device B for the switch source OS of the execution result.

The switch prohibition data notifying unit is configured to notify the OS switching function of OS switch prohibition data.

For example the switch prohibition data notifying unit is configured to notify the OS switching function of the OS switch prohibition data by writing the OS switch prohibition data in the region shared between the OS switching function and the OS switching control device B or in a region designated by the OS switching function .

Here the OS switch prohibition data includes information indicating whether or not an OS in the active status can be switched for example an OS switch prohibition flag and information of a reason why the switching of the OS in the active status is prohibited.

For example the switch prohibition data notifying unit is configured to notify the OS switching function of the OS switch prohibition data by calling a function such as OS Switch Control flag status alive .

Here the flag denotes an OS switch prohibition flag being the information indicating whether or not the OS in the active status can be switched the status denotes a reason of prohibiting the switching of the OS in the active status for example during a telephone communication or data communications or the like and the alive denotes the information indicating that the OS or the OS switching control device A is alive such as a time stamp and a count .

The activity notifying unit is configured to notify the OS switching function of the fact that the OS or the OS switching control device A is normally operated by periodically notifying the OS switching function of predetermined information.

It is to be noted that the activity notifying unit may notify the OS switching function of the predetermined information with similar means to that of the switch prohibition data notifying unit or may notify the OS switching function of the predetermined information with another means.

Here as one example of the predetermined information to be notified an increasing counter time information time stamp or the like can be pointed out.

The OS switching function can determine that a failure is occurred in the OS switching control device A in a case where the above mentioned counter is not increased for a predetermined period of time or more or in a case where the time information is not updated.

In such cases the OS switching function may be configured to delete or ignore the received OS switch prohibition data or may be configured to perform hardware reset reboot of the computer system itself.

The operation inspector unit is configured to monitor an executing process which is being executed in the OS in which the OS switching control device A is arranged.

For example as shown in the operation inspector unit manages an operating status management table which associates a process type with a switch prohibition process flag .

Here the process type is for specifying a specific process which requests prohibition of switching the OS in the active status whereas the switch prohibition process flag is for indicating whether or not the process specified by the process type is in execution.

It is to be noted that if the switch prohibition process flag is set it indicates that the process specified by the process type is in execution.

In addition the operation inspector unit can monitor the executing process which is being executed in the OS including at least any one of a process activating status a network connecting status and a file input output status.

Accordingly the operation inspector unit can detect that a specific process is being executed such as a critical process is being executed a network connection is made with a specific destination writing is performed in a region of a specific file or storage.

The above mentioned specific process may be given to the operation inspector unit in a form of a process name an address of network connecting destination a file name a path name or the like.

Alternately the above mentioned specific process may be given in a form of being embedded in the operation inspector unit as a program.

In addition the operation inspector unit may output information on the process type in addition to information on whether or not the process specified by the process type is being executed setting of the switch prohibition process flag .

It is to be noted that as one example of the information on the process type a type of activating application a name of file being written and the like can be pointed out.

The switch lock request receiver unit is configured to receive a switch lock request for requesting to prohibit or stop prohibiting the switching of the OS in the active status.

For example the switch lock request receiver unit is configured to receive a switch lock request with any communication means such as calling of a function in accordance with the API message passing or the like.

It is to be noted that the switch lock request receiver unit is configured to receive a switch lock request from an OS a driver an application a middleware or the like.

In addition the switch lock request receiver unit may be configured to receive a switch lock request including a priority.

The lock status manager unit is configured to update a lock request count indicating the number of receiving valid switch lock requests for requesting prohibition of switching the OS in the active status in response to the reception of the switch lock request.

Specifically in a case where a switch lock request for making a request to prohibit the switching of the OS in the active status is received the lock status manager unit performs an operation of increasing the lock request count by one.

In a case where a switch lock request for making a request to stop prohibiting the switching of the OS in the active status is received the lock status manager unit performs an operation of decreasing the lock request count by one.

For example the lock status manager unit may be configured to manage a lock request count for every process type by using the lock status management table shown in .

In the example of as the process type for prohibiting the switching of the active OS the during telephone communication during data communication during writing in a file and during reading a file are pointed out and each of the lock request counts is 1 2 0 and 1 respectively 

Incidentally the lock status manager unit may be configured to manage arrival times of the switch lock request and to reduce the lock request count by invalidating a switch lock request held in the table over a predetermined time after the reception thereof.

The switching permission information manager unit is configured to manage information on whether or not the switch source OS can become an OS in the suspend status whether or not the OS in the active status can be switched for each of the combinations of the event information and the process type by using a switching permission information managing table shown in .

In addition the switching permission information manager unit may be configured to manage whether or not the OS in the active status can be switched and whether or not an inquiry needs to be made to a user about whether or not the OS in the active status can be switched for the combination of the event information and the process type.

In the example of if the telephone communication is being performed when the OS switch request attributable to receiving an incoming telephone call is arrived it is set to prohibit the switching of the OS in the active status.

However it the data communication is being performed when the OS switch request caused by receiving an incoming telephone call is arrived the switching of the OS in the active status is set to be permitted.

On the other hand in the example of if the telephone communication is being performed when the OS switch request due to activating the application is arrived the switching of the OS in the active status is set to be prohibited.

However if the data communication is being performed when the OS switch request due to activating the application is arrived the switching of the OS in the active status is set to be permitted after making an inquiry to a user.

It is to be noted that the switching permission information manager unit may be configured to manage information on whether or not the OS in the active status can be switched and whether an inquiry needs to be made to a user about whether or not the OS in the active status can be switched for the combination of the event information and the process type by using a table associating the event information with a priority as shown in and a table associating a priority with the process type as shown in in place of the switching permission information managing table .

The user inquiring unit is configured to make an inquiry to a user about whether or not the OS in the active status can be switched by presenting to the user the event information and the process type which requests for prohibiting the switching the OS in the active status.

The switch judgment unit is configured to determine whether or not the switch source OS can become an OS in the suspend status whether or not the OS in the active status can be switched .

Specifically the switch judgment unit determines whether or not the switch source OS can become an OS in the suspend status whether or not the OS in the active status can be switched and sets OS switch prohibition data including the OS switch prohibition flag according to the determined result.

In addition the switch judgment unit determines whether or not the switch source OS can become an OS in the suspend status whether or not the OS in the active status can be switched in accordance with the lock request count on the lock status management table managed by the lock status manager unit .

For example the switch judgment unit may be configured to set the OS switch prohibition flag only in a case where the lock request count is one or more when the lock request count on the lock status management table managed by the lock status manager unit is referred.

In addition the switch judgment unit may determine whether or not the switch source OS can become an OS in the suspend status whether or not the OS in the active status can be switched in response to the notification from the activity notifying unit .

In addition the switch judgment unit may determine whether or not the switch source OS can become an OS in the suspend status whether or not the OS in the active status can be switched in accordance with the executing process which is being executed in the monitored OS.

In addition the switch judgment unit may determine whether or not the switch source OS can become an OS in the suspend status whether or not the OS in the active status can be switched in accordance with the combination of the process type which specifies the executing process determined as being executed and the notified event information by referring to the switching permission information manager unit .

For example the switch judgment unit may set the OS switch prohibition flag only in a case where one or more prohibitions of switching the OS in the active status are set for the combination of the event information and the process type which are included in the OS switch request by referring to the switching permission information manager unit .

The switch judgment unit determines whether or not the switch source OS can become an OS in the suspend status whether or not the OS in the active status can be switched in response to the result of making an inquiry to a user.

For example the switch judgment unit may set a user inquiring flag if an inquiry to a user is set to be necessary when referring to the switching permission information manager unit .

In addition the switch judgment unit may be configured to determine whether or not the switch source OS can become an OS in the suspend status in accordance with the priority of the received switch lock request and the priority of the received OS switch request.

For example the switch judgment unit determines that the switch source OS can become an OS in the suspend status if the priority of the received switch lock request is higher than the priority of the OS switch request.

By referring to the operation of the computer system according this embodiment will be described below.

First by referring to an OS switching procedure a procedure of switching an OS in the active status from OS to OS in the computer system according to this embodiment will be described.

As shown in at step S the OS switch request receiver unit of the OS switching control device A receives an OS switch request including event information indicating a cause of switching the OS in the active status from an event source such as an application middleware or a driver.

At step S the switch event notifying unit of the OS switching control device A notifies the event information included in the OS switch request to the OS being the switch source OS.

At step S the OS switch judgment unit of the OS switching control device A determines whether or not the switch source OS can become an OS in the suspend status whether or not the OS in the active status can be switched and then sets OS switch prohibition data.

The determination whether or not the above mentioned switch source OS can become an OS in the suspend status whether or not the OS in the active status can be switched will be described later by referring to .

At step S the switch prohibition data notifying unit of the OS switching control device A notifies the OS switch prohibition data to the OS switching function .

At step S the OS switch controller unit of the OS switching control device A terminates the present procedure without switching the OS in the active status if the OS switch prohibition flag is set in the OS switch prohibition data.

On the other hand at step SA the OS switch controller unit of the OS switching control device A selects and executes the switch process of the switch source OS in accordance with the event information if the OS switch prohibition flag is not set in the OS switch prohibition data at step S.

Thereafter at step SB the switch controller unit of the OS switching control device A deletes all of the OS switch requests held by the OS switch request receiver unit .

Then at step S the switch controller unit calls the OS switching function by using the event information as an argument.

At step S the OS being currently in the active OS becomes an OS in the suspend status and control is shifted to the OS being the switch destination OS.

When the OS is resumed at step S at step S the switch event acquiring unit of the OS switching control device B for the OS acquires the event information notified by the OS being the switch source OS.

At step SA the event processor unit of the OS switching control device B executes the switch process of the switch destination OS selected in accordance with the acquired event information.

At step SB the event processor unit executes the event process corresponding to the acquired event information by utilizing the table shown in .

As described above the active OS OS accepts an incoming telephone call or a incoming mail which is addressed to the inactive OS OS and then passes the incoming telephone call or the incoming mail to the inactive OS OS .

Then the inactive OS OS is switched to the active OS and thus the telephone communication or data communications can be carried out on the OS that is the switch destination OS.

Secondly by referring to description will be given of a procedure of determining whether or not an OS can be switched when the OS in the active status is switched from the OS to the OS in the computer system according to the present embodiment.

As shown in at step S the switch judgment unit of the OS switching control device A refers to the lock request count by referring to the lock status manager unit .

At step S if the lock request count is not 0 the present operation proceeds to step S and if the lock request count is 0 the present operation proceeds to step S.

At step S the operation inspector unit of the OS switching control device A refers to the operating status management table shown in .

At step S the operation inspector unit monitors whether or not the process of prohibiting the switching of the OS in the active status the process specified by the process type is being executed.

At step S when it is determined that the above mentioned process is being executed the present operation proceeds to step S and when it is determined that the above mentioned process is not being executed the present operation proceeds to step S.

At step the switch prohibition data notifying unit of the OS switching control device A sets an OS switch prohibition flag in the OS switch prohibition data.

On the other hand at step S the switch prohibition data notifying unit of the OS switching control device A resets the OS switch prohibition flag in the OS switch prohibition data.

Thirdly by referring to another procedure of determining whether or not an OS can be switched when the OS in the active status is switched from the OS to the OS in the computer system according to this embodiment will be described.

As shown in at step S the switch judgment unit of the OS switching control device A refers to the lock request count by referring to the lock status management table see FIG. in the lock status manager unit .

At step S the switch judgment unit of the OS switching control device A extracts the process type with the lock request count being 1 or more.

At step S the operation inspector unit of the OS switching control device A extracts the executing process which is being executed by referring to the operating status management table shown in .

At step S the switch judgment unit of the OS switching control device A refers to the switching permission information managing table shown in .

At step S the switch judgment unit scans all of the combinations of the event information included in the notified OS switch request and the process type specifying the extracted executing process and then determines whether or not the switch source OS can become the OS in the suspend status whether or not the prohibition of the switching the OS in the active status is designated .

If one or more prohibitions of the switching the OS in the active status are designated at step S the switch prohibition data notifying unit of the OS switching control device A sets at step S an OS switch prohibition flag in the OS switch prohibition data.

On the other hand if one or more prohibitions of switching the OS in the active status are not designated at step S the switch prohibition data notifying unit of the OS switching control device A resets at step S the OS switch prohibition flag in the OS switch prohibition data.

At step S if it is set in the switching permission information table that an inquiry needs to be made to a user about whether or not the switch source OS can become the OS in the suspend status at step S the switch judgment unit of the OS switching control device A sets a user inquiring flag at step S.

On the other hand if it is not set in the switching permission information table that an inquiry needs to be made to a user about whether or not the switch source OS can become the OS in the suspend status at step S at step S the switch judgment unit of the OS switching control device A resets the user inquiring flag.

Fourthly by referring to description will be given of a procedure of receiving a switch lock request in the computer system according to the first embodiment of the present invention.

As shown in at step S the switch lock request receiver unit of the OS switching control device A receives the above mentioned switch lock request.

At step S if the received switch lock request requests the prohibition of the switching the OS in the active status the lock status manager unit of the OS switching control device A increases at step S the lock request count corresponding to the process type designated by the switch lock request by 1 .

On the other hand at step S if the received switch lock request requests to stop prohibiting the switching of the OS in the active status the lock status manager unit of the OS switching control device A decreases at step S the lock request count corresponding to the process type designated by the switch lock request by 1 .

Fifthly by referring to description will be given of an operation of receiving an incoming telephone call will be described as one example of a switch event which occurs in the computer system according to the first embodiment of the present invention.

As shown in when an incoming telephone call signal is received for the OS in the active status at step S the OS performs an interrupting process at step S and then activates a telephone driver at step S.

At step S the telephone driver of the OS determines a destination of an incoming telephone call signal in accordance with a call destination number and a call source number included in the incoming telephone call signal.

At step S if the destination of the above mentioned incoming telephone call signal is the OS the present operation proceeds to step S If the destination of the above mentioned incoming telephone call signal is the OS the present operation proceeds to step S.

At step S the telephone driver of the OS requests an application manager unit not shown to activate start a telephone application.

At step S the telephone application displays a name of a caller a calling source and reproduces a ring tone.

If a user responds to the above mentioned incoming telephone call signal at step S the telephone application starts telephone communication process at step S and when the telephone communication is finished at step S the telephone application stops.

On the other hand at step S the OS switch request receiver unit of the OS switching control device A for the OS receives an OS switch request from the telephone driver.

At step S the switch event notifying unit of the OS switching control device A for the OS notifies the OS of the switch event indicating that an incoming telephone call is received by using a function OS Switch Event event cmd in accordance with the API.

At step S the switch controller unit of the OS switching control device A for the OS selects and executes the switch process of the switch source OS in accordance with the received event information designates the above mentioned argument PHONE RETURN and calls the OS switching function .

At step S the OS is resumed and at step S the OS activates the event processor unit of the OS switching control device B for the OS.

At step S the event processor unit of the OS switching control device B selects and executes the switch process of the switch destination OS in accordance with the received event information and executes the event process by using the above mentioned argument PHONE RETURN .

At step S the telephone driver of the OS is activated by the event processor unit of the OS switching control device B.

At step S the telephone driver of the OS requests an application manager unit not shown to activate a telephone application.

At step S the telephone application displays a name of a caller a calling source and reproduces a ring tone.

If the user responds to the above mentioned incoming telephone call signal at step S the telephone application starts telephone communication process at step S.

At step S when the telephone communication is finished the telephone application notifies the application manager unit of the telephone communication being finished and then stops the process.

At step S the application manager unit notifies the event processor unit of the OS switching control device B of the fact that the telephone communication process by the telephone application is finished.

At step S the event processor unit of the OS switching control device B determines to return the OS in the active status from the OS to the OS based on the above mentioned argument RETURN and at step S the OS in the active status is switched from the OS to OS.

Sixthly by referring to description will be given of an operation when an incoming message a device management DM message of an SMS Short Message Service for DM is received as one example when a switch event occurs in the computer system according to the first embodiment of the present invention.

As shown in when the incoming DM message is received for the OS in the active status at step S at step S the OS performs an interruption process and at step S it starts a network NW driver.

At step S the NW driver of the OS determines a destination of the above mentioned incoming DM message in accordance with an address included in the incoming DM message.

It the destination of the above mentioned incoming DM message is the OS the present operation proceeds to step S.

If the destination of the above mentioned incoming DM message is the OS the present operation proceeds to the step S.

At step S the NW driver of the OS requests an application manager unit not shown to activate a DM agent.

On the other hand the OS switch request receiver unit of the OS switching control device A for the OS receives an OS switch request from the NW driver.

At step S the switch event notifying unit of the OS switching control device A for the OS notifies the OS of the switch event indicating that the incoming DM message is received by using a function OS Switch Event event cmd in accordance with the API.

At step S the switch controller unit of the OS switching control device A for the OS selects and executes the switch process of the switch source OS in accordance with the received event information designates the above mentioned argument DM RETURN and calls the OS switching function .

At step S the OS is resumed and at step S the OS activates the event processor unit of the OS switching control device B for the OS.

At step S the event processor unit of the OS switching control device B selects and executes the switch process of the switch destination OS in accordance with the received event information and executes the event process by using the above mentioned argument DM RETURN .

Then at step S an NW driver of the OS is activated by the event processor unit of the OS switching control device B.

At step S the NW driver of the OS requests an application manager unit not shown to activate a DM agent.

At step S the DM agent executes a predetermined process and when the execution of the predetermined process is finished at step S the DM agent notifies the application manager unit of the process being finished and then stops the process.

At step S the application manager unit notifies the event processor unit of the OS switching control device B of the fact that the predetermined process by the DM agent is finished.

At step S the event processor unit of the OS switching control device B determines the fact that the OS in the active status is returned from the OS to the OS in accordance with the above mentioned argument RETURN and at step S the OS in the active status is switched from the OS to the OS.

Since the computer system according to this embodiment is configured so that the switch source OS in the active status notifies the switch destination OS of event information indicating a switch event it is possible to perform an appropriate process in accordance with the above mentioned event after the OS becomes in the active status.

In addition since the computer system according to this embodiment is configured to execute the switch process of the switch source OS and the switch destination OS which are selected corresponding to the event information at the time of switching the OSs it is possible to reduce a time required for switching the OS by changing the switch process very flexibly corresponding to the switch event.

In addition since the computer system according to this embodiment is configured to pass the event information to the OS switching function it is possible to reduce a time required for switching the OS by causing the OS switching function to optimize the switch process of the OS.

The computer system according to this embodiment does not execute the switching of the OS in the active status if the switch controller unit determines that the OS in the active status cannot be switched so that a failure resulting from the switching of the switch source OS to be in the suspend status can be prevented.

According to the computer system of this embodiment the OS switching function can determine whether or not the switching of the OS in the active status is executed by using the OS switch prohibition data notified by the switch prohibition data notifying unit .

In other words the OS switching function can determine whether or not the switching of the OS in the active status is executed by using the detailed information given by the OS switching control device A since the OS switching function itself does not know about the process being executed in the OS.

According to the computer system of this embodiment the OS switching function can detect a failure of the OS switching control device A.

Accordingly the OS switching function can determine whether or not the switching of the OS in the active status can be performed after considering the failure of the OS switching control device A even if the OS switching control device A makes a notification of the prohibition of the switching the OS in the active status and thereafter the prohibition of the switching the OS in the active status becomes disable to be unlocked due to the failure of the OS switching control device A.

The computer system according to this embodiment prohibit the switching of the OS in the active status while an application or a function which could cause a failure due to the switching of the OS in the active status so that a failure or an abnormal operation can be prevented.

The computer system according to this embodiment can monitor the execution in of a specific process such as a critical process a network connection with a specific destination or a writing process to a specific file or storage region.

The computer system according to this embodiment can lock the switching of the OS in the active status in accordance with a request from an OS a driver an application middleware or the like.

Accordingly the failure due to the switching of the OS in the active status can be prevented and thereby improving stability.

The computer system according to this embodiment can precisely determine whether or not the OS in the active status can be switched by considering the combination of the executing process being executed on the switch source OS and the event information included in the OS switch request.

The computer system according to this embodiment can control permission or prohibition of the switching the OS in the active status after making an inquiry to a user so that it is possible to control the switching of the OS in the active status with the user s intention reflected.

According to the computer system of this embodiment even if a driver middleware or the like of the requesting source which requests to lock the switching of the OS in the active status does not properly request to unlock the lock due to the failure the above mentioned lock can be unlocked after a predetermined period of time passes.

According to the computer system of this embodiment the first OS in the suspend status can process the above mentioned event by driving the switching of the OS in the active status when an interesting event happens even if the second OS is the OS in the active status.

By referring to a computer system according to a second embodiment of this embodiment will be described.

The computer system according to this embodiment is configured to mount a plurality of virtual OS and OS which exclusively become in the active status and to switch an OS in the active status an active OS by an OS switching function for switching among the plurality of virtual OSs.

In this embodiment it is assumed that a single OS with a plurality of setting modes provides a plurality of virtual OSs and the OS and OS are to be executed as a same OS program.

When the OS is switched by the OS switching function a status of an OS or an application when the switch source OS is in the active status is suspended saved and a status of an OS or an application saved when the switch destination OS is in the active status is resumed restarted .

In the example shown in the execution environment independent from a normal OS can be provided on the computer system which supports the TrustZone and the OS switching function can be arranged in the execution environment.

In the example shown in the OS switching function may be implemented in any form of a device driver a server an application and the like.

The configuration motion operation and effect of the above mentioned OS switching control device A are same as those of the above mentioned first embodiment and therefore the description thereof will be omitted.

According to the present invention it is possible to provide a OS switching control device and a computer system which are capable of executing the switch processes of the switch source OS and the switch destination OS which are selected in accordance with to event information while reducing a time required for switching from a switch source OS to a switch destination OS and a time required for performing a process for a switch event addressed to is an inactive OS. In order to reduce these times the operating system switching control device and the computer system are capable of changing the switch process very flexibly in response to an occurring switch event by allowing the switch processes corresponding to the event information to be optimized.

According to the present invention it is possible to provide an operating system switching control device and a computer system which are capable of executing safely the switching of an OS in the active status by checking whether or not a process to prohibit the switching of the OS in the active status is being executed.

Additional advantages and modifications will readily occur to those skilled in the art. Therefore the invention in its broader aspects is not limited to the specific details and the representative embodiments shown and described herein. Accordingly various modifications may be made without departing from the scope of the general inventive concept as defined by the appended claims and their equivalents.

