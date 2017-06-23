---

title: Swept frequency laser metrology system
abstract: A swept frequency laser ranging system having sub-micron accuracy that employs multiple common-path heterodyne interferometers, one coupled to a calibrated delay-line for use as an absolute reference for the ranging system. An exemplary embodiment uses two laser heterodyne interferometers to create two laser beams at two different frequencies to measure distance and motions of target(s). Heterodyne fringes generated from reflections off a reference fiducial Xand measurement (or target) fiducial Xare reflected back and are then detected by photodiodes. The measured phase changes Δφand Δφresulting from the laser frequency swept gives target position. The reference delay-line is the only absolute reference needed in the metrology system and this provides an ultra-stable reference and simple/economical system.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=07764384&OS=07764384&RS=07764384
owner: The United States of America as represented by the Administrator of the National Aeronautics and Space Administration
number: 07764384
owner_city: Washington
owner_country: US
publication_date: 20071026
---
The present application derives priority from U.S. provisional application Ser. No. 60 859 554 filed 16 Nov. 2006.

The invention described hereunder was made in the performance of work under a NASA contract and is subject to the provisions of Public Law 96 517 35 U.S.C. 202 in which the Contractor has elected not to retain title.

The present invention generally relates to precision coordinate measurement systems for positioning pointing control and vibration cancellation and more particularly to a laser metrology system capable of providing real time platform motion information at high precision and accuracy.

Various applications require exacting coordinate control of equipment. For example in the space industry there is a need for precision control of spacecraft and payloads. In the particular space context liquid filled inclinometers cannot be used due to their gravity and temperature dependence and limited resolution and eddy current sensors are undesirable due to electromagnetic compatibility with the rest of the spacecraft.

Another application is astronomical inteferomtry. An astronomical interferometer is an array of controlled position telescopes or mirror segments acting together to resolve at a higher resolution. Astronomical interferometers are widely used for optical astronomy infrared astronomy submillimetre astronomy and radio astronomy.

Optical laser metrology is an excellent Sensor option for the foregoing applications because it has excellent resolution. Laser metrology systems that can measure both absolute distance and displacement have broad applications ranging from coordinate measuring machines to deployable structures. Indeed laser metrology systems have become a key component of space craft and payload positioning systems and of stellar interferometers where they are used to monitor path lengths and dimensions internal to the instrument.

As an example the MSTAR sensor Modulation Sideband Technology for Absolute Ranging is an existing NASA system for measuring absolute distance capable of resolving the integer cycle ambiguity of standard interferometers and making it possible to measure distance with sub nanometer accuracy. The design of this system is described by Lay et al. MSTAR An Absolute Metrology System With Submicrometer Accuracy New Frontiers in Stellar Interferometry Proceedings of SPIE Volume 5491 p.1068 October 2004 . MSTAR is a general purpose tool for conveniently measuring length to micron absolute and sub nm displacement and has a wide range of possible applications.

Unfortunately MSTAR and Other known laser metrology systems are relatively complicated use more hardware acousto optic modulators phase modulators etc. require stabilized lasers and place tight tolerance limits on the optics and electronics. In addition frequency sources must be calibrated and stabilized and still there is a large degree of ambiguity of measurement.

Accordingly it would be greatly advantageous to employ a swept frequency laser source and a calibrated reference cavity to measure unknown distance by comparison with the reference cavity. This approach would provide a far simpler laer metrology with reduced hardware overhead reduced claibration and stabilization requirements and reduced ambiguity of measurement.

It is a primary object of this invention to provide an improved laser ranging system with sub micron accuracy.

It is another object to provide a swept frequency laser metrology system that employs common path heterodyne interferometers with a calibrated delay line used as an absolute reference for the system.

It is another object to provide a swept frequency laser metrology system capable of absolute ranging measurement and displacement measurement with no ambiguity in absolute ranging.

It is another object to provide a swept frequency laser metrology system with a calibrated delay line to simplify the metrology system and increase immunity from environmental influences.

In accordance with the foregoing objects the present invention is a laser ranging system with sub micron accuracy using a swept frequency laser metrology system. A common path heterodyne interferometer with a calibrated delay line is used as an absolute reference for the ranging system. In operation the metrology system uses the two laser heterodyne interferometers to create two laser beams at two different frequencies to measure distance and motions of target s . Heterodyne fringes generated from reflections off a reference fiducial Xand measurement or target fiducial Xare reflected back and are then detected by photodiodes. and are the measured phase changes resulted from the laser frequency swept and the phase changes between the two signals and gives target position. The reference delay line is the only absolute reference needed in the metrology system and can be made of ultra low thermal expansion materials such as Zerodur and ULE to provide a ultra stable reference.

The present invention is a laser ranging system that employs a swept frequency laser and multiple common path. heterodyne interferometers one with a calibrated delay line used as an absolute reference for the ranging system. This reference delay line is the only absolute reference needed in the metrology system.

The laser output is split by .a bifurcated optical fiber or otherwise and the split output signal is fed into the two acousto optic modulators AOMs . The AOMs frequency shift the laser output signals by a pre determined amount to produce two heterodyne laser beams MEAS and LO which are offset in frequency to slightly different frequencies. The heterodyne beams MEAS LO output from the AOM s are then split by a Fiber Distribution network to an interferometer array .

The Fiber Distribution network comprises a number of l N fiber optic splitters which transmit both MEAS and LO beams to each of the two or more beam launchers described below in the electronics platform .

For each beam launcher the. MEAS frequency offset laser beam the measurement beam is used to interrogate the distance to a set of fiducials while the second frequency offset laser beam the local oscillator or LO beam remains internal to the beam launcher.

More specifically the electronics platform comprises a number here two of common path heterodyne interferometers CoPHI here being referred to as beam launchers optically coupled to a corresponding set of fiducials . One CoPHI interferometer uses both the MEAS and LO laser beams to interrogate the positioning of a set of reference fiducials Xwhile the second CoPHI interferometer is used to interrogate the positioning of an unknown measured set of reference fiducials X.

The distance Xof the reference delay line is pre calibrated to a high accuracy and is used by the first beam launcher and hence beam launcher is the reference REF beam launcher. Beam launcher is the unknown UNK beam launcher notably situated outside of its metrology fiducials Xfor measuring the distance between point A and point B. The calibrated reference delay line comprises two optical grade mirrors held with a stable spacer to interpose a known distance Xbetween them thereby forming a calibrated reference delay.

In order to measure the phase changes from the laser frequency swept the interferometer array also comprises a number of phase meters each in communication with a respective beam launcher and each used to measure phase between the fringes in each beam launcher .

In operation the above described metrology system uses the two laser heterodyne interferometers to create two laser beams at two different frequencies to measure distance and motions of target s . Heterodyne fringes generated from reflections off the fiducials Xand Xare reflected back to beam launchers where they are then detected by photodiodes. Here Xis the reference delay line length xis the unknown distance and and are the measured phase changes resulted from the laser frequency swept. The phase changes between the two beat signals can be calculated as described below and give the target MEAS distance X as shown conceptually at the bottom inset of .

The collimated optical beam MEAS is split by a polarizing beam splitter PBS and is transmitted to a first fiducial CC1 via a quarter wave 4 plate and through a mask .

The reflection from PBS is transmitted to a beam splitter and on to a holey mirror and fold mirror as will be described.

The mask is used to provide a guard band between core and annulus fringes to reduce diffraction leakage. The mask is simply a plate containing an aperture to lower edge leakage.

The first fiducial CC1 is a Holey corner cube right angle corner mirror with core drilled out to let the center portion of the MEAS beam pass through to thereby hit a second corner cube CC2 .

Two reflected beams including the annulus beam from CC1 and core beam from CC2 then return to the beam launcher . Both returned beams interfere with the second frequency the LO beam to produce an annulus fringe and a core fringe.

These interference fringes both annulus fringe and core fringe are then spatially separated by for example a holey mirror and fold mirror as shown and are focused into two receiving SM optical fibers SMand SM which are connected back to the phase meters and as seen in for the detection of the respective heterodyne signal phases and .

where x is the distance between the fiducials and fare the laser wavelength and frequency respectively.

If a tuneable laser is used as illustrated in then the phase changes due to frequency sweep fin both the reference REF and unknown UNK beam launchers are 4 X f 2 4 X f 3 

where xis the reference delay line length xis the unknown distance and and are the measured phase changes resulted from the laser frequency swept. Note the phase change resulted from frequency sweep is proportional to the length between the two fiducials.

From Equation 4 it is obvious that Xis the only quantity that needs to be calibrated in the metrology system .

If desired a set of data points Xcan then be filtered using a least square fit to remove random errors such as vibrations.

One apparent advantage of the proposed metrology system is that it does not have ambiguity in its distance measurement. This is because the measured phase change is directly proportional to the distance under measurement Equations 1 and 2 .

Additional advantages include that the system can be used in both absolute mode and relative displacement measuring mode. The former is achieved by tuning the laser frequency. The latter is accomplished by using the laser in stationary mode. In the relative mode since the REF delay line is constant in length the measured phase from the REF channel can be used to calculate the laser frequency drift as shown in Equation 2 . The measured frequency drift can then be applied to the UNK channel to correct for the phase errors resulted from the frequency drift.

Several methods can be used to calibate the length of the REF delay line . For example a conventional white light Michelson interferometer setup can be employed as shown in . The configuration shown in utilizes a two beam Michelson interferometer with a tungsten halogen lamp as the light source. The REF delay line cavity is placed along one arm. Light from the lamp is propagated through a collimating lens to a beamsplitter and the upwardly reflected beam passes through a compensator plate to the REF delay line cavity . A mirror is mounted atop a linear translation stage in the other arm. Light is refracted to the mirror and is reflected back where it interferes with light returning from the REF delay line cavity . The combined beam is focussed by lens to a color charge coupled device CCD . Interference fringes may be observed at the CCD . The user simply measures the displacement L of the mirror between two white light fringes to determine the length of the REF delay line and the procedure can be repeated as desired to calibrate the REF delay line .

We have demonstrated a laser metrology system which can perform both absolute ranging measurement and displacement measurement. This metrology system has the advantage of no ambiguity in absolute ranging. Common path heterodyne interferometer using a calibrated reference delay line greatly simplifies the metrology system . The reference delay line made from highly thermally stable materials such as ULE makes the system less immune to environmental influences.

Having now fully set forth the preferred embodiment and certain modifications of the concept underlying the present invention various other embodiments as well as certain variations and modifications of the embodiments herein shown and described will obviously occur to those skilled in the art upon becoming familiar with said underlying concept. It is to be understood therefore that the invention may be practiced otherwise than as specifically set forth in the appended claims.

