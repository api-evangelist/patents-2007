---

title: System and method for generating 'snapshot's of learning objects
abstract: A system for generating a ‘snapshot’ of a learning object is provided. An interface receives a target object and a user identification number. The target object corresponds to a category, comprising a plurality of sentences and multimedia data, wherein the sentences comprise at least one keyword. A learning object database comprises a plurality of learning objects and a user's historical learning record. Each of the learning objects corresponds to at least one category, and comprises at least one keyword. The user's historical learning record comprises a track record of learning objects used corresponding to the user identification number. A script preview unit selects at least one of the sentences of the target object according to the user's historical learning record corresponding to the user identification number. A multimedia preview unit selects one of the multimedia data of the target object, wherein the selected multimedia data is highly related to the selected sentence. A ‘snapshot’ generator generates a ‘snapshot’ of the target object by combining the selected sentence and the selected multimedia data, and directs a display device to display the ‘snapshot’.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=07930298&OS=07930298&RS=07930298
owner: Institute for Information Industry
number: 07930298
owner_city: Taipei
owner_country: TW
publication_date: 20071227
---
The invention relates to data processing and in particular to systems and methods for generating a snapshot of a learning object.

This section is intended to introduce the reader to various aspects of art which may be related to various aspects of the present invention which are described and or claimed below. This discussion is believed to be helpful in providing the reader with background information to facilitate a better understanding of the various aspects of the present invention. Accordingly it should be understood that these statements are to be read in this light and not as admissions of prior art.

Many learning resource databases provide Application Programming Interface API for other website access and use SQI Simple Query Interface to define an interface to facilitate cross site search operations.

Generally cross site search operations locate large amounts of learning objects and description of these learning objects does not provide adequate information to meet user requirements.

According to a conventional method a provider of a learning object can generate a snapshot of the learning object by composing an abstract of the learning object and combining the abstract with pictures pertinent to the learning object.

The conventional method however is inconvenient for the provider of the learning object. In addition the snapshot is composed from the viewpoint of the provider. Accordingly contents of the snapshot do not provide adequate information for a user to determine whether he she is interested in the learning object. Even though the learning object has a snapshot it is still inconvenient for a user to use it.

Hence there is a need for a method and system for generating a snapshot of a learning object better addressing the problems arising from the existing technology.

Certain aspects commensurate in scope with the originally claimed invention are set forth below. It should be understood that these aspects are presented merely to provide the reader with a brief summary of certain forms the invention might take and that these aspects are not intended to limit the scope of the invention. Indeed the invention may encompass a variety of aspects that may not be set forth below.

A system for generating a snapshot of a learning object is provided. The system for generating a snapshot of a learning object comprises an interface a learning object database a script preview unit a multimedia preview unit and a snapshot generator. The interface receives a target object and a user identification number. The target object corresponds to a category comprising a plurality of sentences and multimedia data wherein the sentences comprise at least one target object keyword. The learning object database comprises a plurality of learning objects and a user s historical learning record. Each of the learning objects corresponds to at least one category and comprises at least one learning object keyword. The user s historical learning record comprises a track record of learning objects used corresponding to the user identification number. The script preview unit selects at least one of the sentences of the target object as a preview sentence according to the user s historical learning record corresponding to the user identification number. The multimedia preview unit selects one of the multimedia data of the target object as a preview multimedia data wherein the selected multimedia data is highly related to the selected sentence. The snapshot generator generates a snapshot of the target object by combining the preview sentence and the preview multimedia data and directs a display device to display the snapshot .

Also provided is a method for generating a snapshot of a learning object. A target object is received. The target object corresponds to a category. The target object comprises a plurality of sentences and multimedia data wherein the sentences comprise at least one target object keyword. A user identification number is received. A learning object database is provided. The learning object database comprises a plurality of learning objects and a user s historical learning record. Each of the learning objects corresponds to at least one category and comprises at least one learning object keyword. The user s historical learning record comprises a track record of learning objects used corresponding to the user identification number. At least one of the sentences of the target object is selected as a preview sentence according to the user s historical learning record corresponding to the user identification number. One of the multimedia data of the target object is selected as a preview multimedia data wherein the selected multimedia data is highly related to the selected sentence. A snapshot of the target object is generated by combining the preview sentence and the preview multimedia data. The snapshot is then displayed.

One or more specific embodiments of the invention are described below. In an effort to provide a concise description of these embodiments not all features of an actual implementation are described in the specification. It should be appreciated that in the development of any such actual implementation as in any engineering or design project numerous implementation specific decisions must be made to achieve specific developer goals such as compliance with system related and business related constraints which may vary from one implementation to another. Moreover it should be appreciated that such a development effort might be complex and time consuming but would nevertheless be a routine undertaking of design fabrication and manufacture for those of ordinary skill in the art having the benefit of this disclosure.

In the following detailed description reference is made to the accompanying drawings which form a part hereof shown by way of illustration of specific embodiments. These embodiments are described in sufficient detail to enable those skilled in the art to practice the invention and it is to be understood that other embodiments may be utilized and that structural logical and electrical changes may be made without departing from the spirit and scope of the invention. The following detailed description is therefore not to be taken in a limiting sense. The leading digit s of reference numbers appearing in the figures corresponds to the figure number with the exception that the same reference number is used throughout to refer to an identical component which appears in multiple figures. It should be understood that the many of the elements described and illustrated throughout the specification are functional in nature and may be embodied in one or more physical entities or may take other forms beyond those described or depicted.

The learning object database comprises plurality of learning objects and a plurality of items of user s historical learning record .

Each of the learning objects corresponds to at least one category and each of learning objects comprises at least one learning object keyword.

Each item of the user s historical learning record comprises a track record of learning objects used corresponding to a specific user identification number. For example name of learning objects that are used a user identified by the specific user identification number as well as categories to which the learning objects are corresponded to and keywords comprised in the learning objects .

Interface receives a target object . The target object corresponds to a category comprising a plurality of sentences and multimedia data wherein the sentences comprise at least one keyword target object keyword . The sentence is constituted by text. The multimedia data comprises video and or audio data figures tables and other types of data.

A keyword can also be provided when a snapshot in connection with the keyword is to be generated based on the target object .

The script preview unit selects at least one of the sentences of the target object as a preview sentence according to the user s historical learning record corresponding to the user identification number . The way in which the script preview unit selects the preview sentence is described later. The preview sentence selected by the script preview unit is provided to the multimedia preview unit and the snapshot generator for further use.

The multimedia preview unit selects one of the multimedia data of the target object as a preview multimedia data wherein the selected multimedia data is highly related to the preview sentence . The way in which the multimedia preview unit selects the preview multimedia data is described later. The preview multimedia data selected by multimedia preview unit is provided to the snapshot generator for further use.

The snapshot generator generates a snapshot of the target object by combining the preview sentence and the preview multimedia data and directs a display device to display the snapshot .

In the method of a customized learning object snapshot is generated automatically according to a user identification number and a keyword input by a user.

In step S a target object is provided. The target object is a user defined target of analysis. The target object can be a learning object corresponding to a category and comprising a plurality of sentences and multimedia data wherein the sentences comprise at least one keyword target object keyword . The sentence is constituted by text. The multimedia data comprises video and or audio data figures tables and other types of data.

In step S a pre process is executed on the target object. Here the pre process comprises a step of separating text data and multimedia data comprised in the target object.

In step S a script preview procedure is executed wherein at least one of the sentences of the target object is selected as a preview sentence according to the user s historical learning record corresponding to the user identification number. Details of the script preview procedure are described later.

In step S a multimedia preview procedure is executed wherein one of the multimedia data of the target object is selected as a preview multimedia data wherein the selected multimedia data is highly related to the selected sentence. Details of the multimedia preview procedure are described later.

In step S a snapshot of the target object is generated by combining the preview sentence and the preview multimedia data.

In step S a learning object database is provided. The learning object database comprises a plurality of learning objects and a user s historical learning record. Each of the learning objects corresponds to at least one category and comprises at least one learning object keyword. The user s historical learning record comprises a track record of learning objects used corresponding to the user identification number.

In step S a relationship matrix of the plurality of sentences in the target object is calculated wherein the relationship matrix comprises a relationship value R for each pair of the plurality of sentences. The relationship value of sentences Si and Sj is calculated according to the following equation 

Ui represents binary terms in the sentence Si of the target object Uj represents binary terms in the sentence Sj of the target object Ui Uj represents a total number of the binary terms of Ui and Uj and Ui Uj represents a number of binary terms appearing in both Ui and Uj.

According to equation 1 binary terms are used as a basis of calculation. Therefore the numerator is multiplied by 2. Accordingly the multiplier for the numerator of equation 1 can be changed when different calculation basis is adopted for equation 1 .

In step S a sum of the relationship values of each of the sentences S S and other sentences of the sentences S S is calculated. The relationship matrix shown in comprises the sum of the relationship values of each of the sentences S S and other sentences of the sentences S S.

In step S a customized pertinent keyword is determined. The pertinent keyword is determined by selecting a pertinent keyword B relating to the target object from the plurality of learning objects according to the user s historical learning record corresponding to the user identification number. Details of step S are described later.

In step S the sentence is selected from the target object and is regarded as the preview sentence. The selected sentence contains the largest amount of information among the sentences i.e. the sentence having a relationship value higher than the others and contains the user keyword A and or the pertinent keyword B. The preview sentence is selected according to the relationship values of each of sentences S S calculated in step S the user keyword A received in step S and the pertinent keyword B determined in step S.

Referring to among sentences S S sentences having higher relationship values are sentences S S S and S in a high to low order . When preview sentences are to be selected sentences S S and S are selected without considering keywords comprised in these sentence . When keywords are taken into account such as keyword A and or B sentences comprising keyword A and or B are first selected and the sentences having higher relationship values are then selected as the preview sentences from the selected sentences.

In step S the user identification number is retrieved wherein the user identification number is input by a user.

In step S the keywords comprised in the target object are obtained as well as the category corresponding to the target object. Here the target object corresponds to category and category the target object comprises keyword and keyword .

In step S at least one learning object is selected from the plurality of learning objects according to the user s historical learning record wherein the selected learning object has the category identical with the target object and has been used by a user identified by the user identification number. For example a set of learning objects learning object set is selected wherein the learning objects within the learning object set corresponds to category and category . A set of learning objects learning object set is selected from learning object set wherein the learning object set comprises learning objects that have been used by a user identified by the user identification number.

In step S the learning object comprising the target object keyword is selected from the learning objects selected in step S. For example a set of learning objects learning object set is selected from learning object set wherein the learning object set comprises learning objects containing the keyword or keyword .

In step S a search is performed for the learning object keyword comprised in the learning objects selected in step S and the learning object keyword that is not comprised in the target object is adopted as the pertinent keyword B. For example a plurality of learning objects are comprised in learning object set . In addition to keyword and keyword the learning objects of learning object set comprise keyword keyword and keyword . Accordingly keyword keyword and keyword are selected as preliminary pertinent keywords.

If too many pertinent keywords are used in the method of generating a snapshot of a learning object inefficiencies of the process would occur and the results obtained would be greatly affected. Accordingly step S can be performed to further select proper pertinent keywords from the pertinent keyword determined in step S. For example among keyword keyword and keyword the one which is contained in a learning object that has been accessed recently is selected as the pertinent keyword. For example keyword is contained in a learning object that has been accessed recently. Accordingly keyword is selected as the pertinent keyword for determining the preview sentence.

In step S a relationship value for each pair of the sentences of the target object is calculated wherein the relationship value calculated in step S can be used i.e. the

In step S the relationship value is divided by the distance between each of the multimedia data and each of the sentences within the target object to obtain the relationship between each of the multimedia data and each of the sentences within the target object. For example distance between multimedia data and a sentence is presented by number of characters located between the multimedia data and the sentence. The distance between sentence Si and multimedia data Gj is presented by d Si Gi .

In step S the relationship between each of the multimedia data and each of the sentences within the target object is calculated according to the R i j obtained in step S and the d Si Gi determined in step S. The relationship is calculated according to the following equation 

In step S the multimedia data at the shortest distance from the preview sentence is selected as the preview multimedia data according to the relationship matrix.

While the invention has been described by way of example and in terms of preferred embodiment it is to be understood that the invention is not limited thereto. To the contrary it is intended to cover various modifications and similar arrangements as would be apparent to those skilled in the art . Therefore the scope of the appended claims should be accorded the broadest interpretation so as to encompass all such modifications and similar arrangements.

