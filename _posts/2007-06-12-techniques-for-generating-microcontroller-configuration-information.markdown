---

title: Techniques for generating microcontroller configuration information
abstract: A method and apparatus for configuring a microcontroller. An XML description of the microcontroller's hardware resources may be accessed. A user may select from available hardware resources and pre-defined user modules to select a configuration. Configuration information, which may include register bit patterns and microprocessor instructions, may be automatically generated. Additionally, application programming interface calls and structure, as well as interrupt vector tables may be automatically generated. Embodiments of the present invention provide improved ease of use and the ability to manage greater complexity in the configuration of configurable microcontrollers.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08069428&OS=08069428&RS=08069428
owner: Cypress Semiconductor Corporation
number: 08069428
owner_city: San Jose
owner_country: US
publication_date: 20070612
---
This is a continuation of application Ser. No. 10 002 726 filed Oct. 24 2001 now U.S. Pat. No. 7 406 674.

Embodiments of the present invention generally relate to the field of microcontrollers. More specifically embodiments of the present invention pertain to a method and apparatus for generating the configuration information for microcontrollers.

Microcontrollers function to replace mechanical and electromechanical components in a variety of applications and devices. Microcontrollers have evolved since they were first introduced approximately 30 years ago to the point where they can be used for increasingly complex applications. Some microcontrollers in use today are also programmable expanding the number of applications in which they can be used.

However even though there are a large number of different types of microcontrollers available on the market with a seemingly wide range of applicability it is still often difficult for a designer to find a microcontroller that is particularly suited for a particular application. Unique aspects of the intended application may make it difficult to find an optimum microcontroller perhaps necessitating a compromise between the convenience of using an existing microcontroller design and less than optimum performance.

In those cases in which a suitable microcontroller is found subsequent changes to the application and new requirements placed on the application will likely affect the choice of microcontroller. The designer thus again faces the challenge of finding a suitable microcontroller for the intended application.

One solution to the problems described above is to design or have designed a microcontroller customized for the intended application. However this solution may still not be practical because of the time needed to develop a custom microcontroller and the cost of doing so. In addition should the design of the intended application be changed it may also be necessary to change the design of the custom microcontroller further increasing costs and lead times. Moreover the option of designing a custom microcontroller is generally only available to very large volume customers.

Application specific integrated circuits ASICs may suggest a solution to the problem of finding a suitable microcontroller for an application. However ASICs can also be problematic because they require a sophisticated level of design expertise and the obstacles of long development times high costs and large volume requirements still remain. Solutions such as gate arrays and programmable logic devices provide flexibility but they too are expensive and require a sophisticated level of design expertise.

In an effort to overcome some of these disadvantages some microcontroller suppliers for example Cypress MicroSystems in Bothell Wash. have started to offer standard parts that combine a microprocessor with several user configurable building blocks. These building blocks may be configured to form many standard microprocessor peripherals as well as to form unique peripherals as may be required by a specific application. Thus a user of such products may be able to tailor or configure such a standard product to meet his specific microcontroller requirements in less time and at less cost than through other means.

Unfortunately the process by which such configurable blocks are configured is burdensome. The configurable blocks are designed to have wide application. As such configuration generally involves setting a large number of bits in a specific sequence in order to define a specific function and interconnection with other blocks.

Many existing microcontrollers also have numerous configuration settings. For example it is not unusual for a given input output port to be designed such that it is either input or output and it may further have a selectable pull up resistor.

In the prior art the configuration process for both standard microcontrollers and configurable microcontrollers has been similar. A designer would study the device s information data sheets and manually determine the value and order of a long string of bits that would create the desired configuration. Subsequently this string would be encoded into microprocessor instructions for execution during the early stages of operation or initialization of the system.

In a very few instances when a microcontroller has found very high acceptance in a particular application high level tools have been created to support that particular microcontroller in that particular application. In such cases a standard configuration is used and various software tools are built based on the standard configuration.

Unfortunately in most design situations calling for a microcontroller this is not the case. Configuration has been for the most part a labor intensive manual process. Further changes in the hardware configuration tend to ripple though to the higher level software requiring changes and recompilation of application software as well as in any software tools designed to ease the development process. In effect if the microcontroller hardware changed the software had to change. Not just the application specific software but also the software tools such as compilers had to change.

Therefore it would be advantageous to provide a method and system for the automatic generation of configuration information. A further need exists for a text readable description of the hardware resources of a microcontroller. A still further need exists for the use of open standards in describing configurable hardware.

Embodiments of the present invention provide a method and system for the automatic generation of configuration information. Further embodiments of the present invention provide for a text readable description of the hardware resources of a microcontroller. Still further embodiments of the present invention may use eXtensible Markup Language an open standard to describe configurable hardware.

A method and apparatus for configuring a microcontroller is disclosed. An XML description of the microcontroller s hardware resources may be accessed. A user may select from available hardware resources and pre defined user modules to select a configuration. Configuration information which may include register bit patterns and microprocessor instructions may be automatically generated. Additionally application programming interface calls and structure as well as interrupt vector tables may be automatically generated.

Another embodiment of the present invention may access predetermined configurations of a microcontroller s hardware resources.

In one embodiment of the present invention a microcontroller having a number of configurable building blocks may be automatically configured.

In another embodiment of the present invention user selected configuration choices are combined with predetermined configurations to automatically generate configuration information.

In yet another embodiment of the present invention user configuration selections are checked against the hardware description for validity.

In still another embodiment of the present invention a user may edit configurable parameters within a computer implemented graphical user interface.

Embodiments of the present invention provide improved ease of use and the ability to manage greater complexity in the configuration of configurable microcontrollers.

Therefore these and other objects and advantages of the present invention will become obvious to those of ordinary skill in the art after having read the following detailed description of the preferred embodiments that are illustrated in the various drawing figures.

In the following detailed description of the present invention method and apparatus for generating microcontroller configuration information numerous specific details are set forth in order to provide a thorough understanding of the present invention. However it will be recognized by one skilled in the art that the present invention may be practiced without these specific details or with equivalents thereof. In other instances well known methods procedures components and circuits have not been described in detail as not to unnecessarily obscure aspects of the present invention.

Some portions of the detailed descriptions which follow e.g. process are presented in terms of procedures steps logic blocks processing and other symbolic representations of operations on data bits that can be performed on computer memory. These descriptions and representations are the means used by those skilled in the data processing arts to most effectively convey the substance of their work to others skilled in the art. A procedure computer executed step logic block process etc. is here and generally conceived to be a self consistent sequence of steps or instructions leading to a desired result. The steps are those requiring physical manipulations of physical quantities. Usually though not necessarily these quantities take the form of electrical or magnetic signals capable of being stored transferred combined compared and otherwise manipulated in a computer system. It has proven convenient at times principally for reasons of common usage to refer to these signals as bits values elements symbols characters terms numbers or the like.

It should be borne in mind however that all of these and similar terms are to be associated with the appropriate physical quantities and are merely convenient labels applied to these quantities. Unless specifically stated otherwise as apparent from the following discussions it is appreciated that throughout the present invention discussions utilizing terms such as indexing or processing or computing or translating or calculating or determining or scrolling or displaying or recognizing or generating or accessing or selecting or tracking or displaying or informing or editing or adding or the like refer to the action and processes of a computer system or similar electronic computing device that manipulates and transforms data represented as physical electronic quantities within the computer system s registers and memories into other data similarly represented as physical quantities within the computer system memories or registers or other such information storage transmission or display devices.

This application makes reference to co pending commonly owned U.S. patent application Ser. No. 10 033 027 filed Oct. 22 2001 entitled Microcontroller System on a Chip which is hereby incorporated herein by reference in its entirety.

The present invention is described in the context of development tools for designing with embedded microcontrollers. However it is appreciated that the present invention may be utilized in other types of computer aided hardware and software design systems for example compilers where it may be necessary to describe various resources.

Traditional microcontrollers have a fixed set of digital and or analog peripherals. Many of these peripherals may have configurable parameters. For example a universal asynchronous receiver transmitter UART may have provision for several user selectable configurations. These may include a choice of baud rates clock sources internal or external number of stop bits parity even odd or none etc. However all such configuration parameters apply to the same function that of UART. Such a fixed peripheral generally may not be reconfigured to perform a completely different function for example a display controller.

A new class of microcontroller provides an analog and or digital subsystem comprising many dynamically configurable blocks. An example of such a device is the CY8C25x 26x family commercially available from Cypress MicroSystems of Washington. These blocks do not in general provide the equivalent function of a traditional microprocessor peripheral. They may be thought of as fundamental building blocks. However these blocks may be combined to create such functions. In further contrast to the fixed peripherals of a traditional microcontroller these blocks may be recombined in a different combination to perform a different function.

Importantly these different combinations of blocks producing different functions may exist at different times within the same system. For example a set of blocks configured to perform the function of analog to digital conversion may sample a signal. After processing that signal in the digital domain those same blocks perhaps in conjunction with a few others may be recombined in a different configuration to perform the function of digital to analog conversion to produce an output signal.

The present invention provides a method and system for managing the configuration of and generating configuration information for both traditional microcontrollers with configurable peripherals and this new class of microcontrollers with dynamically configurable blocks.

In step a description of the hardware resources may be accessed. This description may include a definition of the underlying hardware i.e. what peripherals or configurable blocks are available and the configurable parameters that must be set to operate. In a preferred embodiment of the present invention the underlying hardware is described in well understood names versus mnemonics e.g. conversion complete interrupt versus INT6. It is appreciated that other well known naming conventions are well suited to embodiments of the present invention.

In a preferred embodiment this description is a data set which may be contained in a plurality of files substantially compliant with eXtensible Markup Language or XML.

XML is a well known open standard and is text based. As a text based structure a wide variety of computer tools may be used to create and edit such a description. Being text based it is also compatible with the widest variety of network transmissions and can be easily transferred between computers having different character set descriptions such as ASCII and EBCDIC. Descriptions having non text characters may be more limited in their applications.

It is appreciated however that embodiments of the present invention are well suited to other well known data formats.

In an embodiment of the present invention a separate software tool accesses the descriptive data set. A significant benefit of separating the data set from the software tool is that the software tool does not have to change e.g. re writing or recompiling if the hardware changes. Only the data set needs to be modified to reflect such a change. Changes to a text based data file are significantly less complex than changes to executable software.

Additional benefits derive from this arrangement as well. For example supporting new hardware may only require the mere addition of new files into a module library directory . Additionally the hardware description files may be used across a variety of computer platforms and operating systems. Further since the software tool isn t changing with each new or modified piece of hardware engineering resources may be dedicated to increasing the quality of the software rather than supporting new functionality.

This description may also include lists of standard configurations that have been predetermined either by the users or the manufacturers to be useful. Such a configuration in a traditional microcontroller might be RS 232 9600 baud which would be a set of bit patterns to configure the fixed function UART to select the appropriate clock source stop bits parity etc. for this standard form of communication.

Similarly a standard configuration of configurable blocks might be an analog to digital converter labeled 6 bit ADC. This standard configuration would combine analog and digital blocks to produce a six bit analog to digital converter.

We label such standard configurations as user modules and such user modules may be defined in the description of hardware resources.

Still referring to in step a user typically interacting with a computer implemented design tool may select from available configurations including user modules and other capabilities of the microcontroller hardware to produce a desired configuration.

In a preferred embodiment of the present invention the design tool may track resources as they are assigned providing feedback to the designer such as available blocks and user modules. It is appreciated that such feedback is not required in embodiments of the present invention.

In step the bit patterns corresponding to the selected configuration may be automatically generated. In optional step microprocessor instructions may be generated which when executed cause the hardware to be configured according the selected configuration.

In optional step application programming interface API call structures may be automatically generated. Such APIs may correspond to user modules. For example using the previous example of 6 BIT ADC an API call might take the form of GET6 BIT ADC VALUE. Using meaningful names in such an automatically generated structure is more useful to human designers who must maintain the software than pseudo random unique names generated by computer processes such as ZYX 1. Microprocessor instructions required to perform this task and return the value to the calling software may be automatically generated.

In optional step an interrupt vector table may be automatically generated. Again using the example of 6 BIT ADC instructions to set the conversion complete interrupt to level may be automatically generated. Further instructions to initialize the interrupt vector corresponding to level may be automatically generated and a shell for the interrupt service routine may be automatically created. Finally since this example also includes an API the shell software may be completed to for example read the result register from the 6 BIT ADC and place that value on the stack to be passed back to the calling program.

Computer system also optionally includes a data storage device e.g. a rotating magnetic disk coupled with the bus for storing information and instructions.

Also included in computer system of is an optional alphanumeric input device . Device can communicate information and command selections to the central processor . Device may take the form of a touch sensitive digitizer panel or typewriter style keyboard. Display device utilized with the computer system may be a liquid crystal display LCD device cathode ray tube CRT field emission device FED also called flat panel CRT light emitting diode LED plasma display device electro luminescent display electronic paper or other display device suitable for creating graphic images and alphanumeric characters recognizable to the user. Optional signal input output communication device is also coupled to bus .

System optionally includes a radio frequency module which may implement a variety of wireless protocols for example IEEE 802.11 or Bluetooth.

Microcontroller system may contain microcontroller . Microcontroller may execute instructions stored within memory elements of microprocessor system to configure configurable elements of microcontroller system including analog SoCblocs Digital SoCblocs programmable interconnect and configurable I O transceivers . Configuration information for these configurable elements may have been generated by embodiments of the present invention.

Microcontroller system may include analog SoCblocs . SoC is a trade name of Cypress MicroSystems of Washington for System on a Chip and refers to an architecture of low level building blocks for creating a wide variety of on chip functions associated with a microcontroller. Analog SoCblocs may be an array of such low level building blocks designed to implement analog functions. Similarly digital SoCblocs may be an array of low level building blocks designed to implement digital functions.

Programmable interconnect may be an array of configurable multiplexing elements designed to interconnect low level building blocks together and with other system resources. Configurable I O transceivers allow signals created or accessed by configurations of building blocks to communicate off chip.

User Module Selection Bar may display the User Modules selected for the current project. The instance name for the User Module may be shown below the icon in User Module Selection Bar . The instance name can be changed at any time before code generation.

Block Diagram and Data Sheet correspond to the User Modules highlighted in the User Module catalog window . Block Diagram may provide a block diagram of the highlighted user module and may indicate configurable elements of the user module.

Data Sheet may display a detailed datasheet for the selected user module as would have been contained in a data book or accessed via the world wide web in prior art systems. In this manner a designer has immediate access to detailed engineering information regarding the selected user module without having to refer to a printed book or open an interne browser window which may obscure his work.

Embodiments of the present invention may be configured to allow only User Modules that are seen in the User Module Selection bar to be placed during User Module placement.

Resource assignment window may display the total resources available in a particular device and a summary of the resources used as they are placed into the design. Resource assignment window may display a summary of resources used assigned in numerical and or bar graph formats. Resource assignment window may further change the color of the graph for example to yellow to indicate that a specific resource for example digital blocks are almost used up. In addition resource assignment window may display the graph in yet another color for example red to indicate that all available resources of a particular type have been used.

User Module placement display may include placement pane . Placement pane may display a graphical representation of placed blocks and signal routings. The graphical placement and routing may correspond to the physical placement of such blocks on an integrated circuit or the graphical placement and routing may correspond to simplified renderings of the microcontroller architecture.

Placed User Modules may have colored rectangles around their icons in the User Module Selection Bar and one or more blocks in the Placement Pane may be colored with the same color. The instance name and block name will also be shown on the corresponding blocks. Embodiments of the present invention may be configured to allow only placed User Modules to be parameterized and included in application generation.

User Module placement display may also include global resources window that displays a list of the global resources available in the chosen device.

User Module placement display may further include user module parameters window that displays a list of configurable parameters for the user module selected in user modules selection bar . In this example there are no user configurable parameters for the selected user module TX81. 

When the mouse or other pointing device causes a cursor indicator not shown to move within the active area of a parameter for example parameter text area the cursor may change to a horizontal Dual In line Package DIP shape. If the cursor is left over the active area for about one second then a tool tip may appear showing the name of the parameter and its value.

The parameter value may be shown in the active area of the parameter immediately above the line for example parameter area . If the parameter value has not yet been set then the line may be rendered in an indicator color for example red and a question mark may be displayed in place of the parameter value. The question mark may also be displayed in the same indicator color.

The CLOCK parameter may always map to an area in the upper left corner of the block . Embodiments of the present invention may be configured so that there is only one parameter whose TYPE attribute is set to CLOCK in any one PSoC block within any User Module. The CLOCK parameter does not have a text block similar to parameter text area but shows the triangle symbol within the block .

The INPUT parameters including parameter text area appear in the lower left area of the block . A maximum of 2 inputs can be shown on a block. The text may always be shown as In 0 or In 1 that are assigned in alphabetical order of the INPUT parameters. If only one INPUT parameter is defined for a particular block then that input will appear at the bottom of the block and be shown as In 0. 

The INPUT MUX parameter is a special case parameter that may cause the line to be drawn between the top row of analog PSoC blocks the ANALOG CT blocks and the Pin Input MUX control above them. The INPUT MUX parameter does not have a bitfield associated with it so the BITFIELD attribute should be set to NONE. Consequently an INPUT MUX parameter will not appear in the Parameter Pane. The value shown next to the line is controlled by the Pin Input MUX control above. The INPUT MUX parameter must only be used with ANALOG CT blocks.

The OUTPUT parameters appear in the lower right area of the block. A maximum of 2 outputs can be shown on a block. The text may be always shown as Out 0 or Out 1 that are assigned in alphabetical order of the OUTPUT parameters. If only one OUTPUT parameter is defined for a particular block then that parameter will appear at the bottom of the block and be shown as Out 0. 

The OUTPUT0 and OUTPUT1 parameters are similar to the OUTPUT parameter except that the position of each parameter type is fixed in the block and the line outside the block is extended to connect to one of the two bus lines to the right of the blocks. The OUTPUT0 parameter appears in the upper output position and the line extends to the comparator bus line. The OUTPUT1 parameter appears in the lower output position and the line extends to the analog bus line.

The OUTPUT0 HIDDEN and OUTPUT1 HIDDEN parameters are similar to the OUTPUT0 and OUTPUT1 parameters except that the  HIDDEN implies that the parameter value itself is not made available to the GUI. For these parameters the lines are drawn to the respective bus line but the text block within the block and the parameter value may not be shown.

The syntax of XML files follows other mark up languages in that it consists of tags which represent elements. Elements can contain attributes and in turn attributes have values. All names in XML files whether they are tag names attribute names or attribute values are case sensitive.

The user module description may contain data including user module resource requirements interconnection details parameter description and API code generation substitutions. Ultimately the user module description may define registers which are divided into bitfields. Bitfields may be set according to User Module placement and parameterization thereby setting registers. The bitfields are associated with resources which are presented to the user for example in screen detail . The resources are also how the GUI and the User Module XML file access the bitfields.

The specific device description files reference the base device description file and may define the pins that are available on the part and the RAM and ROM that is available on the part. The specific device description files also cover all parts that share a common package type insomuch as the package falls into a similar category for example 28 pin dual inline package or 44 pin TQFP. Whether the part is DIP or TSOP does may not distinguish it as a distinct part description. In other words if a part shares a common pinout including total pin count with another part then it may share a specific device description file.

According to an embodiment of the present invention the values of some of the attributes in user module description are controlled by the names used in the Device Description XML files while others are controlled by the elements and attributes in the User Module XML file itself. Each User Module XML file may contain the specifications for one and only one User Module. From the root node the User Module XML file may contain one and only one element. The element can contain a multiplicity of elements for example but generally will contain only one. The element may have the following attributes as described below.

A NAME attribute may be the name of the User Module. A TYPE attribute may be the enumerated type of User Module. HTML attribute may be the name of file containing a User Module data sheet for example data sheet in . The ICON attribute may be the name of file containing a User Module icon graphic. METAFILE attribute may be the name of file containing User Module block diagram. API PATH TYPE attribute may be the XML file path relative to other files. RAM attribute may be the amount of RAM used by the User Module API. ROM attribute may be the amount of ROM used by the User Module API.

The NAME attribute is the reference for the User Module used by the Device Editor. It is also the name that appears in under the icon in the User Module Catalog on the User Module Selection view.

The TYPE attribute is an enumeration that places the User Module in a category. The User Modules types serve to partition the User Modules onto the different Outlook bars in the User Module catalog.

The HTML ICON and METAFILE attributes relate to the other files used in the User Module Selection view. All of these attribute values are the literal file names that must include the extension. The HTML attribute specifies the data sheet file that is displayed in the Data Sheet area of the view. The METAFILE attribute specifies the extended metafile that contains the User Module block diagram. The block diagram appears in the Block Diagram pane of the User Module Selection view. The ICON attribute specifies the file containing the User Module icon. The icon is used in the User Module Catalog pane and the User Module Selection Bar.

The RAM and ROM attributes are the values used to determine the resource usage for the User Module. The values of the RAM and ROM attributes are subtracted from the total amount available on the device when the User Module is selected. The resource usage gauge in the configuration tool tracks the RAM and ROM usage for the User Modules selected in the current configuration.

The API PATH TYPE attribute specifies the relative path between the User Module XML file and the other files. With the current library scheme all User Modules should be set for CUSTOM. The other value NORMAL is not used or the attribute should not be included.

The element for example element specifies the PSoC blocks and the resources required by the User Module and establishes some reference names for use in other parts of the User Module description. The element has only a SHAPE TYPE attribute. The SHAPE TYPE attribute may be set to BLOCK LIST.

The element describes a collection of PSoC blocks that are connected between blocks within the element. When multiple elements are included within a element each is placed on the device PSoC blocks independently. Connections between PSoC blocks from distinct elements can exist through resources identified in the element.

The has no attributes and consists of several elements for example element . The elements specify the following information Block name the type of block required Block interrupt generation Block personalization and Block interconnection.

The element may have the attributes described below. NAME attribute may be the block reference name. The TYPE attribute may be the enumerated PSoC block type. The INTERRUPT SOURCE attribute may be the block interrupt handler name. The INTERRUPT TYPE attribute may be the enumerated interrupt calling type.

The NAME attribute is a local name that identifies the block within the User Module description. The NAME must be unique within a User Module but similar names can be used in different User Modules. The NAME attribute value appears in the GUI in the User Module Placement view. When a User Module is placed the PSoC blocks onto which the User Module is placed show the instance name of the User Module with the local name directly under it.

The TYPE attribute specifies the type of PSoC block that the User Module requires. The valid values for the TYPE attributes include DIGITAL DIGITAL COMM ANALOG CT ANALOG SCA ANALOG SCB and ANALOG SC.

The difference between this list and the PSoC block types used in the device description is the addition of the ANALOG SC type in the User Module description. The ANALOG SC block type indicates that the specified block can be placed on an ANALOG SCA or an ANALOG SCB block. Similarly a DIGITAL block type can be placed on a DIGITAL or a DIGITAL COMM block.

The INTERRUPT SOURCE and INTERRUPT TYPE attributes relate to an interrupt handler associated with the PSoC block. If an interrupt handler is not associated with the PSoC block then the INTERRUPT SOURCE and INTERRUPT TYPE attributes should not be included in the element. The INTERRUPT SOURCE attribute value is a name that is used to generate the interrupt handler name. The INTERRUPT SOURCE attribute value is appended to the User Module instance name to form the interrupt handler name. The INTERRUPT TYPE attribute specifies whether a LJMP long jump or a CALL to subroutine is used when calling the interrupt handler from the vector table.

The element for example element may specify the PSoC block personalization. The bitfield values set in this element are set on the PSoC block where the User Module is located.

The consists of one or more elements for example element . The element may have a NAME attribute and one element. The NAME attribute value must match one of the names of the registers in a PSoC block of similar type contained in the element of the device description.

The for example consists of one or more elements. The elements for example element may have NAME and VALUE attributes. The bitfield NAME attribute must be one of those included in the of a block of similar type contained in the of the device description. Similarly the VALUE attribute must be a value that is valid for the specified bitfield as defined in the device description.

The element for example of specifies the interconnection between blocks and resources within the User Module description. The element has no attributes and consists of one or more elements. The element specifies a connection between the block and another block or resource within the User Module description. The relevance of an element is that a connection with another PSoC block or resource on the device implies that a bitfield within the block registers must be set to a particular value.

The element may have the attributes described below. The SOURCE attribute may be the name of the resource or PSoC block that is the source of the input. The TYPE attribute may be an enumeration of the type of the SOURCE either BLOCK or RESERVED RESOURCE. The BLOCK TYPE attribute may be an enumeration of the type of the block on which the block is placed either ANALOG SCA or ANALOG SCB. The REGISTER NAME attribute may be the name of the register within the block containing the relevant bitfield. The BITFIELD attribute may be the name of the bitfield associated with the input.

The BLOCK TYPE attribute is only relevant when the TYPE of the element is ANALOG SC. In this case the bitfield for a connection may vary depending on whether the element was placed on an ANALOG SCA or an ANALOG SCB block. If the bitfield is different then distinct elements specifying both cases must be included in the element for that element.

The REGISTER NAME attribute specifies the NAME attribute of the element in the element of the that contains the relevant bitfield. If the bitfield name is unique then the REGISTER NAME can be omitted but it is better practice to always include it.

The BITFIELD attribute value specifies the NAME attribute of the element that is associated with the input.

The element for example element of specifies the resources that the User Module requires. The User Module uses resources to enable parameterization enable connection between blocks or restrict placement options. There may be only one element in a element. The one element contains all resources used by the User Module.

A consists of one or more elements. The element specifies the type of resource and connections from other blocks or resources in the User Module description. The element may have attributes as described below.

The NAME attribute defines the reference name for the resource within the User Module. The TYPE attribute specifies the type of resource required. Valid values for TYPE may include COLUMN INPUT ANALOG COLUMN CLOCK MUX ANALOG CLOCK SELECT ANALOG DRIVER GLOBAL BUS ANALOG COMPARATOR OUTPUT ANALOG COLUMN OUTPUT ANALOG COMPARATOR CONTROL DECIMATOR ANALOG MODULATOR PIN TEMPERATURE VOLTAGE and DIRECT INPUT.

The element contains an element for example element of . The elements within the are similar to the element in the element. The element for resources may have the following attributes.

The SOURCE attribute may be the name of the resource or PSoC block that is the source of the input. The TYPE attribute may be an enumeration of the type of the SOURCE either BLOCK or RESERVED RESOURCE. The REGISTER NAME attribute may be the name of the register within the block containing the relevant bitfield. The BITFIELD attribute may be the name of the bitfield associated with the input.

In many cases the resource does not have a register associated with it. In these cases the BITFIELD attribute is set to NONE and the REGISTER NAME attribute can be omitted.

The element for example element of exposes bitfields to the GUI to allow the user to set their values. The element associates the parameter with a bitfield defines in the User Module shape. The values shown for the parameters are controlled by the bitfield values or a element. The value list can also be limited with an element. If a parameter has an ambiguous SOURCE in terms of block type then it is possible that the bitfield associated with the parameter has a different name depending on block placement. For example if the SOURCE block is TYPE ANALOG SC then some of the registers have different names for the same bitfield in an ANALOG SCA block as opposed to an ANALOG SCB block. In this case a parameter should be specified for both block types based on the unique register names. When the block is placed the parameter that does not apply will disappear.

The element may contain at least one elements. The element may have the following attributes. The NAME attribute may be the name of parameter. The TYPE attribute may be the enumeration of parameter type. The SOURCE attribute may be the name of PSoC block or resource containing the bitfield associated with the parameter. The REGISTER NAME attribute may be the name of the register containing the bitfield associated with the parameter. The BITFIELD attribute may be the name of the bitfield associated with the parameter. The ORDER attribute may be the order that the parameters appear in the list. The VALUE attribute may be the default value. The VALUE TYPE attribute may be ENUM or INT. The default value is ENUM if attribute is missing. The MN attribute may apply only to VALUE TYPE INT which is the minimum inclusive parameter value. The MAX attribute may apply only to VALUE TYPE INT which may be the maximum inclusive parameter value.

The NAME attribute may be the reference name for the parameter within the User Module. In the User Module Placement view the NAME attribute is the name that appears in the Parameter Pane grid control. The ORDER attribute determines the order that the parameters appear where the ORDER 0 parameter is at the top with the remaining parameter listed down in ascending order. If the ORDER attribute is not specified then the parameters are listed in alphabetical order.

The SOURCE REGISTER NAME and BITFIELD attributes specify the PSoC block or resource and the bitfield in the shape that contains the bitfield associate with the parameter. The SOURCE must be set to a NAME included in the element of a element or of a element. The REGISTER NAME and BITFIELD attributes must also be included in the or element. A special keyword for the SOURCE attribute is ALL DIGITAL. If the SOURCE for a parameter is set to ALL DIGITAL then the parameter applies to a similar bitfield for all digital PSoC blocks defined in the User Module. This value can be used to set all clocks for the digital blocks to the same value.

The VALUE attribute specifies the default value for the parameter. In the case of a parameter that does not include a element the VALUE attribute must be included in the of the bitfield associated with the parameter. If a is included then the VALUE attribute value must be included in the element.

The TYPE attribute may be a UI helper that controls the appearance of parameters on the PSoC blocks in the Placement Pane. When a User Module is placed on to the PSoC blocks some of the parameters may be shown on the blocks. When parameters are shown on the PSoC blocks then they may be set from the Placement Pane by clicking on the active area for the parameter on the block as shown in the Parameter Block Selection screen. The enumerated values of the TYPE attribute determine where on the block the active area for the parameter is shown. The valid values for the TYPE attribute are described below.

The CLOCK attribute may be the clock selection parameter. The INPUT attribute may be the input parameter. The INPUT MUX attribute may be the special MUX input parameter. The INPUT HIDDEN attribute may be the hidden parameter for input. The BLOCK attribute may be the general block parameters. The BLOCK HIDDEN attribute may be hidden parameter for a block. The OUTPUT attribute may be the general output parameter. The OUTPUT0 attribute may be the output parameter to comparator bus. The OUTPUT1 attribute may be the output parameter to analog bus. The OUTPUT0 HIDDEN attribute may be the hidden parameter to comparator bus. The OUTPUT1 HIDDEN attribute may be the hidden parameter to analog bus. The API attribute may be the parameter not associated with any bitfields.

The preferred embodiment of the present invention a method and apparatus for generating microcontroller configuration information is thus described. While the present invention has been described in particular embodiments it should be appreciated that the present invention should not be construed as limited by such embodiments but rather construed according to the below claims.

