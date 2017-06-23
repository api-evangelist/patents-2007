---

title: Performing application setting activity using a removable storage device
abstract: A method of configuring a processing system to perform application setting activity using a removable storage device in data communication with the processing system includes a) selecting an application, where setting activity associated with the selected application is to be performed using the removable storage device, b) installing, in the processing system, an interception module to intercept application setting activity associated with the selected application; and c) in response to the interception module intercepting application setting activity associated with the selected application, performing the application setting activity using the removable storage device, thereby storing application setting data associated with the selected application in the removable storage device.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08001367&OS=08001367&RS=08001367
owner: Symantec Corporation
number: 08001367
owner_city: Mountain View
owner_country: US
publication_date: 20071009
---
This application claims the benefit of priority from U.S. Provisional Patent Application No. 60 850 771 filed Oct. 10 2006 and is incorporated by referenced.

The present invention generally relates to a method system computer readable medium of instructions and or computer program product for performing application setting activity associated with an application using a removable storage device.

A portion of the disclosure of this patent document contains material that is subject to copyright protection. The copyright owner has no objection to the facsimile reproduction by anyone of the patent disclosure as it appears in a Patent Office patent files or records but otherwise reserves all copyrights whatsoever.

Software applications are generally configured to store application settings in non removable memory of a processing system. For example it is common for software to be configured to store settings in either the system registry of the processing system or data files which are stored in the hard drive of the processing system.

However in the event that the processing system crashes application setting data is irretrievable causing the user to reset the application settings which can be a time consuming task.

A user may manually attempt to copy application setting data in a removable storage device in order to make a back up copy of the settings data. However the user generally requires an extremely detailed knowledge of internal functionality of the software to copy the appropriate application settings successfully.

Some solutions have proposed copying all settings associated with the user environment in a processing system. However when all the settings are restored one or more applications can malfunction. For example system variables copied from one processing system can likely lead to malfunctioning software due to applications being installed in different locations in processing systems.

Therefore there exists a need for a method system computer readable medium of instructions and or a computer program product which copies application setting data for a selected one or more applications without the user requiring a detailed knowledge of the internal functionality of the selected one or more applications.

The reference in this specification to any prior publication or information derived from it or to any matter which is known is not and should not be taken as an acknowledgment or admission or any form of suggestion that that prior publication or information derived from it or known matter forms part of the common general knowledge in the field of endeavour to which this specification relates.

In one broad form there is provided a method of configuring a processing system to perform application setting activity using a removable storage device in data communication with the processing system wherein the method comprises 

selecting an application wherein setting activity associated with the selected application is to be performed using the removable storage device 

installing in the processing system an interception module to intercept application setting activity associated with the selected application and

in response to the interception module intercepting application setting activity associated with the selected application performing the application setting activity using the removable storage device thereby storing application setting data associated with the selected application in the removable storage device.

In one form the method comprises performing the application setting activity using the removable storage device and a non removable storage device of the processing system.

In another form when the application setting activity is intercepted the method comprises the removable storage device copying application setting data stored to the non removable data storage device for the selected application.

In one embodiment the method comprises launching a selection module to select the application wherein the selection module is launched from one of 

installing in the processing system a plurality of interception modules to intercept application setting activity associated with the plurality of applications selected and

in response to each interception module intercepting respective application setting activity associated with the respective application performing the respective application setting activity using the removable storage device thereby storing respective application setting data associated with the respective selected application in the removable storage device.

In an optional form the interception module comprises one or more hook functions wherein the method comprises intercepting using the one or more hook functions of the interception module the application setting activity associated with the application.

In another optional form the method comprises installing the interception module followed by launching and installing the application in the processing system.

Optionally the removable storage device comprises a database wherein the method comprises in response to intercepting application setting activity using the database to emulate a system registry.

Also optionally the method comprises storing interception data in the removable storage device wherein the interception data is indicative of 

In one form in response to intercepting application setting activity the method comprises querying the interception data to determine if application setting data associated with the application setting activity is stored on the removable storage device wherein in response to a positive query the application setting data is used to perform the application setting activity.

coupling the removable setting data with a second processing system wherein the second processing system comprises the selected application wherein use of the selected application results in application setting activity being intercepted such that application setting data stored on the removable storage device is used.

installing in at least one of the removable storage device and the processing system one or more rules and

upon intercepting application setting activity applying at least some of the one or more rules to determine if the application setting activity is to be performed using one of the processing system and the removable storage device.

In another broad form there is provided a system to configure a processing system to perform application setting activity using a removable storage device in data communication with the processing system wherein the system is configured to 

select an application wherein setting activity associated with the selected application is to be performed using the removable storage device 

install in the processing system an interception module to intercept application setting activity associated with the selected application and

in response to the interception module intercepting application setting activity associated with the selected application perform the application setting activity using the removable storage device thereby storing application setting data associated with the selected application in the removable storage device.

In one form the system is configured to perform the application setting activity using the removable storage device and a non removable storage device of the processing system.

In another form the system is configured to launch a selection module to select the application wherein the selection module is launched from one of 

install in the processing system a plurality of interception modules to intercept application setting activity associated with the plurality of applications selected and

in response to each interception module intercepting respective application setting activity associated with the respective application perform the respective application setting activity using the removable storage device thereby storing respective application setting data associated with the respective selected application in the removable storage device.

In another embodiment the interception module comprises one or more hook functions configured to intercept the application setting activity associated with the application.

In an optional form the removable storage device comprises a database configured to emulate a system registry.

In another optional form the system is configured to store interception data in the removable storage device wherein the interception data is indicative of 

In one aspect in response to intercepting application setting activity the system is configured to query the interception data to determine if application setting data associated with the application setting activity is stored on the removable storage device wherein in response to a positive query the application setting data is used to perform the application setting activity.

In another broad form there is provided a computer program product for performing application setting activity using a removable storage device in data communication with a processing system wherein the computer program product comprises a computer readable medium having a computer program recorded therein or thereon wherein the computer program product configures the processing system to 

select an application wherein setting activity associated with the selected application is to be performed using the removable storage device 

install in the processing system an interception module to intercept application setting activity associated with the selected application and

in response to the interception module intercepting application setting activity associated with the selected application perform the application setting activity using the removable storage device thereby storing application setting data associated with the selected application in the removable storage device.

According to another broad form the present invention provides a computer readable medium of instructions for giving effect to any of the aforementioned methods or systems.

The following modes given by way of example only are described in order to provide a more precise understanding of the subject matter of a preferred embodiment or embodiments.

In the figures incorporated to illustrate features of an example embodiment like reference numerals are used to identify like parts throughout the figures.

A particular embodiment of the present invention can be realised using a processing system an example of which is shown in .

In particular the processing system generally comprises at least one processor or processing unit or plurality of processors memory at least one input device and at least one output device coupled together via a bus or group of buses . In certain embodiments input device and output device could be the same device. An interface can also be provided for coupling the processing system to one or more peripheral devices for example interface could be a PCI card or PC card. At least one storage device which houses at least one database can also be provided. The memory can be any form of memory device for example volatile or non volatile memory solid state storage devices magnetic devices etc. The processor could comprise more than one distinct processing device for example to handle different functions within the processing system . Input device receives input data and can comprise for example a keyboard a pointer device such as a pen like device or a mouse audio receiving device for voice controlled activation such as a microphone data receiver or antenna such as a modem or wireless data adaptor data acquisition card etc. Input data could come from different sources for example keyboard instructions in conjunction with data received via a network. Output device produces or generates output data and can comprise for example a display device or monitor in which case output data is visual a printer in which case output data is printed a port for example a USB port a peripheral component adaptor a data transmitter or antenna such as a modem or wireless network adaptor etc. Output data could be distinct and derived from different output devices for example a visual display on a monitor in conjunction with data transmitted to a network. A user could view data output or an interpretation of the data output on for example a monitor or using a printer. The storage device can be any form of data or information storage means for example volatile or non volatile memory solid state storage devices magnetic devices etc.

In use the processing system can be adapted to allow data or information to be stored in and or retrieved from via wired or wireless communication means the at least one database . The interface may allow wired and or wireless communication between the processing unit and peripheral components that may serve a specialised purpose. The processor receives instructions as input data via input device and can display processed results or other output to a user by utilising output device . More than one input device and or output device can be provided. It should be appreciated that the processing system may be any form of terminal server processing system specialised hardware or the like.

A hook also known as a hook procedure or hook function as used herein generally refers to a callback function provided by a software application that receives certain data before the normal or intended recipient of the data. A hook function can thus examine or modify certain data before passing on the data. Therefore a hook function allows a software application to examine data before the data is passed to the intended recipient.

An API Application Programming Interface hook also known as an API interception as used herein as a type of hook refers to a callback function provided by an application that replaces functionality provided by an operating system s API. An API generally refers to an interface that is defined in terms of a set of functions and procedures and enables a program to gain access to facilities within an application. An API hook can be inserted between an API call and an API procedure to examine or modify function parameters before passing parameters on to an actual or intended function. An API hook may also choose not to pass on certain types of requests to an actual or intended function.

A hook chain as used herein is a list of pointers to special application defined callback functions called hook procedures. When a message occurs that is associated with a particular type of hook the operating system passes the message to each hook procedure referenced in the hook chain one after the other. The action of a hook procedure can depend on the type of hook involved. For example the hook procedures for some types of hooks can only monitor messages others can modify messages or stop their progress through the chain restricting them from reaching the next hook procedure or a destination window.

At step an event occurs in the processing system . At step an operating system running in the processing system registers the occurrence of the event. At step the operating system passes the registered event to the hook chain. At step the event is passed to each hook in the hook chain such that different applications processes and devices may be notified of the registered event. Once the event has propagated throughout the hook chain the method comprises at step an application receiving notification of the event being registered by the processing system .

At step the method comprises the application initiating an API call to an API procedure so as to carry out a response to the registered event. If an API hook has been established between the API call and the API procedure the API call is intercepted before it reaches the API procedure at step . Processing can be performed by an API hook function once the API call has been intercepted prior to the API procedure being called. The API call may be allowed to continue calling the API procedure at step .

Referring now to there is shown a flow diagram illustrating an example method of configuring a processing system to perform application setting activity using a removable storage device in data communication with the processing system .

In particular at step the method comprises selecting an application wherein setting activity associated the selected application is to be performed using the removable storage device . At step the method comprises installing in the processing system an interception module to intercept application setting activity associated with the selected application . In response to the interception module intercepting application setting activity associated with the selected application step comprises performing the application setting activity using the removable storage device thereby storing application setting data associated with the selected application in the removable storage device .

As can be appreciated by using the interception module to intercept the application setting activity and performing the application setting activity for the selected application using the removable storage device application settings data specific to the selected application is stored and performed using the removable storage device.

Additionally due to the interception module intercepting the application setting activity source code of the selected application does not have to be rewritten in order to store application setting data in the removable storage device .

Furthermore it can be appreciated that since the interception module can automatically intercept application setting activity associated with the selected application the user does not need in depth knowledge of the application to copy the relevant settings data .

Additionally if the processing system crashes the settings data for the selected application can be restored from the removable storage device without the user requiring an indepth knowledge of which settings cannot be copied as the setting data stored on the removable storage device is relevant to the selected application .

Referring now to there is shown a block diagram of an example of a system to perform application setting activity using a removable storage device in data communication with the processing system .

In particular the selection module allows for one or more applications to be selected wherein application setting data associated with the selected application is to be stored in the removable storage device . When the selection has been completed the interception module is installed in the processing system to intercept application setting activity associated with the selected application . In response to intercepting application setting activity the application setting activity is performed using the removable storage device . Therefore application setting data associated with the selected application is stored in the removable storage device . Setting data for non selected applications continues to be stored in the non removable storage device .

Optionally as shown by dotted lines in the application setting activity can be performed using the removable storage device and the non removable storage device . For example if a setting value is being stored for application the storage activity is intercepted and performed using the removable storage device and the non removable storage device . In this form the setting data stored on the removable storage device is a back up copy of the settings stored in the non removable data storage device for the selected application .

Referring now to B and C there is shown a more detailed flow diagram of an example method of performing application setting activity using a removable storage device .

In particular at step the method comprises launching the selection module . In one form the selection module is provided as a software application on the removable storage device which is in data communication with the processing system . However it will be appreciated that the selection module could alternatively be provided in the non removable data storage device of the processing system .

At step the user interacts with the selection module to select an application to install in the processing system . In one form the selection module is provided as a graphical user interface GUI which allows the user to select the application to install in the processing system . A pull down menu may be provided with the GUI to select the application to install in the processing system .

At step the interception module is installed in the processing system to intercept application setting activity associated with the selected application from step . The interception module may be provided in the form of one or more hook functions which intercept application setting activity for the selected application . It will be appreciated that the interception module can be configured to intercept activity using the technique discussed in relation to .

At step once the interception module has been installed an installation file to install the selected application is launched so as to begin installing the application in the memory of the processing system .

Alternatively the installation of the application may redirected to be installed in the removable storage device such that the application is portable between processing systems and thus does not require installation in the processing system memory. The installation may be at least partially installed in the removable storage device or wholly installed in the removable storage device. The interception module can be configured to intercept application installation activity. During the installation the interception module may intercept application installation activity associated with installing the application in the processing system and perform the application installation activity using the removable storage device . Thus the application is installed in the removable storage device . Optionally the application may be installed in both the processing system and the removable storage device .

At step during the installation of the application application setting activity associated with the selected application is intercepted by the interception module . Generally whilst an application is installing a number of default settings are installed such as the setting entries in the system registry of the processing system . This form application setting activity is intercepted by the interception module .

At step the method comprises performing the application setting activity using the removable storage device . The application setting activity can comprise a read activity a create activity and or a write activity.

The removable storage device can comprise a database to emulate a system registry to allow data to be created stored and read using the removable storage device . The database can be configured to emulate common configuration file formats comprising INI files INF files and Windows registry entries.

It will be appreciated that other forms of settings activity associated with the application can be intercepted during the installation process of the application . In an optional form non system installed processes loaded by the launched installation file can be intercepted such that the setting activity can be performed using the removable storage device .

At step details of the intercepted setting activity performed using the removable storage device are stored in the removable storage device . These details are herein referred to as interception data . The interception data can be indicative of the type of setting data the original location which the setting data was to be stored created and or read and the new location in the removable storage device of the setting data .

Steps to continue to be performed until the installation of the application has completed as depicted by the decision block of step in .

Once the application has been installed the user may launch the application at step . During the launch and execution of the application application setting activity is generally initiated by the application to retrieve create and or store setting data . At step the method comprises the interception module intercepting the application setting activity during the launch and execution of the application . Step is performed similarly to step .

At step the interception data may be compared to the intercepted request to determine if setting data has been stored in the removable storage device. If the comparison results in a positive comparison as determined at step the method proceeds to step to perform the application setting activity using the removable storage device. If the comparison results in a negative comparison the method proceeds to step where the interception module passes the application setting activity to the intended destination as previously discussed in relation to . It will be appreciated that if the intercepted request is to create a setting a comparison to the removable storage device may not be required.

At step the method comprises performing the application setting activity using the removable storage device . For example if the application initiates a request to retrieve a setting associated with whether a wizard should be opened upon launching the application the interception data is used to determine where the application setting data is stored in the database. Once the location in the database is determined the application setting data is retrieved from the removable storage device and returned to the application .

Steps to are repeated until the application is terminated as represented by step . During termination of the application further application setting activity may be intercepted and performed using the removable storage device .

Referring now to there is shown a method of transferring application settings between processing systems. The method is directed towards allowing a roaming application profile in that application settings stored on the removable storage device for a first processing system can be used and maintained for the same application at a second processing system not shown . It will be appreciated that the second processing system is a form of processing system .

In particular at step the method comprises coupling the removable storage device with the second processing system . The removable storage device comprises application setting data associated with an application in a first processing system . In an optional form the removable storage device may also comprise the installed application.

At step the method comprises selecting the application which application setting data from the first processing system is to be maintained. In particular the selection module in the form of a graphical user interface may be used to select the application .

At step the method comprises installing the interception module for the selected application in the second processing system . At step the application is launched in the second processing system . The application may be launched from memory of the second processing system or from the removable storage device depending on where the application has been installed.

At step the method comprises intercepting application setting activity associated with the selected application . At step the method comprises performing a comparison between the intercepted setting activity and the interception data . In response to a positive comparison as determined at step the method proceeds to step . In response to a negative comparison the method proceeds to step where the intercepted setting activity is passed to the appropriate destination as discussed in relation to .

At step the method comprises the intercepted setting activity being performed using the removable storage device . This can comprise determining using the interception data the location of the application setting data in the removable storage device and performing the application setting activity using the removable storage device . For example an intercepted read activity results in the appropriate application setting data being retrieved from the database of the removable storage device . In another example an intercepted write activity results in the old application setting data being overwritten in the database of the removable storage device .

At step the method comprises determining if the application has terminated. If the application has terminated the method ends. If the application has not terminated the method returns back to step to intercept application setting activity for the selected application in the second processing system .

The method of allows for application setting data for one or more selected applications to be maintained between a first and second processing system . Therefore the user is not required to reset application settings for an application at the second processing system .

In an optional form the processing system comprises one or more rules which when applied determine whether intercepted application setting activity is to be performed using the memory of the processing system or the removable storage device. In particular the one or more rules are applied once application setting activity is intercepted. The one or more rules may be part of or called by the respective intercepting hook function. The one or more rules may be installed in the memory of the processing system by the installation module.

In another alternative the one or more rules may be installed in the removable storage device rather than the memory of the processing system thereby allowing the one or more rules to be portable between processing systems. In this embodiment the one or more rules may be used from the removable storage device or alternatively the one or more rules may be copied to the processing system memory and then used from the memory of the processing system. When the removable storage device is coupled to the processing system the one or more rules are copied onto the memory of the processing system. When the removable storage device is uncoupled from the processing system a clean up process may be performed in order to delete the one or more rules from the memory of the processing system.

In one form the one or more rules may be dynamically generated during installation of the application. This can comprise the use of a rule generation module which monitors the installation by the installation module of the application and generates one or more rules which can be applied to determine whether the removable storage device and or the processing system is to be used for performing the application setting activity. In an additional or alternate form an analyst may monitor the execution of the application after installation of the application and manually generate the one or more rules.

The application of the one or more rules can be used to ignore performing application setting activity such as writing temporary files and the like at non standard temporary locations in the memory of the processing system. Furthermore the application of the one or more rules also filter the storage or entities which are unable to be stored only on the removable storage device such as kernel mode drivers and system service thereby allowing these types of application setting activity to be performed using the memory of the processing system.

It will also be appreciated that the binary code of the application does not need to be altered in order for the setting activity to be stored on the removable storage device due to the interception module intercepting setting activity to be performed using the removable storage device. This therefore alleviates custom code for the application being written in order to redirect the application setting activity to the removable storage device .

Furthermore it will also be appreciated that installing the application in the removable storage device also provides significant benefits such as a reduction in memory usage in processing systems as only the interception module is required to be installed in each processing system rather than the application .

It will be appreciated that the application setting activity can subsequently be performed in relation to non removable storage device of the second processing system .

It will be appreciated that any form of removable storage device can be used such as a floppy disk rewrittable compact disks Universal Serial Bus USB keys and the like.

An example piece of pseudocode for performing application setting activity using a removable storage device is provided below.

An example piece of pseudocode for maintaining application settings from a first processing system to a second processing system using a removable storage device is provided below.

The embodiments illustrated may be implemented as a software package or component. Various embodiments can be implemented for use with the Microsoft Windows operating system or any other modern operating system. The embodiments described throughout can also be implemented via hardware or a combination of hardware and software.

In an optional form prior to installing the interception module in a processing system a search of the processing system memory may be conducted to determine if an interception module for the selected application has already previously been installed. If the interception module has previously been installed in the processing system the installation step of the interception module does not need to be performed.

Optional embodiments of the present invention may also be said to broadly consist in the parts elements and features referred to or indicated herein individually or collectively in any or all combinations of two or more of the parts elements or features and wherein specific integers are mentioned herein which have known equivalents in the art to which the invention relates such known equivalents are deemed to be incorporated herein as if individually set forth.

Although a preferred embodiment has been described in detail it should be understood that various changes substitutions and alterations can be made by one of ordinary skill in the art without departing from the scope of the present invention.

