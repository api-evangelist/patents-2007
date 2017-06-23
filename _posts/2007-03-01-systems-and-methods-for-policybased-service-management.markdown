---

title: Systems and methods for policy-based service management
abstract: Systems and method for policy-based service management are provided. An exemplary system includes a rule definition interface module configured to receive a plurality of rule definitions and a separate policy management interface module configured to allow a user to define a rule instance from an existing rule definition instance and to define a policy instance based on the defined rule instance. A policy may be simply expressed via the policy management interface as “perform the following set of action if all of the following rule instances are true unless any of the following rule instances are true.” Additionally, policies may be associated with a context at a specific a level in a context hierarchy having multiple levels. The policy may therefore inherit rules from contexts at a higher level in the hierarchy.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08127336&OS=08127336&RS=08127336
owner: Bridgewater Systems Corp.
number: 08127336
owner_city: Ottawa
owner_country: CA
publication_date: 20070301
---
Subscribers use networks to access applications and resources such as voice video gaming and conferencing from their communication devices such as phones personal digital assistants PDAs laptop and desktop computers. Providers of these applications and resources utilize policies to determine whether a subscriber is authorized to access the requested service or application.

Because of the complexity of creating policies in current rule based approaches many of these current rule based systems limit a service provider to a simple yes or no answer when access to a specific application or resource is attempted. The ability to specify additional actions or parameters associated with an access attempt is limited or non existent in these systems.

Furthermore rule definition is tied directly to policy creation. For example in these systems a rule engine is used to define and enact subscriber policies. Typical rule engines have a rule definition interface that allows rules to be defined as predicate statements such as If condition then action or as decision trees that use a flow chart format. However to define a policy based on conditions a rule engine based interface requires that each step be defined in a step by step fashion. As conditions and path variations increase the complexity and difficulty of entering policies increases. In addition when rules change in a rule engine applications interacting with the rule engine may need code changes or end user interaction e.g. in the form of application restarts in order to update the applications. Furthermore current rule engines do not allow for the extension of existing rule definitions to new rule instances. Instead new rule flows must be created for each rule instance.

What is therefore needed are systems and methods which separate rule definition from policy definition.

What is further needed is a simple extensible method for expressing policies particularly at a subscriber level basis.

The present invention will now be described with reference to the accompanying drawings. In the drawings like reference numbers can indicate identical or functionally similar elements. Additionally the left most digit s of a reference number may identify the drawing in which the reference number first appears.

The policy based approaches to service management described herein allow providers to offer personalized and tiered services to subscribers. Policies define network and application behaviors which may be based on the individual characteristics and or entitlements of a subscriber. A policy may be associated with a context such as subscriber a provider or an individual resource. For example policies may define access to applications based on criteria such as subscription levels age location may define the quality of service such as bandwidth jitter and delay based on subscription and application requirements may specify charges based on network access quality of service application access special offers and or may specify security based on criteria such as authentication strength and risk assessment.

A policy defines for example whether a subscriber can access a specific network application service or other resource the level of access to be provided to a subscriber the quality of service to be provided and or other network or service parameters or behaviors. For ease of description content e.g. video audio or multi media services applications or other network hardware and or software resources are referred to herein as a resource. A policy includes a set of actions e.g. allow access provide high QOS etc. and a set of rule instances for determining whether the set of actions should be performed. A rule instance contains one or more conditions. For example a rule definition may be allow access on a weekday. The condition is therefore that the day must be a weekday.

In conventional rule based service management systems policies are hard coded into program logic prior to deployment of the logic in the network. Policy decision domain of in contrast allows for the creation and modification of policies after deployment.

Policy decision domain includes a rule definition interface module a rule repository and a policy management interface subsystem . Rule definition interface module interfaces with rule engine and is configured to allow a user such as a system administrator to create rule definitions. A rule definition is a template for a rule. The rule definition includes one or more conditions. A condition may include an element a comparator and a variable. A rule variable is a placeholder for a value which is entered by a user when defining a policy instance. For example in the rule condition subscriber age is greater than AGE the condition element is subscriber age the comparator is greater than and the variable is AGE. 

Rule repository stores the rule definitions. Rule repository may be any type of data storage including but not limited to a database.

The policy management interface subsystem is separate from the rule definition interface module . Policy management interface subsystem includes policy decision interface module data repository and policy management interface module .

Policy management interface module is configured to allow a user to create instances of rules and to define policies by applying one or more rule instances. In an embodiment policy management interface module includes a graphical user interface GUI . In addition or alternatively policy management interface module includes an application programming interface API . For example an instance of a rule includes a set of values to be applied to a variable in a rule condition for a specific policy. For example an instance of the rule defined as allow access on a weekday is allow access on Tuesday. In an embodiment policy management interface module uses a generic simple policy expression method to define policies. The generic simple policy expression method is described in further detail in section 2 below.

In current rule based systems rule instances are created and values are specified at the same time the rule is defined. In contrast in the system of policy creation is separated from rule definition allowing a user to create new policies from existing rule definitions without the need to access rule engine directly.

Data repository is configured to store the defined policies and data upon which the defined rules operate. Data repository may be any type of data storage including but not limited to a database.

Policy decision interface module includes rule engine . Rule engine is configured to enact subscriber policies based on configurable logic statements and other data. Policy decision interface module receives a request for a service management decision and interacts with rule repository data repository and optionally network control system to obtain information necessary to make the requested decision.

As would be appreciated by persons of skill in the art the components of policy decision domain do not have to be implemented in separate devices. A portion or all of the components may be implemented in the same device.

Policy enforcement domain may include one or more subscriber devices network systems one or more servers and one or more network control systems . Subscriber devices access the network or network resources via network systems . Network systems may be any type of communication network including a wireless network a public data network such as the Internet a private data network and or the public switched telephone network. The interface between subscriber devices may be a wireless interface or a wired interface

Server may include one or more resources e.g. subscriber applications . Server is also configured to mediate access by a subscriber or subscriber device to the network and or one or more resources. Server communicates with policy decision interface module to request a service management decision when a subscriber attempts access to the network or a network resource.

Network control system is configured to store information associated with subscribers. In an embodiment network control system includes a session storage facility.

Prior to step one or more rule definitions are created in rule engine using rule definition interface module . In an embodiment the rule definitions are templates in which variables may be used to indicate that a value substitution will be required by the policy decision interface module and a value specification will be required from policy management interface module . These rule definitions are stored in rule repository and made available to policy management interface module .

In addition prior to step policy management interface module presents the user with a graphical user interface including a mechanism for creating a new policy instance.

In step policy management interface module receives a request to create a policy instance or modify an existing policy instance. In response to the request the policy management interface module presents the user with a graphical user interface including a set of existing rule definitions and optionally a set of predefined actions.

In step the user of the policy management interface subsystem associates the policy instance with a context. Examples of contexts include but are not limited to content stream service application provided by the network service package grouping of services applications or subscriber. For example a policy instance may be created for a subscriber when the subscriber registers for a service or application. Note that step may occur at any point during flowchart .

In step a selection of an existing rule definition from the set of rule definitions is received. In response to the selection the policy management interface module displays the rule definition in the graphical user interface. If the rule definition includes a variable a set of possible values for the variable is also displayed in the graphical user interface. In an embodiment the set of possible values is predefined by a user.

In step an instance of the rule and condition values associated with the rule instance are received. The condition values are selected from a set of values for the variables. As described above the set of values may be predefined by a user. For example the user of the policy management interface subsystem may create an instance of the subscriber age rule e.g. subscriber must be older than VARIABLE and associate a value of 21 with the rule variable.

In step a determination is made whether any additional rule instances are to be created. For example the user may activate a link button or similar mechanism to indicate to policy management interface module that an additional rule instance is to be associated with the policy instance. If an additional rule instance is to be created operation returns to step . If no additional rule instances are to be created operation proceeds to step .

In step one or more actions are received and associated with the policy instance. This step is optional. An action may include any action that an entity requesting a policy based service management decision can take. Exemplary actions include provide access provide a certain QOS or route the subscriber to a specific web page or application. Note that step may occur at any point during flowchart .

In step a request for access to the network or a network resource is received from a subscriber device at a policy enforcement entity e.g. server . Additionally or alternatively a subscriber may request access to a specific resource. For example a user may turn on a mobile or data device or attempt access to a network. As a function of activating the device or requesting access to the network a listing of the applications or services available e.g. streaming content for the subscriber may be requested.

In step a network entity e.g. server transmits a service management request to the policy decision interface module . In an embodiment the service management request identifies the subscriber and or subscriber device and the network or resource for which access is requested. The request may also include additional information about the subscriber the subscriber device and or the resource requested.

In step the policy decision interface module interfaces with the rule repository the data repository and optionally the network control system to obtain information necessary to make the requested service management decision. In an embodiment policy decision interface module may access the rule repository to obtain one or more rule definitions associated with a request. Alternatively a set of rule definitions may be received beforehand e.g. at the start of the day or at periodic intervals and cached at the policy decision interface module . In an additional alternative the policy decision interface module may obtain a first group of rule definitions from the rule repository when a request is received e.g. if rule is based on subscriber age and may download and cache a second group of rule definitions in advance e.g. if rule is based on day of week .

In step rule engine determines that a value substitution is required for one or more variables in a rule definition and indicates the required value substitution s to the policy decision interface module .

In step the policy decision interface module provides the values to rule engine . In an embodiment the policy decision interface module accesses data repository to obtain the values to be applied to the variable in the rule instance. For example the values may be specified in the rule instances found in the policy instance being evaluated.

In step the values are substituted in real time for the variables in the rule definition and a determination is made whether the action s defined in the policy are allowed.

In step the decision is transmitted to the requesting entity. The decision may direct the entity to perform a set of actions specified in the policy such as whether requested access is authorized the level of service to provide to the subscriber or other service parameters and or additional actions to take prior to providing access to the resource e.g. routing subscriber to another web page for entry of additional information . Alternatively the decision may direct the entity to deny access to the subscriber.

The generic simple policy expression method provides a mechanism for defining policy instances which is simpler to understand and configure than policy and rule expressions defined via a typical rule definition interface. As discussed above a rule engine based interface requires that each step be defined in a step by step fashion. This definition technique becomes complex and convoluted for a user when many conditions and many path variations exist.

The following is an example of a policy instance defined using a typical rule engine based definition technique. The policy instance example includes a hierarchical dependence of rules and actions 

In contrast in the generic simple policy expression method a policy instance includes a set of actions a set of inclusion rules and a set of exclusion rules. At a high level a policy instance is defined using the generic simple policy expression method as follows 

The following is an example of the policy instance for a rule based engine defined using the generic simple policy expression method.

Prior to step the policy management interface module presents the user with a graphical user interface having a section for defining a set of inclusion rules and a section for defining a set of exclusion rules. The graphical user interface may also include a section for defining a set of actions.

In step one or more actions are defined for the policy instance. Actions may include but are not limited to specifying whether access to a resource is allowed specifying the level of access allowed and or specifying other parameters associated with the application or resource. Example actions include allow access to requested content re direct user to a log in page or present billing page and request additional credit. 

In step one or more rule instances are defined for the set of inclusion rules. An exemplary method for defining rule instances is described below in reference to .

In step one or more rule instances are defined for the set of exclusion rules. An exemplary method for defining rule instances is described below in reference to .

In step a rule definition is selected from an existing set of rule definitions. As illustrated in when a user activates the add another rule link a set of existing rule definitions is displayed. The user then selects a rule definition from the set.

In step the instance of the rule is defined by specifying a value or values for any variables included in the rule definition. For example the value or values may be selected from a set of values for the variable. The set of values may be predefined by a user. depicts an exemplary screen shot including a section for defining the instance of the selected rule. In this example the user selected the rule definition month of year in step . The user can then specify the value or values for the rule variable month. 

As described above a policy instance is associated with a context. The policy management interface allows a provider of the resource or application to establish N hierarchical levels of context. In addition each level may have multiple contexts associated with it. A provider may specify any number of contexts and any form of hierarchy for the contexts. The following is an example of a context level hierarchy for use in the policy management interface.

In current rule based service management systems defined policies cannot be extended. Instead new rule flows must be created for each instance. For example assume two groups of subscribers need the same rule flow to achieve a specified goal except the first group needs its ages compared to 18 whereas the second group needs its age compared to 21. Despite the similarity of rule instances for each group separate rule sets must defined in current rule based systems. The following is an example of the two rule sets which must be defined 

Using policy interface extensibility the set of rule instances can be defined for Group 1 at a high context and can then be further refined by adding a single rule instance at a lower context for users of Group 2. The simple policy expression for Group 2 is then 

Via the use of policy extensibility policies are faster to create and easier to maintain than with a rule engine alone. In addition from a data storage perspective far less data needs to be stored for policies. In a rule engine all policies would be stored as a list of all conditions and the values associated with the conditions. In contrast the policy extensibility method allows for a single instance of a rule to exist with policies referring to the rules that are pertinent and with only the condition variables stored for each policy. The real time substitution of these condition variables aids in achieving this extensibility.

Because rule definitions and data upon which the rules operate can be added or modified after deployment techniques are needed to automatically synchronize this information into policy management interface . In conventional rule based systems this type of synchronization requires manual interface changes including code changes and application restarts.

In step a new or modified rule definition is created via rule definition interface module or new data is added into data repository upon which the rules operate. New data may include modification or additions to the values associated with a rule instance or modification or additions to the set of possible values that a variable in a rule condition may take.

In step synchronization of the added or modified information with the user interface and or application programming interfaces of policy management interface is initiated. In an embodiment the initiation is via database triggers in the rule repository and data repository . In this embodiment policy decision interface module receives the triggers and initiates the necessary modifications in policy management interface . In alternative embodiments synchronization may be achieved through a combination of application program interface communication remote method invocation as well as through the user of messaging frameworks such as Java Message Service JMS messaging.

In step the rules and or actions are added deleted or modified in the user interface and application programming interfaces of the policy management interface module .

The automatic synchronization described above allows for seamless changes to be made between the rule definition interface and policy management interface . Because neither interface needs to be halted for the purpose of synchronizing its rule configuration services do not be paused or stopped. In addition because no manual synchronization steps are necessary the efficiency of personnel required to create or alter rule sets and policies is increased.

While various embodiments of the present invention have been described above it should be understood that they have been presented by way of example only and not limitation. It will be apparent to persons skilled in the relevant art that various changes in form and detail can be made therein without departing from the spirit and scope of the invention. Thus the breadth and scope of the present invention should not be limited by any of the above described exemplary embodiments but should be defined only in accordance with the following claims and their equivalents.

