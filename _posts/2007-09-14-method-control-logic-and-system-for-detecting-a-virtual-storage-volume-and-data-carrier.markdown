---

title: Method, control logic and system for detecting a virtual storage volume and data carrier
abstract: A method, corresponding control logic, and a correspond system for detecting a virtual storage volume. The method includes: determining a first access pattern for a read operation of a target storage volume; monitoring a second access pattern of at least one other storage volume of a computer system during the read operation; determining a correlation between the first access pattern and the second access pattern; and deriving that the target storage volume is a virtual storage volume if the determined correlation is above a predefined threshold.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08429345&OS=08429345&RS=08429345
owner: SONY DADC Austria AG
number: 08429345
owner_city: Anif
owner_country: AT
publication_date: 20070914
---
The invention relates to a method a control logic and a system for detecting a virtual storage volume and a data carrier.

Certain copy protection schemes for optical discs e.g. CDROM DVD or blue ray disc check if a special feature a so called signature which can not be duplicated onto optical recordable media is present on the optical disc. Such a signature and a corresponding method for verifying the signature are disclosed for example in WO 03 054878 A1 or in EP1672631A1. A computer program is only allowed to execute if the signature is present. Copy protection software is looking for such a signature on a target storage medium which should be e.g. an original optical disc and which is expected to be placed in a target storage drive e.g. an optical disc drive. An operating system of a computer system presents a storage drive together with a storage medium as a storage volume. Other examples for such storage volumes might be provided by a USB Stick semiconductor memory with a USB interface a floppy drive with a floppy disk a memory card in a card reader or partitions on hard disks. The wording target storage medium target storage drive and target storage volume is used throughout this description for the corresponding storage medium storage drive and storage volume on which the certain data is expected to be found by the copy protection software. Typically the copy protection software is checking whether the signature is present on the target storage volume.

Emulation software intercepts the communication between the copy protection software and the optical disc drive and manipulates the data and or access timing information to insert false signature information. Emulation software can achieve this by presenting a virtual storage medium such as a disc image mounted on a virtual drive as a virtual storage volume to the copy protection software while the disc image is actually stored on a hard disk drive HDD .

Such virtual storage volumes with disc images of floppy disks optical discs etc. are useful in certain circumstances i.e. 

However in cases where the content of a copy protected optical disc is stored as a disc image on the hard disk and presented to a copy protection software also called control logic copy protection schemes may be circumvented by malicious virtual drive software which not only provides access to the content but also to the signature. The copy protection software is not aware of the fact that the target storage volume on which the signature is found is not the original optical disc in an optical disc drive but is a disc image on the hard disk drive. The original disc might be redistributed to other user s and the copy on the hard disk drive might be in fact an unauthorized copy.

Known methods to identify a virtual storage volume depend either on system level software device drivers or have become ineffective. Such previous methods may include separately or in combination 

A further possibility to protect data content within protected areas on a target optical carrier against unauthorized reading and or copying with a computer is disclosed in WO 2004 088658 A1. The disclosed method comprises steps of determining whether a target optical record carrier or a non target optical record carrier is inserted into a drive of the computer and if a target optical record carrier is inserted into the drive of the computer modifying read requests to the protected data areas so that no data is read or the read data is useless and or modifying write commands in respect to the data within the protected data areas to a recordable carrier or other storage so that the written data is useless.

It is an object of the present invention to provide a method for detecting a virtual storage volume which is difficult to circumvent and which provides an effective way to discover whether a virtual storage volume is used in order to fake or otherwise give the impression that the presence of an original storage medium in a corresponding drive 

It is a further object of the present invention to provide a control logic for detecting a virtual storage volume which enables an easy and efficient detection of such virtual storage volume when used on a computer system to provide measures against unauthorized copying of protected software applications or data.

It is a further object of the present invention to provide a system for detecting a virtual storage volume which enables an easy and efficient detection of such virtual storage volume which are present on such a system.

The object is achieved in a first aspect by a method for detecting a virtual storage volume comprising the steps of

Throughout the description the wording read operation is used to describe a sequence of read accesses to different storage locations on a storage volume.

In other words the method is able to distinguish whether a data transfer is obtained from the virtual storage volume or from an original storage volume built of a drive and an original storage medium by querying and correlating the data transfer statistics from the operating system. So by checking the data transfers of a target storage volume which should read the data from the original storage volume e.g. provided by an optical disc a floppy disk a USB stick a memory card and comparing the signal pattern during such data transfer with a signal pattern of data transfers of another storage volume e.g. a hard disk drive similarities are obtainable. In case the target storage volume is not represented by a virtual drive with a disc image stored on the other storage volume e.g. the hard disk drive the signal pattern of the data transfers from the other storage volume e.g. the hard disk drive and from the target storage volume should differ significantly since the access is not related. However in case that the target storage volume is in fact a virtual disc drive with a disc image stored on another storage volume e.g. the hard disk drive the signal pattern should look similar since the access in question actually takes place on the hard disk drive. In case such a virtual storage volume is detected appropriate measures could be taken e.g. to refuse to run the application to remove the disc image from the other storage volume or to instruct the user to insert the original storage medium in the corresponding drive.

With a second aspect a control logic for detecting a virtual storage volume the control logic being adapted to run on a computer system said computer system comprising

With a fourth aspect a tangible data carrier is provided having stored thereon software code components which when loaded onto a computer system execute the above mentioned method.

The terms first access pattern and second access pattern are used to distinguish both access pattern and do not imply any timerelationship between these access patterns.

In a schematic block diagram of the system for detecting a virtual storage volume is depicted. Such a virtual storage volume e.g. a virtual drive with a virtual storage medium is created by an emulation software. The virtual drive software is accessing a disc image which data is actually stored on a hard disk drive or another storage volume of a computer system e.g. a network drive. The virtual drive software or emulation software like Daemon Tool or Alcohol 120 presents the virtual drive to a control logic e.g. a copy protection software. So the virtual drive software intercepts the communication between the control logic and the virtual storage volume thereby giving the impression faking that the data is actually present on a separate original optical disc inserted into an optical disc drive and not on the hard disk drive as a disc image . Other storage media that might be copied on a hard disk drive and be accessed as a virtual storage volume using the same scheme are USB memory sticks dongles or magnetic tapes memory cards or the like.

A copy protection software is typically checking whether a characteristic which is difficult or impossible to copy e.g. a so called signature is actually present on a target storage medium e.g. an original optical disc. Therefore the copy protection software accesses a target storage volume e.g. an optical disc drive with the original optical disc in order to check whether on the target storage medium such a signature is actually present. The virtual drive software presents the virtual storage medium as such target storage medium so that the signature is read from the disc image which is actually present on the hard disk drive because it has been copied possibly without authorization onto the hard disk drive . The control logic is not able to detect that the signature is in fact stored on the hard disk drive and not read from the original optical disc.

In order to distinguish whether data transfer is obtained from a virtual storage volume or a physical storage volume access patterns are derived from the target storage volume and from other storage volumes of the computer system . Such access patterns are derivable by using performance application programming interfaces API of operating systems e.g. Microsoft Windows .

Such performance APIs show for example how many bytes are transferred in a given amount of time and the number of read operations explained more in detail with respect to and .

Another possibility is the use of a device driver which is able to collect such required measurement data e.g. how many bytes are transferred in a given amount of time and the number of read operations.

Read access statistics or a first access pattern are obtained from the target storage volume which is supposed to access the original disc and a second or further access pattern is obtained from one or more hard disk drives . The read access statistics or access patterns are collected either continuously or during predefined time intervals. In one embodiment the access patterns are monitored while performing a verification of signature of the disc.

In a further embodiment the first access pattern is determined before actually reading the target storage volume. If the result of the read operation is known because for example the signature of the disc is known beforehand then the resulting first access pattern can be simulated beforehand and can be compared with the monitored second access pattern of another storage volume.

If the characteristic read access pattern resulting from the signature verification access can be statistically detected not only in the access statistics or access pattern of the target storage volume but also in the access statistics of one of the hard disk drives of the computer system the control logic can conclude that emulation by means of a virtual storage volume is present and can start appropriate measures e.g. to refuse to run the protected application to remove the virtual storage volume or to instruct the user to insert the original storage medium in a corresponding drive.

In measurement data for a first access pattern and in for a second access pattern are depicted. The first access pattern is obtained by monitoring the access to a target storage volume 2048 bytes are transferred every 50 ms from increasing sector numbers 65536 bytes apart. The performance data bytes transferred of the hard disk drive are sampled every 10 ms. In a finer resolution not shown it is observable that the monitored transfer from one of the other storage volumes usually slightly precedes the completion of the read request on the target storage volume.

By determining the correlation between the first access pattern and the second access pattern it is derived that the first access pattern and the second access pattern show a similar time dependent behavior.

For example such correlation might be determined by counting how many accesses have been executed nearly in parallel and by using a predefined threshold of number of parallel accesses in order to derive whether a virtual storage volume is present. Another possibility would be to calculate according to a known algorithm a correlation value between the first access pattern and the second access pattern and to use a predefined threshold value between 0 and 1 e.g. 0.5 to determine whether a virtual storage volume is present when the correlation value is above the threshold value.

With this high correlation value or similar access pattern it is concluded that the target storage volume is in fact a virtual storage volume with a disc image on the hard disk drive and not a separate optical disk drive with an original optical disc.

The read ahead logic of the virtual drive software used in this example seems to be 64 sectors i.e. 131072 bytes explaining the large transfers on the hard disk drive compared to the small transfers on the virtual storage volume .

In the method steps are depicted. In a first step S the first access pattern of the target storage volume is determined. In parallel during a second step S the second access pattern of at least one of the other storage volumes is monitored. In a third step S the correlation of the first access pattern and the second access pattern is determined. Afterwards in a fourth step S it is evaluated whether the determined correlation is above a predefined threshold which results in discovering a virtual storage volume in a fifth step S in case the correlation is above the predefined threshold and otherwise in a sixth step S in the result that no virtual storage volume is present. In the latter case it is allowed to execute the application program afterwards since it is assumed to be on an original disc and therefore the execution is authorized.

It is possible to use additional copy protection schemes like checking whether the signature is present on the original storage medium.

A very efficient way to implement the method is the use of statistics provided by an operating system of the computer system dealing with access statistics of storage volumes since these statistics are already present and can easily be used e.g. by the control logic .

Operating systems provide so called performance application programming interfaces performance API which can be sampled to determine the first access pattern and the second access pattern .

Since the check of the signature is part of many copy protection schemes and properties like a time interval during which such signature is read by the control logic and the length of the signature are known beforehand by the control logic this time interval is well suited for monitoring the first access pattern and the second access pattern . In this case it is even possible to only monitor the second access pattern and determine the first access pattern by simulating the read operation of the signature beforehand.

Monitoring of the access pattern can take place during predefined time intervals for using less control logic efforts during other time intervals or can take place continuously in order to further enhance the probability of detecting the virtual storage volume .

Since the computer system may have a plurality of storage volumes each of which might have stored the virtual image the method is applicable as well for these cases thereby monitoring access patterns of every storage volume and determining correlations between the first access pattern and further access patterns of all of the storage volumes in order to find out on which storage volume a virtual image has been stored.

The method may be improved by filtering the first access pattern and the second access pattern before determining the correlation thereby decreasing noise effects e.g. from other processes that are running on the computer system . Such filtering might include but is not restricted to 

The method is applicable for optical discs as target storage medium optical disc drives as target storage drive and a hard disk drive as other storage volume.

Although the method control logic and system have been described with respect to read operations it is apparent that a corresponding method control logic and system is applicable as well during write operations in order to identify on which volume a writing process takes place actually.

