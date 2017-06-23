---

title: Charged particle beam device
abstract: A charged particle beam device () is provided, including a computer operable in response to commands entered by a user of the device to control the device, wherein the device further includes an interface () operable to cause data from the computer in the form of short message service (SMS) and/or multimedia message service (MMS) messages to be transmitted to a mobile device () via a mobile telephone network (). The charged particle beam device () is operable to receive commands in the form of SMS and/or MMS messages from the mobile telephone (), and to cause the computer to execute the commands. The interface () includes a user interface operable to enable a user of the device to select operating parameters and/or conditions of the device from a list of operating parameters and/or conditions, set values of each selected operating parameter or condition in response to which the interface will transmit an SMS message to a mobile device, and for each selected operating parameter or condition, enter an identification, typically a telephone number, of the mobile device to which the SMS message will be transmitted.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=07925284&OS=07925284&RS=07925284
owner: Carl Zeiss SMT Limited
number: 07925284
owner_city: 
owner_country: GB
publication_date: 20070111
---
This invention relates to charged particle beam devices particularly but not exclusively to electron microscopes and focused ion beam systems.

A known electron microscope includes a computer operable to monitor and adjust various operating parameters of the microscope such as an accelerating voltage EHT used to accelerate electrons in the microscope. The computer is operable to adjust the operating parameters in accordance either with a control algorithm or commands entered by a user of the microscope.

The computer can communicate with another computer via the Internet. The user can operate the microscope from the other computer which can be remote from the microscope. However this requires both computers to be connected to the Internet and a continuous connection between the computers to be maintained.

The operations carried out by an electron microscope can take many hours to complete. For example x ray scanning of a mineral sample can take twenty hours or more. Some microscopes include a focused ion beam FIB column for milling i.e. using an ion beam to remove layers of a specimen . Milling operations can take several hours to complete. At present the user must initiate an operation at the microscope or at the other computer then return to the microscope or to the other computer from time to time to determine whether the microscope has completed the operation or whether a fault has occurred that has prevented completion of the operation.

According to the invention there is provided a charged particle beam device including a computer operable in response to commands entered by a user of the device to control the device wherein the device further includes an interface operable to cause data from the computer to be transmitted in the form of short message service SMS and or multimedia message service MMS messages to a mobile device via a mobile telephone network.

In this specification mobile device means a device operable to receive and display SMS and or MMS messages from a mobile telephone network. Such devices include mobile telephones and some personal digital assistants PDAs .

Most people nowadays have a mobile telephone and are familiar with SMS and MMS messages. A mobile device such as a mobile telephone does not need to be programmed or to have any software installed on it by the user in order to be able to receive SMS and MMS messages. This makes such mobile devices ideal for use to notify a user of events relating to a charged particle beam device.

The invention can provide a charged particle beam device that is operable to notify a user who is not in the immediate vicinity of the device of events relating to the device such as the completion of an operation by the device or the occurrence of a fault that has interrupted operation of the device by means of a mobile device of the user.

Use of the mobile device of the user to notify the user of events relating to the charged particle beam device avoids the need for a continuous connection to be maintained between the charged particle beam device and the mobile device. The charged particle beam device has no need to establish the location of the user to notify him because this is done by the mobile telephone network.

Moreover use of the mobile device of the user and the mobile telephone network to notify the user of events relating to the charged particle beam device means that there is no need for the security protocols that would be necessary if the notification were provided via the Internet.

Preferably the interface is operable to cause the data to be transmitted to the mobile device via a Global System for Mobile Communications GSM mobile telephone network. The interface may advantageously be operable to receive commands in the form of SMS and or MMS messages from the mobile telephone network and to cause the computer to execute the commands.

The invention can further provide a charged particle beam device that can be controlled by a user who is not in the immediate vicinity of the device by transmission of commands such as commands to start up or shut down to the interface by means of the mobile device of the user.

The interface may advantageously be adapted for communication with a data transceiver operable to transmit the data to the mobile device via the mobile telephone network.

The data transceiver might for example be another mobile device or simply a modem card such as a GSM PCMCIA modem card.

Where the interface is adapted for communication with a data transceiver the interface is preferably further operable to receive commands in the form of SMS and or MMS messages from the data transceiver the commands being received by the data transceiver from the mobile telephone network and to cause the computer to execute the commands.

The interface may advantageously be adapted for communication with the data transceiver by connection to the data transceiver for example by means of a Universal Serial Bus USB serial or local area network LAN connection.

Preferably the interface is adapted for wireless communication with the data transceiver for example in accordance with the Bluetooth or Wi Fi protocol.

Alternatively or additionally the interface may advantageously be adapted for communication with a host computer by means of the Internet the host computer being operable to transmit the data to the mobile device via the mobile telephone network.

The host computer would typically be used to implement an application programming interface API to allow transmission and reception of SMS and or MMS messages by the host computer examples of such APIs being MSN Messenger ActiveX COM XML and .NET.

Where the interface is adapted for communication with a host computer the interface is preferably operable to receive commands in the form of SMS and or MMS messages from the host computer the commands being received by the host computer from the mobile telephone network and to cause the computer of the device to execute the commands.

The interface may advantageously be operable to cause data from the computer of the device to be transmitted to a plurality of mobile devices via the mobile telephone network.

In this way several other users who are waiting to use the device could be informed that the device has completed an operation initiated by a first user and is available for use by the other users.

Preferably the interface is operable to cause data from the computer to be transmitted to a first mobile device in response to occurrence of a first event relating to the device and to a second mobile device in response to occurrence of a second event relating to the device.

By way of example in response to completion of an operation by the device the interface might cause an SMS message indicating that the device is available for use to be transmitted to the mobile device of a user of the device whereas in response to detection of occurrence of a fault with the device the interface might cause an SMS message indicating the nature of the fault to be transmitted to the mobile device of a service engineer. If the fault is such as to interrupt the operation of the device the interface might additionally cause an SMS message indicating that completion of the operation will be delayed to be transmitted to the mobile device of the user of the device.

The interface preferably includes a user interface operable to enable a user of the device to select operating parameters and or conditions of the device from a list of operating parameters and or conditions set values of each selected operating parameter or condition in response to which the interface will transmit an SMS message to a mobile device and for each selected operating parameter or condition enter an identification typically a telephone number of the mobile device to which the SMS message will be transmitted.

Such an operating condition might for example be percentage completion of an operation of the device so that in order to be notified of completion of an operation of the device the user would use the user interface to select percentage completion from the list of operating parameters set a value of 100 for percentage completion and enter the telephone number of his mobile device.

Preferably the user interface is further operable to enable a user of the device to enter a text string for each of the selected operating parameters or conditions which text string will be included in the SMS message sent to the mobile device identified in connection with that parameter or condition.

Thus for example where the device is an electron microscope the user interface could be used to select a condition that a filament of an electron column of the microscope has failed to enter the telephone number of the mobile device of a service engineer and to enter a text string such as SEM23574 replace filament to be transmitted as an SMS message to the mobile device of the service engineer in the event of failure of the filament.

The user interface may advantageously be operable to enable a user to compose a message for transmission by the interface to the mobile device. The user interface may advantageously further be operable to display a SMS or MMS message received by the interface from the mobile device. In this way a user in the immediate vicinity of the device can communicate conveniently with a user who is not in the immediate vicinity of the device.

The user interface is preferably operable to enable a user of the device to select commands from a list of commands executable by the device and for each selected command to enter a text string corresponding to the command and the interface is further operable in response to receipt of an SMS message containing the text string to cause the computer to execute the corresponding command.

Such commands executable by the computer might include commands to start up or shut down the device the text strings corresponding to these commands being for example start and stop respectively.

Where the device is operable to produce an image of a specimen as is the case with an electron microscope for example the commands executable by the device preferably include a command to convert an image of the specimen produced by the device to an MMS message and to transmit the MMS message to a mobile device. The text string corresponding to this command might for example be get image . Thus a user not in the immediate vicinity of the device can transmit an SMS message containing the text string get image to the interface of the device using his mobile device and his mobile device will receive an MMS message containing an image of a specimen from the interface of the device.

This process of assigning simple text strings to commands from a list of commands executable by the device makes the device very simple to operate remotely using a mobile device because it avoids the need for any software to be installed on the mobile device.

Where the device is operable to modify a specimen as in the case of a focused ion beam device operable to mill a specimen i.e. remove layers or portions of layers from the specimen the interface is preferably operable to receive an MMS message from a mobile device containing an image of a milling pattern and to cause the computer to control the device so as to mill the milling pattern into the specimen.

Preferably the device is an electron microscope and more preferably still a scanning electron microscope SEM .

The communication network of comprises a scanning electron microscope SEM a local mobile telephone wirelessly connected in accordance with the Bluetooth protocol to the SEM a GSM mobile telephone network and first second and third remote mobile telephones denoted by reference numerals and respectively.

The SEM is of conventional construction and operation in that it has a beam generating column in which a beam of electrons is generated shaped and focused by means of controlled electrostatic and or magnetic fields and scanned across a specimen to be analysed. The SEM also includes control software executable by a computer not shown to control the operation of the SEM and a focused ion beam FIB column not shown . The SEM also includes an interface which is wirelessly connected to the local mobile telephone as explained above. The SEM is described in greater detail below with reference to .

The control software monitors and modifies the operating parameters and conditions of the SEM such as accelerating voltage of the electron optical column that produces the electron beam deflection of the electron beam relative to a specimen pressure in the specimen chamber progress through a milling list carried out on the specimen by the FIB column and accelerating voltage of a secondary electron detector.

The interface includes application programming interface software that interfaces with the control software . The interface displays in a windowed dialog system a list of the operating parameters and conditions monitored by the control software . A user of the SEM can select any of the operating parameters and conditions monitored by the control software in the windowed dialog system and enter a trigger value of that parameter or condition that will trigger a notification. In the description that follows the event of a parameter or condition reaching a trigger value of that parameter or condition will be referred to as a trigger event . For the parameter of the pressure in the specimen chamber for example the user might enter a trigger value that if reached by the pressure in the specimen chamber would indicate a fault with the vacuum system of the SEM so that if the pressure in the specimen chamber reaches that trigger value it will trigger a notification.

For each selected operating parameter or condition the user enters a mobile telephone number to which a notification SMS message will be sent in the event of a trigger event. The user can also enter a time range for example 08.00 to 18.30 when the notification is allowed to occur. If a trigger event occurs outside this time range the notification will not be triggered. This enables a user of the SEM to ensure that a notification is not sent to his mobile device at inconvenient times for example when he is at home.

For each entered trigger event the user also enters a text string to be included in the notification if the trigger event occurs. In the example above of the trigger value of the pressure in the specimen chamber indicative of a fault with the vacuum system of the SEM the text string might be warning high specimen chamber pressure . The selected operating parameters and conditions mobile telephone numbers time ranges if any and text strings are stored on the hard drive of the computer of the SEM.

In the event of a trigger value of an operating parameter or condition being reached the interface retrieves the mobile telephone number and text string associated with that trigger value from the hard disc drive of the computer of the SEM and transmits a signal to the local mobile telephone that causes it to transmit an SMS message containing the text string to the mobile telephone number.

In remote mobile telephone is the telephone of a first user of the SEM and remote mobile telephone is the telephone of a second user of the SEM. Remote mobile telephone is the telephone of a service engineer responsible for maintenance of the SEM.

The list of operating parameters and conditions includes detectable fault conditions such as failure of the filament of the electron optical column of the SEM. The windowed dialog system would typically be used to select the fault condition of failure of the filament and the telephone number of the telephone of the service engineer entered. The text string for transmission to the telephone of the service engineer in the event of failure of the filament can include identification of the SEM such as a serial number of the SEM where the service engineer is responsible for maintenance of several SEMs. This is not essential however because the local mobile telephone has a unique telephone number which can be used by the service engineer to identify the SEM provided that his mobile telephone is operable to display the telephone number of mobile devices from which it has received an SMS message.

The interface also displays in the windowed dialog system a list of commands executable by the control software . These commands include commands to start up and shut down the SEM to vent the specimen chamber of the SEM and to produce an image of the specimen. The user of the SEM can select any of the commands and enter a text string in response to receipt of which in an SMS message the interface will carry out the corresponding command.

For example the user might select the command to start up the SEM and enter the text string start . He can then use his remote mobile telephone to transmit an SMS message containing the text string start to the local mobile telephone . Upon receipt of the SMS message the local mobile telephone transmits the SMS message to the interface which identifies the text string start in the SMS message and causes the computer of the SEM to start up the SEM. Starting up the SEM can take 20 to 30 minutes so this enables the user to start up the SEM during his journey to work so that the SEM is ready for use upon his arrival at work.

The user might also select the command to produce an image of the specimen and enter the text string get image . He can then use his remote mobile telephone to transmit an SMS message containing the text string get image to the local mobile telephone . Upon receipt of the SMS message the local mobile telephone transmits the SMS message to the interface which identifies the text string get image in the SMS message and causes the computer to obtain an image of the specimen and transmit it to the interface . The interface then converts the image into a form suitable for transmission as an MMS message and transmits the MMS message to the local mobile telephone which transmits the MMS message to the remote mobile telephone of the user.

For security purposes the user can also enter one or more telephone numbers for each selected command the telephone numbers being those of remote mobile telephones from which the user wishes the SEM to be able to receive commands. Upon receiving an SMS message containing a text string associated with a command executable by the computer the interface determines whether the telephone number of the remote mobile telephone from which the SMS message has been received is one of the telephone numbers entered for that command and causes the computer to execute the command only if it is so determined.

Turning to the computer system of the SEM can be regarded as comprising four functional blocks namely the control software of the SEM a trigger event definition module a trigger event and command processing monitoring module and a hard drive on which the selected trigger events commands text strings and mobile telephone number or numbers for each selected trigger event or command are stored.

The trigger event module is accessed by the user through the windowed dialog system as explained above and obtains the list of controllable parameters conditions and executable commands from the control software . The mobile telephone numbers and text strings entered by the user into the trigger event module are stored by the trigger event module on the hard drive . The trigger event and command processing monitoring module is wirelessly connected to the local mobile telephone and monitors the controllable parameters and conditions of the control software and responds to trigger events by retrieving the relevant text string and mobile telephone number from the hard drive composing an SMS message containing the text string and causing the local mobile telephone to transmit the SMS message to the mobile telephone number.

The trigger event and command processing monitoring module also monitors the SMS messages received by the local mobile telephone and each time an SMS message is received searches the hard drive to determine whether the SMS message contains a text string corresponding to a command executable by the control software checks the hard drive if required to determine whether the SMS message has been received from a mobile telephone from which that command is to be accepted and if so causes the control software to carry out the command.

In addition to the control software and interface the SEM comprises a controller an electron emitter an extraction electrode a control Wehnelt electrode an anode a condenser lens including a magnetic coil an objective lens including a magnetic coil a scanning coil a specimen stage an electron detector and a pressure sensor .

The controller is operable to control the voltage of the electron emitter as well as the voltages of the electrodes and . The controller is also operable to control the currents of the condenser lens coil and the objective lens coil as well as the current of the scanning coil . The controller can determine the region of a specimen on the specimen stage that is scanned by the electron beam by control of the current of the scanning coil . The controller is also operable to control an actuator to move the specimen stage in any of three mutually perpendicular directions shown in and denoted by reference numeral so as to select that region of the specimen of which an image is to be generated. The controller generates the image using signals from the electron detector which signals are transmitted to the controller by the detector .

The pressure sensor transmits signals representative of the pressure in the specimen chamber not shown of the SEM to the controller which transmits the signals to the control software so as to enable the control software to detect a trigger value of the pressure in the specimen chamber if a fault develops in the vacuum system of the SEM because such a fault will give rise to an increase in pressure in the specimen chamber.

The control software interface and controller are therefore operable to notify a user of the SEM via his mobile telephone of any chosen value of the parameters of the SEM such as specimen chamber pressure and electron detector signal that are monitored by the controller . The control software interface and controller are also operable to adjust any of the parameters such as electrode voltages coil currents and specimen stage position in response to commands transmitted to the SEM by the user of the SEM using his mobile telephone.

It will be appreciated that the foregoing description relates only to one embodiment of the invention and that the invention encompasses other embodiments as defined by the foregoing statements of the invention.

