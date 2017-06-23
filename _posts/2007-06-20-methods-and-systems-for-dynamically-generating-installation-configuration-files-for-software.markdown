---

title: Methods and systems for dynamically generating installation configuration files for software
abstract: The present invention provides methods and systems for dynamically generating configuration files used in installing software distributions and software installation testing. In particular, the present invention employs a framework comprising an API to discover and monitor an inventory of distributions, a set of templates for the configuration files, and plugins that may be selectively invoked to customize the configuration files. When performing installation testing, a server will access the distribution inventory and select appropriate templates that are to be part of the test. The server will then automatically generate the installation configuration files from the templates. The server may also execute one or more plugins that customize the configuration files as desired. Small client applications run on the target machines of the installation tests and are used to download the configuration files and the distributions. The present invention may also employ a scheduling service to coordinate the operations of the server and target machines.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08561058&OS=08561058&RS=08561058
owner: Red Hat, Inc.
number: 08561058
owner_city: Raleigh
owner_country: US
publication_date: 20070620
---
Today there are several automation frameworks currently deployed that support software provisioning for example for installation testing of software. Each framework encounters similar obstacles such as test scheduling results storage reporting environment initialization and test case design. Often times the implementations to overcome similar problems are divergent.

Most automation frameworks must address the issue of system initialization. A common method for addressing this on Anaconda based Linux distributions is by performing a fresh product installation using a set of hand crafted kickstart files. While this method works fairly well once established it suffers from several problems.

First before any system is made available a kickstart template must be created for each applicable test release. To obtain this file every applicable test release must be installed and the resulting root anaconda ks.cfg file can then be used as the kickstart template for all future installs of that release for that test system. This is a time consuming processing.

Second as the number of systems in the test pool increases the number of kickstart files to maintain grows significantly. This translates to hand maintaining a large number of kickstart template files. Thus when a situation arises where an installation workaround is required the number of kickstart files requiring updates is significant.

Accordingly it would be desirable to provide a tool that makes installation testing simpler for the end user. It would also be desirable to provide a tool that helps automate installation testing.

The present invention provides methods and systems for dynamically generating installation configuration files such as kickstart files for Linux distributions which may be used for installing software or for software installation testing. In some embodiments the present invention is implemented for generating kickstart files for Anaconda based Linux distributions. In particular the present invention employs a framework comprising an API to discover and monitor an inventory of distributions a set of templates for the configuration files and plugins that may be selectively invoked to customize the configuration files.

When performing installation testing a server will receive a test request access the distribution inventory and select appropriate templates that are to be part of the test. The server will then automatically generate the installation configuration files from a template. In some instances the generated configuration files may require customization. Accordingly the server may execute one or more plugins that modify the configuration files as desired. Small client applications run on the target machines of the installation tests and work with the server to download the configuration files and the distributions. The present invention may also employ a scheduling service to coordinate the operations of the server and target machines.

The present invention may be applied to installation and installation testing of any form of software such as Windows systems UNIX systems and Linux systems. For purposes of illustration the present invention will now be explained with reference to implementation to Linux systems such as Fedora and Red Hat Enterprise Linux by Red Hat Inc.

Accordingly the description will first provide some general information about Linux installations. Next is presented to explain an exemplary system of the present invention. Finally is provided to illustrate a general process flow for installation testing used in the present invention. In the figures wherever possible the same reference numbers will be used throughout to refer to the same or like parts.

Turning now to the subject of Linux installations many system administrators use what is known as the kickstart installation method. Kickstart files are files that specify the intended configuration of the software being provisioned. Kickstart files can be kept on a server and can be read by individual computers during the installation. This installation method allows the use of a single or relatively few standard kickstart files to install Linux on multiple machines making it ideal for network and system administrators.

The kickstart file is a simple text file containing a list of items each identified by a keyword. In general a kickstart file can be edited with any text editor or word processor that can save files as ASCII text. Typically kickstart files specify parameters related to language selection mouse configuration keyboard selection boot loader installation disk partitioning network configuration NIS LDAP Kerberos Hesiod and Samba authentication firewall configuration and package selection. One skilled in the art will recognize that the present invention may be applied to non kickstart files in Linux provisioning. For example configuration files such as AutoYAST Answer files used in Novell SuSe Linux and Sun Solaris Jumpstart files may also be used by the present invention.

Kickstart files can be made available over a network using protocols such as NFS FTP or HTTP to support network based installations. In the present invention the network based approach is employed to conduct installation testing on one or more networked target machines. If desired however the present invention may utilize kickstart installations using a local CD ROM local DVD or a local hard drive. Reference will now be made in detail to the exemplary embodiments of the invention which are illustrated in the accompanying drawings.

Referring now to an exemplary system that is consistent with the present invention is shown. The system may comprise a server a code repository which provides access to distribution trees and a set of installation templates a set of exception plugins clients running on target machines a scheduler and a configuration database which comprises a distribution tree list and template list . Each of these components will now be further described.

Server from herein referred to as a SNAKE server for Smart Network Automated Kickstart Environment is responsible for serving as an extensible markup language remote procedure call XMLRPC handler retrieving install distribution trees and hosting kickstart templates and plugins and generating installation configuration files i.e. kickstart files. SNAKE server may be implemented as software such as Python code running on conventional server hardware or some other suitable computing device. Such devices are well known to those skilled in the art.

In order to control its operations SNAKE server may provide a command line interface that allows a user to enter various commands such as commands for triggering the generation of kickstart files for an installation or installation test. Alternatively with its XMLRPC handler SNAKE server may support RPCs from remote devices such as clients . RPCs that may be supported are RPCs for listing templates listing distribution trees or generating one or more kickstart files generating the command line interface and registering one or more of target machines . Of course SNAKE server may be implemented with other types of interfaces such as a graphical user interface. The primary function and responsibilities of server will now be further described.

In order to retrieve one or more of installation trees and server may implement an API. Accordingly as distributions are written and stored at code repository code repository or other device may provide an information file via the API. For example any product built by pungi will write out a .composeinfo file that indicates what deliverables are associated with that product. Pungi is a well known open source program that spins Linux distribution trees and isos disk images of an ISO 9660 file system for CD ROMs . Other tools for creating distribution trees and isos may also be employed by the present invention.

This indicates that the compose distribution supplies 3 trees and several DVD images. For additional details on the tree server may follow the path noted and examine the contents of the .treeinfo file generated by anaconda. Anaconda is a well known open source installer for Red Hat Linux and Fedora Core. Anaconda is capable of using a kickstart file to automatically configure the installation allowing users to run it with minimal supervision. Of course other installers similar to anaconda may be employed by the present invention.

Alternatively server may execute various scripts to scan nfs mounted directories in order to determine the type of product and locate bootable images on its shared network file system. Typically these scripts may provide what is known as a .discinfo file which provides of the same information as the .treeinfo file noted above.

Server may host templates and plugins using known technology. For example server may be coupled to one or more databases not shown via a local network or wide area network. Alternatively server may be coupled to a local storage network to host templates and plugins .

Server may implement various access mechanisms to protect or segregate templates and plugins . For example in an environment where multiple users or entities are performing installations and testing server may support multiple template and plugin repositories. This feature allows server to host templates and plugins for multiple organizations and users yet still provides a security mechanism if desired. For example the templates and plugins for a company A may be kept private from other users. Alternatively templates and plugins for a company B may be public or accessible to others. The present invention may employ a wide variety of these types of features using well known technology.

In order to generate kickstart files SNAKE server may employ what is known as the pykickstart utility. Pykickstart is software that is able to accurately distinguish and generate valid grammar for the kickstart language from templates . Of course any software that is capable of generating configuration files such as kickstart files from a template may be used by the present invention. The other components shown in will now be described.

Code repository is responsible for hosting distribution trees and . Code repository may be implemented using well known components of hardware and software.

Distributions and are bundles of software that are already compiled and configured. Distributions and may be in the form of formats such as rpm deb tgz msi exe etc. For Linux distributions and are bundles of software that comprise the Linux kernel the non kernel parts of the operating system and assorted other software. Distributions and may take a variety of forms from fully featured desktop and server operating systems to minimal environments.

Installation templates are pre formatted generic files from which kickstart files can be generated. Templates may be of several types such as minimal everything default etc. An example of a minimal template is shown below 

Exception plugins comprise program code for customizing kickstart files for cases when special circumstances are required. For example Fedora Core 6 FC6 introduced IPv6 support in its installer. A plugin may be used to enable or disable use of IPv6. Any such type of circumstance may be accounted for by the present invention. Other circumstances for plugins are known to those skilled in the art.

Client assists SNAKE server in performing installations. Client is installed on target machines and establishes communications with SNAKE server . Client then downloads the distributions bootable installation images and the kickstart files from the SNAKE server . In some embodiments client is written in Python code to accommodate a variety of operating systems machine architectures etc.

Target machines represent the particular machines to which software provisioning is directed. Target machines may represent a wide variety of devices such as a personal computer a server etc.

Although shows relatively few number of target machines the present invention is capable of managing a wide range environments such as datacenters with thousands of machines or server pools with just a few machines.

Scheduler assists in coordinating installation provisioning on target machines . For example scheduler may access a database of registered target machines for example on database not shown . Scheduler may then be configured to find applicable subsets of target machines to schedule software installations against one or more of templates .

Configuration database serves as data storage for hosting the data used by SNAKE server . For example as shown configuration database will typically comprise a distribution tree list and a template list .

Distribution tree list provides an inventory of distributions and that are hosted by SNAKE server . Accordingly tree list will comprise information about the nature and location of distributions such those stored by code repository . This information may include for example a name of the tree a location version information and the like.

Template list provides an inventory of templates that are hosted by SNAKE server . Accordingly template list will comprise information about the nature and location of the templates hosted by server . For example this information may include a name of the template a location a version an architecture and the like. Those skilled in the art should recognize that configuration database may employ a variety of data structures such as relational database tables and object oriented data structures. Therefore use of the word list above is merely explanatory and not meant to limit the data structure used to store the list.

Reference is now made to which illustrates the process flows of the present invention. As shown in phase a new distribution is submitted to code repository . For example a user or developer not shown may create the new distribution using the Pungi and Anaconda tools to spin this new distribution on to code repository .

In phase server receives information about the new distribution and updates its tree list . For example server may access the .composeinfo file which was generated by the Pungi tool. Server may also follows the path noted in .composeinfo file and examine the contents of the .treeinfo file generated by anaconda for further information. Server then updates its tree list . Server may record all or some of the information in these files in tree list .

In phase server receives a request for a software installation or installation test. For example server may receive the request via its command line interface or via its XMLRPC handler. The request may come in various forms such as a file or script and may include other information such as test parameters and the like. Typically the request will specify a distribution or multiple distributions and information indicating one or more desired targets of the installation or test. The desired targets may be specified several ways such as by processor architecture network interfaces file system etc.

In phase server locates the distribution or distributions of the request and selects the appropriate templates for the request. For example server may refer to its tree list to determine the location of the distribution at code repository . In addition server may refer to template list and determine which of templates should be used for the requested installation. Alternatively server may execute a script for scanning the directories of networked file systems.

Server may employ various criteria to select templates . Examples of criteria that may be used include the identity of the user or entity requesting the installation or test information in the request and the availability of test machines .

In phase server generates the installation configuration files e.g. kickstart files based on the selected template . For example server may employ the pykickstart utility to generate kickstart files from templates .

Of note server may generate any number of kickstart files from templates . For example for installation testing server may be configured to generate a range of kickstart files to test that a distribution can install across a variety of different types of target machines . The range of scope of the kickstart files may be specified manually for example via the command line interface or RPC information in the request or from a test plan or test script running on server .

In phase server may optionally customize the kickstart files. In the present invention server may customize the kickstart files by executing one or more of plugins . Server may simply iterate through all of plugins and rely on conditional logic within the plugins to determine if they should be executed. Alternatively server may include a utility or program that assists it in selecting plugins . Such mechanisms are well known to those skilled in the art.

Should one wish to disable support of IPv6 for all installs of Fedora Core 6 or newer the following plugin could be executed to customize kickstart files 

In phase the requested distribution and associated kickstart files are provided to target machines . For example a user may be running clients on target machines and may use RPCs to request download of boot media and kickstart files from server . Upon receiving these files clients may then configure the installation of the requested distribution based on the kickstart file.

Alternatively server may push distributions and kickstart files to perform the installation or test. For example clients may register their target machines with server . Server may then initiate communications with clients and send kickstart and distribution files to target machines .

As another alternative scheduler may work with both server and clients to schedule installation on target machines . Upon request scheduler may find applicable subsets of target machines to schedule software installations against one or more of templates .

Other embodiments of the invention will be apparent to those skilled in the art from consideration of the specification and practice of the invention disclosed herein. It is intended that the specification and examples be considered as exemplary only with a true scope and spirit of the invention being indicated by the following claims.

