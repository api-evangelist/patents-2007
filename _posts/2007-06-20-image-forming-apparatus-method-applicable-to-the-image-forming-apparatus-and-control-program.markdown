---

title: Image forming apparatus, method applicable to the image forming apparatus, and control program
abstract: A method for controlling an image forming apparatus includes: storing data in which pages are defined; specifying insertion data to be inserted into the data; providing instructions to insert the insertion data specified at a specific page of the data stored; determining whether the insertion data specified has been input by using the input device specified by the specifying unit; and inserting the input insertion data at the specific page indicated if it is determined that the insertion data specified has been input.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08634101&OS=08634101&RS=08634101
owner: Canon Kabushiki Kaisha
number: 08634101
owner_city: Tokyo
owner_country: JP
publication_date: 20070620
---
The present invention relates to an image forming apparatus having a function of a multifunction apparatus including a printer a scanner a facsimile and a copy machine and also relates to a method for controlling the image forming apparatus and a control program.

There have conventionally been programs that are executable in an image forming apparatus having a function of a multifunction apparatus including a printer a scanner a facsimile and a copy machine. In such an apparatus a program is selected on a touch panel of a display unit and a user operation required by the program is input on the touch panel. Also the program is executed by allowing the user to operate the program through a numeric keypad e.g. see Japanese Patent Laid Open No. 2003 330671 .

On the other hand there has been a binding application to perform imposition of arranging a layout in a page and to instruct a finisher to fold and staple printed sheets e.g. see Japanese Patent Laid Open No. 2004 185489 .

In the above described known arts however when a user wants to insert a document image captured by a scanner of a multifunction apparatus into a document the user needs to store the document image in a hard disk of the multifunction apparatus and make a file of the document image. Furthermore the user needs to insert the file into a desirable part of the document by using a binding application provided in the multifunction apparatus. These operations cause a burden for the user. This is the same for another function of the multifunction apparatus for example inserting a document input by facsimile and inserting a document in the hard disk in the multifunction apparatus transmitted from a PC personal computer connected to a network.

For example assume a case where a document is transferred from the PC connected to the network to the hard disk in the multifunction apparatus and the document is bound and printed by the binding application in the multifunction apparatus. In this case when the document to be created includes a report and data transmitted from someone an entire process including transfer instruction of binding and printing needs to be performed after transmission from the person completes. This is also a burden for the user. These problems are not limited to the binding application.

According to an embodiment of the present invention there is provided a method for controlling an image forming apparatus. The method includes storing data in which pages are defined specifying insertion data to be inserted into the data and an input device providing instructions to insert the insertion data specified at a specific page of the data stored determining whether the insertion data specified has been input by using the input device specified by the specifying unit and inserting the input insertion data at the specific page indicated if it is determined that the insertion data specified has been input.

Other features and advantages of the present invention will be apparent from the following description taken in conjunction with the accompanying drawings in which like reference characters designate the same or similar parts throughout thereof.

An aspect of this embodiment is providing a mechanism capable of easily capturing data into data including pages in an image forming apparatus and flexibly processing the captured data. This embodiment enables providing instructions to input an image obtained by a device of a multifunction apparatus to an application so that user friendliness can be improved.

The image obtained by the device of the multifunction apparatus can be captured into the application only when a preset condition is satisfied. Furthermore it becomes possible to perform reserved printing in which scanning FAX reception or BOX reception is waited for and printing starts upon satisfaction of the condition. Accordingly user friendliness can be improved. Hereinafter the embodiment of the present invention is described.

A network processing unit controls transmission reception of data to from a computer connected via a network or a computer connected via the Internet . The network processing unit functions as a receiving unit.

A PDL expanding unit expands print data PDL transmitted from a computer to a print image in accordance with an attribute set in a page. At this time if a specified print layout requires two pages being printed on one side of a sheet two scaled down pages are printed on one side of the sheet. This is called 2 in 1 printing . Then the PDL expanding unit transfers the print image to a printer unit via an internal bus . The printer unit prints the print image. The printer unit includes a duplex staple unit which performs duplex printing if the PDL has a duplex attribute. Also the duplex staple unit staples a plurality of pages on which image information is printed. A predetermined storage area in a hard disk serves as a BOX which holds print images transferred from a computer. The print images can be printed by the printer unit .

A modem communication unit controls transmission reception of data to from the FAX connected via a public network .

A scanner unit reads a document set thereon. A CPU central processing unit transfers the read image data to a data processing unit . The image data is accumulated in a memory after being processed for example rotated or scaled.

A display and operation unit is a liquid crystal display including a touch panel and serves as a display unit. The liquid crystal display displays a state of an application and receives input from a user.

The CPU executes the application stored in the memory performs an operation in each processing unit and transfers data.

An OS operating system is a first execution environment according to the embodiment of the present invention and controls the image forming apparatus. The OS includes a group of modules and libraries of a real time OS capable of controlling various functions of the copy machine in real time.

A controller operates in the OS as the first execution environment. The controller includes a module controlling the scanner unit the display and operation unit the printer unit the modem communication unit and the PDL expanding unit .

An API is an application programming interface hereinafter referred to as an API . The API performs a process to access the controller in response to a command string input from an application.

A system application is an application operating in the OS as the first execution environment. The application requests various processes to the controller by using the API . Also the application is capable of communicating with the computers and on the network via the network processing unit .

A virtual machine is a second execution environment that is optimal to execute a specific application. This environment is realized by a virtual machine of JAVA for example. An API is used by an application in the virtual machine as the second execution environment to access the controller . The controller operates in the real time OS as the first execution environment. The API has a function of a converting module to call the API in this embodiment.

A management application manages other applications in the virtual machine as the second execution environment.

Applications and operate in the virtual machine as the second execution environment. The applications and request various processes to the controller by using the API . Also the applications and are capable of communicating with the computers and on the network via the network processing unit . In this embodiment the application serves as a binding application.

A resource management unit manages resources used by the virtual machine as the second execution environment and operates in the real time OS realizing the first execution environment. The resource management unit performs control so that resources including a memory are not used beyond a predetermined range by the virtual machine realizing the second execution environment the API or all applications in the virtual machine .

Hereinafter an example of a process performed by the CPU is described with reference to the flowchart shown in . shows an example of a top menu of the copy machine according to this embodiment. Icons of respective functions are displayed in the display and operation unit by the system application . When the system application detects that an icon is indicated on the user interface a plurality of applications one of which being selected and started are displayed . Icons of the binding application and the applications of translation OCR optical character recognition and conversion of electronic document stored in the copy machine are displayed. Among them the icon of the binding application is selected and displayed .

In step S the binding application is selected and started. The binding application is started when the system application detects that an icon is specified on the user interface.

In step S the binding application determines which of a file and a function icon has been dragged and dropped.

If it is determined in step S that a file e.g. cover A report B or report C in has been dragged and dropped into an area the process proceeds to step S. In step S the binding application inserts an obtained image to a specified position. Herein the image of cover A obtained from the dragged and dropped file is inserted to the specified position. In this example there is no document and thus the cover A is displayed at the top. shows the cover in the first page and the head of a report in the second page. Then the process proceeds from step S to step S.

In step S the binding application determines whether the print button at the upper right in has been pressed. If it is determined that the print button has been pressed the binding application determines that the entire document has been input and the process proceeds to step S. In step S a binding process is performed and the printer unit performs printing. The binding process means binding in a broad sense. For example the application executes a printer driver so as to interpret a job ticket including instructions of various processes such as duplex printing stapling and N UP. Then instructions are provided so that PDL data on which setting of the job ticket is reflected is formed on the basis of application data.

On the other hand if it is determined in step S that the print button has not been pressed processing returns to step S. In step S if the binding application determines that a function icon has been dragged and dropped the process proceeds to step S. In step S the binding application determines which function icon has been dropped.

In the example shown in the function icons include a BOX function icon a SCAN function icon and a FAX function icon . shows a state where a SCAN icon scanner function is dragged and dropped on the third page. In this way there is no need to obtain a document image from the scanner unit hold the document image as a file in a BOX hard disk and call the file in the BOX from the binding application. In this example icons of the respective functions are dragged and dropped to the binding application so that user friendliness can be improved.

In this case the SCAN icon scanner function is selected in step S and thus the process proceeds to step S. If the BOX function is selected the process proceeds to step S. If the FAX function is selected the process proceeds to step S.

In step S the controller waits until a document is set on the scanner. If the controller detects that the document has been set the controller instructs a scanner controller to scan the document. shows a screen where the user is requested to set a document and start scanning. This state is held until the start button is pressed and the document is appropriately scanned. If the user wants to cancel the scanning he she presses the back button on the upper right so as to back to the screen shown in .

After the controller notifies the binding application that the scanning process has completed the binding application receives scanned data from the controller . At this time the binding application displays thumbnails of the document images captured by the scanner on the third page and thereafter instead of the scanner icon. For example if a document of five pages is scanned the scanned document is inserted to the third to eighth pages.

After that binding and printing are performed upon press on the print button as in the above described example of the file.

Hereinafter an example of improving user friendliness by performing binding and printing is described. In this example a page is inserted if a preset condition is satisfied.

In step S a document input reservation mode is turned on. Specifically the binding application determines whether the document input reservation mode button on the upper right in is pressed. Then as in the above described example the binding application captures the file cover A from the BOX.

In step S the binding application determines which of a file and a function icon has been dragged and dropped. If a file is dragged and dropped the process proceeds to step S where the binding application inserts the file to the position. This state corresponds to the first and second pages 1 1 and 1 2 of a bound pages of a book shown in .

The position where the SCAN icon is dragged and dropped in corresponds to the third page in the bound pages of the book indicated by an arrow in .

On the other hand if it is determined in step S that a function icon is dragged and dropped processing proceeds to step S. In step S the binding application determines whether the function corresponding to the dragged and dropped icon is BOX SCAN or FAX. In this case the function is the SCAN function and thus the process proceeds to step S.

In step S the binding application waits for input of document input conditions and binding and printing conditions. This state is shown in . In the SCAN function expected time of SCAN can be specified as the document input conditions. In this example three days from the set time 10 00 on May 1 can be set as the document input conditions. The document input conditions can be specified to the binding application from the operation unit. The information of May 1 2006 can be specified as expected time of SCAN.

When the time is not specified input of document is accepted until just before time of printing. Also ID can be specified in a section . The ID is not necessarily specified but anyone can input a document from the scanner.

As the binding and printing conditions time of printing when binding and printing are performed can be specified in a section and a contact address used to transmit a notification of end of printing by e mail can be specified in a section . The conditions are input by the user through the operation unit. The input conditions are transmitted to the binding application . Upon press on the set conditions button the screen shown in is displayed.

Then in step S the binding application determines whether the set conditions button on the upper right in has been pressed. If the binding application determines that the button has been pressed the process proceeds to step S. The state where the conditions have been input is maintained until the set conditions button is pressed. If the user wants to cancel the input conditions he she can clear the input conditions by pressing the back button on the upper right so as to back to the screen shown in step S .

Then in step S the binding application determines whether the end reservation registration button has been pressed. The button is at the upper right in .

If it is determined that the end reservation registration button has been pressed the binding application determines that the entire document has been input and the process proceeds to step S. Then a standby state occurs. Then a process is performed according to the flowchart shown in .

If it is determined in step S that a button other than the end reservation registration button has been pressed the binding application determines that document input reservation continues. Thus the process returns from step S to S and the above described steps are performed.

An example of scanning is described above but this process can also be applied to BOX in steps S and S see and FAX steps S and S see .

In the icon button of the BOX function is dropped on the third page . Accordingly the data stored in the BOX is inserted to the third page of the document data in the conditions set as shown in . The BOX function is a data management system to manage the data stored in the hard disk . In the example shown in instructions are provided so as to capture the data in the BOX No. indicated in a box number field for three days from 10 00 as indicated in a time field May 1 2006 not shown . The information of May 1 2006 can be specified as the expected time of SCAN. The functions of the back button and the set conditions button are the same as those in .

The ID 12345 indicated in an ID field is an ID that is used by the application to manage the data to be captured as a job. In a section the name of the file to be captured is specified. That is the data of the file monthly report.txt is captured upon input of the data. In this example binding and printing conditions can also be specified. As shown in in a time of printing field it is scheduled that printing is performed at 10 00 on May 5 2006. Also the contact address abc xyz.co.jp used for notification of printing is specified in a contact field . In this example the document input conditions are satisfied if all of the input conditions and are satisfied. Alternatively it can be determined that the conditions are satisfied if any one of the conditions is satisfied.

Now the process performed after document input reservation has completed is described with reference to the flowchart shown in .

The flowchart shown in illustrates the process performed by the binding application the controller and the system application .

In step S document input reservation registration ends and instructions to start binding and printing are provided that is press of the start button on the upper right in is detected.

In step S the display and control of the screen of the copy machine are returned to the system application . That is monitoring of the reserved device starts by the controller step S .

In step S the operation panel is backed to an ID input screen default screen and a standby state occurs. That is a screen of a normal state to wait for input in the copy machine is displayed. The screen shown in is an example of the screen to select a function after an ID is input. That is the multifunction apparatus can be operated by operating the system application but the controller continues to regularly monitor the device in the background until the document input conditions are satisfied step S .

In step S the system application detects that a device in the copy machine is used the controller detects an event from the OS or interrupt from the hardware and the process proceeds to step S.

In step S the controller determines whether the document input conditions are satisfied. For example whether the expected time of scanning and the ID set in the screen shown in are satisfied is determined. If the conditions are satisfied the process proceeds to step S.

In step S the system application stores the data in a temporary area of the hard disk. Then in step S the system application transmits the stored image data to the binding application that is waiting for input. Thereafter the process is performed by the binding application . If any other task is being processed the binding application requests suspension of the task to the OS. Then the binding application performs input of document step S . Alternatively the input of document may be performed in parallel with another task of high priority.

If the document input conditions are not satisfied in step S the process proceeds to step S where a normal operation such as copying is performed. For example if a copy button is pressed while waiting for scan and store in a normal copying operation is performed.

If the process proceeds to step S after the conditions are satisfied the binding application inserts the image data transferred from the system application to the document.

In step S the binding application determines whether the entire reserved document has been input. If the entire document has been input the process proceeds to step S where binding and printing are performed. Then in step S the binding application transmits a notification that binding and printing have completed to the contact address by e mail and the process ends.

If the entire document has not been input in step S the process proceeds to step S where the binding application determines whether the time of printing that is set as the binding and printing conditions has come. If the time of printing has come the process proceeds to step S and printing is performed. If the time has not come the process returns to step S where input of a document is waited for.

An example of the SCAN function is described above but this is the same for BOX reception and FAX reception.

That is if the system application determines in step S that a BOX is used the document input conditions of the BOX input on the screen shown in are determined in step S. If the conditions are satisfied the process proceeds to step S where the system application copies the data stored in the BOX having the BOX No. extracted from the conditions to the temporary area. In the example shown in the data in the BOX No. is obtained and copied.

Alternatively if the system application determines in step S that a FAX reception event occurs the process proceeds to step S where it is determined whether the document input conditions input on the screen shown in are satisfied. If the conditions are satisfied the document is input.

In the case of receiving FAX the received data may be printed at the same time of temporarily storing the data in the HDD in step S. Both the output of data received by facsimile and the input of document can be performed at the same time. Whether this process is to be performed can be specified in advance to the controller and the system application in accordance with an input from the user interface of the binding application .

Also the copy machine includes the display and operation unit hereinafter referred to as an operation unit to specify data to be inserted to data. Data in a specific BOX or data received by facsimile can be specified as the data to be inserted from the operation unit . The operation unit provides instructions to insert the data specified by the operation unit to a specific page of the data stored in the hard disk . Whether the data specified by the operation unit has been received is determined.

If the CPU determines that the data specified by the operation unit has been received the CPU inserts the received data to the page specified by the operation unit by using the binding application .

The conditions to insert the data specified by the operation unit are indicated by the operation unit . If the conditions are satisfied the CPU performs an inserting process by using the binding application .

An icon representing the function of a copy machine e.g. is placed between specific pages or on a specific page shown in the preview or displayed by the operation unit .

Accordingly the position to which the data is to be inserted can be indicated by the operation unit . The copy machine also includes the network processing unit to transmit a notification of end of binding and printing to a mail address of a person who has provided the instructions.

The operation unit can specify the expected time when data is to be received as the conditions. At the time specified by the operation unit the controller determines whether the data specified by the operation unit has been received.

The copy machine disclosed here has a plurality of data processing functions. The copy machine includes the hard disk to store data in which pages are defined.

An object shown in is disclosed as an example of a first displayed object corresponding to the position where data is to be inserted to the data stored in the hard disk .

The object shown in is the desired position of insertion and the respective pages can be displayed in a list. If the user selects and indicates a position between pages specified data is inserted to the position. If the user selects and indicates a page the specified data is inserted just after or before set in advance the page.

Function icons as an example of second displayed objects corresponding to the functions held by the copy machine are displayed in the operation unit .

One of the function icons displayed in the operation unit and the object corresponding to the insertion position are selected by using the binding application .

The data processed by the function corresponding to the function icon selected by the binding application is inserted to the desired position of the data specified by the operation unit .

The object visually indicates the insertion position in a plurality of pages in a state where the plurality of pages of the data stored in the hard disk are displayed in a list. The function icons indicate the functions of the image forming apparatus.

The binding application selects one of the function icons by detecting drag of the icon. By detecting drop of the icon on the object visually indicating the insertion position the binding application selects the position of the object .

The copy machine has a function icon corresponding to at least one of an image input function by the scanner a FAX receiving function and a BOX function to store data transmitted from a computer via a network in the memory or hard disk in the copy machine.

The copy machine provided with an application and a control program to control the functions of the copy machine is disclosed.

Insertion conditions to insert data input to the copy machine to data managed by an application are obtained. In this embodiment document input conditions are disclosed as an example of the insertion conditions. The copy machine processes data by controlling the above described functions by using the control program. An event related to execution of data processing is detected by the controller. In response to the detected event the binding application determines whether the obtained insertion conditions are satisfied. If the document input conditions are satisfied the data processed by the control program is transmitted to the application and is edited.

The binding application can perform printing by applying specific binding and printing conditions that are specified from the operation unit at input of document input reservation conditions. For example binding with the 2 in 1 layout or stapling with the 1 in 1 layout can be specified.

The application according to the present invention is not limited to the binding application but an OCR application can also be applied. The resolution of the OCR can be set at setting of document input reservation conditions. Accordingly document input reservation by scanning can be realized so that binding or a specific process about OCR can be performed on read data.

With the above described process when a user performs binding and printing of sales report of each branch for a meeting of branch managers the user friendliness can be enhanced. In the conventional method the user waits until all documents are transmitted from the branches and then provides instructions to perform binding. That is the user needs to wait until the last document is transmitted. On the other hand according to the embodiment of the present invention FAX reception and binding can be reserved on the copy machine so that the documents transmitted from the branches can be automatically bound and a necessary number of copies can be printed. Accordingly user friendliness can be improved.

While the present invention has been described with reference to exemplary embodiments it is to be understood that the invention is not limited to the disclosed exemplary embodiments. The scope of the following claims is to be accorded the broadest interpretation so as to encompass all modifications equivalent structures and functions.

This application claims the benefit of Japanese Application No. 2006 173625 filed Jun. 23 2006 which is hereby incorporated by reference herein in its entirety.

