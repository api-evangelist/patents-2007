---

title: Generating specialized search results in response to patterned queries
abstract: Third party content providers can specify parameters for generating specialized search results in response to queries matching specific patterns. In this way, a generic search website can be enhanced to provide specialized search results to subscribed users. In one embodiment, these specialized results appear on a given user's result pages only when the user has subscribed to the enhancements from that particular content provider, so that users can tailor their search experience and see results that are more likely to be of interest to them. In other embodiments the specialized results are available to all users.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=07593939&OS=07593939&RS=07593939
owner: Google Inc.
number: 07593939
owner_city: Mountain View
owner_country: US
publication_date: 20070330
---
This patent application claims priority from U.S. Provisional Patent Application Ser. No. 60 790 319 filed Apr. 7 2006 for Specifying Output Generation in Response to Patterned Queries which is incorporated herein by reference.

The present invention is related to display of specialized search results and more particularly to mechanisms to allow third party content providers to create enhancements to a search result page triggered on queries matching certain patterns.

When users search for websites and other information on the Internet they may not always obtain the desired results. In many cases users must carefully formulate their queries in order to obtain the information they are seeking. Some users particularly novice users do not have the skills expertise knowledge experience or patience to formulate a query that will yield the desired information.

Website authors on the other hand often have such expertise and are able to formulate queries that will provide information likely to be of use to visitors of those websites. Specialized search functionality often appears on websites allowing visitors to those websites to see search results tailored to the particular content they are likely to be interested in based on the fact that they are searching from that website. For example a website devoted to traffic information can interpret a query such as Interstate 280 differently than a general purpose search site would provide. The fact that a user is visiting the traffic information website means that he or she is interested in traffic information.

However it is not always convenient for users to visit a particular website in order to perform such a specialized search. Users may wish to perform all or most of their searches on a general purpose search site such as www.google.com without having to visit different websites to perform different searches. Accordingly it would be useful if third party content providers could enable specialized searches on general purpose search sites.

Furthermore different users have different preferences needs and interests. Some users might be interested in searches relating to television shows while other users may be interested in searches relating to weather around the world. It would be beneficial therefore for users to have the ability to specify which types of specialized searches they are interested in so that specialized search results could be tailored to those affirmed areas of interest.

The present invention allows third party content providers to create enhancements to a search result page triggered on queries matching certain patterns. In one embodiment these specialized results will appear on a given user s result pages only when the user has subscribed to the enhancements from that particular content provider so that users can tailor their search experience and see results that are more likely to be of interest to them.

In response to a query matching a given pattern the system of the present invention generates one or more of the following 

An application programming interface API allows third party content providers to specify parameters for including their specialized results in search result pages. The content providers can thus particular types of information to be displayed in particular formats in response to certain kinds of queries.

The content provider specifies parameters i.e. what type of search query will trigger retrieval of content from that provider. The content provider also specifies how the search query will be parsed and how the extracted query terms will be used to retrieve content. Finally the content provider specifies how the retrieved content will be displayed in the user s browser window. In one embodiment users can select which types of specialized search results they wish to receive and add them to their results pages in order to enhance their search experience with the third party content.

The Figures depict a preferred embodiment of the present invention for purposes of illustration only. One skilled in the art will readily recognize from the following discussion that alternative embodiments of the structures and methods illustrated herein may be employed without departing from the principles of the invention described herein.

In the following description the term subscribed link is used to refer to a mechanism by which the user can indicate that he or she is interested in receiving a particular category of search results. The category of search results is usually based on some query pattern as described in more detail below. The term subscribed refers to the fact that the user can freely opt in or out of the search results category in effect turning on or off the subscription.

In one embodiment however the search results category can be provided to all users. Alternatively the search results category can be provided to some users based on some criteria such as browser platform OS platform geographical location search history demographics website visitation history or the like . In effect then those users for which the criteria apply can be auto subscribed to certain links. In one embodiment users are free to opt out after they have been auto subscribed in other embodiments they may not have the freedom to do so.

In the following description the term specialized result refers to any result that is generated by the patterned query response mechanism described herein whether or not the initiating link is a subscribed link.

Referring now to there is shown an example of a system for practicing the present invention. One skilled in the art will recognize that the architecture shown in and described herein is presented for illustrative purposes only and that the present invention can be practiced with other architectures as well.

Referring also to there is shown an example of a method for practicing the present invention according to one embodiment.

In one embodiment the present invention is implemented using a data server or collection of data servers . These servers store knowledge base data and query result specification files submitted by various content providers. The format and function of these specification files are described in further detail below.

Using client a logged in user enters a query at a search website which may be a general purpose search site such as www.google.com. In one embodiment the user is logged in so that he or she can be identified and so that a determination can be made as to which if any links the user has subscribed to. The user s query is sent to a front end server . The front end server passes the request to one or more trust servers which perform the following steps 

First the trust server retrieves a list of the content providers which the user trusts enough that specialized results from them should be presented to the user. This includes all explicit direct subscription decisions the user has made. In one embodiment it may also include indirect trust relations and or experimental recommendations. List includes provider feed URLs so that the data for subscribed links can be obtained from the appropriate source.

For each provider in the list the trust server sends a request to the appropriate data server to get specialized results for that content provider for the query . Data servers can be sharded according to well known techniques.

Specialized results are returned to trust server which renders the results in an HTML form and sends the HTML rendered results to front end server . In one embodiment this rendering is performed by a component external to trust server . For example the rendering may be performed by a renderer not shown implemented as a library linked into the trust server alternatively it can be implemented as a call out to a server such as for example a Google Gadgets server in order to support close integration with an API such as the Google Gadgets API. The renderer handles decisions such as for example what to display if the total number of specialized results returned is too large to fit them all in the available display space. One skilled in the art will recognize that the results need not be formatted in HTML but that any other format can be used.

Once the rendered results are provided to the front end server they are relayed to search site for drop in display by search site possibly along with other search results . Search site generates a results page and transmits it to a browser running at the client . The client browser then displays the results for the user. As shown in the examples described below the specialized rendered results can be displayed in a visually distinct manner such as within a shaded box so as to distinguish them from ordinary search results alternatively no special visual distinction can be made.

Each individual data server when it receives a call to provide specialized results for a given query and provider processes the query according to the list of specialized results for that provider extract appropriate knowledge base elements. The data server formats the results according to the output templates specified by the provider.

The subscriber provider server allows users to subscribe to and unsubscribe from specialized results offered by particular content providers and also allows providers to upload the locations of XML files defining their specialized results.

Feed crawl server handles loading of actual XML data files from content providers websites based on a list of provider feed URLs received from subscriber provider server . The feed crawl server converts XML into an internal protobuffer format used by the data servers . The feed crawl server validates the data and sends updates to data server shards when the data changes. Load requests are generated when a data server receives a request for subscribed links from a provider it does not have in its memory. The data server sends the load request to the feed crawl server so that the feed crawl server will fetch the data for that provider.

Changes to user subscription information are handled by a trust relations server architecture. When a provider s information changes the feed crawl server broadcasts update requests to the front end servers which then passes them onto the appropriate data server shards.

The front end server has the following responsibilities with respect to the data server shards it controls 

The architecture shown in and the method shown in will be further described in the context of several examples. However the particular features of the examples are intended to be illustrative rather than limiting. One skilled in the art will recognize that the invention can be practiced in different ways.

In one embodiment the present invention is implemented as an Application Programming Interface API that allows third parties to specify parameters for displaying specialized information in response to particular queries. The parameters may be provided for example in the form of an XML file.

In one embodiment the content provider defines one or more ResultSpecs tags. A ResultSpec tag contains a Query tag and a Response tag. The Query tag provides a general trigger pattern of queries that will cause the content provider s results to be obtained and displayed. The Response tag provides a template for the display of the content provider s results when the trigger pattern is satisfied.

The ResultSpec tag can also have an id attribute to uniquely identify the ResultSpec. In one embodiment every ResultSpec has an id attribute.

For example the following specification would display a Hello World informational message whenever the user enters the query subscribed links 

In this example the ResultSpec tag has an id of InfoMatch. The Query tag specifies that the result will display in response to one specific query namely subscribed links . On any other query the result will not display. Each Output tag has a name attribute that specifies the place where that particular part of the output will appear in the displayed result. The output named title will be the anchor text for a title link the more url output gives the URL which that link points to and the text1 text2 text3 outputs define three lines of body text.

Referring now to there is shown an example of a result screen generated by the code of the above example in response to query . The specialized search result is shown in a highlighted box which distinguishes specialized result from other results . The words Subscribed Link in the upper right corner of the result indicate that users must subscribe in order to see this specialized result . In one embodiment a user must subscribe in order to indicate that he or she would like that content provider s specialized results to appear on his or her result pages in another embodiment there is no requirement for the user to subscribe.

Edit link allows the user to edit his or her list of subscribed links. Remove link allows the user to remove the subscribed link that produced specialized result .

It can be seen from that the text shown in result is generated based on the Output tags presented in the above example of a ResultSpec tag.

Referring now to there is shown a flowchart depicting an example of the user s experience in interacting with the system of the present invention according to one embodiment. The user configures search results to include specialized results as follows. First the user signs on with a login and password so that he or she can be identified. In one embodiment cookies can be used to store login information including password if desired on the user s machine so that manual login is not needed for each session. The user then visits a web page that includes a directory of subscribed links that users can add to their search results. The user selects an entry in the directory by clicking on it to subscribe to one of the subscribed links.

As mentioned above in some cases users can be automatically subscribed to certain subscribed links categories of query results based on any desired criteria.

Once the user has subscribed to a link or once he or she has been auto subscribed the user is taken to a profile page. Here he or she can specify additional parameters and options and can confirm that he or she wants to subscribe.

Subsequently when the user enters a search query that matches the specified parameters the relevant information is retrieved and a results page is shown that includes the content provider s results as shown in and according to the method described above in connection with .

If the user does not want to see specialized search results of a particular kind in the future he or she clicks on the remove link in the lower right corner of the result box in order to unsubscribe from a particular subscribed link.

As illustrated in the above example the Query item in the XML file defines the set of queries for which the specialized results will appear. In the above example the pattern is very restrictive it will only trigger on a single particular query. Theoretically the content provider could write a separate ResultSpec for each individual query that is to trigger a specialized result. Generally however it is more efficient to specify a pattern that when matched will cause specialized results to be displayed. To create more powerful query patterns the content provider can use types in the Query item and attributes in constructing the corresponding Response. The types refer to DataObjects which are discussed below.

For example suppose the content provider wishes to report speed limits on various highways. The content provider would like to have essentially the same result format for any query of the form speed limit on X where X is the name of a highway. The particular result would depend on the value of X the name of the highway . To do this the content provider can define a number of supporting DataObjects of type Highway each with an attribute called max speed limit giving the maximum speed limit on the highway. Then the content provider can define a Query and Response like this 

Here DataObjects in the Query are denoted by type names enclosed in brackets. In one embodiment type names are case sensitive.

In the Output lines of the Response the content provider can refer to attributes of the extracted DataObjects which are numbered starting from 0. These attribute references are also enclosed in brackets and are also case sensitive.

To make the HighwayMatch Query and Response actually work the content provider defines some DataObjects of type Highway. One such object might look like this 

Referring now to there is shown an example of a results screen including a specialized result . This example assumes that the content provider has generated an XML file containing both the ResultSpec and the DataObject as described above. The specialized search result is shown in response to query . A result similar to will be shown when the user searches on either speed limit on 101 or speed limit on US 101 because both of 101 and US 101 will match the Highway object that was defined. To make results display for more speed limit queries the content provider can define more DataObjects of type Highway and does not have to add anything more to the ResultSpec.

The specialized result in is generated as follows. Query speed limit on 101 matches the Query tag speed limit on Highway since a data object of type Highway has been defined as matching QueryName 101 . The data object specifies other attributes for Highway101 including a full name US Route 101 an abbreviation US101 and a speed limit 65 MPH . The Output tags in the ResultSpec indicate a format for including these attributes along with accompanying text in the displayed specialized result .

To complete the XML file that specifies Subscribed Links the content provider adds a top level Results tag. The content provider can also add an AuthorInfo tag giving some information about the author of the specification or of the content provider. The following is an example of a complete file 

As shown in the examples above in one embodiment a standard result format includes a title link and up to three lines of body text. In one embodiment all HTML tags in the Output specification are automatically formatted accordingly. In one embodiment output lines exceeding a character length limit are automatically clipped.

Besides the title link the content provider can also include additional links in the body of the result if desired. To do this the content provider can specify a link for each line by adding more Outputs to the Response. The names of the Outputs are link1 link2 link3 for the links anchor text and url1 url2 url3 for the links URLs . The number 1 2 or 3 controls which line of the body text the link s will appear on. For example to provide just one link in the body but on the third line then the Output names associated with that link should be link3 url3.

The content provider can specify links for some of the lines leave some plaintext only or omit the plaintext entirely from a line leaving only the link.

By default the body links will appear to the left of the text on each line. To change this the content provider can set the format attribute of the Response tag to answer right. So for example 

will produce on the query result format the output shown in screen shot of including links and link text . Alternatively if the attribute format answer right were omitted from the Response tag the links on the first two lines would display to the left of the snippets of text .

In some embodiments any or all of the following features can also be provided singly or in any combination.

When the content provider submits a URL for the XML file defining its Subscribed Links the form actually allows the content provider to specify more than one URL. If more than one is specified the Subscribed Links will trigger based on the combined data from all the specified URLs. This can be useful for example if it desired to reuse lists of DataObjects created by others.

For example if a content provider has an XML file containing a list of DataObjects of type Highway and a separate XML file containing the ResultSpecs that use that list then the first file can be made publicly available so that other content providers can use the existing list of DataObjects of type Highway.

In the above examples the bracket characters are used to set off types of extracted elements in Queries and attributes of extracted elements in Responses. If the content provider wishes to include these characters in the output or Query pattern he or she can do so by prefixing the character with backslash .

In one embodiment a number of common object types are available for use in Query patterns. By using one of these object types the content provider avoids the need to provide his or her own DataObjects. Examples of such common object types include without limitation 

Cities. The element specification City will match names of cities and towns in North America given by city name with state or for larger cities by city name alone. So for example 

will match queries like elevation of San Francisco elevation of Springfield Ill. etc. The resultant extracted objects will have the following attributes which can be used in Responses 

Regular expression matches. In one embodiment the system of the present invention supports Perl Compatible Regular Expressions PCREs according to a standard format. The content provider can specify a regular expression to match in a query by prefixing it with RE . The attributes of the resultant object are the match groups of the regular expression they are named gr0 gr1 and so on. So for example 

will match queries like 127.0.0.1 subnet . Referring now to there is shown an example of a results screen including a specialized search result generated based on a regular expression wherein query matched the regular expression.

Dates. The element types date timeofday and timerange will match respectively dates times of day and time ranges in US English format. So for example 

will match queries of the form sunset on X where X is a date. The matcher is flexible enough to recognize different date formats so sunset on Nov. 22 2005 and sunset on October 16th will both match.

In addition to specifying objects to be found in the query itself the content provider may specify additional elements to be obtained given those already found. To specify an additional extracted element the content provider adds an Extract tag to the ResultSpec that gives type name and an extraction specification. The extraction specification uses attributes of already extracted elements in the same way that a Response does to construct a string and then matches that string against the QueryNames of objects of the given type.

This would trigger on the query population of San Francisco in 2000 attempt to extract an additional DataObject of type CityPopulationData named pop SanFranciscoCA2000 and display the result.

Referring now to there is shown an example of a results screen wherein the specialized result contains the additional extracted elements described above.

The content provider can include as many additional extracted objects as he or she wishes and each one can use the attributes of all previous ones in constructing its extraction specification.

The content provider can use a Validate tag to restrict the set of queries on which a Response will be displayed. A Validate tag works much like an Extract tag it uses two strings the source and destination which are populated using attributes of extracted elements. These two strings are then compared and the Response will display only if they are equal.

With the definitions above a result will trigger on the queries frequency of KQED in California and frequency of WMHT in New York but not on frequency of KQED in New York . The reason is that the values for 0.state and 1.fullname must match in order for the specialized result to be triggered. This helps prevent ill advised attempts to generate specialized results based on nonsensical combinations of terms. Since the state for KQED is California and the state for WHMT is New York the query will only match when the full name of the state as entered in the query matches the state for the radio station entered.

There are some circumstances where it is useful to have the value of an Attribute of a DataObject be not a string literal but a reference to another DataObject. The content provider can specify this by setting the Attribute s value equal to the ID of the DataObject to be referred to and using multilevel attribute references multiple attribute names separated by periods in the Response accordingly. For example 

This will trigger on the query population KQED and produce the output as shown in results screen of . The output tag specifies that 0.state.population should be displayed. This resolves to the population of the state associated with the record on which the query matched. Since the query was Population KQED the term KQED maps to RadioStation . The state for that data object is CaliforniaState which is an ID for another data object. Thus to resolve 0.state.population the CaliforniaState ID is consulted which shows a value for population of 36 000 000 . That value is then displayed.

In one embodiment the present invention is also able to analyze query and suggest alternative queries to the user. This can be implemented for example by comparing the entered query with an index of results terms and selecting likely alternative query forms that a are similar to the entered query and b would yield higher numbers of results if entered. In one embodiment the alternative queries are presented as a clickable link that the user can activate if he or she is not satisfied with the displayed specialized links and regular links.

In one embodiment users can be automatically subscribed to a search results category based on some criteria such as browser platform OS platform geographical location search history demographics website visitation history or the like . In effect then those users for which the criteria apply can be auto subscribed to certain links. For example a user who tends to search for information at automotive sites can be automatically subscribed to a search results category related to automobiles.

In one embodiment users are free to opt out after they have been auto subscribed in other embodiments they may not have the freedom to do so.

In one embodiment the content provider can test the operation of ResultSpecs before releasing them to ensure that they trigger on the queries you expect them to and display the correct output. To do this for a particular ResultSpec the content provider adds the attribute test true to the ResultSpec tag as in this example 

Then the result specified by this ResultSpec will display when a specific user such as the content provider him or herself logs in to his or her Google Account and does a search matching the Query but not when any other user who has added that content provider s Subscribed Links does searches.

In one embodiment to ensure fairness any given ResultSpec is only allowed a certain fixed amount of calculation time per query.

These steps are all performed by writing an XML file as described above. Also supported is the ability to extract additional elements using strings derived from the elements matched so far and also a validation step where a string generated from matched elements is compared to an expected value before output generation is allowed to proceed.

In one embodiment the system of the present invention also provides the capability to perform richer calculations on attributes of matched elements in a manner or to write more complex algorithms for making query trigger decisions. Third parties can write their own code for these purposes. In one embodiment only highly trusted third parties are given permission to submit such transforms.

In one embodiment the present invention is implemented using a number of datacenters. Each datacenter has a full complement of servers including data server shards supporting front end servers and Prose trust servers at least one feed crawler and at least one front end server.

Latency penalty is controlled by sending queries for specialized results at the very beginning of the query cycle even before spell correction and query rewriting since only the raw query is required.

In one embodiment sharding of specialized data is performed by content provider since each content provider has a distinct set of knowledge base data that to be accessed when matching queries for that provider s specialized results. Two sets of data server shards are provided one for specialized results provided by the operator of the system or by trusted third parties and the other for general untrusted content providers. Sharding is distinct from replication here each shard handling a certain set of providers is replicated at least twofold for load balancing and fault tolerance purposes and trusted shards may need a different presumably higher degree of replication than untrusted shards.

Assigning a content provider can be done simply by modding the provider s ID by the number of shards of its type trusted or untrusted . This should work fine going forward for untrusted providers as random distribution of IDs will ensure a good spread of providers across shards and each provider s data size will be limited. Alternatively for trusted providers in one embodiment special sharding rules are implemented as some providers may need to submit so much data that they will crowd other providers out of their shards. In one embodiment multiple provider IDs are provided for some providers whose data sizes are so large as to require them to be split across multiple machines.

In one embodiment as space fills up old provider data from memory is deleted in order to fit in new data in response to queries shards flush providers from memory on a least recently used basis. In some cases the system may stop allowing new untrusted providers until more machines are available.

A request for specialized results consists of a query and a set of content providers. For each content provider listed the query is matched against all trigger patterns for that content provider. For this purpose a structure is maintained called a OneboxSet for each content provider. When doing the matching for a particular content provider the system makes reference to the knowledge base objects that content provider has defined thus the knowledge base structure called a KB is divided into KBSegments each KBSegment representing the objects defined by one content provider.

For each trigger pattern a content provider specifies the system determines whether a given query matches that particular pattern and finds the conceptual objects corresponding to parameters specified in the pattern. To encapsulate this process abstract base classes ObjectMatcher and MatchedObject are defined. An ObjectMatcher corresponds to a particular type of conceptual object its Match routine decides whether a given string has a prefix matching an object of that type and if so outputs a MatchedObject. MatchedObjects are essentially attribute name value maps to use an attribute of an object in constructing the results of a triggering query MatchedObject GetAttribute is called.

The core work of matching queries is then done by subclasses of ObjectMatcher. LiteralKeywordMatcher checks that a string has a prefix literally equal to some given keyword or keyphrase. The one likely to be most commonly used is KBObjectMatcher which operates by looking up tokenized prefixes of a query in a hash table of knowledge base objects. Special purpose matchers are provided for regular expressions and for dates and times.

In order to speed up the matching process in one embodiment a hash table is created for each provide. The keys of the hash table are the literal prefixes of the corresponding trigger patterns. For example for the trigger pattern flights from City to City the literal prefix is flights from . Then when matching a query against a provider s set of trigger patterns the system of the present invention considers those whose literal prefix matches a prefix of the query.

As discussed above in one embodiment the feed crawl server uses a standard web crawling mechanism to crawl the XML files that content providers specify as the locations of their data parse these files and if the parse is successful place the resulting data in its in memory LRU least recently used cache. The feed crawler gets its crawling jobs in three ways. First when a data server shard receives a GetProseOneboxes request demanding data from a content provider it does not have in its memory it issues a load request. Second when a provider submits a new XML file location for specialized data the feed crawler reloads that provider s data into its in memory cache. Third the feed crawler periodically polls providers XML files for updates broadcasting UpdateOneboxData requests when it detects new data the polling schedule is determined by how often the provider has gotten into the cache previously.

Thus the data server shards function as a first level cache and the feed crawler s memory as a second level cache for the data ultimately stored on the content providers websites in XML format.

In one embodiment a query to a data server shard will only return specialized results if the specialized data for the specified content provider is in the data server shard s memory at the time of the query. When the data server issues a load request for content provider data it does not have it will not wait for the load to happen before trying to return specialized results for the query that provoked the load request. Thus a user may occasionally fail to get specialized results if he or she happens to be the first person to submit a query.

In one embodiment the present invention is implemented in such a manner as to counter certain security threats. Examples of such threats include 

To deal with issue 1 in one embodiment the system of the present invention escapes all output strings from untrusted providers completely. Lengths of output strings are limited so as to prevent excessive space consumption on the page as well as overflow attacks. These limitations may be relaxed or eliminated for more trusted providers as long as they go through a review process in which their initial specifications and data are scrutinized.

To deal with issue 2 in one embodiment the data server shards are subject to timeouts after a certain number of milliseconds processing a given query a shard will just stop and return whatever results it has for that query. Likewise after a certain number of milliseconds waiting for data server shards to return results from a GetProseOneboxes request the front end server simply aggregates whatever results it has gotten so far and passes these back to the requester.

In one embodiment a sharding policy is put into place as described above to ensure that specialized results which have been promoted to show all users or which come from more highly trusted providers are on separate shards from those carrying completely untrusted providers data. In this manner their processing times for trusted providers are not affected by possible bad behavior of untrusted providers. Also in one embodiment if queries to a provider s data time out too often that provider is deactivated for at least some period of time so as to allow other providers data to trigger. Also in one embodiment fairness policies are enforced on the feed crawler end so that no one provider can take up too much update traffic.

As to issue 3 in one embodiment content providers can track most subscriptions to their specialized search results. The content providers therefore know how often users click through to their sites via their specialized search links.

A further line of defense against all issues above is that all untrusted content provider search results can be set up as opt in. Users take positive action to subscribe to them i.e. trust their providers before they can be displayed. Furthermore users can easily unsubscribe from content providers they find give them bad results and can report spam deception copyright violations and the like.

The present invention has been described in particular detail with respect to one possible embodiment. Those of skill in the art will appreciate that the invention may be practiced in other embodiments. First the particular naming of the components capitalization of terms the attributes data structures or any other programming or structural aspect is not mandatory or significant and the mechanisms that implement the invention or its features may have different names formats or protocols. Further the system may be implemented via a combination of hardware and software as described or entirely in hardware elements. Also the particular division of functionality between the various system components described herein is merely exemplary and not mandatory functions performed by a single system component may instead be performed by multiple components and functions performed by multiple components may instead be performed by a single component.

Some portions of above description present the features of the present invention in terms of algorithms and symbolic representations of operations on information. These algorithmic descriptions and representations are the means used by those skilled in the data processing arts to most effectively convey the substance of their work to others skilled in the art. These operations while described functionally or logically are understood to be implemented by computer programs. Furthermore it has also proven convenient at times to refer to these arrangements of operations as modules or by functional names without loss of generality.

Unless specifically stated otherwise as apparent from the above discussion it is appreciated that throughout the description discussions utilizing terms such as calculating or determining or identifying or the like refer to the action and processes of a computer system or similar electronic computing device that manipulates and transforms data represented as physical electronic quantities within the computer system memories or registers or other such information storage transmission or display devices.

Certain aspects of the present invention have been described using commands mnemonics tokens formats syntax and other programming conventions. The particular selections of the names formats syntax and like are merely illustrative and not limiting. Those of skill in the art can readily construct alternative names formats syntax rules and so forth for defining context files and programming the operations a programmable search engine via context processing.

Certain aspects of the present invention include process steps and instructions described herein in the form of an algorithm. It should be noted that the process steps and instructions of the present invention could be embodied in software firmware or hardware and when embodied in software could be downloaded to reside on and be operated from different platforms used by real time network operating systems.

The present invention also relates to an apparatus for performing the operations herein. This apparatus may be specially constructed for the required purposes or it may comprise a general purpose computer selectively activated or reconfigured by a computer program stored on a computer readable medium that can be accessed by the computer. Such a computer program may be stored in a computer readable storage medium such as but is not limited to any type of disk including floppy disks optical disks CD ROMs magnetic optical disks read only memories ROMs random access memories RAMs EPROMs EEPROMs magnetic or optical cards or any type of media suitable for storing electronic instructions and each coupled to a computer system bus.

The algorithms and operations presented herein are not inherently related to any particular computer or other apparatus. Various general purpose systems may also be used with programs in accordance with the teachings herein or it may prove convenient to construct more specialized apparatus to perform the required method steps. The required structure for a variety of these systems will be apparent to those of skill in the art along with equivalent variations. In addition the present invention is not described with reference to any particular programming language. It is appreciated that a variety of programming languages may be used to implement the teachings of the present invention as described herein and any references to specific languages are provided for disclosure of enablement and best mode of the present invention.

Finally it should be noted that the language used in the specification has been principally selected for readability and instructional purposes and may not have been selected to delineate or circumscribe the inventive subject matter. Accordingly the disclosure of the present invention is intended to be illustrative but not limiting of the scope of the invention which is set forth in the following claims.

