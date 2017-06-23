---

title: Wireless USB hub
abstract: This invention provides a Wireless USB hub that includes a first port configured to communicate with a wired USB enabled device, a second port configured to communicate with a first wireless USB enabled device, and a controller that detects the wired USB enabled device and presents the wired USB enabled device as a native wireless USB enabled device to the first wireless USB enabled device.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=07761627&OS=07761627&RS=07761627
owner: QUALCOMM Incorporated
number: 07761627
owner_city: San Diego
owner_country: US
publication_date: 20071221
---
This application claims priority to U.S. provisional patent application Ser. No. 60 871 527 titled ENHANCED WIRELESS USB PROTOCOL AND HUB filed Dec. 21 2006 the disclosure of which is incorporated herein by reference.

This application is related to the following U.S. patent application Ser. No. 11 963 427 titled Enhanced Wireless USB Protocol filed Dec. 21 2007 assigned to a common assignee.

The present invention relates generally to Certified Wireless Universal Serial Bus WUSB interfaces. More specifically the present invention is related to improving the throughput of Certified Wireless USB Wire Adapter systems.

Universal Serial Bus USB is a serial bus standard for attaching electronic peripheral devices to a host computing device. It was designed for personal computers but its popularity has prompted it to also become commonplace on video game consoles PDAs portable DVD players mobile phones and other popular electronic devices. The goal of USB is to replace older serial and parallel ports on computers since these were not standardized and called for a multitude of device drivers to be developed and maintained.

USB was designed to allow peripherals to be connected without the need to plug expansion cards into the computer s expansion bus and to improve plug and play capabilities by allowing devices to be hot swapped wherein devices are connected or disconnected without powering down or rebooting the computer. When a device is first connected the host enumerates and recognizes it and loads the device driver needed for that device.

USB can connect peripherals such as mouse devices keyboards scanners digital cameras printers external storage devices etc. and has become the standard connection method for many of these devices.

The Wireless Universal Serial Bus Specification revision 1.0 published May 12 2005 available from the USB Implementers Forum Inc. describes and specifies extensions to wired USB which enable the use of wireless links in extended USB WUSB systems. These wireless extensions to the USB specification are referred to as Certified Wireless Universal Serial Bus or simply Wireless USB WUSB . The extensions build on existing wired USB specifications and WiMedia Alliance MAC and PHY ultra wide band UWB wireless technology.

The WUSB Specification includes descriptions and specifications of devices known as Wire Adapters WA . These devices are wired USB to Wireless USB adapters which allow legacy wired USB hosts and devices to be interconnected with WUSB devices in extended USB systems containing both wired and wireless links.

There are two types of Wire Adapters Host Wire Adapter HWA and Device Wire Adapter DWA which work in conjunction with each other. HWAs have a wired upstream USB port and a wireless downstream WUSB port allowing a wired USB host to communicate with WUSB devices.

DWAs have a wireless upstream WUSB port and one or more wired downstream USB ports allowing wired USB devices to communicate with a Wireless USB host.

The WUSB Specification Wire Adapter Protocol is used to transfer data through WAs and to control and manage WAs. Unfortunately the Wire Adapter Protocol as specified in the WUSB Specification in typical situations is very inefficient resulting in unacceptably low throughput. The inefficiency of the protocol is primarily attributable to two factors the protocol is chatty in that a number of non data messages conveying control and transfer complete status information are exchanged for each block of data transferred. In addition the protocol does not lend itself well to pipelining of data flow through the system resulting in high latency during transfer of data and therefore low throughput.

Therefore it would be desirable to have a method for improving throughput for devices in USB systems containing both wired and wireless USB devices.

An embodiment of the present invention provides a Wireless USB WUSB hub that allows wireless communication between wired USB devices and a host system. The WUSB hub acts as a proxy for the wired USB devices and presents them to the host system as if they were native WUSB devices. The WUSB hub presents an attached wired USB device as a unique WUSB device with its own device address or as a separate function on an already existing device the WUSB hub for instance which may enumerate as a Device Wire Adapter .

Another embodiment of the present invention provides an enhanced Wire Adapter Protocol for improving data throughput for a wireless USB system that includes wire adapters that wirelessly transmit data between a host system and a wired USB device. Using this protocol wire adapters automatically segment incoming data transfers into smaller segments wherein a wire adapter uses its buffer status to determine how much data to fetch. Data is transferred downstream without waiting to receive a complete data segment when a wire adapter receives a specified minimum amount of data from upstream. The enhanced protocol also dispenses with Transfer Complete messages and instead determines when a data transfer has completed by polling downstream for a transfer result. The wire adapters also employ forward pipe descriptors in conjunction with remote pipe descriptors to forward transfer requests downstream.

Embodiments of the present invention include improving the throughput of WUSB Wire Adapter systems. One embodiment includes streamlining the Wire Adapter Protocol to improve the throughout of WUSB Wire Adapter systems. Another embodiment includes presenting wired USB devices plugged into a WUSB hub as if they are native WUSB devices. This embodiment is referred to as a USB Device Proxy WUSB Hub or simply WUSB hub.

The current solution for connecting wired USB devices into WUSB systems is to plug them into a Device Wire Adapter DWA depicted in . Wired USB devices are plugged into the DWA using standard USB cables . The DWA in turn provided a wireless antenna that provides a wireless link to a USB host.

A corresponding Host Wire Adapter HWA may be used by the host system to communicate with the DWA or the DWA may communicate with the host system through a native WUSB host adapter.

Because the HWA and DWAs are recognized as USB devices the host system incorporates multiple software driver layers to enable communication with wired external USB devices via the HWA and DWAs .

The host has a wired USB root hub to which the HWA is connected whether external or internal to the host housing . Next is the root hub driver . The host has a separate HWA driver as well as a DWA driver . On top of these are device drivers that are specific to the external USB devices at the end of the chain. Each of the device drivers attaches to and communicates with the DWA driver .

Data is communicated from the host to the HWA through a wired connection. The HWA then uses a wireless protocol to transmit the data to one of the DWAs which in turn sends the data to the specified USB device or over a wired connection.

In the example shown in the data packet is preceded by Transfer Request while Transfer Request is preceded by Transfer Request . Transfer Requests and direct the HWA to send Transfer Request and data packet to the DWA. Transfer Request directs the DWA to send data packet to the USB device. A transfer request only appears as such to its intended device. For example the DWA transfer request looks like data to the HWA but looks like a transfer request to the DWA.

As explained above the current wireless USB systems use control packets Transfer Requests which are generated by multiple layers of drivers between the external device and its specific driver in the host in order to direct the flow of data to or from the target USB device. Unfortunately this design dramatically hampers throughput.

An embodiment of the present invention includes an Enhanced Wire Adapter Protocol that improves throughput by reducing the number of messages that are exchanged as a part of data transfer thereby reducing processing time and transfer time of the messages over the wired USB interfaces and wireless medium. Throughput is also increased by improving pipelining of data flow through the system which reduces transfer latency.

The enhanced Wire Adapter Protocol eliminates the Transmit Complete message and instead uses polling for Transfer Result to determine when a transfer has completed. IN data transfers may be automatically segmented auto segmentation into smaller transfers by Wire Adapters. This pushes the intelligence functions onto the Wire Adapters and away from the host software i.e. the DWA manages the buffer . During the auto segmentation the size of each segment may vary whereby the Wire Adapter dynamically and adaptively adjusts the segment size in order to maximize throughput for a given situation. The Wire Adapter automatically manages its available buffers by issuing IN tokens for pending transfers based on buffers being available to accept the IN data.

In an embodiment of the present invention a Wire Adapter driver segments a transfer request and submits all of these at once. The DWA automatically manages memory to complete each segment. For IN data the Wire Adapter checks for memory before starting the IN transfers and for OUT data negative acknowledgements are used to backpressure a segment for which the Wire Adapter does not have enough memory. In an embodiment of the present invention multiple transfers to or from HWAs over the upstream USB interface may be aggregated into a single USB transfer in order to reduce transfer latency.

For OUT transfer data packets the enhanced Wire Adapter Protocol uses packets that cut through rather than being passed using store and forward transfer. Using this new approach whenever some minimum amount of OUT data is received from the upstream port the Wire Adapter may transfer the data on the downstream port rather than wait until a complete segment of data is received. Conversely the Wire Adapter automatically manages its available data buffers by putting backpressure on the upstream port by issuing negative acknowledgments NAKs when data buffers are not available to hold incoming data.

The enhanced Wire Adapter Protocol allows forwarding of Transfer Requests by a Wire Adapter thereby reducing the number of messages used to complete data transfer. Referring back to the example in under the enhanced protocol the DWA Transfer Request looks like a Transfer Request to the HWA and not data. Thus the HWA realizes that the incoming Transfer Request is really for the DWA and forwards it to the DWA. Forwarding Pipe FPipe descriptors are used in conjunction with Remote Pipe RPipe descriptors to control forwarding of Transfer Request packets.

Under the enhanced protocol a Wire Adapter automatically polls a downstream Wire Adapter for Transfer Result packets based on a previous Transfer Request to that downstream Wire Adapter. Similarly the Wire Adapter forwards any received Transfer Result to the upstream interface rather than generating and forwarding a Transmit Complete and new Transfer Result.

Rather than the poll for downstream data initiated by receiving a Transfer Request from the host driver the Wire Adapter automatically polls a downstream device for IN data based on previously receiving a Transfer Result for an IN data transfer. Similarly rather than generating and forwarding a Transmit Complete and new Transfer Result the Wire Adapter simply forwards IN Transfer Data to the upstream interface after reception.

For Transfer Request forwarding the Wire Adapter host driver maintains an association between Transfer IDs in a Transfer Request accepted from another Wire Adapter host driver and the resulting transfer generated by the Wire Adapter. It then uses this association to modify the Transfer ID in Transfer Request and Transfer Result packets.

In one embodiment of the present invention Multiple Wire Adapter drivers HWA and DWA may be combined into a single Wire Adapter driver in order to reduce the number of Application Programming Interfaces APIs and therefore the latency incurred by passing of messages across the APIs. In addition combining multiple Wire Adapter drivers allows consolidation in the assignment of Transfer IDs such that when Transfer Request forwarding is being used the need to maintain the association between Transfer IDs in Transfer Request presented from an upstream driver and the Transfer IDs in issued Transfer Request is eliminated.

The Proxy WUSB Hub is similar to a DWA in that it has a wireless upstream port and one or more wired USB downstream ports wherein wired USB devices may be plugged into the downstream wired USB ports. The WUSB Hub differs from a DWA in that the wired USB devices appear to the host system as if they are native WUSB devices. This is accomplished by having the WUSB Hub proxy the attached downstream wired devices on the wireless interface. Therefore the WUSB hub appears to the host as one or more WUSB devices not a DWA which eliminates much of the control packet overhead used by the standard Wire Adapter Protocol.

An attached wired USB device either 1 is presented as a unique WUSB device with its own device address or 2 is presented as a separate function on an already existing device the WUSB hub for instance which may enumerate as a DWA . With this latter approach the wired device endpoints are mapped into WUSB hub endpoints.

The WUSB Hub uses various mechanisms in order to properly proxy a USB device to the host as if it is a WUSB device. The following description applies to the case when the WUSB hub presents downstream USB devices as WUSB devices rather than as functions on the DWA.

Each WUSB device maintains a security connection context. The connection context is negotiated during first time connection. The WUSB Hub negotiates the security connection context for the USB devices without the knowledge or involvement of the downstream devices and stores the security connection context. A sufficient number of unique security connection contexts are negotiated and maintained in order to support the maximum number of downstream USB devices that the WUSB hub is capable of simultaneously proxying. A specific connection context is not tied to a particular downstream USB device rather the connection contexts are applied as needed when USB devices are attached.

The WUSB hub maintains a unique WUSB device address for each attached proxy USB device and it participates in the WUSB protocol as if it were the WUSB devices it is proxying rather than appearing as an intervening device like a DWA .

The WUSB Hub detects USB attachment either directly or by intercepting interrupt packets from attached downstream hubs. Upon detecting attachment of downstream devices the WUSB hub does not forward interrupt packets to the host or directly inform the host of USB attachment. Instead the WUSB hub performs a WUSB device connection procedure on behalf of the USB device.

The WUSB hub reads the descriptors of the USB devices and modifies them so that they are consistent with descriptors for WUSB devices. For example the maximum packet size field in the Standard Endpoint Descriptor is modified so that it is consistent with WUSB packet sizes. The bmAttributes field in the Standard Configuration Descriptor is set to indicate that the device is self powered.

For some USB devices which do not use zero packet length semantics to indicate the end of transfers the lengths of IN transfers are used so that the correct number of bytes are read. However in the case of a WUSB hub the length of IN transfers is not available with the WUSB protocol. Without transfer requests there is no previously declared limit on the amount of data to read. Fortunately the upstream wireless device is provided with the expected length of transfers.

The WUSB protocol is modified slightly in order to support the WUSB hub. Two options are available. In the first option the maximum packet size field in IN Channel Time Allocation CTE Information Elements IEs sent in WUSB host Micro scheduled Management Control MMC can be used to indicate the expected transfer length. Alternatively a field may be added to CTAs to indicate the expected transfer length.

In an embodiment of the present invention the WUSB hub includes a controller to perform the functions and operations of the WUSB hub discussed above.

For the case in which a WUSB hub proxies one or more downstream USB devices as functions on the WUSB hub DWA the above description generally applies except that the security connection context and WUSB device address is shared with the WUSB hub. In addition when a USB device attaches the WUSB hub maps WUSB hub wireless endpoints one for one for USB device endpoints and treats the collection of endpoints associated with a particular USB device as a function on the WUSB hub. The WUSB hub informs the host that a new function needs to be enumerated in order to activate support for a newly attached device.

Although embodiments of the present disclosure have been described in detail those skilled in the art should understand that they may make various changes substitutions and alterations herein without departing from the spirit and scope of the present disclosure.

