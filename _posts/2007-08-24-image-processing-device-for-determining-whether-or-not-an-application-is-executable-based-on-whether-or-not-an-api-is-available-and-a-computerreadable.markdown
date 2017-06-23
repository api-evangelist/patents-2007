---

title: Image processing device for determining whether or not an application is executable based on whether or not an API is available and a computer-readable medium storing a program
abstract: Referring to contents of a user information storage, an MFP information storage, an API information storage and the like, whether or not an API is available is determined, an unexecutable function of an application due to unavailability of the API is determined, and a display way for displaying a list of applications on a display is switched
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08570539&OS=08570539&RS=08570539
owner: Konica Minolta Business Technologies, Inc.
number: 08570539
owner_city: Chiyoda-Ku, Tokyo
owner_country: JP
publication_date: 20070824
---
This application is based on Japanese Patent Application No. 2006 290573 filed with the Japan Patent Office on Oct. 26 2006 the entire content of which is hereby incorporated by reference.

The present invention relates to an image processing device and a computer readable medium storing a program.

In a case where an application is installed in an image processing device capable of newly installing the application including a plurality of functions when the application operates in the image processing device the relevant application often calls an API Application Programming Interface for utilizing a prepared function of the image processing device. In such a case a configuration in which an available API is restricted is disclosed in US2006 0287962A1.

When an available API and an unavailable API exist together although a case where unavailability of an API disables an application to be executed may occur a user cannot know it until he or she actually operates the application. Thus there is a problem in that seen from the user s viewpoint it may be recognized by mistake as a trouble that the application does not operate properly.

Therefore an object of the present invention is to provide an image processing device capable of easily determining whether or not an application is executable based on whether or not an API is available and a computer readable medium storing a program.

An image processing device according to an aspect of this invention comprises an application acquiring unit for acquiring an application program including a plurality of functions an information acquiring unit for acquiring an information on a relation between the plurality of functions and application programming interfaces APIs which each of the plurality of functions is able to call a determining unit for determining whether or not the APIs are available to said functions and an indicating unit for indicating to a user unexecutability of the function due to unavailability of the APIs to the function when the determining unit determines the APIs are not available to the function.

Preferably the indicating unit indicates to the user that the application is unexecutable when all of the plurality of functions are unexecutable.

Preferably the determining unit determines whether or not the APIs are available to the functions by referring to information on the user logging into the image processing device.

Preferably the determining unit determines whether or not the APIs are available to the functions by referring to information on the image processing device.

More preferably the information on the image processing device includes information on a content set to the image processing device.

Furthermore more preferably the information on the image processing device includes information on a state of the image processing device.

Preferably the information acquiring unit externally acquires a file retaining the information on the relation.

Preferably the indicating unit switches an indication way between a case where the application is executable and a case where part of the functions are unavailable.

According to another aspect of this invention there is provided a computer readable medium storing a program the program being installed in an image processing device including a processor to make the processor execute processing of acquiring an application program including a plurality of functions processing of acquiring an information on a relation between the plurality of functions and application programming interfaces APIs which each of the plurality of functions is able to call processing of determining whether or not the APIs are available to the function and processing of indicating to a user unexecutability of the function due to unavailability of the APIs to the function when the determining unit determines the APIs are not available to the function.

According to the image processing device of the present invention execution validity or invalidity of the application due to whether or not the API is available can be easily determined.

The foregoing and other objects features aspects and advantages of the present invention will become more apparent from the following detailed description of the present invention when taken in conjunction with the accompanying drawings.

Next a configuration of MFP is described. is a diagram showing one example of a hardware configuration of MFP .

MFP comprises an operating unit a display a scanner unit a printer unit a communication interface a document feeder a paper feeding device a CPU a ROM a RAM a hard disk and the like.

Operating unit includes a plurality of keys for inputting numeral characters letters signs and the like a sensor that recognizes a pressed key a transmission circuit that transmits a signal indicating the recognized key to CPU and the like.

Display displays a screen that displays a message to a user a screen for the user to input setting contents and processing contents a screen showing a result of processing executed in MFP and the like. In the present embodiment a touch panel making up part of operating unit is provided on display . The touch panel has a function of sensing a position on the touch panel that the user has touched with his or her finger and transmitting a signal indicating a sensing result to CPU .

Scanner unit reads an image drawn in a manuscript with a predetermined reading resolution by irradiating the manuscript with light to detect reflected light and generates digital image data in this case concentration data indicating concentrations of RGB or black .

The obtained image data is used for printing in printer unit and in addition is converted into a file in a format of TIFF PDF JPEG and the like to be stored in hard disk . It may be also converted into FAX data to be FAX transmitted. Moreover as described before it may be attached to a mail to be transmitted outside. Document feeder is provided for example on the top of a body of MFP and is used to feed one or a plurality of sheets of manuscript to scanner unit sequentially.

Printer unit prints an image read in scanner unit an image of data transmitted from an external device such as another MFP which is connected through the network such as a LAN or an image of FAX data received over FAX on a recording sheet such as paper or a film.

Paper feeding device is provided for example in the bottom of the MFP body and is used to supply the recording sheet to printer unit . The recording sheet on which the image is printed by printer unit is discharged for example onto a catch tray.

Communication interface is an interface for performing communication with an external device such as PC and a mail server through the network such as the LAN and a WAN or performing FAX transmission and reception through a telephone line. As communication interface for example an NIC Network Interface Card a TA Terminal Adapter and the like can be used.

In ROM programs and data for realizing reading of an image scanning copying of a manuscript transmission and reception of FAX data network printing and basic functions of MFP such as a document server box function are stored. In addition programs and data that realize the functions of the present embodiment are stored.

A part or whole of these programs or data may also be installed in hard disk in advance. In this case the programs and data installed in hard disk are loaded on RAM as necessary.

The functions described in the present embodiment can also be realized by using not only CPU but also a dedicated hardware or part of them can also be realized by utilizing a function of a general purpose program of an operating system OS and the like.

As to corresponding relations between and the present invention application acquiring unit corresponds to an application acquiring unit application information management unit corresponds to an information acquiring unit and determining unit and UI display and display correspond to an indicating unit .

Application acquiring unit downloads an application from PC to install in MFP . The installed application calls the API prepared in MFP to realize the function.

Application information management unit manages various types of information on the application stored in hard disk . UI display controls display contents of user interface screens onto display .

The above described file of the API list is stored in function information storage as a file in an XML format in the present embodiment. is a diagram showing one example of contents of the file of the API list and for each application a plurality of functions and the API called for realizing the relevant function are defined. In the example of this figure and a function of accounting table printing and a function of accounting table registration are illustrated and the API called when each of the functions is utilized is described. This API list can be prepared in advance and be acquired for example from a download destination when the application is downloaded.

In Y indicates that the relevant API is related to each of the functions and N indicates no relation. Moreover a case where U is set means that whether or not the API is available is determined with reference to the user information. Since the upper limit of the number of sheets to be printed varies depending on the user U is set. Moreover a case where MS is set means that whether or not the API is available is determined with reference to the MFP setting information in the example of setting of security strengthening mode .

The API related state information indicates a related state state of the MFP . for each API. For example it is indicated that for determination as to whether or not an API CreateBox is available a state of the hard disk is referred to. Obviously the API related function information and the API related state information are not limited to the items defined above.

Execution invalidity information storage stores information on the unavailable API the functions of the application which cannot be executed due to unavailability of the API and the like from the information on the respective units described above. This execution invalidity information will be described in detail later.

Hereinafter the processing contents of MFP of the present embodiment are described. is a flowchart for explaining one example of the processing contents of MFP . The processing explained by the flowchart in the present embodiment is realized by CPU executing a program corresponding to the processing.

When the list display of the applications is instructed S YES CPU first acquires a user ID of a user logging into MFP at this point S . There is possibility that the user using MFP has not passed through user authentication and in this case for example a user ID that any user can use such as Guest can be given in advance.

Next referring to the contents of user information storage CPU acquires the user information S . The user information can be registered in user information storage in advance through operating unit or the like. Next the CPU acquires the MFP information stored in MFP information storage S . Then CPU performs execution validity invalidity determining processing S .

In the execution validity invalidity determining processing CPU first acquires the API to be used and parameter setting for each application S . This information acquisition can be performed with reference to the contents of the file in the XML format as one example in the present embodiment of the API list illustrated in .

CPU then acquires API related functions S . In this case the API related functions are functions described in tags in the API list of . As shown in since the API to be called is associated with the related functions the related functions can be acquired from the API acquired in step S.

Next referring to the user information illustrated in and the API related function information and the API related state information illustrated in CPU extracts the unexecutable API based on the user information S . For example in the API CreateJob in since U is set for the upper limit management in the API related function information with reference to the user information if it is found that the actual number of printed sheets which is retained as the user information has reached the upper limit the relevant user can no longer execute printing processing. Thus the API CreateJob is unavailable.

Moreover for CreateBox referring to the API related state information since it is found that the scanner state is related if the user is not given scanner authority the relevant API is also unavailable. If after the unexecutable API is extracted in this manner some unexecutable API is found to exist S YES CPU writes the execution invalidity information into execution invalidity information storage S . are diagrams for explaining one example of the contents of execution invalidity information storage .

In execution invalidity information storage unexecutable API information as shown in and unexecutable function information as shown in are stored. In the above described step S the unexecutable API information is written. In the present embodiment at this time a reason for execution invalidity e.g. the number of printed sheets reached the upper limit is stored together. This reason is utilized for execution validity invalidity indication to the user by the display onto display as will be described later.

Next the extraction of the unexecutable API based on the MFP information is performed S . As illustrated in the MFP information includes the MFP setting information and the MFP state information and in this case referring to both of them the unexecutable API is extracted. For example if address book setting is prohibited the API performing the address book setting cannot be executed and if a state of hard disk is not ready the API accessing the hard disk cannot be executed. Thus also referring to the MFP state the unexecutable API is extracted.

If there exists any unexecutable API based on the MFP information S YES CPU writes the unexecutable API information into execution invalidity information storage as in step S S . The processing goes to a flowchart of and when the extraction of all the unexecutable APIs is finished S YES CPU extracts an unexecutable function due to the existence of the unexecutable API S .

If there exists any unexecutable function S YES CPU writes the unexecutable function information into execution invalidity information storage S . As a result the unexecutable function information as illustrated in is written.

When for all the applications whose application information as illustrated in is registered the extraction of the unexecutable functions is finished S YES CPU determines whether or not an application all the functions of which are unexecutable exists S . If there exists any application all the functions of which are unexecutable S YES CPU registers the relevant application as the unexecutable application S . This processing is also enabled for example in a form of setting an execution invalidity flag in the table of .

As described above the execution validity invalidity determining processing is finished and CPU returns to the processing in the flowchart of to perform the application list display S . In this processing the list of the applications is displayed on display . is a diagram showing one example of a state where the list of the applications is displayed.

As shown in this figure in the application list display of the present embodiment for the application all the functions of which are executable in the example of this figure bookshelf the application part of the functions of which are unexecutable in the example of this figure accounting table management and easy setup and the application all the functions of which are unexecutable in the example of this figure home page printing a way of the display is switched and the unexecutable functions are indicated. This switching of the display can be performed with reference to the unexecutable function information. The application all the functions of which are unexecutable in is preferably configured so as not to be activated even when a relevant button is pressed and may be configured such that the relevant button itself is not displayed.

As described above according to the present embodiment in the application list display since not only the application which is unexecutable is displayed in such an unselectable manner but also it can be easily identified that the functions which cannot be executed due to unavailability of the API exist a situation can be prevented from occurring for example in which even if the user attempts to activate the function during operating the application the function does not operate so that the user has trouble addressing this. Moreover the determination as to whether or not the API is available can be performed while reflecting the dynamically changing state so that fixed setting values need not be reset each time.

While the embodiment of the present invention has been described above it is obvious that the contents of the present invention are not limited by the specific examples explained in the above embodiment and for example the following modification can be also carried out.

Namely while in the above described embodiment a case where the application is installed from PC has been described the installation of the application can also be executed from a CD ROM a DVD ROM a USB memory and other various media and in any case the present invention can be applied.

Moreover while in the above described embodiment the execution validity invalidity determining processing is performed when the application list display is instructed the execution validity invalidity determining processing may be performed as needed after the application is launched. In this case more precise execution validity invalidity determination against the dynamic state change can be performed.

Although the present invention has been described and illustrated in detail it is clearly understood that the same is by way of illustration and example only and is not to be taken by way of limitation the spirit and scope of the present invention being limited only by the terms of the appended claims.

