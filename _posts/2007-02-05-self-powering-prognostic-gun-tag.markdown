---

title: Self powering prognostic gun tag
abstract: An apparatus for counting and storing a number of rounds fired from a gun includes a microcomputer; a non-volatile memory connected to the microcomputer; and at least one piezoelectric transducer connected to the microcomputer and mounted on the gun, the at least one piezoelectric transducer comprising a power source that generates power during operation of the gun. The piezoelectric transducer may also sense the firing of the gun.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=07716863&OS=07716863&RS=07716863
owner: The United States of America as represented by the Secretary of the Army
number: 07716863
owner_city: Washington
owner_country: US
publication_date: 20070205
---
This application claims the benefit under 35 USC 119 e of U.S. provisional patent application No. 60 766 729 filed on Feb. 8 2006 which application is hereby incorporated by reference.

The inventions described herein may be manufactured used and licensed by or for the U.S. Government for U.S. Government purposes.

The invention relates in general to munitions and in particular to large caliber gun tubes and breech mechanisms. Large caliber gun tubes and breech mechanisms are components of for example cannons mortars recoilless rifles and howitzers.

Large caliber gun tubes and breech mechanisms are expensive. It is desired to use a gun tube and or breech mechanism as long as possible. However these systems may become ineffective and potentially dangerous when operated beyond their useful service life. A significant component of the service life is the historical firing information. In the absence of this information the system will require additional costly inspections or be prematurely removed from service.

One way to track the activity of a gun tube is with a Weapon Data Record Card. The Weapon Data Record Card includes the number and type of each round fired from a particular gun tube. A soldier manually records the data on the Weapon Data Record Card. The card is stored with the gun tube. A record of the number of tubes used with each breech mechanism is also recorded manually and stored with the breech.

Unfortunately the Weapon Data Record Cards are often lost and the component has to be either inspected in the field or condemned prematurely. The costs associated with this procedure are high and critical information of the firing history is permanently gone. The administrative responsibilities associated with maintaining accurate information of the Weapon Data Record cards is often an unreasonable requirement for the soldier in the field. Devices similar to those tested on small caliber munitions were determined to be ineffective or untested for large caliber gun tubes and breech mechanisms. In addition these devices require an external battery to operate. Periodic battery replacement is an unacceptable additional maintenance requirement. There is a need for a device for monitoring the firing history of gun components that requires no periodic maintenance.

It is an object of the invention to provide an apparatus to reliably record the firing history of gun components while reducing the administrative responsibilities of the soldier.

It is another object of the invention to provide an apparatus to reliably record the firing history of gun components wherein the apparatus operates with no external power source.

It is a further object of the invention to provide an apparatus to reliably record the firing history of gun components to thereby avoid premature condemnation of gun tubes and or breech mechanism resulting from lost or inaccurate record keeping.

One aspect of the invention is an apparatus for counting and storing a number of rounds fired from a gun comprising a microcomputer a non volatile memory connected to the microcomputer and at least one piezoelectric transducer connected to the microcomputer and mounted on the gun the at least one piezoelectric transducer comprising a power source that generates power during operation of the gun.

In one embodiment the at least one piezoelectric transducer further comprises a firing sensor that senses a firing of the gun. Or the at least one piezoelectric transducer may comprise two piezoelectric transducers wherein a first piezoelectric transducer comprises the power source that generates power during the operation of the gun and a second piezoelectric transducer comprises the firing sensor that senses the firing of the gun.

In another embodiment the apparatus further comprises an accelerometer connected to the microcomputer and mounted on the gun. The accelerometer may comprise a firing sensor that senses a firing of the gun and or a type of round sensor.

Preferably the apparatus further comprises a radio frequency circuit and a remote computer for accessing the non volatile memory via the radio frequency circuit.

The non volatile memory stores one or more of a number of rounds fired a number of each type of round fired gun recoil acceleration profiles for every round fired and radial strain magnitudes for every round fired.

The invention will be better understood and further objects features and advantages thereof will become more apparent from the following description of the preferred embodiments taken in conjunction with the accompanying drawings.

The invention includes an apparatus that mounts to a gun tube or breech and maintains a permanent firing history. The apparatus includes one or more transducers that directly monitor key characteristics of gun response to fired rounds. The invention eliminates the administrative responsibilities associated with maintaining Weapon Data Record Cards. No external power source i.e. battery is required. When the gun fires the firing history is updated and stored permanently in a non volatile memory such as an Electrically Erasable Programmable Read Only Memory here throughout also referred to as an EEPROM.

In one embodiment power for the apparatus is derived from the response of piezoelectric material to gun recoil or the radial strain of the gun tube associated with the pressure pulse. In some embodiments a nanowatt microcomputer determines the round type based on the acceleration profile of the gun recoil or the magnitude of the radial strain. The stored firing information may be extracted remotely from the non volatile memory via radio frequency using power derived from the interrogating device. The stored firing information may include 1 the total number of rounds fired and 2 the number of each specific type of round fired or sensor data for remotely determining the number of each specific type of round fired. The apparatus is permanently mounted to the gun tube or gun breech so that the firing information becomes an integral and permanent part of the component.

At least one piezoelectric transducer is connected to the microcomputer and mounted on the gun barrel or breech . The piezoelectric transducer functions as a power source during operation of the gun . One type of power generating piezoelectric transducer comprises a mass that accelerates due to recoil of the gun . The force of the mass against the piezo crystal generates power. This type of transducer may be used on either the barrel or the breech of gun because both the barrel and breech recoil during operation of the gun . Another type of piezoelectric transducer is sensitive to the radial strain of the barrel during a firing event and generates power as a result of the radial strain of the barrel. The radial strain type of transducer may not be suitable for the breech because the amount of radial strain at the breech may be too small.

The at least one piezoelectric transducer further functions as a firing sensor that senses a firing of the gun . In the case of the accelerating mass type of transducer the acceleration of the mass not only generates power but also indicates a firing event due to recoil of the gun . In the case of the radial strain transducer the radial strain generates power and also indicates the firing of the gun due to radial strain of the barrel. Of course rather than a single transducer that both generates power and senses a firing event two separate transducers may be used one for generating power and one for sensing the firing event. Both transducers are connected to the microcomputer .

Apparatus may further comprise an accelerometer connected to the microcomputer and mounted on the gun barrel or breech . The accelerometer senses a firing event due to recoil of the gun . When using the accelerometer the piezoelectric transducer may function only as a power generating source and need not independently sense the firing event.

In another embodiment of the invention the accelerometer further comprises a type of round sensor that senses the acceleration profile of the gun recoil. In this embodiment a database of gun recoil acceleration profiles is created for each of the known types of rounds that may be fired from the gun . This database may be created empirically by firing known types of rounds from the gun sensing the acceleration profile of the gun recoil for each type of round and storing the acceleration profiles in the non volatile memory of the apparatus or in a remote computer . Alternatively the database may be created mathematically.

Then whenever a round is fired from the gun the accelerometer senses the acceleration profile of the gun recoil and sends this information to the microcomputer . In one embodiment the microcomputer compares the sensed acceleration profile to the known acceleration profiles stored in memory and determines the type of round that was fired. In another embodiment the sensed acceleration profiles are stored in memory and then remotely accessed via radio frequency link by remote computer . Remote computer then compares the sensed acceleration profiles retrieved from memory to the known acceleration profiles stored in its own memory and determines the type of round that was fired.

In another embodiment of the apparatus the at least one piezoelectric transducer may comprise the type of round sensor. In this case the piezoelectric transducer comprises a mass that accelerates due to recoil of the gun . The voltage produced by the transducer is proportional to the gun acceleration and is used to create a sensed acceleration profile that is used as described above with respect to accelerometer .

In still another embodiment of the invention the piezoelectric transducer may measure the magnitude of the radial strain of the gun tube. In this embodiment a database of radial strain magnitudes is created for each of the known types of rounds fired from the gun . This database may be created empirically or mathematically in a manner analogous to the database of acceleration profiles for different types of rounds. The database is stored either in memory or in remote computer .

Then whenever a round is fired from the gun the transducer senses the magnitude of the radial strain of the gun tube and sends this information to the microcomputer . In one embodiment the microcomputer compares the sensed radial strain to the known radial strain magnitudes stored in memory and determines the type of round that was fired. In another embodiment the sensed radial strains are stored in memory and then remotely accessed via radio frequency link by remote computer . Remote computer then compares the sensed radial strains retrieved from memory to the known radial strain magnitudes stored in its own memory and determines the type of round that was fired.

So that the non volatile memory may be accessed remotely a radio frequency circuit is included. At a minimum the information retrieved from memory is the number of rounds fired. In the embodiments where the microcomputer determines the type of round fired the information retrieved also includes the number of each type of round fired. In the embodiments where the remote computer determines the type of round fired the information retrieved is the gun recoil acceleration profile or radial strain magnitude for each round fired. The apparatus does not require power when a radio frequency interrogator accesses the memory .

While the invention has been described with reference to certain preferred embodiments numerous changes alterations and modifications to the described embodiments are possible without departing from the spirit and scope of the invention as defined in the appended claims and equivalents thereof.

