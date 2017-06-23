---

title: Abstract interface for unified communications with dynamic models
abstract: A device may include a first type of modeling environment, a second type of modeling environment, and an abstract interface. The first type of modeling environment may be associated with at least one of a first toolbox or a first function. The second type of modeling environment may include a model. The second type of modeling environment may be different than the first type of modeling environment and may be incompatible with the at least one of a first toolbox or a first function. The abstract interface may interface with the first type of modeling environment and the second type of modeling environment. The abstract interface may allow the at least one of a first toolbox or a first function to be used in the model in the second type of modeling environment.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08220006&OS=08220006&RS=08220006
owner: The MathWorks, Inc.
number: 08220006
owner_city: Natick
owner_country: US
publication_date: 20070820
---
This application is a continuation of U.S. patent application Ser. No. 11 270 221 Now U.S. Pat. No. 8 127 311 entitled ABSTRACT INTERFACE FOR UNIFIED COMMUNICATIONS WITH DYNAMIC MODELS filed Nov. 9 2005 the entire disclosure of which is incorporated herein by reference.

The present invention relates to modeling environments for dynamic systems. More particularly the present invention relates to interfacing with models regardless of model type.

Many organizations are embracing the paradigm of Model Based Development in their production processes. Model Based Development refers to the practice of specifying analyzing and implementing systems using a common model containing a set of block diagrams and associated objects. System implementation typically involves automatically generating code for portions of the model particularly portions corresponding to the system s control algorithm.

Graphical modeling environments are an example of software applications that may enable a user to model dynamic systems i.e. systems whose outputs change over time using a graphical model such as a block diagram. Some graphical modeling environments also enable simulation and analysis of models. Simulating a dynamic system in a graphical modeling environment is typically a two step process. First a user creates a graphical model such as a block diagram of the system to be simulated. A graphical model may be created using a graphical user interface such as a graphical model editor. The graphical model depicts time based relationships between the systems inputs states parameters and outputs. After creation of the graphical model the behavior of the dynamic system over a specified time period is simulated using the information entered into the graphical model. In this step the graphical model is used to compute and trace the temporal evolution of the dynamic systems outputs execute the graphical model and automatically produce either deployable software systems or descriptions of hardware systems that mimic the behavior of either the entire model or portions of the model code generation .

Dynamic systems may also be modeled textually. In this methodology dynamic systems are described in an application specific language or code. Using this textual description the dynamic system may be simulated and analyzed. Simulating a dynamic system in a textual modeling environment is typically a two step process. First a user creates a textual model such as an M file or LTI model of the system to be simulated. A textual model may be created using a textual user interface such as a textual model editor. The textual model depicts time based relationships between the systems inputs states parameters and outputs. After creation of the textual model the behavior of the dynamic system over a specified time period is simulated using the information entered into the textual model. In this step the textual model is used to compute and trace the temporal evolution of the dynamic systems outputs execute the graphical model and automatically produce either deployable software systems or descriptions of hardware systems that mimic the behavior of either the entire model or portions of the model code generation .

There are many different techniques for modeling systems using different modeling environments. One problem with this is that a model created in one modeling environment may not be compatible with another modeling environment. As such toolboxes possessing tools and functions of interest for use with a model may not be compatible with the modeling environment the model was created in. Thus what is need is a simple convenient way of interfacing a model regardless of model type.

According to one aspect a device may include a first type of modeling environment a second type of modeling environment and an abstract interface. The first type of modeling environment may be associated with at least one of a first toolbox or a first function. The second type of modeling environment may include a model. The second type of modeling environment may be different than the first type of modeling environment and may be incompatible with the at least one of a first toolbox or a first function. The abstract interface may interface with the first type of modeling environment and the second type of modeling environment. The abstract interface may allow the at least one of a first toolbox or a first function to be used in the model in the second type of modeling environment.

According to another aspect a method may be implemented by one or more computing devices. The method may include receiving via an abstract interface that is configured to interface with a first type of modeling environment and a second type of modeling environment a call from a first toolbox to a model in the second type of modeling environment. The call may use at least one function that may be compatible with the first type of modeling environment and may be incompatible with the second type of modeling environment. The method may also include allowing via the abstract interface the at least one function from the first toolbox to be implemented in the model in the second type of modeling environment placing via the abstract interface the call to the model in the second type of modeling environment and receiving data from the model in the second type of modeling environment in response to placing the call to the model and the at least one function being implemented in the model.

According to a further aspect a computer readable medium may store instructions executable by at least one processor to perform a method. The computer readable medium may include one or more instructions for receiving an abstract interface from a remote device the abstract interface being configured to interface with a first type of modeling environment and a second type of modeling environment one or more instructions for receiving via the abstract interface a call from a first toolbox to a model in the second type of modeling environment the call using at least one function that is compatible with the first type of modeling environment and incompatible with the second type of modeling environment one or more instructions for allowing via the abstract interface the at least one function from the first toolbox to be implemented in the model in the second type of modeling environment and one or more instructions for placing the call to the model.

According to still another aspect a system may include means for receiving a call to a model in a first type of modeling environment. The call may use at least one function that is compatible with a second type of modeling environment and incompatible with the first type of modeling environment. The at least one function may cause one or more properties to be obtained from the model cause the model to be simulated and a response to be returned cause at least one Jacobian associated with the model to be obtained or cause the model to be at least one of trimmed or linearized. The system may further include means for allowing the at least one function to be implemented in the model in the first type of modeling environment and means for placing the call to the model.

An illustrative embodiment of the present invention is directed to creating a universal object class representation of a model which can be interfaced by a number of modeling environments. The present invention will be described relative to illustrative embodiments. Those skilled in the art will appreciate that the present invention may be implemented in a number of different applications and embodiments and is not specifically limited in its application to the particular embodiments depicted herein.

Typically the interaction of a human user with the computing device occurs through an input output I O device such as a graphical user interface GUI . The I O device may include a display device such as a monitor and an input device such as a mouse and a keyboard and other suitable conventional I O peripherals.

For example the memory holds a modeling application capable of creating and simulating digital versions of system models such as block diagrams state diagrams signal diagrams flow chart diagrams sequence diagrams UML diagrams dataflow diagrams circuit diagrams ladder logic diagrams kinematic element diagrams or other models which may be displayed to a user via the display device . In the illustrative embodiment the modeling application comprises a MATLAB modeling environment such as Simulink or another suitable modeling environment. As used herein the terms modeling environment and physical modeling environment refer to an application where a model such as a model of a physical system is created and translated into executable instructions. Examples of suitable modeling applications include but are not limited to MATLAB including Simulink SimMechanics and SimDriveline from the MathWorks Inc. LabVIEW DasyLab and DiaDem from National Instruments Corporation VEE from Agilent SoftWIRE from Measurement Computing VisSim from Visual Solutions SystemVIEW from Elanix WiT from Coreco Vision Program Manager from PPT Vision Khoros from Khoral Research and numerous others. The memory may comprise any suitable installation medium e.g. a CD ROM floppy disks or tape device a computer system memory or random access memory such as DRAM SRAM EDO RAM Rambus RAM etc. or a non volatile memory such as a magnetic media e.g. a hard drive or optical storage. The memory may comprise other types of memory as well or combinations thereof.

In an alternate embodiment the computing device is also interfaced with a network such as the Internet. Those skilled in the art will recognize that the diagrams used by the diagramming application may be stored either locally on the computing device or at a remote location interfaced with the computing device over a network. Similarly the diagramming application may be stored on a networked server or a remote peer.

The modeling application of an illustrative embodiment of the invention includes a number of generic components. Although the discussion contained herein focuses on MATLAB from The MathWorks Inc. of Natick Mass. those skilled in the art will recognize that the invention is applicable to other software applications. The generic components of the illustrative diagramming program include a model editor for specifying models of dynamic systems. The model editor allows users to perform such actions as construct edit display annotate save and print out a model that represents a physical system. The illustrative diagramming application also includes elements libraries that contain elements that may be combined to model systems. There may also be a graphical aspect that allows graphical modeling. An execution engine also implemented in the application is used to process a model to produce simulation results or to convert the model to executable code. The execution engine translates a model to executable entities. The executable entities are compiled and executed on a computational device such as a computer to implement the functionality specified by the model. Typically the code generation preserves a model hierarchy in a call graph of the generated code. For instance each subsystem of a model in a physical modeling environment can map to a user specified function and the generated code. Real Time Workshop from the MathWorks Inc. of Natick Mass. is an example of a suitable execution engine for generating code.

In the illustrative embodiment the modeling program is implemented as a companion program to a technical computing program such as MATLAB also available from the MathWorks Inc.

The model editor is the component that allows a user to create and modify a model representing a physical system. The model editor also allows a user to create and store data relating to model element . A textual interface with a set of commands allows interaction with the model editor. Using this textual interface users may write special scripts that perform automatic editing operations on the model. A user generally interacts with a set of windows that act as canvases for the model. There is generally more than one window for a model because models may be partitioned into multiple hierarchical levels through the use of subsystems.

Once a model has been constructed using the editor the execution engine simulates the model by solving equations defined by the model to trace the system outputs as a function of time. The solution of the model which may be referred to as model execution is carried out over a user specified time span for a set of user specified inputs.

These model equations can be implemented in an M file to be solved. Such an M file may contain code as shown below.

The Mass Spring Damper system of can also be modeled in a graphical modeling environment such as Simulink. An example of such a system can be seen in the block diagram of .

Alternatively to the M file or Simulink models the system of can be modeled as linear time invariant LTI object. Such a LTI object can be created using the following commands 

As can be seen from the above examples there are several ways to model a system. One of the problems with there being multiple techniques is that they are not necessarily compatible. As such toolboxes possessing tools and functions of interest may be compatible with one model but not another. For example Simulink Parameter Estimation SPE Simulink Response Optimization SRO and Simulation Control Design SCD toolboxes can only be used with Simulink models. Likewise the Control System Toolbox CST can only be used with LTI models. This presents a problem in that it may be desirable to use the features of a toolbox on a model the toolbox is not compatible with. Ideally it would be advantageous to be able to interface a model such as from a toolbox regardless of how the model was created.

The abstract interface allows for a model to be interfaced regardless of how it was generated. For each model type the implementation for the functions that interface with the toolbox are provided. As such a toolbox or modeling environment can access any type of model. An example of this can be seen in the diagram of . As depicted in this diagram various model types can be interface with a toolbox using the abstract interface . In certain instances a static model can also be interface for optimization and statistical analysis .

In certain embodiments the abstract interface is an application programming interface API . An API is a set of definitions of the ways one piece of computer software communicates with another. The API provides a set of routines protocols and tools for allowing communication between the software applications for example the model and toolbox. Using these routines protocols and tools the toolbox or modeling environment can interface with the model.

In one embodiment the abstract interface is implemented using a model object class. The model class defines an interface for communicating with various types of models that can be created in MATLAB including Simulink models SimBiology models and ODEs defined in M functions. Toolboxes can communicate with the models through the model class interface allowing the implementation of other model types.

The model class defines the properties for objects representing models. For example the class can define properties that are common for representations of all model types. These include field details constructor details and method details.

Field details include the version of the model. Other field details may be provided as necessary for specific models. Other suitable field details will be apparent to one skilled in the art given the benefit of this disclosure.

Constructor details set forth the call made by the abstract interface to create a model object. Examples of constructor details will be given below in reference to specific model types. Other suitable constructor details will be apparent to one skilled in the art given the benefit of this disclosure.

Method details include the methods functions and calls that are to be supported by an instantiated model object. A list of example methods that are to be implemented for all model types can be seen below 

The model class can also be extended for specific model types. For example the model class may be extended to a MLModel class. The MLModel class defines a concrete interface for communication with models defined in either M Files or Mex files. Mex files are used to implement model equation in compiled code such as Fortran or C. The MLModel class has all the properties of the model class plus some additional properties set forth below.

LinearizationPorts Object array of type MLLinearizationPortID containing information about the linearization I Os of the model.

Parameters Object array of type MLParameterID containing information about the parameters of the model.

The hierarchy of the model class to other classes including sub classes such as the MLModel class can be seen in . Other possible subclasses extended from the model class will be apparent to one skilled in the art given the benefit of this disclosure.

In some embodiments the abstract interface is further implemented using an identifier object class. As with the model class the identifier VariableID class can define properties that are common for representations of all model types. These include field details constructor details and method details.

In this example there are three main subclasses of the identifier class. These include the port identifier class PortID the parameter identifier class ParameterID and the state identifier class StateID . Each of these share the common properties of the Variable ID class plus additional properties.

The port identifier class PortID is an abstract class that defines an interface for objects representing the concept of inputs and outputs of a model. The inputs are the points where signals are injected into a model and the outputs are the points where signals of interest are measured and logged. These also include signals marked as linearization I Os. The classes derived from the PortID class need to implement the operations defined by the interface and are used by the Model objects to identify their inputs and outputs to interested client objects. In the context of parameter estimation the operations defined by the interface provide a mapping between the inputs and outputs of a model and the experimental data that is associated with them during estimations. For example each object storing transient data in SPE will keep a reference to an object derived from the PortID class to do this mapping.

Version The version number used by subclasses to handle backward compatibility issues in conjunction with their loadobj and saveobj methods.

getDimensions Returns a row vector of integer numbers corresponding to the dimensions of the signal at the port.

getFullName Returns the unique full name of the port. The full name of a port usually consists of a concatenation of its path and name and it uniquely identifies the port in the model.

getPath Returns the path to the port which is usually the full name of the sub system containing the port.

As with the model class the port identifier class portID can also be extended for specific model types. The hierarchy of the portID class to the VariableID and other classes can be seen in . Other possible subclasses extended from the PortID class will be apparent to one skilled in the art given the benefit of this disclosure.

In certain embodiments a linearization I O class is used in conjunction with the PortID classes to denote the linearization I Os in a model. Examples of the pertinent properties are set forth below 

The interrelation of the Linerization I O class to subclasses and other classes can be seen in . Other possible embodiments will be apparent to one skilled in the art given the benefit of this disclosure.

The parameter identifier class ParameterID defines an interface for objects representing the concept of parameters of a model. The classes derived from the ParameterID class need to implement the operations defined by the interface and are used by the Model objects to identify their parameters to interested client objects. In the context of parameter estimation the operations defined by the interface provide a mapping between the parameters of a model and the objects working with parameter values during estimations. For example each object representing estimated parameters in SPE will store a reference to an object derived from the ParameterID class to avoid redundant storage of parameter information.

Version The version number used by subclasses to handle backward compatibility issues in con junction with their loadobj and saveobj methods.

getDimensions Returns a row vector of integer numbers corresponding to the dimensions of the parameter value.

getPath Returns the path to the parameter which is usually the full name of the sub system in which the parameter is defined.

getLocations Returns a cell array of the full names of the objects model subsystems blocks etc. using the parameter. If no other information is available the string from getPath could be returned in a cell array. The location names are all relative to the model and hence they do not include the model name.

As with the port identifier class portID the parameter identifier class ParameterID can also be extended for specific model types. The hierarchy of the ParameterID class to other classes can be seen in . Other possible subclasses extended from the ParameterID class will be apparent to one skilled in the art given the benefit of this disclosure.

The state identifier class StateID defines an interface for objects representing the concept of states of a model. The classes derived from the StateID class need to implement the operations defined by the interface and are used by the Model objects to identify their states to interested client objects. In the context of parameter estimation the operations defined by the interface provide a mapping between the states of a model and the objects working with state values during estimations. For example each object representing estimated states or initial state data in SPE will store a reference to an object derived from the StateID class to do this mapping.

Version The version number used by subclasses to handle backward compatibility issues in conjunction with their loadobj and saveobj methods.

getDimensions Returns a row vector of integer numbers corresponding to the dimensions of the state value.

getPath Returns the path to the state which is usually the full name of the sub system in which the state is defined.

As with the port identifier class portID the state identifier class StateID can also be extended for specific model types. The hierarchy of the StateID class to other classes can be seen in . Other possible subclasses extended from the StateID class will be apparent to one skilled in the art given the benefit of this disclosure.

In some embodiments the abstract interface is further implemented using a value object class. As with the model and identifier classes the value class can define properties that are common for representations of all model types. These include field details constructor details and method details.

In this example there are four main types of the value class. These include a variable value class a parameter value class a state value class and port value class. For purposes of illustration the discussion will focus on the variable value class. The implementation of the other classes will be apparent to one skilled in the art given the benefit of this disclosure.

The variable value VariableValue class defines an interface to represent the concept of value of an object identified by a Variable ID object. The classes derived from the VariableValue class need to implement the operations defined by the interface and are used by the Model objects to identify values of parameters states and ports to interested client objects. The value objects are used to store the values of I Os parameters or states resulting from estimation tuning or trimming the model. They can also be used to initialize model parameters and initial states. Hence most of their properties are public since they would be modified by the users.

Version The version number used by subclasses to handle backward compatibility issues in conjunction with their loadobj and saveobj methods.

The hierarchy of the variable value class the parameter value class the state value class and port value class can be seen in .

In some embodiments the abstract interface is further implemented using a specification object class. As with the model and value classes the specification class can define properties that are common for representations of all model types. These include field details constructor details and method details.

In this example there are four main types of the specification class. These include a variable specification class a parameter specification class a state specification class and port specification class. For purposes of illustration the discussion will focus on the variable specification class. The implementation of the other classes will be apparent to one skilled in the art given the benefit of this disclosure.

The variable specification VariableSpec class defines an interface to represent the concept of value specification for an object identified by a VariableID object. The specifications include the variable s range and initial value. These are used to specify information about unknown values to be computed i.e. estimated optimized and trimmed . The classes derived from the VariableSpec class need to implement the operations defined by the interface and are used by the Model objects to specify values of parameters states and ports to interested client objects. The specification objects are used to specify I O parameter or state information ranges initial guesses etc for estimation tuning or operating point computations. Hence most of their properties are public since they would be modified by the users.

Version The version number used by subclasses to handle backward compatibility issues in conjunction with their loadobj and saveobj methods.

The hierarchy of the variable specification class the parameter specification class a state specification class and port specification class can be seen in .

In some embodiments the abstract interface is further implemented using a helper object class. As with the other classes discussed above the helper class can define properties that are common for representations of all model types. These include field details constructor details and method details.

In this example there are two main types of the helper class. These include a model manager class and an options class. The implementation of the other classes will be apparent to one skilled in the art given the benefit of this disclosure.

The model manager ModelManager class defines a singleton object to manage various model objects to avoid duplications. Basically each model object is a singleton for a given model name.

ModelListeners Stores listeners to remove the model object handles from the model list when they are deleted.

In this example the option class has two types simoptions and gradoptions. The simoptions and gradoptions classes are used to specify various simulation and sensitivity computation options in conjunction with method object method calls.

Version The version number used by subclasses to handle backward compatibility issues in conjunction with their loadobj and saveobj methods.

The gradoptions class is a subclass of the simoptions class. As such is has the same base properties as simoptions plus the following 

Referring now back to the second step of the method is making a call to the dynamic model via methods specified in the abstract interface. The call may be any of methods supported by the object classes set forth above. Using the abstract interface calls can be used to query the model about its properties such as its inputs parameters etc. simulate the model and gather its response obtain various model jacobians and trim and linearize the model.

In this example a model object was created and initial values were set. Then the model was simulated sensitivity was computed and operating points determined. Then the model was linearized.

The examples to this point have focused primarily on the system where the graphical modeling environment was on a local computing device. The graphical modeling environment may of course also be implemented on a network as illustrated in having a server and a client device . Other devices such as a storage device may also be connected to the network.

In one such embodiment a system for generating and displaying a graphical modeling application comprises a distribution server for providing to a client device intrinsic units of measure for modeling physical systems and a client device in communication with the distribution server. Here the distribution server provides a client device such as a computing device discussed above an abstract interface for interfacing a model. The abstract interface is compatible with a plurality of model types. The abstract interface may be an API. The client may then use the abstract interface to access a dynamic model of a system.

In another embodiment the server may execute the modeling environment. A user may then interact with the modeling environment on the server through the client device. In one example of such a system a server and client device are provided. The server is capable of executing a modeling environment. The client device is in communication with the server over a network. An abstract interface is provided for interfacing a model. The abstract interface is compatible with a plurality of model types. The server receives from the client device a call to a dynamic model using the abstract interface. The client device then receives data from the dynamic model from the server in response to the call.

It will be understood by one skilled in the art that these network embodiments are exemplary and that the functionality may be divided up in any number of ways over a network.

The proceeding examples have focused primarily on models of physical systems but it will be apparent to one skilled in the art that there are numerous other domains systems fields and applications the present invention would be suitable. Some examples include but are not limited to models in the electrical biological and chemical domains.

The present invention has been described relative to illustrative embodiments. Since certain changes may be made in the above constructions without departing from the scope of the invention it is intended that all matter contained in the above description or shown in the accompanying drawings be interpreted as illustrative and not in a limiting sense.

It is also to be understood that the following claims are to cover all generic and specific features of the invention described herein and all statements of the scope of the invention which as a matter of language might be said to fall therebetween.

