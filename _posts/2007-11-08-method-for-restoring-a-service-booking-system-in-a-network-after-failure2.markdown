---

title: Method for restoring a service booking system in a network after failure
abstract: A method for restoring a service reservation booking system in a network after a failure, that comprises a first step of invalidating at least a portion of the bookings which cannot be seen anymore by the service booking system due to the failure, a second step of recalculating the bookings which cannot be seen anymore by the service booking system by validating the bookings which are valid in the network topology after the failure and by cancelling the bookings which are invalid in the network topology after the failure. Advantageously, the method of the present invention further includes a third step during which the nodes of the network disappear from the service booking system. The present invention also includes to a service booking system in a network.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09544246&OS=09544246&RS=09544246
owner: THOMSON LICENSING
number: 09544246
owner_city: Boulogne-Billancourt
owner_country: FR
publication_date: 20071108
---
This application claims the benefit under 35 U.S.C. 365 of International Application PCT FR2007 052314 filed November 8 2007 which was published in accordance with PCT Article 21 2 on May 15 2008 in English and which claims the benefit of French patent application No. 0654843 filed Nov. 10 2006.

The present invention relates more specifically to a method for restoration of a network service reservation system after a failure. The method applies to loop free networks that is that at a given instant there is a unique path between two points of the network and this unique path is only modified by a change in the topology of the network. In the sense of the present invention a service reservation system is a centralised system that ensures a service on a network path between two points of a loop free network.

Quite often the systems of the prior art did not take into account the fact that network failures can take place. When a failure takes place the reservation system suffers a crash and does not return to a stable condition.

The prior art already knows methods and systems for restoring the link on a network that is methods and systems that consist in re establishing the transmission of data between two points on a network.

In a loop free network there is a single path between two points on the network. A network failure therefore cuts the transmission of data at the point of failure. The traffic cannot be re routed in a loop free network. The traffic can resume if the network if the network re establishes links to transmit the data. This can be done manually by the addition of network equipment or via protocol as the STP Spanning Tree Protocol protocol does which searches for redundant links that were previously deactivated to create the loop free network. This aspect of re establishment of data transmission works currently and is not the object of the present invention.

When a centralised system manages a service reservation system that is controls the access to the service and ensures the requested service it updates the status of the reservations on the network. When there is a network failure the topology of the network can be modified suppression of a network node service degradation on some links or even disappearance of entire parts of the network. Likewise it is possible that new elements appear particularly after a network failure addition of a network node appearance of new links or even improvement of the service on a link.

In the case of a network failure the information concerning service reservations can be no longer coherent for example for a service reserved on a part of the network that has disappeared. In this case it is necessary to implement mechanisms internal to service management to again render coherent the information and more generally the service management.

The prior art knows from the American patent application US 2005 0063701 a method and a system to restore resources upon the occurrence of a data burst loss in optical communication networks based on WDM Wavelength Division Multiplexing protocol. This American patent application describes a mechanism for the reservation of resources shared at the level of each item of network equipment thus a distributed architecture for this mechanism. This document of the prior art introduces a means to refuse and or stop a communication when this latter leads at the level of at least one of the items of core network equipment to the detection of a failure network overload broken link etc . The architecture implemented in this American patent application is entirely distributed and does not rely on a centralised knowledge of the topology. The control command of this prior mechanism uses a wavelength attributed only to the exchange of system data.

The present invention intends to overcome the disadvantages of the prior art by proposing a method that enables the return to operation of a services manager in a loop free network which implicates manager internal operations.

The present invention relates to a centralised mechanism for the recovery of established resource reservations with respect to a centralised management of the topology. When the topology manager detects a change it informs the resources manager that detects possible conflicts failures introduced by this new topology on the reservations of resources previously established and attempts to automatically resolve them by contacting the nodes concerned or by alerting the system user. It is to be noted that the control command of this mechanism uses a packet mode protocol using a unique identifier address port number attributed at the exchange of these packets.

The present invention is based on a centralised knowledge of the topology while the architecture implemented in the American patent application US 2005 0063701 is entirely distributed.

For this purpose the present invent relates in its most generally accepted sense to a method for restoration of a service reservation system on a network after a failure comprising a first step consisting of invalidating at least some of the reservations that are no longer visible to said service reservation system due to said failure a second step consisting in recalculating said reservations that are no longer visible to said service reservation system while validating the reservations that are valid in the network topology after said failure and cancelling reservations that are invalid in the network topology after said failure.

Advantageously said method also comprises a step during which the network nodes disappear from the service reservation system.

According to a specific embodiment the disappearance of nodes at the level of the service reservation system takes place at the expiration of a predetermined delay.

The present invention also relates to a network service reservation system characterized in that it comprises 

The method according to the present invention applies to loop free networks that is that at a given instant there is a unique path between two points of the network and this unique path is only modified by a change in the topology of the network. By network failure is understood in the sense of the present invention a modification in the network topology that renders completely unusable or progressively degraded one or several network link s . In the sense of the present invention a service reservation system is a centralised system that ensures a service on a network path between two points of a loop free network.

In the present invention the service manager is based on an entity that enables it to have a current view of the network topology that it manages.

Service reservations take place on a path between two network nodes. The communications traffic between the service manager and the items of network equipment that send service reservation requests have the highest priority.

The service manager maintains a list of granted service reservations. This list can take the following form 

When a service user wants to quit the network he must release all his service reservations before quitting the network.

On can be seen a camera service user that requests a reservation of bandwidth to the monitor from the bandwidth manager. This reservation has been granted and the network operates correctly. The data exchanges transit via the switch S.

On the camera quits the network without releasing the service reservation. Here the reservation is still taken into account by the bandwidth manager but does not exist in reality.

The service manager sees on its topology that the service user is no longer there and can envisage two scenarios 

It can be decided to release the service reservation for both scenarios to reuse the service the service user must perform a new service reservation request. This case presents a problem if the service user quits the network and returns thinking that his service reservation is still active. In this situation the user of the service uses a service that is not reserved.

In the preceding example the camera of could have not detected that the link is no longer working and could therefore once the link is re established still transmit traffic thinking that the bandwidth is reserved.

In what follows it is considered that the service users are not aware of possible failures in the network. This explains the decision to consider that when a service user wants to quit the network he must release all his service reservations before quitting the network.

In the following example a network failure is repaired by modifying the network topology. This modification provokes conflicts between reservations.

In our example the links are Ethernet 100 Mbits s with the exception of the link between switches and which are at 1 GBits s.

The present invent is not limited to bandwidth it also applies to other types of service between two points of a loop free network for example those presented above.

In the network of this example shown in the reserved streams were granted by the bandwidth manager from camera to monitor from camera to monitor from camera to monitor and from camera to monitor .

The different steps of the method according to the present invention are shown in . This shows the restoration of a reservation during a complete failure of a link or of an item of equipment.

The state diagram presented in this figure describes the operation of a reservation. The various reservations of the preceding example Table 2 are found in the initial state Valid.

Next the switch experiences a failure. The service bandwidth manager only sees the left side of the network switch switch switch switch monitor monitor and camera . The failure of switch is shown in .

The service bandwidth manager could have chosen to delete from its table all reservations that had partially disappeared from the network topology that is to only conserve reservation . However this decision would pose certain problems. In fact reservation still works and so when the network is repaired this reservation should not be removed as it has always worked. Hence in order to indicate that a reservation is perhaps invalid but that this is not affirmed the value Valid must be changed to In standby . The state machine of reservations and passes to the In standby state. The links of reservation have not disappeared its state therefore remains as Valid .

All of the streams arriving at switch were routed to switch . All the reservation sources destinations currently in the state In standby reappear on the network. As the state machine indicates in the reservations and pass therefore into the state Restoration . This state passes the value Validity to Restoration .

Once the services manager again finds the network equipment that are implicated in a service reservation it must restore all the restorable reservations that is those for which the two network nodes and a path exist in the topology of the current network. Naturally if the two network nodes or a path do not exist it is not possible to realise the operation on the reservation.

A non restorable reservation detected following the disappearance of two network nodes and paths is considered as being definitive. This definitive character can be determined using a reappearance delay. Before the detection of the definitive character of the disappearance a non restorable reservation remains in the In standby state.

The first step in the restoration is the processing of all the restorable reservations. The service manager must validate the reservations that are valid and must detect the impossible reservations.

Hence the switch can be seen by the services manager and reservation can be re validated due to the fact that the path is the same as before the failure. The bandwidth is still available after the topology reshaping. The state machine of reservation returns therefore to the Valid state. The Validity value is returned to Valid .

As for reservation a path still exists between the source and the destination. The difference is that the stream passes via switch instead of passing via switch . As for reservation reservation can therefore be re validated. Its state machine returns to the Valid state and the Validity value is returned to Valid .

Reservation poses some problems it is an impossible reservation. Even if the services manager sent a request for release to camera this latter would not have received it before connecting to the network. Thus the camera has enough time to send the stream via the new network topology before receiving the request for release from the manager. In this case the link at 100 Mbits s between switch and switch cannot support two 80 Mbits s streams. Here two streams reservations and will not be correctly transported. The service is no longer assured for reservation that was not affected by the failure of switch before the reshaping of the topology.

An impossible reservation is a restorable reservation that it is impossible to ensure in the new network topology. These reservations must be noted in the Failed state.

The next step consists in requesting the release of reservations noted in the Failed state so as to establish a coherent operation of the services reservation system.

In our example the services manager must request a release for reservation as the link cannot support this reservation on the link between the switches and due to the existence of reservation . Once the release of reservation is carried out the reservation manager deletes the reservation from its table. The service reservation system is again coherent and the table no longer contains reservations in the In standby state or in the Failed state the service reservation is once again assured.

The second step of the restoration of the service reservation system is the activation of non restorable reservations. This is the situation in which some nodes of a service reservation do not return in the network topology.

Once this disappearance is considered as definitive the machine state of the reservation passes to the state Non restorable . This case cannot be treated automatically by the service manager.

An external decision must release these reservations. It is understood by external decision in the sense of the present invention a decision coming from an individual person or a module that possesses more knowledge and a more important degree of command on the service type in such a way to be able to manage the following steps which are 

The external decision must ensure the coherence of information on the different devices involved in the reservations to be released.

Using the method according to the present invention it is possible to restore the reservation system following a network failure. These failures in the sense of the present invention can be complete failures of a link or of an item of equipment but also the degradation of a link or item of equipment.

This progressive approach of the degradation enables management of cases in which the network progressively loses the means to ensure a service reaching a point where the service reservations granted are no longer guaranteed.

The service manager ensures the service reservations basing itself on the state of the network at the time of the service reservation. As the state of the network changes with time some parameters required for service reservation can become degraded. There is a problem from the point when the degradation of these parameters acquires an importance such that the service can no longer be ensured on the network link in question.

A network degradation must be treated in a different way to a complete network failure for the following two reasons 

If the required parameters are parameters linked to the network topology the service manager can detect a disturbing degradation and notify the two nodes of the service reservation linked to this degradation.

If network degradation becomes so important that a reservation is in the failed state the service reservation system restores this can be activated reservation. As long as the network link is not in complete failure the management traffic is transported on this link as it has the highest priority. The communications between the service manager and the applicant are the following 

The service reservation system has been restored following the failure of the service reservation due to degradation.

The invention is described in the preceding text as an example. It is understood that those skilled in the art are capable of producing variants of the invention without leaving the scope of the patent.

