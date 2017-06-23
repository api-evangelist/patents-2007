---

title: Converting documents
abstract: A method of converting a document, such as a document complying with the CEN-XFS standard for Forms. The method comprises accessing format parameters; reading information from the document; parsing the read information to detect attributes and text; identifying any detected attributes not consistent with the accessed format parameters; converting any identified attributes not consistent with the accessed format parameters into attributes consistent with the accessed format parameters; and creating a converted document in which all of the attributes conform to the accessed format parameters.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09064231&OS=09064231&RS=09064231
owner: NCR Corporation
number: 09064231
owner_city: Duluth
owner_country: US
publication_date: 20071213
---
The present invention relates to converting documents in particular though not exclusively the present invention relates to converting documents complying with a CEN XFS standard.

The CEN XFS standard is well known in the financial services field. CEN XFS provides a common API for accessing and manipulating various devices such as Automated Teller Machine ATM devices regardless of the vendor of those devices. This allows a single application to run in a multi vendor hardware environment which is useful for ATMs because these typically include a plurality of devices such as card readers and printers which may be supplied by different vendors.

Devices in an ATM are controlled by XFS service providers which are software components that comply with the CEN XFS standard and that are supplied by the vendor of that device or the vendor of the ATM including that device. Each service provider provides a CEN XFS interface that is uniform for that type of device.

An application executing on an ATM for example a supervisor application that supports diagnostic maintenance and replenishment operations can display or print information using documents that provide text and location attributes for the display or printer. These documents also referred to as XFS Forms comply with the CEN XFS standard see CWA 14050 Extensions for Financial Services XFS interface specification Release 3.03 in particular Part 3 Printer Device Class Interface and Part 9 Text Terminal Unit Device Class Interface . shows the format of a CEN XFS Form 10.

To display information for example on a rear operator panel an ATM application sends a display request and a pointer to a display document Form . The service provider for the rear operator panel receives the request and accesses the display document. The service provider then parses the display document and renders the information contained in the display document using the attributes provided by the display document.

Although these documents comply with this XFS standard different vendors have different interpretations of this standard. As a result a document prepared by one vendor may not be correctly parsed by a service provider supplied by a different vendor. If the service provider cannot parse a document the document is not displayed or printed in the case of a print request .

There is therefore a need to ensure compatibility between documents provided by one vendor and service providers supplied by a different vendor.

According to a first aspect of the present invention there is provided a method of converting a document the method comprising accessing format parameters reading information from the document parsing the read information to detect attributes and text identifying any detected attributes not consistent with the accessed format parameters converting any identified attributes not consistent with the accessed format parameters into attributes consistent with the accessed format parameters and creating a converted document in which all of the attributes conform to the accessed format parameters.

The step of accessing format parameters may include receiving one or more parameters selected by a user via a graphical user interface. Alternatively the step of accessing format parameters may include using predefined format parameters.

The format parameters may indicate dimensions of media on which the text is to be rendered. The media dimensions may relate to paper size display size or the like and may be in the format of a number of characters wide and a number of characters high. The format parameters may relate to characteristics of a self service device such as a self service display a self service printer or the like.

The method may further comprise the step of saving the converted document as multiple files each file having a filename derived from part of the original document.

According to second aspect of the present invention there is provided a computer program comprising program instructions for implementing all of the steps of the first aspect of the invention.

The computer program may be i embodied on a record medium ii conveyed on an electrical carrier signal or iii stored in computer memory.

According to a third aspect of the present invention there is provided a method of converting a document complying with a first implementation of a CEN XFS standard to a second implementation of the CEN XFS standard the method comprising reading information from a document complying with the first implementation of the CEN XFS standard parsing the read information to ascertain text and position information converting the position information to a format used by the second implementation of the XFS standard and creating a new document comprising the ascertained text and the converted position information so that a service provider operating according to the second implementation is operable to render the text.

According to fourth aspect of the present invention there is provided a computer program comprising program instructions for implementing all of the steps of the third aspect of the invention.

The computer program may be i embodied on a record medium ii conveyed on an electrical carrier signal or iii stored in computer memory.

By virtue of these aspects of the invention documents can be converted automatically thereby saving time and reducing the scope for human error.

Reference is first made to which illustrates a document in the form of an XFS Form in a first format and which illustrates an ATM operator panel . The particular XFS Form 20 illustrated in is for use with the panel .

The XFS Form 20 is entitled enBusOpPleaseWait as shown in a title attribute and is configured for use with a display size of thirty two characters by sixteen characters as shown in size attribute . The form has two main XFS fields one called Information the other called Information .

The Information field comprises a plurality of attributes. These attributes include a content type attribute which is text in this example a text size attribute which is thirty two characters wide and one character high in this example a text location attribute which is at the left most co ordinate on the width of the display and six lines down and an initial value attribute which is Please wait while accessing in this example .

The Information field is very similar to the Information field . The only differences are i the value of the location attribute is different one line below that of the Information field and ii the value of the initial value attribute is also different the text is the device in this example .

When this enBusOpPleaseWait XFS Form 20 is loaded into an ATM and accessed by a service provider a software component for the panel then the service provider parses the Form 20 and renders the text Please wait while accessing the device on a display in the panel as shown in . The display can render thirty two characters in a row and sixteen characters in a column. The display also has two columns of programmable keys . The function performed by one of these keys depends on the particular screen being displayed as indicated by the text presented in alignment with that key .

The panel is typically used by an authorized person member of bank staff customer engineer replenishment agent or the like when performing diagnostic maintenance or replenishment operations. The panel is not typically used by a customer of the ATM.

On a typical ATM there may be hundreds of different Forms each Form being used to provide information either on the rear operator panel a journal printer not shown or a receipt printer not shown .

When Forms such as Form 20 are to be used on an ATM having a display that can render a different number of characters than thirty two by sixteen then the Form 20 has to be converted. There may also be other changes that are required. For example the text may have to be presented on more lines than in Form 20.

A method of implementing this conversion will now be described with reference to which is a flowchart illustrating one embodiment of the present invention and which is a listing of an XFS Form 80 created using the steps illustrated in .

The method may be implemented by a general purpose computer executing a computer program having instructions for performing the steps of the flowchart .

In the first step step is for the computer program to access the XFS Form 20 to be converted. A user of the program may use a graphical user interface to point to the location of the XFS Form 20 in a directory structure or the user may load the XFS Form 20 file into a predefined directory.

The program then prompts the user step to enter details about the type of Form to be created. The program may provide predefined Form types for example one Form type used by a first vendor another Form type used by a second vendor and such like. The Form types may correspond to those used by well known ATM vendors such as NCR Corporation trade mark Diebold Corporation trade mark Wincor Nixdorf AG trade mark and the like. If the user does not wish to select a Form type associated with a particular vendor then the user can select individual parameters such as i the size of the display that will be used for example forty characters by twelve characters eighty characters by forty characters or the like ii the reference scheme used for the upper left location on a display for example 0 0 or 1 1 and such like. The program may also prompt the user to enter details about the version of the CEN XFS standard to be converted from and or to for example NCR XFS v2.02 to Diebold XFS v3.02 .

In this example the newly converted Form will be used in conjunction with a display having a width of forty characters and a height of twelve characters. The upper left hand location will be referenced as 1 1 . The user selects these parameters using a drop down menu on a graphical user interface.

Once the program can access the XFS Form 20 and the conversion parameters have been entered either individually or by selecting a predefined Form type the program then reads step the XFS Form 20 and parses step the contents of the XFS Form 20.

When the program parses the XFS Form 20 it ascertains step for each attribute for example size attribute whether that attribute is correct for example having the correct value and format for the type of Form to be created.

If the attribute is correct step then it is copied to a corresponding line in a new XFS Form 80 see . For example the title attribute is unchanged from the title attribute of XFS Form 20.

If the attribute is incorrect then the program converts the incorrect attribute to a new attribute consistent with the conversion parameters step and copies the new attribute to a corresponding line in the new XFS Form 80. For example because the display for which the XFS Form 80 is intended is wider and shorter than display the program converts the size attribute from 32 16 to 40 12 . Similarly because the upper left location is referenced as 1 1 rather than 0 0 the program converts the text size attribute to that shown for the text size attribute . The program also converts the text location attributes to new text location attributes because of the change in the reference scheme.

If there is a substantial change in the number of characters available in either the width or the height then the program may also change how the text is displayed. For example if many lines of text are to be displayed using this Form 80 then the program may reduce the spacing between lines so that the text will fit onto one screen of the display. In this example the program has converted the initial value attributes to new initial value attributes so that part of the text the from initial value attribute has been moved to new initial value attribute .

When all of the attributes have been copied or converted to the new XFS Form 80 step then the program saves the XFS Form step using either the name of the title attribute or a name entered by the user.

This new XFS Form 80 can be loaded onto an ATM having a rear operating panel with a display having forty by twelve characters. When this new XFS Form 80 is interpreted by a service provider for the display then the text presented is as shown in . The operating panel includes programmable keys . It is worth noting that when the program is converting a Form the program may also have to adjust the spacing between lines to ensure that text from the newly created Form 80 aligns with corresponding programmable keys on the panel .

Various modifications may be made to the above described embodiment within the scope of the present invention. For example the Form may be rendered on printable media such as thermal paper rather than a display. In an ATM the printable media may be printed on a receipt printer a journal printer a statement printer a passbook printer or the like.

In other embodiments the steps of method may be performed in a different order to that described for example the program may prompts the user step to enter details about the type of Form to be created prior to accessing the Form step .

In other embodiments the documents may not be text files for example the documents may include graphics.

The attributes listed in the above embodiment are just a small selection from the many different attributes that are available in other embodiments different attributes may be converted than those described above for example a language attribute.

