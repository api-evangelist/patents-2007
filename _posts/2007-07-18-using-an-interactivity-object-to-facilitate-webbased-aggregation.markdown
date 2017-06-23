---

title: Using an interactivity object to facilitate web-based aggregation
abstract: Some embodiments of the present invention provide a system that uses an interactivity object to facilitate interactivity during automated web site accesses. During operation, the system examines a web page on the web site to determine a data type for an interactivity request associated with the web page. Next, the system creates an interactivity object, which includes the interactivity request along with the determined data type for the interactivity request. Finally, the system sends the interactivity object to the user to solicit a response from the user.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08977709&OS=08977709&RS=08977709
owner: Intuit Inc.
number: 08977709
owner_city: Mountain View
owner_country: US
publication_date: 20070718
---
The subject matter of this application is related to the subject matter in a co pending non provisional application by inventors Spencer W. Fong Richard M. Ng Thomas E. Dockman Rodney A. Robinson and Marvin Mah entitled Using Interactive Scripts to Facilitate Web Based Aggregation having Ser. No. 11 771 217 and filing date 29 Jun. 2007.

Financial institutions typically provide websites that enable their customers to access account information on line. Moreover most people have accounts at a number of different financial institutions. For example a person might have 1 bank accounts at a bank 2 credit card accounts with different credit card issuers and 3 investment accounts with different brokerage firms. This means that the person must visit a number of different websites belonging to different financial institutions to determine their financial position accurately which is a cumbersome and time consuming process.

In order to speed up this process a number of account aggregation systems have been developed to compile information from different accounts automatically. To use this type of system a user typically provides account access information such as usernames and passwords for various accounts and the account aggregation system uses this information to gather and compile the account information into a single presentation. These account aggregation systems typically reside within a web based application or within client side software. Note that similar aggregation systems are also used to gather and compile other types of information such as emails and news articles.

Unfortunately existing aggregation systems navigate through websites in a programmed fashion that is static. This means that such systems require data to be already stored e.g. a username and also require a website map which is already known. Such systems have problems dealing with dynamic situations where user interaction is required

Some embodiments of the present invention provide a system that uses an interactivity object to facilitate interactivity during automated web site accesses. During operation the system examines a web page on the web site to determine a data type for an interactivity request associated with the web page. Next the system creates an interactivity object which includes the interactivity request along with the determined data type for the interactivity request. Finally the system sends the interactivity object to the user to solicit a response from the user.

In some embodiments of the present invention the system receives a response to the interactivity request from the user. Next the system determines a data type for the response. The system then creates a response object wherein the response object includes the response along with the determined data type for the response. Finally the system returns the response object to the web site.

In some embodiments of the present invention the system receives the response from a keyboard a mouse a touch sensitive screen a biometric device a hardware token and a file system.

In some embodiments of the present invention the response can include a text answer a biometric signature a certificate a file and a token.

In some embodiments of the present invention the interactivity object can include a text question an image an instruction an audio file a video file a HyperText Markup Language HTML file an eXtensible Markup Language XML file and a document.

In some embodiments of the present invention the system receives an interactivity object at a client wherein the interactivity object includes an interactivity request along with a data type for the interactivity request. The system then presents the interactivity request to the user through a presentation mechanism which is selected based on the data type for the interactivity request.

In some embodiments of the present invention the presentation mechanism can include an audio player a video player a browser a text display and an image viewer.

The following description is presented to enable any person skilled in the art to make and use the invention and is provided in the context of a particular application and its requirements. Various modifications to the disclosed embodiments will be readily apparent to those skilled in the art and the general principles defined herein may be applied to other embodiments and applications without departing from the spirit and scope of the present invention. Thus the present invention is not limited to the embodiments shown but is to be accorded the widest scope consistent with the claims.

The data structures and code described in this detailed description are typically stored on a computer readable storage medium which may be any device or medium that can store code and or data for use by a computer system. This includes but is not limited to volatile memory non volatile memory magnetic and optical storage devices such as disk drives magnetic tape CDs compact discs DVDs digital versatile discs or digital video discs or other media capable of storing computer readable media now known or later developed.

One embodiment of the present invention provides a system that uses script technology to aggregate data from websites. While navigating through a given website if the system detects an interactive portion of the website the system provides an interface to a user to facilitate user interactivity with the website. The system also swaps out a process which is executing the script. Next after obtaining information input from the user and forwarding this information to the website the system resumes executing the script. This system is described in more detail below.

Some embodiments of the present invention provide a system that uses an interactivity object to facilitate interactivity during automated web site accesses. During operation the system examines a web page on the web site to determine a data type for an interactivity request associated with the web page. Next the system creates an interactivity object which includes the interactivity request along with the determined data type for the interactivity request. Finally the system sends the interactivity object to the user to solicit a response from the user.

In some embodiments of the present invention the system receives a response to the interactivity request from the user. Next the system determines a data type for the response. The system then creates a response object wherein the response object includes the response along with the determined data type for the response. Finally the system returns the response object to the web site.

In some embodiments of the present invention the system receives the response from a keyboard a mouse a touch sensitive screen a biometric device a hardware token and a file system.

In some embodiments of the present invention the response can include a text answer a biometric signature a certificate a file and a token.

In some embodiments of the present invention the interactivity object can include a text question an image an instruction an audio file a video file a HyperText Markup Language HTML file an eXtensible Markup Language XML file and a document.

In some embodiments of the present invention the system receives an interactivity object at a client wherein the interactivity object includes an interactivity request along with a data type for the interactivity request. The system then presents the interactivity request to the user through a presentation mechanism which is selected based on the data type for the interactivity request.

In some embodiments of the present invention the presentation mechanism can include an audio player a video player a browser a text display and an image viewer.

In one embodiment of the present invention script executes on a standalone application which includes a script engine. In an alternative embodiment script is executed by a script engine that is part of application . In yet another embodiment the script executes within a web browser.

Script includes uniform resource locators URLs that are directed to pages on websites such as target website as well as macro instructions to that navigate through and parse pages on a target website . Note that target website can generally include any type of website from which data can be aggregated such as a website for a financial institution. For example script can first automatically navigate to a logon screen for a financial website. Next the script can automatically enter a username and password into the logon screen to obtain access to an associated account summary page. Script can then determine how many accounts are associated with the account summary page. For each of these accounts the system can follow a corresponding URL to gather data from one or more pages associated with the account. During this process if user interaction is required the system allows the user to provide such input as is described below. For example the interaction can involve the user reading an obscured word in a digital image and inputting the word as a response. In another example the interaction can involve the user answering a question in text form such as what is your mother s maiden name 

The aggregation system also includes a database DB or some other type of repository which contains user supplied information such as passwords or credentials that are used to gain access to various accounts on various websites.

Instead of interacting with user the system can alternatively interact with a device or a computer system. For example the system can interact with an optical character recognition OCR device which for example can automatically read a word in a digital image. In general the system can interact with any type of device or computer system that can perform some type of interaction for example such as input output I O system .

In yet another embodiment instead of interacting with the user the system can interact with a person who is on call to respond to queries on behalf of users. For example the person who is on call might be employed by an organization such as a call center to answer such queries on behalf of users.

Next the script retrieves user specific data for a website such as a username and password from a repository such as database step . The script then uses this user specific data to log on to the website.

Next the script interacts with the website. This can involve performing page parsing operations on web pages to retrieve data from the website and to ascertain the structure of the website. It can also involve performing various navigation operations through various web pages on the website step .

While accessing the website the website can generate an interactivity request which can be in the form of an interactivity object step . In one embodiment of the present invention the interactivity object is an object defined within an object oriented programming system. Note that this interactivity object can encapsulate different data types associated with different types of interactivity requests. For example the interactivity object can include an image to be viewed by the user an audio file to be listened to by the user a question in text form to be presented to the user or HTML or XML code to generate a presentation to be presented to the user. Note that an HTML presentation can provide a drop down menu with options that a user can select.

In response to receiving the interactivity object the system presents the interactivity object to a user of the application which invoked the script. Note that this can involve presenting the interactivity object to user through a user interface for application . For example the user might be asked to recognize an obscured word in a digital image or to recognize some music in an audio file.

In one embodiment of the present invention the script is then suspended step while the user takes time to respond. This enables other scripts to run on the script engine.

Next the user provides a response step which for example may involve inputting a recognized word or a recognized piece of music and the response is forwarded to the website step .

In one embodiment of the present invention the answer is stored by the system in database so that when the same interactivity request is encountered the system can automatically provide the response instead of asking the user to provide the response again. This feature prevents the user from having to respond to the same query again.

Also note that the response might include biometric data from the user such as a fingerprint scan or a retina scan.

Finally the script is re started to continue processing from where it left off step . Note that when the script is suspended a certain amount of state information must be saved for the script and when the script is re started the saved state information needs to be restored.

Note that a number of extensions can be made to the macro language in which the scripts are written to facilitate the above described process.

In one embodiment of the present invention the system supports invoking and communicating with scripts such as script through a specialized application programming interface API such as a web services API. This allows the scripts to accept direct requests through the API.

The foregoing descriptions of embodiments have been presented for purposes of illustration and description only. They are not intended to be exhaustive or to limit the present description to the forms disclosed. Accordingly many modifications and variations will be apparent to practitioners skilled in the art. Additionally the above disclosure is not intended to limit the present description. The scope of the present description is defined by the appended claims

Data type indicator indicates what type of data is included in interactivity object . This can include but is not limited to text audio video image HyperText Markup Language HTML a certificate a file a document or a command. Note that interactivity object can include the object that is presented to user or the object that is received from user .

During operation script receives a request from target website operation . Note that this request could be in the form of a challenge question that requires a response from user an image file with partially obfuscated numbers that requires that requires identification of the numbers by user a document that requires processing by user etc. Next script determines a data type for the request operation . Upon determining the data type script creates interactivity object including data type indicator and data operation .

Next script sends interactivity object to application operation . Note that in some embodiments of the present invention script is running inside of application while in other embodiments of the present invention target website script and application are all on separate computing devices. Upon receiving interactivity object application presents interactivity object to user via the appropriate presentation mechanism operation . For example application may present a text question to user via a web browser or application may present an image to user via an image viewer.

Note that in some embodiments of the present invention user may include a physical device rather than a person. In these embodiments of the present invention user may perform some automatic processing on interactivity object such as performing an Optical Character Recognition OCR operation.

Next application receives a response from user operation . Note that the response can be in the form of a text string a biometric signature wherein user used a biometric device such as a fingerprint scanner a designation of a data file including a digital certificate etc.

Upon receiving the response application packages the response into interactivity object operation . Application then forwards interactivity object to script operation . Script then processes interactivity object to create a response to the request from target website operation . Finally script forwards the response to target website operation .

In some embodiments of the present invention the system interacts with target website such that it would appear to target website as if target website is interacting directly with user . Furthermore in some embodiments of the present invention user is only presented with interactivity object via an appropriate presentation mechanism and is never presented with any web pages from target website .

The foregoing descriptions of embodiments of the present invention have been presented only for purposes of illustration and description. They are not intended to be exhaustive or to limit the present invention to the forms disclosed. Accordingly many modifications and variations will be apparent to practitioners skilled in the art. Additionally the above disclosure is not intended to limit the present invention. The scope of the present invention is defined by the appended claims.

