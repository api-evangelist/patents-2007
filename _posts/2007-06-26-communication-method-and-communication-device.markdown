---

title: Communication method and communication device
abstract: A request change unit outputs a command as a request under control of a judgment control unit. A response condition determination unit determines a condition that is to be matched by a correct response which is to be returned from the other device-in-communication in reply to the command if the other device-in-communication operates in conformity with a protocol. A check unit checks a response received from the other device-in-communication in reply to the command, against the condition. If the received response does not match the condition but is correctable to match the condition as a result of the check, a response correction unit corrects the received response to match the condition under control of the judgment control unit.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08074139&OS=08074139&RS=08074139
owner: The University of Tokyo
number: 08074139
owner_city: Tokyo
owner_country: JP
publication_date: 20070626
---
The present invention relates to communication techniques of sending receiving a request and a response between communication devices.

Nowadays communication devices such as personal computers and network appliances perform communication with other communication devices based on various protocols. For example communication between communication devices is performed by using various networks such as the Internet and a LAN Local Area Network or various hardware interfaces.

POP3 Post Office Protocol version 3 RFC 1939 is known as such a protocol that is used in communication between communication devices.

Communication between communication devices based on a protocol such as POP3 is conducted by one communication device sending a request and the other communication device returning a response to the request.

J. Myers RFC 1939 Post Office Protocol POP Version 3 online May 1996 IAB Internet Architecture Board standard recommendation RFC Request for Comments searched on Apr. 3 2006 .

In communication between communication devices based on a protocol such as POP3 if a response to a request has an error that is if data that does not conform to a procedure or format prescribed by the protocol is returned as a response a communication device that sends the request terminates communication processing for the occurrence of the error.

For instance in the case where the protocol is not implemented strictly in a communication device that receives the request or part of the implemented protocol contains a bug the communication device will end up returning a wrong response to the request. Whenever this happens error termination occurs in the communication between the communication devices.

The present invention was conceived in view of the above problem and aims to provide a communication method and a communication device that can suppress the occurrence of error termination in communication between communication devices as much as possible even when a wrong response is returned in reply to a request.

The stated aim can be achieved by a communication method used in a communication device that sends a request to an other communication device and receives a response to the request from the other communication device the communication method including a sending step of sending a command of the request to the other communication device a determination step of determining a condition that is to be matched by a correct response the correct response being to be sent from the other communication device in reply to the command if the other communication device operates in conformity with a predetermined protocol a check step of checking a response received from the other communication device in reply to the command against the condition determined in the determination step and a correction step of if the received response fails to match the condition in the check step correcting the received response to match the condition.

The stated aim can also be achieved by a communication device that sends a request to an other communication device and receives a response to the request from the other communication device the communication device including a sending unit operable to send a command of the request to the other communication device a determination unit operable to determine a condition that is to be matched by a correct response the correct response being to be sent from the other communication device in reply to the command if the other communication device operates in conformity with a predetermined protocol a check unit operable to check a response received from the other communication device in reply to the command against the condition determined by the determination unit and a correction unit operable to if the received response fails to match the condition as a result of the check by the check unit correct the received response to match the condition.

According to the above method and construction the response returned in reply to the command of the request is checked against the condition that is to be matched by the correct response which is to be returned from the other communication device if the other communication device operates in conformity with the protocol. If the response does not match the condition the response is corrected to match the condition. Thus by correcting the response returned in reply to the command of the request if the response has an error the occurrence of error termination in the communication which is caused by the existence of the error in the response returned in reply to the command of the request can be suppressed.

Here the communication method may further include a level reception step of receiving a restriction level for restricting the correction of the response wherein an execution level of the correction of the response is set in advance and the correction step is executed if the execution level exceeds the restriction level.

According to this method for example the user can decide whether or not to perform response correction that has a high degree of risk in terms of security.

The stated aim can also be achieved by a communication method used in a communication device that sends a request to an other communication device and receives a response to the request from the other communication device the communication method including a sending step of sending a command of the request to the other communication device a determination step of determining a condition that is to be matched by a correct response the correct response being to be sent from the other communication device in reply to the command if the other communication device operates in conformity with a predetermined protocol a check step of checking a response received from the other communication device in reply to the command against the condition determined in the determination step a replacement step of if the received response fails to match the condition in the check step specifying one or more alternative commands that substitute for the command and executing communication with the other communication device by using the one or more alternative commands sequentially and a generation step of generating a response that matches the condition based on a response received from the other communication device in reply to each of the one or more alternative commands.

The stated aim can also be achieved by a communication device that sends a request to an other communication device and receives a response to the request from the other communication device the communication device including a sending unit operable to send a command of the request to the other communication device a determination unit operable to determine a condition that is to be matched by a correct response the correct response being to be sent from the other communication device in reply to the command if the other communication device operates in conformity with a predetermined protocol a check unit operable to check a response received from the other communication device in reply to the command against the condition determined by the determination unit a replacement unit operable to if the received response fails to match the condition as a result of the check by the check unit specify one or more alternative commands that substitute for the command and execute communication with the other communication device by using the one or more alternative commands sequentially and a generation unit operable to generate a response that matches the condition based on a response received from the other communication device in reply to each of the one or more alternative commands.

According to the above method and construction the response returned in reply to the command of the request is checked against the condition that is to be matched by the correct response which is to be returned from the other communication device if the other communication device operates in conformity with the protocol. If the response does not match the condition one or more alternative commands that substitute for the command are used to communicate with the other communication device and the response that matches the condition is generated based on the response returned in reply to each alternative command. Thus if the response returned in reply to the command of the request has an error the communication with the other communication device is performed using one or more alternative commands and the response corresponding to the command is generated based on the response returned in reply to each alternative command. By doing so the occurrence of error termination in the communication which is caused by the existence of the error in the response returned in reply to the command of the request can be suppressed.

Here the communication method may further include a judgment step of if the received response fails to match the condition in the check step judging whether or not the received response is correctable to match the condition wherein the replacement step is executed if the received response is not correctable to match the condition in the judgment step and the received response is corrected to match the condition if the received response is correctable to match the condition in the judgment step.

According to this method if the response returned in reply to the command of the request is correctable to match the condition the response is corrected. Otherwise the communication using one or more alternative commands is performed. This makes it possible to suppress the occurrence of error termination in the communication which is caused by the existence of the error in the response returned in reply to the command of the request while reducing an increase in communication load between the communication devices.

Here the communication method may further include an alternative determination step of determining for each of the one or more alternative commands an alternative condition that is to be matched by a correct response which is to be sent from the other communication device in reply to the alternative command if the other communication device operates in conformity with the predetermined protocol and an alternative check step of checking the response received from the other communication device in reply to each of the one or more alternative commands against the alternative condition determined in the alternative determination step wherein if the response received in reply to each of the one or more alternative commands matches the alternative condition or is correctable to match the alternative condition in the alternative check step the one or more alternative commands are used instead of the command in subsequent communication.

According to this method if the response returned in reply to the command of the request does not match the condition one or more alternative commands that substitute for the command will be prioritized over the command in subsequent communication. This reduces an increase in communication load between the communication devices.

Here the communication method may further include an alternative determination step of determining for each of the one or more alternative commands an alternative condition that is to be matched by a correct response which is to be sent from the other communication device in reply to the alternative command if the other communication device operates in conformity with the predetermined protocol and an alternative check step of checking the response received from the other communication device in reply to each of the one or more alternative commands against the alternative condition determined in the alternative determination step wherein if a response received from the other communication device in reply to any of the one or more alternative commands fails to match an alternative condition determined for the alternative command and is not correctable to match the alternative condition in the alternative check step the replacement step is executed again.

According to this method the occurrence of error termination in the communication can be further suppressed by repeating the replacement step.

Here the communication method may further include a level reception step of receiving a restriction level for restricting the communication with the other communication device in the replacement step wherein an execution level of the communication by using the one or more alternative commands is set in advance and the communication with the other communication device by using the one or more alternative commands in the replacement step is executed if the execution level exceeds the restriction level.

According to this method for example the user can decide to what extent continued communication using one or more alternative commands that has a high degree of risk in terms of security is to be performed.

A construction of a communication system according to the first embodiment is described below with reference to . shows a system construction of the communication system according to the first embodiment.

The communication system includes communication devices and . The communication devices and are connected to a network . The network may be a local area network or a wide area network such as the Internet. Also the network may be a wired network or a wireless network.

The communication device has functions of executing a communication method according to the present invention and sends receives a request and a response to the request with the other communication device.

For example the communication device sends a command of a request to the other device in communication and receives a response from the other device in communication in reply to the command of the request. If the received response has an error depending on the error in the received response the communication device corrects the received response or performs communication with the other device in communication by using one or more alternative commands that substitute for the command.

One or more alternative commands referred to here i.e. one alternative command or one alternative command group that is composed of a plurality of alternative commands enable when the request source communication device receives an error free response in reply to each alternative command the communication device to generate an error free response corresponding to the command based on the error free response received in reply to each alternative command.

An error free response referred to here is a correct response that is to be returned from the other device in communication in reply to a command or an alternative command if the other device in communication operates in conformity with a predetermined protocol.

The communication device sends receives a request and a response to the request with the other communication device. The communication device may or may not have functions of executing the communication method according to the present invention.

The present invention relates to a construction in which when a response to a request has an error a communication device that sends the request performs correction of the response and the like depending on the error in the response. In view of this the following description of functions and operations of the communication device only concerns the case where the communication device sends a request.

A device construction of the communication device shown in is described below with reference to . shows the device construction of the communication device shown in .

The communication device includes a CPU Central Processing Unit a memory a DSP Digital Signal Processor an assist circuit a communication interface communication IF a display control circuit a display device an input interface input IF a keyboard a mouse and a tablet . The CPU the memory the DSP the assist circuit the communication IF the display control circuit and the input IF are each connected to a bus .

The memory is a storage element. For example various control programs for controlling the communication device and various application software are stored on the memory .

The communication IF is used for the communication device to perform communication with an external device. In this embodiment the communication IF is capable of sending receiving TCP IP Transmission Control Protocol Internet Protocol packets. As an example the communication IF is based on a standard such as Ethernet registered trademark a wireless network USB Universal Serial Bus UWB Ultra Wide Band Bluetooth registered trademark or the like.

The display device is a display unit such as a CRT Cathode Ray Tube a liquid crystal display and a plasma display or a light emitting element such as a LED Light Emitting Diode .

The input IF is used for connecting input devices such as the keyboard the mouse and the tablet to the CPU in the communication device via the bus . The input devices may also include a keypad a touch panel and the like.

The following describes a hierarchical structure for executing processing of the communication method according to the present invention hereafter referred to as adaptive communication processing in this embodiment with reference to . shows a hierarchical structure of the communication device shown in .

In detail shows an OSI reference model developed by ISO International Organization for Standardization that divides communication functions of a communication device for realizing inter device data communication into layers. also shows a TCP IP layer model that divides communication functions of a communication device for realizing inter device data communication into layers.

The OSI reference model has seven layers that are an application layer a presentation layer a session layer a transport layer a network layer a data link layer and a physical layer.

The TCP IP layer model has an application layer a transport layer an internet layer and a network interface layer.

The adaptive communication processing in this embodiment is located between POP3 and TCP Transmission Control Protocol or UDP User Datagram Protocol and relays communication between POP3 and TCP or UDP. Here POP3 is a processing target protocol.

Other than POP3 the processing target protocol may also be IMAP4 Internet Message Access version 4 HTTP Hyper Text Transfer Protocol FTP File Transfer Protocol SMTP Simple Mail Transfer Protocol UPnP Universal Plug and Play SIP Session Initiation Protocol RTP Real Time Transfer Protocol RTCP RTP Control Protocol and the like.

A functional construction of the communication device shown in is described below with reference to . shows the functional construction of the communication device shown in .

The communication device includes communication processing units and an adaptive communication processing unit a response condition database response condition DB a command database command DB a correction database correction DB an alternative database alternative DB and a response storage unit .

The communication processing unit is located at a higher layer of the adaptive communication processing unit . The communication processing unit performs processing in conformity with a standard of a protocol such as POP3 and sends receives commands and data with the adaptive communication processing unit . When inputting a command of a request into the adaptive communication processing unit the communication processing unit also inputs a device name of a request destination communication device into the adaptive communication processing unit together with the command.

The communication processing unit is located at a lower layer of the adaptive communication processing unit . The communication processing unit performs processing in conformity with a standard such as TCP or UDP and sends receives commands and data with the adaptive communication processing unit .

The adaptive communication processing unit is located between the communication processing units and and relays communication between the communication processing units and . Functions of the adaptive communication processing unit will be described in detail later.

The response condition DB stores a response condition corresponding to each command of a protocol such as POP3 and IMAP4. shows an example response condition corresponding to each command of POP3.

A response condition is a condition that is to be matched by a correct response which is to be returned from the request destination communication device in reply to a corresponding command if the request destination communication device operates in conformity with the protocol. If the response matches the response condition error termination will not occur in the communication based on the protocol of the higher layer such as POP3.

If a response returned in reply to a command of a request matches a response condition stored in the response condition DB in correspondence with the command the response is error free. If the response returned in reply to the command of the request does not match the response condition stored in the response condition DB in correspondence with the command the response has an error.

The command DB stores in correspondence with each command an alternative command or an alternative command group made up of a plurality of alternative commands as a substitute for the command. shows an example of this In an alternative command or an alternative command group that substitutes for a command stored in the field command is stored in the fields alternative command group 1 alternative command group 2 and alternative command group 3 . Note here that one command may have a plurality of alternative commands or a plurality of alternative command groups.

The correction DB stores a command or an alternative command of a request for which a response was corrected in past communication in correspondence with a request destination communication device. shows an example of this. In a command or an alternative command which was sent to a communication device having a device name stored in the field request destination and for which a response was corrected is stored in the field command .

By referring to the storage contents of the correction DB it is possible to recognize commands which other communication devices are unable to process properly.

The alternative DB stores an alternative command or an alternative command group that was used instead of a command in past communication in correspondence with the command and a request destination communication device. shows an example of this. The contents of the alternative DB are changed as appropriate while communication is being performed with another communication device. In an alternative command or an alternative command group that was used in past communication for a communication device having a device name stored in the field request destination instead of a command stored in the field command is stored in the field alternative command group .

By referring to the storage contents of the alternative DB it is possible to recognize commands which other communication devices are unable to process properly.

The adaptive communication processing unit functions as a request change unit a response condition determination unit a check unit a judgment control unit and a response correction unit .

The request change unit is controlled by the judgment control unit and outputs a command of a request received from the communication processing unit to the communication processing unit and the response condition determination unit or outputs an alternative command or each alternative command in an alternative command group stored in the alternative DB to the communication processing unit and the response condition determination unit .

The response condition determination unit extracts from the response condition DB a response condition corresponding to a command or an alternative command received from the request change unit to determine the response condition. The response condition determination unit outputs the determined response condition to the check unit .

The check unit checks a response received from the communication processing unit against the response condition received from the response condition determination unit and outputs a result of the check to the judgment control unit .

The judgment control unit controls the request change unit based on the storage contents of the correction DB and the alternative DB and controls the response correction unit based on the storage contents of the correction DB and the alternative DB and the check result received from the check unit .

The judgment control unit searches the command DB for an alternative command or an alternative command group in accordance with the check result received from the check unit . The judgment control unit stores the alternative command or alternative command group found as a result of the search in the alternative DB in correspondence with a request destination communication device and the command input from the communication processing unit into the adaptive communication processing unit .

The response correction unit is controlled by the judgment control unit and outputs the response received from the communication processing unit directly to the communication processing unit or corrects the received response to match the response condition and outputs the corrected response to the communication processing unit .

Also the response correction unit stores the response received from the communication processing unit directly to the response storage unit or corrects the received response to match the response condition and stores the corrected response to the response storage unit under control of the judgment control unit . The response correction unit generates a response that matches the response condition corresponding to the command input from the communication processing unit into the adaptive communication processing unit based on the response stored in the response storage unit and outputs the generated response to the communication processing unit .

An operation of the adaptive communication processing unit shown in is described below with reference to . is a flowchart of a main flow of a processing operation performed by the adaptive communication processing unit shown in .

The request change unit waits for input of a command of a request from the communication processing unit . Upon receiving the command of the request the request change unit outputs the received command to the judgment control unit step S .

The judgment control unit judges whether or not the command is registered in the correction DB in correspondence with the request destination communication device step S . If the command is registered in the correction DB step S YES the judgment control unit sets a correction flag step S and proceeds to step S. If the command is not registered in the correction DB step S NO the judgment control unit resets the correction flag step S and proceeds to step S.

The judgment control unit judges whether or not the command is registered in the field command in the alternative DB in correspondence with the request destination communication device step S . If the command is registered in the alternative DB step S YES the judgment control unit sets an alternative flag step S and proceeds to step S. If the command is not registered in the alternative DB step S NO the judgment control unit resets the alternative flag step S and proceeds to step S.

The judgment control unit calls a judgment control process step S and then returns to step S to wait for input of a command.

The judgment control process step S shown in and a judgment control process step S shown in de scribed later which are performed by the adaptive communication processing unit shown in are described below with reference to . is a flowchart of the judgment control process step S shown in and the judgment control process step S shown in .

If the alternative flag is set step S YES the judgment control unit calls an alternative command process step S and then returns to the caller.

If the alternative flag is not set step S NO the judgment control unit judges whether or not the correction flag is set step S .

If the correction flag is set step S YES the judgment control unit calls a correction command process step S and then returns to the caller.

If the correction flag is not set step S NO the judgment control unit calls a normal command process step S and then returns to the caller.

The alternative command process step S shown in which is performed by the adaptive communication processing unit shown in is described below with reference to . is a flow chart of the alternative command process step S shown in .

The request change unit acquires from the alternative DB an alternative command or an alternative command group registered in correspondence with the request destination communication device and the command received from the communication processing unit step S . The request change unit acquires number N that is the number of commands of the acquired alternative command or alternative command group step S .

The request change unit outputs an nth alternative command to the communication processing unit and the response condition determination unit as a request step S .

The response condition determination unit extracts a response condition stored in the response condition DB in correspondence with the alternative command received from the request change unit to determine the response condition corresponding to the alternative command step S .

The adaptive communication processing unit waits for input of a response from the communication processing unit i.e. a response from the other device in communication step S .

When the response is input from the communication processing unit into the adaptive communication processing unit the check unit checks the received response against the response condition step S .

The judgment control unit judges whether or not the received response matches the response condition based on a result of the check by the check unit step S .

If the response matches the response condition step S YES the response correction unit stores this response which is received in reply to the nth alternative command directly to the response storage unit step S and proceeds to step S.

If the response does not match the response condition step S NO the judgment control unit judges based on the check result of the check unit whether or not the response covers the response condition that is whether or not the response is correctable to match the response condition step S .

The state where the response covers the response condition i.e. the response is correctable to match the response condition is such a state where the response received in reply to the command does not match the response condition but a response which matches the response condition can be generated from the received response.

If the response does not cover the response condition step S NO the judgment control unit calls an alternative command search process step S and then returns to the caller.

The state where the response does not cover the response condition is such a state where the response received in reply to the command does not match the response condition and also a response which matches the response condition cannot be generated from the received response.

If the response covers the response condition step S YES the judgment control unit judges whether or not the nth alternative command is registered in the field command in the correction DB in correspondence with the request destination communication device step S .

If the nth alternative command is registered in the correction DB step S YES the response correction unit corrects the response to match the response condition step S . The response correction unit stores the corrected response to the response storage unit as a response corresponding to the nth alternative command step S and proceeds to step S.

If the nth alternative command is not registered in the correction DB step S NO the judgment control unit stores a device name of the request destination communication device into the field request destination and the nth alternative command into the field command in the correction DB step S . The response correction unit corrects the response to match the response condition step S stores the corrected response to the response storage unit as a response corresponding to the nth alternative command step S and proceeds to step S.

The request change unit increments variable n by 1 step S and judges whether or not variable n is larger than number N step S . If variable n is not larger than number N step S NO the request change unit returns to step S.

If variable n is larger than number N step S YES the response correction unit generates a response that matches the response condition corresponding to the command input from the communication processing unit into the adaptive communication processing unit based on a response to the alternative command or a response group made up of responses to the alternative commands that compose the alternative command group in the response storage unit step S . The response correction unit outputs the generated response to the communication processing unit step S and returns to the caller.

The correction command process step S shown in which is performed by the adaptive communication processing unit shown in is described below with reference to . is a flowchart of the correction command process step S shown in .

The request change unit outputs the command received from the communication processing unit directly to the communication processing unit and the response condition determination unit as a request step S .

The response condition determination unit extracts a response condition stored in the response condition DB in correspondence with the command received from the request change unit to determine the response condition step S .

The adaptive communication processing unit waits for input of a response from the communication processing unit i.e. a response from the other device in communication step S .

When the adaptive communication processing unit receives the response from the communication processing unit the check unit checks the received response against the response condition step S .

The judgment control unit judges whether or not the received response matches the response condition based on a result of the check by the check unit step S .

If the response matches the response condition step S YES the response correction unit outputs the response received from the communication processing unit directly to the communication processing unit step S and returns to the caller.

If the response does not match the response condition step S NO the judgment control unit judges whether or not the response covers the response condition that is whether or not the response is correctable to match the response condition based on the check result of the check unit step S .

If the response does not cover the response condition step S NO the judgment control unit calls the alternative command search process step S and then returns to the caller.

If the response covers the response condition step S YES the response correction unit corrects the response to match the response condition step S and outputs the corrected response to the communication processing unit step S . The response correction unit then returns to the caller.

The normal command process step S shown in which is performed by the adaptive communication processing unit shown in is described below with reference to . is a flowchart of the normal command process step S shown in .

The request change unit outputs the command received from the communication processing unit directly to the communication processing unit and the response condition determination unit as a request step S .

The response condition determination unit extracts a response condition stored in the response condition DB in correspondence with the command received from the request change unit to determine the response condition step S .

The adaptive communication processing unit waits for input of a response from the communication processing unit i.e. a response from the other device in communication step S .

When the adaptive communication processing unit receives the response from the communication processing unit the check unit checks the received response against the response condition step S .

The judgment control unit judges whether or not the received response matches the response condition based on a result of the check by the check unit step S .

If the response matches the response condition step S YES the response correction unit outputs the response received from the communication processing unit directly to the communication processing unit step S and then returns to the caller.

If the response does not match the response condition step S NO the judgment control unit judges whether or not the response covers the response condition that is whether or not the response is correctable to match the response condition based on the check result of the check unit step S .

If the response does not cover the response condition step S NO the judgment control unit calls the alternative command search process step S and then returns to the caller.

If the response covers the response condition step S YES the judgment control unit registers the command in the correction DB in correspondence with the request destination communication device step S . The response correction unit corrects the response to match the response condition step S outputs the corrected response to the communication processing unit step S and then returns to the caller.

The alternative command search process steps S S and S shown in and which is performed by the adaptive communication processing unit shown in is described below with reference to . is a flowchart of the alternative command search process steps S S and S shown in and .

The judgment control unit judges whether or not the alternative flag is set step S . If the alternative flag is not set step S NO the judgment control unit proceeds to step S. If the alternative flag is set step S YES the judgment control unit proceeds to step S.

The judgment control unit searches the command DB for an alternative command or an alternative command group corresponding to the command received from the communication processing unit step S . The judgment control unit judges whether or not any of the alternative command and the alternative command group is found as a result of the search step S .

If none of the alternative command and the alternative command group is found in the command DB step S NO the response correction unit notifies the communication processing unit of an error step S and then returns to the caller.

If any of the alternative command and the alternative command group is found in the command DB step S YES the judgment control unit registers the found alternative command or alternative command group in the alternative DB in correspondence with the request destination communication device and the command received from the communication processing unit step S . The judgment control unit also sets the alternative flag step S . After this the judgment control unit calls the judgment control process step S and then returns to the caller.

The judgment control unit searches the command DB for another alternative command or alternative command group corresponding to the command received from the communication processing unit step S . Another alternative command or alternative command group referred to here is an alternative command or alternative command group that is stored in the command DB and has not been used for the request destination communication device as a substitute for the command received from the communication processing unit . The judgment control unit judges whether or not any of another alternative command and alternative command group is found in the command DB as a result of the search step S .

If none of another alternative command and alternative command group is found in the command DB step S NO the response correction unit notifies the communication processing unit of an error step S and then returns to the caller.

If any of another alternative command and alternative command group is found in the command DB step S YES the judgment control unit replaces an alternative command or alternative command group registered in the alternative DB in correspondence with the request destination communication device and the command received from the communication processing unit by another alternative command or alternative command group found as a result of the search step S . The judgment control unit also sets the alternative flag step S . After this the judgment control unit calls the judgment control process step S and then returns to the caller.

The following describes an operation of the communication device shown in when correcting a response to a request with reference to . shows an operation sequence when the communication device shown in corrects a response to a request.

The communication processing unit inputs a TOP command into the adaptive communication processing unit step S . The judgment control unit in the adaptive communication processing unit resets the correction flag because the TOP command is not registered in the correction DB in correspondence with the request destination communication device. Also the judgment control unit resets the alternative flag because the TOP command is not registered in the field command in the alternative DB in correspondence with the request destination communication device. Since none of the alternative flag and the correction flag is set the judgment control unit calls the normal command process step S .

The request change unit outputs the TOP command received from the communication processing unit directly to the communication processing unit and the response condition determination unit step S . This TOP command is sent from the communication device to the other device in communication as a request as a result of which the communication device receives a response to the TOP command from the other device in communication.

The response condition determination unit extracts a response condition stored in the response condition DB in correspondence with the TOP command to determine the response condition step S .

The communication device receives a response to the TOP command from the other device in communication and the communication processing unit inputs the response in the adaptive communication processing unit step S . The check unit checks the received response against the response condition step S .

Suppose the response condition specifies the number of lines of the mail message body to be 5 while the number of lines of the mail message body in the response received from the communication processing unit is 7. In such a case the judgment control unit judges that the response does not match the response condition step S but the response covers the response condition step S . Accordingly the judgment control unit registers the TOP command in the correction DB . in correspondence with the request destination communication device step S .

The response correction unit corrects the response received from the communication processing unit to match the response condition step S and outputs the corrected response to the communication processing unit step S . When the number of lines of the mail message body specified by the response condition is 5 while the number of lines of the mail message body in the received response is 7 the response correction unit corrects the response by deleting 2 lines from the mail message body to make it 5 lines.

Suppose the TOP command is issued again to the same other device in communication as in steps S to S.

The communication processing unit inputs the TOP command in the adaptive communication processing unit step S . The judgment control unit in the adaptive communication processing unit sets the correction flag because the TOP command is registered in the correction DB in correspondence with the request destination communication device. Meanwhile the judgment control unit resets the alternative flag because the TOP command is not registered in the alternative DB in correspondence with the request destination communication device. Since the alternative flag is not set but the correction flag is set the judgment control unit calls the correction command process step S .

The request change unit outputs the TOP command received from the communication processing unit directly to the communication processing unit and the response condition determination unit step S . This TOP command is sent from the communication device to the other device in communication as a request as a result of which the communication device receives a response to the TOP command from the other device in communication.

The response condition determination unit extracts the response condition stored in the response condition DB in correspondence with the TOP command to determine the response condition step S .

The communication device receives a response to the TOP command from the other device in communication and the communication processing unit inputs the response in the adaptive communication processing unit step S . The check unit checks the received response against the response condition step S .

Suppose the response condition specifies the number of lines of the mail message body to be 5 while the number of lines of the mail message body in the response received from the communication processing unit is 7. In such a case the judgment control unit judges that the response does not match the response condition step S but the response covers the response condition step S .

The response correction unit corrects the response received from the communication processing unit to match the response condition step S and outputs the corrected response to the communication processing unit step S .

The following describes an operation of the communication device shown in when continuing communication using an alternative command with reference to . show an operation sequence when the communication device shown in continues communication using an alternative command.

The communication processing unit inputs the TOP command in the adaptive communication processing unit step S . The judgment control unit in the adaptive communication processing unit resets the correction flag because the TOP command is not registered in the correction DB in correspondence with the request destination communication device and resets the alternative flag because the TOP command is not registered in the field command in the alternative DB in correspondence with the request destination communication device. Since none of the alternative flag and the correction flag is set the judgment control unit calls the normal command process step S .

The request change unit outputs the TOP command received from the communication processing unit directly to the communication processing unit and the response condition determination unit step S . This TOP command is sent from the communication device to the other device in communication as a request as a result of which the communication device receives a response to the TOP command from the other device in communication.

The response condition determination unit extracts a response condition stored in the response condition DB in correspondence with the TOP command to determine the response condition step S .

The communication device receives a response to the TOP command from the other device in communication and the communication processing unit inputs the response in the adaptive communication processing unit step S . The check unit checks the received response against the response condition step S .

Suppose the response condition specifies the number of lines of the mail message body to be 10 while the number of lines of the mail message body in the response received from the communication processing unit is 7. In such a case the judgment control unit judges that the response does not match the response condition step S and also the response does not cover the response condition. Accordingly the judgment control unit calls the alternative command search process step S .

The judgment control unit searches the command DB for an alternative command or an alternative command group corresponding to the TOP command step S and registers a RETR alternative command found as a result of the search in the alternative DB in correspondence with the request destination communication device and the TOP command step S .

The judgment control unit resets the correction flag because the TOP command is not registered in the correction DB in correspondence with the request destination communication device. Meanwhile the judgment control unit sets the alternative flag because the TOP command is registered in the field command in the alternative DB in correspondence with the request destination communication device. Since the alternative flag is set the judgment control unit calls the alternative command process.

The request change unit extracts the RETR alternative command stored in the alternative DB in correspondence with the request destination communication device and the TOP command received from the communication processing unit and outputs the RETR alternative command to the communication processing unit and the response condition determination unit step S . This RETR alternative command is sent from the communication device to the other device in communication as a request as a result of which the communication device receives a response to the RETR alternative command from the other device in communication.

The response condition determination unit extracts a response condition stored in the response condition DB in correspondence with the RETR alternative command to determine the response condition step S .

The communication device receives a response to the RETR alternative command from the other device in communication and the communication processing unit inputs the response in the adaptive communication processing unit step S . The check unit checks the received response against the response condition step S .

Suppose the received response contains the whole mail message body. In such a case the judgment control unit judges that the received response matches the response condition step S and the response correction unit stores the received response in the response storage unit step S .

The response correction unit generates a response that matches the response condition corresponding to the TOP command received from the communication processing unit by using the response received in reply to the RETR alternative command step S . The response correction unit outputs the generated response to the communication processing unit step S .

Suppose the TOP command is issued again to the same other device in communication as in steps S to S.

The communication processing unit inputs the TOP command in the adaptive communication processing unit step S . The judgment control unit in the adaptive communication processing unit resets the correction flag because the TOP command is not registered in the correction DB in correspondence with the request destination communication device. Meanwhile the judgment control unit sets the alternative flag because the TOP command is registered in the field command in the alternative DB in correspondence with the request destination communication device. Since the alternative flag is set the judgment control unit calls the alternative command process step S .

The request change unit extracts the RETR alternative command stored in the alternative DB in correspondence with the request destination communication device and the TOP command received from the communication processing unit step S and outputs the RETR alternative command to the communication processing unit and the response condition determination unit step S . This RETR alternative command is sent from the communication device to the other device in communication as a request as a result of which the communication device receives a response to the RETR alternative command from the other device in communication.

The response condition determination unit extracts the response condition stored in the response condition DB in correspondence with the RETR alternative command to determine the response condition step S .

The communication device receives a response to the RETR alternative command from the other device in communication and the communication processing unit inputs the response in the adaptive communication processing unit step S . The check unit checks the received response against the response condition step S .

Suppose the received response contains the whole mail message body. In such a case the judgment control unit judges that the received response matches the response condition step S and the response correction unit stores the received response in the response storage unit step S .

The response correction unit generates a response that matches the response condition corresponding to the TOP command received from the communication processing unit by using the response received in reply to the RETR alternative command step S . The response correction unit outputs the generated response to the communication processing unit step S .

The second embodiment adds a function of restricting the execution of each of the response correction and the continued communication using an alternative command or an alternative command group to the first embodiment.

In this embodiment construction elements and processing steps that are the same as those in the first embodiment have been given the same reference numerals and their explanation has been omitted.

A device construction of a communication device according to this embodiment is described below with reference to . shows the device construction of the communication device according to this embodiment.

The communication device includes a CPU a memory the DSP the assist circuit the communication interface communication IF the display control circuit a display device the input interface input IF the keyboard the mouse and the tablet . The CPU the memory the DSP the assist circuit the communication IF the display control circuit and the input IF are each connected to the bus .

A restriction level setting screen is displayed on the display device . Also a restriction level designated by the user on the restriction level setting screen is stored on the memory by the CPU

The restriction level setting screen displayed on the display device shown in is explained below with reference to . shows an example of the restriction level setting screen displayed on the display device shown in .

The restriction level setting screen includes a message A MOVE SLIDER INDICATOR TO SET RESTRICTION LEVEL FOR EXECUTION OF RESPONSE CORRECTION AND EXECUTION OF CONTINUED COMMUNICATION USING ALTERNATIVE COMMAND OR ALTERNATIVE COMMAND GROUP .

The restriction level setting screen also includes a slider B. The user can designate a restriction level by moving an indicator C on the slider B using the mouse and the like. The restriction level is used to restrict the execution of the response correction and the execution of the continued communication using an alternative command or an alternative command group 

The slider B and the indicator C allow the user to designate six restriction levels. The restriction level decreases from the top to bottom of the screen. Levels 5 4 . . . 1 and 0 are assigned to the restriction levels in descending order.

Suppose the restriction level represents the degree of risk. In this case the restriction level 5 indicates a safest level a lowest degree of risk whereas the restriction level 0 indicates a least safe level a highest degree of risk .

The restriction level setting screen also includes an OK button D for restriction level determination and a CANCEL button E for cancellation.

A restriction level storage process performed by the CPU shown in is described below with reference to . is a flowchart of a restriction level reception process performed by the CPU shown in .

The CPU monitors an input operation by the user based on an input signal received from the keyboard the mouse and the like via the input IF step S .

The CPU judges whether or not the user s input operation is an operation to call the restriction level setting screen based on the input signal step S . If the restriction level setting screen call operation is not performed step S NO the CPU returns to step S.

If the restriction level setting screen call operation is performed step S YES the CPU controls the display control circuit to display the restriction level setting screen such as the one shown in on the display device step S .

The user moves the indicator C and presses the OK button D or the CANCEL button E by using the mouse and the like on the restriction level setting screen.

The CPU judges whether the OK button D or the CANCEL button E is pressed by the user based on an input signal received from the mouse and the like via the input IF step S .

If the OK button D is pressed step S OK the CPU specifies a restriction level based on the position of the indicator C and stores the specified restriction level in a restriction level storage unit described later of the memory step S . The CPU then controls the display control circuit to exit the display of the restriction level setting screen step S and returns to step S.

If the CANCEL button E is pressed step S CANCEL the CPU controls the display control circuit to exit the display of the restriction level setting screen step S and returns to step S.

A functional construction of the communication device shown in is described below by referring to . shows the functional construction of the communication device shown in .

The communication device includes the communication processing units and an adaptive communication processing unit the response condition database response condition DB a command database command DB the correction database correction DB the alternative database alternative DB the response storage unit and the restriction level storage unit .

The adaptive communication processing unit is located between the communication processing units and and relays communication between the communication processing units and . Functions of the adaptive communication processing unit will be described in detail later.

The command DB stores in correspondence with each command a pair of an alternative command or an alternative command group made up of a plurality of alternative commands that substitutes for the command and an alternative operation level. shows an example of this. If an alternative operation level corresponding to an alternative command or an alternative command group exceeds the restriction level continued communication using the alternative command or the alternative command group is executed.

In the example of a pair of an alternative command or alternative command group that substitutes for a command stored in the field command and an alternative operation level are stored in the fields alternative 1 alternative 2 and alternative 3 . Each of the fields alternative 1 alternative 2 and alternative 3 has an area for storing an alternative command or an alternative command group and an area for storing an alternative operation level.

The restriction level storage unit stores the restriction level determined as a result of the restriction level reception process shown in .

The adaptive communication processing unit functions as the request change unit the response condition determination unit the check unit a judgment control unit and a response correction unit

The judgment control unit controls the request change unit based on the storage contents of the correction DB and the alternative DB and controls the response correction unit based on the storage contents of the correction DB and the alternative DB and the check result of the check unit .

The judgment control unit searches the command DB for an alternative command or an alternative command group in accordance with the check result received from the check unit . If an alternative operation level of the alternative command or alternative command group found as a result of the search exceeds the restriction level stored in the restriction level storage unit the judgment control unit stores the alternative command or alternative command group found as a result of the search in the alternative DB in correspondence with the request destination communication device and the command input from the communication processing unit into the adaptive communication processing unit

The response correction unit is controlled by the judgment control unit and outputs the response received from the communication processing unit directly to the communication processing unit or if a correction operation level exceeds the restriction level stored in the restriction level storage unit corrects the received response to match the response condition and outputs the corrected response to the communication processing unit .

Also the response correction unit stores the response received from the communication processing unit directly in the response storage unit or if the correction operation level exceeds the restriction level stored in the restriction level storage unit corrects the received response to match the response condition and stores the corrected response in the response storage unit under control of the judgment control unit . The response correction unit generates a response that matches the response condition corresponding to the command which is input from the communication processing unit into the adaptive communication processing unit based on the response stored in the response storage unit and outputs the generated response to the communication processing unit .

The adaptive communication processing unit performs the substantially same request input process and judgment control process as those shown in the flowcharts of .

In this embodiment the judgment control process flow shown in is called in the judgment control process step S in .

Also an alternative command process flow shown in is called in the alternative command process step S in a correction command process flow shown in is called in the correction command process step S in an a normal command process flow shown in is called in the normal command process step S in .

The alternative command process step S shown in which is performed by the adaptive communication processing unit shown in is described below with reference to . is a flow chart of the alternative command process step S shown in .

The alternative command process flow shown in adds a step of judging whether or not to execute the response correction before the step of judging whether or not the response covers the response condition step S in the alternative command process flow of .

Note that an alternative command search process flow shown in is called in the alternative command search process step S in .

When the judgment control unit judges that the response does not match the response condition in step S step S NO the response correction unit judges whether or not the correction operation level set in advance exceeds the restriction level stored in the restriction level storage unit step SA .

If the correction operation level exceeds the restriction level step SA YES the judgment control unit proceeds to step S. If the correction operation level is no higher than the restriction level step SA NO the judgment control unit proceeds to step S.

The correction command process step S shown in which is performed by the adaptive communication processing unit shown in is described below with reference to . is a flow chart of the correction command process step S shown in .

The correction command process flow shown in adds a step of judging whether or not to execute the response correction before the step of judging whether or not the response covers the response condition step S in the correction command process flow of .

Note that the alternative command search process flow shown in is called in the alternative command search process step S in .

When the judgment control unit judges that the response does not match the response condition in step S step S NO the response correction unit judges whether or not the correction operation level set in advance exceeds the restriction level stored in the restriction level storage unit step SA .

If the correction operation level exceeds the restriction level step SA YES the judgment control unit proceeds to step S. If the correction operation level is no higher than the restriction level step SA NO the judgment control unit proceeds to step S.

The normal command process step S shown in which is performed by the adaptive communication processing unit shown in is described below with reference to . is a flowchart of the normal command process step S shown in .

The normal command process flow shown in adds a step of judging whether or not to execute the response correction before the step of judging whether or not the response covers the response condition step S in the normal command process flow of .

Note that the alternative command search process flow shown in is called in the alternative command search process step S in .

When the judgment control unit judges that the response does not match the response condition in step S step S NO the response correction unit judges whether or not the correction operation level set in advance exceeds the restriction level stored in the restriction level storage unit step SA .

If the correction operation level exceeds the restriction level step SA YES the judgment control unit proceeds to step S. If the correction operation level is no higher than the restriction level step SA NO the judgment control unit proceeds to step S.

The alternative command search process steps S S and S shown in and which is performed by the adaptive communication processing unit shown in is described below with reference to . is a flowchart of the alternative command search process steps S S and S shown in and .

The alternative command search process flow shown in adds the following two judgment steps to the alternative command search process flow of .

The first judgment step judges after the judgment that any of an alternative command and an alternative command group exists step S YES whether or not to execute the communication using the alternative command or alternative command group found as a result of the search.

The second judgment step judges after the judgment that any of another alternative command and another alternative command group exists step S YES whether or not to execute the communication using another alternative command or alternative command group found as a result of the search.

When the judgment control unit judges that any of an alternative command and an alternative command group exists in step S step S YES the judgment control unit acquires an alternative operation level of the alternative command or alternative command group found as a result of the search with reference to the command DB . The judgment control unit then judges whether or not the acquired alternative operation level exceeds the restriction level stored in the restriction level storage unit step SA .

If the alternative operation level exceeds the restriction level step SA YES the judgment control unit proceeds to step S. If the alternative operation level is no higher than the restriction level step SA NO the judgment control unit returns to step S.

In the case where the alternative operation level exceeds the restriction level step SA YES the alternative command or alternative command group found as a result of the search is stored in the alternative DB and the alternative command process flow shown in is executed through the judgment control process flow shown in . Which is to say the judgment step of step SA is equivalent to the step of judging whether or not to execute the communication using the alternative command or alternative command group found as a result of the search.

When the judgment control unit judges that any of another alternative command and another alternative command group exists in step S step S YES the judgment control unit acquires an alternative operation level of another alternative command or alternative command group found as a result of the search with reference to the command DB . The judgment control unit then judges whether or not the acquired alternative operation level exceeds the restriction level stored in the restriction level storage unit step SA .

If the alternative operation level exceeds the restriction level step SA YES the judgment control unit proceeds to step S. If the alternative operation level is no higher than the restriction level step SA NO the judgment control unit returns to step S.

In the case where the alternative operation level exceeds the restriction level step SA YES another alternative command or alternative command group found as a result of the search is stored in the alternative DB and the alternative command process flow shown in is executed through the judgment control process flow shown in . Which is to say the judgment step of step SA is equivalent to the step of judging whether or not to execute the communication using another alternative command or alternative command group found as a result of the search.

Suppose the correction operation level is set to 1 command a has alternative commands a and a whose alternative operation levels are respectively 2 and 4 and the communication processing unit inputs command a in the adaptive communication processing unit

The correction operation level 1 exceeds the restriction level 0 so that the response correction is performed according to need. Also the alternative operation level 2 of alternative command a and the alternative operation level 4 of alternative command a both exceed the restriction level 0 so that the communication using alternative command a and the communication using alternative command a are performed according to need.

The correction operation level 1 does not exceed the restriction level 1 so that the response correction is not performed. Meanwhile the alternative operation level 2 of alternative command a and the alternative operation level 4 of alternative command a both exceed the restriction level 1 so that the communication using alternative command a and the communication using alternative command a are performed according to need.

The correction operation level 1 does not exceed the restriction level 2 so that the response correction is not performed. Also the alternative operation level 2 of alternative command a does not exceed the restriction level 2 so that the communication using alternative command a is not performed. Meanwhile the alternative operation level 4 of alternative command a exceeds the restriction level 2 and so the communication using alternative command a is performed according to need.

The correction operation level 1 does not exceed the restriction level 5 so that the response correction is not performed. Also both the alternative operation level 2 of alternative command a and the alternative operation level 4 of alternative command a do not exceed the restriction level 5 and so the communication using alternative command a and the communication using alternative command a are not performed.

According to this embodiment the user can decide whether or not to perform the response correction and to what extent the communication using an alternative command or an alternative command group is to be performed.

Though the present invention has been described by way of the above embodiments the present invention is not limited to the above. For example the following modifications are applicable.

 1 The above embodiments describe the case where the TCP IP layer model is used as an example but this is not a limit for the present invention which can be equally applied to other models.

 2 The above embodiments describe the case where the processing target protocol is POP3 or the like and the functions of the present invention are provided between the protocol such as POP3 and TCP or UDP. However the present invention is not limited to this as the functions of the present invention can be provided between any processing target protocol and a protocol located at its lower layer.

 3 The above embodiments describe the case where the functions of the present invention are provided between a protocol such as POP3 and TCP or UDP but the present invention is not limited to such. The functions of the present invention may be incorporated in the processing target protocol. Also the functions of the present invention may be incorporated in the protocol that is located at a lower layer of the processing target protocol.

 4 The first embodiment describes the case where the command DB is generated beforehand but the present invention is not limited to such. For example the command DB may be automatically generated using an inference mechanism.

Let A be a set of all communication commands func x be a function of communication command x and FUNC x y . . . be a function that combines communication commands x y . . . .

Command a a A can be substituted by command b b B where func a func b . Also command a a A can be substituted by command group x y . . . x y . . . B where func a func x y . . . .

By searching the response condition DB based on the above rule it is possible to generate an alternative command or an alternative command group composed of a plurality of alternative commands that can substitute for command a.

For instance in the case of POP the relations func TOP func RETR and func LIST func STAT can be discovered according to an inference mechanism using a predicate logic. As a result it can be understood that TOP is replaceable by RETR and LIST is replaceable by STAT.

 5 The functions of the present invention can be applied to various communication such as communication between a device such as a personal computer and a device such as a server communication between a personal computer and a peripheral device communication between LSIs Large Scale Integration and intra chip communication so long as they involve sending receiving a request and a response to the request.

For instance the functions of the present invention are applicable to communication by a HDD interface such as ATAPI AT Attachment Packet Interface or Serial ATAPI communication on USB or Bluetooth and intra chip communication according to a protocol of a serial bus such as I2C Inter Integrated Circuit .

 6 The above embodiments describe the case where the storage of the correction DB and the alternative DB is performed in units of communication devices but this is not a limit for the present invention. As one example in a situation where a device model name is obtainable the storage of the correction DB and the alternative DB may be performed in units of models of communication devices.

 7 The above embodiments describe the case where the response is corrected to match the response condition if the response does not match the response condition but covers the response condition. Alternatively an alternative command or an alternative command group may be sent to the other device in communication if the response does not match the response condition but covers the response condition.

 8 Suppose a command sent as a request has a form that includes a command name a plurality of arguments and a range of each argument and a response to each command has a plurality of types with a value range and a restriction condition being defined for each type. The generation of a response condition and the search for an alternative command or an alternative command group may be performed by using these.

Also suppose a command sent as a request has a form that includes a command name a current communication status a next communication status a plurality of arguments and a range of each argument and a response to each command has a current communication status and a plurality of types with a value range and a restriction condition being defined for each type. The generation of a response condition and the search for an alternative command or an alternative command group may be performed in consideration of the current communication status and the next communication status by using these.

 9 A program that describes the same procedure as the processing shown in the above embodiments and modifications may be generated and recorded on a recording medium such as a CD ROM which can read the program on a computer and the like.

Although the present invention has been fully described by way of examples with reference to the accompanying drawings it is to be noted that various changes and modifications will be apparent to those skilled in the art.

Therefore unless such changes and modifications depart from the scope of the present invention they should be construed as being included therein.

