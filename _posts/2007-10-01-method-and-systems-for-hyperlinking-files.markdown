---

title: Method and systems for hyperlinking files
abstract: A method and apparatus for hyperlinking a main file with N target files stored in a computer readable medium (N≧1). A primary filename of the main file, which is hyperlinked with N target file addresses to form a composite filename, has a form of F.E. The composite filename has a form of F(A).E, wherein F and E respectively represent a name component and an extension component of the primary filename. The N target files are denoted as T, T, . . . , Thaving the associated N target file addresses respectively denoted as A, A, . . . , A, wherein A represents A, A, . . . , A. The symbol ( between F and A denotes a first control character that separates F and A. The symbol ) between A and E denotes a second control character that separates A and E. The composite filename is stored in the computer readable medium.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08041753&OS=08041753&RS=08041753
owner: International Business Machines Corporation
number: 08041753
owner_city: Armonk
owner_country: US
publication_date: 20071001
---
This application is Continuation of Ser. No. 10 533 597 filed May 2 2005 now U.S. Pat. No. 7 330 863 B2 issued Feb. 12 2008.

The present invention relates to information storage and retrieval systems and more particularly to a method and systems for creating hyperlinks from a file to source files from which it has been copied and or any other target files source files and or other target files located on the same or different computer systems .

Generally computer systems store data such as computer programs text documents graphics pictures audio video or other information and documents as files that may contain any combination of these kind of information. These files are typically maintained on a hard disk drive associated with a computer but may also be maintained in memory on floppy drives remote servers or other types of mass storage media. To simplify their retrieval files are generally dispatched among numerous directories or folders. Each directory or folder may have sub directories or sub folders. A computer system may contain hundreds of such directories or folders and file servers which may be a part of a computer system may have thousands of such directories or folders. A user generally locates a file by using the file s filename typically a short character string e.g. myphoto.gif a disk drive designation and directory or folder may be prepended to the filename e.g. C photos myphoto.gif .

Different types of file systems are available for different operating systems. Each file system type has its own format and set of characteristics such as filename length maximum file size and so on. For example on Linux operating system the most commonly used file system type is the Second Extended File system also known as ext2fs. It allows filenames up to 256 characters. On Windows registered trademark of Microsoft Corp. the VFAT Windows 95 and FAT32 Windows 98 file system maximum length of filenames is 255 characters. NTFS and UNIX file system maximum length of filenames is 256 characters.

On the Internet an addressing scheme is employed to identify resources e.g. HTTP servers files or programs and files or HTML documents to display. This addressing scheme is called Uniform Resource Locator URL . An URL may contain the application protocol to use when accessing the server e.g. http the Internet domain name also referred to as the server host name of the site on which the server is running the port number of the server the port number may not be specified in the URL but is obtained by translating the server host name and the location of the resource in the file structure of the server. For example the URL

If the client request is for a file the HTTP server locates the file and sends it to the client. Depending on the type of file retrieved the client may activate an application to process the file. Upon reception of a file the client browser typically examines the extension to determine how to process the file after receipt e.g. launching an application program to process the file. For example if an HTML document is retrieved a client s web browser may parse the HTML document and display it. Likewise if a word processing document is retrieved the client may activate a word processor to process the document. Alternatively the accessed file may be saved locally or downloaded for a further use.

Most operating systems and file systems do not enable once a file has been downloaded to keep track of the relationship between a downloaded or copied file children and the source file parent . For instance when a file is copied from a network e.g. the Internet from a server computer to a client computer the relationship of the copy file on the client computer with the source file on the server computer is lost because the URL of the source file is not recorded with the copied file.

A serious risk associated to the exchange of electronic information on open and unsecured networks particularly on the Internet concerns the modification of data during the transfer. As a consequence it is important to check files received over a network to verify that they have not been corrupted nor altered and or that they have not been sent by an impostor. It may also be important to keep track of the source files when documents are modified so as to recover the original ones e.g. to analyze modifications.

A file may also have descriptive and referential information i.e. file metadata associated with it. This information may be relative to the source content generation date and place ownership or copyright notice central storage location conditions to use related documentation applications associated with the file or services. However most file systems do not enable to keep a persistent connection of a file with the associated metadata. When a file is transmitted from a computer system to another the connection of that file with associated metadata is frequently lost.

When a user receives a file through a network e.g. by clicking on the icon of a file attached to a received e mail he would need to get apart from the attached file metadata related with such file. For example when a file is received from an Internet server it may be necessary to verify that it has not been corrupted altered in some manner or to verify that it has been received from the proper sender rather than by an impostor. Particularly if the received file is a software program it could be of the utmost importance to ensure that received file has been sent by a trustworthy party prior exposing the computer system to a program file that might include a Trojan Horse or that could infect the user s computer with a virus. To that aim the user may require to access file metadata particularly a digital certificate and digital signature to verify the authenticity and integrity of the file before executing it.

Today there are different approaches for implementing the association of a file with metadata of that file. Basically metadata of a file can be encoded onto the same filename of the file they can be prepended or appended onto the file as part of a file wrapper structure they can be embedded at a well defined convenient point elsewhere within the file or they can be created as an entirely separate file. Each approach has inherent advantages and disadvantages 

As a conclusion there is a need for a method and systems for creating hyperlinks from a main file to target files that could be either source or other associated files.

Thus it is a broad object of the invention to remedy the shortcomings of the prior art as described here above.

It is another object of the invention to provide a method and systems to create hyperlinks from a main file to target files so that each target file may be accessed from the main file.

It is a further object of the invention to provide a method and a system to create an hyperlink from a main file to the source from which it has been retrieved.

It is still a further object of the invention to provide a method and systems to create hyperlinks from a main file to associated metadata.

The accomplishment of these and other related objects is achieved by a computer like readable medium comprising a main file having a filename including a primary filename and at least one encoded target file address the primary filename of said main file and said at least one encoded target file address being separated by a first control character and two consecutive encoded target addresses being separated by a second control character 

and by a method for hyperlinking at least one target file available at a target address to a main file having a primary filename said method comprising the steps of 

Further advantages of the present invention will become apparent to the ones skilled in the art upon examination of the drawings and detailed description. It is intended that any additional advantages be incorporated herein.

According to the invention the filename of a main file is used to encode the target addresses of one or several target files using a particular lexicography. The used lexicography is determined so as to avoid particular characters that may be forbidden by the file system e.g. with Microsoft Windows system and or to encode the target addresses so as to reduce their sizes. The target addresses to be encoded may be of any forms e.g. local addresses addresses in private networks or Internet addresses however for sake of illustration the examples given in the following description are based on URL type of addresses.

In a first embodiment a method for encoding the source file address from which a file is saved is disclosed. According to this embodiment the source file address may be encoded either when the main file is transmitted from the server to the user system or when it is locally saved or transmitted to another system. Likewise the source file address may represent either the address of the source file or the address of the Internet page wherein the main file is included.

As an illustration let us consider a main file consisting in an image having myphoto.jpg as primary filename that is included on an Internet page having the following URL 

When the user chooses an option to download this image such as the standard menus save . . . save as . . . or send to . . . this image is transmitted from the Internet server to the user system with the corresponding primary filename and the URL is encoded as follows by using the previous lexicography table 

Then the encoded URL is merged with the primary filename. In this example the encoded URL is enclosed in parenthesis that are used as separators. The encoded URL is inserted in front of the extension dot of the primary filename as follows 

Instead of associating the address of the Internet page wherein the image is included and from which it is copied the encoded hyperlinked filename may contain the address of the source image file. For example if the address of the image file is

It must be noticed that for sake of illustration this encoding algorithm is purposely very simple. A preferred one would consist in replacing a sequence of forbidden characters by a single one e.g. replacing by . Likewise some sets of characters may be replaced by more compact codes e.g. replacing http by H . This kind of encoding optimisation will be discussed later.

In a second embodiment the method for encoding the addresses of one or a plurality of associated target files is disclosed. As discussed above a target file may consist for example of a source file metadata computer programs text documents graphics pictures audio video or other information. A target file may also provide services that may be accessed through e.g. an HTML file. In this embodiment the method of the invention may be integrated as a module of most of software e.g. this module may be launched optionally when saving a main file or implemented as an independent software. shows the main steps of this embodiment. After getting the primary filename of the main file box a test is performed to determine whether or not the user needs to associate target files box if not the process ends. Else if the user needs to associate target files a request is transmitted to the user to enter the address of the first target file to associate therewith box . To that end the user may type the target address or determine it using a standard browsing function. Then the address of the target file to associate is encoded box and merged with the primary filename using particular separators box . An algorithm similar to the one described by reference to may be used to encode the address of the target file to associate. A second test is performed to determine whether or not the user desires to associate more target files box . If there is no more target file to associate the process ends. Else the last four steps are repeated boxes to . A control character is inserted between each encoded target addresses so that the encoded hyperlinked filename may be parsed and each target address may be retrieved. It must be noticed that the address of the source file of a copied or saved main file could be linked like any associated target files.

As an illustration let us take again the previous example wherein the user wants now to associate apart from the address of the source of the image the address of a target file containing a textual description of the image. Thus in this new example the source file address and the address of the image description file must both be associated to the primary filename of the image. In this example the primary filename of the image is my photo.jpg the URL of the source image file is

When saving this main file the user may choose an option such as associate files . . . and then select the target files he or she likes to associate. In such a case the addresses of all target files to associate are encoded. Thus in this example the encoded target addresses are

In this example external parenthesis and are used as separators to identify the primary filename portion where hyperlinks have been encoded and a bracket is inserted between each encoded target address.

Once again the encoding procedure may be optimized so as to reduce the length of the encoded hyperlinked filename.

A third embodiment concerns a method for decoding a filename comprising several encoded addresses of target files and then accessing these target files. illustrates an example of an algorithm implementing such method. After having selected a main file which filename contains a primary filename and encoded target addresses and upon selection of a button or menu like view source file . . . or view associated files . . . the filename is parsed using the same separators than those used during the encoding process box . Then the number n of hyperlinks i.e. the number of encoded target addresses is determined box and a variable i is set to zero box . The iencoded target address is selected box and decoded using the lexicography table used for encoding this target address e.g. table box . Using this decoded target address the associated target file may be accessed box . As it is generally the case in Internet browser systems dealing with files the accessed target file may be locally saved or a plug in may be automatically launched to view the target file depending upon selected options or software configuration. For example if the accessed target file is an image an image viewer or editor may be automatically launched. Preferably the type of the target file is determined by analyzing the extension of the target address. Then variable i is incremented by one box and a test is performed to determine whether or not all hyperlinks have been accessed box i.e. if variable i has reached the number n of encoded target addresses in which case the process ends. Otherwise i.e. if variable i has not reached the number n of encoded hyperlinks the last five steps are repeated boxes to . Optionally the algorithm may include a sub module allowing the user to select the hyperlinks for which associated target files have to be accessed so as to avoid accessing all of them. For sake of clarity such option is not represented on the algorithm of .

This decoding algorithm may be illustrated with the previous example wherein the encoded hyperlinked filename is 

The encoded hyperlinked filename may be parsed by identifying the separators and to extract the primary filename of the main file and the encoded target addresses respectively

Then using the lexicography table used for the encoding process the encoded target addresses may be decoded as 

As discussed herein before the address encoding procedure may be optimized to generate compressed encoded hyperlinked filenames. Even if different data compression techniques may be applied efficiently with the only restriction of generating valid encoded filenames only the simplest ones are described below it is not the object of the invention to deal with data compression techniques .

Since target files hyperlinked to a main file are generally stored on the same location e.g. same folder directory or web page a single common path may be encoded so as to avoid redundancy. Thus still considering the previous example wherein the encoded hyperlinked filename is

During the decoding process once a common path has been identified as preceding common path control character it is pre pended to each of the following individual encoded target files paths identified by means of the separator control character i.e. in this example.

In the case where only a subset of target files share a common path another control character may be inserted to identify path s that do not share the common path.

The encoded hyperlinked filename may also be optimized by replacing the host name by the Internet Protocol IP Domain Name Server DNS address. Determining the DNS address may be easily done by using standard API or operating system functions e.g. ping function under MS DOS registered trademark of Microsoft Corp. operating system. In such case the previous example of encoded hyperlinked filename is 

Finally as discussed above some frequently used sets of characters e.g. http http www. or ftp may be replaced by more compact codes e.g. H W or F respectively. Such reserved strings of characters and the associated compact codes may be stored in the lexicography table mentioned above. Still considering the previous example the optimized encoded hyperlinked filename is 

However it must be noticed that in this particular case the set of characters http i.e. HTTP internet access protocol code may even be ignored since generally Internet browsers automatically assume HTTP access protocol by default.

Naturally the steps of removing common paths replacing host names by the DNS IP addresses and replacing sets of characters by control characters may be executed in any order without modifying the final result.

When the encoding process is optimized the decoding process firstly consists in replacing the compact codes by corresponding sets of characters and inserting missing common paths before decoding the encoded hyperlinked filename as described by reference to . The lexicography table used for replacing compact codes by sets of characters must the same than the one applied for the optimization process. It is not required to replace IP addresses by host names however it could be done using API or operating system functions e.g. GetHostByName function from DNSUtility Code.

Naturally in order to satisfy local and specific requirements a person skilled in the art may apply to the solution described above many modifications and alterations all of which however are included within the scope of protection of the invention as defined by the following claims.

