---

title: Game enhancer
abstract: A method, apparatus, computer program, and computer readable storage medium storing the computer program, is disclosed for generating a real-world description to operate a set of devices () to augment a user's experience of a game world. The game world is defined by a game world model, and parameters of the game world model are accessed by a first module being run within a protected computing environment. These parameters are sent to a second module running outside of the protected computing environment, and the second module uses these parameters to generate the real world description for controlling the set of devices.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08376844&OS=08376844&RS=08376844
owner: AMBX UK Limited
number: 08376844
owner_city: Redhill, Surrey
owner_country: GB
publication_date: 20070614
---
This application is a national phase application of and claims priority to PCT IB2007 052264 filed Jun. 14 2007 which claims priority to European Application No. 06115685.7 filed Jun. 19 2006 the disclosures of which are incorporated herein in their entirety for all purposes.

This invention relates to accessing parameters from computer game world models and operating a set of devices according to the parameters to augment the game experience.

When playing a computer game the user s experience of the game consists in most cases of the viewing of a simple display device while listening to the associated audio. Since the advent of computer games it has been desired to augment this user experience. A number of ways of achieving this have been proposed including head mounted displays surround screen installations and game peripherals such as rumble pads. The object of these functional improvements has been to increase the user s immersion in the game environment or game world model.

Applicant s International Patent Application Publication WO 02 092183 describes a real world representation system and language in which a set of devices are operated according to a received real world description and hence render a real world experience in the ambient environment of the user. For example the real world experience may be rendered by lighting devices that project coloured light onto the walls of the user s private dwelling by fan devices that simulate wind within the dwelling or by rumble devices that are embedded into the user s furniture to cause the user to feel vibrations. Hence an ambient immersive environment is created which is flexible scalable and provides an enhanced experience to a user.

Applicant s International Patent Application Publication WO 02092122 discloses a method of operating a set of devices according to a game world model. The method comprises receiving a signal comprising at least part of a game world model analysing the signal to generate a real world description in the form of an instruction set of a markup language and operating the devices according to the description to give real world effects in the ambient environment. The real world description is in the form of an instruction set of a markup language that communicates a description of physical environments and the objects within them their relationship to the user each other and to the physical space of the user s ambient environment. The instruction set of the markup language is interpreted and then one or more devices in the user s ambient environment are used to render the real world effects. These real world effects augment and enhance the user s experience of the computer game world. For example the user s character in the virtual computer game world may be standing in a forest on a summers evening and so the real world description might read . This description may be interpreted into specific instructions for controlling devices in the user s real world ambient environment such as to give a colour tone of a pleasant green and a light level of low but warm. Hence an environment in the virtual game world may be rendered in the user s real world ambient environment to provide an enhanced game playing experience.

To effectively augment the user s experience of the game the devices rendering the real world effects real world experience must be in close synchronicity with the events in the game world. For example if a lightening flash occurs in the game world the flash should immediately be reflected by the rendering devices e.g. by pulsing a light producing device . Hence changes in the game world must be reflected by immediate changes in the real world description being generated to operate the devices.

In order to generate the real world description it is desirable to access parameters of the game world model so that the state of the game world s virtual environment can be determined. However it is common for computer game applications programs to deliberately prevent other applications programs from having full access to the computer game application. Computer game applications commonly do this by defining a protected computing environment within which all applications wishing to gain access to the computer game application must be executed run .

Since the protected computing environment is defined by the computer game application the computer game application is able to restrict the functionality of the applications that are executed within the protected computing environment and hence restrict the functionality of the applications that are allowed to access the computer game application.

In the context of computer game applications the protected computing environment is usually implemented for security reasons to prevent third parties from creating applications that could modify the computer game s functionality in undesired ways and or to undesired extents.

Hence for many computer game applications the accessibility to game world model parameters to enable the rendering of real world experiences is greatly reduced or impossible.

Additionally applications being executed in the protected computing environment are often only allowed access to hardware devices that are specifically allowed by the computer game application. Hence applications being executed in the protected computing environment are unlikely to have access to hardware devices that can be used to render the real world experience.

Furthermore applications being executed in the protected computing environment typically do not have access to the level of computing power required to generate real world descriptions to operate devices in close synchronicity with changes in the game world.

According to a first aspect of the invention there is provided a method for generating a real world description to operate a set of devices to augment a user s experience of a computer game world the method comprising 

Accordingly it is possible to generate a real world description to operate a set of devices in close synchronicity with a game world thereby enhancing the user s experience of the game world despite the restrictions imposed by the protected computing environment.

Advantageously the second module running outside of the protected computing environment is not subject to the same restrictions to which the first module is subject. In particular the second module has access to greater computing power and may therefore generate real world descriptions in close synchronicity with changes in the virtual game world.

Furthermore the second module has access to the set of one or more devices for rendering the real world experience. Therefore the first and second modules together enable the creation of complex real world effects that can greatly improve a user s experience of a game world.

Applications that are run within a computer game s protected computing environment are often referred to as plug in applications. These plug in applications are often allowed access to a communication channel for sending data to other games via the internet for example for the purposes of multiplayer game playing as will be apparent to those skilled in the art.

Advantageously such a communication channel could be utilised by the first module not for the conventional purpose of communicating via the Internet with another computer game but for the purpose of sending game world model parameters to the second module for generating a real world description of the game world.

Conveniently the communication channel may use a protocol that is typically used for implementing multiplayer games over the internet such as TCP IP.

According to a second aspect of the invention there is provided an apparatus configured to generate a real world description to operate a set of devices to augment a user s experience of a computer game world the apparatus comprising 

Accordingly there is provided an apparatus for generating a real world description to operate a set of devices in close synchronicity with a game world thereby enhancing the user s experience of the game world. The communication channel is suitable for carrying data between the first and second modules for example data comprising computer game world model parameters.

According to a third aspect of the invention there is provided a computer program comprising program instructions for causing a processor to carry out the method of the first aspect of the invention.

According to a fourth aspect of the invention there is provided a computer readable storage medium storing the computer program of the third aspect of the invention.

At least one of the devices making up the system is arranged to receive a real world description in the form of an instruction set of a markup language the devices being operated according to said description. In this example this description augments a first person shooter computer game that a user is playing on computer . As different environments are encountered by the user s character in the game a description generated by computer is transmitted to the devices in the system. The devices then render this description onto the real world environment of .

For a full description of the aspects of operation of such a real world system and real world description language the reader is directed to published patent applications WO 02 092183 and WO 02 092122.

A second module is being executed outside of the protected computing environment and inter module communication between the first module and the second module is enabled via a communication channel .

At step the first module accesses parameters of the game world model by communicating with the game world engine via the API . The parameters are parameters that indicate the state of the game world and which may be useful for operating a set of devices to augment the user s experience of the game. For example the first module may access parameters indicating that a lightening flash is about to occur that a game character is about to be shot that the scenery surrounding the game player is dominated by green foliage or blue sky or that an explosion is in progress or any other factor reflecting the state of the game world. The first module may access parameters that relate to parts of the game world that are not currently within user s field of view of the game world. For example a monster creeping up behind the user s game world character may be reflected in the ambient environment by projecting a shadow onto the wall in front of the user similarly to as described in co pending patent application EP 05113363.8 Agent s reference PH002231 .

At step these parameters are sent from the first module to the second module via the communication channel . The first module may perform some processing on the accessed parameters before sending them to the second module for example so the parameters are received by the second module in a format that the second module understands.

Then at step the second module analyses the parameters received from the first module determines how the parameters should be reflected in the user s real world ambient environment and generates a real world description.

At step the real world description is provided to a set of devices such as lights rumble packs fans or speakers. The real world description is used by the set of devices to render real world effects that cause changes in the user s ambient environment to reflect the state of the game world and to augment the user s experience of the game.

In this embodiment the association between the game world engine and the protected computing environment is due to the protected computing environment being defined by the game world engine . In other embodiments the association may simply be due to the API or any other type of connection that is used for passing data between the game world engine and the first module within the protected computing environment.

In this embodiment the communication channel is provided using the TCP IP protocol although other protocols suitable for transferring game world model parameters between the first and second modules could also be used.

In this embodiment the API provides an interpreter function which the computer game world engine uses to interpret the program code of the first module . Hence in this embodiment the execution running of the first module within the protected computing environment is constituted by the interpretation or parsing of the first module s program code by the game world engine s interpreter function as will be apparent to those skilled in the art. In other embodiments the first module may be executed directly on the processor instead of via an interpreter function.

The real world description generated by the second module may be in the form of an instruction set of a markup language or it may be in the form of commands specifying how aspects of the user s ambient environment should be set.

In this embodiment the computing device is a personal computer PC the link from the second module to the controller is a cable and controller is implemented in a control box that transmits wireless signals for controlling devices D D and D.

In this embodiment the client is a PC and the server is a server that is accessible to the client via the Internet. This arrangement is advantageous since the server has greater computing power available for generating the real world description than the client has available. In this embodiment the communication channel and link are implemented as TCP IP links over the internet. The controller is embedded within the client device and the devices D D D for rendering the real world experience are connected to the controller via cables.

The memory stores the game world engine the first module and the second module . The memory may be formed by a single physical or logical memory or it may be stored by multiple physical or logical memories.

The processor executes the game world engine the first module and the second module . In this embodiment the first module is executed on the processor directly although in other embodiments the first module may be executed by an interpreter function of the game world engine. The processor may comprise multiple processing units such as a single physical processor with multiple processing cores or such as multiple physical processors that are distributed in a network.

The processor may comprise memory for storing the game world and the generated real world description or in other embodiments a further memory separate from the processor may be provided for storing the game world and the generated real world description.

The communication channel carries data between the first and second modules for example data representing game world model parameters.

In this embodiment the first and second modules take the form of software programs that are loaded into a memory and then executed by a processor although in other embodiments the first and or second modules may be in the form of hardware software or any combination thereof.

In summary there is disclosed a method apparatus computer program and computer readable storage medium storing the computer program for generating a real world description to operate a set of devices to augment a user s experience of a game world. The game world is defined by a game world model and parameters of the game world model are accessed by a first module being run within a protected computing environment. These parameters are sent to a second module running outside of the protected computing environment and the second module uses these parameters to generate the real world description for controlling the set of devices.

Other embodiments falling within the scope of the appended claims will also be apparent to those skilled in the art. For example there are many ways in which the various components of the invention discussed herein may be partitioned between physical logical devices and or connected to one another. Reference signs in the claims are not to be construed so as to limit the scope of the claims.

