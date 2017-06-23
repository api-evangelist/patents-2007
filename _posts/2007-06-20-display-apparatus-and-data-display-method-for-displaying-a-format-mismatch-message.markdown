---

title: Display apparatus and data display method for displaying a format mismatch message
abstract: A display apparatus includes a display; a receiver which receives a broadcasting signal including a program with a data format; an image processing part which processes the received program according to an available data format; and a controller which controls the image processing part to display a message informing that both data formats are not matched on the display if the data format of the received program is not matched with the available data format to be processed by the image processing part.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08325277&OS=08325277&RS=08325277
owner: Samsung Electronics Co., Ltd.
number: 08325277
owner_city: Suwon-si
owner_country: KR
publication_date: 20070620
---
This application claims priority from Korean Patent Application No. 2006 0088959 filed on Sep. 14 2006 in the Korean Intellectual Property Office the disclosure of which is incorporated herein by reference.

Apparatuses and methods consistent with the present invention relate to a display apparatus and more particularly to displaying an image according to a data format of a received program.

A related art display apparatus receives a broadcasting signal transmitted from a broadcasting station to display viewable images. As digital broadcasting has started in the related art it is possible to receive a data broadcasting channel among channels of broadcasting signals. The data broadcasting channel is a channel to display images by data instead of a video signal and displays images about how to use an application channel information weather information etc. which are in the broadcasting signals.

The data broadcasting channel includes a related art data format such as Advanced Common Application Platform ACAP Open Cable Application Platform OCAP Multimedia and Hypermedia information coding Experts Group MHEG Multimedia Home Platform MHP etc. The display apparatus extracts data from the received broadcasting signals and displays only a broadcasting signal of a data format matched with a predetermined data format.

However if the data format of the received data broadcasting is not matched with an available data format which the display apparatus can process nothing is displayed. Thus a user who does not have information on the data format may be confused.

The present invention provides a display apparatus and a data display method thereof which provides information for unmatched data if a data format of received data broadcasting is not matched with an available data format that the display apparatus is capable of processing and which allows a user to select only a channel of a program with a matched data format.

According to an aspect of the present invention there is provided a display apparatus comprising a display a receiver which receives a broadcasting signal including a program with a data format an image processing part which processes the received program according to an available data format and a controller which controls the image processing part to display a message informing that both data formats are not matched on the display if the data format of the received program is not matched with the available data format to be processed by the image processing part.

According to another aspect of the invention the controller generates a channel list with the available data format to be processed by the image processing part and controls the image processing part to select a channel in the channel list.

According to another aspect of the invention the controller controls the image processing part to display the channel list on the display.

According to another aspect of the invention the image processing part further comprises a filter part to process received data from the broadcasting signal having a format matched with the available data format to be processed by the image processing part and process the data processed by the filter part to be displayed on the display.

According to another aspect of the invention the available data format of the image processing part comprises one of ACAP OCAP MHEG and MHP.

According to another aspect of the present invention there is provided a display apparatus comprising a display a receiver which receives a broadcasting signal including a program with a data format an image processing part which processes the received program according to an available data format and a controller which generates a channel list having channels with the available data format to be processed by the image processing part and controls the image processing part to select a channel in the channel list.

According to another aspect of the invention the display apparatus further comprises a storing part wherein the controller stores the channel list in the storing part so as to select a channel from the channel list.

According to another aspect of the invention the display apparatus further comprises a user input part and a user interface generating part which generates a user interface corresponding to the channel list wherein the controller receives a channel selection from the user input part through the user interface.

According to another aspect of the invention the image processing part further comprises a filter part to process received data from the broadcasting signal having a format matched with the available data format to be processed by the image processing part and process the data processed by the filter part to be displayed on the display.

According to another aspect of the invention the available data format of the image processing part comprises one of ACAP OCAP MHEG and MHP.

According to another aspect of the present invention there is provided a data display method of a display apparatus comprising a display comprising receiving a broadcasting signal which comprises a program including a data format determining whether a data format of the program is matched with an available data format to display an image on the display and displaying a message informing that both data formats are not matched with each other on the display if the data format is determined to be unmatched with the available data format.

According to another aspect of the invention the data display method of the display apparatus further comprises generating a channel list having channels with the available data format which can be displayed on the display and displaying an image corresponding to a channel selected from the channel list on the display.

According to another aspect of the invention the available data format to display an image on the display comprises one of ACAP OCAP MHEG and MHP.

The foregoing and or other aspects can be achieved by providing a data display method of a display apparatus comprising a display and an image processing part comprising receiving a broadcasting signal which comprises a program including a data format generating a channel list having channels with an available data format which the image processing part is capable of processing and displaying an image corresponding to a channel selected from the channel list on the display.

According to an aspect the available data format to display an image on the display comprises one of ACAP OCAP MHEG and MHP.

Reference will now be made in detail to the exemplary embodiments of the present invention examples of which are illustrated in the accompanying drawings wherein like reference numerals refer to like elements throughout. The exemplary embodiments are described below so as to explain the present invention by referring to the figures.

Referring to a display apparatus according to an exemplary embodiment of the present invention includes a receiver a signal separation part a display a storing part a user input part a user interface UI generating part an image processing part and a controller . The display apparatus according to the exemplary embodiment may be provided as a digital television TV which receives data broadcasting and displays it for example but not by way of limitation.

The receiver receives a broadcasting signal which includes a program having a data format. The receiver may be provided as a tuner but is not limited thereto.

The signal separation part separates the broadcasting signal which the receiver receives into a video signal an audio signal and a data signal by a stream unit of each channel with the same program identifier ID . The broadcasting signal includes Program Specific Information PSI . Service information in the PSI includes digital television service teletext service FM radio data broadcasting service etc. The signal separation part extracts and transmits data broadcasting service information to a filter part . In the exemplary embodiment the signal separation part may be provided as a demultiplexer Demux but is not limited thereto.

The display displays images based on a video signal which is processed by the image processing part . The display may include a cathode ray tube CRT a liquid crystal display LCD a plasma display panel PDP a digital light processing DLP device a surface conduction electron emitter display SED a field emission display FED etc. but is not limited thereto.

The storing part stores a channel list with an available data format which the image processing part is capable of processing by control of the controller . The storing part may include a memory stick an Electrically Erasable Programmable Read Only Memory EEPROM etc. but is not limited thereto.

The user input part selects one of channels in the channel list with the available data format which the image processing part is capable of processing. The user input part includes a channel selection key and may be disposed on one side of the display apparatus or on a remote controller or the like.

The UI generating part generates a UI image corresponding to a message to inform the user that a data format of a received program is not matched with the available data format which the image processing part is capable of processing if the data format of the received program are not matched for the available data format which the image processing part is capable of processing. Further the UI generating part may generate a UI corresponding to the channel list with the data format which the image processing part is capable of processing.

The image processing part processes the program received through the receiver according to the available data format. In the exemplary embodiment the image processing part includes the filter part and a decoder

The filter part processes a data signal from the received broadcasting signal with a format matched with the available data format which the image processing part is capable of processing. The filter part detects the stream type of data transmitted from the signal separation part and extracts the data format which the image processing part is capable of processing from the data if service information in the PSI is the data broadcasting service.

The data format includes ACAP OCAP MHEG and MHP. The ACPA and OCAP are standards which are used for the data broadcasting in the USA and in Korea. The MHEG standard is mostly used in England and the MHP is mostly used in Europe except England.

The display apparatus according to the exemplary embodiment may process signals for data broadcasting by one of the foregoing data formats. Here the filter part transmits a data signal with a data format corresponding to the available data format which the image processing part is capable of processing to the decoder

The decoder decodes a data signal transmitted from the filter part in a form possible to output to the display .

The controller controls the image processing part to display a message to inform the user that a data format of a received program by the receiver is unmatched if the data format of the received program are not matched with the available data format which the image processing part is capable of processing. The controller may include a microcomputer a software program etc. but is not limited thereto.

The controller controls the image processing part to display the appropriate UI image generated by the UI generating part on the display if a data signal is not transmitted to the decoder by the filter part as the data format of the received broadcasting signal does not match with the available data format which the image processing part is capable of processing.

The controller generates a channel list having channels with a matched data format and controls the image processing part to select a channel in the channel list if a data format of a received broadcasting signal is not matched for the data format which the image processing part is capable of processing.

Hereinafter the user interface of the display apparatus according to the exemplary embodiment will be described with reference to . The user interface includes an interface to indicate that a data format is not matched with the available data format which the image processing part is capable of processing and a user interface to show the channel list having channels with the matched data format.

The controller controls the image processing part to display an interface image about a message to inform the user that a data signal of the received broadcasting signal is an unmatched data format on the display if a data format of a received data broadcasting signal is not matched with the available data format which the image processing part is capable of processing. Thus if the display apparatus receives a program of a data format which cannot be processed by the image processing part information that the program of the data format cannot be processed is provided to the user.

The controller generates a channel list of received broadcasting signals having format matched for the available data format which the image processing part is capable of processing so that the user selects only one of the channels in the channel list thereby preventing a selection of a channel having data broadcasting with an unmatched data format from being selected.

If a key in the user input part is inputted the controller controls the image processing part to display the user interface showing the channel list having the matched data format on the display . Thus the user may select one of viewable channels of the digital broadcasting through the user input part .

Hereinafter a data display method of the display apparatus according to the exemplary embodiment will be described with reference to .

The controller receives a broadcasting signal including a program with a data format operation S . The filter part determines whether the data format of the program received at operation S is matched with the available data format which may be processed in the image processing part to display an image operation S .

If the data format is not matched the controller controls the image processing part to display a message informing that the data format of the received program is not matched on the display operation S . If the data format is matched the controller controls the image processing part to display an image corresponding to the received program on the display operation S . Thus if the display apparatus receives a program of a data format which can not be processed in the image processing part it provides information that the program cannot be processed.

The controller at operation S further includes an operation to generate a channel list having channels with the matched data format and an operation to display an image corresponding to a channel selected from the channel list on the display . Accordingly the user may select only digital broadcasting channels possible to be displayed.

As described above a display apparatus and a data display method thereof displays information that a program can not be processed on a screen if the display apparatus receives a program of a data format which cannot be processed which may prevent a user from being confused.

Further the display apparatus displays only a channel with a data format which can be processed and thus a user may conveniently watch data broadcasting.

Although exemplary embodiments of the present invention have been shown and described it will be appreciated by those skilled in the art that changes may be made in these embodiments without departing from the principles and spirit of the invention the scope of which is defined in the appended claims and their equivalents.

