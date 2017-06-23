---

title: Method and apparatus for adaptive transport injection for playback
abstract: There are provided a method and apparatus for adaptive transport injection for playback. The apparatus includes a playback manager for managing at least one buffer to maintain a fullness of the at least one buffer for a data playback by adapting a data injection size, relating an amount of data injected at a given time into the at least one buffer, to smallest available space in the at least one buffer.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09432729&OS=09432729&RS=09432729
owner: Thomson Licensing
number: 09432729
owner_city: Boulogne-Billancourt
owner_country: FR
publication_date: 20070126
---
This application claims the benefit under 35 U.S.C. 365 of International Application PCT US2007 001989 filed Jan. 26 2007 which was published in accordance with PCT Article 21 2 on Aug. 16 2007 in English and which claims the benefit of U.S. provisional patent application No. 60 771 376 filed Feb. 8 2006.

The present principles relate generally to data playback and more particularly to a method and apparatus for adaptive transport injection for transport stream playback.

There are potentially several clients for a recorded Moving Picture Experts Group MPEG or Digital Broadcast System DBS transport stream. At the time of recording corresponding buffer levels are maintained by the broadcaster. However when this data is stored to a medium for playback the buffer levels have to be maintained in order to prevent overflowing a client s buffer and losing any of the data and underflowing the client s buffer and interrupting the playback of the data.

These and other drawbacks and disadvantages of the prior art are addressed by the present principles which are directed to a method and apparatus for adaptive transport injection for transport stream playback.

According to an aspect of the present principles there is provided an apparatus. The apparatus includes a playback manager for managing at least one buffer to maintain a fullness of the at least one buffer for a data playback by adapting a data injection size relating an amount of data injected at a given time into the at least one buffer to smallest available space in the at least one buffer.

According to another aspect of the present principles there is provided a method for playing back media content. The method includes managing at least one buffer to maintain a fullness of the at least one buffer for a data playback by adapting a data injection size relating an amount of data injected at a given time into the at least one buffer to smallest available space in the at least one buffer.

These and other aspects features and advantages of the present principles will become apparent from the following detailed description of exemplary embodiments which is to be read in connection with the accompanying drawings.

The present principles are directed to a method and apparatus for adaptive transport injection for transport stream playback.

The present description illustrates the present principles. It will thus be appreciated that those skilled in the art will be able to devise various arrangements that although not explicitly described or shown herein embody the present principles and are included within its spirit and scope.

All examples and conditional language recited herein are intended for pedagogical purposes to aid the reader in understanding the present principles and the concepts contributed by the inventor s to furthering the art and are to be construed as being without limitation to such specifically recited examples and conditions.

Moreover all statements herein reciting principles aspects and embodiments of the present principles as well as specific examples thereof are intended to encompass both structural and functional equivalents thereof. Additionally it is intended that such equivalents include both currently known equivalents as well as equivalents developed in the future i.e. any elements developed that perform the same function regardless of structure.

Thus for example it will be appreciated by those skilled in the art that the block diagrams presented herein represent conceptual views of illustrative circuitry embodying the present principles. Similarly it will be appreciated that any flow charts flow diagrams state transition diagrams pseudocode and the like represent various processes which may be substantially represented in computer readable media and so executed by a computer or processor whether or not such computer or processor is explicitly shown.

The functions of the various elements shown in the figures may be provided through the use of dedicated hardware as well as hardware capable of executing software in association with appropriate software. When provided by a processor the functions may be provided by a single dedicated processor by a single shared processor or by a plurality of individual processors some of which may be shared. Moreover explicit use of the term processor or controller should not be construed to refer exclusively to hardware capable of executing software and may implicitly include without limitation digital signal processor DSP hardware read only memory ROM for storing software random access memory RAM and non volatile storage.

Other hardware conventional and or custom may also be included. Similarly any switches shown in the figures are conceptual only. Their function may be carried out through the operation of program logic through dedicated logic through the interaction of program control and dedicated logic or even manually the particular technique being selectable by the implementer as more specifically understood from the context.

In the claims hereof any element expressed as a means for performing a specified function is intended to encompass any way of performing that function including for example a a combination of circuit elements that performs that function or b software in any form including therefore firmware microcode or the like combined with appropriate circuitry for executing that software to perform the function. The present principles as defined by such claims reside in the fact that the functionalities provided by the various recited means are combined and brought together in the manner which the claims call for. It is thus regarded that any means that can provide those functionalities are equivalent to those shown herein.

Reference in the specification to one embodiment or an embodiment of the present principles means that a particular feature structure characteristic and so forth described in connection with the embodiment is included in at least one embodiment of the present principles. Thus the appearances of the phrase in one embodiment or in an embodiment appearing in various places throughout the specification are not necessarily all referring to the same embodiment.

Turning to an exemplary client server environment to which the present principles may be applied is indicated generally by the reference numeral . The client server environment includes a set of clients a hard drive a disk extraction manager link multiplexer Application Programming Interfaces APIs a transport packet circular buffer an injection manager a transport Packet Identifier Packetized Elementary Stream PID PES filter and a set of circular buffers .

It is to be appreciated that the disk extraction manager and the injection manager may be collectively referred to herein as playback manager . Moreover it is to be appreciated that the hard drive the disk extraction manager the link multiplexer Application Programming Interfaces APIs the transport packet circular buffer the injection manager and the transport PID PES filter can be considered to be part of a server side of the client server environment .

In an exemplary embodiment the server side writes audio video data and or so forth collectively referred to herein as data into one or more buffers in the set of buffers and one or more clients in the set of clients reads the data out there from. For example the data may be read out by a decoder of one or more of the clients.

In an embodiment the address space represented by the set of buffers is shared between the server side and the set of clients so that one or more clients in the set of clients may act upon the data as such data resides in the set of buffers .

Of course as noted above embodiments described herein are not mutually exclusive and thus may be combined and or otherwise modified and implemented in accordance with the teachings of the present principles while maintaining the scope of the present principles. That is given the teachings of the present principles provided herein one of ordinary skill in this and related arts may contemplate these and other arrangements of the elements of the client server environment with respect to a server side and a client side as well as the exchanging of data there between while maintaining the scope of the present principles.

It is to be further appreciated that while circular buffers are described with respect to given the teachings of the present principles provided herein one of ordinary skill in this and related arts will contemplate this and other types of memory devices and configurations that may be used in accordance with the present principles while maintaining the scope of the present principles.

In accordance with the present principles a method and apparatus are provided for managing video audio and or data buffers for playback from a stored transport stream.

In an embodiment all client buffers e.g. buffers are kept full by adapting the size of the packet injection to the smallest available space in the clients buffers. In this embodiment data is extracted from the stored medium and injected so as to prevent underflow or overflow of the clients buffers.

It is to be appreciated that as used herein the phrase client buffers refers to buffers that are part of a client s and or are accessible by a client s . Thus in some cases the client buffers may be part of another entity e.g. the server but are nonetheless accessible by a client s .

In an embodiment the injection manager maintains full client buffers but restricts injection size to be limited by the smallest free space in the clients circular buffers. The injection system runs and determines the smallest free space available in the clients output buffer. An injection is setup to put this number of bytes into the transport. This restriction guarantees that the smallest buffer will not overflow. The size of the injection may be changed to reflect the size of the free space.

An embodiment of the present principles will initially be described by the following C language pseudocode followed by further descriptions with respect to . The pseudocode describes functions performed by the injection manager and the disk extraction manager of .

It is to be appreciated that the term bytes in the pseudo code may be replaced with size as the present principles are not dependent upon the use of bytes of data and thus other measures of data e.g. bits etc. may also be employed while maintaining the scope of the present principles.

Turning to an exemplary method for adaptive transport injection for playback of transport data is indicated generally by the reference numeral .

The method includes a start block that passes control to a function block . The function block retrieves the number of relevant circular buffers in memory to be checked for empty space and passes control to a function block .

The function block searches through all the relevant circular buffers by index to determine the minimum free space in the relevant circular buffers hereinafter the minimum circular buffer free space and passes control to a decision block . The decision block determines whether or not the minimum circular buffer free space is greater than the data available in the transport packet circular buffer. If so then control is passed to a function block . Otherwise control is passed to a function block .

The function block designates the minimum free space to be equal to the amount of available data in the transport packet circular buffer and passes control to a function block .

The function block designates the minimum free space to be equal to the minimum circular buffer free space and passes control to the decision block .

The decision block determines whether or not the designated minimum free space amount of available data in the transport packet circular buffer or the minimum circular buffer free space is greater than a minimum injection size. If so then control is passed to a function block . Otherwise control is passed to a function block .

The function block reads the data from the transport packet circular buffer injects the data from the transport packet circular buffer into the transport PID PES filter for PID filtering and passes control to a function block . The function block performs PID filtering of the injected data and passes control to a function block . The function block injects the data from the transport PID PES filter into at least one of the relevant circular buffers and passes control to a function block . The function block notifies a disk extraction manager that data has been removed from the transport packet circular buffer and passes control to a decision block .

The decision block determines whether or not the designated minimum free space is equal to a maximum injection size. If so then control is returned to the function block . Otherwise control is passed to the function block .

The function block waits for a data event e.g. data is now available for injection or timeout and passes control to a decision block . The decision block determines whether or not a data event or a timeout has occurred. If so then control is returned to the function block . Otherwise control is returned to the decision block .

Turning to an exemplary method for adaptive disk extraction is indicated generally by the reference numeral . The method includes a start block that passes control to a function block . The function block determines the amount of fee space available in the transport packet circular buffer and passes control to a decision block . The decision block determines whether or not the available amount of free space in the transport packet circular buffer is greater than a minimum read requirement for the hard drive. If so then control is passed to a function block . Otherwise control is passed to a function block .

The function block limits the size of reads from the hard drive to the maximum read requirement for the hard drive and passes control to a function block .

The function block copies the next available bytes from the hard drive to the transport packet circular buffer and passes control to a function block .

The function block informs the injector manager that data is available for injection and passes control to a decision block . The decision block determines whether or not the available amount of free space in the transport packet circular buffer is equal to a maximum read requirement for the hard drive. If so then control is returned to the function block . Otherwise control is passed to the function block .

The function block waits for a data read event e.g. data is now available for extraction or timeout and passes control to the decision block . The decision block determines whether or not a data read event or a timeout has occurred. If so then control is returned to the function block . Otherwise control is returned to the decision block .

A description will now be given of some of the many attendant advantages features of the present invention some of which have been mentioned above. For example one advantage feature is an apparatus that includes a playback manager for managing at least one buffer to maintain a fullness of the at least one buffer for a data playback by adapting a data injection size relating an amount of data injected at a given time into the at least one buffer to smallest available space in the at least one buffer. Another advantage feature is the apparatus having the playback manager as described above wherein the at least one buffer includes a plurality of buffers and the playback manager determines the smallest available space based on all of the plurality of buffers. Yet another advantage feature is the apparatus having the playback manager as described above wherein the playback manager determines the smallest available space based on an index of the at least one buffer.

Moreover another advantage feature is the apparatus having the playback manager as described above wherein the playback manager extracts the data from a remote storage device into a transport packet buffer and injects the data from the transport packet buffer into the at least one buffer. Further another advantage feature is the apparatus having the playback manager as described above wherein the playback manager limits a size of reads from the remote storage device to prevent an overflow condition of the transport packet buffer when an amount of free space available in the transport packet buffer is greater than a minimum read requirement for the remote storage device. Also another advantage feature is the apparatus having the playback manager as described above wherein the playback manager injects into the transport packet buffer an available amount of data greater than the smallest available space in the at least one buffer when the available amount of data is less than the smallest available space in the at least one buffer.

Additionally another advantage feature is the apparatus having the playback manager as described above wherein the playback manager rechecks the at least one buffer to determine the smallest available space subsequent to a wait period when any of an insufficient amount of data is available or the smallest available space in the at least one buffer is greater than a minimum injection size. Moreover another advantage feature is the apparatus having the playback manager as described above wherein the wait period ends upon an occurrence of any of a data available event or a timeout.

Further another advantage feature is the apparatus having the playback manager as described above wherein the playback manager adapts the data injection size based on changes in the smallest available space in the at least one buffer.

These and other features and advantages of the present principles may be readily ascertained by one of ordinary skill in the pertinent art based on the teachings herein. It is to be understood that the teachings of the present principles may be implemented in various forms of hardware software firmware special purpose processors or combinations thereof.

Most preferably the teachings of the present principles are implemented as a combination of hardware and software. Moreover the software may be implemented as an application program tangibly embodied on a program storage unit. The application program may be uploaded to and executed by a machine comprising any suitable architecture. Preferably the machine is implemented on a computer platform having hardware such as one or more central processing units CPU a random access memory RAM and input output I O interfaces. The computer platform may also include an operating system and microinstruction code. The various processes and functions described herein may be either part of the microinstruction code or part of the application program or any combination thereof which may be executed by a CPU. In addition various other peripheral units may be connected to the computer platform such as an additional data storage unit and a printing unit.

It is to be further understood that because some of the constituent system components and methods depicted in the accompanying drawings are preferably implemented in software the actual connections between the system components or the process function blocks may differ depending upon the manner in which the present principles are programmed. Given the teachings herein one of ordinary skill in the pertinent art will be able to contemplate these and similar implementations or configurations of the present principles.

Although the illustrative embodiments have been described herein with reference to the accompanying drawings it is to be understood that the present principles is not limited to those precise embodiments and that various changes and modifications may be effected therein by one of ordinary skill in the pertinent art without departing from the scope or spirit of the present principles. All such changes and modifications are intended to be included within the scope of the present principles as set forth in the appended claims.

