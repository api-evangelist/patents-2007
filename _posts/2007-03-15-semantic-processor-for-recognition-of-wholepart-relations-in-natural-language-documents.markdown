---

title: Semantic processor for recognition of whole-part relations in natural language documents
abstract: A semantic processor and method for automatically recognizing Whole-Part relations in at least one natural language electronic or digital document recognizes one or more expanded Subject-Action-Object (eSAO) sets in text, wherein each eSAO set has one or more eSAO components; matches the one or more eSAO sets against Whole-Part relationship patterns, and generates one or more eSAO Whole-Part relations based on the matching, wherein the eSAO Whole-Part relation comprises a Whole eSAO and an Part eSAO.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08799776&OS=08799776&RS=08799776
owner: Invention Machine Corporation
number: 08799776
owner_city: Boston
owner_country: US
publication_date: 20070315
---
The present application is a continuation in part application of co pending U.S. patent application Ser. No. 10 208 941 filed Jul. 31 2002 entitled Computer Based Summarization of Natural Language Documents published as U.S. Patent App. Pub. No. 20030130837 on Jul. 10 2003 which claims priority to U.S. Provisional Application Ser. No. 60 308 886 titled Computer Based Summarization of Natural Language Documents filed Jul. 31 2001 . These applications are incorporated herein by reference in their entirety.

The present application while not claiming priority to may also be related to the following U.S. Pat. No. 6 167 370 Document Semantic Analysis Selection with Knowledge Creativity Capability utilizing Subject Action Object SAO structures issued Dec. 26 2000 to Tsourikov et al. which is incorporated herein by reference in its entirety.

This application relates to systems and methods for automatic knowledge recognition and extraction from documents in electronic or digital form which reflect Whole Part semantic relations between objects concepts and facts of the outside world subject domain.

The following U.S. Patent documents provide descriptions of art related to the present application U.S. Pat. No. 5 418 889 issued May 1995 to Ito hereinafter Ito U.S. Pat. No. 5 696 916 issued December 1997 to Hitachi hereinafter Hitachi U.S. Pat. No. 6 026 388 issued February 2000 to Liddy et al. hereinafter Liddy U.S. Pat. No. 6 185 592 issued February 2001 to Boguraev et al. hereinafter Boguraev 1 U.S. Pat. No. 6 212 494 issued April 2001 to Boguraev hereinafter Bogureav 2 U.S. Pat. No. 6 263 335 issued July 2001 to Paik et al. hereinafter Paik U.S. Pat. No. 6 754 654 issued June 2004 to Kim et al. hereinafter Kim U.S. Pat. No. 6 823 325 issued November 2004 to Davies et al. hereinafter Davies and U.S. Pat. No. 6 871 199 issued March 2005 to Binniget et al. hereinafter Binniget .

Knowledge bases and knowledge engineering are the key components of modern information systems and correspondingly technologies. Knowledge engineering was traditionally based on generalization of information obtained from experts in different knowledge domains. However analysis shows that this approach cannot be utilized for creating adequate real life industrial applications. Two questions arise first what can be the most reliable and effective source of such knowledge and second how can this knowledge be recognized extracted and later formalized. Analysis shows that at the present time the time of global computerization the most reliable source of knowledge is text in the broad sense of the word that is text as a set of documents in natural language books articles patents reports etc. . Thus the basic premises of knowledge engineering in the light of the second question are as follows 

The second premise may seem excessively categorical but with the tendency to increase the text range this is more and more the case.

What types of knowledge can be obtained from text and with what automatic means Some existing methods are aimed at databases having a strict structure and manually compiled or at texts with strictly defined fields. A shallow linguistic analysis of text is usually performed. Kim describes processing text with a rigid structure primarily emails . Kim s process extracts corresponding information from previously known fields of source documents and places it in predefined fields of a database DB that reflects the structure of the organization such a DB has for example fields for names and titles of individuals within an organization . The linguistic processing described in Kim is utilized only for the extraction of key terms from documents according to the so called filters.

Davies describes the performance of lexical and grammatical analysis of text in order to differentiate nouns from verbs and to perform in such a way a strongly definite search in a predefined and structured database according to how why what and what is relations.

Binniget also describes the use of a pre structured database i.e. a Knowledge Database in the form of a fractal hierarchical network which reflects the knowledge of the outside world knowledge domain in order to automatically expand information from an input string. Initially the input string for example part of sentence or the whole sentence etc. is treated with a semantic processor that performs syntactic and grammatical parsing and transforming to build an input network. This network is then immersed into the Knowledge Database to expand the input information that is some kind of recording and later expansion of input information by means of a model of the outside world concerning objects their relations and attributes.

Boguraev 1 describes the performance of a deep text analysis where for text segments the most significant noun groups are marked on the basis of their usage frequency in weighted semantic roles.

All abovementioned cases are concern with a particular knowledge about concepts. This is an entry level of knowledge that can be extracted from text.

Boguraev 2 describes the use of computer mediated linguistic analysis to create a catalog of key terms in technical fields and to also determine doers solvers of technical functions verb object .

Hitachi describes a system that uses a predefined concept dictionary with high low relations namely is a relations and part whole relations between concepts.

Ito describes the use of a Knowledge Base including a Causal Model Base and a Device Model Base. The Device Model Base has sets of device knowledge describing the hierarchy of devices of the target machine. The Casual Model Base is formed on the basis of the Device Model Base and has sets of casual relations of fault events in the target machine. Thus the possible cause of failure in each element of the device is guessed on the basis of information about its structural connections with other elements of the device. Usually these are the most connected elements which are determined as the cause.

Paik describes a system that is domain independent and automatically builds its own subject knowledge base. The system recognizes concepts any named entity or idea such as a person place thing or organization and relations between them. These relations allow the creation of concept relation concept triples. Thus the knowledge recognized in Paik is close to the next important knowledge level facts subject action object although they are not yet facts suitable for recognition of such important semantic relations as Whole Part relations.

In fact none of the above approaches teach or suggest processing text in electronic documents or digital information to determine Whole Part semantic relations between objects concepts and facts of the outside world subject domain.

In accordance with aspects of the present invention provided a method for automatically recognizing Whole Part relations in natural language documents. The method comprises providing text from at least one natural language document recognizing one or more expanded Subject Action Object eSAO sets in the text wherein each eSAO set has one or more eSAO components matching the one or more eSAO sets against Whole Part relationship patterns and generating one or more eSAO Whole Part relations based on the matching wherein the eSAO Whole Part relation comprises a Whole eSAO and an Part eSAO.

The one or more eSAO components can be one or more elements from a group comprising subjects objects actions adjectives prepositions indirect objects and adverbs.

The Whole eSAO can comprise one or more of the eSAO components or a part of a single eSAO component of the one or more eSAO sets and the Part eSAO can comprise one or more of the eSAO components or a part of a single eSAO component of the one or more eSAO sets.

The eSAO Whole Part relations can comprise a sequential operator relating the eSAO components of the Whole eSAO to the eSAO components of the Part eSAO the operator including one or more of a lexical grammatical and semantic language indicator.

The method can further comprise applying parts of speech tags to at least portions of the text to generate tagged portions of the text and parsing the tagged portions of the text to generate parsed and tagged portions of the text wherein recognizing the eSAO sets in the text is performed on the parsed and tagged portions of the text.

Applying parts of speech tags can be performed on preformatted portions of the text whereby the preformatted portions of the text comprise the text with non natural language symbols removed.

Matching the one or more eSAO sets against Whole Part relationship patterns can comprise matching a single eSAO set and generating one or more eSAO Whole Part relations based on the matching can comprise generating a single eSAO Whole Part relation.

Matching the one or more eSAO sets against Whole Part relationship patterns can comprise matching a pair of eSAO sets and generating one or more eSAO Whole Part relations based on the matching can comprise generating a single eSAO Whole Part relation based on matching the pair of eSAO sets.

Matching the one or more eSAO sets against Whole Part relationship patterns can comprise accessing a Whole Part pattern database that is generated by a method comprising recognizing eSAO sets in a corpus of text documents generating a corpus of sentences wherein each sentence contains at least one of the recognized eSAO sets recognizing particular cases of Whole Part relations in the sentences generalizing the particular cases of Whole Part relations into eSAO Whole Part patterns and storing the eSAO Whole Part patterns in the Whole Part pattern database.

Recognizing one or more expanded Subject Action Object eSAO sets in the text can comprise accessing a linguistic knowledge base having a database defining eSAO component definitions in the form of Recognizing Linguistic Models.

Recognizing one or more expanded Subject Action Object eSAO sets in the text can comprise recognizing one or more of subjects objects actions adjectives prepositions indirect objects and adverbs in one or more sentences of the text.

In accordance with another aspect of the invention provided is a method for generating a Whole Part knowledge base by automatically recognizing Whole Part relations in natural language documents. The method comprises providing text from at least one natural language document recognizing one or more expanded Subject Action Object eSAO sets in the text wherein each eSAO set has one or more eSAO components matching the one or more eSAO sets against Whole Part relationship patterns generating one or more eSAO Whole Part relations based on the matching wherein the eSAO Whole Part relation comprises a Whole eSAO and an Part eSAO and storing the one or more eSAO Whole Part relations in the Whole Part knowledge base.

In accordance with another aspect of the invention provided is a computer program product comprising a computer readable medium having computer executable instructions for performing a method for recognizing Whole Part relations in natural language documents. The method comprises providing text from at least one natural language document recognizing one or more expanded Subject Action Object eSAO sets in the text wherein each eSAO set has one or more eSAO components matching the one or more eSAO sets against Whole Part relationship patterns and generating one or more eSAO Whole Part relations based on the matching wherein the eSAO Whole Part relation comprises a Whole eSAO and an Part eSAO.

The method can further comprise storing the one or more eSAO Whole Part relations in a Whole Part knowledge base.

In accordance with another aspect of the invention provided is a semantic processor for automatically recognizing Whole Part relations in text in electronic or digital form the semantic processor comprising a linguistic knowledge base and a semantic analyzer. The semantic analyzer comprises an expanded subject action object eSAO recognizer for producing one or more eSAO sets based on the text wherein the eSAO sets are based on eSAO definitions stored in the linguistic knowledge base in the form of Recognizing Linguistic Models and a Whole Part recognizer configured to match the one or more eSAO sets with known Whole Part relationship patterns stored in the linguistic knowledge base and to produce one or more eSAO Whole Part relations based on the match.

The semantic processor can comprise a linguistic analyzer that comprises the semantic analyzer. The linguistic analyzer can further comprise a part of speech tagger configured to apply parts of speech tags to at least portions of the text and a parser configured to parse the text tagged by the parts of speech tagger and to provide the parsed and tagged text to the expanded subject action object eSAO recognizer.

The semantic processor can further comprise a preformatter configured to receive the text in electronic or digital format and to produce preformatted text based on data stored in the linguistic knowledge base for input to the part of speech tagger and a knowledge base generator configured to produce a Whole Part knowledge base from the one or more eSAO Whole Part relations generated by the linguistic analyzer.

The preformatter can be configured to perform at least one of the following functions remove symbols in a digital or electronic representation of the text that do not form a part of natural language text detect and correct mismatches or mistakes in the text and partition the text into structures of sentences and words.

The semantic processor can further comprise a Whole Part relationship generator configured to generate and store the known Whole Part relationship patterns. The Whole Part relationship generator can comprise a corpus linguistic analyzer configured to recognize eSAO sets in a corpus of text documents a corpus eSAO generator configured to generate a corpus of sentences wherein each sentence contains at least one of the recognized eSAO sets a relation recognizer configured to recognize particular cases of Whole Part relations in the sentences a pattern generator configured to generalize the particular cases of Whole Part relations to eSAO Whole Part patterns and a pattern tester configured to store the eSAO Whole Part patterns in a Whole Part pattern database.

The one or more eSAO Whole Part relations can each comprise a Whole eSAO a Part eSAO and at least one sequential operator relating the Whole eSAO to the Part eSAO.

Each eSAO set based on the text can comprise eSAO components and the Whole eSAO can comprise one or more of the eSAO components and the Part eSAO can comprise one or more of the eSAO components different than the one or more eSAO components of the Whole eSAO.

The eSAO components can comprise one or more elements from a group comprising subjects objects actions adjectives prepositions indirect objects and adverbs.

The Whole Part recognizer can be further configured to match a single eSAO set with a known Whole Part relationship pattern to generate a single eSAO Whole Part relation.

The Whole Part recognizer can be further configured to match a pair of eSAO sets with a known Whole Part relationship pattern to generate a single eSAO Whole Part relation.

It will be understood that although the terms first second etc. may be used herein to describe various elements these elements should not be limited by these terms. These terms are used to distinguish one element from another but not to imply a required sequence of elements. For example a first element can be termed a second element and similarly a second element can be termed a first element without departing from the scope of the present invention. As used herein the term and or includes any and all combinations of one or more of the associated listed items.

It will be understood that when an element is referred to as being on or connected or coupled to another element it can be directly on or connected or coupled to the other element or intervening elements may be present. In contrast when an element is referred to as being directly on or directly connected or directly coupled to another element there are no intervening elements present. Other words used to describe the relationship between elements should be interpreted in a like fashion e.g. between versus directly between adjacent versus directly adjacent etc. .

The terminology used herein is for the purpose of describing particular embodiments only and is not intended to be limiting of the invention. As used herein the singular forms a an and the are intended to include the plural forms as well unless the context clearly indicates otherwise. It will be further understood that the terms comprises comprising includes and or including when used herein specify the presence of stated features steps operations elements and or components but do not preclude the presence or addition of one or more other features steps operations elements components and or groups thereof.

In the various embodiments provided is a system and method for automatic recognition and extraction from documents in electronic or digital form of very important knowledge reflecting Whole Part semantic relations between objects concepts and facts. For example Whole Part semantic relations between objects concepts show what components a certain technical device includes. And whole part semantic relations between facts for example show operations a certain technological process includes and an order of the operations.

In accordance with aspects of the present disclosure unlike prior approaches that detected semantic relations between SAOs only expanded SAOs eSAOs are used. In a preferred embodiment eSAOs include seven components where again at least one eSAO component is defined. The additional components provide a greater depth and quality of analysis. In other embodiments the eSAOs could be expanded to include additional components. In this document the terms eSAO and eSAO set are used interchangeably where both terms refer to a collection of eSAO components.

One of the types of semantic relations between facts i.e. between eSAO is Cause Effect relations as discussed in U.S. Patent Appl. Pub. No. 20030130837 titled Computer Based Summarization of Natural Language Documents. Recognition of Cause Effect relations is also described in that publication. For example the input sentence Today the user can download 10 000 papers from the web by typing the word screen. will result in the Cause Effect relation between eSAOs shown in Table 3.

Semantic processing is used to establish the Whole Part relations present in the knowledge from the eSAOs within natural language documents. Given that objects are constituent parts of facts complete or incomplete the eSAO format is considered here as the format for formal knowledge representation of document content.

In the illustrative embodiments the semantic processing for recognizing Whole Part relations in text in electronic or digital form comprises preformatting the text performing linguistic analysis and generating a Whole Part Knowledge Base.

An embodiment of a Whole Part Semantic Processor hereinafter Semantic Processor SP in accordance with aspects of the present invention may be appreciated with reference to . The Semantic Processor processes an original text to generate a Whole Part Knowledge Base . In this embodiment the Semantic Processor includes a Preformatter for preformatting the original text a Linguistic Analyzer for performing linguistic analysis and a Knowledge Base Generator for generating the Whole Part Knowledge Base . The functionality of all the modules of the Semantic Processor may be maintained within a Linguistic Knowledge Base which includes various databases such as dictionaries classifiers statistical data etc. and a database for recognizing linguistic models for text to words splitting recognition of noun and verb phrases subject object action and their attributes cause effect recognition etc. . The Linguistic Analyzer and the Knowledge Base Generator are described in additional detail below. The text preformatting performed by the Preformatter is preferably performed according to the techniques described in U.S. Patent Appl. Pub. No. 20030130837. Preferably preformatting the text includes removing non natural language symbols e.g. punctuation from the text.

This rule means that if an input sentence contains a sequence of words w1 w2 w3 which at the step of part of speech tagging obtained HVZ BEN VBN tags respectively then the word with VBN tag in this sequence is in Action. For example has  HVZ been BEN produced VBN A produce . Furthermore the voice of the action active or passive voice is taken into consideration in the rules for extraction of Subject and Object.

Recognition of Whole Part relations within and or between the eSAOs is performed by the Whole Part W P Recognizer which then produces the semantically analyzed text . An embodiment of this procedure is described below in more detail according aspects of the present invention.

The Whole Part recognizer uses algorithms for detecting Whole Part relations in text sentences within a single eSAO as well as between different eSAOs. These algorithms can be categorized as generating linguistic models or patterns. Firstly the patterns describe the use environment i.e. indicators of presence of Whole Part relations in a sentence and secondly the information about which components of a single eSAO act as the Whole element of the relation and which components of a single eSAO or set of eSAOs act as the Part element of the relation. Whole Part indicators refer to separate eSAO components and describe linguistic units their lexical and grammatical tags semantic classes etc.

The Whole Part Recognizer preferably analyzes all eSAOs and sets of eSAOs for compliance with one of the patterns from a common list. If an eSAO or set of eSAOs complies with a pattern the Whole Part recognizer registers the presence of Whole Part a relation and marks which components of the eSAO or set of eSAOs are semantic units of the Whole type and which semantic units are of the Part type in accordance with the pattern. The eSAOs and sets of eSAOs marked this way are then directed to the Knowledge Base Generator see which forms a list of objects concepts and a list of facts having a Whole Part relation between them and stores the lists in the Whole Part Knowledge Base .

Presented below are the preferred patterns for recognition of Whole Part relations in text in accordance with this embodiment. However other patterns may also be used in accordance with other embodiments.

This pattern arises if an eSAO is recognized in the text and the eSAO has at least three non empty fields for Subject Action and Object. Two cases are possible for this pattern in this embodiment. In the first case Subject has a PART OF sense the Object is not empty and the Action linking the Subject to the Object is of LINK VERB sense. In the second case the Action has the same sense the Subject is not empty and the Object has PART OF sense. In any case the certain part of the eSAO component Subject or Object that has PART OF sense is recognized as the Whole component of the output relation and the other component of the indicated pair of components is recognized as the Part.

In this pattern the PART OF Subject Object sense is a non terminal symbol denoting any word or phrase not having the word of therein and ending with a word or phrase matching at least one word of the following list part component constituent element unit construct ingredient interior inside followed by the word of and further followed by any word or phrase. The part of the Subject Object following the word of is recognized as the Whole part of the output relation. In a preferred embodiment the LINK VERB sense at least matches the words or phrases be present represent. Table 4 shows the generic form of Pattern 1 for the first case.

As example consider the input sentence to be The principal part of the car is the driver s wheel. Table 5 shows the eSAO extracted from the sentence 

Because this eSAO meets the conditions of the Pattern 1 the following Whole Part relation is obtained 

For example the input sentence The driver s wheel represents the principal part of the car would result in the eSAO shown in Table 7.

Pattern 2 arises if the Action field has a COMPRISE sense or is expressed by verbs have or include. In this pattern a COMPRISE Action sense is a non terminal symbol denoting at least the words or phrases comprise contain incorporate consist of Table 8 shows the generic form of Pattern 2.

In case Action is expressed by the verb have it must be presented by the having form in the original sentence. Action expressed by the verb include and presented by the including form in the original sentence must have the related eSAO with Subject in singular number.

For example the input sentences The internal combustion engine contains the camshaft The internal combustion engine having the camshaft The internal combustion engine includes the camshaft The internal combustion engine including the camshaft would each result in the corresponding eSAOs shown in Table 9.

Because all these eSAO meet the conditions of the Pattern 2 the following Whole Part relation is obtained 

There are two types of such a pattern. In first case the pattern arises if the Action field has an EQUIP sense and Preposition field has a WITH sense. In this case the EQUIP Action sense is a non terminal symbol denoting at least the words or phrases equip provide supply instrument. The WITH Preposition sense is a non terminal symbol denoting at least the word with. Table 10 shows the generic form of Pattern 3 for this case.

For example the input sentence of The car is equipped with the engine would result in the eSAO shown in Table 11.

In the second case Pattern 3 arises if the Action field has a POSITION sense and is expressed in the original sentence by a verb in passive mode and the Preposition field has an INSIDE sense. In this pattern the POSITION Action sense is a non terminal symbol at least matching words or phrases equip provide supply instrument. The INSIDE Preposition sense is a non terminal symbol that at least matches words or phrases inside within. Table 12 shows the generic form of Pattern 3 for this case.

For example the input sentence of The engine is located inside the card would result in the eSAO shown in Table 13.

Pattern 4 arises if a NounPhrase denoting Subject component or Object component of an eSAO contains the following structure NG1 CONTAINING RICH NG2

In this pattern NG1 and NG2 are non terminal symbols denoting noun groups CONTAINING is a non terminal symbol that at least matches the words containing comprising incorporating RICH is a non terminal symbol denoting at least the words rich based laden enriched reduced fortified. In this case NG2 is recognized as the Whole component of the Whole Part relation and NG1 is recognized as the Part component.

For example the input sentences the example contains only sentence parts necessary for pattern illustration Gold containing cord is . . . and Oxygen rich water is . . . meet the conditions of pattern 4 and the following Whole Part relations are correspondingly obtained 

Pattern 5 is aimed at extraction of Whole Part relations between eSAOs where one eSAO denotes the Whole component of relation and the other eSAOs denote Part components. Pattern 5 arises if an eSAO with Action field expressed in the original sentence by gerund VBG phrase is followed by an eSAO where Action field has a COMPRISE sense and is further followed by one or more eSAOs expressed by gerund phrases separated by or or other punctuation marks or conjunctions. The first eSAO is marked as the Whole eSAO and the other eSAOs starting from the third eSAO are marked as the Part eSAOs. Between at least three eSAOs mentioned above there may be other so called attributive eSAOs that may be marked as eSAO attributes if necessary. In this pattern the COMPRISE Action sense is a non terminal symbol at least matching words or phrases comprise include contain incorporate consist of Table 14 shows the generic form of Pattern 5 not including attributive eSAOs.

For example the set of eSAOs extracted from the input sentence of Creating a data flow includes the following steps adding one or more sources to extract data from files and databases adding the transformations that meet the business requirements is shown in Table 15.

Because all these eSAOs meet the conditions of Pattern 5 the following Whole Part relation is obtained 

Pattern 6 arises if an eSAO with an Action field expressed in the original sentence by clause of condition IF clause introduced by conjunctions where at least if when is followed by an eSAO that has an Action field with a PERFORM sense and is further followed by one or more eSAOs separated by or or other punctuation marks or conjunctions. The first eSAO is marked as the Whole eSAO and the other eSAOs starting from the third eSAO are marked as the Part eSAOs. In this pattern the PERFORM Action sense is a non terminal symbol at least matching words or phrases follow complete do perform take. Table 16 shows the generic form of Pattern 6.

For example the set of eSAOs extracted from the input sentence of When initially creating an extension take the following steps coordinate the use of extension with the vendor write an extension specification is shown in Table 17.

Because all these eSAOs meet the conditions of Pattern 6 the following Whole Part relation is obtained 

Pattern 7 arises if an eSAO with an Action field expressed in the original sentence by an infinitive phrase introduced by particle to or at least phrase in order to is followed by an eSAO where Action field has a PERFORM sense and is further followed by one or more eSAOs separated by or or other punctuation marks or conjunctions. The first eSAO is marked as the Whole eSAO and the other eSAOs starting from the third eSAO are marked as the Part eSAOs. In this pattern the PERFORM Action sense is a non terminal symbol at least matching words or phrases follow complete do perform take. Table 18 shows the generic form of Pattern 7.

For example the set of eSAOs extracted from the input sentence of To change your margins in Microsoft Internet Explorer follow these steps Click on the File menu Select Page Setup is shown in Table 19.

Because all these eSAOs meet the conditions of Pattern 7 the following Whole Part relation is obtained 

Preferably the function of the Relation Recognizer is carried out manually by experts. For example an expert analyzes the sentence The engine is located inside the car from eSAO Text Corpus where the Linguistic Analyzer performed part of speech tagging parsing and semantic analysis and recognized an eSAO see Table 13 and puts special tags that indicate that Object and IndirectObject of this eSAO form a Whole Part relation where IndirectObject is the Whole component of the relation and Object is the Part component. Such distribution of roles is possible based on the sense of the preposition inside. Then this sentence goes to the Pattern Generator .

The Pattern Generator performs analysis and generalization of the Whole Part relations to the level of patterns. The function of the Pattern Generator is also preferably carried out manually by experts. In this way an expert takes into consideration his or her own experience and knowledge as well as the knowledge contained in Linguistic Knowledge Base. Returning to the previous example the expert should come to a conclusion that preposition within has meaning similar to the preposition inside and at least verbs situate contain position dispose fix install mount house have meaning similar to that of the verb locate. Therefore the expert registers the prototype of the pattern in the way represented in Table 12.

The Pattern Tester using prototypical patterns looks for the examples of Whole Part relations in eSAO Text Corpus. The expert analyzes the retrieved examples and approves the pattern possibly with some corrections . The Pattern Tester then puts this approved pattern into the Data Base of patterns for Whole Part recognition.

As indicated above both the Semantic Analyzer and the Pattern Generator may access the Linguistic Knowledge Base for the performance of their functions. Further in some embodiments the Data Base of patterns may be incorporated within the Linguistic Knowledge Base to support the Whole Part semantic processing described above with respect to .

Embodiments in accordance with aspects of the present invention can be provided by computer executable instructions resident on one or more computers microprocessors microcontrollers or other processing devices. The computer executable instructions for executing the system and method can be resident in memory in the processing devices or may be provided to the processing devices by floppy disks hard disks compact disk CDs digital versatile disks DVDs read only memory ROM or any other storage medium.

The foregoing Detailed Description of exemplary and preferred embodiments is presented for purposes of illustration. It is not intended to be exhaustive nor to limit the invention to the precise form s described but only to enable others skilled in the art to understand how the invention may be suited for a particular use or implementation. The possibility of modifications and variations will be apparent to practitioners skilled in the art having understood the disclosure herein. No limitation is intended by the description of exemplary embodiments which may have included tolerances feature dimensions specific operating conditions engineering specifications or the like and which may vary between implementations or with changes to the state of the art and no limitation should be implied therefrom.

This disclosure has been made with respect to the current state of the art but also contemplates advancements and that adaptations in the future may take into consideration those advancements namely in accordance with the then current state of the art. It is intended that the scope of the invention be defined by the Claims as written and equivalents as applicable. Moreover no element component nor method or process step in this disclosure is intended to be dedicated to the public regardless of whether the element component or step is explicitly recited in the Claims. No claim element herein is to be construed under the provisions of 35 U.S.C. Sec. 112 sixth paragraph unless the element is expressly recited using the phrase means for . . . and no method or process step herein is to be construed under those provisions unless the step or steps are expressly recited using the phrase step s for . . . 

