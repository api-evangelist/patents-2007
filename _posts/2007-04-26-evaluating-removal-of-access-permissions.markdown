---

title: Evaluating removal of access permissions
abstract: Methods and systems are provided for controlling access to a file system. A record of actual accesses by users of the file system is maintained. Before a user is removed from a set of users or before a privilege for a set of users to access a data element is removed, it is determined whether the actual recorded accesses of the user are allowed by residual access permissions that would remain after implementing the proposed removal of access permission. An error condition is generated if the proposed removal of the access permission would have prevented at least one of the actual accesses. In another aspect of the invention, the system determines if the users would have alternate access to the storage element following implementation of the proposal.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08239925&OS=08239925&RS=08239925
owner: Varonis Systems, Inc.
number: 08239925
owner_city: New York
owner_country: US
publication_date: 20070426
---
This invention relates to computer security. More particularly this invention relates to modification of user access permissions on a computer system.

Data security policies typically determine who has access to an organization s stored data on various computer systems. These policies are rarely static. Users from within the organization e.g. employees partners contractors can pose a threat as severe as threats from outside the organization. Thus as the structure and personnel makeup of the organization change the security policy should be adjusted from time to time. Yet information technology IT departments often find it difficult to manage user access rights and to ensure that needed information is conveniently available while still protecting the organization s sensitive data.

Current techniques available to IT personnel include review and maintenance of access control lists in conjunction with administration of user names passwords and the extension of such techniques to include biometrics encryption and limitation of access to a single sign on. Such techniques are inefficient often inaccurate and become impractical in the context of large complex organizations whose structure and personnel are constantly changing.

According to disclosed embodiments of the invention methods and systems are provided for validation of removal of user access permissions within the scope of a file security policy. Specifically proposed removals of users from groups with data access are validated prior to actual implementation by determining that the users do not have alternative means of accessing the same data through other groups and by determining that historical user accesses would still be allowable by the proposed residual access rights. This reduces the risk of needed data being denied to a user or class of users an event that would risk disruption to the work of the organization. The principles of the invention are applicable to networked organizations having diverse access control models and file server protocols.

In some embodiments the historical information is acquired automatically as part of a data security model in which access to storage elements within the organizational network is continually monitored and analyzed by an access control system. The system monitors access to storage elements within the network and stores the information in a database. Periodically an aggregated table is produced from the log table. The aggregated table indicates which users accessed which storage elements without duplicate entries. It is therefore possible to search this table efficiently to determine whether a specified user accessed a specified storage element.

For every user for whom removal from a subject user group is proposed the system verifies that no other user groups of which the user is a member have access to any data which the user can currently access by virtue of its membership in the subject user group. If such an alternative means of accessing data is available the details are reported to an operator such as a system administrator. Embodiments of the invention further use the aggregated table to verify that for every user for whom removal from a user group is proposed all actual accesses of storage elements by the user are allowed by residual access permissions that would remain after implementation of the proposal. Any historical data access by an affected user that is no longer allowed by its residual access rights is categorized as an error which is reported to the operator. The error may nevertheless be overridden by the administrator who may know that the user does not need access to the storage element.

An embodiment of the invention provides a computer implemented method for controlling access to a file system that has storage elements which is carried out by maintaining a record of respective actual accesses by users of the file system to the storage elements and defining a proposed removal of a set of the users from a superset of the users wherein members of the superset have common access privileges to a portion of the storage elements. Following an implementation of the proposed removal members of the set would retain respective residual access permissions to the storage elements. The method is further carried out by automatically determining prior to the implementation of the proposed removal that at least one of the respective actual accesses is disallowed to the members of the set by the respective proposed residual access permissions and thereupon generating a report or error indication.

According to an additional aspect of the method the users have memberships in respective alternative user groups. Each of the alternative user groups has group permissions to access respective portions of the storage elements and the respective residual access permissions of the users comprise the group permissions of the alternative user groups.

In one aspect of the method. The record is maintained by constructing an aggregated table of unique actual accesses by the users.

In yet another aspect of the method the removal of the user from the user group is proposed automatically.

Another aspect of the method includes automatically establishing that the respective proposed residual access permissions allow at least one of the members of the set associated therewith to access one of the storage elements in the portion and responsively thereto generating another report or error indication.

Other embodiments of the invention provide computer software product and apparatus for performing the method.

An embodiment of the invention provides a computer implemented method for controlling access by users of a file system that has storage elements which is carried out by defining a proposed removal of a set of the users from a superset of the users wherein members of the superset have common access privileges to a portion of the storage elements and wherein following an implementation of the proposed removal members of the set retain respective proposed residual access permissions to the storage elements. The method is further carried out by automatically determining that the respective proposed residual access permissions allow at least one of the members of the set to access one of the storage elements in the portion and thereupon generating a report or an error indication.

An embodiment of the invention provides a computer implemented method for controlling access to a file system has storage elements which is carried out by maintaining a record of respective actual accesses by users of the file system to the storage elements defining a proposed removal of a right to access a designated storage element by a set of the users wherein members of the set have common access privileges to at least the designated storage element and wherein following an implementation of the proposed removal the members of the set retain respective proposed residual access permissions to the storage elements. The method is further carried out by automatically determining prior to the implementation of the proposed removal that at least one of the respective actual accesses are disallowed to the members of the set by the respective proposed residual access permissions responsively thereto generating an error indication.

An aspect of the method includes automatically establishing that the respective proposed residual access permissions allow at least one of the members of the set associated therewith to access the designated storage element and responsively thereto generating another error indication.

Other embodiments of the invention provide computer software product and apparatus for performing the methods.

In the following description numerous specific details are set forth in order to provide a thorough understanding of the present invention. It will be apparent to one skilled in the art however that the present invention may be practiced without these specific details. In other instances well known circuits control logic and the details of computer program instructions for conventional algorithms and processes have not been shown in detail in order not to obscure the present invention unnecessarily.

Software programming code which embodies aspects of the present invention is typically maintained in permanent storage such as a computer readable medium. In a client server environment such software programming code may be stored on a client or a server. The software programming code may be embodied on any of a variety of known media for use with a data processing system such as a diskette or hard drive or CD ROM. The code may be distributed on such media or may be distributed to users from the memory or storage of one computer system over a network of some type to other computer systems for use by users of such other systems.

Turning now to the drawings reference is initially made to which is a block diagram of a data processing system wherein proposals for data access control policies are automatically verified in accordance with a disclosed embodiment of the invention. The system may be implemented as a general purpose processor or computer or a plurality of computers linked together in a network for example the Internet. Using the facilities of the system data access control policies can be automatically established using the methods disclosed in commonly assigned U.S. Patent Application Publication No. 2006 0277184 which is herein incorporated by reference. Although the system is shown as comprising a number of separate functional blocks these blocks are not necessarily separate physical entities but rather represent different computing tasks or data objects stored in a memory that is accessible to the computer. These tasks may be carried out in software running on a single processor or on multiple processors. The software may be provided to the processor or processors on tangible media such as CD ROM or non volatile memory. Alternatively or additionally the system may comprise a digital signal processor or hard wired logic.

Organization wide data storage accessible by the system is represented by an organizational file system . The organizational file system may comprise one or more colocated storage units or may be a geographically distributed data storage system as is known in the art. There is no requirement that individual storage units of the organizational file system have the same capabilities.

The organizational file system may be accessed by any number of users using one or more applications which communicate with the organizational file system using an application programming interface API . The users are typically members of the organization but may also include outsiders such as customers.

The organizational file system verifies that the users have access to the data requested using an access control list ACL . The ACL can be viewed as a set of pairs where each pair consists of a user group and a group of data elements that can be accessed by the user group. A user group consists of users and or other user groups. The users and user groups within any user group are also listed in the ACL.

The organizational file system typically comprises files and directories in a hierarchical structure in which the files and directories contained in a directory may be viewed as being below the containing directory.

A probe engine is designed to collect access information from the organizational file system in an ongoing manner and store the resulting information stream in a log file . In some embodiments the probe engine may also be utilized to collect the organization s current file security policy the current structure of the organizational file system and information about the users . The probe engine can be implemented in various environments and architectures.

In some embodiments an analysis engine not shown may analyze the data in the log file to automatically propose and revise the organization s security policy as described in U.S. Patent Application Publication No. 2006 0277184 cited above.

A sufficiently qualified user e.g. an administrator can view changes recommended by the system . Alternatively the administrator may consider specific removals of user access permissions. Before applying the changes the administrator uses a GUI Graphical User Interface application to verify the proposed changes. In particular the GUI application verifies that all the data accesses in the log file would still be possible after the proposed changes have been performed. If any of the proposed changes would prevent a data access in the log file the proposed change is categorized as invalid although the administrator may still override this.

An aggregation module produces an aggregated table from data in the log file . Typically this is performed daily. Alternatively it may be performed on demand.

Reference is now made to which is a diagram illustrating exemplary construction of the aggregated table from the log file in accordance with a disclosed embodiment of the invention.

The log file comprises a sequence of log entries. Each log entry is constructed when a user accesses a data element in the organizational file system and comprises the following fields. Typically a data element may be a file a directory or a directory together with all files and directories below it in the hierarchical structure of the organizational file system 

The aggregated table comprises a sequence of table entries. Each table entry is a condensed form of one or more corresponding log entries of the table and comprises the following fields 

The aggregated table does not contain duplicated entries. A table entry is derived from the log entry . A table entry is derived from the log entry . A table entry is derived from the log entry . A table entry is derived from the log entry .

No table entry is derived from the log entry since such a table entry would match the table entry . No table entry is derived from the log entry since such a table entry would match the table entry .

A table entry is derived from the log entry . A table entry is derived from the log entry . A table entry is derived from the log entry .

No table entry is derived from the log entry since such a table entry would match the table entry . No table entry is derived from the log entry since such a table entry would match the table entry .

No table entry is derived from the log entry since such a table entry would match the table entry . No table entry is derived from the log entry since such a table entry would match the table entry . No table entry is derived from the log entry since such a table entry would match the table entry . No table entry is derived from the log entry since such a table entry would match the table entry .

Reference is now made to which is a flow chart illustrating the procedure of in accordance with a disclosed embodiment of the invention. By way of example and not limitation the method is described hereinbelow with reference to the aggregated table shown in .

Next at step the aggregated table is reset so that the next table entry to be read will be the first.

Next at decision step it is determined whether there are any more table entries in the aggregated table to check against the current log entry .

If the determination at decision step is affirmative control proceeds to step . The next table entry is read from the aggregated table .

Next at decision step it is determined whether the field in the current log entry matches the field in the current table entry .

If the determination at decision step is affirmative control proceeds to decision step . It is determined whether the field in the current log entry matches the field in the current table entry .

If the determination at decision step is negative control proceeds to step . A new table entry is created derived from the current log entry and added to the aggregated table .

Next at decision step it is determined whether there are any more log entries to check. If the determination at decision step is affirmative control returns to step .

If the determination at decision step is negative control proceeds to a final step and the procedure terminates.

The following description discloses operations in which proposed removals of users from user groups are automatically evaluated. Such user groups are accorded respective common access privileges to data elements. It should be noted that a user may itself be a user group. Furthermore a user group from which it is proposed to remove a user may be a constituent of other user groups. Thus such proposals are treated as removal of a set of users from a superset of users. Accordingly the methods that are disclosed below are performed iteratively and recursively.

Reference is now made to which is a flow chart of a method for verifying the effectiveness of a proposed removal of a user from a user group in accordance with a disclosed embodiment of the invention. The steps of the method are shown in an exemplary sequence in for clarity of presentation. However it will be evident to those skilled in the art that many of them can be performed in parallel asynchronously or in different orders. While the method is sometimes disclosed with reference to this is merely for clarity. The method is applicable to many system configured other than the embodiment of . For example systems that do not employ GUI applications or access control lists.

Referring again to the administrator uses the GUI application to specify a set of proposed removals of users from a user group.

In the sequence explained below the administrator selects a containing user group. The portion of the data elements in the file system to which the user group has access are displayed as well as the users and user groups in the containing user group. The administrator selects a displayed user or user group to propose removing the selected user or user group from the containing user group.

The above steps may be repeated allowing the administrator to propose multiple removals of users from user groups.

Referring again to at initial step a user group and a user proposed to be removed from that user group are selected.

Next at decision step it is determined whether there are any more data elements to which members of the current user group have access. Normally the determination in the first iteration of step is affirmative. In the embodiment of decision step can be performed by scanning the ACL .

If the determination at decision step is negative control proceeds to final step and the procedure terminates. A report is provided to the operator which indicates the status of the proposed residual access privileges of the user with respect to the data elements that were evaluated as described below.

If the determination at decision step is affirmative control proceeds to step . A data element to which members of the selected user group have access is selected. It will be evident from inspection of that step is performed iteratively and the data elements for the current user group are evaluated cyclically. However the order of evaluation among the data elements in a cycle is not critical.

Next at decision step it is determined whether it is necessary to process alternative groups of which the selected user is a member besides the group selected at step .

If the determination at decision step is negative control proceeds to step where an indication that no alternative access is possible with respect to the current data element is stored or reported to the operator. Control then returns to decision step .

If the determination at decision step is affirmative control proceeds to step . An alternative group of which the selected user is a member is selected. Step is performed iteratively and the alternative user groups are evaluated cyclically. However the order of evaluation in a cycle is not critical.

Next at decision step it is determined whether members of the current alternative group have access to the selected data element.

If the determination at decision step is affirmative then control proceeds to step . It is concluded that following implementation of the proposal the user would retain alternative access to the current data element that is accessible by the selected user group. An indication of this fact for example an error indication is provided to the operator and details may be stored for subsequent reporting e.g. current group user data element and alternative group may be reported. Control then returns to decision step and the procedure repeated by considering the remaining data elements that are accessible by the selected user group.

Reference is now made to which is a flow chart of a method for determining if a proposed removal of a user from a user group would prevent the user from repeating historical data accesses to storage elements in a file system in accordance with a disclosed embodiment of the invention. This method provides the operator with additional information thereby improving the quality of a decision to implement or reject the proposal. It is assumed that a record of historical data accesses by users of the file system has been compiled. In addition to the use of an aggregated table as described above the record of actual accesses may be prepared using known techniques that optimize information retrieval according to users for example by compiling user specific files or by the use of hash tables to deal with many users.

At initial step a proposal is defined to remove a user from a selected user group having group data access privileges to a portion of the data elements of the file system. It is understood that in the event the current user is a set of users e.g. itself a user group initial step is iterated for each member of the set. Multiprocessor implementations and the use of concurrent processes to efficiently accomplish this and to implement recursive operations will occur to those skilled in the art.

Next at step a historical data access is selected from a record of such accesses. The order of this selection is not critical. The selection may comprise an entry of an aggregated table as described above with reference to or may involve the use of a hash table. Alternatively the selection may be made simply by serially accessing a log file containing data accesses of some or all users.

Control now proceeds to decision step where it is determined if the current data access selection relates to the subject user. If the determination at negative then control proceeds to decision step which is described below.

If the determination at decision step is affirmative then control proceeds to decision step in which it is determined if the user s privileges by virtue of membership in an alternate user group need to be considered. This step is performed identically to decision step .

If the determination at decision step is negative then control proceeds to final step . It is concluded that access to the currently selected data element would be prohibited as it cannot be accessed via any alternate user group to which the user belongs. Thus the user would not be able to repeat data accesses that he had executed in the past if the proposal is implemented. A report is prepared for the operator and the procedure ends. If desired the procedure can be repeated to evaluate the extent of loss of the user s historical access rights by reverting to step and evaluating the remaining historical data accesses.

If the determination at decision step is affirmative then control proceeds to step . An alternate user group is selected. Step is identical to step .

Control now proceeds to decision step where it is determined whether members of the current alternative group have access to the currently selected data element. If the determination at decision step is negative then control returns to decision step to consider the possibility of user access via another alternate user group. Decision step is performed in the same manner as decision step .

If the determination at decision step is affirmative then at step an indication that the current access remains allowable is stored and optionally immediately reported to the operator.

Control now passes to decision step where it is determined if more data accesses remain to be evaluated.

If the determination at decision step is negative then control proceeds to final step . The user has been determined to retain access rights to all its historically accessed data elements. A report is prepared for the operator indicating that all historical accesses of the user are allowable and the procedure terminates.

Reference is now made to which is a detailed flow chart of a method for verifying that a proposed removal of a user from a user group would not prevent the user from repeating historical data accesses in accordance with an alternate embodiment of the invention. The method is described with reference to the embodiment of .

At initial step the administrator uses the GUI application to specify a set of proposed removals of users from user groups as described above with reference to .

The GUI application scans the set of proposed changes and produces a set of groups and users affected by the changes.

Next at step the GUI application scans the ACL for the affected groups and converts each group into a set of users in that group this may be recursive for groups within the group to obtain a complete set of users affected by the proposed removals of users from user groups.

Next at step a historical access is identified. In the embodiment of this can be done by reading the first table entry of the aggregated table is read. In an alternative embodiment a log entry of the log file may be used instead.

Next at decision step it is determined whether the field in the current table entry matches the user selected at step .

If the determination at decision step is affirmative control proceeds to decision step . Referring again to it is determined whether residual access permissions remaining after the proposed removals of users from user groups would still allow the user referenced by the field in the current table entry to access the data referenced by the field in the current table entry .

Referring again to if the determination at decision step is negative control proceeds to decision step .

If the determination at decision step is affirmative control proceeds to step . The GUI application stores the contents of the current table entry for subsequent output to the administrator in a graphical format at the end of the procedure. Additionally or alternatively the details may be output at this step.

Next at decision step it is determined whether there are additional table entries to be processed for the current user.

If the determination at decision step is affirmative control proceeds to step . The next table entry is read and control returns to decision step .

If the determination at decision step is negative control proceeds to decision step . A determination is made if there are more users in the set of affected users who have not yet been selected.

If the determination at decision step is negative control proceeds to a final step . The GUI application displays the results of the procedure to the administrator and the procedure terminates.

The information provided by the methods disclosed with reference to may be consolidated into a report for evaluation by the administrator who is thus able to evaluate the effectiveness and any disadvantages of implementing the proposed removal of the user from the user group.

In some embodiments the method disclosed with reference to or is only performed if the method disclosed with reference to produces no errors.

The previous embodiments have focused on the consequences of removing a user or group of users from a user group. In other embodiments a system such as the system is configured to respond to a proposal in which privileges to access specified data element e.g. a directory is to be removed from the scope of common privileges of a user group. Unlike the previously described proposals the composition of the user group is to remain unchanged.

Reference is now made to which is a flow chart of a method for verifying the effectiveness of a proposed removal of privileges of a user group to access a data element in accordance with a disclosed embodiment of the invention. It is assumed that a historical record of data accesses has been prepared as described above. At initial step a user group and a data element are selected.

Next at step a user is selected from the user group. As noted above the user may itself be a set of users. Appropriate iteration and recursion are therefore applied.

Control now proceeds to decision step where it is determined if the current user has alternative access to the data element that was designated in initial step . This determination is made by applying the method disclosed above with reference to and compiling interim reports from the information stored in steps .

If the determination at decision step is affirmative then an affirmative report is prepared at step . Control proceeds to decision step which is described below. Alternatively if decisional criteria require that no user in the group have alternative access to the data the procedure could terminate at this point in which case control would proceed directly to final step .

If the determination at decision step is negative then a negative report is prepared at step . Control proceeds to decision step . Here it is determined if the current user would still be able to perform all the historical accesses that were recorded. This determination is made by applying the method disclosed in .

If the determination at decision step is affirmative then control proceeds to step . An affirmative report is prepared based on the data stored in step . Control proceeds to decision step which is described below.

If the determination at decision step is negative then control proceeds to step . At least one historical access performed by the current user would no longer be possible. A negative report is prepared based on the information recorded in step . Control proceeds to final step and the procedure terminates.

At decision step it is determined if there are more users to be evaluated who are members of the designated user group. If the determination at decision step is affirmative then control returns to step to iterate the method with a new user.

It will be appreciated by persons skilled in the art that the present invention is not limited to what has been particularly shown and described hereinabove. Rather the scope of the present invention includes both combinations and subcombinations of the various features described hereinabove as well as variations and modifications thereof that are not in the prior art which would occur to persons skilled in the art upon reading the foregoing description.

