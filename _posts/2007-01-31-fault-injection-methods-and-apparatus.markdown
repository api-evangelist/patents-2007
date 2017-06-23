---

title: Fault injection methods and apparatus
abstract: A method of testing a target in a network by fault injection, includes: defining a transaction baseline; modifying at least one of an order and a structure of the transaction baseline to obtain a modified transaction with malformed grammar; and transmitting the modified transaction to a target. The method may further include, receiving a feedback from the target to determine fault occurrence. An apparatus for testing a target in a network by fault injection, includes: a driver configured to generate patterns, where a pattern can generate a plurality of packets for transmission to the target, the pattern being represented by an expression with a literal string and a wild character class; and a network interface coupled to the driver and configured to transmit and receive network traffic.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=07620851&OS=07620851&RS=07620851
owner: Cenzic, Inc.
number: 07620851
owner_city: Santa Clara
owner_country: US
publication_date: 20070131
---
This application is a continuation of U.S. patent application Ser. No. 10 087 000 filed Feb. 28 2002 now U.S. Pat. No. 7 185 232 which is hereby fully incorporated herein by reference. Benefit of all earlier filing date is claimed for all common subject matter.

This application claims the benefit of and priority to U.S. Provisional Application No. 60 272 486 by common inventors Penny C. Leavy Michael Gregory Hoglund Jonathan Walter Gary and Riley Dennis Eller filed Feb. 28 2001 and entitled SYSTEM AND METHOD FOR GENERATING AND ANALYZING NETWORK TRAFFIC . Application No. 60 272 486 is fully incorporated herein by reference.

This disclosure relates generally to fault detection and testing methods and more particularly to an apparatus and methods for detecting and testing vulnerabilities in a system under test.

Security attacks are becoming more prevalent and costly. These attacks often lead to losses of critical information decreases in productivity and negative effects on corporate reputation. For example various worms were able to spread through the Internet in 2001 and infect over 850 000 servers resulting in the disruption of operations of the affected businesses and organizations. While traditional security devices such as firewalls and intrusion detection systems IDS are effective at the network layer these devices are unable to provide effective security in the application layer.

Additionally networks have become more critically complex. It is difficult to test the myriad scripts and protocols even on a small business network let alone on networks that span nationally and globally. Thus creating tests for extremely complex protocols can be complex costly and in some instances not feasible.

Additionally due to security virus and other issues critically affecting networks there is an overwhelming market need for network and software application risk management products.

Accordingly there is a need for an apparatus and method that provide effective detection and testing of vulnerabilities and that will overcome the deficiencies mentioned above.

In the description herein numerous specific details are provided such as examples of components and or methods to provide a thorough understanding of embodiments of the invention. One skilled in the relevant art will recognize however that an embodiment of the invention can be practiced without one or more of the specific details or with other apparatus systems methods components materials parts and or the like. In other instances well known structures materials or operations are not shown or described in detail to avoid obscuring aspects of embodiments the invention.

Reference throughout this specification to one embodiment an embodiment or a specific embodiment means that a particular feature structure or characteristic described in connection with the embodiment is included in at least one embodiment of the present invention. Thus the appearances of the phrases in one embodiment in an embodiment or in a specific embodiment in various places throughout this specification are not necessarily all referring to the same embodiment. Furthermore the particular features structures or characteristics may be combined in any suitable manner in one or more embodiments.

Target can represent a complete collection of code a partial collection of code or a combination of components or devices which are effected by code .

Transactions that occur over network between network elements e.g. SUT include network layer transactions and application layer transactions . Network layer transactions involve for example router information TCP information Ethernet information and or other low level transaction information . Application layer transactions involve for example web information file transfer information electronic mail information and or other information that is an aggregate of low level transactions. A given application layer transaction may exercise particular systems events such as for example database systems electronic mail systems and or logging events and or other systems events .

The precise permutation of a transaction that induces a fault has a concrete form represented by the current iteration of the overall pattern. The output of the pattern for this iteration produces the associated fault. Thus the output becomes an important event in the SUT in that it causes a fault. Thus there is value in examining the network for the given fault pattern. A pattern describes a set of known strings of data interjected with fault inducing sub fields. The precise format of the pattern at a given permutation or iteration can be represented by an expression of the form as shown in Table A.

The expression as represented by the pattern can be used to form a subsequent expression which can be utilized by an intrusion detection system sniffer or firewall to detect and trigger on the above mentioned network at least one transaction that matches the expression.

Permutations of grammar and value when offered as input to runtime software environments tend to solicit a wide range of responses. Some of these responses are indicative of a software bug. Other responses indicate benign behavior with little environmental effect. Many software bugs have a dangerous impact on the security and or reliability of a software system. Certain input permutations are more likely to discover or induce a bug in software regardless of the target system e.g. target in .

To mutate a network transaction that is sent to a target or code in an SUT a baseline or starting point is typically needed. This starting point is defined as a transactional baseline . Once the transaction baseline is obtained the transaction baseline can be used to create supplement transactions which are mutations of the original transaction baseline. These mutations can be used to enable undesired events and are therefore used to discover bugs viruses and or other faults in the SUT . Thus the mutations are transmitted as modified transactions to a system under test and feedback may indicate if a fault occurrence had occurred in response to the modified transactions .

Various methods to mutate a transaction baseline to cause malformation include the following as described below I grammar injection II value injection and III other vulnerability detection methods.

 I Grammar Injection Grammar is the order and structure to a transaction. Many transactions require value fields that are separated by metacharacters or delimiters . shows an example transaction with value fields through and metacharacters or delimiters and . The number of value fields and delimiters may vary. In the example of value fields and are separated by delimiter and value fields and are separated by delimiter . What determines a value and what determines a delimiter is based on numerical character values.

The trick in the method is to select a numerical range of character values that are to be treated as meta characters. This range does not have to be continuous. The range may include several smaller sub ranges which when combined as a whole constitute the set of all characters which are to be treated as delimiters.

The order in which they occur determines if a malformed grammar exists. Malformed grammar on a variety of cleartext protocols such as HTTP could induce parser errors.

The following algorithms can be applied for creating malformed grammar. The testing unit may be configured to create the following strings.

The patterns represent a template for generating a plurality of transactions which are delivered as network traffic . The construction of the pattern is particular to a technique for malforming grammar of a transaction.

Patterns consist of sub fields or Functions as they are called in the attached texts that each have a particular behavior. The sequence of transactions represented by a pattern depend on the combination of sub fields in the pattern. Sub fields may be literal data values and some may represent a set of values. Sub fields that represent sets of data are said to iterate. There are two specific ways to inter relate subfields within a pattern a Nested and b Non nested. Nested relationships cause sub fields that iterate to multiply their results. This is called nested iteration . Various examples of pattern iteration and sub field types are described in further detail below.

1. Remove a field s from a transaction As shown in the example of Table 1 the original transaction includes fields with the characters ABCD and the delimiter between fields. Of course other value fields and other delimiters may be used. One of the fields for example with characters ABCD is removed as shown in the modified transaction. This modified transaction may confuse a parser. Other characters may also be used besides ABCD .

2. Duplicate a field cause a field to appear more than once A field with characters ABCD is duplicated as shown in the modified transaction in Table 2.

3. Create Double Delimiter cause a delimiter to appear twice between value fields A delimiter is duplicated as as shown in the modified transaction in Table 3. Other delimiters may be used besides the semicolon character .

4. Send all delimiters in a transaction All characters are changed into a delimiter as shown in the modified transaction in Table 4.

5. Send a blank transaction transaction with no values Usually part of a transaction that is considered an atomic unit is removed as shown below in Table 5.

6. Send a single character delimiter value pair at a repeated large buffer All characters are changed into a delimiter value pair e.g. W. or A as shown in the modified transactions in Table 6. These transaction types can cause buffer overflow in parsers.

7. Send unbalanced pair For example if an open parenthesis character is present in a transaction then the close parenthesis character is omitted as shown in Table 7. The same unbalanced pair configuration can apply to other pair characters such as pipes quotation marks and or other pair characters. One of the pair characters may appear at the end of a field as for example shown by the string ABCD ABCD ABCD in Table 7. An unbalanced pair may confuse a parser causing the parser to treat the characters inside the unbalanced pair as special information.

8. Replace delimiters with random ranges that cover the delimiter value. This means using not only the delimiter value but a range of characters that are near to about the delimiter s original numerical value. For example not just a character but also 

9. Use alternative character encoding through a translation table Alternative encoding is one example of a grammar injection method for fault detection.

Many programs accept user data in many different formats. For example mail programs often accept data in Unicode ASCII and or other formats. This feature can present a problem when a user can change the data format of the input transaction in such a way that the input passes security checks and when the input transaction is parsed at the end e.g. at the target system the input transaction behaves maliciously.

Alternative encoding involves encoding a transaction field with characters that are equal in nature but different in representation. Table 8 lists some examples of an alternative encoding for a carriage return. These alternative encoding includes for example n and 2f .

The technique is to use a character replacement translation table. This may be a set of characters replaced by an alternative set of characters.

As another example if a Java Server Page JSP is requested from a web server by a client the request should be parsed. The web server is case sensitive and only understands the lowercase .jsp . If all caps .JSP is requested see Table 8 then the file is handled via a default text handler and as a result the source code becomes visible at for example the client side.

This is a specialization of the alternative encoding method where the character translation table is from lower case versions of each alphabetic letter to upper case versions of the alphabetic letter.

As shown in the example in the parser in a system under test interprets the alternative encoding in the transaction and thus misclassifies the transaction since the parser is looking for a lower case version of .jsp . As a result state occurs and the actual Java source code is shown via a client device such as the testing unit . The showing of the source code may result in potential breaches of security since the source code may for example include passwords or other information such as trade secrets. In contrast a non fault state does not allow the showing of the source code .

 1 Internet Information Server IIS 5.0 Using the string . c0 af.. in a certain way in a Uniform Resource Locator URL allows a malicious user to execute commands on a remote server. For example the URL in Table 9 returns the source of default.asp.

 2 IIS 4.0 Invalid codes are passed on by the testing unit to the file system of the target. For example the code 0G would be passed on to the filesystem even though 0G is not a valid hexadecimal value. The sequences are then converted to actual characters by the target system which allows for specifying some characters that are not permitted.

 3 theBat The following attachment name shown in Table 10 is not properly filtered due to the alternative coding in the name. The saved attached file names are indicated in Table 10 also.

This is a specific example of the ISO character set alternative encoding. The SUT is performing analysis of attached filenames to ensure that the target is not being saved to an unsafe location. An unsafe location in this example is the windows directory. Since the filter does not handle ISO character sets the encoded filename looks innocent and thus is allowed to pass. Once decoded however we can see that the filename is indeed malicious. The failure of the software filter to handle all possible decodes of the attached content constitutes the vulnerability.

This is an algorithm for generating alternative encodings of characters. A character A will be prefixed with a slash if the resulting character sequence is A . The prefix character can be chosen. A subsequent technique is to allow the prefix of a multi character sequence. A multi character prefix could be and the character A prefixed would result in the following character sequence A .

A specialization of the technique is to prefix delimiter characters which are chosen by numerical range with a special character known as an escape character which can be chosen depending on the target system. An example escape character is a backslash and a delimiter character prefixed would result in the following character sequence .

 II Value Injection Value injection does not alter the grammar of a transaction. Instead as shown in value injection injects or alters the input fields in a transaction . Value injection can be useful for example to exercise inputs to Application Programming Interface API calls and to change the behavior of database transactions. The value injection techniques may be combined with grammar injection to obtain maximum effect.

Ghost Characters Ghost characters encoding is one example of a value injection method for fault detection. This method involves encoding a transaction field with characters that do not affect the transaction. Ghost characters may be added to a server request where the characters do not affect the validity of the request and may be used for example to cause misinterpretations by intrusion detection systems IDS or firewalls that are detecting network transactions.

This is an example of multiple SUTs each which respond to the same request. The ghost characters are significant in one SUT while being ignored in the other SUT. The resulting transactions are thus unique to each SUT and attempts to measure the state of one SUT by the other SUT may become desynchronized.

Additionally ghost characters can cause logs to not report correct information. Ghost characters are generally stripped out of a request or are completely ignored by the request and as a result ghost characters do not cause problems with the request. The testing unit can be configured to insert a variety of characters into any request regardless of protocol. Table 11 lists an example of an encoding for a ghost character.

As an example a filtering and monitoring system is looking for the string PASSWORD and the target SUT accepts ghost characters and . The subsequently ghosted transaction is sent over the network as P A S S W O R D . The SUT interprets the transaction as PASSWORD . The monitoring system interprets that data as P A S S W O R D and thus fails to trigger on a valid PASSWORD transaction.

Input Field Injection System calls are used internally with a program to access the file system or spawn other processes. If a remote user can control the arguments to a system call the user can often cause commands to be run improperly or private files to be viewed or modified.

This method involves replacing an input field in a transaction field with characters that may cause faults. This input field is typically used in system calls or API calls for enabling an event such as for example the opening of a file.

Filenames For example in an effort for a target system in a system under test to open a password protected file or to open a log file the characters may be placed in the input field as shown in Table 12.

The remote machine e.g. testing unit requests the file ...... and the contents of the root filesystem will be displayed. In this manner any file on the system can be accessed.

As also shown in Table 12 a repeatable Relative Path bug allows the web request to traverse upward in the filesystem by inserting .. into the path. The user can view any file on the system by using .. to traverse the filesytem upward.

Another example of using value injection to alter a file path is as follows. A SUT accepts request target i.e. GET index.html. The value stored in target directly altered to .. .. .. .. etc passwd indicates a target on the system. The target is valid. The subsequent transaction GET .. .. .. .. etc passwd is valid in the context of a fileystem. If the server software fails to filter the directly modified value the SUT will be fooled into returning a file that was not intended as part of the design.

Numerical Ranges Typically if there is a range that may have a limit then maximum values mid point values minimum values and or signed or unsigned and off by one errors may produce a fault. For example if an input field has the content ABCD then changing the input field content A .D may cause a fault in the target system because the character is out of range with the Hexadecimal values for the characters A through Z.

If there is a range restriction on an input such as the numbers 1 100 then the values 1 50 and 100 should be attempted. If the SUT expects numbers to be in the range 1 99 the number 100 may cause a fault even though technically the number 100 can be supplied.

Signed conversion errors occur because the same number occupying the same amount of data space can represent either a zero based range i.e. 0 255 or a signed range with zero as a midpoint i.e. 127 to 127. Supplying a value of 255 may result in a signed representation of 1. This may cause arithmetic to be invalidated.

User Identity Other value injection techniques include controlling user identity fields which indicate resource names or user identities and brute force attacks based on dictionary.

If a number is used to represent a user identity then this number can be iterated throughout a range in an attempt to spoof the identity of another user. If the user ID is AAAA 0000 then a brute force attack would iterate the input values through a range 

Passwords brute force attacks. This is a simple example of a sub field that represents a set of data. The set would be a dictionary of possible passwords. The pattern would supply every password from the dictionary.

Range injection alter input characters over a range that includes the character. This is the same as User identity example above.

 a replace field with or .exe many possibilities Some API calls allow the specification of a matching expression such as .exe which means match any single character followed by .exe so the expression would match A.exe and Z.exe both. Different systems have different expression formats. The key is to supply expressions and determine if they are being interpreted by the target SUT. Matching expressions may be used to cause the wrong file to be opened or returned.

 b can cause SQL transaction problems The character and the character are expressions for matching in SQL transactions. Supplying input fields such as and may cause multiple records to be returned from the database.

The buffer overflow technique can be categorized as a value injection method. To create a buffer overflow fault injector extra characters are inserted into a transaction where the characters are typically separated by a normal command or field separator. This fault injector or mutated transaction is transmitted to for example a system under test in order to detect faults in the SUT .

Typically in software operations a process is broken into functions that are called periodically so that the process can manage memory and input output operations. When a function is executing the function needs to store data regarding the operation that is being executed. When a function needs to store a temporary value the function places the data on a stack which is a memory region that will grow and shrink as functions use the memory region. A network transaction may be formed by fields and if a field is made too large the problem of buffer overflow may occur. Thus when a program writes past the bounds of a buffer this buffer overflow condition will cause the next contiguous chunk of memory to be overwritten.

The reading or writing past the end of a buffer can cause a number of diverse and often unanticipated behaviors 1 programs can act in strange ways 2 programs can fail completely and or 3 programs can proceed without any noticeable difference in execution. As shown in the example in during a buffer overflow the buffer overflows on the stack and grows toward a saved return address . Thus the attacker may be able to change the return address . As a result when the function is finished executing the return address is popped off the stack and execution branches to the address. If the attacker can overwrite this return address then the attacker has control of the processor.

Table 13 lists some of the function calls that commonly lead to buffer overflow conditions. Additional details on buffer overflow conditions are described in for example HACK PROOFING YOUR NETWORK INTERNET TRADECRAFT Copyright 2000 published by Syngress Media Inc. 800 Hingham Street Rockland Mass. 02370. The above reference HACK PROOFING YOUR NETWORK INTERNET TRADECRAFT is fully incorporated herein by reference.

 1 Eserv 2.50 A user can view any file on the system by using .. to traverse the filesystem upward. For example the following as shown in Table 14 would show all configuration information including account names.

 2 SYMANTEC Mail Gear 1.0 Web Interface Server Using the .. string a user can fool a Common Gateway Interface CGI script into displaying any file on the system. For example the following as shown in Table 15 would display the boot.ini file on an NT system.

The entire network can also be scanned for problems by inserting a procedural function in place of the destination IP address and then setting up a Checkpoint to watch for a response that implies that the scan was successfully performed.

Data Leakage Data leakage occurs when an application or network gives away valuable information for free to a potential attacker. For example data leakage is problematic if the attacker is trying to determine the structure of a filesystem or the contents of an accounts database. A common place where data leakage occurs is within error messages. An attacker may craft special requests causing an error result and the error message sent to the attacker may contain valuable information such as the status of the application the existence of a user account or the topology of a database or file system.

As an example CGI programs can be scanned for leaked data. Every response to the scans below Table 16 can be parsed for relevant data or saved to disk. Error conditions can be detected or certain tags can be gathered from the response.

 1 Gathering Process Information from the Auth Service By connecting the Auth service a remote attacker can determine which processes are running as root.

 2 Determine Which Accounts Exist If the response for a bad password is different than the response for a bad user name then a remote attacker can determine valid usernames by noting the different responses.

 3 Error Conditions Leak True Path Connecting to a CGI script incorrectly can cause the server to return actual filesystem paths. This fault can be tested for by simply noting the return values from the scripts for certain key characters such as c inetpub and or the like.

Injection of Unfiltered Metacharacters to Secondary Process A server component may call another component with user supplied input. In this situation the server component filters certain characters or character sequences to limit the string that is passed to the other component. For example a CGI script that lists the contents of a download directory might call Is DIRNAME with DIRNAME being supplied by the client. If certain characters are not filtered then requesting the directory rm rf would cause the command Is rm rf to be run on the command line. This particular command would be very destructive.

Table 17 lists at least some the characters that should never be passed to the shell. The target system can be tested to determine which characters are filtered and not filtered. These delimiters and escaped sequences can be stored in a file and directly read from the file by the testing unit to simplify testing.

As shown in the example in a transaction may include primary information followed by a delimiter and an additional command . A first parser in an SUT may allow the delimiter and additional command to pass through. The shell in the second parser will then execute the additional command to cause a fault condition. As an example the content in the transaction field may be put in an on line form on a webpage. The content may be as follows in Table 18. The primary command content is the username username . The delimiter is . The additional command is rm rf . The username is passed through with the delimiter and additional command rm rf . When the shell in the second parser executes the additional command a fault event is generated such as the deletion of contents in the hard drive of the system under test.

As shown in another method is by having a translator convert a delimiter into a character that should not be passed to the shell. For example as shown in Table 19 assume that the original transaction content includes primary command username delimiter 3F and additional command rm rf . The parser will pass the original content username 3Frm rf . However the translator will convert the original delimiter 3F into . As a result the parser will parse the translated transaction with content username rm rf leading to a fault event of hard drive content deletion.

The following are other examples of the vulnerabilities made possible by Injection of Unfiltered Metacharacters to Secondary Process.

 1 Campas CGI A remote user can execute any command on the system by executing a CGI script as shown in Table 20. This command would print the password file.

 2 fcheck The checker fcheck is a file integrity checker written in Perl. This checker uses the system call and passes the filename to the shell. If the filename has embedded metacharacters then arbitrary commands can be run.

Extraneous Meta characters For Causing Misclassification Classification is performed by many on line applications. Complex applications often handle multiple types of requests. The application determines which type of request is being submitted and handles the request appropriately. For example if a request for a graphics file is made to a web server the image is streamed to the client browser in binary. If a request for a script is made to a web server then the script is parsed and interpreted by the web server and the result is passed to the web client. Many web servers determine the type of file by examining the file extension usually three characters following the last period in the file name . If a web server can be fooled into misinterpreting the type of file security problems may occur. For example many script files contain sensitive data such as passwords or file structures. If web server can be tricked a remote attacker can obtain the source code to the script.

This method involves encoding characters in a transaction that causes misclassification of the transaction. These meta characters are not alternative encoding because characters are not being converted into equivalent characters. These meta characters are also not ghost characters because these characters do change the transaction. These characters do not involve input field injection because the input field is not changed or because extraneous meta characters are added into the original characters in the input field.

The ASP DOT Bug If an ASP file is requested on MICROSOFT IIS Servers then the file should be parsed. However on some servers if an additional period . is appended to the end of the file name file.asp. then IIS will not understand that an ASP file is being requested and the default text handler will deliver the source code instead.

Table 21 lists an example of modifying a source code based on use of extraneous meta characters. The source code file target.asp is changed to target.asp. and as a result the parser misclassifies the file as a non asp file because of the modified extension .asp. resulting in result B instead of result A . The result B may be for example a default action that shows source codes containing passwords. As a result the revealed passwords will permit security to be compromised.

The following are other examples of the vulnerabilities made possible by Extraneous Meta characters For Causing Misclassification.

 1 Truncating Strings to webhits.dll On MICROSOFT IIS Servers a problem exists where an Internet Server API ISAPI filter may truncate a URL. Table 22 lists a problematic request that is passed to the webhits.dll because the request ends in .htw but the DLL then truncates the URL to about 200 characters.

Sensitive Dependance Resource Consumption If an application spends an undue amount of resources on any particular transaction then that transaction may be manipulated to create a resource consuming denial of service DoS situation. The HTTP GET request may be modified and created into templates for valid and invalid requests.

Additionally if random garbage content is inserted in a transaction field the target will parse the content and the parser will work harder to understand the field content. This condition may result in DoS problems.

The following are other examples of the vulnerabilities made possible by Sensitive Dependance Resource Consumption.

 1 Fragmented Segmented TCP IP Transmission Control Protocol Internet Protocol TCP IP packets can be fragmented and segmented. Furthermore these fragments may overlap. If these fragmentations and segmentations occur then the server must reconstruct the data. Bombarding servers with this type of traffic can cause the server to stop responding due to the overhead processing of the TCP IP protocol.

 2 ICMP Amplifier SMURFING Some networks will respond to broadcast Internet Control Message Protocol ICMP ping packets and given a spoofed source address the responses will bombard a target with traffic. The overload may cause the target network to fail.

Invalid State Almost all programs have a state i.e. do certain things in a certain order . At each point where a program can make a decision the program is said to be in a certain state. The program will typically have a different set of choices to make depending on which state the program is at. Problems occur when a program can make invalid decisions. Typically an invalid decision can lead a program into a processor loop or can lead a program into simply crashing. An invalid decision may also lead to a resource leak. An invalid decision may lead a program into waiting for input that will never arrive or may lead a program into a deadlock situation. These situations may lead to denial of service problems.

In one embodiment the testing unit can replicate TCP sessions. The testing unit can modify and or edit patterns in order to test for example a TELNET server for a variety of configuration options in the client server relationship.

 1 Real Server Malformed URL The following URL in Table 23 can cause a server hang and only requires an additional question mark at the end of the URL.

 2 MSDTC.EXE The testing unit can be connected to a TCP port on a Windows NT machine and then disconnected. The MSDTC.EXE begins to consume 100 of CPU utiliztion.

 3 Stream of Zeros The testing unit sends a stream of binary zeros to any number of Windows 2000 TCP or User Datagram Protocol UDP ports and begins to consume 100 of CPU utilization.

 4 HP OpenView OmniBack The testing unit connects multiple times to TCP port and HP Openview OmniBack goes to 100 CPU usage and becomes locked. As a result a restart is required.

 5 PCAnywhere The testing unit is connected to TCP port and sends a large string of garbage characters. PCAnywhere will then hang.

Blind Trust A problem with network is blindly trusting data supplied by a client. Often a piece of client and server software is written in tandem in such a way that the client would never send dangerous data to the server. However an attacker could re write portions of the client software in such a way as to break the security.

As an example assume that a server accepts a username and password from the client. The client calculates the length of the password and supplies this length value along with the password and the username. If the amount of server memory allocated for the password was based on the user supplied value then the remote user could easily cause a fault.

 1 Testing of LOTUS Domino Mailbox The testing unit can send a request to a server in order to send or receive electronic mail. This request contains the name of the user s mailbox. The testing unit can be used to sniff and replay this request and alter the request so that a different user s mailbox is being specified. The current user does not have authority to access the different mailbox being specified. It has been found that LOTUS Domino does not validate the mailbox name. The mailbox name that is specified in the request is the name that is used. Thus a client can authorize correctly with the mailbox and then change the mailbox name to access the mailbox of any other user.

 2 Testing Windows 9X SMB vulnerability In the Windows 9X SMB the password length is passed to the server in the same packet as the password and only the number of characters specified in the length is checked against the real password. Thus if a length of 1 is passed less than 255 passwords are possible and as a result brute force attacks are not difficult to carry out.

Below Threshold One common type of security bug is due to an attacker performing an attack under the threshold of logging software. The threshold can appear in the logging mechanism of a piece of software or in an IDS system. Testing for this type of vulnerability can involved for example inputting an item that normally would be logged in a lesser or less visible manner. In the drip port scanning method a port is scanned with the requests transmissions spread out over a long period of time. IDS systems often are unable to correlate data over such a long period of time. The problem results from having too much data over that period of time to perform intelligent correlation of all of the data.

The following are other examples of the vulnerabilities made possible by the below threshold technique.

 1 Secure Shell SSH Earlier versions of SSH had a login bug where if a user had entered a bad password one time or two times a failed login was not recorded. The failed login was only recorded if the user failed three times.

 2 Snort Snort detects unusual fragment usage on a network. However if the fragments are over 128 bytes the fragments are not flagged as unusual.

Improper Configuration Many systems have the potential to be secure but remain vulnerable due to improper installation and configuration. These improper configuration include improper file and directory permissions improper rules on how to handle certain commands and failure to change a default password.

The delimiters can be parsed out to obtain intermediate representations and . For intermediate representation the value V is replaced with a buffer a function BF. Each buffer BF may have a range of for example 1 to 1000 in increments of 100. Thus in this example the intermediate representation will have a total of 10 patterns.

For intermediate representation the value V is replaced with a buffer BF with the buffer BF having a range of for example 1 to 1000 in increment of 100. Thus intermediate representation will also have a total of 10 patterns. Similarly intermediate representations and each have values V replaced by the buffer BF.

A pattern specifies how a packet is to be generated over a network. Thus a pattern represents a set of rules for generating packets. A single pattern can be responsible for generating for example thousands of packets. A pattern could for example generate DNS traffic HTTP traffic and or denial of service attacks.

Various methods are now discussed for building patterns that can be used for different types of injections for purposes of fault testing. Table 25 lists a collection of functions that may form a pattern. These functions can specify how to build for example an Ethernet header an Internet Protocol IP header a Transmission Control Protocol TCP header and a source port. By using functions together desired packet sequences can be generated.

The simplest function is static text which a user can type in the text character that is sent over a wire of a network. Table 26 lists a generated pattern where a packet is printed over the wire in the network. Every function can be individually edited. Thus the functions for the Ethernet header IP header TCP header and source port for a pattern will have the values A A B B respectively.

More complex functions may include for example a sequence through a series of numbers or read values from a file. The file may be in for example the memory which may be integrated in or accessible to the testing unit . Functions can also perform the task of handling activities such as calculating TCP IP checksums packet lengths and or dealing with Ethernet addressing. Functions may also perform repetitive tasking and may be derived objects that use an application program interface API .

Table 27 lists generated patterns where a packet is printed over a wire in a network with use of a sequence number. Functions that cause more than one packet to be generated are called iterating functions . A pattern with one or more iterating functions will generate multiple packets over a wire. One type of iterating function is the number sequence. The number sequence iterates through a range of integers. For example there are number sequences available for 8 bit 16 bit and 32 bit numbers.

Table 28 lists generated patterns where a packet is printed over a wire in a network with the source port function using a sequence e.g. sequence 4 to 6 .

Table 29 lists generated patterns where a packet is printed over a wire in a network with the source port function using a sequence number in flat mode.

Table 30 lists generated patterns where a packet is printed over a wire in a network with the source port function using a sequence number in nested mode.

Table 31 lists generated patterns where the source port function is using a sequence e.g. 1 to 3 in a parent pattern and the parent pattern is with for example two child patterns. A child pattern behaves as a normal pattern except the child pattern is only generated along with its parent pattern. Packets can occur in a particular order by making them children patterns.

Table 33 lists generated patterns having a parent pattern with an iterating child pattern. Iterating functions are noted with an asterisk n where n indicates the number of times that the function will iterate. Iterating children patterns contain an iterating function within them such as a buffer overflow test or a number sequence. An iterating child will generate many packets.

Table 34 lists generated patterns having an iterating parent pattern with an iterating child pattern.

Table 35 lists generated patterns having a parent pattern with a 3 way handshake Checkpoint. A checkpoint object permits a pattern to react intelligently to responses from a system under test. A pattern may be iterating until it hits a checkpoint and the checkpoint will inform the testing unit to stop the iteration task until a decision has been made. Checkpoints can be assigned to patterns in order to alter the behavior of the patterns.

The 3 way handshake checkpoint is typically used exclusively for spoofing TCP IP sessions to a remote host. When the 3 way handshake is used with a parent pattern the child patterns are often sent as part of the TCP session.

The 3 way handshake is noted in parenthesis in Table 35 because it is derived from the contents of the parent packet A A but it is not a direct dump of A A onto the network it is only indirectly based on the contents of A A. After the 3 way handshake is complete A A is handled normally and dumped directly onto the wire along with its children.

The SYNC ACK return packet is received from the system under test and is a type of packet that is related to TCP. The information from the return packet is then placed into the PARENT pattern prior to sending the PARENT pattern to the system under test. This process permits information to be obtained about the state of the system under test.

Table 36 lists generated patterns having a parent pattern with an Auto TCP Sequence with multiple children patterns. The 3 way handshake is useful because it automatically sets up the TCP sequence numbers in a session. The TCP sequence numbers are typically required for proper TCP session to be handled. Patterns that are auto sequencing a TCP session will use the Auto TCP Sequence function.

In Table 36 the Auto TCP Sequence number keeps count so that each child packet is considered in its proper order on the target device system under test . The first child always has the same sequence as the parent as typical in the operation of TCP handshakes. If an actual 3 way TCP handshake is performed the auto sequence number is typically required for proper TCP session handling.

Table 37 lists generated patterns having a parent pattern with a 3 Way Handshake Checkpoint Auto TCP Sequence function. The first three packets are considered the 3 way handshake of TCP IP. After the 3 way handshake is completed the actual patterns are dumped onto the wire. The auto TCP Sequence is incremented for each packet correctly indicating the current position in the byte stream for each TCP packet.

Table 38 lists generated patterns having a parent pattern with an Auto TCP Sequence with iterating child pattern.

Table 39 lists children pattern reference data in a parent pattern. Thus reference data can be referenced between patterns. A child pattern can for example reference data in another child pattern or even in the parent. In Table 39 the parent pattern has a small sequence from 0 3 and Child C references the Z function in the parent. If this were part of a TCP session each iteration of the parent would be an entirely new TCP handshake session.

Table 40 lists generated patterns having a parent pattern with a 3 Way Handshake Checkpoint with Auto TCP Sequence with Reference. The pattern has a 3 way handshake checkpoint that causes the SYN SYN ACK traffic for each iteration of the parent. Since the parent itself is not live the parent pattern s data being transmitted over the network is not typically seen. After the TCP handshake is completed the children are generated with auto sequence numbers. Note that child C is referencing data in the parent specifically the Z function.

Table 41 lists generated patterns having a parent pattern with a 3 Way Handshake with Buffer Test with REFERENCES

If the non fault condition of state occurs then the target system will be in a no fault state before the target system resets as shown in state .

Typically for fault injection methods based on extraneous meta characters and buffer overflow fault injector detection is made for a reset to determine fault occurrence.

A fault occurrence in state may also result in a non reset by the target system as shown in state . This non reset condition allows the testing unit to detect a fault occurrence.

A fault occurrence in state may also result in a non response by the target system as shown in state . This non response condition allows the testing unit to detect a fault occurrence.

In one embodiment based on the fault condition the testing unit can create an IDS signature based on for example at least some of the following known information 1 test pattern 2 direction of the transaction that caused the fault condition 3 transaction source identity 4 transaction destination identity 5 Protocol e.g. TCP . A parser in the testing unit can then translate the IDS signature into a regular expression . The regular expression is useful by being able to provide a more generic expression or broader definition of strings of data that define the parameters that caused a fault condition or problematic transaction. Regular expressions can be a powerful tool for manipulating text and data. For example regular expressions can play a vital role in constructing a World Wide Web CGI script which can involve text and data of all sorts. Additional details on regular expression may be found in for example Jeffrey E. F. Friedl MASTERING REGULAR EXPRESSIONS POWERFUL TECHNIQUES FOR PERL AND OTHER TOOLS 1st Edition O Reilly Books January 1997 . The reference MASTERING REGULAR EXPRESSIONS POWERFUL TECHNIQUES FOR PERL AND OTHER TOOLS is fully incorporated herein by reference.

The pattern from the testing unit represents an abstract description of a network transaction . An intrusion detection equipment that operate on signatures are driven by expressions that describe network transactions . Thus there is a conversion possible between a pattern from the testing unit and a signature expression.

The format of an IDS signature expression is typically proprietary but is usually very similar to a standard regular expression. For example a signature expression to detection of the character string etc passwd in a network transaction might look like as shown in Table 42 

A pattern describes all portions of a transaction in the context of a network protocol. A pattern may be using the substring etc passwd . The pattern is a TCP transaction and this fact can be used to generate the network protocol specific information for the IDS signature as shown in Table 43 

The patterns encode the knowledge about which portions of the transaction are being injected with fault and which portions are string literals not actually part of the fault injection but required for a valid transaction.

The pattern encodes several text fields and a special field that is labeled BUFFER . The BUFFER field is a part of the pattern and it has a position in relation to the text fields around it. The transactions produced by this pattern will contain the following strings as shown in Table 47 

Since the letter A is chosen arbitrarily the IDS signature can be generated based on character class such as the following 

The pattern encodes data for all fields and the delimiters between fields. That is the pattern encodes spaces and special characters that mark the boundary between fields. To restrict an IDS signature to match only a given field the delimiter characters around a field can be included in the expression 

Other variations and modifications of the above described embodiments and methods are possible in light of the foregoing teaching.

Further at least some of the components of an embodiment of the invention may be implemented by using a programmed general purpose digital computer by using application specific integrated circuits programmable logic devices or field programmable gate arrays or by using a network of interconnected components and circuits. Connections may be wired wireless by modem and the like.

It will also be appreciated that one or more of the elements depicted in the drawings figures can also be implemented in a more separated or integrated manner or even removed or rendered as inoperable in certain cases as is useful in accordance with a particular application.

It is also within the scope of the present invention to implement a program or code that can be stored in a machine readable medium to permit a computer to perform any of the methods described above.

Additionally the signal arrows in the drawings Figures are considered as exemplary and are not limiting unless otherwise specifically noted. Furthermore the term or as used in this disclosure is generally intended to mean and or unless otherwise indicated. Combinations of components or steps will also be considered as being noted where terminology is foreseen as rendering the ability to separate or combine is unclear.

As used in the description herein and throughout the claims that follow a an and the includes plural references unless the context clearly dictates otherwise. Also as used in the description herein and throughout the claims that follow the meaning of in includes in and on unless the context clearly dictates otherwise.

The above description of illustrated embodiments of the invention including what is described in the Abstract is not intended to be exhaustive or to limit the invention to the precise forms disclosed. While specific embodiments of and examples for the invention are described herein for illustrative purposes various equivalent modifications are possible within the scope of the invention as those skilled in the relevant art will recognize.

These modifications can be made to the invention in light of the above detailed description. The terms used in the following claims should not be construed to limit the invention to the specific embodiments disclosed in the specification and the claims. Rather the scope of the invention is to be determined entirely by the following claims which are to be construed in accordance with established doctrines of claim interpretation.

