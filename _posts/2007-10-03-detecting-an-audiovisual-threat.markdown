---

title: Detecting an audio/visual threat
abstract: A method, system, computer program product and/or computer readable medium of instructions for detecting if a processing system has been compromised with audio/visual threat. The method comprises steps of intercepting one or more requests to perform an activity associated with an audio and/or visual communication device of the processing system; and performing a behavioural analysis of the processing system to determine if the processing system exhibits behavioural characteristics indicative of the processing system having been compromised with an audio/visual threat.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=07941852&OS=07941852&RS=07941852
owner: Symantec Corporation
number: 07941852
owner_city: Mountain View
owner_country: US
publication_date: 20071003
---
This application claims the benefit of priority from U.S. Provisional Patent Application No. 60 849 365 filed Oct. 4 2006 and is incorporated by referenced.

The present invention generally relates to a method system computer readable medium of instructions and or computer program product for detecting and optionally restricting a threat which transmits audio and or visual data indicative of user activity at a processing system.

A portion of the disclosure of this patent document contains material that is subject to copyright protection. The copyright owner has no objection to the facsimile reproduction by anyone of the patent disclosure as it appears in a Patent Office patent files or records but otherwise reserves all copyrights whatsoever.

As used herein a threat comprises malicious software also known as malware or pestware which comprises software that is included or inserted in a part of a processing system for a harmful purpose. The term threat should be read to comprise possible potential and actual threats. Types of malware can comprise but are not limited to malicious libraries viruses worms Trojans adware malicious active content and denial of service attacks. In the case of invasion of privacy for the purposes of fraud or theft of identity malicious software that passively observes the use of a computer is known as spyware .

A hook also known as a hook procedure or hook function as used herein generally refers to a callback function provided by a software application that receives certain data before the normal or intended recipient of the data. A hook function can thus examine or modify certain data before passing on the data. Therefore a hook function allows a software application to examine data before the data is passed to the intended recipient.

An API Application Programming Interface hook also known as an API interception as used herein as a type of hook refers to a callback function provided by an application that replaces functionality provided by an operating system s API. An API generally refers to an interface that is defined in terms of a set of functions and procedures and enables a program to gain access to facilities within an application. An API hook can be inserted between an API call and an API procedure to examine or modify function parameters before passing parameters on to an actual or intended function. An API hook may also choose not to pass on certain types of requests to an actual or intended function.

A process as used herein is at least one of a running software program or other computing operation or a part of a running software program or other computing operation that performs a task.

A hook chain as used herein is a list of pointers to special application defined callback functions called hook procedures. When a message occurs that is associated with a particular type of hook the operating system passes the message to each hook procedure referenced in the hook chain one after the other. The action of a hook procedure can depend on the type of hook involved. For example the hook procedures for some types of hooks can only monitor messages others can modify messages or stop their progress through the chain restricting them from reaching the next hook procedure or a destination window.

In a networked information or data communications system a user has access to one or more terminals which are capable of requesting and or receiving information or data from local or remote information sources. In such a communications system a terminal may be a type of processing system computer or computerised device personal computer PC mobile cellular or satellite telephone mobile data terminal portable computer Personal Digital Assistant PDA pager thin client or any other similar type of digital electronic device. The capability of such a terminal to request and or receive information or data can be provided by software hardware and or firmware. A terminal may comprise or be associated with other devices for example a local data storage device such as a hard disk drive or solid state drive.

An information source can comprise a server or any type of terminal that may be associated with one or more storage devices that are able to store information or data for example in one or more databases residing on a storage device. The exchange of information ie. the request and or receipt of information or data between a terminal and an information source or other terminal s is facilitated by a communication means. The communication means can be realised by physical cables for example a metallic cable such as a telephone line semi conducting cables electromagnetic signals for example radio frequency signals or infra red signals optical fibre cables satellite links or any other such medium or combination thereof connected to a network infrastructure.

A system registry is a database used by operating systems for example Windows platforms. The system registry comprises information needed to configure the operating system. The operating system refers to the registry for information ranging from user profiles to which applications are installed on the machine to what hardware is installed and which ports are registered.

An entity can comprise but is not limited to a file an object a class a collection of grouped data a library a variable a process and or a device.

Local communication devices such as video cameras also commonly referred to as webcams and microphones are becoming more commonplace in modern processing systems. For example current laptop computers are provided with in built webcams and microphones.

Due to such devices becoming more popular threats such as malware have recently been configured to utilise local communication devices for exploitation. Herein this form of threat is referred to as an audio visual threat .

In some instances audio visual threats have been configured to spy on an unsuspecting user of a compromised processing system using a webcam or microphone. The visual and or audio data recorded by a webcam can be transferred to a third party wherein the third party may use the visual and or audio data for exploitation such as determining when a user has left their premises so that a robbery can be performed. In some instances the audio visual data has simply been used for voyeuristic activities.

In other instances if the user has unsuspectingly left private information such as details of their credit card within visual range of the webcam the visual data captured by the threat can be analysed by a third party to determine the details of the credit card for financial exploitation.

In other instances the webcam can be controlled by the threat to record typing performed by the user on the keyboard of the processing system in order to determine secret information such as usernames and passwords.

Recently proof of concept computer programs have been developed which can utilise the sound of a user typing on the keyboard recorded by a microphone to determine keystrokes performed by the user within an acceptable accuracy. Again secret information such as usernames and passwords can be determined using the audio data obtained by appropriately configured threat controlling the microphone of the compromised processing system.

Current approaches to detect audio visual threats have involved using signature based detection software. Such software comprises a database of signatures wherein each signature generally represents a file size of the malware a file name associated with the malware a cryptographic hash or checksum value of the malware and pseudocode which represents program flow of the threat.

However signature based approaches are becoming unsuitable as it can take a number of days for a vendor of such software to develop an appropriate signature which can detect and restrict the audio visual threat. During the period of time when audio visual theat is compromising a user s processing system and the time when an appropriate signature is released by the vendor the audio visual threat can exploit audio visual data obtained from the compromised processing system. Furthermore unless a user continually updates signatures for their malware detection software this compromised time period can also be unsatisfactorily extended.

Other approaches to deal with audio visual threats have been to unplug microphones and webcams from the processing system. In some instances placing an object such as a container over the webcam or microphone has also been suggested in order to overcome the compromised time period prior to a signature being released. Not only is this unsightly but it can sometimes be extremely difficult and inconvenient for users of processing systems where the webcam and or the microphone is in built such as a laptop computer.

Therefore there exists a need for a method system computer readable medium of instructions and or a computer program product which can detect an audio visual threat which has compromised a processing system and optionally restrict an audio visual threat performing malicious activity in the processing system which overcomes or at least ameliorates at least one of the above mentioned disadvantages.

The reference in this specification to any prior publication or information derived from it or to any matter which is known is not and should not be taken as an acknowledgment or admission or any form of suggestion that that prior publication or information derived from it or known matter forms part of the common general knowledge in the field of endeavour to which this specification relates.

In one broad form there is provided a method of detecting if a processing system has been compromised with audio visual threat wherein the method comprises 

intercepting one or more requests to perform an activity associated with an audio and or visual communication device of the processing system and

performing a behavioural analysis of the processing system to determine if the processing system exhibits behavioural characteristics indicative of the processing system having been compromised with an audio visual threat.

In another form performing the behavioural analysis comprises applying one or more behavioural rules.

determining if the entity indicative of at least one of audio signal and visual signals being obtained by the audio and or visual communication device 

determining if the entity is being interacted via a graphical user interface currently displayed on the desktop of the processing system 

determining if the entity is recording data indicative of at least one of audio data and visual data 

In another embodiment a requesting entity requests the activity to be performed in relation to a target entity wherein the method comprises 

in response to determining that the activity is suspicious analysing using an analysis module at least one of the activity the requesting entity and the target entity.

In one aspect the filter module filters the activity according to the requesting entity and the target entity to determine if the activity is suspicious or non suspicious.

In another aspect the analysis module comprises a list of activity sequences indicative of an audio visual threat wherein analysing the suspicious activity comprises comparing the suspicious activity and at least one of activities which occurred prior to the suspicious activity and activities which occurred after the suspicious activity to the list of activity sequences wherein in response to a positive comparison the activity is determined to be associated with an audio visual threat.

determining an entity threat value for the entity the entity threat value being indicative of a level of threat that the entity represents to the processing system wherein the entity threat value is determined based on one or more characteristics of the entity and

comparing the entity threat value to an entity threat threshold to identify if the entity is malicious.

In another form each of the one or more characteristics of the entity is associated with a respective characteristic threat value wherein the method comprises calculating the entity threat value using at least some of the characteristic threat values for the one or more characteristics of the entity.

In one embodiment at least one of the one or more characteristics of the entity is associated with a characteristic threat value formula wherein the method comprises calculating using the characteristic threat value formula the characteristic threat value.

In another embodiment at least one characteristic threat value is temporally dependent wherein the method comprises calculating the at least one characteristic threat value for the entity using the characteristic threat value formula and a temporal value.

In one aspect the at least one characteristic is a behaviour associated with the entity wherein the method comprises calculating the at least one characteristic threat value for the entity using the characteristic threat value formula and a frequency of instances the behaviour has been performed.

In another aspect the one or more characteristics comprises at least one of one or more legitimate characteristics indicative of non malicious activity and one or more illegitimate characteristics indicative of malicious activity wherein the method comprises determining the entity threat value using characteristic threat values associated with the one or more legitimate characteristics and the one or more illegitimate characteristics of the entity.

Optionally the step of determining the entity threat value for an entity comprises calculating a difference between the characteristic threat values for the one or more legitimate characteristics of the entity and the characteristic threat values for the one or more illegitimate characteristics of the entity wherein the difference is indicative of the entity threat value.

determining one or more related entities to the activity wherein each related entity has an associated entity threat value and

calculating the entity threat value for the activity using the entity threat value for at least some of the one or more related entities.

determining one or more related entities to the activity wherein each related entity has an associated entity threat value and

calculating a group threat value for the activity and one or more related entities using the entity threat value for at least some of the one or more related entities and the activity.

Optionally the method comprises weighting the entity threat value for at least one related entity according to a relatedness of the at least one related entity relative to the activity.

In another broad form there is provided a system to detect if a processing system has been compromised with audio visual threat wherein the system is configured to 

intercept one or more requests in the processing system to perform an activity associated with an audio and or visual communication device of the processing system and

perform a behavioural analysis of the processing system to determine if the processing system exhibits behavioural characteristics indicative of the processing system having been compromised with an audio visual threat.

In another form the system is configured to apply one or more behavioural rules to perform the behavioural analysis.

if the entity is indicative of at least one of audio signal and visual signals being obtained by the audio and or visual communication device 

if the entity is being interacted via a graphical user interface currently displayed on the desktop of the processing system 

wherein results of the application of the one or more behavioural rules is used to determine whether the processing system having been compromised with an audio visual threat.

In another embodiment a requesting entity requests the activity to be performed in relation to a target entity wherein the system is configured to 

analyse using an analysis module at least one of the activity the requesting entity and the target entity in response to determining that the activity is suspicious.

In one aspect the filter module filters the activity according to the requesting entity and the target entity to determine if the activity is suspicious or non suspicious.

In another aspect the analysis module comprises a list of activity sequences indicative of an audio visual threat wherein the system is configured to analyse the suspicious activity by comparing the suspicious activity and at least one of activities which occurred prior to the suspicious activity and activities which occurred after the suspicious activity to the list of activity sequences wherein in response to a positive comparison the activity is determined to be associated with an audio visual threat.

determine an entity threat value for the entity the entity threat value being indicative of a level of threat that the entity represents to the processing system wherein the entity threat value is determined based on one or more characteristics of the entity and

compare the entity threat value to an entity threat threshold to identify if the entity is malicious.

In another form each of the one or more characteristics of the entity is associated with a respective characteristic threat value wherein the system is configured to calculate the entity threat value using at least some of the characteristic threat values for the one or more characteristics of the entity.

In another broad form there is provided a computer program product comprising a computer readable medium having a computer program recorded therein or thereon the computer program being configured to detect if a processing system has been compromised with audio visual threat wherein the computer program product configures the processing system to 

intercept one or more requests in the processing system to perform an activity associated with an audio and or visual communication device of the processing system and

perform a behavioural analysis of the processing system to determine if the processing system exhibits behavioural characteristics indicative of the processing system having been compromised with an audio visual threat.

The following modes given by way of example only are described in order to provide a more precise understanding of the subject matter of a preferred embodiment or embodiments.

In the figures incorporated to illustrate features of an example embodiment like reference numerals are used to identify like parts throughout the figures.

A particular embodiment of the present invention can be realised using a processing system an example of which is shown in .

In particular the processing system generally comprises at least one processor or processing unit or plurality of processors memory at least one input device and at least one output device coupled together via a bus or group of buses . The at least one input device can take the form of an audio visual communication device such as a webcam or a microphone. In certain embodiments input device and output device could be the same device. An interface can also be provided for coupling the processing system to one or more peripheral devices for example interface could be a PCI card or PC card. At least one storage device which houses at least one database can also be provided. The memory can be any form of memory device for example volatile or non volatile memory solid state storage devices magnetic devices etc. The processor could comprise more than one distinct processing device for example to handle different functions within the processing system . Input device receives input data and can comprise for example a keyboard a pointer device such as a pen like device or a mouse audio receiving device for voice controlled activation such as a microphone data receiver or antenna such as a modem or wireless data adaptor data acquisition card etc. Input data could come from different sources for example keyboard instructions in conjunction with data received via a network. Output device produces or generates output data and can comprise for example a display device or monitor in which case output data is visual a printer in which case output data is printed a port for example a USB port a peripheral component adaptor a data transmitter or antenna such as a modem or wireless network adaptor etc. Output data could be distinct and derived from different output devices for example a visual display on a monitor in conjunction with data transmitted to a network. A user could view data output or an interpretation of the data output on for example a monitor or using a printer. The storage device can be any form of data or information storage means for example volatile or non volatile memory solid state storage devices magnetic devices etc.

In use the processing system can be adapted to allow data or information to be stored in and or retrieved from via wired or wireless communication means the at least one database . The interface may allow wired and or wireless communication between the processing unit and peripheral components that may serve a specialised purpose. The processor receives instructions as input data via input device and can display processed results or other output to a user by utilising output device . More than one input device and or output device can be provided. It should be appreciated that the processing system may be any form of terminal server processing system specialised hardware or the like.

Referring now to there is shown a distributed system which can also be used to implement particular embodiments wherein the distributed system comprises one or more client processing systems in data communication via a network with one or more server processing systems . The one or more client processing systems and the one or more server processing systems are forms of processing system illustrated in . Input data and output data can be communicated to other devices via the network . The transfer of information and or data over the network can be achieved using wired communications means or wireless communications means. The server processing system can facilitate the transfer of data between the network and one or more databases. The server processing system and one or more databases provide an example of an information source.

Referring to there is shown a block diagram illustrating a request to perform an activity . Generally the request is associated with an activity a target entity and a requesting entity . In particular the requesting entity causes the activity to be performed in relation to the target entity .

For example an executable object in a processing system may request to obtain access to an input stream of a communication device such as a microphone or a webcam. In this example the executable object would be considered the requesting entity the activity would be considered the act of obtaining access to an input stream and the target entity would be input stream of the communication device. The requesting entity is a starting point in the processing system or network of processing systems which requests the activity to be performed and the target entity is an end point in the processing system or network of processing systems which the action is performed.

As will be described in more detail a request to perform an activity can be analysed to determine at least one of the requesting entity and the target entity . By determining at least one of the requesting entity and the target entity an accurate and efficient process of detecting a threat in a processing system can be performed.

Referring to there is shown an example of a method of intercepting an activity in a processing system .

At step an event occurs in the processing system . The event can be a request by a requesting entity to perform an action in relation to a target entity . At step an operating system running in the processing system registers the occurrence of the event. At step the operating system passes the registered event to the hook chain. At step the event is passed to each hook in the hook chain such that different applications processes and devices may be notified of the registered event. Once the event has propagated throughout the hook chain the method comprises at step an application receiving notification of the event being registered by the processing system .

At step the method comprises the application initiating an API call to an API procedure so as to carry out a response to the registered event wherein the response may be the execution of the action in relation to the target entity . If an API hook has been established between the API call and the API procedure the API call is intercepted before it reaches the API procedure at step . Processing can be performed by an API hook function once the API call has been intercepted prior to the API procedure being called. The API call may be allowed to continue calling the API procedure at step such that the action is performed in relation to the target entity .

At step the method comprises intercepting one or more requests to perform an activity associated with an audio and or visual communication device of the processing system.

At step the method comprises performing a behavioural analysis of the processing system to determine if the processing system exhibits behaviour indicative of the processing system having been compromised with an audio visual threat.

The behavioural analysis allows for dynamic detection of an audio visual threat. If a particular version of an audio visual threat has been modified such that a threat signature for the version of the audio visual threat does not detect the modified audio visual threat the behaviour exhibited by the compromised processing system can be detected during the behavioural analysis of the processing system to detect the modified audio visual threat. A detailed explanation of detecting threatening and malicious activity based upon behavioural analysis is described in the Applicant s co pending U.S. patent application Ser. No. 11 780 113 and co pending Australian Patent application 2007203373 entitled Detecting Malicious Activity the content of which is herein incorporated by cross reference.

At step in the event that the request is determined to be associated with the audio visual threat the method comprises restricting the request to perform the activity in the processing system at optional step . In the event that the request is not associated with an audio visual threat the method optionally proceeds to step which comprises allowing the request to perform the activity in the processing system .

Referring now to there is shown an example of a system to detect an audio visual threat which has compromised the processing system .

In particular the system comprises an interception module configured to intercept one or more requests to perform an activity associated with an audio and or visual communication device of the processing system.

The system can optionally comprise a filter module which filters intercepted requests to determine suspicious requests requiring analysis.

The system also comprises an analysis module configured to execute a behavioural analysis of the processing system to determine if the processing system exhibits behaviour indicative of the processing system having been compromised with an audio visual threat.

The analysis module can also comprise a number of sub modules which can be used to determine if the request is associated with an audio visual threat as will be explained in more detail later in this document. The analysis module can be configured to control the number of sub modules to determine if the request is associated with an audio visual threat.

Optionally the system can comprise a restriction module which is configured to restrict the activity to be performed by the processing system in the event that results of the behavioural analysis indicate that the request is associated with an audio visual threat. In an alternate form the interception module is configured to restrict the request associated with an audio visual threat as will be explained in more detail later in this document.

Referring now to there is shown a more detailed flow diagram of an example to detect an audio visual threat.

In particular at step the method comprises intercepting the request which can be performed using the technique explained in relation to . The request can be in the form of an API call and the interception module can be provided in the form of an API hook function.

Specific requests can be intercepted which relate to one or more local communication devices such as a webcam or a microphone. For example requests can be intercepted which attempt to obtain access to an input stream for one or more communication devices such as a web cam or a sound card input line in for a microphone.

At step the method comprises determining at least one of the requesting entity and the target entity of the request to perform the activity . This can be performed by the interception module . The requesting entity and the target entity of the request can be determined using one or more parameters which are passed to the hook function.

The interception module can be configured to record intercepted requests in a intercepted request log file. The interception module can also record associated data such as at least one of the target entity the requesting entity properties associated with one of the target entity and the requesting entity the time date that the request was intercepted processing usage and memory usage. As will be explained in more detail later in this document the intercepted request log file can be used to analyse a trend in behaviour in the processing system.

At steps and the method can comprise using a filter module to determine if the request is suspicious. The filter module is configured to apply one or more filter rules to minimise false positive analysis of requesting entities and target entities which are generally not associated with an audio visual threat. The filter module can also be configured to maximise analysis of requesting entities and target entities which are generally associated with an audio visual threat. A more detailed explanation of the filter module is provided later in this document.

In the event that the target entity and or the requesting entity of the request are identified as being suspicious by the filter module the method proceeds to step . Otherwise the activity of the request is allowed to be performed.

At step the method comprises determining using the analysis module if the processing system exhibits behaviour associated an audio visual threat.

The analysis module is passed data indicative of at least one of the requesting entity and the target entity . The analysis module comprises a behaviour analysis sub module having a plurality of behaviour rules which can be applied to at least one of the requesting entity and the target entity to determine if the processing system exhibits illegitimate behaviour generally associated with an audio visual threat. In an optional form the behaviour analysis sub module comprises a plurality of behaviour rules which when applied determine if the processing system exhibits legitimate behaviour which is not generally associated with an audio visual threat. It will be appreciated that illegitimate and legitimate behaviour can be detected simultaneously using the behaviour rules.

At step the method comprises determining based on the results of the behaviour analysis performed in step whether the processing system exhibits behaviour associated with an audio visual threat.

The analysis module can be configured to determine if a threshold number of illegitimate behaviour rules are satisfied indicating that the request is associated with an audio visual threat. In another form if legitimate behaviour rules are also applied during the behaviour analysis the difference between the number of satisfied illegitimate and legitimate behaviour rules can be compared to the threshold number to determine if the request is associated with an audio visual threat.

In another form the analysis module comprises a threat assessment sub module which is configured to determine a threat value using at least the results of the behaviour analysis. The threat value can be used in comparisons to a threat threshold value to determine if the request is associated with an audio visual threat. The threat assessment sub module will be explained in more detail later in this document.

In response to a determination that the request is associated with an audio visual threat the method proceeds to step where the request to perform the activity associated with the audio visual threat is restricted.

Restricting the activity can be performed by the interception module by failing to call the API procedure. In another form an operating system defined error code may be returned to the requesting entity . In an alternative form audio and or visual data may be modified or replaced with predefined random and or invalid data and subsequently an operating system defined success code is returned to the requesting entity .

In other forms the restriction module can be used to terminate the requesting entity associated with the request . Additionally or alternatively a main executable entity associated with the requesting entity and or target entity may be removed from the processing system s memory. In an additional or alternate form data indicative of the main executable entity and or one or more related entities associated with the requesting entity and or target entity of the request is transferred to a server processing system for further analysis. It will be appreciated that a combination of the above approaches can be used to restrict the audio visual threat.

In response to a negative determination the method proceeds to step where the request to perform the activity is satisfied. This may comprise passing the parameters to the API procedure as explained in .

Optionally the method can comprise informing a user of the processing system of the detection of the audio visual threat prompting the user of the processing system regarding the detected audio visual threat and optionally receiving input from the user regarding steps to deal with the malicious activity ie. deny the activity or allow the activity . In the event that the processing system in this example is a client processing system the method can optionally comprise reporting the detection of the audio visual threat to the server processing system .

Referring to there is shown a block diagram illustrating an example of the filter module . The filter module comprises a number of lists of filter rules for filtering intercepted requests . The filter module can comprise at least one of a susceptible target entity filter list a non susceptible target entity filter list a trusted requesting entity filter list and a non trusted requesting entity filter list .

The susceptible target entity filter list comprises one or more target entity filter rules which when applied to a target entity determine if the target entity relating to the intercepted request is of interest thereby identifying that the request is suspicious. For example a common back door entity in a processing system may be known to be susceptible to an audio visual threat. One of the target entity filtering rules may require a comparison of the name of the target entity to the name of the common back door entity and if the susceptible target entity rule is satisfied the target entity is considered of interest therefore identifying the request as suspicious.

The non susceptible target entity filter list comprises one or more target entity filter rules which when applied to a target entity filter out target entities which are not susceptible to malicious activity and thus are not considered of interest thereby identifying the request as non suspicious. By using the non susceptible target entity filter list an activity that occurs in relation to a non susceptible target entity can be dismissed as being associated with an audio visual threat and thus analysis does not need to be performed in relation to the request .

The trusted requesting entity filter list comprises one or more requesting entity filter rules which when applied filter out trusted requesting entities which are not considered of interest ie. there is a high probability that the requesting entity is not associated with a malicious request thereby identifying that the request is non suspicious.

The non trusted requesting entity filter list is similar to the susceptible target entity filter list except this list comprises one or more requesting entity filter rules to identify requesting entities which are of interest ie. there is a high probability that the requesting entity is associated with a malicious request . By identifying a non trusted requesting entity the request can generally be identified as being suspicious.

Each filter rule in each list can have an associated filter rule identity. When a filter rule is satisfied an identity of the satisfied filter rule can be recorded. Over time particular filter rules are satisfied more frequently than others. The frequency which each rule is satisfied can be used to determine a filter rating which can be used to order the rules in each list. As will be described in more detail below the filter rating can be used to determine an order which a list of filter rules are applied to intercepted requests such that on average the number of filter rules used prior to a filter rule being satisfied is reduced.

In some instances a request may have been identified as being non suspicious using one of the lists of the filter module whereas a different list of the filter module may have identified the same request as being suspicious. In this instance the worst case scenario should be applied which would be to identify the request as suspicious. One approach to is to use the susceptible target entity filter list and the non trusted requesting entity filter list prior to the non susceptible target entity filter list and the trusted requesting entity filter list such that the worst case scenario is given priority.

In other instances a request may fail to be identified as suspicious and non suspicious. In this instance a default identification can be assigned to the request . The default identification may be to identify the request as being suspicious. However a more lenient approach may be to set the default identification as being non suspicious. In one form the default identification can be defined by the user of a processing system .

Referring now to there is shown a block diagram illustrating an example of ordering filter rules to facilitate efficient analysis of intercepted requests .

As shown in ordered list the filter rules are ordered in descending order according to the respective filter ratings for each filter rule in the list . Thus Rule 4 has the highest filter rating and therefore this filter rule is positioned at the start of the list. Rule 1 has the next highest filter rating and is therefore positioned second in the list followed by Rule 3 and then Rule 2 .

This process of determining an order of filter rules can be performed by a single processing system or alternatively in a distributed system. A distributed system advantageously allows the generation of the filter ratings and an order of the filter rules using a larger sample of feedback data obtained from a plurality of client processing systems . A single processing system advantageously allows for the determination of filter ratings and an order of the filter rules which are customised for that particular processing system .

In a distributed system order data indicative of the order of the list can be transferred to one or more client processing systems such that the order indicated by the order data can be used when applying the filter rules to determine suspicious requests . In one form one of the client processing systems in a distributed system may transfer a request for an updated order of the filter rules and in response the server processing system transfers the order data to the requesting client processing system . In another additional or alternative form the server processing system may be scheduled to periodically transfer the order data to the plurality of the client processing systems .

As previously indicated each filter rule has an associated frequency indicative of the number of times the filter rule has been satisfied. The frequency can be split into a number of portions. In this example each frequency is split into two portions a first portion being the frequency that the filter rule had been satisfied within the past ten days and a second portion being the frequency that the filter rule had been satisfied outside the past ten days.

As seen from Rule 1 has been satisfied ten times within the past ten days and has also been satisfied one hundred times outside the past ten days. Rule 4 has been satisfied forty five times within the past ten days and has also been satisfied twenty times outside the past ten days.

This distribution of frequencies can indicate a trend of requests associated with audio visual threats. For example in regard to Rule 1 which may be a susceptible target entity filter rule there may have been a threat signature which has been recently distributed amongst client processing systems that has resulted in Rule 1 being satisfied less often compared to past frequencies that occurred outside the ten day period. In regard to Rule 4 which may also be a susceptible target entity filter rule there may have been an outbreak of an audio visual threat which is targeting particular susceptible entities and accordingly Rule 4 has recently been satisfied more often compared to past frequencies that occurred outside this ten day period as indicated by the rise of the frequency within the past ten days.

In order to take into account trends in activity associated with an audio visual threat such as outbreaks of specific malicious requests and distributions of software patches a filter rating formula is used to weight the distribution of frequencies for each filter rule. In this example the filter rating formula is shown below FilterRating 2 recentFreq 0.5 olderFreq Where 

It will be appreciated that different weights can be used. Furthermore it will be appreciated that a larger breakdown of frequency distribution can be used.

As can be seen from the filter rating formula the frequency of instances when the filter rule was satisfied within the past ten days is weighted more heavily in order to take into account recent trends of malicious requests. Thus the filter rating for Rule 1 and Rule 4 are calculated to be FilterRatingRule1 2 10 0.5 100 20 50 70 FilterRatingRule4 2 45 0.5 20 90 10 100

As can be seen from the respective filter ratings for Rule 1 and Rule 4 even though Rule 1 has been satisfied more often in the past as indicated by frequency it appears that Rule 4 has recently been satisfied more often indicated by frequency due to an outbreak of one or more threats targeting susceptible entities which Rule 4 determines to be of interest. Thus Rule 4 receives a higher filter rating compared to the filter rating of Rule 1 due to the recent trend in malicious requests.

When the list of filter rules is ordered Rule 4 is ranked higher in the list compared to Rule 1 and therefore Rule 4 is used prior to Rule 1 when determining suspicious requests. On average this ordering of the filter rules can reduce the number of applications of filter rules by the filter module thereby resulting in an efficient filtering process.

Referring to there is shown a more detailed block diagram of an example of an analysis module . As previously described the analysis module comprises a number of sub modules which the analysis module can control and use individually or in combination to determine if the processing system is compromised with an audio visual threat.

The analysis module can comprise a behaviour analysis sub module a property analysis sub module a cryptographic hash sub module a checksum sub module a disassembly sub module a black list white list sub module a pattern matching sub module a relationship analysis sub module and a threat assessment sub module .

Data returned by the above sub modules can be indicative of whether the one or more entities are associated with an audio visual threat. However data returned may require further processing by other sub modules. Therefore the analysis module is configured to pass data requiring further processing onto the appropriate sub module to thereby determine if the one or more entities are associated with an audio visual threat.

As previously indicated the behaviour analysis sub module comprises a plurality of behaviour rules. The analysis module passes the behaviour analysis sub module one or more entities which require behaviour analysis.

Generally at least one of the requesting entity and the target entity of the suspicious request are passed to the behaviour analysis sub module for behaviour analysis. However other entities can be passed by the analysis module to the behaviour analysis sub module . For example a group of related entities determined by the relationship analysis sub module can be passed by the analysis module to the behaviour analysis sub module to determine if a group of related entities for the suspicious request exhibits behaviour associated with an audio visual threat.

The behaviour analysis sub module can return data to the analysis module indicative of the behaviour rules which were satisfied. As will be explained in more detail below in relation to the threat assessment module the number of satisfied behaviour rules or threat values associated with satisfied behaviour rules can be used to determine whether the processing system is compromised with an audio visual threat.

The behaviour analysis sub module may also query the intercepted request log file to determine whether particular behaviour rules are satisfied. For example the last example behaviour rule above may require a search to be performed of the intercepted request log file to determine if the requesting entity is requesting the activity to be performed at regular intervals. Furthermore the behaviour analysis sub module may query the intercepted request log file to determine if a sequence of requests have been intercepted which are indicative of the processing system being compromised with an audio visual threat.

The property analysis sub module is configured to determine one or more properties of one or more entities. The property analysis sub module receives one or more entities from the analysis module and applies one or more property rules to determine one or more properties of the one or more entities which can be used in determining if the processing system has been compromised with an audio visual threat.

The property analysis sub module generally receives from the analysis module at least one of the requesting entity and the target entity of a suspicious request . However it will be appreciated that other entities can be passed the property analysis sub module such as a group of related entities determined by the relationship analysis sub module .

Property rules can be configured to determine illegitimate properties of an entity which is generally associated with an audio visual threat and or legitimate properties of an entity which is not generally associated with an audio visual threat. The property analysis sub module can comprise the following example property rules 

Data indicative of satisfied property rules can be returned to the analysis module . As will be explained in more detail regarding the threat assessment sub module the number of satisfied property rules or threat values associated with satisfied property rules can be used to determine whether the one or more entities are associated with an audio visual threat.

The cryptographic hash sub module is configured to generate a cryptographic hash value of an entity received from the analysis module . As the cryptographic hash value can be used as an identity the cryptographic hash value can be used in comparisons with the blacklist whitelist sub module to determine whether the target entity and or requesting entity of the request is associated with an audio visual threat.

Other entities such as a group of related entities determined by the relationship analysis sub module can also be passed to the cryptographic hash sub module to determine if one or more of the entities of the group of related entities is associated with an audio visual threat. Data indicative of whether the one or more entities is associated with an audio visual threat is returned to the analysis module . If the analysis module receives data indicating that the one or more entities are associated with an audio visual threat the analysis module initiates at least one of the interception module and the restriction module to restrict the request .

The checksum sub module is configured to determine a checksum of one or more entities of the processing system . The checksum can be compared to a database blacklist whitelist module to determine whether the one or more entities received from the analysis module are malicious. Data indicative of whether the one or more entities is associated with an audio visual threat is returned to the analysis module . If the analysis module receives data indicating that the one or more entities are associated with an audio visual threat the analysis module initiates at least one of the interception module and the restriction module to restrict the request .

The pattern matching sub module is configured to search one or more entities received from the analysis module for particular patterns of strings or instructions which are indicative of malicious audio visual activity. The pattern matching sub module may operate in combination with the disassembly module . Although strings of instructions can be compared by the pattern matching sub module the pattern matching sub module may be configured to perform functional comparisons of groups of instructions to determine whether the functionality of the one or more entities is indicative of an audio visual threat. Data indicative of whether the one or more entities is associated with an audio visual threat is returned to the analysis module . If the analysis module receives data indicating that the one or more entities are associated with an audio visual threat the analysis module initiates at least one of the interception module and the restriction module to restrict the request .

The disassembly sub module is configured to disassemble binary code of one or more entities received from the analysis module such that the disassembly sub module determines processing system instructions for the entity. The processing system instructions of the one or more entities can then be used by the pattern matching sub module to determine whether the one or more entities is associated with an audio visual threat. Data indicative of disassembled instructions are returned to the analysis module wherein the analysis module transfers the disassembled instructions to the pattern matching sub module to determine whether the one or more disassembled instructions of the one or more entities is associated with an audio visual threat.

The blacklist whitelist sub module comprises a list of malicious and or non malicious entities associated with an audio visual threat. The blacklist whitelist sub module may be provided in the form of a table or database which comprises data indicative of malicious and non malicious entities. The table may comprise checksums and cryptographic hash values for malicious and non malicious entities. The data stored in the blacklist whitelist sub module can be used to determine whether one or more entities received from the analysis module is malicious or non malicious. Data indicative of whether the one or more entities is associated with an audio visual threat is returned to the analysis module . If the analysis module receives data indicating that the one or more entities are associated with an audio visual threat the analysis module initiates at least one of the interception module and the restriction module to restrict the request .

The relationship analysis sub module can be used to determine related entities relative to a starting entity . As shown by example in once a request has been identified as suspicious using the filter module the target entity and or requesting entity of the suspicious request can be treated as a starting entity and then using the relationship analysis sub module a group of related entities resembling a web of entities relative to the starting entity can be determined. A detailed explanation of detecting one or more related entities is described in the Applicant s co pending U.S. patent application Ser. No. 11 707 425 and co pending Australian Patent application AU2007200605 entitled Determination of related entities the content of which is herein incorporated by cross reference.

Generally threats such as malware comprise a bundle of malicious entities. By only considering a single entity by itself it may not be accurately possible to determine if a target entity and or requesting entity are malicious. However by determining a group of related entities relative to the target entity and or requesting entity a more accurate assessment can be made in relation to whether or not the request is malicious.

Furthermore removing a single malicious entity may not necessarily disable the audio visual threat from performing some malicious activity. Some particular forms of threats can perform repairs in relation to a single malicious entity being removed or disabled. Therefore detecting a group of related entities can be beneficial for disabling the threat.

Referring now to there is shown a method of determining related entities relative to the starting entity . The method represents the operation of the relationship analysis sub module . Method determines a group of suspicious related entities relative to the starting entity . However it will be appreciated that method can be adapted to determine any form of related entities such as trusted related entities relative to the starting entity .

At step the method comprises recording the starting entity . This generally comprises the processing system recording at least one of the target entity and or the requesting entity as the starting entity in the processing system memory such as a data store. The starting entity may be stored in the form of a table or list.

At step the method comprises determining an entity property associated with the starting entity . The entity property may be an entity type of the entity such as whether the starting entity is an executable entity a run key entity or a dynamic linked library entity. The entity property may also be a time that the starting entity was created or modified. The entity property may comprise the directory which the starting entity is contained within. The entity property may also be a vendor name associated with the starting entity . The entity property may also be a particular network address from which the starting entity was downloaded.

It will be appreciated that more than one entity property may be determined for the starting entity . However for the purposes of simplicity throughout this example it will be assumed that one entity property has been determined for the starting entity .

At step the method comprises selecting based on the entity property of the starting entity one or more related entity rules. In this particular example the one or more related entity rules take the form of one or more rules for determining suspicious entities related to the starting entity .

Step can comprise selecting based on the entity property the one or more related entity rules from a larger set of related entity rules. Each related entity rule is associated with a particular entity property and as such a selection of a related entity rules can be performed based on the entity property of the starting entity . An example list of entity properties and corresponding related entity rules is shown below in List 1.

It will be appreciated that a more detailed list of entity properties and corresponding related entity rules can be obtained using the above general rules. An example of a more detailed list of entity properties and corresponding related entity rules are provided below.

It will be appreciated that a starting entity having a trigger entity property could be any one of the following entities run keys Appinit Uninstall Key Service Hooks protocol filter and a startup list. It will further be appreciated that a starting entity having an executable entity property could be any one of the following entities executables dynamic linked libraries and other modules.

It will be appreciated from List 1 that the general entity properties and related entity rules can be extended to specific entity types such as the entity types shown in Table 1 for example INF entities Cookies entity windows instance entity and the like shown above. The more specific rules in Table 1 allow for a more specific selection of rules based on the more specific entity property which can therefore result in accurately determining the relevant related entity rules.

It will also be appreciated from Table 1 that more than one related entity rule can be obtained based on the one or more entity properties of the starting entity. As shown above in Table 1 if the entity property indicates that the starting entity is an executable entity then nine separate types of related entity rules can be applicable for determining the related entities to the starting entity which are considered suspicious.

Additionally or alternatively in a distributed system the client processing system may transfer to a server processing system one or more entity properties of the starting entity and receive from the server processing system the one or more related entity rules. In this step the server processing system may select the one or more related entity rules using the entity property from a server set of related entity rules and then transfer the one or more related entity rules to the processing system .

At step the method comprises determining using the one or more related entity rules the at least one related entity . In this particular example the related entity rules determine related suspicious entities. For simplicity purposes the following example is presented using one related entity rule. However it will be appreciated that more than one related entity rule can be used. Using an example entity of Spywarz.exe which has an entity property of a vendor name equalling Spywarz Software Enterprises the following related entity rule can be obtained 

This related entity rule is then used to determine one or more entities in the processing system which satisfy this rule. Once a scan has been performed using the related entity rule it is determined that Spywarz.dll also shares a vendor name of Spywarz Software Enterprises . As the related entity rule has been satisfied Spywarz.dll is considered a related entity to the starting entity Spywarz.exe . As such a group of suspicious related entities has been determined which comprises Spywarz.exe and Spywarz.dll .

Steps to represent a single iteration to determine a group of suspicious related entities . However if a more detailed group of related entities is required it is possible to perform multiple iterations of steps to as will now be discussed.

At step the at least one related entity is recorded. This may involve adding the at least one related entity to a list or a table which comprises the starting entity recorded at step . Furthermore the list or table may comprise data indicative of the relationship between the at least one related entity and entities which have been previously recorded.

At step the method comprises determining if an end condition has been met. For example the end condition may be satisfied when no new related entities are determined when a period of time or a number of processing cycles have elapsed when the current starting entity has an entity type which is indicative of the end condition and or when a selected number of repetitions have been performed. If the end condition has not been met the method continues to step .

At step the method comprises setting the at least one related entity as the starting entity . This may be performed in memory by reassigning the value of the starting entity . By setting the at least one related entity as the starting entity steps to can be repeated until an end condition is met. After step the method proceeds back to step to perform the next iteration therefore determining the related entities for the newly set starting entity. As such a web or network of related entities is determined until the end condition is met.

Once the end condition is satisfied the determination of the group of suspicious related entities has been completed. At step at least some of the related entities can be quarantined as will be discussed in more detail below.

Optionally data indicative of direct or indirect links between entities in the group can be recorded. For example Spywarz.exe and Spywarz.dll for the above example would have a direct link. However if a subsequent related entity to Spywarz.dll was determined to be a system variable SPYWARZ VARIABLE then there would be an indirect link between Spywarz.exe and SPYWARZ VARIABLE . The number of links between the original starting entity and other related entities in the group is referred to herein as the link distance .

Once a group of suspicious entities has been obtained using the relationship analysis sub module the group of related entities can be returned to the analysis module. The analysis module can then pass the group of related entities to one or more of the other sub modules to determine if the group of related entities is associated with an audio visual threat. Optionally data indicative of link distances may be also returned to the analysis module.

The threat assessment sub module is configured to determine using the received data from the analysis module a threat value indicative of the risk which the one or more suspicious entities represents to the processing system. A detailed explanation of the threat assessment sub module is described in the Applicant s co pending U.S. patent application Ser. No. 11 829 592 and co pending Australian Patent application 2007203543 entitled Threat Identification the content of which is herein incorporated by cross reference.

The threat assessment sub module receives from the analysis module data indicative of one or more satisfied behaviour rules for one or more suspicious entities and one or more satisfied property rules for one or more suspicious entities. The one or more suspicious entities may be a group of related entities . The one or more suspicious entities can be the target entity and or the requesting entity of a suspicious request . Additional data may be received by the threat assessment module indicative of the original starting entity of the group of related entities and the relatedness of related entities in the group relative to the starting entity . The relatedness of entities may be provided in the form of link distances.

The determined threat value can then be compared to a threshold to determine if the one or more suspicious entities are malicious. Data indicative of whether the one or more suspicious entities is malicious is returned to the analysis module wherein the analysis module passes control and results of the analysis to the interception module and or the restriction module where either the request is restricted or allowed to be performed in accordance with the results of the analysis.

The threat value can take three different forms an entity threat value ETV a relational entity threat value RETV and a group threat value GTV . Each of these values and a method for calculating each will be discussed in more detail below.

An ETV is indicative of the threat that a single suspicious entity represents to the processing system.

The threat assessment sub module can be configured to determine a characteristic threat value CTV for each satisfied behaviour rule and or property rule for the suspicious entity. The threat assessment sub module can comprise a CTV formula associated with each behaviour rule and or property rule used by the behaviour analysis sub module and the property analysis sub module . If a behaviour or property rule has been satisfied as indicated by the received data the corresponding CTV formula is used to calculate the CTV for the respective behaviour or property rule for the entity. The CTVs are then used by the threat assessment sub module to determine the ETV for the suspicious entity.

Some CTV formulas can be configured to assign a constant CTV for the satisfied behaviour rule or property rule. For example if the suspicious entity has a hidden property the associated CTV formula may assign a constant value indicative a level of threat that the hidden property represents to the processing system as shown below CTV 0.3

In additional or alternative forms CTV formulas can be configured to use a recorded frequency as an input when calculating the CTV. For example if one of the satisfied behaviour rules indicates that the suspicious entity has caused the processing system to connect to a remote network address on ten occasions the CTV is adjusted according to the frequency of the behaviour as shown below 0.01 freq 0.01 10 0.1

The frequency may also be determined for a period of time. For example if the suspicious entity is connected to the remote network address on ten instances within the past five minutes then the CTV is adjusted accordingly for this frequency within this period of time. The frequency over a period of time may be determined by the analysis module using the intercepted request log file.

In further additional or alternative forms at least one CTV is temporally dependent. The CTV formula can be configured to calculate the CTV using a temporal value. For example a suspicious entity may have connected to a remote network ten days ago. Again the temporal value may be determined using the intercepted request log file. This period of time is used by the CTV formula in determining the CTV as shown below 

In the event that the suspicious entity caused the processing system to connect to the remote network address one day ago the CTV would be calculated as 

As can be seen from the above CTVs the CTV formulas can be configured to determine a CTV according to how malicious the behaviour or property rule satisfied is considered for the processing system.

As previously discussed behaviour and property rules can be indicative of non malicious and malicious activity. CTVs for legitimate characteristics and illegitimate characteristics can be calculated using the associated CTV formulas. In one form illegitimate characteristics have a positive CTV and legitimate characteristics have a negative CTV. However it will be appreciated that this is not essential.

Once CTVs for the satisfied behaviour and property rules have been determined the threat assessment module determines an ETV for the suspicious entity using the determined CTVs.

Referring to the above CTVs four characteristics of the suspicious entity have been determined. Three of the characteristics are illegitimate as indicated by the positive CTVs and one of the characteristics is legitimate as indicated by the negative CTV . The ETV can be determined by summing the CTVs for the suspicious entity. In this example the ETV would be calculated as 

In some instances an ETV may have been previously calculated for the suspicious entity and recorded in the processing system s memory. In this event the new ETV can be determined by using the CTVs and the previously stored ETV. The previous stored ETV can be weighted accordingly.

The threat assessment module is configured to compare the ETV of the suspicious entity to the ETT to determine if the suspicious entity of the suspicious request is considered malicious. In one form if the ETV is greater than or equal to the ETT the suspicious entity is identified as being malicious.

For example the ETT may be equal to 0.85 . In this example the ETV equals 0.9 which is greater than the ETT. Therefore the suspicious entity is identified as being a malicious entity thereby identifying that the processing system has been compromised with an audio visual threat.

An RETV is a threat value for a single suspicious entity which is calculated according to one or more adjusted ETVs of related suspicious entities relative to the single suspicious entity. In this instance the single suspicious entity is a starting entity in the group of related entities.

Referring to there is shown a group of related entities and corresponding ETVs for each entity in the group. The RETV can be calculated by summing ETVs for each entity in the group which is adjusted according to the relatedness of each entity relative to the starting entity. In one form the link distance is used to adjust the ETVs for each entity in the group.

Therefore a related entity which has a direct link ie. a low link distance to the starting entity is given more weight compared to a related entity which has an indirect link ie. a higher link distance to the starting entity . The higher the link distance the less weight is provided for the respective ETV when calculating the RETV. An example RETV formula to calculate the RETV is provided below 0.5 Where 

For example the RETV for the group of related entities illustrated in would be calculated as 0.5 0.9 0.5 0.2 0.4 0.5 0.6 0.3 0.7 0.5 0.9 0.1 0.05 0.85

The RETV can then be compared to a relational entity threat threshold RETT to determine whether the suspicious entity based at least partially on the related entities is malicious. In this example the RETT may be 0.8 . Therefore the RETV is greater than RETT thereby identifying the starting entity as a malicious entity and thereby identifying that the processing system is compromised with an audio visual threat.

The GTV can be calculated by summing the ETVs for each entity in the group of related entities and then averaging the sum over the number of entities in the group . An example GTV formula to calculate the GTV is provided below 

The GTV can then be compared to a group threat threshold GTT to determine whether the group of related entities is malicious or whether at least a portion of the related entities is malicious. In this example the GTT may be 0.2 . In this instance the GTV is more than the GTT which indicates that the group of related entities is malicious thereby identifying that the processing system has been compromised with an audio visual threat.

Optionally the one or more client processing systems may receive one or more updated behaviour rules property rules filter rules and or related entity rules. The one or more client processing systems may receive updated rules from the server processing system or via a data store such as a compact disk or the like.

Optionally the one or more client processing systems may receive one or more updated formulas. The updated formulas can comprise one or more updated CTV formulas ETV formulas RETV formulas and GTV formulas.

In another optional form the one or more client processing systems may receive one or more updated thresholds. The updated thresholds can comprise one or more updated ETT RETT and GTT.

In one form statistical processes fuzzy logic processes and or heuristical processes can be used in combination with filter rules the related entity rules and or the malicious assessment rules to determine whether a rule has been satisfied.

The embodiments discussed may be implemented separately or in any combination as a software package or component. Such software can then be used to pro actively notify restrict and or prevent malicious activity being performed. Various embodiments can be implemented for use with the Microsoft Windows operating system or any other modern operating system.

In one optional form although four types of filter lists have been herein described for the filter module these filter lists can be used separately or in combination.

In another optional form the user may define user defined filter rules. For example there may be an activity in the client processing system which is being analysed by the analysis module however the user is aware that the activity is not associated with an audio visual threat. As such the user is able to define a user defined rule such as to prevent the request being analysed by the analysis module . In one form user defined filter rules are applied prior to the other filter rules.

In optional forms a mode of operation of an entity may be used to weight the ETV the RETV or the GTV. For example an entity may be operating in an administrative mode when it was recorded connecting to a remote network address. The entity is therefore considered a high threat and therefore the ETV for the entity is weighted accordingly to indicate this high risk threat.

In other optional forms the method of installation for an entity or installation files associated with an entity can be analysed to determine one or more characteristics of an entity to allow the identification of a malicious entity. Such analysis may comprise determining whether an installation file was automatically executed without user input whether the installation file is designed to delete itself after execution whether the installation file is not an executable file whether the installation file does not create a new sub directory in the processing system whether the installation file does not install itself in add and remove wizards of the operating system whether the installation file uses hidden or deceptive methods to install the entity such as using run keys whether the installation file is configured to install the entity in a directory which comprises a large number of other entities whether the installation file was not initially downloaded using an Internet browser whether the installation file does not download ongoing updates using an Internet browser and or requesting user input and whether the installation file uses social engineering to install the entity ie SCVHOST.exe instead of SVCHOST.exe .

Other characteristics that can be determined regarding an entity can comprise where the entity was downloaded from ie which country run key changes performed by the entity contents of the entity whether the entity creates auto startup points the type of packer compression means used in relation to the entity. Associated CTV formulas can be used to calculate an appropriate CTV indicative of the severity of the threat which the characteristic represents to the processing system . For example if the entity was downloaded from the US a small CTV may be calculated which contrasts to an entity which was downloaded from Russia which may result in a large CTV being calculated due to entities being downloaded from Russia being considered to represent a more severe threat to the processing system .

In another form when particular criteria are met in the processing system one or more local communication devices are locked from operating. For example if the processing system has not been used for a period of time and a screen saver is activated the method may comprise deactivating one or more of the communication devices. This may be performed by intercepting an API call to initiate the screen saver wherein the intercepting hook function deactivates one or more of the communications devices as the screen saver is being activated.

The embodiments described throughout can be implemented via hardware software or a combination of both.

Optional embodiments of the present invention may also be said to broadly consist in the parts elements and features referred to or indicated herein individually or collectively in any or all combinations of two or more of the parts elements or features and wherein specific integers are mentioned herein which have known equivalents in the art to which the invention relates such known equivalents are deemed to be incorporated herein as if individually set forth.

Although a preferred embodiment has been described in detail it should be understood that various changes substitutions and alterations can be made by one of ordinary skill in the art without departing from the scope of the present invention.

