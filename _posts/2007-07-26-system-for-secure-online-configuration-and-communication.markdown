---

title: System for secure online configuration and communication
abstract: A system for online configuration and communication for a supervisory control and data acquisition system comprising an online configurable enterprise server, at least one intelligent electronic device, an online configurable intelligent electronic cryptographic module, and a configurable server interface. Both the online configurable enterprise server and the online configurable intelligent electronic cryptographic module include respective cryptography chips and computer instructions for instructing respective processors to selectively encrypt and decrypt commands, messages, data, and responses, allowing non-encrypted transmissions between the at least one intelligent electronic device and the online configurable intelligent electronic cryptographic module, and selectively encrypted transmission between the intelligent electronic cryptographic module and the online configurable enterprise server.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=07673337&OS=07673337&RS=07673337
owner: DJ Inventions, LLC
number: 07673337
owner_city: Houston
owner_country: US
publication_date: 20070726
---
The present embodiments relate to a system for secure online configuration and communication between an online configurable enterprise server and at least one intelligent electronic device using an online configurable intelligent electronic cryptographic module.

A need exists for a system for secure and online configuration and communication able to selectively encrypt decrypt and securely transmit messages commands data and responses between an enterprise server and one or more intelligent electronic devices.

A further need exists for system capable of mixed mode transmission selectively encrypting specified messages or messages from a specified source while omitting encryption of one or more other messages.

A need exists for a system for secure and online configuration and communication that can be configured to perform differing mixed mode transmissions on line without interrupting the normal functions of the enterprise server the intelligent electronic cryptographic module or any of the intelligent electronic devices in communication with the module.

A need also exists for system that is able to securely reconfigure one or more intelligent electronic devices enterprise servers or intelligent electronic cryptographic modules on line without interrupting the normal functions of the enterprise server the intelligent electronic cryptographic module or any of the intelligent electronic devices in communication with the module.

Before explaining the present embodiments in detail it is to be understood that the embodiments are not limited to the particular embodiments and that they can be practiced or carried out in various ways.

The present system provides enhanced security during communication between an online configurable enterprise server and one or more intelligent electronic devices via an online configurable intelligent electronic cryptographic module.

The online configurable intelligent electronic cryptographic module can provide secure communication between an online configurable enterprise server and various kinds of intelligent electronic devices including remote terminal units programmable logic controllers and other similar intelligent electronic devices.

The online configurable intelligent electronic cryptographic module can include software enabling the online configurable intelligent electronic cryptographic module to both function as an online configurable remote terminal unit for performing a variety of processes and to function as an online configurable intelligent electronic cryptographic module selectively encrypting and decrypting messages and responses between an online configurable enterprise server and one or more intelligent electronic devices.

The encryption provided by the present system is more efficient than conventional encryption means due to the present system s ability to enable on line real time reconfiguration of the enterprise server the intelligent electronic cryptographic module and one or more intelligent electronic devices. Through this on line reconfiguration the online configurable intelligent electronic cryptographic module one or more intelligent electronic devices or the enterprise server can be reconfigured without interrupting service to any of the intelligent electronic devices or interrupting the functions of the intelligent electronic devices or the intelligent electronic cryptographic module thereby maintaining continuity of service and saving costs and hindrances associated with deactivating modules and units.

Even Legacy Remote Terminal Units which lack the hardware or software to be reconfigured on line can be selectively reconfigured without affecting the function of any other intelligent electronic devices the online configurable enterprise server or the online configurable intelligent electronic cryptographic module. Additionally data messages and responses from legacy remote terminal units can be selectively encrypted and decrypted using the online configurable intelligent electronic cryptographic module.

The present system further allows for efficient security by utilizing pass through transmission of messages responses commands and data independent of any associated gateway protocols. The present system allows for use of mixed mode transmission selectively encrypting only specified messages or messages from a specified source saving time costs and bandwidth while permitting other data to pass through the online configurable intelligent electronic cryptographic module for encryption or decryption. The specifications relating to the mixed mode transmission can be reconfigured on line in real time without interrupting the functions of the system components.

The pass through capabilities of the present system allow the connectivity and security between an online configurable enterprise server the online configurable intelligent electronic cryptographic module and one or more intelligent electronic devices to be efficiently and effectively tested prior to encrypting transmissions and at any time during service.

The present system also provides enhanced security through use of authentication means such as digital certificates and keys and tamper proof encryption through use of a cryptography chip. The embodied cryptography chip can be built into the online configurable intelligent electronic cryptographic module or separately attached using a removable data storage media. A cryptography chip can also be attached to the online configurable enterprise server using a removable data storage device. The cryptography chip is compatible with the Windows CE Operating System Windows XP Windows 2003 and other similar operating systems and can be utilized through a standard cryptographic application programming interface CAPI .

The authentication means provided through use of the cryptography chips within the online configurable enterprise server and the online configurable intelligent electronic cryptographic module provide greater security than conventional means which typically do not include authentication of system components. The authentication of the online configurable server the online configurable intelligent electronic cryptographic module and one or more intelligent electronic devices can be selectively performed as frequently as needed to maintain security or as infrequently as needed to conserve costs and bandwidth.

The present embodiments relate to a system for configuration and communication for a supervisory control and data acquisition system.

The system includes an online configurable enterprise server. The online configurable enterprise server has a server port such as a universal serial bus port for receiving a server removable data storage device having a server cryptography chip. The server cryptography chip can be a Spyrus Rosetta or a Spyrus Lynks made by Spyrus of San Jose Calif.

The online configurable enterprise server can also include a server power supply which can include alternating current sources direct current sources renewable power sources rechargeable power sources replaceable power sources and combinations thereof. The online configurable enterprise server can further include a server telemetry interface such as a modem radio satellite or Ethernet interface.

The online configurable enterprise server has a server processor in communication with a server data storage. The server data storage can include a server protocol module such as a BSAP a MODBUS or similar protocol modules a server connection module such as a serial module a dial up module or a TCP IP module and a server configuration database such as an Oracle or Microsoft Access database for restoring online configurations of the enterprise server when the server is reset. The server data storage can also include a server authentication module however it is contemplated that the server authentication module can be contained in memory within the server cryptography chip.

In an embodiment the server data storage can also include a configuration software such as Autosol RTU Maintenance Environment ARME made by Automated Solutions of Houston Tex. for enabling the online reconfiguration of one or more intelligent electronic devices in communication with the online configurable enterprise server.

The system can include at least one intelligent electronic device for measuring a process such as metering a utility detecting abnormal operating conditions performing data processing controlling operating conditions and combinations thereof. Possible intelligent electronic devices can include remote terminal units such as an Autosol RTU 4000 a Bristol Babcock 3330 RTU an Emerson ROC 809 or similar remote terminal units. Possible intelligent electronic devices can also include a programmable logic controller PLC or other similar intelligent electronic devices.

It is contemplated that any number of intelligent electronic devices can be in communication with the online configurable enterprise server.

Each intelligent electronic device is contemplated to include an IED processor and IED data storage having computer instructions for instructing the IED processor to transmit non encrypted measured data to the online configurable enterprise server.

In an embodiment one or more intelligent electronic devices can have analog to digital converters in communication with the IED processor for measuring processes and converting non encrypted measurements into digital representations. The digital representations can be selectively stored in IED data storage.

Each intelligent electronic device can include IED computer instructions for instructing the IED processor to selectively store the digital representations and a bidirectional IED port for transmitting the digital representations to the online configurable enterprise server. The bidirectional IED port can also be used for receiving commands from the online configurable enterpriser server in response to the digital representations.

It is further contemplated that the IED data storage can include computer instructions for instructing the IED processor to perform autonomously in the absence of instruction from the enterprise server.

The present system also includes an online configurable intelligent electronic cryptographic module in communication with the online configurable enterprise server. In an embodiment the online configurable intelligent electronic cryptographic module can be adapted to be activated to perform encryption and decryption functions and deactivated to allow messages and responses to pass through without encryption or decryption on line without interruption of service to the online configurable enterprise server or any of the intelligent electronic devices.

The online configurable intelligent electronic cryptographic module includes a first cryptography chip and at least one data storage media which can include removable memory non removable memory flash memory or combinations thereof.

The first cryptography chip is contemplated to be substantially similar to the server cryptography chip. Both the first cryptography chip in the online configurable intelligent electronic cryptographic module and the server cryptography chip can include cryptographic tamper resistant memory which can contain one or more encryption and decryption algorithms one or more keys a random number generator at least one certificate for digital signatures an authentication module and combinations thereof.

In an embodiment the first cryptography chip can be disposed within a first removable data storage device which can be in communication with the first processor through a port such as a universal serial bus port. This embodiment can advantageously allow the cryptography chip to be utilized in after market applications.

It is contemplated that the encryption and decryption functions of first cryptography chip the server cryptography chip or combinations thereof can be selectively activated and deactivated enabling mixed mode transmissions.

For example non encrypted measured data from a low security intelligent electronic device can be permitted to pass through the online configurable intelligent electronic cryptographic module without encryption to conserve bandwidth time and resources and the non encrypted measured data can be transmitted to the online configurable enterprise server.

Simultaneously or independently non encrypted measured data such as alarm thresholds control targets or calculated values from a high security intelligent electronic device can be encrypted prior to transmitting any data from the high security intelligent electronic device to the online configurable enterprise server.

Additionally selective pieces of non encrypted measured data from any intelligent electronic device can be selectively encrypted or remain non encrypted depending on the nature of the measured data or any other factors such as date time of day a need to conserve time or bandwidth or similar factors.

The data storage within the online configurable intelligent electronic cryptographic module can include computer instructions for instructing a first processor within the online configurable intelligent electronic cryptographic module to selectively decrypt messages from the online configurable enterprise server using the first cryptography chip and transmit decrypted messages to one or more intelligent electronic devices.

The data storage can further include computer instructions for instructing the first processor to select at least one protocol module such as BSAP MODBUS ROC DNP 3.0 or other similar protocol modules for communication with one or more intelligent electronic devices the online configurable enterprise server or combinations thereof. The computer instructions can also instruct the first processor to select at least one appropriate telemetry method such as a modem a radio an Ethernet a satellite or other similar telemetry methods for transmitting and receiving messages using the one or more selected protocol modules. The use of a telemetry method can be facilitated through use of one or more connection modules.

The data storage can also include computer instructions for instructing the first processor to perform as a soft remote terminal unit as described in U.S. Pat. No. 6 628 992.

It is contemplated that when the online configurable intelligent electronic cryptographic module performs as a remote terminal unit in addition to performing intelligent encryption and decryption functions the use of additional intelligent electronic devices in communication with the intelligent electronic cryptographic module can be omitted and the intelligent electronic cryptographic module can both function as a cryptographic module and as a remote terminal unit simultaneously.

When the online configurable intelligent electronic cryptographic module functions as a remote terminal unit the module advantageously becomes both an intelligent cryptographic module and an online configurable remote terminal unit. This is a noteworthy advantage over conventional Legacy Remote Terminal Units which typically lack hardware or software to permit online configurability or encrypted transmissions. Use of the online configurable intelligent electronic cryptographic module as a remote terminal unit also provides enhanced security by eliminating the clear text link between the online configurable intelligent electronic cryptographic module and a Legacy Remote Terminal Unit.

It is further contemplated however that any number of additional remote terminal units or other intelligent electronic devices can be in communication with the online configurable intelligent electronic cryptographic module independent of the online configurability of any of the intelligent electronic devices and independent of whether the online configurable intelligent electronic cryptographic module is also functioning as a soft remote terminal unit.

The first processor disposed within the online configurable intelligent electronic cryptographic module is adapted to authenticate the online configurable enterprise server the online configurable intelligent electronic cryptographic module any of the intelligent electronic devices or combinations thereof. The first processor is also adapted to provide encrypted and non encrypted communication with the online configurable enterprise server and non encrypted communication with one or more of the intelligent electronic devices.

The data storage can further include computer instructions for instructing the first processor to selectively encrypt non encrypted measured data transmitted by one or more intelligent electronic devices and transmit encrypted measured data to the online configurable enterprise server.

The data storage can also include computer instructions for instructing the first processor to authenticate at least once that the online configurable enterprise server is authorized to transmit to the online configurable intelligent electronic cryptographic module and that online configurable intelligent electronic cryptographic module is authorized to transmit to the online configurable enterprise server. This provides an additional level of security over conventional means which typically lack authentication. The authentication of the online configurable enterprise server and the online configurable intelligent electronic cryptographic module can be performed as frequently as necessary to ensure security or as infrequently as necessary to conserve costs and bandwidth.

The data storage additionally includes computer instructions for instructing the first processor to communicate a command from the online configurable enterprise server to one or more intelligent electronic devices. The command can include reconfiguration instructions for one or more intelligent electronic devices a request for data or combinations thereof.

Computer instructions for instructing the first processor to communicate a command from one or more intelligent electronic devices to the online configurable enterprise server can also be resident in the data storage. The command can include non encrypted measured data a request for further instructions or combinations thereof.

The computer instructions can further instruct the first processor to store encrypted measured data in the data storage.

In a contemplated embodiment the online configurable intelligent electronic cryptographic module can further include computer instructions for instructing the first processor to embed a first digital signature in the online configurable enterprise server embed a second digital signature in the online configurable intelligent online cryptographic module and validate the digital signatures prior to encrypting decrypting and transmitting messages and responses.

It is also contemplated that the server data storage can include computer instructions for instructing the server processor to derive one or more public and or private exchange keys and transmit the public exchange key to the online configurable intelligent electronic cryptographic module. The public key can be used to encrypt session keys while the private keys are required to decrypt session keys.

The data storage in the online configurable intelligent electronic cryptographic module can include computer instructions for instructing the processor to receive the public exchange key derive at least one session key and encrypt the session key using the public key. The encrypted session key can then be transmitted to the online configurable enterprise server where it can be decrypted using the server private key. The online configurable intelligent electronic cryptographic module can also derive a private key useable to decrypt an encrypted session key transmitted by the online configurable enterprise server. It is contemplated that the session key can then be used to encrypt messages and responses transmitted between the online configurable enterprise server and the online configurable intelligent electronic cryptographic module.

The online configurable intelligent electronic cryptographic module can also include one or more server side ports such as an interface for a radio a modem an Ethernet a satellite or similar interfaces for receiving encrypted and non encrypted messages from the online configurable enterprise server and transmitting encrypted or non encrypted responses to the online configurable enterprise server.

The online configurable intelligent electronic cryptographic module can further include one or more non encrypted ports such as a RS232 KB9 or RS45 terminal for transmitting decrypted or non encrypted messages to one or more intelligent electronic devices and receiving non encrypted responses from the intelligent electronic devices.

It is contemplated that the one or more server side ports non encrypted ports or combinations thereof can be an interface adapted for engaging a serial port a cellular modem a standard modem a wireline modem a satellite network a Transfer Connection Protocol Internet Protocol an Ethernet a radio network a fiber optic network or combinations thereof.

The data storage of the online configurable intelligent electronic cryptographic module can include a log for storing information such as configuration changes communication statistics and data from one or more intelligent electronic devices the online configurable enterprise server from the online configurable intelligent electronic cryptographic module.

In a contemplated embodiment the online configurable intelligent electronic cryptographic module can include a telemetry interface such as an interface for a modem radio Ethernet or satellite in communication with the first processor and the online configurable enterprise server.

In an embodiment the online configurable intelligent electronic cryptographic module can also include a means for wirelessly transmitting messages and responses between the intelligent electronic devices and the online configurable enterprise server. Wireless transmission means can include spreadspectrum radios multipoint radios satellite transmission means cellular transmission means and other similar means.

The present system can also include a configurable server interface which can include a server application programming interface such as OLE for Process Control OPC in communication between one or more client devices having client interfaces and the online configurable enterprise server.

In a contemplated embodiment the present system can include one or more additional enterprise servers in communication with the intelligent electronic devices. Additional enterprise servers can be used to provide online configurability and communication when the primary online configurable enterprise server is damaged or reaches capacity. For example if an enterprise server in California is damaged by an earthquake a second enterprise server in New York remote from the disaster site can seamlessly resume the functions of the damaged enterprise server without interruption of service or functionality. Additional enterprise servers can also be used to independently and simultaneously provide online configurability and communication with the same or different online configurable intelligent electronic cryptographic modules and intelligent electronic devices as the primary online configurable enterprise server.

Each of the intelligent electronic devices the online configurable enterprise server the online configurable intelligent electronic cryptographic module or combinations thereof can be in communication via a network such as the internet a local area network a wide area network a fiber optic network a satellite network a cellular network a virtual private network or other similar networks.

It is further contemplated that each of the intelligent electronic devices the online configurable enterprise server the online configurable intelligent electronic cryptographic module or combinations thereof can be in simultaneous communication via multiple networks.

In an embodiment the online configurable enterprise server can be in communication with a first network a first intelligent electronic device can be in communication with a second network and a second intelligent electronic device can be in communication with a third network and all three components can communicate via their respective networks.

It is contemplated that the online configurable enterprise server the online configurable intelligent electronic cryptographic module one or more of the intelligent electronic devices or combinations thereof can be adapted to engage at least two industry standard protocols simultaneously.

The industry standard protocols can include a MODBUS a DNP3.0 a BSAP a Megaco H.248 protocol simple message transfer protocol SMTP a short message service SMS protocol a multimedia message service MMS protocol an enhanced message service EMS protocol a media gateway control protocol MGCP a SIP protocol a H.323 protocol an ISDN protocol a PSTN protocol and combinations thereof.

Intelligent electronic cryptographic module is shown having secure enclosure which can be any kind of durable housing including tamper proof and weather resistant enclosures. Intelligent electronic cryptographic module is depicted having a first processor in communication with a first data storage . First processor is also in communication with a first cryptography chip .

A power supply is also depicted within intelligent electronic cryptographic module in communication with first processor for supplying power to first processor and other components of intelligent electronic cryptographic module .

Intelligent electronic cryptographic module is shown having a server side port for receiving encrypted message and non encrypted message and for transmitting encrypted response and non encrypted response to an enterprise server via telemetry interface and server telemetry interface . While only one server side port is depicted intelligent electronic cryptographic module can have any number of server side ports including separate ports for encrypted communication non encrypted communication and mixed mode communication.

Intelligent electronic cryptographic module is also depicted having a non encrypted port for receiving first non encrypted response from first remote terminal unit second non encrypted response from second remote terminal unit and third non encrypted response from third remote terminal unit . While intelligent electronic cryptographic module is depicted in communication with three remote terminal units it is contemplated that intelligent electronic cryptographic module can be in communication with any type and any number of intelligent electronic devices.

It is contemplated that first processor can use first cryptography chip to selectively encrypt first non encrypted response second non encrypted response and third non encrypted response prior to transmitting each response to enterprise server . It is contemplated that non encrypted responses can also be transmitted to enterprise server such as when a low priority remote terminal unit does not require secure encryption.

Non encrypted port is also shown transmitting non encrypted message to second remote terminal unit and a decrypted message to a third remote terminal unit

First remote terminal unit is shown having first RTU processor and first RTU data storage . First RTU data storage has computer instructions for instructing first RTU processor to transmit data to enterprise server via intelligent electronic cryptographic module .

Second remote terminal unit is shown having second RTU processor and second RTU data storage . Second RTU data storage has computer instructions for instructing second RTU processor to transmit data to enterprise server via intelligent electronic cryptographic module .

Third remote terminal unit is shown having third RTU processor and third RTU data storage . Third RTU data storage has computer instructions for instructing third RTU processor to transmit data to enterprise server via intelligent electronic cryptographic module .

Third remote terminal unit is depicted having an analog to digital converter and computer instructions in third RTU data storage for instructing third RTU processor to selectively store and transmit digital representations measured by third remote terminal unit . Third remote terminal unit also has a bidirectional port for transmitting the digital representations to enterprise server via intelligent electronic cryptographic module and receiving commands and responses from enterprise server .

Enterprise server is shown having a server processor in communication with server data storage . Server data storage is shown having a server authentication module a server protocol module and a server connection module . Server data storage also includes computer instructions for reconfiguring first remote terminal unit second remote terminal unit or third remote terminal unit . Server data storage is further depicted having server configuration database . Enterprise server is also shown having server power supply in communication with server processor .

Enterprise server is also having a server removable data storage in communication with sever processor via a server port such as a universal serial bus port. Server removable data storage has a server cryptography chip which is contemplated to be substantially similar to first cryptography chip . While server authentication module is depicted in server data storage it is also contemplated that server authentication module can be contained within server removable data storage or in memory within server cryptography chip .

A first client device having first client interface a second client device having second client interface and a third client device having third client interface are shown in communication with enterprise server via configurable server interface and server application protocol interface . First client device second client device and third client device can be used to transmit reconfiguration commands to enterprise server any of first remote terminal unit second remote terminal unit or third remote terminal unit or intelligent electronic cryptographic module and to receive data and responses.

First client device second client device and third client device can be any type of client device including computers cellular telephones personal digital assistants enterprise data servers and other similar devices.

Referring now to a diagram of an embodiment of the intelligent electronic cryptographic module is depicted.

Intelligent electronic cryptographic module is shown having first processor in communication with first data storage and power supply .

Removable data storage device having first cryptography chip is shown in communication with intelligent electronic cryptographic module such as via a universal serial bus port such that first processor can use first cryptography chip to encrypt and decrypt messages and responses. It is contemplated that use of first cryptography chip within removable data storage device can allow modules that lack built in cryptography capability to incorporate use of first cryptography chip .

Intelligent electronic cryptographic module is also shown having server side port telemetry interface and non encrypted port .

First data storage is depicted having authentication module and cryptographic application programming interface CAPI . First data storage is also depicted having computer instructions for instructing first processor to perform as a soft remote terminal unit.

While depicts authentication module within first data storage it is also contemplated that application module can be contained within removable data storage device or in memory within first cryptography chip .

First data storage additionally has computer instructions for instructing first processor to select a protocol module. Protocol module is depicted within first data storage . While a single protocol module is depicted any number of selectable protocol modules can be included within first data storage .

Computer instructions for instructing first processor to select an appropriate telemetry method using protocol module are also included in first data storage .

First data storage also includes computer instructions for instructing first processor to authenticate that the enterprise server is authorized to transmit to one or more remote terminal units and computer instructions for instructing first processor to authenticate that one or more remote terminal units are authorized to transmit to the enterprise server.

First data storage has computer instructions for instructing first processor to decrypt encrypted messages from the enterprise server using first cryptography chip and computer instructions for instructing first processor to encrypt non encrypted responses from one or more remote terminal units using first cryptography chip .

First data storage further has computer instructions for instructing first processor to receive encrypted messages from the enterprise server and computer instructions for instructing first processor to transmit decrypted messages to one or more remote terminal units.

First data storage additionally has computer instructions for instructing first processor to receive non encrypted responses from remote terminal units and computer instructions for instructing first processor to transmit encrypted responses to the enterprise server.

Computer instructions for instructing first processor to embed a digital signature in the enterprise server are also depicted within first data storage . Computer instructions for instructing first processor to embed a digital signature in one or more remote terminal units are further depicted within first data storage . Additionally computer instructions for instructing first processor to validate the digital signatures of the enterprise server and remote terminal units are also depicted.

First data storage is also shown including a log for storing information from intelligent electronic cryptographic module relating to events in the intelligent electronic cryptographic module such as configuration changes.

Referring now to a diagram depicting an embodiment of first cryptography chip is shown. It is contemplated that server cryptography chip can be identical or substantially similar to first cryptography chip as depicted in .

First cryptography chip is shown having cryptographic tamper resistant memory which is contemplated to be effective against both electronic and physical attempts to penetrate encryption algorithms.

Cryptographic tamper resistant memory is depicted containing encryption algorithms decryption algorithms stored keys a random number generator and certificates for establishing digital signatures.

First cryptography chip can include any number of encryption or decryption algorithms keys random number generators or digital signatures limited only by the capacity of cryptographic tamper resistant memory .

While these embodiments have been described with emphasis on the embodiments it should be understood that within the scope of the appended claims the embodiments might be practiced other than as specifically described herein.

