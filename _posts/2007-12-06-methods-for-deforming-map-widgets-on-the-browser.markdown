---

title: Methods for deforming map widgets on the browser
abstract: A method for displaying an image of a map using a processing system, the method including: dividing a first map image obtained from a map widget into sections wherein the first map image is displayed by the processing system; recording the location of each marker to be represented in a second map image; calculating a weight factor for each section; moving and deforming each section according to the weight factor of each section to form the second map image; placing a new marker on the second map image wherein the new marker represents at least one marker with a recorded location; and displaying the second map image in place of the first map image.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08438477&OS=08438477&RS=08438477
owner: International Business Machines Corporation
number: 08438477
owner_city: Armonk
owner_country: US
publication_date: 20071206
---
IBM is a registered trademark of International Business Machines Corporation Armonk N.Y. U.S.A. Other names used herein may be registered trademarks trademarks or product names of International Business Machines Corporation or other companies.

This invention relates to modifying maps received from the Internet and particularly to modifying the maps with a browser.

The World Wide Web provides many services via the Internet. These services are generally accessed using a software application referred to as a browser. Some of the services provide a mapping feature which may be referred to as a map widget. One example of a map widget is GOOGLE Maps.

The map widget may present a map upon which a marker is illustrated. The marker is used to indicate a certain location on the map.

Some problems may arise when a map is displayed with more than one marker. In some situations where markers are close together on a small area of the map the markers may overlap each other. When markers overlap each other a false impression concerning the information presented by the markers may be created. The false impression may be created because a viewer may not be abler to discern the number of markers present at the small area of the map. In addition information displayed on the map may be obstructed by the markers being close together.

Attempts have been made to overcome the problems stated above using available software with the browser. In one example a chart is used to present information that would be presented by the markers. However the chart can also obstruct details on the map such as country names and borders. In another example color is used to convey marker information. The application of color though cannot be applied to maps that already have color. Also the browser is unable to color only the land because the browser cannot find the border between sea and land.

The map image itself cannot be modified using image processing techniques in conjunction with the browser because JAVASCRIPT cannot be used with binary code.

Therefore what are needed are techniques for illustrating a map while providing an accurate impression of the number or markers presented on the map. In addition the map is illustrated so as to limit obscuring of information displayed on the map.

The shortcomings of the prior art are overcome and additional advantages are provided through the provision of a method for displaying an image of a map using a processing system the method including dividing a first map image obtained from a map widget into sections wherein the first map image is displayed by the processing system recording the location of each marker to be represented in a second map image calculating a weight factor for each section moving and deforming each section according to the weight factor of each section to form the second map image placing a new marker on the second map image wherein the new marker represents at least one marker with a recorded location and displaying the second map image in place of the first map image.

Further disclosed is a computer program product stored on machine readable media and including machine executable instructions for displaying an image of a map using a processing system the product including instructions for dividing a first map image obtained from a map widget into sections wherein the first map image is displayed by the processing system recording the location each marker to be represented in a second map image calculating a weight factor for each section wherein the weight factor is proportional to the number of markers to be represented in each section moving and deforming each section according to the weight factor of each section to form the second map image wherein at least one section that includes the location of at least one marker is expanded and at least one section that does not include the location of at least one marker is contracted placing a new marker on the second map image wherein a size of the new marker is proportional to the number of markers the new marker represents and displaying the second map image in place of the first map image.

Additional features and advantages are realized through the techniques of the present invention. Other embodiments and aspects of the invention are described in detail herein and are considered a part of the claimed invention. For a better understanding of the invention with advantages and features refer to the description and to the drawings.

As a result of the summarized invention technically we have achieved a solution which solves the problem of displaying a map image on a processing system wherein markers located close together result in markers overlapping each other and thereby creating an inaccurate first impression. In addition we have achieved a solution to the problem of markers obscuring information displayed on the map image.

The detailed description explains the preferred embodiments of the invention together with advantages and features by way of example with reference to the drawings.

The teachings provide techniques for illustrating a map with at least one marker on a display of a computer processing system. In particular the techniques illustrate the marker on the map while limiting obscuring of information on the map by the marker. The techniques provide for an accurate first impression concerning the number of markers and their location on the map.

The techniques include a method for distorting an image of the map with a browser. Specifically the method emphasizes by expanding a portion of the map that includes the marker. By expanding the emphasized portion more area of the image is available to provide information without being obscured by the marker. The method also includes de emphasizing by contracting portions of the map that do not include any markers. A portion of the map between an emphasized portion and a de emphasized portion is generally distorted to provide a smooth transition between the two portions.

In one embodiment when there are many markers located in a small area of the map the method may illustrate a single marker in place of the many markers. The single marker in these instances will have a size proportional to the number of markers for which the single marker is substituted.

Referring to there is shown an exemplary embodiment of a processing system for implementing the teachings herein. In this embodiment the system has one or more central processing units processors etc. collectively or generically referred to as processor s . In one embodiment each processor may include a reduced instruction set computer RISC microprocessor. Processors are coupled to system memory and various other components via a system bus . Read only memory ROM is coupled to the system bus and may include a basic input output system BIOS which controls certain basic functions of system .

Thus as configured in the system includes processing means in the form of processors storage means including system memory and mass storage input means such as keyboard and mouse and output means including speaker and display . In one embodiment a portion of system memory and mass storage collectively store an operating system such as the AIX operating system from IBM Corporation to coordinate the functions of the various components shown in .

It will be appreciated that the system can be any suitable computer or computing platform and may include a terminal wireless device information appliance device workstation mini computer mainframe computer personal digital assistant PDA or other computing device.

Examples of operating systems that may be supported by the system include WINDOWS 95 WINDOWS 98 WINDOWS NT 4.0 WINDOWS XP WINDOWS 2000 WINDOWS CE WINDOWS VISTA MACINTOSH JAVA LINUX and UNIX or any other suitable operating system. The system also includes a network interface for communicating over a network. The network can be a local area network LAN a metro area network MAN or wide area network WAN such as the Internet or World Wide Web.

Users of the system can connect to the network through any suitable network interface connection such as standard telephone lines digital subscriber line LAN or WAN links e.g. T1 T3 broadband connections Frame Relay ATM and wireless connections e.g. 802.11 a 802.11 b 802.11 g .

As disclosed herein the system includes machine readable instructions stored on machine readable media for example the hard disk for capture and interactive display of information shown on the screen of a user. As discussed herein the instructions are referred to as software . The software may be produced using software development tools as are known in the art. Also discussed herein the software may also referred to as a map display software or by other similar terms. The software may include various tools and features for providing user interaction capabilities as are known in the art.

In some embodiments the software is provided as an overlay to another program. For example the software may be provided as an add in to an application or operating system . Note that the term add in generally refers to supplemental program code as is known in the art. In such embodiments the software may replace structures or objects of the application or operating system with which it cooperates.

The software generally provides users with a capability to distort a map provided by a widget. Commands to distort the map are used with the browser. The commands are automatically executed by the browser to distort the map. The commands may be native to written to function within computer application code programs for example C C PERL JAVA JAVASCRIPT and others other programs typically regarded as computing environments UNIX LINUX DOS and others as well as other types of programs.

In one embodiment the software may initially be placed on a server. In this embodiment the processing system can be a client of the server. The processing system running the browser can receive the software via the Internet by specifying a uniform resource locator URL . In one embodiment the processing system will receive the software that includes JAVASCRIPT and Hypertext Markup Language HTML . The browser can then run the JAVASCRIPT that was received by the processing system .

As a matter of convention herein it is considered that the software provides for interfacing with other computer code used for presenting a map widget. It is recognized that computer code is commonly regarded as software however in the interest of avoiding confusion use of the term software is generally limited to describing embodiments of computer implemented instructions and computer program products that provide for distorting a map presented by a map widget.

For some perspective on the map display software consider the following. A map widget may be presented on the processing system by an Internet browser such as MOZILLA FIREFOX available from Mozilla Corporation of Mountain View Calif. A map with markers associated with the map widget may be transformed by the map display software . The map display software may be run on Firefox to transform the map and present the markers.

As used herein the term distorted generally refers to a capability of the software to transform the undistorted map into an emphasized map. The term transform relates to deforming sections of the undistorted map and assembling the deformed sections to create the emphasized map. The terms map and map image relate to an image of a map displayed on the display of the processing system . The term weight factor relates to a value or values that may be calculated using equations herein that include the term weight .

With respect to step a map application programming interface API associated with the map widget may be used to record a location latitude and longitude for each of the markers on the undistorted map . The map API may also be used to convert the geographical location for each marker into a pixel position on the undistorted map .

Referring to in one embodiment the weight for each of the sections is calculated using equation 1 as follows for row column or r c to row column or r c 

where A is a constant selected to express how much the weight in one section will influence the weight in another section dc represents the number of columns between c and c dr represents the number of rows between r and r and markerNum r c represents the number of markers in the section identified by coordinates r c . Equation 1 represents the weight from position r c to position r c . In general the section with more markers than another section will have a greater weight than the other section . In addition the section adjacent to a section with heavy weight will also have heavy weight.

Referring to in one embodiment the cumulative weight from all sections is calculated using equation 2 as follows 

With respect to step of method in one embodiment each section is moved and deformed in accordance with the weight of each section . To fit all sections that are deformed into the emphasized map image of a given width and height a column weight and a row weight are calculated. Referring to in one embodiment equation 3 is used to calculate a row weight for sections in row r.

An average row weight and an average column weight are calculated using equations 5 and 6 as follows avrRowWeight rowWeight Num 5 avrColWeight colWeight Num 6 

Referring to in one embodiment equations 7 through 14 are used to determine at least one of how each section will be deformed and how each section that is deformed will be located as follows pos pos 1 pos 1 7 

where pos r c x represents a pixel position in the x direction of the section identified by row and column coordinates r c pos pos 1 pos 1 8 where pos r c y represents a pixel position in the y direction of the section identified by row and column r c pos section weight avrColWeight 9 

where sectionH is the pixel height of the section identified by r c pos section weight avrRowWeight 10 

where pos r c tan X represents the gradient degrees in the x direction of the section identified by r c pos tan pos 1 pos pos 12 

where pos r c tan Y represents the gradient degrees in the y direction of the section identified by r c pos pos 1 pos pos 1 pos 13 

where pos r c h represents the height in pixels of the section identified by r c and pos pos 1 pos pos 1 pos 14 

With respect to equation 13 pos r c h uses the larger of pos r c h and pos r c 1 h so that an adjacent section can fill in a resulting gap. Similarly with respect to equation 14 pos r c w uses the larger of pos r c w and pos r 1 c w so that an adjacent section can fill in a resulting gap.

Referring to applying the equations presented above to the undistorted map and the sections results in producing an emphasized map with modified sections . The modified sections result from deforming the sections .

Referring to in one embodiment equations 13 and 14 are used to place the markers on the modified sections of the emphasized map as follows marker marker pos section 15 

where markerX represents the number of pixels in the x direction from an origin r c of the modified section markerX represents the number of pixels in the x direction used to locate the marker on the section and sectionW represents the pixel width of the corresponding section and marker marker pos section 16 

where markerY represents the number of pixels in the y direction from an origin r c of the modified section markerY represents the number of pixels in the y direction used to locate the marker on the section and sectionH represents the pixel height of the corresponding section .

Referring to one example of computing the emphasized map is presented as follows with the following conditions 

In the following code the numbers in parentheses correspond to the numbers on . This code is used to create a transformation array wherein each transformation is applied one after another. The transformations transform each section to one modified section using the gfx library 

One example of the emphasized map is illustrated in . Referring to the emphasized map includes new markers . The new markers result from the markers being placed on the emphasized map . In the embodiment of the size of each new marker is proportional to the number of markers each new marker represents.

The capabilities of the present invention can be implemented in software firmware hardware or some combination thereof.

As one example one or more aspects of the present invention can be included in an article of manufacture e.g. one or more computer program products having for instance computer usable media. The media has embodied therein for instance computer readable program code means for providing and facilitating the capabilities of the present invention. The article of manufacture can be included as a part of a computer system or sold separately.

Additionally at least one program storage device readable by a machine tangibly embodying at least one program of instructions executable by the machine to perform the capabilities of the present invention can be provided.

When introducing elements of the present invention or the embodiment s thereof the articles a an and the are intended to mean that there are one or more of the elements. The terms including and having are intended to be inclusive such that there may be additional elements other than the listed elements.

The flow diagrams depicted herein are just examples. There may be many variations to these diagrams or the steps or operations described therein without departing from the spirit of the invention. For instance the steps may be performed in a differing order or steps may be added deleted or modified. All of these variations are considered a part of the claimed invention.

While the preferred embodiment to the invention has been described it will be understood that those skilled in the art both now and in the future may make various improvements and enhancements which fall within the scope of the claims which follow. These claims should be construed to maintain the proper protection for the invention first described.

