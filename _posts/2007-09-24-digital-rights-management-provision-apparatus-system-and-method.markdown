---

title: Digital rights management provision apparatus, system, and method
abstract: Provided is digital rights management (DRM) provision technology, and more particularly, are an apparatus, system, and method which can easily provide content using one or more DRM systems. A DRM provision apparatus includes a content download unit which downloads encrypted real content and dummy content from a download server and which manages the downloaded real content and dummy content; a license management unit which manages a license issued by a license server; and a processing unit which manages the downloaded real content and dummy content and the issued license.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08612355&OS=08612355&RS=08612355
owner: Samsung Electronics Co., Ltd.
number: 08612355
owner_city: Suwon-si
owner_country: KR
publication_date: 20070924
---
This application claims priority from Korean Patent Application No. 10 2007 0020390 filed on Feb. 28 2007 in the Korean Intellectual Property Office and U.S. Provisional Patent Application No. 60 852 992 filed on Oct. 20 2006 in the United States Patent and Trademark Office the disclosures of which are incorporated herein by reference in its entirety.

The present invention relates to digital rights management DRM provision technology and more particularly to an apparatus system and method which can easily provide content using one or more DRM systems.

Generally digital rights management DRM technology protects and manages the rights of digital content creators. According to the DRM technology a content provision server stores content in an encrypted form and provides encrypted content and key information required to decrypt the encrypted content to a user when the user makes a request for purchasing the encrypted content. The DRM technology defines the number of times that digital content can be played back whether or not the digital content can be duplicated the number of times the content can be duplicated and the like.

DRM functions are largely divided into the following the protection of digital content the management of usage rules of the digital content and the management of a billing system. In order to protect digital content the DRM technology encrypts the digital content and thus prevents the illegal distribution or use of the digital content in all stages i.e. creation distribution use and disposal of its life cycle. In addition the DRM technology enables only an authorized user with an encryption key to decrypt and use encrypted content. Therefore even if the encrypted content is illegally distributed it cannot be used without the encryption key.

However DRM technologies such as Microsoft MS DRM and Open Mobile Alliance OMA DRM developed by various developers are not compatible with each other. That is a DRM structure developed by a developer runs on hardware or software that supports the DRM structure of the developer but not on other platforms. Therefore a user has to purchase different hardware or software that supports each DRM.

In this regard there is a need for a technology that can play back content to which different DRM standards developed by various developers have been applied on any host device.

It is an aspect of the present invention to implement a content provision system using one or more digital rights management DRM systems.

However the aspects of the present invention are not restricted to the one set forth herein. The above and other aspects of the present invention will become more apparent to one of ordinary skill in the art to which the present invention pertains by referencing a detailed description of the present invention given below.

According to an aspect of the present invention there is provided a DRM provision apparatus including a content download unit downloading encrypted real content and dummy content from a download server and managing the downloaded real content and dummy content a license management unit managing a license issued by a license server and a processing unit managing the downloaded real content and dummy content and the issued license.

According to another aspect of the present invention there is provided a DRM provision system including a packaging server performing a first packaging process and a second packaging on unencrypted real content and generating encrypted real content and dummy content a download server downloading the encrypted real content and the dummy content a license server generating and issuing a license for the encrypted real content and a DRM provision apparatus receiving and managing the encrypted real content the dummy content ad the license.

According to another aspect of the present invention there is provided a DRM provision method including receiving encrypted real content and dummy content and receiving a license issued for the encrypted real content.

The present invention will now be described more fully with reference to the accompanying drawings in which exemplary embodiments of the invention are shown. The invention may however be embodied in many different forms and should not be construed as being limited to the exemplary embodiments set forth herein rather these exemplary embodiments are provided so that this disclosure will be thorough and complete and will fully convey the concept of the invention to those skilled in the art. Like reference numerals in the drawings denote like elements and thus their description will be omitted.

Exemplary embodiments of the present invention will hereinafter be described in detail with reference to the accompanying drawings.

The content provider registers content which is to be provided with a contents management system CMS . The CMS supports a function of managing the registration retrieval and deletion of a product content and a function of setting rights. In addition the content provider registers meta information of content in order to distribute the content to users who desire to use the content sets usage rights of the content for service business application and decides the price of the content.

The packaging server performs a first packaging process and a second packaging process on real content registered in the CMS by the content provider and generates dummy content and a DRM packaging file. Here packaging denotes an encryption process for protecting content. The dummy content denotes a file required to receive a license for each DRM such as Microsoft MS DRM and Open Mobile Alliance OMA DRM .

That is the packaging server packages content in order to support the MSDRM and the OMA DRM. The first and second packaging processes will be described in detail later with reference to .

The download server provides downloads content requested by a user to the DRM provision apparatus . In this case the downloaded content is the real content encrypted by the packaging server and the dummy content. The operation of downloading content will be described in detail later with reference to .

The license server issues provides a license for using the encrypted real content. Here the license is issued based on information regarding the dummy content. The operation of receiving a license will be described in detail later with reference to .

The DRM provision apparatus provides content e.g. the encrypted real content and the dummy content received from the download server and the license server to the portable storage device . The DRM provision apparatus may be a kiosk a personal computer PC a portable multimedia player PMP a settop box or a mobile phone. The operation of the DRM provision apparatus will be described in detail later with reference to .

The portable storage device stores the encrypted content the dummy content and the license provided by the DRM provision apparatus . The portable storage device includes a non volatile memory such as a flash memory which can read write and erase data and is capable of performing a predetermined computation on data. In addition the portable storage device can easily be connected to or disconnected from the host device . Examples of the portable storage device include a smart media a memory stick a CompactFlash CF card an extreme Digital xD card and a multimedia card MMC . The operation of the portable storage device will be described in more detail later with reference to .

Meanwhile the encrypted content the dummy content and the license may already be stored in the portable storage device .

For example a user may purchase the portable storage device storing the encrypted content the dummy content and the license and use the encrypted content the dummy content and the license already stored in the portable storage device . That is the user can purchase a portable storage device storing predetermined content and always use the content on the host device .

The host device can be connected to the portable storage device and can play back a content object by using a license and a rights object. The host device may be a portable content playback device such as a mobile phone a personal digital assistant PDA or an MP3 player or a fixed content playback device such as a desktop computer or a digital television TV . The operation of the host device will be described in more detail later with reference to .

Referring to the related DRM system binds encrypted content and a license file for each DRM. Therefore for 1 Gbyte of video a memory with a capacity of n times 1 Gbyte is required.

On the other hand the DRM provision system according to the present invention provides a piece of encrypted real content and a bundle of approximately 5 Kbytes of encrypted dummy content and a license file for each DRM. Therefore content provided by the DRM provision system does not require a large memory space as in the related DRM system.

That is the DRM provision system according to the present invention has a hierarchical structure so that it can run both on a handset loaded with MSDRM and another handset loaded with OMA DRM.

When the related DRM system searches for a license in order to play back content it reads a license ID LID or a content ID CID specified in a DRM handset of encrypted content and searches a license storage database DB or file for a corresponding license.

However the DRM provision system does not directly bind encrypted real content to a corresponding license in order to support both the MSDRM and the OMA DRM. Instead the DRM provision system includes dummy content between the encrypted real content and the corresponding license.

For example if the host device has the MSDRM the DRM provision system reads the ID of dummy content from encrypted real content and then searches for the dummy content protected by the MSDRM.

Then if a file encrypted using the MSDRM is selected from the dummy content the DRM provision system obtains an LID from a header of a corresponding piece of dummy content and obtains a license from a license storage DB or file. The dummy content has a content format which can be played back or listened to by users. However the dummy content merely serves as a medium by which the encrypted real content and the license can be bound to a number of versions of the DRM system. The license bound to the dummy content is a file that sets the rights for the encrypted real content. Meanwhile the same process described above is applied to handsets loaded with the OMA DRM system and other DRM systems.

The packaging server encrypts real content by performing the first and second packaging processes on the real content and generates dummy content and a DRM packaging file.

The first packaging process will now be described. The first packaging process includes a first operation of registering real content a second operation of generating a DRM header a third operation of generating a content encryption key CEK and a fourth operation of encrypting the real content.

Specifically if a content provider registers real content with a CMS the packaging server generates a DRM header of the registered real content. The DRM header includes various forms of metadata that can explain content characteristics such as a dummy content name associated with encrypted content. In addition information contained in the DRM header uses information registered with a metadata DB of the CMS and a dummy content file name is automatically generated based on an uniform resource identifier URI registered with the CMS. In addition the dummy content file name is composed of an English string with no more than 255 English characters.

The structure of the DRM header generated by the packaging server will now be described with reference to .

Referring to DRM type is recorded in a signature field of a DRM header and a filename of dummy content is recorded in a filename length field. A DRM encryption algorithm is recorded in a DRM header length field and DRM version information is recorded in a DRM header field. In addition option information is recorded in a padding field information regarding content length is recorded in a data length field and content data information is recorded in a content data field.

Referring back to the packaging server generates a CEK in order to encrypt the registered real content. In order to generate a CEK indicated by reference character CEK of the registered real content the packaging server generates a 16 byte CEK using a seed value and base64 encodes the generated 16 byte CEK. Here the seed value uses a real time session key value. While real time time information when content is packaged is used in the present exemplary embodiment a random number table separately managed or other values may also be used. For example certain music files such as a musical instrument digital interface MIDI may be stored in a DB in the form of a random number table and may be used as CEKfor encrypting certain real content. In this case CEKis reproducible content.

Next the real content is encrypted using the generated DRM header CEKand a symmetric key algorithm and thus the encrypted real content is generated. The symmetric key algorithm uses an AES 128 bit algorithm and may also use other symmetric key algorithms.

If the first packaging process is completed the second packaging process is performed. The second packaging process includes a first operation of generating dummy content a second operation of generating a CEK of the dummy content and a third operation of packaging the dummy content. The dummy content is not reproducible data such as music or a movie but an intermediate file for generating a license that sets the rights of encrypted content and binding the license to the encrypted content. If certain music files were used as CEKin the first packaging process the dummy content may be reproducible content.

Target dummy content of DRM packaging which is to be supported is automatically generated using CEKthat was used to encrypt the real content. Here the body of the dummy content includes CEK.

For example the OMA DRM generates dummy content in an MP3 format. Thus the dummy content has a payload as a CEK. In addition the MSDRM generates dummy content in a Windows Media Audio WMA format. The MSDRM can generate dummy content not only in the WMA format but also in Windows Media Video WMV and Advanced Systems Format ASF formats. Also the OMA DRM can generate dummy content in various formats.

Next after generating the dummy content in the second packaging process the packaging server generates a CEK in order to encrypt the dummy content. The CEK of the dummy content is indicated by reference character CEK.

Referring to a user or a registration server checks whether the user s portable storage device has been registered. Then the user selects content that the user desires to purchase in a web page through the Internet and requests the download server to download the selected content operation circle around .

Accordingly the download server requests a user authentication server not shown to authenticate information provided by for example the portable storage device requested by the user. If the portable storage device is not registered with the user authentication server the user s request for downloading the selected content is rejected. That is the download server downloads the requested content only after the user registers the portable storage device with the user authentication server.

Next the download server prepares the requested content i.e. encrypted content and dummy content to be downloaded operation circle around . The encrypted content is a file such as a moving picture or music which is copyrighted and the dummy content is a file bound to a license for a content file or to a rights object.

The download server transmits the content requested by the user to the DRM provision apparatus operation circle around and the DRM provision apparatus downloads the received content to the portable storage device operation circle around .

Then the downloaded content i.e. the encrypted content and the dummy content is stored in a content DB. Since the encrypted content itself does not have a license the license server can be accessed only when the encrypted content exists together with the dummy content.

The DRM provision apparatus analyzes a DRM header of dummy content operation circle around . By analyzing the DRM header the DRM provision apparatus obtains URI information required to request the issuance of a license and a key ID KID value required to search for the license.

Then the DRM provision apparatus generates challenge data using the DRM header and a device certificate operation circle around and transmits the generated challenge data to the license server using a hypertext transfer protocol HTTP post method operation circle around . The challenge data includes the DRM header and the device certificate and is base64 encoded.

The license server base64 decodes the received challenge data and obtains the KID by analyzing the DRM header. Then the license server searches for a CEK that matches the obtained KID encrypts the CEK using a public key included in the device certificate and inserts the encrypted CEK into the license operation circle around . Here the CEK is encrypted using an elliptic curve cryptography ECC asymmetric key encryption method.

The license server base64 encodes the generated license and transmits the base64 encoded license to the DRM provision apparatus operation circle around . A transmission method used here is a direct license acquisition DLA method. The DRM provision system suggested in the present invention transmits the encoded license using the DLA method.

The DRM provision apparatus provides the base64 encoded license to the portable storage device and the portable storage device stores the base64 encoded license.

Referring to the DRM provision apparatus includes a content download unit a license management unit a preview provision unit and a processing unit .

The content download unit downloads content from the download server and the downloaded content is stored in the portable storage device . The downloaded content includes encrypted real content and two pieces of dummy content e.g. OMA DRM .dcf and MS DRM .wma which are managed together as a single piece of complex content.

The license management unit receives a license or a rights object from the license server so that a user can use the downloaded content. A license transmitted using an OMA DRM method and a license transmitted using an MS DRM method are stored in respective storage areas for licenses.

For example an OMA rights object is stored in a rights object DB and an encrypted storage space is configured and used in order to prevent rights from being arbitrarily accessed or modified. In addition an MS DRM rights object is stored in a hash storage unit.

The preview provision unit provides the content which was downloaded by the content download unit at the request of the user on a preview screen.

The processing unit manages the operation of each of the content download unit the license management unit and the preview provision unit included in the DRM provision apparatus . In addition the processing unit provides the real content and the dummy content downloaded by the content download unit and a license of the dummy content provided by the license management unit to the portable storage device .

The term unit as used herein means but is not limited to a software or hardware component such as a Field Programmable Gate Array FPGA or Application Specific Integrated Circuit ASIC which performs certain tasks. A unit may advantageously be configured to reside on the addressable storage medium and configured to execute on one or more processors. Thus a unit may include by way of example components such as software components object oriented software components class components and task components processes functions attributes procedures subroutines segments of program code drivers firmware microcode circuitry data databases data structures tables arrays and variables. The functionality provided for in the components and modules may be combined into fewer components and units or further separated into additional components and units.

Referring to the portable storage device includes storage space i.e. a tamper resistant module TRM area a DRM area and a user access area .

The TRM area stores DRM security information. That is the TRM area stores a serial number of the portable storage device a public private key a certificate a device group key etc. for each DRM.

The TRM area may be created when the portable storage device is manufactured. Alternatively the TRM area may be written once when the portable storage device is first used after being purchased. In this case the TRM area can be written after being authenticated by a network server. For security it is desirable to create the TRM area in advance when the portable storage device is manufactured. The TRM area is where data can be read only. The data stored in the TRM area can be read using a particular application programming interface API that accesses the portable storage device .

The rights to access the data recorded in the TRM area must be given only to a DRM agent not shown and an external user must be prohibited from moving or changing the data.

The DRM area stores encrypted dummy content and a license file or a rights object . Even if the DRM area is open to the outside no security problem arises. However if a user of the portable storage device accesses the DRM area and removes or changes a file therein a fatal problem to the operation of the DRM agent may arise. Such a file is stored in the DRM area . In addition the DRM area can be accessed using an API provided by the DRM agent or a particular portable storage device.

The user access area stores encrypted real content such as video or audio which can actually be played back. General users can arbitrarily read or write content in the user access area .

Referring to if a user selects desired content operation circle around the content download unit determines whether DRM has been applied to a selected file. If the selected file is encrypted content the content download unit searches for a filename of dummy content in order to search for a license of the encrypted content operation circle around . Here the filename of the dummy content is read from the DRM header.

Next URI information required to request the issuance of the license and a KID required to search for the license are obtained by analyzing the DRM header operation circle around . Then the license management unit searches for the license stored in the DRM area of the portable storage device using the obtained KID operation circle around .

If it turns out that the license does not exist or has expired the license management unit requests the license server to issue a license through a license downloading process. If the license management unit obtains the license from the DRM area of the portable storage device it transmits the obtained license to the host device .

The host device reads a decryption key CEKof the dummy content included in the license. Since the decryption key CEKof the dummy content is encrypted using a public key the encrypted decryption key is decrypted using a private key stored in the TRM area . Consequently the decryption key CEKis obtained. Then the dummy content is decrypted and thus CEKof the encrypted real content is obtained operation circle around .

Next the encrypted real content is decrypted using CEK and a file is played back operation circle around . The real content has been encrypted using the symmetric key e.g. AES 128 bit algorithm.

If the encrypted real content is normally played back the host device requests the license management unit to update the license for example update a playback count operation circle around .

The user connects the portable storage device e.g. an MMC to a portable storage device interface or universal serial bus USB interface of the kiosk selects desired content and its license type from a product list of the kiosk and makes a purchase request operation circle around .

Next the kiosk identifies the portable storage device that the user connected thereto. The kiosk includes a table that matches a user ID with a serial number of the portable storage device . Therefore the kiosk searches the table for the user ID based on the serial number of the portable storage device connected thereto operation circle around . Alternatively the kiosk may perform an authentication process through a network server.

Referring to the internal structure of the kiosk the kiosk includes a TRM folder a DRM folder and a content folder. The TRM folder stores a table in which a user ID is matched with a serial number and the DRM folder stores a license and dummy content for each user ID. In addition the content folder stores encrypted content.

The kiosk downloads content at a shared directory using Active X operation circle around . Here real content and dummy content are downloaded together.

If the content is downloaded the kiosk obtains a license for the content selected by the user based on the found user ID. The process of obtaining the license for the content from the license server using the kiosk is identical to the process of obtaining a license described above with reference to and thus a detailed description thereof will be omitted.

Then the kiosk provides a preview of the downloaded content operation circle around . If the user selects a Playback function on a purchase screen of the kiosk a preview screen appears. Here if the user selects a content type to preview a content list is displayed. If the user selects the Playback function on the right of the content list a preview function is executed. For the preview function the encrypted real content is decrypted. Since the operation of decrypting encrypted content has been described above with reference to a detailed description thereof will be omitted.

If the preview function is completed the license for the content selected by the user based on the found user ID the dummy content and the encrypted content are transmitted to the portable storage device and thus the purchasing process of the content is completed operation circle around .

As described above a DRM provision apparatus system and method according to the present invention provide at least one of the following advantages.

Since a content provision system is implemented using one or more DRM MSDRM OMA DRM and the like systems it can provide content packaged using a unified encryption algorithm.

In addition DRM content which can be played back by host devices having different DRM systems can be provided.

Regardless of an encoding format of copyrighted real content multi DRM packaging is provided for content in all formats. Therefore there is no need for a content provider to spend additional money to encode content.

While the present invention has been particularly shown and described with reference to exemplary embodiments thereof it will be understood by those of ordinary skill in the art that various changes in form and details may be made therein without departing from the spirit and scope of the present invention as defined by the following claims. The exemplary embodiments should be considered in descriptive sense only and not for purposes of limitation.

