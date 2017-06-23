---

title: Configuring settings for exception pages in a print job
abstract: An apparatus stores a setting value for each print setting item as a basic print setting for a print job according to an instruction of operation from an operator entered via a print setting screen, and sets a setting value for one specific print setting item as exception setting, according to an instruction of operation from the operator entered via an exception page setting screen for designating a setting value for the exception setting different from the setting value for the basic print setting of the print job, with respect to the print setting item, which is entered according to the operation instruction to the one specific print setting item of plural print setting items displayed on the print setting screen. The apparatus defines switching of the print setting for the print job, according to the basic print setting and the exception setting.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08860959&OS=08860959&RS=08860959
owner: Canon Kabushiki Kaisha
number: 08860959
owner_city: Tokyo
owner_country: JP
publication_date: 20070620
---
The present invention relates to an information processing apparatus a print setting method and a computer readable program. In particular the present invention relates to an information processing apparatus a print setting method capable of performing a setting for changing a print attribute of a print job on a specific page or page range and a computer readable program therefor.

In a print on demand POD market and in the field of a high end printer driver and a hot folder for use in office a function for enabling a different setting of a print attribute for each page is desired in addition to setting of a print attribute for the whole print job. For example in creating a document including a plurality of chapters there is a case where a color paper is used for a first page of a chapter and a white paper is used for other pages of the chapter.

In this case a print attribute setting different from the print attribute setting for the whole job is performed in which a white paper is used for the whole job and a color paper is used for the first page of a chapter. While the setting in the examples is made as to paper type and color other print attributes for example paper size one side or both sides printing finishing and color is desired to be set for a specific page of page range.

Generally in performing a different print setting to each page using a printer driver an operator of an apparatus opens a property sheet for setting an exception page then designates a page range to generate a partition and sets a print attribute in a dialog box in a layer below the generated partition.

Japanese Patent Application Laid Open No. 2004 110638 discusses a method in which a printer driver includes a setting function unit capable of performing a different setting for print attribute for each section by storing a current setting value set in properties of the printer driver as a section setting information file.

Japanese Patent Application Laid Open No. 2005 250606 discusses a method in which an exception print condition is predetermined other than a basic setting condition using a printer driver. For example a paper size A3 and a 1 up layout are set as an exception setting condition and A4 and 2 up are set as basic setting conditions to perform printing.

Under these conditions in the case where a document to be input includes five pages of A4 A4 A3 A4 and A4 size the A4 sized first and second pages of the input document are printed in 2 up . The A3 sized third page of the document corresponds to the exception setting condition and is printed in 1 up printing and the fourth and fifth pages are printed in 2 up printing.

According to the Japanese Patent Application Laid Open No. 2004 110638 a user interface UI for basic setting is used in performing an exception setting so that a current setting set in a property can be selected to be applied to current section or applied to current section and beyond . Attributes that are set here as exception are all setting values in a property of a printer driver.

That is in a setting sequence like this when values for some setting items are changed for a specific page the values to be changed are registered as values for the entire setting items. That is the setting items desired to be set in common for the entire document are managed in each section set as an exception. Accordingly it is necessary to change the values to default as to each section when the setting values set in common to the entire document are changed after exceptions are set which makes the operation much complicated.

The Japanese Patent Application Laid Open No. 2005 250606 discusses a method in which a condition for changing a print attribute and a print attribute to be changed are set. In this method print attributes cannot be changed between pages in which print attributes are not changed. That is it is necessary that a user recognizes in advance a page number of a document whose paper size as a changing condition is changed. Further if the paper size is not changed at a portion where the print attribute is desired to be changed the method is not feasible.

There is another method in which an exception page sheet is provided in a property screen of a printer driver in addition to and separately from a main print setting sheet and a range of pages to be set as an exception and an exception print setting are set in the exception page sheet.

However in such a method an exception setting can be performed only with respect to the print setting items included in the exception page sheet which does not offer a high degree of flexibility. Furthermore it is necessary to open an exception setting sheet other than a main print setting sheet. Therefore an operator cannot easily recognize what exception setting is to be performed to a main print setting because the exception setting is performed using a separate exception setting sheet.

An embodiment of the present invention is directed to a method for allowing a user to perform an exception page setting on each print setting item in a print setting screen for performing a print setting common to the entire print job.

According to an aspect of the present invention an embodiment is directed to an apparatus configured to set a print setting of a print job to be printed. The apparatus includes a first display unit configured to display a print setting screen for designating a setting value for each of print setting items on a display device a storage unit configured to store the setting value for each of the plurality of setting items as a basic print setting for the print job according to an instruction of operation entered via the print setting screen a second display unit configured to display an exception page setting screen for designating a setting value for exception setting different from a setting value for the basic print setting for the print job with respect to at least one print setting item on the display device according to an instruction of operation to the at least one print setting item of the plural print setting items displayed on the print setting screen a setting unit configured to set the setting value for the at least one print setting item as the exception setting according to an instruction of operation entered via the exception page setting screen and a definition unit configured to define switching of the print setting for the print job according to the basic print setting and the exception setting.

Further features and aspects of the present invention will become apparent from the following detailed description of exemplary embodiments with reference to the attached drawings.

Various exemplary embodiments features and aspects of the present invention will now herein be described in detail with reference to the drawings. It is be noted that the relative arrangement of the components the numerical expressions and numerical values set forth in these embodiments are not intended to limit the scope of the present invention unless it is specifically stated otherwise.

Now a first exemplary embodiment of the present invention will be described below with reference to .

A host computer which is an information processing apparatus includes a central processing unit CPU . The CPU performs processing based on a program such as a document processing program application program and a print processing related program stored in a program read only memory ROM of a ROM or an external memory .

The processing performed by the CPU includes processing of a document in which components such as a graphic an image a text and a table including a spreadsheet are mixed. Further the CPU controls each device connected to a system bus in the host computer .

The program ROM of the ROM or the external memory stores a basic input output system BIOS and a program such as an operating system OS program i.e. a control program for the CPU .

In addition a font ROM of the ROM or the external memory stores data such as font data used in processing a document. Furthermore a data ROM of the ROM or the external memory stores various data used in performing various processing such as document processing.

A random access memory RAM functions as a main memory and a work area for the CPU . A keyboard controller KBC controls key input through a keyboard KB and input of a command from a pointing device not shown .

A cathode ray tube controller CRTC controls a display on a CRT display CRT . A liquid crystal display LCD controller and an LCD or a surface conduction electron emitter display SED controller and an SED can also be used instead of the CRT controller and the CRT display .

A disk controller DKC controls access to the external memory such as a hard disk HD and a floppy disk FD . The external memory stores a boot program and various kinds of application programs and various data such as font data a user file an editing file and a print control command generation program hereinafter referred to as a printer driver .

A printer controller PRTC communicates with a printer via a specific interactive interface I F to control communication with the printer . For the interactive interface a universal serial bus USB interface an Institute of Electrical and Electronics Engineers IEEE 1394 interface and a wireless local area network LAN interface for example can be used.

The CPU performs rasterizing of an outline font onto display information RAM set on the RAM to provide a graphical user interface GUI . Thus what you see is what you get WYSIWYG on the CRT display is available. In addition the CPU based on a command generated through the operation of a mouse cursor not shown on the CRT display opens various registered windows and performs various kinds of data processing.

A user when performing printing opens an window operation screen related to print setting to perform settings for a printer and settings for a printing method on the printer driver including selection of a print mode.

The printer printing apparatus includes a printer CPU . The printer CPU controls each device connected to a system bus in a printer control unit . In addition the printer CPU outputs an image signal as output information to a printing unit printer engine via a printing unit interface I F .

The output is performed based on the program such as a control program stored in the program ROM of the ROM or an external memory .

The program ROM of the ROM stores a control program for the printer CPU . In addition the font ROM of the ROM stores data such as font data used in generating the output information.

In the case of a printer that does not include the external memory such as a hard disk HD or an integrated circuit IC card the data ROM of the ROM stores information used on the host computer .

The printer CPU can perform processing for communicating with the host computer via an input unit . Furthermore the printer CPU is capable of notifying various information such as status information in the printer to the host computer .

A RAM functions as a main memory and a work area for the printer CPU . The capacity of the RAM can be expanded using an optional RAM connected to an expansion port not shown .

The RAM is used as an output information expansion area an environmental data storage area and a non volatile random access memory NVRAM . An access to the external memory is controlled by a memory controller MC .

The external memory is connected as an option and stores data such as font data an emulation program and form data. An operation unit includes an operation panel a switch and a light emitting diode LED display device used for performing various operations on the printer .

The number of the external memory is not limited to one. That is according to the present exemplary embodiment more than one external memories can be provided such that in addition to a built in font a plurality of external memories storing an option font card and a program for interpreting printer control languages of different language systems can be connected. Further an NVRAM not shown can be provided so that printing mode setting information from the operation unit can be stored.

First in printing a document generated by the user using an application a print dialog screen through which the user issues a print instruction provided by the application is displayed. The print dialog screen includes a menu through which the user selects a printer name of an output destination and a button for opening a property screen of the printer driver corresponding to the selected printer.

The printer driver useful for the print control program of the present invention is called up upon pressing of the button for opening the property screen and provides a GUI for issuing an instruction for performing a print setting related to the print operation by the printer . The user can input a setting parameter for a desired print attribute print output processing condition data by operating the keys via the operation screen.

The printer driver sends the user print attribute setting input via the GUI together with desired image data to a destination such as a printer via a communication medium such as a network.

By the operation via the selection field displayed on the print dialog screen the user selects a desired output destination device in the system.

A page setting control is used for selecting a page to be printed and output from a print job. The user operator using the page setting control can make a determination as to which page of print target data that is generated using application software operating on a client computer is output.

The user can select a page to be printed and output the page using a device such as the printer in the system via the page setting control . Thus the user can perform printing of all the pages or a specific page s without printing all the pages.

A print number setting control is used for designating an output number of a job to be printed and output by the device such as the printer in the system. By moving a pointing cursor to the position of the print number setting control and clicking an arrow in a scroll bar the user can increase or decrease the number of the output number of the job.

A property button is used for performing a detailed setting as to the destination device selected via the destination selection field . When the property button is pressed by the user various detailed screens illustrated in are displayed on the display of the computer.

After the desired setting has been performed by the user via the various operation screens illustrated in the user presses an OK key to start print processing according to the print setting desired by the user. When canceling the print setting processing the user presses a cancel key . When the user presses the cancel key the control unit suspends the print setting processing discards the current print setting and terminates the display on the print dialog screen .

The screen includes a plurality of tab sheets such as page setting finishing paper feed print quality and special features . When the tab is clicked by the user a screen for performing a setting is displayed as to various detailed print output conditions such as the page setting a setting related to the finishing the paper feed the print quality and the special features .

In the examples illustrated in the screen has a configuration similar to a conventional printer driver which is commonly used.

A layout setting unit is used for selecting a layout mode for arranging and generating document image data for a plurality of pages on one side of one recording paper sheet . Using the layout setting unit the user can input an instruction and select from plural alternatives a number of pages which are to be arranged and generated on one side of a recording paper.

A paper orientation setting unit is used for performing a setting as to an orientation of printing for the job desired by the user from among a plurality of alternatives such as portrait and landscape. A print number setting unit is used by the user for setting a print number of the job to be processed.

As described above by the operation of the each setting field on the page setting screen illustrated in the user can perform desired print settings.

When the user presses the finishing tab the CPU control unit opens the GUI of the printer driver and displays the operation screen illustrated in on the CRT display . The screen includes various detailed setting fields such as a discharge method setting field for setting a finishing manner and a stapling position and a printing method such as one sided printing two sided printing and bookbinding printing which are unique setting information related to the selected printer.

For example with the setting in the display example the CPU can perform processing of a print job using the printer selected by the user according to the two sided print mode set via a setting field of the operation screen illustrated in . In addition the CPU can add a control command to the print job so that the printer performs the two sided print processing according to the long edge binding setting in the two sided print mode set via a setting field . Furthermore when the user operates a default key on the operation screen in the CPU can perform control so as to return the print detailed setting in the operation screen of each tab sheet to a default value.

When the user presses an OK key the user setting is entered and then the process returns to the screen illustrated in . When the user presses i.e. issues an instruction a cancel key the CPU nullifies the user setting and then the process returns to the screen in .

Similarly although not shown here by pressing the paper feed tab the user can designate a paper feed stack and by pressing the print quality tab the user can make a selection as to a resolution and a halftone setting.

Now the method for performing a setting for some of the pages or a specific page range different from the setting for the entire job will be described below. Performing a setting for some of the pages or a specific page range other than the setting for the entire job is referred to as performing an exception page setting .

The sheet includes a button for setting a top cover and a back cover aside from text data. A button is used for setting a paper to be inserted aside from the text data.

A table is used for displaying a list of items which are set differently from the entire setting via the operation of the buttons through . The table includes and displays from right to left a column of the setting target page or page range a setting item column and a setting content column.

It is to be noted that this display is a mere example and other form and other items can be used. A list combination button is used for combining lists of the settings in the case where with respect to special feature items listed in the table designated by the user the same settings are made for adjacent pages or page ranges.

The setting lists are combined by selecting the adjacent settings desired to be combined from among the special feature setting lists and by pressing the list combination button . A delete button is used for deleting a setting from the special feature settings listed in the special feature setting list generated by the user.

The setting is deleted by selecting a setting to be deleted from the special feature setting list and pressing the delete button . A setting button is used for changing a setting in the special feature settings listed in the special feature setting list generated by the user.

The change in the setting can be performed by previously selecting the setting to be deleted from the special feature setting list before pressing the setting button . The OK button is used to close the operation screen and save the setting contents set via to the operation screen of . And cancel button is used to cancel the setting contents set via to the operation screen of .

A control is used for setting a page or page range. When designating a specific page the user enters the same page number for a start page column and an end page column. Thus a value set by the control process described below is applied only to the designated page.

A control is used for performing a setting different from the entire job on the page or page range set via the control . By the control the user can perform a setting as to a print medium. More specifically by the control the user can perform a setting as to print medium that is a paper type a paper size and whether the printing is performed on one side or two sides.

A control is used for performing a setting different from the setting for the entire job on the page or page range set via the control . By the control the user can perform a setting as to color. More specifically by the control the user can perform a setting as to a color mode halftone and an input profile.

After the user performs the desired setting via the controls through in when an OK key is pressed the user can apply the desired setting. When canceling the applied setting the user presses a cancel key . The printer driver which receives the instruction for canceling the setting from the user discards the content of the current setting and then terminates the display in .

Using the special features tab sheet and the exception page dialog box described above the user can perform an exception page setting. The above is a first method for performing an exception page setting.

The printer driver according to the present exemplary embodiment can use a second method for performing the exception page setting. The second method will be described below with reference to .

A control is used for setting a state of mounting of a paper feed option. A control is used for setting a mounting condition of a paper discharge option. After the user performs a desired setting via the controls and in when an OK key is pressed the desired setting is entered. When canceling the applied setting the user presses a cancel key . The printer driver which receives the instruction for canceling the setting from the user discards the setting content of the current setting and then terminates the display in .

A control is used to designate a work of the printer driver when the application generates a PDL code. This control includes in Always Permit PDL Output From Application Always Prohibit PDL Output From Application Depends on Printer Driver Settings . When Always Permit PDL Output From Application is selected the application always generates the PDL code. In this case the printer driver performs drawing processing through the drawing system of the OS.

When Depends on Printer Driver Settings is selected the application does not generate the PDL code. The button is used to acquire the device information. The button is used for display the dialog that includes the version information of the printer driver.

As described above first the client user sets a desired output condition of the print processing conditions including various detailed settings and exception page settings via various print setting screens in .

In addition a printer driver and application software program are installed on the OS and controlled by the OS .

The printer driver includes a user I F driver that displays a user I F and stores a setting and a graphic driver that converts a printing and rendering command instructed from the application program into a code that can be interpreted by the printer. The user I F driver displays a print setting property sheet illustrated in when the user instructs print setting from the application program via the OS .

A printer driver setting storage area is provided in a storage area managed by the OS . The print attribute set by the user via the user I F driver is stored in the printer deriver setting storage area . Furthermore the user I F driver the graphic driver and the application program can access the printer deriver setting storage area via the OS to read the print attribute set by the user.

Moreover a communication I F of the host computer is in communication with a communication I F of a printer via a communication medium such as a network. The graphic driver is capable of sending print data to the printer via the OS . Furthermore the graphic driver can acquire printer configuration information and status information via the OS .

Now a flow of processing will be described below in which first the user selects a print menu from the menu of the application then sets a print attribute on the printer driver and then a job is printed and output. and are flow charts illustrating processing by the host computer from when the user instructs printing until printing is performed.

Referring to in step S the user selects a print setting menu from the application software menu. Then the application program displays the print dialog screen illustrated in .

In step S when the user presses the property button in the print dialog screen the application program calls an application programming interface API of the OS .

The API call is made to the OS from the application program to instruct display of a property sheet for setting a print attribute of the printer driver selected via the print dialog screen. According to the instruction the OS activates the user I F driver to generate an instruction for displaying a print attribute setting property sheet.

In step S the user I F driver of the printer driver upon receiving the instruction for displaying the property sheet from the OS performs control so that the print attribute setting property sheet illustrated in is displayed on the CRT display .

In step S the user performs a desired print attribute setting on the property sheet in described above and then the printer driver inputs the print attribute setting. The user after performing the print attribute setting presses the OK button in the property sheet in to enter the print attributes that are set.

After the OK button is pressed in step S the user I F driver stores the print attribute setting value set by the user in the printer deriver setting storage area within the OS by calling the API of the OS . Thus the print attribute setting and storing of the setting value for the print attribute are completed.

In step S of in order to print a document the user selects a print menu from the menu of the application software. Then the application program displays the print dialog screen illustrated in .

In step S when the user presses the OK key in the print dialog screen the application program calls the API of the OS to issue a print start instruction to the printer driver .

In step S the graphic driver which constitutes the printer driver upon receiving the print start instruction reads the print attribute setting value stored in the printer deriver setting storage area of the OS . Then the graphic driver generates a print attribute setting command directed to the printer according to the read print attribute setting value.

In step S the application program generates a rendering command via the OS according to data of a printing target document. In step S the CPU sends the rendering command to the graphic driver via the OS and then the graphic driver converts the received rendering command into print data that can be interpreted by the printer .

In step S the printer driver generates a print job including the print attribute setting command and the print data and sends the generated print job to the printer . After that the printer performs rendering based on the received print rendering code and performs print processing on the print paper.

In the case where an exception page setting is performed the CPU generates a print job defining a basic print setting which is a print setting for the entire print job and an exception setting for which a page range is designated. The print job itself on which an exception page setting is performed is publicly known. Accordingly a detailed description thereof is omitted here.

Now control related to constraint processing by a printer driver will be described below. illustrate an operation performed during processing for constraining a function by the printer driver on the user I F.

An application and a printer driver such as a hot folder that performs a print attribute setting include functions that can not or should not be set at the same time. Some functions do not effectively operate for example an overhead projector OHP sheet and two sided printing should be set to be unselectable at the same time. If an OHP sheet transparent sheet is selected as a print medium when two sided printing is performed an obtained output cannot be used as a print product.

Further if the printer cannot perform stapling when a thick print medium is used for example the function of the printer is restricted. Therefore stapling should be set unselectable on the user I F of the printer driver.

An operation on the user I F for items that cannot be functionally and meaningfully set is called constraint processing . Now the constraint processing by the printer driver will be described.

As an example when bookbinding printing is selected as the print style in the finishing sheet in the printer driver property sheet the setting for the binding method setting field is set to be constrained null . This operation will be described below.

It is noted that the constraint rule file is a mere example and another format and a file system can be used. Furthermore as long as the constraint processing can be performed other means such as the program that can control the constraint processing are also feasible.

The body of the constraint rule file is described in . The constraint rule file is described in a text format whose each line includes a keyword starting from and a parameter defined based on the keyword. The keyword and the parameter are separated by a colon .

A line describes a version of the constraint rule file. The keyword ConstraintsFileVersion is used and the parameter is 1.0 which indicates that the version of the constraint rule file is 1.0. The constraint file includes other information however in this example only the lines related to the present exemplary embodiment are extracted from the actually used lines and illustrated here.

Lines and describes the constraint rule for the print style and the bookbinding method. As the format for describing the constraint the keyword Constraints at the head portion of the line which indicates the constraint rule the function that is the source of the constraint the options of the constraint source function the function that is the object of the constraint and then the options of the constraint object function are described in this order.

That is the definitions of items are made in the order of the items to be determined for constraint the setting value to be determined for constraint the items to be constrained and the values to be constrained. The description of the function and the options of the function are provided with an asterisk at the head portion thereof.

For example the line is interpreted as follows That is constraint is set between the print style PrintStyle and the binding method BindingEdge .

The example shows that when the bookbinding printing Booklet is selected for the print style PrintStyle long edge binding LongEdge cannot be selected for the binding method BindingEdge . The next line is interpreted similar to the above described rule. Thus the next line is interpreted to indicate that when the bookbinding printing is selected for the print system short edge binding cannot be selected for the binding method.

Now an operation performed for the constraint processing when the user changes the setting for print system field from one sided printing which is currently selected to bookbinding printing in the property sheet of the finishing sheet is described with reference to the flow chart of . The operation starts when the user changes the setting via the printer driver user I F.

In step S the printer driver reads one line of the constraint rule from the constraint rule file illustrated in . That is the printer driver reads the first line .

In step S the printer driver determines whether all the constraint rules are read referring to a description End of File EOF of the constraint file. If it is determined in step S that the EOF is not read yet No in step S then the printer driver advances to step S.

In step S the printer driver determines whether the read line includes information about the constraint rule. This determination can be made according to whether the keyword is Constraints . If it is determined in step S that the read line does not include the information about the constraint rule No in step S then the printer driver returns to step S. On the other hand if it is determined that the read line includes the information about the constraint rule Yes in step S then the printer driver advances to step S.

In step S the printer driver determines whether the constraint rule in the read line describes the function to be determined as to constraint. In the present case the current operation for the constraint processing has been started according to the change in the print style field PrintStyle made by the user. Accordingly the function to be determined as to constraint is the print style field PrintStyle .

Thus in this processing the printer driver determines whether the constraint rule in the read line is the constraint rule for the print style PrintStyle and whether the constraint rule in the read line is the setting value for the bookbinding printing Booklet . That is it is determined whether both the item to be determined for constraint and the setting value to be determined for constraint match the condition.

In the example in the constraint rule is set for the print style PrintStyle and for the setting value of the bookbinding printing Booklet Yes in step S . Thus the printer driver advances to step S. If it is determined in step S that the constraint rule in the read line does not describe the function to be determined as to constraint No in step S then the printer driver returns from step S to step S to read the constraint rule file again.

In step S the printer driver nullifies the value to be constrained in the item to be constrained which is an option in the function to be constrained. In the example of the line defines that when the print style PrintStyle is set to the bookbinding printing Booklet long edge binding LongEdge for the binding method BindingEdge is nullified.

Accordingly the user I F driver nullifies the option of the long edge binding LongEdge with respect to the print setting field binding method . Thus the user cannot select the long edge binding. After this processing the printer driver returns to step S to read the next line . For the next line the printer driver performs processing similar to the above described processing. When bookbinding printing Booklet is set for the print style PrintStyle more specifically the printer driver performs the following processing 

Short edge binding ShortEdge is nullified for the binding method BindingEdge . Thus the option of the short edge binding ShortEdge is nullified. Accordingly the user cannot select the short edge binding option. By repeating the processing the printer driver applies the constraint rule file.

The option for the binding method in the finishing sheet of the printer driver includes only the long edge binding and the short edge binding . In the case of the example in both of the options are nullified.

Accordingly the printer driver nullifies the option for the binding method itself and grays out the control for the binding method as illustrated in . Thus the user cannot select the option for the binding method. As described above the printer driver performs the constraint processing.

Now the flow of the exception page setting processing during the print attribute setting according to the present exemplary embodiment will be described below. The first method for the exception page setting processing is described above with reference to . Now a second method for the exception page setting processing which is a characteristic feature of the present exemplary embodiment will be described below with reference to .

In the present exemplary embodiment the entire print job is set as an example such that the paper size is set to A4 size the print system is set to one sided printing and the color mode is set to monochromatic printing and that a document including fifty pages are printed.

For the exception setting a paper of A3 size is already set for each of pages through of the document and the print system is set to two sided printing and the color mode for pages through is already set to color printing. The method for performing the exception setting is as follows 

In the present exemplary embodiment the description is made as to a method for performing exception setting that is a red green blue RGB input profile is set to sRGB for the pages through when the above described setting for the entire job and the exception page setting are performed. is a flow chart illustrating a procedure for controlling the printer driver to perform the above described exception setting. The operation performed during the processing will be described below according to the flow chart of .

Before describing the processing according to the flow charts in the description will be made as to an exception page setting table stored in the printer deriver setting storage area by the printer driver .

The function column includes a list of the functions of the printer driver on which the exception page setting can be performed. In the function column a print system are defined which includes options such as two sided printing one sided printing and bookbinding printing and a color mode a paper size halftone and the RGB input profile . In the setting value column the setting values for each page in the designated page range which correspond to the functions listed in the function column are stored.

In the example illustrated in as the exception page setting A3 size is set as the paper size and the print system is set to two sided printing for the pages through and the color mode for the pages through is set to color printing . Accordingly in the two sided printing function column in the cell for the pages through the setting of two sided printing is described.

The exception page setting table includes the cell in which the setting value NULL is described. This indicates that the exception setting is not set to the specific page of the specific function. That is to the page of the function for which the setting value is set to NULL the setting for the entire job is applied.

In the color mode function column the color mode is set to color for the pages through . Accordingly the setting value describes color . In the paper size function column A3 size is set for the pages through . Accordingly the setting value describes A3 .

In the halftone column the exception setting is not performed. Accordingly the value NULL is set for all the pages. In the RGB input profile column the exception setting is not performed. Accordingly the value NULL is set for all the pages just as in the case of the halftone column .

The printer driver in performing computation for constraint computes the constraint information for the exception setting according to the flow of processing in based on the exception page setting table .

Now with reference to the flow chart of the procedure in which the user sets the option of the RGB input profile to sRGB for the pages through will be described below.

In step S the user selects the exception setting menu via the control of the user interface of the printer driver on which the user desires to perform exception setting. Thus the processing starts. More specifically the user opens a user I F screen of the printer driver illustrated in and then opens a print quality property sheet .

Then the user in order to perform exception setting on the RGB input profile function points an RGB input profile control with a mouse cursor and right clicks the RGB input profile control . That is when the RGB input profile control is right clicked with the mouse cursor when the RGB input profile control is being focused a tool tip for designating the exception setting is displayed.

After this operation is performed by the user the user I F driver of the printer driver displays an exception setting sub menu in a portion close to a designated subject item so as to allow the user to select the exception setting menu.

In the above description the menu is displayed upon right clicking the RGB input profile control with the mouse cursor. However the present exemplary embodiment is not limited to this. The menu can also be displayed by left clicking of the RGB input profile control when a specific key a control key and the like is being pressed by the user. By performing the processing in this step the user designates the exception setting for the RGB input profile. Accordingly the printer driver in the steps beyond computes necessary information such as the constraint information to display a dialog for the exception setting.

In step S the printer driver computes the constraint information for the RGB input profile according to the constraint rule illustrated in the example in . The processing in step S is illustrated in detail in the flow chart of .

From the description in a last setting table of the exception page setting table it is known that the last exception set page is the page . In the steps beyond in the flow chart of the printer driver computes constraint for each page of the pages through .

In step the printer driver substitutes i which is a variable of a number of pages to be checked for constraint with a value 1 .

In step S the printer driver acquires the exception setting value for the i th page first page from the exception page setting table . From the exception page setting table in it is known that the exception setting for the first page is NULL as to all functions.

Next in step S the printer driver determines whether the RGB input profile can be set for the first page using the method described in the described above. The setting of the RGB input profile can be performed only when the color mode is set to color . If the color mode is set to monochromatic the setting of the RGB input profile is constrained.

In the exception page setting table the color mode for the first page is set to NULL . The description NULL is set for the entire job and the color mode for the entire job is set to monochromatic . Accordingly the constraint rule is applied and it is determined that the setting of the RGB input profile for the first page cannot be performed.

Thus the setting of the RGB input profile for the first page is constrained in step S and accordingly in step S the printer driver excludes the first page from the pages on which exception is set.

In step S the printer driver increments the counter i of the page by one and processes a next page. In step S the printer driver determines whether the i th page exceeds an N th page.

If it is determined in step S that the i th page does not exceed the N th page Yes in step S then the printer driver returns to step S. For the pages through the processing and determination similar to that performed for the first page are made. Accordingly the description as to the pages through is omitted here.

In step S the printer driver acquires the exception setting value for the page from the exception page setting table . In the exception page setting table in the exception setting for the page is such that color is set for the color mode and all the other functions are set to NULL .

In step S the printer driver determines whether the RGB input profile can be set for the page using the method described in the above just as in the case of the processing for the first page. The setting of the RGB input profile can be performed only when the color mode is set to color .

In the example in the exception page setting table in the color mode for the page is set to color . Accordingly the constraint rule is applied and it is determined that the RGB input profile can be set for the page . Similarly it is determined that the setting of the RGB input profile can be performed for the pages through

In step S the printer driver acquires the exception setting value for the page from the exception page setting table . In the exception page setting table in the exception setting for the page is such that A3 is set for the paper size and all the other functions are set to NULL .

In step S the printer driver determines whether the RGB input profile can be set for the page using the method described above. In the exception page setting table in the color mode for the page is set to NULL .

The description NULL is set for the entire job and the color mode for the entire job is set to monochromatic . Accordingly the constraint rule is applied and it is determined that the setting of the RGB input profile for the page cannot be performed. In a similar manner it is determined that the RGB input profile cannot be set for the pages through .

After step S for the page is completed the variable i 31 in step S. In step S the printer driver ends the constraint determination processing.

In step S the printer driver consolidates the pages to which the RGB input profile can be set. According to the result of the above described processing the RGB input profile can be set to the pages through . The processing in the flow chart of namely the processing in step S thus ends.

In step S the printer driver displays an exception page setting dialog illustrated in . The exception page setting dialog includes a control information a compulsory setting check box and an RGB input profile control . The control is used for inputting the page range on which exception setting is set. The information includes information about the page range computed in step S on which the RGB input profile can be set.

The option for the RGB input profile displayed in step S can include a value same as job setting which indicates that the same value as the value set for the entire job is set in addition to the options for the RGB input profile used for performing a setting for the entire job illustrated in FIG. . This applies to the RGB input profile and also to the functions on which exception can be set.

In step S the user performs desired setting via the exception page setting dialog . the printer driver inputs the setting value designated by the user.

It is supposed that the user has selected 5 20 for the exception page range and sRGB for the RGB input profile control . The user needs to click an OK button to enter the user setting. In addition in order to cancel the setting and close the exception page setting dialog the user clicks a cancel button .

In step S the printer driver determines whether the OK button and the cancel button are pressed by the user. If it is determined in step S that the OK button has been pressed by the user then the printer driver advances to step S. On the other hand if it is determined in step S that the cancel button has been pressed by the user then the printer driver ends the processing.

In step S the printer driver determines whether the setting for the compulsory setting button is set ON. If it is determined in step S that the compulsory setting button is set OFF then the printer driver advances to step S.

In step S the printer driver compares the exception page range 5 20 which has been input by the user with the page range 10 20 that can be set.

If it is determined in step S that the set exception page range does not exceed the settable page range that can be set Yes in step S then the printer driver advances to step S. On the other hand if it is determined that the set exception page range exceeds the page range that can be set No in step S then the printer driver shifts to step S. In the example in the exception page range 5 20 input by the user exceeds the page range 10 20 that can be set. Accordingly the printer driver shifts to step S.

In step S the printer driver displays a message dialog which indicates an error message illustrated in . In the message dialog the printer driver displays the message indicating that the page range set by the user exceeds the page range that can be set to urge the user to reset the page range.

Then the printer driver returns to step S. In step S the user sets again the page range on which exception setting is performed. If the user enters the value 10 20 for the exception page range the entered page range does not exceed the page range that can be set. Accordingly the printer driver advances to step S.

In step S the printer driver stores the setting values set via the exception page setting dialog in the printer deriver setting storage area corresponding to the printer driver . In step S the printer driver writes the content of the print setting set as exception for the set page range into the exception page setting table so that the exception page setting table is updated.

In addition by the above user operation the exception setting of the RGB input profile for the pages through is completed.

Thus the printer driver can receive an instruction for performing the exception setting to one print setting item in the print setting screen. Furthermore according to the instruction the printer driver can display the page range designation screen used for setting the page range to perform the exception setting for the print setting items.

Accordingly the user can generate an instruction for exception setting independently and separately for each of the print setting items via the print setting screen of the user interface of the commonly used printer driver. Thus the user s convenience can be improved.

Furthermore when setting an exception page range with respect to a specific print setting item the page range on which the exception setting can be performed is computed from the already set print setting values and is displayed. Accordingly the user is prevented from setting by mistake the page range on which exception setting cannot be set.

Now the processing for designating perform compulsory setting in the exception page setting dialog will be described below. It is now supposed that the user has opened the exception page setting dialog of the RGB input profile in order to perform the exception setting of the RGB input profile.

In this case because the color mode is set to color the RGB input profile can be set for the pages through only when the exception page setting dialog is opened. If the user desires to set the color mode color and the RGB input profile for the pages through in a conventional method the user has to cancel and close the exception setting dialog set the color mode color for the pages through as the exception setting and then open the exception setting dialog for the RGB input profile to perform exception setting.

In this method many steps need to be taken during the operation because the user is required to change the setting and re open the dialog. Thus this method is inconvenient for the user. Since it is more effective to perform setting regardless of the constraint the printer driver according to the present exemplary embodiment includes the perform compulsory setting check box in the exception page setting dialog .

When the check box is set ON even when the exception page range set by the user exceeds the page range that can be set the printer driver temporarily stores the content set via the exception page setting dialog . This operation will be described below with reference to the flow chart of .

It is supposed that the user enters the value 5 20 in the exception page range control . Then if the user desires to perform the setting although the set page range exceeds the page range that can be set the user sets the perform compulsory setting check box to ON.

Now the operation of the printer driver according to the steps in the flow chart illustrated in will be described below. The steps similar to those described above will be omitted in the following description and only the operation different from the above description will be described below.

In step S the printer driver determines whether the perform compulsory setting check box is set ON. If it is determined in step S that the perform compulsory setting check box is set ON then the printer driver advances to step S.

In step S the printer driver makes a list of functions which can be constrained according to the constraint rule file illustrated in . In step S the printer driver determines whether there exists any function to be constrained.

In the supposed state the setting of the RGB input profile is constrained against the setting of the monochromatic printing in the color mode setting item. Accordingly the printer driver advances to step S. In step S in order to notify the user of the constraint the printer driver displays a message dialog illustrated in .

In the message dialog a print setting item print function that is constrained conflicting with the setting for the color mode due to the setting of the exception setting is displayed. The user after confirming the message displayed in the message dialog presses an OK button . Then the message dialog disappears.

In step S the printer driver stores the content of the setting performed via the exception page setting dialog into the printer deriver setting storage area . In step S the printer driver updates an exception page setting table. illustrates an exception setting table after the updating. In the exception page setting table sRGB is set for the RGB input profile for the pages through .

Now the processing for controlling the print in response to a print instruction according to the present exemplary embodiment will be described below. is a flow chart illustrating the control related to the print processing by the printer driver performed when the user issues a print instruction.

In step S the user selects a print menu of the application to display the print property dialog illustrated in and then presses the OK key in to issue the print instruction. Thus the printer driver is activated via the OS and receives the print start instruction from the application.

In step S the printer driver according to the constraint rule applies the constraint rule based on the setting value for the entire job also referred to as the basic print setting and the setting value in the exception page setting table to check whether constraint has occurred. In step S the printer driver based on the result of the checking determines whether any constraint has occurred.

In the supposed state in the present exemplary embodiment in the exception page setting table constraint occurs between the setting of the RGB input profile and the setting of the color mode as the constraint related to the page range that can be set. When it is determined in step S that constraint has occurred Yes in step S then the printer driver shifts to step S.

In step S the printer driver displays a list of the constrained functions and an error message. illustrates an example of the error message. By displaying a message dialog the printer driver urges the user to reset the printing condition.

When the user presses an OK key in the printer driver suspends the print processing. In step S the printer driver displays a print setting dialog screen using the user I F driver . Thus the user can perform the setting for the printer driver again so that the constraint can be solved.

On the other hand if it is determined that no constraint has occurred No in step S then the printer driver performs the processing for generating a print job as described above. With the above described processing the exception page setting for the print job can be performed.

Now a second exemplary embodiment of the present invention will be described below. The print system and the preconditions applied in the second exemplary embodiment are similar to those in the first embodiment. Accordingly the description will be made below only with respect to portions different from the first exemplary embodiment and the description of the similar portions will be omitted in the following.

In the case where the user has set the perform compulsory setting check box to ON the printer driver shifts to step S. In step S in the processing after step S the printer driver sets a compulsory setting flag to True .

The compulsory setting flag is a storage table existing in a setting storage area of the printer driver. illustrates a setting table . The printer driver stores the value True in the setting table .

If the user sets the perform compulsory setting check box to OFF the compulsory setting flag remains to be a default value namely the value False .

In step S the user selects the print menu of the application to display a print property dialog and presses the OK key in to issue an instruction for printing. Thus the printer driver is activated via the OS and receives the print start instruction from the application.

In step S the printer driver acquires the compulsory setting flag stored in the printer deriver setting storage area . If the compulsory setting flag is set to False no constraint has occurred. Accordingly the printer driver shifts to step S. In step S the printer driver sends the print job to the printer .

On the other hand if the compulsory flag is set ON that is if it is likely that the user has performed the exception setting regardless of the constraint then the printer driver shifts to step S. In step S the printer driver according to the constraint rule checks whether any constraint has occurred by applying the constraint rule based on the setting value for the entire job and the setting value in the exception page setting table .

Because the user has performed the setting regardless of the constraint i.e. the page range that can be set in the exception page setting table constraint has occurred between the setting of the RGB input profile and the setting for the color mode. If it is determined that the constraint have occurred the printer driver shifts from step S to step S. In step S the printer driver displays a list of the constrained functions and an error message.

In step S the user resets the printer driver so that the constraint can be cancelled. Then the printer driver returns to step S. In step S the user issues a print instruction. According to the setting performed this time no constraint occurs. Then in step S it is determined that no constraint has occurred. Then the printer driver advances to step S.

In step S because all the constraints have been already cancelled the printer driver sets the compulsory setting flag to False . In step S the printer driver performs printing.

Now a third exemplary embodiment of the present invention will be described below. The print system and the preconditions applied in the third exemplary embodiment are similar to those in the first embodiment. Accordingly the description will be made below only with respect to portions different from the first exemplary embodiment and the description of the similar portions will be omitted in the following.

The operation of displaying the exception page setting dialog and the operation performed thereafter to print the print job are similar to the first and the second exemplary embodiment. Accordingly the description thereof is omitted here.

As described above according to the present exemplary embodiment the user can perform the desired exception setting to the control of the function which the user wishes to set as exception page without changing an appearance of a user interface UI screen of the commonly used printer driver. Accordingly the user can easily understand the operation and the user can perform the exception page setting by a simple operation.

Furthermore because the appearance of the UI screen of the commonly used printer driver is not changed even a user who is not accustomed to performing exception page setting can easily perform the operation.

In addition because the constraint conditions are displayed the setting in which no constraint occurs can be easily performed.

According to the exemplary embodiments of the present invention a method can be provided which allows the user to perform exception page setting for each print setting item on the print setting screen that is used to perform a common print setting for the print job.

Therefore the user operator can perform exception page setting for the print job by a simple operation.

While the present invention has been described with reference to exemplary embodiments it is to be understood that the invention is not limited to the disclosed exemplary embodiments. The scope of the following claims is to be accorded the broadest interpretation so as to encompass all modifications equivalent structures and functions.

This application claims priority from Japanese Patent Application No. 2006 173630 filed Jun. 23 2006 which is hereby incorporated by reference herein in its entirety.

