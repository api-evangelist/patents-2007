---

title: Network interoperability
abstract: The present invention relates to a method in a communication network for connecting at least one application server (AS) () of an internet protocol multimedia subsystem (IMS) () to an intelligent network (IN) () through an interface unit (). The IMS () comprises a call server control function (CSCF) unit () connected to the at least one AS () arranged for processing call signaling. In the method the interface unit () directs the call signaling to the at least one AS () through the CSCF unit () and the at least one AS () processes the call signaling and sends the processed call signaling through the CSCF unit () back to the interface unit (). Based on the information received in the call signaling processed by the at least one AS (), the interface unit () then directs the call to a destination.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08233485&OS=08233485&RS=08233485
owner: Comverse Ltd
number: 08233485
owner_city: Tel Aviv
owner_country: IL
publication_date: 20070817
---
This application claims priority from the European patent application EP06291323 filed on 17 Aug. 2006 which is hereby incorporated by reference in its entirety.

The present invention relates to interoperability between communication networks. More specifically it relates to a situation in which application servers of an internet protocol multimedia subsystem IMS provide services to terminals of a time division multiplexing TDM intelligent network IN .

Network service providers are facing a major migration challenge as the telephony networks currently deployed using TDM digital switches need to be redesigned to use voice over internet protocol VoIP . Emerging standards such as the European Telecommunication Standards Institute ETSI 3Generation Partnership 3GPP IMS also change the way network services may be designed.

In conventional telephone networks employing TDM a major issue faced by complex telecom services is the so called tromboning which means that a switch which implements a specific service and which is used to set up a call also processes the voice bearer channels when the call has already been set up.

In a large network a call from a user located in a city A to another user also in the city A may need to be processed by a centralized switch located in a city B. If the distance between these two cities is large then the voice path is long enough to introduce perceptible delays echoes and require additional and expensive echo cancellers.

The widely used signaling system 7 SS7 does not solve the problem even if the transport networks are separate for signaling and voice bearers. In fact although the transport network of the signaling and voice are indeed separate the SS7 integrated services digital network user part ISUP signaling and voice bearers are still processed by each switch. It is not feasible to build centralized service switches processing only SS7 ISUP without also implementing a TDM switching matrix for the voice bearers. Therefore TDM centralized service switches continue to cause tromboning issues even in TDM networks using SS7 signaling.

The technology called intelligent network IN can be used in order to partially solve this problem. This technology uses an abstract call model and lets an external application interact with a remote TDM switch using control primitives acting on the abstract call model. The intelligent network application part INAP protocol standardized by the International Telecommunications Union ITU ITU T SG 11 recommendation Q1224 approved in 1997 is the most widely used protocol enabling an external application to interact with remote TDM switches using a call processing logic that can be modeled according to the state machine defined by ITU Q1224. The ITU has also defined IN capability set CS call models ITU T SG 11 Q1244 defines CS4 which let INAP applications control voice over IP VoIP calls.

The SSP acts as a trigger point for further services to be invoked during a call. The SSP may invoke a query to the SCP to wait for instructions on how to proceed. The SCP contains service logic which implements the behavior described by the operator. This enables service providers to deploy the application logic centrally while only SSPs are distributed. The signaling protocol used between the SSP and the SCP is INAP and is based on an abstract call model which represents the capabilities of the SSP .

The SSP and SCP functions can also be collocated leading to the so called service node deployment model. In this case there is no longer a requirement for standardized call model. However this induces even higher costs as the SSP function needs to be distributed because of tromboning issues and therefore in this case also the application needs to be deployed over multiple Points of Presence POPs .

By contrast to TDM technology VoIP technology separates the media transport plane and the call media control plane. A VoIP service switch can interact with media streams without processing the IP packets containing the signaling at all.

For instance in if the phones are communicating with each other by use of VoIP then the calls are set up via the SSP but once the calls are set up the IP packets transporting the media stream can be routed to the destination directly without a need to route the packets via the SSP any longer. The tromboning problem no longer exists in a properly designed VoIP network. Because there is no tromboning the SSP function can now be centralized and because it can be centralized it can also be collocated with the application logic itself SCP . With both SSP and SCP collocated there is no longer a need for a standardized call model supporting communication between them.

Recognizing this major improvement the ETSI 3Generation Partnership Project 3GPP defined internet protocol multimedia subsystem IMS which is a new telecommunications service architecture optimized for VoIP technology.

The CSCF block is further connected to home subscriber server HSS . It contains the subscriber related information performs authentication and authorization of the user and can provide information of the physical location of the user. The CSCF block is further connected to a media resource function MRF and a gateway which interfaces with a circuit switched public switched telephone network PSTN or public land mobile network PLMN . The MRF provides a source of media in the home network and it is for instance used for playing announcements real time transcoding of multimedia data text to speech conversation and speech recognition.

The use of VoIP by the IMS network has an important consequence. While TDM networks required a standardized call model in order to allow applications to efficiently interact with the communications network the ASs have access to the call signaling directly and therefore no call model is required. This gives much more flexibility to application designers reduces the complexity of the network mainly by reducing the level of interactions between components and makes it possible to introduce applications not previously allowed by the call models standardized for TDM networks.

For instance the IMS network allows support for applications in a roaming environment for cellular phones. In TDM INs most services e.g. a short numbering plan for a corporation are lost when roaming outside of the home network because routing outgoing calls to the home network would create a tromboning problem and because INAP links are not so frequently allowed among roaming networks. In an IMS network on the contrary the signaling of all calls placed by an end user in a roaming situation is routed to the home network and therefore most services working in the home environment will work in a roaming situation.

Many service providers are now convinced that the advantages brought by VoIP and the IMS architecture justify a migration of TDM networks to VoIP and IMS. However such a migration takes a long time and for a long time TDM networks such as mobile GSM networks and IMS networks will have to coexist. It is tempting for TDM service providers to start developing all new applications in an IMS mode using IMS ASs and stop developing IN applications in current TDM networks. However most IMS devices will have to work in dual mode initially and therefore the same application logic needs to be available while working in IMS mode or working in TDM mode.

Developing applications for the two networks would require to either develop them twice as IMS AS applications and as IN applications or would require introducing an IMS AS implementing an IN call model and develop the application in IN mode only.

The latter approach using an IN call model for VoIP networks has been proposed by multiple standard bodies and resulted in concepts and products such as IN CS4 JAIN or PARLAY. Although this approach does have the merit of allowing a single application to run over a TDM or a VoIP network it does have significant drawbacks.

It proposes to continue using the standardized call model of the IN and therefore has some limitations. All applications cannot be developed using the IN call models. It introduces a complexity not required by most native IMS applications that could be implemented directly over an IMS AS and perhaps using other call models or application programming interfaces APIs more suited to the application. It does not enable building applications controlling both TDM and IP legs in a transparent manner applications need to control separately TDM to TDM calls and IP to IP calls. TDM to IP calls need to be processed twice once by the TDM to TDM application logic which is responsible to route the call to a VoIP gateway then by the VoIP to VoIP application logic. The VoIP to TDM bridge logic has to be designed by each application developer.

One object of the invention is to limit the above identified deficiencies. More specifically a method for connecting the IMS network to the IN by use of ASs has been invented.

According to a first aspect of the invention there is proposed a method for connecting at least one AS of an IMS network to an IN through an interface unit wherein the IMS comprises a CSCF unit connected to the at least one AS arranged for processing call signaling wherein the method comprises the following steps with respect to a call 

The invention in accordance with an embodiment of the invention has the advantage that it allows a smooth integration of the IN and the IMS network . The invention thus makes it possible to the IMS ASs to control the IN endpoints. Furthermore there is no need to design the applications separately to the INs and to the IMS networks nor is there a need to implement the IN call model in IMS ASs and develop the applications in IN mode only.

The invention further allows in accordance with an embodiment to program telecommunication applications using only the SIP IMS service control ISC interface. The interface can take control of heterogeneous IMS and TDM IN endpoints and the applications do not need to handle any special case for the TDM to IP or IP to TDM calls.

The invention also relates to a corresponding system an interface unit and a computer program product.

Next some embodiments of the invention will be described in more detail with reference to . In the following description the originating side is the side and corresponding network elements from where the call originates as opposed to terminating side which is the side and corresponding network elements where the call terminates. Furthermore in the following description the TDM IN operates in accordance with global system for mobile communications customized applications for mobile network enhanced logic GSM CAMEL standard but the IN could equally use any other TDM communication standard.

The IU uses a first access protocol in this example ISC SIP to communicate with the S CSCF and a second access protocol in this case INAP protocol to communicate with the IN .

The IU of is interfacing with an external S CSCF . However it is also possible to embed a dedicated S CSCF function into the IU . In the latter case the IU behaves like a standard IMS S CSCF .

The S CSCF is responsible for sending the IMS call over the ISC interface to each of the relevant ASs . ASs are instructed by the S CSCF to return the call signaling after appropriate processing to the S CSCF which can then send the call signaling to the next AS . This property is used to enable access to many applications designed on top of an IMS AS from a TDM IN . This is achieved by emulating IMS entities on top of an IN SCP .

The IU when invoked by the IN is arranged to give instructions regarding the processing of a call to simulate a 3GPP SIP call to the target AS s relayed by a P CSCF if the call is from a TDM terminal or I CSCF if the call is directed to a TDM terminal.

The calls of subscribers get specific processing depending on whether the call originates from the IN or from the IMS network .

For sessions originating from the IN the call control is directed to the IU which further relays the call to the S CSCF . The call will get back to the S CSCF after processing by each AS and the S CSCF routes this call to the IU as last originating side AS . This enables the IU to analyze the modifications affecting the call signaling after processing by the ASs and convert these modifications as appropriate for the I N call model if possible and necessary.

For incoming calls from the IMS network the call will reach the IU because the IU registers the SIP address of record AoR the public identity of the endpoint of the endpoints it controls onto the S CSCF .

The IU sends TDM calls received on the terminating side i.e. to the GSM user to the IMS network . This is achieved by the IU emulating the I CSCF sending a call from another network or S CSCF to the S CSCF of the target user.

Many IMS applications can be converted in an optimal way to proper INAP primitives. For instance an IMS service implementing a short numbering plan for an enterprise modifies only calling and called numbers or generates announcements. The IU can detect whether a call is GSM to GSM and in this case sends the customized applications for mobile network enhanced logic CAMEL an IN protocol with extensions for GSM networks instruction to the GSM mobile switching centre MSC a TDM switch with an IN call model to route the call after modification of the calling or called parties.

In a GSM network a user of an application using the IU will need to have a CAMEL trigger defined for all relevant incoming DP and outgoing DP calls. This is defined in the GSM home location register HLR as part of the profile of that user. In other TDM INs the IN switches also need to be configured to send an INAP initial detection point to the IU for any outgoing or incoming call. The way to configure this depends on the TDM network vendor but usually involves a service mark e.g. specific configuration information in the access TDM switch linked to the physical access link to the user.

If the call is GSM to VoIP e.g. to an IP phone then the IU may decide to execute the application logic in the IN network or later when the call is processed by the VoIP network. If the AS application logic generates an announcement then the IU instructs the MSC to connect the call to the VoIP announcement server through a VoIP gateway.

The IU is not invoked for VoIP to VoIP calls as the application logic used will be that of the IMS AS and does not require any adaptation.

For eliminating tromboning the IU identifies TDM to TDM calls and emulates the IMS AS application logic using INAP commands to the TDM IN switches of the calling and called party users.

The IU needs to be made aware of any outgoing or incoming calls from terminals having the phone numbers that must be controlled by the IMS network . This is achieved by registering the IU logic as INAP trigger detection point TDP R .

Calls are routed through a voice over internet gateway over the IMS at least in one of the following situations TDM to IP calls IP to TDM calls or when call handling capabilities of the AS exceed the capabilities of a SSP of the IN . The call routing is done by the IN instructing an SSP of the IN to route the call through a voice over internet gateway over the IMS .

Next an exemplary embodiment of the invention is described with reference to the flow chart of . In this embodiment of the invention the destination is reachable through the TDM IN and the call is received from the IN which operates in accordance with a GSM standard.

At step the IU receives an Initial DP service request i.e. an incoming call from the originating IN SSP of an incoming call from the IN . Then at step by emulating the operation of the P CSCF or access gateway control function AGCF in the TISPAN IMS variant the IU sends a SIP INVITE message to the S CSCF of this user possibly through an I CSCF if the service provider has so configured its IMS network . The S CSCF then executes the service triggers defined for this user by propagating step the SIP INVITE message to a sequence of originating ASs which may relay and modify step any parameter of the SIP INVITE message or even absorb it.

Next at step the last AS sends the processed SIP INVITE message to the S CSCF and S CSCF forwards step the processed SIP INVITE message to the IU . This is achieved by defining the IU as the last originating AS for this user s identity in the user HSS profile in this case originating and terminating sides are handled separately but it is also possible to wait until the SIP call returns to the terminating side IU in which case the IU will execute in one step both originating and terminating services. This is called here as a variation SIMPLE .

Next at step the IU accesses the processed SIP INVITE message parameters as modified by the sequence of originating ASs invoked by the S CSCF . The originating side IU when it receives the SIP INVITE message processed by the sequence of originating side ASs analyses step the new destination number or uniform resource identifier URI as modified by the ASs . For instance the ASs may have expanded a short number e.g. 1234 into a public format such as 33 671201234.

If the IU determines step that the destination number at this stage is reachable in TDM mode by the SSP it instructs the SSP to propagate step the call over TDM IN using the appropriate CAMEL commands. The reachability may be determined by multiple means e.g. by using number pattern analysis i.e. number belongs to a number block which is part of the IN local number portability query carrier for this number corresponds to the IN or HLR query for GSM networks. Several of these reachability determination methods can be used simultaneously.

The destination user may have set its profile to redirect the call to another destination. If the new destination is TDM or if the call has not been redirected then the call flow is optimized end to end over TDM. However if the new destination is IP then a VoIP gateway will be invoked on the terminating side. This can be achieved by instructing the IN SSP to route the call to a VoIP gateway acting as an Intelligent Peripheral. The MRF could act for this purpose as the VoIP gateway. This method effectively gives precedence to the TDM path over the IP path by the originating IU .

If the destination is an endpoint also controlled by the IMS service logic its IU will be invoked by a CAMEL Initial DP command from the SSP running on the originating side in the CAMEL model . The IU managing the destination endpoint sends a SIP INVITE message to the terminating side S CSCF of the corresponding user identity and the terminating side S CSCF invokes the terminating side ASs as configured in the HSS profile of this user s identity.

The terminating side IU then receives an SIP INVITE message processed by the sequence of terminating side ASs because the IU registered the corresponding address of record. In the SIMPLE variation the terminating IU communicates modified call parameters to the originating IU at this stage triggering the routing process described earlier. The terminating side IU instructs the SSP to connect the call if the modified destination is reachable by this SSP .

Any of the originating side ASs may terminate the call locally e.g. to an announcement specifying that the call has been blocked. In this case the IU does not receive the SIP INVITE message of step . Instead the originating side IU receives a session description protocol SDP answer and connects the GSM terminal to the announcement through a VoIP gateway. It is also possible that any of the terminating side ASs terminates the call locally e.g. to an announcement specifying that the call has been blocked.

If the originating side IU determines at step that the destination number at this level is not reachable in TDM mode by the SSP it acts as a non concerned AS by returning step the SIP INVITE message to the S CSCF unmodified with an SIP contact header allowing the S CSCF to by pass this AS for any subsequent message.

The terminating side S CSCF then redirects step the call to another destination. If the destination is in IP network as is the case for a normal call not redirected by the destination then the TDM to IP call flow is optimized and the VoIP gateway used is that controlled by the originating IU and the MRF acts as a VoIP gateway.

However if the destination redirects the call to a TDM destination the TDM shortcut will be established by the originating side IU if it runs on the same IU as the terminating side IU .

The procedures described above need to be simplified if IN supports only CS 1 or CAMEL. The CAMEL protocol has major limitations no half leg call model which do not allow conversion from AS commands to IN commands in the general sense.

However mapping to IN can be performed provided that the application logic complies with the following limitations 

These limitations still allow implementation of sophisticated services. For instance the following applications are possible number conversion e.g. short numbering plans call filtering accounting call forwarding anonymous call blocking computer telephony interface CTI call supervision. These are examples of call services which do not require a dynamic update of media streams i.e. not more than one SDP offer answer is required. If an AS needs to provide a service to a mobile end user which requires dynamic update of media streams then the first media termination port provided to the caller needs to be an IP port.

The invention also relates to the corresponding computer program product that is capable of implementing the method in accordance with the embodiments of the invention when loaded and run on computer means of the network.

Furthermore the invention relates to a corresponding system that comprises at least the IU that is arranged to perform any of the method steps in accordance with the embodiments of the invention. The system may further comprise at least some elements of the IN and the IMS network .

Above the invention was described by use of some exemplary embodiments. However it is to be noted that the invention is not limited to those examples but the scope of the invention can vary within the appended claims.

