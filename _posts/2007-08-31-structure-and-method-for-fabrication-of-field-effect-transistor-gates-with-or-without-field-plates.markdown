---

title: Structure and method for fabrication of field effect transistor gates with or without field plates
abstract: A method for fabrication of a field effect transistor gate, with or without field plates, includes the steps of defining a relatively thin Schottky metal layer by a lithography/metal liftoff or metal deposition/etch process on a semiconductor surface. This is followed by depositing a dielectric passivation layer over the entire wafer and defining a second lithographic pattern coincident with or slightly inset from the boundaries of the previously defined metal gate layer. This is followed by etching the dielectric using dry or wet etching techniques and stripping the resist, followed by exposing and developing a third resist pattern to define the thicker gate metal layers required for electrical conductivity and also for the field plate if one is utilized. The final step is depositing gate and/or field plate metal, resulting in a gate electrode and an integral field plate.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08003504&OS=08003504&RS=08003504
owner: Biogen IDEC MA Inc.
number: 08003504
owner_city: Cambridge
owner_country: US
publication_date: 20070831
---
This Application claims rights under 35 USC 119 e from U.S. application Ser. No. 60 841 742 filed Sep. 1 2006 the contents of which are incorporated herein by reference.

This invention was made with United States Government support under Contract No. W911QX 05 C 0087 awarded by the United States Army Research Laboratory. The United States Government has certain rights in this invention.

This invention relates to transistors and more particularly to structures and methods for fabrication of field effect transistor gates with or without field plates.

In high power field effect transistors in order to increase the power output in the past field plates have been provided. These field plates help reduce the peak electric field and also help control some of the surface charge so that the device is able to operate at higher voltages and thus operate at higher power outputs. It is noted that these FET based amplifiers are designed to operate in the MegaHertz range up to the tens of GigaHertz.

By way of background silicon based field effect transistors and more recently gallium arsenide based field effect transistors have been used to provide the architecture for high power devices.

While silicon and gallium arsenide devices have been utilized in the past more recently these high power devices take advantage of the properties of gallium nitride material to increase the voltage that can be applied to the device to in excess of 40 volts thus to increase output power. It is of course noted that the power for the transistor amplifier depends on the size of the device. Assuming a power density that is normalized to the device periphery it would be desirable to obtain about 10 watts per millimeter biased on the 40 volt range. This 10 watt per millimeter design goal is about ten times what one can achieve using silicon or gallium arsenide.

In typical applications for field effect transistor amplifiers such devices operate up to about 100 watts output power although several hundred watts in output power are not out of the question for discrete devices.

The reason that the industry has gravitated to gallium nitride as opposed to gallium arsenide is the fact that gallium nitride is a wide band gap semiconductor material with a relatively high saturated electron velocity of 1.5 2 10cm s. A wide band gap material is a material having a property that allows high electric fields to be applied without the material breaking down. As a result one can apply higher voltages to devices with higher voltages leading to higher RF output power for the individual devices.

However due to the lack of reproducible lattice matched substrates and relative immaturity of AlGaN GaN processing technology many bulk and surface defects exist in the device material. Bulk traps due primarily to threading dislocations in the material reduce the sheet carrier concentration and therefore microwave performance of the device. Bulk and surface traps give rise to gate and drain lag that is a source of dispersion in the device which impacts large signal power performance.

Advanced device designs have been pursued in the industry to reduce trapping effects and boost GaN device performance and reliability. Among these designs implementing a field plate on a dielectric layer at the drain side of the gate electrode has resulted in the most significant enhancement. The function of a field plate is to modify the electric field profile and to decrease its peak value at the gate edge hence reducing trapping and increasing breakdown voltage. Power densities exceeding 30 W mm at 4 GHz has been demonstrated with a field plate design.

There are basically two ways of fabricating field plate electrodes one being a dry etch process which creates an integrated gate field plate structure. The other method utilizes field plates that are separately defined and are externally connected to the gate or source electrode on the chip.

S. Karmalkar and U. K. Mishra Enhancement of Breakdown Voltage in AlGaN GaN High Electron Mobility Transistors Using a Field Plate IEEE Trans. Electron Devices vol. 48 pp. 1315 1521 2001 discloses a prior art method in which the field plate is defined as part of the gate electrode.

Y. F. Wu A. Saxler M. Moore R. P. Smith S. Sheppard P. M. Chavarkar T. Wisleder U. K. Mishra and P. Parikh 30 W mm GaN HEMTs by Field Plate Optimization IEEE Electron Device Lett. vol. 25 March 2004 and Y. F. Wu M. Moore T. Wisleder P. M. Chavarkar U. K. Mishra and P. Parikh High gain microwave GaN HEMTs with source terminated field plates IEEE IEDM Technical Digest pp. 1078 1079 December 2004 disclose a method in which the field plate is separately defined but directly connected to the gate or source electrode on chip.

One criterion for the provision of a field plate electrode is that one has to place the field plate electrode very close to the gate of the field effect transistor for it to be effective. In the Karmalkar et al. method one derives an integrated structure such that the field plate and the gate are in essence one electrode. Thus there is no spacing problem.

This technique is generally referred to as a dielectric assisted T gate process. In this process one puts a passivation layer on a substrate before any gate metal is put down. One then utilizes some etching technique usually dry chemistry or plasma etching to open a trench in the passivation layer to contact the semiconductor substrate. After this process of opening up the contact area one deposits metal that fills the trench and also forms the field plate extension that goes to either side of the actual gate connection.

Note that the field plate allows a spreading of the electric field so that the total voltage that can be applied to the device is higher. The field plate extension is also useful in controlling the surface states that are close to the gate which helps with reducing any dispersive effect that comes from the surface states in semiconductors.

However the dry etch technique described above is relatively difficult to control because when one has a plasma etch with active ions that are hitting the surface to perform the removal of the passivation layer one always has to do an over etch to ensure complete removal of passivation dielectric material. During the over etch the semiconductor material at the bottom of the trench is exposed to the plasma and because of the energy that the ions carry the semiconductor substrate is damaged. In particular there is atomic level damage in the semiconductor itself that can penetrate up to hundreds of angstroms. Depending on the plasma energy as much as 200 to 300 angstroms of damage can result which is quite normal in the dielectric assisted T gate process.

Damage to the gate area causes a reduction in the power output of the device because many electronic traps are generated. The traps are material defects in the crystal that can hold electrons. One does not want to retain electrons in the gate area because one wants the electrons to be in the active channel where the current is being carried. If the traps hold some of the electrons the result is that one does not have as many electrons as one would like to carry the current. The result is that the power output of the discrete device is significantly reduced.

There is another problem with respect to the etching technique described above and that is one of reliability. When one has material defects the material itself is less capable of holding the high electric field that is applied to the physical areas of the device. Thus the material utilized in the field effect transistor degrades over time if dry etching is used which means that the reliability of the device is lower than one would expect assuming no plasma damage.

Moreover with the dielectric assisted T gate approach the critical gate dimension formed by dry etching and opening is considerably less well controlled than is desired. It is this gate dimension that is critical to device operation.

The above mentioned over etching results in trench sidewalls whose positions are not sufficiently well defined. When the gate metal is deposited in the trench it spreads out in the over etched areas. This means that the size and shape of the gate contact area with the substrate cannot be well controlled.

In order to eliminate the problems associated with the dielectric assisted T gate approach for forming a field plate at the gate of the device a separate gate field plate approach has been used in which the gate and the field plate are deposited in separate lithography steps and separate metallization steps. This gets away from the dry etch damage as well as the difficulty in dimension control as mentioned above.

Separating the field plate and the gate works to some extent but one cannot put the field plate exactly next to the gate contact of the semiconductor. At the very least the field plate has to be separated by the thickness of the passivation layer. It will be appreciated that the extra separation makes the device performance inferior to the integrated approach above.

In short the field plate is separated by as much as the thickness of the passivation layer. The passivation layer is typically on the order of 1 000 angstroms for normal devices. Thus there is quite a substantial distance from the edge of the gate electrode to the field plate. If the gate dimension is on the order of 0.25 microns and assuming a 1 000 angstrom passivation layer this is equivalent to a spacing of 0.1 micron out of the 0.25 micron dimension which is substantial. There is thus quite a substantial distance from the edge of the gate electrode to the field plate.

Also when utilizing a separate gate and field plate one has to connect them externally together. When one has an electrical contact that is external to the active area of the device the field plate and the gate plate connect to the same bar of metal outside so they are under the same electrical bias. This presents a number of problems.

First this technique opens up the device to potential metal connect reliability issues because one has a separate metal connect that one is making. Moreover this technique also induces another effect when one is operating at high frequencies. There is a phase difference between the electrical signal traveling down the field plate and the one going down the gate. If one is feeding them at the same point because the gate and the field plate are presenting different impedances to the point that one is applying the RF to the signals travel slightly out of phase and could potentially lead to a fighting out of phase condition between the field plate and the gate. The result is that one is not extracting the maximum effect that one would seek from the utilization of the field plate.

In summary the prior art methods may have a number of disadvantages. The prior art method of etching all the way to the semiconductor surface results in damage to the surface leading to increased leakage current and poor reliability and device performance. Damage is particularly severe with dry etching techniques such as Reactive Ion Etching or Inductively Coupled Plasma etching. Alternative wet chemical etching techniques are often less damaging but a wet etch processes result in undesirable undercut of the resist pattern leaving a widened and non uniform gate length. In the separate gate and field plate technique the gate is defined with standard lithography techniques after which the passivation dielectric is deposited. This eliminates the need to etch through the dielectric but results in a gap between the gate and field plate reducing field plate effect and requiring that the electrical connection be made remotely.

A need therefore exists for an improved method for fabrication of field effect transistor gates with or without field plates. More specifically there is a need to 1 eliminate damage inherent in the dielectric gate etch process 2 decrease gate leakage current which is the result of damage during formation of the gate and 3 reduce or eliminate the impact of traps in the gate drain region of the transistor.

According to the present invention a method has been devised that retains all the advantages of forming a gate through a previously deposited dielectric but eliminates damage to the semiconductor surface. This result is accomplished by first depositing a relatively thin metal normally the first Schottky metal layer of the gate on the semiconductor surface before deposition of the dielectric and then etching through the dielectric to reach the Schottky metal which defines the critical transistor gate length. Additional metal is then defined and deposited on the thin Schottky metal to increase the gate cross section and if desired to form a field plate which is integrally connected to the gate.

As a result of the above technique one utilizes the integrated process but adds an additional step of putting down a thin gate metal on the semiconductor after which a passivation layer is deposited. One then performs a dry etch conducted on the passivation layer. It is a feature of the subject invention that the dry etch will stop at the gate metal layer.

With the gate metal layer being in place it serves two purposes. The first is to form a Schottky contact at the gate and the second is to protect the semiconductor from dry etch damage since the plasma etch terminates when it hits the thin Schottky metal. This results in a higher power device and better reliability as well as lower gate leakage.

It is understood that in the dielectric assisted T gate process when one dry etches one produces undercuts in the photolithography pattern. This undermines the actual dimension of the gate electrode which dimension is critical. Not only does the utilization of the subject technique eliminate the plasma damage mentioned above but it also preserves the actual and originally patterned dimensional accuracy of the gate electrode thus to preserve the originally designed gate length.

For instance in performing photolithography and assuming a spread of critical dimension across the wafer of for instance 0.1 micron when doing the dry etch the dry etch could incur an extra non uniformity of for example 0.05 micron on top of the original dimensional non uniformity of 0.1 micron. One therefore has a total non uniformity of about 0.15 micron across the wafer. Thus the initial lithography dimensions in the dielectric assisted T gate process are degraded by the dry etch process.

However with the subject technique one only incurs the initial 0.1 micron of non uniformity across the wafer. As a result the subject process will always have a dimensional accuracy better than performing a separate dry etch process.

Regardless of the dimensional accuracy to which the gate can be manufactured there is the question of reduced gate leakage. The reason that there is reduced gate leakage is because one does not have damaged semiconductor material. It is noted that in an ideal field effect transistor one would want the gate Schottky contact to be very low leakage ideally having a zero leakage. In this case the gate Schottky contact should not draw any current on the gate. When one starts to draw current on the gate electrode one degrades the device efficiency and makes it more difficult to account for current that would be drawn on the gate electrode during amplifier designs.

In summary when utilizing the dry etch process it is certainly more difficult to come up with a process that works very well and still will incur low leakage. If one uses a direct etch process without the subject technique one could potentially incur a gate leakage that is an order or two of magnitude higher than when utilizing the metal layer protection between the dry etch and the semiconductor.

While the subject devices have major utility in military applications such as radars and the like in the commercial realm the focus for such high power transistors is in cellular base stations which operate in the lower microwave range for instance from 2 to 5 GigaHertz.

Base station transmitters for cell towers are based on silicon LDMOS devices in which LDMOS refers to lightly doped drain metal oxide semiconductor field effect transistors.

The gallium nitride devices with field plates provide much higher power and produce better linearity than standard LDMOS FETs which is very important in the cell phone applications. Also the gallium nitride devices have lower cooling requirements due to the larger bandgap and lower intrinsic carrier concentration. The use of gallium nitride devices thus reduces the cost that one would have to incur when one is setting up a new cellular base station.

Whether utilizing gallium arsenide or gallium nitride or in fact any other FET device the subject fabrication technique provides improved results. The subject technique is optimally efficient due to the utilization of the thin refractory metal layer that not only serves to shut off the gate contact but also is a protective layer during the dry etch process. The refractory metal layer permits control of the very critical gate length because it permits utilizing a very well controlled conventional photolithographic technique for gate length. As compared with the dielectric assisted T gate approach with the absence of the refractory metal layer the critical gate length dimension is the dry etch opening which is much less well controlled compared to the direct lithography utilized with the refractory metal layer patterning.

In summary a method for fabrication of a field effect transistor gate with or without field plates includes the steps of defining a relatively thin Schottky metal gate by a lithography metal liftoff or metal deposition etch process on a semiconductor surface. This is followed by depositing a dielectric passivation layer over the entire semiconductor surface and defining a second lithographic pattern coincident with or slightly inset from the boundaries of the previously defined metal gate layer. This is followed by etching a dielectric opening using dry or wet etching techniques and stripping the resist followed by exposing and developing a third resist pattern to define the thicker gate metal layers required for electrical conductivity and also for the field gate if one is utilized. The final step is depositing the gate electrode and an integral field plate if desired.

Referring now to in the prior art direct etch technique described above a field effect transistor is provided with a source and a drain on top of a gallium nitride layer which is in turn deposited over an aluminum gallium nitride layer which is on top of a gallium nitride layer .

Note that the base of the field effect transistor can be either of but not limited to silicon silicon carbide sapphire aluminum nitride or gallium nitride on which the gallium nitride layers are deposited.

In order to provide the gate here illustrated at or an integral field plate the active area of the device is defined by either mesa etching or ion implantation.

For the active area in the prior art process passivation layer is formed over the source drain and gallium nitride layer at which point an opening at is provided in passivation layer by direct ion etching.

This direct ion etching is supposed to provide passivation layer with correctly dimensioned sidewalls so that the gate metal layer is deposited over passivation layer the gate electrode will have a critical dimension indicated by double ended arrow that defines the dry etched dimension.

However as can be seen in walls in the silicon nitride passivation layer are not dimensionally accurate enough and slope inwardly such that the critical dimension here the gate length is not very well controlled.

What this means is that when the gate and or its integral field plate are deposited over the passivation layer and onto the exposed substrate the critical gate electrode dimension is not adequately controlled.

Moreover as can be seen by the Xs at there is semiconductor crystal damage near the surface of the gallium nitride layer such that electron trapping and other deleterious effects occur.

It is thus the lack of ability to define the critical dimension for the gate electrode along with the damage caused by dry etch process that is problematic for the method described in .

In order to get away from the deleterious effects of the dry etch process shown in and referring now to field effect transistor built on top of layers and is provided with a separate gate and field plate with gate and field gate being connected externally as illustrated at .

The problem with such a configuration is that there is a gap between field plate and the gate electrode which reduces the effectiveness of the field plate in controlling surface states next to gate electrode . Also a problem is the external connection. Note that there is a separation of the field plate with respect to the gate which is at least the dimension of the passivation layer.

Referring now to in the subject technique field effect transistor has an integral gate field plate structure deposited over an aperture in passivation layer which is deposited over a thin refractory metal layer that preserves the critical dimension against subsequent processing.

What will be appreciated is that regardless of the dry etch processing that may be utilized to provide the aperture in passivation layer the priorly patterned refractory metal layer maintains the critical dimension regardless of the subsequent processing.

Also as will be described thin refractory metal layer protects the underlying substrate namely layer from being damaged in the process used to etch layer . Additionally the use of the refractory metal layer preserves the critical dimension even in the presence of resist undercutting associated with dry etching.

Referring now to source and drain electrodes are photolithographically formed on top of gallium nitride layer and are annealed to react with the gallium nitride layer to form an ohmic contact.

After forming the source and drain regions and referring now to a thin refractory metal layer is formed on top of gallium nitride layer to form a gate contact. Layer is also is a protective layer that is useful during a subsequent dry etching process. Note that the refractory metal layer can be centered between the source and drain or can be offset to one side typically toward the source contact.

In one embodiment the refractory metal layer is made of nickel. Alternatively platinum can be used with nickel and platinum being typical choices for gallium nitride. In one embodiment the thin refractory metal layer is on the order of 50 1 000 angstroms. If one is utilizing gallium arsenide one can potentially use other metal layers for forming the gate contact as long as it is a reliable Schottky contact on the material.

As can be seen in a passivation layer is deposited over the entire structure which passivation layer in one embodiment is provided by plasma enhanced chemical vapor deposition of silicon nitride. Thus the silicon nitride passivation layer covers all of the metal contacts as well as the active and non active device areas.

Referring to utilizing photolithography windows are opened in the passivation layer to connect to the ohmic contacts for the source and drain regions. Note that only the source and drains are opened up at this juncture. The gate contact is not opened up at this step because the dimensions are much smaller than the source and drain regions and because one wants to have better control of the lithography on top of the gate contacts. Thus typically the opening up of the refractory metal layer is done utilizing electron beam lithography.

Referring to the opening up of the refractory metal layer in one embodiment is accomplished by photolithographically providing a photoresist over the top of the structure formed in with the photoresist layer providing an opening either coextensive with or slightly smaller than the dimension of refractory metal layer .

Referring now to passivation layer having been photolithographically masked off is subjected to ion etching utilizing electron beam lithography which offers better control of the dimension of the aperture in the passivation layer. This careful control is more desirable for higher frequency applications where the dimension of gate contact is smaller but commercial devices that operate at lower frequencies benefit from the utilization of electron beam lithography for better alignment control.

Electron beam lithography is fine line lithography desirable for high frequency devices. However while this is useful in commercial applications commercial applications utilize larger dimensions and longer gate lengths. Thus one can use standard photolithography with reduced dimension control at this step.

Here it is important to note that the dimension illustrated by double ended arrow is the aforementioned critical dimension and corresponds in one embodiment to gate length.

Referring now to additional metal for gate electrode is deposited into the etched aperture in passivation layer which extends down to the refractory metal layer that provides Schottky contact to substrate in the active area of the field effect transistor.

In one embodiment a field plate is integrally formed with the gate such that integral field plate region is formed in the same step as the gate electrode. Here the field plate overlap area is shown by double ended arrow . Electron beam lithography is utilized to deposit metal that covers the open trench on top of the refractory metal layer . This gate metal is such that it provides for good adhesion to silicon nitride and also makes a good contact to the underlying refractory metal layer that one already has in place.

In the embodiment the field plate extends toward the drain because that is where the high electric field is in the field effect transistor. Note that the field plate can be made smaller for higher frequency or larger for lower frequencies. However a bigger field plate will allow one to operate at higher voltages. Thus there is a tradeoff between frequency performance versus high voltage operation.

It should also be noted that there is no gap between the field plate and the gate due to the integrated structure.

By way of comparison and referring to critical dimension shown by the corresponding double ended arrow is preserved by the pre patterned thin refractory metal layer. Note that in ion etching or dry etching of passivation layer sidewalls exhibit etch undercut due to the abrasion of the ion etching regardless of the high accuracy of this technique. This well known effect is referred to as etch undercut as indicated in . The result is that the dry etch opens a window over refractory metal layer with a not well controlled dimension . This dimension is however non critical.

It will be appreciated that not only does the refractory metal layer provide for the critical dimension but also prevents erosion and damage to the underlying substrate here illustrated by layer .

In contrast and as shown in in the prior art dry etch technique for providing for the gate electrode not only are walls tapered and therefore not well controlled there is also undercutting of the passivation layer as illustrated at . This results in a reduction of the accuracy of the critical dimension in the direct dry etch scenario along with an area which is a damaged surface area in layer right underneath the gate.

For the dry etch technique the dry etch damage results in the aforementioned traps and at the very least a variation in the characteristic right underneath the gate. If one has some damage at this position those damage defect sites collect some electrons and take away from the current carrying channel layer that one has formed underneath the gate. One therefore has reduced current. Moreover because of the damaged material right underneath the very critical control electrode namely the gate electrode one has substantial issues with reliability.

In the subject invention the dimensional accuracy of the refractory metal layer comes directly from the lithography that one is using to pattern this layer and is a very well controlled process utilizing conventional lithography techniques.

On the other hand with the dielectric assisted T gate approach there is an absence of the refractory metal layer. Because there is no such refractory metal layer the critical dimension now becomes the dry etch opening which is much less well controlled compared to the direct lithography utilized to pattern the thin refractory metal layer.

It is important to note that the refractive metal layer that forms the Schottky contact is also a protective layer during the dry etch so that the plasma etching will not attack the gallium nitride layer underneath. This helps with reliability and reduces gate leakage.

As will be appreciated the same kind of field plate and gate formation is applicable to gallium arsenide based devices silicon based devices or indium phosphide based devices all of which can benefit from the subject technique.

Referring back to it will be appreciated that when one is opening a window directly on top of the gate using electron beam lithography and a subsequent plasma etch during the plasma etch the ions are hitting the surface to remove the passivation layer. The refractory metal layer that is the subject of this invention basically stops this erosion process. Note also that the metal layer can absorb any energy that is imparted by the plasma ions. Thus the underlying gallium nitride material does not have to absorb the energy and there is much less damage in the gallium nitride semiconductor layer.

While the present invention has been described in connection with the preferred embodiments of the various figures it is to be understood that other similar embodiments may be used or modifications or additions may be made to the described embodiment for performing the same function of the present invention without deviating therefrom. Therefore the present invention should not be limited to any single embodiment but rather construed in breadth and scope in accordance with the recitation of the appended claims.

