---

title: Makeup simulation system, makeup simulator, makeup simulation method, and makeup simulation program
abstract: According to the present invention, a makeup simulation system applying makeup to a video having an image of the face of a user captured thereon is characterized by image capturing means for capturing the image of the face of the user and outputting the video, control means for receiving the video output from the image capturing means, performing image processing on the video, and outputting the video; and display means for displaying the video output from the control means, wherein the control means includes face recognition means for recognizing the face of the user from the video based on predetermined tracking points; and makeup processing means for applying a predetermined makeup on the face of the user included in the video based on the tracking points and outputting the video to the display means.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08107672&OS=08107672&RS=08107672
owner: Shiseido Company, Ltd.
number: 08107672
owner_city: Tokyo
owner_country: JP
publication_date: 20070115
---
The present invention relates to makeup simulation systems makeup simulators makeup simulation methods and makeup simulation programs and more particularly to a makeup simulation system a makeup simulator a makeup simulation method and a makeup simulation program for applying makeup on a user s face included in a video.

A conventional technique is known that simulates a face with makeup on a computer without actually applying makeup in order to sell commercial products for applying makeup. See for example Patent Document 1. However according to Patent Document 1 a simulation result is displayed in a still image which has made it difficult to check the made up face reflecting a change in the user s expression. Therefore the development of a technology that simulates makeup in a video having a change in a user s expression captured thereon has been advanced. See for Example Patent Document 2. 

However the makeup simulator described in Patent Document 2 calculates a makeup region to which to apply a face makeup by specifying a change in the user s expression by pixel regions corresponding to the mouth and eyes and tracking the pixel regions with template matching. See for example paragraph 0028 . Tracking a change in the user s expression with the pixel regions corresponding to the mouth and eyes as described above imposes a large processing load on a computer and thus has the problem of difficulty in accurately responding to cases such as eye closing.

The present invention has been made in view of the above described points and has an object of providing a makeup simulation system a makeup simulator a makeup simulation method and a makeup simulation program that make it possible to accurately make up a user s face included in a video with a reduced processing load.

According to the present invention in order to solve the above described problems a makeup simulation system applying makeup to a video having an image of the face of a user captured thereon is characterized by image capturing means for capturing the image of the face of the user and outputting the video control means for receiving the video output from the image capturing means performing image processing on the video and outputting the video and display means for displaying the video output from the control means wherein the control means includes face recognition means for recognizing the face of the user from the video based on predetermined tracking points and makeup processing means for applying a predetermined makeup on the face of the user included in the video based on the tracking points and outputting the video to the display means.

According to the present invention by having face recognition means for recognizing the face of a user from a video based on predetermined tracking points and makeup processing means for applying a predetermined makeup on the face of the user included in the video based on the tracking points and outputting the video to display means it is possible to recognize the face of the user from the video based on the tracking points with a reduced processing load and to apply makeup with accuracy to the face of the user included in the video based on the tracking points.

Methods apparatuses systems computer programs recording media and data structures to which elements representations or any combination of elements of the present invention is applied are also effective as modes of the present invention.

According to the present invention it is possible to provide a makeup simulation system a makeup simulator a makeup simulation method and a makeup simulation program that make it possible to accurately make up a user s face included in a video with a reduced processing load.

Next a description is given based on the following embodiments with reference to the drawings of the best modes for carrying out the present invention. is an external view of a first embodiment of a makeup simulator according to the present invention. The makeup simulator includes a camera an operations panel a printer lights and a monitor .

The camera captures an image of a user standing in front of the makeup simulator and outputs a video. The operations panel displays an operation image and outputs operation information in response to reception of an operation from a user. The printer prints an image such as an imaginary image with makeup and information such as merchandise information for doing makeup like the imaginary image displayed on the monitor. The lights control light after the start of a makeup simulation for example.

The camera outputs a captured video to the control part . The operations panel displays an operation image output from the control part and outputs operation information to the control part in response to reception of an operation from a user. The printer prints an image and information output from the control . The monitor displays a video main image output from the control part . The control part receives a video output from the camera applies makeup on a user s face included in the video by performing image processing on the video as described below and outputs the video to the monitor .

The makeup simulator of and which is based on a mirror an item indispensable for makeup as a concept has the function of interacting with a user. That is the makeup simulator has the characteristic of giving a user a natural feeling as if the user were putting on makeup looking at a mirror.

The makeup simulator performs image processing on a video output from the camera in the control part thereby applying makeup on a user s face included in the image and displays the video on the monitor which is a digital mirror. The makeup simulator is capable of displaying various merchandise and cosmetic information items and the imaginary image of a user s face with makeup applied on it on the monitor .

Further is an external view of a second embodiment of the makeup simulator according to the present invention. The same parts as those of are assigned the same reference numerals.

The makeup simulator of includes the operations panel the printer the lights and a transparent plate . The transparent plate transmits light from outside the makeup simulator and transmits light from inside the makeup simulator .

The half mirror semi transparent mirror reflects light striking it and allows part of the striking light through it. The camera is provided at a position where the camera can capture an image of a user standing in front of the makeup simulator through the half mirror and the transparent plate . The camera is provided at the level of the user s eyes. The camera captures an image of the user standing in front of the makeup simulator through the half mirror and the transparent plate and outputs a video.

The monitor is provided at such a position as to enable a user standing in front of the makeup simulator to view the monitor through the half mirror and the transparent plate . The output light of the monitor is reflected by the half mirror to be output outside the makeup simulator through the transparent plate . Accordingly the user can view a video displayed on the monitor from outside the makeup simulator .

The makeup simulator of and which is based on a mirror an item indispensable for makeup as a concept has the function of interacting with a user. That is the makeup simulator has the characteristic of giving a user a natural feeling as if the user were putting on makeup looking at a mirror.

Since the makeup simulator has the camera provided at the level of a user s eyes the image of the face of a user standing in front of the makeup simulator can be captured more naturally than by providing the camera at its position in the first embodiment.

The makeup simulator performs image processing on a video output from the camera in the control part thereby applying makeup on a user s face included in the image and displays the video on the monitor which is a digital mirror. The makeup simulator is capable of displaying various merchandise and cosmetic information items and the imaginary image of a user s face with makeup applied on it on the monitor .

Further is an external view of a third embodiment of the makeup simulator according to the present invention. The same parts as those of the previous drawings are assigned the same reference numerals. The makeup simulator of includes the camera the half mirror the operations panel the printer and the lights .

The half mirror transmits part for example 50 of light from the bright side and reflects the rest for example 50 of the light from the bright side to the front side. Since there is no light on the dark side the half mirror neither transmits nor reflects light from the dark side.

The lights control light after the start of a makeup simulation so as to brighten the monitor side of the half mirror . Accordingly the half mirror provided on the display direction side of the monitor reflects light from the user side outside the makeup simulator to function as a mirror before the start of the makeup simulation.

After the start of the makeup simulation the half mirror functions as glass to transmit light from the monitor side inside the makeup simulator . Accordingly a user can view a video displayed on the monitor through the half mirror .

The makeup simulator of and which is based on a mirror an item indispensable for makeup as a concept has the function of interacting with a user. That is the makeup simulator has the characteristic of giving a user a natural feeling as if the user were putting on makeup looking at a mirror.

The makeup simulator performs image processing on a video output from the camera in the control part thereby applying makeup on a user s face included in the image and displays the video on the monitor which is a digital mirror. The makeup simulator is capable of displaying various merchandise and cosmetic information items and the imaginary image of a user s face with makeup applied on it on the monitor .

The makeup simulator of and is different from the makeup simulator of and in including the touch panel monitor in place of the operations panel and the monitor . The touch panel monitor functions as the operations panel and the monitor .

The touch panel monitor displays an operation image and outputs operation information in response to reception of an operation from a user. The touch panel monitor displays an operation image output from the control part and outputs operation information to the control part in response to reception of an operation from a user. The touch panel monitor displays a video main image output from the control part . The control part receives a video output from the camera applies makeup on a user s face included in the video by performing image processing on the video as described below and outputs the video to the touch panel monitor .

The makeup simulator of and which is based on a mirror an item indispensable for makeup as a concept has the function of interacting with a user. That is the makeup simulator has the characteristic of giving a user a natural feeling as if the user were putting on makeup looking at a mirror.

The makeup simulator performs image processing on a video output from the camera in the control part thereby applying makeup on a user s face included in the image and displays the video on the touch panel monitor which is a digital mirror. The makeup simulator is capable of displaying various merchandise and cosmetic information items and the imaginary image of a user s face with makeup applied on it on the touch panel monitor .

The makeup simulator of the fourth embodiment may be provided with for example a display case for displaying products for testers to be tried by a user hereinafter referred to as tester products as shown in and to be used as an enclosure for self service selling. is an external view of a fifth embodiment of the makeup simulator according to the present invention. is a cross sectional view of the fifth embodiment of the makeup simulator according to the present invention. The same parts as those of the previous drawings are assigned the same reference numerals.

The makeup simulator includes the camera the printer the lights the touch panel monitor a display case and an IC tag reader writer . The makeup simulator of and is different from the makeup simulator of and in including the display case and the IC tag reader writer .

The display case is for exhibiting multiple tester products. The tester products have IC RFID tags attached thereto. The IC tags attached to the tester products contain identification information by which the tester products can be identified. A tester product is taken out of the display case and brought close to the IC tag reader writer by a user so that the IC tag reader writer reads the identification information of the tester product from the IC tag.

The IC tag reader writer transmits the identification information of a tester product read from the IC tag to the control part . The control part receives a video output from the camera and performs image processing on the video as described below thereby outputting to the touch panel monitor the imaginary image of a user s face included in the video and made up using the tester product corresponding to the identification information read from the IC tag.

A correspondence table that correlates tester products with corresponding identification information may be provided in the makeup simulator or in another apparatus from which the makeup simulator can obtain the correspondence table via a network.

Further with respect to the makeup simulator of and the case of using an IC tag in order to identify a tester product is shown but a barcode two dimensional code or label may also be used. Further the makeup simulator of and may have a scheme that enables identification of an extracted tester product for example position recognition using a sensor such as an optical sensor provided in the display case so that the display case sends a notification to the control part .

The makeup simulator of and which is based on a mirror an item indispensable for makeup as a concept has the function of interacting with a user. That is the makeup simulator has the characteristic of giving a user a natural feeling as if the user were putting on makeup looking at a mirror.

The makeup simulator performs image processing on a video output from the camera in the control part and displays the imaginary image of a user s face included in the video and made up using a tester product selected from the display case by the user on the touch panel monitor which is a digital mirror. The makeup simulator is capable of displaying various merchandise and cosmetic information items and the imaginary image of a user s face with makeup applied on it on the touch panel monitor . The makeup simulator is capable of obtaining data such as a user s preferences by logging the tester product selected from the display case by the user.

For example if the makeup simulator is provided with a shelf for displaying not only tester products but also items for sale the makeup simulator can be used effectively as an enclosure for self service selling by displaying items for sale displayed on the touch panel monitor on the shelf.

A description is given below taking the makeup simulator of the first embodiment as an example. is a hardware configuration diagram of an embodiment of the makeup simulator. The same parts as those of and are assigned the same reference numerals.

The makeup simulator of includes the camera the operations panel the printer the monitor a processor a memory unit a drive unit and a secondary storage unit which are connected to one another via a bus B. The processor the memory unit the drive unit and the secondary storage unit form the control part of .

A makeup simulation program of the present invention is at least part of various programs that control the makeup simulator . The makeup simulation program is provided through distribution of a recording medium for example.

Various types of recording media such as recording media on which information is optically electrically or magnetically recorded such as a CD ROM a flexible disk and a magneto optical disk and semiconductor memories on which information is electrically recorded such as a ROM and a flash memory are usable as the recording medium on which the makeup simulation program is recorded.

Further when the recording medium having the makeup simulation program recorded thereon is loaded into the drive unit the makeup simulation program is installed in the secondary storage unit from the recording medium through the drive unit . The secondary storage unit stores the installed makeup simulation program and stores necessary files and data. The memory unit reads the makeup simulation program from the secondary storage unit and stores it at the time of a startup. The processor implements processing as described below in accordance with the makeup simulation program contained in the memory unit .

The control part is continuously receiving a video captured by the camera . At this point the control part displays the screen image on the monitor and the screen image on the operations panel . The screen images and show the case of displaying screen savers.

Proceeding to step S the control part is continuously determining whether a user s face is included in the received video. The control part repeatedly performs the processing of step S NO in S until it recognizes that a user s face is included in the video.

If the control part recognizes that a user s face is included in the video YES in S it proceeds to step S to activate software containing a makeup simulation program for performing a makeup simulation. At this point the control part displays the screen image on the monitor and displays the screen image on the operations panel .

The screen image shows the case of displaying the video of the user s face captured with the camera . The screen image shows the case of displaying a WELCOME message that moves laterally.

Proceeding to step S the control part starts a makeup simulation based on the software activated in step S. At this point the control part displays the screen image on the monitor and displays the screen image on the operations panel . The screen image shows the case of displaying the video of the user s face captured with the camera with a magic mirror like effect on it. The screen image shows the case of displaying a WELCOME message that moves laterally the same as the screen image .

Proceeding to step S the control part performs a makeup simulation as described below. At this point the control part successively displays the screen images through on the monitor and displays the screen images through on the operations panel .

The screen images through show the case of displaying the user s face with four makeup patterns images applied thereon by the makeup simulation. The screen images through show the case of displaying the contents for example names of the makeup patterns of the screen images through displayed on the monitor then. The control part successively displays the screen images through on the monitor and displays the screen images through on the operations panel until a predetermined period of time passes or the user touches the operations panel .

If a predetermined period of time passes or the user touches the operations panel the control part proceeds to step S to display the screen image on the monitor and display the screen image on the operations panel . Like the screen image the screen image shows the case of displaying the video of the user s face captured with the camera . The screen image shows the case of displaying an image selection screen where one image is selectable from the four makeup patterns images . The user can select one image from the image selection screen by operating the operations panel .

Proceeding to step S the control part repeatedly performs the processing of step S NO in S until one image is selected from the image selection screen. If the user selects one image from the image selection screen the operations panel outputs operation information to the control part in response to reception of the operation from the user.

If the control part determines that the user has selected one image from the image selection screen YES in S the control part proceeds to step S to display the image screen of the selected image on the monitor and the operations panel . At this point the control part displays the screen image on the monitor and displays the screen image on the operations panel .

The screen image shows the case of successively displaying the imaginary image of the made up user s face with different color patterns applied thereon and merchandise information for doing makeup like the imaginary image based on the one image selected from the image selection screen. The screen image shows the case of displaying the contents of the one image selected from the image selection screen and merchandise information for doing makeup like the imaginary image of the screen image displayed on the monitor at that point.

The user can also give an instruction for printing out by operating the operations panel . In response to reception of a PRINT OUT instruction from the user the control part displays the screen image on the monitor and displays the screen image on the operations panel . The screen image shows the case of displaying an imaginary image to be printed out. The screen image shows the case of displaying a comment of NOW PRINTING. The control part controls the printer to print out the imaginary image displayed on the monitor .

Further the user can also give an instruction to display and print out a comparison screen including imaginary images before and after makeup by operating the operations panel . In response to reception of an instruction to display the comparison screen from the user the control part displays the screen image on the monitor . The screen image shows the case of displaying the comparison screen including imaginary images before and after makeup. In response to reception of a PRINT OUT instruction from the user while displaying the comparison screen the control part controls the printer to print out the comparison screen displayed on the monitor .

When the makeup simulation by the user ends the control part displays the screen images and which are screen savers on the monitor and the operations panel and ends the processing.

In the case of and four images are displayed by the makeup simulation. However images other than the four may be displayed. Further the case of applying makeup on a user s face included in a video output from the camera is shown but the makeup simulator may store a precaptured video in the secondary storage unit as a video file and apply makeup on a user s face included in the video file.

The makeup simulator is also capable of using a video output from the camera for other than a makeup simulation. is an image diagram showing processing performed by the makeup simulator other than makeup simulation.

A screen image shows the case of displaying the video of a user s face captured with the camera . The makeup simulator recognizes the user s face included in the video and cuts out a still image of the user s face.

The makeup simulator is capable of making a features diagnosis and a skin color diagnosis on the still image based on a features analysis logic and a skin analysis logic and displaying a screen image showing their results on the monitor . Making a features diagnosis and a skin color diagnosis on the still image based on a features analysis logic and a skin analysis logic is a known technique described in for example Japanese Laid Open Patent Application No. 2001 346627.

Further the makeup simulator is capable of displaying a course selection screen like a screen image on the monitor and causing a user to select a course for example TREND BASIC or FREE . The makeup simulator displays screen images through based on the course selected by the user on the monitor and performs a simulation and give advice.

The screen images through show the case of displaying the respective simulation screens of the courses. The screen images through show the case of displaying the respective advice screens of the courses.

For example the BASIC course simulates and advises on an optimum makeup technique based on the results of the features diagnosis and the skin color diagnosis. Further the TREND course simulates and advises on a makeup of the latest trend. Further the FREE MAKEUP course simulates and advises on items corresponding to the individual parts of the eyes mouth cheeks and eyebrows.

The control part is also capable of controlling the printer to print out a simulation screen or an advice screen displayed on the monitor in response to a PRINT OUT instruction from a user while displaying the simulation screen or the advice screen.

Next a description is given of the details of a makeup simulation system for implementing the makeup simulator as described above. is a system configuration diagram of an embodiment of a makeup simulation system according to the present invention.

A makeup simulation system of includes an analog camera a USB capture device a video file a makeup camera a still image system a video file a shared memory a simulator main application and an interface application .

The analog camera outputs for example a captured NTSC video through the USB capture device . The video output from the USB capture device is input to the simulator main application using a DirectX as an example API application programming interface for example. Further the video file is also input to the simulator main application using the DirectX . The makeup camera outputs a captured video through IEEE 1394 as an example serial interface. The video output from the makeup camera is input to the simulator main application using a dedicated API . The simulator main application obtains an original image of a resolution for videos and a still image of a resolution for still images from the video input using the dedicated API .

The simulator main application employs the video and the video file input using the DirectX and the video of the resolution for videos obtained from the video input using the dedicated API as an original image and trims and reduces the original image.

The simulator main application obtains a pre makeup image by trimming the original image. Further the simulator main application obtains an image for face recognition by reducing the original image. A face recognition part obtains tracking points for recognizing a user s face as described below from the image for face recognition by FFT fast Fourier transform .

A makeup processing part obtains a post makeup image by applying a makeup formed of foundation eyebrow shadow lipstick and cheek on the user s face included in the pre makeup image based on the tracking points . The makeup processing part includes a foundation processing part an eyebrow processing part a shadow processing part a lipstick processing part and a cheek processing part .

The makeup processing part is capable of including merchandise information for doing makeup like the post makeup image in the post makeup image. A video server is capable of writing the pre makeup image and the post makeup image into the shared memory and also outputting the pre makeup image and the post makeup image as the video file .

The interface application includes a video control object a video display object and other controllers that use an ActiveX controller and an ActiveX viewer . The interface application and the simulator main application are linked through ActiveX and Socket.

The interface application is capable of displaying the pre makeup image and the post makeup image written into the shared memory on the above described monitor using the ActiveX viewer .

The simulator main application trims and reduces the still image of the resolution for still images obtained from the video input using the dedicated API . The simulator main application trims the still image of the resolution for still images. Further the simulator main application reduces the still image of the resolution for still images thereby obtaining an image for face recognition. A face recognition part obtains tracking points as described below for recognizing the user s face from the image for face recognition.

The simulator main application extracts specific regions from the user s face included in the trimmed video based on the tracking points obtains additional information to be used for a features diagnosis and a skin color diagnosis such as a type and a skin color from the specific regions and outputs tracking points which are the tracking points plus the additional information and the still image of the resolution for still images obtained from the video input using the dedicated API to the still image system .

The still image system is capable of making a features diagnosis and a skin color diagnosis on the still image based on the above described features analysis logic and skin analysis logic using the tracking points and displaying the screen image showing their results on the monitor . In addition the still image system is also capable of displaying the screen images through on the monitor .

Of the processing performed by the simulator main application face recognition and makeup processing are described in order below in detail with reference to the drawings. In this embodiment a description is given of makeup processing composed of foundation processing eyebrow processing shadow processing lipstick processing and cheek processing as an example of the makeup processing. However the combination may be different.

By thus obtaining the tracking points from a user s face included in the pre makeup image the makeup processing part can set how to apply makeup and color in correlation with the tracking points in a makeup processing parameter file as in .

The lipstick processing part included in the simulator main application performs lipstick processing referring to the tracking points eight on the lips and three on the nose as shown in . is an image diagram showing the tracking points referred to by the lipstick processing.

Proceeding to the cutting out and rotation of step S the lipstick processing part cuts out a partial image containing the lips of the user s face from the image for face recognition and obtains a partial image by rotating the partial image to a position for processing.

Proceeding to the creation of an Image for outline extraction of step S the lipstick processing part creates an image for outline extraction from the partial image . Proceeding to the outline extraction of step S the lipstick processing part extracts the outline of the lips from the image for outline extraction as points as shown in a partial image .

Proceeding to the spline curve generation of step S the lipstick processing part interpolates the points of the image for outline extraction or the default points as in with quadratic splines thereby completing the outline as shown in . is an image diagram showing the processing of completing the outline from the points or default points. When the outline of the lips is completed like a partial image the lipstick processing part proceeds to step S and performs return rotation to reverse the rotation performed in the cutting out and rotation of step S.

Proceeding to the coloring map generation of step S the lipstick processing part generates a coloring map determining the strength of coloring from the lightness and saturation of a partial image . is an image diagram showing the coloring map generation. Specifically the lipstick processing part generates a gray scale image that shows the strength of coloring from the lightness and saturation. The lipstick processing part cuts out only a partial image surrounded by the outline of the lips completed in the spline curve generation of step S from the gray scale image as a coloring map .

Proceeding to the coloring map based coloring of step S the lipstick part applies color to a pre makeup image based on the coloring map generated in the coloring map generation of step S and on how to apply makeup and a specified color set in a makeup processing parameter file like .

Then proceeding to the drawing for debugging and designing of step S the lipstick processing part performs drawing for debugging and designing and thereafter ends the lipstick processing.

The shadow processing part included in the simulator main application performs shadow processing referring to the tracking points three on the eye and one on the eyebrow for each of the right side and the left side as shown in . is an image diagram showing the tracking points referred to by the shadow processing.

The coloring includes the coloring outline generation of step S the coloring center generation of step S the coloring map generation of step S the coloring map based coloring of step S and the drawing for debugging and designing of step S which are repeated as many times as the number of coloring patterns.

Proceeding to the basic outline generation of step S the shadow processing part obtains the shape of an eye of the user s face like a partial image from the image for face recognition. is an image diagram showing the basic outline generation.

The shadow processing part searches upward and downward from the center of the eye and recognizes two points of the outline of the eye upper side boundary and lower side boundary as shown in a partial image in order to generate an outline to serve as the base of a coloring outline. The shadow processing part adds four points generated by spline interpolation to the four points the two recognized points of the eye outline the outer corner of the eye and the inner corner of the eye and generates a polygon by the total of eight points like a partial image .

Proceeding to the coloring outline generation of step S the shadow processing part generates a coloring outline like a partial image . is an image diagram showing the coloring outline generation. The shadow processing part generates a coloring outline based on the outer corner and the inner corner of the eye as shown in a partial image in order to generate the coloring outline. Parameters may be specified with a GUI for extending the outline or shifting vertexes.

Proceeding to the coloring center generation of step S the shadow processing part generates the center position of coloring like in a partial image . Proceeding to the coloring map generation of step S the shadow processing part generates a coloring map determining the strength of coloring like a partial image .

Specifically the coloring map generation determines the strength of application in correspondence to the distances from the coloring center to the sides of the polygon. For example the shadow processing part determines the coloring map so that the strength of application is reduced toward the sides. The coloring map generation is performed on the part between the coloring outline and the basic outline.

The shadow processing part generates a smoother gradation by performing grading on the generated coloring map as shown in . is an image diagram showing the coloring map without grading and the coloring map with grading.

Proceeding to the coloring map based coloring of step S the shadow processing part obtains a post makeup image by coloring a pre makeup image based on the coloring map generated in the coloring map generation of step S and on how to apply makeup and specified colors set in a makeup processing parameter file like .

Then proceeding to the drawing for debugging and designing of step S the shadow processing part performs drawing for debugging and designing and thereafter ends the shadow processing. The shadow processing part is capable of implementing a multi color application by repeating the processing of steps S through S as many times as the number of coloring patterns.

The cheek processing part included in the simulator main application performs cheek processing referring to the tracking points on the outer eye corner and the mouth corner of each of the right side and the left side and between the eyes and at the center of the nose for stabilization as shown in . is an image diagram showing the tracking points referred to by the cheek processing.

Proceeding to the coloring outline generation of step S the cheek processing part generates an outline polygon as a coloring outline based on the outer eye corner and the mouth corner in order to generate the coloring outline. is an image diagram showing the coloring outline. The number of points size shape or position of the outline polygon may be specified by parameters with a GUI.

Proceeding to the coloring of step S the cheek processing part determines the strength of application in correspondence to the distances from the coloring center to the sides of the outline polygon. If the determination of application strength requires too much processing cost the strength of application may be determined by reducing thinning out in a mosaic like manner resolution parameters specified with a GUI . The cheek processing part obtains a post makeup image by coloring a pre makeup image based on the determined strength of application and on how to apply makeup and specified colors set in a makeup processing parameter file like .

Then proceeding to the drawing for debugging and designing of step S the cheek processing part performs drawing for debugging and designing and thereafter ends the cheek processing.

The eyebrow processing part included in the simulator main application performs eyebrow processing referring to the tracking points one on the outer eye corner one on the eye center and two on the eyebrow for each of the right side and the left side as shown in . is an image diagram showing the tracking points referred to by the eyebrow processing.

The original eyebrow region erasure includes the region expansion of step S and the eyebrow erasure of step S. The eyebrow shape deformation includes the creation of an instruction curve corresponding to a specified deformation of step S and the deformed eyebrow generation of step S.

Proceeding to the eyebrow outline extraction of step S the eyebrow processing part obtains the shape of an eyebrow of the user s face like a partial image from the image for face recognition. is an image diagram showing the eyebrow outline extraction. The eyebrow processing part searches the eyebrow rightward and leftward from the outer eyebrow end around the center of the eyebrow in practice as shown in a partial image in order to extract the outline of the eyebrow. The eyebrow processing part recognizes the outline shape of the eyebrow from the search result as shown in a partial image .

Proceeding to the region expansion of step S the eyebrow processing part expands a region showing the recognized outline shape of the eyebrow. Proceeding to the eyebrow erasure of step S the eyebrow processing part erases the eyebrow by filling in the expanded region with a nearby skin color. Further the eyebrow processing part performs blending on the boundary part of the expanded region.

Proceeding to the creation of an instruction curve corresponding to a specified deformation of step S the eyebrow processing part deforms the region skeleton showing the recognized outline shape of the eyebrow as specified. is an image diagram showing the creation of an instruction curve corresponding to a specified deformation.

By replacing the region showing the recognized outline shape of the eyebrow as shown in a partial image with a skeleton composed of a lateral axis and multiple vertical strips and changing the shape of the axis and the height of the strips the eyebrow processing part can deform the region showing the recognized outline shape of the eyebrow like for example a skeleton .

Proceeding to the deformed eyebrow generation of step S the eyebrow processing part generates a deformed eyebrow from the skeleton . Proceeding to the deformed eyebrow pasting of step S the eyebrow processing part obtains a post makeup image by pasting the deformed eyebrow to a pre makeup image.

The foundation processing part included in the simulator main application performs foundation processing referring to the tracking points one on each of the outer eye corner the inner eye corner and the eyebrow on each of the right side and the left side and between the eyes and at the center of the nose as shown in . is an image diagram showing the tracking points referred to by the foundation processing.

Proceeding to the outline generation of step S the foundation processing part generates the outlines of three kinds four parts of the forehead nose and cheeks right and left as shown in the imaginary image of . is an imaginary image showing the outlines. The size and position of each outline may be specified by parameters with a GUI.

Proceeding to the grading on an object image of step S the foundation processing part performs grading on object images corresponding to the generated outlines as . is an image diagram showing an original image before grading and the original image after grading. By performing grading on an object image the foundation processing part can smooth minute skin roughness.

Proceeding to the image pasting of step S the foundation processing part obtains a post makeup image by pasting the object images after grading to the outlines of three types four parts of the forehead nose and cheeks right and left of a pre makeup image.

Thus according to the present invention it is possible to accurately apply makeup to a user s face included in a video with a reduced processing load. Image capturing means described in CLAIMS corresponds to the camera control means corresponds to the control part display means corresponds to the monitor face recognition means corresponds to the face recognition part makeup processing means corresponds to the makeup processing part operation means corresponds to the operations panel half mirror means corresponds to the half mirror and printing means corresponds to the printer .

Further the present invention is not limited to the specifically disclosed embodiments and variations and modifications may be made without departing from CLAIMS.

Unlike those based on still images or the conventional makeup simulator the makeup simulator of the present invention which performs a real time simulation is capable of instantaneously recognizing tracking points of a face and performing simulation based on the tracking points. Therefore the makeup simulator enables the following that have not been possible so far.

The makeup simulator of the present invention is capable of a real time simulation. The makeup simulator of the present invention is capable of simulation not only from a full face as conventionally but also from a face in profile. Accordingly it is easy to view the simulation effect or technique of blusher or the like.

The makeup simulator of the present invention is capable of not only the conventional two dimensional representation but also analyzing a face as a three dimensional shape and representing solidity and texture.

Further since the makeup simulator of the present invention is capable of recognizing multiple faces at the same time the makeup simulator of the present invention is capable of performing simulation for multiple persons at the same time. Since the makeup simulator of the present invention has an excellent face recognition function the makeup simulator of the present invention is capable of automatically performing classification according to individual features or performing classification into men and women and doing makeup suited to features or classification. For example the makeup simulator of the present invention is capable of simultaneously performing respective makeup simulations for a couple.

The present international application claims priority based on Japanese Patent Application No. 2006 9268 filed on Jan. 17 2006 the entire contents of which are incorporated into the present international application.

