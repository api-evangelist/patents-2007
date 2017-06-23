---

title: Interruptible thread synchronization method and apparatus
abstract: An interruptible thread synchronization method and apparatus are provided. The interruptible thread synchronization method includes controlling mutually exclusive access to an object by one or more threads using a monitor, and interrupting a first thread that is on standby for the monitor. The interruptible thread synchronization method and apparatus allows for access and control of an object by one or more threads.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08286166&OS=08286166&RS=08286166
owner: Samsung Electronics Co., Ltd.
number: 08286166
owner_city: Suwon-si
owner_country: KR
publication_date: 20070122
---
This application claims priority from Korean Patent Application No. 10 2006 0018411 filed on Feb. 24 2006 in the Korean Intellectual Property Office the disclosure of which is incorporated herein by reference in its entirety.

Methods and apparatuses consistent with the present invention relate to synchronization of threads and more particularly to an interruptible thread synchronization.

Most thread programs enable a plurality of threads to share data. Even when a thread modifies an invariable value of data that is shared with other threads another thread may use the data. In order to prevent this problem a program technique called synchronization is needed. Synchronization is a technique of synchronizing a plurality of threads so that all attempts that are made to access to the same data present in a memory can be mutually exclusive. That is synchronization enables only one thread to use data while making other threads wait for their turn to use the data.

However in conventional synchronization techniques even when there is the need to immediately return system resources occupied by a thread the thread may not be stopped if the thread is on standby to be synchronized for acquiring a monitor.

Therefore it is necessary to develop techniques of choosing a predetermined thread that is needed from a plurality of threads that are on standby to be synchronized and interrupting the chosen thread from a monitor while not affecting threads that are on standby for a monitor as well as threads that have already acquired the monitor and are currently performing a critical section and particularly techniques that do not require modification of a thread library and comply with existing standards e.g. the Portable Operating System Interface POSIX standard.

In the meantime Korean Patent Laid Open Gazette No. 10 2004 0068993 entitled Method and Apparatus for Stopping Execution of Thread Until Predetermined Memory Access Is Made discloses a technique of temporarily stopping the execution of a thread with the aid of a multi threading processor. However this technique can stop the execution of a thread only temporarily and thus there is a clear limit in completely releasing from a monitor a thread that is on standby for the monitor.

The present invention provides an interruptible thread synchronization method and apparatus which can interrupt a thread that is on standby for a monitor that provides mutually exclusive synchronization for a predetermined object.

However the aspects of the present invention are not restricted to the one set forth herein. The above and other aspects of the present invention will become more apparent to one of daily skill in the art to which the present invention pertains by referencing a detailed description of the present invention given below.

According to an aspect of the present invention there is provided an interruptible thread synchronization method including controlling mutually exclusive access to an object by one or more threads using a monitor and interrupting a first thread that is on standby for the monitor.

The present invention will now be described more fully with reference to the accompanying drawings in which exemplary embodiments of the invention are shown. The invention may however be embodied in many different forms and should not be construed as being limited to the exemplary embodiments set forth herein rather these exemplary embodiments are provided so that this disclosure will be thorough and complete and will fully convey the concept of the invention to those skilled in the art. Like reference numerals in the drawings denote like elements and thus their description will be omitted.

Terms used in this disclosure have been defined in consideration of their functions in this disclosure and may have different meanings depending on a user s intent or understanding. Therefore the terms are defined based on the invention claimed in this disclosure.

An object is an entity that is accessed by threads for the purpose of performing certain functions and may be realized in various forms namely as data items resources and code segments.

Synchronization is a state where threads can access a predetermined object in a mutually exclusive manner. In other words in a case where there are a plurality of threads that attempt to access a predetermined object synchronization allows only one of the threads to access the predetermined object at a time.

A monitor controls attempts to mutually exclusively access a predetermined object. In other words a monitor synchronizes a plurality of threads with a single object thereby preventing all the threads from attempting to access the object at the same time. In this manner only a thread that has acquired a monitor is allowed to access an object. In other words in order to access a synchronized object a thread must acquire a monitor corresponding to the synchronized object. In some standards that prescribe the definition of threads monitor acquirement is referred to as monitor lock. In this disclosure it is assumed that the terms monitor acquirement and monitor lock bear the same meaning. Examples of a monitor include a mutex or a semaphore of the Portable Operating System Interface POSIX . The present invention provides new types of monitors and they will be described later in detail with reference to .

Interrupt is a process of stopping the execution of a thread and performing other functions. According to the present invention interrupt can be interpreted as a state where a thread that is on standby for a monitor fails to acquire the monitor is completely released from the monitor and thus does not request the monitor any longer.

A condition variable indicates a standby condition of a thread and places a thread on standby until a predetermined condition becomes true. A thread is put on standby according to a condition variable by signal standby information. An example of the signal standby information is a function pthread cond wait of a POSIX application programming interface API . A thread that is on standby according to a condition variable may be woken up by predetermined signal generation information. According to the present invention signal generation information may be classified into signal generation information regarding a single signal and signal generation information regarding a broadcast signal.

In an exemplary embodiment a condition variable operates together with a mutex in order to put threads on standby. For example if a first thread is blocked by a condition variable that waits for the generation of a predetermined condition after locking a mutex then the mutex may be unlocked as long as the first thread is blocked. If a second thread modifies a state of the predetermined condition and wakes up the first thread then the first thread locks the mutex again and examines the predetermined condition. If the predetermined condition is false then the first thread may be blocked again by the condition variable. However if the predetermined condition is true then the first thread unlocks the mutex and performs a necessary operation. According to an exemplary embodiment illustrated in a condition variable can perform the aforementioned processes together with a sub monitor .

A single signal is information that is used to wake up only one of a plurality of threads that are put on standby by a condition variable. According to an exemplary embodiment of the present invention a thread that is woken up by a single signal may be able to acquire a monitor. An example of a single signal is a function pthread cond signal of a POSIX API.

A broadcast signal is information that is used to wake up more than one thread that is put on standby by a condition variable. A plurality of threads are sequentially woken up by a broadcast signal. According to an exemplary embodiment of the present invention a thread that satisfies a predetermined condition may be interrupted by a broadcast signal. An example of a broadcast signal is a function pthread cond broadcast of a POSIX API.

The present invention will hereinafter be described in detail with reference to the accompanying drawings in which exemplary embodiments of the invention are shown.

The sub monitor synchronizes a plurality of threads with information that is present in the monitor . In detail the sub monitor synchronizes a plurality of threads for the condition variable and the counter variable . An example of the sub monitor is a mutex.

The condition variable provides synchronization of a predetermined object using signal generation information and signal standby information. According to the present exemplary embodiment when the monitor that has been locked by a first thread is requested by a second thread the condition variable puts the second thread on standby.

A thread that is on standby can acquire the monitor after being woken up by a single signal. If more than one thread is on standby then only one of the standby threads may be woken up by a single signal. Threads that are on standby may be woken up by a broadcast signal. In this case threads that satisfy a predetermined condition are completely released from a standby state by the broadcast signal while threads that do not satisfy the predetermined condition are placed back on standby.

The counter variable indicates the number of threads that have acquired the monitor and the number of threads that are on standby for the monitor . The counter variable may have a nonnegative integer value. Whenever a thread requests the monitor the value of the counter variable increases. On the other hand whenever a thread that has acquired the monitor releases the monitor or whenever a thread that is on standby for the monitor is interrupted from the monitor the value of the counter variable decreases.

The counter variable may have a nonnegative integer value. The value of the counter variable increases or decreases by 1 at a time. In this case if the counter variable is set to a value of 1 then it appears that the only thread has acquired the monitor is on standby. If the counter variable is set to a value of 0 then it appears that even the thread that has acquired the monitor does not exist. If the counter variable is set to an integer value N that is greater than 1 then the number of threads that are on standby for the monitor is N 1 assuming that the counter variable has a nonnegative integer value and increases or decreases by 1 at a time. However the present invention is not restricted to this.

The broadcast flag has a true value when a broadcast signal is output in order to wake up threads that are on standby for the condition variable . A thread to be interrupted may learn from the broadcast flag that the thread to be interrupted must be interrupted from the monitor .

The blocked monitor information includes information regarding a monitor for which the thread has been on standby.

The interrupt flag includes information indicating whether the thread is to be interrupted. For example if the thread is to be interrupted then the interrupt flag may be set to a true value. A thread whose interrupt flag is set to a true value may be completely released from a standby state i.e. may be interrupted from a monitor for which the thread has been on standby when being woken up by a broadcast signal.

An interruptible thread synchronization method according to an exemplary embodiment of the present invention will hereinafter be described in detail.

In operation S if it is determined in operation S that the monitor is not being used by any thread then the request thread acquires the monitor .

On the other hand in operation S if it is determined in operation S that the monitor is currently being used by a thread other than the request thread then the request thread sets information regarding the monitor in blocked monitor information of the request thread. In operation S the request thread is placed on standby by the condition variable of the monitor .

In operation S it is determined whether a single signal has been output by the condition variable . In operation S if it is determined that a single signal has been output by the condition variable then the request thread wakes up from standby and acquires the monitor . If more than one thread is on standby for the monitor then one of the standby threads may wake up when a single signal is output.

In operation S if it is determined that a single signal has not yet been output by the condition variable then it is determined whether a broadcast signal has been output. If it is determined in operation S that a broadcast signal has been output then an interrupt process may be performed for the request thread and this will be described in detail with reference to .

If neither a single signal nor a broadcast signal is output then the request thread keeps waiting for the monitor .

In detail since the monitor is yet to be released the counter variable must be set to a value greater than 0. If the counter variable is set to a value of 1 then it may be determined that no thread is currently on standby for the monitor . On the other hand if the counter variable is set to a value greater than 1 then it may be determined that a thread that is on standby for the monitor exists.

In operation S if no thread is on standby for the monitor then the release thread releases the monitor by reducing the value of the counter variable of the monitor by 1 so that the value of the counter variable is changed from 1 to 0.

In operation S if it is determined in operation S that a thread that is on standby for the monitor exists then the release thread outputs a single signal for the condition variable . In operation S the release thread releases the monitor by reducing the value of the counter variable by 1 so that the value of the counter variable is changed from N where N is an integer value greater than 1 to N 1.

In operation S if it is determined in operation S that the target thread is on standby for the predetermined monitor then the interrupt instruction thread records predetermined information in the target thread to indicate that the target thread is to be interrupted. The predetermined information may be set as an interrupt flag of the target thread.

Thereafter in operation S the interrupt instruction thread outputs a broadcast signal for a condition variable of the predetermined monitor. In this case a plurality of threads that are on standby for the condition variable of the predetermined monitor are sequentially woken up in response to the broadcast signal.

In operation S if it is determined in operation S that the thread is a thread to be interrupted then the thread deletes information regarding a monitor for which the thread has been on standby. The information regarding the monitor is set in blocked monitor information of each thread that has been on standby for the monitor.

In operation S the thread is interrupted from the monitor by reducing the value of the counter variable of the monitor so that the value of the counter variable is changed from L where L is an integer value greater than 1 to L 1. Then the interrupted thread may be driven to perform another operation or may be terminated.

If it is determined in operation S that the thread is not a thread to be interrupted then the thread may be placed back on standby in operation S illustrated in .

The interruptible thread synchronization method according to the present exemplary embodiment may also include controlling synchronization regarding internal information of the monitor with the aid of the sub monitor of the monitor when a thread attempts to access the internal information of the monitor . For example threads can be prevented from accessing the internal information of the monitor by locking the sub monitor before operation S. Thereafter threads are allowed to access the internal information of the monitor by unlocking the sub monitor after operation S.

The present invention can be realized by recording a computer program that comprises computer code for executing the interruptible thread synchronization method described above with reference to in a recording medium such as a flash memory a compact disc CD or a hard disc and executing the computer program from the recording medium.

The main memory module provides memory space that is needed for the execution of a program by the processing module . According to the present exemplary embodiment the main memory module may be realized as a random access memory RAM such as a dynamic RAM DRAM a static RAM SRAM or a synchronous DRAM SDRAM .

The input output module provides the processing module with data that is needed for the execution of the program and receives the result of execution of the program by the processing module . For example if a user inputs a request regarding the program which is currently being executed with the aid of an input device such as a remote control a keyboard a keypad or a mouse then the input output module may transmit the request to the processing module . Alternatively the input output module may output the result of the execution of the program by the processing module to a display device or a speaker.

The processing module executes the program . For this the processing module may execute the program by performing a read operation a write operation a conversion operation or a computation operation. The processing module executes the program thereby realizing for example the monitor illustrated in and the thread illustrated in and performing the processes described above with reference to .

The program may be comprised of computer code that generates the monitor and the thread when being processed by the processing module .

The term module as used herein means but is not limited to a software or hardware component such as a Field Programmable Gate Array FPGA or Application Specific Integrated Circuit ASIC which performs certain tasks. A module may advantageously be configured to reside on the addressable storage medium and configured to execute on one or more processors. Thus a module may include by way of example components such as software components object oriented software components class components and task components processes functions attributes procedures subroutines segments of program code drivers firmware microcode circuitry data databases data structures tables arrays and variables. The functionality provided for in the components and modules may be combined into fewer components and modules or further separated into additional components and modules.

As described above according to the present invention it is possible to interrupt a predetermined thread from a monitor that provides mutually exclusive synchronization for a predetermined object.

While the present invention has been particularly shown and described with reference to exemplary embodiments thereof it will be understood by those of ordinary skill in the art that various changes in form and details may be made therein without departing from the spirit and scope of the present invention as defined by the following claims.

