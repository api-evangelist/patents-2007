---

title: Method of processing open asynchronous application service event and open web service gateway implementing the same
abstract: A method of processing an open asynchronous application service event and an open web service gateway implementing the method are provided. The open web service gateway includes: a plurality of SCFs (service capability features) operatively connected to an application service through a web service interface, receives an event registration request from the application service, and notifies an event occurring in a network to the application service; and an event broker registering the registration-requested based on a predetermined policy in correspondence with the SCFs, when the registration-requested event received from the application service is an asynchronous event, and notifies an occurrence of the event in the network to the SCFs according to a registered priority of the event. Accordingly, an asynchronous event is registered and notified based on a predetermined policy, so that it is possible to prevent event registration conflict between the SCFs and between the application services and to maximize network operation efficiency.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08046419&OS=08046419&RS=08046419
owner: Electronics and Telecommunications Research Institute
number: 08046419
owner_city: Daejeon
owner_country: KR
publication_date: 20071129
---
This application claims the priorities of Korean Patent Application No. 10 2006 0120968 filed on Dec. 1 2006 and No. 10 2007 0082152 filed on Aug. 16 2007 in the Korean Intellectual Property Office the disclosure of which is incorporated herein by reference.

The present invention relates to a method of processing an open asynchronous application service event and an open web service gateway implementing the method and more particularly to a method of processing an open asynchronous application service event capable of registering and notifying an asynchronous event based on a predetermined policy and an open web service gateway implementing the method. This work was supported by the IT R D program of MIC IITA Project No. 2005 S 056 02 Project Name Development of Open API and Service Platform Technologies .

In general in an open system an open web service gateway provides a standard web service application programming interface API so that a third party service provider can easily generate a service without knowledge of low layers of a network. In addition the open web service gateway provides functions such as presence information notification terminal state notification terminal location notification call notification and SMS message transmission in units of service capability feature SCF .

The open web service gateway provides an interface to an application service which is to use the SCF so that the application service can invoke the API in a web service format. Operations for processing the API that is invoked by the application service are divided into synchronous and asynchronous operations according to functions of the SCF.

The asynchronous operation is performed to notify presence terminal state terminal location call or other events which occur in the network.

In addition before the event notification the application service needs register event conditions in advance by using the API provided from the open web service gateway.

More specifically in the asynchronous operation the application service registers a specific event in the open web service gateway in advance. When the registered event occurs in the network the SCF associated with the event notifies the generation of the event to the application service.

However in a conventional event registration procedure an event having the same event condition may be registered by a plurality of application services. In this case event notification conflict occurs.

Therefore according to a feature of an application service or an event the application service is designed to be invoked one time per event. Otherwise different events are designed to be sequentially notified to different application services. However in event registration logic the event notification conditions are not considered.

Therefore in a case where the registered event is generated from a plurality of the application services without any arbitration unpredicted event notification may be performed so that conflict of event notification between application services or between SCFs in the open web service gateway may occur. Accordingly there is a need for a method and apparatus capable of preventing the event notification conflict.

An aspect of the present invention provides a method of processing an open asynchronous application service event and an open web service gateway implementing the method capable of notifying an event without conflict between application services and between SCFs service capability features in the open web service gateway.

According to an aspect of the present invention there is provided an open web service gateway comprising a plurality of SCFs service capability features operatively connected to an application service through a web service interface receiving an event registration request from the application service and notifying an event occurring in a network to the application service and an event broker registering the registration requested based on a predetermined policy in correspondence with the SCFs when the registration requested event received from the application service is an asynchronous event and notifying an occurrence of the event in the network to the SCFs according to a registered priority of the event.

In the above aspect of the present invention when an event registration conflict is predicted in the registration of the registration requested event received from the application service due to existence of registration information on an event equal to the registration requested event the event broker may determine an event registration priority based on a policy corresponding to the predicted conflict to register the event.

In the above aspect of the present invention the event registration information includes at least one of the event information event associated terminal number information event registration SCF information EndPoint information registration date information and priority information.

In addition the event broker may use the information of the event that occurs in the network and the event associated terminal number as a triggering condition to determine the event registration information corresponding to the triggering condition and notifies the occurrence of the event to the SCF included in the determined event registration information.

In addition when the number of event registration information corresponding to the triggering condition is one the event broker may notify the occurrence of the event to the SCF included in the one registration information and when the number of event registration information corresponding to the triggering condition is two or more the event broker may sequentially notify the occurrence of the event to the SCFs included in the two or more registration information according to the priorities of the registration information.

In addition when the number of event registration information corresponding to the triggering condition is two or more the event broker may determine the priorities of the registration information when there is registration information having a priority of 0 the event broker may notify the occurrence of the event to the SCF included in the registration information having the priority of 0 and when there is no registration information having the priority of 0 the event broker may sequentially notify the occurrence of the event to the SCFs included in the registration information according to the priorities of the registration information.

In addition when there is no registration information having the priority of 0 the event broker may determine whether or not the number of the SCFs included in the registration information is two or more when the number of the SCFs is two or more the event broker may sequentially notify the occurrence of the event to the SCFs included in the registration information according to the priorities of the registration information and when the number of the SCFs is one the event broker may transmit a plurality of the event information corresponding to the registration information and the priority information thereof to the one SCF.

In addition when a plurality of the event information and the priority information are transmitted from the event broker the SCF sequentially transmits the events of the registration information to the application service in the order of the priorities included in the priority information.

In addition the SCF may comprise a web service processing unit providing the web service interface to the application service so that the application service can access to the SCF and a logic processing unit determining the registration requested event received from the accessed application service to identify asynchronous and synchronous events transmitting the registration request of the event identified as the asynchronous event to the event broker and transmits the notification requested event received from the event broker to the application service.

In addition the open web service gateway may further comprise a policy DB storing a plurality of policy data corresponding to the policy.

In addition the open web service gateway may further comprise a gateway OAM operation and maintenance processing unit generating modifying and removing the policy data.

According to another aspect of the present invention there is provided a method of processing an open asynchronous application service event including a plurality of SCFs service capability features the method comprising receiving an event registration request transmitted from an application service through the SCF an event registration of registering the registration requested event according to the SCF based on a predetermined policy when the event received through the SCF is an asynchronous event receiving an event occurring in a network and event notification of notifying the event occurring in the network to the application service according to a registered priority through the SCF.

In the above aspect of the present invention the event registration may comprise determining whether or not registration information on an event equal to the registration requested event exists previously and when an event registration conflict is predicted in the registration of the registration requested event due to the existence of the event equal to the registration requested event determining an event registration priority based on a policy corresponding to the predicted conflict to register the event.

In addition in the registration event registration information may include at least one of the event information event associated terminal number information event registration SCF information EndPoint information registration date information and priority information is registered.

In addition the event notification may comprise using the information of the event that occurs in the network and the event associated terminal number as a triggering condition to determine the event registration information corresponding to the triggering condition and notifying the event that occurs in the network to the application service through the SCF included in the determined event registration information.

In addition in the event notification when the number of event registration information corresponding to the triggering condition is one the event that occurs in the network may be notified to the application service through the SCF included in the one registration information.

In addition the event notification may comprise when the number of the event registration information corresponding to the triggering condition is two or more determining the priority of the registration information and determining whether or not there is registration information having a priority of 0 when there is registration information having the priority of 0 notifying the event that occurs in the network to the application service through the SCF included in the registration information and when there is no registration information having the priority of 0 determining whether or not the number of the SCFs included in the registration information is two or more and when the number of the SCFs included in the registration information is two or more sequentially notifying the event that occurs in the network to the application service through the SCF included in the registration information according the priority of the registration information.

In addition the event notification may further comprise when the number of the SCFs determined from the registration information is one SCF s sequentially notifying the event of the registration information to the application service in the order of the priority according to priority information of the registration information.

According to the method and apparatus for processing an open asynchronous application service event an asynchronous event is registered and notified based on a predetermined policy so that it is possible to prevent event registration conflict between the SCFs and between the application services and to maximize network operation efficiency.

In addition according to the method and apparatus for processing an open asynchronous application service event a priority for event notification is determined based on a policy set by a network operator so that it is possible to easily perform a dynamical change of the event notification policy.

Hereinafter exemplary embodiments of the present invention will now be described in detail with reference to the accompanying drawings. For clarifying of the present invention description of well known functions structures configuration or constructions may be omitted.

Referring to the open system includes an open web service gateway application service terminals and which are connected to a wire network a wireless network and an Internet Protocol IP network.

The open web service gateway provides an interface through which the application service can invoke an application programming interface API in a web service format so as to use service capability features SCFs which is set therein. The open web service gateway abstract functions for the wire wireless and IP networks as open APIs and provides the APIs in the web service format.

The open web service gateway can be operatively connected to at least one open application service . In addition the open web service gateway can be operatively connected to at least one protocol such as a wireless application protocol wireless intelligent network WAP WIN an intelligent network application protocol INAP and session initiation protocol SIP so as to provide the web service to a plurality of networks.

The open web service gateway provides functions of three way calling connection call event notification short message service SMS multimedia message transmission presence information notification terminal state information notification terminal location notification and the like in which the different functions are implemented by using different SCFs.

The application service performs an open application service by using an application service logic and the open API in cooperation with the open web service gateway .

When the application service requests for registration of an event the open web service gateway registers an event according to a predetermined policy. When an event occurs in a network the open web service gateway notifies the event to the application service according to a registered priority of the event.

As shown in the open web service gateway is constructed with a plurality of SCFs including a web service processing unit and a logic processing unit an event broker including an event DB a policy DB a protocol message processing unit and gateway operation and maintenance OAM processing unit .

In the open web service gateway the web service processing unit of each SCF provides the web service interface to the application service so that the application service can be connected to the open web service gateway through the web service interface.

The logic processing unit performs SCF functions such as presence information notification terminal state information notification terminal location notification call notification and SMS message transmission. The logic processing unit implements an event registration processing logic in response to an event registration request of the application service that is transmitted through the web service processing unit .

The event broker implements an event registration logic in response to the event registration request which is transmitted from an SCF which is to be subject to an asynchronous operation process that is an SCF which performs event registration and notification functions. The event broker implements an event notification logic for an event which occurs in the network. Therefore the event broker allows the event to be registered and notified based on a policy of the policy DB that is described later.

The event broker manages registration information of an registration request event by using the event DB . The registration information is arbitrated based on policy data acquired from the policy DB .

For the implementation of the event registration logic associated with the event registration request the event broker checks conflict between the registration requested event and event registration information stored in the event DB . If there is conflict the conflict is resolved according to a policy searched from the policy DB and after that the registration requested event is registered.

The policy DB stores and manages the policy data that a network operator inputs through the gateway OAM processing unit .

The protocol message processing unit provides to the network the registration requested event of which registration is requested by the application service . The protocol message processing unit notifies to the SCFs the events that occur in the network.

Referring to the event registration information is managed in a formation of table. The event registration information includes event information event associated terminal number information event registration SCF information EndPoint information registration date information priority information and the like. The event associated terminal number information and the event information are used as event triggering conditions. The conditions of the notification requested event information are checked and notified to the notification requested event registration SCF.

In the event registration information table the priority information and the registration date information are used for the event broker sequentially notifying to the SCFs the events of which event triggering conditions occur.

More specifically the event broker allocates the highest priority to the priority 0 event so that the event can be notified exclusively. The event broker notifies events except for the priority 0 event in the order of registration date and priority.

Now operations of the open web service gateway performing the event registration and notification is described in detail.

As shown in when the application service is to generate an event in the network the application service accesses the SCF web service processing unit of the open web service gateway through the web service interface to invoke the event registration API for the event registration request S .

When the application service requests for the event registration the web service processing unit invokes an event registration processing logic of the logic processing unit in response to the event registration request of the application service S . In the implementation of the event registration processing logic the logic processing unit determines whether the registration requested event of the application service is to be subject to asynchronous or synchronous operation process S .

If the registration requested event condition of the application service is determined to be synchronous through the event registration processing logic the logic processing unit transmits the registration requested event to the protocol message processing unit by using a protocol message to provide the event to the network S . If the registration requested event condition of the application service is determined to be asynchronous through the event registration processing logic the logic processing unit requests the event broker to perform the event registration S .

When the event registration is requested by the SCF logic processing unit the event broker performs the event registration logic based on the policy information acquired from the policy DB to register the event S .

When the registration requested event is registered in the event DB according to the event registration logic the event broker transmits the registered event to the protocol message processing unit by using the protocol message to provide the event to the network S .

The event registration logic shown in is an event registration logic performed by the event broker of the open web service gateway .

Referring to when the event registration is requested by the SCF logic processing unit the event broker checks the registration requested event S . Next the event broker invokes the event registration information table from the event DB S .

Next the event broker determines whether or not event information equal to the registration requested event exists in the invoked event registration information table S . If the event information equal to the registration requested event is determined not to exist the event broker registers the registration requested event in the event DB S .

However if the event information equal to the registration requested event exists in the event registration information table the registration requested event may cause event registration conflict. Therefore if the event information equal to the registration requested event is determined to exist the event broker searches the policy DB S and invokes the policy data corresponding to the predicted event registration conflict S .

The event registration conflict may be event registration conflict in one SCF event registration conflict between SCFs or event registration conflict between application services .

In other words the event registration conflict may occur in a case where a registration requested event of SCF exists previously a case where a registration requested event of an arbitrary is previously registered in another SCF or a case where a registration requested event of an application service exists previously.

The event broker determines an event registration priority based on the invoked policy and registers the registration requested event together with the determined priority information in the event DB S .

When the event registration priority cannot be determined based on the invoked policy data the event broker accesses and requests the gateway OAM processing unit to supplement the invoked policy.

As shown in when the event occurs in the network S the protocol message processing unit of the open web service gateway transmits the received event to the event broker by using a protocol message S .

When the event is transmitted from the protocol message processing unit the event broker performs an event notification logic S . Next the event broker transmits the event to an SCF that is determined to be a destination of the event transmission according to the event notification logic S .

The SCF receives the event from the event broker through the logic processing unit . The SCF determines the application service that is to be notified with the received event. The SCF allows the web service processing unit to perform the event notification to the determined application service in response to invoke of the event notification API S and S .

The event notification logic shown in is an event notification logic performed by the event broker of the open web service gateway .

Referring to when the event is received from the protocol message processing unit S the event broker invokes the event registration information table from the event DB S .

The event broker determines based on the registration information corresponding to the received event in the event registration information table whether or not the number of registration information is equal to or larger than two S .

If the number of registration information corresponding to the received event is determined to be one the event broker transmits the received event to the SCF included in the registration information S .

If the number of registration information corresponding to the received event is determined to be equal to or larger than two the event broker determines whether or not there is registration information having a priority of 0 S .

If there is registration information having a priority of 0 the event broker transmits the received event to the SCF included in the registration information S . If there is no registration information having a priority of 0 the event broker determines whether or not the number of the SCFs that are determined from the registration information corresponding to the received event is two or more S .

If the number of SCFs included in the registration information corresponding to the received event is determined to be equal to or larger than two the event broker sequentially transmits the received event to the SCFs included in the registration information according to the priority of the registration information S .

If the number of SCFs included in the registration information corresponding to the received event is determined to be one the event broker determines that the registration information is generated from one SCF and transmits the event information and the priority information included in the registration information to the SCF S .

Accordingly the SCF can sequentially transmit the events to the application service in the order of priority of the registration information that is transmitted from the event broker .

While the present invention has been shown and described in connection with the exemplary embodiments it will be apparent to those skilled in the art that modifications and variations can be made without departing from the spirit and scope of the invention as defined by the appended claims.

