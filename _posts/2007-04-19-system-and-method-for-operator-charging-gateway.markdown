---

title: System and method for operator charging gateway
abstract: An Operator Charging Gateway (OCG) facility within a Mobile Commerce environment that, among other things, provides a bearer-independent and delivery-agnostic charging platform that, inter alia, (a) uncouples all of the particulars of the delivery of content, services, etc. from the myriad of activities, challenges, etc. of charging and (b) adds substantial value to each of the involved parties (including, for example, Mobile Subscribers, Operators, Merchants, etc.). Within a wireless messaging ecosystem an OCG may leverage the capabilities of a centrally-located, full-featured Value-Added Service Provider.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08788354&OS=08788354&RS=08788354
owner: SYBASE 365, Inc.
number: 08788354
owner_city: Dublin
owner_country: US
publication_date: 20070419
---
This application claims the benefit of U.S. Provisional Patent Application No. 60 793 304 filed on Apr. 20 2006 which is herein incorporated by reference in its entirety.

The present invention relates generally to telecommunications services. More particularly the present invention relates to capabilities that enhance substantially the value and usefulness of for example various wireless messaging paradigms including inter alia Short Message Service SMS Multimedia Message Service MMS IP Multimedia Subsystem IMS etc. through a gateway facility that offers possibly among other things flexible and extensible charging capabilities.

As the wireless revolution continues to march forward the ability of a Mobile Subscriber MS for example a user of a Wireless Device WD such as a mobile telephone BlackBerry etc. that is serviced by an Operator to fully and completely utilize their WD to partake of services within a truly ubiquitous cross Operator environment grows in importance while simultaneously the challenges that are associated with same similarly increase.

As one specific example consider Mobile Commerce M Commerce which broadly speaking encompasses the buying and selling of Merchant supplied products goods and services through WDs. A stylized high level depiction of a hypothetical M Commerce environment involving multiple Operators and multiple Merchants is presented in . Within an M Commerce environment a number of factors including inter alia the ever expanding and rapidly changing universe of products goods services the frequently low value nature of those items the practical aspects of a youth demographic that include for example a lack of conventional credit cards etc. all contribute to the need for the separation of charging rating billing etc. activities from product good service delivery activities and once separated for the flexible comprehensive dynamic sometimes non intuitive etc. processing and management of charging events.

Such a separation yields among other things a bearer independent and delivery agnostic charging platform that inter alia a uncouples all of the particulars of delivery from the myriad of activities challenges etc. of charging and b adds substantive value to each of the involved parties including for example MS Operator Merchant etc. .

The present invention facilitates aspects of such a separation and addresses various of the not insubstantial challenges that are associated with same.

Embodiments of the present invention provide an Operator Charging Gateway OCG facility within a M Commerce environment that among other things provides a bearer independent and delivery agnostic charging platform that inter alia a uncouples all of the particulars of the delivery of content services etc. from the myriad of activities challenges etc. of charging and b adds substantial value to each of the involved parties including for example MSs Operators Merchants etc. .

In an embodiment of the invention an OCG facility may receive a purchase authorization from an external entity perform one or more processing steps on the received purchase authorization including at least submitting a purchase reservation to an Operator and return an acknowledgement to the external entity. An illustrative external entity is a Content Provider CP .

Another embodiment of the invention includes receiving a delivery confirmation notice from an external entity performing one or more processing steps on the received delivery confirmation notice including at least submitting delivery confirmation to an Operator and conditionally returning an acknowledgement to the external entity.

Yet another embodiment of the invention includes receiving a rollback request from an external entity performing one or more processing steps on the received rollback request including at least initiating rollback with an Operator and conditionally returning an acknowledgement to the external entity.

In another embodiment of the invention an OCG facility may employ a Pricing Scheme PS and or a Contract Scheme CS .

In yet another embodiment of the invention an OCG facility may employ a Universal Rating Engine URE .

In another embodiment of the invention an OCG facility may employ one or more of fraud detection capabilities multiple billing models and multiple currencies.

These and other features of the embodiments of the present invention along with their attendant advantages will be more fully appreciated upon a reading of the following detailed description in conjunction with the associated drawings.

The present invention preferably leverages the capabilities of a centrally located full featured VASP facility. As illustrated in and reference number a VASP is disposed between possibly inter alia multiple Operators Operator Operator on one side and multiple Merchants Merchant Merchant on the other side. A VASP thus bridges all of the connected entities and may provide key interoperability services including inter alia connectivity routing reporting etc. to same. For example a VASP may provide inter alia 

1 An Operator and by extension all of the MSs and that are serviced by an Operator with ubiquitous access to a broad universe of Merchants and

2 A Merchant with ubiquitous access to a broad universe of Operators and by extension to all of the MSs and that are serviced by an Operator .

Reference is made to U.S. Pat. No. 7 154 901 entitled INTERMEDIARY NETWORK SYSTEM AND METHOD FOR FACILITATING MESSAGE EXCHANGE BETWEEN WIRELESS NETWORKS and its associated continuations for a description of a VASP a summary of various of the services functions etc. that are performed by a VASP and a discussion of the numerous advantages that arise from same.

While the discussion below will include a centrally located VASP it will be readily apparent to one of ordinary skill in the relevant art that other arrangements are equally applicable and indeed are fully within the scope of the present invention.

In the discussion below aspects of the present invention are described and illustrated as being separate and apart from for example a CP and an Operator. However aspects of the present invention may be realized as for example a third party service bureau an element of an Operator an element of a VASP multiple third party entities working together etc.

In the discussion below reference is made to messages that are sent for example between a MS and an Operator. As set forth below a given message sent between a MS and an Operator may actually comprise a series of steps in which the message is received forwarded and routed between different entities including possibly inter alia a MS a VASP etc. Thus unless otherwise indicated it will be understood that reference to a particular message generally includes that particular message as conveyed at any stage between an origination source such as for example a MS and an end receiver such as for example an Operator. As such reference to a particular message generally includes a series of related communications between for example a MS and a VASP a VASP and an Operator etc. The series of related communications may in general contain substantially the same information or information may be added or subtracted in different communications that nevertheless may be generally referred to as a same message. To aid in clarity a particular message whether undergoing changes or not is referred to by different reference numbers at different stages between a source and an endpoint of the message.

A Communication Engine CE . A CE provides flexible and extensible support for a range of communication protocols including inter alia Short Message Peer to Peer SMPP Simple Mail Transfer Protocol SMTP HyperText Transfer Protocol HTTP MM4 MM7 Wireless Communication Transport Protocol WCTP Simple Object Access Protocol SOAP Telelocator Alphanumeric Protocol TAP Signaling System No. 7 SS7 etc. over which outside entities may communicate with a VASP. Support for a new protocol may be quickly realized by plugging a new protocol specific module into an internal CE framework.

B Queues . A dynamically updateable set of queues e.g. Queue Queue operate as intermediate or temporary buffers for incoming and outgoing traffic.

C Database . A logical representation of the possibly multiple physical repositories that may be implemented to support inter alia administrative configuration routing profile rating transaction inventory etc. information. The physical repositories may be implemented through any combination of conventional Relational Database Management Systems RDBMSs such as Oracle Object Database Management Systems ODBMSs in memory Database Management Systems DBMSs etc. or through any combination of other equivalent facilities.

D Transaction Engine TE . Within a TE a dynamically updateable set of one or more WorkFlows WorkFlow WorkFlow in the diagram remove incoming traffic from an intermediate or temporary incoming queue such as for example Queue perform all of the required processing operations and deposit processed artifacts on an intermediate or temporary outgoing queue such as for example Queue . Through flexible extensible and dynamically updatable configuration information a WorkFlow component may be quickly and easily realized to support any number of activities.

E Inventory Engine IE . An IE provides inter alia means possibly World Wide Web WWW based possibly data exchange based possibly Application Programming Interface API based etc. through which entities e.g. Merchants such as inter alia CPs etc. may identify upload manage etc. inventory which may include anything from static text and images to dynamic multimedia presentations to games to news alerts to etc. . Through an IE identified inventory may be stored locally e.g. within a VASP stored remotely e.g. within a Merchant such as a CP or stored through some combination of local and or remote means.

F Billing Engine BE . A BE provides inter alia comprehensive rating charging authorization etc. services and includes among other things a fa ade behind which lie or reside a range of external entities including inter alia Operator billing environments aspects of which are described in pending U.S. patent application Ser. No. 10 837 695 entitled SYSTEM AND METHOD FOR BILLING AUGMENTATION credit and debit card clearinghouses banks third party payment services electronic fund transfer services such as PayPal etc. Such a fa ade effectively isolates and abstracts away the numerous non trivial challenges that are associated with interacting with same access and security communication protocols and API sets development time and cost potentially limited pricing logic time consuming and costly certification qualification regimes administrative and regulatory concerns etc.

G Delivery Engine DE . A DE provides possibly among other things key routing conveyance etc. services. The routing services of a DE are of considerable importance given the presence of and the not insignificant challenges that arise from initiatives such as Mobile Number Portability MNP wireless wireline convergence etc. The routing services of a DE may leverage ENUM and other similar facilities to for example possibly among other things provide authoritative lookup or resolution capabilities across any range of addressing paradigms including inter alia Telephone Numbers TNs Short Codes SCs reference is made to pending U.S. patent application Ser. No. 10 742 764 entitled UNIVERSAL SHORT CODE ADMINISTRATION FACILITY for a description of various of the advantages e.g. abbreviated length such as five digits for a SC administered by Neustar under the Common Short Code CSC program and challenges e.g. management etc. that are associated with SCs Session Initiation Protocol SIP addresses etc.

H Logging Engine LE . A LE possibly among other things collects logging artifacts that are generated by all of the other components elements e.g. CE TE IE etc. as those components elements perform their individual activities and after applying an appropriate set of configurable and dynamically updateable processing steps records the resulting artifacts to a repository such as for example Database .

I Reporting Engine RE . A RE provides possibly among other things real time along with scheduled and ad hoc off line reporting services that may be delivered through various channels including inter alia WWW e mail SMS MMS IMS etc. messaging Instant Messenger IM API etc. . To supply such reporting services a RE may leverage possibly inter alia the contents of a repository such as for example Database .

J Administrator . An Administrator provides management or administrative control over all of the different components of a VASP through as one example a WWW based interface . It will be readily apparent to one of ordinary skill in the relevant art that numerous other interfaces e.g. a data feed etc. are easily possible.

The catalog of VASP components or elements that was presented above is illustrative only and it is to be understood that it would be readily apparent to one of ordinary skill in the relevant art that other components elements are easily possible and indeed are fully within the scope of the present invention.

Consistent with the particulars of aspects of the instant invention the balance of the present discussion will focus on the BE component or element and more specifically on those features capabilities functions etc. of a BE that may be offered under the umbrella of an OCG.

For purposes of illustration consider for a moment the hypothetical transaction that is depicted briefly in and reference number and more fully in and reference number . As illustrated through and reference number a series of exchanges or interactions under ultimate direction of one or more TE WorkFlows may be supported by an OCG including 

A Product service good request. For example a MS issues a request to a CP for a product service or good.

B Authorization Reservation. For example a CP submits a purchase authorization to an OCG and in turn the OCG initiates a purchase reservation to for example an Operator . The OCG may return an acknowledgement to the CP .

D Fulfillment acknowledgement. For example a CP may dispatch a delivery confirmation notice e.g. successful fulfillment unsuccessful fulfillment etc. to an OCG and in turn the OCG may submit such a notice to for example an Operator .

E Charge cancel confirmation and acknowledgement. For example confirmation and acknowledgement may be passed back to an OCG via and optionally to a CP via .

F Rollback. For example if required a CP may submit a rollback request to an OCG . Confirmation and acknowledgement of the rollback from e.g. an Operator may be passed back to an OCG via and optionally to a CP via .

The exchanges or interactions that were presented above are illustrative only and it is to be understood that it would be readily apparent to one of ordinary skill in the relevant art that other exchanges interactions are easily possible and indeed are fully within the scope of the present invention.

The individual exchanges or interactions that were described above are illustrated in somewhat more detail within the context of a download transaction involving a CP in and reference number 

A Status Verification . For example a MS issues a request to a CP for a product service or good and the CP subsequently verifies same through an OCG .

B Authentication . For example based on a MS request a CP dispatches an authentication request to an OCG and in turn the OCG submits such a request to for example an Operator . Confirmation and acknowledgement from e.g. an Operator may be passed back to an OCG via and optionally to a CP via .

C Authorization . For example a CP submits an authorization request to an OCG . The OCG following the completion of various internal processing steps involving possibly among other things an OCG s URE discussed in detail below initiates a reservation request to for example an Operator via . The OCG may return an acknowledgement to the CP .

D Delivery Confirmation . For example a CP may dispatch a delivery confirmation notice e.g. successful fulfillment unsuccessful fulfillment etc. to an OCG via and in turn the OCG may submit such a notice to for example an Operator via . Confirmation and acknowledgement from e.g. an Operator may be passed back to an OCG via and optionally to a CP via .

E Rollback . For example if required a CP may submit a rollback request to an OCG . Confirmation and acknowledgement of the rollback from e.g. an Operator may be passed back to an OCG via and optionally to a CP via .

An OCG may aid in bridging the impedance imbalance that may exist between for example Operators who may be large monolithic slow to change subject to numerous regulatory and other constraints etc. and Merchants and other similarly situated entities who may desire to respond quickly to market pressures who may need to package price distribute time sensitive content new music an upcoming movie news alerts etc. quickly and creatively etc. .

1 Push. For example a VASP may purchase capacity bandwidth etc. in bulk from various operators and then re sell same to one or more Merchants under any number of pricing plans.

2 Revenue Share. For example an Operator may collect funds from an MS for products services goods consumed and then dispatch some portion or share or percentage of those funds to a VASP who may in turn dispatch some portion or share or percentage of the amounts received to one or more Merchants based on any number of distribution schemes or models.

The reporting services that may be offered by a VASP may support or otherwise facilitate aspects of the process of funds settlement across all of the different entities that may exist upstream of the VASP e.g. one or more Operators and or downstream of the VASP e.g. one or more Merchants . For purposes of illustration consider for a moment the following hypothetical example 

A Operator X collects 100 of the charges that are assessed for transactions involving their MSs for applicable products services goods during a specified time interval. The collected funds are dispatched or reported or etc. to a VASP.

B For the first 10 of transaction volume the collected funds are to be distributed by the VASP as follows 

C Following the first 10 of transaction volume and up to 50 of transaction volume the collected funds are to be distributed by the VASP as follows 

D For the remaining transaction volume the collected funds are to be distributed by the VASP as follows 

The example that was presented above is illustrative only and it is to be understood that it would be readily apparent to one of ordinary skill in the relevant art that numerous other allocations distributions etc. and arrangement of same are easily possible and indeed are fully within the scope of the present invention.

An OCG may optionally generate one or more data files including inter alia a daily weekly monthly etc. settlement file see for an illustrative example a daily reconciliation file etc.

An OCG may provide a flexible extensible and dynamically configurable set of checks and balances that work together to ensure among other things that delivery of a product good service etc. does not take place unless the requisite financial transaction s are successfully completed that a MS is not billed unless delivery of a product good service etc. is successfully completed etc.

An OCG may optionally leverage a body of flexible extensible and dynamically updatable rules logic etc. to perform real time analysis of all of the activity that transits its borders in support of inter alia the comprehensive detection of fraudulent activity.

The real time reporting that an OCG may provide may be used by a Merchant to for example support immediate adjustments to the pricing of their products goods services as the volumes of transactions sales etc. are monitored so as to entice or otherwise stimulate further purchases etc.

B An internal neutral or pseudo currency with mappings or conversions as appropriate and as required to from supported real world currencies .

D Variable billing cycles e.g. by the minute hourly daily weekly monthly quarterly annual by bandwidth consumed by volume transferred etc. .

E Numerous pre paid models including for example line of credit debit card or mechanism etc. . Under a pre paid model a MS may secure e.g. through the purchase of a phone card or through any other functionally equivalent means a specified number of units e.g. credits messages etc. that may subsequently be consumed at defined rates during the processing of events. Under such a model an OCG may optionally interact with a MS Operator to for example pre approve different aspects of a transaction.

F The flexible extensible and dynamic hierarchical aggregation of entities e.g. Merchants Operators etc. with optionally the distribution of charge payment etc. amounts up and down the hierarchy through inter alia dynamically updateable rules. As one example consider the data model that is depicted in and reference number and which provides such support for a generic Customer .

G The use of Profiles for various entities e.g. Merchants Operators etc. . As one example consider the data model that is depicted in and reference number and which provides such support for various aspects of a generic Customer .

An OCG may employ a number of internal artifacts structures etc. in support of its activities. One such entity is a PS. A PS is a self contained framework for capturing all of the particulars associated with cost and may include possibly among other things elements such as 

1 Descriptive Information. A range of descriptive or identifying information that may include possibly inter alia a unique identifier a description that may be displayed that may be conveyed to an Operator for inclusion in a line item on a MS monthly statement etc. effective dates times etc.

2 Interval. The starting point e.g. the first of each month and the duration e.g. one calendar month of the interval or cycle during which cost is accumulated.

3 Pre Amounts. Zero one or more fixed e.g. 5.00 or variable e.g. 0.05 times the number of items processed amounts that contribute to an interval s overall or aggregate cost amount. A Pre Amount may be either a charge a positive amount or a discount a negative amount and may include possibly inter alia set up fees monthly service charges etc.

4 Base Amount. The particulars that are applied to each event to rate or determine the cost of an event. Numerous plans or models are available to select from including inter alia Static Flat Rate Basic e.g. a single fixed price Static Flat Rate Tiered e.g. price is derived from inter alia volume through defined thresholds or plateaus etc. It is important to note that the preceding catalog of plans is illustrative only it will be readily apparent to one of ordinary skill in the relevant art that other plans may be easily added.

5 Post Amounts. Zero one or more fixed e.g. 1.00 or variable e.g. 2 of the aggregate interval cost amounts that contribute to an interval s overall or aggregate cost. A Post Amount may be either a charge a positive amount or a discount a negative amount .

For purposes of illustration consider the hypothetical PS that is illustrated in and reference number which includes three 3 Pre Amounts one 1 Base Amount and two 2 Post Amounts .

It should be noted that the specific PS that was just presented is illustrative only. It will be readily apparent to one or ordinary skill in the relevant art that the inclusion of different elements and or alternative arrangements of the elements are easily possible.

One or more PSs may be associated with a Contract. A Contract may contain possibly inter alia descriptive information e.g. a unique identifier a description etc. all applicable terms and conditions e.g. including support for one or more levels of optional taxation by possibly inter alia geography national entity etc. etc.

One or more Contracts may be associated with an Operator Merchant etc. through a CS. For purposes of illustration consider the hypothetical CS that is presented in . The depicted CS employs a flexible and extensible ontology that easily supports multiple contracts per Operator Merchant etc . A contract may include a Pricing Scheme Pricing Scheme . Descriptive material may also be associated with a given Operator Merchant .

A specific item of inventory may optionally be associated with a PS through a Stock Keeping Unit SKU . A SKU may contain possibly inter alia descriptive information e.g. a unique identifier a description etc. temporal i.e. date time constraints etc.

It is important to note that the discussion of internal artifacts structures etc. that was just presented was illustrative only. It will be readily apparent to one of ordinary skill in the relevant art that numerous other artifacts structures etc. and alternative arrangements of same are easily possible.

Various of an OCG s internal artifacts structures etc. e.g. possibly expressed through data models similar to the hypothetical Rate Plan data model that is presented in and reference number may be used by an OCG s URE facility see for example and reference number to flexibly and dynamically rate events e.g. the downloading of a ringtone the downloading of and the subsequent participation in a multi party interactive game the dispatch receipt of a stock news travel weather etc. alert etc. As illustrated in and reference number a hypothetical URE may accept as input a raw or unrated event leverage a pool of flexible extensible and dynamically configurable definitional and configuration information and produce as output a processed or rated event .

Under certain circumstances a URE may during its rating of an event identify the need to go back and re rate one or more previously rated events to for example apply some updated corrected different etc. amount apply some volume sensitive increase or decrease etc. . Additionally a URE may optionally draw upon estimated message volume projections e.g. extrapolated from historical message volumes etc. to artificially align a volume sensitive Base Amount plan to what is anticipated to be the final message volume at the end of the instant cycle so as to continuously maintain a real time exact amount charged and thus obviate any number of intermediate go back and re rate operations .

These and other properties optionally enable an OCG to continuously maintain accurate up to date event rating amounts so that the OCG can at any moment in time authoritatively respond to any inquiry quickly in real time with an exact amount charged.

Various of the messages that were identified during the preceding exchanges interactions descriptions may optionally contain an informational element e.g. Thank you for using our service etc. that is provided through an OCG. The informational element may be selected statically e.g. all generated messages are injected with the same informational text randomly e.g. a generated message is injected with informational text that is randomly selected from a pool of available informational text or location based i.e. a generated message is injected with informational text that is selected from a pool of available informational text based on the current physical location of the recipient of the message as derived from as one example a Location Based Service LBS facility .

The messages may also optionally contain advertising e.g. textual material if an SMS model is being utilized or multimedia images of brand logos sound video snippets etc. material if another suitably capable model is being utilized. The advertising material may be selected statically e.g. all generated messages are injected with the same advertising material randomly e.g. a generated message is injected with advertising material that is randomly selected from a pool of available material or location based i.e. a generated message is injected with advertising material that is selected from a pool of available material based on the current physical location of the recipient of the message as derived from as one example a LBS facility .

The messages may also optionally contain promotional materials e.g. static text still images video clips etc. .

It is important to note that while aspects of the discussion that was presented above focused on the use of SCs it will be readily apparent to one of ordinary skill in the relevant art that TNs and other message address identifiers are equally applicable and indeed are fully within the scope of the present invention.

The discussion that was just presented referenced the specific wireless messaging paradigms SMS and MMS. These paradigms potentially offer an incremental advantage over other paradigms in that native support for SMS and or MMS is commonly found on a WD that a potential MS would be carrying. However it is to be understood that it would be readily apparent to one of ordinary skill in the relevant art that other paradigms IMS etc. are fully within the scope of the present invention.

It is important to note that the hypothetical example that was presented above which was described in the narrative and which was illustrated in the accompanying figures is exemplary only. It will be readily apparent to one of ordinary skill in the relevant art that numerous alternatives to the presented example are easily possible and indeed are fully within the scope of the present invention.

The foregoing disclosure of the preferred embodiments of the present invention has been presented for purposes of illustration and description. It is not intended to be exhaustive or to limit the invention to the precise forms disclosed. Many variations and modifications of the embodiments described herein will be apparent to one of ordinary skill in the relevant art in light of the above disclosure.

