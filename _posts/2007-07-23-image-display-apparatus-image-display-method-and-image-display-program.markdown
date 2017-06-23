---

title: Image display apparatus, image display method, and image display program
abstract: An image display apparatus is disclosed that includes an image projecting unit that projects a projection image on a projection screen, a written image capturing unit that captures a written image of a writing screen that is arranged opposite the projection screen, a written image area extracting unit that extracts a written image area from the captured written image captured by the written image capturing unit, an image compositing unit that composites the written image area extracted by the written image area extracting unit and the projection image projected by the image projecting unit. The written image area extracting unit includes an external light value detecting unit that detects an external light value and an image processing unit that performs an image correction process on the captured written image based on the external light value detected by the external light detecting unit.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08031941&OS=08031941&RS=08031941
owner: Ricoh Company, Ltd.
number: 08031941
owner_city: Tokyo
owner_country: JP
publication_date: 20070723
---
The present invention relates to an image display apparatus an image display method and an image display program adapted for compositing a projection image projected on a projection screen and a written image written on a writing screen extracting the written image as electronic information and processing the written image.

In addition to having basic functions for displaying visual information such as characters figures and images on a display screen an image display apparatus is starting to have interactive functions for enabling the apparatus to work closely with a user.

Such functions may have developed in view of the recent technological advancements in information processing apparatuses such as the computer which is used to configure the system of the image display apparatus. Also the fact that the image display apparatus is often used in situations demanding efficient execution of complicated processes involving interactive operations by the user may have created incentives for developing such functions.

For example in a situation where the image display apparatus is used in a conference or a seminar in which participants discuss the contents of the image information displayed on the display screen the image display apparatus may desirably have a function for inputting information describing matters discussed during the course of the conference seminar as electronic information in a personal computer which function may enable a participant to write information over the image information displayed on the display screen as is necessary in leading the discussion.

In view of such circumstances image display apparatuses have been developed that are adapted to realize image display and image writing on the same screen and extract the written image as electronic information.

For example Japanese Laid Open Patent Publication No. 2005 71192 discloses an image display apparatus that uses an image capturing device such as a CCD camera to capture images of written characters and figures as electronic image information determines a representative color based on the RGB value of the written image information and performs color conversion of the written image information into the determined representative color to extract the written image information. Japanese Laid Open Patent Publication No. 2005 354171 discloses an image display apparatus that measures the external light in the used environment switches the color of a projected image of an image projecting apparatus such as a projector to black or white according to the measured external light and changes the color of a written image in order to obtain a composite image including a high quality written image that is not influenced by external light.

However the technique disclosed in Japanese Laid Open Patent Publication No. 2005 71192 does not take into account variations in external light so that when the image display apparatus is used in a very dark environment e.g. inside a room with the lights turned off or a very bright environment e.g. environment in which sunlight seeps through the display screen the accuracy of color distinction involving determining a representative color based on the RGB value of a written image and distinguishing the written color may be degraded.

Also although the technique disclosed in Japanese Laid Open Patent Publication No. 2005 354171 takes into account the variations in external light in adjusting the color of a written image to thereby achieve advantageous effects in improving the quality of the composite image from which a written image is extracted i.e. an image suitable for having written information extracted therefrom may be stably obtained under any usage environment with regard to image processes for extracting the written image from the composite image e.g. background removal shading correction color conversion effective measures that take into account such variations in external light to accurately extract the written image are not proposed so that the accuracy of written image extraction may be degraded in such image processes including color distinction and recognition of the written image for example.

As can be appreciated prior art techniques as described above have problems with regard to accurately extracting a written image from a composite image taking into account variations in external light conditions that may vary depending on the usage environment of the image display apparatus.

Embodiments of the present invention are directed to an image display apparatus an image display method and an image display program that are adapted for controlling image processes for extracting a written image from captured image data according to external light conditions that may vary depending on the usage environment of the image display apparatus.

According to one embodiment of the present invention an image display apparatus is provided that includes 

a written image capturing unit that captures a written image of a writing screen that is arranged opposite the projection screen 

a written image area extracting unit that extracts a written image area from the captured written image captured by the written image capturing unit and

an image compositing unit that composites the written image area extracted by the written image area extracting unit and the projection image projected by the image projecting unit 

wherein the written image area extracting unit includes an external light value detecting unit that detects an external light value and an image processing unit that performs an image correction process on the captured written image based on the external light value detected by the external light detecting unit.

According to another embodiment of the present invention an image display method is provided that includes the steps of 

the written image area extracting step involves detecting an external light value and performing an image correction process on the captured written image based on the detected external light value.

According to another embodiment of the present invention a computer readable medium is provided that contains a computer readable program for displaying an image which programs is run on a computer and is executed by the computer to perform the steps of 

the written image area extracting step involves detecting an external light value and performing an image correction process on the captured written image based on the detected external light value.

In the following preferred embodiments of the present invention are described with reference to the accompanying drawings.

The image display apparatus according to the present embodiment includes the display unit as is shown in and a mainframe unit projection image generating unit as is shown in .

The display unit includes a rectangular plane unit having a rectangular screen display screen arranged at its center portion on which an image projected from the interior of the apparatus is displayed.

As is shown in the display unit includes the plane unit with the screen arranged at its center portion a box that supports the plane unit a projector that projects an image on the screen and a CCD Charge Coupled Devices camera image capturing unit that is positioned such that its angle of view covers the entire rear face of the screen and is configured to capture an image of the screen from its rear face.

The projector and the CCD camera are accommodated inside the box . The CCD camera is connected to the mainframe unit by a cord and the projector is optically coupled to the mainframe unit .

The screen has a dual layer structure including a projection screen on which a projection image may be projected that is arranged on the rear side of the screen and a writing screen on which images may be written using a water base pen or a white board marker referred to as marker hereinafter that is arranged on the surface side of the screen . The projection screen and the writing screen face each other and are bound together into an integrated structure.

In the present embodiment the projection screen and the writing screen are both transparent and the face of the projection screen that comes into bonding contact with the writing screen is arranged into a fine indented surface so that when an image is projected on the projection screen the image light may be slightly scattered and transmitted to enable the projected image to be viewed from various angles.

The surface of the writing screen may be covered by a transparent protective sheet or a transparent coating for example so that it may be protected from damage such as scratches.

The projector is optically coupled to a display of the mainframe unit by an optical system including a reflection mirror and a beam splitter for example and is configured to project a desired image generated at the mainframe unit on the projection screen of the screen .

The CCD camera is connected to the mainframe unit via a USB Universal Serial Bus interface and a cord for example. The CCD camera successively captures images of characters and figures written on the surface of the screen i.e. the writing screen at predetermined time intervals from the rear face of the screen i.e. projection screen to acquire captured images referred to as captured image data hereinafter .

It is noted that the CCD camera may be any type of image capturing device that is capable of acquiring an image as digital image data including an industrial CCD camera and a generally used digital camera for example. Also it is noted that the interface used for establishing connection between the mainframe unit and the CCD camera does not necessarily have to be a USB interface and other types of interfaces preferably having a relatively high transmission speed may be used as well.

The illustrated mainframe unit includes a control unit having a CPU Central Processing Unit a main storage unit having a RAM Random Access Memory and a ROM Read Only Memory for example an auxiliary storage unit having a HD Hard Disk for example external input output I Fs interfaces and for establishing connection with external units such as the CCD camera and the projector . The control unit executes an image display control program according to an embodiment of the present invention.

For example in a case where a user wishes to write characters and figures directly onto the writing screen using a marker while viewing the projected image of the projection screen and store the written information along with the projected image as electronic information the control unit may execute a relevant control program according to a control command signal that is issued in response to a corresponding trigger such as the user clicking a dialog button or pressing a hard key switch.

By executing such a control program image information of characters and figures written on the writing screen may be captured by the CCD camera and the written image may be extracted from the captured image data. Then the extracted written image and the projection image projected on the projection screen from the projector may be composited and the resulting composite image data may be projected on the projection screen

As can be appreciated from the above descriptions in the present embodiment written characters and figures may be captured as electronic information to thereby enable effective usage of the written information such as projecting the information on the projection screen or storing the information in the auxiliary storage unit of the mainframe unit .

It is noted that the mainframe unit does not necessarily have to be a dedicated unit for the image display apparatus according to the present embodiment and may alternatively be a PC personal computer that includes at least the essential components of the mainframe unit and has relevant programs and data installed therein for executing image display processes according to an embodiment of the present invention for example. In this case the PC being used as the mainframe unit may be arranged outside the box .

As can be appreciated in the image display apparatus according to the present embodiment a desired image generated by the mainframe unit may be projected on the projection screen of the screen by the projector and characters and figures written on the writing screen of the screen may be captured from the rear face of the screen by the CCD camera to acquired captured image data.

As is shown in the mainframe unit includes a written image capturing unit a written image area extracting unit an image compositing unit a projection image generating unit and an image projecting unit .

The written image capturing unit captures an image of the writing screen of the screen with the CCD camera and acquires captured image data including image information of characters and figures written on the writing screen

The written image area extracting unit extracts image data of a minimal image area including the image information of the characters and figures written on the writing screen referred to as written image hereinafter from the captured image data acquired by the written image capturing unit .

The written image area extracting unit includes an external light value detecting unit an image processing unit and a minimal area extracting unit for accurately extracting a written image without being influenced by external light conditions that may vary depending on the usage environment of the image display apparatus.

The image compositing unit composites the written image extracted by the written image area extracting unit and the projection image projected on the projection screen

The projection image generating unit includes an interface with the projector and generates an image to be projected on the projection screen by the projector according to a predetermined application program.

The image projecting unit projects the projection image generated by the projection image generating unit and the composite image generated by the image compositing unit i.e. composite image of the written image and the projection image on the projection screen

When a control program according to an embodiment of the present invention that is run on the control unit is executed a command signal for the projector to project a black image may be issued from the control unit according to the control program so that the projector may be controlled to project such a black image according to the issued command signal.

In capturing an image of the writing screen with the CCD camera since a projection image is projected on the screen the captured image data acquired by capturing the image of the writing screen after information is written thereon include information of characters and figures written on the writing screen by a marker as well as information of the projection image projected by the projector .

The captured image data as described above merely include color information so that it is quite difficult to distinguish and extract the written image from the captured image data.

Accordingly in the present embodiment the projector is shielded by the image projecting unit in order to avoid transfer of unnecessary information into the captured image data.

In another embodiment if the projector has a mute function such a function may be used to shield the projector .

The written image capturing unit captures an image of the writing screen when the projector is shielded by the image capturing unit to acquire captured image data as is shown in for example.

In the process flow of the image display apparatus as is shown in a black image is projected on the projection screen from the projector by the image projecting unit according to a command signal from the control unit S and information of characters and figures written on the writing screen as captured image data are acquired by the written image capturing unit from the CCD camera S .

Then the captured image data acquired by the written image capturing unit are transferred to the written image area extracting unit .

The written image area extracting unit controls the external light value detecting unit to detect an external light value under the current usage environment of the image display apparatus based on captured image data of the writing screen that does not include written characters and figures referred to as blank image hereinafter S .

Then based on the external light value detected by the external light value detecting unit the image processing unit performs a background removal process S and image correction process shading correction process S and a color conversion process S .

Then the minimal area extracting unit extracts a minimal written image area written image from the processed image data S .

Then the written image extracted by the written image area extracting unit are transferred to the image compositing unit at which the written image is composited with a projection image generated by the projection image generating unit so that the resulting composite image may be stored in the auxiliary storage unit of the image display apparatus or projected on the projection screen by the image projecting unit for example.

As can be appreciated from the above descriptions in the present embodiment image processing is performed on image data subject to written image extraction according to external light conditions based on the external light value detected by the external light value detecting unit so that influences of the external light on the captured image data may be properly corrected and information of written characters and figures may be accurately acquired.

In the following image processes performed by the written image area extracting unit according to external light conditions are described with reference to .

As is described above the written image area extracting unit includes the external light value detecting unit the image processing unit and the minimal area extracting unit .

Captured image data captured by the written image capturing unit are input to the written image extracting unit at which the image processing unit performs image correction processes on the input captured image data and the minimal area extracting unit extracts the written image.

In this case functional units included in the image processing unit are controlled according to the external light conditions in the usage environment of the image display apparatus based on the external light value detected by the external light detecting unit .

The external light detecting unit includes external light value detection means for detecting the external light value to be used upon performing image correction on the captured image data at the image processing unit . According to one embodiment the external light value detecting unit may detect the external light value for image correction by calculating the brightness distribution histogram from the blank image as is shown in and determining the most frequently occurring brightness value of the calculated brightness distribution histogram as the external light value for image correction.

The image processing unit has image processing means for correcting the captured image data captured and acquired by the written image capturing unit so that information of written characters and figures may be accurately obtained. Specifically the image processing unit includes a background removal unit a shading correction unit and a color conversion unit .

The background removal unit includes background removal means for calculating a background removal threshold value for a target pixel using an averaging filter and performing a binarization process on the captured image data captured by the written image capturing unit and removing a background area corresponding to an image area other than the written image area containing written characters and figures. It is noted that the averaging filter range averaging computational range for the target pixel may be adjustably set according to the variations in the external light conditions.

The background removal unit uses the background removal means to remove a background area including noise such as shadows as is shown in to extract only the written image area containing characters and figures written on the writing screen

The characters and figures that are written with a marker are in contact with the writing screen . Such characters and figures have clear outlines and internal portions with high density low gray scale value . On the other hand backgrounds areas and shadows have lower densities compared to the characters and figures so that the written characters and figures may be distinguished from the rest of the captured image data by performing a binarization process.

Generally a clipping process is performed upon removing a background area from a processing image and extracting a target image portion from the processing image. The clipping process involves dividing areas into two according formulae 1 and 2 described below where f x y denotes a color component density value and t denotes a threshold value when 1 0 when 2 In this process a background area and a written area containing written characters and figures are divided based on the threshold value t.

It is noted that thresholding methods such as the mode method the p tile method and the differential histogram method are known for determining a threshold value however the threshold value is maintained at a constant value according to such methods. In the present embodiment as is shown in since the manner in which shadows and noise occur in a captured image may vary depending on the movement of persons and objects at the time the image is captured a variable threshold value is used. Such a variable threshold value may be determined by a method involving scanning the pixels of the captured image data and varying the threshold value t for each target pixel. In this case an average density value of each local area of N N pixels including a target pixel and neighboring pixels may be determined as the threshold value t.

The background removal means handles nine pixels including a target pixel i j and neighboring pixels i j as a computation area divides a total value of green component G component density values g of the pixels by the number of pixels to calculate an average value g ave. That is an averaging filter according to the computation range i.e. 3 3 pixels in is used to calculate the average density value.

In this case the computation range for background removal on which the averaging filter is to be applied is adjusted based on the external light value detected by the external light value detecting unit . Specifically the number of pixels m filter size of one side of the computation range of m m pixels is determined according to the detected external light value.

In a preferred embodiment based on the external light value the computation range for background removal may be reduced in size when the background is bright i.e. when the external light value is greater than a predetermined threshold value and the computation range for background removal may be enlarged when the background is dark i.e. when the external light value is less than the predetermined threshold value . In one specific embodiment the pixel number m of one side of the m m pixels defining the computation range for background removal may be adjusted to be within a value range of 3 9 when the background is bright i.e. when the external light value is greater than a predetermined threshold value and the pixel number m of one side of the m m pixels may be adjusted to be within a value range of 5 15 when the background is dark i.e. when the external light value is less than the predetermined threshold value so that a suitable threshold value may be calculated for effectively removing a background area while leaving behind the lines of written characters and figures.

In the present embodiment the average value g ave calculated for the computation range of m m pixels for background removal that is adjusted based on the external light value detected by the external light detecting unit is used as the threshold value t in performing the clipping process as is described above.

It is noted that illustrates an example in which the density value of the green color component is referenced in performing background removal. However in certain cases written characters and figures may not be easily distinguished from a background area based on the average density values of the green color component depending on the marker used for example. Accordingly in a preferred embodiment an averaging filter is used for every color component of the RGB color components to calculate an average density value threshold value of each color in each computation range and the density value of a target pixel is compared with a corresponding threshold value for each color component to distinguish the written area with characters and figures from the background area based on the overall comparison results.

In the illustrated example of a background area is removed from the captured image data by the background removal means as is described above so that the information of characters and figures written with a marker may be extracted.

The shading correction unit has brightness correction means for planarizing a brightness gradient of the external light of the captured image data captured by the written image capturing unit .

Since external light incident on the screen is used to capture an image with the CCD camera there may be unevenness in the incident light caused by external light conditions depending on the usage environment of the image display apparatus.

In the illustrated blank image is brighter at the left side than the right side so that a brightness gradient is created within the captured blank image data. Due to such unevenness in the distribution of light in the image data the threshold value for extracting a written image area including written characters and figures may vary depending on the pixel positions within the captured image data.

Provided that a pixel line Y J extending along the X axis direction within the blank image shown in has a brightness gradient as is shown in the graph of when characters and figures are written on the writing screen under such an environment even when the same type of marker in the same color is used to write the characters and figures the brightness values of the written characters and figures within the captured image data may not be uniform. Specifically the characters and figures written in a brighter portion of the captured image data may be brighter than the characters and figures written in a darker portion of the captured image data as is shown in . That is the brightness values of the written lines of the characters and figures may vary depending on their positions within the captured image data and differences are created in the RGB values of the color components of these lines as is shown in the graph of see correction portion .

Accordingly in order to planarize the brightness gradient within the captured image data the brightness correction means performs brightness correction shading correction on the captured image data using the blank image shown in .

The brightness correction means performs planarization of the brightness gradient by dividing pixel values of captured image data including written characters and figures by corresponding pixel values of a blank image converting the pixel values of the captured image data into values representing a density level within a range of 0 255 256 levels and replacing the pixel values of the captured image data with the converted values.

It is noted that the blank image shown in that is captured beforehand by the image display apparatus according to the usage environment and the captured image data including the written characters and figures as is shown in have corresponding field angles so that a one on one correspondence is realized between coordinates i j of the blank image and coordinates i j of the captured image data. Provided that the pixel values of a given pixel of the captured image data are denoted as Rc Gc and Bc the pixel values of a corresponding pixel of the blank image with the same coordinates as the given pixel are denoted as Rn Gn and Bn and the number of density levels is denoted as D brightness corrected pixel values R G and B may be calculated from formulae 3 5 indicated below. 3 4 5 

In the brightness gradient characteristics within the captured image data are planarized by the brightness correction means so that the differences in brightness of the lines written in the same color may be corrected and the captured image data may be corrected and converted into image data having distinct color shades.

According to the present embodiment a high quality image as is shown in may be obtained that is free of external light influences from which a written image may be accurately extracted.

It is noted that the blank image used by the brightness correction means may be automatically captured by the image display apparatus upon its activation or the blank image may be captured at a given time by the image display apparatus user for example.

The shading correction unit has noise removal means for performing a clipping process on the brightness corrected image obtained by the brightness correction means to remove noise of the background image area corresponding to image portions of the corrected image other than the written image area including the written characters and figures.

It is noted that the background image area of the captured image data corresponding to image portions other than the written image area including the written characters and figures is removed by the background removal means as is described above and noise such as shadows are also removed by the background removal means .

However since the captured image data that is subject to background area removal by the background removal means may have an uneven light distribution caused by external light influences in some cases noise may still remain in the image data even after the removal process by the background removal means is performed.

Accordingly the noise removal means is used to remove noise that may be remaining in the brightness corrected image obtained by the brightness correction means .

The noise removal means performs a clipping process on a target pixel based on a noise removal threshold value that is set in accordance with external light conditions to remove noise within the background image area corresponding to image portions of the brightness corrected image other than the written image area including the written characters and figures in a manner similar to the clipping process performed by the background removal means .

The noise removal threshold value used in the clipping process by the noise removal means may be set based on the external light value detected by the external light value detecting unit namely the noise removal threshold value may be set high when the background is bright i.e. when the external light value is greater than a predetermined threshold value and the threshold value may be set low when the background is dark i.e. when the external light value is less than a predetermined threshold value . In one preferred embodiment the noise removal threshold value may be within a value range of 225 235 when the background is bright i.e. when the external light value is greater than a predetermined threshold value and the threshold value may be within a value range of 220 230 when the background is dark i.e. when the external light value is less than a predetermined threshold value .

The noise removal means performs a clipping process according to formulae 1 and 2 described above by comparing a pixel value of a target pixel with the corresponding noise removal threshold value and replacing the pixel value of the target pixel with the pixel value of a white pixel 255 255 255 when the pixel value of the target pixel is greater than the noise removal threshold value.

Also the shading correction unit has outline correcting means for performing outline correction on written lines of the characters and figures included in the noise removed image obtained by the noise removal means .

The outline correction means performs a smoothing process that involves detecting bumps or indentations in the pixel arrangement within the subject image data adding a pixel to fill in a detected indentation of one pixel and removing a pixel to remove a detected bump of one pixel for example.

As can be appreciated from the above descriptions in the present embodiment noise that has not been removed by the background removal means may be removed in the noise removal process performed on the brightness corrected image by the noise removal means . Then the outlines of the written characters and figures may be made more distinct by the outline correction process performed on the noise removed image by the outline correction means .

The color conversion unit has averaging means that uses an averaging filter to calculate an average density value of each color component RGB component for the pixels of the corrected image obtained by the shading correction unit i.e. corrected image resulting from performing brightness correction noise removal and outline correction on the captured image data . It is noted that the average density value calculation process performed by the averaging means may be similar to the average density value calculation process performed by the background removal means of the background removal unit .

Also the color conversion unit has color distinction means for distinguishing the color of the written lines of the characters and figures included in the averaging processed image obtained based on a relevant color distinction threshold value to thereby divide the image into a written image area including characters and figures and a background image area by dividing the image into a representative color image portion and a white portion for example.

In the present embodiment the color distinction threshold value may be set based on the external light value detected by the external light value detection means .

It is noted that image data of the writing screen may be captured using external light and the image display apparatus according to the present embodiment may normally be used in a conference for example where the lights in a room are turned on. In such a case the background area corresponding to the image portions other than the written image area including the written characters and figures of the captured image data captured by the written image capturing unit may be white or close to white so that the RGB values of color components of the background area may be relatively large.

Thus based on the relative relationship between the R G and B color components red blue and black color component information may be extracted and the remaining color components may be regarded as the background area. In this way information of written characters and figures may be extracted.

According to the illustrated example of in the color distinction process a pixel of the corrected image having RGB values satisfying the relationship R B G is identified as a red pixel and a pixel satisfying the relationship B G R is identified as a blue pixel. In this way information of characters and figures written with a red or blue marker may be extracted. Also according to the present example the three values representing the R G and B color components of a black pixel are all below a predetermined value so that a pixel having RGB values below a predetermined threshold value may be identified as a black pixel and characters. In this way information of characters and figures written with a black marker may be extracted. According to the present example information written with markers in three different colors may be identified and extracted.

Thus the color distinction means may distinguish a red writing a blue writing a black writing and a background based on corresponding color distinction threshold values.

The color distinction threshold values used in the color distinction process include a threshold value for distinguishing red a threshold value for distinguishing blue and a threshold value for distinguishing black that are determined based on the external light value detected by the external light detecting unit .

The threshold value for distinguishing blue may normally be within a value range of 150 190 under external light conditions in a normal usage environment for the image display apparatus. On the other hand the threshold value for distinguishing blue may be within a value range of 160 200 when the background of the processing image is relatively dark i.e. when the external light value is less than a predetermined threshold value .

The threshold value for distinguishing red may normally be within a value range of 180 200 under external light conditions of a normal usage environment for the image display apparatus.

The threshold value for distinguishing black is compared with a value representing the difference between the largest value and the smallest value of the three RGB color component values and may be set within a value range of 15 30 under normal external light conditions of a normal usage environment of the image display apparatus.

The color distinction means distinguishes the color of a target pixel based on the color distinction threshold values that are set according to variations in the external light conditions and converts the pixel value of the target pixel to RGB 255 0 0 in the case where the target pixel is identified as red RGB 0 0 255 in the case where the target pixel is identified as blue and RGB 0 0 0 in the case where the target pixel is identified as black for example.

Also the color conversion unit has color distinction correction means for calculating a rate at which the pixel values of predetermined pixels including a target pixel and its neighboring pixels represent black in a corrected image processed by the shading correction unit and replacing converting the pixel value of the target pixel with a pixel value of black 0 0 0 or a pixel value obtained from the color conversion process by the color distinction means based on the calculated rate and reflecting the color conversion in the corrected image.

The rate at which the pixel values represent black may be calculated by counting the number of pixels having a pixel value other than white 255 255 255 and the number of pixels having the pixel value of black 0 0 0 of the predetermined pixels including the target pixel and its neighboring pixels and obtaining a ratio between the counted numbers to thereby calculate the rate at which neighboring pixels of the target pixel having pixel values other than white have the pixel value of black.

As is shown in in the present embodiment color conversion may be performed on the lines of written characters and figures without receiving influence of external light conditions and distinct lines may be obtained for enabling accurate extraction of a written image for example.

As is shown in this drawing the size of the captured image data captured by the written image capturing unit corresponds to the image size of the CCD camera and the minimal area extracting unit extracts a minimal area containing the written characters and figures.

For example in a corrected image obtained by the correction processes performed by the shading correction unit and the color conversion unit pixels other than those corresponding to the written characters and figures are converted into white pixels. In such a case raster scanning may be performed in a downward direction from an upper left hand side of the corrected image to determine a position x at which a pixel in a color other than white is first identified raster scanning may be performed in a downward direction from the upper right hand side of the corrected image to determine a position x at which a pixel in a color other than white is first identified raster scanning in the rightward direction may be performed from the upper left hand side of the corrected image to determine a position y at which a pixel in a color other than white is first identified and raster scanning may be performed in the rightward direction from the lower left hand side of the corrected image to determine a position y at which a pixel in a color other than white is first identified.

By extracting a rectangular area with the coordinate positions x y and x y as the upper left hand side apex and the lower right hand side apex a written area may be extracted according to the positions at which characters and figures are written within the writing screen for example.

It is noted that such a written image may subsequently be composited with a projection image generated by the projection image generating unit by the image compositing unit .

According to an aspect of the present embodiment image processes performed at an image display apparatus for extracting a written image may be controlled according to an external light detection value which may vary depending on the usage environment of the image display apparatus.

Thus a written image may be accurately extracted without being influenced by external light conditions that may vary depending on the usage environment of the image display apparatus and information of written characters and figures may be converted into electronic information.

In the following process steps performed by the units of the written image area extracting unit are described with reference to .

The external light value detection unit uses the external light value detection means to calculate the brightness distribution e.g. brightness distribution of the G component of the RGB color components as is shown in based on the blank image that is captured beforehand by the written image capturing unit . Then based on the calculated brightness distribution the external light value detection means detects the peak brightness corresponding to the most frequently occurring brightness value as the external light value.

In the following process steps are described for controlling the computation processes performed by the functional units of the image processing unit based on the external light value detected by the external light value detection unit .

The written image area extracting unit uses the external light value detection means of the external light value detection unit to detect the external light value representing the external light conditions under the current usage environment of the image display apparatus based on the brightness distribution of the blank image captured beforehand by the written image capturing unit S .

Then based on the detected external light value the background removal means of the background removal unit of the image processing unit sets a computation range on which an averaging filter for background removal is to be applied S .

Then based on the detected external value the noise removal means of the shading correction unit of the image processing unit sets a noise removal threshold value based on which a noise removal process is to be performed S .

Then based on the detected external value the color distinction means of the color conversion unit of the image processing unit sets a color distinction threshold value based on which a color distinction process is to be performed S .

Then the background removal means of the background removal unit performs the background removal process using the set computation range for background removal S .

Then the noise removal means of the shading correction unit performs the noise removal process based on the set noise removal threshold value S .

Then the color distinction means of the color conversion unit performs the color distinction process based on the set color distinction threshold value S .

As can be appreciated from the above descriptions the computation processes performed by the functional units of the image processing unit e.g. background removal unit shading correction unit and color conversion unit may be controlled based on the external light value detected by the external light detection means of the external light detection unit .

According to the external light detection means secures a memory area hist 256 for storing information on the occurrence count numbers of brightness values of the brightness distribution and initializes the secured memory area hist 256 0 . . . 0 S .

Then the external light detection means starts pixel scanning in raster order and obtains a G value g i j representing the G component density value of a scanned pixel of a blank image S . It is noted that since a G component brightness value may be no different from a Y component value that is calculated by performing color conversion using the G component value and an RGB value G component values of pixels are used in the present example in order to reduce the processing speed.

Based on the obtained G value g i j the external light detection means counts up the occurrence number of a corresponding brightness value hist g i j within the brightness distribution hist S and moves on to pixel scanning of a next pixel S .

During the pixel scanning process a determination is made as to whether a currently scanned pixel corresponds to a last pixel for pixel scanning according to the raster order S and this determination step is repeated S No until the last pixel is scanned.

When it is determined that the currently scanned pixel corresponds to the last pixel S Yes a variable peak kido for holding the most frequently occurring brightness value peak brightness value within the brightness distribution and a variable cnt for holding the greatest occurrence number are initialized peak kido 0 cnt 0 S .

Then an occurrence number hist kido of a given brightness value kido within the brightness distribution is searched and a determination is made as to whether the occurrence number hist kido of the given brightness value kido is the greatest occurrence number so far S .

If the occurrence number hist kido of the given brightness value kido is presently the greatest occurrence number S Yes the value of the variable peak kido for holding the most frequently occurring brightness value is substituted by the given brightness value peak kido kido and the variable for holding the greatest occurrence number cnt is substituted by the occurrence number hist kido of the given brightness value cnt hist kido S .

Then the process moves on to searching and obtaining the occurrence number of a next brightness value kido S .

On the other hand if the occurrence number hist kido obtained for the given brightness value kido is less than the currently set greatest occurrence number hist kido 

In moving on to the next brightness value a determination is made as to whether this next brightness value to be searched corresponds to the last brightness value within the density level range of the brightness distribution S and the searching of a brightness value is repeated S Yes until reaching the last brightness value.

The present process is ended when searching of the last brightness value within the density level range is complete S No .

In this case the last substituted brightness value kido that is substituted as the variable peak kido for holding the most frequently occurring brightness value within the brightness distribution range at this point corresponds to the peak brightness value to be used as the external light value for controlling subsequent computation processes of the image processing unit .

The background removal unit uses the background removal means to set the computation range for background removal on which the averaging filter is to be applied based on the external light value detected by the external light value detection means of the external light value detecting unit . Specifically the background removal means determines the number of pixels m arranged along one side of a computation range of m m pixels.

In one example the computation range for background removal may be set based on the external light value in the manner described below. The computation range for background removal may be arranged to be relatively small e.g. the number of pixels arranged on one side of the computation range may be set to m 3 as is shown in when the background is relatively bright e.g. when the external light value is above a predetermined threshold value and the computation range for background removal may be arranged to be relatively large the number of pixels arranged on one side of the computation range may be set to m 5 as is shown in when the background is relatively dark e.g. when the external light value is below a predetermined threshold value . In one aspect the computation range for background removal is preferably set within a suitable range for enabling calculation of a color component threshold value for accurately removing a background area while leaving behind the line images of written characters and figures and when the background is bright when the external light value is above a predetermined threshold value the number of pixels arranged along one side of the computation range may be reduced compared to the number of pixels set for the computation range when the background is dark when the external light value is below a predetermined threshold value .

As is shown in average density values r ave g ave and b ave are calculated using corresponding averaging filters for R G and B color components from the computation range of m m pixels for background removal that is set based on the external light value detected by the external light detection unit and the calculated average density values r ave g ave and b ave are used as threshold values upon performing a clipping process.

Thus when the density value r of a target pixel i j is greater than the threshold value r ave r r ave the density value g of the target pixel i j is greater than the threshold value g ave and the density value b of the target pixel i j is greater than the threshold value b ave the background removal means determines that the target pixel i j belongs to a background shadow or noise area and replaces the pixel value of the target pixel i j with that of a white pixel 255 255 255 . In the present example the background removal means calculates the average density values of all color components of the RGB components using corresponding averaging filters in consideration of the fact that in some cases characters and figures written by markers may not easily be identified based on their green color component values for example. Then the background removal means compares color density values of a target pixel with corresponding color component threshold values to determine a background area and an area in which characters and figures are written based on the overall comparison results.

According to the background removal means of the background removal unit acquires the external light value peak brightness peak kido detected by the external light detection means of the external light detection unit S .

Then the background removal means determines whether the acquired external light value peak kido is greater than a predetermined threshold value th bg S .

If the external light value is greater than the predetermined threshold value S Yes the number of pixels m on one side of the computation range of m m pixels for the averaging filter is set to be within a value range of 3 9 filtsize for setting the size of the computation range to a small size m filtsize S .

On the other hand if the external light value is less than or equal to the predetermined threshold value S No the number of pixels m of one side of the computation range of m m pixels for the averaging filter is set to be within a value range of 5 15 filtsize for setting the computation range to a large size m filtsize S .

It is noted that in this case the values of filtsize and filtsize satisfy the following relationship filtsize

In this way the background removal means of the background removal unit may set a suitable value for the number of pixels m of a side of the computational range of m m pixels on which an averaging filter is to be applied based on the external light value detected by the external light detection means of the external light detection unit so that background removal may be adequately performed in consideration of variations in external light conditions.

As can be appreciated by comparing in the image data obtained by performing background removal according to the present invention the written line images of the written characters and figures are clearer compared to the image data obtained by performing background removal according to the conventional art. It can also be appreciated that more noise remains in the image data of compared to the image data of . Accordingly in the present embodiment noise is removed from the image data of by the noise removal means of the shading correction unit as is described below.

According to the shading correction unit of the image processing unit uses the brightness correction means to perform brightness correction by dividing a pixel value of a pixel within captured image data of a written image by a pixel value of a corresponding pixel within a blank image and converting the pixel value of the pixel within the captured image data into a density level e.g. within a value range of 0 255 for indicating 256 different brightness levels that is represented by the pixel S .

Then the noise removal means removes noise from a background area corresponding to an image area other than the written image area containing written characters and figures of the brightness corrected image by performing a clipping process on a target pixel based on the noise removal threshold value that is set according to external light conditions S .

Then the outline correction means performs a smoothing process for correcting the outlines of the written characters and figures by detecting bumps and indentations in the arrangement of pixels within the noise removed image data and adding removing a pixel in accordance with the detected indentations and bumps. Specifically if an indentation of one pixel is detected a pixel may be added to fill such an indentation and if a bump of one pixel is detected the corresponding pixel may be removed for example S .

As can be appreciated from the above descriptions the shading correction unit may perform brightness correction using the brightness correction means to planarize the brightness gradient characteristics of a captured image. Also the shading correction unit may use the noise removal means to perform noise removal on the brightness corrected image to remove noise that has not been removed by the background removal process performed by the background removal means . Further the shading correction unit may use the outline correction means to perform outline correction on the noise removed image to make the outlines of the written characters and figures more distinct.

According to the noise removal means of the shading correction unit acquires the external light value peak brightness peak kido detected by the external light detection means of the external light detection unit S .

Then the noise removal means determines whether the acquired external light value is greater than a predetermined threshold value th sh S .

If the external light value is greater than the predetermined threshold value th sh S Yes the noise removal threshold value th shade is set to a relatively large value within a range of 225 235 th shade S .

On the other hand if the external light value is less than the predetermined threshold value th sh S No the noise removal threshold value th shade is set to a relatively small value within a range of 220 230 th shade S .

It is noted that in the present example the threshold values th shade and th shade are arranged to satisfy the following relationship th shade th shade.

By implementing the process steps according to the present example the noise removal means of the shading correction unit may set the noise removal threshold value to a suitable value based on the external light value detected by the external light value detection means of the external light value detection unit to adequately perform noise removal in accordance with variations in external light conditions for example.

As is shown in when a target pixel of a noise removed image is white 255 255 255 while the adjacent pixels on the right side and left side of the target pixel are not white or when the target pixel is white while the upper and lower adjacent pixels of the target pixel are not white the outline correction means of the shading correction unit determines that the target pixel corresponds to an indentation of a written line of a written character or figure and replaces the value of the target pixel with the average density value of its adjacent pixels to correct the outline of the written line.

As is shown in when a target pixel of a noise removed image is not white while the adjacent pixels on the right side and left side of the target pixel are white if the upper side the upper right side and the upper left side of the target pixel are not white while the lower side of the target pixel is white or if the lower side lower right side and the lower left side of the target pixel is not white while the upper side of the target pixel is white the outline correction means of the shading correction unit determines that the target pixel corresponds to a bump on a written line of a written character or figure and replaces the value of the target pixel with the average density value of the left and right adjacent pixels of the target pixel to correct the outline of the written line image.

Also when the target pixel is not white while both the upper and lower adjacent pixels of the target pixel are white if the right side the upper right side and the lower right side of the target pixel are not white while the left side of the target pixel is white or if the left side the upper left side and the lower left side of the target pixel is not white while the right side of the target pixel is white the outline correction means of the shading correction unit determines that the target pixel corresponds to a bump on a written line of a written character or figure and replaces the value of the target pixel with the average density value of its upper and lower adjacent pixels to correct the outline of the written line.

As is described above in the example of after determining that a target pixel may possibly correspond to a bump bump candidate of a written line by referring to its adjacent pixels a determination is made as to whether pixels at the opposite side of the outline of the written line are white in order to avoid formation of a crack as is described in where a target pixel corresponding to a pixel of a written line with a line width of one pixel is mistakenly assumed to be a bump and replaced with a white pixel.

As can be appreciated from these drawings in the image data of obtained through image correction according to an embodiment of the present invention discontinuities and roughened portions of written lines are reduced compared to the image data of obtained through image correction according to the prior art. Also according to an embodiment of the present invention noise still remaining in the image data even after background removal is performed by the background removal means of the background removal unit may be removed by the noise removal means of the shading correction unit . In this way a high quality image as is shown in that is not influenced by external light conditions may be obtained for extracting a written image.

The averaging means of the color conversion unit acquires the corrected image pImage that is corrected by the shading correction unit S and secures a memory area for storing an averaged image filtimg S .

Then the averaging means copies the acquired corrected image pImage onto the memory area for the averaged image filtimg filtimg pImage S .

Then the averaging means starts pixel scanning of the corrected image pImage to determine whether a currently scanned target pixel corresponds to a white pixel S .

When the currently scanned target pixel is not white S No a counter totalcount is initialized for counting the number of color pixels other than white pixels within a computation range including pixels surrounding the target pixel on which an averaging filter is to be applied totalcount 0 S and a determination is made as to whether a given pixel of the corrected image pImage within the computation range is a white pixel S .

On the other hand when the currently scanned target pixel is white S Yes the subsequent process steps S S are not performed and the process moves on to step S.

When a given pixel within the computation range is not white S No the pixel is determined to be a color pixel other than a white pixel the counter is counted up totalcount and the pixel value of the pixel is added to the pixel value of the computation range filtimg pImage S .

On the other hand if a pixel within the computation range is a white pixel S Yes the process step S is not performed with respect to this pixel and the process moves on to step S.

Then a determination is made as to whether the determination process for determining whether a pixel is white has been performed on all the neighboring pixels of the target pixel within the computation range on which the averaging filter is to be applied S .

If the white non white pixel determination process has been performed on all the neighboring pixels within the computation range S Yes the total pixel value of the color pixels other than white pixels within the computation range is divided by the total number of color pixels other than white pixels to obtain an average pixel value of the color pixels filtimg totalcount S .

On the other hand if the white non white pixel determination process is not yet completed for all the pixels within the computation range S No the process moves on to a next pixel subject to computation within the computation range S .

After performing the averaging process the pixel scanning position is returned to the position of the currently scanned target pixel current position S .

Then a determination is made as to whether the current position corresponds to a last pixel subject to pixel scanning of the corrected image pImage S .

If the current position is not the last pixel subject to pixel scanning within the corrected image pImage S No the current position is moved to a next pixel position within the corrected image pImage according to the pixel scanning order raster order S .

If the current position corresponds to the last pixel subject to pixel scanning within the corrected image pImage S Yes the present process is ended.

According to the color distinction means of the color conversion unit acquires the external light value peak brightness peak kido detected by the external light value detection means of the external light detection unit S .

Then the color distinction means first determines whether a written line is red based on the acquired external light value and a red color distinction threshold value th red that is not influenced by the external light value peak kido th red S .

If the external light value is greater than the red color distinction threshold value S Yes a flag flag red for indicating that the written line is red is turned on flag red 1 S .

If the external light value is less than the red color distinction threshold value S No the flag flag red for indicating that the written line is red is turned off flag red 0 S .

Then the color distinction means determines whether a written line is blue based on the external light value and a blue color distinction threshold value th blue that is not influenced by the external light value peak kido

If the external light value is less than the blue color distinction threshold value S Yes a flag flag blue for indicating that the written line is blue is turned on flag blue 1 S .

If the external light value is greater than the blue color distinction threshold value S No the flag flag blue for indicating that the written line is blue is turned off flag blue 0 S .

In this way the color distinction means of the color conversion unit may use flags to indicate whether a written line is red blue or a color other than red and blue based on the external light value detected by the external light value detection means of the external light value detection unit and temporarily store such information for use in distinguishing the color of the written line.

According to the color distinction means of the color conversion unit acquires the averaged image filtimg resulting from the averaging process performed by the averaging means S and secures a memory area for a color distinguished image tmpimg S .

Then the color distinction means copies the averaged image filtimg on the memory area for the color distinguished image tmpimg tmpimg filtimg S .

Then the color distinction means starts pixel scanning of the averaged image filtimg to detect the maximum brightness value maxrgb of the color components of the averaged image filtimg and the corresponding color maxcol with the maximum brightness value S and the minimum brightness value minrgb of the color components of the averaged image filtimg and the corresponding color mincol with the minimum brightness value S .

Then the color distinction means subtracts the minimum brightness value minrgb from the maximum brightness value maxrgb to obtain a difference value diffrgb diffrgb maxrgb minrgb S 

Then the color distinction means starts pixel scanning of the color distinguished image tmpimg to determine whether a target pixel that is currently scanned corresponds to a white pixel S .

When it is determined that a target pixel is not white a determination is made as to whether the target pixel is blue S .

When it is determined that the target pixel is white the process steps S S are omitted and the process moves on to step S.

When it is determined that the target pixel is blue S Yes the pixel value of the target pixel is replaced with the pixel value of a blue pixel 0 0 255 S .

When it is determined that the target pixel is not blue S No a determination is made as to whether the target pixel is red S .

When it is determined that the target pixel is red S Yes the pixel value of the target pixel is replaced with the pixel value of a red pixel 255 0 0 S .

When it is determined that the target pixel is not red a determination is made as to whether the target pixel is black S .

When it is determined that the target pixel is black S Yes the pixel value of the target pixel is replaced with the pixel value of a black pixel 0 0 0 S .

When it is determined that the target pixel is not black the target pixel is determined to be in a non distinguishable color i.e. a color other than the representative colors red blue and black and the background color white and the pixel value of the target pixel is corrected accordingly in the color distinguished image tmpimg tmpimg filtimg 1.5 S .

Then a determination is made as to whether the current position of a target pixel corresponds to a last pixel within the color distinguished image tmpimg S .

If the current position is not the last pixel within the color distinguished image tmpimg S No the current position is moved to a next pixel position within the color distinguished image tmpimg and the averaged image filtimg according to the pixel scanning order raster order S .

If the current position is located at the last pixel of the color distinguished image tmpimg S Yes the present process is ended.

According to upon performing the white color distinction process step S of the color distinction means of the color conversion unit acquires the pixel value of the target pixel of the color distinguished image tmpimg S obtains the total sum r g b of the r value g value and b value of the color components of the target pixel and determines whether the total sum is greater than a value equal to three times a predetermined threshold value th sh S .

If the total sum of the RGB values of the color components is greater than the tripled value of the predetermined threshold value th sh S Yes it is determined that the target pixel is white and the pixel value of the target pixel is color converted into the pixel value of a white pixel 255 255 255 S .

If the total sum of the RGB values of the color components is less than or equal to the tripled value of the predetermined threshold value th sh S No color conversion of the target pixel is not performed.

According to upon performing the blue color distinction process step S of the color distinction means of the color conversion unit acquires the pixel value of the target pixel of the color distinguished image tmpimg S and determines whether the color with the maximum density value maxcol of the color components of the target pixel corresponds to blue whether the color with the minimum density value mincol of the color components of the target pixel corresponds to red and whether the B component of the b value of the target pixel is greater than a blue color distinction threshold value th blue for determining that the target pixel is blue regardless of the external light value S .

If positive determinations are made in step S the target pixel is determined to be a blue pixel and the pixel value of the target pixel is color converted into the pixel value of a blue pixel 0 0 255 S .

If one or more negative determinations are made in step S it is determined whether the flag indicating that the target pixel has been distinguished as a blue pixel based on the external light value flag blue is turned on whether the color with the minimum density value mincol corresponds to red and whether the b value of the B component of the target pixel is greater than a blue color distinction threshold value th blue for a case in which the external light value is low S .

If positive determinations are made in step S the target pixel is distinguished as blue pixel and the pixel value of the target pixel is color converted into the pixel value of a blue pixel 0 0 255 S .

If one or more negative determinations are made in step S color conversion of the target pixel is not performed.

In one preferred embodiment the threshold value th blue is set to be within a value range of 150 190 and the threshold value th blue is set to be within a value range of 160 200 and the values of the two threshold values are set to satisfy the following relationship th blue

According to upon performing the red color distinction process step S of the color distinction means of the color conversion unit acquires the pixel value of the target pixel of the color distinguished image tmpimg S and determines whether the color with the maximum density value maxcol corresponds to red and whether the r value of the R component of the target pixel is greater than a red color distinction threshold value for determining that a pixel is red regardless of external light influences S .

If positive determinations are made in step S the target pixel is distinguished as a red pixel and the pixel value of the target pixel is color converted to the pixel value of a red pixel 255 0 0 S .

In one preferred embodiment the red color distinction threshold value th red is set to be within a value range of 180 200 under normal external light conditions.

According to upon performing the black color distinction process step S of the color distinction means of the color conversion unit acquires the pixel value of the target pixel of the color distinguished image tmpimg and determines whether the color with the maximum density value maxcol of the color components of the target pixel corresponds to green and whether the color with the minimum color density value mincol corresponds to blue S .

If positive determinations are made in step S the target pixel is distinguished as a black pixel and the pixel value of the target pixel is color converted to the pixel value of a black pixel 0 0 0 .

If a negative determination is made in step S it is determined whether the difference value diffrgb obtained by subtracting the minimum density value minrgb from the maximum density value maxrgb of the RGB values of the color components is less than a black color distinction threshold value th black for determining a pixel to be black regardless of external light influences S .

If positive determinations are made in step S the target pixel is distinguished as a black pixel and the pixel value of the target pixel is color converted into the pixel value of a black pixel 0 0 0 S .

In one preferred embodiment the black color distinction threshold value th black is set to be within a value range of 15 30.

As can be appreciated from the above descriptions the color distinction means of the color conversion unit may set color distinction threshold values for distinguishing the color white of the background and typical colors of markers including red blue and black for example based on the external light value detected by the external light detection means of the external light detection unit so that optimal color distinction processes may be performed according to variations in the external light conditions.

According to the color distinction correction means of the color conversion unit acquires the corrected image pImage that is obtained by the shading correction unit S and the color distinguished image tmpimg S .

Then the color distinction correction means starts pixel scanning of the color distinguished image tmpimg and determines whether a target pixel that is currently scanned corresponds to a blue pixel or a red pixel S .

If the target pixel is distinguished as blue or red S Yes the counter totalcount for counting the number of neighboring pixels other than white pixels of the target pixel that are within the correction computation range subject to an averaging process and the counter count for counting the number of black pixels of the above counted pixels are initialized totalcount 0 count 0 S .

If the target pixel is neither blue nor red S No the pixel value of a pixel of the corrected image pImage located at the same coordinate position as the current scanning position according to the pixel scanning order is replaced with the pixel value of the target pixel located this current scanning position S .

If the target pixel is not white S No the counter totalcount for counting the number of neighboring pixels other than white pixels is counted up totalcount S .

In step S a determination is made as to whether the target pixel that is currently scanned corresponds to a black pixel.

If the target pixel is black S Yes the counter count for counting the number of black pixels is counted up count S .

In step S a determination is made as to whether the color distinction correction process has been performed on all pixels of the color distinguished image tmpimg within a corresponding correction range.

When it is determined that the color distinction correction process has been performed on all pixels within the correction range S Yes the number of black pixels count within the correction range is divided by the number of pixels other than white totalcount to obtain the occurrence rate rate of the black pixel with respect to the color pixels other than white pixels S .

If it is determined that the color distinction correction process has not yet been completed for all the pixels within the correction range S No the current position is moved to the position of a next pixel subject to the color distinction correction process S .

Then a determination is made as to whether the occurrence rate of the black pixel is greater than a predetermined threshold value e.g. 0.2 in the present example S .

If the calculated black pixel occurrence rate rate is greater than the predetermined value 0.2 S Yes the pixel value of a pixel of the corrected image pImage located at the same coordinate position as the current scanning position of the color distinguished image tmpimg according to the pixel scanning order raster order is replaced with the pixel value of a black pixel 0 0 0 S .

If the calculated rate rate is less than or equal to the predetermined value 0.2 S No the pixel value of a pixel of the corrected image pImage located at the same coordinates position as the current scanning position according to the pixel scanning order raster order is replaced with the pixel value of the target pixel located at the current scanning position of the color distinguished image tmpimg S .

After the color distinction correction process the pixel scanning position is returned to the current position on of the color distinguished image tmpimg that is currently being scanned S .

Then a determination is made as to whether the current position of the target pixel corresponds to the last pixel for pixel scanning of the color distinguished image tmpimg S .

If the current position does not correspond to the last pixel of the color distinguished image tmpimg for pixel scanning S No the current position is moved to a next pixel position within the color distinguished image tmpimg according to the pixel scanning order raster order S .

If the current position corresponds to the last pixel of the color distinguished image tmpimg for pixel scanning S Yes the process is ended.

As can be appreciated from the above descriptions the color distinction correction means of the color conversion unit may accurately correct pixels of the color distinguished image tmpimg that have a high likelihood of being erroneously distinguished by the color distinction means .

In this way color conversion may be accurately performed on written lines of characters and figures without being influenced by external light conditions so that distinct lines may be obtained for accurately extracting a written image.

It is noted that in one preferred embodiment the above described process steps may be realized by a program that is stored in a computer readable medium.

As can be appreciated from the above descriptions an image display apparatus according to the first embodiment of the present invention is adapted to control computation processes of the image processing unit upon extracting a written image from captured image data captured by the written image capturing unit using the written image area extracting unit based on an external light value detected by the external light detection means of the external light value detection unit .

In this way the image display apparatus according to the present embodiment may accurately perform image correction on the captured image data according to variations in the external light conditions depending on the usage environment of the image display apparatus so that a high quality written image may be extracted.

Also in the image display apparatus according to the first embodiment the background removal means of the image processing unit performs an averaging process for each color component within a predetermined computation range including a target pixel and its neighboring pixels determines that the target pixel corresponds to a background pixel when the averaged brightness value of the target pixel is greater than a predetermined background removal threshold value and replaces the pixel value of the target pixel with the pixel value of a white pixel. In this case the background removal means is adapted to adjust enlarge or reduce the computation range for the averaging process to an optimal range based on the external light value detected by the external light detection means of the external light detection unit .

In this way the image display apparatus according to the present embodiment may perform a background removal process on captured image data according to variations in external light conditions so that accuracy may be improved in determining the image background and the written image area with written characters and figures.

Also in the image display apparatus according to the first embodiment the noise removal means of the image processing unit removes noise from an image that is corrected by the brightness correction means through planarizing an uneven distribution of light caused by external light conditions brightness gradient based on a predetermined noise removal threshold value. In this case the noise removal means adjusts the predetermined noise removal threshold value based on the external light value detected by the external light value detection means of the external light value detection unit .

In this way the image display apparatus according to the present embodiment may perform noise removal on captured image data according to variations in external light conditions so that a high quality corrected image may be obtained without being influenced by external light conditions.

Also in the image display apparatus according to the first embodiment the color distinction means of the color conversion unit of the image processing unit performs a color distinction process on pixel values of an image corrected by the shading correction unit based on a predetermined color distinction threshold value to distinguish the color of written lines of written characters and figures included in the image. In this case the color distinction means adjusts the predetermined color distinction threshold value based on the external light value detected by the external light value detection means of the external light value detection unit .

In this way the image display apparatus according to the present embodiment may perform accurate color distinction without being influenced by external light conditions.

It is noted that show image data of lines written on the writing screen of the image display apparatus of the first embodiment using a marker with a width of approximately 1 mm for example in which case color distinction of the written lines may be rather difficult.

As can be appreciated from these drawings the image correction scheme according to the present embodiment that takes external light conditions into account enables extraction of a higher quality written image compared to the case of using the conventional image correction scheme. Specifically by implementing the image correction scheme according to the present embodiment a written image may be stably extracted from captured image data even when the written image includes fine lines of which color may be difficult to distinguish and even when external light conditions may vary depending on the usage environment of the image display apparatus for example.

In this way an image display apparatus according to the first embodiment of the present invention may accurately extract a written image from captured image data without being influenced by external light conditions to thereby obtain high grade electronic information of written characters and figures of the written image.

In the following a second embodiment of the present invention is described that involves removing an isolated dot surrounded by white pixels of the background that has not been removed by image correction processes such as the background removal process of the first embodiment to further improve the image quality of the extracted written image.

It is noted that aside from having the additional function of removing an isolated dot the second embodiment is substantially identical to the first embodiment. Thus hardware components functional elements and process steps of the second embodiment that are identical to those of the first embodiment are given the same numerical references and their descriptions may be omitted.

As is shown in this drawing the isolated dot removing function of the second embodiment is realized by isolated dot removal means of a color conversion unit of an image processing unit included in the written image area extracting unit of the second embodiment.

The isolated dot removal means inputs an image corrected by the color distinction correction means and performs pixel scanning on the input image to determine whether each target pixel corresponds to an isolated dot and replace the pixel value of the target pixel that is determined to be an isolated dot with the pixel value of a white pixel.

The isolated dot removal means is provided in view of the fact that an isolated dot that is relatively inconspicuous in an image obtained from image correction by a shading correction unit of the written image extracting unit may subsequently become conspicuous after performing image correction by the color conversion unit and such a conspicuous isolated dot is preferably removed in order to extract a high quality written image.

According to the example of the isolated dot removal means performs pixel scanning on an input image and determines whether a target pixel is a color pixel other than a white pixel. Upon determining that the target pixel is a color pixel other than a white pixel the isolated dot removal means refers to surrounding pixels of the target pixel pixel area defined by hatched lines in . If all the pixels surrounding the target pixel have pixel values of white pixels the target pixel is determined to be an isolated dot and the pixel value of the target pixel is replaced with the pixel value of a white pixel 255 255 255 .

In this way the isolated dot removal means performs image correction on a color distinguished image to determine whether all surrounding pixels of a target pixel are white and replace the pixel value of the target pixel with the pixel value of a white pixel depending on the determination result so that an isolated dot that has become conspicuous as a result of performing a color distinction process may be removed.

As can be appreciated from the above descriptions in the image display apparatus according to the second embodiment of the present invention an isolated dot that has become conspicuous as a result of performing a color distinction process may be removed by the isolated dot removal means so that a high quality written image may be extracted.

In the following exemplary advantages realized by embodiments of the present invention are described.

According to one aspect of the present invention image processes performed in an image display apparatus for extracting a written image may be controlled according to an external light detection value that may vary depending on the usage environment of the image display apparatus. By taking the external light detection value into account in controlling the image processes a written image may be accurately extracted regardless of external light conditions for example.

According to another aspect of the present invention in a background removal process involving averaging each color component of pixels within a predetermined range computation range for averaging of a captured image to obtain an averaged pixel value brightness value of a target pixel determining whether the averaged pixel value is greater than a background removal threshold value distinguishing the target pixel as a background pixel the pixel value of the target pixel is greater than the background threshold value and replacing the pixel value of the target pixel with a white pixel value by adjustably setting reducing or enlarging the predetermined range computation range for averaging based on the detected external light value the background removal process may be performed on the captured image taking into account variations in the external light conditions. By performing a background removal process according to external light conditions in the manner described above accuracy may be improved in distinguishing a background from written characters and figures for example.

According to another aspect of the present invention in a noise removal process for removing noise from a brightness corrected image based on a noise removal threshold value by adjustably setting the noise removal threshold value according to the detected external light value the noise removal process may be performed taking into account variations in the external light conditions. By controlling image processes according to variations in the external light in the manner described above a high quality corrected image may be obtained without being influenced by external light conditions for example.

According to another aspect of the present invention in a color distinction process for distinguishing the color of a written line by comparing the pixel values of a corrected image with relevant color distinction threshold values by adjustably setting the color distinction threshold values according to the detected external light value accurate color distinction of the written line may be performed without being influenced by external light conditions for example.

According to another aspect of the present invention by controlling image processes for extracting a written image according to the detected external light value a written image may be accurately extracted without being influenced by external light conditions so that high grade electronic information of written characters and figures of the written image may be obtained for example.

Although the present invention is shown and described with respect to certain preferred embodiments it is obvious that equivalents and modifications may occur to others skilled in the art upon reading and understanding the specification. The present invention includes all such equivalents and modifications and is limited only by the scope of the claims.

For example the hardware configuration of an image display apparatus according to an embodiment of the present invention is not limited to that illustrated in and other hardware configurations are possible such as that shown in where the screen is positioned vertically.

Also the functional configuration of an image display apparatus according to an embodiment of the present invention is not limited to those illustrated in and and in other examples the functional elements may be combined in a different manner or combined with other additional elements.

Further it is noted that the functional elements of the image display apparatus according to an embodiment of the present invention may comprise hardware software or combinations thereof. When one or more of the functional elements comprise software in the form of computer readable program code for example they may be embodied in any computer readable medium for carrying or having computer executable instructions or data structures stored thereon. By way of example and not limitation such computer readable medium may be a physical medium such as a RAM a ROM an EEPROM a CD ROM or some other type of storage device or any other medium which can be accessed by a computer and used to carry or store desired program code means in the form of computer executable instructions or data structures.

Also it is noted that the thresholding method used by the background removal unit for adjustably setting the variable background removal threshold value that involves calculating the average density value of a target pixel and its neighboring pixels within a predetermined computation range is merely one illustrative method for calculating the variable threshold value and the present invention is not limited to such a method.

Specifically in certain alternative examples the present invention may use other thresholding methods such as the mode method the p tile method and the differential histogram method to calculate a background removal threshold value for a computation range of neighboring pixels surrounding a target pixel. Also it is noted that since an enormous amount of computation capacity is needed to actually perform the above described threshold calculation processes on all the pixels of a processing image and the processing speed may be sacrificed as a result in a preferred embodiment the threshold calculation process may be performed on representative pixels while the threshold values for the other pixels may be obtained through interpolation for example.

Also in the above described embodiment a pixel is arranged to have a pixel value range brightness value range of 256 levels in which case a pixel may represent 256 different density levels. However the present invention is not limited to such an arrangement and in other alternative examples a pixel value may be represented by 7 bits to realize a pixel value range brightness value range of 128 levels or a pixel value may be represented by 9 bits to realize a pixel value range brightness value range of 512 levels.

Also in the above described embodiment of the present invention the external light detection means determines the most frequently occurring brightness value based on the brightness distribution characteristics of the G component of the RGB components in calculating the external light value. However the present invention is not limited to using such a calculation method for obtaining the external light value.

For example the Y component may be calculated from the RGB component and the most frequently occurring brightness value based on the Y component distribution characteristics may be determined as the external light value. However since the G component brightness distribution characteristics is substantially identical to the Y component distribution characteristics the G component brightness distribution characteristics may preferably be referred to in determining the external light value in consideration of the processing speed for example.

Further it is noted that the present invention is not limited to the illustrated structures of the above described embodiments and various modified structures such as combinations with other elements are also possible.

That is the present invention may be adapted for a variety of applications and modifications may be made accordingly within the scope of the present invention.

The present application is based on and claims the benefit of the earlier filing date of Japanese Patent Application No. 2006 209264 filed on Jul. 31 2006 the entire contents of which are hereby incorporated by reference.

