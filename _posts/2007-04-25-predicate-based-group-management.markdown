---

title: Predicate based group management
abstract: Embodiments are provided to generate an integrated data structure. In an embodiment, a database system is configured to generate an integrated database view that includes a number of predicate-based objects and a number of enumerated objects. A declarative membership criteria can be used to provide automatic membership to a group of objects associated with the database system. A number of predicate-based group membership rules can be used when generating a database view that includes a number of predicate-based views and a number of enumerated groups.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=07596584&OS=07596584&RS=07596584
owner: Microsoft Corporation
number: 07596584
owner_city: Redmond
owner_country: US
publication_date: 20070425
---
A portion of the disclosure of this patent document contains material which is subject to copyright protection. The copyright owner has no objection to the facsimile reproduction by anyone of the patent document or patent disclosure as it appears in the U.S. Patent and Trademark Office patent file or records but otherwise reserves all copyright rights whatsoever.

Businesses and other organizations routinely maintain large amounts of records data and other information. An organization may use some type of database system to manage and maintain sales information employee records equipment types and locations access rights etc. Correspondingly the organization expects to use the database system effectively by quickly and efficiently updating information contained therein. Unfortunately many database systems are not configured to expeditiously update information. For example some database systems require manual assessment and updating of each record. Moreover some database systems are not configured to update multiple records without employing an inordinately complicated process. For example if an employee leaves a company a manager or other user may have to spend an unreasonable amount of time to locate all of the records associated with the employee and manually update each record to reflect that the employee is no longer associated with the company.

This summary is provided to introduce a selection of concepts in a simplified form that are further described below in the Detailed Description. This summary is not intended to identify key features or essential features of the claimed subject matter nor is it intended as an aid in determining the scope of the claimed subject matter.

Embodiments are provided to generate an integrated data structure. In an embodiment a database system is configured to generate an integrated database view that includes data associated with a number of predicate based groups and a number of enumerated groups. As such predicate based membership criteria can be used in part to manage information associated with the database system. Accordingly declarative membership criteria can be used to provide automatic membership to a group of objects associated with the database system. In one embodiment a number of predicate based group membership rules can be used when generating a database view that includes a number of predicate based groups and a number of enumerated groups.

These and other features and advantages will be apparent from a reading of the following detailed description and a review of the associated drawings. It is to be understood that both the foregoing general description and the following detailed description are explanatory only and are not restrictive of the invention as claimed.

Embodiments are provided to generate an integrated data structure. In an embodiment a database system is configured to generate an integrated database view that includes a predicate based view and a number of enumerated objects. In another embodiment a method uses a number of predicate based group membership rules used when generating a database view that integrates a number of predicate based views with a number of enumerated groups. The various embodiments can be used with any application that uses groups of objects that are stored in a relational database.

In one embodiment a database management system includes a database application that can be used to define a number of predicate based membership and other rules according to a desired implementation. The database application can be configured to define a number of SELECT statements union operations and includes other functionality. The database management system can use a logical schema when defining a predicate based group membership. A logical schema can also be used to generate a predicate based membership view and a number of these views can be combined to provide an integrated predicate based view. The integrated predicate based view can be combined with a number of enumerated objects to provide an overall view that encompasses predicate based and enumerated objects. The overall view can be queried to locate desired information according to a query construct. These and other embodiments are described below and other embodiments are available.

As shown in the system includes a database system an organizing component and a query component but is not so limited. The database system can be configured as a relational multi dimensional or other data repository that includes data management functionality. For example the database system can comprise one or more serving computers and associated storage capacity such as one or more SQL servers. The database system can include information such as objects associated attributes and values for example.

The organizing component can be used to interact with the database system in various ways. In one embodiment the organizing component can be configured as an application programming interface API or other interactive interface and used to interact with the database system to add delete and or modify one or more groups including parameters associated with the one or more groups. For example a user can use the organizing component to define attributes for various groups including predicate based groups enumerated groups and other defined groups. The organizing component can also be used to define one or more rules that can be associated with one or more groups as described below.

The query component can also be used to interact with the database system . For example the query component can be used to query the database system to determine desired information. In one embodiment the query component can be used to query the database system and receive results associated with a desired view or subset of data as stored in the database system . A view can be used to represent information associated with the database system . A view may be automatically generated by storing the associated view criteria as part of a query which can be defined and executed using the query component .

With continuing reference to the database system includes a predicate membership rules table . The predicate membership rules table can be used to generate a predicate membership view . The predicate membership view can be described as integrated view which includes a number of defined predicate based views. In an embodiment the predicate membership view can be created by using a union operation which operates to combine each defined predicate based view into an integrated view. In one embodiment a logical schema for the predicate membership rules table includes the following columns shown in Table 1 below. The predicate membership rules table can include one row for each defined group.

As shown in Table 1 the ObjectID identifies which group an associated membership rule applies to. As described above the organizing component can be used to define membership rules for various groups. For example building printers can be defined as all printers whose building attribute is . Similarly and as further example declarative membership criteria can be used to define a person s staff as all persons whose manager attribute is defined as a particular person. The PredicateSql and ViewSql define which subset of the objects are members of a group. A group can also be a member of a different group.

In one embodiment the database system maintains an add time and a delete time which are useful for auditing and other purposes. A rule that is still current can be constructed with a large DeleteTime such as 9999 for example. When a user uses the organizing component to delete a rule the operation marks the associated rule as deleted. Add and delete reasons can also be maintained in the database system which can be the ObjectID of the person rule process etc. associated with the addition or deletion of a rule for example.

In one embodiment the organizing component can be used to define a new rule by specifying an ObjectID PredicateSql and CteSql for the new rule. In an alternative embodiment an AddCause may be specified for the associated rule. The ViewName and ViewSql can be generated by using PredicateMembershipBuildRuleBaseSelect described further below. The ViewName and ViewSql can be generated using the ObjectID PredicateSql and CteSql parameter and stored with the rule as an optimization.

Correspondingly once the individual rule s ViewSql is generated the associated information can be saved and does not require regeneration each time the larger PredicateMembership is regenerated. The AddTime associated with the rule can be generated using a database function that obtains the current time such as GETUTCDATE for example. As described above the DeleteTime associated with the rule can be generated as a large number such as 9999 for example. To delete a rule the ObjectID and DeleteCause can be specified. The DeleteTime can be generated using a database function that obtains the current time such as GETUTCDATE for example.

When the predicate membership rules table is updated the predicate membership view can be regenerated. The regeneration of the predicate membership view can be triggered by a number of stored procedures that are used to modify the predicate membership rules table . In another embodiment the regeneration of the predicate membership view can be triggered by a database trigger on the predicate membership rules table . Furthermore the members of each predicate based group appear to be enumerated even though the predicate membership view corresponds to a predicate calculus statement. Although the predicate membership view contains virtual rows that are attached to base tables through a predicate calculus statement i.e. a view s SELECT statement described below a user of a view is unaware that the view is not a base table.

In an embodiment a logical schema for the predicate membership view includes the following columns as shown in Table 2 below. The predicate membership view can include a row per group member pair. According to one embodiment the attribute name associated with the predicate membership view is member and has the type reference. 

When the query component is used to perform a query a database compiler of the database system can operate to push the associated query predicates down onto predicates on the base tables. For example a SQL view is a virtual table that adds predicate logic on top of a table. At query compile time the query on the SQL view can be combined with the associated predicate logic to construct a query on a number of base tables. Correspondingly a single predicate group rule may add a large number of virtual rows to the predicate membership view . For example a single rule in the predicate membership rules table associated with a group called All Managers may add 100 000 virtual rows to the predicate membership view .

Accordingly a large database computation may be required to list all members of the group. On the other hand testing an individual for membership in the group may only require a simple database index seek on the underlying enumerated objects table . As such the enumerated objects table can be used to define a number of enumerated groups. The number of enumerated groups can include a number of enumerated objects as defined using the organizing component .

In an embodiment a logical schema for the enumerated objects table includes the following columns as shown in Table 3 below. The logical schema can include a row per attribute value. However if an attribute is multi valued the logical schema may have multiple rows for the same object e.g. one row per value . In one embodiment only one of the Value columns is not NULL. Separate columns can be are provided so that a query can be used to perform comparisons based on specific database types. In another embodiment a SQL schema can be used for the enumerated objects table . Other schemas can be implemented for use with the various embodiments described herein.

Content associated with the predicate membership view and the enumerated objects table can be combined to provide an objects view . That is the objects view integrates the predicate based group membership with enumerated objects by combining the predicate membership view and the enumerated objects. In one embodiment the objects view is provided as a result of a union operation using data associated with the predicate membership view and data associated with the enumerated objects table as described further below. Correspondingly users of the objects view do not need to be aware of whether a group exists as a predicate or an explicit enumeration.

The organizing component can be used to create one or more enumerated groups by explicitly enumerating a number of members of each enumerated group. The enumerated group memberships can be stored in the enumerated objects table of the database system . The organizing component can also be used to define and store other enumerated objects in the database system . For example other defined enumerated objects may include an employee a location a building computer printer process device etc. In one embodiment each enumerated group includes a multi valued attribute named member that contains the ObjectIDs of member objects.

The organizing component can also be used to define a number of predicate based groups according to a number of desired rules. A predicate based group refers to a group of objects that is defined and exists as a predicate. Thus a predicate based group is configured to be current and up to date. As described below and in accordance with an embodiment predicate based groups can be configured to include a number of member inclusions and or member exclusions having multi valued attributes which contain ObjectIDs of other objects. The member inclusion attribute values add to the members included by the membership predicate. The member exclusion attribute values remove members included by either the membership predicate or the member inclusion attribute values.

In an embodiment a number of attributes associated with a predicate based group can be stored in the enumerated objects table . As described below the Member attribute of a Group object can be either enumerated in the enumerated objects table or defined using group membership rules that are predicates on the objects view. As described above group membership rules can be defined using the organizing component and stored in the predicate membership rules table . Predicates that are used in defining groups can be maintained in a database view i.e. the predicate membership view of .

The organizing component can be used to define a new rule according to a desired implementation. In an embodiment after defining a new predicate based membership rule a stored procedure can be called to add the new predicate based membership rule. For example the PredicateMembershipAddRule stored procedure can be called to add a new predicate based membership rule. As an example of this a membership for a group with ID 8A112A70 14D0 40A9 803B 87D1AA764D0C is defined as persons whose manager has object ID 5D6F3249 B729 4DE9 9D64 E14378C21995 as follows 

According to one embodiment logic associated with the PredicateMembershipAddRule stored procedure is described below using TransactSQL language. However similar algorithms can be implemented in various database languages and systems. For example a markup language such as extensible markup language XML can be used. As shown below the logic does not include AddCause and DeleteCause in order to simplify the description.

The PredicateMembershipAddRule can be included as a single transaction. Accordingly the update to predicate membership rules table and the update to the predicate membership view can be both performed or both not performed. In one embodiment the PredicateMembershipAddRule generates an AddTime using a database function that obtains the current time such as GETUTCDATE for example. The DeleteTime can be generated as a large number such as 9999 for example. The PredicateMembershipBuildRuleBaseSelect can be called to build the SELECT statement that obtains the predicate based members. The memberInclusions and memberExclusions attributes are described below. The PredicateMembershipBuildRuleView function can be called to build the SELECT for this single rule that handles the interaction between predicate members and the memberExclusions attributes. A new row can then be inserted into the predicate membership rules table .

The PredicateMembershipRegenerateView stored procedure can then be called which operations to union all of the rule views. The PredicateMembershipRegenerateView stored procedure also handles the interaction between the memberInclusions and memberExclusions attributes for all predicate based groups. The view can be created if it did not already exist or altered if it already exists. The view is named with a desired convention which can include the ObjectID of the group provided by the PredicateMembershipRuleViewName function.

SELECT corresponds to producing a row for the full inclusion interval when an inclusion does not have an entry in the memberExclusions attribute.

SELECT corresponds to producing a row with the following aspects when an inclusion has an entry in the memberExclusions attribute and the inclusion range starts before the exclusion range ends e.g. cases and . SELECT results in a row having 

Thus for SELECT result.DeleteTime exclusion.AddTime for cases and and result.DeleteTime inclusion.DeleteTime for case i.e. no overlap .

SELECT corresponds to producing a new row with the following aspects when an inclusion has an entry in the memberExclusions attribute and the inclusion range ends before the exclusion range ends e.g. cases and . SELECT results in a row having 

Thus for SELECT result.DeleteTime inclusion.DeleteTime no overlap for case and result.DeleteTime exclusion.AddTime for cases and .

As described below the inclusion exclusion interaction rules can be used in various functions and operations. For example the PredicateMembershipBuildRuleBaseSelect function can use the inclusion exclusion interaction rules for the interaction between the predicate based inclusions and the memberExclusions attribute for each predicate membership rule. As further example the PredicateMembershipBuildRuleView function can use the inclusion exclusion interaction rules for the interaction between the memberInclusions and memberExclusions attributes for all predicate based groups.

According to one embodiment logic associated with the PredicateMembershipBuildRuleBaseSelect function is described below using TransactSQL language. Again similar algorithms can be implemented in various database languages and systems. The logic for the PredicateMembershipBuildRuleBaseSelect function can be defined as 

The PredicateMembershipBuildRuleBaseSelect function operates to build a base SELECT statement for the associated rule and defines a number of virtual rows that correspond with the format of the predicate membership view . The AddTime for the number of virtual rows can be defined as the maximum of the following 

a the AddTime for the rows of the enumerated objects table that qualify the members to be in a group and

In other words the membership begins after both of the qualifying value and the associated rule are added.

a the DeleteTime for rows of the enumerated objects table that qualify the members to be in the group and

In other words the membership ends when either the qualifying value or the rule has been deleted. The AddCause and DeleteCause are the predicate based membership rule ID which corresponds to the GroupID.

According to one embodiment logic associated with the PredicateMembershipBuildRuleView function is described below using TransactSQL language. Again similar algorithms can be implemented in various database languages and systems. The logic for the PredicateMembershipBuildRuleView function can be defined as 

The following logic is configured to handle interaction between a group s predicate inclusion rule and the group s memberExclusions attribute. The logic also handles predicate inclusion members with no entry in the memberExclusions attribute.

For predicate inclusion members with an entry in the memberExclusions attribute and the inclusion range comes before the exclusion range the logic is as follows 

For predicate inclusion members with an entry in the memberExclusions attribute and the inclusion range comes after the exclusion range the logic is as follows 

As shown above the PredicateMembershipBuildRuleView function generates the rule specific view by doing the following 

b applies the rules for interaction between inclusions and exclusions that were described above to this predicate based membership rule and the memberExclusions attributes and

According to one embodiment logic associated with the PredicateMembershipRegenerateView stored procedure is described below using TransactSQL language. Again similar algorithms can be implemented in various database languages and systems. The logic for the PredicateMembershipRegenerateView stored procedure can be defined as follows 

The following logic is configured to handle memberInclusions minus memberExclusions for all predicate based membership groups.

For inclusionMembers with an entry in the memberExclusions attribute and the inclusion range comes before the exclusion range the logic is as follows 

For inclusionMembers with an entry in the memberExclusions attribute and the inclusion range comes after the exclusion range the logic is as follows 

The PredicateMembershipRegenerateView stored procedure regenerates the predicate membership view by performing the following 

a performing a union operation of the per predicate based membership rule views by creating a cursor across all rules in the predicate membership rules table

b applying the rules for interaction between inclusions and exclusions described above to the memberInclusions and memberExclusions attributes. This operates to union the three SELECTs in the interaction rules to the view. The three SELECTs handle the memberInclusions and memberExclusions attributes for all predicate based membership groups because they are independent of the membership predicate. Since the above can be handled outside of individual rules they can be performed once for all rules resulting in a more efficient process since the number of SELECT statements can be reduced. In one embodiment the memberInclusions and memberExclusions attributes are included in the top level predicate membership view instead of in each rule specific view.

c if not in existence the predicate membership view can be created or the view can be altered if already in existence.

According to one embodiment logic associated with the PredicateMembershipDeleteRule stored procedure is described below using TransactSQL language. Again similar algorithms can be implemented in various database languages and systems. The logic for the PredicateMembershipDeleteRule stored procedure can be defined as the DeleteCause parameter is omitted to simplify the description 

The PredicateMembershipDeleteRule can be performed in a single transaction so that the update to predicate membership rules table and the deletion of the rule specific view are either both done or both not done. The PredicateMembershipDeleteRule operates to do the following 

a generates the DeleteTime using a database function that gets the current time such as GETUTCDATE for example

c deletes the rule specific view. In one embodiment the view name uses the same PredicateMembershipRuleViewName function to convert the GroupID to the view name and

d calls the PredicateMembershipRegenerateView stored procedure to regenerate the predicate membership view with the exclusion of the deleted group s rule.

According an embodiment the following logic operates to integrate predicate based group membership parameters which includes using the above predicate membership view and the enumerated objects table to generate an objects view . The logic to create the objects view includes 

For the first SELECT from PredicateMembership the AttributeName is member the MemberID is put in the ValueReference column and all other values are NULL. Correspondingly the above defined view see objects view of allows queries to be built and executed without having to know which groups have enumerated membership and which groups have predicate membership. That is both types of group membership have enumerated member attribute qualities.

At the database system creates a predicate where clause that is associated with the rule. At the database system considers any inclusion and or exclusion operations that may be associated with the rule. At the database system builds a SELECT statement for the associated rule. At the database system generates a data structure for each defined predicate based group. At the database system generates an encompassing data structure for all of the predicate based groups. In one embodiment the database system uses a union operation to union each view of a defined predicate based group into an overall predicate based view which encompasses each individual predicate based view.

At the database system generates an objects data structure which encompasses the data structure associated with all of the predicate based groups and any enumerated objects. In one embodiment the database system uses a union operation to union all of the predicate based groups and any enumerated objects when generating an objects view. If there are new rules to be defined at the flow returns to . If there are no new rules to define the flow ends.

The following provides an example of using of group membership rules to provide an integrated data set to a user.

The organizing component can be used to designate and manage groupings rules and other information as described above. For any object an ObjectID can be defined using a function that generates a unique ID. Staff associated with manager John Doe can be designated as a group with an identification ID 8A112A70 14D0 40A9 803B 87D1AA764D0C and defined as persons whose manager has object ID 5D6F3249 B729 4DE9 9D64 E14378C21995 thereby defining a predicate based membership rule. John Doe s staff can be defined as follows 

Extended staff associated with John Doe can be designated as a group with ID C2B502C1 368C 44A6 83D0 EACAE414EFE6 and defined as persons whose manager eventually reports to the manager with object ID 5D6F3249 B729 4DE9 9D64 E14378C21995. This uses a recursive CTE to traverse the management chain 

All Managers can be designated as a group with ID 62132177 50F3 4437 98D0 FD7DE2B5497A and defined as persons referenced by at least one employee 

Full time employees can be designated as a group with ID BE740FF6 8C80 4B75 9A33 5799F9C5F42A and defined as persons whose object type is FullTimeEmployee 

The above defined group membership rules result in the following generated views. The predicate membership views for each defined group can be defined as follows minus memberExclusions 

The following description handles memberInclusions minus memberExclusions for all defined predicate membership groups.

For inclusionMembers with an entry in the memberExclusions attribute and the inclusion range comes before the exclusion range 

For inclusionMembers with an entry in the memberExclusions attribute and the inclusion range comes after the exclusion range 

The following description handles interaction between the group s predicate inclusion rule and the group s memberExclusions attribute.

Predicate inclusion members with an entry in the memberExclusions attribute and the inclusion range comes before the exclusion range includes 

Predicate inclusion members with an entry in the memberExclusions attribute and the inclusion range comes after the exclusion range includes 

The following description handles interaction between the group s predicate inclusion rule and the group s memberExclusions attribute.

Predicate inclusion members with an entry in the memberExclusions attribute and the inclusion range comes before the exclusion range includes 

Predicate inclusion members with an entry in the memberExclusions attribute and the inclusion range comes after the exclusion range includes 

The following description handles interaction between the group s predicate inclusion rule and the group s memberExclusions attribute.

Predicate inclusion members with an entry in the memberExclusions attribute and the inclusion range comes before the exclusion range includes 

Predicate inclusion members with an entry in the memberExclusions attribute and the inclusion range comes after the exclusion range includes 

The following description handles interaction between the group s predicate inclusion rule and the group s memberExclusions attribute.

Predicate inclusion members with an entry in the memberExclusions attribute and the inclusion range comes before the exclusion range includes 

Predicate inclusion members with an entry in the memberExclusions attribute and the inclusion range comes after the exclusion range includes 

The system can be implemented as part of networked distributed or other computer implemented environment. The system and its components can communicate via a wired wireless and or a combination of communication networks. A number of client computing devices including desktop computers laptops handhelds or other smart devices can interact with and or be included as part of the system . In alternative embodiments the various components can be combined and or configured according to a desired implementation. For example the organizing component and or query component can be included as part of the database system . Other embodiments and configurations are available.

As described above defined groups can be used for many purposes. For example groups can be used when sending an e mail to multiple people for granting access rights identifying multiple people as the principle for granting access rights identifying multiple targets of an action etc. A predicate based membership can be used to eliminate the additional management action of adding or removing a member from an associated group. As soon as a member of a group is stored in the database the member can be automatically and immediately in the group because the member can be included using a defined group membership predicate. Once a member is no longer associated with a group the member can be automatically and immediately disassociated with the group as stored in the database.

A predicate based group is not only defined as a predicate it exists as a predicate. Thus a predicate based group will be automatically up to date. In an embodiment the predicate is not used to cache associated members. Rather as described above a predicate defining a group can be maintained using a database view. Correspondingly a query using the database view gets the up to date membership since caching of the members is not required. Moreover the complexity and overhead associated with cache invalidation can be avoided. Constantly checking whether an update to the database invalidates the cached group membership can require complex error prone programming as well as a very large processing overhead. In some cases a group can be used to test membership so that producing the set of members in not necessary resulting in better performance.

Referring now to the following discussion is intended to provide a brief general description of a suitable computing environment in which embodiments of the invention may be implemented. While the invention will be described in the general context of program modules that execute in conjunction with program modules that run on an operating system on a personal computer those skilled in the art will recognize that the invention may also be implemented in combination with other types of computer systems and program modules.

Generally program modules include routines programs components data structures and other types of structures that perform particular tasks or implement particular abstract data types. Moreover those skilled in the art will appreciate that the invention may be practiced with other computer system configurations including hand held devices multiprocessor systems microprocessor based or programmable consumer electronics minicomputers mainframe computers and the like. The invention may also be practiced in distributed computing environments where tasks are performed by remote processing devices that are linked through a communications network. In a distributed computing environment program modules may be located in both local and remote memory storage devices.

Referring now to an illustrative operating environment for embodiments of the invention will be described. As shown in computer comprises a general purpose desktop laptop handheld or other type of computer capable of executing one or more application programs. The computer includes at least one central processing unit CPU a system memory including a random access memory RAM and a read only memory ROM and a system bus that couples the memory to the CPU . A basic input output system containing the basic routines that help to transfer information between elements within the computer such as during startup is stored in the ROM . The computer further includes a mass storage device for storing an operating system application programs and other program modules.

The mass storage device is connected to the CPU through a mass storage controller not shown connected to the bus . The mass storage device and its associated computer readable media provide non volatile storage for the computer . Although the description of computer readable media contained herein refers to a mass storage device such as a hard disk or CD ROM drive it should be appreciated by those skilled in the art that computer readable media can be any available media that can be accessed or utilized by the computer .

By way of example and not limitation computer readable media may comprise computer storage media and communication media. Computer storage media includes volatile and non volatile removable and non removable media implemented in any method or technology for storage of information such as computer readable instructions data structures program modules or other data. Computer storage media includes but is not limited to RAM ROM EPROM EEPROM flash memory or other solid state memory technology CD ROM digital versatile disks DVD or other optical storage magnetic cassettes magnetic tape magnetic disk storage or other magnetic storage devices or any other medium which can be used to store the desired information and which can be accessed by the computer .

According to various embodiments of the invention the computer may operate in a networked environment using logical connections to remote computers through a network such as a local network the Internet etc. for example. The computer may connect to the network through a network interface unit connected to the bus . It should be appreciated that the network interface unit may also be utilized to connect to other types of networks and remote computing systems. The computer may also include an input output controller for receiving and processing input from a number of other devices including a keyboard mouse etc. not shown . Similarly an input output controller may provide output to a display screen a printer or other type of output device.

As mentioned briefly above a number of program modules and data files may be stored in the mass storage device and RAM of the computer including an operating system suitable for controlling the operation of a networked personal computer such as the WINDOWS operating systems from MICROSOFT CORPORATION of Redmond Wash. The mass storage device and RAM may also store one or more program modules. In particular the mass storage device and the RAM may store application programs such as a word processing application a spreadsheet application e mail application drawing application etc.

It should be appreciated that various embodiments of the present invention can be implemented 1 as a sequence of computer implemented acts or program modules running on a computing system and or 2 as interconnected machine logic circuits or circuit modules within the computing system. The implementation is a matter of choice dependent on the performance requirements of the computing system implementing the invention. Accordingly logical operations including related algorithms can be referred to variously as operations structural devices acts or modules. It will be recognized by one skilled in the art that these operations structural devices acts and modules may be implemented in software firmware special purpose digital logic and any combination thereof without deviating from the spirit and scope of the present invention as recited within the claims set forth herein.

Although the invention has been described in connection with various exemplary embodiments those of ordinary skill in the art will understand that many modifications can be made thereto within the scope of the claims that follow. Accordingly it is not intended that the scope of the invention in any way be limited by the above description but instead be determined entirely by reference to the claims that follow.

