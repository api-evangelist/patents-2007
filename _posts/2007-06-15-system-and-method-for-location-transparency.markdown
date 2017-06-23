---

title: System and method for location transparency
abstract: A service that augments a key element of Unified Messaging and Unified Communications initiatives—i.e., Mobile Subscriber Location Awareness—to enhance substantially the value, usefulness, etc. of the presence awareness, place shifting, etc. components of such initiatives. The service may optionally leverage the capabilities of a centrally-located, full-featured Messaging Inter-Carrier Vendor.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=07805148&OS=07805148&RS=07805148
owner: Sybase 365, Inc.
number: 07805148
owner_city: Reston
owner_country: US
publication_date: 20070615
---
This application claims the benefit of U.S. Provisional Patent Application No. 60 814 047 filed on Jun. 16 2006 which is herein incorporated by reference in its entirety.

The present invention relates generally to telecommunications services. More particularly the present invention relates to capabilities that enhance substantially a key element of Unified Messaging UM and Unified Communications UC initiatives i.e. Mobile Subscriber MS Location Awareness LA .

As the wireless revolution continues to march forward the importance to a MS for example a user of a Wireless Device WD such as a cellular telephone or a BlackBerry that is serviced by a Wireless Carrier WC of their WD grows substantially.

For example under UM and UC schemes or environments among other things the storage management presentation etc. of multiple messaging paradigms or models including inter alia voice Short Message Service SMS Multimedia Message Service MMS Internet Protocol IP Multimedia Subsystem IMS Instant Messenger IM Electronic Mail E Mail facsimile transmission FAX etc. are dynamically adapted to match or otherwise meet the unique requirements needs etc. of a MS particular circumstances and are subsequently exposed or offered to a MS WD through mechanisms such as Session Initiation Protocol SIP Real time Transport Protocol RTP Session Initiation Protocol for Instant Messaging and Presence Leveraging Extensions SIMPLE eXtensible Messaging and Presence Protocol XMPP etc.

A key element in the determination of a MS particular circumstances as referenced above is knowledge of the current physical location of a MS WD i.e. MS LA.

MS LA based service offerings are of particular interest to for example individuals who are on call for business reasons e.g. technical support etc. or for personal reasons e.g. a medical condition such as organ transplantation pregnancy etc. first responders individuals within a large corporate environment etc.

The present invention extends key elements of wireless technology to augment MS LA based offerings and addresses various of the not insubstantial challenges that are associated with same thereby incrementally enhancing the value usefulness etc. of the presence awareness place shifting etc. components of UM and UC schemes or environments.

Embodiments of the present invention provide a service that augments a key element of UM and UC initiatives i.e. MS LA to enhance substantially the value usefulness etc. of the presence awareness place shifting etc. components of such initiatives.

In an embodiment of the invention a Service Provider SP 1 receives a location update from a WC indicative of the current physical location of a MS s WD 2 completes one or more processing steps on the received location update using possibly inter alia information that was previously supplied by the MS and 3 updates one or more elements within a repository with the results of the processing steps.

In another embodiment of the invention a SP 1 receives a location inquiry from a requester 2 processes the received inquiry and 3 dispatches one or more response messages containing current location information to the requester. The location inquiry and the response messages may transit any number of channels including possibly inter alia SMS MMS IMS IM E Mail a Web based facility etc.

In another embodiment of the invention a SP 1 receives a contact inquiry from a requester 2 processes the received inquiry and 3 dispatches one or more response messages containing current contact information to the requester. The contact inquiry and the response messages may transit any number of channels including possibly inter alia SMS MMS IMS IM E Mail a Web based facility etc.

In still another embodiment there is provided a method for providing contact information for a mobile subscriber. Registration information is received from a mobile subscriber including information about predetermined locations frequented by the mobile subscriber and contact information is further received corresponding to at least some of said predetermined locations. A wireless carrier providing service to the mobile subscriber provides an indication of a current location of a wireless device belonging to the mobile subscriber.

A query for contact information for the mobile subscriber is received and then based at least in part on the indication of the current location of the wireless device belonging to the mobile subscriber one of the predetermined locations frequented by the mobile subscriber is identified as a present location of the mobile subscriber. The contact information corresponding to the present location of the mobile subscriber if any is then selected and a message in response to the query is generated and sent then message including the contact information corresponding to the present location of the mobile subscriber.

These and other features of the embodiments of the present invention along with their attendant advantages will be more fully appreciated upon a reading of the following detailed description in conjunction with the associated drawings.

The present invention may leverage the capabilities of a centrally located full featured MICV facility. Reference is made to U.S. Pat. No. 7 154 901 entitled INTERMEDIARY NETWORK SYSTEM AND METHOD FOR FACILITATING MESSAGE EXCHANGE BETWEEN WIRELESS NETWORKS and its associated continuations for a description of a MICV a summary of various of the services functions etc. that are performed by a MICV and a discussion of the numerous advantages that arise from same.

As illustrated by and reference numeral a MICV is disposed between possibly inter alia multiple WCs WCWC on one side and multiple SPs SPSP on the other side and thus bridges all of the connected entities. A MICV thus as one simple example may offer various routing formatting delivery value add etc. capabilities that provide possibly inter alia 

1 A WC WCWC and by extension all of the MSs MSMS MS MS MSMS that are serviced by a WC WCWC with ubiquitous access to a broad universe of SPs SPSP and

2 A SP SPSP with ubiquitous access to a broad universe of WCs WCWC and by extension to all of the MSs MSMS MSMS MSMS that are serviced by a WC WCWC .

Generally speaking a MICV may have varying degrees of visibility e.g. access etc. to the MSMS MSSP etc. messaging traffic 

1 A WC may elect to route just their out of network messaging traffic to a MICV. Under this approach the MICV would have visibility e.g. access etc. to just the portion of the WC s messaging traffic that was directed to the MICV by the WC.

2 A WC may elect to route all of their messaging traffic to a MICV. The MICV may possibly among other things subsequently return to the WC that portion of the messaging traffic that belongs to i.e. that is destined for a MS of the WC. Under this approach the MICV would have visibility e.g. access etc. to all of the WC s messaging traffic.

While the discussion below will include a MICV it will be readily apparent to one of ordinary skill in the relevant art that numerous other arrangements are equally applicable and indeed are fully within the scope of the present invention.

In the discussion below the present invention is described and illustrated as being offered by a SP. A SP may for example be realized as a third party service bureau an element of a WC or a landline carrier an element of a MICV multiple third party entities working together etc.

In the discussion below reference is made to messages that are sent for example between a MS and a SP. As set forth below a given message sent between a MS and a SP may actually comprise a series of steps in which the message is received forwarded and routed between different entities including possibly inter alia a MS a WC a MICV and a SP. Thus unless otherwise indicated it will be understood that reference to a particular message generally includes that particular message as conveyed at any stage between an origination source such as for example a MS and an end receiver such as for example a SP. As such reference to a particular message generally includes a series of related communications between for example a MS and a WC a WC and a MICV a MICV and a SP etc. The series of related communications may in general contain substantially the same information or information may be added or subtracted in different communications that nevertheless may be generally referred to as a same message. To aid in clarity a particular message whether undergoing changes or not is referred to by different reference numbers at different stages between a source and an endpoint of the message.

To better understand the particulars of the present invention consider for a moment a simple hypothetical example SP SPoffers a service that has been enhanced or augmented as provided through the instant invention and Mary a MS uses SP s service.

SP Billing Interface BI . A single consolidated interface that SPX may use to easily reach inter alia one or more external entities such as a credit card or debit card clearinghouse a carrier billing system a service bureau that provides access to multiple carrier billing systems etc.

SP AS . Facilities that provide key elements of the instant invention which will be described below .

1 The MS WD and MS PC entities are illustrated as being adjacent or otherwise near each other. In actual practice the entities may for example be physically located anywhere.

3 The SP may employ a Short Code SC or a regular Telephone Number TN as its source address and to which it would ask users of its service to direct any messages . While the abbreviated length of a SC e.g. five digits for a SC administered by Neustar under the Common Short Code CSC program incrementally enhances the experience of a MS e.g. the MS need remember and enter only a few digits as the destination address of a message it also by definition constrains the universe of available SCs thereby causing each individual SC to be a limited or scarce resource and raising a number of SC CSC management etc. issues. A description of a common i.e. universal short code environment may be found in pending U.S. patent application Ser. No. 10 742 764 entitled UNIVERSAL SHORT CODE ADMINISTRATION FACILITY which is incorporated herein by reference.

In the exchanges that are collected under the designation Set 1 represent the activities that might take place as Mary our MS completes a registration process with SP. For example 

A Mary uses one of her PCs to visit a WS that is offered by SP to possibly among other things complete a service registration process .

B SP s WS interacts with SP s AS to possibly among other things commit some or all of the information that Mary provided to a data repository e.g. a database optionally complete a billing transaction etc. .

The specific exchanges that were described above as residing under the designation Set 1 are illustrative only and it will be readily apparent to one of ordinary skill in the relevant art that numerous other exchanges are easily possible and indeed are fully within the scope of the present invention. As just one example the registration process may be completed through any combination of one or more channels including inter alia the indicated WWW facility wireless messaging SMS MMS IMS etc. E Mail messages IM exchanges conventional mail telephone Interactive Voice Response IVR facilities etc.

During the registration process that was described above a range of information may be captured from a MS including inter alia 

1 Identifying Information e.g. general information about Mary . For example possibly among other things a unique identifier and a password optionally a pseudonym or handle name address age etc.

2 Billing Information. Different service billing models may be offered by SPX including possibly inter alia free e.g. possibly advertising based a fixed one time charge a recurring monthly etc. fixed charge a recurring monthly etc. variable charge a per use charge etc. Different payment mechanisms may be supported by SPincluding possibly among other things credit or debit card information authorization to place a charge on a MS s phone bill etc.

3 Locations e.g. the various physical locations home work schools stores etc. that Mary frequents and which Mary wishes to explicitly identify . For example possibly among other things a brief description the full physical address etc.

4 Contacts e.g. all of the different ways that Mary may be contacted telephone E Mail IM etc. and which Mary wishes to make available . For example possibly inter alia wireline telephone numbers e.g. home work etc. wireless telephone numbers e.g. personal work etc. E Mail addresses e.g. personal work etc. IM handles e.g. personal work etc. Uniform Resource Locators URLs for example a personal Web site etc.

5 Associations e.g. the mapping or association between a location and a contact along with the relative prioritization 1 2 etc. of same .

The specific pieces of information that were described above are illustrative only and it will be readily apparent to one of ordinary skill in the relevant art that numerous other pieces of information are easily possible and indeed are fully within the scope of the present invention.

As noted above the information that Mary provided during the registration process may be preserved in a data repository e.g. a database and may optionally be organized as a MS Profile. For purposes of illustration a portion of an exemplary MS Profile data model is presented in and reference numeral and selected contents of same are presented in and reference numeral .

The content of Mary s profile may optionally be augmented by SP. For example for each of the identified locations an internal or external data source may be queried to determine the latitude or Phi and longitude or Lambda of the location from the physical address of the location.

As noted above a SP s BI may optionally complete a billing transaction. The billing transaction may take any number of forms and may involve different external entities e.g. a WC s billing system a carrier billing system service bureau a credit or debit card clearinghouse etc. . The billing transaction may include inter alia 

1 The appearance of a line item charge on the bill or statement that a MS receives from her WC. Exemplary mechanics and logistics associated with this approach are described in pending U.S. patent application Ser. No. 10 837 695 entitled SYSTEM AND METHOD FOR BILLING AUGMENTATION. Other ways of completing or performing line item billing are easily implemented by those skilled in the art.

In the exchanges that are collected under the designation Set 2 represent the activities that might take place as SP registers coordinates etc. with WC to possibly among other things receive from WC Location Based Services LBS based Global Positioning System GPS based etc. location updates regarding or concerning Mary s WD .

The specific exchanges that were described above as residing under the designation Set 2 are illustrative only and it will be readily apparent to one of ordinary skill in the relevant art that numerous other exchanges including inter alia a WC optionally explicitly confirming with a MS their desire acceptance before beginning to provide MS WD location information to a SP updates to various of the information in a MS Profile in a SP s repository etc. are easily possible and indeed are fully within the scope of the present invention.

In the exchanges that are collected under the designation Set 3 represent the activities that might take place as SP dispatches to Mary one or more confirmation E Mail messages .

The specific exchanges that were described above as residing under the designation Set 3 are illustrative only and it will be readily apparent to one of ordinary skill in the relevant art that numerous other exchanges including inter alia other types or forms of confirmation messages are easily possible and indeed are fully within the scope of the present invention.

In the exchanges that are collected under the designation Set 4 represent the activities that might take place as SP s AS dispatches one or more confirmation SMS MMS IMS etc. messages to Mary s WD and Mary replies or responds to the message s . In the instant example the messages are shown traversing a MICV . The SP may employ a SC or a regular TN as its source address and to which it would ask a MS to direct any reply messages .

The specific exchanges that were described above as residing under the designation Set 4 are illustrative only and it will be readily apparent to one of ordinary skill in the relevant art that numerous other exchanges are easily possible and indeed are fully within the scope of the present invention.

The Set 1 Set 2 Set 3 and Set 4 exchanges that were described above are illustrative only and it will be readily apparent to one of ordinary skill in the relevant art that numerous other exchanges are easily possible and indeed are fully within the scope of the present invention.

The information that was described above may be subsequently managed e.g. existing information may be edited or removed new information may be added etc. through any combination of one or more channels including inter alia a SP s WWW facility wireless messaging SMS MMS IMS etc. E Mail messages IM exchanges conventional mail telephone IVR facilities etc.

To continue with our hypothetical example . . . After completing the registration process Mary goes about her normal activities e.g. she drives to work she attends meetings she works in her office she goes to lunch she drives home she attends functions at her children s schools she goes shopping she attends sporting events she travels on business etc. As Mary moves about her WC provides updates to SPX containing information about the physical location of Mary s WD.

The WC supplied location updates may consist of any combination of for example real time periodic batched etc. updates and may be conveyed through any combination of for example SMS MMS IMS etc. messages eXtensible Markup Language XML documents custom Application Programming Interfaces APIs etc. For purposes of illustration an exemplary XML document might contain possibly inter alia 

After a SP receives a location update from a WC it may complete one or more processing steps. For example 

2 The Contacts portion of the SP s repository e.g. see in in may be queried using the extracted TN to obtain MSId.

3 The latitude and the longitude of the instant MS WD may be extracted and or otherwise obtained or developed from information in the received location update.

4 The Locations portion of the SP s repository e.g. see in in may be queried using a MSId b the extracted obtained developed etc. latitude and longitude and c a defined level of position granularity or precision to obtain LocationId. If no match is identified then LocationId of the MS default Other location may be employed. 

5 The MSs portion of the SP s repository e.g. see in in may be updated using MSId to preserve LocationId in CurrentLocationId.

The catalog of processing steps that were described above are illustrative only and it will be readily apparent to one of ordinary skill in the relevant art that numerous other processing steps are easily possible and indeed are fully within the scope of the present invention.

To continue with our hypothetical example . . . At any time Mary may optionally submit a location inquiry i.e. a Where am I test to determine where SPX believes Mary to be at that moment in time. Such an inquiry may be submitted through any combination of one or more channels including inter alia SMS MMS IMS etc. messages Web based facility IM messages E Mail messages telephone call IVR facility etc. The returned response message may traverse any combination of one or more of the above channels and may include possibly inter alia current location information.

At any time Mary may optionally submit a spot update to fine tune or otherwise refine the location where SPbelieves Mary to be at that moment in time. Such an update may be submitted through any combination of one or more channels including inter alia SMS MMS IMS etc. messages Web based facility IM messages E Mail messages telephone call IVR facility etc. An optional response message may traverse any combination of one or more of the above channels and may include possibly inter alia confirmation of the update.

Employing interactions similar to those that were just described SPX may optionally dispatch a SMS MMS IMS etc. IM etc. message to Mary the first time that Mary visits each of her defined locations and optionally allow Mary to confirm refine correct etc. same through a spot update.

At any time Mary may optionally submit a contact inquiry i.e. a How can I be reached test to determine what SPX believes to be the correct way of contacting Mary at that moment in time. Such an inquiry may be submitted through any combination of one or more channels including inter alia SMS MMS IMS etc. messages Web based facility IM messages E Mail messages telephone call IVR facility etc. The returned response message may traverse any combination of one or more of the above channels and may include possibly inter alia current contact details.

A SP may optionally secure one or more of the interactions that were just described through the appropriate use of an identifier password mechanism.

To continue with our hypothetical example . . . At any time an interested third party may submit a contact inquiry for a MS i.e. a How may I reach Mary inquiry . Such an inquiry may be based on any combination of one or more identifiers such as possibly inter alia name TN E Mail address IM handle etc. Such an inquiry may be submitted through any combination of one or more channels including inter alia SMS MMS IMS etc. messages Web based facility at a URL such as ContactMe.com or HowToReachMe.com IM messages E Mail messages telephone call IVR facility etc.

1 The identifier of the instant MS e.g. name TN E Mail address IM handle etc. may be extracted from information in the received contact inquiry.

2 The Contacts portion of the SP s repository e.g. see in in may be queried using the extracted identifier to obtain MSId. If no match is identified then a Not Found failure response may be returned. 

3 The MSs portion of the SP s repository e.g. see in in and reference numeral may be queried using MDId to obtain CurrentLocationId.

4 The Associations portion of the SP s repository e.g. see in in may be queried using Current LocationId and a Priority of 1 to obtain ContactId.

5 The Contacts portion of the SP s repository e.g. see in in may be queried using ContactId to obtain Value.

6 The obtained Value may be returned to the requestor in a response message which may traverse any combination of one or more of the above identified channels e.g. SMS MMS IMS etc. messages IM messages E Mail messages etc. .

The catalog of processing steps that were described above are illustrative only and it will be readily apparent to one of ordinary skill in the relevant art that numerous other processing steps are easily possible and indeed are fully within the scope of the present invention.

For purposes of illustration consider for a moment a simple example that makes use of the exemplary data model contents that are presented in and reference numeral 

1 An interested third party wishes to contact Mary and therefore submits a contact inquiry to SPbased on Mary s personal E Mail address i.e. Mary37 SomeMailSvc.com .

2 The Contacts portion of the SP s repository e.g. see in in may be queried using the supplied identifier Mary37 SomeMailSvc.com to obtain MSId 1001 in the instant case .

3 The MSs portion of the SP s repository e.g. see in in may be queried using MDId 1001 in the instant case to obtain CurrentLocationId 2003 in the instant case .

4 The Associations portion of the SP s repository e.g. see in in may be queried using Current LocationId 2003 in the instant case and a Priority of 1 to obtain ContactId 3004 in the instant case .

5 The Contacts portion of the SP s repository e.g. see in in may be queried using ContactId 3004 in the instant case to obtain Value 703 555 3456 in the instant case .

6 The obtained Value 703 555 3456 in the instant case may be returned to the requester in a response message.

Using the contact details that are included in a response message a requester may attempt to contact reach the instant MS. If the attempt is unsuccessful the requester may optionally submit another contact inquiry in which case a SP may leverage its internal tracking or state maintenance to identify the new contact inquiry as inquiry number 2 and thus change the Priority designation in the Associations query from 1 to 2. If the contact attempt using the details returned in the second response message is unsuccessful and yet another contact inquiry is submitted the SP may change the Priority designation in the Associations query from 2 to 3. Such a cycle may continue until the available contacts are exhausted at which point a No Further Contacts Available response message may be returned to the requester.

A SP may optionally require that an interested third party complete a registration process before the third party is allowed to submit contact inquiries. Such a registration process may employ one or more aspects elements of Mary s registration process that was described above. Through such a registration process a SP may optionally associate an identifier password to a third party and may optionally require that a third party supply those credentials each time that they submit a contact inquiry.

If SPwere to require such third party registration then SPX may optionally allow Mary to possibly inter alia 

1 Explicitly identify those third parties to whom Mary wishes to grant inquiry access. Any other i.e. unidentified third party inquirer might receive for example a Not Authorized response message.

2 Dynamically change the content etc. of a response message based on the identity of an inquirer e.g. if Mary s husband were inquiring then the TN of Mary s WD might always be returned if one of Mary s friends were inquiring then Mary s work E Mail address might be returned etc. Additionally specific information about Mary e.g. her vCard her personal or professional Web site URL etc. may also be conditionally included in a response message based on the identity of an inquirer.

Such processing and response message behavior may be directed through a body of flexible extensible dynamically configurable and easily managed rule sets.

A SP may optionally provide any number of value add additions to the core functionality that was described above. Such additions may carry an incremental one time recurring etc. fee or charge. For example a SP may offer 

1 Alerts. For example Mary may indicate that she would like e.g. for tracking purposes that an alert to or an indication of each incoming contact inquiry be directed to a specified destination e.g. TN E Mail address IM address etc. .

2 Diversion. For example Mary may indicate that in addition to contact inquiries that actual SMS MMS IMS etc. messages should also be subject to similar rule based diversion or re direction. Under such a message diversion scheme a MICV may as just one example intercept incoming messages and appropriately re direct them based on possibly inter alia flexible extensible dynamically configurable and easily managed routing etc. rules additional interactions with an SP etc. .

3 Directories. For example in a corporate setting an on line directory of all employees with real time indicators for the current locations and or the current contact vehicles for each employee may be offered through among other channels a Web based facility. Such a directories may be augmented or enhanced by possibly among other means tying into existing corporate employee telephone etc. directories. Such directories may facilitate for example intelligent searches Who is the most senior employee with skills knowledge X Y and Z who is currently in building 3 of the corporate office campus 

A SP may optionally provide a first responder legal intercept etc. capability through which any of the exchanges or interactions that were described above may be monitored transparently altered or modified etc.

The confirmation response etc. message s that were described above may include any number of textual visual etc. information elements. For example various response messages may contain an XML document similar to as one simple illustrative example 

The confirmation response etc. message s that were described above may optionally contain an informational element e.g. a relevant or applicable factoid about a specific drug etc. The informational element may be selected statically e.g. all generated messages are injected with the same informational text randomly e.g. a generated message is injected with informational text that is randomly selected from a pool of available informational text or location based i.e. a generated message is injected with informational text that is selected from a pool of available informational text based on the current physical location of the recipient of the message as derived from as one example a LBS facility .

The confirmation response etc. message s may optionally contain advertising e.g. textual material if an SMS model is being utilized or multimedia images of brand logos sound video snippets etc. material if an MMS model is being utilized. The advertising material may be selected statically e.g. all generated messages are injected with the same advertising material randomly e.g. a generated message is injected with advertising material that is randomly selected from a pool of available material or location based i.e. a generated message is injected with advertising material that is selected from a pool of available material based on the current physical location of the recipient of the message as derived from as one example a LBS facility .

The confirmation response etc. message s may optionally contain promotional materials e.g. still images video clips etc. .

A dynamically updateable set of one or more Gateways GWGW in the diagram handle incoming e.g. SMS MMS IMS etc. messaging etc. traffic and outgoing e.g. SMS MMS IMS etc. messaging etc. traffic. Incoming traffic is accepted and deposited on an intermediate or temporary Incoming Queue IQIQ in the diagram for subsequent processing. Processed artifacts are removed from an intermediate or temporary Outgoing Queue OQOQ in the diagram and then dispatched.

A dynamically updateable set of one or more Incoming Queues IQIQ in the diagram and a dynamically updateable set of one or more Outgoing Queues OQOQ in the diagram operate as intermediate or temporary buffers for incoming and outgoing traffic.

A dynamically updateable set of one or more WorkFlows WorkFlowWorkFlow in the diagram remove incoming traffic from an intermediate or temporary Incoming Queue IQIQ in the diagram perform all of the required processing operations more about this below and deposit processed artifacts on an intermediate or temporary Outgoing Queue OQOQ in the diagram .

The Database that is depicted in is a logical representation of the possibly multiple physical repositories that may be implemented to support inter alia configuration profile monitoring alerting etc. information. The physical repositories may be implemented through any combination of conventional Relational Database Management Systems RDBMSs such as Oracle through Object Database Management Systems ODBMSs through in memory Database Management Systems DBMSs or through any other equivalent facilities.

As depicted in an Administrator provides management or administrative control over all of the different components of an AS through as one example a WWW based interface . It will be readily apparent to one of ordinary skill in the relevant art that numerous other interfaces e.g. a data feed an API etc. are easily possible.

Through flexible extensible and dynamically updatable configuration information a WorkFlow component may be quickly and easily realized to support any number of activities. For example WorkFlows might be configured to support a registration process to support interactions with a WC to support the receipt and processing of location updates from WCs to support the generation and dispatch of confirmation response etc. messages to support various billing transactions to support the generation of scheduled and or on demand reports etc. The specific WorkFlows that were just described are exemplary only it will be readily apparent to one of ordinary skill in the relevant art that numerous other WorkFlow arrangements alternatives etc. are easily possible.

A SP may maintain a repository e.g. a database into which selected details of all administrative messaging etc. activities may be recorded. Among other things such a repository may be used to support 

1 Scheduled e.g. daily weekly etc. and or on demand reporting with report results delivered through SMS MMS IMS etc. messages through E Mail through a WWW based facility etc.

2 Scheduled and or on demand data mining initiatives possibly leveraging or otherwise incorporating one or more external data sources with the results of same presented through Geographic Information Systems GISs visualization etc. facilities and delivered through SMS MMS IMS etc. messages through E Mail through a WWW based facility etc.

It is important to note that while aspects of the discussion that was presented above focused on the use of SCs it will be readily apparent to one of ordinary skill in the relevant art that TNs and other message address identifiers are equally applicable and indeed are fully within the scope of the present invention.

The discussion that was just presented referenced two specific wireless messaging paradigms SMS and MMS. These paradigms potentially offer an incremental advantage over other paradigms in that native support for SMS and or MMS is commonly found on a WD that a potential MS would be carrying. However it is to be understood that it would be readily apparent to one of ordinary skill in the relevant art that other paradigms IMS etc. are fully within the scope of the present invention.

The foregoing disclosure of the preferred embodiments of the present invention which was described in the narrative and which was illustrated in the accompanying figures has been presented for purposes of illustration and description. It is not intended to be exhaustive or to limit the invention to the precise forms disclosed. It will be readily apparent to one of ordinary skill in the relevant art that numerous alternatives to the presented embodiments are easily possible and indeed are fully within the scope of the present invention.

