---

title: Reshaping a camera image
abstract: Apparatuses, computer media, and methods for altering a camera image, in which the source image may be angularly displaced from a camera image. A plurality of points on the camera image is located and a mesh is generated. Compensation information based on the displacement is determined, and a reshaped image is rendered from the mesh, the compensation information, and the camera image. The camera image is reshaped by relocating a proper subset of the points on the camera image. Deformation vectors are applied to corresponding points on the mesh using the compensation information. A correction factor is obtained from an angular displacement and a translation displacement of the source image from the camera image. The deformation factor is multiplied by the compensation factor to form a deformation vector to compensate for angular and translational displacements of the source image from the camera image.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=07953294&OS=07953294&RS=07953294
owner: Accenture Global Services Limited
number: 07953294
owner_city: Dublin
owner_country: IE
publication_date: 20070213
---
This application is a continuation in part of co pending U.S. patent application Ser. No. 11 625 937 entitled Reshaping an Image to Thin or Fatten a Face and filed on Jan. 23 2007 the entire disclosure of which is hereby incorporated by reference.

This invention relates to altering a camera image. More particularly the invention applies to a source image being angularly displaced from the camera image plane.

Excessive body weight is a major cause of many medical illnesses. With today s life style people are typically exercising less and eating more. Needless to say this life style is not conducive to good health. For example it is acknowledged that type 2 diabetes is trending to epidemic proportions. Obesity appears to be a major contributor to this trend.

On the other hand a smaller proportion of the population experiences from being underweight. However the effects of being underweight may be even more divesting to the person than to another person being overweight. In numerous related cases people eat too little as a result of a self perception problem. Anorexia is one affliction that is often associated with being grossly underweight.

While being overweight or underweight may have organic causes often such afflictions are the result of psychological issues. If one can objectively view the effect of being underweight or underweight one may be motivated to change one s life style e.g. eating in a healthier fashion or exercising more. Viewing a predicted image of one s body if one continues one s current life style may motivate the person to live in a healthier manner.

Embodiments of invention provide apparatuses computer media and methods for altering a camera image in which the source image may be angularly displaced from a camera image.

With an aspect of the invention a plurality of points on the camera image is located and a mesh is generated. The mesh is superimposed on the camera image and associated with corresponding texture information of the camera image. Compensation information based on the displacement is determined and a reshaped image is rendered from the mesh the compensation information and the camera image.

With another aspect of the invention the camera image is reshaped by relocating a proper subset of the points on the camera image. Deformation vectors are applied to corresponding points on the mesh using the compensation information. A deformation vector may comprise a product of factors including a weight value factor A a scale factor s a deformation factor w and a direction vector right arrow over u .

With another aspect of the invention a correction factor is obtained from an angular displacement and a translation displacement of the source image from the camera image. The deformation factor is multiplied by the compensation factor to form a deformation vector to compensate for angular and translational displacements of the source image from the camera image.

This mesh is associated to its corresponding texture from the picture where the alteration is taking place. The corners and four points along each side of the picture as shown in are also considered as part of the mesh. Computer graphics software API Application Programming Interface is used to render the altered image e.g. as shown in . OpenGL API is an example of computer graphics software that may be used to render the altered image.

In the following discussion that describes the determination of the deformation vectors for reshaping the face image index i 6 to index i 31 correspond to points to points respectively. The determined deformation vectors are added to points to points to re position the point forming a transformed mesh. A reshaped image is consequently rendered using the transformed mesh.

In accordance with embodiments of the invention deformation vector correspond to a product of four elements factors EQ. 1 where A is the weight value factor s is the scale factor w is the deformation factor and right arrow over u is the direction vector. In accordance with an embodiment of the invention 

With an embodiment of the invention A 100 corresponds to a maximum degree of fattening and A 100 corresponds to a maximum degree of thinning. The value of A is selected to provide the desired degree of fattening or thinning. For example if a patient were afflicted anorexia the value of A would have a negative value that would depend on the degree of affliction and on the medical history and body type of the patient. As another example a patient may be over eating or may have an unhealthy diet with many empty calories. In such a case A would have a positive value. A medical practitioner may be able to gauge the value of A based on experience. However embodiments of invention may support an automated implementation for determining the value of A. For example an expert system may incorporate knowledge based on information provided by experienced medical practitioners.

In step deformation vectors are determined and applied to points e.g. points as shown in on the face. For example as discussed above EQs. 1 5. are used to determine the relocated points. In step deformation vectors are determined e.g. using EQs. 6 9 and applied to points e.g. points as shown in on the neck. A transformed mesh is generated from which a reshaped image is rendered using computer graphics software in step .

Computer may also include a variety of interface units and drives for reading and writing data. In particular computer includes a hard disk interface and a removable memory interface respectively coupling a hard disk drive and a removable memory drive to system bus . Examples of removable memory drives include magnetic disk drives and optical disk drives. The drives and their associated computer readable media such as a floppy disk provide nonvolatile storage of computer readable instructions data structures program modules and other data for computer . A single hard disk drive and a single removable memory drive are shown for illustration purposes only and with the understanding that computer may include several of such drives. Furthermore computer may include drives for interfacing with other types of computer readable media.

A user can interact with computer with a variety of input devices. shows a serial port interface coupling a keyboard and a pointing device to system bus . Pointing device may be implemented with a mouse track ball pen device or similar device. Of course one or more other input devices not shown such as a joystick game pad satellite dish scanner touch sensitive screen or the like may be connected to computer .

Computer may include additional interfaces for connecting devices to system bus . shows a universal serial bus USB interface coupling a video or digital camera to system bus . An IEEE 1394 interface may be used to couple additional devices to computer . Furthermore interface may configured to operate with particular manufacture interfaces such as FireWire developed by Apple Computer and i.Link developed by Sony. Input devices may also be coupled to system bus through a parallel port a game port a PCI board or any other interface used to couple and input device to a computer.

Computer also includes a video adapter coupling a display device to system bus . Display device may include a cathode ray tube CRT liquid crystal display LCD field emission display FED plasma display or any other device that produces an image that is viewable by the user. Additional output devices such as a printing device not shown may be connected to computer .

Sound can be recorded and reproduced with a microphone and a speaker . A sound card may be used to couple microphone and speaker to system bus . One skilled in the art will appreciate that the device connections shown in are for illustration purposes only and that several of the peripheral devices could be coupled to system bus via alternative interfaces. For example video camera could be connected to IEEE 1394 interface and pointing device could be connected to USB interface .

Computer can operate in a networked environment using logical connections to one or more remote computers or other devices such as a server a router a network personal computer a peer device or other common network node a wireless telephone or wireless personal digital assistant. Computer includes a network interface that couples system bus to a local area network LAN . Networking environments are commonplace in offices enterprise wide computer networks and home computer systems.

A wide area network WAN such as the Internet can also be accessed by computer . shows a modem unit connected to serial port interface and to WAN . Modem unit may be located within or external to computer and may be any type of conventional modem such as a cable modem or a satellite modem. LAN may also be used to connect to WAN . shows a router that may connect LAN to WAN in a conventional manner.

It will be appreciated that the network connections shown are exemplary and other ways of establishing a communications link between the computers can be used. The existence of any of various well known protocols such as TCP IP Frame Relay Ethernet FTP HTTP and the like is presumed and computer can be operated in a client server configuration to permit a user to retrieve web pages from a web based server. Furthermore any of various conventional web browsers can be used to display and manipulate data on web pages.

The operation of computer can be controlled by a variety of different program modules. Examples of program modules are routines programs objects components and data structures that perform particular tasks or implement particular abstract data types. The present invention may also be practiced with other computer system configurations including hand held devices multiprocessor systems microprocessor based or programmable consumer electronics network PCS minicomputers mainframe computers personal digital assistants and the like. Furthermore the invention may also be practiced in distributed computing environments where tasks are performed by remote processing devices that are linked through a communications network. In a distributed computing environment program modules may be located in both local and remote memory storage devices.

In an embodiment of the invention central processor unit obtains a face image from digital camera . A user may view the face image on display device and enter points e.g. points as shown in to form a mesh that is subsequently altered by central processor as discussed above. The user may identify the points with a pointer device e.g. mouse that is displayed on display device which overlays the mesh over the face image. With embodiments of the invention a face image may be stored and retrieved from hard disk drive or removable memory drive or obtained from an external server not shown through LAN or WAN .

The camera is characterized by optical center and focal length F . The axis orientation of the camera is characterized by angles and corresponding to the x y and z axes respectively. The origin of the axis orientation is located at the center of the camera image plane of the projected section that is shown in . Projected point x y is related to the corresponding source point by the following relationship 

With embodiments of the invention one may assume that the face of the person is perpendicular to the axis orientation of the camera. Taking into account the 3D observation model detailed as will be discussed a direct pose occurs when 0.

Embodiments of the invention support image poses in which the pose is angularly offset. The correction factor for such a situation adapts the deformation factor w applied to the deformation vector of each vertex e.g. as the vertices shown in that is moved during the reshaping of the image e.g. the face of a person . With an embodiment of the invention the correction factor may be obtained from an angular displacement and a translation displacement of the source image from the camera image. The translation and the displacement may be determined from the difference from the 3D face pose in a frontal position from which one has previously computed the weights and the 3D pose of the face that one has actually taken the picture of.

The observation model utilized to relate the head in its neutral pose source image facing the camera and its projected representation taking into account the rigid motion translations and rotations of the head observed from reference origin and the projection due to the camera. Although the acquisition camera is not calibrated because one does not control the nature of the input sequences one can still consider that it obtains a perspective projection and not an orthogonal projection.

Reference origin is situated along the optical axis of the camera at the center of camera image plane . Camera image plane represents the video image where the face is focused. Focal distance F represents the distance from camera image plane to the optical center of the camera. To describe the rigid motion of the head one may specify three translations along the X Y and Z axes and three rotations around the X Y and Z axes. presents the graphical interpretation of the model and the orientation of the reference axes.

One may describe points using their homogenous coordinates to be able to describe a perspective transform linearly and derive the relationship between 3D neutral coordinates and 2D projections.

A vector x y z o corresponds to a homogenous point if at least one of its elements is not 0. o is the coordinate that is added to convert the coordinates to homogenous coordinates. Homogeneous coordinates allow affine transformations to be easily represented by a matrix. Also homogeneous coordinates make calculations possible in projective space just as Cartesian coordinates do in Euclidean space. The homogeneous coordinates of a point of projective space of dimension n are typically written as x y z . . . o a row vector of length n 1 other than 0 0 0 . . . 0 . If a is a real number and is not 0 x y z o and ax ay az ao represent the same homogenous point. The relationship between a point in 3D or 2D Euclidean space and its homogenous representation is 

As an example of projective space in three dimensions there are corresponding homogeneous coordinates x y z o . The plane at infinity is typically identified with the set of points with o 0. Away from this plane one can denote x o y o z o as an ordinary Cartesian system therefore the affine space complementary to the plane at infinity is assigned coordinates in a similar way with a basis corresponding to 1 0 0 1 0 1 0 1 0 0 1 1 .

The following matrices represent different transformations that describe rigid motion where s sin c cos s sin c cos s sin and c cos .

The final location of the head regarding reference origin is obtained applying the translation and rotation matrices upon the coordinates of the head in its neutral pose. where

Then the position head is facing the camera is defined when t t t 0 0 0 0 0 and 0. The observed projection on camera image plane is where

After transforming the homogenous coordinates to Euclidean space coordinates o 1 and zis not taken into account the observation x y on the image plane of a given point x y z belonging to the face in its neutral pose is 

For each of the vertices i to be moved during the reshaping of the face referring to according to the new deformation factor w. 1 EQ. 11 where

From EQs. 11 and 12 a deformation factor w e.g. as determined with EQs. 4A 4D is multiplied by a correction factor r t 1 in order obtain a new corrected deformation factor w. From EQs. 1 5B a corrected deformation vector is determined. Each deformation vector is applied to a corresponding vertex to obtain a transformed mesh. Experimental data using EQs. 11 12 have been obtained for angular displacement varying between 0.087 radians and angular displacement varying between 0.17 radians.

As can be appreciated by one skilled in the art a computer system e.g. computer as shown in with an associated computer readable medium containing instructions for controlling the computer system may be utilized to implement the exemplary embodiments that are disclosed herein. The computer system may include at least one computer such as a microprocessor a cluster of microprocessors a mainframe and networked workstations.

While the invention has been described with respect to specific examples including presently preferred modes of carrying out the invention those skilled in the art will appreciate that there are numerous variations and permutations of the above described systems and techniques that fall within the spirit and scope of the invention as set forth in the appended claims.

