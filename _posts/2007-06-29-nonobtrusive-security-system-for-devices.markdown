---

title: Non-obtrusive security system for devices
abstract: A security system is provided including providing a device including: storing a security rule for operation of the device when an event occurs; and implementing the security rule upon the occurrence of the event to allow non-obtrusive user access to the device.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=07971229&OS=07971229&RS=07971229
owner: McAfee, Inc.
number: 07971229
owner_city: Santa Clara
owner_country: US
publication_date: 20070629
---
The present invention relates generally to electronic devices and more particularly to a security system for devices.

Security is a critical issue with almost all aspects of computer use and mobile electronic device use including such devices as computers mobile phones handheld computers etc.

All modern operating systems provide a mechanism for security that involves some form of authentication or authorization hereinafter generically referred to as authentication to determine if a rightful user is accessing the system. For example such a mechanism is the prompt for a user name and password by an operating system in a personal computer when it is powered up. Another example of such a mechanism is the prompt for authentication information when a user accesses a protected resource such as a secure file in a database. Implementing such security measures often requires modification of the user s behavior which at the very least involves the user having to enter authentication information one or more times while accessing the protected resource.

Requiring users to modify their behavior in order to obtain data security is a particularly arduous task especially in the context of mobile devices. Most users are not used to securing their mobile devices with power on user name and password authentication information etc. However this is important to prevent unauthorized users from being able to incur large phone charges against the rightful user s cell phone account or accessing information that maybe deemed to be of a sensitive nature.

In the past there have been several methods to reduce the complexity of the task of authorization such as the use of picture passwords key based locking systems transponder based authentication etc.

However all such methods while reducing the complexity of entering authorization information still required such information to be provided and hence required a change in the usage behavior of a user who was used to using the cell phone without having to use security precautions before.

Also in the past software security systems were used with subscriber identity modules SIMs or cards that enabled remote device management using protocols such as Open Mobile Alliance s SyncML Device Management protocol etc. Such management software may be used to provide mobile devices with appropriate security features. Using such software a security policy could be defined which did not prompt for any authentication or authorization unless a device had been marked as a security threat in an event such as the device being lost or stolen the SIM being changed etc. 

However if the device connectivity environment changed in events such as changing the SIM roaming to a different mobile network etc the device would not be able to communicate with the management software backend server and hence it would not be possible to remotely lock or wipe data off of the device.

Also if the device is reset to default factory settings by formatting it all connectivity is lost with the management software backend and thus the device can thereafter be easily used without security protection. Thus the best way currently known to ensure that the device is secure is to use some form of authentication or authorization while the device is running to ensure that the device is in the hands of the right user. Such a method however requires changes in the usage pattern for users not accustomed to taking security precautions.

Solutions to these problems have been long sought but prior developments have not taught or suggested any solutions and thus solutions to these problems have long eluded those skilled in the art.

The present invention provides a security system comprising providing a device including storing a security rule for operation of the device when an event occurs and implementing the security rule upon the occurrence of the event to allow non obtrusive user access to the device.

Certain embodiments of the invention have other aspects in addition to or in place of those mentioned above. The aspects will become apparent to those skilled in the art from a reading of the following detailed description when taken with reference to the accompanying drawings.

The following embodiments are described in sufficient detail to enable those skilled in the art to make and use the invention. It is to be understood that other embodiments would be evident based on the present disclosure and that system process or mechanical changes may be made without departing from the scope of the present invention.

In the following description numerous specific details are given to provide a thorough understanding of the invention. However it will be apparent that the invention may be practiced without these specific details. In order to avoid obscuring the present invention some well known circuits system configurations and process steps are not disclosed in detail.

Likewise the drawings showing embodiments of the system are semi diagrammatic and not to scale and particularly some of the dimensions are for the clarity of presentation and are shown greatly exaggerated in the drawing FIGs.

The term obtrusive means that an input from a user is required during regular usage or that a change is required in the user s behavior e.g. by the input of a password connection of a dongle or key contacting a trusted authority etc.

The term non obtrusive means that no input from a user is required during regular usage or that no change is required in the user s behavior.

In various embodiments of the present invention a multi tier security model is described that uses security mechanisms such as prompting for authentication or authorization information on device startup while augmenting the security mechanism with an intelligent security agent that satisfies the security method non obtrusively based on remotely set policies.

Additional embodiments of the present invention provide a security policy that may be used in conjunction with the multi tier security mechanism and an agent based approach to ensure that security is not compromised even when the device is formatted or in periods of communication blackout with the management software backend.

Various other embodiments of the present invention provide for a software product that can be directly loaded and deployed in an operating system based device. The software product enables remotely setting security policies and describes a version of a conventional agent which is an intelligent state based agent that performs the intelligent security agent functions.

Further embodiments of the present invention ensure that in the event of the un installation of a security agent through formatting a device or otherwise the device security is maintained. In the event of un installation the user of the device will be prompted for authentication information which would not ordinarily be required when the intelligent security agent is present.

Further embodiments of the present invention ensure that there exists a mechanism of security through a policy as enforced by the intelligent security agent that is non obtrusive.

Referring now to therein is shown a security system in accordance with a first embodiment of the present invention. The security system includes a device which contains a processor system such as a microcontroller or microcontroller implementing an intelligent security agent in hardware or in software stored on any such media that the device maybe equipped with including but not limited to flash memory ROM and other such forms of programmable or permanent memory and a policy store stored in a memory . The intelligent security agent is considered intelligent because it responds differently to different events based on instructions in the policy store .

The device can be an operating system based device such as a cell phone personal digital assistant palm computer etc. and the device runs the terminal operating system TOS 

The intelligent security agent communicates using an operating system application programming interface API through a wireless network such as a cell network Internet etc. with a server system to retrieve a set of determined rules from storage and caches them locally in the policy store .

When the device starts up the intelligent security agent communicates with the terminal operating system and in accordance with the rules defined in the policy store pre authenticates the device for example by entering a stored user name and password in the processor system or terminal operating system non obtrusively for the user.

Since the device user name and password are persistent even when the device is formatted formatting the device which also removes the intelligent security agent will still ensure device security because the device will require the user name and password after the formatting is completed without the pre authentication being performed by the intelligent security agent .

This will ensure that while the device has the intelligent security agent installed no change in user behavior is required unless the policy in the policy store dictates such change. If the intelligent security agent is not installed the device is still secure since the terminal operating system on the device will ask the user to authenticate when the device starts up.

Referring now to therein is shown a schematic of the intelligent security agent in accordance with an embodiment of the present invention.

The intelligent security agent includes one or more event watchers through n. The event watchers through n watch for various events to occur such as but not limited to device startup SIM change etc. The event watchers through n are connected to an event queue which in turn is connected to an event manager .

The event manager receives information from the policy store and provides instructions for an operation into an operations queue .

An operations manager then executes the operation from the operations queue in various operations designated as operations through n.

The intelligent security agent is a software construct in which each of the elements may be coupled together or decoupled implemented as one software component or multiple components where the various functions are performed.

In operation the event watchers through n watch for an event to occur. When the event occurs an event watcher for example the event watcher adds an appropriate record in the event queue . The event manager takes each event from the event queue and then queries the policy store to determine if the event has any corresponding operation or operations to be performed on the device of .

If an operation or operations are to be performed the event manager adds an appropriate record to the operations queue . The operations manager then executes the desired operation as an operation .

Referring now to therein is shown a table of an exemplary security policy in an exemplary policy store of .

The table of has column headings of Event Required conditions Operations and Post conditions and is described in conjunction with .

The Event column lists the events watched for by the event watchers through n. When an event occurs the event watcher through n adds a note from the appropriate list under Required Conditions and provides the information to the event queue . The Required Conditions are the conditions that are required for an operation to be performed. If the Required Conditions are met the event manager then adds the operation to be performed from the Operations column to the operations queue . When the operations in the operations queue are performed the results are as indicated in the column Post conditions .

Thus as examples on device startup there are no preconditions and the operation to be performed is the pre authentication using the terminal operating system through the application programming interface to result in the user being authenticated. Where an event is the network being disconnected there are no required conditions and the operation desired is to lock the device of and to set a network connectivity flag to result in the device being locked and the network connectivity flag being set. Where the event is the network being connected the required condition is that the device is locked and the network coverage flag is set and the operation to be performed is the unlocking of the device and the unsetting of the network connectivity flag to result in the post condition of the device being unlocked and the network connectivity flag not being set.

The above provides that the device is usable only while it is connected to a network through the application programming interface .

Also with the above the user does not need to enter any authentication while the intelligent security agent is installed on the device and hence non obtrusive security is provided.

However the user will be prompted for authentication if the intelligent security agent is removed from the system in which case the security becomes obtrusive.

For example when the event watcher for example signals a device startup event the operation which could be the pre authentication operation is performed by the operations manager and thus the user does not need to enter any authentication information on device startup. This is true as long as the intelligent security agent is present and the policy described in is in force.

When an event watcher for example signals a Network Disconnected event the operation which could be a lock operation is performed and the network connectivity flag is set by the operations manager . Thus the device is rendered unusable in periods of connectivity blackouts.

In a Network Connected event with the device currently locked and the network connectivity flag set the operation which could be an unlock operation is performed and the network connectivity flag is unset by the operations manager . Thus the device is rendered usable again when connectivity is restored.

Referring now to therein is shown a portion of a security system in which a software product is being loaded into the device in accordance with a second embodiment of the present invention. The software product may be in the form of a diskette RAM disk magnetic tape CD ROM Flash drive or any other suitable software carrier. The device is an exemplary palm computer.

Referring now to therein is shown a flow chart of a security system in accordance with a third embodiment of the present invention.

Security is insured because the software must always be installed on the cell phone and with it not being installed the phone and the SIM are rendered useless without the permission of the trusted authority.

It is also possible to tie a SIM to a specific cell phone rendering it useless in any other cell phone. For example the security software that implements this system is installed on the cell phone. If a thief removes the SIM and tries to use it in another cell phone the SIM has the PIN enabled and thus the thief will be prompted for a PIN in the other cell phone.

On the particular cell phone itself use of the SIM could be prevented by set policies that the intelligent security agent may choose to implement e.g. the SIM is allowed to call only certain numbers etc.

Referring now to therein is shown a flow chart of a security system in accordance with a fourth embodiment of the present invention. The security system includes providing a device including storing a security rule for operation of the device when an event occurs in a block and implementing the security rule upon the occurrence of the event to allow non obtrusive user access to the device in a block .

While the invention has been described in conjunction with a specific best mode it is to be understood that many alternatives modifications and variations will be apparent to those skilled in the art in light of the aforegoing description. Accordingly it is intended to embrace all such alternatives modifications and variations that fall within the scope of the included claims. All matters hithertofore set forth herein or shown in the accompanying drawings are to be interpreted in an illustrative and non limiting sense.

