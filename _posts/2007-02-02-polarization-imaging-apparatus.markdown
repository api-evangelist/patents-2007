---

title: Polarization imaging apparatus
abstract: A polarization imaging apparatus measures the Stokes image of a sample. The apparatus consists of an optical lens set , a linear polarizer  with its optical axis , a first variable phase retarder  with its optical axis  aligned 22.5° to axis , a second variable phase retarder  with its optical axis  aligned 45° to axis , a imaging sensor  for sensing the intensity images of the sample, a controller  and a computer . Two variable phase retarders  and  were controlled independently by a computer  through a controller unit  which generates a sequential of voltages to control the phase retardations of VPRs  and . A set of four intensity images, I, I, Iand Iof the sample were captured by imaging sensor  when the phase retardations of VPRs  and  were set at (0,0), (π,0), (π,π) and (π/2,π), respectively Then four Stokes components of a Stokes image, S, S, Sand Swere calculated using the four intensity images.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=07701561&OS=07701561&RS=07701561
owner: Boston Applied Technologies Incorporated
number: 07701561
owner_city: Woburn
owner_country: US
publication_date: 20070202
---
This application claims the benefit of Provisional Patent Application Ser. No. 60 772 779 filed Feb. 13 2006.

This invention was made partially with Government supports under grant no NNJ05JC13C awarded by NASA. The government has certain rights in this invention.

The invention relates to optical imaging apparatus particularly related to polarization imaging apparatus more specifically related to a high speed polarization imaging system that can measure Stokes components from a sample at different optical wavelengths.

The light scattered by a tissue has interacted with the ultrastructure of the tissue which imprinted some intrinsic properties of the tissue. Tissue ultrastructure extends from membranes to membrane aggregates to collagen fibers to nuclei to cells. Photons are most strongly scattered by those structures whose size matches the photon wavelength. It has been demonstrated that light scattering can provide structural and functional information about the tissue. One important biomedical application of optical imaging and spectroscopy is non invasive or minimally invasive detection of pre cancerous and early cancerous changes in human epithelium such as dysplasia or carcinoma in situ.

In recent years there has been an increasing interest in the propagation of polarized light in randomly scattering media. The investigation of backscattered light is of particular interest since most medical applications aimed at the in vivo characterization of biological tissue rely on backscattered light. By recording the spatially dependent response of a medium to a polarized point source one may obtain information about the scattering particles that are not accessible to mere intensity measurements. A diagnostic imaging modality based on near infrared NIR radiation offers several potential advantages over existing radiological techniques. First the radiation is non ionizing and therefore reasonable doses can be repeatedly employed without harm to the patient. Second optical methods offer the potential to differentiate between soft tissues due to their different absorption or scatter at NIR wavelengths that are indistinguishable using other modalities. And third specific absorption by natural chromophores such as oxy haemoglobin allows functional information to be obtained. NIR imaging research has focused on a variety of possible clinical applications.

The fact that the polarization state of the light contains useful information has been shown in many literatures for example. Rahmann and Canterakis in Reconstruction of specular surfaces using polarization imaging vol. 1 pp. 149 155 2001 describe how the polarization state of light can be used for the reconstruction of specular surfaces to determine the shape of 3 D objects. They use the fact that light reflected by dielectrics and metals becomes partially linearly polarized and that the direction of polarization depends on the orientation of the reflecting surface. Demos and Alfano in Deep subsurface imaging in tissues using spectral and polarization filtering vol. 7 no. 1 pp. 23 28 2000 demonstrate a technique based on polarization imaging that allows for optical imaging of the surface as well as structures beneath the surface.

There have been several polarization imaging schemes published. In U.S. Pat. No. 6 437 856 inventor Steven Louis Jacques which issued Aug. 20 2002 and U.S. Pat. No. 5 847 394 inventors Robert R. Alfano et al. which issued Dec. 8 1998 a set of measurements at different polarization orientations are taken to render a new image that is independent of the light reflected from the surface of a tissue sample and that is dependent of the light scattered from deep tissue layers. Especially a linearly parallel polarized light is used for illumination and two images are acquired one image selecting linearly parallel Par polarized light i.e. parallel to the light source tissue camera plane and one image selecting linearly perpendicular Per polarized light i.e. perpendicular to the light source tissue camera plane . A new image is obtained by Par Per or Par Per Par Per .

Many polarimetric sensing technologies have been developed to capture the Stokes polarization information. People use rotating retarder rotating polarizer to obtain Stokes parameters from several successive frames of image. In these mechanically rotation approaches however the exact spatial registration between various frames is difficult due to changes of viewing angle and the polarization properties during the period of between successive frames in most target detection applications.

In U.S. Pat. No. 6 798 514 inventor James Maurice Daniels which issued Sep. 28 2004 the light passes through two liquid crystal waveplates and a polarizing filter before falling on a light sensitive element device to measure intensity of light in four different polarizations. However the same difficulty also applied to the approach using liquid crystal for electro optic polarization modulation which usually has response time in the order of 100 ms. Another drawback for the liquid crystal approach is that polarization rotating liquid crystals are not commercially available in many important IR bands.

It is therefore the main objects of the invention to provide a polarization imaging apparatus which can consistently provide high speed and broadband Stokes images in real time.

The first key feature of the polarization imaging apparatus is that it provides fast adjustable optical phase control through high speed electro optical variable phase retarders made from transparent electro optic ceramics.

The second key feature of the invention is that the polarization imaging apparatus can be worked at a wavelength from 400 nm to 7 m using electro optic ceramics.

The third key feature of the invention is that a simplified time sequential control and measurement algorithm which provides a fast measurement and converts sequential intensity images to Stokes images.

A preferred embodiment of the polarization imaging apparatus is shown in which consists of a polarization imaging sensing unit an electronic driver and a computer . The imaging sensing unit consists of an optical lens set a linear polarizer with its optical axis a first variable phase retarder VPR with its optical axis aligned 22.5 to axis a second variable phase retarder with its optical axis aligned 45 to axis and a imaging sensor for sensing the intensity images of the sample. The imaging sensor can be a focal plan array FPA detector a CMOS or a CCD sensor. Two VPRs and were controlled independently by a computer through a controller unit which generates a sequential of voltages to control the phase retardations of VPRs and . A set of four intensity images I I Iand Iof the sample were captured by imaging sensor when the phase retardations of VPRs and were set at 0 0 0 and 2 respectively Then four Stokes components of a Stokes image S S Sand Scan be calculated by computer using the following formula 

In one aspect the present invention includes the ferro electric materials such as PLZT La modified PMN PT and La modified PZN PT to form the electric voltage controlled ferro electric variable phase retarder.

Referring to is another preferred embodiment of the polarization imaging apparatus consists of an illumination unit a polarization imaging sensing unit a controller unit and a computer . The said illumination unit and imaging sensing unit are aligned in a reflection configuration. In addition to a light source the illuminator may consist of parts such as a collimator a polarizer or polarization modulator and a fixed wavelength filter or tunable wavelength filter. Tunable optical band pass filter is used to produce desired wavelength for the imaging from visible to infrared IR . The illuminator can produce a linear or arbitrary polarized light beam.

The illumination unit and a polarization imaging sensing unit in can be further aligned in a transmission configuration as illustrated in .

Additional features and advantages of the invention will be set forth in the detailed description which follows and in part will be readily apparent to those skilled in the art from that description or recognized by practicing the invention as described herein including the detailed description which follows the claims as well as the appended drawings.

It is to be understood that both the foregoing general description and the following detailed description present embodiments of the invention and are intended to provide an overview or framework for understanding the nature and character of the invention as it is claimed. The accompanying drawings are included to provide a further understanding of the invention and are incorporated into and constitute a part of this specification. The drawings illustrate various embodiments of the invention and together with the description serve to explain the principles and operations of the invention.

It is to be understood that the invention is not limited in its application to the details of the particular arrangement shown since the invention is capable of other embodiments. Also the terminology used herein is for the purpose of description and not of limitation.

Using Mueller s calculus we can obtain the Stokes parameters of an input light by measuring the output light intensity of the sensor . The transformation done by the phase retarders can be described in the following equation . 2 

where S SSSS is the unknown input Stokes vector of the target which consists of four Stokes components. The parameter Sis the intensity of the light including un polarized component Sis the intensity difference between horizontal linearly polarized and the vertical linearly polarized components Sis the intensity difference between 45 linearly polarized and the 135 linearly polarized components and Sis the difference between left and right circularly polarized intensities.

The quantities M and Mare the Mueller matrices representing two variable phase retarders and respectively. These are given for the specific orientation by

where and are the two phase retardance introduced by the two variable phase retarders and respectively.

To be able to measure the four components of the input Stokes vector we need to set the variable phase retarders to at least four different states labeled as k. In the following we detail the linkage between input state Stokes parameters and measured light intensity. The Mueller matrix for the cascaded variable retarders can be generally cast into an alternative form so that the state of polarization incident on the polarizer can be expressed as 

It is clear that the output intensity can be linked to the input Stokes parameters through generating four known states of polarization at the input so that we have 

where mis the Mueller matrix element at the k th state of variable retarders and Iis the intensity measured with the i th state of variable retarder. From Equation 7 it can be noticed that once the matrix A is known the input Stokes parameters can be found out the inverse the matrix so that 

The very question now is to find out the matrix A. It can be calculated from each Muller matrix in the system or it can be done by generating four known states of polarization so that 

where Sis the i th Stokes parameter generate by the j th retardance. Thus we are able to link the input state polarization to the intensity measured at four retardance states. The Mueller matrix elements needed for finding the input state of polarization can be figured out through the use of four known state of polarization.

The measurement procedure is based on specifying above general principle for practical applications. As the configuration shown in we can find out the useful Muller matrix elements according to equation 6 as follows m 1 cos 1 2 cos 2 sin 1 sin 2 2 sin 1 2 cos 1 2 sin 2 sin 1 cos 2 2 10 

where and are the retardance of two VPRs and respectively. Although their values could be many different combinations for finding out the Stokes vector the following 4 state procedure is considered to be the simplest yet most effective approach.

Four intensity images I I are needed and taken sequentially with two variable phase retarders and controlled by a sequence of voltages which were generated by controller . Phase retardation changes and of VPR and VPR respectively. Iis taken with 0 volt applied to both and . Iis taken with the half wave voltage V applied to and 0 volt applied to . Iis taken with V is applied to both retarder and . Iis taken with a quarter wave voltage Vapplied to and V applied to . The four Stokes vector images S Scan be calculated from the intensity as follows 

Table 1 listed the state of retardance of first and second variable phase retarders and the corresponding four intensities measured in each equal length time slot. The intensities also can be expressed as a function of Stokes parameters S Sof the input Stokes vector according to equation 2 . Table 1 also listed the formula for extracting the Stokes parameters S Sfrom these intensities.

With this simple converting formula Stokes images can be obtained using very simple calculation from the intensity images captured by an imaging sensor.

It should be pointed out that the switch of the relative positions of VPR and VPR will not affect the outcome of the Stokes images according to equation 2 .

It is to be appreciated that the orientation configuration between the two variable phase plates and might be achieved with an intervening fixed waveplate so that physical orientation of the two plates could be less constrained. Hence the 22.5 degree orientation of the second variable phase retarder with respect to the first variable phase retarder of claim is achieved by any combination of relative physical rotation of the second variable phase retarder with respect to the first retarder and rotation of the polarization reference frame between the two variable phase retarders and by a fixed phase retarding plate not shown but included as part of the present invention .

Any other orientation configuration of first variable phase retarder and second variable phase retarder will also work as long as the two variable retarders oriented at different angles however may involve more difficult calculations.

In addition to the simplified measurement algorithm a key component in this polarization imaging apparatus is the variable phase retarder. The other means to change the phase retardation rotating waveplates Faraday rotators and Pockel s cell have been used in laboratories worldwide. These devices however are bulky high power consumption slow or expensive.

A preferred variable phase retarder is made from an electro optic EO material. The general requirement for an EO variable phase retarder is that when a voltage is applied a predetermined phase shift is produced for the light beam. Also the material is isotropic with no voltage applied there is no residual birefringence to cause the initial phase shift. Preferably the material has a high electro optic coefficient in order to reduce operating voltages to less than 500 volts. Also the mechanical characteristics allow formation of a bar or plate for use as the electrode. Of course the material must be transparent at the wavelength of interest e.g. between 450 nm and 7 m for most of the polarization imaging applications.

These requirements are satisfied by a class of ferroelectric complex oxides which 1 are optically isotropic 2 have a Curie temperature less than about 490 C. so that electro optic coefficients are high near room temperature 3 have a diffusive phase transition so that the temperature dependence of the electro optic coefficients is lessened and 4 which are not permanently poled by moderate electric fields since materials with a low Curie temperature that become permanently poled are less stable. Example material systems include electro optic lanthanum modified PZT PLZT lead manganese niobate PMN a solid solution of lead zinc niobate and lead tantalate PZN PT and a solid solution of lead manganese niobate and lead tantalate PMN PT . Besides PLZT without being an exhaustive list the following materials and their solid solution with or without lanthanum modification may be used Pb Zr Ti O Pb Mg Nb O PbTiO Pb Zn Nb Oand PbTaO. These materials are available from Corning Inc. Corning N.Y. and Boston Applied Technologies Inc. Woburn Mass. referenced as OptoCeramic materials. These materials are electrical controllable solid state high speed low insertion loss and low fabrication cost.

A preferred OptoCeramic material PMN PT for use in the present invention may be described by the general formula PbLa MgNb Ti O

wherein x is between about 0.6 and about 0.95 z is between about 0 and about 0.08 and t is between about 0.30 and about 0.36. In especially preferred electro optic ceramic materials of the present invention z is between about 0.01 and about 0.06. In preferred electro optic materials of the present invention t may be between about 0.32 and about 0.34 and x may be between about 0.65 and about 0.90.

According to the present invention the preferred OptoCeramic PMN PT is lanthanum modified solid solution of lead manganese niobate and lead tantalate La PMN PT or PLMNT with a nominal 3.5 75 25 La PMN PT composition. For reference purposes nominal values for this PLMNT are n 2.48 and R 11.5 10m Vat 1.06 m and n 2.458 and R 6.86 10m Vat 1.55 m both at 23 C. PLMNT has a polycrystalline structure with crystal sizes ranging from about 5 to 20 microns. In the form of hot pressed ceramics it is optically isotropic and exhibits little birefringence with zero applied voltage.

An electrode geometry of phase retarder which takes advantage of these materials is illustrated by the transverse field configuration illustrated in . A plate for use as the variable phase retarder and of is shown which has thin metallized electrodes and on the both sides respectively of a block section of EO material. The electrodes and are shown connected to a driving voltage provide by controller shown in . The electric field designated E is 90 to the direction of light propagation. Since the effect is based on the electric field in the material it is desirable to arrange the electrodes as close together as possible to minimize the control voltage. The optical axis of the EO element is perpendicular to the electric field.

As an example an EO phase retarder is made from a PLMNT plate with metallized electrodes which has dimensions where the width w between the electrodes is about 5 mm a thickness t of about 4 mm and a length l of about 5 mm. Such a dimensioned PLMNT plate has an insertion loss of about 0.1 dB and half wave voltage of 320V for a 700 nm wavelength laser at 23 C.

It will be understood that the particular geometry described is an example and that other device geometries can be used. Different dimensions of w and t can be selected to provide the same phase shift with different control voltage. The other preferred PLMNT plate has dimensions of but not limited to a width w of about 0.5 5 mm a thickness t of about 1.30 5 mm and a length l of about 1.0 5.0 mm.

Another preferred OptoCeramic material is PLZT with a nominal 9.5 65 35 La Pb Zr composition. This composition is known to be transparent in a range from 450 nm to 7 m see for example Lionel M. Levinson Electronic Ceramics Chapter 7 Marcel Dekker New York 1987 .

Yet another preferred OptoCeramic material PZN PT for use in the present invention may be described by the general formula PbBaLa ZnNb Ti O

wherein x is between about 0.5 and about 0.9 y is between about 0.05 and about 0.5 z is between about 0 and about 0.05 and t is between about 0.30 and about 0.36. In especially preferred electro optic ceramic materials of the present invention x is between about 0.65 and about 0.85 y is between about 0.1 and about 0.2 z is between about 0.02 and 0.04 and t is between about 0.32 and about 0.34.

Referring to is the measured variable phase retarder response. The optical response to the applied control voltage is less than 1 microsecond. This means that the speed of setting and resetting of the VPR is as fast as 1.0 microsecond. According to the present invention the imaging apparatus only needs 2 and 3 settings for the first and the second variable phase retarders and to complete a measurement cycle respectively. The polarization sampling time could be less than 3 microseconds. This equals the system can generate a set of 4 Stokes component images at a speed of up to 300K frames per second fps . With a fast enough imaging sensor a real time Stokes polarization imaging system can be realized.

In the present invention another preferred EO material for variable phase retarders and are made from liquid crystals for a polarization imaging system working between the optical wavelengths 350 nm to 2000 nm. Using the invented control algorithm illustrated in and relationship between sequential intensity images and Stokes images listed in Table 1 a fast polarization imaging system using LC variable retarders can also be configured.

A polarization imaging apparatus shown in is basically a passive imaging system which using ambient light source to illuminate the sample. Referring to is a schematic view of a preferred embodiment of an active polarization imaging apparatus in accordance with the present invention. It consists of an illumination unit and an imaging sensing unit . The said illumination unit and imaging sensing unit are aligned in a reflection configuration. Both illumination unit and imaging sensing unit can be set to an angle related to sample surface normal . In addition to a light source the illuminator may consist of parts such as a collimator a polarizer or polarization modulator and a fixed wavelength filter or tunable wavelength filter . Tunable optical band pass filter was used to produce desired wavelength for the imaging from visible to infrared IR . The illuminator could produce a linear or arbitrary polarized light beam.

A preferred light source is a broadband light source such as a tungsten halogen lamp which provides a strong intensity over a broad spectrum from UV to NIR 300 nm to 2 m . Another preferred light source is a light emitting diode LED source or laser source.

The scattering light from sample is detected by the imaging sensing unit . The optical lens set in shown in can be an optical objective lens in with an infinite focal length which makes the polarization imaging system a Stokes microscope.

The first VPR and second VPR were controlled independently by a computer through a controller unit which generates a sequential of voltages to control the phase retardations of VPRs and . A set of four intensity images I I Iand Iof the sample were captured by imaging sensor when the phase retardations of VPRs and were set at 0 0 0 and 2 respectively Then four Stokes components of a Stokes image S S Sand Scan be calculated by computer according to equation 1 .

Referring to is a schematic view of a polarization imaging apparatus shown in configured in a transmission configuration.

It will be apparent to those skilled in the art that various modifications and variations can be made to the present invention without departing from the spirit and scope of the invention. Thus it is intended that the present invention cover the modifications and variations of this invention provided they come within the scope of the appended claims and their equivalents.

