---

title: Providing independent verification of information in a public forum
abstract: A social networking site host includes, in a user's profile, information that has been attested to and verified by both the user and an independent verifier. The independent verifier is an accepted authority with direct knowledge of the information. Both the user and verifier attest to the information by digitally signing the information and including the digital signature with the information. The host or visitors to the social networking site can authenticate the information by using both digital signatures. By authenticating the information, visitors and users viewing information on the social networking site can assume that the information is trusted and accurate.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09660812&OS=09660812&RS=09660812
owner: Red Hat, Inc.
number: 09660812
owner_city: Raleigh
owner_country: US
publication_date: 20070228
---
Recently the rapid growth of social networking sites such as MySpace and Facebook has revealed a new trend of Internet usage. Social networking generally relates to services and tools that help users maintain and expand their circles of friends usually by exploiting existing relationships. Social networking sites have shown potential to become the places on the Internet where many people spend most of their time thus making these sites the main entry point for online activity. Often times these social networking sites can become the focal point of sharing information such as links multimedia music and the like. Additionally the social networking sites allow users to present personal profiles of themselves to visitors of the social networking sites.

Unfortunately visitors to the social networking sites have no way to determine if the information contained therein is authentic and accurate. Typically the users place information in the social networking sites without providing any type of independent verification of the information. Accordingly all the information contained therein is self asserted and unverified. As such visitors to the social networking sites may not be able to trust the information contained therein. This prevents visitors to the social networking sites from using the information to verify important personal information such as employment history or education. Accordingly it may be desirable to provide methods and systems that provide information in the social network which is independently verified.

Embodiments of the present disclosure concern methods and systems for providing independently verified information in a public forum. In particular a social networking site host includes in a user s profile information that has been attested to and verified by both the user and an independent verifier. The independent verifier is an accepted authority with direct knowledge of the information. Both the user and verifier attest to the information by digitally signing the information and including the digital signature with the information. The host or visitors to the social networking site can authenticate the information by using both digital signatures. By authenticating the information visitors and users viewing information on the social networking site can assume that the information is trusted and accurate.

Reference will now be made in detail to the exemplary embodiments of the invention which are illustrated in the accompanying drawings. Wherever possible the same reference numbers will be used throughout the drawings to refer to the same or like parts.

Host serves as a social network service and stores manages and provides access to the social networking site. In general host is essentially a website host and application service that stores manages and publishes information shared by users as well as user profiles and social network information. Host may be hosted as a public social networking site similar in fashion to a service such as MYSPACE or linkedin. In addition host may provide various application programming interfaces that have an open specification so that anyone can create an interface. Further host may create authenticate and incorporate independently verified information of user into the social networking site.

Host may be implemented using a variety of devices and software. For example host may be implemented as a website running on one or more servers that support various application programs and stored procedures.

User provides an interface for creating and updating a profile in the social networking site maintained by host . User may register with host and create a profile in the social networking site. User may post information on the social network site including independently verified information. For example user may create a profile in which user includes personal information such as biographic information employment history and education.

Verifier provides an interface for an entity to provide independent verification of information in the social networking site. Verifier may be an accepted authority of the information to which verifier is providing verification. For example if a user would like to provide verified employment history verifier may be the past or present employer of user . Verifier may be capable of verifying information from user and providing an attestation such as a digital signature to the information.

Visitor provides an interface for viewing a profile in the social networking service maintained by host . Visitor may access the social networking site and view information about user of the social network site. Visitor may also authenticate the independently verified information in a user profile.

User verifier and visitor may be implemented using a variety of devices and software. For example user verifier and visitor may be implemented on a personal computer workstation or terminal. In addition user verifier and visitor may run under an operating system such as the LINUX operating system the MICROSOFT WINDOWS operating system and the like. User verifier and visitor may also operate through an Internet browser application such as FIREFOX by Mozilla INTERNET EXPLORER by Microsoft Corporation or NETSCAPE NAVIGATOR by Netscape Communications Corporation.

One skilled in the art will also recognize that user verifier and visitor may be implemented with various peripheral devices such as a display one or more speakers and other suitable devices. User verifier and visitor may also be implemented with various peripherals for accepting input from a user such as a keyboard a mouse and the like. Although shows one user verifier and visitor system may include any number of users verifiers and visitors . Further one skilled in the art will realize that user may also be a visitor or verifier and vice versa.

The components of system may be coupled together via network . Network may comprise one or more networks such as a local area network the Internet or other type of wide area network. In addition network may support a wide variety of known protocols such as the transport control protocol and Internet protocol TCP IP and hypertext transport protocol HTTP .

Operating system OS is an integrated collection of routines that service the sequencing and processing of programs and applications running in host . OS may provide many services such as resource allocation scheduling input output control and data management. OS may be predominantly software but may also comprise partial or complete hardware implementations and firmware. Well known examples of operating systems that are consistent with the principles of the present invention include the Linux operating system the UNIX operating system. In addition OS may operate in conjunction with other software such as an application server such as JBoss to implement various features of open host .

Application server provides the logic for analyzing and managing the operations of host . As previously noted application server may be written in a variety of programming languages such as C C Java etc.

For example one responsibility of application server may be managing the various identities of the users of the social networking site maintained by host . Application server may also determine what information of a user should be public or private. In some embodiments application server may default to making information public but provide an option such as a checkbox that allows the user to designate information as private. Application server may also employ per page settings such as all private or all public. Other privacy policies may be implemented by application server .

Application server may here provide various search features. For example application server may allow users to search for other users based on various criteria such as age gender school etc. Application server may also allow searches for various resources such as email addresses topics links etc.

Application server may further create incorporate and authenticate independently verified information. Application server may allow users to upload independently verified information and incorporate the independently verified information into the user s profile. Application server may also authenticate the independently verified information. For example application server may provide an asymmetric cryptographic system to create and authenticate digital signatures contained in the independently verified information.

Web server provides interface access and communication to the social networking site. Such communications may be based on well known protocols and programming languages such as HTTP TCP IP and Java. Interfaces provided by web server may be implemented using well known Internet technologies such as web pages which are well known to those skilled in the art.

User database maintains information identifying users . User database may be implemented using well known database technology such as relational databases or object oriented databases.

For example user database may include information indicating one or more operating systems and applications installed on users as well as services subscribed to by users. User database may also comprise information related to authenticating a user determining the respective rights of a user relative to other users. User database may further include information that indicates the permissions and delivery of the information to user . Other information that may be included in user database may comprise information such as system and individual permissions of user on the social network site activation keys registration information public cryptographic keys of the users visitors and verifiers and payment information such as credit card information .

Furthermore user database may include other information related to the manner in which open host communicates with users . For example this information may relate to periodicity of notifications email addresses format of the information and the like. User database may include data structures to log the activities and transactions of its users. Activities such as recent links history of operations etc. that may be logged in user database are well known to those skilled in the art.

As mentioned above host may provide verifiable and accurate information by allowing user to include information in public forum such as a social networking site that has undergone independent verification and that includes attestation of the independent verification. is a flow diagram illustrating a method in which user acquires the independent verification and host manages the verified information. Method may be performed in system by host user and verifier .

Method begins with user creating a statement to be verified and posted on the social networking site maintained by host stage . The statement may contain any type of information about user that may be useful when independently verified. For example user may create a statement that includes employment information. To be useful to visitors of the social networking site the employment information may need to be verified independently.

After creating the statement user signs the statement stage . User may attest to the statement by signing the statement using any type of digital signing process such as an asymmetric cryptographic digital signature process. For example if user utilizes an asymmetric cryptographic digital signature user may apply a transform to the statement such as a hash. Then user may encrypt the transformed statement with user private cryptographic key to create the digital signature. User may then append the digital signature to the statement.

After signing the statement user transmits the statement with the attestation to verifier stage . User may transmit the statement to verifier via network . As mentioned above verifier may be any entity that can independently verify the information contained in the statement. For example if the statement contains user employment information verifier may be user past or present employer.

After receiving the statement verifier verifies the information contained in the statement stage . Verifier may verify the information by comparing the information in the statement with its records.

Optionally verifier may authenticate user attestation such as a digital signature appended to the statement stage . By authenticating the attestation verifier may confirm that the statement was sent from the correct user . Additionally by authenticating the attestation verifier may confirm that the statement has not been altered.

If a digital signature is utilized verifier may authenticate user digital signature by performing the authentication method for the particular type of digital signature. For example if user signs the statement using an asymmetric system verifier may authenticate the digital signature by retrieving user public key. User public key may be included with the statement. Alternatively user public key may be maintained and retrieved from a key authority. Also user public key may be requested from user or host .

After retrieving user public key verifier applies the public key to the digital signature. By applying the public key verifier recovers the transformed statement for example the hashed statement. Verifier then applies the same transform to the statement to be authenticated and compares it to the recovered transformed statement.

If the statement verifies verifier attests to the statement by signing the statement stage . If the statement does not verify verifier may inform user of the lack of authentication not shown . Similar to user verifier may attest to the statement by signing the statement using any type of digital signing process such as an asymmetric cryptographic digital signature process.

For example if verifier utilizes an asymmetric cryptographic digital signature verifier may apply a transform such as a hash to the statement including user digital signature. Then verifier may encrypt the transformed statement with verifier private cryptographic key to create verifier digital signature. Verifier may then append the digital signature to the statement including user digital signature.

After signing the statement verifier returns the statement with both attestations to user stage . Alternatively verifier may return the statement with both attestations directly to host . Verifier may return the statement via network . If the statement is returned to user user transmits the statement to host stage . User may transmit that statement via network .

Once host receives the statement with attestations of both the verifier and user host may incorporate the statement in the social networking site stage . Host may incorporate the information by including the statement in user personal profile. Host may display both attestations such as digital signatures visually next to the statement. Additionally host may embed the attested statement itself in an html tag that is not normally visible but is detected by the browser.

Method was described about with user creating and attesting to the statement. Nonetheless user may provide information to be independently verified to host . In such a case host may create and attest to a statement containing the information employing the same method employed by user .

The signed statement may be utilized in several different ways to show the authenticity of the information contained in the statement. Host may authenticate both the signatures of the verifier and user prior to displaying the statement. Host may then indicate in user profile that the information has been independently verified. Additionally host may authenticate both signatures upon request by a visitor to the social networking site. Further host may allow visitor to download the signed statement with both attestations and verify the signatures personally.

Method begins with host retrieving verifier public key stage . Verifier public key may be stored at host . Likewise Verifier public key may be retrieved directly from verifier . Additionally verifier public key may be maintained at a key authority.

After retrieving the public key host applies the public key to verifier digital signature stage . By applying the public key host recovers the transformed statement such as the hashed statement.

Host then applies the same transform such as a hash to the statement to be verified stage and compares it to the recovered transformed statement stage . If the statements match host considers verifier digital signature authentic. If not host rejects the statement as being invalid stage .

Next host authenticates user digital signature. Host retrieves user public key stage . User public key may be stored at host . Likewise user public key may be retrieved directly from user . Additionally user public key may be maintained at a key authority.

Then host applies the public key to user digital signature stage . By applying the public key host recovers the transformed statement such as the hashed statement.

Host then applies the same transform such as a hash to the statement and compares it to the recovered transformed statement stage . If the statements match host considers user digital signature authentic and accepts the statement as trusted and accurate . If not host rejects the statement as being invalid stage .

As mentioned above host maintains a social networking site in which users may share information which has been independently verified. are diagrams illustrating an exemplary social networking webpage consistent with embodiments of the present disclosure. Webpage may be created by user and maintained by host . Visitors may view webpage using any well known browsers by entering the web address in field .

As illustrated in webpage displays information about user . Webpage may include biographically data about user and a picture . Webpage also includes history information about user . For example webpage includes employment information and educational information . Since the history information is valuable if independently verified user or host may acquire verification by a verifier with knowledge. For example user or host may acquire verification according to method described above.

As illustrated in to authenticate the information a visitor may select a verify link embedded in employment information . In response host authenticates the information according to method described above. If the statement authenticates host displays a message notifying visitor .

Other embodiments of the invention will be apparent to those skilled in the art from consideration of the specification and practice of the invention disclosed herein. It is intended that the specification and examples be considered as exemplary only with a true scope and spirit of the invention being indicated by the following claims.

