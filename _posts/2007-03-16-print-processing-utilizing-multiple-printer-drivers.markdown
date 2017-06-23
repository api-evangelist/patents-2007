---

title: Print processing utilizing multiple printer drivers
abstract: It is analyzed on the basis of received print data whether the print data is print data generated via a process path formed from a combination of the first application and first printer driver, or print data generated via a process path formed from a combination of the second application and second printer driver. Settings associated with the process of print data are made for each process path. The process of the received print data is controlled on the basis of the analysis result and setting contents.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08094332&OS=08094332&RS=08094332
owner: Canon Kabushiki Kaisha
number: 08094332
owner_city: Tokyo
owner_country: JP
publication_date: 20070316
---
The present invention relates to an image forming apparatus which receives print data and prints a control method therefor and a program.

An application on a host computer prints an image or text from a printing apparatus by generally using an arrangement as shown in .

More specifically an application on a host computer passes graphics data to a graphics engine . The graphics engine processes the graphics data and passes it to a printer driver . The printer driver generates print data e.g. PDL Page Description Language to a printer . The print data is stored in a spooler and then sent to the printer .

In particular the graphics engine converts the resolution of graphics data created by the application and processes graphics data by a simulation process or the like in accordance with the performance of the printer driver . The graphics engine allows the application and printer driver to operate independently of each other. The graphics engine is generally provided as part of an OS Operating System .

For example Microsoft held a hardware engineering conference WinHEC 2005 in Seattle U.S.A. in 2005. At this conference Microsoft announced that a new Microsoft OS Windows Vista supports two graphics engines GDI 202 and WPF 212 as shown in Advances in Windows Printing TWPR05001 WinHEC05.ppt . The WPF stands for Windows Presentation Foundation. 

A conventional Microsoft printing system utilizes a graphics engine GDI from an application using an API called a Win32API and creates print data from graphics data by a printer driver called from the GDI. This print process sequence is called a GDI print path.

The API stands for Application Programming Interface. The GDI stands for Graphic Device Interface. An application using the Win32API will be referred to as a Win32 application . A printer driver called from the GDI will be referred to as a GDI printer driver .

According to Windows Vista a new print process sequence called an XPS print path is added to the conventional GDI print path. The XPS print path is a print process sequence to convert XPS graphics data into print data by the printer driver using a graphics engine WPF from an application using a WinFxAPI.

The XPS stands for XML Paper Specification. An application using the WinFxAPI will be referred to as a WinFx application . A printer driver which processes XPS graphics data will be referred to as an XPS printer driver .

In Windows Vista applications are classified into two types the Win32 application and WinFx application . The OS supports the two graphics engines i.e. the GDI and WPF .

The Win32 application passes graphics data to the GDI whereas the WinFx application passes graphics data to the WPF . Printer drivers are classified into two types the GDI printer driver and XPS printer driver . The GDI printer driver receives graphics data from the GDI and changes it into print data for the printer . The XPS printer driver receives graphics data from the WPF and changes it into print data for the printer . Print data created by each printer driver is transmitted to the printer via the spooler .

These graphics engines i.e. GDI and WPF can cooperate with each other. With this cooperation the Win32 application can pass graphics data to the XPS printer driver and the WinFx application can pass graphics data to the GDI printer driver .

The cooperative mechanism of the two graphics engines in Windows Vista will be explained with reference to .

Print process sequence represents a conventional GDI print path. Rendering data passed from the Win32 application is stored as an EMF Enhanced Metafile spool file in the GDI . Then the GDI printer driver converts the EMF spool file into print data.

Print process sequence represents an XPS print path added in Windows Vista. Rendering data passed from the WinFx application is stored as an XPS spool file in the WPF . Then the XPS printer driver converts the XPS spool file into print data.

Print process sequence represents a print process sequence when the GDI printer driver prints graphics data from the WinFx application . Rendering data passed from the WinFx application is converted into EMF graphics data by an XPS GDI conversion module via the WPF and stored as the EMF spool file . Then the GDI printer driver converts the EMF spool file into print data.

Print process sequence represents a process sequence when the XPS printer driver prints graphics data from the Win32 application . Rendering data passed from the Win32 application is converted into XPS graphics data by a GDI XPS conversion module via the GDI and stored as the XPS spool file . Then the XPS printer driver converts the XPS spool file into print data.

In Windows Vista the four print process sequences are prepared. Either the GDI printer driver or XPS printer driver is prepared as a printer driver for a printer and can cope with print processes from both the Win32 application and WinFx application .

When giving attention to the XPS format itself the XPS format can have a security function which is a feature of the XPS format. For example an electronic signature can be added to XPS document data to detect tampering of the document data. The use of the electronic signature adding function proposes security solutions in cooperation with a printer.

For example a printing system in which a printer has the electronic signature verification function can be built. In this printing system the printer verifies an electronic signature added to a received XPS document and prints only when determining that no tampering of the document has occurred.

For example patent reference 1 proposes a technique of analyzing received print data by the printer to determine whether to actually print it. According to patent reference 1 the determination method adopts a criterion for judging whether a job attribute designated by print data is processible.

However the XPS and EMF formats are different. The print quality print function and print speed may degrade in a print process sequence in which graphics data conversion may occur like print process sequences and in .

In terms of the print quality for example graphics data containing a logical operation such as ROP Raster OPeration which is supported by the EMF format is not supported by the XPS format in print process sequence . Depending on specifications determined by Microsoft logical operation information may be omitted when the GDI XPS conversion module converts logical operation containing graphics data. When the XPS printer driver receives graphics data having no logical operation information it may not create an output result intended by the Win32 application .

To the contrary advanced graphics graphics data supported by the XPS format is not supported by the EMF format in print process sequence . The XPS GDI conversion module performs local bitmap Flattering when converting XPS graphics data into GDI one. In this case graphics data is converted into bitmap data and the GDI printer driver cannot determine the original object attribute failing to create any optimum output result.

In print process sequence or therefore a print result output from the printer may degrade in quality from what the user intends.

In terms of security for example electronic signature information supported by the XPS format is not supported by the EMF format in print process sequence . After an XPS document passes through print process sequence electronic signature information added to the document is lost and the printer must print by a conventional system. In this case printing by a malicious user by intentionally avoiding the security restriction may not be prevented.

The present invention has been made to overcome the conventional drawbacks and has as the first object to provide an image forming apparatus capable of preventing illicit printing or degradation of the print quality a control method therefor and a program.

It is the second object to provide an image forming apparatus capable of minimizing outputs at poor print quality a control method therefor and a program.

According to the present invention the foregoing object is attained by providing an image forming apparatus which prints by receiving print data generated by an information processing apparatus that operates a first graphics unit that generates first graphics data processible by a first printer driver in accordance with a print instruction from a first application and a second graphics unit that generates second graphics data processible by a second printer driver in accordance with a print instruction from a second application comprising 

analysis means for analyzing on the basis of the print data received by the receiving means whether the print data is print data generated via a process path formed from a combination of the first application and the first printer driver or print data generated via a process path formed from a combination of the second application and the second printer driver 

setting means for making a setting associated with a process of the print data for each process path and

control means for controlling the process of the print data received by the receiving means on the basis of an analysis result of the analysis means and setting contents of the setting means.

In a preferred embodiment the setting means includes an item to set whether to inhibit prevent printing of print data generated via a process path formed from a combination of the first application and the second printer driver or print data generated via a process path formed from a combination of the second application and the first printer driver and an item to set whether to notify a designated notification destination of information.

In a preferred embodiment the analysis means analyzes a combination of an application and a printer driver used to generate print data on the basis of information representing execution non execution of a graphics data conversion process and a driver type of a designated printer driver that are contained in the print data.

In a preferred embodiment the control means controls to inhibit printing of the print data when the combination is a specific combination as a result of the analysis by the analysis means and inhibition of printing when the combination is the specific combination is set as the setting contents of the setting means.

In a preferred embodiment the control means further comprises notification means for notifying the designated notification destination of information of a control result by the control means on the basis of the analysis result of the analysis means and the setting contents of the setting means.

In a preferred embodiment the notification means notifies the information processing apparatus of identification information representing a printer driver capable of generating print data printable by the image forming apparatus.

According to the present invention the foregoing object is attained by providing an image forming apparatus which prints by receiving print data generated by an information processing apparatus that operates a first graphics unit that generates first graphics data processible by a first printer driver in accordance with a print instruction from a first applications and a second graphics unit that generates second graphics data processible by a second printer driver in accordance with a print instruction from a second application comprising 

analysis means for analyzing on the basis of the print data received by the receiving means whether the print data is print data generated via a process path formed from a combination of the first application and the first printer driver or print data generated via a process path formed from a combination of the second application and the second printer driver and

control means for controlling to inhibit printing of the print data received by the receiving means when the analysis means analyzes that the print data was generated via neither the process path formed from the combination of the first application and the first printer driver nor the process path formed from the combination of the second application and the second printer driver.

According to the present invention the foregoing object is attained by providing an image forming apparatus which prints by receiving print data generated by an information processing apparatus that operates a first graphics unit that generates first graphics data processible by a first printer driver in accordance with a print instruction from a first application and a second graphics unit that generates second graphics data processible by a second printer driver in accordance with a print instruction from a second application comprising 

analysis means for analyzing on the basis of the print data received by the receiving means whether the print data is print data generated via a process path which is formed from a combination of the first application and the second printer driver and accompanied by graphics conversion or print data generated via a process path which is formed from a combination of the second application and the first printer driver and accompanied by graphics conversion 

specifying means for specifying a type of printer driver not accompanied by graphics conversion when the analysis means analyzes that the print data was generated via the process path which is formed from the combination of the first application and the second printer driver and accompanied by graphics conversion or via the process path which is formed from the combination of the second application and the first printer driver and accompanied by graphics conversion and

notification means for notifying the information processing apparatus of device information containing the type of printer driver specified by the specifying means.

In a preferred embodiment the specifying means specifies the first printer driver when the analysis means analyzes that the print data was not generated via a process path formed from a combination of the first application and the first printer driver and

the specifying means specifies the second printer driver when the analysis means analyzes that the print data was not generated via a process path formed from a combination of the second application and the second printer driver.

In a preferred embodiment the specifying means executes a printer driver specifying process when a device search message is received from the information processing apparatus and

the notification means notifies the device information to a message transmitting side indicated by message transmitting side information contained in the device search message.

According to the present invention the foregoing object is attained by providing an image forming apparatus which prints by receiving print data generated by an information processing apparatus that operates a first graphics unit that generates first graphics data processible by a first printer driver in accordance with a print instruction from a first application and a second graphics unit that generates second graphics data processible by a second printer driver in accordance with a print instruction from a second application comprising 

analysis means for analyzing on the basis of the print data received by the receiving means whether a process path is to convert the second graphics data into the first graphics data and output the first graphics data to the second printer driver and

control means for controlling to inhibit printing of the print data received by the receiving means when the analysis means analyzes that the print data was generated via the process path to convert the second graphics data into the first graphics data and output the first graphics data to the first printer driver.

According to the present invention the foregoing object is attained by providing a method of controlling an image forming apparatus which prints by receiving print data generated by an information processing apparatus that operates a first graphics unit that generates first graphics data processible by a first printer driver in accordance with a print instruction from a first application and a second graphics unit that generates second graphics data processible by a second printer driver in accordance with a print instruction from a second application comprising 

an analysis step of analyzing on the basis of the print data received in the receiving step whether the print data is print data generated via a process path formed from a combination of the first application and the first printer driver or print data generated via a process path formed from a combination of the second application and the second printer driver 

a setting step of making a setting associated with a process of the print data for each process path and

a control step of controlling the process of the print data received in the receiving step on the basis of an analysis result of the analysis step and setting contents of the setting step.

According to the present invention the foregoing object is attained by providing a method of controlling an image forming apparatus which prints by receiving print data generated by an information processing apparatus that operates a first graphics unit that generates first graphics data processible by a first printer driver in accordance with a print instruction from a first application and a second graphics unit that generates second graphics data processible by a second printer driver in accordance with a print instruction from a second application comprising 

an analysis step of analyzing on the basis of the print data received in the receiving step whether the print data is print data generated via a process path formed from a combination of the first application and the first printer driver or print data generated via a process path formed from a combination of the second application and the second printer driver and

a control step of controlling to inhibit printing of the print data received in the receiving step when the print data is analyzed in the analysis step to have been generated via neither the process path formed from the combination of the first application and the first printer driver nor the process path formed from the combination of the second application and the second printer driver.

According to the present invention the foregoing object is attained by providing a method of controlling an image forming apparatus which prints by receiving print data generated by an information processing apparatus that operates a first graphics unit that generates first graphics data processible by a first printer driver in accordance with a print instruction from a first application and a second graphics unit that generates second graphics data processible by a second printer driver in accordance with a print instruction from a second application comprising 

an analysis step of analyzing on the basis of the print data received in the receiving step whether the print data is print data generated via a process path which is formed from a combination of the first application and the second printer driver and accompanied by graphics conversion or print data generated via a process path which is formed from a combination of the second application and the first printer driver and accompanied by graphics conversion 

a specifying step of specifying a type of printer driver not accompanied by graphics conversion when the print data is analyzed in the analysis step to have been generated via the process path which is formed from the combination of the first application and the second printer driver and accompanied by graphics conversion or via the process path which is formed from the combination of the second application and the first printer driver and accompanied by graphics conversion and

a notification step of notifying the information processing apparatus of device information containing the type of printer driver specified in the specifying step.

According to the present invention the foregoing object is attained by providing a method of controlling an image forming apparatus which prints by receiving print data generated by an information processing apparatus that operates a first graphics unit that generates first graphics data processible by a first printer driver in accordance with a print instruction from a first application and a second graphics unit that generates second graphics data processible by a second printer driver in accordance with a print instruction from a second applications comprising 

an analysis step of analyzing on the basis of the print data received in the receiving step whether a process path is to convert the second graphics data into the first graphics data and output the first graphics data to the first printer driver and

a control step of controlling to inhibit printing of the print data received in the receiving step when the print data is analyzed in the analysis step to have been generated via the process path to convert the second graphics data into the first graphics data and output the first graphics data to the first printer driver.

According to the present invention the foregoing object is attained by providing a program which causes a computer to control an image forming apparatus which prints by receiving print data generated by an information processing apparatus that operates a first graphics unit that generates first graphics data processible by a first printer driver in accordance with a print instruction from a first application and a second graphics unit that generates second graphics data processible by a second printer driver in accordance with a print instruction from a second application by causing the computer to execute

an analysis step of analyzing on the basis of the print data received in the receiving step whether the print data is print data generated via a process path formed from a combination of the first application and the first printer driver or print data generated via a process path formed from a combination of the second application and the second printer driver 

a setting step of making a setting associated with a process of the print data for each process path and

a control step of controlling the process of the print data received in the receiving step on the basis of an analysis result of the analysis step and setting contents of the setting step.

According to the present invention the foregoing object is attained by providing a program which is stored in a computer readable medium and causes a computer to control an image forming apparatus which prints by receiving print data generated by an information processing apparatus that operates a first graphics unit that generates first graphics data processible by a first printer driver in accordance with a print instruction from a first application and a second graphics unit that generates second graphics data processible by a second printer driver in accordance with a print instruction from a second application by causing the computer to execute

an analysis step of analyzing on the basis of the print data received in the receiving step whether the print data is print data generated via a process path formed from a combination of the first application and the first printer driver or print data generated via a process path formed from a combination of the second application and the second printer driver and

a control step of controlling to inhibit printing of the print data received in the receiving step when the print data is analyzed in the analysis step to have been generated via neither the process path formed from the combination of the first application and the first printer driver nor the process path formed from the combination of the second application and the second printer driver.

According to the present invention the foregoing object is attained by providing a program which is stored in a computer readable medium and causes a computer to control an image forming apparatus which prints by receiving print data generated by an information processing apparatus that operates a first graphics unit that generates first graphics data processible by a first printer driver in accordance with a print instruction from a first application and a second graphics unit that generates second graphics data processible by a second printer driver in accordance with a print instruction from a second application by causing the computer to execute

an analysis step of analyzing on the basis of the print data received in the receiving step whether the print data is print data generated via a process path which is formed from a combination of the first application and the second printer driver and accompanied by graphics conversion or print data generated via a process path which is formed from a combination of the second application and the first printer driver and accompanied by graphics conversion 

a specifying step of specifying a type of printer driver not accompanied by graphics conversion when the print data is analyzed in the analysis step to have been generated via the process path which is formed from the combination of the first application and the second printer driver and accompanied by graphics conversion or via the process path which is formed from the combination of the second application and the first printer driver and accompanied by graphics conversion and

a notification step of notifying the information processing apparatus of device information containing the type of printer driver specified in the specifying step.

According to the present invention the foregoing object is attained by providing a program which is stored in a computer readable medium and causes a computer to control an image forming apparatus which prints by receiving print data generated by an information processing apparatus that operates a first graphics unit that generates first graphics data processible by a first printer driver in accordance with a print instruction from a first application and a second graphics unit that generates second graphics data processible by a second printer driver in accordance with a print instruction from a second application comprising 

an analysis step of analyzing on the basis of the print data received in the receiving step whether a process path is to convert the second graphics data into the first graphics data and output the first graphics data to the first printer driver and

a control step of controlling to inhibit printing of the print data received in the receiving step when the print data is analyzed in the analysis step to have been generated via the process path to convert the second graphics data into the first graphics data and output the first graphics data to the first printer driver.

Further features of the present invention will be apparent from the following description of exemplary embodiments with reference to the attached drawings.

A preferred embodiment of the present invention will now be described in detail with reference to the drawings. It should be noted that the relative arrangement of the components the numerical expressions and numerical values set forth in the embodiment do not limit the scope of the present invention unless it is specifically stated otherwise.

Print process sequence represents a conventional GDI print path. Rendering data passed from a Win32 application is stored as an EMF spool file in a GDI . Then a GDI printer driver converts the EMF spool file into print data.

Print process sequence represents an XPS print path added in Windows Vista. Rendering data passed from a WinFx application is stored as an XPS spool file in a WPF . Then an XPS printer driver converts the XPS spool file into print data.

Print process sequence represents a print process sequence when the GDI printer driver prints graphics data from the WinFx application . Rendering data passed from the WinFx application is converted into EMF graphics data by an XPS GDI conversion module via the WPF and stored as the EMF spool file . Then the GDI printer driver converts the EMF spool file into print data.

Print process sequence represents a process sequence when the XPS printer driver prints graphics data from the Win32 application . Rendering data passed from the Win32 application is converted into XPS graphics data by a GDI XPS conversion module via the GDI and stored as the XPS spool file . Then the XPS printer driver converts the XPS spool file into print data.

In Windows Vista the four print process sequences are prepared. Either the GDI printer driver or XPS printer driver is prepared as a printer driver for a printer and can cope with print processes from both the Win32 application and WinFx application .

In an information processing apparatus comprises the Win32 application serving as the first application and the GDI printer driver serving as the first printer driver. The information processing apparatus also comprises the WinFx application serving as the second application and the XPS printer driver serving as the second printer driver.

The two graphics engines i.e. the GDI serving as the first graphics unit and the WPF serving as the second graphics unit exist on the OS. The Win32 application passes a GDI function serving as the first graphics data to the GDI while the WinFx application passes WPF API data serving as the second graphics data to the WPF .

The GDI printer driver receives graphics data from the GDI and converts it into print data for a printer . The XPS printer driver receives graphics data from the WPF and converts it into print data for the printer . Print data created by the printer driver is transmitted to the printer via a spooler .

In the embodiment print process paths and accompanied by graphics conversion using the conversion module are generically called a cross path. On the contrary print process paths and not accompanied by graphics conversion using the conversion module are generically called a straight path.

The present invention is applicable to a system having the functions of a single device or formed from a plurality of devices as far as the system can execute the functions of the present invention unless otherwise specified. The present invention is also applicable to a system which is connected via a network such as a LAN or WAN to perform processes.

In reference numeral denotes a host computer having a CPU . The CPU processes a document of building elements such as a figure image text table including a spreadsheet and the like and the like on the basis of a program such as a document processing program application program stored in a program ROM of a ROM or an external memory . The CPU comprehensively controls each device connected to a system bus in a host computer main body .

The program ROM of the ROM or the external memory stores programs such as an operating system program to be referred to as an OS hereinafter which is a control program for the CPU . A font ROM of the ROM or the external memory stores data such as font data used in the document process. A data ROM of the ROM or the external memory stores various data used to perform various processes such as the document process.

Reference numeral denotes a RAM functioning as a main memory work area and the like for the CPU . Reference numeral denotes a keyboard controller KBC which controls a key input from a keyboard KB or a pointing device not shown . Reference numeral denotes a CRT controller CRTC which controls display on a CRT display CRT . An LCD controller and LCD are also available instead of the CRT controller and CRT display .

Reference numeral denotes a disk controller DKC which controls access to the external memory for a boot program various applications font data user files edit files and the like. The DKC also controls access to the external memory e.g. a hard disk HD or floppy disk FD which stores various data such as a print control command generation program to be referred to as a printer driver hereinafter .

Reference numeral denotes a printer controller PRTC which connects to the printer via a predetermined bidirectional interface and executes a communication control process with the printer . Examples of the bidirectional interface are a USE interface IEEE1394 interface and wireless LAN interface.

The CPU enables WYSIWYG on the CRT by expanding rasterizing an outline font in a display information RAM set in e.g. the RAM to provide a GUI. The CPU opens various registered windows and executes various data processes on the basis of commands designated with the mouse cursor not shown or the like on the CRT . In printing the user opens a window associated with print settings and sets the printer and a printing method to the printer driver including selection of the print mode.

In the printer reference numeral denotes a printer CPU. The printer CPU comprehensively controls each device connected to a system bus in a printer control unit . The printer CPU outputs an image signal serving as output information to a printing unit printer engine connected to the system bus on the basis of a program such as a control program stored in a program ROM of a ROM or an external memory .

The program ROM of the ROM stores programs such as a control program for the printer CPU . A font ROM of the ROM stores data such as font data used to generate the output information. When the printer does not comprise any external memory such as a hard disk HD or IC card a data ROM of the ROM stores information or the like used in the host computer .

The printer CPU can communicate with the host computer via an input unit and can notify the host computer of various types of information such as status information in the printer . Reference numeral denotes a RAM functioning as a main memory work area and the like for the CPU . The RAM can increase its memory capacity by an optional RAM connected to an expansion port not shown .

The RAM is used as an output information expansion area environment data storage area NVRAM and the like. A disk controller DKC controls access to the external memory . The external memory is connected as an option and stores data such as font data an emulation program and form data. Reference numeral denotes an operation unit having an operation panel switch LED display and the like for various operations to the printer .

The number of external memories is not limited to one and is at least one. It is possible to connect a plurality of optional font cards and a plurality of external memories which store a program for interpreting printer control languages of different language systems in addition to a built in font. The external memory may have an NVRAM not shown to store printer mode setting information from the operation unit .

The printer connects to one or more PDL devices PDL boards to control the PDL device from the CPU . The PDL device is an image forming unit having a function of interpreting print data PDL received from the host computer and converting it into bitmap data printable by the printing unit . One or more PDL devices are connected as a standard and a PDL device can also be added later. The PDL device holds IEEE1284 device information used in plug and play.

The information processing apparatus according to the embodiment can generate print data print job interpretable by the printer via the printer driver.

In general the printer comprises PDL as a standard PDL device and can be expanded by adding another type of PDL such as PDL as an optional PDL device.

This expansion may be achieved by physically connecting a dedicated PDL device mounted expansion board to the printer . If the PDL device is implemented by a program a program corresponding to the program ROM may be added. It is also possible to store programs corresponding to a plurality of types of PDL devices in the program ROM and validate and add a necessary PDL device with a license key input by a user operation.

The printer applied to the embodiment includes various printing types of printing apparatuses image forming apparatuses such as a laser beam printer and inkjet printer. The printer may be an MFP Multi Function Peripheral having a plurality of functions.

The MFP incorporates a storage such as a hard disk capable of storing a plurality of jobs. The MFP has a copy function which allows the printer unit via the storage to print a job output from the scanner unit. The MFP also has a print function which allows the printer unit via the storage to print a job output from an external apparatus such as a PC Personal Computer . In this manner the MFP has a plurality of functions including the above ones.

MFPs are classified into full color MFPs and monochrome MFPs. In many cases the full color MFP includes the arrangement of the monochrome MFP at the basic part except for a color processing function internal data and the like. The embodiment will explain mainly the full color MFP and a description of the monochrome MFP will be added as needed.

The system described in the embodiment may comprise a multifunction type image forming apparatus printing apparatus having a plurality of functions or an SFP which is a single function type image forming apparatus printing apparatus having only the print function. In any case the system is configured to implement control according to the embodiment.

A job receiving unit receives a print job from the host computer and transmits it to a job analysis unit . The job analysis unit analyzes the print job to identify a print process sequence print job generation path by which the print job was generated according to an identification method to be described later. The print job is synonymous with print data.

The print job processing method is determined in accordance with the process result of the job analysis unit and a mode set by a mode setting unit . To print the print job the print job is transmitted to a printing unit and printed. A job deletion unit cancels the print job in accordance with the process result of the job analysis unit . A notification unit gives a notification to the host computer in accordance with the process result of the job analysis unit .

An example of a data process between the host computer and the printer according to the embodiment will be described with reference to .

As described above there are two print paths along which the WinFx application passes data to the printer via the GDI printer driver or XPS printer driver .

On the print path via the XPS printer driver the XPS printer driver processes electronic signature information added graphics data . Electronic signature information is transmitted to the printer together with PDL data converted by the XPS printer driver . The format at this time will be described later.

On the print path via the GDI printer driver electronic signature information is lost during conversion into GDI by the XPS GDI conversion module generating graphics data having no electronic signature information. The GDI printer driver processes the graphics data having no electronic signature information. The graphics data is converted into PDL data having no electronic signature information which is transmitted to the printer .

The embodiment provides the security function of adaptively controlling inhibition execution of the print process in a printing environment where electronic signature information may be lost.

To implement the security function the embodiment adopts the mode setting unit which sets inhibition execution of the print process on the basis of a path on which a print job created in the host computer is generated. A mode setting window generated by the mode setting unit will be explained with reference to .

Each setting item has buttons to switch between ON and OFF. If the administrator selects either button the button changes into black representing the selected state.

Reference numeral denotes a button to switch between validation and invalidation of the security setting. When the button is OFF buttons to are grayed out to inhibit setting to each item and invalidate all settings.

The button is used to set whether to inhibit printing via the GDI. When the button is ON print jobs processed by print process sequences and are canceled to inhibit printing. When the button is ON but the button is ON a print job processed by print process sequence is printed. That is when the button is ON printing of a print job from the Win32 application is permitted.

Print data generated via the print path of print process sequence in is printed whereas print data generated via the print path of print process sequence in is not printed. It is also possible to inhibit printing of print data generated via the print paths of print process sequences and in by arranging an inhibit printing via the cross path button in the setting window in .

In this manner the printer according to the embodiment can make settings for the process of print data on each print process path. For example the window in can comprise an item to set whether to inhibit printing of print data generated via process path formed from a combination of the Win32 application and XPS driver or process path formed from a combination of the WinFx application and GDI driver.

The button is used to when receiving a print job via the GDI set whether to notify the administrator of the reception by mail. Assume that the administrator s mail address serving as a notification destination has already been set in another window for setting administrator information.

The button is used to when receiving a print job via the GDI set whether to notify the administrator of the reception. The notification is unicasted to the IP address of a host computer which transmitted the print job which will be described later.

The notification methods with the buttons and are merely examples. It is also possible to notify a host computer designated by a message dialog or output the contents of a notification to a designated printer.

If the administrator operates an OK button in this state the setting state mode setting information in is stored in e.g. the RAM and the display of the mode setting window disappears. If the administrator operates a cancel button the setting state in is canceled and the display of the mode setting window disappears.

Setting items in the mode setting window shown in are merely examples and various setting items can be provided in accordance with the application purpose. The main purpose of the embodiment is to avoid or inhibit a situation in which a print error or illicit printing may occur depending on a print process sequence for use when there are a plurality of types of print process sequences to generate print data. Various setting items can be provided as long as they can achieve this purpose.

In step S the job receiving unit receives a print job. In step S the job analysis unit analyzes the print job to identify a path print process sequence print job generation path on which the print job was generated. The job generation path identification method will be described with reference to . In step S the mode setting unit refers to mode setting information in the RAM to determine whether the setting value of the button is ON as the security setting.

If the security setting is OFF NO in step S the process advances to step S to print the print job and then ends. If the security setting is ON YES in step S the process advances to step S and the job analysis unit determines whether the print job generation path is print process sequence .

If the print job generation path is print process sequence YES in step S the printer executes a subroutine SR to be described later. In step S the mode setting unit refers to mode setting information in the RAM to determine whether the setting value of the button is ON as the security setting inhibition of printing via the GDI .

If inhibition of printing via the GDI is ON YES in step S the process advances to step S the printing unit cancels the print job and then the process ends. If inhibition of printing via the GDI is OFF NO in step S the process advances to step S the printing unit prints the print job and then the process ends.

If the print job generation path is not print process sequence in step S NO in step S the process advances to step S and the job analysis unit determines whether the print job generation path is print process sequence .

If the print job generation path is print process sequence YES in step S the printer executes the subroutine SR to be described later. In step S the mode setting unit refers to mode setting information in the RAM to determine whether the setting value of the button is ON as the security setting permission of printing from the Win32 application .

If permission of printing from the Win32 application is OFF NO in step S the process advances to step S the printer cancels the print job and then the process ends. If permission of printing from the Win32 application is ON YES in step S the printing unit prints the print job and the process ends. In this fashion the printer controls the process of received print data on the basis of the analysis result in step S and the setting contents of .

By the process in the CPU of the printer controls to inhibit printing of print data when the analysis result in step S reveals that a combination of an application and printer driver is a specific one and it is set to inhibit printing in the case of this specific combination. Accordingly the printer can prevent degradation of confidentiality print quality and the like.

In step S the mode setting unit refers to mode setting information in the RAM to determine whether the setting value of the button is ON as the security setting administrator notification .

If the administrator notification is OFF NO in step S the process advances to step S. If the administrator notification is ON YES in step S the process advances to step S and the notification unit acquires a preset administrator s mail address. In step S the notification unit sends mail to the acquired administrator s mail address. After that the process advances to step S. shows an example of the mail.

Assume that the user generates data with electronic signature information by the WinFx application. When the user selects the GDI printer driver via the WinFx application the electronic signature added to the data generated by the WinFx application is deleted losing security.

When the printer analyzes that the received print data was generated by print process sequence it determines that electronic signature information may be omitted as described above. To notify the administrator that the print data was generated using an undesirable printer driver the printer generates mail as shown in and sends it to the administrator.

In step S the mode setting unit refers to mode setting information in the RAM to determine whether the setting value of the button is ON as the security setting user notification .

If the setting value of the button is OFF user notification is OFF NO in step S the process ends. If the setting value of the button is ON user notification is ON YES in step S the process advances to step and the notification unit unicasts a notification message to the host computer which transmitted the print job. Then the process ends.

The printer sends the notification message in upon reception of a print job from the host computer via the GDI while the setting values of the buttons and are ON as security settings. In response to this for example the GDI printer driver in the host computer is uninstalled to inhibit subsequent printing from being executed via the GDI.

In the host computer transmits a device information request to the printer . Upon reception of the device information request the printer generates device information in by a method to be described later and transmits the generated device information to the host computer in .

In the host computer designates a necessary service ID from the received device information and transmits a service information request. Upon reception of the service information request the printer transmits service information containing the value of IEEE1284 device information corresponding to the designated service ID to the host computer in . shows an example of the service information.

If the printer transmits device information containing a plurality of service lists to the host computer in the sequence of and is repeated.

In the host computer refers to the service information received from the printer and uninstalls a printer driver corresponding to DeviceID which has not been sent back from the printer.

A process when the printer which has received a device information request generates device information in of will be explained with reference to .

In step S the printer receives a device information request. In step S the printer acquires one printable PDL from a PDL list of PDL devices supported by the printer. In step S the printer adds to device information a service entry corresponding to a service with DeviceID for the XPS driver corresponding to the acquired PDL device. That is in step S the printer adds information that the XPS printer driver corresponding to the acquired PDL is valid.

In step S the printer refers to mode setting information in the RAM and acquires the setting values of the buttons and as security settings to determine whether GDI printing is acceptable. If no GDI printing is acceptable NO in step S the process advances to step S.

If GDI printing is acceptable YES in step S the process advances to step S to add to the device information a service entry corresponding to a service with DeviceID for the GDI driver corresponding to the acquired PDL. That is in step S the printer adds to the device information information that the GDI printer driver corresponding to the acquired PDL is valid.

In step S the printer determines whether the process has ended for all PDL devices in the PDL list. If the process has not ended for all PDL devices NO in step S the process returns to step S to acquire an unprocessed PDL device and execute the above described process. If the process has ended for all PDL devices YES in step S the process advances to step S to transmit the generated device information to the host computer and then ends.

By the above process the printer can designate a printer driver which generates print data processible by the printer . For example if the printer determines in step S that GDI printing is impossible NO in step S no GDI printer driver is added as a valid printer driver to device information.

Upon reception of this device information the host computer can determine not to generate any print data via the GDI printer driver because the device information does not contain any GDI printer driver. This can prevent transmission to the printer of print data from which electronic signature information added to data generated by e.g. the WinFx application is deleted.

In other words the host computer can control the printer driver in accordance with device information sent from the device. For example the host computer can specify a printer driver not contained in the received device information among printer drivers held in the host computer and uninstall the specified printer driver. The printer can notify the host computer of identification information representing a printer driver capable of generating printable data.

A process when the printer recommends a desirable printer driver using the process in upon reception of print data generated via the cross pass will be explained with reference to . In this case the uninstallation process shown in may not be executed.

The printer determines whether it has received print data step S . If the printer has received print data YES in step S it determines whether the print data was generated via the cross path step S . The method of analyzing whether print data was generated via the cross path will be described later with reference to .

If the job analysis unit determines upon analysis in step S that the print data was generated via the cross path YES in step S it specifies the type of printer driver capable of generating print data without any conversion by the graphics module step S . Specifically the job analysis unit can determine the type of print requesting application by using the process in .

More specifically the job analysis unit determines whether the requesting application is the WinFx application or Win32 application. Based on this result the printer specifies the type of printer driver not accompanied by graphics conversion. When the print requesting source is the WinFx application the printer specifies the XPS printer driver. When the print requesting source is the Win32 application the printer specifies the GDI printer driver.

The printer creates device information containing the printer driver specified in step S step S . The printer transmits the device information to the host computer step S .

The process in step S will be exemplified. For example when printer A determines that GDI printer driver A generated print data via the cross path it specifies XPS printer driver A as a desirable printer driver. Printer A transmits device information containing specified XPS printer driver A to the host computer so the user can switch the printer driver to a desirable one recommended by the printer. This can prevent degradation of the print quality or illicit printing as much as possible.

The printer notifies the device information created in step S to a transmitting side indicated by the message transmitting side information contained in a device search message in .

The method of identifying a path on which a print job was generated when the printer receives the print job will be explained.

Before a description of this identification method the arrangement of the XPS printer driver will be described with reference to .

In the environment shown in print setting data is held with a data structure called a DEVMODE structure on the GDI print path. Print setting data is held with an XML data structure called PrintTicket on the XPS print path. Conversion from GDI into XPS or from XPS into GDI requires conversion from DEVMODE into PrintTicket or from PrintTicket into DEVMODE.

Similar to graphics data the DEVMODE expressible range and PrintTicket expressible range are different from each other. This process is done not automatically by the operating system but by the printer driver itself using an extended architecture.

The XPS printer driver holds a print ticket provider and UI driver module XPS . The UI driver module XPS is based on DEVMODE and displays a UI for setting print setting information in response to a call from an application. The print ticket provider converts PrintTicket print ticket into DEVMODE or DEVMODE into PrintTicket.

In when the Win32 application requests DEVMODE for print settings the XPS printer driver is based on DEVMODE and does not require any conversion. If the Win32 application prints using the XPS printer driver the print ticket provider need not perform any conversion.

To the contrary the WinFx application requests a print ticket for print settings. The XPS printer driver does not hold any print ticket and the print ticket provider converts the print ticket into DEVMODE.

The XPS printer driver can recognize the conversion process of the print ticket provider . If the print ticket provider converts a print ticket into DEVMODE upon accepting data to be printed the XPS printer driver can determine that the print setting requesting source is the WinFx application . If the print ticket provider does not execute any conversion upon accepting data to be printed the XPS printer driver can determine that the print setting requesting source is the Win32 application .

The GDI printer driver is identical in structure to the XPS printer driver and comprises a UI driver module GDI equivalent to the UI driver module XPS 

The GDI printer driver can recognize the conversion process of the print ticket provider similar to the XPS printer driver . The GDI printer driver can determine the process path of data to be printed and a print setting requesting application.

In graphics data in a print job passed from the WinFx application to the GDI printer driver is automatically converted by the XPS GDI conversion module under the control of the OS . Thus the GDI printer driver cannot detect that the graphics data has been converted.

On the contrary print setting data of a stapling process or the like cannot be automatically converted by the OS . Instead the UI driver module of the XPS printer driver converts PrintTicket passed from the WinFx application into DEVMODE interpretable by the GDI printer driver .

When automatically converting graphics data the OS passes PrintTicket to the UT driver module of the GDI printer driver in order to ask the GDI printer driver to convert print settings. After acquiring PrintTicket from the OS the UI driver module converts the received XML PrintTicket information into DEVMODE. At this time the UI driver module sets in DEVMODE a conversion flag representing that the XPS GDI conversion module has executed conversion.

Reference numeral denotes PrintTicket passed from the OS to the UI driver module of the XPS printer driver . The PrintTicket is expressed in the XML format and holds information on print settings such as the paper size and execution non execution of double sided printing.

Information converted from the PrintTicket is DEVMODE . The DEVMODE holds print settings used by the GDI printer driver and shows the paper size execution non execution of double sided printing and the like similar to the PrintTicket .

The conversion flag of the XPS GDI conversion module is dmConvertFlag . By designating DM CNV PTTODEVMODE in conversion by the GDI printer driver the print ticket provider records that XPS GDI conversion has been executed. DM CNV NONE is designated for DEVMODE having undergone no XPS GDI conversion.

The format of print data generated from DEVMODE and graphics data by the GDI printer driver will be described with reference to .

Print data is made up of a job print setting part and graphics data part . The job print setting part contains information on print settings such as the number of copies and double sided printing and in addition a conversion flag representing execution non execution of XPS GDI conversion and information on the driver type GDI or XPS of print data. The printer analyzes print data e.g. PDL data to extract the conversion flag and driver type information determining a print process sequence print job generation path by which the print job was generated.

When the GDI printer driver determines that conversion from the print ticket into DEVMODE has been executed it can determine that the print requesting source is the WinFx application. Hence the GDI printer driver generates print data describing that XPS GDI conversion has been executed and the driver type is GDI as shown in . If the GDI printer driver determines that no conversion from the print ticket into DEVMODE has been executed it can determine that the print requesting source is the Win32 application. In this case the GDI printer driver generates print data describing that no XPS GDI conversion has been executed and the driver type is GDI.

When receiving a print request from the WinFx application the XPS printer driver can print normally without degrading either the print function or graphics result as described above. When the XPS printer driver determines that conversion from the print ticket into DEVMODE has been executed it can determine that the print requesting source is the WinFx application as described with reference to .

In this case the XPS printer driver generates print data describing that no GDI XPS conversion has been executed and the driver type is XPS. If the XPS printer driver determines that no conversion from the print ticket into DEVMODE has been executed it can determine that the print requesting source is the Win32 application. In this case the XPS printer driver generates print data describing that print data has undergone GDI XPS conversion and the driver type is XPS.

In this way print data received by the printer contains information representing execution non execution of the graphics data conversion process and the driver type of a designated printer driver. Based on the received print data the job analysis unit analyzes the combination of an application and printer driver used to generate the print data.

In particular the process to determine the job generation path print process sequence of a received print job by the printer will be described.

In step S the job analysis unit identifies a driver type contained in the job print setting part of print data. As shown in the print data received by the printer describes the driver type. If the driver type is XPS the process advances to step S.

In step S the job analysis unit determines whether the conversion flag is set. If the conversion flag is set YES in step S i.e. the job analysis unit determines that GDI XPS conversion has been executed the process advances to step S to determine that the print process sequence is . If no conversion flag is set NO in step S the process advances to step S to determine that the print process sequence is .

If the driver type is GDI the process advances to step S and the job analysis unit determines whether the conversion flag is set. If the conversion flag is set YES in step S i.e. the job analysis unit determines that XPS GDI conversion has been executed the process advances to step S to determine that the print process sequence is .

If no conversion flag is set NO in step the process advances to step S to determine that the print process sequence is . In this manner the printer can determine a print process requesting application on the basis of the driver type and graphics data conversion flag which are contained in print data. As a result of the specifying process the printer controls to inhibit print data when analyzing that the print data was not generated via the straight path.

The embodiment has exemplified the security setting using electronic signature information as information which is omitted by XPS GDI conversion. With the same arrangement the present invention can cope with even the problem of the print quality in addition to the print restriction for security.

As described above according to the present invention the printer can adaptively change the process contents by identifying information on a path on which a print job was generated. For example when printing via the GDI is inhibited the button is ON in and printing from the Win32 application is permitted the button is ON the printer cancels inhibits the print process upon determining that the print process sequence is .

When the security setting is valid the button is ON in and both the buttons and are ON the printer may cancel the print process via print process sequence . In this case if the job analysis unit analyzes received print data to determine that the driver type is XPS and GDI XPS conversion has been executed it can determine that the print process sequence is canceling the print process.

Based on received print data the printer can analyze whether the print data was generated via a process path formed from a combination of the Win32 application and GDI printer driver. Also based on received print data the printer can analyze whether the print data was generated via a process path formed from a combination of the WinFx application and XPS printer driver.

The printer can inhibit printing of a print job which may not ensure security or a print job which may degrade the print quality. Accordingly the embodiment can provide a printing system which prevents any attempt to avoid the security restriction and print and prevents a situation in which results do not meet a user s request due to poor print quality to wastefully use sheets.

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

This application claims the benefit of Japanese Patent Application No. 2006 75550 filed on Mar. 17 2006 which is hereby incorporated by reference herein in its entirety.

