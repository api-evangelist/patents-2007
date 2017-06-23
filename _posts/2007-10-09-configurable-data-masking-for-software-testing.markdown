---

title: Configurable data masking for software testing
abstract: A data masking tool can support a wide variety of data sources and execution mechanisms. For example, any of a wide variety of data masking techniques can be achieved via a web interface, API, command line, SOA, or the like. Connectivity to mainframe environments can be achieved. Multiple data source types and data to and from different technology platform types can be supported. The tool can support interfacing with a metadata management tool. High quality randomness can be provided by a Mersenne Twister random number generator. The tool can be useful for performing data masking during software testing without having to write data masking code.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=07917770&OS=07917770&RS=07917770
owner: Infosys Technologies Ltd.
number: 07917770
owner_city: Bangalore
owner_country: IN
publication_date: 20071009
---
Software testing is an integral part of software development. Ideally the data used when testing software will resemble live data that is expected when the software is deployed. However for security reasons live data is not always available.

For example some software deals with personal or confidential information. A banking application may access a database that has names addresses social security numbers and bank balances of customers. Besides possibly being in violation of the law providing such information to testers may not be desirable because the testing environment might not otherwise need to have the security safeguards in place to adequately protect the data.

Accordingly testing may be done with data that does not resemble live data. However such an approach can easily lead to inadequate testing. As a result certain problems with the software are later found after the application is put into production leading to dissatisfied users.

Although there are certain data masking software packages available they are not sufficiently flexible and do not lend themselves well to use in a variety of settings.

Therefore there still remains need for technologies to address shortcomings of current data masking techniques.

A variety of techniques can be used for supporting data masking. As described herein a wide variety of data sources and execution mechanisms can be supported. Configuration for a wide variety of scenarios can be achieved via a configurable data masking tool without having to write data masking code.

A configurable data masking tool that can be accessed in a variety of ways can be helpful because developers need not start from scratch or re code if data masking is desired for a particular software development project. Instead the tool can easily be tailored to work within the particularities of the project via configuration data.

Flexibility of a data masking tool can accommodate data from a variety of sources including different technology platform types.

The data masking tool can input and output data in a common editable format e.g. extensible markup language so that a variety of other tools can be used.

If desired a Mersenne Twister random number generation technique can be employed for high quality randomness.

As described herein a variety of other features and advantages can be incorporated into the technologies as desired.

The foregoing and other features and advantages will become more apparent from the following detailed description of disclosed embodiments which proceeds with reference to the accompanying drawings.

In the example the data masking tool is configured to receive unmasked data e.g. source data and output masked data e.g. output data . The data masking tool can include a data masking rule engine that supports any of a variety of masking rules e.g. static substitution rules dataset substitution rules random substitution rules shuffling rules encryption rules and the like .

The data masking tool can also store a plurality of data masking profiles that specify configuration settings for various data masking scenarios including one or more masking rules per scenario. In practice the data masking profiles can be stored outside of the tool . In some implementations configuration data can be specified without storing a profile with the tool .

Although some of the examples assume the perspective of the data masking tool the methods described herein can be implemented from other perspectives e.g. from the perspective of a hosting application or from one or more client applications . For example although the terminology receiving unmasked data can used from the perspective of the data masking tool such an act could also be described as sending unmasked data from the perspective of a client application.

At one or more masking rules are applied e.g. by a data masking rule engine to the unmasked data as indicated via configuration data e.g. in a profile or the like .

The method and any of the methods described herein can be performed by computer executable instructions stored in one or more computer readable media e.g. storage or other tangible media .

In any of the examples herein data masking configuration data can include any of a variety of information by which data masking can be configured. For example the configuration data can indicate which data masking rules are to be applied to which data e.g. which table columns .

To facilitate interchangeability of the data masking configuration data the data masking tool can both send and receive the data masking configuration data as Extensible Markup Language XML .

To facilitate editing in XML editors and metadata tool fields can be stored as human readable names. For example indications of columns or fields can be stored as column or field names data types can be stored as human readable words e.g. number varchar date and the like masking rules stored as human readable words e.g. no rule static substitution dataset substitution random substitution encryption shuffling and the like and the like.

The XML generated by the data masking tool can be sufficient to completely reconfigure it to perform the data masking a second or subsequent time. If desired such XML can be edited using any XML editor including a text editor.

The API can be used to invoke functionality of the data masking tool as described herein. The API can be used to perform data masking as indicated in one or more of the profiles or according to other configuration data as indicated via calls to the API .

In the example the API can accept calls from a web interface . For example a web interface can present configuration screens by which a user can create configuration data e.g. a data masking profile and execute one or more profiles against source data.

The API can also accept calls from other interfaces e.g. any application that can issue API calls or serve as a hosting application for a data masking tool plug in . For example it may be desirable for an application to have access to data masking functionality or a custom front end can be provided.

The API can also accept calls as a result of a command given at a command line . For example a command can be configured to invoke the API with specified configuration data.

The API can also be invoked from a Service Oriented Architecture SOA endpoint . Thus data can be masked via the SOA technique e.g. through a web service without installing the data masking software at a local machine .

In the example an interface can invoke the API and specify that the data masking tool apply the configuration data .

For example the data masking tool can be configured to recognize a language e.g. XML and the configuration tool can generate configuration data for consumption by the data masking tool in the language.

In this way a commonly available application e.g. MICROSOFT EXCEL software can be used to generate the configuration data .

In the example the hosting application has access to input data and can send the data to the custom transformation to generate appropriate configuration data and invoke the data masking tool e.g. via API to perform data masking. The custom transformation can provide the unmasked data and retrieve the masked data which is then relayed back to the hosting application which stores it as output data .

Such an arrangement can be particularly useful if the hosting application can access data in specialized environments such as in a mainframe environment. The hosting application can serve as a broker between the specialized environment and the data masking tool .

At input data is read with the hosting application. At the input data is sent to the custom transformation. For example in a flat file situation the flat file can be read and then sent to the custom transformation e.g. the entire file or record by record . Data can be sent via a port arrangement.

At the masked data is received from the data masking tool. For example the custom transformation can specify a target location at which the tool will place the data.

In any of the examples herein the data masking tool can support a variety of source data types. For example unmasked flat file data A unmasked database data B and unmasked other data C e.g. data passed when the data masking tool is a plug in hosted by an application can be supported.

Further the data sources and data targets can be from different technology platform types e.g. mainframes microcomputer based desktops UNIX based systems and the like . Similarly a platform hybrid approach a data source from one platform type and a data target on another platform type can be implemented.

In any of the examples herein the data masking tool can be used to mask data in flat files. Features to assist in masking can be offered such as automatically detecting details about the format of a table represented in a flat file. For example the tool can be configured to read a table in a flat file and determine the number of columns name of columns e.g. if stored in the first row of the flat file data type size precision and the like. The format e.g. list of column names of the table in the flat file and the fields therein can be presented to the user for confirmation. Because the column names are listed the user can easily identify the familiar column names and select masking rules to be applied to the columns based on their respective names.

A graphical user interface presenting the column names can be used to select masking rules for the respective columns as described herein.

In the example the data masking profile includes a source definition and one or more masking rules . The source definition can be stored within the data masking tool for re use in other profiles.

In the example the executable data masking task includes one or more names or locations of data masking profiles that are executed when the executable data masking task is invoked. In this way more than one profile can be strung together to achieve more complex functionality or to re use functionality already available.

In the example the data masking tool can contact the metadata management tool via an application programming interface API which produces metadata regarding the source data .

The metadata can include any of a variety of characteristics about the source data . For example if the source data comprises tables the metadata can indicate column names for tables data types for the columns and the like. If multiple tables are represented in the source data the metadata can also indicate table names relationships between the tables and the like.

The metadata can be used to generate data masking configuration data . As in any of the examples supporting an API the API can be used to invoke the data masking tool which ultimately outputs the masked data .

At metadata regarding the source data is stored as data masking configuration information. For example if the metadata contains information about tables columns column names data types and the like it can be used to generate corresponding data masking configuration information.

If desired incomplete information can be completed based on partially populated configuration information. For example a user can choose the appropriate masking rules to be applied to the respective columns in a table.

However it is also possible for the metadata management tool to store the masking rules and masking parameters as part of its metadata leading to a more integrated configuration information management approach.

At data masking is performed with the data masking configuration information including that obtained from the metadata management tool.

The client tier need not be considered a part of the system because a standard browser can be used. However it can be considered the client side of the data masking system in some implementations.

The web tier can include the presentation with JSP forming the view and Struts providing the control as depicted in . The web tier can implement the user interface of the tool providing the user with the way to defining maintaining the various entities like Source Definitions Profiles Data Sets and Executions.

The application tier can include infrastructure execution and I O components to provide execution control logic implementation and file system access respectively as depicted in the diagram.

The I O Component can perform the task of reading the input source data passing it to the execution component and subsequently receiving the masked output data from the execution component.

The Execution Component can include the data masking logic and algorithms. The component can perform the following applying the rules defined in the profile to the input dataset e.g. source data received from the I O component returning the masked output dataset e.g. target data to the I O component and composing the execution details into XML format. The execution component can be self sufficient and expose an interface that can be invoked from other applications.

The Data tier implements access to the mapping rules persisted in the data store. The persistence component can encapsulate the database interaction logic and be accessed by the web component and the execution component.

After the information about the source text file is available to the tool the tool can fetch the metadata from the file e.g. the number of columns name of columns their data type size or precision and the like and displays it to the user.

After the user selects the masking rules for the columns the information can be submitted with the Submit button.

The tool can read the spreadsheet and create XML from it. The tool or a separate tool can read the XML to file the source of the data e.g. real time data or from a text file .

If real time data is indicated then the tool acts on the data using the masking rules provided by the user in the spreadsheet. If the source is a text file then the tool acts on the data in the text file masking it based on the user information in the spreadsheet.

The tool can easily be extended to any data source because the tool can use a spreadsheet to obtain the metadata about the source.

The following tags can be defined when representing data masking configuration information in extensible markup language. In any of the examples herein corresponding data masking configuration information can be stored and implemented by the data masking tool.

Static substitution is shown in . A column is replaced with a static values for all the rows in the Name field. For example all names can be replaced with ZZZ ZZZZZ. 

Dataset substitution is shown in . A column is replaced with a value from a pre defined dataset. For example the names dataset can be used to replace all the rows in the Name column.

Random substitution is shown in . A column is replaced with a random value within a range such that the value is random e.g. replace a data with a random date between a range .

Encryption is shown in . The data in a column is encrypted using a secure encryption algorithm e.g. replace the Name column with an encrypted string .

Shuffling is shown in . The column values of a dataset are shuffled like a pack of cards e.g. the column Name is shuffled without changing the SSN column .

In the example a Java custom transform is used in INFORMATICA software. A data masking tool can take advantage of the PowerMart and PowerCenter features of INFORMATICA software to allow access to and from a wide variety of data sources and formats.

A package containing a component e.g. pcjava.dll and pcjava2.jar can be installed by which the custom transform can be implemented.

The PowerCenter Designer can be started and an external object from the package pcjava.xml can be imported. The Transformation Developer can be opened and a new Advanced External Transformation ATX can be created as shown in .

The ATX can be renamed to describe the custom transform. The ports section can be left as it is e.g. empty for now and proceed to the Properties section as shown in . The ATX can be configured as shown. Note that if the pmjava2.dll is installed in any other directory than the ExtProc directory of the PowerCenter server the Runtime Location setting must be overridden. The Runtime Location should contain the absolute path to the directory that PCJava is installed.

A sample mapping is created to read records from a flat file and invoke the custom transformation. The custom transformation can create a flat file from the records and invoke the data masking tool to process the file. After the data masking operation is completed the records in the masked output file are fed back to the INFORMATICA software which creates a target file.

After the mapping is stored in the repository a reusable workflow component can be created to execute the flow as shown in .

The technologies described herein can be used in any of a variety of scenarios but are particularly useful in the field of software development such as in software testing. Data masking as described herein can be applied to production data to generate test data suitable for use in testing environments.

Because the data can be pulled across technology platform types it is possible for example to pull data from a live mainframe environment onto a desktop e.g. microcomputer environment as part of the masking process. This can be helpful if testing is taking place on the microcomputer environment. For example the data can be tested in place or easily transferred to another microcomputer.

In any of the examples herein randomization can be achieved via a random number generator that applies a Mersenne Twister random number generation technique. For example data shuffling can be achieved via such a random number generator. A Mersenne Twister random number generation technique can exhibit very high periodicity and other advantages.

With reference to the computing environment includes at least one processing unit and memory . In this most basic configuration is included within a dashed line. The processing unit executes computer executable instructions and may be a real or a virtual processor. In a multi processing system multiple processing units execute computer executable instructions to increase processing power. The memory may be volatile memory e.g. registers cache RAM non volatile memory e.g. ROM EEPROM flash memory etc. or some combination of the two. The memory can store software implementing any of the technologies described herein.

A computing environment may have additional features. For example the computing environment includes storage one or more input devices one or more output devices and one or more communication connections . An interconnection mechanism not shown such as a bus controller or network interconnects the components of the computing environment . Typically operating system software not shown provides an operating environment for other software executing in the computing environment and coordinates activities of the components of the computing environment .

The storage may be removable or non removable and includes magnetic disks magnetic tapes or cassettes CD ROMs CD RWs DVDs or any other computer readable media which can be used to store information and which can be accessed within the computing environment . The storage can store software containing instructions for any of the technologies described herein.

The input device s may be a touch input device such as a keyboard mouse pen or trackball a voice input device a scanning device or another device that provides input to the computing environment . For audio the input device s may be a sound card or similar device that accepts audio input in analog or digital form or a CD ROM reader that provides audio samples to the computing environment. The output device s may be a display printer speaker CD writer or another device that provides output from the computing environment .

The communication connection s enable communication over a communication medium to another computing entity. The communication medium conveys information such as computer executable instructions audio video or other media information or other data in a modulated data signal. A modulated data signal is a signal that has one or more of its characteristics set or changed in such a manner as to encode information in the signal. By way of example and not limitation communication media include wired or wireless techniques implemented with an electrical optical RF infrared acoustic or other carrier.

Communication media can embody computer readable instructions data structures program modules or other data in a modulated data signal such as a carrier wave or other transport mechanism and includes any information delivery media. The term modulated data signal means a signal that has one or more of its characteristics set or changed in such a manner as to encode information in the signal. Communication media include wired media such as a wired network or direct wired connection and wireless media such as acoustic RF infrared and other wireless media. Combinations of any of the above can also be included within the scope of computer readable media.

The techniques herein can be described in the general context of computer executable instructions such as those included in program modules being executed in a computing environment on a target real or virtual processor. Generally program modules include routines programs libraries objects classes components data structures etc. that perform particular tasks or implement particular abstract data types. The functionality of the program modules may be combined or split between program modules as desired in various embodiments. Computer executable instructions for program modules may be executed within a local or distributed computing environment.

Any of the methods described herein can be implemented by computer executable instructions in one or more computer readable media e.g. computer readable storage media or other tangible media . The technologies described herein can be implemented in a variety of programming languages.

The technologies from any example can be combined with the technologies described in any one or more of the other examples. In view of the many possible embodiments to which the principles of the disclosed technology may be applied it should be recognized that the illustrated embodiments are examples of the disclosed technology and should not be taken as a limitation on the scope of the disclosed technology. Rather the scope of the disclosed technology includes what is covered by the following claims. We therefore claim as our invention all that comes within the scope and spirit of these claims.

