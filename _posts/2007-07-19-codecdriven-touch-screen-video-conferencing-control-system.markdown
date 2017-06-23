---

title: CODEC-driven touch screen video conferencing control system
abstract: A CODEC-driven touch screen video conferencing control system provides a touch screen entry and display device that interfaces with the CODEC of the existing video conferencing system so that remote operation is compatible with the pre-programming of the video conferencing system. A computer with video capture device captures the output video of the video conferencing CODEC and transmits it to the touch screen so that what is displayed on the touch screen is all of the controls for the video conferencing system as pre-programmed by the video conferencing system manufacturer. There is no requirement to employ a cursor on the video conferencing monitor screen. In fact, through use of the present invention, none of the control functions of the video conferencing system appear on its monitor screens. Rather, those functions are solely displayed on the touch screen of the remote control device.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08358327&OS=08358327&RS=08358327
owner: 
number: 08358327
owner_city: 
owner_country: 
publication_date: 20070719
---
The present invention relates to a CODEC driven touch screen video conferencing control system. In the prior art video conferencing systems customarily include a coder and decoder described as the CODEC which performs the functions of compaction of video signals to a volume that can be transmitted and de compaction of video signals to a volume that can be displayed. Output of the CODEC typically determines the look and feel of the display screens or monitors of the video conferencing system.

Known video conferencing systems generally fall into two categories. In a first category control is carried out through the use of a dumb handheld remote control device. Other video conferencing systems may also utilize a touch screen entry and display device backed by an appliance such as a personal computer that has intelligence and is capable of being programmed. In the former case where a dumb handheld remote control device is employed the remote control device typically has buttons that when depressed transmit command codes or information in the form of numbers and letters via infra red methodology to a CODEC. Such remote control devices do not have intelligence and are only able to perform actions specifically dictated as a result of depression of specified buttons.

In the latter type of prior art video conferencing system a touch screen is used for control but the touch screen is typically an after market product that has its own unique screen programming that does not relate to the screen programming provided by the video conferencing device manufacturer. Such touch screen control systems are driven by programs that reside in an intelligent appliance such as a personal computer. They present touch screen control screens of their own creation and design rather than those of the manufacturer of the video conferencing system. As a result there is no actual or implied consistency from system to system because the programmer of the touch screen device is free to implement control screens in any way or manner he or she chooses without regard to the look and feel of the video conferencing system on which the touch screen is operating. Additionally in such installations the regions on the touch screen corresponding to functions of the manufacturer s controls are typically displayed on one of the system monitors as well although sometimes the prior art touch screen is designed to suppress those control displays.

It would be desirable to develop a control system for a video conferencing system that would be compatible with the video conferencing system and act upon the video conferencing system s pre programmed screen look and feel to enhance compatibility and effectiveness of operation. It is with this thought in mind that the present invention was developed.

The present invention relates to a CODEC driven touch screen video conferencing control system. The present invention includes the following interrelated objects aspects and features 

 1 In a first aspect of the present invention it is intended to provide a touch screen entry and display device that interfaces with the CODEC of the existing video conferencing system so that remote operation is compatible with the pre programming of the video conferencing system.

 2 In accordance with the teachings of the present invention the inventive touch screen captures the output video of the video conferencing CODEC so that what is displayed on the touch screen is all of the controls for the video conferencing system as pre programmed by the video conferencing system manufacturer.

 3 In an important aspect of the present invention since the present invention is the first to capture the control screens of the CODEC manufacturer the control process is the same for all systems in accordance with the teachings of the present invention as it is for all manufacturer supplied video conferencing systems.

 4 Thus every system in accordance with the teachings of the present invention has the same look and feel and operation as any other system since it uses the same control screens and processes as the CODEC manufacturer created systems.

 5 In a further aspect in accordance with the teachings of the present invention there is no requirement to employ a cursor on the video conferencing monitor screen. In fact through use of the present invention none of the control functions of the video conferencing system appear on its monitor screens. Rather those functions are solely displayed on the touch screen of the remote control device.

Accordingly it is a first object of the present invention to provide a CODEC driven touch screen video conferencing control system.

It is a further object of the present invention to provide such a system in which the screen display of the existing video conferencing system is captured and displayed on the touch screen remote control.

It is a yet further object of the present invention to provide such a system in which function displays are no longer displayed on the monitor screens of the video conferencing system.

It is a still further object of the present invention to provide such a system in which use of a cursor on the video conferencing monitor screens is no longer required.

These and other objects aspects and features of the present invention will be better understood from the following detailed description of the preferred embodiment when read in conjunction with the appended drawing figures.

Reference is first made to . With particular reference to the typical video conferencing system known in the art is generally designated by the reference numeral . The system includes a camera supplying signals to a CODEC which supplies audio video signals to the monitors and . The CODEC may also be supplied with signals from a VCR a DVD player recorder a document camera and an external personal computer . As understood by the double headed arrows between the CODEC and the VCR and DVD player recorder the VCR and DVD player recorder may be used to play programming to be displayed on the monitors and control signals can be sent from the CODEC to the VCR and DVD player recorder. The VCR may be used to record programming from the CODEC .

With further reference to the CODEC has a port from which capture video may be obtained. Additionally the CODEC has an additional port from which API communications are obtained. API is an abbreviation for Application Programming Interface. This interface accessed via the port permits the present invention to communicate with the CODEC so that the present invention can provide the CODEC with a desired series of commands and receive responses from the CODEC .

With further reference to the components of the present invention are generally designated by the reference numeral and are seen to include the touch screen remote control a personal computer and a video capture board . As seen the personal computer has a port to which is coupled a conductor coupled to the API communications port of the CODEC . The video capture device has a port that is connected to the capture video port of the CODEC by the conductor .

The video capture device under control of the personal computer provides captured video signals to the touch screen via a port . When a user touches the screen of the touch screen the x and y location coordinates corresponding to the location of touching are transmitted via the port and the conductor to a port on the personal computer .

As should be understood the personal computer is pre programmed with data that corresponds each set of x and y location coordinates corresponding to a function of the video conferencing system related to the location of control of that function on the touch screen . In other words the touch screen is provided the pattern that would normally be displayed on the monitors and which pattern includes buttons corresponding to a variety of functions of the video conferencing system as better explained with reference to . In accordance with the teachings of the present invention those buttons are no longer displayed on the monitors and but rather are now solely displayed on the screen of the touch screen .

The S Video of the monitor or output which contains the control information in a manufacturer supplied handheld remote controlled system is routed from the CODEC to a video capture device which then places the image into a Capture Region as defined by a program on the PC appliance program cropping and scaling the image as necessary as understood by those of ordinary skill in the art.

When the user logs in the CODEC Dynamic Link Library DLL is designed to cause loading of a Screen Behavior Definitions file from the PC . This file enumerates all navigable screens in the system and defines XY coordinate information for each region on the screen.

When the user touches the Capture Region of the touch screen the User Interface Module in the touch screen system sends the coordinates of that touch to the PC for analysis.

The PC cross references the XY coordinates against the current screen and then takes appropriate action.

A Command is a raw CODEC API command. These are generally things like screen jumps or other direct orders to the CODEC .

An Action involves invoking a general purpose subroutine there are several such subroutines available to determine what should actually happen. Arguments can be specified in the Action Statement to ensure proper behavior. Generally actions verify a CODEC state before completing or do additional command processing.

The display pattern is provided to the video capture device from the port of the CODEC and provided to the touch screen via the port . Thus when a region on the screen is touched by the user the coordinates corresponding to that touching are transmitted to the personal computer via the conductor and thence via the port conductor and port to effectuate control of a variety of functions on the monitors and via the CODEC as well as the conductors and .

As explained above in accordance with the teachings of the present invention use of a cursor on the screens and is eliminated. There is no further need to line up a cursor with a region on one of the screens and and press an enter button as is the case in the prior art system illustrated in . The regions on the screens and no longer exist only the screen of the touch screen has the regions thereon with the functions of the system represented in those regions.

In accordance with the teachings of the present invention the screen includes two general areas a center rectangle that displays the exact output of the CODEC and a four sided periphery that contains control buttons for activating attendant audio video devices such as the camera VCR DVD document camera and external PC as well as control commands for CODEC operation. Additionally an area on the screen is provided to facilitate display of status information about conditions of the system. Ports and are provided to connect the touch screen to associated sub systems of the present invention and the video conferencing system .

As compared to the prior art in accordance with the teachings of the present invention the inventive system captures the exact video output of the CODEC and also inputs to the CODEC a duplication of the output of the manufacturer s handheld remote device. In this way operation is always precisely the same as designed by the manufacturer of the CODEC . Every implementation of the system remains consistent as compared to prior art devices in which the touch screen remote control does not operate based upon the programming of the CODEC but rather based upon the programming of the remote control device.

In more detail the personal computer is capable of executing logical instructions written in a computer programming language. The PC controls operation of the video conferencing system with a video capture device via a PCI or other appropriate bus physically installed in the PC with the CODEC via a RS232 serial connection schematically represented in FIG. Communications are commands that go back and forth between the port of the PC and the port of the CODEC. As should be understood these communications conform to the manufacturer s Application Programming Interface API of the CODEC .

Communications also occur using the touch screen via a serial communications link shown in and designated by the reference numeral for the conductor and and for the ports. As explained above when the present invention is employed there is no cursor displayed on the monitor screens and . Rather the touch screen acts as a mouse in that when a region on the screen is touched the x and y coordinates of that location of touching are transmitted to the PC via the conductor and as the PC is pre programmed appropriate control signals are sent to the CODEC via the conductor . If desired the PC may be programmed such that when a region on the touch screen is touched a display is provided asking the user to touch the screen again to verify the operation.

In summary the PC executes a unique set of computer programs which initiate and control all actions of the video conferencing system . Logic includes 

If desired the PC software may include unique password and security controls to prevent tampering. An important key to the present invention is the fact that the PC operates the video conferencing system via the video conferencing system s own CODEC through the CODEC s API.

With reference to all communications between the PC and the CODEC follow a similar procedure. With reference to when the user touches the screen this causes the user to be logged on to the system . Thereafter the video capture board captures the video from the CODEC .

Next the video capture board sends the video from the CODEC to the touch screen via the port conductor port and port on the touch screen system .

As pre programmed by the PC once the CODEC video has been received by the touch screen system the system overlays the screen with x and y coordinates corresponding to each region of the screen where a function will be initiated by touching that region.

Thereafter when a user desires to cause a function to be initiated the user touches the touch screen at the desired region to indicate the desired action. Responsive to that touching the touch screen system transmits the x and y coordinates of the touched area to the PC via the port conductor and port . A look up table pre programmed in the memory of the PC correlates the x and y coordinates received by the PC with the desired action. Responsive thereto the PC transmits API code via the port conductor and port to the CODEC . The CODEC echoes back to the PC via the same transmission path indicating receipt of the transmission and then the CODEC performs the desired action via one of its ports and associated conductors.

The CODEC then sends an action completed signal to the PC via the port conductor and port . Once the action has been completed in the manner described above the PC awaits indication of the next touch of the screen by the user.

To understand the importance of the present invention it is instructive to contrast its operation with that of the prior art manufacturer supplied handheld control device. The present invention essentially duplicates the actions of the CODEC manufacturer s handheld remote device. In the manufacturer s version of a video conferencing system the control screens with graphics indicating a desired action are displayed on the same device e.g. a television screen that is used for viewing the video conference.

The prior art handheld remote device is pointed at the viewing device e.g. a television screen and an appropriate button on the handheld remote device is pressed. An infra red signal is transmitted to the CODEC indicating the location of the graphic symbol on the viewing device and therefore the desired action. Because the handheld remote device is dumb lacks logical intelligence the sequence and logicality of the action must be determined by the user i.e. there are no logical checks or possibilities of second chances. The CODEC remote device similar to virtually all handheld remote devices is not easy to operate and is not intuitive. Often prior art devices require use of a cursor on the monitor screens moved by the remote control to a desired region then activated by a click. The following describes the actions of the present invention.

In the present invention the control screens do not appear on the same viewing device e.g. a television screen as is used for viewing the video conference. Instead the video of the control screen is captured by the video capture device Item and transmitted to the touch screen display item . The PC also performs another function. It transmits a screen full of information to the CODEC for display on the viewing device e.g. a television screen that displays the far site location in a video conference. This screen of information which originates in the PC obscures the far site from vision until it is dismissed by the local user via the touch screen. It is employed for reasons of security i.e. to not permit viewing of the far site until approval is granted .

The CODEC is a coder decoder device manufactured by several different manufacturers. It is the central portion of a video conferencing system . It essentially performs all the intelligent actions of a video conferencing system with the exception of control. It determines what video source camera VCR DVD Document Camera Personal Computer is displayed on the viewing devices establishes communications with the remote site s and accepts action commands and performs the requested action e.g. place a video call display a list of contacts display a VCR etc. .

In the present invention how the touch screen remote control invention works is described rather than how the CODEC works. The contents of the CODEC screens and the functions a CODEC performs are not centrally pertinent. What is pertinent is how the PC interfaces with the CODEC how API commands are processed how commands are sent to and received from the CODEC etc. Of special importance is what is done differently from everyone else i.e. capturing the CODEC video screens overlaying them with x and y coordinates transmitting control codes from the touch screen to the PC and transmitting messages from the PC to the touch screen .

The touch screen system is comprised of an LCD screen or other video display technology CRT Plasma etc. that can be of varying sizes. In addition to the display screen the touch screen contains hardware that overlays the screen with a matrix of x and y coordinates. When the touch screen display is touched it transmits a mouse click representing the x and y coordinates of the screen area to the PC . The PC logic recognizes the location by virtue of a programmed look up table and therefore the implied control symbol to be activated. The PC transmits a code which conforms to the API protocol of the CODEC to the CODEC via port conductor and port . The CODEC then executes the desired command.

The periphery of the touch screen is lined with command and information rectangles on all four sides. These rectangles are always located in the same spots and always operate in a specific manner. The screen periphery is preferably comprised of four command areas 

When the system is engaged in a call over a transmission line an additional Network Statistics button is displayed. Pressing this button permits the user to view several pages of network statistics directly from the CODEC .

There can be more than one camera involved in a given system determined at system set up time . Camera control is comprised of six buttons 

Pressing one of these buttons activates that video source. It is displayed on one of the viewer s devices and remotely if in a call.

The Video Source buttons are used to request the connection to the desired video source. Typical video conferencing systems display two views 

Pressing and holding the Volume Up or Down buttons increases or decreases the audio until released. The Mute Unmute buttons either turn off or turn on the microphone or speaker sound.

As such an invention has been disclosed in terms of a preferred embodiment thereof which fulfills each and every one of the objects of the invention as set forth hereinabove and provides a new and useful CODEC driven touch screen video conferencing control system of great novelty and utility.

Of course various changes modifications and alterations in the teachings of the present invention may be contemplated by those of ordinary skill in the art without departing from the intended spirit and scope thereof.

As such it is intended that the present invention only be limited by the terms of the appended claims.

