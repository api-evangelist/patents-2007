---

title: Broadcast signal processing apparatus and control method thereof
abstract: A broadcasting signal processing apparatus includes: a signal receiver which receives a broadcasting signal, the broadcast signal including an application program for providing broadcasting information; a signal processor which processes the broadcasting signal so that a video is displayed based on the broadcasting signal received by the signal receiver; and a controller which controls the signal processor so that execution of the application program is paused and the video is adjusted if an adjustment condition of the video being displayed is satisfied while the application program is executed.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08015579&OS=08015579&RS=08015579
owner: Samsung Electronics Co., Ltd.
number: 08015579
owner_city: Suwon-si
owner_country: KR
publication_date: 20071003
---
This application claims priority from Korean Patent Application No. 10 2007 0004379 filed on Jan. 15 2007 in the Korean Intellectual Property Office the disclosure of which is incorporated herein by reference.

Apparatuses and methods consistent with the present invention relate to a broadcasting signal processing apparatus and a control method thereof and more particularly to a broadcasting signal processing apparatus that executes an application program included in a broadcasting signal and a control method thereof.

A broadcasting signal processing apparatus such as a TV or a set top box receives a broadcasting signal from a broadcasting station and processes the broadcasting signal so that a video is displayed based on the broadcasting signal.

The broadcasting signal may include an application program that provides various broadcasting services such as data broadcasting and that broadcasts information. For example the application program may include a Java application that is defined in digital TV broadcasting specifications such as OpenCable Application Platform OCAP Advanced Common Application Platform ACAP and Multimedia Home Platform MHP .

Such an application program is downloaded to the broadcasting signal processing apparatus through the received broadcasting signal and the broadcasting signal processing apparatus provides various broadcasting information by executing the downloaded application program.

However the broadcasting signal processing apparatus can perform only the functions provided by the application program during execution of the application program. That is if a user desired function is not included in the application program in advance the broadcasting signal processing apparatus cannot perform the user desired function during execution of the application program.

Hereinafter detailed descriptions will be given with examples. The broadcasting signal processing apparatus provides broadcasting information by displaying a graphical user interface GUI of an application program. shows a screen where a GUI of an application program is displayed by a broadcasting signal processing apparatus.

When the application program is executed a broadcasting signal video hereinafter will be referred to as video can be displayed on an upper left portion of the screen and the GUI of the application program can be displayed on the other portion of the screen .

In this case a user may want to display the video which is displayed on only a portion of the screen over the full screen. However when the application program does not have a function that allows adjusting of the size of the video the application program must be terminated in order to adjust the size of the video while the application program is being executed.

In addition when a user wants to use broadcasting information of the terminated application program the application program needs to be restarted. In this case the previous execution information of the application program is lost. Therefore previous operations must be performed again in order to use the broadcasting information.

The above information disclosed in this Background section is only for enhancement of understanding of the background of the invention and therefore it may contain information that does not form the prior art that is already known in this country to a person of ordinary skill in the art.

The exemplary embodiment of the present invention overcomes the above disadvantages and other disadvantages not described above. Also the present invention is not required to overcome the disadvantages described above.

Accordingly the exemplary embodiment provides a broadcasting signal processing apparatus and a control method that performs a user desired function without terminating an application program.

Particularly the exemplary embodiment provides a broadcasting signal processing apparatus and a control method that more conveniently performs a user desired function during execution of an application program.

The foregoing and or other aspects of the present invention can be achieved by providing a broadcasting signal processing apparatus comprising a signal receiver which receives a broadcasting signal the broadcast signal including an application program for providing broadcasting information a signal processor which processes the broadcasting signal so that a video is displayed based on the broadcasting signal received by the signal receiver and a controller which controls the signal processor so that execution of the application program is paused and the video is adjusted if an adjustment condition of the video being displayed is satisfied while the application program is executed.

According to an aspect of the invention the broadcasting signal processing apparatus further comprises a user input unit to which a user s instruction to adjust the video is input wherein the controller determines that the adjustment condition of the video being displayed is satisfied when the user s instruction is input.

According to an aspect of the invention the user input unit comprises a remote controller or a control panel the remote controller or control panel including at least one button and wherein the controller determines that the user s instruction is input when the at least one button is pressed.

According to an aspect of the invention the controller changes a current state of the application program from an execution state to a pause state by calling a function of the application program that pauses the execution of the application program.

According to an aspect of the invention adjustment of the video includes adjusting a size of the video.

According to an aspect of the invention the broadcasting information comprises a graphic user interface GUI that displays the broadcasting information.

According to an aspect of the invention the controller resumes execution of the paused application program.

According to an aspect of the invention the broadcasting signal processing apparatus further comprises a user input unit to which a user s instruction to resume the paused application program is input wherein the controller resumes the paused application program when the user s instruction is input.

According to an aspect of the invention the controller controls the signal processor so that the video is restored prior to adjustment if the application program is resumed.

According to an aspect of the invention the controller calls a function of the application program that changes a current state of the application program from a pause state to an execution state in order to resume the paused application program.

According to an aspect of the invention the broadcasting signal processing apparatus further comprises a display unit which displays a video based on the broadcasting signal processed by the signal processor.

The foregoing and or other aspects of the present invention can be achieved by providing a control method of a broadcasting signal processing apparatus having a signal receiver that receives a broadcasting signal the broadcasting signal including an application program for providing broadcasting information and a signal processor that processes the broadcasting signal so that a video is displayed based on the broadcasting signal received by the signal receiver the control method comprising determining whether an adjustment condition of the video being displayed is satisfied while the application program is executed pausing the execution of the application program if the adjustment condition of the video being displayed is satisfied and controlling the signal processor so that the video being displayed is adjusted while the application program is paused.

According to an aspect of the invention the control method further comprises receiving a user s instruction for adjusting the video wherein it is determined that the adjustment condition of the video being displayed is satisfied if the user s instruction is input.

According to an aspect of the invention the pausing of the execution of the application program comprises calling a function of the application program so as to change a current state of the application program from an execution state to a pause state.

According to an aspect of the invention the adjustment of the video comprises adjusting a size of the video.

According to an aspect of the invention the providing of the broadcasting information comprises displaying a graphic user interface GUI for the broadcasting information.

According to an aspect of the invention the control method further comprises resuming the execution of the paused application program.

According to an aspect of the invention the resuming of the execution of the paused application program comprises receiving a user s instruction for resuming the execution of the paused application program and resuming the execution of the paused application program if the user s instruction is input.

According to an aspect of the invention the resuming of the execution of the paused application program further comprises controlling the signal processor so that the video is restored prior to adjustment.

According to an aspect of the invention the resuming of the execution of the paused application program further comprises calling a function of the application program so as to change a current state of the application program from a pause state to an execution state.

Reference will now be made in detail to an embodiment of the present invention examples of which are illustrated in the accompanying drawings wherein like reference numerals refer to like elements throughout. The exemplary embodiment is described below so as to explain the present invention by referring to the figures.

Hereinafter the exemplary embodiment of the present invention will be described in detail with reference to the accompanying drawings.

The broadcasting signal processing apparatus may be a TV or a set top box that receives a broadcasting signal from a broadcasting station and processes the received signal so that a video is displayed based on the received broadcasting signal.

The broadcasting signal includes an application program that provides various broadcasting information such as data broadcasting. Such an application program can be provided as a Java application defined in a specification associated with digital TV broadcasting such as OpenCable Application Platform OCAP Advanced Common Application Platform ACAP and Multimedia Home Platform MHP .

The broadcasting signal processing apparatus can adjust a video or perform other functions without terminating the application program that is currently being executed. For example the broadcasting signal processing apparatus can adjust the size of the video according to instructions of a user during execution of the application program.

In further detail as shown in the broadcasting signal processing apparatus includes a signal receiver that receives a broadcasting signal a signal processor that processes the received broadcasting signal so that a video is displayed based on the broadcasting signal and a controller that controls the signal processor so that execution of the application program is temporarily paused in order to adjust the video if at least one adjustment condition of the video being displayed is satisfied while broadcasting information is provided by the execution of the application program.

The signal receiver performs frequency tuning to one of a plurality of channels according to control of the controller and therefore receives the broadcasting signal.

The signal processor performs demultiplexing or decoding of the broadcasting signal received by the signal receiver . The signal processor adjusts the displayed video according to control of the controller .

When it is determined that the receiving of the application program by the signal receiver is completed the controller can start the application program. In this case as shown in the GUI of the application program can be displayed on the screen by the execution of the application program. The broadcasting information is provided through the GUI of the application program.

When adjustment conditions of a predetermined image are satisfied during the execution of the application the controller temporarily pauses the execution of the application program and controls the signal processor so that the video is adjusted.

The controller can control the signal processor so that for example the size of the video is adjusted. For example when the video is displayed on a portion of the screen together with the GUI of the application program the controller can control the signal processor so that the size of the video is adjusted. Therefore the video can be displayed over the entire screen as shown in .

The user can determine whether the adjustment conditions of the video are satisfied during the execution of the application program. That is the broadcasting signal processor may further include a user input unit that receives at least one instruction of the user to adjust the video. The controller can determine that adjustment conditions of the video being displayed are satisfied when the user s instructions are input through the user input unit .

Thus a user s preference can be better satisfied because the user is able to perform user desired video adjustment at a user desired time during execution of the application program.

The user input unit can be provided as a remote controller not shown having at least one button such as a hotkey or as a control panel not shown provided in the broadcasting signal processor . The controller determines that the user s instructions for video adjustment are input when a button of the remote controller or the control panel is pressed.

Therefore the user can perform a convenient user desired video adjustment with a simple key input like a hotkey during execution of the application program.

The controller can then resume the execution of the application program that has been temporarily paused after the video adjustment. If the execution of the application program is resumed the controller can control the signal processor so that the video of is restored to the original state of the video refer to video of prior to adjustment.

The controller can resume the temporarily paused application program when the user instructs the application program to resume through the user input unit . The instruction meaning resume execution of the application program can be input through a predetermined button of the user input unit such as a remote controller or a control panel.

A button corresponding to the user instruction for the application program resumption may be the same as the button corresponding to the user instruction for video adjustment during execution of the application program. That is whenever the button is pressed the video of and the video of can be alternatively displayed.

As described since the video can be switched from the after adjustment state to the before adjustment state and vice versa with a simple key input such as the hot key user convenience can be improved.

The controller can be software and hardware. is a block diagram of a configuration of software of the controller . The controller may include a host platform and a middleware both as software.

Referring to the controller may include a read only memory ROM as hardware for storing the host platform and the middleware a random access memory RAM for loading the stored host platform and the stored middleware and a central processing unit CPU for executing the host platform and the middleware that are loaded to the RAM . The application program can also be loaded to the RAM and executed by the CPU .

The host platform includes a device driver not shown that controls the broadcasting signal processing apparatus . When the application program is executed the middleware provides an application programming interface API for using functions of the host platform . The API serves as an interface between the host platform and the application program . The host platform and the middleware are programmed so that the CPU performs the above described operations of the controller .

Referring to execution pause and resumption of the application program will be described in detail. shows a diagram of the states of the application program . As shown in the states of the application program include a Loaded state a Paused state an Active state and a Destroyed state .

The Loaded state indicates that receiving of the application program has been completed by the signal receiver . The Paused state indicates that the application program has been initialized and is ready for execution. The Active state indicates that the initialized application program is being executed. The Destroyed state indicates that the application program has been terminated. The Paused state and the Active state are examples of a pause state and an execution state respectively in the present exemplary embodiment.

The application program has functions respectively corresponding to the states and . These functions are defined in the broadcasting specifications such as the OCAP and the MHP. That is the application program can be switched to the Paused state from the Loaded state by calling an initXlet function of the application program .

In addition the Paused state and the Active state can be executed by respectively calling pauseXlet and startXlet functions and the two states and can be switched to each other accordingly.

Further the application program in the Loaded state the Paused state or the Active state can be moved to the Destroyed state at any time by calling for example a destroyXlet function.

During execution of the application program the controller changes the current state of the application program from the Active state to the Paused state by calling the pauseXlet function so as to temporarily pause the execution of the application program .

In addition the controller changes the current state of the application program from the Paused state to the Active state by calling the startXlet function while the execution of the application program is paused. This resumes the temporarily paused application program .

Referring to the broadcasting signal processing apparatus may further include a display unit that displays images based on the broadcasting signals processed by the signal processor . The display unit may display images by using a liquid crystal display LCD or a plasma display panel PDP .

Subsequently the controller determines whether the user has input instructions for video adjustment at operation of S. The user s instructions may require maximization of the size of the video of to the size of the screen . The user s instructions may be input through a predetermined button on the user input unit such as a remote controller.

When it is determined at the operation of S that the user s instructions have been input the controller temporarily pauses the execution of the application program at operation of S. For example the controller changes the current state of the application program from the Active state to the Paused state by calling the pauseXlet function. This temporarily pauses the application program.

Next the controller controls the signal processor so that the video is adjusted according to the user s instructions at operation of S. For example the controller controls the signal processor so that the size of the video of is maximized and the video is displayed on the full screen as shown in . At operation of S the controller may hide the GUI of the application program shown in so as to fully display the video on the screen .

Next the controller determines whether user s instructions for restoring the video prior to adjustment are input at operation of S. That is the controller determines whether user instructions for resuming the application program are input at operation of S.

When it is determined at operation of S that the user s instructions for resuming the application program are input the controller controls the signal processor so that the video is restored to a before adjustment state at operation of S. Restoring of the video may indicate that the size of the video of is adjusted to the size of the video of .

Next the controller resumes the paused application program at operation of S. For example the controller calls the startXlet function of the application program in order to change the current state of the application program from the Paused state to the Active state . Thereby the paused application program is resumed.

When the application program is paused the GUI of the application program as shown in may be displayed. The operation order of the operation of S and the operation of S may be interchanged.

As described above a broadcasting signal processor and a control method of performing a user desired function without terminating an application program can be provided according to the exemplary embodiment of the present invention.

Particularly the user can adjust the video during execution of the application program so that the user does not need to terminate the application program in order to adjust the video.

In addition a user can be more satisfied by performing user desired video adjustment at user desired time during execution of the application program according to the exemplary embodiment of the present invention.

Further user convenience can be improved by allowing the user to adjust the video to a desired state with a simple key input like a hotkey.

Although an exemplary embodiment of the present invention has been shown and described it will be appreciated by those skilled in the art that changes may be made in this exemplary embodiment without departing from the principles and spirit of the invention the scope of which is defined in the appended claims and their equivalents.

