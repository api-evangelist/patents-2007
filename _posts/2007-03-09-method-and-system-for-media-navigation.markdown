---

title: Method and system for media navigation
abstract: A method and system for media navigation. A descriptor hierarchy may be accessed. The descriptor hierarchy may include at least one category list. One or more media descriptors may be accessed for a plurality of media items. The plurality of media items may be accessible from a plurality of sources. The one or more media descriptors may be mapped to the at least one category list. The navigation may be processed through a user interface to enable selection of the plurality of media items from the plurality of sources.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=07908273&OS=07908273&RS=07908273
owner: Gracenote, Inc.
number: 07908273
owner_city: Emeryville
owner_country: US
publication_date: 20070309
---
This application claims the benefit of U.S. Provisional Patent Application entitled Method and System to Navigate Media from Multiple Sources Ser. No. 60 781 609 Filed 9 Mar. 2006 the entire contents of which is herein incorporated by reference.

This application relates to media navigation and more specifically to systems and methods for navigating media from a plurality of sources.

The growth in popularity of digital media has brought increased benefits and accompanying new challenges. While developments have continued to improve the digitization compression and distribution of digital media it has become difficult to easily and effectively navigating through such media. Accessing media from a variety of sources of potentially different types for navigation increases the difficultly of navigation as each of the sources may include a large number of media items including songs videos pictures and or text in a variety of formats and with varying attributes.

The sheer volume of digital media available along with significant diversity in metadata systems navigational structures and localized approaches makes it difficult for any single device or application user interface to meet the needs of all users for accessing the digital media.

In general descriptive metadata ordinarily associated with the digital media may be unavailable inaccurate incomplete and or internally inconsistent. When available the metadata is often only available via textual tags that indicate only a single level of description e.g. rock genre and the level of granularity used in that single level may vary greatly even within a single defined vocabulary for the metadata. Often the level of granularity available is either too detailed or too coarse to meet the needs of a given user interface requirement. Additionally for a given media object there may be multiple values available for a given descriptor type and or multiple values of the same type from multiple sources that may cause additional problems when attempting to navigate the digital media.

While the scope and diversity of digital media available to users has increased the user interface constraints of limited screen size and resolution in some devices have remained effectively fixed. Although increases in resolution have been gained the screen size being used to access some digital media has decreased as the devices have become more portable. Portable devices may include constraints that the length of lists and the length of the terms used in such lists remain short and simple.

At the same time the application logic driving media applications such as automatic playlist engines recommendation engines user profiling and personalization functions and community services benefits from increasingly detailed and granular descriptive data. Systems that attempt to utilize the same set of descriptors for both user interface display and application logic may be unable to meet both needs effectively at once while using two completely separate systems risk discontinuity and user confusion.

In addition different users may use different media navigation structures labeling and related content when accessing content from different geographic regions in different languages from various types of devices and applications from different user types and or according to personal media preferences. Existing navigation structures may not enable developers to easily select configure and deliver appropriate navigational elements to each user group or individual user especially in the case of an embedded device.

Traditionally access to media available from such alternatives has been organized in a source or service paradigm. If a user desired to hear jazz music they would either pre select just a single device or source to browse such as a local HDD or drill in and out of the navigation UI for each device source separately to view available jazz content.

Existing media navigation solutions have been more or less static in terms of not being able to respond dynamically to changes in a user s media collection or other explicit or implicit temporary or long term personal preferences. Likewise there has been only limited capability for media navigation options to respond dynamically to real time or periodic changes in other global and personal contextual data sources including those related to time location motion orientation personal presence object presence.

Example methods and systems for media navigation are described. In the following description for purposes of explanation numerous specific details are set forth in order to provide a thorough understanding of example embodiments. It will be evident however to one skilled in the art that the present invention may be practiced without these specific details.

A navigation system is described that may provide consistent simple effective and efficient access to a vast scope of digital media regardless of application display device or user interface UI paradigm. The navigation system may be deployed to enable end users to perform customization and re classification of their media collections without impacting the integrity of an underlying portion of the navigation system. Example embodiments of the navigation system may be used to navigate digital content e.g. digital audio and may thus be deployed in a portable media device e.g. MP3 player iPOD or audio any other portable audio player in vehicle audio systems home stereo systems computers or the like.

The navigation system may enable the efficient configuration and dynamic updating of diverse navigational structures across a plurality of devices and applications while maintaining the integrity of the underlying metadata. A configuration module of the navigation system may automatically pre generate and load into a client e.g. provided on a media player appropriate alternative normalized media navigation structures. The structures may be used to create an indexed application media database and navigational elements to present one or more views of media items of diverse and multiple sources types and metadata. The views may be switched on demand personalized dynamically adapted and updated without altering the underlying global granular source media identifiers descriptor codes and or labeling data.

An example system may be built upon a foundation of navigation structures that may include lists ordering data hierarchies trees weighted relations mappings links and other information architecture elements as well as entity grouping labeling filters and related navigational content. The navigation structures may incorporate a set of semantic entities and descriptors designed to be understandable and appropriate and may be automatically optimized. Thus for example a user of a media device e.g. a portable media player or vehicle audio system may be customized or optimized for one or more particular users or user location s .

The navigation system may include a mapping of global internal granular annotation codes to a variety of alternative category lists and navigational content used for user interface purposes. The category lists may be fluidly mixed and matched to generate a wide variety of hierarchies and navigation trees while maintaining the integrity of the parent child mapping between each list and without any change in the global granular annotation codes.

In a pre processing phase a configuration module may be utilized to automatically select from a pre defined super set of options pre generate and load into a specific connected or unconnected client at time of manufacture or initial start up an appropriate set of alternative normalized media navigation structures. The options chosen may be determined based on a combination of device application region language user type manufacturer publisher and or end user account IDs which are provided as parameters to the configuration module.

A client application may then utilize the navigational structures to create an indexed application media database typically in conjunction with media recognition technology.

The index may compile media items sourced from diverse and multiple types services and providers. Additionally the media items may be accessed from diverse and multiple devices connectivity and transport. The media items may furthermore contain identifiers and metadata of diverse types completeness consistency and accuracy without materially impacting the performance of the system.

The client application may utilize the navigational structures to generate default and alternative user interface elements such as browse trees faceted navigation and relational lists and or to drive aspects of application logic such as auto playlisting search personalization recommendation internet community media retail and on demand subscription services and the like.

In an example embodiment the user interface elements present uniquely for each user on a client simple unified descriptor based and other views. Via an application programming interface API provided on the media player the views and structures may be altered on demand personalized dynamically adapted based on personalized and or contextual input and updated remotely from a set of master databases via a network service and or from a local database.

The alternate views may be applied on a global e.g. a country or several countries region e.g. regions within a country application e.g. an online catalog or store . . . device e.g. portable media player vehicle media player etc. and or user account level. All such changes at the presentation information architecture layer may be achieved without altering the underlying master granular media identifiers descriptor codes labeling data and file tags.

The master media information architecture contextual data and user profile databases may be refined and appended based on feedback from the clients and thus be modified based on user input.

The navigation system may be used to power various applications running on any device rendering media including a search a recommendation playlisting internet community facilitation stores on demand subscription services and the like.

The client application may provide navigational access to content through a user interface . The user interface may provide navigational information and other information to an end user through a display device e.g. on a device or an application.

Navigation templates may access one or more descriptor hierarchies available to the client through the user interface to provide one or more navigation views.

Master descriptor code list associated with content may be used to enable navigational access to the content e.g. audio video or the like by mapping it to selected descriptor category lists that are contained within the descriptor hierarchies . The descriptor codes may describe an attribute an entity of a media item. The selected category lists may be selected from the plurality of available category lists contained within a plurality of the descriptor systems . .n. In an example embodiment the master descriptor code list of the client may not include all master descriptor codes of the master descriptor code list of a descriptor system ..

A descriptor system . includes a master descriptor code list from which master descriptor code list may be selected. The master descriptor code list may include a list of a plurality of available master descriptor codes and associated names for a particular type of media descriptor. For example the master descriptor code list for a genre media descriptor may include coded identification of a greatest amount of granularity desired for genre. By way of example the master descriptor code list for genre may include e.g. more than fifteen hundred different genres . For example the master descriptor code list may be a detailed genre list used for coding media items such as artists albums and recordings. The master descriptor code list for a particular type of descriptor may optionally be given a unique identifier that may be used for identification.

In an example embodiment by linking the master descriptor code that is associated with the media items to the corresponding master descriptor code in the master descriptor code list the media item may be associated with the descriptor categories by mapping the media item to the master descriptor code.

The most granular descriptor category list of the available category lists may be referred to as the master descriptor category list. The master descriptor codes are mapped directly into the master descriptor category list which may contain an equal or smaller number of categories than there are codes in the master descriptor code list .

By maintaining the master descriptor category list separately from the other descriptor category lists maintenance of the descriptor system . may be simplified. The mapping from the master descriptor code list to each of the other descriptor category lists may not need to be directly updated as the mapping from the master descriptor category list to each of the other descriptor category lists may remain unchanged.

The plurality of available category lists e.g. the descriptor category list may include a number of levels of category lists as part of each descriptor system. Each category list may include a differing number of category codes and associated labels from the other category lists in the descriptor system. For example a category list at a first level may include five category codes and associated labels and at a second level may include twenty category codes and associated labels. The most granular level of the plurality of available category lists may be referred to as a master descriptor category list.

Each descriptor category code in each descriptor category list in each descriptor system may be mapped to its parent descriptor category code in the next less granular descriptor category List. A number of child category codes may be mapped to each parent category code. The mapping may have an indirect effect of mapping each master descriptor code to its appropriate parent category in every category list via the master descriptor category list and mapping every category code to its appropriate parent and child category code in every non adjacent category list. The mappings from the master descriptor codes to the descriptor category codes may also be stored directly. Each descriptor code may be a unique identifier.

To enable data annotation by end users artists venue label content broadcast partners internal experts or others using the more simplified category lists rather than the highly granular master descriptor lists mapping may be used.

A one to one downward mapping may be created and stored for each descriptor category. As the descriptor categories may generally be of more aggregate nature than many of the master descriptor codes the descriptor categories may typically be mapped to the more aggregated master descriptor codes to ensure than only the level of information actually known is encoded. The user interface presented to the submitter may only display the applicable hierarchy of category lists from which they select the annotation labels. Once selected the item may be annotated with the mapped master descriptor code. For example a venue operator may publish the music genres that are primarily associated with the venue but do so by selecting from a simplified list of fifteen meta genres.

A descriptor system . may be created for each desired viewpoint. The viewpoints of the descriptor system . may be defined by a combination of regional genre preference psychographic demographic and or other factors that combine to define a preferred perception of the applicable descriptor types. Examples of viewpoints of descriptor systems . include North American Default Japanese Classical Aficionado. South American Youth and Southern European Traditional.

To provide for a more useful user interface different descriptor systems . .n may group the same master descriptor code list into substantially different category arrangements. The grouping may enable the ability to substantially change the areas of category focus in different implementations while utilizing the same master descriptor codes. For example a European genre descriptor system might include the genre Chanson in its shorter more highly aggregated genre category lists as a European end user may desire quick access to music of this type whereas for a North American genre descriptor system the genre category might only be exposed at the lower levels if at all with content coded with Chanson master descriptor codes instead being included along with music from other related master genre codes in a genre category of World .

Navigational content may be used to enhance navigational access on the user interface . The navigational content may be provided during navigation to identify content and may include by way of example audio clips media packaging graphics photos text genre icons genre mini clips genre descriptions origin icons origin mini clips origin descriptors navigational icons e.g. channel icons phonetic data and the like.

A recognition module may be further included in the client to recognize media items . .. The recognition module may optionally use a local database and or a remote database to perform look and or obtain metadata for the media items . .. An example embodiment of a method for recognizing the media items . . that may be performed at the recognition module is described in greater detail below.

The navigation system may include a client that may have access to media objects . from one or more media sources and media objects . from one or more media services . The media objects . may be associated with entity types . while the media objects . may be associated with the entity types .. The media objects . . may be accessed through an indexing module by a local information architecture .

The media objects . . may be recognized by use of a recognition module . The recognition module may use a local media object lookup database to identify the media objects . . to assemble a local metadata database of metadata for the media objects . .. The recognition module may also instead of or in addition to the local lookup perform a remote lookup by contacting a recognition service . The recognition service may use a master media object lookup database to identify the media objects . . and a master media metadata database to obtain metadata for the media objects . ..

The local information architecture may be used by a navigation system application to configure various navigational views as described in greater detail below. The navigation system application may configure the navigational views according to a personalization module and or a contextualization module.

Hierarchies and navigation trees may be generated from the local information architecture and used to provide the navigational views. The hierarchies and the navigation trees may optionally be stored and available for later retrieval.

A navigation API may be used to provide access to the navigation system application . One or more contextual data feeds and or sensors may be used to provide contextual data through the navigation API to the navigation system application . Personalized data may also be received from a master user profile database by use of a personalization service .

A navigational update module may be used to update the local information architecture . The navigation update module may optionally use one or more IDs which may identify a build ID a device ID an application ID a customer ID a region ID a taste profile ID a user type ID a client ID and or a user ID to receive the appropriate updates for the local information architecture as deployed.

A navigation service may provide updated information to the navigation update module . The navigation service may obtain information used for navigation e.g. navigational content from one or more descriptor systems and navigational content from a master navigation content object store utilizing a navigational content metadata database . The navigational content may be provided to aid in navigation and may include by way of example audio clips media packaging images text genre icons genre mini clips genre descriptions origin icons origin descriptors channel icons phonetic data and the like.

One or more navigation templates may be accessed by the navigation service . The navigation templates may enable differing navigational views into one or more descriptor hierarchies available to the client through the user interface .

One or more navigation templates may be accessed by the navigation service . The navigation templates may enable differing navigational views into one or more descriptor hierarchies available to the client through the user interface .

Descriptor codes associated with content in the local metadata database may be used to enable navigational access to the content by mapping content to selected category lists that are contained within the descriptor hierarchies . The selected category lists may be selected from the plurality of available category lists contained within a plurality of the descriptor systems .

The plurality of available category lists may include a number of levels of category lists. Each category list may include a differing number of category codes and associated labels. For example a category list at a first level may include five category codes and associated labels and at a second level may include twenty category codes and associated labels.

The configuration system includes a configuration application in which a configuration module may communicate with one or more master media sources and a reference media database . The configuration application may utilize one or more master descriptor code lists . .n for content e.g. media items available through the master media sources . A master code descriptor list . of the master descriptor code lists . .n may be provided to a plurality of descriptor systems .

The configuration application may also create a descriptor hierarchy from an original descriptor system or an alternate viewpoint descriptor system . From each of these an alternate label and or a translated language descriptor system may also be created.

The original descriptor system includes the master descriptor code list see third party descriptor label mappings third party descriptor ID mappings master category lists other category lists system mapping tables and ordering value data . The third party label and identifier mapping tables may associate third party labels e.g. genre label R R or IDs e.g. ID3 Genre tag 96 with the appropriate master descriptor code.

3party mapping tables associate descriptor term labels and descriptor term unique identifiers utilized externally to the most appropriate master descriptor code for each applicable descriptor type. If more than one 3rd party system uses an identical descriptor label this one label may be mapped to the single best fit master descriptor code or alternatively the system may store a 3rd party organization ID with each instance of a descriptor label such that it is possible to support alternate mapping form 3rd party descriptor to master descriptor code depending on the source as indicated by the 3rd party entity identifier. In the case of mapping 3rd party descriptor unique identifiers it is always necessary to include the 3rd party organization ID. External descriptor labels do not have to be associated with a specific entity they may represent colloquial expressions.

The ordering value data may optionally be associated with the category lists of the descriptor systems . The ordering values for each of the categories indicate an order in which the labels of a category list may be presented in the user interface see . For example the ordering values may be based on judgmental similarity judgmental importance judgmental chronological and the like.

The labeled hierarchy may be assembled from a specific descriptor system with specific labels associated with each category ID. The labeled hierarchy includes the master descriptor code list labeled category lists the system mapping tables and the ordering value data . The alternate master category lists may include one or more alternate labels for the category lists contained in the master category lists . For example the alternate labels may include nicknames short names and the like.

The translated hierarchy is a version of a labeled hierarchy with translated labels e.g. in Spanish Japanese and English . The localized language descriptor system. The translated hierarchy includes the master descriptor code list translated labeled category lists the system mapping tables and the ordering value data .

The descriptor hierarchy may include the selected category lists see category list ordering data hierarchy mapping tables descriptor relational tables and entity hierarchies . The selected category lists may be selected from the master category lists the alternate master category lists and or the localized master category lists .

The category list ordering data may enable one or more alternate orderings of the category lists of the descriptor hierarchy .

The third party mapping tables e.g. tables provided by a third party content provider may associate descriptor terms and unique identifiers used by third parties to the master descriptor codes contained in the master descriptor code list . For example a third party descriptor term may be mapped to a master descriptor code to which it is most similar. Thus discrepancies in terminology used may be accommodated.

The descriptor relational tables relate master descriptor codes with other master descriptor codes in the master descriptor code list . The relations may be defined by a correlation value or a weighting for each relationship.

The entity hierarchies define the parent child relationship between at least some of the entity types. An example of an entity item hierarchy is as follows Series Album Edition Release SKU Disc Track Recording Movement Composition.

The navigation template may include a template ID a region one or more application parameters one or more device parameters a user type one or more third party IDs and or one or more navigation trees .

The region may define the regional viewpoint that is used to select the appropriate descriptor systems and other navigational elements such that they can be assembled into a user interface that conforms to the cultural expectations of a specific regional user base. For example the selection of the region may include the United States Germany Brazil Japan Korea the Middle East China global Eurasia America and or Asia U.S. East Coast New England States Chicago and the like. Other regions may also be available for selection.

The region may define the regional viewpoint that is used to select the appropriate descriptor systems and other navigational elements such that they can be assembled into a user interface that conforms to the cultural expectations of a specific regional user base. For example the selection of the region may include the United States Germany Brazil Japan Korea the Middle East China global Eurasia America and or Asia U.S. East Coast New England States Chicago and the like. Other regions may also be available for selection

The one or more application parameters indicate the application type e.g. media player a web site a playlist generator a collection manager or other application in which the navigation package may be deployed. For example the application parameters may cause alternate category labels to be made selected such as short names standard names or extended names.

The one or more device parameters specify the device in which the navigation package may be deployed. For example the device parameters may indicate whether the device is a PC a home media server a vehicle stereo a portable media player a mobile phone a digital media adapter a connected CD DVD flash player a remote control and the like.

The user type may identify a type of user that may use the deployment of the navigation template in the client . For example the user type may identify a user of the navigation template as a basic user a simple user a standard user an advanced user or a professional user. Other user types may also be used.

The one or more third party IDs may identify third parties associated with a deployment of the navigation template . The third party IDs may be associated with third party customers and or partners that have IDs e.g. unique IDs that define their navigational preferences for the end user as well as IDs of third parties whose labels or IDs may need to be mapped via the appropriate third party mapping tables.

The one or more navigation trees may be a sequence of category lists taken from selected category lists and or entity types to be available for constructing elements of the user interface based on the selection of the application parameters the device parameters the user type and or the other third party IDs . The navigation trees may also include an ordering of items in a category list. The list ordering definition may include a judgmental unique ordering alphabetical dynamic item count a dynamic popularity or the like.

The other category lists may selected from one or more descriptor hierarchies not included in the information architecture . The default mappings may be used in the information architecture to enable mapping of legacy descriptors IDs e.g. from a provide or a third party and or to perform third party descriptor label mapping. Other configurations of the information architecture including different elements may also be deployed in the client .

The reference media database may be created at block . Upon creation the reference media database may include the plurality of master descriptor code lists . .n. An example embodiment of creating the reference media database is described in greater detail below.

Information architecture see may be created at block . An example embodiment of creating the information architecture is described in greater detail below.

A navigation template see may be defined at block . An example embodiment of defining a navigation template is described in greater detail below.

Media descriptors may be associated with a plurality of entities at block . The plurality of entities may be from a single media source . e.g. from a single content provider or fixed disk the plurality of media sources . .n and or the media library see . For example the entities may include a channel a stream a station a program a slot a playlist a web page a recording artist a composer a composition a movement a performance a recording a recording mix track a track segment a track a release an edition an album an album series a graphic image a photograph a video segment a video a video still image a TV episode a TV series a film a podcast an event a location and or a venue. Other entities may also be used.

The media descriptors may use an identification ID code to identify a characteristic of an entity with which it is associated. For example the ID code used with the media descriptors may include a genre ID code an origin ID code a recording era ID code a composition era ID code an artist type ID code a tempo ID code a mood ID code a situation ID code a work type ID code a topic ID code a personal historical contextual IDs a community historical contextual ID code a timbre ID code and the like. Other ID codes may also be used with the media descriptors to identify characteristics of entities.

Each of a particular type of ID code may be associated with a single master descriptor code list . For example the genre ID codes may be on a genre master descriptor code list where each genre ID code is associated with a genre label and the mood ID codes may be on a mood master descriptor code list where each mood ID code is associated with a mood label.

A particular entity may be associated with a plurality of media descriptors. One or a plurality of media descriptors with a same type of code e.g. a genre ID code may be associated with an entity. The media descriptors may optionally be given a ranking and or weighting to indicate their relevance among other media descriptors. For example an album may be associated with a primary media descriptor of blues and a secondary media descriptor of rock where the primary media descriptor is ranked higher than the secondary media descriptor.

A determination of which media descriptors to associate with an entity may optionally be based on information received from one or more data sources. For example the data sources may include content information received from providers e.g. label data feeds and or content registries expert editorial information individual community submissions collaborative community submissions digital signal processing DSP analysis statistical analysis and the like.

One or more flags may optionally be associated with one or more entities of the plurality of entities at block . The flags may be used to identify a certain type e.g. a special type of entity that may receive special handling during navigation. For example a flag may be used to indicate that an entity is a various artist compilation a soundtrack a holiday related theme e.g. Christmas an interview and or a bootleg recording. Other types of flags may also be used to identify other certain types of entities that may receive special handling during navigation.

Inheritance may be applied to the plurality of entities at block . Applying inheritance to the plurality of entities may enable access for at least some of the plurality of entities to selected media descriptors associated with one or more other entities. Inheritance may optionally be used to reduce an amount of media descriptors associated with a plurality of entities based on the relationship among the entities. The use of inheritance may provide greater efficiency and or scalability of the reference media database .

By way of an example a set of media descriptors may be associated with a recoding artist. For an album of the recording artist where the media descriptors differ from the set of media descriptors associated with the recording artist a set of media descriptors may be associated for the album. When the individual recordings of the artist differ from that of an album on which the recordings were recorded a set of media descriptors may be associated with the individual recordings. If one or more individual segments of a recording differ from a parent recording a set of media descriptor may be associated with the individual segments.

Inheritance may be applied to entities in a cascading down manner e.g. cascading down inheritance to provide for inheritance from a parent and or in a cascading up manner e.g. cascading up inheritance to provide for inheritance from a child. Inheritance may be applied in a cascading down manner when a child entity does not have directly associated media descriptors. The child entity may then inherit the media descriptors associated with a parent entity. For example if a genre ID code is associated with a recording artist and an album does not have an associated genre ID code the album may inherit the genre ID code of the recording artist. If a recording on the album does not have an associated genre ID code the recording may inherit the genre ID code of the album.

Inheritance may be applied in a cascading up manner when a parent entity does not have directly associated media descriptors. The parent entity may then inherit the media descriptors associated with a child entity. For example if a genre ID code is associated with one or more recordings and an album containing the recordings does not have associated genre ID code the album may inherit the genre ID code associated with the most common genre ID code from its recordings. If an artist who recorded a plurality of recordings has not been associated with a genre ID code the artist may inherit the most common genre ID code associated with albums associated with the artist.

An additional mapping may be created for the reference media database at block to provide for an additional association among at least two entities of the plurality of entities. For example an alternate artist billing may be mapped to a primary artist ID code and or an individual artist ID code may be mapped to a collaboration artist ID code. Other additional mappings may also be created.

The reference media database may optionally be stored at block . The reference database may include the association of the media descriptors with a plurality of entities the association of a flag with the selected entities of the plurality of entities applied inheritance to the plurality of entities and or the additional mapping among at least two entities of the plurality of entities.

A descriptor hierarchy see may be created at block . The descriptor hierarchy may be created by selecting from a plurality of available category lists of a corresponding descriptor type and mappings from the upward mapping and or downward mapping associated with the selected category lists . The descriptor system thereby may act as having a superset of available category lists from which the selected category lists of the descriptor hierarchy are selected..

A descriptor hierarchy see may be created at block . The descriptor hierarchy may be created by selecting from a plurality of available category lists of a corresponding descriptor type and mappings from the upward mapping and or downward mapping associated with the selected category lists . The descriptor system thereby may act as having a superset of available category lists from which the selected category lists of the descriptor hierarchy are selected. .

A plurality of descriptor hierarchies may be created for a particular descriptor type from one or more descriptor systems . .n e.g. an original descriptor system an alternate language descriptor system and or a localized language descriptor system . Two or more of the multiple descriptor hierarchies may be linked together e.g. through pointers to facilitate version selection during viewing.

The category list ordering data may be created at block . The category list ordering data may enable one or more alternate orderings of the selected category lists of the descriptor hierarchy .

Third party mapping tables may optionally be created at block . The third party mapping tables may associate descriptor terms used by third parties to the master descriptor codes contained in the master descriptor code list .

Descriptor relation tables may be created at block . In an example embodiment the descriptor relation tables may be created at a macro and micro level. At a macro level a macro level correlate list may define correlation levels for the items on a single category list. At a micro level correlation levels may be defined between master descriptor codes. The micro level may then be mapped to the macro level to create the descriptor relation tables .

The information architecture created during the operations at blocks may optionally be deployed in the client at block .

A master descriptor code list see may be generated at block . A media descriptor for which the master descriptor code list may be generated may include but is not limited to a genre media descriptor an origin media descriptor a recording era media descriptor a composition era media descriptor a time cycle media descriptor an artist type media descriptor a tempo media descriptor a mood media descriptor a situation media descriptor or a topic media descriptor.

A descriptor system may be generated from the master descriptor code list at block . The descriptor system is generated to include a plurality of available category lists . The available category lists of the descriptor system may be generated to include summarized versions of the master descriptor code list with decreasing or increasing granularity. The summarized versions of the master descriptor code list may include a lesser number of list entries.

The amount of list entries in a category list of the descriptor system and the number of category lists in the descriptor system may be selected to provide flexibility when selecting a number of category lists for deployment as a hierarchy as described in greater detail below. Each category list may optionally be provided with a unique identifier.

A plurality of descriptor systems . .n may optionally be created for a particular descriptor type where each descriptor system of the particular descriptor type may have a different number of category lists and each category list may include a different number of list entries. For example a plurality of descriptor systems . .n may be created for different region focuses e.g. a global descriptor system a US descriptor system a Japan descriptor system etc. different genre focuses e.g. general descriptor system classical descriptor system internal descriptor system etc. different mood focuses e.g. smooth excited reflective etc. or the like.

Master descriptor codes may be mapped to a master category list of the descriptor system at block . The master category list may be the category list of the descriptor system with the highest granularity e.g. number of list entries . When the master category list of a descriptor system is not a master list more than one descriptor code may be mapped into a category code of a same list entry.

The category lists of the descriptor system may be mapped to one another at block . The category codes of the category lists may be mapped to a category code of a parent category list e.g. a less granular category list in the descriptor system. The category codes of a parent category list may include one or more mappings from a category code of a child category list.

An alternate label version of the descriptor system e.g. the alternate language descriptor system may be created at block . The alternate language descriptor system may include the same category lists of the original descriptor system on which the alternate version is based but contain the alternate master category lists with an alternate language label substituted for some or all of the category names of the master category lists . The alternate language labels may include abbreviated names short names extended names and the like. Multiple alternate language label versions of an original descriptor system may be created.

A localized label version of the descriptor system e.g. the localized language descriptor system may be created at block . The localized language descriptor system may include a different label based on localization. For example a localized label version of the descriptor system may be in Japanese Korean German French and or other different languages. A localized label version may be created for an original descriptor system and or the alternate language descriptor system .

Ordering value data may optionally be associated with the category lists of a descriptor system at block .

A determination of a template selection for inclusion in a navigation package may be made at decision block . The determination may be made from explicit input presence data received from a geolocation service dynamically or the like. The template selection may be for a selection of a pre built template at block a dynamically generated template at block or a manually configured template at block .

The pre built template that may be selected at block may be a navigation profile based on a common use case. The pre built template may identify included descriptor hierarchies and other information architecture elements that are associated with the template. The pre built template may include a unique identifier to enable selection among other available templates. Examples of pre built templates include pre built templates for a basic user in the European market that plays classical music in a car using a media player and a pre built template for an advanced user in the Japanese market that plays music on a personal computer using a media player. Other pre built templates may also be available for selection.

The dynamically generated template that may be selected at block may be a template dynamically generated as needed based on use case parameters. The template may be dynamically generated by input regions and or markets for deployment taste demographics psychographic profiles s application and or device type user type and or customer partner preferences. An example embodiment of dynamically generating a template is described in greater detail below.

The manually defined template that may be selected at block may be manually defined based on a use case. For example the manual selection may include 

Upon completion of the selection at block block or block a determination may be made at decision block whether to make another template selection for the navigation package. If a determination is made to make another template selection the method may return to decision block . If a determination is made not to make another selection at decision block the method may proceed to block .

Descriptor hierarchies mappings and navigational content corresponding to the selected templates may be associated with the navigation package at block .

Other lists may be associated with the navigation package at block . The other lists may include category lists not contained within the descriptor hierarchies .

A region for deployment may be selected at block . The selection of the region may be used in determining which descriptor systems . . will be used by the navigation template and the default and or alternate language labels that will be used to label the descriptor hierarchy .

The selection of the region may also be used in determining which navigational content parameters may be used. For example the navigational content parameters may include basic audio graphic voice or advanced settings. The selection of the region may be used in determining which text terms may be use in a mapping set. For example slang terms regional dialect terms professional terms and the like may be used as text terms in the mapping set.

Personal profile parameters may be selected at block . The personal profiles may include a taste profile based on age based on sex based on historical information explicit input and the like. The taste profile may be a classical view an electronica view a boomer view a generation X view and the like.

The selection of the personal profile may be used in determining which taste profile variation may be selected. For example the taste profile variation may be used in determining which view of the descriptor system may be made. The selection of the personal profile may also be used in determining alternate label terms selected for labelling of the descriptor hierarchy . For example the alternate labelling may include slang labels regional dialect labels informal labels old school labels and the like.

The selection of the personal profile may be used to determine which navigational content parameters and the related content parameters. For example the related content parameters may include basic audio graphic voice or advanced settings. The selection of the personal profile may also be used determining the text terms for a mapping set.

Application parameters see may be selected at block . The selection of the application parameters may be used in determining a number of levels e.g. a number of category lists to include in a hierarchy system and label formatting parameters.

Device parameters see may be selected at block . The selection of the device parameters may be used in determining a number of levels e.g. a number of category lists to include in a hierarchy system the length of category lists used at each level of the category list and label formatting parameters. For example the category list at each level may be twenty for a single level ten and seventy five for two levels twenty five two hundred and fifty and eight hundred for three levels and five for each of four levels. The selection of the device parameters may also be used in determining the related content parameters.

A user type see may be selected at block . The selection of the user type may be used in determining the length of category lists used at each level of the category list.

Third party IDs see may optionally be selected at block . The selection of one or more third party IDs may be used in determining which partner mapping selection may be used.

An identifier may be associated with a navigation tree at block . The navigation tree may include a sequence of category lists that may be taken from selected hierarchies and or entity types to be available for constructing UI elements based on the selection of application parameters device parameters user type and or other unique IDs.

Upon completion of the selections from the operations of blocks a navigation template may be definable based on the selections that were made. A unique identifier may optionally be associated with one or more navigation trees at block .

A template ID see may be generated at block . The identifier e.g. a unique identifier may be generated and stored based on the combination of the selected attributes of the navigation template . Unique IDs for the component attributes and the navigational profiles that drive the component attributes may also be associated with the identifier of the navigation template .

In an example embodiment current updated version of corresponding descriptor hierarchies the mappings and the navigational content may be retrieved based on the parameters in the navigation template. Other lists may also be retrieved for the use case.

Upon completion of the method a navigation package including default hierarchies alternate hierarchies mapping tables and navigational content appropriate for the use case may be available for deployment.

A determination may be made at decision block whether to code a media object e.g. a media item . If a determination is made to code the media object the media object may be embedded during production at block and or during encoding at block .

Identifiers and or master descriptor codes may be embedded e.g. as metadata containers in media objects during production e.g. during product and or post production at block . The embedded data may optionally be encrypted or otherwise obfuscated. The master descriptor codes may be associated with one or multiple entities of the media object.

Unique identifiers and or master descriptor codes may be associated with media objects during encoding e.g. during encoding and or other processing step as part of distribution at block .

Examples of identifiers that may be embedded during the operations at block or associated at block include DDEX GRID MI3P ID UPC EAN ISRC ISWC DOI ID commercial IDs public IDs e.g. FreeDB proprietary recording ID proprietary album ID or a proprietary composition ID. Other unique identifiers may also be embedded and or associated.

If a determination is made not to code the media object at decision block or upon completion of the operations at block and or block the method may proceed to decision block .

At decision block a determination may be made code another media object. If a determination is made to embed another media object the method may return to decision block . If a determination is made not to embed another media item at decision block the media objects may be delivered at block .

The media objects may be delivered with any metadata that has been embedded or associated. The delivery methods for providing the metadata with the media objects may include as part of a media object s exposed predefined tag field in a proprietary tag field as a watermark as MPEG 7 data as MPV or HiMAT Tag in an FM sideband e.g. RDS in a satellite radio data channel in a digital radio data channel or in an Internet radio data stream e.g. MPEG ancillary data . Other delivery methods may also be used.

A media collection may be pre loaded on the client at block . The media collection may be pre loaded prior to use by an end user. The media collection may be the same for all of a number of units a finite set of target libraries geared for a specific genre regional lifestyle or other interest or may be personalized based on a personal profile of an end user. The media collection may include audio files video files image files and the like.

Customer related content and information architecture elements may be ingested by the client at block .

Related content may be pre loaded e.g. prior to use by an end user on the client at block . The related content may include the navigational content and or other content. The other content may include album cover art artist photos concert posters text artist factoids lyrics channel station logos and the like.

The information architecture see may be pre loaded at block . The information architecture may be made locally accessible and subject to customization based on the template ID see . The template ID may be stored on the client for future use. The preloaded information architecture may include genre hierarchies era hierarchies origin hierarchies navigation trees mappings ordering data and station channel directories.

A request may be received for a navigation package including an information architecture at block . The request may also be made by obtaining a device ID generating a default template ID using the device ID and or issuing a request for a navigation package from the default template ID. Other methods for requesting the navigation package may also be used.

Predefined descriptor hierarchies may be accessed at block . A default descriptor hierarchy and optionally alternate descriptor hierarchies may be accessed for use in the information architecture . The descriptor hierarchies may optionally be accessed based on the template ID . The alternate hierarchies may be accessed from one or more different descriptor systems . .n.

By way of example the predefined descriptor hierarchies that may be accessed include one predefined and one or several alternate genre hierarchies a predefined and alternate origin hierarchies a predefined and alternate artist type hierarchies a predefined and alternate recording era hierarchies a predefined and alternate composition era hierarchies a predefined and alternate composition mood hierarchies a predefined and alternate temp or rhythm hierarchies a predefined and alternate composition theme topic hierarchies and the like.

Predefined navigation trees may be accessed at block . A default and optionally alternate navigation trees may be accessed for use in the information architecture . The navigation trees may be accessed from one or more descriptor systems . .n. The navigation trees may optionally be accessed based on the template ID .

By way of example the navigation trees may include genre era track genre mood tempo recording artist mood year track and genre album mood track. Other navigation trees may also be used.

Other category lists may be accessed at block . The other category lists may be used to generate alternate navigation trees descriptor hierarchies faceted navigation or other local navigation options that have not been pre defined. In an example embodiment a descriptor system may be retrieved to provide increased flexibility.

By way of example the other category lists may include a selected genre category list from a genre descriptor system a selected origin category list from an origin descriptor system a selected artist type category list from an artist type descriptor system a selected recording era category list from a recording era descriptor system a selected composition era category list from a composition era descriptor system a selected mood category list from a mood descriptor system a tempo category list from a tempo descriptor system a selected theme topic category list from a theme topic descriptor system and the like. The selected category lists may be supported by the client.

The descriptor relational tables may be accessed at block . A filter may optionally be applied to the descriptor relational tables that are accessed to obtain relational data for relationships with weightings above a threshold level.

Navigational content may be accessed at block . The default navigational content may be accessed using a navigational content ID.

Media items may be provided at block . The media items may be loaded and or transmitted into the client . An example embodiment of providing media items is described in greater detail below.

The provided media items may be identified e.g. through recognition at block . An example embodiment of recognizing the provided media items is described in greater detail below.

The media items may be mapped to entities at block . An example embodiment of mapping media items to entities is described in greater detail below.

Codes and content IDs may be received for the entities at block . An example embodiment of receiving codes and content IDS is described in greater detail below.

Indices may be created at block . The index may be into a unified data system. The index may physically reside on the client on another client in a local network on a remote server or distributed across more than one client. The indices may be created dynamically based on a client ID a user ID and or a combination of one or more parameters indicating a type of indexing that is relevant for a particular user. The indices may optionally indicate which one or more users are associated with a media collection.

A determination may be made at decision block whether to load content from a service directory or from a device. The content may include media objects in a variety of forms including audio video image text and spoken word audio. For example the formats of the media objects may include WAV MP3 AAC WMA OggVorbis FLAC analog audio or video MPEG2 WMV QUICKTIME JPEG GIF plaintext MICROSOFT WORD and the like.

The content may be loaded from a variety of media including by way of example optical media such as audio CD CD R CD RW DVD DVD R HD DVD Blu Ray hard disk drive HDD and other magnetic media solid state media including SD MEMORY STICK and flash memory stream and other IP or data transport. The content may reside locally or be available through a tether using connections such as LAN WAN Wifi WiMax cellular networks or the like.

The media objects may be taken from a variety of objects including an intra media item segment a media item e.g. audio video photo image text etc. a program a channel a collection or a playlist.

If a determination is made to load from a service directory one or more media items may be loaded from the service directory at block . The service directory may include local content AM FM HD radio satellite radio Internet on demand and streaming radio web page satellite and cable TV IPTV RSS and other web data feeds and other web services.

If a determination is made to load from a device one or more media items may be loaded from the device at block . The devices may include by way of example a PC a home media server an auto stereo a portable media player a mobile phone a PDA a digital media adapter a connected CD DVD Flash player changer a remote control a connected TV a connected DVD in flight entertainment or a location based system e.g. at a club restaurant or retail . Other devices may also be used.

Upon completion of the operations at block and or a determination may be made at decision block as to whether additional media items may be loaded. If additional media items may be loaded the method may return to decision block . If no additional media items may be loaded at decision block the method may terminate.

A determination may be made at decision block as to how identifier recognition may be performed on content. Identifier recognition may be performed by extracting the identifiers from the content at block recognizing the content using one or more techniques at block performing a lookup using a mapping table at block and or utilizing an embedded or associated identifier with the content at block .

The identifiers extracted during the operations at block may include but are not limited to TOCs TOPs audio file FP audio stream FP digital file file system data e.g. file tags file names folder names etc. image FP voice FP embedded entity IDs embedded descriptor IDs and a metadata data stream.

The one or more techniques used for recognizing the content at block may include optical media identifiers e.g. TOCs or TOPs digital file stream identifiers e.g. audio file FP audio stream FP or metadata data stream digital file and digital system data e.g. file tags file names or folder names image recognition voice speech recognition video FP recognition text analysis melody humming recognition and the like.

An example of a digital fingerprint technique that may be used during the operations at block to identify digital content is robust hashing. For example in mono audio a single signal may be sampled. If the audio is stereo either hash signals may be extracted for the left and the right channels separately or the left and the right channel are added prior to hash signal extraction. A short piece or segment of audio e.g. of the order of seconds may be used to perform the analysis. As audio can be seen as an endless stream of audio samples audio signals of an audio track may be divided into time intervals or frames to calculate a hash word for every frame. However any known technique that may used to identify content from a segment or portion of content e.g. the actual audio content or video content may be also used. Thus in an example embodiment the content may be identified independent of any watermark tag or other identifier but rather from the actual content data actual video data or actual audio data .

The embedded and or associated identifiers that may be used in performing a lookup using a mapping table at block may include a UPC an ISRC an ISWC a GRID MI3P DDEX a third party ID a SKU number a watermark HiMAT MPV and the like.

Upon completion of the operations at block block and or a determination may be made at decision block whether to perform text analysis recognition. If a determination is made to perform text analysis recognition a text match of entity names may be performed at block and or mapping tables may be utilized at block .

The text match of entity names to a more normalized entity ID at block may include artist name album name alternate spellings abbreviations misspellings and the like. The mapping tables may be utilized at block to map available textual descriptors from an available entity e.g. album artist or track to a normalized descriptor ID. The available textual descriptors may include a genre name text a mood name text a situation name text and the like.

If text analysis recognition is not to be performed or upon completion of the operations at block and or block the most granular descriptive data may be accessed at block . The most granular descriptive data may be embedded in a media item and or may be retrieved from the database of descriptors associated with the identifier.

The most authoritative descriptive data may be accessed at block . The most authoritative descriptive data may be embedded in a media item and or may be retrieved from the database of descriptors associated with the identifier.

Higher level descriptors may optionally be created at block . The higher level descriptors may be created by extracting features and classifying and creating one or more mid level or high level descriptors.

A taste profile may optionally be generated at block . The taste profile may be generated by summarizing the media collection and using the summary to generate the taste profile e.g. a preference of a user of the client .

Media identifiers may be mapped to entities at block . The media identifiers may optionally be mapped to normalized semantically meaningfully core entities. The media identifiers that may be mapped include but are not limited to a lyric ID a composition ID a recording ID a track ID a disc ID a release ID an edition ID an album ID a series ID a recording artist ID a composer ID a playlist ID a film TV episode ID a photo ID or a text work ID.

Parent and child entities may be mapped at block . The mapping may be a local map to hierarchically related semantically meaningful entities. Example of mappings between parent and child entities may include mapping between a composition ID a recording ID and a track ID a lyric ID a recording ID and a track ID a lyric ID a composition ID and a track ID a lyric ID a composition ID and a recording ID a track ID a release ID an edition ID an album ID and a series ID a track ID a disc ID an edition ID an album ID and a series ID a track ID a disc ID a release ID an album ID and a series ID a track ID a disc ID a release ID an edition ID and a series ID and a track ID a disc ID a release ID an edition ID and an album ID. Other mappings may also be used.

Relationally related entities may be mapped at block . For example segments may be mapped. An example of a map for relationally related entities includes a map between disc ID release ID edition ID album ID and series ID.

Descriptor codes may be received for the entities of the content at block . The retrieved descriptor codes may be for granular ordered or weighted factual and descriptive codes. The descriptor codes may be received from one or a plurality of sources locally and or over a network.

Unrecognized descriptor IDs may be optionally mapped at block . The mapping may translate the unrecognized descriptor code into a normalized descriptor code. Examples of maps that may be used to map the descriptor IDs include a genre map an origin map a recording era map a composition era map a mood map a tempo map and a situation map.

Descriptor IDs may optionally be mapped to entities without descriptor IDs at block . For example when a descriptor has not been mapped to parent and child entities via cascading prior to retrieval a local mapping to an entities without a direct descriptor ID may be performed after retrieval of a parent or child descriptor ID.

Alternative billings and collaboration artist IDs may be received at block . Mappings of alternative billing IDs to primary artist IDs and mappings of collaborations to component individual contributors may be received.

Navigational and related content IDs may be received at block . Navigational and related content IDs may include by way of example cover art an artist photo an artist bio an album review a track review a label logo a track audio preview a track audio a palette or phonetic data.

Related content may be received at block . Related content may be received by using a related content ID to request delivery of or unlocking of related content from local and or remote sources e.g. a store 

A single descriptor type hierarchy may be created at block . Default templates may be used to organize media items into one or more single descriptor type hierarchies that may optionally be normalized e.g. normalized single descriptor type hierarchy . Options for the single descriptor type hierarchy may include a number of levels an average number of categories under each note at each level and or the entity type contained in the lowest level categories e.g. track artist album or composition .

Example of single descriptor type hierarchies include meta genre genre sub genre track meta mood mood sub mood track meta origin origin sub origin track meta era era sub era track meta type type sub type track meta tempo tempo sub tempo track meta theme theme sub theme track meta situation situation sub situation track and meta work type work type sub work type track. Each of the single descriptor hierarchies may optionally be identified with a unique identifier.

Hierarchical views may be created using normalized metadata at block . The normalized metadata from recognition may be used to organize media items into summarized normalized single entity hierarchical views. The hierarchical views may be a single level or multiple levels. For example a main artist may be displayed at a top level and an alternate billing level may be displayed when applicable.

By way of example the hierarchical views may include recording artist track composer track album track recording track and composition track.

Hierarchical views may be created using existing metadata and or entity hierarchies from templates at block . The existing metadata and or entity hierarchies from the navigation templates may be used to organize media items into summarized normalized single entity hierarchical views. For example the views may include artist album track or composer composition recording. Other views may also be created.

Navigation trees may be created at block . The default navigation template may be used to organize media items into one or more navigation trees . The navigation trees may optionally be normalized and may include a unique identifier for subsequent identification.

A particular navigation tree may be defined by a number of levels of the tree the container e.g. a descriptor category or entity type used at each level of the tree and a number of categories for each category level of the tree e.g. which category list is used for the levels using category lists the entity type or types that are ultimately organized by the categories of the tree at the lowest level or alternatively the navigation tree may consistent only of levels of descriptors. The particular navigation tree may be further defined by the mappings from the master descriptor list to the category lists and the mappings from each category list to the other category lists.

Examples of navigation trees may include genre era track genre mood tempo recording artist mood year track genre year news article genre origin and the like.

A determination may be made at decision block whether a parameter was received. If a determination is made that the parameter was received the parameter may be processed to enable control at block . The parameter may be received to allow for control over a category list and entity item ordering at each level. For example the ordering options of the API input may include alpha numerical date time number of sub categories number of items in container editorial semantic relationship B e.g. similarity clustering editorial semantic relationship B e.g. liner sequence closest fit editorial importance or quality popularity e.g. may be static or dynamically generated custom and the like. If a determination is made that the parameter was not received at decision block the method may proceed to decision block .

At decision block a determination may be made as to whether a display selection has been received. If a determination is made that the display selection has been received the display selection may be processed at block . The display selection may specify e.g. through an API of the client whether to display metadata as is being from a media item or alternatively display a higher level category item label from a selected hierarchy category list for a descriptor category field. The display selection may optionally be used to override parameters inherited from a global profile for a device or application. If a determination is made that the display selection has not been received at decision block the method may proceed to decision block .

A determination may be made at decision block whether to perform a conversion. If a determination is made to perform a conversion e.g. based on instructions received through the API the conversion may be preformed at block . The conversion may be to convert text into alternate forms of presentation e.g. TLS for a name label field. If a determination is made not to perform the conversion at decision block the method may proceed to block .

The unified library of media items may be navigated at block . The unified library may include the media items available from the plurality of media sources . .n. The unified library may be navigated from the client and optionally another client on the network.

At decision block a determination may be made whether to modify the navigation. If a determination is made to modify the navigation the method may return to decision block . If a determination is made not modify the navigation at decision block the method may proceed to decision block .

A determination may be made at decision block whether to further navigate the unified library of media items. If a determination is made to further navigate the unified library the method may return to block . If a determination is made not to further navigate the unified library the method may terminate.

Global settings may be defined per client at block and per navigation tree at block . Settings may also be defined per navigation tree level at block .

A determination may be made at decision block whether to use personalized navigation. If a determination is made to use personalized navigation personalized navigation may be used at block .

Navigation may be personalized by providing tools for user tagging and to adapt tagging menus based on a profile. End users may be able to personalize by manually overriding category names entity item names and category groupings.

Navigation may also be personalized by dynamic configuration of hierarchies based on collection and or user profile. An end user may also manually select and or construct a hierarchy to be used for navigation. Content may be flagged and or tagged by the user at the client level and or file level.

Preferences may be stored remotely to be retrieved by a difference client e.g. application or device of the user and or may be transferred directly from one client to another via a wired or wireless connection.

If a determination is made not to use personalized navigation at decision block the method may proceed to decision block .

At decision block a determination may be whether to use dynamic personalization. If a determination is made to use dynamic personalization dynamic personalization may be used at block .

Assembled personal profile data may be accessed automatically to provide dynamic personalized navigation. An implicit profile may be overridden with any explicit input provided by the user. Sources used for dynamic personalization may include explicit input an index of user media collection including counts of media items per entities and per categories or an activity log that logs user activity to track activity across a current device or multiple devices of a user to an activity and consists of plays clicks time engages and or other factors.

The output of the dynamic personalization may be a combined profile. The profile may indicate a relative level of interest importance of category or entity item to the end user and may be stored remotely and or locally.

An alternative navigational tree may be dynamically constructed based on profile input. A determination may be made as to how many levels to step up or down for sub sections of the list in order to re tune. An example of the alternative navigation tree dynamically constructed is as follows 

Composite graphical audio video or textual navigational icons may be dynamically selected for personalization based on current contents of the container.

If a determination is made not to use personalized navigation at decision block the method may proceed to decision block .

A determination may be made at decision block whether to use contextual adaptation. If a determination is made to use contextual adaptation contextual adaptation may be used at block .

Contextual adaptation may use real time global textual adaptation and or real time personal contextual adaptation. The data may be accessible by a client either locally or remotely.

Examples of real time global contextual adaptation include use of location GPS cell time of day week season year date holidays weather acceleration speed temperature orientation object presence using technologies like RFID BLUETOOTH and public personal presence. Examples of real time personal contextual adaptation include use of personal location bookmarks using data provided by GPS or cellular networks personal time of day week year preference birthdays anniversaries weather preference personal tagged object presence known tagged personal presence heart rate and other bio data feeds.

If a determination is made not to use contextual adaptation at decision block the method may proceed to decision block .

At decision block a determination may be whether to restore navigation. If a determination is made to restore navigation navigation may be restored at block .

If a determination is made not to restore navigation at decision block the method may proceed to decision block .

A determination may be made at decision block whether to make further modifications. If a determination is made to make further modifications the method may return to decision block . If a determination is made not to make further modification the method may terminate.

The example computer system includes a processor e.g. a central processing unit CPU a graphics processing unit GPU digital signal processor DSP or any combination thereof a main memory and a static memory which communicate with each other via a bus . The computer system may further include a video display unit e.g. a liquid crystal display LCD or a cathode ray tube CRT . The computer system also includes an alphanumeric input device e.g. a keyboard a user interface UI navigation device e.g. a mouse a disk drive unit a signal generation device e.g. a speaker and a network interface device .

The disk drive unit includes a machine readable medium on which is stored one or more sets of instructions and data structures e.g. software embodying or utilized by any one or more of the methodologies or functions described herein. The software may also reside completely or at least partially within the main memory and or within the processor during execution thereof by the computer system the main memory and the processor also constituting machine readable media.

The software may further be transmitted or received over a network via the network interface device utilizing any one of a number of well known transfer protocols e.g. FTP .

While the machine readable medium is shown in an example embodiment to be a single medium the term machine readable medium should be taken to include a single medium or multiple media e.g. a centralized or distributed database and or associated caches and servers that store the one or more sets of instructions. The term machine readable medium shall also be taken to include any medium that is capable of storing encoding or carrying a set of instructions for execution by the machine and that cause the machine to perform any one or more of the methodologies of the present invention or that is capable of storing encoding or carrying data structures utilized by or associated with such a set of instructions. The term machine readable medium shall accordingly be taken to include but not be limited to solid state memories optical and magnetic media and carrier wave signals.

The device processor may receive content from a plurality of sources . .. The plurality of sources as illustrated include a mobile phone PDA . a CD DVD BLURAY HD DVD a media player . local and or remote storage . a radio station . internet access streaming content .. However other sources of content may also be used.

The content may be made navigable by an end user through user of a user interface coupled to a display an audio output and a user input e.g. for voice and or text . The information obtain by the device processor may be stored locally on the device storage and or remotely on a system database by use of a system server .

Although an embodiment of the present invention has been described with reference to specific example embodiments it will be evident that various modifications and changes may be made to these embodiments without departing from the broader spirit and scope of the invention. Accordingly the specification and drawings are to be regarded in an illustrative rather than a restrictive sense. The accompanying drawings that form a part hereof show by way of illustration and not of limitation specific embodiments in which the subject matter may be practiced. The embodiments illustrated are described in sufficient detail to enable those skilled in the art to practice the teachings disclosed herein. Other embodiments may be utilized and derived therefrom such that structural and logical substitutions and changes may be made without departing from the scope of this disclosure. This Detailed Description therefore is not to be taken in a limiting sense and the scope of various embodiments is defined only by the appended claims along with the full range of equivalents to which such claims are entitled.

Such embodiments of the inventive subject matter may be referred to herein individually and or collectively by the term invention merely for convenience and without intending to voluntarily limit the scope of this application to any single invention or inventive concept if more than one is in fact disclosed. Thus although specific embodiments have been illustrated and described herein it should be appreciated that any arrangement calculated to achieve the same purpose may be substituted for the specific embodiments shown. This disclosure is intended to cover any and all adaptations or variations of various embodiments. Combinations of the above embodiments and other embodiments not specifically described herein will be apparent to those of skill in the art upon reviewing the above description.

The Abstract of the Disclosure is provided to comply with 37 C.F.R. 1.72 b requiring an abstract that will allow the reader to quickly ascertain the nature of the technical disclosure. It is submitted with the understanding that it will not be used to interpret or limit the scope or meaning of the claims. In addition in the foregoing Detailed Description it can be seen that various features are grouped together in a single embodiment for the purpose of streamlining the disclosure. This method of disclosure is not to be interpreted as reflecting an intention that the claimed embodiments require more features than are expressly recited in each claim. Rather as the following claims reflect inventive subject matter lies in less than all features of a single disclosed embodiment. Thus the following claims are hereby incorporated into the Detailed Description with each claim standing on its own as a separate embodiment.

