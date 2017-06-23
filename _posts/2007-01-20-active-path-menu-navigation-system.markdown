---

title: Active path menu navigation system
abstract: A method for navigating within a multi-level hierarchical collapsing menu structure is disclosed. Each level in the menu structure contains plural items, each item being at least one of a function, a pointer to a location, and a pointer to another level. The method of the present invention includes a step of providing a graphical user menu system displaying the items of a given level and enabling selection thereof, wherein access of the given level requires sequential access of each of the levels preceding the given level in the hierarchy. An Active Path is dynamically constructed as a sequence of active links as items are selected using the graphical user menu system, with one active link correspond to each of the items selected. The active links provide direct access to a function corresponding level or menu item without the need to navigate using the graphical user menu system.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=07640517&OS=07640517&RS=07640517
owner: 
number: 07640517
owner_city: 
owner_country: 
publication_date: 20070120
---
This application is a continuation of application Ser. No. 10 164 520 filed Jun. 6 2002 issued as U.S. Pat. No. 7 191 411.

The present invention generally relates to a navigation system used to navigate a hierarchical menu such as a directory structure or a pull down menu. The menu navigation system of the present invention may be implemented in software executing on a standalone software program or on a client server application. More particularly the menu navigation system of the present invention allows a user to access different levels in a hierarchical menu system without retracing back to the top level of the hierarchy.

Hierarchical systems are used to organize items by function or theme in order to facilitate efficient locating of functions or locations. Hierarchical systems are used to organize documents into directories or folders and to organize functions into pull down menus.

Conventionally one of two navigation systems are used to navigate through the various levels of a menu tree. By far the most popular menu navigation system is the so called collapsing menu system which for example is used by many traditional personal computer applications. The distinguishing characteristics of this system are that the navigation always commences from the initial or root level and that the menu collapses or disappears after a selection is made.

Computer software frequently includes dozens of functions. The sheer number of features makes it desirable to organize the functions into a hierarchy of categories to facilitate efficient searching. In a collapsing menu system each level in the hierarchy is presented as a level in the pull down menu.

To address this shortcoming conventional operating systems such as Microsoft Windows provide short cuts in the form of pre defined function keys or icons. Such short cuts enable the user to directly access the desired function associated with the short cut.

In the absence of a pre defined short cut the user must resort to navigating the menu structure. The problem with the collapsing menu system is that navigation must always commence from the root level. Consequently more experienced users are unable to take advantage of their knowledge of the hierarchical structure to directly access a given level.

Navigation using the path menu system requires the user to memorize and enter complex hierarchical sequences. This method of navigation is time consuming not suitable for users who have not memorized the path. Moreover this method becomes extremely cumbersome as the number of levels increases. Accordingly one object of the present invention is to provide a more efficient way of navigating hierarchical menu systems.

A method for navigating within a multi level hierarchical collapsing menu structure is 15 disclosed. Each level in the menu structure contains plural items each item being at least one of a function a pointer to a location and a pointer to another level.

The method of the present invention includes a step of providing a graphical user menu system displaying the items of a given level and enabling selection thereof wherein access of the given level requires sequential access of each of the levels preceding the given level in the 20 hierarchy. An Active Path is dynamically constructed as a sequence of active links as items are selected using the graphical user menu system with one active link correspond to each of the items selected. The active links provide direct access to a function corresponding level or menu item without the need to navigate using the graphical user menu system.

According to a further aspect of the invention pre defined short cuts are provided which enable direct access to a given menu item. The Active Path is dynamically constructed when one of the pre defined short cuts are executed with one active link corresponding to each of the menu items necessary to access the given menu item using the graphical user menu system.

Navigation using the Active Path is accomplished by at least of one of rolling over and selecting an active link using a pointing device. Rolling over a given active link triggers the display of sibling menu items on the level associated with the given active link. Selecting a given active link triggers the execution of a function associated with the given active link.

The processing logic generally represented by processor is connected by a bus structure to the various other components of the computer . The schematic representation of bus is shown in as a simple and unitary structure but in conventional practice as is known to those in the art there usually are several buses and communication pathways operating at different speeds and having different purposes. Further bus may be segmented and controlled by respective bus controllers as is also known in the art.

Computer will also have a random access memory unit or units connected to the bus . RAM which may be DRAM SDRAM or other known types typically has loaded into it the operating system of the computer and executable instructions for one or more special applications designed to carry out the invention. Computer also has electronic read only memory for storing those programs such as the BIOS which are non volatile and persist after the computer is shut down.

In alternative embodiments of the invention one or more components of the invention s logic may be hard wired into the ROM instead of loaded as software instructions into RAM . ROM can consist of or comprise electrically programmable read only memory EPROM electrically erasable and programmable read only memory EEPROM of either flash or nonflash varieties or other sorts of read only memory such as programmable fuse or antifuse arrays.

In a typical architecture a computer program suitable for carrying out the invention will be stored on a mass storage device such as an optical disk or magnetic hard drive. Bus connects mass storage device to RAM . The computer is connected to various peripheral devices used to communicate with an operator such as display keyboard and pointing device mouse .

In operation operating system software such as Microsoft Windows executes on the computer and the user interacts with the operating system using the display keyboard and pointing device mouse .

As will be explained below the Active Path may be used in conjunction with a conventional navigation system such as the above described collapsing menu system or path menu system.

The Active Path consists of a sequential listing of active links each active link providing direct access to a corresponding level in the hierarchical path and to all of the menu items on the level sibling menu items . The last active link in the Active Path is termed an end link . The Active Path is dynamically assembled and displayed as the user navigates using the conventional menu screens. The Active Path is assembled automatically without the need for any additional user interaction as the user navigates using the collapsing menu system.

In contrast a conventional short cut such as a function key icon or the like is static in that it only provides access to a single pre defined item function allocation within a given level and does not provide the user with the full range of items available within a given level. Moreover the definition of a short cut requires user interaction. The Active Path is automatically constructed as the user navigates between the various levels of the conventional collapsing menu system. The first active link corresponds to the root level and each subsequent active link corresponds to a user selected menu item which may be a location or a classification sublevel of functions. As will be explained below the end link points either to a function or a location. The Active Path of the present invention may be used in place of the menu system to navigate through classes of functions and execute a selected function. Moreover the Active Path may also be used to navigate to a desired location such as a web address or directory folder.

By manner of illustration shows how the Active Path is sequentially assembled as menu items and are selected from the collapsing menu system. Active link corresponds to menu item selected from the initial or root level . Likewise active link corresponds to menu item selected from level and active link corresponds to menu item selected from level . Construction of the Active Path occurs automatically as the user navigates through the menu system . It should be noted that active link is the end link in the Active Path .

Turning now to the menu system pull down menu tree collapses when the user selects end node whereas the Active Path persists. As will be described the active links enable the user to directly access levels and without having to navigate from the root level . Moreover end link enables the user to re execute the function associated with directly without the need for a pre defined short cut.

Each of the active links in the Active Path may be accessed by either rolling over the active link with the pointer of the pointing device or by immediately selecting the active link . As shown in rolling over the active simply entails manipulating the mouse to position the software pointer over the active link . Rolling over an active link causes the sibling menu items on the level corresponding the active link to be displayed. It should be noted that simply rolling over an active link does not alter the Active Path it merely causes the sibling menu items to be displayed.

Selection of an active link is accomplished by for example positioning the software pointer over the active link and actuating and releasing one of the mouse buttons . Selection of an active link causes different results depending on whether or not the selected active link is the end link in the Active Path . If the selected active link is not the end link then selection will cause the sibling menu items on the associated level to be displayed and will trigger the construction of a new Active Path . For example selection of menu item in will result in the generation of the Active Path shown in .

Selection of an end link will cause the immediate execution of the associated function last function executed . Thus the last executed function may be re executed by simply selecting the end link in the Active Path .

As described above the Active Path is dynamically constructed as the user navigates the collapsing menu system and is subsequently retained after the menu tree collapses back to the root level. In addition the Active Path may optionally be constructed each time a short cut such as a function key or the like is used. This requires the use of a look up table stored in RAM . The look up table stores each of the pre defined shortcuts and the associated data necessary to create the active path . According to a presently preferred embodiment the Active Path constructed is the same as would be constructed by accessing the function through the collapsing menu system.

In operation the look up table would originally be created by the software developer during initial definition of each of the pre defined short cuts function keys . Moreover as will be explained the look up table may be updated by the user to reference newly created short cuts.

According to a further aspect of the present invention the Active Path may be used to define a short cut on the fly. Once the Active Path has been constructed for example by navigating the conventional collapsing menu system the user may store the end link as a shortcut within the lookup table . According to a presently preferred embodiment this is accomplished by a combination of commands. Thus for example the user could be prompted to define a short cut identifier by clicking mouse button over end link . The Active Path then stores the association between the function or location and the user selected shortcut in the rewriteable table

As noted previously the Active Path of the present invention may similarly be used to navigate to a location. Notably the Active Path is created in the same manner regardless of whether the menu items are functions or locations. The difference in using the Active Path to navigate to locations arises after the Active Path has been generated when the user selects an active link . More particularly the difference is only manifested if the selected active link is not the end link .

Notably in the case of navigating to a location selecting an active link other than the end link triggers the access of the associated location. In contrast when navigating to a class of functions selection of an active link other than the end link merely triggers the display of the sibling menu items on the associated level. See .

By manner of illustration shows a user selecting a location by manipulating the pointing device to position the pointer over and actuating the mouse key or . As shown the selection of a location results in the creation of a new active path .

One of ordinary skill in the art will appreciate that the Active Path of the present invention may be used in standalone applications such as operating systems word processors spreadsheets or the like. Moreover the Active Path may also be used in a client server environment. Notably the Active Path may be used to navigate functions provided on a web site or to navigate between different web addresses.

In standalone applications a range of Windows Application Programming Interface functions such as CreateWindow and other graphics library function calls may be used to create the graphic components of the Active Path. Any combination of mainstream programming languages such as Visual Basic Java C or Delphi may be used to create the dynamic components and rollover effects.

In client server applications the code for the Active Path may be part of the initial HTML file in form of a JavaScript DHTML combination or separate JavaScript files .js containing the arrays describing the Active Path and Cascading Style Sheets files .css containing the graphic attributes of the Active Path . This data may be cached locally after the initial server call.

For internet browser applications such as Internet Explorer or Mozilla the referred embodiment foresees a replacement of the address bar with the Active Path to avoid redundancy allow the user to focus on the content and make browsing more efficient. For Internet Explorer this would involve utilizing its custom Explorer Bars integration feature.

In standalone applications a range of Windows Application Programming Interface functions such as CreateWindow and other graphics library function calls may be used to create the graphic components of the Active Path. Any combination of mainstream programming languages such as Visual Basic Java C or Delphi may be used to create the dynamic components and rollover effects.

Windows Explorer may replace the Address Bar with the Active Path. This could make the display of the folder window redundant. The user may better take advantage of the screen real estate by rolling over and browsing through the levels of the collapsing menu system.

In client server applications the code for the Active Path may be part of the initial HTML file in form of a JavaScript DHTML combination or separate JavaScript files .js containing the arrays describing the Active Path and Cascading Style Sheets files .css containing the graphic attributes of the Active Path. This data may be cached locally after the initial server call.

For internet browser applications such as Internet Explorer or Mozilla the preferred embodiment foresees a replacement of the address bar with the Active Path to avoid redundancy allow the user to focus on the content and to make browsing more efficient. For Internet Explorer this would involve utilizing its custom Explorer Bars integration feature.

The Active Path of the present invention may also be used to navigate audio interfaces. A preferred embodiment for audio interfaces would allow users to navigate to the end point of a path. A certain input command such as pressing a certain key would read the sequence and level of the selected path. Users can then select any level of the path and navigate to a new endpoint.

Although a preferred embodiment of the Active Path navigation system of the present invention has been specifically described and illustrated it is to be understood that variations or alternative embodiments apparent to those skilled in the art are within the scope of this invention. Since many such variations may be made it is to be understood that within the scope of the following claims this invention may be practiced otherwise than specifically described.

