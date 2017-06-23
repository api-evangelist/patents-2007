---

title: Method of compiling source code, compiler, computer system, and computer program product
abstract: A method of compiling source code, involving a pre-processing step for including at least one additional source code file into the source code prior to generating target code from the source code. The proposed method further comprises the steps of: establishing, during the pre-processing step, at least one network connection to at least one remote server; and downloading the additional source code file from the remote server.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08214810&OS=08214810&RS=08214810
owner: International Business Machines Corporation
number: 08214810
owner_city: Armonk
owner_country: US
publication_date: 20070828
---
This application claims the priority benefit under 35 U.S.C. 119 of prior European application 06119711.7 filed Aug. 29 2006 and incorporated herein by reference.

The present invention relates to a method of compiling source code involving a pre processing step for including at least one additional source code file into the source code prior to generating target code from the source code.

The present invention also relates to a compiler for compiling source code the compiler comprising a pre processor adapted to include at least one additional source code file into the source code prior to generating target code from the source code.

The present invention further relates to a computer system for compiling source code and to a computer program product for use on a computer.

Compiling of computer programs i.e. translating source file text or source code to a predetermined type of target code typically involves a pre processing step to include additional text in the form of additional source code files into a main source file text by means of a pre processor. A well known example from the C programming language is the pre processor command include include.h which commands the pre processor to include additional source file text comprised in the additional source code file include.h into the main source file text which is typically denoted main.c in the present example. The additional source code files are also commonly referred to a header files .h .

In a general way the pre processor allows text manipulations before actual compilation of a source code file. In the present example the include directive is replaced with a text file which is usually stored on a local hard disk of the machine compiling the source code.

As known to a person skilled in the art real world software projects may include up to 100 different files or more. Most of these files are header files from libraries i.e. collections of sub programs for software development wherein the header files define an Application Programming Interface API to that particular library by means of function prototypes. For instance the Xine executable of the heavily used Xine media player on Linux is linked against 34 libraries. Xine comprises the xine ui user interface and a shared library xine lib packages which currently include a combined number of 390 external header files.

However APIs generally are not fixed since the libraries are constantly being developed i.e. updated to keep up with changing requirements and specifications. This leads to the particular problem that local copies of the above mentioned header files quickly become outdated. Thus frequent time consuming and cumbersome manual updates of header files are required.

It is an object of the present invention to provide a method of compiling source code of the above defined type which is less tedious and more time effective from a developer s point of view.

It is also an object of the present invention to provide a compiler of the above defined type a computer system and a computer program product which can be used for translating the method into practice.

According to a first aspect of the present invention these objects are achieved by providing a method of the above defined type which comprises the steps of establishing during the pre processing step at least one network connection to at least one remote server and downloading the additional source code file from the remote server.

According to a second aspect of the present invention these objects are achieved by providing a compiler of the above defined type the compiler comprising means for establishing at least one network connection to at least one remote server and means for downloading the additional source code file from the remote server.

According to a third aspect of the present invention these objects are also achieved by providing a computer system of the above defined type the computer system comprising at least a first computer comprising first storing means and a source code stored in the first storing means and at least a second computer comprising second storing means and at least one additional source code file stored in the second storing means wherein the first and second computers are connectable by means of a network connection the computer system further comprising on the first computer a compiler according to the second aspect of the present invention wherein the means for establishing a network connection are adapted to establish the network connection between the first and second computers for downloading the additional source code file from the second computer.

According to a fourth aspect of the present invention these objects are further achieved by providing a computer program product for use on a computer comprising code sequences for implementing and or configuring on the computer a compiler according to the second aspect of the present invention.

Thus according to a general idea underlying the present invention additional source code files to be included in a source code prior to compilation are downloaded or fetched from a remote entity via a suitable network connection during the pre processing step. This obviates the necessity for frequent and time consuming manual updates of local copies of the additional source code files.

In order to reduce network traffic in a further embodiment of the method in accordance with the present invention the latter further comprises the step of locally caching the at least one additional source code file. In a corresponding embodiment of the compiler in accordance with the present invention the latter comprises means for locally caching the additional source code file.

For improved functionality a further embodiment of the method in accordance with the present invention may include using a local copy of the additional source code file if the network connection cannot be established.

In order to further reduce network traffic yet another embodiment of the method in accordance with the present invention comprises the steps of checking a current version of the additional source code file on the remote server and using a local copy of the additional source code file if the current version of the additional source code file has been previously downloaded.

In a corresponding embodiment of the compiler in accordance with the present invention the latter comprises means for checking a current version of the additional source code file on the remote server.

In yet another embodiment of the compiler in accordance with the present invention the version checking means are in operative connection with the downloading and caching means to command using a locally cached copy of the additional source code file if the current version of the additional source code file has been previously downloaded from the remote server.

In another embodiment of the method in accordance with the present invention the latter comprises the step of providing a network location of the additional source code file as an element of the source code i.e. within the source code itself e.g. in the form of an include directive as described above. However for increased operational flexibility a further embodiment of the method in accordance with the present invention may comprise the step of providing and or modifying a network location of the additional source code file in the form of a command option when invoking a compiler for compiling the source code. In this way no editing of source code is required to modify the network location.

In order to reduce compiling time in a further embodiment of the method in accordance with the present invention source code compilation can be accelerated by including in the method the step of downloading a precompiled version of the additional source code from the at least one remote server.

Furthermore in accordance with yet another embodiment of the method in accordance with the present invention the latter may comprise the step of establishing a plurality of network connections with different remote servers and or using different connection protocols. In case of parallel connections this may further seed up the compilation process.

In a corresponding embodiment of the compiler in accordance with the present invention the means for establishing the network connection are adapted to establish a plurality of network connections with different remote servers and or using different connection protocols.

In a further embodiment of the computer program product in accordance with the present invention the latter comprises further code sequences for operating the compiler in accordance with the method according to the first aspect of the present invention.

Further advantages and characteristics of the present invention can be gathered from the following description of preferred embodiments given by way of example only with reference to the enclosed drawings. Features mentioned above as well as below can be used in accordance with the present invention either individually or in conjunction. The described embodiments are not to be regarded as an exhaustive enumeration but rather as examples with respect to a general concept underlying the present invention.

Local computer comprises storing means . for storing source code . e.g. in the form of a main source file text. Storing means . is operatively connected with data processing means . which implement the compiler .. Compiler . is adapted to translate source code . into a predefined type of target code as known to a person skilled in the art.

According to the embodiment of compiler . comprises a pre processor . including connection establishing means . and downloading means . the functioning of which will become apparent later.

Remote server comprises storing means . for storing additional source code files . . . . . only two of which are depicted for reason of clarity. As will be appreciated by a person skilled in the art the additional source code files . .can either be stored in storing means . in the form of additional source code text files or alternatively or additionally in the form of precompiled code files. Hereinafter storing means . on remote server will also be referred to as repository for the additional source code files . .

Furthermore remote server comprises updating means . which are adapted for ensuring that the additional source code files . .stored in the repository on remote server represent a most recent up to date version of the respective additional source code.

During operation of computer system of source code . is provided to compiler . for generating the target code. For instance source code . may represent a main source text file written in the C programming language and compiler . may be devised to translate the main source file text into a machine readable object code.

The compiling process involves a pre processing step implemented by pre processor . which comprises including at least one additional source code file i.e. one of the additional source code files . . into source code . prior to generating the target code. As will be explained in detail below with reference to appended pre processor . may be commanded to include the additional source code file by means of corresponding pre processor instructions included in source code ..

In accordance with an embodiment of the present invention for to include the at least one additional source code file into source code . pre processor . controls connection establishing means . to establish network connection with remote server . Using downloading means . pre processor . then downloads a most recent up to date version of at least one required additional source code file . .from the remote server and includes the at least one additional source code file into source code . prior to performing further compiling steps by means of pre processor . and or compiler ..

In this way compiler . on local computer always uses the most recent version of additional source code files . .when compiling source code . without the need for cumbersome and or time consuming manual updates of the additional source code files on local computer .

As already stated above for triggering network download of remote additional source code files in accordance with an embodiment of the present invention source code . may comprise at least one dedicated source code element .which represents a command to pre processor . for establishing a network connection and for downloading the required additional source code file from a remote server as previously described.

According to the embodiment of the source code element .is devised in the form of a C type include command .followed by an URL Uniform Resource Locator .including respective identifiers of a network protocol .to be used for downloading the additional source code a remote server identifier . an identifier .for a repository path on the remote server and an identifier file name .of an additional source code file to be downloaded.

In the C type language example of an additional source code file . .to be included in source code . is generally referred to as a header file with suffix .h . Such header files are typically used in connection with libraries i.e. collections of sub programs for software development and define APIs Application Programming Interfaces of a given library by means of function prototypes.

Referring again to appended source code . comprising source code element .is provided to pre processor . which downloads additional source code . . as previously described with reference to appended from remote server thus producing augmented source code . comprising original source code . and included additional source code . . as further illustrated in . Augmented source code . is then further processed by compiler . for generating the target code denoted by means of reference numeral . in .

Exemplary protocols which may be specified within URL .may include any one of standard protocols like http Hypertext Transfer Protocol ssh Secure Shell ftp File Transfer Protocol or the like. Furthermore by means of network connection access to software management servers could be provided e.g. in the context of cvs svn git or the like to allow for transparent update from code repositories such as repository . on remote server .

In order to optimize the above described downloading process of additional source code files respective file locking mechanisms active in an operating system of local computer and or remote server may be exploited in order to obtain atomic access i.e. access undisturbed by any signal handler during an actual file access process.

As can be gathered from the embodiment of local computer comprises an additional storing means . hereinafter also referred to as caching means.

Within pre processor . compiler . comprises checking means . a functioning of which will become apparent later.

Within its updating means . remote server further comprises time stamping means . a functioning of which will also become apparent later.

Caching means . is adapted to store local copies of additional source code files . .downloaded from remote server as previously described with reference to appended . In this way cached access to the local copies of additional source code files . .by pre processor . may be provided in order to reduce traffic on network connection .

In order to guarantee that pre processor . always uses a most recent version of the additional source code files . . the time stamping means . of remote server marks every stored source code file . .with a respective time stamp . . indicating an update time or a version number of each additional source code file . .. When downloading the additional source code files from remote server for caching in storing means . local computer i.e. pre processor . also downloads the time stamps . . together with the additional source code files. By means of network connection checking . is thus enabled to compare a time stamp version number of a given additional source code file cached in storing means . with a respective time stamp version number of the same file in repository . on remote server . If the respective time stamps version numbers are identical pre processor . may use the locally cached copy of a given additional source code file . .instead of downloading it from remote server thus reducing network traffic. Otherwise if the respective time stamps version numbers differ from each other i.e. the locally cached copy of a given additional source code file . .is outdated with respect to the most recent version of the same file available from remote server then pre processor . uses downloading means . to download a copy of a required additional source code file . .from remote server as previously described with respect to .

However as will be appreciated by a person skilled in the art the computer system of could also be devised on the basis of computer system as previously described with reference to appended . In the following only the differences between the embodiment of and the previously described embodiments according to appended will be described in detail.

As can be gathered from local computer further comprises input means . in operative connection with compiler .. Input means . are adapted to input a compiler command . to compiler . for controlling the latter.

According to compiler command . comprises the actual command word . here the word compile a parameter .indicating the main source file text to be compiled i.e. source code . in the present example and a command option .. In the exemplary embodiment of the command option .is introduced by the sign and to some extent corresponds to URL .of . As can be gathered from command option .indicates a protocol a server and optionally a path on the server which are to be used for locating and downloading a required additional source code file . .from a remote server specified by the command option . e.g. remote server according to .

Note that compiler . will use the information comprised in the command option . i.e. server name and path on that server in connection with a file name comprised in a corresponding include directive in source code .. This means that compiler . will assemble a complete URL from the information comprised in the compiler option and the include file name comprised in the source code. Thus existing source code may benefit from the proposed feature of remote include without requiring any modification.

In this way in addition or as an alternative to the embodiment of according to download related information with respect to protocol server or path for downloading a required additional source code file can be modified without having to modify the source code file ..

As will be appreciated by a person skilled in the art a general concept underlying the embodiment of may be extended to file converting automation utilities e.g. make Unix Ant or the like by providing command structures which can be used within the utilities for modifying the download process for additional source code files without modifying the source code . itself as previously described.

In the embodiment of network connection establishing means . of compiler . pre processor . on local computer are adapted to establish a plurality of network connections simultaneously with the plurality of remote servers for downloading additional source code files . . at least in case locally cached copies of the additional source code files . .are outdated with respect to the most recent versions available from the remote servers .

In the exemplary embodiment of remote server comprises storing means repository . for storing first additional source code files . .while remote server comprises storing means repository . for storing second additional source code files . .

In this way local computer may download required additional source code files concurrently from a plurality of remote servers . Additionally a variety of download protocols may be used in parallel on the plurality of established network connections .

As will be appreciated by a person skilled in the art implementing and or configuring controlling of the various functional elements comprised on local computer and or remote servers in accordance with the embodiments of may be achieved by means of a computer program product which provides suitable program code sequences. The program code sequences may be written in any suitable computer language e.g. and without limitation C C Java or the like. Furthermore the program code sequences may be provided to local computer by any suitable means not shown e.g. on a computer readable data carrier via a network connection or the like.

According to the embodiment of the inventive method starts with step S. In subsequent step S the local computer i.e. a compiler implemented thereon receives a command to compile a particular source code.

In subsequent step S a pre processor comprised within the compiler receives connection information with respect to a network connection to at least one remote server which is required for downloading at least one additional source code file which has to be included into the source code prior to compilation. According to the embodiment of the connection info may be included in the source code. Alternatively as described with reference to appended the connection info may be included as an option in the compiler command received in step S.

Then in step S the compiler establishes the network connection s through dedicated connection establishing means. In subsequent step S the compiler thus accesses the at least one additional source code file on a remote server for fetching its time stamp version number.

In subsequent step S the time stamp version number is compared with a time stamp version number of a corresponding cached copy of the additional source code file in question on the local computer. Step S determines whether or not the cached copy of the additional source code file in question is older than the most recent version available from the remote server. If the question in step S is answered in the affirmative y then in step S the most recent version of the additional source code file is downloaded from the remote server via the established network connection. Otherwise if the question in step S is answered in the negative n then the step S is omitted and the locally cached copy of the additional source code file is used to avoid network traffic.

In subsequent step S either the downloaded version of the additional source code file or the locally cached version of the additional source code file is included in the source file to be compiled by means of the co processor.

Then in step S a further decision step is performed to determine whether or not all additional source files which are to be included in the source code have been downloaded or read from the local cache. If the question in step S is answered in the affirmative y then the augmented source code i.e. including the additional source code files is compiled in step S and the method terminates with step S. Otherwise if the question in step S is answered in the negative n then the method returns to step S in order to include further additional source code files in the source code.

As will be appreciated by a person skilled in the art at least the method steps S S may be performed in parallel for a plurality of required additional source code files available from a plurality of repositories residing on a plurality of remote servers as already stated above in connection with appended .

