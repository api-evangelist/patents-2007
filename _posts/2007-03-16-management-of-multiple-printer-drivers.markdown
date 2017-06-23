---

title: Management of multiple printer drivers
abstract: It is determined whether a combination of an output requesting application and a printer driver designated as an output destination is a combination of the first application and first printer driver or a combination of the second application and second printer driver. When it is determined that the combination of the output requesting application and the printer driver is neither of these combinations, confirmation information to confirm whether to execute a print process is output.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=07907313&OS=07907313&RS=07907313
owner: Canon Kabushiki Kaisha
number: 07907313
owner_city: Tokyo
owner_country: JP
publication_date: 20070316
---
The present invention relates to an information processing apparatus in which a plurality of types of printer drivers and a plurality of types of graphics units run a control method therefore and a program.

An application on a host computer prints an image or text from a printer by generally using an arrangement as shown in .

More specifically an application on a host computer passes graphics data to a graphics engine . The graphics engine processes the graphics data and passes it to a printer driver . The printer driver generates print data e.g. PDL Page Description Language to a printer . The print data is stored in a spooler and then sent to the printer .

In particular the graphics engine converts the resolution of graphics data created by the application and processes graphics data by a simulation process or the like in accordance with the performance of the printer driver . The graphics engine allows the application and printer driver to operate independently of each other. The graphics engine is generally provided as part of an OS Operating System .

For example Microsoft held a hardware engineering conference WinHEC 2005 in Seattle U.S.A. in 2005. At this conference Microsoft announced that a new Microsoft OS Windows Vista supports two graphics engines GDI and WPF as shown in . Daniel Emerson Advances in Windows Printing WinHEC 2005 Conference April 2005. The WPF stands for Windows Presentation Foundation.

A conventional Microsoft printing system utilizes a graphics engine GDI from an application using an API called a Win32 API and creates print data from graphics data by a printer driver called from the GDI. This print process sequence is called a GDI print path.

The API stands for Application Programming Interface. The GDI stands for Graphic Device Interface. An application using the Win32 API will be referred to as a Win32 application . A printer driver called from the GDI will be referred to as a GDI printer driver .

According to Windows Vista a new print process sequence called an XPS print path is added to the conventional GDI print path. The XPS print path is a print process sequence to convert XPS graphics data into print data by the printer driver using a graphics engine WPF from an application using a WinFx API.

The XPS stands for XML Paper Specification. An application using the WinEx API will be referred to as a WinFx application . A printer driver which processes XPS graphics data will be referred to as an XPS printer driver .

These graphics engines i.e. GDI and WPF can cooperate with each other. With this cooperation the Win32 application can pass graphics data to the XPS printer driver and the WinFx application can pass graphics data to the GDI printer driver .

The cooperative mechanism of the two graphics engines in Windows Vista will be explained with reference to .

A print process sequence represents a conventional GDI print path. Graphics data passed from the Win32 application is stored as an EMF Enhanced Metafile spool file in the GDI . Then the GDI printer driver converts the EMF spool file into print data.

A print process sequence represents an XPS print path added in Windows Vista. Graphics data passed from the WinFx application is stored as an XPS spool file in the WPF . Then the XPS printer driver converts the XPS spool file into print data.

A print process sequence represents a print process sequence when the GDI printer driver prints graphics data from the WinFx application . Graphics data passed from the WinFx application is converted into EMF graphics data by an XPS GDI conversion module via the WPF and stored as the EMF spool file . Then the GDI printer driver converts the EMF spool file into print data.

A print process sequence represents a process sequence when the XPS printer driver prints graphics data from the Win32 application . Graphics data passed from the Win32 application is converted into XPS graphics data by a GDI XPS conversion module via the GDI and stored as the XPS spool file . Then the XPS printer driver converts the XPS spool file into print data.

In Windows Vista two graphics engines coexist and cooperate with each other so the four print process sequences are conceivable. Either the GDI printer driver or XPS printer driver is prepared as a printer driver for a printer and can cope with print processes from both the Win32 application and WinFx application .

There is proposed a print support technique of acquiring PDL information from a printer selecting a proper driver and if no proper driver exists uploading it from a device installing it and printing by the installed driver Japanese Patent Laid Open No. 2004 021460 .

The XPS and EMF formats are different. The print quality print function and print speed may degrade if a print process is executed using a print process sequence of converting graphics data like the print process sequences and in .

In terms of the print function for example logical operation containing graphics data supported by the EMF format is not supported by the XPS format in the print process sequence . The GDI XPS conversion module deletes logical operation information when converting EMF graphics data into XPS one. The XPS printer driver receives graphics data having no logical operation information. When the user outputs the result created using the Win32 application from the XPS printer driver he may not obtain any intended output result.

To the contrary advanced graphics graphics data supported by the XPS format is not supported by the EMF format in the print process sequence . The XPS GDI conversion module performs local bitmapping Flattering when converting XPS graphics data into GDI one. In this case graphics data is converted into bitmap data and the GDI printer driver cannot determine the original object attribute failing to obtain any user intended output result.

In terms of the print function for example electronic signature information supported by the XPS format is not supported by the EMF format in the print process sequence . A process supported by the EMF format to directly notify the GDI printer driver of information from an application is not supported by the XPS format in the print process sequence . For this reason even if an application uses functions applicable to the print process sequences and these functions cannot be implemented in the print process sequences and .

The print speeds in the print process sequences and are lower than those in the print process sequences and because of processes such as GDI XPS conversion and XPS GDI conversion.

It is therefore desirable to avoid the print process sequences and . Even if both the XPS printer driver and GDI printer driver are registered for the same printer the graphics engine in Windows Vista does not dynamically switch to give priority to the print process sequence or . In principle the user does not recognize that the application is a Win32 or WinFx application or that there are four print process sequences. It is difficult to avoid the print process sequences and .

Print setting information has print setting data in a data structure called the DevMode structure on the GDI print path but has it in an XML data structure called PrintTicket on the XPS print path. Conversion from GDI to XPS or from XPS to GDI requires conversion from DevMode into PrintTicket or from PrintTicket into DevMode. Similar to graphics data the DevMode expressible range and PrintTicket expressible range are different from each other. This process is done not automatically by the operating system but by the printer driver itself using an expanded architecture. No data is omitted unlike graphics if an IHV which creates a printer driver appropriately prepares a conversion process.

The present invention has been made to overcome the conventional drawbacks and has as its object to provide an information processing apparatus capable of confirming an error generated by a graphics function for use before printing in an environment where graphics functions with different print data generation formats coexist a control method therefore and a program.

According to the present invention the foregoing object is attained by providing an information processing apparatus which operates a first graphics unit that generates first graphics data processible by a first printer driver in accordance with a print instruction from a first application and a second graphics unit that generates second graphics data processible by a second printer driver in accordance with a print instruction from a second application comprising 

In a preferred embodiment the output means outputs as the confirmation information information representing that the designated printer driver is not proper.

In a preferred embodiment the first printer driver and the second printer driver have driver information of a first format and comprise conversion means for converting the driver information of the first format into driver information of a second format.

In a preferred embodiment the output means outputs information representing a proper printer driver as the confirmation information.

In a preferred embodiment the determination means determines as the proper printer driver a printer driver having the same printer driver name as a printer driver name of a selected printer driver.

In a preferred embodiment the determination means determines as the proper printer driver a printer driver having the same printer driver name and the same output destination information as a printer driver name and output destination information of a selected printer driver.

In a preferred embodiment when no proper printer driver is installed the output means outputs information representing an acquisition site of the proper printer driver as the confirmation information.

In a preferred embodiment when no proper printer driver is installed the output means outputs as the confirmation information information to confirm whether to install the proper printer driver.

According to the present invention the foregoing object is attained by providing an information processing apparatus which operates a first graphics unit that generates first graphics data processible by a first printer driver in accordance with a print instruction from a first application and a second graphics unit that generates second graphics data processible by a second printer driver in accordance with a print instruction from a second application comprising 

According to the present invention the foregoing object is attained by providing a method of controlling an information processing apparatus which operates a first graphics unit that generates first graphics data processible by a first printer driver in accordance with a print instruction from a first application and a second graphics unit that generates second graphics data processible by a second printer driver in accordance with a print instruction from a second application comprising 

According to the present invention the foregoing object is attained by providing a method of controlling an information processing apparatus which operates a first graphics unit that generates first graphics data processible by a first printer driver in accordance with a print instruction from a first application and a second graphics unit that generates second graphics data processible by a second printer driver in accordance with a print instruction from a second application comprising 

According to the present invention the foregoing object is attained by providing a computer program which is stored in a computer readable medium and causes a computer to control an information processing apparatus which operates a first graphics unit that generates first graphics data processible by a first printer driver in accordance with a print instruction from a first application and a second graphics unit that generates second graphics data processible by a second printer driver in accordance with a print instruction from a second application causing the computer to execute

According to the present invention the foregoing object is attained by providing a computer program which is stored in a computer readable medium and causes a computer to control an information processing apparatus which operates a first graphics unit that generates first graphics data processible by a first printer driver in accordance with a print instruction from a first application and a second graphics unit that generates second graphics data processible by a second printer driver in accordance with a print instruction from a second application causing the computer to execute

Further features of the present invention will be apparent from the following description of exemplary embodiments with reference to the attached graphics.

Preferred embodiments of the present invention will now be described in detail with reference to the graphics. It should be noted that the relative arrangement of the components the numerical expressions and numerical values set forth in these embodiments do not limit the scope of the present invention unless it is specifically stated otherwise.

A print process sequence represents a conventional GDI print path. Graphics data passed from a Win32 application is stored as an EMF Enhanced Metafile spool file in a GDI . Then a GDI printer driver converts the EMF spool file into print data.

A print process sequence represents an XPS print path added in Windows Vista. Graphics data passed from a WinFx application is stored as an XPS spool file in a WPF . Then an XPS printer driver converts the XPS spool file into print data.

A print process sequence represents a print process sequence when the GDI printer driver prints graphics data from the WinFx application . Graphics data passed from the WinFx application is converted into EMF graphics data by an XPS GDI conversion module via the WPF and stored as the EMF spool file . Then the GDI printer driver converts the EMF spool file into print data.

A print process sequence represents a process sequence when the XPS printer driver prints graphics data from the Win32 application . Graphics data passed from the Win32 application is converted into XPS graphics data by a GDI XPS conversion module via the GDI and stored as the XPS spool file . Then the XPS printer driver converts the XPS spool file into print data.

In Windows Vista two graphics engines coexist and cooperate with each other so the four print process sequences are conceivable. Either the GDI printer driver or XPS printer driver is prepared as a printer driver for a printer and can cope with print processes from both the Win32 application and WinFx application .

In an information processing apparatus comprises the Win32 application serving as the first application and the GDI printer driver serving as the first printer driver. The information processing apparatus also comprises the WinFx application serving as the second application and the XPS printer driver serving as the second printer driver.

The two graphics engines i.e. the GDI serving as the first graphics unit and the WPF serving as the second graphics unit exist on the OS. The Win32 application passes a GDI function serving as the first graphics data to the GDI while the WinFx application passes WPF API data serving as the second graphics data to the WPF .

The GDI printer driver receives graphics data from the GDI and converts it into print data for a printer . The XPS printer driver receives graphics data from the WPF and converts it into print data for the printer . Print data created by the printer driver is transmitted to the printer via a spooler .

The present invention is applicable to a system having the functions of a single device or formed from a plurality of devices as far as the system can execute the functions of the present invention unless otherwise specified. The present invention is also applicable to a system which is connected via a network such as a LAN or WAN to perform processes.

In reference numeral denotes a host computer having a CPU . The CPU processes a document of building elements such as a figure image text table including a spreadsheet and the like and the like on the basis of a document processing program application program stored in a program ROM of a ROM or an external memory . The CPU comprehensively controls each device connected to a system bus in a host computer main body .

The program ROM of the ROM or the external memory stores programs such as an operating system program to be referred to as an OS hereinafter which is a control program for the CPU . A font ROM of the ROM or the external memory stores data such as font data used in the document process. A data ROM of the ROM or the external memory stores various data used to perform various processes such as the document process.

Reference numeral denotes a RAM functioning as a main memory work area and the like for the CPU . Reference numeral denotes a keyboard controller KBC which controls a key input from a keyboard KB or a pointing device not shown . Reference numeral denotes a CRT controller CRTC which controls display on a CRT display CRT . An LCD controller and LCD are also available instead of the CRT controller and CRT display .

Reference numeral denotes a disk controller DKC which controls access to the external memory for a boot program various applications font data user files edit files and the like. The DKC also controls access to the external memory e.g. a hard disk HD or floppy disk FD which stores various data such as a print control command generation program to be referred to as a printer driver hereinafter .

Reference numeral denotes a printer controller PRTC which connects to the printer via a predetermined bidirectional interface and executes a communication control process with the printer . Examples of the bidirectional interface are a USB interface IEEE1394 interface and wireless LAN interface.

The CPU enables WYSIWYG on the CRT by expanding rasterizing an outline font in a display information RAM set in e.g. the RAM to provide a GUI. The CPU opens various registered windows and executes various data processes on the basis of commands designated with the mouse cursor not shown or the like on the CRT . In printing the user opens a window associated with print settings and sets the printer and a printing method to the printer driver including selection of the print mode.

In the printer reference numeral denotes a printer CPU. The printer CPU comprehensively controls each device connected to a system bus in a printer control unit . The printer CPU outputs an image signal serving as output information to a printing unit printer engine connected to the system bus on the basis of a program such as a control program stored in a program ROM of a ROM or an external memory .

The program ROM of the ROM stores programs such as a control program for the printer CPU . A font ROM of the ROM stores data such as font data used to generate the output information. When the printer does not comprise any external memory such as a hard disk HD or IC card a data ROM of the ROM stores information or the like used in the host computer .

The printer CPU can communicate with the host computer via an input unit and can notify the host computer of various types of information such as status information in the printer . Reference numeral denotes a RAM functioning as a main memory work area and the like for the CPU . The RAM can increase its memory capacity by an optional RAM connected to an expansion port not shown .

The RAM is used as an output information expansion area environment data storage area NVRAM and the like. A disk controller DKC controls access to the external memory . The external memory is connected as an option and stores data such as font data an emulation program and form data. Reference numeral denotes an operation unit having an operation panel switch LED display and the like for various operations to the printer .

The number of external memories is not limited to one and but is at least one. It is possible to connect a plurality of external memories which store a built in font an optional font card and a program for interpreting printer control languages of different language systems. The external memory may have an NVRAM not shown to store printer mode setting information from the operation unit .

A control unit implemented by the CPU of the host computer controls a determination unit and output unit and executes various processes e.g. processes shown in the flowcharts of and implemented by various programs.

The control unit controls the first graphics unit which generates the first graphics data processible by the first printer driver in accordance with a print instruction from the first application and the second graphics unit which generates the second graphics data processible by the second printer driver in accordance with a print instruction from the second application.

The determination unit determines whether a combination of an output requesting application and a printer driver designated as an output destination is a combination of the first application and first printer driver or a combination of the second application and second printer driver. And the determination unit determines whether a process path is to convert the first graphics data into the second graphics data and output the second graphics data to the second printer driver.

If the determination unit determines that the combination of the output requesting application and the printer driver is neither of these combinations the output unit outputs confirmation information to confirm whether to execute a print process.

And if the determination unit determines the process path which is to convert the first graphics data into the second graphics data and output the second graphics data to the second printer driver the output unit outputs confirmation information to confirm whether to execute a print process.

The user displays a print dialog from an application in printing and displays the user interface UI of the printer driver. At this time if the user does not grasp the type of selected application and that of selected printer driver he cannot know which print process sequence runs.

The type of application is the Win32 application or WinFx application . The type of printer driver is the CDI printer driver or XPS printer driver .

A feature of the first embodiment is to display a warning to the user when the print process sequence in is or upon displaying the printer driver UI i.e. to output confirmation information to confirm whether to execute a print process.

The printer driver holds driver information in the DevMode format. The Win32 application uses DevMode while the WinFx application uses DevMode or PrintTicket.

If the application requests PrintTicket the GDI printer driver must convert DevMode into PrintTicket. It can be determined that the print process sequence is when the GDI printer driver converts DevMode into PrintTicket.

Also when the application requests PrintTicket the XPS printer driver must convert DevMode into PrintTicket. In the print process sequence the Win32 application requests DevMode so the XPS printer driver does not convert it into PrintTicket. When the XPS printer driver does not perform any conversion it can be determined that the XPS printer driver is highly likely to follow the print process sequence . However it cannot be concluded that the print process sequence is because the WinFx application may request DevMode print process sequence .

In printing the user displays the print dialog of the WinFx application . At this time the WinFx application activates the GDI printer driver to request PrintTicket as printer driver information. Since the GDI printer driver holds only DevMode it converts DevMode into PrintTicket and notifies the WinFx application of the PrintTicket.

To make detailed print settings from the WinFx application the user instructs the GCD printer driver via the WinFx application to display the UI of the GDI printer driver . The WinFx application sets PrintTicket if any change is made through the print dialog including the change for the GDI printer driver . The GDI printer driver converts the PrintTicket into DevMode and displays the UT.

Since the GDI printer driver converts DevMode into PrintTicket at the time of start up it determines that it has received a print instruction from the WinFx application . A graphics error and degradation of the print process function are expected and the GDI printer driver displays a warning message shown in .

When the Win32 application activates the GDI printer driver it requests the GDI printer driver to acquire DevMode. The GDI printer driver need not execute conversion into PrintTicket. Neither a graphics error nor degradation of the print process function is expected so the GDI printer driver does not display any warning in particular. That is when PrintTicket is requested of the GDI printer driver it can be determined that the print process sequence is .

In printing the user displays the print dialog of the Win32 application . At this time the Win32 application activates the XPS printer driver to request DevMode as driver information. Since the XPS printer driver holds DevMode it notifies the Win32 application of the DevMode.

To make detailed print settings from the Win32 application the user instructs the XPS printer driver via the Win32 application to display the UI of the XPS printer driver . The Win32 application sets DevMode if any change is made through the print dialog including the change for the XPS printer driver . The XPS printer driver displays the UI using the DevMode.

When called from the WinFx application the XPS printer driver should convert DevMode into PrintTicket. However the XPS printer driver does not convert DevMode into PrintTicket at the time of start up. Thus the XPS printer driver determines that it has received a print instruction from the Win32 application . A graphics error and degradation of the print process function are expected so the XPS printer driver displays a warning message shown in . Since the WinFx application may request DevMode the XPS printer driver notifies the Win32 application of the possibility of the print process sequence .

An outline of the process in the first embodiment has been described. A concrete arrangement to implement this process will be explained 

The XPS printer driver holds a print ticket provider and UI driver module XPS . The UI driver module XPS is based on DevMode and displays a UI for setting print setting information in response to a call from an application. The print ticket provider converts PrintTicket print ticket into DevMode or DevMode into PrintTicket.

In when the Win32 application requests DevMode for print settings the UI driver module of the XPS printer driver is based on DevMode and does not require any conversion. If the Win32 application prints using the XPS printer driver the print ticket provider need not perform any conversion.

To the contrary the WinFx application requests a print ticket for print settings. The XPS printer driver does not hold any print ticket and the print ticket provider converts the print ticket into DevMode.

The XPS printer driver can recognize the conversion process of the print ticket provider . If the XPS printer driver recognizes that the print ticket provider converts a print ticket into DevMode it can determine that the print setting requesting source is the WinFx application . If the print ticket provider does not execute any conversion the XPS printer driver can determine that the print setting requesting source is the Win32 application.

The GDI printer driver is identical in structure to the XPS printer driver and comprises a UI driver module GDI equivalent to the UI driver module XPS . The GDI printer driver is also based on DevMode.

The GDI printer driver can recognize the conversion process of the print ticket provider similar to the XPS printer driver . The GDI printer driver can determine the process path of data to be printed and a print setting requesting application.

The internal functional arrangement of the printer driver in the first embodiment will be explained with reference to .

Reference numeral denotes an application a printer driver and a system spooler. Reference numeral denotes a driver control unit which acquires driver information from a driver information holding unit . If necessary a driver information conversion processing unit converts its driver information e.g. DevMode into another format and notifies the application of the converted driver information.

Reference numeral denotes a driver UI display unit which displays a UI on the basis of driver information received from the application and inquires whether the driver information conversion processing unit has performed conversion.

Reference numeral denotes a print process sequence determination unit which receives from the driver information conversion processing unit information representing whether it has performed conversion and determines whether the print process sequence is or . When the printer driver is the GDI printer driver and conversion has been done the print process sequence determination unit determines that the print process sequence is not proper. When the printer driver is the XPS printer driver and no conversion has been done the print process sequence determination unit determines that the print process sequence may not be proper. Reference numeral denotes a warning notification unit which outputs warning information warning message as shown in or B when the print process sequence determination unit determines that the print process sequence is not proper.

In the process the GDI printer driver has a conversion process flag as a work area and the initial value of the flag is OFF.

In step S the driver control unit determines whether the driver information request from the application is a DevMode request or PrintTicket request. If the driver information request is a DevMode request YES in step S the process advances to step S to notify the application of DevMode.

If the driver control unit determines that the driver information request is a PrintTicket request NO in step S the process advances to step S to convert DevMode into PrintTicket. More specifically if the print ticket provider shown in driver information conversion processing unit in receives a PrintTicket request it converts DevMode into PrintTicket. Since the print ticket provider has converted DevMode into PrintTicket in step S the conversion process flag is set ON to this effect in step S. The RAM of the host computer saves whether the conversion process flag is ON or OFF. In step S the driver control unit notifies the application of the converted PrintTicket.

In step S the driver UI display unit determines whether it has received a UI display request from the application. If the driver UI display unit has not received any UI display request NO in step S the process waits until the driver UI display unit receives a UI display request. If the driver UI display unit has received a UI display request YES in step S the process advances to step S.

In step S the driver UI display unit displays a driver UI. In step S the warning notification unit determines whether the conversion process flag is ON.

Since the RAM saves the conversion process flag in the process of step S the warning notification unit can make determination in step S by referring to the RAM .

If the warning notification unit determines in step S that the conversion process flag is ON YES in step S the process advances to step S to notify the user of e.g. a warning message shown in and then ends. If the conversion process flag is OFF NO in step S the process ends without notifying the user of any warning message.

In the conversion process flag is determined step S after displaying the driver UI step S but the order of these steps is arbitrary. It suffices to execute the determination process in step S after the user issues a UI display request.

That is the GDI printer driver determines in whether a combination of a print instructing application and a printer driver designated as an output destination is a combination of the Win32 application and GDI printer driver. If the GDI printer driver determines that the combination of the print instructing application and printer driver is not a combination of the Win32 application and GDI printer driver it outputs information in step S to confirm whether to execute a print process.

In step S for example if the selected printer driver is the GDI printer driver it displays a message box warning message shown in to the user. If the selected printer driver is the XPS printer driver it displays a message box warning message shown in . The message can warn the user that the currently selected printer driver does not follow a proper print process sequence.

In the processes in steps S to S correspond to those in steps S to S of the flowchart in and details thereof will be omitted.

After the process in step S the warning notification unit determines in step S whether the conversion process flag is ON. If the conversion process flag is ON YES in step S the process ends. If the conversion process flag is OFF NO in step S the process advances to step S the warning notification unit notifies the user and then the process ends. When the XPS printer driver does not execute conversion into PrintTicket it determines that a graphics error and degradation of the print process function occur as described above. Thus if the warning notification unit determines in step S that the conversion process flag is OFF it displays a warning message shown in .

That is the XPS printer driver determines in whether a combination of a print instructing application and a printer driver designated as an output destination is a combination of the WinFx application and XPS printer driver. If the XPS printer driver determines that the combination of the print instructing application and printer driver is not a combination of the WinFx application and XPS printer driver it outputs information in step S to confirm whether to execute a print process.

As described above according to the first embodiment the printer driver determines whether a driver selected via an application is appropriate and outputs confirmation information warning information in accordance with the determination result. This can improve user friendliness while preventing degradation of the image quality and performance omission of security information and the like.

In the first embodiment the printer driver determines whether a driver selected via an application is appropriate and warns the user in accordance with the determination result that the print process sequence is not appropriate. However the user may not know which printer driver is proper and may be notified of a proper printer driver name.

In this arrangement printer drivers hold partner driver names in addition to the work area described in the first embodiment. Assume that there are a GDI printer driver LBP XXXX GDI and an XPS printer driver LBP XXXX XPS as printer drivers of a printer LBP XXXX . In this case the driver information holding unit of the GDI printer driver holds an XPS printer driver name whereas the driver information holding unit of the XPS printer driver holds a GDI printer driver name.

The operation of the printer driver is the same as that in the first embodiment except for the notification processes in steps S and S.

Details of the notification process will be explained with reference to . Step S of is executed when it is determined in step S of or step S of to generate a warning.

If a warning notification unit of the CDI printer driver determines that the conversion flag is ON it displays a message box shown in . The driver information holding unit holds the name e.g. LBP XXXX GDI of the GDI printer driver and the name e.g. LBP XXXX XPS of the compatible printer driver.

If the warning notification unit determines to generate a warning it reads out the compatible printer driver name from the driver information holding unit and displays e.g. the message box shown in . The basic process is the same as for the XPS printer driver. However if the selected printer driver is the XPS printer driver the warning notification unit displays a message box shown in when determining that the conversion flag is OFF. In this manner the printer driver outputs information representing a proper printer driver as confirmation information.

As described above according to the second embodiment the printer driver warns the user that the currently selected printer driver is not appropriate and notifies the user of the name of a printer driver expected to be appropriate. The user can easily select an appropriate printer driver.

The second embodiment has been described on the assumption that each printer driver holds a compatible printer driver name. If each printer driver does not hold a compatible printer driver name it cannot notify the user of a proper printer driver name. In the third embodiment it may be determined whether a proper printer driver compatible with a selected printer driver is installed in a host computer for the same printer notifying the user that the proper printer is installed.

In this arrangement the printer driver forms PrinterInfo holding the number N of listed printers and printer information in addition to the work area described in the second embodiment. The initial value of the number N of printers is 0. PrinterInfo holds information by the number of listed printers. The driver operation is the same as that in the first embodiment except for the notification processes in steps S and S.

In step S a driver control unit lists printers installed in a host computer . Since a RAM holds information on printers installed in the host computer the printer driver refers to the RAM to list installed printers. In step S the driver control unit sets the number of listed printers to N and sets the listed printer information in Printerinfo.

In step S the driver control unit determines whether the number N of printers 0. If N 0 YES in step S all printers have been checked or no printer driver can be listed and the process ends. If N 0 NO in step S the process advances to step S.

In step S the driver control unit determines whether the Nth printer driver name in PrinterInfo coincides with a printer driver name held in a driver information holding unit . If these printer driver names do not coincide with each other NO in step S the process advances to step S to decrement N and then returns to step S.

If the driver control unit determines that these printer driver names coincide with each other YES in step S the process advances to step S. The driver control unit determines whether the ports of the selected printer driver and Nth printer driver whose names are determined to coincide with each other coincide with each other. More specifically PrinterInfo holds port information of each printer driver and the driver control unit refers to PrinterInfo to make determination in step S.

An individual port is assigned to each printer driver and held by the driver information holding unit of the printer driver. For a network port if the IP addresses of the selected printer driver and Nth printer driver coincide with each other it may be determined that their network ports coincide with each other.

If the driver control unit determines that the ports of the selected printer driver and Nth printer driver do not coincide with each other NO in step S the process advances to step S. If the driver control unit determines that these ports coincide with each other YES in step S the process advances to step S.

In step S for example if the selected printer driver is the GDI printer driver its warning notification unit displays a message box shown in . If the selected printer driver is the XPS printer driver its warning notification unit displays a message box shown in .

In the third embodiment whether the ports of printer drivers coincide with each other is confirmed after confirming whether their names coincide with each other but the order of these steps may be reverse.

As described above according to the third embodiment the printer driver warns that the currently selected printer driver is not proper. The printer driver recommends as a proper printer driver a printer driver with the same name and port output destination information as those of the selected printer driver. The user can recognize a printer driver expected to be able to execute an appropriate print process without grasping all printer drivers held in the host computer.

According to the third embodiment the printer driver notifies the user that a proper printer driver is installed for the same printer as that of the printer driver. When there is a printer whose printer driver is installed with a different port the printer driver may notify the user of a message to this effect. In this case the user can use an appropriate printer driver by only switching the port.

The printer driver forms OtherPortPrnInfo holding information on a printer using the same printer driver with different ports in addition to the work area described in the third embodiment. The operation of the printer driver is the same as that in the first embodiment except for the notification processes in steps S and S.

The flowchart of in the fourth embodiment is almost the same as that of in the third embodiment and only a difference will be explained.

In step S a driver control unit determines whether ports coincide with each other corresponding to step S of in the third embodiment . If the driver control unit determines that the ports do not coincide with each other NO in step S the process advances to step S to set PrinterInfo N in OtherPortPrnInfo and then to step S.

If the driver control unit determines N 0 in step S corresponding to step S of in the third embodiment the process advances to step S to determine whether there is OtherPortPrnInfo.

If there is no OtherPortPrnInfo NO in step S the process ends. If there is OtherPortPrnInfo YES in step S the printer driver can determine that another printer driver is installed with a different port. In step S for example a warning notification unit of the CDI printer driver displays a message box shown in . A warning notification unit of the XPS printer driver displays a message box shown in .

As described above according to the fourth embodiment the printer driver warns that the currently selected printer driver is not proper. The printer driver recommends as a proper printer driver a printer driver with the same name as that of the selected printer driver. The printer driver can also recommend printing by switching the port of the proper printer driver. The printer driver can notify the user of the proper printer driver name as far as the names of printer drivers coincide with each other even if their ports do not coincide with each other.

In the fourth embodiment when it is determined that a selected printer driver is not appropriate but there is another printer driver with the same name but a different port the user is notified of the printer driver. The fourth embodiment assumes that a printer driver compatible with one selected by the user is installed. The fifth embodiment will describe a process to notify the user of a printer driver acquisition site when no compatible printer driver is installed. In this case the user can know the printer driver acquisition site and easily acquire a compatible printer driver.

The printer driver holds the printer driver acquisition site in addition to the work area described in the third embodiment. The acquisition site may be a URL or path name. The acquisition site may be held by the printer driver itself or held by the printer and acquired by the printer driver from the printer in display. The operation of the printer driver is the same as that in the first embodiment except for the notification processes in steps S and S.

The flowchart of in the fifth embodiment is almost the same as that of in the fourth embodiment and only a difference will be explained.

In step S corresponding to step S of in the fourth embodiment a driver control unit determines whether there is OtherPortPrnInfo. If the driver control unit determines that there is no OtherPortPrnInfo NO in step S the process advances to step S.

In step S for example if the selected printer driver is the GDI printer driver its warning notification unit displays a message box shown in . If the selected printer driver is the XPS printer driver its warning notification unit displays a message box shown in . The printer driver holds information on the acquisition site of a proper printer driver and if it is determined that no proper printer driver is installed performs the process in step S by reading out the acquisition site of the proper printer driver.

As described above according to the fifth embodiment if it is determined that a printer driver compatible with the currently selected printer driver is not installed the printer driver can notify the user of the acquisition site URL of the printer driver to be installed. That is when no appropriate printer driver is installed the printer driver outputs information representing the acquisition site of an appropriate printer driver as confirmation information. The user can install the appropriate printer driver from the displayed acquisition site.

In the fifth embodiment the user is notified of the printer driver acquisition site when no proper printer driver is installed but the present invention is not limited to this. For example a printer driver installable while displaying the UI can display a proper printer driver and prompt the user to install it. The operation of the printer driver is the same as that in the first embodiment except for the notification processes in steps S and S.

The flowchart of in the sixth embodiment is almost the same as that of in the fifth embodiment and only a difference will be explained.

In step S corresponding to step S in the fifth embodiment the printer driver notifies the user that another printer driver is installed with a different port. At this time for example if the selected printer driver is the CDI printer driver it displays a message box shown in . If the selected printer driver is the XPS printer driver it displays a message box shown in .

In step S the printer driver inquires of the user whether to add a printer. In step S the printer driver determines whether to add a printer by the user as a result of the inquiry through the UI in or B. If a driver control unit recognizes that the user has selected addition of a printer has pressed the OK button it changes the printer driver port held in OtherPortPrnInfo.

More specifically the driver control unit adds the printer after changing printer driver information in OtherPortPrnInfo so that the name and port of the printer driver to be added coincide with those of the currently selected printer driver. If the user has pressed the cancel button the driver control unit determines not to add any printer.

If the driver control unit determines to add a printer YES in step S the process advances to step S to add a printer and then ends. If the driver control unit determines not to add any printer NO in step S the process ends.

If there is no OtherPortPrnInfo NO in step S for example the GDI printer driver displays a message box shown in in step S or the XPS printer driver displays a message box shown in .

In step S the driver control unit determines whether to install a printer. If the driver control unit determines that the user has pressed the OK button on the message box in it installs a proper printer driver. If the user has pressed the cancel button the driver control unit determines not to install any printer driver.

If the driver control unit determines to install a printer YES in step S the process advances to step S and the driver control unit acquires acquisition site information from a driver information holding unit and installs an appropriate printer driver from the acquisition site. If the driver control unit determines not to install any printer NO in step S the process ends.

As described above according to the sixth embodiment when no appropriate printer driver is installed whether to install an appropriate printer driver is confirmed as confirmation information. The user can install an appropriate printer driver without recognizing its information.

Note that the present invention can be applied to an apparatus comprising a single device or to system constituted by a plurality of devices.

Furthermore the invention can be implemented by supplying a software program which implements the functions of the foregoing embodiments directly or indirectly to a system or apparatus reading the supplied program code with a computer of the system or apparatus and then executing the program code. In this case so long as the system or apparatus has the functions of the program the mode of implementation need not rely upon a program.

Accordingly since the functions of the present invention are implemented by computer the program code installed in the computer also implements the present invention. In other words the claims of the present invention also cover a computer program for the purpose of implementing the functions of the present invention.

In this case so long as the system or apparatus has the functions of the program the program may be executed in any form such as an object code a program executed by an interpreter or scrip data supplied to an operating system.

Example of storage media that can be used for supplying the program are a floppy disk a hard disk an optical disk a magneto optical disk a CD ROM a CD R a CD RW a magnetic tape a non volatile type memory card a ROM and a DVD DVD ROM and a DVD R .

As for the method of supplying the program a client computer can be connected to a website on the Internet using a browser of the client computer and the computer program of the present invention or an automatically installable compressed file of the program can be downloaded to a recording medium such as a hard disk. Further the program of the present invention can be supplied by dividing the program code constituting the program into a plurality of files and downloading the files from different websites. In other words a WWW World Wide Web server that downloads to multiple users the program files that implement the functions of the present invention by computer is also covered by the claims of the present invention.

It is also possible to encrypt and store the program of the present invention on a storage medium such as a CD ROM distribute the storage medium to users allow users who meet certain requirements to download decryption key information from a website via the Internet and allow these users to decrypt the encrypted program by using the key information whereby the program is installed in the user computer.

Besides the cases where the aforementioned functions according to the embodiments are implemented by executing the read program by computer an operating system or the like running on the computer may perform all or a part of the actual processing so that the functions of the foregoing embodiments can be implemented by this processing.

Furthermore after the program read from the storage medium is written to a function expansion board inserted into the computer or to a memory provided in a function expansion unit connected to the computer a CPU or the like mounted on the function expansion board or function expansion unit performs all or a part of the actual processing so that the functions of the foregoing embodiments can be implemented by this processing.

While the present invention has been described with reference to exemplary embodiments it is to be understood that the invention is not limited to the disclosed exemplary embodiments. The scope of the following claims is to be accorded the broadest interpretation so as to encompass all such modifications and equivalent structures and functions.

This application claims the benefit of Japanese Patent Application No. 2006 075545 filed on Mar. 17 2006 which is hereby incorporated by reference herein in its entirety.

