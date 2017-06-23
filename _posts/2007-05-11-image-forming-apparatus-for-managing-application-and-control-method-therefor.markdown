---

title: Image forming apparatus for managing application and control method therefor
abstract: A control method for an image forming apparatus having means for managing a software application includes the steps of: detecting that a job is generated in the image forming apparatus; obtaining notification information of the detected job; and sending the notification information of the job to the application.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08094334&OS=08094334&RS=08094334
owner: Canon Kabushiki Kaisha
number: 08094334
owner_city: Tokyo
owner_country: JP
publication_date: 20070511
---
The present invention relates to an image forming apparatus in which an application is installed a method for controlling the application in the image forming apparatus and a program for executing the method.

Digital multifunctional apparatuses that include an image scanning section such as a scanner and an image forming section such as a printer and which handle image information from the image scanning section as digital information are known. Such digital multifunctional apparatuses have besides the basic document copy function the additional function of connecting to a network. Thus the digital multifunctional apparatuses can perform the print function of printing print data received via the network and the transmission function of transmitting image information scanned by the image scanning section via the network. Among the digital multifunctional apparatuses some digital multifunctional apparatuses have the function of connecting to a publicly switched telephone network PSTN and performing facsimile communication.

The above described digital multifunctional apparatuses generally have a display apparatus such as a liquid crystal display LCD with a certain degree of resolution. The digital multifunctional apparatuses can execute application programs for allowing a user to use various functions.

For example Japanese Patent Laid Open No. 2000 122853 discloses a digital multifunctional apparatus that can enhance improve and add functions by installing a program received via a network in the apparatus and allowing the apparatus to execute processing in accordance with the program.

Japanese Patent Laid Open No. 2002 287990 describes the technique of not only installing a program in a digital multifunctional apparatus but also performing other operations that is activating deactivating and uninstalling the installed program via a network.

One of the aspects of our invention provides features that the applications can cooperate together to perform predetermined job processing in an image forming apparatus in which multiple applications are installed.

In one of the other aspects of our invention the applications that cooperate together to perform predetermined job processing can be presented to the user.

According to an aspect of the present invention an image forming apparatus is provided for managing a software application. Here the apparatus includes a job generation detecting unit configured to detect that a job is generated in the image forming apparatus a notification information obtaining unit configured to obtain notification information of the job detected by the job generation detecting unit and a notification unit configured to send the notification information of the job to the application.

According to another aspect of the present invention an image forming apparatus is provided for managing a software application. Here the apparatus includes a completion detecting unit configured to detect completion of processing performed by a first application a notification information obtaining unit configured to obtain notification information of a job generated in the image forming apparatus by the first application when the completion detecting unit detects the completion of the processing performed by the first application and a notification unit configured to send the notification information of the job which is obtained by the notification information obtaining unit to a second application.

Furthermore according to another aspect of the present invention an image forming apparatus is provided for managing a software application. The apparatus includes a storage unit configured to store application definition data describing the type of job that can be accepted by the application a job generation detecting unit configured to detect that a job is generated in the image forming apparatus a checking unit configured to check the type of job detected by the job generation detecting unit against the type of job that can be accepted by the application which is described in the application definition data an application information displaying unit configured to display when a check result obtained by the checking unit shows that the type of job detected by the job generation detecting unit matches the type of job that can be accepted by the application which is described in the application definition data application information regarding the application on a display unit included in the image forming apparatus such that the application is selectable by a user and an activation unit configured to activate the application regarding the application information which is displayed on the display unit by the application information displaying unit and selected by the user.

Moreover according to another aspect of the present invention an image forming apparatus is provided for processing a plurality of types of jobs. The apparatus includes a detection unit configured to detect the type of an issued job a determination unit configured to determine a software application corresponding to the type of the issued job and a display control unit configured to control a display operation of displaying the application determined by the determination unit on a display unit so as to present the application to a user.

Still further according to another aspect of the present invention a control method is provided for an image forming apparatus to manage a software application. The method includes detecting that a job is generated in the image forming apparatus obtaining notification information of the detected job and sending the notification information of the job to the application.

Additionally according to another aspect of the present invention a control method is provided for an image forming apparatus to manage a software application. Here the method includes detecting completion of processing performed by a first application obtaining notification information of a job generated in the image forming apparatus by the first application when it is detected that the processing performed by the first application is completed and sending the obtained notification information of the job to a second application.

Also according to yet another aspect of the present invention a control method is provided for an image forming apparatus to manage a software application. The method includes storing application definition data describing the type of job that can be accepted by the application detecting that a job is generated in the image forming apparatus checking the type of the detected job against the type of job that can be accepted by the application which is described in the application definition data displaying when a check result shows that the type of the detected job matches the type of job that can be accepted by the application which is described in the application definition data application information regarding the application on a display unit included in the image forming apparatus such that the application is selectable by a user and activating the application regarding the application information which is displayed on the display unit and selected by the user.

Moreover according to another aspect of the present invention a control method is provided for an image forming apparatus which processes a plurality of types of jobs. Here the method includes detecting the type of an issued job determining a software application corresponding to the type of the issued job and controlling a display operation of displaying the determined application on a display unit so as to present the application to a user.

And further according to yet another aspect of the present invention a control program is provided including computer executable instructions which when loaded into a programmable image forming apparatus and executed controls an image forming apparatus to manage a software application. The program includes computer executable instructions for detecting that a job is generated in the image forming apparatus computer executable instructions for obtaining notification information of the detected job and computer executable instructions for sending the notification information of the job to the application.

And still further according to another aspect of the present invention a computer readable storage medium is provided containing computer executable instructions for controlling an image forming apparatus to manage a software application. The program includes computer executable instructions for detecting that a job is generated in the image forming apparatus computer executable instructions for obtaining notification information of the detected job and computer executable instructions for sending the notification information of the job to the application.

Other embodiments features and aspects of the present invention will be apparent from the following description taken in conjunction with the accompanying drawings in which like reference characters designate the same or similar parts throughout thereof.

Numerous embodiments features and aspects of the present invention will now herein be described with reference to the drawings.

An image scanning section includes a scanner and optically scans a document image and converts the document image into digital image information. The image scanning section outputs the digital image information to the image forming section to form an image or transfers the digital image information to a facsimile unit or a network interface unit to transmit the digital image information via a line.

A digital multifunctional apparatus controller controls the operation of the image forming section and the operation of the image scanning section . For example the digital multifunctional apparatus controller controls the image forming section and the image scanning section such that document information scanned by the image scanning section is copied by the image forming section . The digital multifunctional apparatus controller includes the network interface unit a print processing unit the facsimile unit and an operation unit controller and controls information exchange among these components to .

The facsimile unit transmits and receives a facsimile image. Specifically the facsimile unit transmits the digital image information obtained by the image scanning section or decodes a received facsimile signal which in turn is recorded by the image forming section .

The operation unit controller performs a control operation to generate a signal in accordance with a user operation using an operation panel of an operation unit or to display various data or messages on the operation unit or a display unit . The print processing unit performs a control operation to process print data input via the network interface unit and to output the processed print data to the image forming section thereby printing the print data. The network interface unit controls transmission and reception of data to and from another communication apparatus via a communication line.

A virtual machine is positioned above the digital multifunctional apparatus controller . The virtual machine is configured to control the digital multifunctional apparatus controller .

The network interface unit can be directly used from both the digital multifunctional apparatus controller and the virtual machine . This enables the digital multifunctional apparatus controller and the virtual machine to independently access an external network.

Applications A to D written in a programming language supported by an application programming interface API provided by the virtual machine are positioned above the virtual machine . These applications A to D can indirectly affect the digital multifunctional apparatus controller via the virtual machine or activate the image forming section and the image scanning section .

An external storage controller converts the image scanned by the image scanning section into a data format that can be saved to an external storage by the image forming section and saves the converted data to the external storage. The external storage controller reads the data saved in the external storage and prints the data via the image forming section or transmits the data to the outside via the network using the network interface unit .

An application manager manages the applications A to D. The application manager accepts activation deactivation installing and uninstalling of each application or receives device information generated by the digital multifunctional apparatus controller to control each application.

An application management system according to the first embodiment includes the above described digital multifunctional apparatus and an application installer which will be described later connected to the digital multifunctional apparatus such that the application installer and the digital multifunctional apparatus can communicate with each other.

The application installer may be a web browser connected to the digital multifunctional apparatus via a hyptertext transport protocol HTTP protocol to install and control an application from a remote environment. Alternatively the application installer may install and control an application in a local environment using the operation unit or the display unit included in the digital multifunctional apparatus. As shown in the application manager includes an application management unit an application controller and an install manager .

The application management unit stores a set of the name of an installed application path information indicating the path storing a program file of the application and an application definition file. The install manager accepts installing activation and deactivation of an application from the external application installer . The application controller receives information generated by the digital multifunctional apparatus controller or information generated by the application installer to control each application.

The install manager may be a servlet operating on an HTTP server to accept installing and control of each application from a remote environment via the web. Alternatively the install manager may be an applet to install and control each application in a local environment using the operation unit or the display unit included in the digital multifunctional apparatus.

A job is a management unit of digital image data generated in the digital multifunctional apparatus controller using the functions of the digital multifunctional apparatus. For example the digital multifunctional apparatus generates a copy job when using the copy function a scan job when using the scan function a facsimile job when receiving a facsimile and a save job when saving data to the external storage connected to the digital multifunctional apparatus.

There may be only one type of job depending on the job management method of the digital multifunctional apparatus controller . In this case the type of job need not be described in each application definition file. In contrast the type of job may be defined according to the state of a job depending on the job management method of the digital multifunctional apparatus controller . The state of a job includes for example the state of a job managed in a data format that can be directly analyzed by the print processing unit or the state of a job managed in such a manner that digital data is compressed to be saved to the external storage. To define the type of job according to the job state the type of job is described in a classified manner in each application definition file .

Next an exemplary process of installing an application will be described with reference to . is a sequence diagram showing the process and is a diagram of an application install screen.

As shown in the install manager transmits an install form to the application installer in response to a request from the application installer sequence S . The install form includes as shown in a space to enter the name of an application a space to enter the path storing program data of the application in the application installer and a transfer button .

Using the application installer the user enters on the install form the application name and the path storing the program in the application installer and presses the transfer button sequence S . The application installer transfers as an install instruction the name of the application to be installed and the application program data to the install manager in accordance with the defined specification of the install form sequence S . At this point the application program data contains the application definition file .

The install manager receives the program data sent from the application installer and saves the program data in a file on the external storage sequence S . In addition the install manager registers the path storing the program the application name and the application definition file in the application management unit sequence S .

Next an exemplary process of controlling an application will be described with reference to . is a sequence diagram showing the process and is a diagram of an application control screen.

As shown in the install manager transmits an activation setting form or data regarding the activation setting form to the application installer in response to a request from the application installer sequence S . The activation setting form includes as shown in an application name list including application names and associated check boxes an activation button and a deactivation button .

Using the application installer the user checks on the check box of a desired application to activate in the application name list on the activation setting form and presses the activation button sequence S . Then the application installer transfers as a program activation instruction the name of the application to be activated to the install manager in accordance with the defined specification of the activation setting form sequence S .

The install manager receives the application name sent from the application installer and transfers as a program activation instruction the name of the application to be activated to the application controller sequence S .

The application controller receives the name of the application to be activated which serves as the activation instruction from the install manager and transfers a registration confirmation request to the application management unit asking whether the application with that name is registered or not sequence S .

When the application with that name is not registered in the application management unit the application management unit ends the control process shown in . In contrast when the application with that name is registered in the application management unit the application management unit returns information indicating that the application is registered to the application controller .

The application controller receives the information indicating that the application is registered and sends an operation confirmation request to the application management unit asking whether the application with that name is operating or not sequence S .

When the application with that name is operating the application management unit ends the control process shown in . In contrast when the application with that name is not operating the application management unit obtains the path information indicating the path storing the program file of that application on the basis of the application name. On the basis of the path information the application management unit loads the program data file from the external storage and activates the application sequence S .

The digital multifunctional apparatus according to the first embodiment includes the application manager which manages the operation of multiple applications operating on the virtual machine and the install manager operating on the application manager . Therefore an application can be installed activated or deactivated in the digital multifunctional apparatus using for example the application installer at a remote place. In other words a program can be easily added activated or deleted without affecting another application running on an embedded apparatus such as the digital multifunctional apparatus.

Now other exemplary embodiments using the above described digital multifunctional apparatus will be described as second and third embodiments.

The operation panel of the digital multifunctional apparatus has an interface for presenting information to the user and an interface for accepting information from the user. That is the operation panel includes for example a touch panel type liquid crystal screen and push buttons serving as the input interface.

When activated the application manager registers a job generation notification request in the digital multifunctional apparatus controller . This allows the digital multifunctional apparatus controller to send notification information to the application manager when a job serving as digital data to be processed by the digital multifunctional apparatus is generated.

The job generation timing is as follows. For example image data scanned by the image scanning section is converted into digital image information and this digital image information is generated as a scan job in the digital multifunctional apparatus controller . For example a facsimile signal received by the facsimile unit is decoded and this decoded signal is generated as a facsimile job in the digital multifunctional apparatus controller . For example print data received via the network interface unit is processed and the processed data is generated as a print job in the digital multifunctional apparatus controller .

At the time the job is generated the digital multifunctional apparatus controller sends the notification information to the device that has registered the job generation notification request namely the application manager . As shown in the notification information includes the job state indicating the state in which the job is generated the type of the generated job a job handle for managing the job in the digital multifunctional apparatus controller and a job identifier for specifying the job. shows the structure of the notification information sent from the digital multifunctional apparatus controller when the job is generated.

On the basis of the notification information the application manager detects that the job in a controllable format is generated in the digital multifunctional apparatus controller . Using the job handle included in the notification information the application manager controls the generated job for the digital multifunctional apparatus controller .

The method of detecting by the application manager that a job is generated in the digital multifunctional apparatus controller is not limited to the above method. For example the application manager may periodically check the digital multifunctional apparatus controller to see whether a job has been generated or not.

Next the application manager controls the operation unit controller via the digital multifunctional apparatus controller to display a check box whereby the user selects whether to display available applications as shown in . is a diagram of an application selection display screen.

When the check box is not checked by the user an application management method described in the second embodiment is not performed and the general functions of the digital multifunctional apparatus are performed.

Alternatively for example the application manager may additionally have the function of managing user information. According to the user an application that has been displayed once may not be automatically displayed on the operation panel . In this case the application manager obtains login information including user information of the user via the operation panel distinguishes the user and manages information identifying the application that has been displayed to that user. The application manager determines according to the user whether the application has already been displayed once. In contrast the application manager may automatically display a newly installed application on the operation panel .

With reference to and an exemplary operation of the digital multifunctional apparatus in the case that the check box is checked will be described. include flowcharts of a process from job generation detection to execution of an application by the application manager . is a diagram of an available application presenting screen. is a connectable application presenting screen.

When the user wants to use one of the known functions of the digital multifunctional apparatus such as the function of sending a copied or scanned image via email the digital multifunctional apparatus controller generates a job and sends the notification information to notify the application manager of generation of a job step S .

On the basis of the type of job included in the sent notification information the application manager searches the acceptable job types described in the corresponding application definition files managed in the application management unit step S .

On the basis of the search result the application manager determines whether the type of job included in the sent notification information matches any of the acceptable job types described in the application definition files managed in the application management unit step S . When it is determined that the two job types match each other YES in step S the application manager proceeds to step S. Otherwise NO in step S the process shown in is ended.

In step S the application manager uses the job handle in the notification information to copy the generated job and stores the copied job as a saved job on the external storage . In this case the application manager specifies the job identifier and saves the copied job. The job identifier is required to be unique only within the digital multifunctional apparatus. The application manager generates for example a universal unique identifier UUID and uses this UUID as a job identifier.

Next the application manager determines whether the user wants to continue using the known function of the digital multifunctional apparatus such as the copy function or the data transfer function via a network step S . In this case the application manager determines whether to continue using the function on the basis of preset information. To this end the selection display screen shown in may include an additional check box to be checked when the user wants to continue using the function. On the basis of the check box the determination whether the user wants to continue using the function may be made.

When it is determined to continue using the function YES in step S the application manager proceeds to step S. In contrast when it is determined not to continue using the function NO in step S the application manager proceeds to step S.

In step S the application manager uses the job handle in the sent notification information to control deletion of the generated job thereby deleting the generated job.

In step S the application manager obtains the job handle of the job copied and saved in step S. For example when the copied job is saved in step S the application manager receives and saves the notification information serving as a generation notification of the saved job which is issued by the external storage . The application manager checks the job identifier set in the notification information against the job identifier specified in step S to specify the notification information regarding the generation notification of the corresponding copied job. The application manager then obtains the job handle in the specified notification information . As has been described above the application manager uses the job handle to control deletion of the generated job thereby deleting the generated job.

When the application manager copies the job and saves the copied job in step S the digital multifunctional apparatus controller may be structured to return the job handle of the saved job to the application manager . With this structure the application manager need not specify the job identifier in step S.

The application manager sends to the screen controller the application definition file of the application in which the type of job is determined in step S to match the acceptable job type. On the basis of the received application definition file the screen controller displays the application corresponding to the application definition file as an available application as shown in step S .

As shown in the available application presenting screen is displayed on the operation panel and includes an area presenting the name of an available application and a description of the application and a selection button for selecting the application. The available application presenting screen further includes an area for displaying the names of applications that have already been selected an execution button for starting sequential execution of the applications displayed in the area and a close button for canceling the process. A method of displaying the area on the operation panel will be described later.

Referring to the user presses the selection button of one of the applications that the user wants to use. Detecting that the selection button is pressed the screen controller in step S searches the application definition files on the basis of the output job type included in the application definition file of the selected application. That is the screen controller searches the application management unit for the application having the acceptable job type that matches the output job type the acceptable job type being described in the corresponding application definition file .

As shown in after processing performed by the application selected by the user is completed the screen controller displays the application which is detected in step S as a connectable application step S . The connectable application presenting screen shown in includes besides the elements of the available application presenting screen shown in an additional return button .

The user can select a plurality of applications on the available application presenting screen shown in . When the user selects multiple applications the screen controller displays the connectable application presenting screen shown in for each of the selected applications.

When the user completes a series of application selecting operations and presses the execution button shown in the selected applications are sequentially executed.

With continued reference to the operation of the digital multifunctional apparatus in the case that the user selects applications and presses the execution button will be described.

When the execution button is pressed the screen controller notifies the application controller of the names of the selected applications. In response to the notification the application controller obtains path information of an application corresponding to one of the application names which is stored in the application management unit loads the application from the external storage and executes the application. In this case the application controller sends job handle information included in the notification information sent from the digital multifunctional apparatus controller as additional information to the application step S .

Then the application controller detects completion of processing performed by the activated application. When the application has generated a job the application controller receives a job handle of the generated job step S .

After the completion of the processing performed by the application the application controller determines whether there is an application specified to be connected step S . When it is determined that there is an application specified to be connected YES in step S the application controller proceeds to step S. In contrast when it is determined that there is no application to be connected NO in step S the application controller proceeds to step S.

In step S on the basis of the name of the application specified to be connected the application controller obtains path information of the application from the application management unit . On basis of the path information the application controller activates the application specified to be connected. In step S the application controller specifies the received job handle and activates the application specified to be connected.

In step S the application controller determines whether there is another application whose selection button has been selected selected application . If it is determined that there is another selected application YES in step S the application controller returns to step S. In contrast if it is determined that there is no more selected application NO in step S the application controller ends the process shown in .

The application controller continues executing the process from step S to step S until the execution of all the selected or connected applications is completed.

As has been described above according to the second embodiment when multiple applications are installed in the digital multifunctional apparatus the user can simultaneously use the applications that can be executed by the same operation without needing to perform multiple operations. Thus the digital multifunctional apparatus becomes user friendlier. Depending on the type of job output by each application multiple applications can be connected and used. This further enhances the user friendliness of the digital multifunctional apparatus. The known functions of the digital multifunctional apparatus can be continuously performed and one operation can achieve various output results.

According to the second embodiment the user can easily understand available applications in conjunction with operating the digital multifunctional apparatus. Furthermore the user can easily select and execute applications installed in the digital multifunctional apparatus.

The management application can communicate with the application management unit and the application controller included in the application manager . Also the management application controls the display operation of the operation panel of the digital multifunctional apparatus and accepts inputs from the operation panel .

The operation panel of the digital multifunctional apparatus has an interface for presenting information to the user and an interface for accepting information from the user. That is the operation panel includes for example a touch panel type liquid crystal screen and push buttons serving as the input interface.

When activated the management application registers a job generation notification request in the digital multifunctional apparatus controller . This allows the digital multifunctional apparatus controller to send the notification information to the management application when a job serving as digital data to be processed by the digital multifunctional apparatus is generated.

The job generation timing is as follows. For example image data scanned by the image scanning section is converted into digital image information and this digital image information is generated as a scan job in the digital multifunctional apparatus controller . For example a facsimile signal received by the facsimile unit is decoded and this decoded signal is generated as a facsimile job in the digital multifunctional apparatus controller . For example print data received via the network interface unit is processed and the processed data is generated as a print job in the digital multifunctional apparatus controller .

At the time the job is generated the digital multifunctional apparatus controller sends the notification information to the device that has registered the job generation notification request namely the management application . As shown in the notification information includes the job state indicating the state in which the job is generated the type of the generated job the job handle for managing the job in the digital multifunctional apparatus controller and the job identifier for specifying the job.

On the basis of the notification information the management application detects that the job in a controllable format is generated in the digital multifunctional apparatus controller . Using the job handle included in the notification information the management application controls the generated job for the digital multifunctional apparatus controller .

The method of detecting by the management application that a job is generated in the digital multifunctional apparatus controller is not limited to the above method. For example the management application can periodically check the digital multifunctional apparatus controller to see whether a job is generated or not.

The management application can perform processing similar to that performed by the application manager of the first and second embodiments thereby implementing the application management method described in the first and second embodiments.

As has been described above according to the third embodiment besides the advantages achieved in the first and second embodiments the management application can be activated deactivated installed and uninstalled. That is the application management method described in the first and second embodiments can be performed only when a specific condition is satisfied or a specific user uses the digital multifunctional apparatus. This is advantageous in an apparatus with limited hardware resources such as an embedded apparatus.

According to the embodiments described above in an apparatus in which multiple applications are installed the applications can cooperate together to perform common processing. According to the embodiments described above the effective applications that cooperate together to perform common processing can be presented to the user.

Exemplarily applications include a scanned data processing application a document management application various image processing applications and an email sending application.

For example assume that a scan operation is executed in response to a user instruction. The digital multifunctional apparatus controller generates a job and sends the notification information to notify the application manager of generation of a job.

The application manager copies the job on the basis of a job handle included in the sent notification information and saves the copied job as a saved job on the external storage . In this case the application manager specifies the job identifier and saves the copied job.

When the application manager detects the generation of the saved job and when the job identifier of the generated job matches the specified job identifier the application manager maintains the job handle of that job.

Next the application manager searches for an application in which a scan job is registered as the acceptable job type. As a result the scanned data processing application is displayed as an available application.

Now assume that the user selects the scanned data processing application. In addition assume that the type of job output by the scanned data processing application is a print job and the acceptable job type of the document management application is a print job. In such a case the document management application is displayed as a connectable application.

When the user selects to connect the document management application to the scanned data processing application and gives an instruction to execute these applications the names of the applications to be connected are sent to the application controller .

On the basis of the sent information the application controller activates the scanned data processing application and sends the job handle to the scanned data processing application. The scanned data processing application processes the scanned data. As a result a print job is generated and the job handle of the print job is returned to the application controller .

Next the application controller sends the job handle to the document management application and activates the document management application. Using the job handle the document management application registers and updates a document in a box.

Although the operation flow in the case of a scan job has been described above the operation flow is similar in the case of an application having another acceptable job type.

While the present invention has been described with reference to exemplary embodiments it is to be understood that the invention is not limited to the disclosed exemplary embodiments. The scope of the following claims is to be accorded the broadest interpretation so as to encompass all modifications equivalent structures and functions.

This application claims the benefit of Japanese Application No. 2006 134318 filed May 12 2006 which is hereby incorporated by reference herein in its entirety.

