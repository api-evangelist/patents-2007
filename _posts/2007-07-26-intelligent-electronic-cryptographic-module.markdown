---

title: Intelligent electronic cryptographic module
abstract: An intelligent electronic cryptographic module comprising a processor in communication with data storage, a cryptography chip for encrypting and decrypting messages and responses, at least one server-side port for receiving and transmitting encrypted and non-encrypted messages and responses between the intelligent electronic cryptographic module and an enterprise server, and at least one non-encrypted port for receiving and transmitting decrypted and non-encrypted messages and responses between the intelligent electronic cryptographic module and at least one intelligent electronic device. The data storage comprises computer instructions for instructing the processor to select a protocol module and telemetry method, authenticate the enterprise server and intelligent electronic cryptographic module, encrypt and decrypt messages and responses using the cryptography chip, and transmit and receive messages and responses.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=07673338&OS=07673338&RS=07673338
owner: DJ Inventions, LLC
number: 07673338
owner_city: Houston
owner_country: US
publication_date: 20070726
---
The present embodiments relate to an intelligent electronic cryptographic module for communication between at least one intelligent electronic device and an enterprise server.

A need exists for an intelligent electronic cryptographic module able to selectively encrypt decrypt and securely transmit messages commands data and responses between an enterprise server and one or more intelligent electronic devices.

A further need exists for an intelligent electronic cryptographic module able to perform mixed mode transmission selectively encrypting specified messages or messages from a specified source while omitting encryption of one or more other messages.

A need exists for an intelligent electronic cryptographic module that can be configured to perform different mixed mode transmissions on line without interrupting the normal functions of the intelligent electronic cryptographic module the enterprise server or any of the intelligent electronic devices in communication with the intelligent electronic cryptographic module.

A need also exists for an intelligent electronic cryptographic module that is able to reconfigure one or more intelligent electronic devices or be reconfigured online without interrupting the normal functions of the intelligent electronic cryptographic module the enterprise server or any of the other intelligent electronic devices in communication with the module.

Before explaining the present embodiments in detail it is to be understood that the embodiments are not limited to the particular embodiments and that they can be practiced or carried out in various ways.

The present intelligent electronic cryptographic module provides enhanced security more efficiently than conventional encryption means by permitting online real time reconfiguration of the module and attached intelligent electronic devices. Through this on line reconfiguration the intelligent electronic cryptographic module any of the attached intelligent electronic devices or a central enterprise server can be reconfigured without interrupting service to any of the intelligent electronic devices or interrupting the functions of the intelligent electronic devices or the intelligent electronic cryptographic module thereby maintaining continuity of service and saving costs and hindrances associated with deactivating modules and units.

The intelligent electronic cryptographic module can provide secure communication between an enterprise server and various kinds of intelligent electronic devices including remote terminal units programmable logic controllers and other similar intelligent electronic devices.

Even Legacy Remote Terminal Units which lack the hardware or software to be reconfigured on line can be selectively reconfigured without affecting the function of any intelligent electronic devices the enterprise server or the intelligent electronic cryptographic module. Additionally data messages and responses from legacy remote terminal units can be selectively encrypted and decrypted using the online configurable intelligent electronic cryptographic module.

The intelligent electronic cryptographic module can include software enabling the intelligent electronic cryptographic module to both function as an online configurable remote terminal unit for performing a variety of processes and to function as an online configurable intelligent electronic cryptographic module selectively encrypting and decrypting messages and responses between an online configurable enterprise server and one or more intelligent electronic devices.

The present intelligent electronic cryptographic module further allows for efficient security by permitting pass through transmission of messages responses commands and data independent of the associated gateway protocols. The module can provide mixed mode transmission selectively encrypting only specified messages or messages from a specified source saving time costs and bandwidth while permitting other data to pass through the cryptographic module. The specifications relating to the mixed mode transmission can be reconfigured on line in real time without interrupting the functions of the intelligent electronic cryptographic module.

The pass through capabilities of the present intelligent electronic cryptographic module allow the connectivity and security between an enterprise server the intelligent electronic cryptographic module and one or more intelligent electronic devices to be efficiently and effectively tested prior to encrypting transmissions and at any time during service.

The present intelligent electronic cryptographic module provides enhanced security through use of authentication means such as digital certificates and keys and tamper proof encryption through use of a cryptography chip. The embodied cryptography chip can be built into the module or separately attached using a removable data storage media. The cryptography chip is compatible with the Windows CE Operating System Windows XP Windows 2003 and other similar operating systems and can be utilized through a standard cryptographic application programming interface CAPI .

The authentication means provided through use of the cryptography chip within the intelligent electronic cryptographic module provide greater security than conventional means which typically do not include authentication of system components. The authentication of the enterprise server the intelligent electronic cryptographic module and one or more intelligent electronic devices can be selectively performed as frequently as needed to maintain security or as infrequently as needed to conserve costs and bandwidth.

The present embodiments relate to an intelligent electronic cryptographic module for communication between an enterprise server and at least one intelligent electronic device. An intelligent electronic device can be a remote terminal unit RTU such as an Autosol RTU 4000 a Bristol Babcock 3330 RTU an Emerson ROC 809 or similar remote terminal units. An intelligent electronic device can also be a programmable logic controller PLC or other similar intelligent electronic devices.

The intelligent electronic cryptographic module can include a secure enclosure which can be any kind of durable housing including secure tamper resistant and weather resistant enclosures.

One or more power supplies can be disposed within the secure enclosure for supplying power to each of the components of the intelligent electronic cryptographic module. It is contemplated that the power supplies can include direct current sources alternating current sources rechargeable power sources replaceable power sources renewable power sources or combinations thereof.

The intelligent electronic cryptographic module has a first processor disposed within the secure enclosure. The first processor can be in communication with one or more data storage media and a cryptographic application programming interface CAPI . The data storage can include removable memory non removable memory flash memory or combinations thereof. The data storage can include a first authentication module however it is contemplated that the first authentication module can instead be included in memory within a first cryptography chip disposed within the secure enclosure in communication with the first processor.

The first processor is adapted to authenticate the enterprise server any of the remote terminal units or combinations thereof. The first processor is also adapted to provide encrypted and non encrypted communication with the enterprise server and non encrypted communication with one or more of the remote terminal units.

A first cryptography chip such as a Spyrus Rosetta or a Spyrus Lynks made by Spyrus of San Jose Calif. is disposed within the secure enclosure in communication with the first processor for decrypting messages from the enterprise server encrypting responses from one or more of the intelligent electronic devices or combinations thereof.

In an embodiment the first cryptography chip can be disposed within a first removable data storage device which can be in communication with the processor through a port such as a universal serial bus port. This embodiment can advantageously allow the cryptography chip to be utilized in after market applications.

It is contemplated that the first cryptography chip can include cryptographic tamper resistant memory which can contain one or more encryption and decryption algorithms one or more keys a random number generator at least one certificate for digital signatures an authentication module and combinations thereof.

The intelligent electronic cryptographic module can include at least one server side port such as such as an interface for a radio a modem an Ethernet a satellite or similar interfaces for receiving encrypted messages non encrypted messages or combinations thereof from the enterprise server. The one or more server side ports can also be used to transmit encrypted and non encrypted responses from the intelligent electronic devices to the enterprise server via the intelligent electronic cryptographic module.

Both the encrypted and non encrypted messages can include reconfiguration commands for reconfiguring one or more of the intelligent electronic devices.

The intelligent electronic cryptographic module also has at least one non encrypted port such as a RS232 KB9 or RS45 terminal for transmitting one or more decrypted messages or encrypted messages to one or more of the intelligent electronic devices and receiving non encrypted responses from the intelligent electronic devices.

It is contemplated that the one or more server side ports non encrypted ports or combinations thereof can be an interface adapted for engaging a serial port a cellular modem a standard modem a wireline modem a satellite network a Transfer Connection Protocol Internet Protocol an Ethernet a radio network a fiber optic network or combinations thereof.

The server side ports the non encrypted ports or combinations thereof can further be adapted to engage at least two industry standard protocols simultaneously. Contemplated industry standard protocols can include a MODBUS a DNP3.0 a BSAP a Megaco H.248 protocol simple message transfer protocol SMTP a short message service SMS protocol a multimedia message service MMS protocol an enhanced message service EMS protocol a media gateway control protocol MGCP a SIP protocol a H.323 protocol an ISDN protocol a PSTN protocol and combinations thereof.

The data storage media of the present intelligent electronic cryptographic module can include computer instructions for instructing the first processor to perform as a soft remote terminal unit as described in U.S. Pat. No. 6 628 992.

It is contemplated that when the intelligent electronic cryptographic module performs as a remote terminal unit in addition to performing intelligent encryption and decryption functions the use of additional intelligent electronic devices in communication with the intelligent electronic cryptographic module can be omitted and the intelligent electronic cryptographic module can both function as a cryptographic module and as a remote terminal unit simultaneously.

When the intelligent electronic cryptographic module functions as a remote terminal unit the module advantageously becomes both an intelligent cryptographic module and an online configurable remote terminal unit. This is a noteworthy advantage over conventional Legacy Remote Terminal Units which typically lack hardware or software to permit online configurability or encrypted transmissions. Use of the intelligent electronic cryptographic module as a remote terminal unit also provides enhanced security by eliminating the clear text link between the intelligent electronic cryptographic module and a Legacy Remote Terminal Unit.

It is further contemplated however that any number of additional remote terminal units or other intelligent electronic devices can be in communication with the intelligent electronic cryptographic module independent of the online configurability of any of the intelligent electronic devices and independent of whether the intelligent electronic cryptographic module is also functioning as a soft remote terminal unit.

The data storage also includes computer instructions for instructing the first processor to select at least one protocol module such as BSAP MODBUS ROC DNP 3.0 or other similar protocol modules for communication with one or more of the intelligent electronic devices the enterprise server or combinations thereof. The computer instructions also instruct the first processor to select at least one appropriate telemetry method such as a modem a radio an Ethernet a satellite or other similar telemetry methods for transmitting and receiving messages using the one or more selected protocol modules. The use of a telemetry method can be facilitated through use of one or more connection modules.

The computer instructions further instruct the processor to authenticate at least once that the intelligent electronic cryptographic module is authorized to transmit to the enterprise server and to authenticate at least once that the enterprise server is authorized to transmit to the intelligent electronic cryptographic module. This provides an additional level of security over conventional means which typically lack authentication. The authentication of the enterprise server and the intelligent electronic cryptographic module can be performed as frequently as necessary to ensure security or as infrequently as necessary to conserve costs and bandwidth.

The data storage also includes computer instructions for instructing the first processor to decrypt encrypted messages transmitted from the enterprise server using the first cryptography chip and to transmit decrypted messages to one or more of the intelligent electronic devices. The computer instructions also instruct the first processor to receive non encrypted responses from intelligent electronic devices encrypt the responses using the cryptography chip and transmit the encrypted responses to the enterprise server.

In an embodiment the data storage can include computer instructions for instructing the processor to embed a digital signature in the enterprise server embed a digital signature in the intelligent electronic cryptographic module and validate the digital signatures prior to encrypting or transmitting responses and decrypting or transmitting messages.

It is also contemplated that the data storage can include computer instructions for instructing the processor to receive at least one public and exchange key from the enterprise server. The public exchange key can be derived by the server processor or the server cryptography chip. The computer instructions further instruct the processor to derive at least one session key and encrypt the session key using the public exchange key. The encrypted session key can then be transmitted to the enterprise server. It is contemplated that the session key can then be used to encrypt messages and responses transmitted between the enterprise server and the intelligent electronic cryptographic module.

It is further contemplated that the computer instructions could instruct the first processor to derive at least one public and at least one private exchange key and transmit the public exchange key to the enterprise server. The computer instructions could also instruct the first processor to receive an encrypted session key derived by the enterprise server and encrypted by the enterprise server using the public key. The encrypted session key can then be decrypted using the private key and used to encrypt messages and responses transmitted between the enterprise server and the intelligent electronic cryptographic module.

In a contemplated embodiment the intelligent electronic cryptographic module can include a telemetry interface such an interface for a modem a radio an Ethernet a satellite or other similar telemetry methods in communication with the first processor and the enterprise server.

In an embodiment the intelligent electronic cryptographic module can also include a means for wirelessly transmitting messages and responses between the intelligent electronic devices and the enterprise server. Wireless transmission means can include spreadspectrum radios multipoint radios satellite transmission means cellular transmission means and other similar means.

It is contemplated that the enterprise server can include a server processor in communication with server data storage a server telemetry interface such as a modem a radio a satellite or an Ethernet interface and a server port for receiving a removable data storage device having a second cryptography chip. The server data storage can include a server authentication module a server protocol module such as a BSAP a MODBUS or similar protocol modules and a server connection module such as a serial module a dial up module or a TCP IP module. It is contemplated that the server authentication module can also be resident in memory within the second cryptography chip.

The server data storage can include computer instructions for instructing the server processor to configure the enterprise server the intelligent electronic cryptographic module one or more of the intelligent electronic devices or combinations thereof.

In an embodiment the server data storage can also include a configuration software such as Autosol RTU Maintenance Environment ARME made by Automated Solutions of Houston Tex. for enabling the online reconfiguration of one or more intelligent electronic devices in communication with the enterprise server.

It is contemplated that the first cryptography chip in the intelligent electronic cryptographic module the second cryptography chip in the enterprise server or combinations thereof can be selectively activated to perform encryption and decryption functions and deactivated to allow messages to pass through without encryption or decryption on line without interruption of service to any of the intelligent electronic devices.

The data storage of the intelligent electronic cryptographic module can also include a log for storing information such as configuration changes communication statistics and data from one or more intelligent electronic devices from the intelligent electronic cryptographic module.

Referring now to a diagram depicting a system incorporating the present intelligent electronic cryptographic module is shown.

Intelligent electronic cryptographic module is shown having secure enclosure . Intelligent electronic cryptographic module is depicted having a first processor in communication with a first data storage . First processor is also in communication with a first cryptography chip .

A power supply is also depicted within intelligent electronic cryptographic module in communication with first processor for supplying power to first processor and other components of intelligent electronic cryptographic module .

Intelligent electronic cryptographic module is shown having a server side port for receiving encrypted message and non encrypted message and for transmitting encrypted response and non encrypted response to an enterprise server via telemetry interface and server telemetry interface . While only one server side port is depicted intelligent electronic cryptographic module can have any number of server side ports including separate ports for encrypted communication non encrypted communication and mixed mode communication.

Intelligent electronic cryptographic module is also depicted having a non encrypted port for receiving first non encrypted response from first remote terminal unit second non encrypted response from second remote terminal unit and third non encrypted response from third remote terminal unit . While intelligent electronic cryptographic module is depicted in communication with three remote terminal units it is contemplated that intelligent electronic cryptographic module can be in communication with any type and any number of intelligent electronic devices.

It is contemplated that first processor can use first cryptography chip to selectively encrypt first non encrypted response second non encrypted response and third non encrypted response prior to transmitting each response to enterprise server . It is contemplated that non encrypted responses can also be transmitted to enterprise server such as when a low priority remote terminal unit does not require secure encryption.

Non encrypted port is also shown transmitting non encrypted message to second remote terminal unit and a decrypted message to a third remote terminal unit

First remote terminal unit is shown having first RTU processor and first RTU data storage . First RTU data storage has computer instructions for instructing first RTU processor to transmit data to enterprise server via intelligent electronic cryptographic module .

Second remote terminal unit is shown having second RTU processor and second RTU data storage . Second RTU data storage has computer instructions for instructing second RTU processor to transmit data to enterprise server via intelligent electronic cryptographic module .

Third remote terminal unit is shown having third RTU processor and third RTU data storage . Third RTU data storage has computer instructions for instructing third RTU processor to transmit data to enterprise server via intelligent electronic cryptographic module .

Third remote terminal unit is depicted having an analog to digital converter and computer instructions in third RTU data storage for instructing third RTU processor to selectively store and transmit digital representations measured by third remote terminal unit . Third remote terminal unit also has a bidirectional port for transmitting the digital representations to enterprise server via intelligent electronic cryptographic module and receiving commands and responses from enterprise server .

Enterprise server is shown having a server processor in communication with server data storage . Server data storage is shown having a server authentication module a server protocol module and a server connection module . Server data storage also includes computer instructions for reconfiguring first remote terminal unit second remote terminal unit or third remote terminal unit . Server data storage is further depicted having server configuration database such as an Oracle or Microsoft Access database for restoring online configurations of the enterprise server when the server is reset. Enterprise server is also shown having server power supply in communication with server processor .

Enterprise server is also having a server removable data storage in communication with sever processor via a server port such as a universal serial bus port. Server removable data storage has a second cryptography chip which is contemplated to be substantially similar to first cryptography chip .

A first client device having first client interface a second client device having second client interface and a third client device having third client interface are shown in communication with enterprise server via configurable server interface such as OLE for Process Control OPC and server application protocol interface . First client device second client device and third client device can be used to transmit reconfiguration commands to enterprise server or any of first remote terminal unit second remote terminal unit or third remote terminal unit and to receive data and responses.

First client device second client device and third client device can be any type of client device including computers cellular telephones personal digital assistants enterprise data servers and other similar devices.

Referring now to a diagram of an alternative embodiment of intelligent electronic cryptographic module is depicted.

Intelligent electronic cryptographic module is shown having first processor in communication with first data storage and power supply .

Removable data storage device having first cryptography chip is shown in communication with intelligent electronic cryptographic module such as via a universal serial bus port such that first processor can use first cryptography chip to encrypt and decrypt messages and responses. It is contemplated that use of first cryptography chip within removable data storage device can allow modules that lack built in cryptography capability to incorporate use of first cryptography chip .

Intelligent electronic cryptographic module is also shown having server side port telemetry interface and non encrypted port .

First data storage is depicted having authentication module and cryptographic application programming interface CAPI . First data storage is also depicted having computer instructions for instructing first processor to perform as a soft remote terminal unit.

First data storage additionally has computer instructions for instructing first processor to select a protocol module. Protocol module is depicted within first data storage . While a single protocol module is depicted any number of selectable protocol modules can be included within first data storage .

Computer instructions for instructing first processor to select an appropriate telemetry method using protocol module are also included in first data storage .

First data storage also includes computer instructions for instructing first processor to authenticate that the enterprise server is authorized to transmit to one or more remote terminal units and computer instructions for instructing first processor to authenticate that one or more remote terminal units are authorized to transmit to the enterprise server.

First data storage has computer instructions for instructing first processor to decrypt encrypted messages from the enterprise server using first cryptography chip and computer instructions for instructing first processor to encrypt non encrypted responses from one or more remote terminal units using first cryptography chip .

First data storage further has computer instructions for instructing first processor to receive encrypted messages from the enterprise server and computer instructions for instructing first processor to transmit decrypted messages to one or more remote terminal units.

First data storage additionally has computer instructions for instructing first processor to receive non encrypted responses from remote terminal units and computer instructions for instructing first processor to transmit encrypted responses to the enterprise server.

Computer instructions for instructing first processor to embed a digital signature in the enterprise server are also depicted within first data storage . Computer instructions for instructing first processor to embed a digital signature in one or more remote terminal units are further depicted within first data storage . Additionally computer instructions for instructing first processor to validate the digital signatures of the enterprise server and remote terminal units are also depicted.

First data storage is also shown including a log for storing information from intelligent electronic cryptographic module relating to events in the intelligent electronic cryptographic module such as configuration changes.

Referring now to a diagram depicting an embodiment of first cryptography chip is shown. It is contemplated that second cryptography chip can be identical or substantially similar to first cryptography chip as depicted in .

First cryptography chip is shown having cryptographic tamper resistant memory which is contemplated to be effective against both electronic and physical attempts to penetrate encryption algorithms.

Cryptographic tamper resistant memory is depicted containing encryption algorithms decryption algorithms stored keys a random number generator and certificates for establishing digital signatures.

First cryptography chip can include any number of encryption or decryption algorithms keys random number generators or digital signatures limited only by the capacity of cryptographic tamper resistant memory .

While these embodiments have been described with emphasis on the embodiments it should be understood that within the scope of the appended claims the embodiments might be practiced other than as specifically described herein.

