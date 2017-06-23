---

title: Apparatus and method for receiving a transport stream containing a plurality of content data
abstract: To compensate a failure in downloading of music piece data. For example, when a viewer instructs purchase of a music pieceC to an IRD at a timing t during the sixth transmission of music piece data, the music piece data to be transmitted for the seventh time immediately after the instruction is usually downloaded. When the downloading of the music piece data transmitted for the seventh time fails for some reason, downloading is re-executed on music piece data to be transmitted for the eighth time. The music piece data for the final transmission time in each of musical pieces is used for re-execution. Timing at which downloading of the music piece data transmitted for the time immediately preceding the final time can be instructed is set as purchase limit time by using elapsed time since program start time.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08204789&OS=08204789&RS=08204789
owner: Sony Corporation
number: 08204789
owner_city: 
owner_country: JP
publication_date: 20071102
---
This application is a divisional of U.S. application Ser. No. 09 744 121 filed on Mar. 19 2001 now U.S. Pat. No. 7 310 810 which is a national stage application under 35 U.S.C. 371 of International Application No. PCT JP00 03199 filed May 18 2000 which claims priority from Japanese Application Nos. JP 11 138849 JP 11 138850 JP 11 138851 and JP 11 138852 each filed on May 19 1999 the disclosures of which are incorporated herein by reference.

The present invention relates to broadcasting equipment and method receiving equipment and method and a medium and more particularly to broadcasting equipment and a method receiving equipment and a method and a medium suitable for use in the case of providing service of downloading contents data.

Digital satellite broadcasting such as for example Sky PerfecTV trademark is being widespread. The digital satellite broadcasting can transmit a signal of higher quality as compared with existing analog broadcasting and realizes a large number of channels. In such digital satellite broadcasting channels dedicated to sports movies music news and the like are prepared. A music channel is one of popular channels among the dedicated channels.

When a view watches such a music channel he she may like a music piece being broadcasted and want to purchase a CD Compact Disc or the like containing the musical piece. In such a case it is convenient that data on the music piece can be downloaded while watching the music channel. The applicant of the present invention has proposed a system capable of multiplexing music piece encoded by using the ATRAC Adaptive Transform Acoustic Coding system with respect to main broadcasting signals video signal and sound signal of the music channel distributing the resultant data and charging the viewer who is purchasing downloading the ATRAC data for example in Japanese Patent Application No. 10 201731.

The ATRAC system is a compression coding system adopted in the case of recording audio data onto an MD Mini Disc trademark .

In a system of distributing music piece data and charging the viewer who purchases it as described above if purchase of a plurality of music piece data can be instructed in a lump and the plurality of music piece data can be downloaded in optimum order efficiency with respect to time increases and music piece data of a larger amount can be downloaded within predetermined time. The conventional system has a problem that it does not have such a function.

In a pay per view carried out on a movie channel or the like in digital satellite broadcasting purchasing watching a program from a midpoint of the program is not sufficiently worthy. Consequently in the case where predetermined time is elapsed since the broadcasting start time of the program purchase limitation time is set so that the program cannot be purchased.

In a system of distributing music piece and charging the viewer who is purchasing the data as described above however the purchase limitation time is not specified. There is consequently a problem such that a failure in downloading cannot be compensated.

Further in a pay per view carried out on a movie channel or the like in digital satellite broadcasting preview time test listening time during which there is no charge for viewing is set. Consequently the viewer can determine whether a program is worth viewing purchasing or not during the preview.

Such a system of distributing music piece data and charging the viewer who purchases it has however a problem that there is no regulation regarding test listening of purchasable music piece data.

Furthermore a receiving apparatus as a component of a system as described above has a problem that the apparatus cannot process the two kinds of music piece data simultaneously and independently of each other.

Further in a system of distributing music piece data and charging the viewer who purchases it as described above if purchase of plural music piece data can be instructed in a lump and the plural music piece data can be downloaded in an optimum order efficiency with respect to time increases and music piece data of a larger amount can be downloaded within predetermined time. The conventional system has a problem that it does not have such a function.

An object of the present invention is to compensate failure in downloading by setting the purchase limitation time of music piece data in a system of downloading music piece data or the like.

An object of the present invention is to enable music piece data to be test listened before the user purchases the music piece data in a system of downloading music piece data or the like.

An object of the present invention is to enable two kinds of music piece data compression coded in the ATRAC system and the MPEG2 system to be processed simultaneously and independently of each other in a system of downloading music piece data or the like.

An object of the present invention is to enable efficiency with respect to time to be improved and music piece data of a larger amount to be downloaded within predetermined time by optimizing the order of downloading plural music piece data in a system of downloading music piece data or the like

The first invention is broadcasting equipment for multiplexing downloadable contents data together with program information onto a main broadcast signal and broadcasting resultant data comprising 

multiplexing means for repeatedly multiplexing the same contents data and the program information a plurality of times onto the main broadcast signals of broadcasting time of one program thereby generating a transport stream. By doing in this manner a failure in downloading can be compensated by setting the purchase limit time corresponding to the contents data.

The second invention is the broadcasting equipment wherein the purchase limit time setting means sets timing at which downloading of the contents data of a time immediately preceding the final time among the plurality of times can be instructed as the purchase limit time. By doing in this manner it is possible to favorably set the purchase limit.

The third invention is the broadcasting equipment wherein the contents data includes audio data encoded by the ATRAC system or audio data encoded by the MPEG 2 system. By doing in this manner it becomes possible to favorably download the contents data including audio data encoded by the ATRAC system or audio data encoded by the MPEG system.

The fourth invention is a broadcasting method of a broadcasting equipment for multiplexing downloadable contents data together with program information onto a main broadcast signal and broadcasting resultant data comprising 

a multiplexing step of repeatedly multiplexing the same contents data and the program information a plurality of times onto the main broadcast signals of broadcasting time of one program thereby generating a transport stream. By doing in this manner a failure in downloading can be compensated by setting the purchase limit time corresponding to the contents data.

The fifth invention is a medium for allowing broadcasting equipment for multiplexing downloadable contents data together with program information onto a main broadcast signal and broadcasting resultant data to execute a program comprising 

a multiplexing step of repeatedly multiplexing the same contents data and the program information onto the main broadcast signals of broadcasting time of one program thereby generating a transport stream. By doing in this manner a failure in downloading can be compensated by setting the purchase limit time corresponding to the contents data.

The sixth invention is receiving equipment for receiving a transport stream obtained by repeatedly multiplexing downloadable contents data together with program information onto a main broadcast signal a plurality of times comprising 

capturing means for capturing the contents from the transport stream in response to the download instruction received by the receiving means 

re executing means for re executing capture of the contents when the capturing means fails to capture the contents 

extracting means for extracting the program information corresponding to the contents data from the transport stream and

stopping means for stopping the receiving process of the receiving means in accordance with purchase limit time included in the program information. By doing in this manner when the capture of contents fails the capture of the contents is re executed and reception of a download instruction from the user is stopped according to the purchase limit time included in the program information. Thus a failure in downloading can be compensated.

the contents data includes audio data encoded by the ATRAC system or audio data encoded by the MPEG2 system. By doing in this manner it becomes possible to favorably download the contents data including audio data encoded by the ATRAC system or audio data encoded by the MPEG system.

The eighth invention is a receiving method of receiving equipment for receiving a transport stream obtained by repeatedly multiplexing downloadable contents data together with program information onto a main broadcast signal a plurality of times comprising 

a capturing step of capturing the contents from the transport stream in response to the download instruction received in the receiving step 

a re executing step of re executing capture of the contents when the capturing step fails to capture the contents 

an extracting step of extracting the program information corresponding to the contents data from the transport stream and

a stopping step of stopping the receiving process of the receiving means in accordance with purchase limit time included in the program information.

The ninth invention is a medium for allowing a receiving equipment for receiving a transport stream obtained by repeatedly multiplexing downloadable contents data together with program information onto a main broadcast signal a plurality of times to execute a program comprising 

a capturing step of capturing the contents from the transport stream in response to the download instruction received in the receiving step 

a re executing step of re executing capture of the contents when the capturing step fails to capture the contents 

an extracting step of extracting the program information corresponding to the contents data from the transport stream and

a stopping step of stopping the receiving process of the receiving means in accordance with purchase limit time included in the program information. By doing in this manner when the capture of contents fails the capture of the contents is re executed and reception of a download instruction from the user is stopped according to the purchase limit time included in the program information. Thus a failure in downloading can be compensated.

The tenth invention is receiving equipment for receiving a transport stream obtained by multiplexing plural encoded data encoded by different systems comprising 

first outputting means for outputting the first encoded data extracted by the first extracting means 

decoding means for decoding the second encoded data extracted by the second extracting means to thereby generate audio data and

second outputting means for outputting the audio data generated by the decoding means. By doing in this manner it becomes possible to process for example two kinds of music piece data simultaneously and independently.

the second encoded data is audio data compression encoded by using an MPEG2 system. By doing in this manner it becomes possible to process two kinds of music piece data compression encoded by the ATRAC system or MPEG 2 system simultaneously and independently.

The twelfth invention is a receiving method of receiving equipment for receiving a transport stream obtained by multiplexing a plurality of encoded data encoded by different systems comprising 

a decoding step of decoding the second encoded data extracted in the second extracting step to thereby generate audio data and

a second outputting step of outputting the audio data generated in the decoding step. By doing in this manner it becomes possible to process for example two kinds of music piece data simultaneously and independently.

The thirteenth invention is a medium for allowing a receiving equipment for receiving a transport stream obtained by multiplexing a plurality of encoded data encoded by different systems to execute a program comprising 

a decoding step of decoding the second encoded data extracted in the second extracting step to thereby generate audio data and

a second outputting step of outputting the audio data generated in the decoding step. By doing in this manner it becomes possible to process for example two kinds of music piece data simultaneously and independently.

The fourteenth invention is receiving equipment for receiving a transport stream obtained by repeatedly multiplexing a plurality of contents data comprising 

reading means for reading predetermined information corresponding to the contents data from the transport stream 

determining means for determining order of extracting the plurality of contents data corresponding to the designation from the user received by the receiving means from the transport stream with reference to the predetermined information read by the reading means on the basis of a predetermined algorithm and

extracting means for extracting the plurality of contents data corresponding to the designation from the user received by the receiving means from the transport stream in accordance with the order determined by the determining means. By doing in this manner since it is arranged such that the order of extracting the plurality of contents data is determined based on a predetermined algorithm by referring to the predetermined read out information and the plurality of contents data corresponding to the designation from the user is extracted from the transport stream in accordance with the order it becomes possible to improve efficiency with respect to time as well as download the music piece data of a larger amount within predetermined time.

display control means for controlling a display to the effect that the contents data unable to be extracted exists when there exists the contents data which cannot be extracted within predetermined time by the extracting means in the plurality of contents data corresponding to the designation by the user received by the receiving means in the case where the extracting means extracts from the transport stream the plurality of contents data corresponding to the designation by the user received by the receiving means in accordance with the order determined by the determining means. By doing in this manner it becomes possible to ascertain details concerning the unloadable contents data from the display.

The sixteenth invention is a receiving method of receiving equipment for receiving a transport stream obtained by repeatedly multiplexing a plurality of contents data comprising 

a reading step of reading predetermined information corresponding to the contents data from the transport stream 

a determining step of determining order of extracting a plurality of contents data corresponding to the designation from the user received in the receiving step from the transport stream with reference to the predetermined information read in the reading step on the basis of a predetermined algorithm and

an extracting step of extracting the plurality of contents data corresponding to the designation from the user received in the receiving step from the transport stream in accordance with the order determined in the determining step. By doing in this manner since it is arranged such that the order of extracting the plurality of contents data is determined based on a predetermined algorithm by referring to the predetermined read out information and the plurality of contents data corresponding to the designation from the user is extracted from the transport stream in accordance with the order it becomes possible to improve efficiency with respect to time as well as download the music piece data of a larger amount within predetermined time.

The seventeenth invention is a medium for allowing receiving equipment for receiving a transport stream obtained by repeatedly multiplexing a plurality of contents data to execute a program comprising 

a reading step of reading predetermined information corresponding to the contents data from the transport stream 

a determining step of determining order of extracting a plurality of contents data corresponding to the designation from the user received in the receiving step from the transport stream with reference to the predetermined information read in the reading step on the basis of a predetermined algorithm and

an extracting step of extracting the plurality of contents data corresponding to the designation from the user received in the receiving step from the transport stream in accordance with the order determined in the determining step. By doing in this manner since it is arranged such that the order of extracting the plurality of contents data is determined based on a predetermined algorithm by referring to the predetermined read out information and the plurality of contents data corresponding to the designation from the user is extracted from the transport stream in accordance with the order it becomes possible to improve efficiency with respect to time as well as download the music piece data of a larger amount within predetermined time.

The eighteenth invention is broadcasting equipment for multiplexing downloadable contents data onto a main broadcast signal comprising 

the test listening number of times setting means for setting the number of test listening times of the contents data 

generating means for generating program information including the test listening time and the number of test listening times and

multiplexing means for multiplexing the program information generated by the generating means the main broadcast signal and the contents data to thereby generate a transport stream. By doing in this manner since it is arranged such that the test listening time and test listening times corresponding to the contents data are set and the program information including them is multiplexed onto the main broadcasting signal and contents data to thereby generate the transport stream it becomes possible to distribute the contents data capable of test listening before the music piece data is purchased.

the contents data includes audio data encoded by an ATRAC system or audio data encoded by an MPEG2 system. By doing in this manner it becomes possible to test listen the music piece data transmitted as audio data encoded by the ATRAC system or audio data encoded by the MPEG 2 system before the audio data is purchased.

The twentieth invention is broadcasting method of broadcasting equipment for multiplexing downloadable contents data onto a main broadcast signal and broadcasting resultant data comprising 

a test listening number of times setting step of setting the number of test listening times of the contents data 

a generating step of generating program information including the test listening time and the number of test listening times and

a multiplexing step of multiplexing the program information generated in the generating step the main broadcast signal and the contents data to thereby generate a transport stream. By doing in this manner since it is arranged such that the test listening time and test listening times corresponding to the contents data are set and the program information including them is multiplexed onto the main broadcasting signal and contents data to thereby generate the transport stream it becomes possible to distribute the contents data capable of test listening before the music piece data is purchased.

The twenty first invention is a medium for allowing broadcasting equipment for multiplexing downloadable contents data onto a main broadcast signal and broadcasting resultant data to execute a program comprising 

a test listening number of times setting step of setting the number of test listening times of the contents data 

a generating step of generating program information including the test listening time and the number of test listening times and

a multiplexing step of multiplexing the program information generated in the generating step the main broadcast signal and the contents data to thereby generate a transport stream. By doing in this manner since it is arranged such that the test listening time and test listening times corresponding to the contents data are set and the program information including them is multiplexed onto the main broadcasting signal and contents data to thereby generate the transport stream it becomes possible to distribute the contents data capable of test listening before the music piece data is purchased.

The twenty second invention is receiving equipment for receiving a transport stream obtained by multiplexing downloadable contents data together with program information onto a main broadcast signal comprising 

extracting means for extracting the program information corresponding to the contents data separated by the separating means from the transport stream 

regulating means for regulating a reproducing process of the reproducing means in accordance with the test listening time and the number of test listening times included in the program information extracted by the extracting means. By doing in this manner the contents data and the program information is extracted from the transport stream and the reproduction of the contents data is regulated in accordance with the test listening time and the number of test listening times included in the extracted program information. Consequently the music piece data can be test listened before purchasing it.

the contents data includes audio data encoded by the ATRAC system or audio data encoded by the MPEG2 system. By doing in this manner it becomes possible to test listen the music piece data transmitted as audio data encoded by the ATRAC system or audio data encoded by the MPEG 2 system before it is purchased.

The twenty fourth invention is a receiving method of receiving equipment for receiving a transport stream obtained by multiplexing downloadable contents data together with program information onto a main broadcast signal comprising 

an extracting step of extracting the program information corresponding to the contents data separated in the separating step from the transport stream 

a regulating step of regulating a reproducing process of the reproducing means in accordance with the test listening time and the number of test listening times included in the program information extracted in the extracting step. By doing in this manner the contents data and the program information is extracted from the transport stream and the reproduction of the contents data is regulated in accordance with the test listening time and the number of test listening times included in the extracted program information. Consequently the music piece data can be test listened before purchasing it.

The twenty fifth invention is medium for allowing receiving equipment for receiving a transport stream obtained by multiplexing downloadable contents data together with program information onto a main broadcast signal to execute a program characterized by comprising 

an extracting step of extracting the program information of the contents data separated in the separating step from the transport stream 

a regulating step of regulating a reproducing process of the reproducing means in accordance with the test listening time and the number of test listening times included in the program information extracted in the extracting step. By doing in this manner the contents data and the program information is extracted from the transport stream and the reproduction of the contents data is regulated in accordance with the test listening time and the number of test listening times included in the extracted program information. Consequently the music piece data can be test listened before purchasing it.

The electric wave transmitted from the antenna is relayed by a communication satellite received by an antenna and supplied to an IRD . The IRD QPSK demodulates the electric wave received by the antenna performs necessary processes such as error correction extracts a TS packet of a channel selected by the user and descrambles the data. The IRD MPEG decodes the main broadcast signal included in the extracted TS packet outputs an obtained video signal to a monitor and outputs the sound signal to a speaker .

The IRD extracts the TS packet including the music piece data ATRAC data for downloading and supplies the TS packet to an MD deck connected to the IRD via an IEEE1394 bus . Further the IRD MPEG decodes the music piece data MPEG audio data for downloading and outputs resultant data to the speaker or an MD deck connected to a sound output terminal.

The IRD records a download history of music piece data into a built in IC card and periodically transmits the download history information to the transmitting equipment via a public telephone network . The download history information transmitted to the transmitting equipment is used as information for charging the user of the IRD .

The MD deck records the music piece data ATRAC data supplied from the IRD via the IEEE1394 bus onto an MD and reproduces the data. The MD deck encodes the music piece data audio data obtained by decoding the MPEG audio data supplied from the IRD in accordance with the ATRAC system records the encoded data onto an MD and reproduces the data.

Since the music piece data for downloading includes ATRAC data which will be described hereinlater which does not match the TS in the MPEG2 system some contrivance is necessary at the time of multiplexing the details will be described hereinlater .

The additional information tables PSI are a PAT Program Association Table a PMT Program Map Table an SIT Selection Information Table and the like. By sequentially referring to the tables the packet ID of the TS packet including the desired data can be known. The details are described in for example ETS 300468 Digital Video Broadcasting DVB Specification for Service Information SI in DVB system.

The music piece data for downloading will now be described with reference to . As shown in for example music piece data for downloading to be multiplexed on the main broadcast signal of a program A is data on a plurality of musical pieces A B and C related to the program A and has two kinds of data for each musical piece MPEG audio data compression coded by the MPEG2 system and ATRAC data compression coded by the ATRAC system. The MPEG audio data and the ATRAC data of each music piece is repeatedly transmitted during the broadcasting time of the program A.

Time required to transmit MPEG audio data once is equal to time play time to reproduce the MPEG audio data. Time required to transmit ATRAC data once is equal to a quarter of time required to reproduce the ATRAC data.

For example when broadcasting time of the program A is one hour and the play time of the music pieceA is eight minutes the time to transmit MPEG audio data music pieceA.mpg of the music pieceA once is also eight minutes. The MPEG audio data on the music pieceA is repeatedly transmitted seven times 60 8 at the maximum during the broadcasting time of the program A. On the other hand the time required to transmit the ATRAC data on the music pieceA once is 2 8 4 minutes and the ATRAC data on the music pieceA is repeatedly transmitted 30 60 2 times at the maximum. When play time of the music pieceB is nine minutes time required to transmit MPEG audio data on the music pieceB music pieceB.mpg is also nine minutes and MPEG audio data on the music pieceB is repeatedly transmitted six 60 9 times at the maximum during the broadcasting time of the program A. On the other hand time required to transmit the ATRAC data on the music pieceB once is 2.25 9 4 minutes. During the broadcasting time of the program A the ATRAC data on the music pieceB is repeatedly transmitted 26 60 2.25 times at the maximum.

Referring to again the scrambler scrambles the TS supplied from the multiplexer by using a scramble key Ks supplied from the related information transmitting equipment and outputs the resultant to the post stage. A program control system generates a predetermined control signal to control the encoder . The program control system outputs information such as a program ID a channel ID and the like on the program corresponding to the main broadcast signal to be compression coded by the encoder to the related information transmitting equipment . The scramble control system supplies a contract key Kw to the related information transmitting equipment generates the individual information EMM including the contract key encrypted by using an individual key peculiar to the IRD and outputs the individual information EMM to the multiplexer .

The individual information EMM to be generated has items such as card ID contract key number Kw no contract key Kw contract channel ID service id series id contract number ID event id contract type authorize type program purchase upper limit Over view SMS call generation date polling date and SMS call generation amount upkink fee . The details of the items will be described hereinlater as appropriate.

The related information transmitting equipment supplies a scramble key to the scrambler . The related information transmitting equipment also generates program information ECM including the scramble key encoded by using the contract key supplied from the scramble control system and outputs the program information ECM to the multiplexer .

The program information ECM to be generated has items such as the contract key number Kw no encoded scramble key Ks Odd Ks Even channel ID service id series id event id number ID event id pay per view fee PPV fee preview viewing time the limit number of previewing viewing times current time and purchase limit time. The details of the items will be described hereinlater as appropriate.

An audio visual information collecting and processing system processes audio visual history information and the like supplied from the IRD via the public telephone line and outputs processed information as contract information to the scramble control system .

The viewing time and the limit number of viewing times of each of the music piece data included in the program information ECM will now be described. In the embodiment each of the music piece data can be viewed within the range described as the viewing time and the limit number of viewing times included in the program information ECM. As the viewing time set for the music piece data time shorter than the whole play time of the music piece and long enough to select the music piece is set. The limit number of viewing times is set to a value larger than one so that a plurality of music piece data can be repeatedly compared with each other. The viewing time and the limit number of viewing times of music piece data can be set so as to vary according to music piece data.

The purchase limit time of each music piece data included in the program information ECM will now be described with reference to . As described above the music piece data for downloading MPEG audio data and ATRAC data of each music piece is repeatedly transmitted during the broadcasting time of the program. In the example shown in during the broadcasting time of the program A the music piece data for downloading of the music pieceA is repeatedly transmitted 15 times the music piece data for downloading of the music pieceB is repeatedly transmitted 13 times and the music piece data for downloading of the music pieceC is repeatedly transmitted 11 times.

In the case where for example the viewer instructs the IRD to purchase the music pieceC at timing to during the sixth transmission of the music piece data the music piece data to be transmitted for the seventh time immediately after the instruction is usually downloaded. When the downloading of the music piece data transmitted for the seventh time fails for some reason downloading is re executed with respect to the music piece data to be transmitted for the eighth time. The final transmission time of the music piece data on each of the musical pieces is used for re execution. Timing at which downloading of the music piece data transmitted immediately preceding to the final time is set as purchase limit time by using elapsed time since the program start time. Specifically as shown in the purchase limit time of the musical pieces A B and C are set at timings t t and t respectively. By setting the purchase limit time as described above occurrence of a situation such that downloading cannot be performed in spite of an instruction of purchase can be suppressed.

A process of multiplexing the ATRAC data into the TS in the MPEG2 system will now be described. The TS packet as a transmission unit of a TS in the MPEG2 system is set to have a fixed length of 188 bytes. On the other hand a sound group as a transmission unit of the ATRAC data has 424 bytes. When the ATRAC data is used as it is as a TS in the MPEG2 system the match is poor.

In the embodiment as shown in ATRAC data of 159 bytes is arranged in a TS packet and a PES Packetized Elementary Stream packet is constructed by eight TS packets TSP to TSP. One PES packet therefore includes ATRAC data of 1272 159 8 bytes. Since the ATRAC data of 1272 bytes corresponds to as shown in three sound groups as transmission units of the ATRAC data three sound groups can be transmitted by one PES packet. When an integer number of sound groups are transmitted by one PES packet the match between the ATRAC data and the TS in the MPEG2 system is good.

In the TS packet header sequentially from the head one sync byte a TS error indicator in which a flag indicative of presence absence of an error in the TS packet is written a payload unit start indicator in which a flag indicating that a new PES packet starts from the payload of the TS packet is written and TS priority indicative of the degree of importance of the TS packet are arranged. Subsequently stream identification information PID of 13 bits indicative of the attribute of an individual stream of the TS packet TS scrambling control indicative of the presence absence and kind of scrambling on the payload of the packet adaptation field control indicative of the presence absence of an adaptation field and continuity counter indicative of a serial number given to a packet having the same PID are arranged.

In the TS packet header sequentially from the head packet start code prefix of a fixed value of three bytes stream ID of one byte for identifying the stream and PES packet length of two bytes indicative of the length of the PES packet are arranged. Subsequently fixed pattern 10 of two bits PES scrambling control of two bits PES priority of one bit data alignment indicator of one bit copy right of one bit discrimination between original and copy of one bit PTS and DTS flags of two bits ESCR flag of one bit ES rate flag of one bit DMS trick mode flag of one bit additional copy information flag of one bit CRC flag of PES of one bit and PES extension flag of one bit are arranged.

Further PES header data length of one byte fixed pattern 1101 of four bits time stamp PTS to PTS of three bits one market bit time stamp PTS to PTS of 15 bits one market bit time stamp PTS to PTS of 15 bits and one market bit are arranged.

In the data header sequentially from its head data type of one byte data transmission type of six bits and tag of two bits are arranged.

The TS packet shown in is the first one of eight TS packets constructing the PES packet. In each of the second to eighth TS packets among the eight TS packets in place of the PES packet header and the data header existing in the first TS packet as shown in stuffing data is disposed.

In the data body in which the ATRAC data is arranged as shown in sequentially from the head the 21st byte of the TS packet FDF field length of four bits indicative of length of an FDF Field Dependent Field and audio data types and each of four bits are arranged. Audio data type is to define the audio type for example ATRAC . Audio data type is to define the classification for example ATRAC or ATRAC in the data type . Subsequently copyright original copy flag corresponding to CGMS Copy Generation Management System discrimination between stereo and monophonic emphasis information data start indicator data end indicator and PES data counter of three bits are arranged.

The data start indicator is a flag indicating that the TS packet is the head of the music piece data. In the data start indicator of the TS packet as the head of the music piece data 1 is written. The data end indicator is a flag indicating that the TS packet is at the end of the music piece data. In the data end indicator of the TS packet as the end of the music piece data 1 is written. The PES data counter is to indicate the position of the TS packet among the eight TS packets constructing the PES packet.

Further subsequently identification of copyright mode of one bit identification of EMI Encryption Mode Information of one bit one reserved bit present PES number of three bytes reserved two bytes and ATRAC data checksum of one byte are arranged. After that the ATRAC data is placed.

The present PES number indicates the PES packet having the TS packet among a plurality of PES packets constructing the musical piece. Consequently by detecting the present PES numbers and the PES data counters of the TS packets sequentially transmitted continuity of the TSs on the TS packet unit basis can be checked.

In the 29th byte in the TS packet the ATRAC data checksum is placed. The relation between the ATRAC data checksum and the ATRAC data body in the 30th and subsequent bytes will be described with reference to . As shown in when the values of the bits of the ATRAC data checksum are CS to CS and the values of the bits of the ATRAC data body from the 30th byte to the 188th byte are AT to AT the values of CS to CS are set so that the following is obtained.

As described above by providing the checksum for the ATRAC data body on the reception side of the TS packet whether there is an error in the ATRAC data body or not can be determined.

The descrambler descrambles the scrambled TS supplied from the front end unit by using an individual key and the like supplied from the IC card into a TS packet including the main broadcast signals MPEG video data and MPEG audio data the MPEG audio data for downloading the ATRAC data for downloading the MHEG script for GUI and the like which are multiplexed on the TS. Further the descrambler supplies the derived TS packet of the MPEG video data in the main broadcast signal to an MPEG video decoder supplies the TS packet of the MPEG audio data in the main broadcast signal and the TS packet of the MPEG audio data for downloading to an MPEG audio decoder supplies the TS packet of the ATRAC data for downloading to an IEEE1394 interface I F and supplies the TS packet of the MHEG script for GUI to a control unit .

The MPEG video decoder decodes the MPEG video data supplied from the descrambler and outputs derived video data to a display control unit . The display control unit for example superimposes the video data supplied from the MPEG video decoder on a main program display area of a GUI screen inputted from the control unit and displays the composite data on the monitor .

The MPEG video decoder decodes the MPEG audio data in the main broadcast signal or the MPEG audio data for downloading supplied from the descrambler and outputs the derived audio data to a sound control unit . The sound control unit performs an appropriate process such as fade in and fade out of the audio data supplied from the MPEG audio decoder on the basis of the control from the control unit and outputs resultant data to the speaker or the MD deck .

The IEEE1394 interface eliminates a PMT corresponding to a program other than the program from which the music piece can be purchased from PAT in the additional information table PSI multiplexed on the TS packet in which the ATRAC data inputted from the descrambler is placed eliminates PIDs corresponding to the main broadcast signal MPEG audio data for downloading and sound additional information from the PMT corresponding to the program newly adds SIT indicative of a partial TS and outputs an obtained partial TS to the MD deck via the IEEE1394 bus .

An input unit receives a station selecting operation of the user and an operation on the GUI screen and outputs the operation information to the control unit . The control unit controls each of the units in the IRD on the basis of the operation information from the input unit and predetermined information inputted from the descrambler . For example the control unit processes the MHEG script for GUI inputted from the descrambler and outputs the image data to the display control unit .

In the IC card information such as an individual key for descrambling the TS packet is stored. In response to a request from the descrambler the stored information is supplied to the descrambler . History information on watched pay per view programs and downloaded music piece data is recorded in the IC card . A modem outputs the history information recorded on the IC card to the transmitting equipment via the public telephone network every predetermined period.

A test listening process of the IRD will now be described with reference to the flowchart of . The test listening process is executed after the user viewer of the IRD performs an operation of displaying a GUI for music piece purchase during test listening a broadcast program from which the music piece data can be purchased downloaded and a GUI as shown in is displayed on the monitor .

In step S the descrambler extracts the program information ECM multiplexed on the TS and outputs viewing time the limit number of test listen times and purchase limit time of each of music piece data written in the program information ECM to the control unit . In step S the control unit compares the number of test listen times with the limit number of test listen times for each musical piece thereby determining whether a music piece which can be test listened exists or not. When it is determined that a music piece which can be test listened exists the program advances to step S.

In step S the control unit allows a music piece list to be displayed on the screen of GUI as shown in . Among the titles of the musical pieces described in the music piece list the display method of the titles of musical pieces which can be test listened and purchased and that of the titles of musical pieces which cannot be test listened the number of test listening times has reached the limit number of test listening times but can be purchased are distinguished from each other. For example characters of the titles of the musical pieces which can be test listened and purchased are displayed dark and characters of the titles of the musical pieces which cannot be test listened but can be purchased are displayed light.

The user watching the music piece list selects one of the musical pieces which are displayed in the music piece list and can be test listened and depresses a test listen button in step S selection information on the music piece to be test listened is supplied from the input unit to the control unit .

In step S the descrambler outputs the MPEG audio data of the music piece selected in step S to the MPEG audio decoder on the basis of the control from the control unit . The MPEG audio decoder decodes the MPEG audio data from the descrambler only for length of test listen time written in the program information ECM on the basis of the control from the control unit and outputs the obtained audio data to the sound control unit . In step S the sound control unit makes the volume of the head portion of the audio data supplied from the MPEG audio decoder fade in makes the ending portion fade out and outputs the resultant to the speaker .

In place of executing the fade in and fade out sound indicative of test listen may be inserted at the head and ending portions of the audio data. The sound quality of the audio data may be changed by using a filter or the like as long as the purpose of the test listen can be achieved.

In step S the control unit increments the number of test listening times of the music piece selected in step S only by one.

After that in step S until it is determined that a music piece which can be test listened does not exist subsequent processes are repeated. When it is determined that no music piece which can be test listened exists the test listening process is finished.

As described above by enabling each of the music piece data to be test listened it is advantageous for the audiences and also an effect of prompting purchase is produced. By limiting the number of test listening times of each of the music piece data and executing fade in fade out and the like on the audio data to be reproduced it is suppressed that the music piece data is copied by connecting the test listened audio data.

The purchasing process of the IRD will now be described with reference to the flowchart of . The purchasing process is executed after the user performs an operation of displaying GUI for music piece purchase to the IRD during test listening of the program from which the music piece data can be purchased and the GUI as shown in is displayed on the monitor . The music piece data to be purchased is either the MPEG audio data or ATRAC data for downloading. The MPEG audio data or ATRAC data is selected by a predetermined operation performed by the user or is selected by the IRD by detecting a sound output terminal of the IRD or a recording equipment MD deck or the like connected to the IEEE1394 interface .

In step S the program information ECM included in the TS is extracted and the viewing time the limit number of test listening times and purchase limit time of each of music piece data written in the program information ECM are outputted from the descrambler to the control unit . In step S the control unit compares the current time with the purchase limit time for each musical piece thereby determining whether a purchasable music piece exists or not. When it is determined that a purchasable music piece exists the program advances to step S.

In step S the control unit allows the music piece list to be displayed on the screen of the GUI as shown in . In the music piece list the titles of musical pieces which can be test listened and purchased and the titles of musical pieces which cannot be test listened the number of test listening times has reached the limit number of test listening times but can be purchased are distinguished and for example the titles of musical pieces which can be test listened and purchased are displayed dark and the titles of musical pieces which cannot be test listened but can be purchased are displayed light.

In step S after the user sees the music piece list and selects some of the purchasable musical pieces which are displayed in the music piece list the control unit determines whether a purchase button is depressed or not. Until depression of the purchase button is determined the program returns to step S and subsequent processes are repeated. During the repetition the display of the titles of musical pieces of which purchase limit time has elapsed is changed. When depression of the purchase button is determined the program advances to step S.

In step S the control unit determines whether the purchase of a plurality of musical pieces has been instructed by the user in step S or not. When it is determined that the purchase of the plurality of musical pieces has been instructed the program advances to step S. In step S the control unit determines the downloading order of the plurality of musical pieces to be purchased. The process of determining the downloading order will be described with reference to the flowchart of .

In step S the descrambler extracts sound additional information at the present time corresponding to play time and play elapsed time of a musical piece and transmission time and transmission elapsed time of the MPEG audio data for downloading corresponding to the plurality of music piece data instructed to be purchased by the control of the control unit from the TS and outputs the sound additional information to the control unit .

In step S the control unit refers to the sound additional information from the descrambler and optimizes the downloading order of the plurality of music piece data. For example in the case of purchasing three musical pieces A B and C shown in at time t where the purchase instruction is given the music piece data of which timing of transmission start music pieceB in this case is the earliest in the three music piece data is set as music piece data to be downloaded first. At transmission end time of the first music piece data the music piece data having the earlier transmission start timing music pieceA in this case in the music piece data on the remaining two musical pieces is set as music piece data to be downloaded second. The remaining piece music pieceC in this case is set as the music piece data to be downloaded third. In the case of optimizing the downloading order as described above the end time is t. On the contrary in the case of downloading the musical pieces in accordance with the order of A B and C without optimizing the downloading order the end time is t which is behind t by one musical piece.

Naturally in the case of downloading music piece data on three or more musical pieces as well the downloading order is optimized in a similar manner.

In step S the control unit determines whether or not there is music piece data which cannot be downloaded due to the purchase limit time in the downloading order determined in step S. When it is determined that the music piece data which cannot be downloaded exists the program advances to step S.

In step S the control unit allows the message to the effect that the music piece data which cannot be downloaded exists and the title of the music piece to be displayed in an information display area in the GUI. By the display the user can know the music piece data which cannot be downloaded and can select another music piece data to be purchased as necessary.

When it is determined at step S that no music piece data which cannot be downloaded exists the program skips step S.

After executing the process of determining the downloading order as described above the program returns to step S in . In step S the descrambler extracts music piece data in accordance with the order determined in step S by the control of the control unit and outputs the extracted music piece data to the post stage. In the case of downloading MPEG audio data for downloading the MPEG audio data is MPEG decoded by the MPEG audio decoder and after that decoded data is supplied to for example the MD deck via the sound control unit and the sound output terminal and is recorded. In the case where the ATRAC data is downloaded the ATRAC data is supplied to the MD deck via the IEEE1394 interface and is recorded.

By executing the purchasing process including the download order determining process as described above the music piece data of a larger amount can be efficiently downloaded.

The following manner is also possible. In step S when the control unit detects the level of a received wave and the level is equal to or lower than a predetermined value it is determined that no purchasable music piece exists.

It is also possible to store the order when a plurality of musical pieces are selected in step S skip the downloading order determining process in step S and perform downloading in accordance with the order at the time of the selection.

Even in the case where the music piece data is downloaded in the order which is not intended by the user each of the MD decks and can reproduce the musical pieces in arbitrary order as a provided standardized function.

In the embodiment however the two kinds of MPEG audio data and ATRAC data exist as music piece data for downloading as described above. At the time of test listening the musical piece the MPEG audio data in the two kinds of data is reproduced. Therefore the MPEG audio data can be test listened while downloading the ATRAC data. The parallel process will be described with reference to the flowchart of .

The parallel process is executed simultaneously with the downloading process in step S in . When the control unit determines whether the music piece data being downloaded is ATRAC data or not and determines that the music piece data being downloaded is ATRAC data in step S the program advances to step S. In step S the control unit executes the above described test listening process . The same music piece as that of the ATRAC data being downloaded and the music piece which has already been downloaded cannot be test listened.

When it is determined in step S that the music piece data being downloaded is not the ATRAC data that the music piece data being downloaded is MPEG audio data step S is skipped.

Alternately in step S MPEG audio data on a music piece different from the ATRAC data being downloaded can be purchased.

By executing such a parallel process a music piece can be test listened during loading another musical piece and music piece data on two different musical pieces ATRAC data on a music piece and MPEG audio data on another musical piece can be simultaneously downloaded.

An example of the configuration of the MD deck connected to the IRD via the IEEE1394 bus will now be described with reference to . The MD deck is constructed in such a manner that a control unit for controlling each of the units in the MD deck an IEEE1394 interface for receiving the partial TS including the ATRAC data from the IRD a recording reproducing unit for controlling recording reproducing of the ATRAC data to from an MD and an ATRAC encoder decoder for decoding the ATRAC data from the recording reproducing unit and outputting the decoded data to a DAC or encoding digital audio data from the DAC and outputting the encoded data to the recording reproducing unit are connected to each other via a system bus .

To the recording reproducing unit a buffer for temporarily storing ATRAC data to be recorded on an MD a magnetic head an optical pickup and a spindle motor are connected. At the time of recording the optical pickup emits a laser beam onto the MD to increase the temperature of the spot irradiated with the laser beam to a predetermined value. The magnetic head records a magnetic signal corresponding to the ATRAC data supplied from the recording reproducing unit to the spot on the MD at which the temperature is increased to the predetermined value by the laser beam from the optical pickup . The optical pickup irradiates the MD with a laser beam at the time of reproduction receives reflection light of the laser beam converts the reflection light to an electric signal and outputs obtained ATRAC data to the recording reproducing unit . The spindle motor rotates the MD on the basis of the control from the recording reproducing unit .

The DAC for conversion between digital and analog signals is connected to the ATRAC encoder decoder .

The operation will now be described. At the time of recording a PES packet including the ATRAC data is detected on the basis of the PSI packet multiplexed on the partial TS from the IRD and further only the ATRAC data is extracted from the PES packet. The extracted ATRAC data is supplied to the recording reproducing unit via the system bus . The recording reproducing unit controls the optical head optical pickup and spindle motor to record the ATRAC data supplied from the IEEE1394 interface onto the MD .

At the time of reproduction the recording reproducing unit controls the optical pickup and the spindle motor to read the ATRAC data from the MD and supplies the ATRAC data to the ATRAC encoder decoder . In the ATRAC encoder decoder the ATRAC data supplied from the recording reproducing unit is decoded and resultant data is outputted to for example a speaker via the DAC .

The PID detecting unit converts the partial TS supplied from the IRD into an MPEG stream extracts only the TS packet whose PID of 13 bits written in the packet header is equal to a predetermined PID PID indicative of the TS packet including the ATRAC data designated by the control unit from the TS packets and outputs the extracted TS packet to the start end bit detecting unit and to ATRAC data extracting unit at the post stage.

The start end bit detecting unit detects a data start indicator in the 23rd byte in the TS packet shown in in the TS packet sequentially supplied from the PID detecting unit . When 1 is written in the data start indicator the detection information is outputted to the control unit . The detection information is supplied to the control unit via the control unit and is used as a trigger to start recording the ATRAC data onto the MD . The start end bit detecting unit detects a data end indicator the bit next to the LSB side of the data start indicator in the TS packet. When 1 is written in the data end indicator the detection information is outputted to the control unit . The detection information is supplied to the control unit via the control unit and is used as a trigger to finish the recording of the ATRAC data onto the MD .

The packet counter detecting unit ascertains continuity of the PES data counter three bits next to the LSB side of the data end indicator of the TS packet sequentially supplied from the PID detecting unit and a present PES number from the 24th byte to the 26th byte in the TS packet shown in .

Meanwhile the PES data counter is a cyclic counter of the values from 0 to 7. The present PES number is incremented by one each time the value of the PES data counter is restarted from 0 after 7. That is in the PES data counter of the first TS packet among eight TS packets constructing a PES packet of a continuous normal TS TS where no packet dropout occurs 1 is written. In the PES data counters of the subsequent TS packets values incremented one by one are sequentially written. In the PES data counter of the eighth TS packet in the PES packet 7 is written. The present PES number of the eight TS packets is commonly used. In the PES data counters of eight TS packets subsequent to the above TS packets values from 0 to 7 incremented one by one are written again. Each of the present PES numbers is obtained by adding 1 to the value written in the PES number of the preceding eight TS packets. The value of the present PES number of the head TS packet of the ATRAC data having the data start indicator in which 1 is written is zero.

When the value of the PES data counter of a TS packet inputted and the value of the present PES number are read and stored and discontinuity of the value of the PES data counter of a TS packet supplied next and the value of the present PES number is detected the packet counter detecting unit outputs the information to the control unit .

The error detecting unit detects the TS error indicator in the second byte in the TS packet sequentially inputted from the PID detecting unit and determines whether 1 is written or not in the TS error indicator. 1 is written in the TS error indicator when an error correcting process cannot be completed in the front end unit in the IRD . When 1 is written in the TS error indicator therefore it can be considered that at least one error is included in the TS packet. When it is determined that 1 is written in the TS error indicator the error detecting unit outputs the information to the control unit . When the ATRAC data described in the 30th and subsequent bytes is checked by using the ATRAC data checksum in the 29th byte in the TS packet and an error is detected the error detecting unit outputs the detection information to the control unit .

The format detecting unit detects the data type in the 19th byte in the TS packet shown in of a TS packet subsequently inputted from the PID detecting unit data transmission type in the 20th byte in the TS packet shown in FDF field length in the 21st byte in the TS packet shown in and audio data types and in the 21st and 22nd bytes in the TS packet shown in to check whether or not each of the values written in the bytes is equal to a predetermined value indicative of a packet including ATRAC data. When it is determined that each of the values is not equal to the predetermined value the format detecting unit outputs the detection information to the control unit .

The copyright information detecting unit detects the copyright original or copy copyright mode and EMI mode in the 22nd and 23rd bytes in the TS packet shown in of the TS packet sequentially inputted from the PID detecting unit and checks whether or not each of the values is equal to a predetermined value indicating that the ATRAC data is permitted to be copied. When it is determined that each of the values is not equal to the predetermined value the copyright information detecting unit outputs the detection information to the control unit .

The ATRAC data extracting unit extracts the ATRAC data placed in the 30th bytes to 188th bytes in the TS packet inputted from the PID detecting unit and outputs the detected data to the post stage.

The ATRAC data extracting process of the IEEE1394 interface will now be described with reference to the flowchart of . The ATRAC data extracting process is started upon receipt of the partial TS from the IRD .

In step S the PID detecting unit converts the partial TS inputted from the IRD into an MPEG stream after that extracts only a TS packet having the PID of 13 bits written in the packet header equal to the PID indicative of the TS packet including the ATRAC data and outputs the extracted TS packet to the start end bit detecting unit to the ATRAC data extracting unit at the post stage.

In step S the copyright information detecting unit detects the copyright original or copy copyright mode and EMI mode of the TS packet sequentially inputted from the PID detecting unit and checks whether or not each of the values is equal to a predetermined value indicating that the ATRAC data placed in the TS packet is permitted to be copied. When it is determined that each of the values is equal to the predetermined value and indicates that the ATRAC data is permitted to be copied the program advances to step S.

In step S the start end bit detecting unit monitors the data start indicator in the TS packet inputted from the PID detecting unit waits until 1 is detected and when 1 is detected outputs the detection information to the control unit . In response to the detection information the control unit outputs a predetermined signal to the ATRAC data extracting unit and the control unit .

In step S in response to the signal from the control unit the ATRAC data extracting extracts the ATRAC data placed in the 30th and subsequent bytes in the TS packet supplied from the PID detecting unit and outputs the extracted ATRAC data to the recording reproducing unit at the post stage. The control unit instructs each of the units in the MD deck to start recording of the ATRAC data onto the MD in response to the signal from the control unit thereby starting the recording of the ATRAC data onto the MD .

In step S the packet counter detecting unit detects the PES data counter and the present PES number in the TS packet supplied from the PID detecting unit to check the continuity of the values written in the PES data counter and the present PES number. When it is determined that the values of each of the PES data counter and the present PES number in the TS packet have continuity the program advances to step S.

In step S the error detecting unit detects a TS error indicator in the TS packet supplied from the PID detecting unit and determines whether. 1 is written in the TS error indicator or not. Further the error detecting unit determines whether or not an error exists in the ATRAC data written in the 30th and subsequent bytes by using the ATRAC data checksum in the TS packet. When 1 is not written in the TS error indicator and it is determined that no error exists in the ATRAC data the program advances to step S.

In step S the format detecting unit detects the data type data transmission type FDF field length and audio data types and in the TS packet supplied from the PID detecting unit and determines whether or not each of those values is equal to a predetermined value indicative of a packet including the ATRAC data. When it is determined that each of the written values is equal to the predetermined value indicative of a packet including the ATRAC data the program advances to step S.

In step S the start end bit detecting unit monitors the data end indicator in the TS packet supplied from the PID detecting unit and determines whether 1 is written in the data end indicator or not. When it is determined that 1 is not written the program returns to step S and the subsequent processes are repeated. On the contrary when it is determined that 1 is written in the data end indicator the start end bit detecting unit outputs the detection information to the control unit . In response to the detection information the control unit outputs a predetermined signal to the ATRAC data extracting unit and the control unit . In response to the signal from the control unit the ATRAC data extracting unit finishes extracting the ATRAC data from the TS packet supplied from the PID detecting unit . In response to the signal from the control unit the control unit instructs each of the units in the MD deck to finish the recording of the ATRAC data onto the MD thereby finishing the recording of the ATRAC data onto the MD .

In step S when the value written in each of the copyright original or copy copyright mode and EMI mode of the TS packet sequentially inputted from the PID detecting unit is not equal to a predetermined value indicating that the ATRAC data placed in the TS packet is permitted to be copied and it is determined that the ATRAC data is not permitted to be copied the result of the determination is outputted from the copyright information detecting unit to the control unit and the program advances to step S.

In step S when it is determined that the values of each of the PES data counter and the present PES number in the TS packet supplied from the PID detecting unit do not have continuity the determination result is outputted from the packet counter detecting unit to the control unit and the program advances to step S.

In step S when it is determined that 1 is written in the TS error indicator in the TS packet supplied from the PID detecting unit or when it is determined that an error exists in the ATRAC data the detection result is outputted from the error detecting unit to the control unit and the program advances to step S.

In step S when it is determined that each of values written in the data type data transmission type FDF field length and audio data types and in the TS packet supplied from the PID detecting unit is not equal to a predetermined value indicative of a packet including the ATRAC data the program advances to step S.

In step S in response to the determination result from the packet counter detecting unit to the copyright information detecting unit the control unit makes the PID detecting unit stop extracting the TS packet and outputs the information to the control unit . In response to the information the control unit instructs each of the units in the MD deck to stop the recording of the ATRAC data onto the MD and notifies the IRD of the stop of recording.

When it is considered that occurrence of an error on the transmission path of the TS is little that is the quality of the transmission path is good the error detection using the checksum in step S is not executed but only the TS error indicator may be checked.

As described above the IEEE1394 interface in the MD extracts only the ATRAC data placed in the TS packet. At this time abnormality data dropout occurrence of an error and the like which occurs in the TS packet is monitored. When abnormality is detected the extraction of the ATRAC data is stopped. Thus a failure in downloading such that abnormal ATRAC data is recorded can be suppressed.

In the EMD system as the embodiment the invention is applied to digital satellite broadcasting. The invention can be also applied to digital cable television broadcasting and digital ground broadcasting.

The invention is not limited to the audio data distributing service but can be applied to for example service of distributing a program processed by a computer or a television game machine.

Referring to a medium used for installing a program of executing the series of processes to the IRD or MD deck to set a state in which the program can be executed by the IRD or MD deck will now be described.

As shown in the program conformed to the IRD can be provided to the user in a state where it is pre installed on a hard disk or a semiconductor memory as a recording medium provided in an IRD corresponding to the IRD in .

Alternately as shown in the program can be temporarily or permanently stored in a recording medium such as a floppy disk a CD ROM Compact Disc Read Only Memory an MO Magneto Optical disk a DVD Digital Versatile Disc a magnetic disk or a semiconductor memory and can be provided as package software.

Further as shown in the program can be transferred by radio from a download site to an IRD via a satellite or transferred by a wire or by radio to the IRD via a network such as a local area network or the Internet. The program can be stored into a built in hard disk or the like in the IRD .

Since a program conformed to the MD deck is similar to that conformed to the IRD its description is omitted here.

In the specification the steps of writing a program provided by the medium include not only processes time sequentially performed according to the written order but also processes which are not always processed time sequentially but are executed in parallel or individually.

Although the example in which data in the MHEG format is transmitted as data for GUI or the like distributed from a broadcast station side has been described in the foregoing embodiment the invention can be also applied to a case where data is transmitted as data in another format. For example the invention can be also applied to a case where data in the HTML Hyper Text Make up Language format or data in the XML extensive Markup Language format is transmitted.

In the specification the system denotes the whole equipment constructed by a plurality of equipments.

