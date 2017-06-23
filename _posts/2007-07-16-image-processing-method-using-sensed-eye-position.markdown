---

title: Image processing method using sensed eye position
abstract: A method for processing a captured image is provided. The method includes the steps of sensing the position of an eye and processing the captured image using the sensed eye position. In one embodiment, the step of processing involves detecting a face within the image, and applying a graphical object at a location within the image and relative to the detected face. The graphical object may be a speech bubble.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=07847836&OS=07847836&RS=07847836
owner: Silverbrook Research Pty Ltd
number: 07847836
owner_city: Balmain, New South Wales
owner_country: AU
publication_date: 20070716
---
This Application is a Continuation Application of U.S. Ser. No. 10 636 226 filed on Aug. 8 2003 which is a Continuation Application of U.S. Ser. No. 09 112 746 filed on Jul. 10 1998 now issued as U.S. Pat. No. 6 690 419 all of which are herein incorporated by reference.

The present invention relates to an image processing method and apparatus and in particular discloses a process for Utilising Eye Detection Methods in a Digital Image Camera.

The present invention relates to the field of digital image processing and in particular the field of processing of images taken via a digital camera.

Recently digital cameras have become increasingly popular. These cameras normally operate by means of imaging a desired image utilising a charge coupled device CCD array and storing the imaged scene on an electronic storage medium for later down loading onto a computer system for subsequent manipulation and printing out. Normally when utilising a computer system to print out an image sophisticated software may available to manipulate the image in accordance with requirements.

Unfortunately such systems require significant post processing of a captured image and normally present the image in an orientation to which is was taken relying on the post processing process to perform any necessary or required modifications of the captured image. Further much of the environmental information available when the picture was taken is lost.

It is an object of the present invention to provide a method and apparatus for the utilisation of camera eye detection techniques in a digital camera.

In accordance with a first aspect of the invention there is provided a method of processing an image taken with a digital camera including an eye position sensing means said method comprising the step of utilizing the eye position information within the sensed image to process the image in a spatially varying sense depending upon said location information.

The utilizing step can comprise utilizing the eye position information to locate an area of interest within said sensed image. The processing can includes the placement of speech bubbles within said image or applying a region specific warp to said image. Alternatively the processing can include applying a brush stroke filter to the image having greater detail in the area of said eye position information. Ideally the camera is able to substantially immediately print out the results of the processing.

The preferred embodiment is preferable implemented through suitable programming of a hand held camera device such as that described in the concurrently filed application entitled A Digital Image Printing Camera with Image Processing Capability filed concurrently herewith by the present applicant the content of which is hereby specifically incorporated by cross reference and the details of which and other related applications are set out in the tables below.

The aforementioned patent specification discloses a camera system hereinafter known as an Artcam type camera wherein sensed images can be directly printed out by an Artcam portable camera unit. Further the aforementioned specification discloses means and methods for performing various manipulations on images captured by the camera sensing device leading to the production of various effects in any output image. The manipulations are disclosed to be highly flexible in nature and can be implemented through the insertion into the Artcam of cards having encoded thereon various instructions for the manipulation of images the cards hereinafter being known as Artcards. The Artcam further has significant onboard processing power by an Artcam Central Processor unit ACP which is interconnected to a memory device for the storage of important data and images.

In the preferred embodiment the Artcam device is modified so as to include an eye position sensor which senses a current eye position. The sensed eye position information is utilised to process the digital image taken by the camera so as to produce modifications transformations etc. in accordance with the sensed eye position.

The construction of eye position sensors is known to those skilled in the art and is utilised within a number of manufacture s cameras. In particular within those of Canon Inc. Eye position sensors may rely on the projection of an infra red beam from the viewfinder into the viewer s eye and a reflection detected and utilized to determine a likely eye position.

In the preferred embodiment it is assumed that the eye position sensor is interconnected to the ACP unit of the Artcam device as discussed in the aforementioned Australian Provisional Patent Application which is converted to a digital form and stored in the Artcam memory store for later use.

Turning now to the eye position information and the image are stored in the memory of the Artcam and are then processed by the ACP to output a processed image for printing out as a photo via a print head. The form of image processing can be highly variable provided it is dependant on the eye position information . For example in a first form of image processing a face detection algorithm is applied to the image so as to detect the position of faces within an image and to apply various graphical objects for example speech bubbles in a particular offset relationship to the face. An example of such process is illustrated in wherein a first image is shown of three persons. After application of the face detection algorithm three faces and are detected. The eye position information is then utilised to select that face which is closest to an estimated eye view within the frame. In a first example the speech bubble is place relative to the head . In a second example the speech bubble is placed relative to the head and in a third example the speech bubble is placed relative to the head . Hence an art card can be provided containing an encoded form of speech bubble application algorithm and the image processed so as to place the speech bubble text above a pre determined face within the image.

It will be readily apparent that the eye position information could be utilised to process the image in a multitude of different ways. This can include applying regions specific morphs to faces and objects applying focusing effects in a regional or specific manner. Further the image processing involved can include applying artistic renderings of an image and this can include applying an artistic paint brushing technique. The artistic brushing methods can be applied in a region specific manner in accordance with the eye position information . The final processed image can be printed out as required. Further images can be then taken each time detecting and utilising a different eye position to produce a different output image.

It would be appreciated by a person skilled in the art that numerous variations and or modifications may be made to the present invention as shown in the specific embodiment without departing from the spirit or scope of the invention as broadly described. The present embodiment is therefore to be considered in all respects to be illustrative and not restrictive.

The present invention is further best utilized in the Artcam device the details of which are set out in the following paragraphs although it is not restricted thereto.

The embodiments of the invention use an ink jet printer type device. Of course many different devices could be used. However presently popular ink jet printing technologies are unlikely to be suitable.

The most significant problem with thermal inkjet is power consumption. This is approximately 100 times that required for high speed and stems from the energy inefficient means of drop ejection. This involves the rapid boiling of water to produce a vapor bubble which expels the ink. Water has a very high heat capacity and must be superheated in thermal inkjet applications. This leads to an efficiency of around 0.02 from electricity input to drop momentum and increased surface area out.

The most significant problem with piezoelectric inkjet is size and cost. Piezoelectric crystals have a very small deflection at reasonable drive voltages and therefore require a large area for each nozzle. Also each piezoelectric actuator must be connected to its drive circuit on a separate substrate. This is not a significant problem at the current limit of around 300 nozzles per print head but is a major impediment to the fabrication of pagewide print heads with 19 200 nozzles.

Ideally the inkjet technologies used meet the stringent requirements of in camera digital color printing and other high quality high speed low cost printing applications. To meet the requirements of digital photography new inkjet technologies have been created. The target features include 

All of these features can be met or exceeded by the inkjet systems described below with differing levels of difficulty. 45 different inkjet technologies have been developed by the Assignee to give a wide range of choices for high volume manufacture. These technologies form part of separate applications assigned to the present Assignee as set out in the table below.

The inkjet designs shown here are suitable for a wide range of digital printing systems from battery powered one time use digital cameras through to desktop and network printers and through to commercial printing systems

For ease of manufacture using standard process equipment the print head is designed to be a monolithic 0.5 micron CMOS chip with MEMS post processing. For color photographic applications the print head is 100 mm long with a width which depends upon the inkjet type. The smallest print head designed is IJ38 which is 0.35 mm wide giving a chip area of 35 square mm. The print heads each contain 19 200 nozzles plus data and control circuitry.

Ink is supplied to the back of the print head by injection molded plastic ink channels. The molding requires 50 micron features which can be created using a lithographically micromachined insert in a standard injection molding tool. Ink flows through holes etched through the wafer to the nozzle chambers fabricated on the front surface of the wafer. The print head is connected to the camera circuitry by tape automated bonding.

The following table is a guide to cross referenced patent applications filed concurrently herewith and discussed hereinafter with the reference being utilized in subsequent tables when referring to a particular case 

Eleven important characteristics of the fundamental operation of individual inkjet nozzles have been identified. These characteristics are largely orthogonal and so can be elucidated as an eleven dimensional matrix. Most of the eleven axes of this matrix include entries developed by the present assignee.

The complete eleven dimensional table represented by these axes contains 36.9 billion possible configurations of inkjet nozzle. While not all of the possible combinations result in a viable inkjet technology many million configurations are viable. It is clearly impractical to elucidate all of the possible configurations. Instead certain inkjet types have been investigated in detail. These are designated IJ01 to IJ45 above.

Other inkjet configurations can readily be derived from these 45 examples by substituting alternative configurations along one or more of the 11 axes. Most of the IJ01 to IJ45 examples can be made into inkjet print heads with characteristics superior to any currently available inkjet technology.

Where there are prior art examples known to the inventor one or more of these examples are listed in the examples column of the tables below. The IJ01 to IJ45 series are also listed in the examples column. In some cases a printer may be listed more than once in a table where it shares characteristics with more than one entry.

Suitable applications include Home printers Office network printers Short run digital printers Commercial print systems Fabric printers Pocket printers Internet WWW printers Video printers Medical imaging Wide format printers Notebook PC printers Fax machines Industrial printing systems Photocopiers Photographic minilabs etc.

The information associated with the aforementioned 11 dimensional matrix are set out in the following tables.

A large number of new forms of ink jet printers have been developed to facilitate alternative ink jet technologies for the image processing and data distribution system. Various combinations of ink jet devices can be included in printer devices incorporated as part of the present invention. Australian Provisional Patent Applications relating to these ink jets which are specifically incorporated by cross reference. The serial numbers of respective corresponding US patent applications are also provided for the sake of convenience.

Further the present application may utilize advanced semiconductor fabrication techniques in the construction of large arrays of ink jet printers. Suitable manufacturing techniques are described in the following Australian provisional patent specifications incorporated here by cross reference. The serial numbers of respective corresponding US patent applications are also provided for the sake of convenience.

Further the present application may utilize an ink delivery system to the ink jet head. Delivery systems relating to the supply of ink to a series of ink jet nozzles are described in the following Australian provisional patent specifications the disclosure of which are hereby incorporated by cross reference. The serial numbers of respective corresponding U.S. patent applications are also provided for the sake of convenience.

Further the present application may utilize advanced semiconductor microelectromechanical techniques in the construction of large arrays of ink jet printers. Suitable microelectromechanical techniques are described in the following Australian provisional patent specifications incorporated here by cross reference. The serial numbers of respective corresponding US patent applications are also provided for the sake of convenience.

Further the present application may include the utilization of a disposable camera system such as those described in the following Australian provisional patent specifications incorporated here by cross reference. The serial numbers of respective corresponding US patent applications are also provided for the sake of convenience.

Further the present application may include the utilization of a data distribution system such as that described in the following Australian provisional patent specifications incorporated here by cross reference. The serial numbers of respective corresponding US patent applications are also provided for the sake of convenience.

Further the present application may include the utilization of camera and data processing techniques such as an Artcam type device as described in the following Australian provisional patent specifications incorporated here by cross reference. The serial numbers of respective corresponding US patent applications are also provided for the sake of convenience.

